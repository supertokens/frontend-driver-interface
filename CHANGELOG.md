# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html)

## [1.13.0]

### Added 
- ThirdPartyPasswordless recipe APIs
  - adds `/signinup/code`                 POST
  - adds `/signinup/code/resend`          POST
  - adds `/signinup/code/consume`         POST
  - adds `/signup/email/exists`           GET
  - adds `/signup/phoneNumber/exists`     GET
  - adds `{apiBasePath}/signinup`         POST
  - adds `{apiBasePath}/authorisationurl` GET
  - adds `{apiBasePath}/callback/apple`   GET



## [1.12.0]

### Added
- passwordless recipe APIs
  - `/signinup/code`
  - `/signinup/code/consume`
  - `/signup/email/exists`
  - `/signup/phoneNumber/exists`

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