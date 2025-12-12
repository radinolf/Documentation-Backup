# E.1 How to configure the Execute button to execute JavaScript code

## How to configure the Execute button to execute JavaScript code

This example will show how to use JavaScript code in the Execute button through the **execution type** **JAVASCRIPT**. In this instance, a confirmation box is displayed on the page after the button execution using the **Decisyon JavaScript function:** `DECISYON.utils.openConfirmDialog(message, title, onConfirm, onCancel, icon, labelYes, labelNo, width, height, idDialog)`

## **Step 1**

Create a new Page in the Page Design and use the Execute button widget.

<figure><img src="../../../../../.gitbook/assets/image (33).png" alt=""><figcaption></figcaption></figure>

## **Step 2**

Configure the widget properties:

* **button-text** (**Main** group)**:** input "Open"
* **execution-type** (**Execution** group)**:** select JAVASCRIPT\_ONLY
* **javaScript-code-after** (**Execution** group)**:** open the dialog and enter the JavaScript code to be run:

```javascript
let message = 'Dialog message content';
        let title = 'Dialog title';
        let onConfirm = () => {
              };
        let onCancel = () => {
            alert('openConfirmDialog cancel callback');
        };
        let icon = '2';
        let labelYes = 'YES';
        let labelNo = 'NO';
        let width = 600;
        let height = 400;
        let idDialog = '1234567890';
        
        DECISYON.utils.openConfirmDialog(message, title, onConfirm, onCancel, icon, labelYes, labelNo, width, height, idDialog);
```

## **Step 3**

Open the Web Application and click the button.

<figure><img src="../../../../../.gitbook/assets/image (29).png" alt=""><figcaption></figcaption></figure>

