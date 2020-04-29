As you learned in the previous module, when creating formulas, it's best
to combine multiple functions in a single formula when possible. 
Similarly, when implementing controls, the same logic should apply. There is
nothing to stop you from creating a button for every action that you would
like the user to take, but it's far more efficient and effective to
combine them when you can. To combine more than one action in a formula,
use the semicolon (;). 
> [!NOTE]
> Do not use a semicolon if your locale is fr-FR or similar. 

Continuing with the previous example, add an **UpdateContext** function to
the formula.

```powerappsfl
UpdateContext( { x: 1 } ); Navigate(Screen2,ScreenTransition.Cover)
```

> [!NOTE]
> The actions are performed in the order in which they appear
> in the formula. The next function won't start until the previous
> function has completed. If an error occurs, subsequent functions will
> not process. 
