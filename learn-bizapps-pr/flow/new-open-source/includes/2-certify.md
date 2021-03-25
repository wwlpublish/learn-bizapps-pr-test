To make a custom connector available to all users in Logic Apps, Power Automate, and Power Apps as a certified connector, submit your connector to Microsoft for certification. Microsoft will review the connector and, if it meets certification criteria, approve it for publishing. Once published it will join the [full list](https://docs.microsoft.com/connectors/connector-reference/?azure-portal=true) of publicly available connectors.

In the rest of this unit, we're going to look at each step in the certification process. The following are the high-level steps in the journey to certify your connector. These same steps apply to later updates as well, but depending on the scope of the update, can be a lot quicker.

> [!div class="mx-imgBorder"]
> [![Certification process diagram with planning, development, open sourcing, submission, certification, testing, deployment, and support steps.](../media/certification-process.png)](../media/certification-process.png#lightbox)

## Planning

This is where your journey begins as you start envisioning what your connector will look like. Building a connector that others will use should have some planning. Here are a few key planning considerations:

- Identify what triggers and actions will initially be available. You don't need 100% of your API covered but the initial set of triggers and action should be a useful set. If you're too limiting on what you have in your initial version, users will get frustrated that functionality is missing for common scenarios. Consider writing or sketching one or more workflows that can be created in Microsoft Power Automate using your connector. It can help you decide which APIs to include in the connector.

- Evaluate what changes might be needed to the API to support triggers or otherwise improve the ability to deliver a user-friendly connector.

- Consider how authentication will be handled and any adaptation that is necessary between how your API authenticates currently and the supported capabilities of custom connectors.

- If your API uses API keys, consider how users wanting to use the connector will get a key.

- Review connector policy templates to see if implementing any would help the usability of your connector.

- Review the supported OpenAPI extensions for applicability. For example, the test connection is commonly implemented by certified connectors. Also using dynamic value extensions can be helpful if you have parameters with lists of values to choose from.

For new connector certification, you don't have to wait until you finish developing the connector to register for certification. Follow how to register [here](https://docs.microsoft.com/connectors/custom-connectors/submit-certification?azure-portal=true#certification-process). Expect an email from a Microsoft representative to understand your custom connector, learn about your development progress, and guide you through the certification process.

For updates to a certified connector, the most important part of planning is to not break existing users. We'll cover that in more detail in the updates and versioning unit.

## Development

The primary focus in this step is getting your API and the definition for your custom connector ready to submit. Before you proceed to the next step, you should make sure your custom connector definition is cleaned up and has all the proper naming that you want to publish.

## Open-source

In the introduction unit, we covered a high-level overview of how to make an open-source connector. For your certified connector, you will put it in the certified-connectors folder. Prior to submitting a pull request, you must perform the following tasks:

- Edit your connector files to add the [specific required meta data](https://docs.microsoft.com/connectors/custom-connectors/certification-submission?azure-portal=true#publisher-and-stack-owner). Your connector files must contain specific metadata describing the connector and its end service.

- Run the paconn validate command on your downloaded connector and resolve any errors.

To run validation, use the following command:

`paconn validate --api-def [Location of apiDefinition.swagger.json]`

Once you have passed validation, you can submit your pull request to the dev branch of the GitHub repository. This will start an automated process that will do some initial validation of your pull request and make sure that you have a proper contribution agreement in place. Once the automated validation has been completed, it will be assigned to Microsoft for initial review. If they find anything that needs correcting, they will put comments on the pull request, and you are expected to resolve them and resubmit the pull request. Once everything looks good, your pull request will be merged into the repository.

## Submission

The next step is to submit your connector for certification in [ISV Studio](https://isvstudio.powerapps.com/ep/connector/?azure-portal=true) once you've been asked to by your Microsoft contact. ISV Studio is a portal for managing the rest of the certification process and give you the health of your connector once it's deployed.

As part of submitting to ISV Studio for certification you should be prepared to provide the following information:

- Connector testing information, for example, any API key or other authentication details. Any details that would help a tester use the connector.

- An `Intro.md` file that contains info to include in the public documentation for the connector. You can find a template [here](https://docs.microsoft.com/connectors/custom-connectors/certification-submission?azure-portal=true#submitting-to-isv-studio).

As the certification progresses, you will get updates in the portal, and an email to the primary contact. If any issues are encountered, you will be expected to resolve them before the certification will proceed. Once the connector is passed certification that will be scheduled for deployment to the "Preview" region for testing.

## Testing

As part of the certification process your connector is deployed to the "Preview" region for testing. This is your opportunity to make sure the deployed connector works properly before it's deployed to all the regions worldwide. You'll want to test all functionality of your connector in Power Apps, Power Automate, and Logic Apps. You can find detailed instructions on how to get a preview environment and to test your connector [here](https://docs.microsoft.com/connectors/custom-connectors/certification-testing/?azure-portal=true).

## Deployment

After testing is completed, your connector is deployed to all public regions. This process is expected to take seven to 10 business days as we deploy incrementally in our regions around the world. You'll receive notifications as each region is deployed.

## Support

Now that your connector is publicly released you can monitor its performance from ISV Studio. Ensure that your support staff is aware of how your connector might be used with Power Apps or Power Automate so that they can support users experiencing issues.
