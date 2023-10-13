# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html)

## [1.19.0] - 2023-10-XX

### Added

- Added an endpoint to query information about MFA factors
- Updated loginmethods (`{apiBasePath}/loginmethods`) response type to include a list of first factors

## [1.18.0] - 2023-08-XX

### Changed
- Updates ThirdParty, ThirdPartyEmailPassword, ThirdPartyPasswordless, Passwordless and EmailPassword recipes to support account linking 
  - Updates `{apiBasePath}/signinup/code`               POST
  - Updates `{apiBasePath}/signinup/code/consume`       POST
  - Updates `{apiBasePath}/signinup`                    POST
  - Updates `{apiBasePath}/signin`                      POST
  - Updates `{apiBasePath}/signup`                      POST
  - Updates `{apiBasePath}/user/password/reset/token`   POST
  - Updates `{apiBasePath}/user/password/reset`         POST
- The changes to the above endpoints are:
  - Added new response statuses
  - Unified the type/shape of the user objects across all different responses 
  - Renamed `createdNewUser` to `createdNewRecipeUser`

## [1.17.1] - 2023-08-31

### Changed

- Updated authorisationurl GET response to match implementation (and plans)

## [1.17.0] - 2023-07-21

### Added
- Multitenancy recipe APIs
  - adds `{apiBasePath}/loginmethods` GET

### Changed
- Updates ThirdParty, ThirdpartyEmailpassword and Thirdpartypasswordless recipes to support multitenancy
  - Updates `{apiBasePath}/signinup`          POST
  - Updates `{apiBasePath}/authorisationurl`  GET
  - Updates `{apiBasePath}/callback/apple`    POST

## [1.16.0]

- Updated authorization and response headers for header based auth

## [1.15.0]

- Added example user endpoint to showcase the `401` and `403` responses
- Updated description of `/{apiBasePath}/user/email/verify` to mention claims

## [1.14.0] - 2022-06-24
- Added `{status: "GENERAL_ERROR", message: string}` as a possible output to all APIs, except for session refresh and apple redirect.
- Removed FIELD_ERROR status type from social sign in up APIs

## [1.13.2] - 2022-05-12
- Adds missing required cookies for the signout API

## [1.13.1]
- Fixes `user` object returned in third party apis.

## [1.13.0]

### Added 
- ThirdPartyPasswordless recipe APIs
  - adds `{apiBasePath}/signinup/code`                 POST
  - adds `{apiBasePath}/signinup/code/resend`          POST
  - adds `{apiBasePath}/signinup/code/consume`         POST
  - adds `{apiBasePath}/signup/email/exists`           GET
  - adds `{apiBasePath}/signup/phoneNumber/exists`     GET
  - adds `{apiBasePath}/signinup`         POST
  - adds `{apiBasePath}/authorisationurl` GET
  - adds `{apiBasePath}/callback/apple`   GET



## [1.12.0]

### Added
- passwordless recipe APIs
  - `{apiBasePath}/signinup/code`
  - `{apiBasePath}/signinup/code/consume`
  - `{apiBasePath}/signup/email/exists`
  - `{apiBasePath}/signup/phoneNumber/exists`

## [1.11.0]

### Added 
- OpenId Recipe
  - adds  `/{apiBasePath}/.well-known/openid-configuration` GET

## [1.10.0]

### Added
- Adds `authCodeResponse` to `thirdparty` and `thirdpartyemailpassword`'s `signinup` POST API to support auth code exchange via PKCE method.
- Adds an optional `clientId` in `signinup` API to `thirdparty` and `thirdpartyemailpassword`
- Adds apple sign in callback API

## [1.9.0]

### Added

- Email OTP Recipe
  - adds `{apiBasePath}/signin`                POST
  - adds `{apiBasePath}/signup`                POST
  - adds `{apiBasePath}/signinup/email/exists` GET
  - adds `{apiBasePath}/signinup/otp`          POST

## [1.8.0]

### Updates

- All requests that go through session interception will have a custom header `rid` to prevent CSRF attacks (see [this](https://cheatsheetseries.owasp.org/cheatsheets/Cross-Site_Request_Forgery_Prevention_Cheat_Sheet.html#use-of-custom-request-headers)). The backend would then need to check for the existence of this header in case CSRF is enabled

## [1.7.0]

## Added 
- added `{apiBasePath}/session/signout`

## [1.6.0]

### Added 
- adds `{apiBasePath}/signinup`         POST
- adds `{apiBasePath}/signout`          POST
- adds `{apiBasePath}/authorisationurl` POST


### Updates
- moves `{apiBasePath}/user/email/verify/token` to its own recipe (email verification)
- moves `{apiBasePath}/user/email/verify` to its own recipe (email verification)
- moves `{apiBasePath}/user/email/verify` to its own recipe (email verification)

## [1.5.0]

### Added 

- adds `{apiBasePath}/user/email/verify/token` POST
- adds `{apiBasePath}/user/email/verify`       POST
- adds `{apiBasePath}/user/email/verify`       GET

## [1.4.0]

### Added
- adds `/signup/email/exists`  API

## [1.3.0]

### Updates
- All API requests must have an optional `rid` header. This also needs to be exposed in `Access-Control-Allow-Headers` 

### Removed
- removes `supertokens-sdk-name` and `supertokens-sdk-version`

### Updates
- Refresh API URL change

### Added
adds `{apiBasePath}/signin`
adds `{apiBasePath}/signup`
adds `{apiBasePath}/user/password/reset/token`
adds `{apiBasePath}/user/password/reset`