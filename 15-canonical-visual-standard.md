# Mandatory canonical visual implementation contract

The file [examples/enterprise-workbench.html](examples/enterprise-workbench.html) is the normative visual reference, not optional inspiration. Whenever this skill is invoked for UI design, implementation or review, read its complete HTML, CSS and relevant JavaScript before generating UI. Reproduce its visual language faithfully. Do not substitute a generic component-library theme, independently invent a palette or redesign the shell. Adapt domain content and functionality, not visual identity.

## Exact base tokens
Use the following reference values without alteration unless the user explicitly approves a deviation:
| Token | Value |
|---|---|
| Main text | #20324b |
| Muted text | #64758e |
| Border | #dfe6ef |
| Subtle background | #f3f6f9 |
| Accent | #6345ff |
| Success | #26821d |
| Error | #d82d50 |
| Canvas | white |
| Sidebar width | 222px |
| Bottom utility bar | 44px |
| Base typography | 13px / 1.5, -apple-system, BlinkMacSystemFont, Segoe UI, Arial, sans-serif |

The complete CSS in the canonical HTML governs component-specific colors, dimensions, spacing, breakpoints, hover and selected states. Do not approximate these from the table alone.

## Required component fidelity
Use the reference's compact outlined buttons (6px radius, 6px 10px padding), filled accent primary button where applicable, bare icon utilities, 17px single-colour outline SVG icons with 1.65 stroke, 26px page headings, 18px secondary headings, 13px section headings, understated horizontal tabs, compact search field, thin table separators, status labels, status filter buttons, date-grouped request rows, bordered popovers, JSON syntax highlighting, and modest shadows restricted primarily to floating surfaces. Preserve visual hierarchy and whitespace relationships from the HTML. Do not introduce gradients, large rounded cards, colourful illustrations, oversized headings, alternate icon families or decorative backgrounds.

## Required layout fidelity
- Business list page: 222px grouped left navigation, 62px global header, compact page header with right-aligned actions, tabs, optional contextual banner, visible status filters and table toolbar, flat data table, pagination, 44px bottom utility dock.
- Developer workbench: dock-triggered full-width workspace above utility bar, compact header and horizontal tabs, two-thirds integration metrics region and one-third health/resources region, two-column metric grid with genuine empty states, read-only console pattern at bottom when appropriate.
- Log inspector: compact horizontal filters, two independently scrollable panes separated by draggable divider, date-grouped list left, selected request metadata and collapsible syntax-highlighted payload right. Preserve list context and selection.
- Use analogous layouts for other domain screens. Do not add a developer dock or log console to unrelated tasks simply to copy the example. Adapt the appropriate region structure while preserving its styling.
- Follow the reference responsive breakpoints (1000px, 720px) and layout collapse patterns unless accessibility or task requirements necessitate adjustment.

## Implementation procedure
1. Read canonical HTML and identify matching classes and layouts.
2. Extract/reuse its CSS variables, component rules, icon geometry and shell structure in the target framework. Use existing accessible primitives only if styled to match.
3. Map domain functionality into the matching template. Never copy demo account data, simulate production operations or replace real integrations with mock handlers.
4. Preserve existing business logic, permissions, accessibility and security. If a reference implementation detail conflicts with those requirements, correct the functional/accessibility issue while retaining visual fidelity as closely as possible.
5. Compare rendered output against the canonical example at matching viewport widths. Check colors, type, spacing, controls, sidebar, table, panels and responsive behavior. Report discrepancies and any approved or necessary exceptions. Do not claim tests not executed.
6. If the target project has a conflicting mandatory brand/design system, identify the conflict explicitly rather than silently mixing styles; request direction when necessary.

## Definition of done
All relevant components and regions visually match the canonical reference; no unauthorized style overrides; actual tasks function; keyboard and responsive behavior verified where tools permit; deviations documented. A screenshot alone or a generic modern-looking implementation is not sufficient.
