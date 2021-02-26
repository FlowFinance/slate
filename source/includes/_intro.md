# Introduction

Learn how to use Flow Finance's [REST](http://en.wikipedia.org/wiki/Representational_State_Transfer) API, which allows platforms to quickly and programmatically issue loans to their users.

We've strived to make our API easy to use and hope you find it so.

If you have any suggestions on how we can make it even easier, feel free to get in touch with us.

Follow the steps below to get started:

  * Contact our sales team in order to register your platform and get access to API credentials.
  * You will be assigned an Integration Engineer who will guide you through the integration process.
  * Create accounts on behalf of your users following the KYC (Know Your Customer) guidelines.
  * Upload documents that verify your user's identity.
  * Wait for the account approval.
  * Issue a loan.

Since Flow Accounts are transparent to your users, you are in charge of all interactions with your users and for gathering all the information needed to verify the account. It's also up to you to build the onboarding process, UIs, and reporting functionalities.

## Overview

A brief, high-level technical overview of how to use the API.

* Your platform details and configuration will be set up for you by our team. Meanwhile, you will receive API credentials to be able to make requests.
* Using the above credentials you will be able to create accounts for your users.
* (Optional) You can use the `pre-qualify` endpoint to check if your user might not be eligible for an account before registration. This is not a mandatory step but it will help you to avoid offering credit to users who aren't eligible.
* Upload business and beneficial owners' information.
* Upload all the necessary documents, verifying business and persons identities.
* Collect your user's acceptance of our Terms of Service.
* The newly-created account will then go through an internal analysis (it usually takes less than 24 hours).
* After account approval, a line of credit will be established for the account.
* Using the `loan preview` endpoint you can get all available offers.
* Show these offers to your use and store the corresponding offer token for later use.
* Submit the offer token using the `/loan` endpoint to initiate the loan creation process.
* Once a loan has been successfully created, show the Loan Agreement Terms to your user and collect their acceptance (digital signature).
* Submit the above digital signature and the loan will then be issued.


## Getting started

<aside class="notice">
Contact our sales team to register your platform and get API credentials.
You will then be assigned an Integration Engineer who will guide you through the integration process.

Please note that this process is not set in stone, so we can always skip a step or work in parallel.
</aside>

### Platform Onboarding Steps
There are roughly 6 steps in the integration process.

### 1. Transactional Data Samples
In this step, you provide us with platform transactional data samples, which will be used by our data science team to train our algorithms.

### 2. Real Transactional Data
We will also need your platform API endpoint that will be used for retrieving transactional data. It must be capable of being queried by business id (cnpj/cpf). This allows us to perform real-time credit decisions.

We understand that providing an external API endpoint may not be an option for your platform, so we also provide 2 alternatives:
* You can attach the relevant data on every request where transactional data is needed
* You can send us your transactional data and we will process everything offline.

### 3. API Walkthrough
With the samples processed and an accessible API endpoint, we will schedule an API walkthrough where your assigned engineer will give you an overview of the Flow API, tailored to your platform, and explain relevant API calls and the suggested order in which to use them.

### 4. Sandbox Credentials
A sandbox environment that replicates the production API will be configured for you within 3 business days.
An email with your credentials will be sent. Note that in this environment events such as loan processing and account registration might appear faster than in production to make it easier to test your integration.

### 5. Integration
This is the phase where we will describe KYC compliance requirements, security best practices, and general guidelines.

We urge you to thoroughly examine all of the API endpoints in your sandbox environment since it replicates our real production platform. This is also the time to bring us any suggestions or customizations that would make our product better for your use case. Be sure to let us know of any problems you may encounter.

### 6. Testing and Review
During the final phase, we will work with you to make sure your integration is ready to go to production, performing security checks and manual tests.

Once we've performed these checks, a set of production credentials will be generated for the production environment.

# Additional Infomation

## KYC

The collection of Know Your Customer (KYC) documentation from your users is an important step in the onboarding process.
This not only helps facilitate compliance with regulators but also helps prevent fraudulent user activity.

The documents collected for both businesses and individuals help us understand who our customers are and the nature of their relationship with us.

There are two steps to these requirements:
  * Gathering information about the platform user (business) and associated individuals (persons);
  * Verifying the information is current and accurate.

Different platforms and limits will have different KYC requirements because the underlying risks can vary greatly. We encourage you to collect more KYC than our minimum requirements.

### Types of Information

There are two types of information we need to collect: business information (name, cnpj, address, etc) and information about the owners.


### How We Validate
Submitted user information is validated through public and private databases and partner APIs.
Physical documents, such as government IDs, are validated through automated software, which incorporates:

  * OCR
  * Facial detection


### Physical Documents
Physical documents must be encoded to Base64 before being submitted to our API.
You can submit these documents separately or (preferably) all at once in one API call.


## User Onboarding Process

  * First, you will make an API call to create a new account - `POST /account`. You can either send the business information later - `PATCH /account`, or within the account creation process.
  * For every beneficial owner of the business, you'll create a separate Person entity - `POST /persons`.
  * Upload the required documentation - `PATCH /account` and `PATCH /persons`.
  * Subscribe to `accounts.update` and `persons.update` events - `POST /webhook_endpoints` or poll the appropriate endpoints - `GET /accounts/id` and `GET /persons/id`.
  * Watch for status changes in the verification object.
  * If there aren't any verification problems, wait for the enabled account status change.


## Dashboard

A dashboard is provided at `/dashboard` to which you can log in with your credentials and perform the following operations:
- Reset your `client_id`
- Browse all accounts registered on your platform, their approval status and line of credit
- Browse all loans issued on your platform and their statuses
