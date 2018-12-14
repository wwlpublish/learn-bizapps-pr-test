As we mentioned at the beginning of this module, service level agreements (SLAs) aren't customer-specific. They're defined at the organization level and applied to cases. Out of the box, the case record doesn't have a lookup field to the SLA entity. Therefore, an SLA isn't applied to a case unless it's set at the default SLA for your organization or associated with an entitlement.

The following table explains how SLAs are applied when a new case is created.

<table>
<thead>
<tr>
<th>Scenario</th>
<th>Applicable SLA</th>
</tr>
</thead>
<tbody>
<tr>
<td>A case is created, but no entitlement is associated with it.</td>
<td>
<ul>
<li>If the organization has a default SLA, it's applied to the case.</li>
<li>If the organization doesn't have a default SLA, no SLA is applied to the case.</li>
</ul>
</td>
</tr>
<tr>
<td>A case is created, and an entitlement is associated with it.</td>
<td>
<ul>
<li>If the entitlement has an active associated SLA, the associated SLA is applied to the case.</li>
<li>If the entitlement doesn't have an active associated SLA, but the organization has a default SLA, the default SLA is applied to the case.</li>
<li>If the entitlement doesn't have an active associated SLA, and the organization doesn't have a default SLA, no SLA is applied to the case.</li>
</ul>
</td>
</tr>
</tbody>
</table>

For more about how SLAs are applied, see [How is the SLA applied?](https://docs.microsoft.com/dynamics365/customer-engagement/customer-service/define-service-level-agreements#how-is-the-sla-applied)

For more about applying SLAs on demand, see [Apply SLA on demand](https://docs.microsoft.com/dynamics365/customer-engagement/customer-service/define-service-level-agreements#apply-sla-on-demand).

An SLA can't be set as the default SLA for an organization until it's activated. An organization can have only one default SLA. If you set another SLA as the default SLA, you override the previous default SLA. If you need to temporarily inactivate the default SLA for any reason, you must set it as the default SLA again after it's reactivated.

SLAs must be inactivated any time you want to make changes. When you inactivate an SLA, all entitlements that are associated with it remain active. While an SLA is inactive, no SLA fields on cases that are linked to the inactive SLA will be updated.

For more about inactivating SLAs, see [Disable the SLA](https://docs.microsoft.com/dynamics365/customer-engagement/customer-service/define-service-level-agreements#disable-the-sla).

For more about setting default SLAs, see [Set the SLA as default](https://docs.microsoft.com/dynamics365/customer-engagement/customer-service/define-service-level-agreements#set-the-sla-as-default).

## Pausing and resuming SLAs

Let's say that you're working on a case with a customer, and you need some specific information from that customer. While you're waiting for the customer to get back to you, you might have to pause the calculation time on the SLA, so that the time that you spend waiting doesn't affect the SLA calculation time. For example, a customer has been promised a two-hour response time. After you've been working with the customer on a case for 30 minutes, you put the case into *Waiting for details* status for 45 minutes. When the timer is resumed, only 30 minutes will count toward the SLA calculation.

When you create an enhanced SLA, you can define pause and resume statuses for a specific SLA. You can then place a case on hold. To set up specific statuses for paused cases, go to **Settings** \> **Service Management**, and then, in the **Service Terms** section, select **Service Configuration Settings**. Here, you can specify whether your organization uses the SLA functionality. You can also define the statuses that will be considered pause statuses for each entity that's set up to be used with SLAs. For example, for the Case entity, you might define *On hold* and *Waiting for details* as the pause statuses. After you've set up those statuses, the SLA timer will automatically be paused any time one of them is selected.

For more about setting up pause and resume statuses, see [System Settings dialog box - Service tab](https://docs.microsoft.com/dynamics365/customer-engagement/admin/system-settings-dialog-box-service-tab).

## Timer control

From the form customization page, you can add a timer control to any entity to provide countdown information for any KPI that's defined on that entity. When a timer control is added, you can set the following information:

- **Failure Time Field:** Define the date/time-based field that should be used to calculate success or failure (for example, the **Created On** field). (Required)
- **Success Condition:** Define the field and field value that determine successful resolution (for example, a setting of *Yes* for the **First Response Sent** option). (Required)
- **Failure Condition:** Define the field and field value that determine failure for the time (for example, a setting of *No* for the **First Response Sent** option).
- **Warning Condition:** Define the field and field value that determine when a warning should be triggered.
- **Cancel Condition:** Define the field and field value that determine when the timer should be canceled (for example, a value of *Resolved* for the **Status Reason** field).
- **Pause Condition:** Define the field and field value that determine when the timer should be canceled (for example, a value of *Waiting for Details* for the **Status Reason** field).

You can add and define timer controls any time you need countdown capabilities. The timer will change color to reflect the different statuses. For example, it might change from green to yellow for warnings or red for failures.

For more about working with the timer control, see [Add a timer control to the Case form to track time against an SLA](https://docs.microsoft.com/dynamics365/customer-engagement/customer-service/add-timer-control-case-form-track-time-against-sla).
