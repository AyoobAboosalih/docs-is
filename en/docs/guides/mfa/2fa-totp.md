# Configure TOTP for 2-Factor Authentication

This page guides you through configuring [two-factor authentication]({{base_path}}/references/concepts/authentication/intro-authentication#two-factor-authentication) for a web application using TOTP (Time-based One-Time Password) as the second factor. 

!!! tip
    For more information, see the [TOTP specification](https://tools.ietf.org/html/rfc6238).

----

## Register a service provider

{!fragments/register-a-service-provider.md!}

## Configure the service provider

1. Expand **Local and Outbound Authentication Configuration**.

2. Click the **Advanced Configuration** radio button. 

3. Add the following authentication steps. 
    - **Step 1**
        1. Click **Add Authentication Step**.

        2. Select `basic` under **Local Authenticators** and click **Add Authenticator** to add the basic authentication as the first step.

            Adding basic authentication as a first step ensures that the first step of authentication will be done using the user's credentials that are configured with the WSO2 Identity Server.

    - **Step 2**
        1. Click **Add Authentication Step**.

        2. Select `totp` under **Local Authenticators** and click **Add Authenticator** to add TOTP authentication as the second step.

            Adding TOTP as a second step adds another layer of authentication and security.
    
         <img name='totp-authentication-steps' src='{{base_path}}/assets/img/guides/totp-authentication-steps.png' class='img-zoomable'/>

4. Click **Update** to save the changes.

You have successfully configured TOTP as the second factor of authentication. 
You can use an application such as the [Google Authenticator Mobile Application](https://play.google.com/store/apps/details?id=com.google.android.apps.authenticator2&hl=en) to generate one time passwords (tokens).

----

## Send emails with TOTP

Optionally, you can set up the users to receive the TOTP code via an email during the authentication flow. You need to 
configure the email adapter for this purpose.

### Configure the email adapter to send emails

{!fragments/configure-email-sending.md!}

!!! tip 
    The email template used to send this email notification is the **TOTP** template.
    You can edit and customize the email template. For more information on how to do this, 
    see [Customize Automated Emails]({{base_path}}/guides/tenants/customize-automated-mails).
    
----

!!! info "Related topics"
    - [Concept: Two-Factor Authentication]({{base_path}}/references/concepts/authentication/intro-authentication/#two-factor-authentication)
    - [Guide: Configure an Authentication Journey]({{base_path}}/configure-authentication-journey)
