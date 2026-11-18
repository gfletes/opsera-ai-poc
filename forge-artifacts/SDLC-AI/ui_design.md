# UI Design Specification

## Design Tokens

### Colors

### Typography

### Spacing
- 1: 4px
- 2: 8px
- 3: 12px
- 4: 16px
- 5: 20px
- 6: 24px
- 8: 32px
- 10: 40px
- 12: 48px
- 16: 64px
- 24: 96px

### Border Radius
- lg: 12px
- md: 8px
- sm: 4px
- full: 9999px

### Shadows

## Design Tokens (JSON)
```json
{
  "colors": {
    "info": {
      "dark": "#38BDF8",
      "light": "#0284C7"
    },
    "text": {
      "dark": "#F1F5F9",
      "light": "#0F172A",
      "description": "Primary text"
    },
    "error": {
      "dark": "#F87171",
      "light": "#DC2626"
    },
    "accent": {
      "dark": "#A78BFA",
      "light": "#7C3AED",
      "description": "Purple — CI/automation, accent elements"
    },
    "border": {
      "dark": "#334155",
      "light": "#E2E8F0"
    },
    "code-bg": {
      "dark": "#1E293B",
      "light": "#F1F5F9"
    },
    "info-bg": {
      "dark": "#0C4A6E",
      "light": "#F0F9FF"
    },
    "primary": {
      "dark": "#60A5FA",
      "light": "#0068B5",
      "description": "Intel blue — primary actions, links, active states"
    },
    "success": {
      "dark": "#34D399",
      "light": "#059669"
    },
    "surface": {
      "dark": "#1E293B",
      "light": "#F8FAFC",
      "description": "Elevated surface for cards, panels"
    },
    "warning": {
      "dark": "#FBBF24",
      "light": "#D97706"
    },
    "error-bg": {
      "dark": "#7F1D1D",
      "light": "#FEF2F2"
    },
    "secondary": {
      "dark": "#34D399",
      "light": "#00C7B7",
      "description": "Teal — secondary actions, admin role"
    },
    "background": {
      "dark": "#0F172A",
      "light": "#FFFFFF"
    },
    "success-bg": {
      "dark": "#064E3B",
      "light": "#ECFDF5"
    },
    "text-muted": {
      "dark": "#64748B",
      "light": "#94A3B8",
      "description": "Timestamps, captions, labels"
    },
    "warning-bg": {
      "dark": "#78350F",
      "light": "#FFFBEB"
    },
    "accent-light": {
      "dark": "#2E1065",
      "light": "#EDE9FE"
    },
    "border-strong": {
      "dark": "#475569",
      "light": "#CBD5E1"
    },
    "primary-hover": {
      "dark": "#93C5FD",
      "light": "#005494"
    },
    "primary-light": {
      "dark": "#1E3A5F",
      "light": "#E8F2FB",
      "description": "Primary tint for backgrounds, hover states"
    },
    "surface-raised": {
      "dark": "#334155",
      "light": "#FFFFFF",
      "description": "Higher elevation surface"
    },
    "text-secondary": {
      "dark": "#CBD5E1",
      "light": "#475569",
      "description": "Descriptions, metadata"
    }
  },
  "shadows": {
    "lg": {
      "dark": "0 10px 15px -3px rgba(0,0,0,0.5), 0 4px 6px -4px rgba(0,0,0,0.4)",
      "light": "0 10px 15px -3px rgba(0,0,0,0.1), 0 4px 6px -4px rgba(0,0,0,0.1)"
    },
    "md": {
      "dark": "0 4px 6px -1px rgba(0,0,0,0.4), 0 2px 4px -2px rgba(0,0,0,0.3)",
      "light": "0 4px 6px -1px rgba(0,0,0,0.1), 0 2px 4px -2px rgba(0,0,0,0.1)"
    },
    "sm": {
      "dark": "0 1px 2px 0 rgba(0,0,0,0.3)",
      "light": "0 1px 2px 0 rgba(0,0,0,0.05)"
    },
    "xl": {
      "dark": "0 20px 25px -5px rgba(0,0,0,0.5), 0 8px 10px -6px rgba(0,0,0,0.4)",
      "light": "0 20px 25px -5px rgba(0,0,0,0.1), 0 8px 10px -6px rgba(0,0,0,0.1)"
    }
  },
  "spacing": {
    "1": "4px",
    "2": "8px",
    "3": "12px",
    "4": "16px",
    "5": "20px",
    "6": "24px",
    "8": "32px",
    "10": "40px",
    "12": "48px",
    "16": "64px",
    "24": "96px"
  },
  "typography": {
    "font-mono": "'JetBrains Mono', 'Fira Code', 'Consolas', monospace",
    "font-sans": "'Inter', -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif",
    "size-scale": {
      "lg": "1.125rem (18px)",
      "sm": "0.875rem (14px)",
      "xl": "1.25rem (20px)",
      "xs": "0.75rem (12px)",
      "2xl": "1.5rem (24px)",
      "3xl": "1.875rem (30px)",
      "4xl": "2.25rem (36px)",
      "base": "1rem (16px)"
    },
    "line-heights": {
      "tight": 1.25,
      "normal": 1.5,
      "relaxed": 1.625
    },
    "weight-scale": {
      "bold": 700,
      "medium": 500,
      "regular": 400,
      "semibold": 600
    }
  },
  "border_radius": {
    "lg": "12px",
    "md": "8px",
    "sm": "4px",
    "full": "9999px"
  }
}
```

---

## Design System

Visual component library, typography, color palette, and design tokens for the IT-Standard MCP server's machine-facing response presentation patterns. Since the system has no standalone human UI, this design system documents how MCP tool responses should be rendered when embedded in IDE panels, AI agent chat interfaces, and developer tooling. All tokens and components are optimized for dense, data-rich presentation within constrained embedding contexts.

### Component Hierarchy
```
DesignSystem
├── ThemeToggle (fixed position, light/dark switch)
├── Header
│   ├── Title
│   ├── Description
│   └── VersionBadge
├── TabNavigation (role=tablist)
│   ├── Tab: Colors
│   ├── Tab: Typography
│   ├── Tab: Components
│   ├── Tab: Spacing & Layout
│   └── Tab: Data Patterns
├── ColorsPanel
│   ├── ColorSection: Brand Colors
│   │   └── ColorSwatch[] (swatch + name + token)
│   ├── ColorSection: Surface & Background
│   ├── ColorSection: Text
│   ├── ColorSection: Semantic States
│   └── ColorSection: Borders
├── TypographyPanel
│   ├── FontFamilySamples
│   ├── SizeScale (xs–4xl)
│   └── WeightScale (regular–bold)
├── ComponentsPanel
│   ├── ButtonRow (primary, secondary, ghost, destructive, disabled, loading)
│   ├── FormInputs (text, error, disabled, select, checkbox, radio, toggle)
│   ├── BadgesAndTags
│   ├── CardGrid
│   ├── DataTable
│   ├── AlertVariants (info, success, warning, error)
│   ├── Tooltip
│   ├── Accordion
│   ├── Modal
│   ├── Breadcrumb
│   ├── SidebarNav
│   ├── DropdownMenu
│   └── CodeBlock
├── SpacingPanel
│   ├── SpacingScale (visual bars)
│   ├── ShadowGrid
│   ├── BorderRadiusGrid
│   └── IconGrid
└── DataPatternsPanel
    ├── SkillCardPattern
    ├── ErrorResponsePattern
    ├── DeprecationWarningPattern
    └── CacheStatusPattern
```

### HTML Preview
```html
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>IT-Standard MCP — Design System</title>
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&family=JetBrains+Mono:wght@400;500&display=swap" rel="stylesheet">
<style>
:root {
  --color-primary: #0068B5;
  --color-primary-hover: #005494;
  --color-primary-light: #E8F2FB;
  --color-secondary: #00C7B7;
  --color-secondary-hover: #00A89B;
  --color-accent: #7C3AED;
  --color-accent-light: #EDE9FE;
  --color-bg: #FFFFFF;
  --color-surface: #F8FAFC;
  --color-surface-raised: #FFFFFF;
  --color-text: #0F172A;
  --color-text-secondary: #475569;
  --color-text-muted: #94A3B8;
  --color-success: #059669;
  --color-success-bg: #ECFDF5;
  --color-warning: #D97706;
  --color-warning-bg: #FFFBEB;
  --color-error: #DC2626;
  --color-error-bg: #FEF2F2;
  --color-info: #0284C7;
  --color-info-bg: #F0F9FF;
  --color-border: #E2E8F0;
  --color-border-strong: #CBD5E1;
  --color-code-bg: #F1F5F9;
  --color-badge-active: #059669;
  --color-badge-active-bg: #ECFDF5;
  --color-badge-deprecated: #D97706;
  --color-badge-deprecated-bg: #FFFBEB;
  --font-sans: 'Inter', -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif;
  --font-mono: 'JetBrains Mono', 'Fira Code', 'Consolas', monospace;
  --text-xs: 0.75rem;
  --text-sm: 0.875rem;
  --text-base: 1rem;
  --text-lg: 1.125rem;
  --text-xl: 1.25rem;
  --text-2xl: 1.5rem;
  --text-3xl: 1.875rem;
  --text-4xl: 2.25rem;
  --weight-regular: 400;
  --weight-medium: 500;
  --weight-semibold: 600;
  --weight-bold: 700;
  --leading-tight: 1.25;
  --leading-normal: 1.5;
  --leading-relaxed: 1.625;
  --space-1: 4px;
  --space-2: 8px;
  --space-3: 12px;
  --space-4: 16px;
  --space-5: 20px;
  --space-6: 24px;
  --space-8: 32px;
  --space-10: 40px;
  --space-12: 48px;
  --space-16: 64px;
  --space-24: 96px;
  --shadow-sm: 0 1px 2px 0 rgba(0,0,0,0.05);
  --shadow-md: 0 4px 6px -1px rgba(0,0,0,0.1), 0 2px 4px -2px rgba(0,0,0,0.1);
  --shadow-lg: 0 10px 15px -3px rgba(0,0,0,0.1), 0 4px 6px -4px rgba(0,0,0,0.1);
  --shadow-xl: 0 20px 25px -5px rgba(0,0,0,0.1), 0 8px 10px -6px rgba(0,0,0,0.1);
  --radius-sm: 4px;
  --radius-md: 8px;
  --radius-lg: 12px;
  --radius-full: 9999px;
  --transition-fast: 150ms ease;
  --transition-normal: 200ms ease;
}
[data-theme="dark"] {
  --color-primary: #60A5FA;
  --color-primary-hover: #93C5FD;
  --color-primary-light: #1E3A5F;
  --color-secondary: #34D399;
  --color-secondary-hover: #6EE7B7;
  --color-accent: #A78BFA;
  --color-accent-light: #2E1065;
  --color-bg: #0F172A;
  --color-surface: #1E293B;
  --color-surface-raised: #334155;
  --color-text: #F1F5F9;
  --color-text-secondary: #CBD5E1;
  --color-text-muted: #64748B;
  --color-success: #34D399;
  --color-success-bg: #064E3B;
  --color-warning: #FBBF24;
  --color-warning-bg: #78350F;
  --color-error: #F87171;
  --color-error-bg: #7F1D1D;
  --color-info: #38BDF8;
  --color-info-bg: #0C4A6E;
  --color-border: #334155;
  --color-border-strong: #475569;
  --color-code-bg: #1E293B;
  --color-badge-active: #34D399;
  --color-badge-active-bg: #064E3B;
  --color-badge-deprecated: #FBBF24;
  --color-badge-deprecated-bg: #78350F;
  --shadow-sm: 0 1px 2px 0 rgba(0,0,0,0.3);
  --shadow-md: 0 4px 6px -1px rgba(0,0,0,0.4), 0 2px 4px -2px rgba(0,0,0,0.3);
  --shadow-lg: 0 10px 15px -3px rgba(0,0,0,0.5), 0 4px 6px -4px rgba(0,0,0,0.4);
  --shadow-xl: 0 20px 25px -5px rgba(0,0,0,0.5), 0 8px 10px -6px rgba(0,0,0,0.4);
}
* { margin: 0; padding: 0; box-sizing: border-box; }
body { font-family: var(--font-sans); background: var(--color-bg); color: var(--color-text); line-height: var(--leading-normal); }
.theme-toggle { position: fixed; top: 12px; right: 12px; z-index: 9999; background: var(--color-surface-raised); border: 1px solid var(--color-border); border-radius: var(--radius-full); width: 40px; height: 40px; cursor: pointer; display: flex; align-items: center; justify-content: center; font-size: 18px; transition: background var(--transition-fast); box-shadow: var(--shadow-sm); }
.theme-toggle:hover { background: var(--color-primary-light); }
.ds-container { max-width: 1200px; margin: 0 auto; padding: var(--space-8); }
.ds-header { margin-bottom: var(--space-12); padding-bottom: var(--space-8); border-bottom: 2px solid var(--color-border); }
.ds-header h1 { font-size: var(--text-3xl); font-weight: var(--weight-bold); margin-bottom: var(--space-2); }
.ds-header p { color: var(--color-text-secondary); font-size: var(--text-lg); }
.ds-header .badge { display: inline-block; background: var(--color-primary-light); color: var(--color-primary); padding: var(--space-1) var(--space-3); border-radius: var(--radius-full); font-size: var(--text-xs); font-weight: var(--weight-semibold); margin-top: var(--space-2); }
.ds-section { margin-bottom: var(--space-12); }
.ds-section h2 { font-size: var(--text-2xl); font-weight: var(--weight-bold); margin-bottom: var(--space-6); padding-bottom: var(--space-3); border-bottom: 1px solid var(--color-border); }
.ds-section h3 { font-size: var(--text-lg); font-weight: var(--weight-semibold); margin-bottom: var(--space-4); color: var(--color-text-secondary); }
.color-grid { display: grid; grid-template-columns: repeat(auto-fill, minmax(180px, 1fr)); gap: var(--space-4); }
.color-swatch { border-radius: var(--radius-md); overflow: hidden; border: 1px solid var(--color-border); background: var(--color-surface-raised); }
.color-swatch .swatch-color { height: 64px; }
.color-swatch .swatch-info { padding: var(--space-3); }
.color-swatch .swatch-name { font-size: var(--text-sm); font-weight: var(--weight-semibold); }
.color-swatch .swatch-token { font-size: var(--text-xs); color: var(--color-text-muted); font-family: var(--font-mono); margin-top: 2px; }
.type-sample { margin-bottom: var(--space-4); padding: var(--space-4); background: var(--color-surface); border-radius: var(--radius-md); border: 1px solid var(--color-border); }
.type-sample .meta { font-size: var(--text-xs); color: var(--color-text-muted); font-family: var(--font-mono); margin-bottom: var(--space-2); }
.spacing-row { display: flex; align-items: center; gap: var(--space-4); margin-bottom: var(--space-3); }
.spacing-bar { background: var(--color-primary); border-radius: var(--radius-sm); height: 24px; }
.spacing-label { font-size: var(--text-sm); font-family: var(--font-mono); color: var(--color-text-secondary); min-width: 120px; }
.shadow-grid { display: grid; grid-template-columns: repeat(auto-fill, minmax(200px, 1fr)); gap: var(--space-6); }
.shadow-box { background: var(--color-surface-raised); border-radius: var(--radius-md); padding: var(--space-6); text-align: center; }
.shadow-box .label { font-size: var(--text-sm); font-weight: var(--weight-medium); margin-top: var(--space-3); }
.btn { display: inline-flex; align-items: center; gap: var(--space-2); padding: var(--space-2) var(--space-4); border-radius: var(--radius-md); font-size: var(--text-sm); font-weight: var(--weight-medium); font-family: var(--font-sans); cursor: pointer; border: 1px solid transparent; transition: all var(--transition-fast); line-height: var(--leading-tight); }
.btn-primary { background: var(--color-primary); color: #FFF; }
.btn-primary:hover { background: var(--color-primary-hover); }
.btn-secondary { background: var(--color-surface); color: var(--color-text); border-color: var(--color-border); }
.btn-secondary:hover { background: var(--color-primary-light); border-color: var(--color-primary); }
.btn-ghost { background: transparent; color: var(--color-primary); }
.btn-ghost:hover { background: var(--color-primary-light); }
.btn-destructive { background: var(--color-error); color: #FFF; }
.btn-destructive:hover { opacity: 0.9; }
.btn:disabled, .btn-disabled { opacity: 0.5; cursor: not-allowed; pointer-events: none; }
.btn-loading { position: relative; color: transparent !important; }
.btn-loading::after { content: ''; position: absolute; width: 16px; height: 16px; border: 2px solid #FFF; border-top-color: transparent; border-radius: 50%; animation: spin 0.6s linear infinite; }
@keyframes spin { to { transform: rotate(360deg); } }
.component-row { display: flex; flex-wrap: wrap; gap: var(--space-3); align-items: center; margin-bottom: var(--space-4); }
.input-field { padding: var(--space-2) var(--space-3); border: 1px solid var(--color-border); border-radius: var(--radius-md); font-size: var(--text-sm); font-family: var(--font-sans); background: var(--color-surface-raised); color: var(--color-text); transition: border-color var(--transition-fast), box-shadow var(--transition-fast); width: 240px; }
.input-field:focus { outline: none; border-color: var(--color-primary); box-shadow: 0 0 0 3px rgba(0,104,181,0.15); }
.input-field.input-error { border-color: var(--color-error); }
.input-field:disabled { opacity: 0.5; cursor: not-allowed; background: var(--color-surface); }
.badge-component { display: inline-flex; align-items: center; padding: 2px var(--space-2); border-radius: var(--radius-full); font-size: var(--text-xs); font-weight: var(--weight-medium); }
.badge-active { background: var(--color-badge-active-bg); color: var(--color-badge-active); }
.badge-deprecated { background: var(--color-badge-deprecated-bg); color: var(--color-badge-deprecated); }
.badge-info { background: var(--color-info-bg); color: var(--color-info); }
.badge-primary { background: var(--color-primary-light); color: var(--color-primary); }
.tag-chip { display: inline-flex; align-items: center; padding: 2px var(--space-3); border-radius: var(--radius-full); font-size: var(--text-xs); background: var(--color-surface); border: 1px solid var(--color-border); color: var(--color-text-secondary); }
.card { background: var(--color-surface-raised); border: 1px solid var(--color-border); border-radius: var(--radius-lg); padding: var(--space-6); box-shadow: var(--shadow-sm); transition: box-shadow var(--transition-fast); }
.card:hover { box-shadow: var(--shadow-md); }
.card-header { font-weight: var(--weight-semibold); margin-bottom: var(--space-2); }
.card-body { font-size: var(--text-sm); color: var(--color-text-secondary); }
.table-wrapper { overflow-x: auto; border: 1px solid var(--color-border); border-radius: var(--radius-md); }
table.ds-table { width: 100%; border-collapse: collapse; font-size: var(--text-sm); }
.ds-table th { background: var(--color-surface); padding: var(--space-3) var(--space-4); text-align: left; font-weight: var(--weight-semibold); border-bottom: 2px solid var(--color-border); white-space: nowrap; }
.ds-table td { padding: var(--space-3) var(--space-4); border-bottom: 1px solid var(--color-border); }
.ds-table tbody tr:hover { background: var(--color-primary-light); }
.ds-table tbody tr:nth-child(even) { background: var(--color-surface); }
.ds-table tbody tr:nth-child(even):hover { background: var(--color-primary-light); }
.alert { padding: var(--space-4); border-radius: var(--radius-md); font-size: var(--text-sm); display: flex; gap: var(--space-3); align-items: flex-start; margin-bottom: var(--space-3); }
.alert-info { background: var(--color-info-bg); color: var(--color-info); border: 1px solid var(--color-info); }
.alert-success { background: var(--color-success-bg); color: var(--color-success); border: 1px solid var(--color-success); }
.alert-warning { background: var(--color-warning-bg); color: var(--color-warning); border: 1px solid var(--color-warning); }
.alert-error { background: var(--color-error-bg); color: var(--color-error); border: 1px solid var(--color-error); }
.code-block { background: var(--color-code-bg); border: 1px solid var(--color-border); border-radius: var(--radius-md); padding: var(--space-4); font-family: var(--font-mono); font-size: var(--text-sm); overflow-x: auto; line-height: 1.6; }
.nav-tabs { display: flex; border-bottom: 2px solid var(--color-border); gap: 0; }
.nav-tab { padding: var(--space-3) var(--space-4); font-size: var(--text-sm); font-weight: var(--weight-medium); color: var(--color-text-muted); cursor: pointer; border-bottom: 2px solid transparent; margin-bottom: -2px; transition: all var(--transition-fast); background: none; border-top: none; border-left: none; border-right: none; font-family: var(--font-sans); }
.nav-tab:hover { color: var(--color-text); }
.nav-tab[aria-selected="true"] { color: var(--color-primary); border-bottom-color: var(--color-primary); }
.tab-panel { padding: var(--space-6) 0; }
.accordion-item { border: 1px solid var(--color-border); border-radius: var(--radius-md); margin-bottom: var(--space-2); overflow: hidden; }
.accordion-item summary { padding: var(--space-3) var(--space-4); font-weight: var(--weight-medium); font-size: var(--text-sm); cursor: pointer; background: var(--color-surface); list-style: none; display: flex; align-items: center; gap: var(--space-2); }
.accordion-item summary::before { content: '▸'; transition: transform var(--transition-fast); }
.accordion-item[open] summary::before { transform: rotate(90deg); }
.accordion-item .accordion-body { padding: var(--space-4); font-size: var(--text-sm); color: var(--color-text-secondary); border-top: 1px solid var(--color-border); }
.modal-overlay { position: fixed; inset: 0; background: rgba(0,0,0,0.5); display: flex; align-items: center; justify-content: center; z-index: 1000; }
.modal-content { background: var(--color-surface-raised); border-radius: var(--radius-lg); padding: var(--space-8); max-width: 480px; width: 90%; box-shadow: var(--shadow-xl); }
.modal-header { font-size: var(--text-xl); font-weight: var(--weight-bold); margin-bottom: var(--space-4); }
.modal-footer { display: flex; gap: var(--space-3); justify-content: flex-end; margin-top: var(--space-6); }
.tooltip-wrapper { position: relative; display: inline-block; }
.tooltip-content { position: absolute; bottom: 100%; left: 50%; transform: translateX(-50%); background: var(--color-text); color: var(--color-bg); padding: var(--space-1) var(--space-3); border-radius: var(--radius-sm); font-size: var(--text-xs); white-space: nowrap; opacity: 0; pointer-events: none; transition: opacity var(--transition-fast); margin-bottom: 4px; }
.tooltip-wrapper:hover .tooltip-content { opacity: 1; }
.radius-grid { display: grid; grid-template-columns: repeat(auto-fill, minmax(140px, 1fr)); gap: var(--space-4); }
.radius-box { width: 80px; height: 80px; background: var(--color-primary-light); border: 2px solid var(--color-primary); display: flex; align-items: center; justify-content: center; font-size: var(--text-xs); font-family: var(--font-mono); margin: 0 auto var(--space-2); }
.icon-grid { display: flex; flex-wrap: wrap; gap: var(--space-4); }
.icon-item { display: flex; flex-direction: column; align-items: center; gap: var(--space-2); padding: var(--space-3); border-radius: var(--radius-md); border: 1px solid var(--color-border); font-size: var(--text-xs); color: var(--color-text-secondary); min-width: 80px; }
.icon-item .icon { font-size: 20px; }
.checkbox-wrapper { display: flex; align-items: center; gap: var(--space-2); font-size: var(--text-sm); cursor: pointer; }
.checkbox-wrapper input[type="checkbox"] { width: 16px; height: 16px; accent-color: var(--color-primary); }
.radio-wrapper { display: flex; align-items: center; gap: var(--space-2); font-size: var(--text-sm); cursor: pointer; }
.radio-wrapper input[type="radio"] { width: 16px; height: 16px; accent-color: var(--color-primary); }
.toggle-switch { position: relative; width: 40px; height: 22px; background: var(--color-border-strong); border-radius: var(--radius-full); cursor: pointer; transition: background var(--transition-fast); border: none; }
.toggle-switch.active { background: var(--color-primary); }
.toggle-switch::after { content: ''; position: absolute; top: 3px; left: 3px; width: 16px; height: 16px; background: white; border-radius: 50%; transition: transform var(--transition-fast); }
.toggle-switch.active::after { transform: translateX(18px); }
.select-field { padding: var(--space-2) var(--space-3); border: 1px solid var(--color-border); border-radius: var(--radius-md); font-size: var(--text-sm); font-family: var(--font-sans); background: var(--color-surface-raised); color: var(--color-text); min-width: 200px; }
.select-field:focus { outline: none; border-color: var(--color-primary); box-shadow: 0 0 0 3px rgba(0,104,181,0.15); }
.breadcrumb { display: flex; align-items: center; gap: var(--space-2); font-size: var(--text-sm); }
.breadcrumb a { color: var(--color-primary); text-decoration: none; }
.breadcrumb a:hover { text-decoration: underline; }
.breadcrumb .separator { color: var(--color-text-muted); }
.breadcrumb .current { color: var(--color-text-secondary); }
.sidebar-item { display: flex; align-items: center; gap: var(--space-3); padding: var(--space-2) var(--space-3); border-radius: var(--radius-md); font-size: var(--text-sm); cursor: pointer; color: var(--color-text-secondary); transition: all var(--transition-fast); }
.sidebar-item:hover { background: var(--color-primary-light); color: var(--color-text); }
.sidebar-item.active { background: var(--color-primary-light); color: var(--color-primary); font-weight: var(--weight-medium); }
.dropdown-menu { background: var(--color-surface-raised); border: 1px solid var(--color-border); border-radius: var(--radius-md); box-shadow: var(--shadow-lg); min-width: 200px; padding: var(--space-1) 0; }
.dropdown-item { padding: var(--space-2) var(--space-4); font-size: var(--text-sm); cursor: pointer; transition: background var(--transition-fast); }
.dropdown-item:hover { background: var(--color-primary-light); }
@media (max-width: 768px) {
  .ds-container { padding: var(--space-4); }
  .color-grid { grid-template-columns: repeat(auto-fill, minmax(140px, 1fr)); }
  .component-row { flex-direction: column; align-items: flex-start; }
  .shadow-grid { grid-template-columns: 1fr 1fr; }
}
</style>
</head>
<body>
<button class="theme-toggle" aria-label="Toggle theme">☀</button>
<div class="ds-container">
  <header class="ds-header">
    <h1>IT-Standard MCP — Design System</h1>
    <p>Response presentation patterns for IDE/MCP client embeddings. Machine-facing component library and token reference.</p>
    <span class="badge">v1.0.0 · November 2026</span>
  </header>

  <!-- Tabs -->
  <div role="tablist" class="nav-tabs" aria-label="Design system sections">
    <button role="tab" aria-selected="true" aria-controls="panel-colors" id="tab-colors" class="nav-tab">Colors</button>
    <button role="tab" aria-selected="false" aria-controls="panel-typography" id="tab-typography" class="nav-tab">Typography</button>
    <button role="tab" aria-selected="false" aria-controls="panel-components" id="tab-components" class="nav-tab">Components</button>
    <button role="tab" aria-selected="false" aria-controls="panel-spacing" id="tab-spacing" class="nav-tab">Spacing & Layout</button>
    <button role="tab" aria-selected="false" aria-controls="panel-patterns" id="tab-patterns" class="nav-tab">Data Patterns</button>
  </div>

  <!-- Colors Panel -->
  <div role="tabpanel" id="panel-colors" aria-labelledby="tab-colors" class="tab-panel">
    <section class="ds-section">
      <h2>Color Palette</h2>
      <h3>Brand Colors</h3>
      <div class="color-grid">
        <div class="color-swatch"><div class="swatch-color" style="background:#0068B5"></div><div class="swatch-info"><div class="swatch-name">Primary</div><div class="swatch-token">--color-primary · #0068B5</div></div></div>
        <div class="color-swatch"><div class="swatch-color" style="background:#005494"></div><div class="swatch-info"><div class="swatch-name">Primary Hover</div><div class="swatch-token">--color-primary-hover · #005494</div></div></div>
        <div class="color-swatch"><div class="swatch-color" style="background:#E8F2FB"></div><div class="swatch-info"><div class="swatch-name">Primary Light</div><div class="swatch-token">--color-primary-light · #E8F2FB</div></div></div>
        <div class="color-swatch"><div class="swatch-color" style="background:#00C7B7"></div><div class="swatch-info"><div class="swatch-name">Secondary</div><div class="swatch-token">--color-secondary · #00C7B7</div></div></div>
        <div class="color-swatch"><div class="swatch-color" style="background:#7C3AED"></div><div class="swatch-info"><div class="swatch-name">Accent</div><div class="swatch-token">--color-accent · #7C3AED</div></div></div>
      </div>
      <h3 style="margin-top:var(--space-6)">Surface & Background</h3>
      <div class="color-grid">
        <div class="color-swatch"><div class="swatch-color" style="background:#FFFFFF; border-bottom:1px solid #E2E8F0"></div><div class="swatch-info"><div class="swatch-name">Background</div><div class="swatch-token">--color-bg · #FFFFFF</div></div></div>
        <div class="color-swatch"><div class="swatch-color" style="background:#F8FAFC"></div><div class="swatch-info"><div class="swatch-name">Surface</div><div class="swatch-token">--color-surface · #F8FAFC</div></div></div>
        <div class="color-swatch"><div class="swatch-color" style="background:#FFFFFF; border-bottom:1px solid #E2E8F0"></div><div class="swatch-info"><div class="swatch-name">Surface Raised</div><div class="swatch-token">--color-surface-raised · #FFFFFF</div></div></div>
      </div>
      <h3 style="margin-top:var(--space-6)">Text</h3>
      <div class="color-grid">
        <div class="color-swatch"><div class="swatch-color" style="background:#0F172A"></div><div class="swatch-info"><div class="swatch-name">Text Primary</div><div class="swatch-token">--color-text · #0F172A</div></div></div>
        <div class="color-swatch"><div class="swatch-color" style="background:#475569"></div><div class="swatch-info"><div class="swatch-name">Text Secondary</div><div class="swatch-token">--color-text-secondary · #475569</div></div></div>
        <div class="color-swatch"><div class="swatch-color" style="background:#94A3B8"></div><div class="swatch-info"><div class="swatch-name">Text Muted</div><div class="swatch-token">--color-text-muted · #94A3B8</div></div></div>
      </div>
      <h3 style="margin-top:var(--space-6)">Semantic States</h3>
      <div class="color-grid">
        <div class="color-swatch"><div class="swatch-color" style="background:#059669"></div><div class="swatch-info"><div class="swatch-name">Success</div><div class="swatch-token">--color-success · #059669</div></div></div>
        <div class="color-swatch"><div class="swatch-color" style="background:#D97706"></div><div class="swatch-info"><div class="swatch-name">Warning</div><div class="swatch-token">--color-warning · #D97706</div></div></div>
        <div class="color-swatch"><div class="swatch-color" style="background:#DC2626"></div><div class="swatch-info"><div class="swatch-name">Error</div><div class="swatch-token">--color-error · #DC2626</div></div></div>
        <div class="color-swatch"><div class="swatch-color" style="background:#0284C7"></div><div class="swatch-info"><div class="swatch-name">Info</div><div class="swatch-token">--color-info · #0284C7</div></div></div>
      </div>
      <h3 style="margin-top:var(--space-6)">Borders</h3>
      <div class="color-grid">
        <div class="color-swatch"><div class="swatch-color" style="background:#E2E8F0"></div><div class="swatch-info"><div class="swatch-name">Border</div><div class="swatch-token">--color-border · #E2E8F0</div></div></div>
        <div class="color-swatch"><div class="swatch-color" style="background:#CBD5E1"></div><div class="swatch-info"><div class="swatch-name">Border Strong</div><div class="swatch-token">--color-border-strong · #CBD5E1</div></div></div>
        <div class="color-swatch"><div class="swatch-color" style="background:#F1F5F9"></div><div class="swatch-info"><div class="swatch-name">Code BG</div><div class="swatch-token">--color-code-bg · #F1F5F9</div></div></div>
      </div>
    </section>
  </div>

  <!-- Typography Panel -->
  <div role="tabpanel" id="panel-typography" aria-labelledby="tab-typography" class="tab-panel" style="display:none">
    <section class="ds-section">
      <h2>Typography Scale</h2>
      <h3>Font Families</h3>
      <div class="type-sample"><div class="meta">--font-sans · Inter, system fallback</div><span style="font-family:var(--font-sans);font-size:var(--text-lg)">The quick brown fox jumps over the lazy dog. 0123456789</span></div>
      <div class="type-sample"><div class="meta">--font-mono · JetBrains Mono</div><span style="font-family:var(--font-mono);font-size:var(--text-lg)">const skill = getSkill("SDLC", "2.0.0");</span></div>
      <h3 style="margin-top:var(--space-6)">Size Scale</h3>
      <div class="type-sample"><div class="meta">--text-4xl · 2.25rem · 36px</div><div style="font-size:var(--text-4xl);font-weight:var(--weight-bold)">Skill Catalog Header</div></div>
      <div class="type-sample"><div class="meta">--text-3xl · 1.875rem · 30px</div><div style="font-size:var(--text-3xl);font-weight:var(--weight-bold)">Section Title</div></div>
      <div class="type-sample"><div class="meta">--text-2xl · 1.5rem · 24px</div><div style="font-size:var(--text-2xl);font-weight:var(--weight-semibold)">Subsection Heading</div></div>
      <div class="type-sample"><div class="meta">--text-xl · 1.25rem · 20px</div><div style="font-size:var(--text-xl);font-weight:var(--weight-semibold)">Skill Name Display</div></div>
      <div class="type-sample"><div class="meta">--text-lg · 1.125rem · 18px</div><div style="font-size:var(--text-lg);font-weight:var(--weight-medium)">Tool Response Title</div></div>
      <div class="type-sample"><div class="meta">--text-base · 1rem · 16px</div><div style="font-size:var(--text-base)">Body text for descriptions and content. Used in SKILL.md rendering within IDE panels.</div></div>
      <div class="type-sample"><div class="meta">--text-sm · 0.875rem · 14px</div><div style="font-size:var(--text-sm)">Metadata labels, table content, secondary information in response cards.</div></div>
      <div class="type-sample"><div class="meta">--text-xs · 0.75rem · 12px</div><div style="font-size:var(--text-xs);color:var(--color-text-muted)">Timestamps, version numbers, commit SHAs, caption text.</div></div>
      <h3 style="margin-top:var(--space-6)">Weight Scale</h3>
      <div class="type-sample"><div class="meta">--weight-regular · 400</div><div style="font-weight:400;font-size:var(--text-base)">Regular weight for body text and descriptions</div></div>
      <div class="type-sample"><div class="meta">--weight-medium · 500</div><div style="font-weight:500;font-size:var(--text-base)">Medium weight for labels and emphasis</div></div>
      <div class="type-sample"><div class="meta">--weight-semibold · 600</div><div style="font-weight:600;font-size:var(--text-base)">Semibold for headings and important metadata</div></div>
      <div class="type-sample"><div class="meta">--weight-bold · 700</div><div style="font-weight:700;font-size:var(--text-base)">Bold for primary headings and emphasis</div></div>
    </section>
  </div>

  <!-- Components Panel -->
  <div role="tabpanel" id="panel-components" aria-labelledby="tab-components" class="tab-panel" style="display:none">
    <section class="ds-section">
      <h2>Component Library</h2>

      <h3>Buttons</h3>
      <div class="component-row">
        <button class="btn btn-primary">Primary</button>
        <button class="btn btn-secondary">Secondary</button>
        <button class="btn btn-ghost">Ghost</button>
        <button class="btn btn-destructive">Destructive</button>
        <button class="btn btn-primary btn-disabled" disabled>Disabled</button>
        <button class="btn btn-primary btn-loading">Loading</button>
      </div>

      <h3>Form Inputs</h3>
      <div class="component-row">
        <input type="text" class="input-field" placeholder="Skill name..." value="SDLC">
        <input type="text" class="input-field" placeholder="Focus me...">
        <input type="text" class="input-field input-error" value="invalid-version" placeholder="Error state">
        <input type="text" class="input-field" disabled value="Disabled input">
      </div>
      <div class="component-row" style="margin-top:var(--space-2)">
        <select class="select-field">
          <option>Select version...</option>
          <option>2.0.0 (latest)</option>
          <option>1.1.0</option>
          <option>1.0.0 (deprecated)</option>
        </select>
      </div>
      <div class="component-row" style="margin-top:var(--space-3)">
        <label class="checkbox-wrapper"><input type="checkbox" checked> Active skills only</label>
        <label class="checkbox-wrapper"><input type="checkbox"> Include deprecated</label>
      </div>
      <div class="component-row" style="margin-top:var(--space-2)">
        <label class="radio-wrapper"><input type="radio" name="env" checked> Production</label>
        <label class="radio-wrapper"><input type="radio" name="env"> Development</label>
      </div>
      <div class="component-row" style="margin-top:var(--space-3)">
        <span style="font-size:var(--text-sm);margin-right:var(--space-2)">Cache:</span>
        <button class="toggle-switch active" id="toggle-demo" aria-label="Toggle cache"></button>
      </div>

      <h3 style="margin-top:var(--space-6)">Badges & Tags</h3>
      <div class="component-row">
        <span class="badge-component badge-active">● active</span>
        <span class="badge-component badge-deprecated">● deprecated</span>
        <span class="badge-component badge-info">P0</span>
        <span class="badge-component badge-primary">v2.0.0</span>
      </div>
      <div class="component-row" style="margin-top:var(--space-2)">
        <span class="tag-chip">sdlc</span>
        <span class="tag-chip">governance</span>
        <span class="tag-chip">development</span>
        <span class="tag-chip">security</span>
      </div>

      <h3 style="margin-top:var(--space-6)">Cards</h3>
      <div style="display:grid;grid-template-columns:repeat(auto-fill,minmax(260px,1fr));gap:var(--space-4)">
        <div class="card">
          <div class="card-header">SDLC <span class="badge-component badge-active" style="margin-left:var(--space-2)">● active</span></div>
          <div class="card-body">Software Development Lifecycle skill definition for enterprise governance compliance.</div>
          <div style="margin-top:var(--space-3);display:flex;gap:var(--space-2)">
            <span class="tag-chip">sdlc</span><span class="tag-chip">governance</span>
          </div>
          <div style="margin-top:var(--space-3);font-size:var(--text-xs);color:var(--color-text-muted)">Latest: 2.0.0 · Owner: it-standards-team</div>
        </div>
        <div class="card">
          <div class="card-header">Code-Review <span class="badge-component badge-active" style="margin-left:var(--space-2)">● active</span></div>
          <div class="card-body">Structured code review guidelines for AI-assisted development workflows.</div>
          <div style="margin-top:var(--space-3);display:flex;gap:var(--space-2)">
            <span class="tag-chip">review</span><span class="tag-chip">quality</span>
          </div>
          <div style="margin-top:var(--space-3);font-size:var(--text-xs);color:var(--color-text-muted)">Latest: 1.2.0 · Owner: dev-excellence</div>
        </div>
      </div>

      <h3 style="margin-top:var(--space-6)">Table</h3>
      <div class="table-wrapper">
        <table class="ds-table">
          <thead><tr><th>Version</th><th>Status</th><th>Branch</th><th>Commit SHA</th></tr></thead>
          <tbody>
            <tr><td style="font-family:var(--font-mono)">2.0.0</td><td><span class="badge-component badge-active">● active</span></td><td>main</td><td style="font-family:var(--font-mono);font-size:var(--text-xs)">a1b2c3d</td></tr>
            <tr><td style="font-family:var(--font-mono)">1.1.0</td><td><span class="badge-component badge-active">● active</span></td><td>main</td><td style="font-family:var(--font-mono);font-size:var(--text-xs)">e4f5g6h</td></tr>
            <tr><td style="font-family:var(--font-mono)">1.0.0</td><td><span class="badge-component badge-deprecated">● deprecated</span></td><td>main</td><td style="font-family:var(--font-mono);font-size:var(--text-xs)">i7j8k9l</td></tr>
          </tbody>
        </table>
      </div>

      <h3 style="margin-top:var(--space-6)">Alerts / Toasts</h3>
      <div class="alert alert-info"><span>ℹ</span><div><strong>Info:</strong> Cache hit — response served in 12ms from Redis.</div></div>
      <div class="alert alert-success"><span>✓</span><div><strong>Success:</strong> Skill SDLC v2.0.0 retrieved successfully.</div></div>
      <div class="alert alert-warning"><span>⚠</span><div><strong>Warning:</strong> SDLC 1.0.0 is deprecated; latest is 2.0.0.</div></div>
      <div class="alert alert-error"><span>✕</span><div><strong>Error:</strong> SKILL_NOT_FOUND — did you mean: SDLC, SDL-Process, SDLC-Lite?</div></div>

      <h3 style="margin-top:var(--space-6)">Tooltip</h3>
      <div class="component-row">
        <div class="tooltip-wrapper">
          <span class="badge-component badge-primary">v2.0.0</span>
          <span class="tooltip-content">Commit: a1b2c3d · Branch: main</span>
        </div>
        <div class="tooltip-wrapper">
          <span class="badge-component badge-deprecated">● deprecated</span>
          <span class="tooltip-content">Use latest version 2.0.0 instead</span>
        </div>
      </div>

      <h3 style="margin-top:var(--space-6)">Accordion</h3>
      <details class="accordion-item">
        <summary>YAML Frontmatter Schema</summary>
        <div class="accordion-body">
          <div class="code-block">---\nname: SDLC\nversion: 2.0.0\ndescription: "Software Development Lifecycle skill"\nowner: it-standards-team\nstatus: active\ntags:\n  - sdlc\n  - governance\n---</div>
        </div>
      </details>
      <details class="accordion-item">
        <summary>Error Response Schema</summary>
        <div class="accordion-body">
          <div class="code-block">{\n  "error": "SKILL_NOT_FOUND",\n  "message": "No skill found with name 'SDCL'",\n  "suggestions": ["SDLC", "SDL-Process"]\n}</div>
        </div>
      </details>

      <h3 style="margin-top:var(--space-6)">Modal (click to open)</h3>
      <div class="component-row">
        <button class="btn btn-primary" data-modal-target="demo-modal">Open Modal</button>
      </div>
      <div class="modal-overlay" id="demo-modal" style="display:none">
        <div class="modal-content">
          <div class="modal-header">Confirm Skill Pin</div>
          <p style="font-size:var(--text-sm);color:var(--color-text-secondary)">Pin SDLC v2.0.0 (commit a1b2c3d) as the active skill version for this agent session?</p>
          <div class="modal-footer">
            <button class="btn btn-secondary" data-modal-close>Cancel</button>
            <button class="btn btn-primary" data-modal-close>Confirm Pin</button>
          </div>
        </div>
      </div>

      <h3 style="margin-top:var(--space-6)">Navigation — Breadcrumbs</h3>
      <div class="breadcrumb">
        <a href="#">Catalog</a><span class="separator">›</span>
        <a href="#">SDLC</a><span class="separator">›</span>
        <span class="current">v2.0.0</span>
      </div>

      <h3 style="margin-top:var(--space-6)">Navigation — Sidebar Items</h3>
      <div style="background:var(--color-surface);padding:var(--space-4);border-radius:var(--radius-md);max-width:240px">
        <div class="sidebar-item active">📋 Catalog</div>
        <div class="sidebar-item">🔍 Search</div>
        <div class="sidebar-item">📊 Versions</div>
        <div class="sidebar-item">⚙ Settings</div>
        <div class="sidebar-item">📖 Docs</div>
      </div>

      <h3 style="margin-top:var(--space-6)">Dropdown Menu</h3>
      <div style="position:relative;display:inline-block">
        <button class="btn btn-secondary" id="dropdown-trigger">Environment ▾</button>
        <div class="dropdown-menu" id="dropdown-menu" style="display:none;position:absolute;top:100%;left:0;margin-top:4px;z-index:100">
          <div class="dropdown-item">Production (main)</div>
          <div class="dropdown-item">Development (dev)</div>
        </div>
      </div>

      <h3 style="margin-top:var(--space-6)">Code Block</h3>
      <div class="code-block">POST /it-standard/mcp HTTP/1.1\nAuthorization: Bearer eyJhbGciOiJSUzI1NiIs...\nContent-Type: application/json\n\n{\n  "jsonrpc": "2.0",\n  "method": "tools/call",\n  "params": {\n    "name": "get_skill",\n    "arguments": { "name": "SDLC", "version": "2.0.0" }\n  },\n  "id": 1\n}</div>
    </section>
  </div>

  <!-- Spacing & Layout Panel -->
  <div role="tabpanel" id="panel-spacing" aria-labelledby="tab-spacing" class="tab-panel" style="display:none">
    <section class="ds-section">
      <h2>Spacing Scale (4px grid)</h2>
      <div class="spacing-row"><span class="spacing-label">--space-1 · 4px</span><div class="spacing-bar" style="width:4px"></div></div>
      <div class="spacing-row"><span class="spacing-label">--space-2 · 8px</span><div class="spacing-bar" style="width:8px"></div></div>
      <div class="spacing-row"><span class="spacing-label">--space-3 · 12px</span><div class="spacing-bar" style="width:12px"></div></div>
      <div class="spacing-row"><span class="spacing-label">--space-4 · 16px</span><div class="spacing-bar" style="width:16px"></div></div>
      <div class="spacing-row"><span class="spacing-label">--space-5 · 20px</span><div class="spacing-bar" style="width:20px"></div></div>
      <div class="spacing-row"><span class="spacing-label">--space-6 · 24px</span><div class="spacing-bar" style="width:24px"></div></div>
      <div class="spacing-row"><span class="spacing-label">--space-8 · 32px</span><div class="spacing-bar" style="width:32px"></div></div>
      <div class="spacing-row"><span class="spacing-label">--space-10 · 40px</span><div class="spacing-bar" style="width:40px"></div></div>
      <div class="spacing-row"><span class="spacing-label">--space-12 · 48px</span><div class="spacing-bar" style="width:48px"></div></div>
      <div class="spacing-row"><span class="spacing-label">--space-16 · 64px</span><div class="spacing-bar" style="width:64px"></div></div>
      <div class="spacing-row"><span class="spacing-label">--space-24 · 96px</span><div class="spacing-bar" style="width:96px"></div></div>

      <h3 style="margin-top:var(--space-8)">Shadows & Elevation</h3>
      <div class="shadow-grid">
        <div class="shadow-box" style="box-shadow:var(--shadow-sm)"><div style="height:40px"></div><div class="label">shadow-sm</div></div>
        <div class="shadow-box" style="box-shadow:var(--shadow-md)"><div style="height:40px"></div><div class="label">shadow-md</div></div>
        <div class="shadow-box" style="box-shadow:var(--shadow-lg)"><div style="height:40px"></div><div class="label">shadow-lg</div></div>
        <div class="shadow-box" style="box-shadow:var(--shadow-xl)"><div style="height:40px"></div><div class="label">shadow-xl</div></div>
      </div>

      <h3 style="margin-top:var(--space-8)">Border Radius</h3>
      <div class="radius-grid">
        <div><div class="radius-box" style="border-radius:var(--radius-sm)">sm · 4px</div><div style="text-align:center;font-size:var(--text-xs);color:var(--color-text-muted)">--radius-sm</div></div>
        <div><div class="radius-box" style="border-radius:var(--radius-md)">md · 8px</div><div style="text-align:center;font-size:var(--text-xs);color:var(--color-text-muted)">--radius-md</div></div>
        <div><div class="radius-box" style="border-radius:var(--radius-lg)">lg · 12px</div><div style="text-align:center;font-size:var(--text-xs);color:var(--color-text-muted)">--radius-lg</div></div>
        <div><div class="radius-box" style="border-radius:var(--radius-full)">full</div><div style="text-align:center;font-size:var(--text-xs);color:var(--color-text-muted)">--radius-full</div></div>
      </div>

      <h3 style="margin-top:var(--space-8)">Icons</h3>
      <div class="icon-grid">
        <div class="icon-item"><span class="icon">📋</span>Catalog</div>
        <div class="icon-item"><span class="icon">🔍</span>Search</div>
        <div class="icon-item"><span class="icon">📊</span>Versions</div>
        <div class="icon-item"><span class="icon">✓</span>Success</div>
        <div class="icon-item"><span class="icon">⚠</span>Warning</div>
        <div class="icon-item"><span class="icon">✕</span>Error</div>
        <div class="icon-item"><span class="icon">ℹ</span>Info</div>
        <div class="icon-item"><span class="icon">⚙</span>Settings</div>
        <div class="icon-item"><span class="icon">🔒</span>Auth</div>
        <div class="icon-item"><span class="icon">📖</span>Docs</div>
        <div class="icon-item"><span class="icon">🏷</span>Tag</div>
        <div class="icon-item"><span class="icon">⏱</span>Latency</div>
      </div>
    </section>
  </div>

  <!-- Data Patterns Panel -->
  <div role="tabpanel" id="panel-patterns" aria-labelledby="tab-patterns" class="tab-panel" style="display:none">
    <section class="ds-section">
      <h2>MCP Response Presentation Patterns</h2>
      <p style="color:var(--color-text-secondary);margin-bottom:var(--space-6)">These patterns define how IDE embeddings and MCP clients should render tool responses. No standalone UI exists — these are machine-facing rendering guidelines.</p>

      <h3>Skill Card Pattern</h3>
      <div class="card" style="max-width:500px;margin-bottom:var(--space-4)">
        <div style="display:flex;justify-content:space-between;align-items:center">
          <div class="card-header" style="margin-bottom:0">SDLC</div>
          <span class="badge-component badge-active">● active</span>
        </div>
        <div class="card-body" style="margin-top:var(--space-2)">Software Development Lifecycle skill for enterprise governance compliance and best practices.</div>
        <div style="display:flex;gap:var(--space-2);margin-top:var(--space-3);flex-wrap:wrap">
          <span class="tag-chip">sdlc</span><span class="tag-chip">governance</span><span class="tag-chip">development</span>
        </div>
        <div style="margin-top:var(--space-4);padding-top:var(--space-3);border-top:1px solid var(--color-border);display:flex;justify-content:space-between;font-size:var(--text-xs);color:var(--color-text-muted)">
          <span>Latest: <strong style="color:var(--color-text)">2.0.0</strong></span>
          <span>Owner: it-standards-team</span>
        </div>
      </div>

      <h3>Error Response Pattern</h3>
      <div class="code-block" style="max-width:500px;margin-bottom:var(--space-4)">{\n  "isError": true,\n  "content": [{\n    "type": "text",\n    "text": "SKILL_NOT_FOUND: No skill 'SDCL'.\\nDid you mean: SDLC, SDL-Process?"\n  }]\n}</div>

      <h3>Deprecation Warning Pattern</h3>
      <div class="alert alert-warning" style="max-width:500px">
        <span>⚠</span>
        <div>
          <strong>Deprecated Version:</strong> SDLC 1.0.0 is deprecated. Latest is 2.0.0.<br>
          <span style="font-size:var(--text-xs);color:var(--color-text-muted)">commit_sha: i7j8k9l · branch: main</span>
        </div>
      </div>

      <h3 style="margin-top:var(--space-6)">Cache Status Indicator Pattern</h3>
      <div style="display:flex;gap:var(--space-4);flex-wrap:wrap">
        <div class="alert alert-success" style="flex:1;min-width:200px"><span>✓</span><div><strong>Cache Hit</strong><br><span style="font-size:var(--text-xs)">p95: 12ms · Redis key: skill:main:SDLC:2.0.0</span></div></div>
        <div class="alert alert-info" style="flex:1;min-width:200px"><span>ℹ</span><div><strong>Cache Miss</strong><br><span style="font-size:var(--text-xs)">Fetched from GitHub API · p95: 1,200ms</span></div></div>
      </div>
    </section>
  </div>
</div>

<script>
(function() {
  var isDark = false;
  var toggleBtn = document.querySelector('.theme-toggle');
  toggleBtn.addEventListener('click', function() {
    isDark = !isDark;
    if (isDark) {
      document.documentElement.setAttribute('data-theme', 'dark');
      toggleBtn.textContent = '🌙';
    } else {
      document.documentElement.removeAttribute('data-theme');
      toggleBtn.textContent = '☀';
    }
  });

  // Tabs
  var tabs = document.querySelectorAll('[role="tab"]');
  var panels = document.querySelectorAll('[role="tabpanel"]');
  tabs.forEach(function(tab) {
    tab.addEventListener('click', function() {
      tabs.forEach(function(t) { t.setAttribute('aria-selected', 'false'); });
      panels.forEach(function(p) { p.style.display = 'none'; });
      tab.setAttribute('aria-selected', 'true');
      var panelId = tab.getAttribute('aria-controls');
      document.getElementById(panelId).style.display = 'block';
    });
  });

  // Toggle switch
  var toggleSwitch = document.getElementById('toggle-demo');
  if (toggleSwitch) {
    toggleSwitch.addEventListener('click', function() {
      this.classList.toggle('active');
    });
  }

  // Modal
  document.querySelectorAll('[data-modal-target]').forEach(function(btn) {
    btn.addEventListener('click', function() {
      var modalId = this.getAttribute('data-modal-target');
      document.getElementById(modalId).style.display = 'flex';
    });
  });
  document.querySelectorAll('[data-modal-close]').forEach(function(btn) {
    btn.addEventListener('click', function() {
      this.closest('.modal-overlay').style.display = 'none';
    });
  });
  document.querySelectorAll('.modal-overlay').forEach(function(overlay) {
    overlay.addEventListener('click', function(e) {
      if (e.target === overlay) overlay.style.display = 'none';
    });
  });

  // Dropdown
  var ddTrigger = document.getElementById('dropdown-trigger');
  var ddMenu = document.getElementById('dropdown-menu');
  if (ddTrigger && ddMenu) {
    ddTrigger.addEventListener('click', function(e) {
      e.stopPropagation();
      ddMenu.style.display = ddMenu.style.display === 'none' ? 'block' : 'none';
    });
    document.addEventListener('click', function() {
      ddMenu.style.display = 'none';
    });
    ddMenu.querySelectorAll('.dropdown-item').forEach(function(item) {
      item.addEventListener('click', function() {
        ddTrigger.textContent = this.textContent + ' ▾';
        ddMenu.style.display = 'none';
      });
    });
  }

  // Sidebar items
  document.querySelectorAll('.sidebar-item').forEach(function(item) {
    item.addEventListener('click', function() {
      document.querySelectorAll('.sidebar-item').forEach(function(i) { i.classList.remove('active'); });
      this.classList.add('active');
    });
  });
})();
</script>
</body>
</html>
```

**Source:** intent  
**Provenance:** intent: Vision statement — machine-facing response presentation patterns for IDE/MCP client embeddings | chat: User confirmed: No standalone human UI; document only machine-facing response presentation patterns | assessment: WCAG 2.1 AA not directly applicable — no user-facing UI; patterns apply to future UI

---

## MCP Tool Response Viewer

The primary IDE embedding panel that renders MCP tool call responses. This screen simulates how an AI agent's IDE plugin or chat interface would present the five MCP tools' outputs: list_skills catalog view, search results, version history, skill content display (get_skill / get_latest_skill). It shows the JSON-RPC request on the left and the rendered response on the right, enabling developers to understand the data contracts and response structures. Interactive elements include tool selector tabs, parameter input fields, and response rendering.

### Component Hierarchy
```
ToolResponseViewer
├── ThemeToggle
├── PageHeader
│   ├── Title
│   ├── Description
│   └── EnvironmentSelector (prod/dev toggle)
├── MainContent (2-column grid)
│   ├── RequestPanel
│   │   ├── PanelTitle
│   │   ├── ToolTabs (tablist)
│   │   │   ├── Tab: list_skills
│   │   │   ├── Tab: search_skills
│   │   │   ├── Tab: list_versions
│   │   │   ├── Tab: get_skill
│   │   │   └── Tab: get_latest_skill
│   │   ├── ToolPanel (per tool)
│   │   │   ├── ParameterInputs[] (name, version, query)
│   │   │   ├── RequestCodeBlock (JSON-RPC preview)
│   │   │   └── SendButton
│   └── ResponsePanel
│       ├── PanelTitle
│       ├── ResponseMeta (status, latency, cache, sha)
│       ├── ResponseList (SkillCard[])
│       ├── ResponseVersions (VersionTable)
│       ├── ResponseContent (SkillMarkdown)
│       └── DeprecationWarning
```

### HTML Preview
```html
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>IT-Standard MCP — Tool Response Viewer</title>
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&family=JetBrains+Mono:wght@400;500&display=swap" rel="stylesheet">
<style>
:root {
  --color-primary: #0068B5; --color-primary-hover: #005494; --color-primary-light: #E8F2FB;
  --color-secondary: #00C7B7; --color-accent: #7C3AED; --color-accent-light: #EDE9FE;
  --color-bg: #FFFFFF; --color-surface: #F8FAFC; --color-surface-raised: #FFFFFF;
  --color-text: #0F172A; --color-text-secondary: #475569; --color-text-muted: #94A3B8;
  --color-success: #059669; --color-success-bg: #ECFDF5;
  --color-warning: #D97706; --color-warning-bg: #FFFBEB;
  --color-error: #DC2626; --color-error-bg: #FEF2F2;
  --color-info: #0284C7; --color-info-bg: #F0F9FF;
  --color-border: #E2E8F0; --color-border-strong: #CBD5E1;
  --color-code-bg: #F1F5F9;
  --color-badge-active: #059669; --color-badge-active-bg: #ECFDF5;
  --color-badge-deprecated: #D97706; --color-badge-deprecated-bg: #FFFBEB;
  --font-sans: 'Inter', -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif;
  --font-mono: 'JetBrains Mono', 'Fira Code', 'Consolas', monospace;
  --text-xs: 0.75rem; --text-sm: 0.875rem; --text-base: 1rem; --text-lg: 1.125rem; --text-xl: 1.25rem; --text-2xl: 1.5rem; --text-3xl: 1.875rem;
  --weight-regular: 400; --weight-medium: 500; --weight-semibold: 600; --weight-bold: 700;
  --leading-tight: 1.25; --leading-normal: 1.5;
  --space-1: 4px; --space-2: 8px; --space-3: 12px; --space-4: 16px; --space-5: 20px; --space-6: 24px; --space-8: 32px; --space-12: 48px;
  --shadow-sm: 0 1px 2px 0 rgba(0,0,0,0.05); --shadow-md: 0 4px 6px -1px rgba(0,0,0,0.1), 0 2px 4px -2px rgba(0,0,0,0.1); --shadow-lg: 0 10px 15px -3px rgba(0,0,0,0.1), 0 4px 6px -4px rgba(0,0,0,0.1);
  --radius-sm: 4px; --radius-md: 8px; --radius-lg: 12px; --radius-full: 9999px;
  --transition-fast: 150ms ease;
}
[data-theme="dark"] {
  --color-primary: #60A5FA; --color-primary-hover: #93C5FD; --color-primary-light: #1E3A5F;
  --color-secondary: #34D399; --color-accent: #A78BFA; --color-accent-light: #2E1065;
  --color-bg: #0F172A; --color-surface: #1E293B; --color-surface-raised: #334155;
  --color-text: #F1F5F9; --color-text-secondary: #CBD5E1; --color-text-muted: #64748B;
  --color-success: #34D399; --color-success-bg: #064E3B;
  --color-warning: #FBBF24; --color-warning-bg: #78350F;
  --color-error: #F87171; --color-error-bg: #7F1D1D;
  --color-info: #38BDF8; --color-info-bg: #0C4A6E;
  --color-border: #334155; --color-border-strong: #475569;
  --color-code-bg: #1E293B;
  --color-badge-active: #34D399; --color-badge-active-bg: #064E3B;
  --color-badge-deprecated: #FBBF24; --color-badge-deprecated-bg: #78350F;
  --shadow-sm: 0 1px 2px 0 rgba(0,0,0,0.3); --shadow-md: 0 4px 6px -1px rgba(0,0,0,0.4), 0 2px 4px -2px rgba(0,0,0,0.3); --shadow-lg: 0 10px 15px -3px rgba(0,0,0,0.5), 0 4px 6px -4px rgba(0,0,0,0.4);
}
* { margin:0; padding:0; box-sizing:border-box; }
body { font-family: var(--font-sans); background: var(--color-bg); color: var(--color-text); line-height: var(--leading-normal); }
.theme-toggle { position:fixed; top:12px; right:12px; z-index:9999; background:var(--color-surface-raised); border:1px solid var(--color-border); border-radius:var(--radius-full); width:40px; height:40px; cursor:pointer; display:flex; align-items:center; justify-content:center; font-size:18px; transition:background var(--transition-fast); box-shadow:var(--shadow-sm); }
.theme-toggle:hover { background:var(--color-primary-light); }
.page-header { background:var(--color-surface); border-bottom:1px solid var(--color-border); padding:var(--space-4) var(--space-6); }
.page-header h1 { font-size:var(--text-xl); font-weight:var(--weight-bold); }
.page-header p { font-size:var(--text-sm); color:var(--color-text-secondary); margin-top:var(--space-1); }
.env-selector { display:inline-flex; gap:0; margin-top:var(--space-3); border:1px solid var(--color-border); border-radius:var(--radius-md); overflow:hidden; }
.env-btn { padding:var(--space-1) var(--space-4); font-size:var(--text-xs); font-weight:var(--weight-medium); background:var(--color-surface-raised); border:none; cursor:pointer; font-family:var(--font-sans); color:var(--color-text-secondary); transition:all var(--transition-fast); }
.env-btn.active { background:var(--color-primary); color:#FFF; }
.env-btn:hover:not(.active) { background:var(--color-primary-light); }
.main-content { display:grid; grid-template-columns:1fr 1fr; gap:0; min-height:calc(100vh - 100px); }
.request-panel { border-right:1px solid var(--color-border); padding:var(--space-6); overflow-y:auto; }
.response-panel { padding:var(--space-6); overflow-y:auto; background:var(--color-surface); }
.panel-title { font-size:var(--text-sm); font-weight:var(--weight-semibold); text-transform:uppercase; letter-spacing:0.05em; color:var(--color-text-muted); margin-bottom:var(--space-4); }
.tool-tabs { display:flex; gap:0; border:1px solid var(--color-border); border-radius:var(--radius-md); overflow:hidden; margin-bottom:var(--space-6); flex-wrap:wrap; }
.tool-tab { padding:var(--space-2) var(--space-3); font-size:var(--text-xs); font-weight:var(--weight-medium); background:var(--color-surface-raised); border:none; cursor:pointer; font-family:var(--font-mono); color:var(--color-text-secondary); transition:all var(--transition-fast); border-right:1px solid var(--color-border); }
.tool-tab:last-child { border-right:none; }
.tool-tab[aria-selected="true"] { background:var(--color-primary); color:#FFF; }
.tool-tab:hover:not([aria-selected="true"]) { background:var(--color-primary-light); }
.param-group { margin-bottom:var(--space-4); }
.param-label { font-size:var(--text-xs); font-weight:var(--weight-medium); color:var(--color-text-secondary); margin-bottom:var(--space-1); display:block; }
.param-input { width:100%; padding:var(--space-2) var(--space-3); border:1px solid var(--color-border); border-radius:var(--radius-md); font-size:var(--text-sm); font-family:var(--font-mono); background:var(--color-surface-raised); color:var(--color-text); }
.param-input:focus { outline:none; border-color:var(--color-primary); box-shadow:0 0 0 3px rgba(0,104,181,0.15); }
.send-btn { width:100%; padding:var(--space-3); background:var(--color-primary); color:#FFF; border:none; border-radius:var(--radius-md); font-size:var(--text-sm); font-weight:var(--weight-semibold); cursor:pointer; font-family:var(--font-sans); transition:background var(--transition-fast); margin-top:var(--space-4); }
.send-btn:hover { background:var(--color-primary-hover); }
.code-block { background:var(--color-code-bg); border:1px solid var(--color-border); border-radius:var(--radius-md); padding:var(--space-4); font-family:var(--font-mono); font-size:var(--text-xs); overflow-x:auto; line-height:1.6; white-space:pre; }
.response-meta { display:flex; gap:var(--space-4); margin-bottom:var(--space-4); flex-wrap:wrap; }
.meta-item { font-size:var(--text-xs); padding:var(--space-1) var(--space-3); background:var(--color-surface-raised); border:1px solid var(--color-border); border-radius:var(--radius-full); display:flex; align-items:center; gap:var(--space-1); }
.meta-dot { width:6px; height:6px; border-radius:50%; }
.skill-card { background:var(--color-surface-raised); border:1px solid var(--color-border); border-radius:var(--radius-lg); padding:var(--space-4); margin-bottom:var(--space-3); box-shadow:var(--shadow-sm); transition:box-shadow var(--transition-fast); }
.skill-card:hover { box-shadow:var(--shadow-md); }
.skill-card-header { display:flex; justify-content:space-between; align-items:center; margin-bottom:var(--space-2); }
.skill-name { font-weight:var(--weight-semibold); font-size:var(--text-base); font-family:var(--font-mono); }
.badge { display:inline-flex; padding:2px var(--space-2); border-radius:var(--radius-full); font-size:var(--text-xs); font-weight:var(--weight-medium); }
.badge-active { background:var(--color-badge-active-bg); color:var(--color-badge-active); }
.badge-deprecated { background:var(--color-badge-deprecated-bg); color:var(--color-badge-deprecated); }
.skill-desc { font-size:var(--text-sm); color:var(--color-text-secondary); margin-bottom:var(--space-3); }
.tag-row { display:flex; gap:var(--space-2); flex-wrap:wrap; }
.tag { font-size:var(--text-xs); padding:2px var(--space-2); background:var(--color-surface); border:1px solid var(--color-border); border-radius:var(--radius-full); color:var(--color-text-secondary); }
.skill-footer { display:flex; justify-content:space-between; font-size:var(--text-xs); color:var(--color-text-muted); margin-top:var(--space-3); padding-top:var(--space-3); border-top:1px solid var(--color-border); }
.alert { padding:var(--space-3) var(--space-4); border-radius:var(--radius-md); font-size:var(--text-sm); display:flex; gap:var(--space-3); align-items:flex-start; margin-bottom:var(--space-4); }
.alert-warning { background:var(--color-warning-bg); color:var(--color-warning); border:1px solid var(--color-warning); }
.alert-success { background:var(--color-success-bg); color:var(--color-success); border:1px solid var(--color-success); }
.skill-content { background:var(--color-surface-raised); border:1px solid var(--color-border); border-radius:var(--radius-md); padding:var(--space-6); font-size:var(--text-sm); line-height:1.7; }
.skill-content h2 { font-size:var(--text-lg); font-weight:var(--weight-bold); margin:var(--space-4) 0 var(--space-2); }
.skill-content h3 { font-size:var(--text-base); font-weight:var(--weight-semibold); margin:var(--space-3) 0 var(--space-2); }
.skill-content p { margin-bottom:var(--space-3); color:var(--color-text-secondary); }
.skill-content ul { margin:0 0 var(--space-3) var(--space-6); color:var(--color-text-secondary); }
.version-table { width:100%; border-collapse:collapse; font-size:var(--text-sm); }
.version-table th { text-align:left; padding:var(--space-3) var(--space-4); background:var(--color-surface); font-weight:var(--weight-semibold); border-bottom:2px solid var(--color-border); }
.version-table td { padding:var(--space-3) var(--space-4); border-bottom:1px solid var(--color-border); }
.version-table tr:hover { background:var(--color-primary-light); }
@media (max-width: 768px) {
  .main-content { grid-template-columns:1fr; }
  .request-panel { border-right:none; border-bottom:1px solid var(--color-border); }
  .tool-tabs { flex-wrap:wrap; }
}
</style>
</head>
<body>
<button class="theme-toggle" aria-label="Toggle theme">☀</button>

<header class="page-header">
  <h1>🔧 MCP Tool Response Viewer</h1>
  <p>Interactive request/response explorer for the five IT-Standard MCP tools</p>
  <div class="env-selector">
    <button class="env-btn active" data-env="prod">Production</button>
    <button class="env-btn" data-env="dev">Development</button>
  </div>
</header>

<div class="main-content">
  <div class="request-panel">
    <div class="panel-title">Request</div>
    <div role="tablist" class="tool-tabs" aria-label="MCP Tools">
      <button role="tab" aria-selected="true" aria-controls="tool-panel-list" id="ttab-list" class="tool-tab">list_skills</button>
      <button role="tab" aria-selected="false" aria-controls="tool-panel-search" id="ttab-search" class="tool-tab">search_skills</button>
      <button role="tab" aria-selected="false" aria-controls="tool-panel-versions" id="ttab-versions" class="tool-tab">list_versions</button>
      <button role="tab" aria-selected="false" aria-controls="tool-panel-get" id="ttab-get" class="tool-tab">get_skill</button>
      <button role="tab" aria-selected="false" aria-controls="tool-panel-latest" id="ttab-latest" class="tool-tab">get_latest_skill</button>
    </div>

    <!-- list_skills -->
    <div role="tabpanel" id="tool-panel-list" aria-labelledby="ttab-list">
      <p style="font-size:var(--text-sm);color:var(--color-text-secondary);margin-bottom:var(--space-4)">Returns all skills in the catalog. No parameters required.</p>
      <div class="code-block">{
  "jsonrpc": "2.0",
  "method": "tools/call",
  "params": {
    "name": "list_skills",
    "arguments": {}
  },
  "id": 1
}</div>
      <button class="send-btn" data-tool="list">▶ Send Request</button>
    </div>

    <!-- search_skills -->
    <div role="tabpanel" id="tool-panel-search" aria-labelledby="ttab-search" style="display:none">
      <div class="param-group">
        <label class="param-label">query <span style="color:var(--color-error)">*</span></label>
        <input type="text" class="param-input" id="search-query" placeholder="e.g. security, governance" value="security">
      </div>
      <div class="code-block">{
  "jsonrpc": "2.0",
  "method": "tools/call",
  "params": {
    "name": "search_skills",
    "arguments": { "query": "security" }
  },
  "id": 2
}</div>
      <button class="send-btn" data-tool="search">▶ Send Request</button>
    </div>

    <!-- list_versions -->
    <div role="tabpanel" id="tool-panel-versions" aria-labelledby="ttab-versions" style="display:none">
      <div class="param-group">
        <label class="param-label">name <span style="color:var(--color-error)">*</span></label>
        <input type="text" class="param-input" id="versions-name" placeholder="e.g. SDLC" value="SDLC">
      </div>
      <div class="code-block">{
  "jsonrpc": "2.0",
  "method": "tools/call",
  "params": {
    "name": "list_versions",
    "arguments": { "name": "SDLC" }
  },
  "id": 3
}</div>
      <button class="send-btn" data-tool="versions">▶ Send Request</button>
    </div>

    <!-- get_skill -->
    <div role="tabpanel" id="tool-panel-get" aria-labelledby="ttab-get" style="display:none">
      <div class="param-group">
        <label class="param-label">name <span style="color:var(--color-error)">*</span></label>
        <input type="text" class="param-input" id="get-name" placeholder="e.g. SDLC" value="SDLC">
      </div>
      <div class="param-group">
        <label class="param-label">version <span style="color:var(--color-error)">*</span></label>
        <input type="text" class="param-input" id="get-version" placeholder="e.g. 2.0.0" value="2.0.0">
      </div>
      <div class="code-block">{
  "jsonrpc": "2.0",
  "method": "tools/call",
  "params": {
    "name": "get_skill",
    "arguments": { "name": "SDLC", "version": "2.0.0" }
  },
  "id": 4
}</div>
      <button class="send-btn" data-tool="get">▶ Send Request</button>
    </div>

    <!-- get_latest_skill -->
    <div role="tabpanel" id="tool-panel-latest" aria-labelledby="ttab-latest" style="display:none">
      <div class="param-group">
        <label class="param-label">name <span style="color:var(--color-error)">*</span></label>
        <input type="text" class="param-input" id="latest-name" placeholder="e.g. SDLC" value="SDLC">
      </div>
      <div class="code-block">{
  "jsonrpc": "2.0",
  "method": "tools/call",
  "params": {
    "name": "get_latest_skill",
    "arguments": { "name": "SDLC" }
  },
  "id": 5
}</div>
      <button class="send-btn" data-tool="latest">▶ Send Request</button>
    </div>
  </div>

  <div class="response-panel">
    <div class="panel-title">Response</div>
    <div id="response-area">
      <div class="response-meta">
        <span class="meta-item"><span class="meta-dot" style="background:var(--color-success)"></span> 200 OK</span>
        <span class="meta-item">⏱ 12ms</span>
        <span class="meta-item">📦 Cache Hit</span>
        <span class="meta-item" style="font-family:var(--font-mono)">sha: a1b2c3d</span>
      </div>

      <div id="response-list">
        <div class="skill-card">
          <div class="skill-card-header">
            <span class="skill-name">SDLC</span>
            <span class="badge badge-active">● active</span>
          </div>
          <div class="skill-desc">Software Development Lifecycle skill for enterprise governance compliance and best practices.</div>
          <div class="tag-row"><span class="tag">sdlc</span><span class="tag">governance</span><span class="tag">development</span></div>
          <div class="skill-footer"><span>Latest: 2.0.0</span><span>Owner: it-standards-team</span></div>
        </div>
        <div class="skill-card">
          <div class="skill-card-header">
            <span class="skill-name">Code-Review</span>
            <span class="badge badge-active">● active</span>
          </div>
          <div class="skill-desc">Structured code review guidelines for AI-assisted development workflows.</div>
          <div class="tag-row"><span class="tag">review</span><span class="tag">quality</span><span class="tag">code</span></div>
          <div class="skill-footer"><span>Latest: 1.2.0</span><span>Owner: dev-excellence</span></div>
        </div>
        <div class="skill-card">
          <div class="skill-card-header">
            <span class="skill-name">Security-Baseline</span>
            <span class="badge badge-active">● active</span>
          </div>
          <div class="skill-desc">Security baseline configuration skill for infrastructure and application hardening.</div>
          <div class="tag-row"><span class="tag">security</span><span class="tag">infra</span><span class="tag">compliance</span></div>
          <div class="skill-footer"><span>Latest: 3.1.0</span><span>Owner: security-team</span></div>
        </div>
        <div class="skill-card">
          <div class="skill-card-header">
            <span class="skill-name">API-Design</span>
            <span class="badge badge-deprecated">● deprecated</span>
          </div>
          <div class="skill-desc">API design conventions and REST endpoint naming standards. Superseded by API-Standards.</div>
          <div class="tag-row"><span class="tag">api</span><span class="tag">rest</span><span class="tag">design</span></div>
          <div class="skill-footer"><span>Latest: 1.0.0</span><span>Owner: api-team</span></div>
        </div>
      </div>

      <div id="response-versions" style="display:none">
        <div style="margin-bottom:var(--space-4);font-size:var(--text-lg);font-weight:var(--weight-semibold);font-family:var(--font-mono)">SDLC — Version History</div>
        <div style="overflow-x:auto;border:1px solid var(--color-border);border-radius:var(--radius-md)">
          <table class="version-table">
            <thead><tr><th>Version</th><th>Status</th><th>Path</th></tr></thead>
            <tbody>
              <tr><td style="font-family:var(--font-mono);font-weight:var(--weight-semibold)">2.0.0</td><td><span class="badge badge-active">● active</span></td><td style="font-family:var(--font-mono);font-size:var(--text-xs)">/skills/SDLC/SDLC-2.0.0/SKILL.md</td></tr>
              <tr><td style="font-family:var(--font-mono)">1.1.0</td><td><span class="badge badge-active">● active</span></td><td style="font-family:var(--font-mono);font-size:var(--text-xs)">/skills/SDLC/SDLC-1.1.0/SKILL.md</td></tr>
              <tr><td style="font-family:var(--font-mono)">1.0.0</td><td><span class="badge badge-deprecated">● deprecated</span></td><td style="font-family:var(--font-mono);font-size:var(--text-xs)">/skills/SDLC/SDLC-1.0.0/SKILL.md</td></tr>
            </tbody>
          </table>
        </div>
      </div>

      <div id="response-content" style="display:none">
        <div class="alert alert-success"><span>✓</span><div><strong>Skill retrieved</strong> — SDLC v2.0.0 · branch: main · commit: a1b2c3d</div></div>
        <div class="skill-content">
          <h2>SDLC — Software Development Lifecycle</h2>
          <p>This skill defines the standard Software Development Lifecycle process for all Intel engineering teams. It covers planning, development, testing, deployment, and maintenance phases with governance checkpoints.</p>
          <h3>Planning Phase</h3>
          <ul>
            <li>Define project scope and objectives aligned with business goals</li>
            <li>Conduct stakeholder analysis and identify decision makers</li>
            <li>Create a risk assessment matrix with mitigation strategies</li>
          </ul>
          <h3>Development Phase</h3>
          <ul>
            <li>Follow branch-based development with feature branches from main</li>
            <li>Apply clean code principles: single responsibility, dependency injection</li>
            <li>Write unit tests with ≥80% code coverage for business logic</li>
          </ul>
          <h3>Deployment Phase</h3>
          <ul>
            <li>Use automated CI/CD pipelines with security scanning gates</li>
            <li>Implement blue-green or rolling deployments for zero downtime</li>
            <li>Validate health endpoints post-deployment before traffic routing</li>
          </ul>
        </div>
      </div>

      <div id="response-deprecated" style="display:none">
        <div class="alert alert-warning"><span>⚠</span><div><strong>Deprecation Warning:</strong> SDLC 1.0.0 is deprecated; latest is 2.0.0. Consider upgrading for the latest governance standards.</div></div>
      </div>
    </div>
  </div>
</div>

<script>
(function() {
  var isDark = false;
  var toggleBtn = document.querySelector('.theme-toggle');
  toggleBtn.addEventListener('click', function() {
    isDark = !isDark;
    document.documentElement.setAttribute('data-theme', isDark ? 'dark' : '');
    if (!isDark) document.documentElement.removeAttribute('data-theme');
    toggleBtn.textContent = isDark ? '🌙' : '☀';
  });

  // Environment selector
  document.querySelectorAll('.env-btn').forEach(function(btn) {
    btn.addEventListener('click', function() {
      document.querySelectorAll('.env-btn').forEach(function(b) { b.classList.remove('active'); });
      this.classList.add('active');
    });
  });

  // Tool tabs
  var toolTabs = document.querySelectorAll('.tool-tab');
  var toolPanels = document.querySelectorAll('[id^="tool-panel-"]');
  var responseViews = {
    'ttab-list': function() { showResponse('list'); },
    'ttab-search': function() { showResponse('list'); },
    'ttab-versions': function() { showResponse('versions'); },
    'ttab-get': function() { showResponse('content'); },
    'ttab-latest': function() { showResponse('content'); }
  };

  toolTabs.forEach(function(tab) {
    tab.addEventListener('click', function() {
      toolTabs.forEach(function(t) { t.setAttribute('aria-selected', 'false'); });
      toolPanels.forEach(function(p) { p.style.display = 'none'; });
      tab.setAttribute('aria-selected', 'true');
      var panelId = tab.getAttribute('aria-controls');
      document.getElementById(panelId).style.display = 'block';
    });
  });

  function showResponse(type) {
    document.getElementById('response-list').style.display = type === 'list' ? 'block' : 'none';
    document.getElementById('response-versions').style.display = type === 'versions' ? 'block' : 'none';
    document.getElementById('response-content').style.display = type === 'content' ? 'block' : 'none';
    document.getElementById('response-deprecated').style.display = type === 'content' ? 'block' : 'none';
  }

  // Send buttons
  document.querySelectorAll('.send-btn').forEach(function(btn) {
    btn.addEventListener('click', function() {
      var tool = this.getAttribute('data-tool');
      if (tool === 'list' || tool === 'search') showResponse('list');
      else if (tool === 'versions') showResponse('versions');
      else showResponse('content');

      this.textContent = '⏳ Loading...';
      var self = this;
      setTimeout(function() { self.textContent = '▶ Send Request'; }, 600);
    });
  });

  showResponse('list');
})();
</script>
</body>
</html>
```

**Source:** intent  
**Provenance:** intent: Core Feature: Five MCP tools — list_skills, search_skills, list_versions, get_skill, get_latest_skill; US-001: list all available skills in the catalog; US-002: retrieve a specific skill by name and exact version; US-003: retrieve the latest version of a skill by name only; US-004: search for skills by keyword; US-005: list all versions of a specific skill | chat: User confirmed: document machine-facing response presentation patterns for IDE/MCP client embeddings | assessment: MCP Tool API Surface — five tools with defined input/output contracts

---

## Skill Catalog Dashboard

Dashboard view showing the full skill catalog as rendered within an IDE sidebar or agent chat panel. Displays all skills with filtering by status (active/deprecated), search functionality, and tag-based filtering. This is the primary discovery interface that an MCP client would render after calling list_skills. Includes aggregate statistics (total skills, active count, deprecated count) and quick-access cards for each skill.

### Component Hierarchy
```
SkillCatalogDashboard
├── ThemeToggle
├── Container
│   ├── PageHeader
│   │   ├── Title + EnvironmentBadge
│   │   └── Description (branch, SHA, refresh timestamp)
│   ├── StatsRow
│   │   ├── StatCard: Total Skills
│   │   ├── StatCard: Active
│   │   ├── StatCard: Deprecated
│   │   └── StatCard: Total Versions
│   ├── Controls
│   │   ├── SearchBox
│   │   ├── StatusFilterGroup (All / Active / Deprecated)
│   │   └── ViewToggle (Grid / List)
│   ├── GridView
│   │   └── SkillCard[]
│   │       ├── SkillCardTop (name + status badge)
│   │       ├── Description
│   │       ├── TagRow (clickable tags)
│   │       └── SkillMeta (version, owner)
│   └── ListView
│       └── ListTable
│           ├── ListHeader
│           └── ListRow[] (name, desc, status, version, count)
```

### HTML Preview
```html
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>IT-Standard MCP — Skill Catalog</title>
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&family=JetBrains+Mono:wght@400;500&display=swap" rel="stylesheet">
<style>
:root {
  --color-primary: #0068B5; --color-primary-hover: #005494; --color-primary-light: #E8F2FB;
  --color-secondary: #00C7B7; --color-accent: #7C3AED;
  --color-bg: #FFFFFF; --color-surface: #F8FAFC; --color-surface-raised: #FFFFFF;
  --color-text: #0F172A; --color-text-secondary: #475569; --color-text-muted: #94A3B8;
  --color-success: #059669; --color-success-bg: #ECFDF5;
  --color-warning: #D97706; --color-warning-bg: #FFFBEB;
  --color-error: #DC2626; --color-error-bg: #FEF2F2;
  --color-info: #0284C7; --color-info-bg: #F0F9FF;
  --color-border: #E2E8F0; --color-border-strong: #CBD5E1;
  --color-code-bg: #F1F5F9;
  --color-badge-active: #059669; --color-badge-active-bg: #ECFDF5;
  --color-badge-deprecated: #D97706; --color-badge-deprecated-bg: #FFFBEB;
  --font-sans: 'Inter', -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif;
  --font-mono: 'JetBrains Mono', 'Fira Code', 'Consolas', monospace;
  --text-xs: 0.75rem; --text-sm: 0.875rem; --text-base: 1rem; --text-lg: 1.125rem; --text-xl: 1.25rem; --text-2xl: 1.5rem; --text-3xl: 1.875rem;
  --weight-regular: 400; --weight-medium: 500; --weight-semibold: 600; --weight-bold: 700;
  --leading-normal: 1.5;
  --space-1: 4px; --space-2: 8px; --space-3: 12px; --space-4: 16px; --space-6: 24px; --space-8: 32px; --space-12: 48px;
  --shadow-sm: 0 1px 2px 0 rgba(0,0,0,0.05); --shadow-md: 0 4px 6px -1px rgba(0,0,0,0.1), 0 2px 4px -2px rgba(0,0,0,0.1);
  --radius-sm: 4px; --radius-md: 8px; --radius-lg: 12px; --radius-full: 9999px;
  --transition-fast: 150ms ease;
}
[data-theme="dark"] {
  --color-primary: #60A5FA; --color-primary-hover: #93C5FD; --color-primary-light: #1E3A5F;
  --color-secondary: #34D399; --color-accent: #A78BFA;
  --color-bg: #0F172A; --color-surface: #1E293B; --color-surface-raised: #334155;
  --color-text: #F1F5F9; --color-text-secondary: #CBD5E1; --color-text-muted: #64748B;
  --color-success: #34D399; --color-success-bg: #064E3B;
  --color-warning: #FBBF24; --color-warning-bg: #78350F;
  --color-error: #F87171; --color-error-bg: #7F1D1D;
  --color-info: #38BDF8; --color-info-bg: #0C4A6E;
  --color-border: #334155; --color-border-strong: #475569;
  --color-code-bg: #1E293B;
  --color-badge-active: #34D399; --color-badge-active-bg: #064E3B;
  --color-badge-deprecated: #FBBF24; --color-badge-deprecated-bg: #78350F;
  --shadow-sm: 0 1px 2px 0 rgba(0,0,0,0.3); --shadow-md: 0 4px 6px -1px rgba(0,0,0,0.4), 0 2px 4px -2px rgba(0,0,0,0.3);
}
* { margin:0; padding:0; box-sizing:border-box; }
body { font-family: var(--font-sans); background: var(--color-bg); color: var(--color-text); line-height: var(--leading-normal); }
.theme-toggle { position:fixed; top:12px; right:12px; z-index:9999; background:var(--color-surface-raised); border:1px solid var(--color-border); border-radius:var(--radius-full); width:40px; height:40px; cursor:pointer; display:flex; align-items:center; justify-content:center; font-size:18px; box-shadow:var(--shadow-sm); }
.theme-toggle:hover { background:var(--color-primary-light); }
.container { max-width:1100px; margin:0 auto; padding:var(--space-8); }
.page-title { font-size:var(--text-2xl); font-weight:var(--weight-bold); margin-bottom:var(--space-2); }
.page-desc { color:var(--color-text-secondary); font-size:var(--text-sm); margin-bottom:var(--space-6); }
.stats-row { display:grid; grid-template-columns:repeat(4,1fr); gap:var(--space-4); margin-bottom:var(--space-8); }
.stat-card { background:var(--color-surface-raised); border:1px solid var(--color-border); border-radius:var(--radius-lg); padding:var(--space-4) var(--space-6); text-align:center; box-shadow:var(--shadow-sm); }
.stat-value { font-size:var(--text-2xl); font-weight:var(--weight-bold); }
.stat-label { font-size:var(--text-xs); color:var(--color-text-muted); margin-top:var(--space-1); text-transform:uppercase; letter-spacing:0.05em; }
.controls { display:flex; gap:var(--space-4); margin-bottom:var(--space-6); flex-wrap:wrap; align-items:center; }
.search-box { flex:1; min-width:200px; padding:var(--space-2) var(--space-4); border:1px solid var(--color-border); border-radius:var(--radius-md); font-size:var(--text-sm); font-family:var(--font-sans); background:var(--color-surface-raised); color:var(--color-text); }
.search-box:focus { outline:none; border-color:var(--color-primary); box-shadow:0 0 0 3px rgba(0,104,181,0.15); }
.filter-group { display:flex; gap:0; border:1px solid var(--color-border); border-radius:var(--radius-md); overflow:hidden; }
.filter-btn { padding:var(--space-2) var(--space-3); font-size:var(--text-xs); font-weight:var(--weight-medium); background:var(--color-surface-raised); border:none; cursor:pointer; font-family:var(--font-sans); color:var(--color-text-secondary); transition:all var(--transition-fast); border-right:1px solid var(--color-border); }
.filter-btn:last-child { border-right:none; }
.filter-btn.active { background:var(--color-primary); color:#FFF; }
.filter-btn:hover:not(.active) { background:var(--color-primary-light); }
.view-toggle { display:flex; gap:0; border:1px solid var(--color-border); border-radius:var(--radius-md); overflow:hidden; }
.view-btn { padding:var(--space-2) var(--space-3); font-size:var(--text-sm); background:var(--color-surface-raised); border:none; cursor:pointer; color:var(--color-text-secondary); transition:all var(--transition-fast); border-right:1px solid var(--color-border); }
.view-btn:last-child { border-right:none; }
.view-btn.active { background:var(--color-primary); color:#FFF; }
.skill-grid { display:grid; grid-template-columns:repeat(auto-fill,minmax(320px,1fr)); gap:var(--space-4); }
.skill-card { background:var(--color-surface-raised); border:1px solid var(--color-border); border-radius:var(--radius-lg); padding:var(--space-5); box-shadow:var(--shadow-sm); transition:all var(--transition-fast); cursor:pointer; }
.skill-card:hover { box-shadow:var(--shadow-md); border-color:var(--color-primary); }
.skill-card-top { display:flex; justify-content:space-between; align-items:flex-start; margin-bottom:var(--space-2); }
.skill-name { font-weight:var(--weight-semibold); font-size:var(--text-base); font-family:var(--font-mono); }
.badge { display:inline-flex; padding:2px var(--space-2); border-radius:var(--radius-full); font-size:var(--text-xs); font-weight:var(--weight-medium); }
.badge-active { background:var(--color-badge-active-bg); color:var(--color-badge-active); }
.badge-deprecated { background:var(--color-badge-deprecated-bg); color:var(--color-badge-deprecated); }
.skill-desc { font-size:var(--text-sm); color:var(--color-text-secondary); margin-bottom:var(--space-3); line-height:1.5; }
.tags { display:flex; gap:var(--space-2); flex-wrap:wrap; margin-bottom:var(--space-3); }
.tag { font-size:var(--text-xs); padding:2px var(--space-2); background:var(--color-surface); border:1px solid var(--color-border); border-radius:var(--radius-full); color:var(--color-text-secondary); cursor:pointer; transition:all var(--transition-fast); }
.tag:hover { border-color:var(--color-primary); color:var(--color-primary); }
.skill-meta { display:flex; justify-content:space-between; font-size:var(--text-xs); color:var(--color-text-muted); padding-top:var(--space-3); border-top:1px solid var(--color-border); }
.skill-list-view { display:none; }
.list-row { display:grid; grid-template-columns:180px 1fr 100px 120px 100px; gap:var(--space-4); padding:var(--space-3) var(--space-4); border-bottom:1px solid var(--color-border); font-size:var(--text-sm); align-items:center; transition:background var(--transition-fast); cursor:pointer; }
.list-row:hover { background:var(--color-primary-light); }
.list-header { font-weight:var(--weight-semibold); background:var(--color-surface); border-bottom:2px solid var(--color-border); }
.list-header:hover { background:var(--color-surface); }
.env-badge { display:inline-flex; padding:var(--space-1) var(--space-3); border-radius:var(--radius-full); font-size:var(--text-xs); font-weight:var(--weight-semibold); margin-left:var(--space-3); }
.env-prod { background:var(--color-success-bg); color:var(--color-success); }
@media (max-width: 768px) {
  .stats-row { grid-template-columns:repeat(2,1fr); }
  .skill-grid { grid-template-columns:1fr; }
  .controls { flex-direction:column; }
  .list-row { grid-template-columns:1fr; gap:var(--space-1); }
  .list-header { display:none; }
}
</style>
</head>
<body>
<button class="theme-toggle" aria-label="Toggle theme">☀</button>
<div class="container">
  <div style="display:flex;align-items:center;gap:var(--space-3)">
    <h1 class="page-title">📋 Skill Catalog</h1>
    <span class="env-badge env-prod">Production</span>
  </div>
  <p class="page-desc">Browse all available enterprise AI agent skills. <span style="font-family:var(--font-mono);font-size:var(--text-xs)">Branch: main · SHA: a1b2c3d · Last refresh: 12s ago</span></p>

  <div class="stats-row">
    <div class="stat-card"><div class="stat-value" style="color:var(--color-primary)">52</div><div class="stat-label">Total Skills</div></div>
    <div class="stat-card"><div class="stat-value" style="color:var(--color-success)">47</div><div class="stat-label">Active</div></div>
    <div class="stat-card"><div class="stat-value" style="color:var(--color-warning)">5</div><div class="stat-label">Deprecated</div></div>
    <div class="stat-card"><div class="stat-value" style="color:var(--color-accent)">184</div><div class="stat-label">Total Versions</div></div>
  </div>

  <div class="controls">
    <input type="text" class="search-box" placeholder="🔍 Search skills by name, description, or tags..." id="search-input">
    <div class="filter-group">
      <button class="filter-btn active" data-filter="all">All</button>
      <button class="filter-btn" data-filter="active">Active</button>
      <button class="filter-btn" data-filter="deprecated">Deprecated</button>
    </div>
    <div class="view-toggle">
      <button class="view-btn active" data-view="grid" aria-label="Grid view">▦</button>
      <button class="view-btn" data-view="list" aria-label="List view">☰</button>
    </div>
  </div>

  <div class="skill-grid" id="grid-view">
    <div class="skill-card" data-status="active" data-name="sdlc" data-tags="sdlc governance development">
      <div class="skill-card-top"><span class="skill-name">SDLC</span><span class="badge badge-active">● active</span></div>
      <div class="skill-desc">Software Development Lifecycle skill for enterprise governance compliance and best practices.</div>
      <div class="tags"><span class="tag">sdlc</span><span class="tag">governance</span><span class="tag">development</span></div>
      <div class="skill-meta"><span>Latest: <strong>2.0.0</strong></span><span>3 versions · it-standards-team</span></div>
    </div>
    <div class="skill-card" data-status="active" data-name="code-review" data-tags="review quality code">
      <div class="skill-card-top"><span class="skill-name">Code-Review</span><span class="badge badge-active">● active</span></div>
      <div class="skill-desc">Structured code review guidelines for AI-assisted development workflows.</div>
      <div class="tags"><span class="tag">review</span><span class="tag">quality</span><span class="tag">code</span></div>
      <div class="skill-meta"><span>Latest: <strong>1.2.0</strong></span><span>3 versions · dev-excellence</span></div>
    </div>
    <div class="skill-card" data-status="active" data-name="security-baseline" data-tags="security infra compliance">
      <div class="skill-card-top"><span class="skill-name">Security-Baseline</span><span class="badge badge-active">● active</span></div>
      <div class="skill-desc">Security baseline configuration skill for infrastructure and application hardening.</div>
      <div class="tags"><span class="tag">security</span><span class="tag">infra</span><span class="tag">compliance</span></div>
      <div class="skill-meta"><span>Latest: <strong>3.1.0</strong></span><span>5 versions · security-team</span></div>
    </div>
    <div class="skill-card" data-status="active" data-name="testing-strategy" data-tags="testing qa automation">
      <div class="skill-card-top"><span class="skill-name">Testing-Strategy</span><span class="badge badge-active">● active</span></div>
      <div class="skill-desc">Comprehensive testing strategy for unit, integration, and end-to-end test automation.</div>
      <div class="tags"><span class="tag">testing</span><span class="tag">qa</span><span class="tag">automation</span></div>
      <div class="skill-meta"><span>Latest: <strong>1.0.0</strong></span><span>1 version · qa-team</span></div>
    </div>
    <div class="skill-card" data-status="deprecated" data-name="api-design" data-tags="api rest design">
      <div class="skill-card-top"><span class="skill-name">API-Design</span><span class="badge badge-deprecated">● deprecated</span></div>
      <div class="skill-desc">API design conventions and REST endpoint naming standards. Superseded by API-Standards.</div>
      <div class="tags"><span class="tag">api</span><span class="tag">rest</span><span class="tag">design</span></div>
      <div class="skill-meta"><span>Latest: <strong>1.0.0</strong></span><span>1 version · api-team</span></div>
    </div>
    <div class="skill-card" data-status="active" data-name="incident-response" data-tags="incident ops sre">
      <div class="skill-card-top"><span class="skill-name">Incident-Response</span><span class="badge badge-active">● active</span></div>
      <div class="skill-desc">Incident response playbook for production systems. Covers detection, triage, mitigation, and postmortem.</div>
      <div class="tags"><span class="tag">incident</span><span class="tag">ops</span><span class="tag">sre</span></div>
      <div class="skill-meta"><span>Latest: <strong>2.1.0</strong></span><span>4 versions · sre-team</span></div>
    </div>
  </div>

  <div class="skill-list-view" id="list-view">
    <div style="border:1px solid var(--color-border);border-radius:var(--radius-md);overflow:hidden">
      <div class="list-row list-header"><span>Name</span><span>Description</span><span>Status</span><span>Latest</span><span>Versions</span></div>
      <div class="list-row" data-status="active"><span style="font-family:var(--font-mono);font-weight:var(--weight-semibold)">SDLC</span><span style="color:var(--color-text-secondary)">Software Development Lifecycle skill</span><span><span class="badge badge-active">● active</span></span><span style="font-family:var(--font-mono)">2.0.0</span><span>3</span></div>
      <div class="list-row" data-status="active"><span style="font-family:var(--font-mono);font-weight:var(--weight-semibold)">Code-Review</span><span style="color:var(--color-text-secondary)">Structured code review guidelines</span><span><span class="badge badge-active">● active</span></span><span style="font-family:var(--font-mono)">1.2.0</span><span>3</span></div>
      <div class="list-row" data-status="active"><span style="font-family:var(--font-mono);font-weight:var(--weight-semibold)">Security-Baseline</span><span style="color:var(--color-text-secondary)">Security baseline configuration skill</span><span><span class="badge badge-active">● active</span></span><span style="font-family:var(--font-mono)">3.1.0</span><span>5</span></div>
      <div class="list-row" data-status="deprecated"><span style="font-family:var(--font-mono);font-weight:var(--weight-semibold)">API-Design</span><span style="color:var(--color-text-secondary)">API design conventions (deprecated)</span><span><span class="badge badge-deprecated">● deprecated</span></span><span style="font-family:var(--font-mono)">1.0.0</span><span>1</span></div>
    </div>
  </div>
</div>

<script>
(function() {
  var isDark = false;
  document.querySelector('.theme-toggle').addEventListener('click', function() {
    isDark = !isDark;
    document.documentElement.setAttribute('data-theme', isDark ? 'dark' : '');
    if (!isDark) document.documentElement.removeAttribute('data-theme');
    this.textContent = isDark ? '🌙' : '☀';
  });

  // Filter buttons
  document.querySelectorAll('.filter-btn').forEach(function(btn) {
    btn.addEventListener('click', function() {
      document.querySelectorAll('.filter-btn').forEach(function(b) { b.classList.remove('active'); });
      this.classList.add('active');
      var filter = this.getAttribute('data-filter');
      document.querySelectorAll('.skill-card').forEach(function(card) {
        if (filter === 'all') card.style.display = '';
        else card.style.display = card.getAttribute('data-status') === filter ? '' : 'none';
      });
    });
  });

  // View toggle
  document.querySelectorAll('.view-btn').forEach(function(btn) {
    btn.addEventListener('click', function() {
      document.querySelectorAll('.view-btn').forEach(function(b) { b.classList.remove('active'); });
      this.classList.add('active');
      var view = this.getAttribute('data-view');
      document.getElementById('grid-view').style.display = view === 'grid' ? 'grid' : 'none';
      document.getElementById('list-view').style.display = view === 'list' ? 'block' : 'none';
    });
  });

  // Search
  document.getElementById('search-input').addEventListener('input', function() {
    var q = this.value.toLowerCase();
    document.querySelectorAll('.skill-card').forEach(function(card) {
      var name = card.getAttribute('data-name') || '';
      var tags = card.getAttribute('data-tags') || '';
      var desc = card.querySelector('.skill-desc') ? card.querySelector('.skill-desc').textContent.toLowerCase() : '';
      card.style.display = (name.indexOf(q) > -1 || tags.indexOf(q) > -1 || desc.indexOf(q) > -1) ? '' : 'none';
    });
  });

  // Tag click filters search
  document.querySelectorAll('.tag').forEach(function(tag) {
    tag.addEventListener('click', function(e) {
      e.stopPropagation();
      var input = document.getElementById('search-input');
      input.value = this.textContent;
      input.dispatchEvent(new Event('input'));
    });
  });
})();
</script>
</body>
</html>
```

**Source:** intent  
**Provenance:** intent: US-001: list all available skills in the catalog; US-004: search for skills by keyword; Business Objective: Drive adoption of standardized skill consumption | assessment: Target catalog size: 500 skills with up to 20 versions each

---

## Skill Detail & Version Browser

Detailed view of a single skill showing its full content (rendered SKILL.md), version history with status indicators, metadata (owner, tags, commit SHA), and deprecation warnings. This screen corresponds to the combined output of get_skill, get_latest_skill, and list_versions. It includes a version selector dropdown, raw JSON response toggle, and a 'pin this version' action pattern for agents to reference.

### Component Hierarchy
```
SkillDetail
├── ThemeToggle
├── Container
│   ├── Breadcrumb (Catalog > SDLC > v2.0.0)
│   ├── SkillHeader
│   │   ├── TitleBlock (name + badge + description)
│   │   └── Actions
│   │       ├── VersionSelector (dropdown)
│   │       ├── PinVersionButton
│   │       └── RawJSONToggle
│   ├── DeprecationAlert (conditional)
│   ├── MetaGrid
│   │   ├── MetaCard: Version
│   │   ├── MetaCard: Branch
│   │   ├── MetaCard: Commit SHA
│   │   ├── MetaCard: Owner
│   │   ├── MetaCard: Status
│   │   └── MetaCard: Tags
│   ├── ContentTabs
│   │   ├── Tab: Content
│   │   ├── Tab: Versions
│   │   └── Tab: JSON Response
│   ├── ContentPanel (rendered SKILL.md)
│   ├── VersionsPanel (timeline)
│   │   └── VersionItem[] (dot + version + status + path)
│   └── JSONPanel (raw response code block)
```

### HTML Preview
```html
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>IT-Standard MCP — Skill Detail</title>
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&family=JetBrains+Mono:wght@400;500&display=swap" rel="stylesheet">
<style>
:root {
  --color-primary: #0068B5; --color-primary-hover: #005494; --color-primary-light: #E8F2FB;
  --color-secondary: #00C7B7; --color-accent: #7C3AED; --color-accent-light: #EDE9FE;
  --color-bg: #FFFFFF; --color-surface: #F8FAFC; --color-surface-raised: #FFFFFF;
  --color-text: #0F172A; --color-text-secondary: #475569; --color-text-muted: #94A3B8;
  --color-success: #059669; --color-success-bg: #ECFDF5;
  --color-warning: #D97706; --color-warning-bg: #FFFBEB;
  --color-error: #DC2626; --color-error-bg: #FEF2F2;
  --color-info: #0284C7; --color-info-bg: #F0F9FF;
  --color-border: #E2E8F0; --color-border-strong: #CBD5E1;
  --color-code-bg: #F1F5F9;
  --color-badge-active: #059669; --color-badge-active-bg: #ECFDF5;
  --color-badge-deprecated: #D97706; --color-badge-deprecated-bg: #FFFBEB;
  --font-sans: 'Inter', -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif;
  --font-mono: 'JetBrains Mono', 'Fira Code', 'Consolas', monospace;
  --text-xs: 0.75rem; --text-sm: 0.875rem; --text-base: 1rem; --text-lg: 1.125rem; --text-xl: 1.25rem; --text-2xl: 1.5rem;
  --weight-regular: 400; --weight-medium: 500; --weight-semibold: 600; --weight-bold: 700;
  --leading-normal: 1.5;
  --space-1: 4px; --space-2: 8px; --space-3: 12px; --space-4: 16px; --space-5: 20px; --space-6: 24px; --space-8: 32px;
  --shadow-sm: 0 1px 2px 0 rgba(0,0,0,0.05); --shadow-md: 0 4px 6px -1px rgba(0,0,0,0.1), 0 2px 4px -2px rgba(0,0,0,0.1); --shadow-lg: 0 10px 15px -3px rgba(0,0,0,0.1);
  --radius-sm: 4px; --radius-md: 8px; --radius-lg: 12px; --radius-full: 9999px;
  --transition-fast: 150ms ease;
}
[data-theme="dark"] {
  --color-primary: #60A5FA; --color-primary-hover: #93C5FD; --color-primary-light: #1E3A5F;
  --color-secondary: #34D399; --color-accent: #A78BFA; --color-accent-light: #2E1065;
  --color-bg: #0F172A; --color-surface: #1E293B; --color-surface-raised: #334155;
  --color-text: #F1F5F9; --color-text-secondary: #CBD5E1; --color-text-muted: #64748B;
  --color-success: #34D399; --color-success-bg: #064E3B;
  --color-warning: #FBBF24; --color-warning-bg: #78350F;
  --color-error: #F87171; --color-error-bg: #7F1D1D;
  --color-info: #38BDF8; --color-info-bg: #0C4A6E;
  --color-border: #334155; --color-border-strong: #475569;
  --color-code-bg: #1E293B;
  --color-badge-active: #34D399; --color-badge-active-bg: #064E3B;
  --color-badge-deprecated: #FBBF24; --color-badge-deprecated-bg: #78350F;
  --shadow-sm: 0 1px 2px 0 rgba(0,0,0,0.3); --shadow-md: 0 4px 6px -1px rgba(0,0,0,0.4), 0 2px 4px -2px rgba(0,0,0,0.3);
}
* { margin:0; padding:0; box-sizing:border-box; }
body { font-family:var(--font-sans); background:var(--color-bg); color:var(--color-text); line-height:var(--leading-normal); }
.theme-toggle { position:fixed; top:12px; right:12px; z-index:9999; background:var(--color-surface-raised); border:1px solid var(--color-border); border-radius:var(--radius-full); width:40px; height:40px; cursor:pointer; display:flex; align-items:center; justify-content:center; font-size:18px; box-shadow:var(--shadow-sm); }
.container { max-width:1000px; margin:0 auto; padding:var(--space-8); }
.breadcrumb { display:flex; gap:var(--space-2); font-size:var(--text-sm); margin-bottom:var(--space-6); }
.breadcrumb a { color:var(--color-primary); text-decoration:none; }
.breadcrumb a:hover { text-decoration:underline; }
.breadcrumb .sep { color:var(--color-text-muted); }
.skill-header { display:flex; justify-content:space-between; align-items:flex-start; margin-bottom:var(--space-6); flex-wrap:wrap; gap:var(--space-4); }
.skill-title-block h1 { font-size:var(--text-2xl); font-weight:var(--weight-bold); font-family:var(--font-mono); display:flex; align-items:center; gap:var(--space-3); }
.badge { display:inline-flex; padding:2px var(--space-2); border-radius:var(--radius-full); font-size:var(--text-xs); font-weight:var(--weight-medium); }
.badge-active { background:var(--color-badge-active-bg); color:var(--color-badge-active); }
.badge-deprecated { background:var(--color-badge-deprecated-bg); color:var(--color-badge-deprecated); }
.skill-title-block .desc { color:var(--color-text-secondary); font-size:var(--text-sm); margin-top:var(--space-2); }
.skill-actions { display:flex; gap:var(--space-3); align-items:center; }
.btn { display:inline-flex; align-items:center; gap:var(--space-2); padding:var(--space-2) var(--space-4); border-radius:var(--radius-md); font-size:var(--text-sm); font-weight:var(--weight-medium); font-family:var(--font-sans); cursor:pointer; border:1px solid transparent; transition:all var(--transition-fast); }
.btn-primary { background:var(--color-primary); color:#FFF; }
.btn-primary:hover { background:var(--color-primary-hover); }
.btn-secondary { background:var(--color-surface); color:var(--color-text); border-color:var(--color-border); }
.btn-secondary:hover { border-color:var(--color-primary); background:var(--color-primary-light); }
.version-selector { padding:var(--space-2) var(--space-3); border:1px solid var(--color-border); border-radius:var(--radius-md); font-size:var(--text-sm); font-family:var(--font-mono); background:var(--color-surface-raised); color:var(--color-text); }
.version-selector:focus { outline:none; border-color:var(--color-primary); }
.meta-grid { display:grid; grid-template-columns:repeat(auto-fill,minmax(200px,1fr)); gap:var(--space-4); margin-bottom:var(--space-6); }
.meta-card { background:var(--color-surface); padding:var(--space-4); border-radius:var(--radius-md); border:1px solid var(--color-border); }
.meta-label { font-size:var(--text-xs); color:var(--color-text-muted); text-transform:uppercase; letter-spacing:0.05em; margin-bottom:var(--space-1); }
.meta-value { font-size:var(--text-sm); font-weight:var(--weight-medium); font-family:var(--font-mono); }
.tags { display:flex; gap:var(--space-2); flex-wrap:wrap; }
.tag { font-size:var(--text-xs); padding:2px var(--space-2); background:var(--color-surface-raised); border:1px solid var(--color-border); border-radius:var(--radius-full); color:var(--color-text-secondary); }
.alert { padding:var(--space-3) var(--space-4); border-radius:var(--radius-md); font-size:var(--text-sm); display:flex; gap:var(--space-3); align-items:flex-start; margin-bottom:var(--space-6); }
.alert-warning { background:var(--color-warning-bg); color:var(--color-warning); border:1px solid var(--color-warning); }
.content-tabs { display:flex; border-bottom:2px solid var(--color-border); margin-bottom:0; }
.content-tab { padding:var(--space-3) var(--space-4); font-size:var(--text-sm); font-weight:var(--weight-medium); color:var(--color-text-muted); cursor:pointer; border-bottom:2px solid transparent; margin-bottom:-2px; transition:all var(--transition-fast); background:none; border-top:none; border-left:none; border-right:none; font-family:var(--font-sans); }
.content-tab:hover { color:var(--color-text); }
.content-tab[aria-selected="true"] { color:var(--color-primary); border-bottom-color:var(--color-primary); }
.tab-panel { padding:var(--space-6) 0; }
.skill-content { background:var(--color-surface-raised); border:1px solid var(--color-border); border-radius:var(--radius-md); padding:var(--space-6); }
.skill-content h2 { font-size:var(--text-lg); font-weight:var(--weight-bold); margin:var(--space-4) 0 var(--space-2); padding-bottom:var(--space-2); border-bottom:1px solid var(--color-border); }
.skill-content h3 { font-size:var(--text-base); font-weight:var(--weight-semibold); margin:var(--space-3) 0 var(--space-2); }
.skill-content p { margin-bottom:var(--space-3); color:var(--color-text-secondary); font-size:var(--text-sm); }
.skill-content ul { margin:0 0 var(--space-3) var(--space-6); color:var(--color-text-secondary); font-size:var(--text-sm); }
.skill-content li { margin-bottom:var(--space-1); }
.code-block { background:var(--color-code-bg); border:1px solid var(--color-border); border-radius:var(--radius-md); padding:var(--space-4); font-family:var(--font-mono); font-size:var(--text-xs); overflow-x:auto; line-height:1.6; white-space:pre; }
.version-timeline { position:relative; }
.version-item { display:flex; gap:var(--space-4); padding:var(--space-4); border-left:2px solid var(--color-border); margin-left:var(--space-3); position:relative; }
.version-item::before { content:''; position:absolute; left:-7px; top:var(--space-4); width:12px; height:12px; border-radius:50%; background:var(--color-surface-raised); border:2px solid var(--color-border); }
.version-item.current::before { background:var(--color-primary); border-color:var(--color-primary); }
.version-item.deprecated::before { background:var(--color-warning); border-color:var(--color-warning); }
.version-info { flex:1; }
.version-number { font-family:var(--font-mono); font-weight:var(--weight-semibold); font-size:var(--text-base); }
.version-meta { font-size:var(--text-xs); color:var(--color-text-muted); margin-top:var(--space-1); }
@media (max-width: 768px) {
  .skill-header { flex-direction:column; }
  .meta-grid { grid-template-columns:1fr 1fr; }
}
</style>
</head>
<body>
<button class="theme-toggle" aria-label="Toggle theme">☀</button>
<div class="container">
  <nav class="breadcrumb"><a href="#">Catalog</a><span class="sep">›</span><a href="#">SDLC</a><span class="sep">›</span><span style="color:var(--color-text-secondary)">v2.0.0</span></nav>

  <div class="skill-header">
    <div class="skill-title-block">
      <h1>SDLC <span class="badge badge-active">● active</span></h1>
      <p class="desc">Software Development Lifecycle skill for enterprise governance compliance and best practices.</p>
    </div>
    <div class="skill-actions">
      <select class="version-selector" id="version-select">
        <option value="2.0.0" selected>v2.0.0 (latest)</option>
        <option value="1.1.0">v1.1.0</option>
        <option value="1.0.0">v1.0.0 (deprecated)</option>
      </select>
      <button class="btn btn-primary">📌 Pin Version</button>
      <button class="btn btn-secondary" id="raw-toggle">{ } Raw JSON</button>
    </div>
  </div>

  <div id="deprecation-alert" style="display:none">
    <div class="alert alert-warning"><span>⚠</span><div><strong>Deprecation Warning:</strong> This version (1.0.0) is deprecated. The latest version is 2.0.0. Consider upgrading for the latest governance standards.</div></div>
  </div>

  <div class="meta-grid">
    <div class="meta-card"><div class="meta-label">Version</div><div class="meta-value" id="meta-version">2.0.0</div></div>
    <div class="meta-card"><div class="meta-label">Branch</div><div class="meta-value">main</div></div>
    <div class="meta-card"><div class="meta-label">Commit SHA</div><div class="meta-value">a1b2c3d</div></div>
    <div class="meta-card"><div class="meta-label">Owner</div><div class="meta-value">it-standards-team</div></div>
    <div class="meta-card"><div class="meta-label">Status</div><div class="meta-value" id="meta-status"><span class="badge badge-active">● active</span></div></div>
    <div class="meta-card"><div class="meta-label">Tags</div><div class="tags"><span class="tag">sdlc</span><span class="tag">governance</span><span class="tag">development</span></div></div>
  </div>

  <div role="tablist" class="content-tabs">
    <button role="tab" aria-selected="true" aria-controls="panel-content" id="ctab-content" class="content-tab">📄 Content</button>
    <button role="tab" aria-selected="false" aria-controls="panel-versions" id="ctab-versions" class="content-tab">📊 Versions (3)</button>
    <button role="tab" aria-selected="false" aria-controls="panel-json" id="ctab-json" class="content-tab">{ } JSON Response</button>
  </div>

  <div role="tabpanel" id="panel-content" aria-labelledby="ctab-content" class="tab-panel">
    <div class="skill-content">
      <h2>Overview</h2>
      <p>This skill defines the standard Software Development Lifecycle process for all Intel engineering teams. It covers planning, development, testing, deployment, and maintenance phases with governance checkpoints at each stage.</p>
      <h2>Planning Phase</h2>
      <p>All projects must begin with a planning phase that establishes scope, identifies stakeholders, and assesses risk.</p>
      <ul>
        <li>Define project scope and objectives aligned with business goals</li>
        <li>Conduct stakeholder analysis and identify decision makers</li>
        <li>Create a risk assessment matrix with mitigation strategies</li>
        <li>Establish success criteria and measurable KPIs</li>
      </ul>
      <h2>Development Phase</h2>
      <p>Development follows branch-based workflows with mandatory code review and automated testing.</p>
      <ul>
        <li>Use feature branches from main with descriptive naming conventions</li>
        <li>Apply clean code principles: single responsibility, dependency injection, explicit error handling</li>
        <li>Write unit tests with ≥80% code coverage for business logic</li>
        <li>Run static analysis (SonarQube) and dependency scanning (Snyk) before merge</li>
      </ul>
      <h2>Testing Phase</h2>
      <ul>
        <li>Execute integration tests against staging environment</li>
        <li>Perform security testing including SAST and DAST scans</li>
        <li>Validate performance against defined SLOs (p95 latency, throughput)</li>
      </ul>
      <h2>Deployment Phase</h2>
      <ul>
        <li>Use Forge Shipping Engine for automated CI/CD pipelines</li>
        <li>Implement rolling deployments with health check validation</li>
        <li>Gate production deployment behind manual approval for critical services</li>
        <li>Monitor post-deployment health for 15 minutes before declaring success</li>
      </ul>
    </div>
  </div>

  <div role="tabpanel" id="panel-versions" aria-labelledby="ctab-versions" class="tab-panel" style="display:none">
    <div class="version-timeline">
      <div class="version-item current">
        <div class="version-info">
          <div class="version-number">2.0.0 <span class="badge badge-active" style="margin-left:var(--space-2)">● active</span> <span class="badge" style="background:var(--color-primary-light);color:var(--color-primary);margin-left:var(--space-1)">latest</span></div>
          <div class="version-meta">Path: /skills/SDLC/SDLC-2.0.0/SKILL.md · Major rewrite with Forge Shipping integration</div>
        </div>
      </div>
      <div class="version-item">
        <div class="version-info">
          <div class="version-number">1.1.0 <span class="badge badge-active" style="margin-left:var(--space-2)">● active</span></div>
          <div class="version-meta">Path: /skills/SDLC/SDLC-1.1.0/SKILL.md · Added testing phase details</div>
        </div>
      </div>
      <div class="version-item deprecated">
        <div class="version-info">
          <div class="version-number">1.0.0 <span class="badge badge-deprecated" style="margin-left:var(--space-2)">● deprecated</span></div>
          <div class="version-meta">Path: /skills/SDLC/SDLC-1.0.0/SKILL.md · Initial release</div>
        </div>
      </div>
    </div>
  </div>

  <div role="tabpanel" id="panel-json" aria-labelledby="ctab-json" class="tab-panel" style="display:none">
    <div class="code-block">{
  "jsonrpc": "2.0",
  "result": {
    "content": [{
      "type": "text",
      "text": "# SDLC — Software Development Lifecycle\n\n## Overview\nThis skill defines the standard..."
    }],
    "metadata": {
      "name": "SDLC",
      "version": "2.0.0",
      "status": "active",
      "branch": "main",
      "commit_sha": "a1b2c3d4e5f6",
      "path": "/skills/SDLC/SDLC-2.0.0/SKILL.md",
      "owner": "it-standards-team",
      "tags": ["sdlc", "governance", "development"],
      "description": "Software Development Lifecycle skill"
    }
  },
  "id": 4
}</div>
  </div>
</div>

<script>
(function() {
  var isDark = false;
  document.querySelector('.theme-toggle').addEventListener('click', function() {
    isDark = !isDark;
    document.documentElement.setAttribute('data-theme', isDark ? 'dark' : '');
    if (!isDark) document.documentElement.removeAttribute('data-theme');
    this.textContent = isDark ? '🌙' : '☀';
  });

  // Content tabs
  var cTabs = document.querySelectorAll('.content-tab');
  var cPanels = document.querySelectorAll('[id^="panel-"]');
  cTabs.forEach(function(tab) {
    tab.addEventListener('click', function() {
      cTabs.forEach(function(t) { t.setAttribute('aria-selected', 'false'); });
      cPanels.forEach(function(p) { p.style.display = 'none'; });
      tab.setAttribute('aria-selected', 'true');
      document.getElementById(tab.getAttribute('aria-controls')).style.display = 'block';
    });
  });

  // Version selector
  var versionSelect = document.getElementById('version-select');
  var deprecationAlert = document.getElementById('deprecation-alert');
  var metaVersion = document.getElementById('meta-version');
  var metaStatus = document.getElementById('meta-status');
  versionSelect.addEventListener('change', function() {
    var v = this.value;
    metaVersion.textContent = v;
    if (v === '1.0.0') {
      deprecationAlert.style.display = 'block';
      metaStatus.innerHTML = '<span class="badge badge-deprecated">● deprecated</span>';
    } else {
      deprecationAlert.style.display = 'none';
      metaStatus.innerHTML = '<span class="badge badge-active">● active</span>';
    }
  });

  // Raw JSON toggle
  document.getElementById('raw-toggle').addEventListener('click', function() {
    cTabs.forEach(function(t) { t.setAttribute('aria-selected', 'false'); });
    cPanels.forEach(function(p) { p.style.display = 'none'; });
    document.getElementById('ctab-json').setAttribute('aria-selected', 'true');
    document.getElementById('panel-json').style.display = 'block';
  });
})();
</script>
</body>
</html>
```

**Source:** intent  
**Provenance:** intent: US-002: retrieve a specific skill by name and exact version; US-003: retrieve the latest version of a skill by name only; US-005: list all versions of a specific skill; US-009: receive structured error with similar skill name suggestions | assessment: YAML Frontmatter Schema — name, version, description, owner, status, tags

---

## Error & Edge Case Patterns

Reference page showing all error response patterns and edge cases that MCP clients must handle. Includes structured error rendering for SKILL_NOT_FOUND (with fuzzy suggestions), INVALID_VERSION format errors, UPSTREAM_UNAVAILABLE (GitHub outage with retryable flag), 401/403 authentication errors, and rate limiting responses. Each pattern shows both the JSON response and a recommended visual rendering for IDE embeddings.

### Component Hierarchy
```
ErrorPatterns
├── ThemeToggle
├── Container
│   ├── PageHeader (title + description)
│   ├── ErrorSection: SKILL_NOT_FOUND
│   │   ├── Description
│   │   └── TwoColumnLayout
│   │       ├── JSONResponse (code block)
│   │       └── RenderPreview
│   │           ├── ErrorAlert
│   │           └── SuggestionList (clickable items)
│   ├── ErrorSection: INVALID_VERSION
│   │   ├── Description
│   │   └── TwoColumnLayout
│   ├── ErrorSection: UPSTREAM_UNAVAILABLE
│   │   ├── Description
│   │   └── TwoColumnLayout
│   │       └── RenderPreview (with RetryButton)
│   ├── ErrorSection: 401 Unauthorized
│   │   ├── Description
│   │   └── TwoColumnLayout
│   │       └── RenderPreview (with auth link)
│   ├── ErrorSection: 403 Forbidden
│   │   └── TwoColumnLayout
│   └── ErrorSection: Deprecation Warning
│       └── TwoColumnLayout
```

### HTML Preview
```html
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>IT-Standard MCP — Error Patterns</title>
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&family=JetBrains+Mono:wght@400;500&display=swap" rel="stylesheet">
<style>
:root {
  --color-primary: #0068B5; --color-primary-hover: #005494; --color-primary-light: #E8F2FB;
  --color-secondary: #00C7B7; --color-accent: #7C3AED;
  --color-bg: #FFFFFF; --color-surface: #F8FAFC; --color-surface-raised: #FFFFFF;
  --color-text: #0F172A; --color-text-secondary: #475569; --color-text-muted: #94A3B8;
  --color-success: #059669; --color-success-bg: #ECFDF5;
  --color-warning: #D97706; --color-warning-bg: #FFFBEB;
  --color-error: #DC2626; --color-error-bg: #FEF2F2;
  --color-info: #0284C7; --color-info-bg: #F0F9FF;
  --color-border: #E2E8F0; --color-border-strong: #CBD5E1;
  --color-code-bg: #F1F5F9;
  --color-badge-active: #059669; --color-badge-active-bg: #ECFDF5;
  --color-badge-deprecated: #D97706; --color-badge-deprecated-bg: #FFFBEB;
  --font-sans: 'Inter', -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif;
  --font-mono: 'JetBrains Mono', 'Fira Code', 'Consolas', monospace;
  --text-xs: 0.75rem; --text-sm: 0.875rem; --text-base: 1rem; --text-lg: 1.125rem; --text-xl: 1.25rem; --text-2xl: 1.5rem;
  --weight-regular: 400; --weight-medium: 500; --weight-semibold: 600; --weight-bold: 700;
  --leading-normal: 1.5;
  --space-1: 4px; --space-2: 8px; --space-3: 12px; --space-4: 16px; --space-6: 24px; --space-8: 32px;
  --shadow-sm: 0 1px 2px 0 rgba(0,0,0,0.05); --shadow-md: 0 4px 6px -1px rgba(0,0,0,0.1), 0 2px 4px -2px rgba(0,0,0,0.1);
  --radius-sm: 4px; --radius-md: 8px; --radius-lg: 12px; --radius-full: 9999px;
  --transition-fast: 150ms ease;
}
[data-theme="dark"] {
  --color-primary: #60A5FA; --color-primary-hover: #93C5FD; --color-primary-light: #1E3A5F;
  --color-secondary: #34D399; --color-accent: #A78BFA;
  --color-bg: #0F172A; --color-surface: #1E293B; --color-surface-raised: #334155;
  --color-text: #F1F5F9; --color-text-secondary: #CBD5E1; --color-text-muted: #64748B;
  --color-success: #34D399; --color-success-bg: #064E3B;
  --color-warning: #FBBF24; --color-warning-bg: #78350F;
  --color-error: #F87171; --color-error-bg: #7F1D1D;
  --color-info: #38BDF8; --color-info-bg: #0C4A6E;
  --color-border: #334155; --color-border-strong: #475569;
  --color-code-bg: #1E293B;
  --color-badge-active: #34D399; --color-badge-active-bg: #064E3B;
  --color-badge-deprecated: #FBBF24; --color-badge-deprecated-bg: #78350F;
  --shadow-sm: 0 1px 2px 0 rgba(0,0,0,0.3); --shadow-md: 0 4px 6px -1px rgba(0,0,0,0.4), 0 2px 4px -2px rgba(0,0,0,0.3);
}
* { margin:0; padding:0; box-sizing:border-box; }
body { font-family:var(--font-sans); background:var(--color-bg); color:var(--color-text); line-height:var(--leading-normal); }
.theme-toggle { position:fixed; top:12px; right:12px; z-index:9999; background:var(--color-surface-raised); border:1px solid var(--color-border); border-radius:var(--radius-full); width:40px; height:40px; cursor:pointer; display:flex; align-items:center; justify-content:center; font-size:18px; box-shadow:var(--shadow-sm); }
.container { max-width:900px; margin:0 auto; padding:var(--space-8); }
.page-title { font-size:var(--text-2xl); font-weight:var(--weight-bold); margin-bottom:var(--space-2); }
.page-desc { color:var(--color-text-secondary); font-size:var(--text-sm); margin-bottom:var(--space-8); }
.error-section { margin-bottom:var(--space-8); }
.error-section h2 { font-size:var(--text-lg); font-weight:var(--weight-semibold); margin-bottom:var(--space-4); display:flex; align-items:center; gap:var(--space-2); }
.error-code { font-family:var(--font-mono); font-size:var(--text-xs); padding:2px var(--space-2); background:var(--color-error-bg); color:var(--color-error); border-radius:var(--radius-sm); }
.http-code { font-family:var(--font-mono); font-size:var(--text-xs); padding:2px var(--space-2); background:var(--color-warning-bg); color:var(--color-warning); border-radius:var(--radius-sm); }
.two-col { display:grid; grid-template-columns:1fr 1fr; gap:var(--space-4); }
.col-label { font-size:var(--text-xs); font-weight:var(--weight-semibold); text-transform:uppercase; letter-spacing:0.05em; color:var(--color-text-muted); margin-bottom:var(--space-2); }
.code-block { background:var(--color-code-bg); border:1px solid var(--color-border); border-radius:var(--radius-md); padding:var(--space-4); font-family:var(--font-mono); font-size:var(--text-xs); overflow-x:auto; line-height:1.6; white-space:pre; }
.render-preview { background:var(--color-surface-raised); border:1px solid var(--color-border); border-radius:var(--radius-md); padding:var(--space-4); }
.alert { padding:var(--space-3) var(--space-4); border-radius:var(--radius-md); font-size:var(--text-sm); display:flex; gap:var(--space-3); align-items:flex-start; margin-bottom:var(--space-3); }
.alert-error { background:var(--color-error-bg); color:var(--color-error); border:1px solid var(--color-error); }
.alert-warning { background:var(--color-warning-bg); color:var(--color-warning); border:1px solid var(--color-warning); }
.alert-info { background:var(--color-info-bg); color:var(--color-info); border:1px solid var(--color-info); }
.suggestion-list { list-style:none; padding:0; margin-top:var(--space-2); }
.suggestion-list li { font-family:var(--font-mono); font-size:var(--text-sm); padding:var(--space-2) var(--space-3); background:var(--color-surface); border:1px solid var(--color-border); border-radius:var(--radius-md); margin-bottom:var(--space-2); cursor:pointer; transition:all var(--transition-fast); display:flex; align-items:center; gap:var(--space-2); }
.suggestion-list li:hover { border-color:var(--color-primary); background:var(--color-primary-light); }
.retry-btn { display:inline-flex; align-items:center; gap:var(--space-2); padding:var(--space-2) var(--space-4); background:var(--color-info); color:#FFF; border:none; border-radius:var(--radius-md); font-size:var(--text-sm); font-weight:var(--weight-medium); cursor:pointer; margin-top:var(--space-3); font-family:var(--font-sans); }
.retry-btn:hover { opacity:0.9; }
.auth-link { color:var(--color-primary); text-decoration:none; font-weight:var(--weight-medium); }
.auth-link:hover { text-decoration:underline; }
.divider { border:none; border-top:1px solid var(--color-border); margin:var(--space-8) 0; }
@media (max-width: 768px) {
  .two-col { grid-template-columns:1fr; }
}
</style>
</head>
<body>
<button class="theme-toggle" aria-label="Toggle theme">☀</button>
<div class="container">
  <h1 class="page-title">⚠ Error & Edge Case Patterns</h1>
  <p class="page-desc">Reference for all structured error responses returned by IT-Standard MCP tools. Each pattern shows the JSON-RPC response and a recommended rendering for IDE/agent embeddings.</p>

  <div class="error-section">
    <h2>Skill Not Found <span class="error-code">SKILL_NOT_FOUND</span></h2>
    <p style="font-size:var(--text-sm);color:var(--color-text-secondary);margin-bottom:var(--space-4)">Returned when get_skill, get_latest_skill, or list_versions receives a skill name that does not exist in the catalog. Includes up to 5 similar skill name suggestions.</p>
    <div class="two-col">
      <div><div class="col-label">JSON Response</div><div class="code-block">{
  "jsonrpc": "2.0",
  "result": {
    "isError": true,
    "content": [{
      "type": "text",
      "text": "SKILL_NOT_FOUND: No skill found with name 'SDCL'"
    }],
    "error": {
      "code": "SKILL_NOT_FOUND",
      "suggestions": [
        "SDLC",
        "SDL-Process",
        "SDLC-Lite"
      ]
    }
  },
  "id": 1
}</div></div>
      <div><div class="col-label">Recommended Rendering</div><div class="render-preview">
        <div class="alert alert-error"><span>✕</span><div><strong>Skill not found:</strong> No skill with name "SDCL" exists in the catalog.</div></div>
        <p style="font-size:var(--text-sm);color:var(--color-text-secondary);margin-bottom:var(--space-2)">Did you mean:</p>
        <ul class="suggestion-list">
          <li>→ SDLC</li>
          <li>→ SDL-Process</li>
          <li>→ SDLC-Lite</li>
        </ul>
      </div></div>
    </div>
  </div>

  <hr class="divider">

  <div class="error-section">
    <h2>Invalid Version Format <span class="error-code">INVALID_VERSION</span></h2>
    <p style="font-size:var(--text-sm);color:var(--color-text-secondary);margin-bottom:var(--space-4)">Returned when the version parameter does not match the strict MAJOR.MINOR.PATCH format (e.g., "v1", "2.00", "1.0").</p>
    <div class="two-col">
      <div><div class="col-label">JSON Response</div><div class="code-block">{
  "jsonrpc": "2.0",
  "result": {
    "isError": true,
    "content": [{
      "type": "text",
      "text": "INVALID_VERSION: 'v1' is not a valid version. Use MAJOR.MINOR.PATCH format (e.g., 2.0.0)"
    }],
    "error": {
      "code": "INVALID_VERSION",
      "provided": "v1",
      "expectedFormat": "MAJOR.MINOR.PATCH"
    }
  },
  "id": 2
}</div></div>
      <div><div class="col-label">Recommended Rendering</div><div class="render-preview">
        <div class="alert alert-error"><span>✕</span><div><strong>Invalid version format:</strong> "v1" is not valid.<br><span style="font-size:var(--text-xs)">Expected format: MAJOR.MINOR.PATCH (e.g., 2.0.0, 1.10.0)</span></div></div>
      </div></div>
    </div>
  </div>

  <hr class="divider">

  <div class="error-section">
    <h2>Upstream Unavailable <span class="error-code">UPSTREAM_UNAVAILABLE</span></h2>
    <p style="font-size:var(--text-sm);color:var(--color-text-secondary);margin-bottom:var(--space-4)">Returned when GitHub is unreachable and the requested content has never been cached. Includes isRetryable flag. Previously cached content is served normally during outages.</p>
    <div class="two-col">
      <div><div class="col-label">JSON Response</div><div class="code-block">{
  "jsonrpc": "2.0",
  "result": {
    "isError": true,
    "content": [{
      "type": "text",
      "text": "UPSTREAM_UNAVAILABLE: GitHub is temporarily unreachable. This content has not been cached yet."
    }],
    "error": {
      "code": "UPSTREAM_UNAVAILABLE",
      "isRetryable": true,
      "retryAfterSeconds": 30
    }
  },
  "id": 3
}</div></div>
      <div><div class="col-label">Recommended Rendering</div><div class="render-preview">
        <div class="alert alert-warning"><span>⚠</span><div><strong>Service temporarily unavailable:</strong> The upstream content source (GitHub) is unreachable. This content has not been cached yet.<br><span style="font-size:var(--text-xs)">This is a temporary issue. The request can be retried.</span></div></div>
        <button class="retry-btn" id="retry-btn">🔄 Retry in 30s</button>
      </div></div>
    </div>
  </div>

  <hr class="divider">

  <div class="error-section">
    <h2>Authentication Error <span class="http-code">401 Unauthorized</span></h2>
    <p style="font-size:var(--text-sm);color:var(--color-text-secondary);margin-bottom:var(--space-4)">Returned by Apigee X when the Bearer token is missing, expired, or invalid. Includes WWW-Authenticate header pointing to the Entra ID authorization server.</p>
    <div class="two-col">
      <div><div class="col-label">HTTP Response</div><div class="code-block">HTTP/1.1 401 Unauthorized
WWW-Authenticate: Bearer
  resource_metadata="https://apigee.intel.com/.well-known/oauth-protected-resource"
  error="invalid_token"
  error_description="The access token has expired"
Content-Type: application/json

{
  "error": "invalid_token",
  "error_description": "The access token has expired"
}</div></div>
      <div><div class="col-label">Recommended Rendering</div><div class="render-preview">
        <div class="alert alert-error"><span>🔒</span><div><strong>Authentication required:</strong> Your access token has expired. Please re-authenticate with your Intel credentials.<br><br><a href="#" class="auth-link">→ Re-authenticate via Microsoft Entra ID</a><br><span style="font-size:var(--text-xs);color:var(--color-text-muted)">Scope: api://it-standard-mcp/skills.read</span></div></div>
      </div></div>
    </div>
  </div>

  <hr class="divider">

  <div class="error-section">
    <h2>Insufficient Scope <span class="http-code">403 Forbidden</span></h2>
    <p style="font-size:var(--text-sm);color:var(--color-text-secondary);margin-bottom:var(--space-4)">Returned when the token is valid but lacks the required skills.read scope.</p>
    <div class="two-col">
      <div><div class="col-label">HTTP Response</div><div class="code-block">HTTP/1.1 403 Forbidden
Content-Type: application/json

{
  "error": "insufficient_scope",
  "required_scope": "api://it-standard-mcp/skills.read"
}</div></div>
      <div><div class="col-label">Recommended Rendering</div><div class="render-preview">
        <div class="alert alert-error"><span>🚫</span><div><strong>Access denied:</strong> Your application does not have the required permission.<br><span style="font-size:var(--text-xs)">Required scope: <code style="font-family:var(--font-mono);background:var(--color-code-bg);padding:1px 4px;border-radius:2px">api://it-standard-mcp/skills.read</code></span><br><span style="font-size:var(--text-xs);color:var(--color-text-muted)">Contact your app registration administrator to add this scope.</span></div></div>
      </div></div>
    </div>
  </div>

  <hr class="divider">

  <div class="error-section">
    <h2>Deprecation Warning <span style="font-family:var(--font-mono);font-size:var(--text-xs);padding:2px var(--space-2);background:var(--color-warning-bg);color:var(--color-warning);border-radius:var(--radius-sm)">WARNING</span></h2>
    <p style="font-size:var(--text-sm);color:var(--color-text-secondary);margin-bottom:var(--space-4)">Not an error — included as a warning field in successful get_skill / get_latest_skill responses when the retrieved version has status "deprecated".</p>
    <div class="two-col">
      <div><div class="col-label">Response Excerpt</div><div class="code-block">{
  "metadata": {
    "name": "SDLC",
    "version": "1.0.0",
    "status": "deprecated",
    "warning": "SDLC 1.0.0 is deprecated; latest is 2.0.0"
  }
}</div></div>
      <div><div class="col-label">Recommended Rendering</div><div class="render-preview">
        <div class="alert alert-warning"><span>⚠</span><div><strong>Deprecated version:</strong> SDLC 1.0.0 is deprecated. The latest version is <strong>2.0.0</strong>.<br><span style="font-size:var(--text-xs)">Consider upgrading to the latest version for the most current standards.</span></div></div>
      </div></div>
    </div>
  </div>
</div>

<script>
(function() {
  var isDark = false;
  document.querySelector('.theme-toggle').addEventListener('click', function() {
    isDark = !isDark;
    document.documentElement.setAttribute('data-theme', isDark ? 'dark' : '');
    if (!isDark) document.documentElement.removeAttribute('data-theme');
    this.textContent = isDark ? '🌙' : '☀';
  });

  // Retry button simulation
  var retryBtn = document.getElementById('retry-btn');
  if (retryBtn) {
    retryBtn.addEventListener('click', function() {
      this.textContent = '⏳ Retrying...';
      this.disabled = true;
      var self = this;
      setTimeout(function() {
        self.textContent = '✓ Retry complete (simulated)';
        setTimeout(function() { self.textContent = '🔄 Retry in 30s'; self.disabled = false; }, 2000);
      }, 1500);
    });
  }

  // Suggestion clicks
  document.querySelectorAll('.suggestion-list li').forEach(function(item) {
    item.addEventListener('click', function() {
      var name = this.textContent.replace('→ ', '').trim();
      this.style.background = 'var(--color-success-bg)';
      this.style.borderColor = 'var(--color-success)';
      this.textContent = '✓ Loading ' + name + '...';
    });
  });
})();
</script>
</body>
</html>
```

**Source:** intent  
**Provenance:** intent: US-009: receive structured error when requesting non-existent skill; US-010: continue retrieving skills when GitHub is temporarily unavailable; US-011: access skills through AI agent without additional registration (401/403 handling); Authentication & Authorization Flow — Error Handling table | policy: API Design Conventions — structured error responses with actionable messages; A10 – Mishandling of Exceptional Conditions — never fail open, never leak stack traces

---

## Operations & Health Dashboard

DevOps-focused dashboard for Platform Engineers monitoring the MCP server health, cache status, GitHub polling state, and key operational metrics. Includes /healthz and /readyz status indicators, Redis cache statistics, GitHub API rate limit tracking, polling leader election status, and recent audit log entries. This page simulates the operational observability that would be rendered in a monitoring tool or internal status page.

### Component Hierarchy
```
OperationsDashboard
├── ThemeToggle
├── Container
│   ├── PageHeader
│   │   ├── Title
│   │   └── EnvironmentTags (prod/dev)
│   ├── HealthRow (4-column grid)
│   │   ├── HealthCard: /healthz Liveness
│   │   ├── HealthCard: /readyz Readiness
│   │   ├── HealthCard: Uptime %
│   │   └── HealthCard: p95 Latency
│   ├── SectionGrid (2-column)
│   │   ├── CacheStatus
│   │   │   ├── MemoryUsage (progress bar)
│   │   │   ├── HitRate
│   │   │   ├── TotalKeys
│   │   │   └── IndexRefresh
│   │   ├── GitHubAPIStatus
│   │   │   ├── ConnectionStatus
│   │   │   ├── RateLimit (progress bar)
│   │   │   ├── HeadSHA
│   │   │   └── LastPoll
│   │   ├── Replicas
│   │   │   └── ReplicaCard[] (status, CPU, memory, role)
│   │   └── RequestMetrics
│   │       ├── TotalRequests
│   │       ├── UniqueClients
│   │       ├── SuccessRate
│   │       └── ErrorCounts
│   └── AuditLogTable
│       └── LogRow[] (timestamp, tool, skill, version, cache, latency, client)
```

### HTML Preview
```html
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>IT-Standard MCP — Operations Dashboard</title>
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&family=JetBrains+Mono:wght@400;500&display=swap" rel="stylesheet">
<style>
:root {
  --color-primary: #0068B5; --color-primary-hover: #005494; --color-primary-light: #E8F2FB;
  --color-secondary: #00C7B7; --color-accent: #7C3AED;
  --color-bg: #FFFFFF; --color-surface: #F8FAFC; --color-surface-raised: #FFFFFF;
  --color-text: #0F172A; --color-text-secondary: #475569; --color-text-muted: #94A3B8;
  --color-success: #059669; --color-success-bg: #ECFDF5;
  --color-warning: #D97706; --color-warning-bg: #FFFBEB;
  --color-error: #DC2626; --color-error-bg: #FEF2F2;
  --color-info: #0284C7; --color-info-bg: #F0F9FF;
  --color-border: #E2E8F0; --color-border-strong: #CBD5E1;
  --color-code-bg: #F1F5F9;
  --color-badge-active: #059669; --color-badge-active-bg: #ECFDF5;
  --color-badge-deprecated: #D97706; --color-badge-deprecated-bg: #FFFBEB;
  --font-sans: 'Inter', -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif;
  --font-mono: 'JetBrains Mono', 'Fira Code', 'Consolas', monospace;
  --text-xs: 0.75rem; --text-sm: 0.875rem; --text-base: 1rem; --text-lg: 1.125rem; --text-xl: 1.25rem; --text-2xl: 1.5rem;
  --weight-regular: 400; --weight-medium: 500; --weight-semibold: 600; --weight-bold: 700;
  --leading-normal: 1.5;
  --space-1: 4px; --space-2: 8px; --space-3: 12px; --space-4: 16px; --space-6: 24px; --space-8: 32px;
  --shadow-sm: 0 1px 2px 0 rgba(0,0,0,0.05); --shadow-md: 0 4px 6px -1px rgba(0,0,0,0.1), 0 2px 4px -2px rgba(0,0,0,0.1);
  --radius-sm: 4px; --radius-md: 8px; --radius-lg: 12px; --radius-full: 9999px;
  --transition-fast: 150ms ease;
}
[data-theme="dark"] {
  --color-primary: #60A5FA; --color-primary-hover: #93C5FD; --color-primary-light: #1E3A5F;
  --color-secondary: #34D399; --color-accent: #A78BFA;
  --color-bg: #0F172A; --color-surface: #1E293B; --color-surface-raised: #334155;
  --color-text: #F1F5F9; --color-text-secondary: #CBD5E1; --color-text-muted: #64748B;
  --color-success: #34D399; --color-success-bg: #064E3B;
  --color-warning: #FBBF24; --color-warning-bg: #78350F;
  --color-error: #F87171; --color-error-bg: #7F1D1D;
  --color-info: #38BDF8; --color-info-bg: #0C4A6E;
  --color-border: #334155; --color-border-strong: #475569;
  --color-code-bg: #1E293B;
  --color-badge-active: #34D399; --color-badge-active-bg: #064E3B;
  --color-badge-deprecated: #FBBF24; --color-badge-deprecated-bg: #78350F;
  --shadow-sm: 0 1px 2px 0 rgba(0,0,0,0.3); --shadow-md: 0 4px 6px -1px rgba(0,0,0,0.4), 0 2px 4px -2px rgba(0,0,0,0.3);
}
* { margin:0; padding:0; box-sizing:border-box; }
body { font-family:var(--font-sans); background:var(--color-bg); color:var(--color-text); line-height:var(--leading-normal); }
.theme-toggle { position:fixed; top:12px; right:12px; z-index:9999; background:var(--color-surface-raised); border:1px solid var(--color-border); border-radius:var(--radius-full); width:40px; height:40px; cursor:pointer; display:flex; align-items:center; justify-content:center; font-size:18px; box-shadow:var(--shadow-sm); }
.container { max-width:1200px; margin:0 auto; padding:var(--space-8); }
.page-header { display:flex; justify-content:space-between; align-items:center; margin-bottom:var(--space-6); flex-wrap:wrap; gap:var(--space-4); }
.page-header h1 { font-size:var(--text-2xl); font-weight:var(--weight-bold); }
.env-tags { display:flex; gap:var(--space-2); }
.env-tag { padding:var(--space-1) var(--space-3); border-radius:var(--radius-full); font-size:var(--text-xs); font-weight:var(--weight-semibold); cursor:pointer; border:1px solid var(--color-border); background:var(--color-surface-raised); color:var(--color-text-secondary); transition:all var(--transition-fast); }
.env-tag.active { background:var(--color-success-bg); color:var(--color-success); border-color:var(--color-success); }
.health-row { display:grid; grid-template-columns:repeat(4,1fr); gap:var(--space-4); margin-bottom:var(--space-6); }
.health-card { background:var(--color-surface-raised); border:1px solid var(--color-border); border-radius:var(--radius-lg); padding:var(--space-4) var(--space-5); box-shadow:var(--shadow-sm); }
.health-card .label { font-size:var(--text-xs); color:var(--color-text-muted); text-transform:uppercase; letter-spacing:0.05em; margin-bottom:var(--space-2); }
.health-card .value { font-size:var(--text-xl); font-weight:var(--weight-bold); display:flex; align-items:center; gap:var(--space-2); }
.health-card .sub { font-size:var(--text-xs); color:var(--color-text-muted); margin-top:var(--space-1); }
.status-dot { width:10px; height:10px; border-radius:50%; display:inline-block; }
.dot-green { background:var(--color-success); box-shadow:0 0 6px var(--color-success); }
.dot-yellow { background:var(--color-warning); box-shadow:0 0 6px var(--color-warning); }
.dot-red { background:var(--color-error); box-shadow:0 0 6px var(--color-error); }
.section-grid { display:grid; grid-template-columns:1fr 1fr; gap:var(--space-6); margin-bottom:var(--space-6); }
.section-card { background:var(--color-surface-raised); border:1px solid var(--color-border); border-radius:var(--radius-lg); padding:var(--space-5); box-shadow:var(--shadow-sm); }
.section-title { font-size:var(--text-base); font-weight:var(--weight-semibold); margin-bottom:var(--space-4); display:flex; align-items:center; gap:var(--space-2); }
.metric-row { display:flex; justify-content:space-between; align-items:center; padding:var(--space-2) 0; border-bottom:1px solid var(--color-border); font-size:var(--text-sm); }
.metric-row:last-child { border-bottom:none; }
.metric-label { color:var(--color-text-secondary); }
.metric-value { font-family:var(--font-mono); font-weight:var(--weight-medium); }
.progress-bar { height:8px; background:var(--color-surface); border-radius:var(--radius-full); overflow:hidden; margin-top:var(--space-2); }
.progress-fill { height:100%; border-radius:var(--radius-full); transition:width 0.5s ease; }
.log-table { width:100%; border-collapse:collapse; font-size:var(--text-xs); }
.log-table th { text-align:left; padding:var(--space-2) var(--space-3); background:var(--color-surface); font-weight:var(--weight-semibold); border-bottom:2px solid var(--color-border); white-space:nowrap; }
.log-table td { padding:var(--space-2) var(--space-3); border-bottom:1px solid var(--color-border); font-family:var(--font-mono); }
.log-table tr:hover { background:var(--color-primary-light); }
.badge-sm { display:inline-flex; padding:1px var(--space-2); border-radius:var(--radius-full); font-size:0.65rem; font-weight:var(--weight-medium); }
.badge-hit { background:var(--color-success-bg); color:var(--color-success); }
.badge-miss { background:var(--color-info-bg); color:var(--color-info); }
.replica-grid { display:flex; gap:var(--space-3); flex-wrap:wrap; }
.replica-card { background:var(--color-surface); border:1px solid var(--color-border); border-radius:var(--radius-md); padding:var(--space-3); font-size:var(--text-xs); min-width:160px; }
.replica-card .name { font-weight:var(--weight-semibold); margin-bottom:var(--space-1); display:flex; align-items:center; gap:var(--space-2); }
.replica-card .info { color:var(--color-text-muted); }
@media (max-width: 768px) {
  .health-row { grid-template-columns:repeat(2,1fr); }
  .section-grid { grid-template-columns:1fr; }
}
</style>
</head>
<body>
<button class="theme-toggle" aria-label="Toggle theme">☀</button>
<div class="container">
  <div class="page-header">
    <h1>⚙ Operations Dashboard</h1>
    <div class="env-tags">
      <span class="env-tag active" data-env="prod">Production</span>
      <span class="env-tag" data-env="dev">Development</span>
    </div>
  </div>

  <div class="health-row">
    <div class="health-card">
      <div class="label">/healthz — Liveness</div>
      <div class="value"><span class="status-dot dot-green"></span> Healthy</div>
      <div class="sub">All 3 replicas responding</div>
    </div>
    <div class="health-card">
      <div class="label">/readyz — Readiness</div>
      <div class="value"><span class="status-dot dot-green"></span> Ready</div>
      <div class="sub">Index loaded · 52 skills indexed</div>
    </div>
    <div class="health-card">
      <div class="label">Uptime (30 days)</div>
      <div class="value" style="color:var(--color-success)">99.72%</div>
      <div class="sub">Target: 99.5% · 1 incident</div>
    </div>
    <div class="health-card">
      <div class="label">p95 Latency (cache hit)</div>
      <div class="value" style="color:var(--color-primary)">14ms</div>
      <div class="sub">Target: ≤ 200ms · p99: 42ms</div>
    </div>
  </div>

  <div class="section-grid">
    <div class="section-card">
      <div class="section-title">📦 Redis Cache Status</div>
      <div class="metric-row"><span class="metric-label">Memory Used</span><span class="metric-value">87 MB / 512 MB</span></div>
      <div class="progress-bar"><div class="progress-fill" style="width:17%;background:var(--color-success)"></div></div>
      <div class="metric-row" style="margin-top:var(--space-3)"><span class="metric-label">Cache Hit Rate</span><span class="metric-value" style="color:var(--color-success)">94.2%</span></div>
      <div class="metric-row"><span class="metric-label">Total Keys</span><span class="metric-value">1,247</span></div>
      <div class="metric-row"><span class="metric-label">Index Key</span><span class="metric-value" style="font-size:var(--text-xs)">index:main:a1b2c3d</span></div>
      <div class="metric-row"><span class="metric-label">Index Refresh</span><span class="metric-value">12s ago</span></div>
    </div>

    <div class="section-card">
      <div class="section-title">🐙 GitHub API Status</div>
      <div class="metric-row"><span class="metric-label">Status</span><span class="metric-value" style="color:var(--color-success)"><span class="status-dot dot-green" style="margin-right:4px"></span>Connected</span></div>
      <div class="metric-row"><span class="metric-label">Rate Limit</span><span class="metric-value">4,847 / 5,000</span></div>
      <div class="progress-bar"><div class="progress-fill" style="width:3%;background:var(--color-success)"></div></div>
      <div class="metric-row" style="margin-top:var(--space-3)"><span class="metric-label">Rate Limit Reset</span><span class="metric-value">42 min</span></div>
      <div class="metric-row"><span class="metric-label">HEAD SHA (main)</span><span class="metric-value" style="font-size:var(--text-xs)">a1b2c3d4e5f6</span></div>
      <div class="metric-row"><span class="metric-label">Last Successful Poll</span><span class="metric-value">12s ago (304)</span></div>
    </div>

    <div class="section-card">
      <div class="section-title">🖥 Replicas</div>
      <div class="replica-grid">
        <div class="replica-card">
          <div class="name"><span class="status-dot dot-green"></span> mcp-prod-1</div>
          <div class="info">CPU: 32% · Mem: 180MB</div>
          <div class="info" style="color:var(--color-primary);margin-top:2px">★ Poll Leader</div>
        </div>
        <div class="replica-card">
          <div class="name"><span class="status-dot dot-green"></span> mcp-prod-2</div>
          <div class="info">CPU: 28% · Mem: 165MB</div>
          <div class="info" style="margin-top:2px">Follower</div>
        </div>
        <div class="replica-card">
          <div class="name"><span class="status-dot dot-green"></span> mcp-prod-3</div>
          <div class="info">CPU: 25% · Mem: 170MB</div>
          <div class="info" style="margin-top:2px">Follower</div>
        </div>
      </div>
    </div>

    <div class="section-card">
      <div class="section-title">📊 Request Metrics (24h)</div>
      <div class="metric-row"><span class="metric-label">Total Requests</span><span class="metric-value">42,180</span></div>
      <div class="metric-row"><span class="metric-label">Unique Clients</span><span class="metric-value">23</span></div>
      <div class="metric-row"><span class="metric-label">Success Rate</span><span class="metric-value" style="color:var(--color-success)">99.4%</span></div>
      <div class="metric-row"><span class="metric-label">Errors (4xx)</span><span class="metric-value" style="color:var(--color-warning)">186</span></div>
      <div class="metric-row"><span class="metric-label">Errors (5xx)</span><span class="metric-value" style="color:var(--color-error)">12</span></div>
      <div class="metric-row"><span class="metric-label">Top Tool</span><span class="metric-value">get_latest_skill (48%)</span></div>
    </div>
  </div>

  <div class="section-card" style="margin-bottom:var(--space-6)">
    <div class="section-title">📝 Recent Audit Log Entries</div>
    <div style="overflow-x:auto">
      <table class="log-table">
        <thead><tr><th>Timestamp</th><th>Tool</th><th>Skill</th><th>Version</th><th>Cache</th><th>Latency</th><th>Client ID</th></tr></thead>
        <tbody>
          <tr><td>2026-11-17 14:23:01</td><td>get_latest_skill</td><td>SDLC</td><td>2.0.0</td><td><span class="badge-sm badge-hit">HIT</span></td><td>8ms</td><td>agent-copilot-prod</td></tr>
          <tr><td>2026-11-17 14:22:58</td><td>list_skills</td><td>—</td><td>—</td><td><span class="badge-sm badge-hit">HIT</span></td><td>12ms</td><td>ide-plugin-vscode</td></tr>
          <tr><td>2026-11-17 14:22:45</td><td>search_skills</td><td>query:security</td><td>—</td><td><span class="badge-sm badge-hit">HIT</span></td><td>15ms</td><td>agent-security-scanner</td></tr>
          <tr><td>2026-11-17 14:22:30</td><td>get_skill</td><td>Code-Review</td><td>1.2.0</td><td><span class="badge-sm badge-miss">MISS</span></td><td>1,240ms</td><td>agent-code-assist</td></tr>
          <tr><td>2026-11-17 14:22:15</td><td>list_versions</td><td>Security-Baseline</td><td>—</td><td><span class="badge-sm badge-hit">HIT</span></td><td>9ms</td><td>agent-copilot-prod</td></tr>
          <tr><td>2026-11-17 14:22:01</td><td>get_skill</td><td>SDLC</td><td>1.0.0</td><td><span class="badge-sm badge-hit">HIT</span></td><td>7ms</td><td>ide-plugin-jetbrains</td></tr>
        </tbody>
      </table>
    </div>
  </div>
</div>

<script>
(function() {
  var isDark = false;
  document.querySelector('.theme-toggle').addEventListener('click', function() {
    isDark = !isDark;
    document.documentElement.setAttribute('data-theme', isDark ? 'dark' : '');
    if (!isDark) document.documentElement.removeAttribute('data-theme');
    this.textContent = isDark ? '🌙' : '☀';
  });

  // Environment tags
  document.querySelectorAll('.env-tag').forEach(function(tag) {
    tag.addEventListener('click', function() {
      document.querySelectorAll('.env-tag').forEach(function(t) { t.classList.remove('active'); });
      this.classList.add('active');
    });
  });
})();
</script>
</body>
</html>
```

**Source:** mixed  
**Provenance:** intent: US-008: monitor MCP server health and receive alerts on failures; Business Objective: Maintain enterprise-grade reliability — 99.5% uptime, p95 ≤ 200ms; Business Objective: Full observability with immutable audit trail | assessment: Architecture: /healthz and /readyz endpoints; structured JSON logs; polling leader election; Redis shared cache with structured keys; GitHub API rate limit 5,000 req/hr

---

## Authentication Flow & Integration Guide

Reference page for AI agent developers showing the OAuth 2.0 authentication flow with Microsoft Entra ID, Apigee X gateway configuration, and step-by-step integration instructions. Includes interactive sequence diagram, code snippets for token acquisition, the well-known endpoint response, and an integration checklist. This serves as the primary onboarding guide for MCP client developers.

### Component Hierarchy
```
IntegrationGuide
├── ThemeToggle
├── Container
│   ├── PageHeader (title + description)
│   ├── EndpointsSection
│   │   ├── EndpointCard: /it-standard/mcp (POST)
│   │   ├── EndpointCard: /it-standard-dev/mcp (POST)
│   │   └── EndpointCard: /.well-known/... (GET)
│   ├── AuthFlowSection
│   │   └── FlowSteps
│   │       ├── Step 1: Register app
│   │       ├── Step 2: Acquire token
│   │       ├── Step 3: Call MCP
│   │       └── Step 4: Apigee validates
│   ├── CodeExamplesSection
│   │   ├── TypeScriptExample (token acquisition)
│   │   └── MCPToolCallExample
│   ├── WellKnownSection (JSON response)
│   ├── JWTClaimsTable
│   └── IntegrationChecklist
│       └── ChecklistItem[] (clickable checkboxes)
```

### HTML Preview
```html
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>IT-Standard MCP — Integration Guide</title>
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&family=JetBrains+Mono:wght@400;500&display=swap" rel="stylesheet">
<style>
:root {
  --color-primary: #0068B5; --color-primary-hover: #005494; --color-primary-light: #E8F2FB;
  --color-secondary: #00C7B7; --color-accent: #7C3AED; --color-accent-light: #EDE9FE;
  --color-bg: #FFFFFF; --color-surface: #F8FAFC; --color-surface-raised: #FFFFFF;
  --color-text: #0F172A; --color-text-secondary: #475569; --color-text-muted: #94A3B8;
  --color-success: #059669; --color-success-bg: #ECFDF5;
  --color-warning: #D97706; --color-warning-bg: #FFFBEB;
  --color-error: #DC2626; --color-error-bg: #FEF2F2;
  --color-info: #0284C7; --color-info-bg: #F0F9FF;
  --color-border: #E2E8F0; --color-border-strong: #CBD5E1;
  --color-code-bg: #F1F5F9;
  --color-badge-active: #059669; --color-badge-active-bg: #ECFDF5;
  --font-sans: 'Inter', -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif;
  --font-mono: 'JetBrains Mono', 'Fira Code', 'Consolas', monospace;
  --text-xs: 0.75rem; --text-sm: 0.875rem; --text-base: 1rem; --text-lg: 1.125rem; --text-xl: 1.25rem; --text-2xl: 1.5rem;
  --weight-regular: 400; --weight-medium: 500; --weight-semibold: 600; --weight-bold: 700;
  --leading-normal: 1.5;
  --space-1: 4px; --space-2: 8px; --space-3: 12px; --space-4: 16px; --space-5: 20px; --space-6: 24px; --space-8: 32px;
  --shadow-sm: 0 1px 2px 0 rgba(0,0,0,0.05); --shadow-md: 0 4px 6px -1px rgba(0,0,0,0.1), 0 2px 4px -2px rgba(0,0,0,0.1);
  --radius-sm: 4px; --radius-md: 8px; --radius-lg: 12px; --radius-full: 9999px;
  --transition-fast: 150ms ease;
}
[data-theme="dark"] {
  --color-primary: #60A5FA; --color-primary-hover: #93C5FD; --color-primary-light: #1E3A5F;
  --color-secondary: #34D399; --color-accent: #A78BFA; --color-accent-light: #2E1065;
  --color-bg: #0F172A; --color-surface: #1E293B; --color-surface-raised: #334155;
  --color-text: #F1F5F9; --color-text-secondary: #CBD5E1; --color-text-muted: #64748B;
  --color-success: #34D399; --color-success-bg: #064E3B;
  --color-warning: #FBBF24; --color-warning-bg: #78350F;
  --color-error: #F87171; --color-error-bg: #7F1D1D;
  --color-info: #38BDF8; --color-info-bg: #0C4A6E;
  --color-border: #334155; --color-border-strong: #475569;
  --color-code-bg: #1E293B;
  --color-badge-active: #34D399; --color-badge-active-bg: #064E3B;
  --shadow-sm: 0 1px 2px 0 rgba(0,0,0,0.3); --shadow-md: 0 4px 6px -1px rgba(0,0,0,0.4), 0 2px 4px -2px rgba(0,0,0,0.3);
}
* { margin:0; padding:0; box-sizing:border-box; }
body { font-family:var(--font-sans); background:var(--color-bg); color:var(--color-text); line-height:var(--leading-normal); }
.theme-toggle { position:fixed; top:12px; right:12px; z-index:9999; background:var(--color-surface-raised); border:1px solid var(--color-border); border-radius:var(--radius-full); width:40px; height:40px; cursor:pointer; display:flex; align-items:center; justify-content:center; font-size:18px; box-shadow:var(--shadow-sm); }
.container { max-width:900px; margin:0 auto; padding:var(--space-8); }
.page-title { font-size:var(--text-2xl); font-weight:var(--weight-bold); margin-bottom:var(--space-2); }
.page-desc { color:var(--color-text-secondary); font-size:var(--text-sm); margin-bottom:var(--space-8); }
.section { margin-bottom:var(--space-8); }
.section h2 { font-size:var(--text-xl); font-weight:var(--weight-bold); margin-bottom:var(--space-4); padding-bottom:var(--space-2); border-bottom:1px solid var(--color-border); }
.section h3 { font-size:var(--text-base); font-weight:var(--weight-semibold); margin:var(--space-4) 0 var(--space-3); }
.section p { font-size:var(--text-sm); color:var(--color-text-secondary); margin-bottom:var(--space-3); }
.code-block { background:var(--color-code-bg); border:1px solid var(--color-border); border-radius:var(--radius-md); padding:var(--space-4); font-family:var(--font-mono); font-size:var(--text-xs); overflow-x:auto; line-height:1.6; white-space:pre; margin-bottom:var(--space-4); }
.flow-steps { display:flex; flex-direction:column; gap:var(--space-4); }
.flow-step { display:flex; gap:var(--space-4); align-items:flex-start; }
.step-number { width:32px; height:32px; border-radius:50%; background:var(--color-primary); color:#FFF; display:flex; align-items:center; justify-content:center; font-weight:var(--weight-bold); font-size:var(--text-sm); flex-shrink:0; }
.step-content { flex:1; }
.step-content .title { font-weight:var(--weight-semibold); margin-bottom:var(--space-1); }
.step-content .desc { font-size:var(--text-sm); color:var(--color-text-secondary); }
.config-table { width:100%; border-collapse:collapse; font-size:var(--text-sm); margin-bottom:var(--space-4); }
.config-table th { text-align:left; padding:var(--space-3) var(--space-4); background:var(--color-surface); font-weight:var(--weight-semibold); border-bottom:2px solid var(--color-border); }
.config-table td { padding:var(--space-3) var(--space-4); border-bottom:1px solid var(--color-border); }
.config-table td:first-child { font-family:var(--font-mono); font-weight:var(--weight-medium); font-size:var(--text-xs); white-space:nowrap; }
.alert { padding:var(--space-3) var(--space-4); border-radius:var(--radius-md); font-size:var(--text-sm); display:flex; gap:var(--space-3); align-items:flex-start; margin-bottom:var(--space-4); }
.alert-info { background:var(--color-info-bg); color:var(--color-info); border:1px solid var(--color-info); }
.alert-success { background:var(--color-success-bg); color:var(--color-success); border:1px solid var(--color-success); }
.checklist { list-style:none; padding:0; }
.checklist li { display:flex; align-items:flex-start; gap:var(--space-3); padding:var(--space-3) var(--space-4); border:1px solid var(--color-border); border-radius:var(--radius-md); margin-bottom:var(--space-2); background:var(--color-surface-raised); font-size:var(--text-sm); cursor:pointer; transition:all var(--transition-fast); }
.checklist li:hover { border-color:var(--color-primary); }
.checklist li.checked { background:var(--color-success-bg); border-color:var(--color-success); }
.check-box { width:18px; height:18px; border:2px solid var(--color-border-strong); border-radius:var(--radius-sm); flex-shrink:0; display:flex; align-items:center; justify-content:center; font-size:12px; margin-top:1px; }
.checklist li.checked .check-box { background:var(--color-success); border-color:var(--color-success); color:#FFF; }
.endpoint-card { background:var(--color-surface); border:1px solid var(--color-border); border-radius:var(--radius-md); padding:var(--space-4); margin-bottom:var(--space-3); }
.endpoint-method { display:inline-flex; padding:2px var(--space-2); border-radius:var(--radius-sm); font-size:var(--text-xs); font-weight:var(--weight-bold); font-family:var(--font-mono); margin-right:var(--space-2); }
.method-post { background:#7C3AED; color:#FFF; }
.method-get { background:var(--color-success); color:#FFF; }
.endpoint-path { font-family:var(--font-mono); font-size:var(--text-sm); font-weight:var(--weight-medium); }
.endpoint-desc { font-size:var(--text-xs); color:var(--color-text-muted); margin-top:var(--space-2); }
@media (max-width: 768px) {
  .container { padding:var(--space-4); }
}
</style>
</head>
<body>
<button class="theme-toggle" aria-label="Toggle theme">☀</button>
<div class="container">
  <h1 class="page-title">🔐 Authentication & Integration Guide</h1>
  <p class="page-desc">Step-by-step guide for integrating your AI agent or IDE plugin with the IT-Standard MCP server via OAuth 2.0 and Apigee X.</p>

  <section class="section">
    <h2>Endpoints</h2>
    <div class="endpoint-card">
      <span class="endpoint-method method-post">POST</span>
      <span class="endpoint-path">/it-standard/mcp</span>
      <div class="endpoint-desc">Production MCP endpoint — serves skills from the main branch</div>
    </div>
    <div class="endpoint-card">
      <span class="endpoint-method method-post">POST</span>
      <span class="endpoint-path">/it-standard-dev/mcp</span>
      <div class="endpoint-desc">Development MCP endpoint — serves skills from the dev branch (pre-production testing)</div>
    </div>
    <div class="endpoint-card">
      <span class="endpoint-method method-get">GET</span>
      <span class="endpoint-path">/.well-known/oauth-protected-resource</span>
      <div class="endpoint-desc">OAuth 2.0 resource metadata discovery endpoint</div>
    </div>
  </section>

  <section class="section">
    <h2>Authentication Flow</h2>
    <p>The IT-Standard MCP server uses gateway-enforced OAuth 2.0 via Microsoft Entra ID. Your agent never sends credentials to the MCP server directly — all authentication is handled at the Apigee X gateway.</p>

    <div class="flow-steps">
      <div class="flow-step">
        <div class="step-number">1</div>
        <div class="step-content">
          <div class="title">Register your app with Entra ID</div>
          <div class="desc">Create an app registration in Microsoft Entra ID and request the <code style="font-family:var(--font-mono);background:var(--color-code-bg);padding:1px 4px;border-radius:2px;font-size:var(--text-xs)">api://it-standard-mcp/skills.read</code> scope.</div>
        </div>
      </div>
      <div class="flow-step">
        <div class="step-number">2</div>
        <div class="step-content">
          <div class="title">Acquire an access token</div>
          <div class="desc">Use the OAuth 2.0 client credentials flow or authorization code flow to obtain a JWT from Entra ID.</div>
        </div>
      </div>
      <div class="flow-step">
        <div class="step-number">3</div>
        <div class="step-content">
          <div class="title">Call the MCP endpoint with Bearer token</div>
          <div class="desc">Send JSON-RPC requests to the Apigee endpoint with <code style="font-family:var(--font-mono);background:var(--color-code-bg);padding:1px 4px;border-radius:2px;font-size:var(--text-xs)">Authorization: Bearer &lt;token&gt;</code> header.</div>
        </div>
      </div>
      <div class="flow-step">
        <div class="step-number">4</div>
        <div class="step-content">
          <div class="title">Apigee validates and forwards</div>
          <div class="desc">Apigee validates the JWT (signature, issuer, audience, expiry, scope), extracts X-User-Id and X-Client-Id, and forwards to the MCP server.</div>
        </div>
      </div>
    </div>
  </section>

  <section class="section">
    <h2>Token Acquisition — Code Example</h2>
    <h3>TypeScript / Node.js</h3>
    <div class="code-block">import { ConfidentialClientApplication } from "@azure/msal-node";

const msalConfig = {
  auth: {
    clientId: "YOUR_APP_CLIENT_ID",
    authority: "https://login.microsoftonline.com/YOUR_TENANT_ID",
    clientSecret: "YOUR_CLIENT_SECRET"
  }
};

const cca = new ConfidentialClientApplication(msalConfig);

const tokenResponse = await cca.acquireTokenByClientCredential({
  scopes: ["api://it-standard-mcp/.default"]
});

const accessToken = tokenResponse.accessToken;</div>

    <h3>MCP Tool Call</h3>
    <div class="code-block">const response = await fetch("https://apigee.intel.com/it-standard/mcp", {
  method: "POST",
  headers: {
    "Authorization": `Bearer ${accessToken}`,
    "Content-Type": "application/json"
  },
  body: JSON.stringify({
    jsonrpc: "2.0",
    method: "tools/call",
    params: {
      name: "get_latest_skill",
      arguments: { name: "SDLC" }
    },
    id: 1
  })
});

const result = await response.json();
// result.result.content[0].text → Skill content
// result.result.metadata → { name, version, status, commit_sha, ... }</div>
  </section>

  <section class="section">
    <h2>Well-Known Endpoint Response</h2>
    <div class="code-block">GET /.well-known/oauth-protected-resource

{
  "authorization_servers": [
    "https://login.microsoftonline.com/{tenant-id}/v2.0"
  ],
  "scopes_supported": [
    "api://it-standard-mcp/skills.read"
  ],
  "bearer_methods_supported": ["header"]
}</div>
  </section>

  <section class="section">
    <h2>JWT Claims Used</h2>
    <div style="overflow-x:auto;border:1px solid var(--color-border);border-radius:var(--radius-md)">
      <table class="config-table">
        <thead><tr><th>Claim</th><th>Mapped Header</th><th>Purpose</th></tr></thead>
        <tbody>
          <tr><td>oid</td><td>X-User-Id</td><td>Identifies the authenticated Intel employee (audit trail)</td></tr>
          <tr><td>appid</td><td>X-Client-Id</td><td>Identifies the calling agent/application (adoption tracking)</td></tr>
          <tr><td>scp / roles</td><td>—</td><td>Validated by Apigee for skills.read scope</td></tr>
          <tr><td>iss</td><td>—</td><td>Must match Entra ID issuer for the Intel tenant</td></tr>
          <tr><td>aud</td><td>—</td><td>Must match api://it-standard-mcp</td></tr>
        </tbody>
      </table>
    </div>
  </section>

  <section class="section">
    <h2>Integration Checklist</h2>
    <ul class="checklist" id="checklist">
      <li><span class="check-box"></span><div><strong>App registration created</strong> in Microsoft Entra ID with appropriate redirect URIs</div></li>
      <li><span class="check-box"></span><div><strong>API permission granted</strong> for scope api://it-standard-mcp/skills.read</div></li>
      <li><span class="check-box"></span><div><strong>Admin consent obtained</strong> for the API permission in your tenant</div></li>
      <li><span class="check-box"></span><div><strong>Token acquisition tested</strong> — successfully obtained a JWT from Entra ID</div></li>
      <li><span class="check-box"></span><div><strong>Dev endpoint reachable</strong> — POST to /it-standard-dev/mcp returns valid JSON-RPC response</div></li>
      <li><span class="check-box"></span><div><strong>list_skills tested</strong> — returns catalog with skill metadata array</div></li>
      <li><span class="check-box"></span><div><strong>get_skill tested</strong> — returns full SKILL.md content with metadata</div></li>
      <li><span class="check-box"></span><div><strong>Error handling implemented</strong> — 401, 403, SKILL_NOT_FOUND, INVALID_VERSION handled gracefully</div></li>
      <li><span class="check-box"></span><div><strong>Token refresh implemented</strong> — auto-refresh before expiry (default 1 hour TTL)</div></li>
      <li><span class="check-box"></span><div><strong>Production endpoint validated</strong> — POST to /it-standard/mcp returns production skills</div></li>
    </ul>
    <div class="alert alert-info" style="margin-top:var(--space-4)"><span>ℹ</span><div>Need help? Contact the IT Standards team at <strong>it-standards-team@intel.com</strong> or open an issue in the intel-innersource/it-standard-mcp repository.</div></div>
  </section>
</div>

<script>
(function() {
  var isDark = false;
  document.querySelector('.theme-toggle').addEventListener('click', function() {
    isDark = !isDark;
    document.documentElement.setAttribute('data-theme', isDark ? 'dark' : '');
    if (!isDark) document.documentElement.removeAttribute('data-theme');
    this.textContent = isDark ? '🌙' : '☀';
  });

  // Checklist interaction
  document.querySelectorAll('.checklist li').forEach(function(item) {
    item.addEventListener('click', function() {
      this.classList.toggle('checked');
      var box = this.querySelector('.check-box');
      box.textContent = this.classList.contains('checked') ? '✓' : '';
    });
  });
})();
</script>
</body>
</html>
```

**Source:** mixed  
**Provenance:** intent: US-011: access skills through AI agent without additional registration; Authentication & Authorization Flow — Token acquisition, gateway validation, ABAC; Well-Known Endpoint: /.well-known/oauth-protected-resource | assessment: Architecture: Gateway-enforced security — Apigee validates JWT, injects X-User-Id, X-Client-Id | policy: API Design Conventions — consistent naming, versioning, response formats

---

## Skill Publishing Workflow

Visual guide for Skill Contributors and Admins showing the end-to-end publishing workflow: fork → create version folder → PR to dev → CI validation → admin review → merge to dev → test on dev MCP → promotion PR to main → production deployment. Includes CI validation rules, folder naming conventions, YAML frontmatter schema, and the CODEOWNERS review process. Presented as an interactive step-by-step flow.

### Component Hierarchy
```
PublishingWorkflow
├── ThemeToggle
├── Container
│   ├── PageHeader (title + description)
│   └── WorkflowTrack
│       ├── WorkflowStep 1: Fork & Create (Contributor)
│       │   ├── StepIndicator (numbered dot + connecting line)
│       │   └── StepContent (title, description, code examples)
│       ├── WorkflowStep 2: Open PR to Dev (Contributor)
│       ├── WorkflowStep 3: CI Validation (CI Pipeline)
│       │   └── ValidationList (pass/fail checks)
│       ├── WorkflowStep 4: Admin Review (Admin)
│       ├── WorkflowStep 5: Dev MCP Serves (System)
│       ├── WorkflowStep 6: Test on Dev (Contributor)
│       ├── WorkflowStep 7: Promotion PR (Admin)
│       └── WorkflowStep 8: Production Updated (System)
│           └── ImmutabilityAlert
```

### HTML Preview
```html
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>IT-Standard MCP — Publishing Workflow</title>
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&family=JetBrains+Mono:wght@400;500&display=swap" rel="stylesheet">
<style>
:root {
  --color-primary: #0068B5; --color-primary-hover: #005494; --color-primary-light: #E8F2FB;
  --color-secondary: #00C7B7; --color-accent: #7C3AED; --color-accent-light: #EDE9FE;
  --color-bg: #FFFFFF; --color-surface: #F8FAFC; --color-surface-raised: #FFFFFF;
  --color-text: #0F172A; --color-text-secondary: #475569; --color-text-muted: #94A3B8;
  --color-success: #059669; --color-success-bg: #ECFDF5;
  --color-warning: #D97706; --color-warning-bg: #FFFBEB;
  --color-error: #DC2626; --color-error-bg: #FEF2F2;
  --color-info: #0284C7; --color-info-bg: #F0F9FF;
  --color-border: #E2E8F0; --color-border-strong: #CBD5E1;
  --color-code-bg: #F1F5F9;
  --color-badge-active: #059669; --color-badge-active-bg: #ECFDF5;
  --color-badge-deprecated: #D97706; --color-badge-deprecated-bg: #FFFBEB;
  --font-sans: 'Inter', -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif;
  --font-mono: 'JetBrains Mono', 'Fira Code', 'Consolas', monospace;
  --text-xs: 0.75rem; --text-sm: 0.875rem; --text-base: 1rem; --text-lg: 1.125rem; --text-xl: 1.25rem; --text-2xl: 1.5rem;
  --weight-regular: 400; --weight-medium: 500; --weight-semibold: 600; --weight-bold: 700;
  --leading-normal: 1.5;
  --space-1: 4px; --space-2: 8px; --space-3: 12px; --space-4: 16px; --space-5: 20px; --space-6: 24px; --space-8: 32px;
  --shadow-sm: 0 1px 2px 0 rgba(0,0,0,0.05); --shadow-md: 0 4px 6px -1px rgba(0,0,0,0.1), 0 2px 4px -2px rgba(0,0,0,0.1);
  --radius-sm: 4px; --radius-md: 8px; --radius-lg: 12px; --radius-full: 9999px;
  --transition-fast: 150ms ease;
}
[data-theme="dark"] {
  --color-primary: #60A5FA; --color-primary-hover: #93C5FD; --color-primary-light: #1E3A5F;
  --color-secondary: #34D399; --color-accent: #A78BFA; --color-accent-light: #2E1065;
  --color-bg: #0F172A; --color-surface: #1E293B; --color-surface-raised: #334155;
  --color-text: #F1F5F9; --color-text-secondary: #CBD5E1; --color-text-muted: #64748B;
  --color-success: #34D399; --color-success-bg: #064E3B;
  --color-warning: #FBBF24; --color-warning-bg: #78350F;
  --color-error: #F87171; --color-error-bg: #7F1D1D;
  --color-info: #38BDF8; --color-info-bg: #0C4A6E;
  --color-border: #334155; --color-border-strong: #475569;
  --color-code-bg: #1E293B;
  --color-badge-active: #34D399; --color-badge-active-bg: #064E3B;
  --color-badge-deprecated: #FBBF24; --color-badge-deprecated-bg: #78350F;
  --shadow-sm: 0 1px 2px 0 rgba(0,0,0,0.3); --shadow-md: 0 4px 6px -1px rgba(0,0,0,0.4), 0 2px 4px -2px rgba(0,0,0,0.3);
}
* { margin:0; padding:0; box-sizing:border-box; }
body { font-family:var(--font-sans); background:var(--color-bg); color:var(--color-text); line-height:var(--leading-normal); }
.theme-toggle { position:fixed; top:12px; right:12px; z-index:9999; background:var(--color-surface-raised); border:1px solid var(--color-border); border-radius:var(--radius-full); width:40px; height:40px; cursor:pointer; display:flex; align-items:center; justify-content:center; font-size:18px; box-shadow:var(--shadow-sm); }
.container { max-width:900px; margin:0 auto; padding:var(--space-8); }
.page-title { font-size:var(--text-2xl); font-weight:var(--weight-bold); margin-bottom:var(--space-2); }
.page-desc { color:var(--color-text-secondary); font-size:var(--text-sm); margin-bottom:var(--space-8); }
.workflow-track { position:relative; }
.workflow-step { display:flex; gap:var(--space-5); margin-bottom:var(--space-6); position:relative; }
.step-indicator { display:flex; flex-direction:column; align-items:center; }
.step-dot { width:36px; height:36px; border-radius:50%; display:flex; align-items:center; justify-content:center; font-weight:var(--weight-bold); font-size:var(--text-sm); color:#FFF; flex-shrink:0; cursor:pointer; transition:all var(--transition-fast); }
.step-dot.contributor { background:var(--color-primary); }
.step-dot.ci { background:var(--color-accent); }
.step-dot.admin { background:var(--color-secondary); }
.step-dot.system { background:var(--color-info); }
.step-dot.active { box-shadow:0 0 0 4px var(--color-primary-light); transform:scale(1.1); }
.step-line { width:2px; flex:1; min-height:20px; background:var(--color-border); margin-top:var(--space-1); }
.step-content { flex:1; background:var(--color-surface-raised); border:1px solid var(--color-border); border-radius:var(--radius-lg); padding:var(--space-5); box-shadow:var(--shadow-sm); transition:all var(--transition-fast); }
.step-content.active { border-color:var(--color-primary); box-shadow:var(--shadow-md); }
.step-content .step-title { font-weight:var(--weight-semibold); font-size:var(--text-base); margin-bottom:var(--space-2); display:flex; align-items:center; gap:var(--space-2); }
.step-content .step-desc { font-size:var(--text-sm); color:var(--color-text-secondary); margin-bottom:var(--space-3); }
.step-content .step-detail { font-size:var(--text-sm); }
.role-badge { display:inline-flex; padding:2px var(--space-2); border-radius:var(--radius-full); font-size:var(--text-xs); font-weight:var(--weight-medium); }
.role-contributor { background:var(--color-primary-light); color:var(--color-primary); }
.role-ci { background:var(--color-accent-light); color:var(--color-accent); }
.role-admin { background:var(--color-success-bg); color:var(--color-success); }
.role-system { background:var(--color-info-bg); color:var(--color-info); }
.code-inline { font-family:var(--font-mono); background:var(--color-code-bg); padding:1px 6px; border-radius:var(--radius-sm); font-size:var(--text-xs); border:1px solid var(--color-border); }
.code-block { background:var(--color-code-bg); border:1px solid var(--color-border); border-radius:var(--radius-md); padding:var(--space-4); font-family:var(--font-mono); font-size:var(--text-xs); overflow-x:auto; line-height:1.6; white-space:pre; margin-top:var(--space-3); }
.validation-list { list-style:none; padding:0; margin-top:var(--space-2); }
.validation-list li { display:flex; align-items:flex-start; gap:var(--space-2); padding:var(--space-1) 0; font-size:var(--text-xs); }
.check-pass { color:var(--color-success); }
.check-fail { color:var(--color-error); }
.alert { padding:var(--space-3) var(--space-4); border-radius:var(--radius-md); font-size:var(--text-sm); display:flex; gap:var(--space-3); align-items:flex-start; margin-top:var(--space-4); }
.alert-info { background:var(--color-info-bg); color:var(--color-info); border:1px solid var(--color-info); }
.section { margin-bottom:var(--space-8); }
.section h2 { font-size:var(--text-xl); font-weight:var(--weight-bold); margin-bottom:var(--space-4); padding-bottom:var(--space-2); border-bottom:1px solid var(--color-border); }
@media (max-width: 768px) {
  .workflow-step { flex-direction:column; }
  .step-indicator { flex-direction:row; gap:var(--space-2); }
  .step-line { width:auto; height:2px; min-height:0; min-width:20px; margin:0 0 0 var(--space-1); }
}
</style>
</head>
<body>
<button class="theme-toggle" aria-label="Toggle theme">☀</button>
<div class="container">
  <h1 class="page-title">📝 Skill Publishing Workflow</h1>
  <p class="page-desc">End-to-end process for creating, validating, testing, and promoting skill definitions from development to production.</p>

  <div class="workflow-track">
    <div class="workflow-step" data-step="1">
      <div class="step-indicator"><div class="step-dot contributor active">1</div><div class="step-line"></div></div>
      <div class="step-content active">
        <div class="step-title"><span class="role-badge role-contributor">Contributor</span> Fork & Create Skill</div>
        <div class="step-desc">Fork the monorepo, create a version folder following naming conventions, and author the SKILL.md file with YAML frontmatter.</div>
        <div class="step-detail">
          <strong>Folder structure:</strong>
          <div class="code-block">skills/
  └── SDLC/                     # Skill folder: [a-zA-Z0-9-]+
      └── SDLC-2.0.0/           # Version: SKILL-MAJOR.MINOR.PATCH
          └── SKILL.md           # Exactly one file per version</div>
          <strong style="display:block;margin-top:var(--space-3)">YAML Frontmatter:</strong>
          <div class="code-block">---
name: SDLC
version: 2.0.0
description: "Software Development Lifecycle skill"
owner: it-standards-team
status: active
tags:
  - sdlc
  - governance
  - development
---</div>
        </div>
      </div>
    </div>

    <div class="workflow-step" data-step="2">
      <div class="step-indicator"><div class="step-dot contributor">2</div><div class="step-line"></div></div>
      <div class="step-content">
        <div class="step-title"><span class="role-badge role-contributor">Contributor</span> Open PR to Dev Branch</div>
        <div class="step-desc">Submit a pull request targeting the <span class="code-inline">dev</span> branch. This triggers automated CI validation.</div>
      </div>
    </div>

    <div class="workflow-step" data-step="3">
      <div class="step-indicator"><div class="step-dot ci">3</div><div class="step-line"></div></div>
      <div class="step-content">
        <div class="step-title"><span class="role-badge role-ci">CI Pipeline</span> Automated Validation</div>
        <div class="step-desc">CI runs comprehensive checks on the skill definition. All checks must pass before merge is allowed.</div>
        <div class="step-detail">
          <ul class="validation-list">
            <li><span class="check-pass">✓</span> Folder name matches <span class="code-inline">[a-zA-Z0-9-]+</span></li>
            <li><span class="check-pass">✓</span> Version folder matches <span class="code-inline">SKILL-MAJOR.MINOR.PATCH</span></li>
            <li><span class="check-pass">✓</span> Exactly one <span class="code-inline">SKILL.md</span> file exists</li>
            <li><span class="check-pass">✓</span> YAML frontmatter contains required fields: name, version, description, owner, status, tags</li>
            <li><span class="check-pass">✓</span> Frontmatter <span class="code-inline">name</span> matches folder name</li>
            <li><span class="check-pass">✓</span> Frontmatter <span class="code-inline">version</span> matches version folder</li>
            <li><span class="check-pass">✓</span> Secret scanning passes (no credentials in content)</li>
            <li><span class="check-fail">✕</span> <em>Example failure:</em> Frontmatter version "2.0" does not match folder "SDLC-2.0.0"</li>
          </ul>
        </div>
      </div>
    </div>

    <div class="workflow-step" data-step="4">
      <div class="step-indicator"><div class="step-dot admin">4</div><div class="step-line"></div></div>
      <div class="step-content">
        <div class="step-title"><span class="role-badge role-admin">Admin</span> Review & Merge to Dev</div>
        <div class="step-desc">A CODEOWNERS-listed admin reviews the PR for content quality and policy compliance, then merges to the dev branch.</div>
      </div>
    </div>

    <div class="workflow-step" data-step="5">
      <div class="step-indicator"><div class="step-dot system">5</div><div class="step-line"></div></div>
      <div class="step-content">
        <div class="step-title"><span class="role-badge role-system">System</span> Dev MCP Serves New Skill</div>
        <div class="step-desc">Within ~60 seconds, the dev MCP server (<span class="code-inline">/it-standard-dev/mcp</span>) detects the new commit via polling and rebuilds its index. The new skill version is now available for testing.</div>
      </div>
    </div>

    <div class="workflow-step" data-step="6">
      <div class="step-indicator"><div class="step-dot contributor">6</div><div class="step-line"></div></div>
      <div class="step-content">
        <div class="step-title"><span class="role-badge role-contributor">Contributor</span> Test on Dev MCP</div>
        <div class="step-desc">Verify the skill is correctly served by calling the dev MCP endpoint. Test all tool calls: list, search, get, get_latest, list_versions.</div>
      </div>
    </div>

    <div class="workflow-step" data-step="7">
      <div class="step-indicator"><div class="step-dot admin">7</div><div class="step-line"></div></div>
      <div class="step-content">
        <div class="step-title"><span class="role-badge role-admin">Admin</span> Promotion PR to Main</div>
        <div class="step-desc">Admin opens a PR from <span class="code-inline">dev</span> to <span class="code-inline">main</span>. CI enforces immutability — rejects any modification or deletion of existing version folders on main.</div>
      </div>
    </div>

    <div class="workflow-step" data-step="8">
      <div class="step-indicator"><div class="step-dot system">8</div></div>
      <div class="step-content">
        <div class="step-title"><span class="role-badge role-system">System</span> Production MCP Updated</div>
        <div class="step-desc">Within ~60 seconds, the production MCP server (<span class="code-inline">/it-standard/mcp</span>) detects the new commit on main and updates its index. The skill is now live for all agents enterprise-wide.</div>
        <div class="alert alert-info"><span>ℹ</span><div>Production content on main is <strong>immutable</strong>. Once merged, version folders cannot be modified or deleted. To fix errors, publish a new patch version.</div></div>
      </div>
    </div>
  </div>
</div>

<script>
(function() {
  var isDark = false;
  document.querySelector('.theme-toggle').addEventListener('click', function() {
    isDark = !isDark;
    document.documentElement.setAttribute('data-theme', isDark ? 'dark' : '');
    if (!isDark) document.documentElement.removeAttribute('data-theme');
    this.textContent = isDark ? '🌙' : '☀';
  });

  // Step click to highlight
  document.querySelectorAll('.workflow-step').forEach(function(step) {
    step.addEventListener('click', function() {
      document.querySelectorAll('.step-dot').forEach(function(d) { d.classList.remove('active'); });
      document.querySelectorAll('.step-content').forEach(function(c) { c.classList.remove('active'); });
      this.querySelector('.step-dot').classList.add('active');
      this.querySelector('.step-content').classList.add('active');
    });
  });
})();
</script>
</body>
</html>
```

**Source:** intent  
**Provenance:** intent: US-006: submit a new skill version via PR and receive CI feedback; US-007: review and merge skill contributions with governance rules enforced; US-012: test skill on dev MCP environment before promoting to production; Process 2: Skill Publishing and Promotion Workflow | assessment: Architecture: CI validation rules, CODEOWNERS, branch protection, immutability enforcement

---

## Available Visual Resources
- **HTML Previews:** 8 page(s) included above as rendered HTML.
  Use the HTML structure, CSS classes, and inline styles as the source of truth for visual layout.
  Cross-reference with the design tokens above for exact color values and spacing.
- **UX Reference Images:** Call `get_artifact(ux_references=true)` to view uploaded mockup images with AI descriptions.
