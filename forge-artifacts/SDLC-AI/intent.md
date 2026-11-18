# INTENT PROFILE

**Project:** SDLC-AI  
**Generated:** 2026-11-18T22:19:19.353Z

---

# Intent profile

**Status:** complete

**Artifact:** `d4b6adae-79f7-4f4e-833f-9c688f44513b`

**Goal:** Full Build

## Vision

Deliver a read-only Model Context Protocol (MCP) server — the IT-Standard MCP — that gives any MCP-compatible AI agent or IDE instant, versioned access to a curated catalog of agent SKILLs stored in a GitHub monorepo, enabling enterprise-wide skill discovery, retrieval, and governance with OAuth 2.0 security enforced at the API gateway.

## Target personas

- MCP Client / AI Agent — any MCP-compatible agent or IDE that discovers and retrieves versioned skills to augment its capabilities; needs fast, reliable, authenticated access to the latest or pinned skill content
- Skill Contributor — developer or standards author who forks the monorepo, creates or updates SKILL.md files following semantic versioning conventions, and opens PRs; needs clear naming rules, CI feedback, and a dev environment to test before promotion
- Admin / Skill Publisher — member of the it-standards-team listed in CODEOWNERS who reviews and merges PRs to dev and main branches; needs branch protection enforcement, CI validation, and confidence that immutability rules are upheld on main
- Consumer / End User — authenticated Intel employee who reads skills through the MCP via an agent or IDE; needs all skills to be discoverable and retrievable without per-group restrictions
- Platform / DevOps Engineer — operates the CaaS-hosted MCP server instances, Apigee proxy, cache infrastructure, and observability stack; needs stateless horizontal scaling, health endpoints, structured logs, and alerting

## Core features

- **Skill Discovery and Listing (list_skills)** (priority 1)
  - Description: Exposes a read-only MCP tool that returns all skills in the catalog, each with its name, description, tags, and computed latest version. The index is built from the GitHub monorepo tree and cached per branch HEAD SHA.
  - Acceptance: list_skills returns every skill folder present on the branch the MCP instance reads from
  - Acceptance: Each entry includes skill name, description, latest version number, and status
  - Acceptance: Latest version is computed as the highest semantic version (numeric comparison, e.g. 1.10.0 > 1.9.0)
  - Acceptance: Response is served from cache when the branch HEAD SHA has not changed
  - Acceptance: Deprecated skills are included in the listing with their status clearly marked
- **Exact Version Retrieval (get_skill)** (priority 1)
  - Description: Retrieves the full content of a specific SKILL.md by skill name and exact version string. The response includes the resolved version, commit SHA, branch, file path, status, and a deprecation warning if applicable.
  - Acceptance: get_skill requires both 'skill' (string) and 'version' (string) parameters
  - Acceptance: Returns the full SKILL.md content along with skill name, version, status, branch, commit_sha, and path
  - Acceptance: For deprecated versions, the 'warning' field contains a message like 'SDLC 1.0.0 is deprecated; latest is 2.0.0'
  - Acceptance: Returns VERSION_NOT_FOUND with available versions list if the version folder does not exist
  - Acceptance: Returns INVALID_VERSION if the version string does not match MAJOR.MINOR.PATCH format
  - Acceptance: Returns SKILL_NOT_FOUND with up to 5 similar names if the skill folder does not exist
  - Acceptance: Returns UPSTREAM_UNAVAILABLE (retryable) if GitHub is unreachable and the item is not in cache
- **Latest Version Retrieval (get_latest_skill)** (priority 1)
  - Description: Retrieves the content of the highest semantic version of a named skill without requiring the caller to know the version number. Returns the same response shape as get_skill, including the resolved version and commit SHA so the caller can pin it later.
  - Acceptance: get_latest_skill accepts only a 'skill' string parameter (no version)
  - Acceptance: Resolves 'latest' as the highest semantic version present on the branch (numeric comparison)
  - Acceptance: Response includes the resolved version number and commit_sha so callers can pin later
  - Acceptance: Deprecated versions are still eligible as 'latest' if they are the highest version, but the warning field is populated
  - Acceptance: Same error handling as get_skill for missing skills and upstream unavailability
- **Versioned Skill Repository Structure and CI Validation** (priority 1)
  - Description: Skills are stored in a GitHub monorepo (intel-innersource) with a strict folder convention: each skill has a folder, each version has a subfolder named SKILL-MAJOR.MINOR.PATCH containing exactly one SKILL.md with YAML frontmatter. CI checks enforce naming, format, frontmatter consistency, and immutability on main.
  - Acceptance: Skill folders use only letters, digits, and hyphens — no spaces
  - Acceptance: Version folders follow the pattern SKILL-<MAJOR>.<MINOR>.<PATCH> with strict semantic versioning
  - Acceptance: Each version folder contains exactly one file named SKILL.md
  - Acceptance: SKILL.md begins with YAML frontmatter containing name, version, description, owner, status, and tags
  - Acceptance: Frontmatter 'name' must match the skill folder name and 'version' must match the version folder
  - Acceptance: CI rejects invalid patterns such as SKILL-2.00, SKILL-v1, skill-1.0.0, SKILL-1.0
  - Acceptance: CI rejects any modification or deletion of existing version folders on main branch
  - Acceptance: CI runs secret scanning on skill content for both dev and main PRs
  - Acceptance: Optional: CI creates a git tag <skill>/<version> on merge to main
  - Acceptance: Version folders on main are immutable once merged; any fix requires a new version folder
  - Acceptance: Version folders on dev are editable while being tested before promotion to main
- **OAuth 2.0 Authentication via Apigee X and Microsoft Entra ID** (priority 1)
  - Description: All MCP requests are authenticated via OAuth 2.0 with Microsoft Entra ID as the identity provider. Apigee X is the single public entry point that validates JWTs, applies rate limits, and forwards identity headers (X-User-Id, X-Client-Id) to the MCP server. The MCP server itself does not validate tokens and must not be reachable except through Apigee.
  - Acceptance: Apigee X validates JWT tokens (issuer, audience, expiry, scope) before forwarding requests
  - Acceptance: Apigee forwards X-User-Id and X-Client-Id headers extracted from token claims
  - Acceptance: Unauthenticated requests receive 401 with WWW-Authenticate header containing the resource metadata URL
  - Acceptance: Apigee serves /.well-known/oauth-protected-resource returning Entra ID as authorization server and the required scope
  - Acceptance: Clients use a pre-registered Entra app registration (clientId) with scope api://it-standard-mcp/skills.read
  - Acceptance: All authenticated users can read all skills — no per-group restrictions
  - Acceptance: CaaS ingress is private or restricted to Apigee egress addresses only
  - Acceptance: Apigee-to-MCP traffic uses mTLS or a shared secret header to reject bypass attempts
  - Acceptance: Dynamic Client Registration is not supported; onboarding docs list clientId, tenant, and scope
- **Skill Search (search_skills)** (priority 2)
  - Description: Provides a search tool that accepts a query string and returns skills whose name, description, or tags match. Enables agents to find relevant skills by topic without knowing exact names.
  - Acceptance: search_skills accepts a single 'query' string parameter
  - Acceptance: Matching is performed against skill name, description, and tags fields from YAML frontmatter
  - Acceptance: Results include the same metadata as list_skills (name, description, latest version, status)
  - Acceptance: Empty or no-match queries return an empty result set, not an error
- **Version Listing (list_versions)** (priority 2)
  - Description: Returns all available versions of a named skill with their status (active or deprecated), enabling agents and users to browse version history before pinning a specific version.
  - Acceptance: list_versions accepts a 'skill' string parameter
  - Acceptance: Returns all version folders found under the skill folder, each with version number and status
  - Acceptance: Versions are ordered by semantic version (highest first)
  - Acceptance: Returns SKILL_NOT_FOUND error with up to 5 similar skill names if the skill folder does not exist
- **Caching with Poll-Based Change Detection** (priority 2)
  - Description: The MCP server caches the skill index and skill content to reduce GitHub API calls and latency. Change detection is performed by polling the branch HEAD commit SHA every 60 seconds using conditional requests with ETag. No webhooks are used.
  - Acceptance: MCP polls the branch HEAD SHA every 60 seconds using conditional GET with ETag
  - Acceptance: Unchanged responses (304 Not Modified) do not count against GitHub rate limit
  - Acceptance: When SHA changes, the skill index is rebuilt from the repo tree at the new SHA
  - Acceptance: Latest version per skill is recomputed on each index rebuild
  - Acceptance: Skill index is cached with key index:<branch>:<sha> and invalidated when SHA changes
  - Acceptance: Skill content on main is cached indefinitely (immutable) with key skill:main:<skill>:<version>
  - Acceptance: Skill content on dev is cached with key skill:dev:<skill>:<version>:<sha> and invalidated when SHA changes
  - Acceptance: A new push becomes visible within one polling interval (~60 seconds)
  - Acceptance: If GitHub is unavailable, MCP continues serving from cache
  - Acceptance: UPSTREAM_UNAVAILABLE is returned only for items never previously cached
  - Acceptance: Multiple replicas either share a cache (e.g. Redis) or poll independently
- **Dual Environment Deployment (Production and Dev)** (priority 2)
  - Description: Two MCP server instances run the same container image with different configurations: it-standard (production, reads main branch) and it-standard-dev (reads dev branch). Apigee routes to each via distinct proxy paths.
  - Acceptance: Both environments run the identical container image; only environment variables differ
  - Acceptance: it-standard reads from the main branch and is exposed at /it-standard/mcp
  - Acceptance: it-standard-dev reads from the dev branch and is exposed at /it-standard-dev/mcp
  - Acceptance: Configuration is driven by environment variables: GITHUB_BRANCH, POLL_INTERVAL_SECONDS, CACHE_URL, etc.
  - Acceptance: GitHub App credentials are stored in CaaS secrets, not in the container image
  - Acceptance: it-standard-dev serves newly merged skills within ~60 seconds for testing before promotion to main
- **MCP Streamable HTTP Transport** (priority 2)
  - Description: The MCP server uses Streamable HTTP as its transport protocol. The Apigee proxy must allow streaming responses with adequate timeouts. The server is stateless with no session state, enabling horizontal scaling on CaaS.
  - Acceptance: MCP server implements Streamable HTTP transport per the MCP specification
  - Acceptance: Apigee proxy is configured to allow streaming responses with adequate timeouts
  - Acceptance: Server maintains no session state — fully stateless for horizontal scaling
  - Acceptance: GitHub access uses a GitHub App (preferred) or fine-grained token with read-only contents permission
  - Acceptance: Credentials are stored in CaaS secrets
- **Publishing Workflow with Branch Protection** (priority 3)
  - Description: A contributor-driven publishing workflow where contributors fork the repo and open PRs to dev, admins review and merge, skills are tested on the dev MCP, and then admins promote from dev to main. Branch protections enforce PR requirements, admin approval, and CI passage.
  - Acceptance: Contributors fork the repo and open PRs; they cannot merge directly
  - Acceptance: Admins (listed in CODEOWNERS) are required reviewers for all paths
  - Acceptance: Branch protection on main and dev requires: PR, admin approval, CI pass, no direct pushes
  - Acceptance: The workflow is: fork → PR to dev → CI + admin review → merge to dev → test on dev MCP → PR dev→main → merge to main → served on production MCP
  - Acceptance: CODEOWNERS file assigns admins as required reviewers
- **Observability, Health Checks, and Alerting** (priority 3)
  - Description: The MCP server exposes health endpoints and emits structured logs for every tool call, including user identity, skill/version details, cache hit/miss, and latency. Alerts are configured for index refresh failures, GitHub errors, and elevated 5xx rates.
  - Acceptance: /healthz endpoint returns liveness status
  - Acceptance: /readyz endpoint returns ready only after the first skill index is loaded
  - Acceptance: Every tool call is logged with: timestamp, tool name, skill, requested version, resolved version, X-User-Id, X-Client-Id, environment, branch, commit SHA, cache hit/miss, latency, result
  - Acceptance: Alert fires when index refresh fails for more than 10 minutes
  - Acceptance: Alert fires when GitHub error rate exceeds threshold
  - Acceptance: Alert fires on elevated 5xx rate at Apigee
  - Acceptance: Logs support analysis of which skills and versions are used to inform deprecation decisions

## In Scope

- Read-only MCP server implementing five tools: list_skills, search_skills, list_versions, get_skill, get_latest_skill
- Versioned skill storage in GitHub monorepo with SKILL-MAJOR.MINOR.PATCH folder convention
- SKILL.md format with YAML frontmatter (name, version, description, owner, status, tags)
- OAuth 2.0 authentication flow with Microsoft Entra ID and Apigee X gateway
- Poll-based cache invalidation using branch HEAD SHA with 60-second interval
- Dual environment deployment: it-standard (main) and it-standard-dev (dev)
- CI validation pipeline for PRs (naming, format, frontmatter consistency, immutability, secret scanning)
- Publishing workflow with fork-based contributions, admin review, and branch protection
- Health endpoints (/healthz, /readyz) and structured observability logging
- Error handling with typed errors (SKILL_NOT_FOUND, VERSION_NOT_FOUND, INVALID_VERSION, UPSTREAM_UNAVAILABLE)
- Deprecation support with warning messages in responses
- Hosting on Intel CaaS platform

## Out of Scope

- Intel AI Asset Catalog integration (deferred)
- GitHub webhooks / HMAC-signed callbacks
- Client-credentials (non-user) flows that trigger processes — agents only read
- Per-group access restrictions — all skills available to all authenticated users
- Multi-file skills (scripts, templates) — each skill version is a single SKILL.md file
- Write operations to GitHub or any other system
- OAuth Dynamic Client Registration
- Mobile or web UI for skill browsing (MCP tools only)
- Skill authoring or editing through the MCP server

## Technical constraints

- Must implement the Model Context Protocol (MCP) with Streamable HTTP transport
- Hosted on Intel CaaS platform (container-based)
- Authentication via OAuth 2.0 with Microsoft Entra ID as identity provider
- API gateway is Apigee X — all token validation happens at Apigee, not in the MCP server
- GitHub monorepo in intel-innersource organization is the single source of truth for skill content
- GitHub access via GitHub App (preferred) or fine-grained token with read-only contents permission
- Read-only server — no write operations to GitHub or any other system
- Stateless server design — no session state, must support horizontal scaling
- Cache required (Redis or equivalent) for shared state across replicas
- Polling-based change detection (no webhooks) — poll branch HEAD SHA every 60 seconds with ETag
- CaaS ingress must be private or restricted to Apigee egress addresses; Apigee-to-MCP uses mTLS or shared secret
- Semantic versioning (MAJOR.MINOR.PATCH) enforced for all skill versions
- Immutability of version folders on main branch — enforced by CI
- Single-file skills only (one SKILL.md per version folder) — multi-file skills are out of scope
- Two environments (it-standard and it-standard-dev) from the same container image, differentiated by configuration
- No Dynamic Client Registration support — clients must use pre-registered Entra app registration

## Platform context

- **Language:** Not specified — to be determined (likely TypeScript/Node.js or Python based on MCP SDK availability)
- **Build toolchain:** Not specified — container image built for CaaS deployment
- **Runtime model:** Stateless containerized service on Intel CaaS, horizontally scalable
- **Deployment target:** Intel CaaS platform with Apigee X as API gateway, two environments (production and dev)
- **Testing methodology:** Not specified in architecture document
- **Memory constraints:** No specific constraints mentioned; standard container limits apply
- **Cross-module linking:** Single service with internal module organization; no cross-service linking

## Confidence

Overall: **92%**

> Exceptionally detailed architecture document covering all major aspects of the system. Minor gaps are limited to implementation-level choices (programming language, testing strategy) that are appropriate to leave open at this stage.

| Section | Score | Why | How to Improve |
| --- | --- | --- | --- |
| Vision | 95% | Clear and detailed purpose statement with well-defined product scope, target use case, and value proposition provided in the architecture document | Add 2-3 measurable success metrics (e.g., target skill retrieval latency, number of skills at launch, adoption targets) |
| Target personas | 88% | Roles are explicitly defined (Admin, Contributor, Consumer) with clear permissions; platform/DevOps persona is inferred from operational requirements rather than explicitly stated | Explicitly list the DevOps/Platform Engineer persona and document their specific operational needs and pain points |
| Core features | 95% | All five MCP tools are fully specified with input/output schemas, error handling, and example usage; CI checks, caching, auth flow, and publishing workflow are thoroughly documented | Specify the search algorithm or matching strategy for search_skills (e.g., substring, fuzzy, weighted fields) and define pagination behavior for large catalogs |
| Technical constraints | 93% | Comprehensive technical decisions documented including hosting platform, auth stack, caching strategy, transport protocol, and environment configuration; primary programming language is not specified | Specify the primary programming language and MCP SDK to be used (TypeScript with @modelcontextprotocol/sdk or Python with FastMCP), and define the testing strategy |

**To improve accuracy, please provide:**

- Primary programming language and MCP SDK choice (TypeScript/Node.js vs Python vs other)
- Testing strategy and framework (unit tests, integration tests, contract tests for MCP tools)
- Search algorithm details for search_skills (substring matching, fuzzy search, field weighting)
- Rate limiting and quota specifics at Apigee (requests per minute per client, burst limits)
- Expected scale parameters (number of skills, number of concurrent clients, request volume)

