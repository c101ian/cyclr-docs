/*
Title: Example JSON
Sort: 5
*/

## Introduction

The below JSON is a taken from a Salesforce connector.

```
{
	"Name": "Salesforce",
	"Description": "Salesforce CRM automates the sales process with an array of cloud-based tools.",
	"Version": "v30.0",
	"AuthType": "OAuth2",
	"ClientId": "",
	"ClientSecret": "",
	"AuthoriseUrl": "https://login.salesforce.com/services/oauth2/authorize",
	"AccessTokenUrl": "https://login.salesforce.com/services/oauth2/token",
	"Methods": [
		{
			"Name": "Get Contacts",
			"Description": "Get the new contacts.",
			"Category": "Contacts",
			"MethodType": "Action",
			"HttpMethod": "Get",
			"DataType": "Json",
			"Endpoint": "{{InstanceUrl}}/services/data/v30.0/query?q=SELECT Title, FirstName, LastName, Name, Email, cyclr__EmailSubscription__c FROM Contact WHERE CreatedDate > {{LastSuccessfulRunDate format=yyyy-MM-ddTHH:mm:ssZ}}",
			"ResponseFormat": {
				"Fields": [
					{
						"ConnectorField": "[records].Salutation",
						"CyclrField": "Salutation",
						"DisplayField": "Salutation"
					},
					{
						"ConnectorField": "[records].FirstName",
						"CyclrField": "FirstName",
						"DisplayField": "First Name"
					},
					{
						"ConnectorField": "[records].LastName",
						"CyclrField": "LastName",
						"DisplayField": "Last Name"
					},
					{
						"ConnectorField": "[records].Name",
						"CyclrField": "Name",
						"DisplayField": "Name"
					},
					{
						"ConnectorField": "[records].Email",
						"CyclrField": "Email",
						"DisplayField": "Email"
					},
					{
						"ConnectorField": "[records].cyclr__EmailSubscription__c",
						"CyclrField": "EmailSubscription",
						"DisplayField": "Email Subscription"
					}
				]
			}
		},
		{
			"Name": "Update Contact",
			"Description": "Update the contact.",
			"Category": "Contacts",
			"MethodType": "Action",
			"HttpMethod": "Patch",
			"DataType": "Json",
			"Endpoint": "{{InstanceUrl}}/services/data/v30.0/sobjects/Contact/{{Id}}",
			"RequestFormat": {
				"Fields": [
					{
						"ConnectorField": "Salutation",
						"CyclrField": "Salutation",
						"DisplayField": "Salutation"
					},
					{
						"ConnectorField": "FirstName",
						"CyclrField": "FirstName",
						"DisplayField": "First Name"
					},
					{
						"ConnectorField": "LastName",
						"CyclrField": "LastName",
						"DisplayField": "Last Name"
					},
					{
						"ConnectorField": "Email",
						"CyclrField": "Email",
						"DisplayField": "Email"
					},
					{
						"ConnectorField": "cyclr__EmailSubscription__c",
						"CyclrField": "EmailSubscription",
						"DisplayField": "Email Subscription"
					}
				]
			},
			"Fields": [
				{
					"TriggerName": "Get Contact ID",
					"IdentifierKey": "Id"
				}
			]
		},
		{
			"Name": "Update Campaign",
			"Description": "Update the campaign.",
			"Hide": true,
			"Category": "Campaigns",
			"MethodType": "Action",
			"HttpMethod": "Patch",
			"DataType": "Json",
			"Endpoint": "{{InstanceUrl}}/services/data/v30.0/sobjects/Campaign/{{Id}}",
			"RequestFormat": {
				"Fields": [
					{
						"ConnectorField": "cyclr__Recipients__c",
						"CyclrField": "Recipients",
						"DisplayField": "Recipients"
					},
					{
						"ConnectorField": "cyclr__Total_Opened__c",
						"CyclrField": "TotalOpened",
						"DisplayField": "Total Opened"
					},
					{
						"ConnectorField": "cyclr__Clicks__c",
						"CyclrField": "Clicks",
						"DisplayField": "Clicks"
					},
					{
						"ConnectorField": "cyclr__Unsubscribed__c",
						"CyclrField": "Unsubscribed",
						"DisplayField": "Unsubscribed"
					},
					{
						"ConnectorField": "cyclr__Bounced__c",
						"CyclrField": "Bounced",
						"DisplayField": "Bounced"
					},
					{
						"ConnectorField": "cyclr__Unique_Opened__c",
						"CyclrField": "UniqueOpened",
						"DisplayField": "Unique Opened"
					},
					{
						"ConnectorField": "cyclr__Spam_Complaints__c",
						"CyclrField": "SpamComplaints",
						"DisplayField": "Spam Complaints"
					},
					{
						"ConnectorField": "cyclr__Forwards__c",
						"CyclrField": "Forwards",
						"DisplayField": "Forwards"
					},
					{
						"ConnectorField": "cyclr__Likes__c",
						"CyclrField": "Likes",
						"DisplayField": "Likes"
					},
					{
						"ConnectorField": "cyclr__Mentions__c",
						"CyclrField": "Mentions",
						"DisplayField": "Mentions"
					}
				]
			},
			"Fields": [
				{
					"Name": "Campaign ID",
					"TriggerName": "Get Campaigns",
					"IdentifierKey": "Id",
					"HumanReadableKey": "Name"
				}
			]
		},
		{
			"Name": "Get Contact ID",
			"Description": "Gets the ID for a contact.",
			"Category": "Contacts",
			"MethodType": "Action",
			"HttpMethod": "Get",
			"DataType": "Json",
			"Endpoint": "{{InstanceUrl}}/services/data/v30.0/query?q=SELECT Id FROM Contact WHERE Email='{{Email}}'",
			"ResponseFormat": {
				"Fields": [
					{
						"ConnectorField": "[records].Id",
						"CyclrField": "Id"
					}
				]
			}
		},
		{
			"Name": "Get Campaigns",
			"Description": "Retrieves a list of campaigns.",
			"Hide": true,
			"Category": "Campaigns",
			"MethodType": "Action",
			"HttpMethod": "Get",
			"DataType": "Json",
			"Endpoint": "{{InstanceUrl}}/services/data/v30.0/query?q=SELECT Id, Name FROM Campaign",
			"ResponseFormat": {
				"Fields": [
					{
						"ConnectorField": "[records].Id",
						"CyclrField": "Id"
					},
					{
						"ConnectorField": "[records].Name",
						"CyclrField": "Name"
					}
				]
			}
		}
	]
}
```