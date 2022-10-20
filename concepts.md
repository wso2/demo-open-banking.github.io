---
layout: ob-base-toc-page
title: Open Banking Concepts
intro: Learn the core concepts of Open Banking
toc: true
---

# What is Open Banking?

Open banking is a concept that enables banks, customers, and third parties to use and benefit more from the vast silos 
of data held by banks on their customers. Fundamentally, open banking allows bank customers to share their financial 
data with third parties with their consent. In technical terms, this is done via secure APIs that allow the customers 
or authorised API consumer applications to access data held by the bank.

An open banking accelerator provides the base technology for financial institutions to meet open banking compliance. 
It accelerates open banking adoption by providing the required technology stack to cater to open banking requirements 
so that you don't have to build a solution from scratch. This can accelerate your pathway of reaching defined goals 
in open banking compliance, technology, and business goals.

## WSO2 Open Banking Accelerator

WSO2 Open Banking Accelerator is a collection of technologies that increases the speed and reduces the complexity of 
adopting open banking compliance. Instead of building a solution from scratch, you can use WSO2 Open Banking Accelerator 
to meet all legislative requirements with additional benefits beyond compliance. 

The WSO2 Open Banking Accelerator runs on top of WSO2 Identity Server and WSO2 API Manager.

Use the accelerator capabilities and customize them according to your open banking requirements. You can easily 
implement a toolkit to customize the accelerator and help you comply with any regional open banking standard including
PSD2, Open Banking Standard UK, Berlin Group's NextGenPSD2, Australia's Consumer Data Standard.

For more information, see <a href="https://ob.docs.wso2.com/en/latest/get-started/wso2-open-banking-accelerator">WSO2 
Open Banking Accelerator Documentation</a>.

## Stakeholders

Following are the categories of stakeholders that actively participate in an open banking ecosystem:

* **Customer** - The owner of a bank account who can grant access to the API consumer applications to retrieve
  account information or initiate payments on their behalf. With open banking in the picture, the owner can use a
  single application to manage the accounts and initiate a payment on behalf of them. The customers have more control
  over their data as they can manage and revoke the API consumer applications’ access to the financial information.

* **API consumer application** - An authorized third-party financial service provider that uses standard APIs to
  access customer’s accounts. API consumer applications play several roles such as retrieving account information,
  initiating payments on behalf of the customers, and checking available funds.

* **Financial institution** - An entity such as a bank that provides and maintains a payment account for a customer.
  With customer consent, they share account and transaction data via API endpoints and let API consumer applications
  make payments on behalf of the customer.

* **Merchant** - A vendor who accepts online payments in exchange for their products or services. A merchant can
  use a single API consumer application to accept payments easily from multiple banks. Unless the customer wants to
  make a payment from their bank account, the role of a merchant is not available in all open banking use cases.

There are other stakeholders such as the government, technology providers, and consultancy service providers that
are involved in open banking.

## API Consumer Onboarding

API consumer (TPP or Data Recipient) onboarding is the process of verifying an API consumer when they register
with a bank to provide services to customers. It is important since the API consumer has access to the customer's
financial information via their applications. The accelerator provides dynamic client registration for API consumers.

## Consent Management

Consent management is the process of prompting, collecting, and managing bank customer’s
consent before an API consumer collects or shares the customer's financial information. The accelerator includes a
fully-featured consent management module that:

- securely exposes consent data through an API
- provides in-built consent management user interfaces for customers and bank staff
- manages the entire consent life cycle

## Consumer Authentication

Consumer authentication is an authentication mechanism with a layered defence. When a user initiates a payment or 
accesses information via an API consumer application, it authenticates the user using the following factors one at a time:

- Knowledge : something the user knows. For example: password
- Possession : something the user owns. For example: ATM cards
- Inherence : something the user is. For example: fingerprint

## Developer Portal

WSO2 Open Banking Accelerator offers a customizable Developer Portal that enables application developers to
publish, republish, subscribe, and test APIs.

## Banking Systems Integration

Use the integration capabilities of [WSO2 Micro Integrator](https://apim.docs.wso2.com/en/4.0.0/integrate/integration-overview/)
to help banks connect their core banking systems and overcome the challenges of legacy technology. With the help of
the Micro Integrator, WSO2 Open Banking can support:
- different message protocols (HTTP/TCP), message types (REST/SOAP), and formats (ISO 8583, ISO 20022).
- mediation between a legacy or digital core and other banking systems, and the bank’s library of open banking APIs.

## Reporting and Data Analytics

The accelerator mediates between the bank’s systems and modern analytics systems. Analytics allows
banks to monitor user patterns and behaviours and to identify fraudulent activities. Furthermore, you can generate
reports according to your regulation requirements.

## API Security

API consumers invoke APIs to access customer’s financial information. Therefore, API security plays
a vital role in open banking to mitigate data theft. There is built-in support for global industry-standards
such as OpenID Connect Financial Grade API (FAPI), OAuth 2.0, Electronic Identification and Trust Services (eIDAS).

## User Experience

Provides an enhanced user experience for the banks, API consumers, and customers with
self-explanatory and simple actions.

## Premium APIs and Monetization

Using the capabilities in WSO2 API Manager, WSO2 Open Banking Accelerator allows:
- banks to publish highly-performant custom APIs for API consumers.
- banks to expose their performance and compliance data by integrating into analytics engines.
- banks to plug in any billing engines with subscription-based freemium, tiered pricing, or per-request pricing.

## Standards-based API Templates

WSO2 API Manager offers standard API management capabilities, and you can customize
the API templates according to your open banking and other requirements.
