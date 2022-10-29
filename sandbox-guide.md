---
layout: ob-base-toc-page
title: Quick Start Guide 
intro: Try out the Open Banking APIs in the Developer Portal
toc: true
---

This guide walks you through the WSO2 Open Banking Accelerator Sandbox.

## Sign up as an API consumer

- Click [here](https://accounts.asgardeo.io/t/tpptenentsorg/accountrecoveryendpoint/register.do?client_id=SfDcIpAGUQXCOdZPPX02DTNaeFwa&commonAuthCallerPath=%2Ft%2Ftpptenentsorg%2Foauth2%2Fauthorize&forceAuth=false&passiveAuth=false&redirect_uri=https%3A%2F%2Fsandbox-openbanking.wso2.com%2Fcommonauth&response_type=code&scope=openid&state=2fd29618-b0b6-4db5-8e49-4ecaa549d68e%2COIDC&sessionDataKey=ed9176cb-6d0c-48f9-b8a4-a5e7839fdfd8&relyingParty=SfDcIpAGUQXCOdZPPX02DTNaeFwa&type=oidc&sp=TPP_Login&isSaaSApp=false&authenticators=BasicAuthenticator%3ALOCAL&reCaptcha=true&reCaptchaResend=true&callback=https%3A%2F%2Faccounts.asgardeo.io%3A443%2Ft%2Ftpptenentsorg%2Fauthenticationendpoint%2Flogin.do%3Fclient_id%3DSfDcIpAGUQXCOdZPPX02DTNaeFwa%26commonAuthCallerPath%3D%2Ft%2Ftpptenentsorg%2Foauth2%2Fauthorize%26forceAuth%3Dfalse%26passiveAuth%3Dfalse%26redirect_uri%3Dhttps%3A%2F%2Fsandbox-openbanking.wso2.com%2Fcommonauth%26response_type%3Dcode%26scope%3Dopenid%26state%3D2fd29618-b0b6-4db5-8e49-4ecaa549d68e%2COIDC%26sessionDataKey%3Ded9176cb-6d0c-48f9-b8a4-a5e7839fdfd8%26relyingParty%3DSfDcIpAGUQXCOdZPPX02DTNaeFwa%26type%3Doidc%26sp%3DTPP_Login%26isSaaSApp%3Dfalse%26authenticators%3DBasicAuthenticator%3ALOCAL%26reCaptcha%3Dtrue%26reCaptchaResend%3Dtrue)
  to create an account in the portal as an API Consumer(TPP/Data Recipient).

## Sign up as a bank customer 

- Click [here](https://accounts.asgardeo.io/t/psutenentsorg/accountrecoveryendpoint/register.do?client_id=HVWp3okkzSev2R_gFVAAAg0j2M8a&commonAuthCallerPath=%2Ft%2Fpsutenentsorg%2Foauth2%2Fauthorize&forceAuth=false&passiveAuth=false&redirect_uri=https%3A%2F%2Fis-sandbox-openbanking.wso2.com%2Fcommonauth&response_type=code&scope=openid&state=bb4a29df-e421-423e-bd5b-d85830752c8f%2COIDC&sessionDataKey=5fb2e67e-0870-463a-8ee7-9907a48b24e4&relyingParty=HVWp3okkzSev2R_gFVAAAg0j2M8a&type=oidc&sp=PSU_Login&isSaaSApp=false&authenticators=BasicAuthenticator%3ALOCAL&reCaptcha=true&reCaptchaResend=true&callback=https%3A%2F%2Faccounts.asgardeo.io%3A443%2Ft%2Fpsutenentsorg%2Fauthenticationendpoint%2Flogin.do%3Fclient_id%3DHVWp3okkzSev2R_gFVAAAg0j2M8a%26commonAuthCallerPath%3D%2Ft%2Fpsutenentsorg%2Foauth2%2Fauthorize%26forceAuth%3Dfalse%26passiveAuth%3Dfalse%26redirect_uri%3Dhttps%3A%2F%2Fis-sandbox-openbanking.wso2.com%2Fcommonauth%26response_type%3Dcode%26scope%3Dopenid%26state%3Dbb4a29df-e421-423e-bd5b-d85830752c8f%2COIDC%26sessionDataKey%3D5fb2e67e-0870-463a-8ee7-9907a48b24e4%26relyingParty%3DHVWp3okkzSev2R_gFVAAAg0j2M8a%26type%3Doidc%26sp%3DPSU_Login%26isSaaSApp%3Dfalse%26authenticators%3DBasicAuthenticator%3ALOCAL%26reCaptcha%3Dtrue%26reCaptchaResend%3Dtrue)
  to create an account in the portal as a bank customer.

## Sign in as an API consumer

- Click the **SIGN-IN** button.
- Enter the user credentials for an API Consumer.
- Once you sign in, you can see the published APIs in the **APIs** tab. 
  Given below is a brief explanation of all published APIs.

   - Token API: To generate application access tokens and the user access tokens 
   - Authorize API: To generate HTTPS requests that will authorize the consent prior to obtaining the authorization code 
   - Account and Transaction API: To generate accounts-consents in order to obtain account-related information 
   - CDR Dynamic Client Registration API: To create Dynamic Client Registration (DCR) Applications 
    
## Try out the flow

This section explains how to complete an entire API flow from creating a DCR application to obtaining account 
information using an authorized consent.

### Register an application

- Go to the **CDR-Dynamic Client Registration API**.
- From the left menu pane, select the **Try Out** option.
- Copy the SSA available [here](/attachments/ssa.txt).
- Use the content and generate the payload. <img src="/img/qsg/GeneratePayload.png"/>
- Select the DCR application **POST /register** call. 
- Paste the previously generated payload as the request body. <img src="/img/qsg/DCRPost.png"/>
- Click **Execute**.
- From the response, copy the **Client ID** of the application.
- If you already have a Client ID of a registered application in the portal, skip the steps above.

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
- In the **Security** section, enter the access token obtained in the previous step.
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
- In the **Security** section, enter the access token obtained in the previous step.
- Select the **Get Accounts** call. 
- Set the **Account Id** to **1**. <img src="/img/qsg/GetAccounts.png"/>
- Click **Execute**.
- The response contains account details.