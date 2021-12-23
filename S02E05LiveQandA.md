## 2021-12-07 - Series 2 - Episode 5: Demystifying OAuth, JWTs and Azure AD for Developers - Q&A

During the live session we did a live Q&A spot where attendees could ask questions. If you didn't manage to make it along, here are the ones that came up. We've included answers where possible.

### ❔ Is there a migration guide from ADAL to MSAL for Angular applications?

Microsoft has published a range of migration documentation. The documentation specifically related to JavaScript-based SPAs is available on [Microsoft Docs](https://docs.microsoft.com/azure/active-directory/develop/msal-compare-msal-js-and-adal-js). One of our Australian Microsoft MVPs wrote a guide in 2018 on what's required and why you should make this move. [Check out his blog post](http://johnliu.net/blog/2018/11/migrate-angular-spa-from-adaljs-to-msal-because-it-is-awesome).

### ❔ Is the React SPA wrapped in a .NET app for Azure AD?

The demonstration (Santaweb) showed a simple web application that was calling a REST API. The REST API was built using .NET and is the actual resource being protected by Azure AD. In order for the web application to call the API the user must first authenticate via Azure AD so they have a valid Access Token for the REST API. 

### ❔ I assume we can configure timeout for tokens, however I am not sure if there is a timeout attached to the code to retrieve the token in PKCE flow?

Azure AD currently has (at time of writing) in-preview capabilities around configuration of token timeouts. You can read the documentation on this feature [on the docs](https://docs.microsoft.com/azure/active-directory/develop/active-directory-configurable-token-lifetimes). Also note that some of these capabilities are controlled via Azure AD's Conditional Access capabilities which is also [documented online](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-session-lifetime). Timeouts are controlled at the issuer and aren't affected by the OAuth2 flow (for example the PKCE flow) used. The Microsoft Docs site also has a great quick start project that uses the [auth code flow with PKCE](https://docs.microsoft.com/azure/active-directory/develop/quickstart-v2-javascript-auth-code). 

### ❔ Are app roles available in B2C or are they only available in AAD?

Azure AD B2C (also known as Azure AD External Identities) supports Roles. This is enabled through adding or removing a user from a particular group membership. Group membership is managed the same way as it is for standard Azure AD. Where there is a difference is how groups are issued in claims, which requires you to use [custom policies](https://docs.microsoft.com/azure/active-directory-b2c/tutorial-create-user-flows?pivots=b2c-custom-policy) so that the group membership is issued to the calling client.

### ❔ What is the maximum number of roles a token can support? I believe some tokens can be too large?

In the context of JWTs and Azure AD it is recommended to keep group / role claims to less than 200. If you exceed this number you will receive back an "overage claim" and your application will have to query the Microsoft Graph API to determine actual group membership.

The IETF Request for Comments ([RFC 7519](https://tools.ietf.org/html/rfc7519)) for JWTs does not specify a maximum size for a JWT. Having said this, you can run into problems if the JWT exceeds limits for HTTP headers for browser-based applications. This typically manifests itself with certain proxy or web servers returning errors to the browser (either 502 or 400 - Request Too Long). In this case the client may need to clear it's cache and re-authenticate to clear out any invalid or old data.

### ❔ How can we use this for "Users" that don't have Microsoft account?

The short answer is 'yes'.

The slightly longer answer is that you have a few choices to enable this capability, but at the most basic level you can invite guest users into your Azure AD tenant and they can be managed much like standard Azure AD accounts. You can read more about adding guest users [on our documentation site](https://docs.microsoft.com/azure/active-directory/external-identities/b2b-quickstart-add-guest-users-portal).

In addition to this business-centric capability we also provide Azure Active Directory External Identities (formerly B2C) which enables people to bring their own social identities to your applications. The behaves differently to inviting guest users and isn't aimed specifically at enabling consumers to use your corporate services, but rather for them to log into your consumer-facing apps (say, for example, your customer banking app). You can find more documentation on this capability [on Microsoft Docs](https://docs.microsoft.com/azure/active-directory-b2c/overview).

### ❔ How did you delete those sessions to logout the user?

During the recorded demonstration, Graeme simply deleted the session cookies his browser was holding which contained the issued tokens for his user session.

### ❔ Tokens over HSTS more secure?

Given the nature of how JWTs are served to clients, and the sensitive data they contain, it is best practices to only provide tokens over TLS/SSL. HTTP Strict Transport Security (HSTS) ensures that servers only provide responses to clients over secured HTTP connections which means using HSTS in your solution helps meet these best practices. HSTS isn't required, but it does help be ensuing the connection is only ever secure.

### ❔ How to configure CORS for logout to fix issue "origin has been blocked by CORS policy" in OIDC / MSAL flow?

Without understanding your full implementation it's hard to pinpoint the exact fix. CORS errors tend to be manifested in SPA / Angular applications where there is a mismatch between how the Web API is setup verses the Angular codebase. Check that your @azure/msal-angular and web API authentication schemes are configured the same way. You can see a sample of how sign-out works for non-Angular web applications in this sample on GitHub. 

https://github.com/Azure-Samples/active-directory-aspnetcore-webapp-openidconnect-v2/tree/master/1-WebApp-OIDC/1-6-SignOut

### ❔ Is there any sort of 'inheritance' in app roles? eg. How would someone with an 'admin' role get access to endpoints protected with the 'santa' role?

See the earlier answer on maximum roles to understand a bit more about how this works. Users can either be directly assigned to a Role, or a group the user is a part of can be assigned to the Role (this second one tends to be the standard in most large organisations). If we assume that the 'admin' role has not be granted the same rights as the 'santa' role then the only way for someone having just the 'admin' role to have the same access as 'santa' would be for that user (or a group they are in) to be explicitly granted the 'santa' role.

### ❔ In OAuth/OpenID how do we do "Act As" implementation flow across two enterprises B2B?

Azure AD's B2B capabilities are quite deep so it's hard to cover this one question easily. When inviting users from another Azure AD tenant their identity remains in their home tenant and a guest user record is created in your Azure AD tenant. You can control what the guest user is able to do in services associated with your Azure AD tenant, but this does not affect what they are able to do in their home tenant. Items such as MFA and password management are all still controlled via the home tenant for the user.

It's worth [reading up on Azure AD B2B](https://docs.microsoft.com/azure/active-directory/external-identities/what-is-b2b) to understand a bit more of the mechanics of how it works.

### ❔ Would you have a different Azure AD application for each environment? Eg if you had prod and uat running from the same Azure AD, would you use one or two applications in Azure AD?

Yes, register one application in Azure AD per environment. For example: Santaweb-prod, Santaweb-uat.

Having different applications means you can apply changes to non-production environments without accidentally impacting production users.

Many people aren't aware that you can spin up additional Azure AD tenants which you can use for testing or other purposes. It's important to note though, that if you want to use extended capabilities in these alternative environments that you will need to apply the appropriate licenses, even though the basic tier of Azure AD is free to use.

### ❔ Does MSAL support implicit flow?

Yes it does. You can read more about that on [Microsoft Docs](https://docs.microsoft.com/azure/active-directory/develop/v2-oauth2-implicit-grant-flow), along with a link to a sample application.

### ❔ How can we use SignalR and function apps to fit into this pattern? Is there any reference links and sample codes?

OAuth is all about protecting a resource with tokens, so as long as you can authenticate a user and generate a token  and pass this token to a service that understands how to validate it then you can use OAuth anywhere. The best [recent example we've seen](https://brettmckenzie.net/2021/05/06/oauth-2-0-authorization-code-flow-with-azure-functions-and-microsoft-identity-part-1-getting-an-access-token/) relates to Azure Functions and was written by an Australian community member who goes deep into the process.

Microsoft Docs has a [great article on SingalR Service authentication](https://docs.microsoft.com/azure/azure-signalr/signalr-concept-authenticate-oauth) options which includes OAuth.

### ❔ When you add a scope, you specify who can consent. If you select "Admin only" does end users get a popup for consent? What should happen for "Admin only" consent?

The user will be served a screen that advises them that only an administrator can consent and that the user should speak to their local administrator. 

### ❔ I have a hosted Blazor application (WASM) and I have used Azure AD for Authentication. This works as expected. I have also successfully used the Azure AD roles which the client application again works as expected. I am communicating to the server app using gRPC. Can you point me to documentation that shows me how to send Authentication and Authorisation data to the server app, when doing my gRPC calls?

gRPC utilises HTTP/2 as its transport and when you create a gRPC client you can specify the necessary HTTP headers (Authorization in this case) you wish to pass to your server. You would first need to authenticate against Azure AD and obtain an access token which can then be passed to your gRPC client and ultimately the backend API. While this isn't gRPC specific, this example is a good place to start: https://devblogs.microsoft.com/microsoft365dev/how-to-build-a-blazor-web-app-with-azure-active-directory-authentication-and-microsoft-graph/