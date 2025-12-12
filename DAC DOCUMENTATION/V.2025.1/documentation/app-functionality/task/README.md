# 🆕 Task

## Overvew&#x20;

Managing tasks is central to effectively coordinating and monitoring work within the platform. Through tasks, actions can be organized in a structured manner, assigned to individuals or teams, tracked for progress, and collaboration among all parties involved is facilitated.

Each task serves as an operational milestone and can be enriched with detailed descriptions, proposed solutions, priorities, deadlines, and attachments. It is also possible to add comments, mention other users, and link pages or reports, ensuring that each task remains strongly connected

The **Task Board** is the visual space where all tasks are represented according to their status (e.g., _New_, _To Do_, _In Progress_, _Completed_), allowing clear and immediate management of the workflow. Each user can view their own tasks, apply filters, create new tasks quickly, and interact with colleagues

The approach adopted emphasizes transparency, accountability, and collaboration, providing a unified work environment where every

Thanks to these features, the platform supports efficient management of operational activities, making coordination between different roles easier and improving visibility on the overall progress of the work.



## Enabling Tasks for the Organisation

#### How to Enable

To enable the use of Tasks within an organization, it's necessary to correctly configure a property during the installation phase.\
The property in question is:

```yaml
isTaskEnabled
```

By setting this value to `true`, Tasks will be available for the organization. If it is set to `false`, the Task functionality will be disabled.

**Where is the `isTaskEnabled` property located?**\
The property is included among the YAML configuration parameters.

**Can this setting be changed later on?**\
Yes, the value of the property can be updated at a later time if you want to enable or disable the use of Tasks after the initial installation.
