For DAX beginners, there's often a degree of confusion about calculated columns and measures. Let's review them both, and highlight similarities and differences.

First, let's start with the similarities. They are both:

-   Calculations you can add to your data model.

-   Defined by using a DAX formula.

-   Referenced in DAX formulas by enclosing their name within square brackets.

Now, this is how they differ:

-   **Purpose:** Calculated columns extend a table with a new column, while measures define how to summarize model data.

-   **Evaluation:** Calculated columns are evaluated using *row context* at data refresh time, while measures are evaluated using *filter context* at query time. We'll introduce filter context in a later module. It's an important topic to understand and master so that you can achieve sophisticated summarizations.

-   **Storage:** Calculated columns (in Import storage mode tables) store a value for each row in the table, but a measure never stores values in the model.

-   **Visual use:** Calculated columns (like any column) can be used to filter, group, or summarize (as an implicit measure). But, measures are designed to summarize.