# SYNC COMPONENTS

Add some flair to your projects by trying our dazzling yet practical Button & Alert components! Built with user interactivity and accessibility in mind, choose from an array of themes/variant types pertaining to each level of action severity, along with customizable options to tailor and enhance the functionality of each component.

Check out our [documentation site](https://sync-documentation.onrender.com/) for visuals of our components.

## Table of Contents (Sticky)

- [Installation](#installation)
- [Usage](#usage)
- [Props](#props)
- [Customization](#customization)

## Installation

Run either of these commands inside the terminal:

```bash
  $ npm install @holmesdev/sync
  $ yarn add @holmesdev/sync
```

> [!IMPORTANT] > [Styled-components](https://styled-components.com/docs/basics#installation) is the JavaScript CSS library used to build our components. To ensure that they work as intended, you will need to separately install `styled-components` within both the `devDependencies` & `peerDependencies` inside of your `package.json` upon installation of the package.
>
> You <ins>MUST</ins> also ensure that you are:
>
> - Using React.js v18.3.1 or higher
> - Using styled-components v6.1.13 or higher

## Latest Package Version

|                                Name                                |                              Version                              |
| :----------------------------------------------------------------: | :---------------------------------------------------------------: |
| [`@holmesdev/sync`](https://www.npmjs.com/package/sync-components) | [![NPM](https://img.shields.io/npm/v/:@holmesdev/sync/v/1.0.2)]() |

Install the latest package version if required:

```bash
  $ npm install @holmesdev/sync@latest
  $ yarn add @holmesdev/sync@latest
```

## Usage

Import the components (together or separately, depending on usage) inside your project:

```js
import { Button, Alert, AlertDialog } from "@holmesdev/sync";
```

### Button Component

A `Button` that allows the user to trigger an action when clicked. It comes with a selection of themes/variants.

```js
import Button from 'sync-components';

//Primary Button with Link and Custom Hover Color
//Aria-Label: aria-label="Link to https://sync-documentation.onrender.com/" —

<Button
  variant="primary"
  hoverColor="#1f56ec"
  path="https://sync-documentation.onrender.com/"
>
  Click Me
</Button>

//Success Button with Click Handler (No Link)
//Aria-Label: aria-label="Success Action"
<Button
  variant="success"
  hoverColor="#1cd560"
  type = "submit"
  onClick={() => alert("Button clicked!")}
>
  Success Action
</Button>

//Warning Button with Path and New Hover Color
//Aria-Label: aria-label="Link to /internal-page"
<Button
  variant="warning"
  hoverColor="#ef2929"
  path="/internal-page"
>
  Warning Link
</Button>

//Default Button with No Hover Color
//Aria-Label: aria-label="Default Action"
<Button
  variant="default"
  onClick={() => console.log("Default button clicked")}
>
  Default Action
</Button>


_________________________________________________


```

### Alert Component

An `Alert` box that appears on the page with a status notification or an action request. It comes with a selection of themes/statuses.

```js
import Alert from 'sync-components';

<Alert
  title="Success!"
  body="Your action was completed successfully."
  status="success"
/>


____________________________________________________________________________________

//ALERT STATUS EXAMPLES:

<div>

// Success Alert
<Alert
  title="Success!"
  body="Your action was completed successfully."
  status="success"
/>

// Error Alert
<Alert
  title="Error!"
  body="Something went wrong. Please try again."
  status="error"
/>

// Warning Alert
<Alert
  title="Warning!"
  body="Be careful! This action could have consequences."
  status="warning"
/>

// Info Alert
<Alert
  title="Information"
  body="Here is some important information for you."
  status="info"
/>

// Custom Alert with auto-dismiss
<Alert
  title="Notice"
  body="This alert will disappear after a few seconds."
  status="info"

/>

// Alert with close button
<Alert
  title="Heads Up!"
  body="You can dismiss this alert by clicking the close button."
  status="warning"

/>
```

### AlertDialog

The role of `AlertDialog` is to "link" the `Alert` & `Button` components together, as well as toggling the visibility of the `Alert` on the page.

```js
import AlertDialog from "sync-components";


<AlertDialog
  title="Success!"
  body="Your action was completed successfully."
  status="success"
  buttonVariant="success"
  btnColor="#28a745"
  hoverColor="#218838"
  onClick={() => alert("Success dialog opened")}
>
  Show Success
</AlertDialog>

<AlertDialog
  title="Error"
  body="Something went wrong. Please try again."
  status="danger"
  buttonVariant="warning"
  btnColor="#dc3545"
  hoverColor="#c82333"
  onClick={() => alert("Error dialog opened")}
>
  Show Error
</AlertDialog>

<AlertDialog
  title="Information"
  body="This is just an informational message."
  status="default"
  buttonVariant="default"
  btnColor="#17a2b8"
  hoverColor="#138496"
  onClick={() => alert("Information dialog opened")}
>
  Show Info
</AlertDialog>

<AlertDialog
  title="Warning"
  body="Are you sure you want to leave without saving?"
  status="warning"
  buttonVariant="warning"
  btnColor="#ffc107"
  hoverColor="#e0a800"
  path="/unsaved-changes"
  onClick={() => alert("Warning dialog opened")}
>
  Leave Without Saving
</AlertDialog>

```

## Props

### Button Component Props

| Prop         | Type       | Required | Description                                                                       |
| ------------ | ---------- | -------- | --------------------------------------------------------------------------------- |
| `children`   | `string`   | Yes      | Text or content inside the button.                                                |
| `variant`    | `string`   | No       | Button style. Options: `default`, `primary`, `success`, `warning`.                |
| `hoverColor` | `string`   | No       | Color displayed on hover.                                                         |
| `path`       | `string`   | No       | URL path if the button is used as a link.                                         |
| `onClick`    | `function` | Yes      | Callback function for the button click event.                                     |
| `type`       | `string`   | No       | Button type attribute. Options: `button`, `submit`, `reset`. Default is `button`. |

### Alert Component Props

| Prop          | Type       | Required | Description                                                               |
| ------------- | ---------- | -------- | ------------------------------------------------------------------------- |
| `children`    | `string`   | Yes      | Content to be displayed inside the alert.                                 |
| `type`        | `string`   | No       | Alert type. Options: `info`, `success`, `warning`, `error`.               |
| `onClose`     | `function` | No       | Callback function triggered when the alert is closed.                     |
| `isVisible`   | `boolean`  | No       | Controls visibility of the alert. Default is `true`.                      |
| `autoDismiss` | `boolean`  | No       | Automatically dismisses the alert after a set time.                       |
| `dismissTime` | `number`   | No       | Time in milliseconds before auto-dismiss (used if `autoDismiss` is true). |

---

### AlertDialog Component Props

| Prop           | Type       | Required | Description                                                                   |
| -------------- | ---------- | -------- | ----------------------------------------------------------------------------- |
| `title`        | `string`   | Yes      | Title text of the alert dialog.                                               |
| `description`  | `string`   | No       | Description text providing more details about the dialog.                     |
| `isOpen`       | `boolean`  | Yes      | Controls whether the dialog is visible.                                       |
| `onConfirm`    | `function` | Yes      | Callback function triggered on confirming action.                             |
| `onCancel`     | `function` | No       | Callback function triggered on canceling action.                              |
| `confirmLabel` | `string`   | No       | Label text for the confirm button. Default is "Confirm".                      |
| `cancelLabel`  | `string`   | No       | Label text for the cancel button. Default is "Cancel".                        |
| `variant`      | `string`   | No       | Dialog variant. Options: `default`, `danger`, `warning`.                      |
| `ariaLabel`    | `string`   | No       | Accessibility label for screen readers, describing the purpose of the dialog. |

## Themes

### Light Themes

- `default`: Gradient border with a white background
- `primary`: Blue border with a white background
- `success`: Green border with a white background
- `warning`: Red border with a white background

### Dark Themes

- `defaultDark`: Gradient border with a black background
- `primaryDark`: Blue border with a black background
- `successDark`: Green border with a black background
- `warningDark`: Red border with a black background

## Customization

- `title` & `body` text is customizable for each component
- `variant` & `status` need to be specified inside your code, and no further CSS customization is necessary

## Accessibility

Each component has an `aria-label` and `title` to meet basic accessibility standards.

## License

[![MIT License](https://img.shields.io/badge/License-MIT-green.svg)](https://github.com/4DEVS-Holmesglen/4DEVS-SYNC/blob/main/MIT%20License)

Available for open-source consumption under MIT licensing. See [MIT License](https://github.com/4DEVS-Holmesglen/Sync-test/blob/main/MIT%20License) for more information.
