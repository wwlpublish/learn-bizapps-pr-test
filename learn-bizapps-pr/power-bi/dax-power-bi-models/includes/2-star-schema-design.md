It's unusual that a Power BI data model comprises a single table. A single-table model can either a very simple design, perhaps suitable for a data exploration task or proof of concept, or, it's possibly not an optimal model design. An optimal model design adheres to *Star Schema* design principles. Star Schema refers to a design approach commonly used by relational data warehouse designers because it presents an easy-to-understand structure to your users, and it supports high-performance analytic queries. We'll define analytic queries in the next unit.

It's called a star schema because it classifies model tables as either *fact* or *dimension*. In a diagram, a fact table forms the center of a star, while dimension tables, when placed around a fact table, represent the points of the star.

## Fact tables

The role of a fact table is to store an accumulation of rows that represent observations or events recording a specific business activity. For example, events stored in a sales fact table could be sales orders and the order lines. You could also use a fact table to record stock movements, stock balances, or daily currency exchange rates. Generally, fact tables contain a large number of rows. As time passes, fact table rows accumulate. In analytic queries, which we define in the next unit, fact table data is summarized to produces values like sales and quantity.

## Dimension tables

Dimension tables describe your business entities, which commonly represent people, places, product, or concepts. A date dimension table, which contains one row per date, is a very common example of a concept dimension table. The columns in dimension tables allow filtering and grouping of fact table data.

Each dimension table must have a unique column, which is referred to as its key column. A unique column doesn't contain duplicate values and it should never have missing values. In a product dimension table, it could be named the **ProductKey** column or **ProductID** column. There are likely to be additional columns that store descriptive values, like the product name, subcategory, category, color, and so on. In analytic queries, these columns are used to filter and group data.

## Compare fact and dimension tables

Let's now compare characteristics of fact and dimension tables:

|                        |     Dimension table                                                                 |     Fact table                                                                               |
|------------------------|-------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------|
|     Model purpose      |     Store business   entities                                                       |     Store events or observations                                                             |
|     Table structure    |     Includes a key column, and   descriptive columns for filtering and grouping.    |     Includes dimension key columns,   and numeric measure columns that can be summarized.    |
|     Data volume        |     Typically, contains a   small number of rows (relative to fact tables)          |     Can contain very large   number of rows                                                  |
|     Query purpose      |     To filter and group                                                             |     To summarize                                                                             |

## Relate star schema tables

In the model, dimension tables are related to fact tables by using one-to-many relationships. The relationships allow filters and groups applied to dimension table columns to propagate to the fact table. This is a very common design pattern.

Dimension tables can be used to filter multiple fact tables, and fact tables can be filtered by multiple dimension tables. However, it's not a good practice to relate a fact table directly to another fact table.

Take a look for yourself. First, download the **Adventure Works DW 2020 M01.pbix** file, and then open the file and switch to the model diagram.

> [!div class="mx-imgBorder"]
> [![An image shows seven model tables. The Sales table is located at the center of the diagram. The other six tables are placed about the Sales table.](../media/dax-star-schema-1-ss.png)](../media/dax-star-schema-1-ss.png#lightbox)

Notice that the model comprises seven tables. There's one fact table, which is named **Sales**. The remaining tables are dimension tables, and they have the following names:

-   Customer

-   Date

-   Product

-   Reseller

-   Sales Order

-   Sales Territory

Notice the relationships between the dimension and fact tables, and that each relationship filter direction is pointing toward the fact table. This way, when filters are applied to dimension table columns (to filter or group by column values), related facts are filtered and summarized.

Look more closely and you might see an actual star!

> [!div class="mx-imgBorder"]
> [![An image shows a star superimposed over the seven model tables. The star assists understanding the star schema design.](../media/dax-star-schema-2-ssm.png)](../media/dax-star-schema-2-ssm.png#lightbox)

For more information on star schemas, see [Understand star schema and the importance for Power BI](https://docs.microsoft.com/power-bi/guidance/star-schema/?azure-portal=true).
