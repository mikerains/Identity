# Identity
OpenId, SAML, IdentityServer

# Identity Server
* https://github.com/IdentityServer

# Identity Server 4
[GitHub Project](https://github.com/IdentityServer/IdentityServer4)

Within IdentityServer4 is a link to Documentation  https://identityserver4.readthedocs.io/en/release/
And within that is a [link to Videos](https://identityserver4.readthedocs.io/en/release/misc/videos.html) that has a great one on[Support for Mobility and Javascript](https://vimeo.com/205451987)

# Kentor
https://github.com/KentorIT/authservices
This has some links on supporting Enterprise Partners with SAML, using Okta as an example external IP.

This is a great article setting up Okta for multiple partners:  https://github.com/KentorIT/authservices/blob/master/doc/IdentityServer3Okta.md

This is a short description of setting up Kentor as OWIN middleware: https://github.com/KentorIT/authservices/blob/master/doc/OwinMiddleware.md
 
# Okta
https://developer.okta.com/

Go to the "Getting Started" to get info on setting up a development Server

# Thinktecture IdentityModel
This is used for ResourceAuthorization
https://github.com/IdentityModel/Thinktecture.IdentityModel

in StartUp.cs.configureAuth(IAppBuilder app), the call to app.UseResourceAuthorization(IResourceAuthorizationManager) registers an IResourceAuthorizationManager that is used in the ResourceAuthorizeAttribute.  It calls a 'CheckAccessAsync' Extension Method on HttpContext or HttpRequestMessage.  These use the OwinContext.GetAuthorizationManager() to retrieve the registered IResourceAuthrizationManager, and call it's CheckAccessAsync.  This is an override that the applicaiton should provide to check the action and resource paramaters against the ClaimsPrinciple claims.  The ClaimsPrinciple is obtain by HttpCOntext.User, or by HttpRequestMessage.GetOwinContext().Authentication.User. 




# Blogs that Are alright
https://www.simple-talk.com/dotnet/asp-net/introducing-single-sign-on-to-an-existing-asp-net-mvc-application/

a decent description of OpenID, OAuth and SAML
https://spin.atomicobject.com/2016/05/30/openid-oauth-saml/

## MSDN - Creating an ASP.Net app with OWIN
https://blogs.msdn.microsoft.com/webdev/2014/03/28/owin-security-components-in-asp-net-openid-connect/

## MSDN - OwinContext
* The IAuthorizationManager: https://msdn.microsoft.com/en-us/library/microsoft.owin.security.iauthenticationmanager(v=vs.113).aspx





