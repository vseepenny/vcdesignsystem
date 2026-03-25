# VSee Design System — Figma Integration Guide

## Overview

The VSee Design System v4 is a healthcare-focused component library. All design tokens and components are defined in `vsee-design-system-v4.html` (embedded CSS) and `vsee-design-system-v4.tokens.json`.

The system is **CSS-class-based** (no React/Vue framework — plain HTML + CSS + vanilla JS). All tokens are CSS custom properties on `:root`.

---

## Design Tokens

Source: `vsee-design-system-v4.tokens.json` and `:root` block in `vsee-design-system-v4.html`.

### Colors

```css
/* Brand */
--brand: #0D875C;
--brand-hover: #0B7550;
--brand-active: #096843;
--brand-light: #E6F5EE;
--brand-50: #F0FAF5;

/* Semantic */
--color-success: #0D875C;
--color-info: #0575AD;
--color-warning: #F59E0B;
--color-danger: #DC2626;

/* Neutral */
--color-black: #111827;
--color-grey-900: #1F2937;  /* ... through ... */
--color-grey-100: #F3F4F6;
--color-white: #FFFFFF;

/* Surfaces */
--surface-page: #FFFFFF;
--surface-subtle: #F9FAFB;
--surface-muted: #F3F4F6;
--surface-overlay: rgba(0,0,0,0.6);

/* Text */
--text-primary: #111827;
--text-secondary: #6B7280;
--text-tertiary: #9CA3AF;
--text-inverse: #FFFFFF;
--text-link: #065F46;

/* Borders */
--border-default: #E5E7EB;
--border-strong: #D1D5DB;
--border-focus: #0D875C;

/* Status (EMR/clinic) */
--status-ordered: #0D875C;
--status-scheduled: #0575AD;
--status-overdue: #EF4444;
--status-in-progress: #F59E0B;
--status-cancelled: #9CA3AF;
--status-completed: #374151;
```

### Spacing

4px base unit: `--sp-1` (4px) → `--sp-24` (96px)

| Token | Value |
|-------|-------|
| `--sp-1` | 4px |
| `--sp-2` | 8px |
| `--sp-3` | 12px |
| `--sp-4` | 16px |
| `--sp-5` | 20px |
| `--sp-6` | 24px |
| `--sp-8` | 32px |
| `--sp-10` | 40px |
| `--sp-12` | 48px |
| `--sp-16` | 64px |

### Typography

```css
--font-sans: 'Inter', -apple-system, BlinkMacSystemFont, sans-serif;
--font-mono: 'SF Mono', 'Fira Code', 'Consolas', monospace;

/* Sizes */
--text-xs: 12px;   --text-sm: 13px;   --text-base: 14px;
--text-lg: 16px;   --text-xl: 18px;   --text-2xl: 20px;
--text-3xl: 24px;  --text-4xl: 30px;  --text-5xl: 36px;
```

### Border Radius

```css
--r-sm: 4px;    --r-md: 6px;    --r-lg: 8px;
--r-xl: 12px;   --r-2xl: 24px;  --r-full: 9999px;
```

### Shadows

```css
--shadow-xs: 0 1px 2px rgba(0,0,0,0.05);
--shadow-sm: 0 1px 3px rgba(0,0,0,0.1), 0 1px 2px rgba(0,0,0,0.06);
--shadow-md: 0 4px 6px -1px rgba(0,0,0,0.1), 0 2px 4px -2px rgba(0,0,0,0.1);
--shadow-lg: 0 10px 15px -3px rgba(0,0,0,0.1), 0 4px 6px -4px rgba(0,0,0,0.1);
--shadow-focus: 0 0 0 3px rgba(13,135,92,0.15);
```

### Motion

```css
--ease: cubic-bezier(0.4, 0, 0.2, 1);
--t-fast: 150ms;   --t-base: 200ms;   --t-slow: 300ms;
```

### Z-Index

```css
--z-base: 0;  --z-dropdown: 10;  --z-sticky: 20;
--z-overlay: 30;  --z-modal: 40;  --z-toast: 50;
```

---

## Component Library

All components use plain CSS classes. No framework. Apply classes directly to HTML elements.

### Buttons

```html
<!-- Variants -->
<button class="btn btn-primary">Save</button>
<button class="btn btn-secondary">Cancel</button>
<button class="btn btn-ghost">Ghost</button>
<button class="btn btn-danger">Delete</button>
<button class="btn btn-danger-outline">Delete</button>
<button class="btn btn-info">Info</button>
<button class="btn btn-warning">Warning</button>
<button class="btn btn-link">Link</button>

<!-- Sizes -->
<button class="btn btn-primary btn-sm">Small</button>
<button class="btn btn-primary btn-lg">Large</button>
<button class="btn btn-primary btn-xl">XL</button>

<!-- Modifiers -->
<button class="btn btn-primary btn-block">Full Width</button>
<button class="btn btn-primary btn-pill">Pill</button>
<button class="btn btn-primary btn-icon">⚙</button>
<button class="btn btn-primary btn-loading">Loading</button>
<button class="btn btn-primary" disabled>Disabled</button>

<!-- Group -->
<div class="btn-group">
  <button class="btn btn-secondary">One</button>
  <button class="btn btn-secondary">Two</button>
</div>
```

### Forms

```html
<!-- Text input -->
<div class="form-group">
  <label class="form-label">Name <span class="req">*</span></label>
  <input type="text" class="input" placeholder="Enter name">
  <div class="form-hint">Helper text</div>
</div>

<!-- Error state -->
<input type="text" class="input error">
<div class="form-error-text">This field is required</div>

<!-- Large input -->
<input type="text" class="input input-lg">

<!-- Textarea -->
<textarea class="input" rows="4"></textarea>

<!-- Select -->
<select class="input">
  <option>Option 1</option>
</select>

<!-- Input group (prefix/suffix) -->
<div class="input-group">
  <span class="input-addon">$</span>
  <input type="text" class="input">
  <span class="input-addon">.00</span>
</div>

<!-- Checkbox / Radio -->
<label class="check-item">
  <input type="checkbox"> Label
</label>

<!-- Toggle -->
<label class="toggle">
  <div class="toggle-track on">
    <div class="toggle-thumb"></div>
  </div>
  <span>Enabled</span>
</label>
```

### Badges & Status

```html
<!-- Badges (pill-shaped, outline style) -->
<span class="badge badge-success">Active</span>
<span class="badge badge-info">Info</span>
<span class="badge badge-warning">Pending</span>
<span class="badge badge-danger">Error</span>
<span class="badge badge-neutral">Neutral</span>

<!-- Solid badges -->
<span class="badge badge-solid-success">Active</span>

<!-- Clinic status badges -->
<span class="status status-ordered">Ordered</span>
<span class="status status-scheduled">Scheduled</span>
<span class="status status-overdue">Overdue</span>
<span class="status status-in-progress">In Progress</span>
<span class="status status-cancelled">Cancelled</span>
<span class="status status-completed">Completed</span>
```

### Alerts & Toasts

```html
<!-- Alerts -->
<div class="alert alert-success">
  <span class="alert-icon">✓</span>
  <div>Success message</div>
</div>
<div class="alert alert-info"> ... </div>
<div class="alert alert-warning"> ... </div>
<div class="alert alert-danger"> ... </div>

<!-- Toast -->
<div class="toast toast-success">
  <div>
    <div class="toast-title">Saved</div>
    <div class="toast-msg">Changes have been saved.</div>
  </div>
  <button class="toast-close">×</button>
</div>

<!-- Callouts -->
<div class="callout callout-tip">
  <span class="callout-icon">💡</span>
  <div>Tip text</div>
</div>
<div class="callout callout-note"> ... </div>
<div class="callout callout-warn"> ... </div>
```

### Panels & Cards

```html
<div class="panel">
  <div class="panel-header">
    <span>Title</span>
    <button class="btn btn-ghost btn-sm">Action</button>
  </div>
  <div class="panel-body">Content</div>
  <div class="panel-footer">Footer</div>
</div>
```

### Tabs

```html
<div class="tabs">
  <button class="tab-item active">Overview</button>
  <button class="tab-item">Details</button>
  <button class="tab-item">History</button>
</div>
```

### Accordion

```html
<div class="accordion">
  <div class="accordion-item open">
    <button class="accordion-trigger">
      Section Title
      <span class="accordion-chevron">▾</span>
    </button>
    <div class="accordion-content">Content here</div>
  </div>
</div>
```

### Table

```html
<table class="table">
  <thead>
    <tr><th>Name</th><th>Status</th><th>Date</th></tr>
  </thead>
  <tbody>
    <tr><td>John Doe</td><td><span class="status status-scheduled">Scheduled</span></td><td>Mar 24</td></tr>
  </tbody>
</table>
```

### Navigation

```html
<!-- Top navbar -->
<nav class="navbar">
  <div class="navbar-logo">VSee</div>
  <div class="navbar-links">
    <a class="navbar-link active" href="#">Dashboard</a>
    <a class="navbar-link" href="#">Patients</a>
  </div>
</nav>

<!-- Breadcrumb -->
<nav class="breadcrumb">
  <a href="#">Home</a>
  <span class="breadcrumb-sep">/</span>
  <a href="#">Patients</a>
  <span class="breadcrumb-sep">/</span>
  <span class="breadcrumb-current">John Doe</span>
</nav>

<!-- Sidebar layout -->
<div class="sidebar-layout">
  <div class="sidebar-panel">
    <div class="sidebar-menu-item active">Dashboard</div>
    <div class="sidebar-menu-item">Patients</div>
  </div>
  <div class="sidebar-content">Main content</div>
</div>
```

### Avatars

```html
<div class="avatar">JD</div>
<div class="avatar avatar-sm">JD</div>
<div class="avatar avatar-lg">JD</div>
<img class="avatar" src="photo.jpg" alt="Jane Doe">

<!-- Group -->
<div class="avatar-group">
  <div class="avatar">A</div>
  <div class="avatar">B</div>
  <div class="avatar avatar-more">+3</div>
</div>
```

### Data & Progress

```html
<!-- Progress bar -->
<div class="progress-track">
  <div class="progress-bar progress-bar-brand" style="width: 65%"></div>
</div>

<!-- Pagination -->
<div class="pagination">
  <button class="page-btn">‹</button>
  <button class="page-btn active">1</button>
  <button class="page-btn">2</button>
  <button class="page-btn">›</button>
</div>
```

### Utility Components

```html
<!-- Divider -->
<hr class="divider">

<!-- Divider with label -->
<div class="divider-text">OR</div>

<!-- Empty state -->
<div class="empty-state">
  <div class="empty-state-icon">📋</div>
  <div class="empty-state-title">No patients</div>
  <div class="empty-state-desc">No patients found matching your search.</div>
  <button class="btn btn-primary">Add Patient</button>
</div>

<!-- Chips -->
<span class="chip">Default <button class="chip-remove">×</button></span>
<span class="chip chip-brand">Brand</span>
<span class="chip chip-danger">Error</span>

<!-- Skeleton loading -->
<div class="skeleton skeleton-title"></div>
<div class="skeleton skeleton-text"></div>
<div class="skeleton skeleton-avatar"></div>
<div class="skeleton skeleton-btn"></div>

<!-- Tooltip -->
<div class="tooltip-wrap">
  <button class="btn btn-ghost">Hover me</button>
  <div class="tooltip-bubble">Tooltip text</div>
</div>
```

### Modal

```html
<div class="modal-demo">
  <div class="modal-box">
    <div class="modal-head">
      <h3>Modal Title</h3>
      <button class="modal-close">×</button>
    </div>
    <div class="modal-content">Modal content here.</div>
    <div class="modal-actions">
      <button class="btn btn-secondary">Cancel</button>
      <button class="btn btn-primary">Confirm</button>
    </div>
  </div>
</div>
```

### Grid Layout

```html
<div class="grid g2">  <!-- 2 columns -->
<div class="grid g3">  <!-- 3 columns -->
<div class="grid g4">  <!-- 4 columns -->
<div class="grid g5">  <!-- 5 columns -->
```

### Ant Design-Inspired Components (v4.1)

These components follow Ant Design v5 patterns:

```html
<!-- Descriptions (labeled key-value display) -->
<div class="descriptions">
  <div class="descriptions-header">Patient Information</div>
  <div class="descriptions-row">
    <div class="descriptions-item"><div class="descriptions-label">Name</div><div class="descriptions-content">Michelle Doe</div></div>
    <div class="descriptions-item"><div class="descriptions-label">DOB</div><div class="descriptions-content">Apr 12, 1980</div></div>
  </div>
</div>

<!-- Timeline -->
<div class="timeline">
  <div class="timeline-item">
    <div class="timeline-dot timeline-dot-success">&#10003;</div>
    <div class="timeline-content">
      <div class="timeline-title">Lab Results</div>
      <div class="timeline-time">Mar 24, 2026</div>
      <div class="timeline-desc">All values normal.</div>
    </div>
  </div>
</div>

<!-- Dropdown -->
<div class="dropdown">
  <button class="btn btn-default">Actions &#9662;</button>
  <div class="dropdown-menu">
    <div class="dropdown-item">Edit</div>
    <div class="dropdown-divider"></div>
    <div class="dropdown-item dropdown-item-danger">Delete</div>
  </div>
</div>

<!-- List -->
<div class="list">
  <div class="list-header">Messages</div>
  <div class="list-item">
    <div class="avatar avatar-sm">SC</div>
    <div class="list-item-content">
      <div class="list-item-title">Dr. Chen</div>
      <div class="list-item-desc">Lab results ready</div>
    </div>
    <div class="list-item-meta">2 min ago</div>
  </div>
</div>

<!-- Result page -->
<div class="result">
  <div class="result-icon result-icon-success">&#10003;</div>
  <div class="result-title">Appointment Booked</div>
  <div class="result-subtitle">Your visit has been scheduled.</div>
  <div class="result-actions">
    <button class="btn btn-primary">View</button>
    <button class="btn btn-default">Back</button>
  </div>
</div>

<!-- Spin / Loading -->
<span class="spin"></span>
<span class="spin spin-sm"></span>
<span class="spin spin-lg"></span>

<!-- Badge count on avatar -->
<div class="badge-count-wrap">
  <div class="avatar avatar-sm">SC</div>
  <span class="badge-count">3</span>
</div>

<!-- Message bar -->
<div class="message-bar message-success">
  <span class="message-icon">&#10003;</span> Saved
</div>

<!-- Popover -->
<div class="popover-wrap">
  <button class="btn btn-default">Info</button>
  <div class="popover">
    <div class="popover-title">Title</div>
    <div class="popover-content">Content</div>
  </div>
</div>

<!-- Tags (Ant naming for badges) -->
<span class="tag tag-success">Active</span>
<span class="tag tag-bordered tag-info">Info</span>

<!-- Buttons: Ant Design types -->
<button class="btn btn-primary">Primary</button>
<button class="btn btn-default">Default</button>
<button class="btn btn-dashed">Dashed</button>
<button class="btn btn-text">Text</button>
<button class="btn btn-link">Link</button>

<!-- Card-type tabs -->
<div class="tabs tabs-card">
  <div class="tab-item active">Tab 1</div>
  <div class="tab-item">Tab 2</div>
</div>

<!-- Drawer (static demo) -->
<div class="drawer-panel">
  <div class="drawer-head"><h3>Title</h3></div>
  <div class="drawer-body">Content</div>
  <div class="drawer-footer"><button class="btn btn-primary">Save</button></div>
</div>

<!-- Tree -->
<div class="tree">
  <div class="tree-node tree-node-root">
    <div class="tree-item">
      <span class="tree-expand open">&#9654;</span>
      <span>Parent Node</span>
    </div>
    <div class="tree-children">
      <div class="tree-node">
        <div class="tree-item selected">Leaf Node</div>
      </div>
    </div>
  </div>
</div>

<!-- Typography -->
<div class="typo-title-1">h1 Title</div>
<div class="typo-title-2">h2 Title</div>
<span class="typo-text typo-text-secondary">Secondary</span>
<span class="typo-text-mark">Highlighted</span>
<span class="typo-text-code">code</span>

<!-- Space utility -->
<div class="space space-md">
  <button class="btn btn-primary">Save</button>
  <button class="btn btn-default">Cancel</button>
</div>

<!-- Watermark -->
<div class="panel watermark" data-watermark="DRAFT">Content</div>

<!-- Rate/Stars -->
<div class="rate">
  <span class="rate-star active">&#9733;</span>
  <span class="rate-star active">&#9733;</span>
  <span class="rate-star">&#9733;</span>
</div>

<!-- Closable alert -->
<div class="alert alert-success alert-closable">
  Message <button class="alert-close">&times;</button>
</div>
```

---

## Theming

The design supports 5 color themes via a `data-theme` attribute on `<html>` or a container element:

- `emerald` (default) — `--brand: #0D875C`
- `ocean` — `--brand: #0575AD`
- `violet` — purple brand
- `amber` — `--brand: #F59E0B`
- `rose` — rose/pink brand

Dark mode: add `data-mode="dark"` to the root element.

---

## Figma → Code Mapping

When translating Figma designs to this system:

| Figma element | CSS class / token |
|---------------|-------------------|
| Primary button | `btn btn-primary` |
| Secondary button | `btn btn-secondary` |
| Card/Panel | `panel` + `panel-header` / `panel-body` |
| Input field | `input` (inside `form-group`) |
| Status pill | `status status-{ordered\|scheduled\|...}` |
| Green badge | `badge badge-success` |
| Alert banner | `alert alert-{success\|info\|warning\|danger}` |
| Data table | `table` |
| Sidebar nav | `sidebar-layout` + `sidebar-panel` |
| Top nav | `navbar` |
| Brand green | `var(--brand)` = #0D875C |
| Body text | `var(--text-primary)` = #111827 |
| Secondary text | `var(--text-secondary)` = #6B7280 |
| Page background | `var(--surface-page)` = #FFFFFF |
| Subtle background | `var(--surface-subtle)` = #F9FAFB |
| Border | `var(--border-default)` = #E5E7EB |
| Default button (bordered) | `btn btn-default` |
| Dashed button | `btn btn-dashed` |
| Text button | `btn btn-text` |
| Key-value data | `descriptions` + `descriptions-row` + `descriptions-item` |
| Timeline / history | `timeline` + `timeline-item` |
| Dropdown menu | `dropdown` + `dropdown-menu` + `dropdown-item` |
| List with items | `list` + `list-item` |
| Side drawer | `drawer-panel` + `drawer-head` / `drawer-body` |
| Result page | `result` + `result-icon-{success\|error}` |
| Loading spinner | `spin` / `spin-sm` / `spin-lg` |
| Count badge on avatar | `badge-count-wrap` + `badge-count` |
| Tag (Ant naming) | `tag tag-{success\|info\|warning\|danger}` |
| Bordered tag | `tag tag-bordered tag-{success\|...}` |
| Card-type tabs | `tabs tabs-card` |
| Tree | `tree` + `tree-node` + `tree-item` |
| Popover | `popover-wrap` + `popover` |
| Watermark | `watermark` + `data-watermark="TEXT"` |

---

## Key Conventions

1. **Font**: Always use Inter (`--font-sans`). 14px is the base body size.
2. **Spacing**: Use `--sp-*` tokens. Default component padding is `--sp-4` (16px) to `--sp-6` (24px).
3. **Radius**: Inputs/buttons use `--r-md` (6px). Panels use `--r-xl` (12px). Pills use `--r-full`. (Aligned with Ant Design v5)
4. **Brand color**: `#0D875C` emerald green. Never use raw hex — reference `--brand`.
5. **Status badges**: Use `.status` classes for clinic workflow states (ordered, scheduled, overdue, etc.).
6. **Danger actions**: Use `btn-danger` (solid) for destructive; `btn-danger-outline` for secondary destructive.
7. **Focus rings**: `--shadow-focus` = `0 0 0 3px rgba(13,135,92,0.15)` — applied automatically on `.input:focus`.
8. **Disabled state**: Add `disabled` attribute or `.disabled` class — renders at 40% opacity.
