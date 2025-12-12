# New Feature

*   **DACXX-2036 – Restored full viewport usage for drill-through dialogs in fullscreen mode**

    The fullscreen mode of drill-through dialogs now completely hides the application interface. Verified that the interface correctly reappears once the dialog is closed. By default, the navigation panel remains closed after exiting fullscreen mode.
*   **DACXX-2059 – Improved backend performance for parameter export functions**

    Optimized parameter calculation by introducing multithreading and thread-safe page loading. Parameter computation for widgets and reports now runs in parallel across multiple threads, improving overall performance.
*   **DACXX-2722 – Display ADP file name in the Synchronization page**

    Updated the synchronization API to include the imported ADP file name, now shown in the Application Synchronization Log Summary dialog in Cockpit. The change slightly modifies the UI layout but does not affect synchronization functionality.
