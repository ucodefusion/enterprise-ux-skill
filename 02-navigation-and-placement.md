# Navigation and action placement

## Navigation hierarchy
Use workspace switcher for organisation, sidebar for modules, tabs for record sections, anchors/scrollspy for long pages, stepper for sequential work and mobile bottom navigation for core destinations.

## Action scope
Global actions in header; page actions in page header; list actions in toolbar; row actions in row; field actions beside field; submission in form footer.

## Frequency and hierarchy
Expose frequent actions directly. Use primary, secondary and tertiary visual emphasis; place rare actions in overflow. Use split buttons for a default plus variants.

## Shortcuts and continuity
Provide favourites, recent records, saved views, deep links, previous/next record and command palette (Cmd/Ctrl+K). Preserve filters, scroll, pagination and tabs; support browser Back.

## Workspace layouts
Use master-detail for repeated browsing, split view for comparison, and multi-tab workspace for parallel work with unsaved-change protection.

## Settings scope
Profile menu: personal preferences/security. Sidebar administration: organisation, roles, billing, integrations. Module settings near module; record settings in record tabs; table preferences in toolbar.

## Navigation decision algorithm
Identify scope (application, workspace, module, record, section, field), frequency, hierarchy and whether destination is a route or an action. Use real links for destinations and buttons for actions. For a handful of short module labels use top navigation; for numerous or nested modules use a persistent collapsible sidebar; for multiple product areas use module switcher plus contextual navigation. Avoid requiring hover to open submenus. Aim for shallow hierarchy, but do not flatten unrelated features into an overwhelming list. Record tabs represent sibling views of the same entity; a stepper represents sequential progress, not arbitrary navigation.

## Placement rules
Global create belongs in header only if it creates records across modules. Create Customer belongs beside Customers title. Add Contact belongs beside Contacts heading within customer details. Export selected belongs in selection toolbar, not each row. Edit a single field belongs next to the field or in an explicit editing mode. Personal preferences belong to profile; organisation billing belongs to authorised organisation settings; table density belongs to table controls. Destructive actions must be labelled and separated from common reversible actions. Never use an unlabeled ellipsis as the only access to frequent actions.

## Navigation state contract
Encode shareable list filters, sort, page and selected detail tab in route/query parameters where appropriate. Keep transient scroll, focus and draft state scoped by workspace, user and route; never store sensitive data in URLs. Browser Back/Forward must behave predictably. On return from editing, restore filter and scroll if record still matches; if not, explain why it disappeared. A direct link must work without prior list history. Unsaved edits require a recoverable draft or a navigation guard when loss would matter.

## Examples
Bad: Dashboard > Sales > Customers > Customer > Settings > Change status. Better: Customers list > inline status control > confirmed update; restrict to valid transitions and allow undo when safe.
Bad: global Settings > Reports > Columns. Better: column chooser directly in report toolbar, with saved view option.
Bad: click each record, back to list, repeat. Better: master-detail or Previous/Next within filtered dataset; keep current position and guard unsaved edits.

## Acceptance criteria
Every destination has an accessible name, current-state indicator and authorised route. Keyboard users can open/close menus and return focus. Breadcrumb current item is not a misleading link. Deep links and browser history are tested. Navigation depth and actual steps for frequent tasks are documented before and after; no universal three-click rule.
