# How to Open the EJ2 JavaScript Schedule Editor Window in a Single Click

This example repository demonstrates how to open the [JavaScript Scheduler](https://www.syncfusion.com/javascript-ui-controls/js-scheduler) editor window directly in a single click. It showcases how to bypass the default QuickInfo popup and immediately launch the editor when a user interacts with the scheduler, providing a streamlined experience for adding or editing appointments.

## Features

- Demonstrates opening the Schedule editor window in a single click
- Cancels the default QuickInfo popup using the `popupOpen` event
- Differentiates between creating a new appointment and editing an existing one
- Uses Syncfusion EJ2 JavaScript controls via CDN
- Includes sample appointment data for quick testing

## Installation

1. Clone or download this repository
2. Open `Ej2.html` directly in a web browser, or serve the file using a local web server (for example, `live-server`)

## Usage

The Schedule component is initialized with a `popupOpen` event handler. When the user clicks on the scheduler, the QuickInfo popup is canceled and the editor window is opened directly. The action type is determined based on the click target:

```javascript
var scheduleObj = new ej.schedule.Schedule({
    width: '100%', height: '550px',
    selectedDate: new Date(2023, 1, 15),
    eventSettings: {
        dataSource: data
    },
    popupOpen: function (args) {
        if (args.type == "QuickInfo") {
            args.cancel = true;
            var currentAction = args.target.classList.contains("e-work-cells") ? "Add" : "Save";
            scheduleObj.openEditor(args.data, currentAction);
        }
    }
});
scheduleObj.appendTo('#Schedule');
```

The `popupOpen` event handler:

- Cancels the default QuickInfo popup by setting `args.cancel = true`
- Checks whether the click target is a work cell (`e-work-cells`) or an existing appointment
- Sets `currentAction` to `"Add"` for new appointments or `"Save"` for existing ones
- Calls `scheduleObj.openEditor(args.data, currentAction)` to open the editor window in a single click

## Documentation

- General Syncfusion docs: https://help.syncfusion.com/
- JavaScript Schedule introduction: https://ej2.syncfusion.com/javascript/documentation/schedule/getting-started
- KB article: https://www.syncfusion.com/kb/10608/how-to-open-editor-window-in-single-click