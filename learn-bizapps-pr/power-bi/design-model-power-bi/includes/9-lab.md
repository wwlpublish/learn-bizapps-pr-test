In this lab, you will create a many-to-many relationship between the **Salesperson** table and the **Sales** table. You will also enforce row-level security to ensure that a salesperson can only analyze sales data for their assigned region(s).

In this lab, you learn how to:

-   Configure many-to-many relationships

-   Enforce row-level security

## Create a many-to-many relationship

In this task, you will create a many-to-many relationship between the **Salesperson** table and the **Sales** table.

Open the **Sales Analysis.pbix** file found in the **D:\DA100\Lab05A\Starter** folder.

1.  In Power BI Desktop, in Report view, in the **Fields** pane, check the follow two fields to create a table visual:

	-   Salesperson | Salesperson
	
	-   Sales | Sales

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the resulting table visual.](../media/lab-2-1-ss.png)](../media/lab-2-1-ss.png#lightbox)

	The table displays sales made by each salesperson. However, there is another relationship between salespeople and sales. Some salespeople belong to one, two, or possibly more sales regions. In addition, sales regions can have multiple salespeople assigned to them.

	> *From a performance management perspective, a salesperson's sales (based on their assigned territories) need to be analyzed and compared with sales targets. In this exercise, you will create relationships to support this analysis.*

1.  Notice that Michael Blythe has sold almost $9 million.

1.  Switch to Model view.

1.  Use the drag-and-drop technique to create the following two model relationships:

	-   **Salesperson | EmployeeKey** to **SalespersonRegion | EmployeeKey**
	
	-   **Region | SalesTerritoryKey** to **SalespersonRegion | SalesTerritoryKey**
	
	The **SalespersonRegion** table can be considered to be a bridging table.

1.  Switch to Report view, and then notice that the visual has not updated---the sales result for Michael Blythe has not changed.

1.  Switch back to Model view, and then follow the relationship filter directions (arrowhead) from the **Salesperson** table.

	Consider this: the **Salesperson** table filters the **Sales** table. It also filters the **SalespersonRegion** table, but it does not continue to propagate to the **Region** table (the arrowhead is pointing the wrong way).

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the relationship between the Region, SalespersonRegion, and Salesperson tables.](../media/lab-2-2-ssm.png)](../media/lab-2-2-ssm.png#lightbox)

1.  To edit the relationship between the **Region** and **SalespersonRegion** tables, double-click the relationship.

1.  In the **Edit Relationship** window, in the **Cross filter direction** dropdown list, select **Both**.

1.  Check the **Apply Security Filter in Both Directions** checkbox.

	This setting will ensure that bi-directional filtering is applied when row-level security is being enforced. You will configure a security role in the next exercise.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of Cross filter direction dropdown list.](../media/lab-2-3-ssm.png)](../media/lab-2-3-ssm.png#lightbox)

1. Click **OK**.

1. Notice that the relationship has a double arrowhead.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of relationship arrow with a double arrowhead visible.](../media/lab-2-4-ssm.png)](../media/lab-2-4-ssm.png#lightbox)

1. Switch to Report view, and then notice that the sales values have not changed.

	> *The issue now relates to the fact that there are two possible filter propagation paths between the **Salesperson** and **Sales** tables. This ambiguity is internally resolved, based on a "least number of tables" assessment. To be clear, you should not design models with this type of ambiguity---it will be addressed in part in this lab, and by the next lab.*

1. Switch to Model view.

1. To force filter propagation via the bridging table, double-click the relationship between the **Salesperson** and **Sales** tables.

1. In the **Edit Relationship** window, uncheck the **Make This Relationship Active** checkbox.

1. Click **OK**.

	> *The filter propagation is now forced to take the only active path.*

1. In the diagram, notice that the inactive relationship is represented by a dashed line.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of a relationship arrow on a dashed line.](../media/lab-2-5-ss.png)](../media/lab-2-5-ss.png#lightbox)

1. Switch to Report view, and then notice that the sales for Michael Blythe is now nearly $22 million.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the updated table visual with Michael Blythe's updated sales.](../media/lab-2-6-ss.png)](../media/lab-2-6-ss.png#lightbox)

1. Notice also, that the sales for each salesperson---if added---would exceed the total.

	> *This observation is a many-to-many relationships, due to the double, triple, etc. counting of regional sales results. Consider Brian Welcker, the second salesperson listed. His sales amount equals the total sales amount. It's the correct result simply due to the fact the he's the Director of Sales; his sales are measured by the sales of all regions.*

	> *While the many-to-many relationship is now working, it's now not possible to analyze sales made by a salesperson (the relationship is inactive).*

1. Switch to Modeling view, and then in the diagram, select the **Salesperson** table.

1. In the **Properties** pane, in the **Name** box, replace the text with **Salesperson (Performance)**.

	> *The renamed table now reflects its purpose: it is used to report and analyze the performance of salespeople based on the sales of their assigned sales regions.*

### Relate the Targets table

In this task, you will create a relationship to the **Targets** table

1. Create a relationship from the **Salesperson (Performance) | EmployeeID** column and the **Targets | EmployeeID** column.

1. In Report view, add the **Targets | Target** field to the table visual.

	Widen the table visual to reveal all data.

1. It's now possible to visualize sales and targets---but take care, for two reasons. First, there is no filter on a time period, and so targets also including future target values. Second, targets are not additive, and so the total should not be displayed. They can either disabled by using a visual formatting property or removed by using calculation logic. You'll write a target measure in **Lab 06B** that will return BLANK when more than one salesperson is filtered.



