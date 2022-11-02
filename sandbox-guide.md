---
layout: ob-base-toc-page
title: Quick Start Guide 
intro: Try out the Open Banking APIs in the Developer Portal
toc: true
---

This guide walks you through the WSO2 Open Banking Accelerator Sandbox.

## Sign up as an API consumer

- Click here to create an account in the portal as an API Consumer(TPP/Data Recipient).

## Sign up as a bank customer 

- Click here to create an account in the portal as a bank customer.

## Sign in as an API consumer

- Click the **SIGN-IN** button.
- Enter the user credentials for an API Consumer.
- Once you sign in, you can see the published APIs in the **APIs** tab. 
  Given below is a brief explanation of all published APIs.

   - Token API: To generate application access tokens and the user access tokens 
   - Authorize API: To generate HTTPS requests that will authorize the consent prior to obtaining the authorization code 
   - Account and Transaction API: To generate accounts-consents in order to obtain account-related information 
   - Dynamic Client Registration API: To create Dynamic Client Registration (DCR) Applications 
    
## Try out the flow

This section explains how to complete an entire API flow from creating a DCR application to obtaining account 
information using an authorized consent.

### Register an application

If you already have a Client ID of a registered application in the portal, skip this section.

- Go to the **Dynamic Client Registration API**.
- From the left menu pane, select the **Try Out** option.
- Copy the SSA available [here](/attachments/ssa.txt).
- Use the content and generate the payload. <img src="/img/qsg/GeneratePayload.png"/>
- Select the DCR application **POST /register** call. 
- Paste the previously generated payload as the request body. <img src="/img/qsg/DCRPost.png"/>
- Click **Execute**.
- From the response, copy the **Client ID** of the application. You can use the same application
  to try out the flow again.
- Save the Client ID for future use, as you cannot retrieve this value later. 

### Obtain an application access token

- Go to the **Token API**.
- From the left menu pane, select the **Try Out** option.
- Enter the **Client ID** of the application and generate an assertion. <img src="/img/qsg/GenerateAssertion.png"/>
- Select the **POST /v1.0.0** call to obtain the access token.
- Fill in the required fields in the form along with the generated assertion. <img src="/img/qsg/ObtainAccessToken.png"/>
- Set the **grant_type** to **client_credentials** and leave the code input field empty.
- Click **Execute**.
- From the response, copy the **access token** value. This is the application access token.

### Initiate a consent

- Go to the **Account and Transaction API**.
- From the left menu pane, select the **Try Out** option.
- In the **Security** section, enter the application access token obtained in the previous step.
- Select the **POST account-access-consents** call. <img src="/img/qsg/EnterAccessToken.png"/>
- Update the **DateTime** values in the sample payload to future date and time.
  <img src="/img/qsg/CreateAccountsConsent.png"/> 
- Click **Execute**.
- From the response, copy the **Consent ID** value.

### Authorize the consent

- Go to the **Authorize API**.
- From the left menu pane, select the **Try Out** option.
- Fill in the required fields in the form and generate the request object. <br/>
  <img src="/img/qsg/GenerateRequestObject.png"/> <br/>
- Use the **Client ID** of the DCR application created.
- Use the **Consent ID** obtained from the previous step.
- Set the **Scopes** to `accounts openid`.
- Enter the **Redirect URL** value as 

  ```https://is-sandbox-openbanking.wso2.com/ob/authenticationendpoint/auth_code.do```

- Select the **GET** call to obtain the HTTP request to authorize the consent.
- Fill in the required fields in the form along with the request object. 
  <br/> <img src="/img/qsg/ObtainAuthorizationCode.png"/> <br/>
- Click **Execute**. 
- Copy the generated **Request URL** and paste it into a browser.
- Enter the user credentials of the bank customer to authorize the consent.
- As 2FA is enabled, obtain the TOTP from the authenticator application through which the QR code was scanned 
  and saved during the initial login.
- Select the checkboxes of the required accounts and click the **Approve** button.
- Copy the **authorization code** displayed in the UI.

### Obtain a user access token

- Go to the **Token API**. 
- From the left menu pane, select the **Try Out** option.
- Enter the **Client ID** of the application and generate an assertion.
- Select the **POST** call to obtain the access token.
- Fill in the required fields in the form along with the generated assertion.
- Click **Execute**.
- Set the **grant_type** to **authorization_code**. 
- Use the authorization code obtained from the previous step for the **code** input field.
- From the response, copy the **access token** value. This is the user access token.

### Retrieve accounts information

- Go to the **Account and Transaction API**.
- From the left menu pane, select the **Try Out** option. 
- In the **Security** section, enter the user access token obtained in the previous step.
- Select the **Get Accounts** call. 
- Set the **Account Id** to **1**. <img src="/img/qsg/GetAccounts.png"/>
- Click **Execute**.
- The response contains account details.