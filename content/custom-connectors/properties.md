/*
Title: Properties
Sort: 2
*/

## Name

Provides a name for the connector to be shown in the Cyclr UI.  Typically the name of the product or service so "Salesforce" or "Sentori".  Use the same capitalisation as the product's website.

## CreatedOnUtc

The date and time when the Connector file was created (in GMT timezone).  Will be used to identify when a Connector should be updated in Cyclr.  Format: "2015-12-14T11:20:00.000Z".  Leave the seconds and milliseconds as zeros (not that precise).

## Description

Provides a description for the connector to be shown in the Cyclr UI.  Try to find some text from the product's website that describes it in their own words, e.g. for Sentori: "Sentori is a powerful multi-channel marketing platform" on www.sentoriapp.com so use "A powerful multi-channel marketing platform."  If nothing leaps out, just briefly describe what the product does, e.g. "An email marketing service."

## Version

This is the version of the product's API and doesn't necessarily match the version of the product itself.

## AuthType

This specifies what type of authentication is used by the remote endpoint.

Type | Description
------------- | -------------
ApiKey | The user should provide an API key for the Connector. Requires: `AuthApiKeyHttpHeaderName` or `AuthApiKeyBodyFieldName`.
Basic | The API uses OAuth 1.0a authentication. Requires: `ConsumerKey`, `ConsumerSecret`, `RequestTokenUrl`, `AuthorizeUrl`, `AccessTokenUrl`.
OAuth2 | The API uses OAuth 2 authentication. Requires: `ClientId`, `ClientSecret`, `AuthoriseUrl`, `AccessTokenUrl`. Optional: `Scopes`.
None | No authentication required. :)
AuthFields | The API needs to inject authorisation fields into the POST message. Requires: `AuthScheme`.

## Icon

Your connector needs an icon.

* 256px / 256px
* 24-bit PNG on a transparent background
* Encode as a Base64 string. We like [Base64 Image Encoder](https://www.base64-image.de/).