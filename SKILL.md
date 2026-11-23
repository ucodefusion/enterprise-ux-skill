---
name: enterprise-ux-skill
description: Design, implement, and review enterprise SaaS, CRM, ERP and admin interfaces for low interaction cost, consistent navigation, accessible controls, responsive layouts, and reliable workflows. Use when creating or changing screens, forms, tables, menus, settings, dashboards, or reviewing UI pull requests.
---
# Enterprise UX skill

## Objective
Minimise total user effort, not clicks alone. Preserve safety, accessibility, privacy, and correctness. Follow existing project design tokens and conventions unless a justified change is requested.

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
