---
metaLinks:
  alternates:
    - >-
      https://app.gitbook.com/s/h9Knuj2BfqZwIB5BI7sj/migration-notes/migration-notes
---

# Migration Notes

## Version 3.0

This section outlines the changes and impacts of migrating the Button widget to version 3.0, which requires management by the App Developer.

## Overview

With the enhancements introduced in Button widget [**DC-1083** / **DC-1069**](../changelog/change-log/version-3.0.md) (refer to the Change Log section), significant style updates have been made to align the widget with the latest Angular Material Design standards. Notably, this includes changes to the **Flat** style.

### Key Changes

1. **Updated Styles**:
   * **Flat Style Renamed to Basic**: The "Flat" style, previously the default, has been redesigned and renamed to "Basic" to reflect its updated design.
   * **Consistency with Angular Material**: All button styles (Raised, FAB, Icon) have been updated to the latest Angular Material standards without any changes to their existing style.
   * **New Styles Introduced**: Additional button styles have been introduced to enhance the design options.
2. **Removal of Zoom Property**:
   * **Zoom Property Removed**: The zoom property has been removed from the widget. The custom zoom options (Medium, Large, and XLarge) are no longer supported. Consequently, buttons previously using these zoom settings will default to "Normal".

### Impact on Existing Buttons

1.  **Flat Style Buttons**:

    * **Visual Changes**: Buttons using the "Flat" style in previous versions will look significantly different after the upgrade.

    <figure><img src="../.gitbook/assets/image (50).png" alt=""><figcaption></figcaption></figure>

    * **Manual Update Required**: The App Developer should manually update buttons from the "Flat" style to the new "Basic" style to maintain visual consistency.

    <figure><img src="../.gitbook/assets/image (51).png" alt=""><figcaption></figcaption></figure>
2. **Zoom Property**:
   * **Impact on Pages**: Buttons previously using zoom options Medium, Large, and XLarge will default to "Normal". This change may result in layout alterations, such as the appearance of scrollbars or misaligned elements.
   * **Verification Needed**: The App Developer should check the pages that utilized custom zoom settings in the previous version to ensure they render correctly and do not introduce layout issues.

### Migration Steps

1. **Upgrade the Button widget to version 3.0**.
2. **Manually Update Styles**: Review and manually update all buttons using the "Flat" style to the new "Basic" style.
3. **Check Pages with Custom Zoom:** Review pages using the Buttons with **zoom** property options  Medium, Large, and XLarge to ensure they render correctly and do not introduce scrollbars or misaligned elements.
4. **Verify and Test**: After updating the styles and checking the custom zoom, verify the appearance and functionality of the buttons to ensure they align with the new design standards.
