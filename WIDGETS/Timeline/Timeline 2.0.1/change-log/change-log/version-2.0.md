# Version 2.0

## ✨ New  <a href="#toc89767737" id="toc89767737"></a>

* DC-1248 – **Support for Parameter Exporting**

The widget now supports exporting key information (such as selected timestamp, title, and description) as parameters, allowing for greater control and data interactivity across widgets. Refer [here](../../whats-new/whats-new.md#export-timeline-selections-as-parameters) for more details.

* DC-1249 / DC-582 – **Configurable Event Spacing Mode**

A new property lets page developers choose how events are distributed along the timeline—either fixed or proportionally based on their actual timestamps. Refer [here](../../whats-new/whats-new.md#new-event-spacing-mode-for-visual-accuracy) for more details.

## ➕ Improved  <a href="#toc68682153" id="toc68682153"></a>

* DC-654 – **Enhanced Layout Flexibility with Flex Containers**

The widget now supports flexible container behavior, adapting its dimensions automatically when placed inside a flex layout. This ensures better responsiveness and smoother integration with modern page structures.

* DC-499 – **Improved Compatibility with Restricted Environments**

The widget now avoids external font calls, improving support for offline and firewall-restricted environments.

* DC-809 **– Standardization of Date Format Handling**

Updated internal handling of date and time formats to align with modern standards, ensuring greater consistency with the other widgets.

## 🔧Fixed <a href="#toc78540232" id="toc78540232"></a>

* DC-957 – **Fixed XSS Vulnerabilities in Timeline Widget**

Fixed cross-site scripting vulnerabilities that allowed script injection through event fields. User inputs are now correctly sanitized and rendered as plain text to prevent execution of malicious code.

&#x20;                                                                       &#x20;
