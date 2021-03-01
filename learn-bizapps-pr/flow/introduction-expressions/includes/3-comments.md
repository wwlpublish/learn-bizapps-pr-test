When you look at the *convertToUtc* expression you wrote earlier, you might notice that you need to scroll to see the whole formula in the function bar. A common technique to make reviewing your expression easier is to use Comments and pasting the whole formula into the comment.

> [!div class="mx-imgBorder"]
> [![Screenshot of pasting the formula into the comment.](../media/paste-formula-ss.png)](../media/paste-formula-ss.png#lightbox)

To add a comment, select the ellipse to show the menu. Then select "Add a comment".

> [!div class="mx-imgBorder"]
> [![Screenshot of selecting the ellipsis to reveal the the "Add a comment" option.](../media/ellipsis-comment-ssm.png)](../media/ellipsis-comment-ssm.png#lightbox)

Then you can enter any text you want. This could either be text or just a copy and paste of your expression as shown previously.

## Defining text

When you use text in a flow expression, you will use the ' (single quote) at the beginning and end of each string. For example, if you wanted to combine the string "Have a" and "good day!" in an expression, you would use the Concat function and your syntax would be:

```powerappsfl
Concat('Have a', ' good day!')
```

> [!div class="mx-imgBorder"]
> [![Screenshot of the concat function syntax.](../media/concat-function-ss.png)](../media/concat-function-ss.png#lightbox)

These little details will help you more effectively work with expressions. One of the great things about expressions is that they are consistent and as you learn about one function you can often apply those learnings to the next function, rapidly speeding up your learning.
