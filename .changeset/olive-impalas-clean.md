---
'lint-staged': patch
---

Remove the `abort` event listener of a task when the task finishes instead of keeping it registered on the shared `AbortSignal`. Listeners previously accumulated for the whole run, so more than 10 tasks triggered `MaxListenersExceededWarning` on Node.js versions that still check `AbortSignal` listener counts.
