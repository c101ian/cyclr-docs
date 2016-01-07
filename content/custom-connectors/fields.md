/*
Title: Fields
Sort: 4
*/

## Introduction

Your fields define what values can be sent or received by a method.

## Field Properties

Name | Description
------------- | -------------
ConnectorField | The name of the field as used by the remote application's API.  Includes Cyclr notation to allow it to locate the value, e.g. `[records].EmailAddress` when receiving an array and retrieving the `EmailAddress` attribute from an element within that array (see *RequestFormat / ResponseFormat* documentation above for more details).
CyclrField | Name to use internally within Cyclr.  Use the field as capitalised by the API and remove any spaces.
DisplayField | Name to be displayed in the Cyclr UI to the user.  Typically, take the `CyclrField` value and add spaces or anything that might help describe it, e.g. in *Google Sheets* the `ConnectorField` `entry.title` used when working with Rows becomes *Row Title*.
Description | This is the description of the Field to appear in the Cyclr UI for the user to understand how the Field is used.  Always include this and keep fairly short (no more than 100 characters).
IsOptional | Set to `true` if the Field doesn’t have to be given a value.  Leave out if it’s a required Field.

## Placeholders 

Placeholders can be used in the connector definition. A placeholder is a piece of text which will be substituted at runtime. 

### Supported placeholders 

Name | Description
------------- | -------------
LastSuccessfulRunDate | A format string needs to be provided. For example, {{LastSuccessfulRunDate format=yyyy-MM-ddTHH:mm:ssZ}}.