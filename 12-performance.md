# UX performance and measurement

## Perceived speed
Use skeletons for meaningful loading, retain previous results during refresh where safe, and avoid full page reloads for small changes.

## Technical patterns
Use debounced search, request cancellation, pagination, caching scoped by permissions, lazy loading and selective prefetch. Respect network and device constraints.

## Optimistic updates
Use only for suitable reversible operations; reconcile server responses and roll back on error. Do not show unconfirmed financial or high-impact operations as complete.

## Metrics
Measure clicks/taps, keystrokes, screen transitions, time on task, completion rate, error rate, abandonment, scroll effort and perceived ease. Establish baseline and compare equivalent tasks.

## Testing
Test real tasks with representative users and realistic data. Include keyboard, mobile, slow network, error, permission and concurrency scenarios. Avoid rigid universal click targets.
