# WorkOS Written Challenge

## Question 1

Email 1: Mark (Product Manager, prospective customer) 

Hi there, I’m setting up SSO for an external service provider we use called SparkNova, and I’m trying to configure WorkOS to act as our Identity Provider (IdP) in the SAML flow. I’ve looked through the docs but wasn’t able to find how to retrieve the IdP metadata XML from WorkOS. Can you point me to the right documentation for using WorkOS as our IdP? 

Thanks, Mark



**My response**

Hi Mark 👋

Thanks for reaching out!

The reason you’re not finding IdP metadata in the WorkOS docs is because WorkOS does not function as an Identity Provider (IdP). WorkOS does not issue IdP metadata or authenticate users to third-party applications.
Instead, WorkOS acts as a middleware layer between your application and your customers’ IdPs (Okta, Google Workspace, Azure AD, etc.) so that your customers can use SSO to log into *your* app via [AuthKit](https://workos.com/docs/authkit/vanilla/nodejs) and/or the [WorkOS SSO API](https://workos.com/docs/sso).

Because of this, WorkOS cannot act as the IdP in a SAML flow for SparkNova. To set up SSO for SparkNova, you would need to configure SAML directly in the IdP your organization already uses (such as Okta, Google, or Azure AD), and then complete the configuration steps in SparkNova’s admin portal or SSO settings page. However, [here is the WorkOS guide to setting up Okta SAML](https://workos.com/docs/integrations/okta-saml), even though this is for WorkOS, you may still find this useful as it shows how to find the IdP metadata via your Okta admin console. 

I hope this helps! Please let me know if you have any further questions.

Happy to help,

Kat Brandt



## Question 2
Email 2: Julia (Software Engineer, current standalone Single Sign-On customer)

Hi! I need a way to pass custom, arbitrary data through the authentication flow - something like an
identifier I can use after the user has authenticated.
Is there a way to include this kind of data in the redirect or auth request? If so, can you show me
how to set it up?

Thanks!
Julia



**My response**

Hi Julia!

Thanks for reaching out. Yes, you can send custom, arbitrary data through the authentication flow. 
You would do this via the `state` field when generating the Authorization URL. 

```ruby
WorkOS::SSO.authorization_url(
  connection: "conn_01E4ZCR3C56J083X43JQXF3JK5",
  client_id: <client_id>,
  redirect_uri: "https://your-app.com/callback",
  state: "dj1kUXc0dzlXZ1hjUQ=="
)
```
In this example, the value of the `state` attribute would persist, exactly as is, and be passed back to your redirect URL, after authentication, allowing you to use it as an identifier or as additional metadata your app requires. 
The redirect URI would then look something like this: 
```
https://your-app.com/callback?code=01E2RJ4C05B52KKZ8FSRDAP23J&state=dj1kUXc0dzlXZ1hjUQ==
```

[Here are the official docs](https://workos.com/docs/reference/sso/get-authorization-url) that show adding the state parameter to your Authorization URL request.

Please let us know if you need any help in implementing this or if you have further questions.

Happy to help!

Kat Brandt
