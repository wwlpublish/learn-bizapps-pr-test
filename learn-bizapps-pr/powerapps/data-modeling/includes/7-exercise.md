Review the requirements for each scenario. Decide how best to address the requirement in the data model.

## Scenario: VIP customer management

You have the following set of requirements:

- Track the preferences of the VIP Customer.
- There are three levels of VIP, each have their own benefits, and the requirements to achieve the level.
- Customers can earn VIP for a term by meeting the requirements.
- Each level gets some benefits automatically, and from the optional ones each VIP can select two optional benefits.

What are the main tables required to support this?

Notes:

- A customer can be a person or a company.
- A term is up to a year.

## Scenario: File and Image storage

You have the following further set of requirements:

- You need to store an image of the customer.
- Contract collaboration for special VIPs must include changes and review by internal legal staff.
- VIPs can send PDF of their current competitor status to get matching status.
- Each VIP level has a 20-page benefit guide that is published as a link via e-mail to the current and prospective VIPs.

Where should you use to store this file and image data?

## Exercise: Design a data model

You are building a solution for Fabrikam Robotics to track visitors to a showroom and manufacturing site. Some of the visitors are potential purchasers and some are there to see the magic of the robots working.

- Visitors must have a reserved spot to gain access.
- Visitors invited by sales staff must be tracked to a sales process, visitors just touring for fun are not tracked to a sales process.
- Visitors can bring guests.
- Each visitor must have a photo taken upon arrival and associated with their visit
- Each visitor must sign a waiver of liability each time they visit, and you must store their signature and date time of acceptance.
- Each primary visitor is assigned an engagement tracking device that tracks their location in the manufacturing area and showroom. This is for safety and for improving the tours. The device stores the data in its own cloud service that offers both bulk export and API access.
- You must allow for the tracking data to be viewed in the sales process user interface used by the sales staff
- Marketing has asked to be able to view visitors by day/month/quarter along with statistics on closing of sales after a visit.

### Tasks

Create a data model for the above requirements. Use whatever tool or medium that you have available to complete the data model. You can use a whiteboard, Visio, or pen and paper.

- How did you handle storing of visitor photos?
- How did you handle storing of visitor waiver acceptance and signature?
- How did you accommodate for viewing of tracking data in the sales process?
- Did you use anything from the Common Data Model schema?
- How did you handle marketing’s statistics needs?

If you get stuck, simplify the problem and solve parts of the model.
