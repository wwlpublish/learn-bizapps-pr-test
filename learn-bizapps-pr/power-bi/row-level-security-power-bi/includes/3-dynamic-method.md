You can set up row-level security only once, without the need to continue maintaining it dynamically. 

To continue the scenario with Tailwind Traders, you want Power BI row-level security to only show sales to the user who made them. In this example, Russel King has made four sales. When he views your report, he should only see the sales that he's responsible for and no other sales. You can configure row-level security exactly the way you configured it previously, with only a single change. Instead of creating four roles, you only need to create one role. The DAX filter for that role would look similar to the following image.

> [!div class="mx-imgBorder"]
> [![Dynamic role-level security](../media/03-dynamic-ss.png)](../media/03-dynamic-ss.png#lightbox)

Notice that instead of the fixed string that was previously used, such as **Game** or **Clothing**, a DAX function is being used in the row-level security filter instead. This function, `userprincipalname()`, will compare the email address from the Employees table with the email that the user entered when signing in to Power BI service. If Russel King uses the email address `russel@tailwindtraders.com` to sign in to Power BI service, the system will compare that value to the email address in the Employees table. Assuming that a relationship has been created between Employees and Sales, Russel will only see his four sales.

