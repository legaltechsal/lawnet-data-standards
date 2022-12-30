# SAL ID Integration

Version: 1


## Description

SAL ID is a single sign-on system provided by the Singapore Academy of Law (SAL). Legal professionals have a single account to access content and services from SAL and partners.

SAL partners can adopt SAL ID to onboard users with a simple, familiar and secure account experience.

SAL ID uses the OAuth 2.0 protocol for authentication and authorization. All data is encrypted in transit and at rest.


## Integration overview

The integrating client is responsible for
* Redirecting login requests to SAL ID’s sign-in endpoint:
    * Providing and specifying a client endpoint to handle successful login.
    * SAL ID will redirect users to that client endpoint on successful validation.

* Depending on integration approach, the integrating client may
    * Receive access rights as additional information in the response JWT,
    * OR be required to manage access rights in its own user database (corresponding to the SAL ID)

* Redirecting logout requests to SAL ID’s sign-out endpoint:
    * Providing to SAL a client endpoint to handle successful logout.
    * SAL ID will redirect users to that client endpoint on successful logout.
    * This client endpoint should terminate any local cookies/session as necessary
    

## Register your application with SAL
Please discuss the following details with SAL (specific to your application environments – test and production):
* Signed In URL (users to be redirected to this path in your application after sign in)
* Signed Out URL (users to be redirected to this path in your application after sign out)
* Refresh Claims URL (users to be redirected to this path in your application after you request an update of access rights)
* Instance
* Domain (provided by SAL)
* Client ID (your application ID)
* Client Secret (only for regular web applications)
* SignUpSignInPolicy (provided by SAL)

SAL ID will support non-https URLs for localhost testing. Web-hosted environments need to have https endpoints.