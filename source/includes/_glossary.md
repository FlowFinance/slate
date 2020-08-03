# Glossary

Here are some of the terms we use throughout our documentation, for ease of reference

<h2 id="glossary-prequalify">Pre-qualify</h2>
The pre-qualify is an optional step that you can use by calling the specific endpoint.
This endpoint will perform an analysis using publicly available data to perform a pre-validation of the business, to allow you to choose wether or not to offer registration.

<h2 id="glossary-tokens">Platform Tokens</h2>
Two types of JWT tokens can be generated: client and account. 

<h3 id="glossary-client-tokens">Client Tokens</h2>
Client tokens refer to your platform tokens; they have full permissions on every API endpoint, being able to perform account creation/deletion and operations on behalf of any account. 
You should keep these tokens in your backend only and never share with mobile nor web devices. 

<h3 id="glossary-account-tokens">Account Tokens</h2>
Account tokens have account-specific permissions; they cannot create/delete accounts and can only operate within the bounds of the account for which they were created.

<h2 id="glossary-documents">Documents</h2>

<h3 id="glossary-physical-docs">Physical Documents</h2>
Physical documents are the image format of a document that exists in the physical world.

All physical documents have a `value` and a `type`, `type` is the document type (from a list o types) and the `value` is a string with the actual document, base64-encoded (without mime type).

<h3 id="glossary-virtual-docs">Virtual Documents</h2>
Virtual documents are how we refer to the actual values contained in a document.
A virtual document can have information such as it's `value` (id number), `type`, `expedition date` and `issuer` agency.
