# Introduction 

Welcome to the Flow Finance API, which allows platforms to quickly and programatically issue loans to their users.

We strived to make the API easy to used and hope you find it so. 

If you have any suggestions on how we can make it even easier, feel free to get in touch.

## Overview

A brief, high-level overview of how to use the API

* Your platform and products will be registered, and you will receive an API token.
* Using the API token you can start creating Accounts for your users.
* (Optional) You can use our Prequalify endpoint to check if your user might be ineligible for an Account before registration.
* Create Accounts for your users, that consists of Person and/or Business entities, according to your product.
* Upload the necessary documents for KYC proccess.
* Get your user's acceptance on our Terms of Service.
* The Account will then go through our internal analysis.
* After approval, a credit line will be made available to the account. 
* Using the Loan Preview endpoint you can show offers to your users, according to the product specified.
* Each Loan Preview is associated with an offer-token.
* Submit an offer-token to the Loan endpoint to create a Loan.
* With a Loan created, you can show the contract to your user and get his acceptance (digital signature). 
* Submit the user's signature and the Loan will then be issued.


## Getting started

<aside class="notice">
Contact our sales team in order to register your platform and get an API token.
You will then be assigned an Integration Engineer who will guide you through the integration process.

Please note that this process is not set in stone, so we can always skip a step or work in parallel.
</aside>

### Onboarding

#### Transactional Data Samples
In this step, you provide us with platform transactional data samples, which will be used by our data science team to train our algorithms.

#### Real Transactional Data
We will also need your platform API endpoint that will be used for retrieving transactional data. It must be capable of being queried by business id (cnpj/cpf). This allows us to perform real-time credit decisions.

We understand that providing an external API endpoint may not be an option for your platform, so we also provide 2 alternatives:
* You can attach the relevant data on every request where transactional data is needed 
* You can send us your transactional data and we will process everything offline.

#### API Walkthrough
With the samples processed and an accessible api endpoint, we will schedule an API walkthrough where your assigned engineer will give you an overview of the Flow API, tailored to your platform, and explain relevant API calls and the suggested order in which to use them.

#### Sandbox Credentials
A sandbox environment that replicates the production API will be configured for you within 3 business days.
An email with your credentials will be sent. Note that in this environment events such as loan processing and account registration might appear faster than in production to make it easier to test your integration.
    
### Integration
This is the phase where we will describe KYC compliance requirements, security best practices and general guidelines. 

We urge you to thoroughly examine all of the api endpoints in your sandbox environment, since it replicates our real production platform. This is also the time to bring us any suggestions or customizations that would make our product better for your use case. Be sure to let us know of any problems you may encounter.

### Testing and Review
During the final phase, we will work with you to make sure your integration is ready for live release, performing security checks and manual tests. 

Once we've performed these checks, a set of production credentials will be generated for the live environment.

## KYC

The collection of KYC documentation from your users is an important step in the onboarding process.
This not only helps facilitate compliance with regulators, but also helps prevent fraudulent user activity. 

The documents collected for both businesses and individuals helps us understand who our customers are and the nature of their relationship with us.

There are two steps to these requirements: 
  * Gathering information about the platform user (business) and associated individuals (persons); 
  * Veryfing the information is current and accurate.

Different platforms and limits will have different KYC requirements because the underlying risks can vary greatly. We encourage you to collect more KYC than our minimum requirements.

### Types of Information

There are two types of information we need to collect: business information (name, cnpj, address, etc) and information about the owners.


### How We Validate
Submitted user information are validated through public and private databases and partner APIs. 
Physical documents, such as government IDs, are validated through automated software, which incorporates:

  * OCR
  * Facial detection


### Physical Documents
Physical documents must be encoded to Base64 before being submitted to our API. 
You can submit these documents separately or (preferably) all at once in one API call.


## User Onboarding Process

  * First, you will make an API call to create a new account - `POST /account`. You can either send the business information later - `PATCH /account`, or within the acount creation process.
  * For every beneficial owner of the business, you'll create a separate Person entity - `POST /persons`.
  * Upload the required documentation - `PATCH /account` and `PATCH /persons`.
  * Subscribe to `accounts.update` and `persons.update` events - `POST /webhook_endpoints` or poll the appropriate endpoints - `GET /accounts/id` and `GET /persons/id`.
  * Watch for status changes in the verification object.
  * If there aren't any verification problems, wait for the enabled account status change.


## Dashboard

A dashboard is provided at `/dashboard` to which you can login with your credentials and perform the following operations:
- Reset your `client_id`
- Browse all accounts registered on your platform, their approval status and line of credit
- Browse all loans issued on your platform and their statuses
