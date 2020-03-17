In the previous module of this learning path, we created a simple, 
two-step linear business process flow. Some business processes are 
simple step-by-step sequential workflows, but many may require branching 
logic requiring one set of stages for one condition, and another set of 
stages for an alternative condition. Think of this as a simple 
*if then else* statement.

Here's a way to conceptualize how logical branching can be used within 
a business process flow. Logical branching requires a decision point 
and a test of a value or condition. If a condition matches a certain value, 
then the flow goes through one branch with one or many stages, if not, 
then the flow goes through another set of one or many stages. Sometimes the two
logical paths will meet at a rendezvous point, and sometimes they will
not. Let's spend some time exploring how you use logical branching with
business process flows.

Branching logic is useful when you are trying to model a business process 
to standardize data collection and improve process outcomes. Logical branching 
enables creation of business process flows that can adapt to different conditions 
within the same flow instead of having to create and launch many
different flows to handle one condition or another. Let's look at an example.

In the scenario we used in the previous module, customers come to our fictitious
company, SmogCheckRUS, for bi-annual smog checks on their vehicles. In
many jurisdictions, there are different requirements for emission
controls standards and equipment based upon the year of the vehicle
manufacture. It would be useful to be able to model all required
tests within a single business process flow. Let's take a look at how we
can accomplish this using logical branching within a business process
flow.

The diagram below models the branching business logic that we need to
build into our flow. Study the diagram and then we will discuss this further.

![Process flow diagram showing a simple if then](../media/1-process-flow-1.png)

In the business process flow logical diagram, you see that the smog
equipment and the checks needed are different for vehicles built before
or during 1971, and after 1971. That means we need to add a logical
branch to check the year of when the vehicle was manufactured, and collect
different information and perform different checks on vehicles built
after 1971. We will discuss how to build a business process flow to
manage this scenario in the module exercises at the end of this module.

Unfortunately, business process flows have some limitations on what can
be modeled using logical branching. Let's examine what types of
logical branching can't be modeled and built in business process flows
today.

### Unsupported logical branching and a possible work-around

Sometimes you will want to model a business process that has multiple
branches, and not all branches end up at the same rendezvous stage. This
is not currently allowed in a business process flow. An example of an
unsupported flow is shown below.

![Example of unsupported branching logic showing vehicle service for a tune-up
versus a smog and a test nested within it for a simple if then else for
cars made in 1971 or before versus cars made after
1971.](../media/2-process-flow-2-bad-branching.png)

Notice the choices that exist around the Vehicle Service decision point.
You can see that two of the branches end up at the Issue or Deny Smog
Certificate stage, and then the Collect Payment stage while
the top branch skips the Issue or Deny Smog Certificate Stage and ends
at the Collect Payment stage. This logical model is NOT supported. All
the stages at a decision point must resolve to the same stage without
intermediate stages for some but not other branches.

The root of the problem above is the logic is not modeled properly. The
decision stage is really modeling two If Then Else conditions and not
one. A better way to model this is to add a second decision point as
shown below. The approach that is shown below is supported because
the decision stages are each testing one condition and all resolve to a
single stage.

![Repaired branching logic diagram showing two sequential branching
logic components with one that tests model year of the vehicle and
another testing the service performed on the
vehicle](../media/3-process-flow-3-repaired-branching.png)

Study this example so you understand how you can add an additional
logical branch and model business process flows correctly.
