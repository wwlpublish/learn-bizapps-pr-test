Now that Microsoft Power BI Desktop is installed, you're ready to connect to the ever-expanding world of data. There are *all sorts* of data sources available in the Microsoft Power Query for Excel window. The following image shows how to connect to data by selecting the **Home** tab on the ribbon and then selecting **Get Data \> More**.

![Get data](../media/TC-DesktopIntro.gif)

In this unit, we'll connect to a couple different **Web** data sources.

Imagine that you're retiring and want to move to a place where there's lots of sunshine, preferable taxes, and good health care. Or perhaps you're a data analyst and want that information so that you can help your customers. For example, you might want to help a sunglasses retailer target sales to areas where the sun shines most often.

Either way, the following web resource has interesting data about those topics, and more:

<http://www.bankrate.com/finance/retirement/best-places-retire-how-state-ranks.aspx>

Select **Get Data \> Web**, and paste the address.

![Connect to web data](../media/pbid-getdata_01.jpg)

When you select **OK**, the **Query** functionality of Power BI Desktop goes to work. Query contacts the web resource, and the **Navigator** window shows what it found on that webpage. In this case, it finds a table (*Table 0*) and the overall web document. We're interested in the table, so select it in the list. The **Navigator** window shows a preview.

![The Navigator window](../media/pbid-getdata_02.jpg)

At this point, you can edit the query before loading the table, by selecting **Edit** at the bottom of the window. Or, you can just load the table.

When you select **Edit**, Power Query Editor starts, and a representative view of the table is shown. The **Query Settings** pane appears (if it doesn't, select the **View** tab on the ribbon, and then select **Show \> Query Settings**). Here's what it looks like.

![Power Query Editor window](../media/pbid-getdata_03.jpg)

In Power BI Desktop, you can connect to multiple data sources and combine them to do interesting things. 

In the next unit, we'll adjust the data to make it meet our needs. The process of adjusting connected data is called *shaping*.