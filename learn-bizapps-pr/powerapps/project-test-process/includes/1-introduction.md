A Solution Architects work does not end once the system is designed, they must ensure it gets deployed and used by real users.

## Solution Architect’s role with testing and go live

The Solution Architect is typically one of the people who knows best how the solution works and can guide the test team as how to test it.

The solution architect has a key role in testing and should:

- Stay involved until the end of testing to ensure success.
- Help educate the testing team on the solution architecture to ensure they adequately test all components and integrations.
- Triage complex problems that arise during testing, dry runs and after go live.
- Participate with the go live team in planning and executing the go live strategy.

## What is testing

Proper testing is important to help ensure the project's success.

> [!NOTE]
> Testing must be an ongoing effort from the first component built until go live; it cannot be a one-time big exercise.

Testing is more than the process of mapping requirements to functionality. While it's important to build and execute these types of tests, there are many more aspects of a solution that should be tested. Regardless of the specific metric being tested, the process is similar.

![Diagram of test process of plan, prepare, execute, and report.](../media/1-test-process-c.png)

Plan: Review the overall test strategy. Develop the test plan. Perform needed analysis for baseline metrics. Identify key business scenarios that are in, and out of scope. Document the requirements, if not already completed.

Prepare: Set up needed environments, for performance testing, user acceptance testing, and so on. Review data received for migration, both before and after the migration testing. Validate high-level system requirements. Develop needed scripts.

Execute: Execute test scripts. Analyze results, identify potential bottlenecks. Review failures and behaviors.

Report: Prepare a detailed assessment of the reporting plan, results, and plan of action.

## Types of testing

The solution architect should be part of the discussion of the amount and type of testing required for a project.

Common types of tests in the Power Platform:

- Unit Tests: Performed by the app builder, business analyst, functional consultant, or developer.
- Functional Tests: Verify the implementation meets requirements.
- Acceptance Tests: Performed by users to give formal approval.
- Regression Tests: Tests non-changed functions for regression and are typically performed whenever there's a system update.
- Integration Tests: The goal is for all integrated systems to work in harmony. Integration testing verifies that everything works together including integrated third-party services and data.
- Performance Tests: Verify with expected peak load and peak transaction volume and are typically automated and run before go-live.
- Migration Tests: Practice data migration to ensure data quality. Performed in close consultation with subject matter experts that know the customer data. These experts should understand the data transition and transformation and can confirm the migrated data is valid with proper context.
- Disaster Recovery Tests: A Disaster Recovery plan is useless if it doesn’t work!
- Go Live Tests: Dry runs of the complete solution and go live process and are typically performed before go-live.

Not all these types of testing will be required. It will depend on the size and scope of the project.

### Unit testing

A unit test is used to check whether a specific function or feature of your app is working correctly. Unit testing is performed by an app maker or developer. Each team member should check their own work before handing off.

Unit testing is recommended but not required. When you are just getting started or if the amount of code in your solution is relatively small, you may feel that you spend more time writing tests than the functionality included in your solution. The benefits of unit testing begin to accrue when your solution becomes larger and more complex. Particularly with server-side development, there can be significant benefits in debugging locally using mocked or faked data with a testing framework.

Manual testing can be done with all apps, business rules, and plug-ins. Some tests can be automated using the Power Apps Test Studio and Visual Studio. A popular unit test framework for server-side development is Fake Xrm Easy.

The solution architect should decide on the tools used for unit testing and level of automation that should be used.

### Integration testing

The solution architect needs to help the test team understand how to test the integrated components.

One of the strengths of the Power Platform is its strong integration capabilities and integration is one of the most important aspects of the business process implementation to function correctly and has a strong impact on overall adoption.

The solution architect should review with the customer the testing scenarios that involve integrations with other line-of-business applications to ensure that end-to-end testing scenarios are created. This will likely require the customer to plan for an approach to have test environments for their other applications.

Each integration will likely have its own test approach, and it needs to be defined. The testing team should be involved early to look at how they'll test each integration scenario. The teams need to ensure as that the necessary integrations have the ability to be configured to support testing.

A key aspect of integration testing should be focused on the data that flows in and out of the integration. Much of the discussion in the data validation testing section can also apply to the data involved in integrations.

Because integration testing can involve other systems, care must be taken to ensure test environments are used for all components. You don't want integration testing to be talking to a live system-modifying production data by accident. In some cases, this means that the test scenarios drive configuration options in the application integration to make it testable. Having the ability to turn off integrations can help testing without invoking the integration.

Building integrations is now more approachable by a larger number of people on the project teams. Often integrations may become hidden inside of Power Apps canvas applications or Power Automate flows. These can often go unnoticed, because the application is simply using a third-party surface connector. The integration plan should consider these just like any other integration and test them accordingly.

### User acceptance testing

A user acceptance test (UAT) is performed by end users to give formal approval, and they test the usability of the system. Acceptance testing is typically performed as a final check before rolling out functionality. This test is to ensure that what has been built by the makers matches the requirements initially requested by the user.

Here are some tips for getting good results from UAT:

- Test with the real users.
- Try to choose users with diversity in terms of IT skill levels. This way, you can get various feedback.
- Don't give the user instructions; see whether they can understand the app intuitively.
- Observe how they navigate the app without assistance, and see where you can improve the design.
- When the user is stuck on a screen, ask them to explain what their expectation was.
- Try out different devices to make sure the test cases behave the same.
- Ideally, test the app in the user's actual environment or location if the app uses offline capabilities.
- Ask your users to try to "break" your app, such as by entering unusual characters in text fields.
- Users will typically test the "happy path" (the path a user takes when everything is going perfectly); ask them to also test scenarios such as canceling an expense report instead of submitting it, or denying an expense report instead of approving it.

Users might not be familiar with testing software. Let them know what kind of feedback you're looking for. It's often helpful to provide a template for "bugs" to make sure testers explain exactly what they were doing, what happened, what they expected to happen instead, and any relevant information about their testing environment (such as device type and browser).

The solution architect will be required to help triage issues raised by the end users when testing.

### Security testing

Security testing is important to ensure the security of application and the alignment with regulatory requirements. This should include a vulnerability assessment to ensure the application is secure. It should also include testing from the security context of different types of users to ensure that an appropriate level of data and features is available.

Security testing should also look at the security model inside the application for access to data and features of the application. Testing should include scenarios with different users with different roles and access characteristics to ensure that the security model holds up. The security model testing should make sure that over sharing or under sharing isn't happening. One way to approach security model testing is to create a dedicated test user account for each major role set.

The solution architect should help defining the level of security testing to perform.
