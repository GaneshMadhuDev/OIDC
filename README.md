# OIDC
Open ID Connect
OpenID Connect (OIDC) is an identity layer built on top of the OAuth 2.0 framework. It allows third-party applications to verify the identity of the end-user and to obtain basic user profile information. OIDC uses JSON web tokens (JWTs), 


JWTs contain claims, which are statements (such as name or email address) about an entity (typically, the user) and additional metadata. The OpenID Connect specification defines a set of standard claims. The set of standard claims include name, email, gender, birth date, and so on. However, if you want to capture information about a user and there currently isn't a standard claim that best reflects this piece of information, you can create custom claims and add them to your tokens.


While OAuth 2.0 is about resource access and sharing, OIDC is about user authentication. Its purpose is to give you one login for multiple sites. Each time you need to log in to a website using OIDC, you are redirected to your OpenID site where you log in, and then taken back to the website. For example, if you chose to sign in to Auth0 using your Google account then you used OIDC. Once you successfully authenticate with Google and authorize Auth0 to access your information, Google sends information back to Auth0 about the user and the authentication performed. This information is returned in a JWT. You'll receive an access token and if requested, an ID token.

Differences between SAML, OAuth, OpenID Connect

The primary difference between these standards is that OAuth is an authorization framework used to protect specific resources, such as applications or sets of files, while SAML and OIDC are authentication standards used to create secure sign-on experiences. 

Additional differences include:
 

SAML is known for its flexibility, but most developers find OIDC easier to use because it is less complex.

SAML is used to access browser-based applications and does not support SSO for mobile devices or provide API access. OAuth provides API access and OIDC provides access to APIs, mobile native applications, and browser-based applications.

OIDC is about who someone is. OAuth 2.0 is about what they are allowed to do.

SAML uses tokens written in XML and OIDC uses JWTs, which are portable and support a range of signature and encryption algorithms.


How does OIDC work?

OIDC is similar to OAuth where users give one application permission to access data in another application without having to provide their usernames and passwords. Instead, tokens are used to complete both authentication and authorization processes:
 

Identity tokens, intended to be read by the client, prove that users were authenticated and are JSON Web Tokens (JWTs), pronounced “jots.” These files contain information about the user, such as their usernames, when they attempted to sign on to the application or service, and the length of time they are allowed to access the online resources.

Access tokens are used to access protected resources, which are intended to be read and validated by the API. These tokens can be JWTs, but might be in a different format. Their purpose is to inform the API that the bearer of this token has been authorized to access the API and perform specific actions (as specified by the scope that has been granted).

ID tokens cannot be used for API access purposes and access tokens cannot be used for authentication. The following diagram shows how a typical OIDC authentication process works.
