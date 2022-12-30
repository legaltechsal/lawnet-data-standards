# eLitigation Billing API

Version: 0.1a
Status: For discussion with integration partners


## Description

LawNet will be providing programmatic access to law firm-specific billing data (based on eLitigation transactions). 

For security reasons, access will only be provided to authorised partners, and only with the explicit approval of law firm administrators.


## Project phasing

SAL is progressively building core infrastructure, including:
* Secure data transfer from eLitigation, (a) to minimise direct integrations with eLitigation, and (b) to minimise costs and efforts for integrating clients
* Access controls for law firms to manage API access (a) on a general level, and (b) specific to integrating clients
* Data integrity checks, reporting and recovery mechanisms, (a) to ensure accurate data across systems and clients, and (b) to enable integrating clients to alert their own users of any discrepancies
* Secure data transfer between LawNet and integrating clients


## Integration overview

The integrating client is responsible for
* Seeking the law firm administrator's permission, through SAL ID, to access billing data on their behalf
* Providing webhooks for LawNet to notify the integrating client of key events, such as new data, outages, permission changes etc
* Retrieving billing data only as requested by users, and provided by LawNet
* Communicating to their users, recency and accuracy of billing data, as enabled by metadata provided by billing APIs
* Verifiably deleting the law firm's billing data, should LawNet notify the integrating client that the law firm has revoked permissions to access billing data
* Securely handling the law firm's billing data in transit and at rest, in accordance to current security best practices
* Complying with PDPA and relevant local regulations