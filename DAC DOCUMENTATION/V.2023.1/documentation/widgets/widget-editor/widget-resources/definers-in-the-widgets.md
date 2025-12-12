# Definers in the Widgets

It is possible to use the following definers in the `configuration.json` of the widgets:

## **SELECT**

The **Select** definer defines the input field with options that can be selected from a dropdown menu.

{% code fullWidth="true" %}
```json
   {
    "additionalSettings": {
        "groups": {
            "$GROUP_NAME": {
                "name": "Group name",
                "desc": "Group description",
                "subGroups": {
                    "$SUB_GROUP_NAME": {
                        "name": "Sub group name",
                        "subSets": {
                            "$SUB_SET_NAME": {
                                "name": "Sub set name",
                                "properties": {
                                  "$selectorPropertyName": {
                                        "name": "Selector property name",
                                        "desc": "Selector property descriptor",
                                        "definer": "SELECT",
                                        "value": {
                                            "desc": "Value 0",
                                            "longDesc": "First value",
                                            "value": "0"
                                        },
                                        "admissibleValues": [
                                            {
                                                "desc": "Value 0",
                                                "longDesc": "First value",
                                                "value": "0"
                                            },
                                            {
                                                "desc": "Value 1",
                                                "longDesc": "Second value",
                                                "value": "1"
                                            },
                                            {
                                                "desc": "Value 2",
                                                "longDesc": "Third value",
                                                "value": "2"
                                              }]
                                }
                            }
                        }
                    }
                }
            }
        }
    }
}}
```
{% endcode %}

<div data-full-width="true"><figure><img src="../../../../.gitbook/assets/image (1108).png" alt=""><figcaption></figcaption></figure></div>

## **NUMERIC**

The **Numeric** definer defines the input field to enter a number and reject any non-numerical values.

{% code fullWidth="true" %}
```json
 {
    "additionalSettings": {
        "groups": {
            "$GROUP_NAME": {
                "name": "Group name",
                "desc": "Group description",
                "subGroups": {
                    "$SUB_GROUP_NAME": {
                        "name": "Sub group name",
                        "subSets": {
                            "$SUB_SET_NAME": {
                                "name": "Sub set name",
                                "properties": {
                                    "$numericPropertyName": {
                                        "name": "Numeric property name",
                                        "desc": "Numeric property description",
                                        "definer": "NUMERIC",
                                        "value": "1234"
                                }
                            }
                        }
                    }
                }
            }
        }
    }
}}               
```
{% endcode %}

<div data-full-width="true"><figure><img src="../../../../.gitbook/assets/image (245).png" alt=""><figcaption></figcaption></figure></div>

## **SWITCH**

The **Switch** definer defines the control element that allows you to enable or disable a property (using a checkbox).

{% code fullWidth="true" %}
```json5
{
    "additionalSettings": {
        "groups": {
            "$GROUP_NAME": {
                "name": "Group name",
                "desc": "Group description",
                "subGroups": {
                    "$SUB_GROUP_NAME": {
                        "name": "Sub group name",
                        "subSets": {
                            "$SUB_SET_NAME": {
                                "name": "Sub set name",
                                "properties": {
                                    "$switchPropertyName": {
                                        "name": "Switch property name",
                                        "desc": "Switch property description",
                                        "definer": "SWITCH",
                                        "value": "1"
                                }
                            }
                        }
                    }
                }
            }
        }
    }
}}
```
{% endcode %}

<div data-full-width="true"><figure><img src="../../../../.gitbook/assets/image (244).png" alt=""><figcaption></figcaption></figure></div>

## **TEXTFIELD**

The **Textfield** definer defines the input field to capture different text data types in a single line.

{% code fullWidth="true" %}
```json5
{
    "additionalSettings": {
        "groups": {
            "$GROUP_NAME": {
                "name": "Group name",
                "desc": "Group description",
                "subGroups": {
                    "$SUB_GROUP_NAME": {
                        "name": "Sub group name",
                        "subSets": {
                            "$SUB_SET_NAME": {
                                "name": "Sub set name",
                                "properties": {
                                    "$stringPropertyName": {
                                        "name": "String property name",
                                        "desc": "String property description",
                                        "definer": "TEXTFIELD",
                                        "value": "initial text value"
                                }
                            }
                        }
                    }
                }
            }
        }
    }
}}
```
{% endcode %}

<div data-full-width="true"><figure><img src="../../../../.gitbook/assets/image (166).png" alt=""><figcaption></figcaption></figure></div>

## **TEXTAREA**

The **Textarea** defines a multi-line text input.

{% code fullWidth="true" %}
```json5
{
    "additionalSettings": {
        "groups": {
            "$GROUP_NAME": {
                "name": "Group name",
                "desc": "Group description",
                "subGroups": {
                    "$SUB_GROUP_NAME": {
                        "name": "Sub group name",
                        "subSets": {
                            "$SUB_SET_NAME": {
                                "name": "Sub set name",
                                "properties": {
                                    "$stringPropertyName": {
                                        "name": "String property name",
                                        "desc": "String property description",
                                        "definer": "TEXTAREA",
                                        "value": "initial text value"
                                }
                            }
                        }
                    }
                }
            }
        }
    }
}}
```
{% endcode %}

<div data-full-width="true"><figure><img src="../../../../.gitbook/assets/image (1132).png" alt=""><figcaption></figcaption></figure></div>

## **EXECUTE\_BUTTON**

The **EXECUTE\_BUTTON** definer allow page developer to select one of the execute button widgets available in the page from a dedicated list.

### Example - Definer for selecting an Execute Button in the page <a href="#definer-to-selected-an-execute-button-in-the-containing-page" id="definer-to-selected-an-execute-button-in-the-containing-page"></a>

In the following example, we will define in the `configuration.json` the definer for selecting an **Execute Button** in the page.

```json
{
  "$variable1": {
    "name": "<variable1>",
    "desc": "A variable that can be to select a execute button in the page",
    "definer": "EXECUTE_BUTTON",
    "definerOptions": {
      "dataType": "STRING"
    },
    "value": "",
    "allowPageParameter": false,
    "preferredPosition": 1
  }
}
```

**Step 1 - Widget Editor**

Access to the Widget Editor:&#x20;

* Select the `configuration.json` resource from the metadata folder--> configuration folder (Resources panel).&#x20;

<figure><img src="../../../../.gitbook/assets/image (1027).png" alt=""><figcaption></figcaption></figure>

* Enter the code in the Code Editor.

```json
{
  "additionalSettings": {
    "groups": {
      "$LAYOUT": {
        "name": "Widget properties",
        "desc": "Contain widget properties",
        "subGroups": {
          "$STYLE": {
            "name": "task",
            "subSets": {
              "$CONTENT": {
                "name": "MyWIDGET",
                "properties": {
                  "$EXECUTE": {
                    "name": "Execute object",
                    "desc": "Allows to to select an execute object in the page",
                    "definer": "EXECUTE_BUTTON"
                  }
                }
              }
            }
          }
        }
      }
    }
  }
}
```

**Step 2 - Page Design**

Access the Page Design:

* Add the widget created in Step 1 and an Execute Button widget on the page. The new property is available in the **Object** tab of the widget properties.
* When the new property **execute object**  is selected, a dialog will open showing the list of Execute Button widgets available in the page.&#x20;
* Select the Execute Button in the page from the Execute object dialog.

<figure><img src="../../../../.gitbook/assets/image (451).png" alt=""><figcaption></figcaption></figure>

## REPORT\_LEVEL

The **REPORT\_LEVEL** definer allow page developer to select one of the execute button widgets available in the page from a dedicated list.

### Example - Definer to select a report's level in Widget Designer

In the following example, we will define in the `configuration.json` the **REPORT\_LEVEL** definer for selecting a report level of one of the reports associated to the widget.

It is possible to define the index with the **reportIndex** optional property. If this property is not specified will be considered the report at index 1.

```json
{
  "$variable2": {
    "name": "<variable2>",
    "desc": "description",
    "definer": "REPORT_LEVEL",
    "definerOptions": {
      "dataType": "LIST",
      "reportIndex": 1
    },
    "preferredPosition": 1
  }
}                        

```

**Step 1 -  Widget Editor**

Access to the Widget Editor:

* Select the `configuration.json` resource from the metadata folder--> configuration folder (Resources panel).&#x20;
* Enter the code in the Code Editor.

```json
{
  "additionalSettings": {
    "groups": {
      "$LAYOUT": {
        "name": "Widget properties",
        "desc": "Contain widget properties",
        "subGroups": {
          "$STYLE": {
            "name": "ReportLevel",
            "subSets": {
              "$REPORT_LEVEL": {
                "name": "Report Level",
                "desc": "Select Report Level",
                "properties": {
                  "$Repor_Level": {
                    "name": "Select Level",
                    "desc": "Select Report Level",
                    "definer": "REPORT_LEVEL",
                    "definerOptions": {
                      "dataType": "LIST",
                      "reportIndex": 1
                    },
                    "value": "",
                    "preferredPosition": 1
                  }
                }
              }
            }
          }
        }
      }
    }
  }
}
```

**Step 2 - Page Design**

Access to the Page Design:

* Add the widget created in Step 1 on the page.
* &#x20;Associate one or more reports with the widget.
* Since the property **reportIndex:** 1 is used in this example, the levels of report number 1 will be considered.
* The new property is available in the **Object** tab of the widget properties.
* When the new property **select Level** is selected, a dialog will open for selecting one or more levels.

<figure><img src="../../../../.gitbook/assets/image (1236).png" alt=""><figcaption></figcaption></figure>
