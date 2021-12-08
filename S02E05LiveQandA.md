## 2021-12-07 - Series 2 - Episode 5: Demystifying OAuth, JWTs and Azure AD for Developers - Q&A

During the live session we did a live Q&A spot where attendees could ask questions. If you didn't manage to make it along, here are the ones that came up. We've included answers where possible.

### ❔ Is there a migration guide from ADAL to MSAL for Angular applications?

Microsoft has published a range of migration documentation. The documentation specifically related to JavaScript-based SPAs is available on [Microsoft Docs](https://docs.microsoft.com/azure/active-directory/develop/msal-compare-msal-js-and-adal-js). One of our Australian Microsoft MVPs wrote a guide in 2018 on what's required and why you should make this move. [Check out his blog post](http://johnliu.net/blog/2018/11/migrate-angular-spa-from-adaljs-to-msal-because-it-is-awesome).

### ❔ Is the React SPA wrapped in a .NET app for Azure AD?

The demonstration (Santaweb) showed a simple web application that was calling a REST API. The REST API was built using .NET and is the actual resource being protected by Azure AD. In order for the web application to call the API any user must first authenticate via Azure AD so they have a valid Access Token for the REST API. 

### ❔ I assume we can configure timeout for tokens, however I am not sure if there is a timeout attached to the code to retrieve the token in PKCE flow?

Azure AD currently has (at time of writing) in-preview capabilities around configuration of token timeouts. You can read the documentation on this feature [on the docs](https://docs.microsoft.com/azure/active-directory/develop/active-directory-configurable-token-lifetimes). Also note that some of these capabilities are controlled via Azure AD's Conditional Access capabilities which is also [documented online](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-session-lifetime). Timeouts are controlled at the issuer and aren't affected by the OAuth2 flow (for example the PKCE flow) used. The Microsoft Docs site also has a great quick start project that uses the [auth code flow with PKCE](https://docs.microsoft.com/azure/active-directory/develop/quickstart-v2-javascript-auth-code). 

### ❔ Are app roles available in B2C or are they only available in AAD?

Azure AD B2C (also known as Azure AD External Identities) supports Roles. This is enabled through adding or removing a user from a particular group membership. Group membership is managed the same way as it is for standard Azure AD. Where there is a difference is how groups are issued in claims, which requires you to use [custom policies](https://docs.microsoft.com/azure/active-directory-b2c/tutorial-create-user-flows?pivots=b2c-custom-policy) so that the group membership is issued to the calling client.

### ❔ What is the maximum number of roles a token can support? I believe some tokens can be too large?

In the context of JWTs it is recommended to keep group / role claims to less than 200. If you exceed this number you will receive back an "overage claim" and your application will have to query the Microsoft Graph API 

The IETF Request for Comments ([RFC 7519](https://tools.ietf.org/html/rfc7519)) for JWTs does not specify a maximum size for a JWT. Having said this, you can run into problems if the JWT exceeds limits for HTTP headers for browser-based applications. This typically manifests itself with certain proxy or web servers returning errors to the browser (either 502 or 400 - Request Too Long)

### ❔ How can we use this for "Users" that don't have Microsoft account?

The short answer is 'yes'.

The slightly longer answer is that you have a few choices to enable this capability, but at the most basic level you can invite guest users into your Azure AD tenant and they can be managed much like standard Azure AD accounts. You can read more about adding guest users [on our documentation site](https://docs.microsoft.com/azure/active-directory/external-identities/b2b-quickstart-add-guest-users-portal).

In addition to this business-centric capability we also provide Azure Active Directory External Identities (formerly B2C) which enables people to bring their own social identities to your applications. The behaves differently to inviting guest users and isn't aimed specifically at enabling consumers to use your corporate services, but rather for them to log into your consumer-facing apps (say, for example, your customer banking app). You can find more documentation on this capability [on Microsoft Docs](https://docs.microsoft.com/azure/active-directory-b2c/overview).

### ❔ How did you delete those sessions to logout the user?

During the recorded demonstration, Graeme simply deleted the session cookies his browser was holding which contained the issued tokens for his user session.

### ❔ Tokens over HSTS more secure?

Given the nature of how JWTs are served to clients, and the sensitive data they contain, it is best practices to only provide tokens over TLS/SSL. HTTP Strict Transport Security (HSTS) ensures that servers only provide responses to clients over secured HTTP connections which means using HSTS in your solution helps meet these best practices. HSTS isn't required, but it does help be ensuing the connection is only ever secure.

### ❔ How to configure CORS for logout to fix issue "origin has been blocked by CORS policy" in oidc / msal flow?

Answer coming soon.

### ❔ Is there any sort of 'inheritance' in app roles? eg. How would someone with an 'admin' role get access to endpoints protected with the 'santa' role?

Answer coming soon.

### ❔ In OAuth/OpenID how do we do "Act As" implementation flow across two enterprises B2B?

Answer coming soon.

### ❔ Would you have a different Azure ad application for each environment? Eg if you had prod and uat running from the same Azure ad, would you use one or two applications in Azure ad?

Answer coming soon.

### ❔ Would you have a different Azure ad application for each environment? Eg if you had prod and uat running from the same Azure ad, would you use one or two applications in Azure ad?

Answer coming soon.

### ❔ Does MSAL support implicit flow?

Answer coming soon.

### ❔ How can we use SignalR and function apps to fit into this pattern? Is there any reference links and sample codes?

Answer coming soon.

### ❔ When you add a scope, you specify who can consent. If you select "Admin only" does end users get a popup for consent? What should happen for "Admin only" consent?

Answer coming soon.

### ❔ I have a hosted Blazor application (Wasm) and I have used Azure AD for Authentication. This works as expected. I have also successfully used the Azure AD roles which the client application again works as expected. I am communicating to the server app using gRPC. Can you point me to documentation that shows me how to send Authentication and Authorisation data to the server app, when doing my gRPC calls?

Answer coming soon.