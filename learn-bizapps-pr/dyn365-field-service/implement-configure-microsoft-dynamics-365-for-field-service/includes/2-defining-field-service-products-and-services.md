 When configuring Dynamics 365 for Field Service, you'll need to define the products and services that will be used and delivered on work orders. Field Service uses the traditional Dynamics 365 product catalog to define products and services. 

After a work order is fulfilled, the products and services involved are indicated on the work order, billed to the customer, and then deducted from inventory.

## Product Setup
When a Field Service solution is installed, an additional tab called **Field Service** appears on the product forms. Here, you'll find details about the product as it relates to Field Service.

Begin setting up your products in Field Service by defining the product type for each product. There are three product types to choose from: 

- **Inventory:** Products whose inventory levels are tracked and deducted from inventory when they are sold. Inventory products might include printers, appliances, windshields, carpet, or televisions.
- **Non-Inventory:** Products that are sold to a customer but are not tracked in inventory. Non-inventory products might include  zip ties or cables, or contract items such as lawn care services which are billed for the same amount each month.
- **Services:** Services that are sold on a time-and-materials basis.
   Examples of services are an oil disposal and recycling fee, a product sanitation fee, or an initial consultation fee.
   All prices and costs associated with services are defined as hourly rates. Services will also have a duration of service associated with them when they are added to work orders. Duration of service can be calculated in one of two ways:
   - **Manual:** The duration is entered by the field agent by using the mobile application.
   -  **Calculated:** The duration will be calculated based on elapsed time between work order schedule statuses.

After defining your product type, configure the following settings:

- **UPC Code:** The Field Service mobile application supports bar code scanning. This field is used to display the UPC code for the product.
- **Convert to Customer Asset:** A customer asset is a physical piece of equipment at a customer location that can have work orders opened against it. This option defines whether or not a specific product can be converted to a customer asset after the work order it is associated with it is closed.
- **Vendor information:** Provides details about the vendor that the product is purchased from. You can define both a default vendor name and a default purchase name for the product.
- **Accounting information:** This includes cost and tax info,  such as the current and standard costs, and whether the product is taxable.

For more info on products and services setup, watch this video.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2KrsV]

## Product and Service Pricing

To ensure you're charging the correct amount for products and services associated with work orders, you must associate each product and service with one or more price lists. Price lists define available pricing levels. You may want to define multiple price lists based on your organization's pricing practices.

To ensure that the most appropriate price list is being used, price lists are noted on the following records:

- Accounts
- Work orders
- Agreements
- Individual product or service records

Price list info will be applied based on these records. For example, a price list could be defined for a work order when it is created. However, if the account has a price list associated with it, the price list associated with the account record will automatically be used for the work order too.

When you are defining a price list item, you have several different pricing options that can be defined to ensure that you are pricing items as they should be. For example, should a product's price be a specific amount, or is the price defined by marking up your cost by 25 percent? Also, if you are working with services, there are additional pricing options available.

The following table defines the different pricing options available for products and services.

 |Pricing Feature           |Products       |Services      |
 |:-------------------------|:-------------:|:------------:|
 | Specific Amount          |      X        |       X      |
 | Minimum Charge Amount    |               |       X      |
 | Minimum Charge Duration  |               |       X      |
 | Flat Fee                 |               |       X      |
 | % of Markup of Price     |               |       X      |
 | % of Markup of Cost      |       X       |       X      |
 | % of Margin of Price     |       X       |       X      |
 | % of Margin of Cost      |       X       |       X      |

### Services Pricing

When adding services to a price list, choose from the following options:

- **Minimum Charge Amount:** Sets the minimum amount a customer will be charged for a visit. The value is added on to the final price regardless of the amount charged.

- **Minimum Charge Duration:** Lets you define the first amount of time as free time. For example, a carpet cleaning service might not charge for the first hour, because it is part of their special offer, but after the first hour the customer is billed at a standard rate.

- **Flat Fee Option:** Specifies a flat fee. For example, every windshield replacement has a windshield disposal fee added to it for proper disposal and recycling of the old windshield.

### Working with Multiple Price Lists

Price lists can be defined in multiple places, such as in a work order or an individual product. It is possible that at times, items will be added that are not on the price list being used by the work order. In those instances, it is important to remember the following:

- A work order's price list is used if a product has a different default price list than the work order.
- The price of the product will come from the list price on the product if an item is not on the work order's price list.

For example, let's say that an organization has two price lists:

- **Standard:** Indicates the standard pricing that is charged to customers.
- **Discounted:** Indicates discounted pricing that is given to customers that have a support contract with your organization.

When a new printer product is added and defined, it must be added as a price list item to both the standard and discounted price lists. Because it will be sold by using standard pricing most of the time, it will have the standard price list defined as its default price list.

Let's say that we need to open a work order for one of our contract customers. They are contract customer, so any work orders created for them will use discounted pricing when available.

When the printer is added to the customer's work order, it will use discounted pricing because the discounted price list is what is being used by the work order, and the printer exists on both the standard and discounted price lists. Even though the standard price list is the default price list for the printer, the product will still use the discounted price list pricing. This ensures that the printer pricing is consistent with all the other items on the work order.

If the printer was not defined as a price list item on the discount price list, the product would use the standard price list pricing. This is because it is the only pricing info that applies to the printer. All other items would use discounted pricing.