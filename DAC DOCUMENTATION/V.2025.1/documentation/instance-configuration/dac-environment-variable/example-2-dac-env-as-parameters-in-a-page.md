# Example 2: DAC ENV as parameters in a page

## Introduction

We propose an example of using DAC ENV as a pre-selection value for a Page.

In this example you will differentiate the background colors of pages between the test and pre-production environments. This could be useful, in example, when you want App Developers to pay more attention during the page editing phase, thereby avoiding making impactful changes, for example, in a pre-production environment.

### Step 1: Create the DAC ENV in the POD

If we aim to have two different colors in two distinct environments, you need to create a DAC ENV containing the specific color in both the Test and Pre-Production environment pods. The variable name must be the same in both environments, but you need to set a different value, i.e.

| DAC ENV name        | Value in Test    | Value in Preprod |
| ------------------- | ---------------- | ---------------- |
| DAC\_ENV\_bg\_Color | rgb(192,192,192) | rgb(144,238,144) |

\
<br>

<figure><img src="../../../.gitbook/assets/image (2039).png" alt=""><figcaption></figcaption></figure>

### Step 2: Create the DAC ENV n the client

In order to have the DAC ENV in the list of pre-selection-values in Page Designer, you need to create the and environment variable in your client.

`setx DAC_ENV_bg_Color "rgb(192,192,192)"`

### Step 3 - Configure the page

Access on the Page Designer and select the page property pre-selection-value.

<figure><img src="../../../.gitbook/assets/image (2040).png" alt=""><figcaption></figcaption></figure>

Create a page parameter named “color” of type “Variable” and select the DAC ENV `DAC_ENV_bg_Color` from the dropdown menu.

### Step 4 - Test the page

Now synchronize the page from the DEV environment to the Pre Prod environment. If you have properly configured the example, the two pages will inherited the value for the background color from the DAC ENV.

<figure><img src="../../../.gitbook/assets/image (2041).png" alt=""><figcaption></figcaption></figure>

In the test environment, the page background is gray.

<figure><img src="../../../.gitbook/assets/image (2042).png" alt=""><figcaption></figcaption></figure>

In the Pre-Production environment, the page background is green .

<br>
