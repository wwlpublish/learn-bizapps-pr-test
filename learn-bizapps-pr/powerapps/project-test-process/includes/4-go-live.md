The solution architect has a unique role in customer implementations of Power Platform solutions. They are one of the key people responsible for the success of the deployment.

Go-live is the process through which the Power Platform solution becomes operational. This goes beyond turning on the production environment and the deployment of the solution files, it also includes the onboarding of users. If you are migrating from a legacy customer relationship management system, it can include the final production data migration, decommissioning of the old system, and post-deployment support of the new system.

To prepare for a successful project go-live, the solution architect should plan and deliver a Go-live Readiness review. The review can be a meeting or a workshop but the solution architect should prepare a go-live document for review. The review's goal is to evaluate how prepared the customer is for go-live. The Go-live Readiness review should be scheduled and completed before the customer's go-live date ideally with enough time to make any necessary corrections that the review brings to light.

Getting ready for go-live is one of the busiest times of the project, and you should be respectful and understanding of the pressure that the team is probably feeling, and keeps the meeting to its primary purpose. Be prepared to participate in the go, no go decision process criteria, and help guide the customer towards successful criteria to avoid escalations later.

The go-live is one of the most critical milestones during a deployment. The Go-live Readiness meeting  will ensure that the customer is ready for a successful go-live, and won't need to postpone the go-live date due to unforeseen issues, bad strategy, or project risks that were not identified earlier. There are specific activities that happen during this phase of which you'll want to keep track and follow-up proactively with the customer to avoid any surprises. This includes activities such as final user acceptance testing, end-user training, final data migration, installation of apps for Outlook and mobile, and migration of the client configuration to production.

## Navigating to go live

It is rare that there will not be unresolved issues prior to go live. It is the role of the solution architect to work with customer to guide towards a go live decision with outstanding issues.

The solution architect will need to evaluate the impact of fixing an issue prior to go-live or fixing after go-live. The solution architect will need to plan how to resolve outstanding issues during the post go-live support period.

## Common go live problems

Below are common go-live problems:

- No plan for how to roll back if deploy goes wrong.
- Incorrect assumptions about end user workstation or network configurations.
- Not enough real-world testing which can lead to customizations that don’t really meet real users needs or performance issues with real user load.

The solution architect should push to reduce risk of problems with go-live, for example:

- Look for places to streamline and simplify the plan e.g., pre-deploy mobile apps
- Prioritize  data migration, so the important data gets in first.
- Have all users access a dummy production environment so you can workout any access issues before go-live.
- Can you run the old system and new system in parallel and slowly move groups users?

## Automate go-live

The solution architect should consider automating go-live activities to reduce effort and risks. By using automation you can script and test go-live activities before go-live. For instance you can consider automating:

- User, team, and business unit creation.
- Reference data creation and updates.
- User configuration.
- Data migration deltas.

Any automation must be well tested.

## Dealing with problems

The solution architect is often the first call with issues arise with go-live and in the post go-live period. The solution architect will need to proactively triage, isolate, and simplify issues. Often, Power Platform tools can be your best friend to fix problems using its built-in features.

Before you make changes, you should think through both the immediate impact as well as long term impact of any mitigation activities you apply.
