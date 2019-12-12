---
layout: ob-base-toc-page
title: Quick Start Guide 
intro: How developers can simply start consuming secured Open Banking APIs
toc: true
---

## Overview

This guide walks you through the WSO2 Open Banking solution.

If you want to start from scratch by creating your own application, start from [Create an Application](#step-1-create-an-application). If not, start from the [Subscribe to APIs](#step-2-subscribe-to-apis) section where you can use our default application.

<!-- steps menu -->

<!-- step 1 -->
## STEP 1: Create an Application

1. In the main menu, go to **Try Developer Portal > App (Sandbox) - UK**.

    <img src="/img/app-sandbox-uk.png" width="600">

2. If you already have a user account at wso2.com click **Sign in**. Else, click Sign-up to create an account.
    
    <img src="/img/signup.png" width="250">
    - When you create an account, provide a valid phone number with the country code to complete the two factor authentication, for example, +44 xxx xxx xxxx for a UK phone number.
    - Once you create and verify the user account at wso2.com, use those credentials to sign in to WSO2 Open Banking App (Sandbox) - UK.

3. In the left menu, click **Applications** to see all the applications. 
   NOTE: WSO2 Open Banking comes with a sample application named DefaultApplication.
    
    <img src="/img/applicationsTab.png" width="200">

4. Click **Add Application**.

     <img src="/img/addApplication.png" width="200">

    - Enter a name for the application.
    - Set the Throttling Tier.
     
     NOTE: You can select an SLA via the dropdown. By default, this value is set to unlimited. If you do not select an SLA, the default SLA value is applied. 
    - Add a brief description of the application.
     
         <img src="/img/addApplicationDetails.png" width="800">
    - Click **Add**. 

<br/>

<!-- step 2 -->
## STEP 2: Subscribe to APIs

1. In the left menu, click **APIs** to see all available APIs.

     The API store displays all available APIs. These APIs can be consumed by AISPs and PISPs. Some APIs require proper authorisation and consumer consent to provide data. 

     <img src="/img/APIsTab.png" width="200">

2. Select a thumbnail and browse the API.

     <img src="/img/browseAPI.png" width="200">

3. To subscribe to the API:

    - Select the application you created in [STEP 1](#step-1-create-an-application) from the **Applications** drop-down. 
    - Set the **Tiers** accordingly.
    - Click **Subscribe**.

     NOTE: If you did not create your own application, select DefaultApplication.
     
     <img src="/img/subscribeToAPI.png" width="500">

<br/>

<!-- step 3 -->
## STEP 3: Generate Tokens

The APIs are secured using the OAuth2.0 protocol. In order to invoke secured APIs, you should submit a valid OAuth2.0 token with required authorisation levels. Depending on the security requirements, we use the Authorization Code grant type and Client Credentials grant type to generate access tokens.

In this guide, the application directs the consumer to the website of the customer’s bank to perform authentication, delegate authorisation, and get consent for the application to retrieve data or perform a transaction on the consumer’s account.

<hr/>
**Generate keys**

The application requires a Client ID(Consumer Key) and a Client secret(Consumer Secret) to access the subscribed APIs.

1. Go to the **Applications** tab.
    
    <img src="/img/applicationsTab.png" width="200">

2. Choose your application from the Application List and go to the **Sandbox Keys** tab to generate access tokens in the sandbox environment.

3. Provide the requested information as defined below:  
     
     - Grant Types: Determine the credentials used to generate the access token. You may use the selected default Grant Types.

     - Callback URL: The URL used by the application to receive the authorisation code sent from the bank. The authorisation code can be used later to generate an OAuth2 access token.
    
     - Scopes: The access tokens required for accessing the APIs must have relevant scopes. The drop-down contains the scopes available for the APIs, the application has subscribed for.   
             NOTE: An application access token can have multiple scopes.

     - Access token validity period: By default, the token validity periods are set to 3600 seconds. 

     - Application Certificate: To validate whether the TPP is registered in a governing entity. You can download a sample application certificate from [here](/attachments/application-cert.pem). Copy the content between the BEGIN CERTIFICATE and END CERTIFICATE strings of the application certificate.

         <img src="/img/generateKeys.png" width="900">

4. Click **Generate Keys**.

<hr/>
**Create a new consent**

1. In the left menu, click **APIs**.

     <img src="/img/APIsTab.png" width="200">

2. Select an API that the application has subscribed to.

     <img src="/img/browseAPI.png" width="200">

3. Go to the **API Console** tab.

     <img src="/img/APIConsole.png" width="600">

     - Select your application from the drop-down lists.
     - Select Sandbox as the environment. 
     - The request header is set by the API Store.

4. Import this [PKCS12 file](/attachments/cert.p12) to your browser to invoke the endpoints. 

5. Create a consent using the **Try it out** option.
      
      <img src="/img/tryItOut.png" width="600">

    - Modify the request payload with a valid date and time values.
    - Set the **x-fapi-financial-id** parameter value to **open-bank**.
    - Click **Execute** to create a consent resource.










