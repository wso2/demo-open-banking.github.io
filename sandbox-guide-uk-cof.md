## CBPII flow 

<!-- CBPII menu -->

<div class="row cDiagramBox">

<div class="col-sm-12 col-md-12 col-lg-2 cStepContainer">
<a href="#step-1-create-an-application-2">
<span class="cStep" >STEP 1 </span>
<div class="cHighlighted cLightGreyBG cHighlightedReducePadding cBorderBox">
<img src="/img/api-invocation.svg"/>
<span class="cIconTitle" >Create an application</span>
<p>Create an application to consume the banking APIs</p>
</div>
<div class="clearfix"></div>
</a>
</div>

<div class="col-sm-12 col-md-12 col-lg-2 cStepContainer">
<a href="#step-2-subscribe-to-apis-2">
<span class="cStep" >STEP 2 </span>
<div class="cHighlighted cLightGreyBG cHighlightedReducePadding cBorderBox">
<img src="/img/api-invocation.svg"/>
<span class="cIconTitle" >Subscribe to APIs</span>
<p>Subscribe to APIs that can be consumed by TPPs</p>
</div>
<div class="clearfix"></div>
</a>
</div>


<div class="col-sm-12 col-md-12 col-lg-4 cIconSection">
<span class="cIconTitle cSectionTitle" >Generate Token</span>

<div class="row">
<div class="col-sm-12 col-md-12 col-lg-6 cStepContainer">
<a href="#step-3-authentication-2">
<span class="cStep" >STEP 3 </span>
<div class="cHighlighted cLightGreyBG cHighlightedReducePadding cBorderBox">
<img src="/img/api-invocation.svg"/>
<span class="cIconTitle" >Authentication</span>
<p>Authentication by the bank to use the application</p>
</div>
<div class="clearfix"></div>
</a>
</div>

<div class="col-sm-12 col-md-12 col-lg-6 cStepContainer">
<a href="#step-4-authorisation-and-consent-2">
<span class="cStep" >STEP 4 </span>
<div class="cHighlighted cLightGreyBG cHighlightedReducePadding cBorderBox">
<img src="/img/api-invocation.svg"/>
<span class="cIconTitle" >Consent Authorisation</span>
<p>Consent authorisation for a CBPII application</p>
</div>
<div class="clearfix"></div>
</a>
</div>
</div>

</div>


<div class="col-sm-12 col-md-12 col-lg-2 cStepContainer cLast">
<a href="#step-5-consume-apis-2">
<span class="cStep" >STEP 5 </span>
<div class="cHighlighted cLightGreyBG cHighlightedReducePadding cBorderBox">
<img src="/img/api-invocation.svg"/>
<span class="cIconTitle" >Consume APIs</span>
<p>Invoking APIs as a CBPII application</p>
</div>
<div class="clearfix"></div>
</a>
</div>
</div>

<!-- step 1 -->
### STEP 1: Create an Application

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

<!-- step 2 for an AISP -->
### STEP 2: Subscribe to APIs

1. In the left menu, click **APIs** to see all available APIs.

     The API store displays all available APIs. These APIs can be consumed by CBPIIs. Some APIs require proper authorisation and consumer consent to provide data. 

     <img src="/img/APIsTab.png" width="200">

2. Browse the Confirmation Of Funds API.

     <img src="/img/browseConfirmationOfFundsAPI.png" width="200">

3. To subscribe to the API:

    - Select the application you created in [STEP 1](#step-1-create-an-application-2) from the **Applications** drop-down. 
    - Set the **Tiers** accordingly.
    - Click **Subscribe**.

     NOTE: If you did not create your own application, select DefaultApplication.
     
     <img src="/img/subscribeToAPI.png" width="500">

<br/>

<!-- step 3 -->
### STEP 3: Authentication

The APIs are secured using the OAuth2.0 protocol. In order to invoke secured APIs, you should submit a valid OAuth2.0 token with required authorisation levels. Depending on the security requirements, we use the Authorization Code grant type and Client Credentials grant type to generate access tokens.

In this guide, the application directs the consumer to the website of the customer’s bank to perform authentication, delegate authorisation, and get consent for the application to retrieve data or perform a transaction on the consumer’s account.

<hr/>
**Generate keys**

The application requires a Client ID (Consumer Key) and a Client Secret (Consumer Secret) to access the subscribed APIs.

1. Go to the **Applications** tab.
    
    <img src="/img/applicationsTab.png" width="200">

2. Choose your application from the Application List and go to the **Sandbox Keys** tab to generate access tokens in the sandbox environment.

3. Provide the requested information as defined below:  
     
     - Grant Types: Determine the credentials used to generate the access token. You may use the selected default Grant Types.

     - Callback URL: The URL used by the application to receive the authorisation code sent from the bank. The authorisation code can be used later to generate an OAuth2 access token.
    
     - Scopes: The access tokens required for accessing the APIs must have relevant scopes. The drop-down contains the scopes available for the APIs, the application has subscribed for. For a CBPII application, set this value to **fundsconfirmations**.   
             NOTE: An application access token can have multiple scopes.

     - Access token validity period: By default, the token validity periods are set to 3600 seconds. 

     - Application Certificate: To validate whether the TPP is registered in a governing entity. You can download a sample application certificate from [here](/attachments/application-cert.pem). Copy the content between the BEGIN CERTIFICATE and END CERTIFICATE strings of the application certificate.

         <img src="/img/generateKeysCOF.png" width="900">

4. Click **Generate Keys**.

NOTE: Follow the above steps to regenerate the access token.
<br/> 
<hr/>
**Create a new consent**

1. In the left menu, click **APIs**.

     <img src="/img/APIsTab.png" width="200">

2. Browse the Confirmation Of Funds API.

     <img src="/img/browseConfirmationOfFundsAPI.png" width="200">

3. Go to the **API Console** tab.

     <img src="/img/APIConsole.png" width="600">

     - Select your application from the drop-down lists.
     - Select Sandbox as the environment. 
     - The request header is set by the API Store.

4. Mutual Transport Layer Security (MTLS) is a protocol recommended by the Open Banking Implementation Entity. In the WSO2 Open Banking solution, MTLS is enforced by using handlers in order to ensure that the authenticated client uses the pre-registered transport certificate to communicate with APIs.

    - To invoke the APIs in the demo, download the certificate available [here](/attachments/cert.p12) and import it into your web browser. 

5. Create a consent using the **POST /funds-confirmation-consents** resource. Use the **Try it out** option.
      
      <img src="/img/tryOutCOFConsent.png" width="800">

    - Replace the request payload with the sample payload available [here](/attachments/payload-cof-conset.json){:target="_blank"}.
    - Set the **x-fapi-financial-id** value to **open-bank**.
    
6. Click **Execute** to create a consent resource. If the creation is successful, the response body will contain a unique ID for the consent named **ConsentId**.

<br/>
<!-- step 4 -->

### STEP 4: Consent Authorisation

This step explains authorising account consents. The AISP redirects the bank customer to authenticate and approve/deny application-provided consents.

1. In the left menu, click APIs and browse the Authorize API.

      <img src="/img/AuthorizeAPI.png" width="200">

2. Go to the **API Console** tab and click **Generate signed request**.

     <img src="/img/AuthoriszeAPIGenerateJWT.png" width="600">

3. Fill the expanded form.

     - Client ID: The Consumer Key of the application.
     - Scopes: To invoke the Accounts API, set the value as **fundsconfirmation openid**.
     - Redirect URI: The Callback URL of the application.
     - Consent ID: The unique ID of the consent resource created in [STEP 3](#step-3-authentication-2).
     - Use the default values for the State, Nonce, and Response type fields.

4. Click **Generate**.

      NOTE: Once you generate a signed request, you can simply regenerate by clicking **Regenerate**.

5. To obtain an authorization code use the **Try it out** option.

   <img src="/img/TryItOutAuthCode.png" width="600">

    - Copy the **response_type, client_id, scope, redirect_uri, state**, and **nonce** values from the form above.
    - Fill the **request** field with the **Generated token**.

        <img src="/img/GeneratedToken.png" height="50">
        
    - Click **Execute** to generate the **Request URL**.

6. Copy the **Request URL** to a browser. You are redirected to a login page, sign in using the credentials of your WSO2 account.

7. As SMSOTP is configured as the second step of Two-factor authentication, enter the code sent to your mobile phone.

8. Upon successful authentication, the PSU is redirected to the consent management page.

      <!-- <img src="/img/consentMgtPage.png" height="400"> -->

9. PSU needs to select the accounts to which the consent is granted; click **Approve**.

10. The browser is redirected to the redirect URL of the application and an authorization code is generated. Note down the authorization code.

<br>
<hr/>

**Generate user access token**

1. In the left menu, click APIs and browse the Token API.

      <img src="/img/TokenAPI.png" width="200">

2. Go to the **API Console** tab and click **Generate signed request**.

     <img src="/img/TokenAPIGenerateJWT.png" width="600">

3. Fill the expanded form.

     - Client ID: The Consumer Key of the application.

4. Click **Generate**.

      <img src="/img/GeneratedSignedToken.png" width="800">

      NOTE: Once you generate a signed request, you can simply regenerate by clicking **Regenerate**.

5. To obtain an OAuth2 access token use the **Try it out** option.

      <img src="/img/OAuth2AccessTokenTryOut.png" width="800">

      - The value of grant_type field should be **authorization_code**.
      - Set the scope to **accounts**.
      - code is the **authorization code** generated in the above step.
      - redirect_uri should be the Callback URL of the application.
      - client_id is the Consumer Key of the application.
      - Set the client_assertion_type to **urn:ietf:params:oauth:client-assertion-type:jwt-bearer**.
      - client_assertion is the **Generated token** in the Generate client assertion form.

6. Click **Execute**. Note down the user access token in the response.

<br/>

<!-- step 5 -->
### STEP 5: Consume APIs

1. In the left menu, click **APIs**.

2. Browse the Confirmation Of Funds API.

      <img src="/img/browseConfirmationOfFundsAPI.png" width="200">

3. Go to the **API Console** tab.

      <img src="/img/ReplacewithAccessToken.png" width="600"> 
     
     - Select your application from the drop-down lists.
     - Select Sandbox as the environment. 
     - Replace the token in the request header with the **user access token** obtained in [STEP 4](#step-4-authorisation-and-consent-2).

4. Invoke the submission resources using the **Try It Out** option. 

      For example, create a Funds Confirmation resource using the **POST /funds-confirmations** resource.

     - Select the resource and click Try It Out.

       <img src="/img/tryOutCOF.png" width="800">

    - Replace the request payload with the sample payload available [here](/attachments/payload-cof.json){:target="_blank"}.
    Update the value of **ConsentId** with the consent generated in [STEP 3](#step-3-authentication-2). 
    - Set the **x-fapi-financial-id** value to **open-bank**.
    - Click **Execute**.
