---
name: enterprise-ux-skill
description: Design, implement, and review enterprise SaaS, CRM, ERP and admin interfaces for low interaction cost, consistent navigation, accessible controls, responsive layouts, and reliable workflows. Use when creating or changing screens, forms, tables, menus, settings, dashboards, or reviewing UI pull requests.
---
# Enterprise UX skill

## Objective
Minimise total user effort, not clicks alone. Preserve safety, accessibility, privacy, and correctness. Follow the mandatory canonical visual standard below. Preserve existing functionality and safety; explicitly surface conflicting project branding requirements.

## Workflow
1. Inspect existing screens, components, project instructions, and task constraints. Identify user role, task frequency, data size, and risk.
2. Map current and proposed workflow; choose navigation, action scope, controls and interaction container. Read the relevant references below.
3. Implement the smallest useful change with existing components. Preserve state and enforce permissions and validation server-side.
4. Cover loading, empty, error, success, permission and recovery states. Test keyboard, responsive layout, and realistic task flows.
5. Report decisions, before/after interaction effort, changes, tests and outstanding issues. Do not claim tests that were not run.

## Mandatory guardrails
- Keep frequent actions directly accessible; use overflow for infrequent actions.
- Global actions belong in global header; page actions in page header; list actions in toolbar; row/field actions near data; long-form submission in sticky footer where useful.
- Choose visible options for small frequent sets and searchable comboboxes for large sets. Do not default to dropdowns.
- Prefer inline edits, drawers, master-detail, and bulk operations when appropriate. Preserve search, filters, pagination, scroll and drafts.
- Separate personal, organisation, module and record settings.
- Use semantic controls, accessible labels, keyboard navigation, focus management, responsive layouts and clear feedback.
- Keep necessary safeguards for destructive, sensitive and high-impact actions. Never bypass authentication or authorisation.
- Reuse the design system; avoid gratuitous redesign and extra dependencies.

## References
- [Application shell and screen architecture](01-application-shell.md)
- [Navigation and action placement](02-navigation-and-placement.md)
- [Input and interaction component selection](03-component-selection.md)
- [Interaction cost and workflow optimisation](04-interaction-optimisation.md)
- [Forms and validation](05-form-design.md)
- [Data tables, views and search](06-data-table-design.md)
- [Settings, identity and collaboration](07-settings-architecture.md)
- [Feedback, system states and assistance](08-feedback-and-system-states.md)
- [Responsive layout and device ergonomics](09-responsive-design.md)
- [Accessibility and inclusive design](10-accessibility.md)
- [Design system and visual consistency](11-design-tokens.md)
- [UX performance and measurement](12-performance.md)
- [Review checklist and acceptance criteria](13-ux-review-checklist.md)

- [Complex enterprise workspace architecture](14-complex-workspace-design.md)

## Complex workspace trigger
For multi-region, nested navigation, record hubs, dense administration screens or split-pane workflows, read 14-complex-workspace-design.md before implementation. Define region ownership, navigation hierarchy, independent state, responsive collapse and action scope. Do not apply a generic dashboard layout blindly.

## Mandatory visual fidelity — read first
Every invocation of this skill for UI work MUST read [15-canonical-visual-standard.md](15-canonical-visual-standard.md) and [examples/enterprise-workbench.html](examples/enterprise-workbench.html) before designing or coding. The HTML is the canonical source of truth for colors, typography, spacing, icons, controls and layout composition. It takes precedence over generic visual suggestions in other references. Match its styles exactly for applicable components; adapt business content and behavior only. Do not silently substitute other themes. Preserve accessibility, security and functional correctness, documenting necessary exceptions.
