The last step in working with a **Form** control is to submit the edited
or new record information that the user entered. To do this use the
**SubmitForm** function. This function is often placed on a **Button**
control labeled **Save** or **Submit**. The formula for **OnSelect** is
**SubmitForm(YourFormName).**

This function will take all of the data that is entered into the
controls on your data cards and save it to the data source for the
**Form** control. Each data card on your **Form** control has an **Update** property
where the value or formula that will be used to update that field is
specified. If you have unlocked your card, you can modify that formula.
This is often unnecessary and only done in special circumstances.

After you submit your form
--------------------------

The **Form** control is great because with a click of the **SubmitForm**
button your data is whisked away and your data source is updated. The
**Form** control has three properties that process after the data is
submitted based on the outcome of the submission. These properties are
**OnSuccess**, **OnFailure**, and **OnReset**.

For each of these properties, you can enter a formula. For example, if
you want the user to go to a different screen after their data is
submitted successfully, then in **OnSuccess** you would use the function
**Navigate(SuccessScreen, ScreenTransition.Cover)** to send them to the
screen named **SuccessScreen**.

### OnFailure property

Use the **OnFailure** property if there is an error when the data is
submitted. You could use a formula to specify a warning message that
appears when the failure occurs. The following formula is an example of
using the **Notify** function to provide more info to the user.

```
Notify("Your data was not saved. Please try again or contact an administrator.", NotificationType.Error)
```

This function would display a red warning at the top of the screen with
the message "Your data was not saved. Please try again or contact an
administrator." This message makes it easier for the user to resolve the issue.

### OnReset property

Use the **OnReset** property if the form is reset. A form reset occurs
when the **ResetForm** function is used. The **ResetForm** function sets
the form back to its default values and then runs any formula specified
in the **OnReset** property. An example would be if you wanted to reset
a **Variable** or **Timer** control used in conjunction with interacting with
the form.

After your form submits successfully, you can reference the submitted
record directly. The last submitted record is available using the
**LastSubmit** property that contains the entire record. You can access
the record by using the formula **FormName.LastSubmit** assuming your
**Form** control was named **FormName**. You can also access the
individual value by inserting a **Label** control into your app, and
then using the formula **FormName.LastSubmit.ID** to return the
**ID** property of the last record submitted using the **Form** control
named **FormName**. This function is a powerful concept as you
start to build relational data where you need to know the value from a
previous form submission. 
