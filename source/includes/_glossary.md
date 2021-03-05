# Glossary

Here are some of the terms we use throughout our documentation for ease of reference.

<h2 id="glossary-prequalify">Pre-qualify</h2>
`Pre-qualification` is an optional step that you can take advantadge of by calling the specific endpoint.
This endpoint will perform an analysis using publicly available data to decide whether the user qualifies for an account. This allows you to choose not to offer loans to those that will not qualify, making you UX better.

<h2 id="glossary-tokens">Platform Tokens</h2>
Two types of JWT tokens can be generated: client and account.

<h3 id="glossary-client-tokens">Client Tokens</h2>
Client tokens refer to your platform tokens; they have full permissions on every API endpoint, being able to perform account creation/deletion and operations on behalf of any account.
You should keep these tokens in your backend only and never share with mobile or web devices.

<h3 id="glossary-account-tokens">Account Tokens</h2>
Account tokens have account-specific permissions; they cannot create/delete accounts and can only operate within the bounds of the account for which they were created. They must always be paired with an `account-id` header parameters.

<h2 id="glossary-documents">Documents</h2>

<h3 id="glossary-physical-docs">Physical Documents</h2>
Physical documents are the image scans or photos of a physical document.

All physical documents have a `value` and a `type`. `type` is the document type (ie: driver's license, passport, etc) and `value` is a base64 encoded string of the actual document. Note: don't use a mime type header; we automatically detect the file format.

<h3 id="glossary-virtual-docs">Virtual Documents</h2>
Virtual documents are personally identifiable document besides business id and government id number that might be required.
A virtual document has a `value` (business id number, for example), a `type` (passport, drivers license id), `expiration date` and `issuer`.
