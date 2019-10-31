## OpenAthens Keystone .NET Core 3.0 MVC Sample
This is a simple example of using OpenID Connect authentication with OpenAthens Keystone in a .NET Core 3.0 MVC web application.

## Getting started
1. Clone the repository: `git clone https://github.com/openathens/keystone-dotnet-core-3-sample`
1. Create a new Application in the OpenAthens [Service Provider dashboard](https://sp.openathens.net/), using:
   * Type: OpenID Connect
   * Application URL `https://localhost:5001` (no trailling '/')
   * Redirect URL `https://localhost:5001/redirect`
1. Update the values in Startup.cs with the Client Id and Client Secret created for the application (you can find them 
on the Configuration tab).
1. If you haven't already done so, create a test personal account in the OpenAthens [Identity Provider dashboard](https://admin.openathens.net/).
1. Run the application and browse to [https://localhost:5001/](https://localhost:5001/)
1. The `Login` link should take you to OpenAthens; log in with your test personal account and it will take you back to
your site.
1. Follow the `User profile` link to view the OpenID Connect claims associated with your personal account. The one of 
most interest is `eduPersonScopedAffiliation` which is in the format `{AFFILIATION}@{SCOPE}`. `{SCOPE}` represents the 
organisation that the user belongs to, and `{AFFILIATION}` is the type of user, which defaults to 'member'. In a real 
world application you would access this claim in a controller to decide whether to grant the user access to the page. 
If you only want some users in an organisation to have access, instead of all, ask them to set up different values of 
`{AFFILIATION}` for different groups of users.
