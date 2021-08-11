Before developing your production canvas app, try creating a blank test
app or use one of the many great App templates available for free and
play with all the controls. Power Apps has lots of great controls
designed to provide the very best experience for both the maker and the
end user. Controls have a number of different properties that you can modify
to easily enhance the user experience without sacrificing functionality
or performance. As you start to develop your production app, it's very
important to think not only about the purpose of the controls you
incorporate and how they will function but also what action or functionality occurs
when a user interacts with the control.

For example, the **Button** control, when a user selects
the **Button** control, a sequence of actions or behaviors will take
place changing the state of the app. This is done by placing a formula
in the **OnSelect** property of the **Button** control.

- Change the screen that's displayed -
    [**Back**](/powerapps/maker/canvas-apps/functions/function-navigate/?azure-portal=true)
    and
    [**Navigate**](/powerapps/maker/canvas-apps/functions/function-navigate/?azure-portal=true)
    functions.

- Control a
    [signal](/powerapps/maker/canvas-apps/functions/signals/?azure-portal=true) -
    [**Enable**](/powerapps/maker/canvas-apps/functions/function-enable-disable/?azure-portal=true)
    and
    [**Disable**](/powerapps/maker/canvas-apps/functions/function-enable-disable/?azure-portal=true)
    functions.

- Refresh, update, or remove items in a [data
    source](/powerapps/maker/canvas-apps/working-with-data-sources/?azure-portal=true) -
    [**Refresh**](/powerapps/maker/canvas-apps/functions/function-refresh/?azure-portal=true),
    [**Update**](/powerapps/maker/canvas-apps/functions/function-update-updateif/?azure-portal=true),
    [**UpdateIf**](/powerapps/maker/canvas-apps/functions/function-update-updateif/?azure-portal=true),
    [**Patch**](/powerapps/maker/canvas-apps/functions/function-patch/?azure-portal=true),
    [**Remove**](/powerapps/maker/canvas-apps/functions/function-remove-removeif/?azure-portal=true),
    [**RemoveIf**](/powerapps/maker/canvas-apps/functions/function-remove-removeif/?azure-portal=true)
    functions.

- Update a [context
    variable](/powerapps/maker/canvas-apps/working-with-variables?azure-portal=true#use-a-context-variable) -
    [**UpdateContext**](/powerapps/maker/canvas-apps/functions/function-updatecontext/?azure-portal=true)
    function.

- Create, update, or remove items in a
    [collection](/powerapps/maker/canvas-apps/working-with-data-sources?azure-portal=true#collections) -
    [**Collect**](/powerapps/maker/canvas-apps/functions/function-clear-collect-clearcollect/?azure-portal=true),
    [**Clear**](/powerapps/maker/canvas-apps/functions/function-clear-collect-clearcollect/?azure-portal=true),
    [**ClearCollect**](/powerapps/maker/canvas-apps/functions/function-clear-collect-clearcollect/?azure-portal=true)
    functions.

A very simple but popular example of using the **Button** control is
to change screens when the button is selected. This can be accomplished
using the following formula.

```powerappsfl
Navigate(Screen2,ScreenTransition.Cover)
```

![Screenshot of Power Apps Tree view Button control.](../media/navigate-button.png)

In the example above, the **OnSelect** property for the **Button1**
control triggers the **Navigate** function. Now, when a user selects the
button, the other screen will display, Screen2.
