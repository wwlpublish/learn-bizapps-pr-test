When using the CALCULATE function, it's possible to pass in filter modification functions. They allow you to do more than simply add filters.

## Remove filters

Use the [REMOVEFILTERS](https://docs.microsoft.com/dax/removefilters-function-dax/?azure-portal=true) DAX function as a CALCULATE filter expression to remove filters from filter context. It can remove filters from one or more columns, or from all columns of a single table.

> [!NOTE]
> The REMOVEFILTERS function is relatively new. In earlier versions of DAX, you removed filters by using the [ALL](https://docs.microsoft.com/dax/all-function-dax/?azure-portal=true) DAX function, or variants including the [ALLEXCEPT](https://docs.microsoft.com/dax/allexcept-function-dax/?azure-portal=true) and the [ALLNOBLANKROW](https://docs.microsoft.com/dax/allnoblankrow-function-dax/?azure-portal=true) DAX functions. These functions behave as both filter modifiers and as functions that return table objects of distinct values. We mention these functions because you're likely to find documentation and formula examples that remove filters by using them.

Let's create a new measure that evaluates the **Revenue** measure but does so by removing any filters from the **Sales Territory** table. Format the measure as currency with two decimal places.

```dax
Revenue Total Region = CALCULATE([Revenue], REMOVEFILTERS('Sales Territory'))
```

Now, add the **Revenue Total Region** measure to the matrix visual found on **Page 2** of the report. The matrix visual groups by three columns from the **Sales Territory** table on the rows: **Group**, **Country**, and **Region**.

> [!div class="mx-imgBorder"]
> [![An image shows a matrix titled Reseller Revenue has Group, Country, and Region grouped on the rows, and Revenue and Revenue Total Region summarizations. The value for Revenue Total Region is the same for each row group.](../media/dax-matrix-sales-territory-revenue-1-ss.png)](../media/dax-matrix-sales-territory-revenue-1-ss.png#lightbox)

Notice that each **Revenue Total Region** value is the same. It's the value of total revenue.

While this result by itself isn't useful, when used as a denominator in a ratio it calculates a percent of grand total. So, let's now overwrite the **Revenue Total Region** measure definition with the following definition. (This new definition changes the measure name. Be sure to format the measure as a percentage with two decimal places.)

```dax
Revenue % Total Region =
VAR CurrentRegionRevenue = [Revenue]
VAR TotalRegionRevenue =
	CALCULATE(
		[Revenue],
		REMOVEFILTERS('Sales Territory')
	)
RETURN
	DIVIDE(
		CurrentRegionRevenue,
		TotalRegionRevenue
	)
```

Verify that the matrix visual now displays the **Revenue % Total Region** values.

> [!div class="mx-imgBorder"]
> [![An image shows a matrix visual titled Reseller Revenue has Group, Country, and Region grouped on the rows, and Revenue and Revenue % Total Region summarizations.](../media/dax-matrix-sales-territory-revenue-2-ss.png)](../media/dax-matrix-sales-territory-revenue-2-ss.png#lightbox)

Let's now create another measure, this time to calculate the ratio of revenue for a region divided by its country's revenue.

But before we do, first notice that the **Revenue % Total Region** value for the Southwest region is 22.95%. Let's investigate the filter context for this cell. Switch to data view, and then in the **Fields** pane, select the **Sales Territory** table. Then, go ahead and apply the following column filters:

- **Group:** North America
- **Country:** United States
- **Region:** Southwest

> [!div class="mx-imgBorder"]
> [![An image shows the Power BI Desktop table filters for the Sales Territory table. Filters are applied to (1) Group = North America, (2) Country = United States, and (3) Region = Southwest.](../media/dax-table-sales-territory-column-filters-ssm.png)](../media/dax-table-sales-territory-column-filters-ssm.png#lightbox)

Notice that the filters reduce the table to just one row. Now, while thinking about our new objective to create a ratio of the region revenue over its country's revenue, clear the filter from the **Region** column.

> [!div class="mx-imgBorder"]
> [![An image shows the column context menu, and the Clear Filters command is highlighted.](../media/dax-sales-territory-table-column-filters-clear-ssm.png)](../media/dax-sales-territory-table-column-filters-clear-ssm.png#lightbox)

Notice that there are now five rows, each belonging to the country United States. So, the lesson here is: When we clear the **Region** column filters, while preserving filters on the **Country** and **Group** columns, we have a new filter context that's for the region's country. Stop and think about it for a moment until it begins to make sense.

In the following measure definition, see how we can clear or remove a filter from a column. In the DAX logic, it's a small and subtle change made to the **Revenue % Total Region** measure formula: The REMOVEFILTERS function now removes filters from the **Sales Territory** table **Region** column, instead of all columns of the **Sales Territory** table.

```dax
Revenue % Total Country =
VAR CurrentRegionRevenue = [Revenue]
VAR TotalCountryRevenue =
	CALCULATE(
		[Revenue],
		REMOVEFILTERS('Sales Territory'[Region])
	)
RETURN
	DIVIDE(
		CurrentRegionRevenue,
		TotalCountryRevenue
	)
```

Add the **Revenue % Total Country** measure, and then format it as a percentage with two decimal places. Then, add the new measure to the matrix visual.

> [!div class="mx-imgBorder"]
> [![An image shows a matrix visual titled Reseller Revenue has Group, Country, and Region grouped on the rows, and Revenue, Revenue % Total Region, and Revenue % Total Country summarizations. Only the Revenue % Total Country values for the United States are not 100%.](../media/dax-matrix-sales-territory-revenue-3-ssm.png)](../media/dax-matrix-sales-territory-revenue-3-ssm.png#lightbox)

Notice that all values, except for those for United States' regions, are 100%. It's because at the Adventure Works company, the United States has regions, while all other countries do not.

> [!NOTE]
> Tabular models don't support ragged hierarchies, which are hierarchies with variable depths. So, it's a common design approach to repeat parent (or other ancestor) values at lower levels of the hierarchy. For example, Australia doesn't have a region, so the country value is repeated as the region name. It's always better to store a meaningful value instead of BLANK.

Let's create one last measure: Add the **Revenue % Total Group** measure, and then format it as a percentage with two decimal places. Then, add the new measure to the matrix visual.

```dax
Revenue % Total Group =
VAR CurrentRegionRevenue = [Revenue]
VAR TotalGroupRevenue =
	CALCULATE(
		[Revenue],
		REMOVEFILTERS(
			'Sales Territory'[Region],
			'Sales Territory'[Country]
		)
	)
RETURN
	DIVIDE(
		CurrentRegionRevenue,
		TotalGroupRevenue
	)
```

> [!div class="mx-imgBorder"]
> [![An image shows a matrix visual titled Reseller Revenue has Group, Country, and Region grouped on the rows, and Revenue, Revenue % Total Region, Revenue % Total Country and Revenue % Total Group summarizations.](../media/dax-matrix-sales-territory-revenue-4-ss.png)](../media/dax-matrix-sales-territory-revenue-4-ss.png#lightbox)

By removing filters from the **Sales Territory** table **Region** and **Country** columns, it calculates the region revenue as a ratio of its group's revenue.

## Preserve filters

You can use the [KEEPFILTERS](https://docs.microsoft.com/dax/keepfilters-function-dax/?azure-portal=true) DAX function as a filter expression in the CALCULATE function to preserve filters. It's more easily explained by an activity.

Switch to **Page 1** of the report. Then, modify the **Revenue Red** measure definition to use the KEEPFILTERS function.

```dax
Revenue Red =
CALCULATE(
	[Revenue],
	KEEPFILTERS('Product'[Color] = "Red")
)
```

> [!div class="mx-imgBorder"]
> [![An images shows a table visual with three columns: Color, Revenue, and Revenue Red. Nine rows and a total are displayed. For Revenue Red, only the Red row and the total aren't BLANK.](../media/dax-table-color-revenue-red-keep-filters-ss.png)](../media/dax-table-color-revenue-red-keep-filters-ss.png#lightbox)

In the table visual, notice that there's now only one **Revenue Red** value. It's because the Boolean filter expression preserves any existing filters on the **Product** table **Color** column. The reason why colors other than red are BLANK is because the two filters filter context and the filter expression are combined. The color black and color red are intersected, and because both cannot be TRUE at the same time, the expression is filtered by no product rows. It's only possible that both red filters can be TRUE at the same time, and it explains why we see just the one **Revenue Red** value.

## Use inactive relationships

An inactive model relationship can only propagate filters when the [USERELATIONSHIP](https://docs.microsoft.com/dax/userelationship-function-dax/?azure-portal=true) DAX function is passed as a filter expression to the CALCULATE function. When you use this function to engage an inactive relationship, the active relationship will automatically become inactive.

Review an example of a measure definition that uses an inactive relationship to calculate the **Revenue** measure by shipped dates:

```dax
Revenue Shipped =
CALCULATE (
	[Revenue],
	USERELATIONSHIP('Date'[DateKey], Sales[ShipDateKey])
)
```

## Modify relationship behavior

It's possible to modify the model relationship behavior when an expression is evaluated. It's done when the [CROSSFILTER](https://docs.microsoft.com/dax/crossfilter-function-dax/?azure-portal=true) DAX function is passed as a filter expression to the CALCULATE function. It's an advanced capability.

The CROSSFILTER function can modify filter directions (from both to single, or from single to both), and even disable a relationship.
