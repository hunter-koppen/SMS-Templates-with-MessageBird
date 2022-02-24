## Description

The SMS Templates with MessageBird module allows you to easily create and send SMS messages from your Mendix app with MessageBird, by providing the templates mechanism, example sending microflows and an integration with MessageBird. 

## Features and limitations

- Send SMS messages
- Create templates with tokens to supply the body for the SMS messages
- Example microflow for quickly adding SMS logic to your application
- Queue SMS messages for bulk messaging

## Dependencies

- MxModelReflections Module
- Encryption Module

## Messagebird Setup

This module uses MessageBird as the SMS provider. In order to start sending out SMS message you also need to do some setup in the MessageBird dashboard.

1. Create an account and login at https://www.messagebird.com/.
2. Make sure to provide a phonenumber in your account details. (this is used for testing purposes)
3. Find your API keys in the developer dashboard, there should be 2, one for testing and one for live usage.
4. Claim test credits in the dashboard. You can claim 10 test tokens which you can use to send an actual SMS to your provided phonenumber in your account details.

## Mendix Configuration

1. Download the MxModelReflection module.
2. Download the Encryption module.
3. Set the encryption key if you havnt already (check readme from Encryption module)
4. Create a new configurator page and add the SNIP_SMSConfigurator snippet to the page.
5. Setup the correct userroles, the configurator needs ModelAdministrator in the MxModelReflection module and Configurator in the SMSTemplates module
6. Run locally, navigate to the configurator page and fill in the setup values in the configuration tab. You can instantly test if it works if you have completed the setup on the MessageBird website aswell.

## Usage

Once the setup has been completed you can copy the SUB_CreateAndSendSMS_Example or SUB_CreateAndQueueSMS_Example microflows and use them in your application. You simply need to provide an SMS template and phonenumber to send an SMS. Use the SUB_CreateAndQueueSMS_Example microflow if you wish to automatically queue all messages.

The USE_ME folder also contains the CONST_UseTestKey constant. You should only set this on true for production environments which will make the API use the Live API Key instead of the Test API Key.

For phonenumbers the E.164 format should be used according to MessageBird. See https://support.messagebird.com/hc/en-us/articles/115003950149-Formatting-your-contact-numbers#h_01FDSNC2M3BAGH02M4CK0BH3G3. 