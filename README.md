# EJ2 JavaScript Schedule

> This sample explains the way to open the [EJ2 JavaScript Schedule](https://www.syncfusion.com/javascript-ui-controls/js-scheduler) editor window in single click. Refer to the below KB for more details.

https://www.syncfusion.com/kb/10608/how-to-open-editor-window-in-single-click

In this example, the Syncfusion JavaScript Scheduler is configured to open the event editor window with a single click. The popupOpen event is used to intercept the default quick popup behavior. When the user clicks on a work cell or an existing event, the popup is canceled using args.cancel = true, and the editor window is manually triggered using openEditor. This allows for a more streamlined and direct editing experience. The editor opens in either "Add" or "Save" mode depending on the target element clicked.

This approach enhances usability by reducing the number of interactions needed to manage events and provides a faster way to access full event details for editing. It is especially useful in applications where quick scheduling and minimal clicks are preferred for better productivity.