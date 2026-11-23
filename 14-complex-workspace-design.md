# Complex enterprise workspace architecture

## When to use
Use for dense CRM, ERP, membership, finance, administration and operational workspaces containing multiple related datasets, nested navigation, forms and contextual actions. Do not impose every region on simple pages. Identify the actual user task, data relationships, edit ownership and viewport constraints first.

## Region and scope contract
| Region | Responsibility | Placement |
|---|---|---|
| Global shell | Product identity, workspace, global search, notifications, account | Persistent top header |
| Product rail | Switch major product areas when genuinely necessary | Leftmost rail |
| Module navigation | Routes within current product area | Left sidebar, collapsible |
| Breadcrumb | Hierarchical ancestors | Above title |
| Record header | Name/ID, status, key summary, primary record action | Top of main workspace |
| Record tabs | Sibling views of current entity | Beneath record header |
| Section toolbar | Actions for one dataset/section | Beside heading or above data |
| Main workspace | Task-critical forms, records and tables | Largest region |
| Related panel | Supporting context, history, notes, quick links | Optional right panel |
| Action footer | Submit/cancel for active editing scope | Bottom of editing region |
| Status bar | Sync/version/connectivity when relevant | Separate from action footer |

## Select a composition
- List-detail: left record list and right selected detail for frequent record switching; selection reflected in URL where appropriate.
- Record hub: identity summary, tabs and related datasets; preserve record ID and active tab.
- Multi-panel operations console: queue, selected work item, contextual information; independent scrolling only where needed.
- Dashboard: actionable exceptions and metrics first; each widget links to its filtered data.
- Configuration workspace: scope selector, section navigation, forms; make inheritance and overrides explicit.
- Comparison view: align corresponding attributes; highlight meaningful differences and provide accessible textual labels.
- Master-detail-detail: use only if hierarchy is important; replace tertiary panel with drawer on narrow screens.

## Nested navigation and action ownership
Use one navigation level per real information hierarchy, not per component. Product rail switches product; sidebar changes module; tabs change record view; anchors scroll within a document. Never use multiple navigation systems for the same destination. Show active path and accessible current state. Use real links for routes, buttons for mutations. Avoid deep menus and duplicate primary buttons. Label scope explicitly: Save customer vs Save invoice; never use one ambiguous Save for unrelated independently persisted sections. Where a whole record is edited atomically, use one shared action footer; where sections persist independently, use local actions and statuses.

## Density and information priority
Classify fields as identity, decision-critical, operational, secondary or historical. Put identity and decision-critical information in summary; operational data in the current view; secondary content in collapsible sections; history in a dedicated tab/panel. Use compact label/value grids for read-only metadata rather than disabled inputs. Group related information; avoid cards inside cards unless boundaries carry meaning. Use whitespace, headings and thin separators rather than heavy borders everywhere. Use existing spacing/type tokens. Keep row actions adjacent to their row. Do not hide important status or permissions in hover-only tooltips.

## Layout implementation
Use CSS grid or flex; main min-width:0, min-height:0 for bounded scroll regions; responsive tracks with minmax(0,1fr). Keep main as default scroll owner; independent scrolling for long queues or related panels only if tested. Example desktop tracks: optional 56px product rail, 224px sidebar, minmax(0,1fr) main, optional 280–360px context panel. These are starting points, not mandatory dimensions. At medium widths collapse rail/sidebar or move contextual panel to drawer; at small widths use a single-column main view, accessible navigation drawer, responsive tabs and local horizontal table scrolling where necessary. Avoid fixed viewport assumptions, clipped content, nested scroll traps and sticky regions covering focused controls. Preserve readable content and zoom support.
```css
.workspace { display:grid; grid-template-columns:auto minmax(0,1fr); }
.workspace-main { min-width:0; min-height:0; }
.record-layout { display:grid; grid-template-columns:minmax(0,1fr) minmax(16rem,22rem); }
@media (max-width: 70rem) {
  .record-layout { grid-template-columns:minmax(0,1fr); }
}
```
Use project breakpoints and components instead of copying these values blindly.

## State and data ownership
Model workspace ID, module route, record ID, active tab, filters, sort, pagination, selection, open panel, focus return target and drafts separately. Encode shareable non-sensitive route state in URL; keep ephemeral state local and tenant/user scoped. Reset record-specific state on identity changes; preserve valid module list state on return. Fetch independent panels independently, with local loading/error/retry; do not block whole workspace for a secondary panel failure. Cancel stale requests when selection changes; avoid displaying previous record data as current. Server validates authorisation for each query and mutation. Resolve concurrent changes and protect drafts before switching records. Do not make unsaved changes disappear on tab change.

## Concrete example: membership management
Record header: member name/number, membership status, renewal date; primary action depends on workflow. Tabs: Membership, Timeline, Invoices, Add-ons, Journal. Membership section: current plan, start/end, linked invoice, renewal action. Invoice section: invoice ID, date, amount, payment status, View/Download; row actions next to invoice. Related panel: activity, notes, affiliations. Personal or organisation settings remain outside record unless they configure that member. Replace large repeated cards with compact structured rows when comparison is the task. A user should open an invoice directly from its link without navigating to an unrelated module first.

## Review gates
1. Document region ownership and navigation hierarchy before coding.
2. Identify the primary task in each region and justify every persistent panel.
3. Record baseline and proposed task steps, including search, scrolling and transitions.
4. Verify no conflicting save actions or inaccessible hidden controls.
5. Test record switching, direct links, browser back, draft recovery, concurrent changes, partial failures and permission changes.
6. Test keyboard, screen reader landmarks, focus management, zoom, narrow viewport and long translated labels.
7. Confirm related panel failure leaves main workspace operable and no cross-record stale data.
8. Report measured evidence and untested cases; do not claim unrun tests.

## Anti-patterns
Nested cards for every field; global header repeated inside record; settings scattered across unrelated menus; deep nested tabs for unrelated entities; all regions sticky; repeated full-page navigation for a single-field edit; global loading overlay for a local refresh; ambiguous Save; hiding frequent actions in overflow; forcing desktop panels into a narrow screen; using colour alone for critical status.
