The Power Platform has many different security features in environments, in data, and in application deployment. Security is a fundamental component in the design in a Power Platform solution. Too often security requirements are ignored until later on in a project. By including security modeling in designing of the solution, the need for significant change late in a project can be avoided.

> [!IMPORTANT]
> Security must be considered up front and not as an afterthought just before deployment.

The right security strategy balances legitimate security requirements with the need for system access and cross-business collaboration. When implementing Power Platform solutions, the solution architect needs to balance two concerns; user access and system security.

![Balance user access with system security.](../media/1-user-access-system-security.png)

On one hand, data and system security is important. The data drives the business, data that you do not want to fall into the hands of a competitor. With regulations surrounding personal data, organizations can be liable for data breaches that include personal data.

On the other hand, is system usability and user adoption. If the security model is too lax, users can view and change data that they should not be able to access; creating a perception that the data in the system is not reliable. If the security model is too stringent and you lock down everything so users can only see a small subset of the data in the system or can only perform limited operations, you diminish the value the solution, and users will revert to their old data silos and user adoption, the most important aspect of measuring the success of a solution, will suffer.

As a functional consultant or developer, you may not have been exposed to all the security features in the Power Platform. As a solution architect, however, you will need to understand each security feature and when to apply it in different scenarios. This module is a fairly deep dive into all the security aspects of Power Platform solutions and contains important information not found in modules for other roles.

## Security Architecture Process

To define security for a solution, the solution architect needs to break down the requirements and drive towards a clear picture of what the solution needs to look like. The solution architect will need to understand the organization's environment and their requirements around:

- Authentication
- Network Security
- Authorization

### Discovery

Discovery is about learning the organization's environment, procedures, and policies.

The solution architect needs to discover what is currently in use for authentication within the organization:

- Do they have Single Sign-On (SSO)?
- Are they using third-party products or just Azure Active Directory (Azure AD)?
- Do they use multi-factor authentication (MFA)?
- Do they use Conditional Access?

A single Power Platform project is unlikely to change organization authentication approach and the solution architect will need to:

- Map security policies and requirements to the design.
- Create an initial authentication blueprint.
- Review the design with the organization's security representatives.

The solution architect needs to understand how authorization will be applied to the solution and will need to:

- Extract security-related requirements.
- Clarify security requirements for simplification.
- Create an initial authorization blueprint.
- Review with business analysts and security teams.

The solution architect needs to understand how the organization manages security:

- How is security managed?
- What security policies must be followed?
- What is the approval process for security architecture?
- How are application level entitlements managed?
- Which team will edit Power Platform security?
- How are users assigned to applications?

When learning about the user environment, the solution architect also needs to discover:

- How does the organization structure influence security?
- Do people work in teams that cross organization boundaries?
- Is there a data classification system?
- What are the data retention policies?
- What are the privacy policies?
- What data access regulations apply such as GDPR?

## Solution Architect’s role in security modeling

The solution architect leads the efforts to build a comprehensive security model that covers from authentication to data column level access.

The solution architect's role in relation to security consists of:

- Leading the efforts to build a comprehensive security model.
- Being able to communicate the options for security architecture at a high level and help guide the team members through the architecture design choices.
- Being an advocate for simplicity, keeping the security from being overcomplicated while at the same time ensuring necessary protections.

A solution architect also needs to consider if there are any security, regulatory, or compliance requirements that will impact the solution design.

## Security requirements

The security model will be different for each solution, but here is some guidance to consider when modeling security:

- Restrict: Users should only be able to edit data relevant to their role. However, it makes sense to be less restrictive about what data users can read as this helps users see their data in context. A solution architect should remove the ability to delete data unless necessary.
- Simplify: There are many security features in the Power Platform. A solution architect should consider the impact of the security design on how complex the management of the system will be and how difficult it will be to change.
- Use: Often the security requirements that will be provided with come from a position of fear or lack of understanding of the capabilities of the Power Platform. A solution architect should ensure that the security design is based in legitimate business requirements. This may require the solution architect to understand where the security requirements have originated and to discuss alternative approaches. Trying to lock down a Power Platform solution to prevent users from performing actions can be difficult, if not expensive, if the capability to do so is not provided by the platform. The solution architect should use the security capabilities of the platform when designing security for their solution.
- Layer: The Power Platform has security features on apps, data, and processes. Security should ideally be implemented at the platform layer for easier implementation and management.
- Review: The usage of the solution, when implemented, will not be as originally envisaged, and the patterns of usage will evolve over time. Sometimes the initial security design decisions are no longer valid and need to be adjusted.
