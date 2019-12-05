---
layout: ob-base-toc-page
title: Concepts
intro: Learn the core concepts of Open Banking
toc: true
---

# What is Open Banking?

Learn the key concepts behind Open Banking, its stakeholders, and the technologies involved.

## Open Banking

Open banking has been introduced to make banking a more competitive business. Its main goals are offering greater financial transparency, a shared chance of success for all financial service providers, and more innovative services to the consumers. 

The current banking practice involves the customer or merchant to maintain separate relationships with different financial institutions in order to achieve their financial goals. Open banking introduces a more consolidated experience to the customer by allowing banks to expose their functionality via APIs.

## PSD2

PSD2 is the revised Payment Service Directive legislation administered by the European Commission and mandated in 2009. PSD2 requires Europe's banks to give regulated third-party providers (TPPs) access to customers' account information and payment initiation with the customers' permission and consent.

Benefits of PSD2 include:

- Customers can manage their finances using third-party applications. For example, pay your bills using social media accounts.
- More consumer choices and better online and mobile payment methods.
- More opportunities for financial technology companies to introduce new and innovative banking services.
- Enhanced payment security.
- Ability to standardize the payment systems and impose limits on transaction fees to ensure lower costs for the consumers.

### Stakeholders

Following are the categories of stakeholders that actively participate in Open Banking:

- PSU: A Payment Service User (PSU) is a person who makes use of a payment service in the capacity of either a payer, payee, or both. For example a bank customer.

- PSP: A Payment Services Provider is an entity that carries out regulated payment services, including AISPs, PISPs, CBPIIs, and ASPSPs.

- TPP: A Third-Party Provider (TPP) is an authorized third-party that allows merchants to accept a wide variety of payments through a single channel/third-party application, and manage the entire transaction process from start to finish. In this process, the bank continues to be the gatekeeper of the customer's information and requires the third-party to produce a security token in order to access the customer's bank details. 
    
    A TPP can be categorized into the following types: AISP, PISP, and PIISP. The customer's bank can also offer AISP and PISP services.

- AISP: An Account Information Service Provider (AISP) provides an aggregated view of all the accounts and past transactions that a customer has with different banks. To provide this view to the customer, the AISP should have authorization from the customer to view the corresponding transaction and balance information of all the payment accounts. 
   
   The AISPs can also provide the facility to analyze the customer's spending patterns, expenses, and financial needs. Unlike a PISP, an AISP cannot transfer funds from a payment account. The following diagram depicts a generic AISP flow:

   <img src="/img/aisp.png" width="400">

  To view a live demo of the AISP flow of events, see [AISP demo.](https://openbanking.wso2.com/demos/aisp)
- PISP: A Payment Initiation Service Provider (PISP) provides an online service to initiate a payment order at the request of the PSU (a bank customer) with respect to a payment account held at another PSP. To provide this facility PISPs should be authorized by the customer to proceed with the payment. PISPs are responsible for the transaction flow starting from the moment a customer inputs the payment details to the moment the funds appear in the merchant's bank account.

  The following diagram depicts a generic PISP flow:

  <img src="/img/pisp.png" width="400">

  To view a live demo of the PISP flow of events, see [PISP demo.](https://openbanking.wso2.com/demos/pisp)

- ASPSP: An Account Servicing Payment Service Provider (ASPSP) is a PSP that provides and maintains a payment account for a payer. Examples of ASPSPs are banks and credit card issuers. The ASPSPs are obligated to grant access to the account and transaction data on their customers’ payment accounts through APIs.
- PIISP/CBPII: A Payment Instrument Issuer Service Provider (PIISP) is a PSP that verifies the coverage of a given payment amount of the PSU's account. Examples of PIISPs are the banks and credit card issuers that are obligated to verify whether the given payment amount can be covered by the PSU's account through APIs.

    Card Based Payment Instrument Issuer (CBPII) is a PSP (ASPSP/TPP) that issues payment instruments based on cards. Those cards can be used to initiate a payment transaction between an ASPSP and another PSP. 

- Fintech: Fintech is another name for financial technology and is often used to refer to a business that offers new and innovative financial services using software and modern technology.

  Fintechs thrive to offer various financial services like money transfers, payments, and lending in fast and easy ways to keep up with the requirements of the modern-day, tech-savvy, digitally advanced customers. Due to this reason, Fintechs have become quite a competitive challenge to banks that have more rigid, process-oriented structures.

### TPP Onboarding
Third-Party Providers (TPPs) can create third-party applications to facilitate banking services exposed via banking APIs. A TPP can play the role of a PISP/AISP/CBPII or a combination of those roles.

<img src="/img/tpp.png" width="600">

The TPPs are subject to thorough verification before connecting them with the banks/ASPSPs. This verification includes a comprehensive sign-up process at the API Store; the developer portal of WSO2 Open Banking. For a TPP to start providing open banking services, it has to be registered under a Competent Authority, which is a regulatory body that authorizes and supervises the open banking services delivered by the TPP.

### Consent Management
Consent management ensures that the following scenarios take place with the consent of the respective PSU:
- Accessing the PSU's account and transaction data by AISPs
- Processing online payments on behalf of PSUs by PISPs

## Consumer Data Right
The Australian Government introduced the Consumer Data Right (CDR) to give consumers more control over their data. CDR provides customers and small businesses a choice about how their data is shared with third parties and sets standards for a whole industry about what data should be made available, safely. In doing so, CDR encourages competition between service providers, leading to better prices for customers and more innovative products and services.

The CDR will be rolled out sector-by-sector, starting with the banking sector. Further information on the CDR is available on the Treasury website at https://treasury.gov.au/consumer-data-right.

### Consumer Data Standards

The Consumer Data Standards (CDS) are the technical standards produced by Data61, which is the Data Standards Body that provides guidance for the banks/Data Holders on how to implement the CDR. These standards enable consumers to access and direct the sharing of data about them with third parties flexibly and simply, and in ways that ensure security and trust in how that data is being accessed and used.

### Stakeholders

Following are the key actors related to CDR context:

- Consumer: The end-user who is benefited from CDR, the consumer is able to request the Data Holder to provide data.
- Data Holder: The Data Holder (DH) is the organization that CDR is applied to provide data to the consumer. For example, a bank.
- Data Recipient: A Data Recipient (DR) is an accredited party that is able to request CDR data from a Data Holder with the consent of the consumer. 

### Client Registration

Data Recipients (DRs) can create applications to facilitate banking services exposed via Bank APIs. 

The DRs are subject to thorough verification before connecting them with the banks/Data Holders. This verification includes a comprehensive sign-up process at the API Store, the developer portal of WSO2 Open Banking. For a DR to start providing open banking services, it has to be registered under the Australian Competition and Consumer Commission (ACCC).

## APIs

Application Programming Interfaces (API) is a mechanism that enables exposing software functionality without revealing its implementation. APIs enable software applications to interact with each other and exchange data. WSO2 Open Banking supports REST, SOAP, and WebSocket APIs.

### API Resources
An API is made up of one more resources, each of which handles a particular type of request. A resource is defined with a URL pattern and a set of methods that operate on it.

- URL Pattern: The URL pattern can be written in either of the following forms:
  - A URL mapping, for example, /state/town/*
  - A URI template, for example, /{state}/{town}

  The URL mapping performs a one-to-one mapping with the request URL whereas the URI template performs a pattern matching.

  You can parameterize the API resource URL to map the incoming requests to the defined resource template based on the message content and the request URI. Once a URI template is matched, the parameters in the template are populated appropriately.

- Methods: A method is analogous to a method of a function and a resource is analogous to an object instance or a class in the object-oriented programming language. There are a few standard methods that are defined for a resource corresponding to the standard HTTP GET, POST, PUT, and DELETE methods, for example, the PhoneVerifier API has the CheckphoneNumber resource with the GET, POST, PUT, and DELETE methods.

### API Lifecycle
APIs have their own lifecycles that are independent of the backend services they rely on. By default, WSO2 Open Banking maintains six API lifecycle states:

- CREATED: In this stage, the API metadata are added to the API Store but the API is not deployed in the API Gateway. Therefore, the API is not visible in the API Store to subscribers.
- PROTOTYPED: The APIs in this stage are deployed and published in the API Store as prototypes. A prototype API is usually a mock implementation made public in order to get feedback about its usability. Users can invoke the API without a subscription.
- PUBLISHED: These APIs are visible in the API Store and available for subscription.
- DEPRECATED: Deprecated APIs are not available for subscription. But these APIs are still deployed in the API Gateway and are available at runtime to existing subscribers. Existing subscribers can continue to use it as usual until the API is retired.
- RETIRED: These APIs are unpublished from the API Gateway and deleted from the API Store.
- BLOCKED: Access to the API is temporarily blocked. Runtime calls are blocked and the API is not shown in the API Store anymore.

### API Visibility
Visibility settings prevent certain user roles from viewing and modifying APIs created by another user role. You can either make them public or restrict to users with specific user roles. Public APIs are visible to all anonymous (users who use APIs without signing in) and registered users, and can be advertised in multiple stores/developer portals.

### API Documentation
WSO2 Open Banking facilitates adding documentation to APIs. API documentation helps API subscribers to understand the functionality of the API and API publishers to market their APIs better and sustain the competition. Similar to APIs, WSO2 Open Banking enables access control to API documentation.

### API Throttling
Throttling allows you to limit the number of successful hits to an API during a given period of time, typically in cases such as the following:
- To protect your APIs from common types of security attacks such as denial of service (DoS)
- To regulate traffic according to infrastructure availability
- To make an API, application, or a resource available to a consumer at different levels of service

WSO2 Open Banking enables defining throttling at the API, application, and resource levels. The final request limit granted to a given user for a given API is ultimately defined by the consolidated output of all the applicable throttling tiers. The throttling tiers are also referred to as Service-level agreements (SLAs).

### OpenAPI Specification

[OpenAPI](https://swagger.io/docs/specification/about/) (formerly known as Swagger) is a 100% open source, standard, language-agnostic specification and a complete framework for describing, producing, consuming, and visualizing RESTful APIs, without the need of a proxy or third-party services. OpenAPI allows consumers to understand the capabilities of a remote service without accessing its source code, and interact with the service with a minimal amount of implementation logic. OpenAPI describes a service in the same way that interfaces describe lower-level programming code. 

The [Swagger Editor](https://github.com/swagger-api/swagger-editor) is a dependency-free collection of HTML, JavaScript, and CSS that dynamically generate documentation from a Swagger-compliant API. Swagger-compliant APIs give you interactive documentation, client SDK generation, and more discoverability. The Swagger Editor has JSON code and its UI facilitates easier code indentation, keyword highlighting and shows syntax errors on the fly. You can add resource parameters, summaries and descriptions to your APIs using the Swagger Editor.

WSO2 Open Banking API Manager supports [Open API 3.0](https://github.com/OAI/OpenAPI-Specification/blob/master/versions/3.0.0.md) and [Open API 2.0](https://github.com/OAI/OpenAPI-Specification/blob/master/versions/2.0.md) specifications and you can simply create, import, edit and consume the APIs defined in both specifications.

## Applications
An application is an intermediary that sits between an API and its consumer. API consumers use applications to subscribe to APIs and consume them.

<img src="/img/applications.png" width="500">

An API consumer can subscribe to multiple APIs using a single application. Thus, it acts as a logical collection of API subscriptions and decouples the API consumer from the APIs. Each application can be associated with different Service Level Agreement (SLA) levels. This is enabled by attaching an application with throttling tiers that determine the maximum number of API calls allowed during a given duration.

Applications therefore enable:
- Generating and using a single key for multiple APIs
- Subscribing to the same API multiple times with different tiers/Service Level Agreement (SLA) levels
WSO2 Open Banking comes with a pre-created default application, which allows unlimited access by default. You can also create your own applications. 

## Security
Security refers to the means through which computer systems are protected from damage and disruption without being compromised to risks and vulnerabilities. WSO2 Open Banking implements security at the application level and transport level.

- Application-level Security: Application-level security refers to the security requirements at the application level such as encryption, authentication, and authorization.
- Transport-level Security: Transport-level security (TLS) is a mechanism that secures internet and intranet communications. WSO2 Open Banking uses certificates, and keystores to implement transport-level security.

### Encryption
Encryption is the process of translating/encoding data/messages (plaintext) using an algorithm (cipher) into a secret code (ciphertext) that can only be accessed by authorized entities with a secret key or a password.

### User Authentication
Authentication is the process used to distinctly identify a certain entity using the following factors:
- Knowledge factor: This is something the user knows. For example, password, PIN, and security question.
- Possession factor: This is something the user has. For example, ATM card, identity card, mobile phone, and security token.
- Inherence factor: This is something the user is/does. For example, fingerprint and voice pattern.  

Authentication is implemented in either of the following forms:
- Multi-factor Authentication: Multi-factor authentication (MFA) utilizes two or more factors to authenticate an entity.
- Two-factor Authentication: Two-factor authentication (2FA) is a subset of MFA. It utilizes two factors to authenticate an entity.
- Strong Customer Authentication: Strong customer authentication (SCA) is another name for 2FA and MFA. It simply means that two or more elements are used to authenticate a user. These elements are based on the same categories used in MFA: customer's knowledge, possession, and inherence. The idea is that these elements are independent so that the breach of one does not compromise the others.
- Adaptive Authentication: Adaptive authentication allows to adjust the authentication strength based on the context at hand. So, that SCA can be enforced only when it is necessary.
- Federated Authentication: Federated authentication provides a user with access to multiple systems across different enterprises. Subscribers can use the same identification data to gain access to all enterprises in a group at once. 
- Out-of-band Authentication:  Out-of-band authentication (OOB) is an anti-fraud measure that is popular among financial institutions. It triggers an alert through a channel such as a mobile device to the customer when a transaction occurs in his/her account. This alert is typically done through a phone call or a message.

### Authorization
Authorization is the process through which an entity is granted permission to access another entity such as data, resources, and system. In general, authorization takes place subsequent to authentication.

WSO2 Open Banking uses role-based access control (RBAC) and scopes to implement authorization.

### Scopes
Scopes enable fine-grained access control to API resources based on user roles. When a user invokes the API, the user's OAuth2 bearer token cannot grant access to any API resource beyond its associated scopes.

### Access Tokens
An access token is a simple string that is passed as an HTTP header of a request. For example, "Authorization: Bearer NtBQkXoKElu0H1a1fQ0DWfo6IX4a".

WSO2 Open Banking supports two types of access tokens for authentication to ensure better security such as preventing DoS attacks:
- Application access tokens: These tokens identify and authenticate an entire application. Thus, you can invoke all the APIs associated with an application using a single application access token.
- User access tokens: These tokens identify the end user of an application. For example, the end user of a mobile application deployed on a different device.

Access tokens authenticate API users and applications, and ensure better security. If a token that is passed with a request is invalid, the request is discarded in the first stage of processing. Access tokens work equally well for SOAP and REST calls.

### Grant Types
Access tokens grant access to protected API resources. The level of access granted by each access token is determined by the method (known as grant type) used to generate the access token. There are several grant types used in WSO2 Open Banking:

- Authorization Code: This grant type enables obtaining a code using the username and the password. You can generate an access token using this code.
- Client Credential: This grant type enables creating an access token using the client key and client secret.
- Refresh Token: This grant type enables to regenerate an access token once the originally provided access token gets expired.

### Certificates
A certificate (also known as an SSL certificate or digital certificate) is an encryption tool issued by a trusted certification authority (CA) that encrypts data transmitted between a client and a server. Certificates are used for public-key encryption in Public Key Infrastructure (PKI).

In WSO2 Open Banking a TPP must forward a certificate to the ASPSP so that when the TPP sends an application access token request, the ASPSP can verify the authenticity of the request using the shared certificate. A keystore is a repository that contains multiple certificates.