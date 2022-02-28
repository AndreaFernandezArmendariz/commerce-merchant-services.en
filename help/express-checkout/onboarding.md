---
title: Onboard the [!DNL Express Checkout] for Adobe Commerce extension
description: Learn how the [!DNL Express Checkout] could benefit your Adobe Commerce instance and how to successfully onboard and setup the extension.
---

# [!DNL Express Checkout] onboarding

>[!IMPORTANT]
>
> This feature is for Early Adopter Program (EAP) users only and is not yet accessible for all customers. Currently limited to US customers. Contact Adobe Commerce Support for assistance and questions.

To get started using the [!DNL Express Checkout] for Adobe Commerce extension you must complete a few onboarding steps to connect your instance with our checkout functionality.

1. [Get extension](#get-extension).
1. [Create a production or sandbox merchant account with Bolt](#create-account-with-bolt). Provide all required information to verify your identity.
1. [Provide the unique API Key and Publishable Key generated in Bolt](#obtain-api-credentials).
1. [Set up a payment provider in the Bolt account](#configure-payment-providers).
1. [Set Enable dropdown to Yes](#enable-extension) to activate the extension.
1. [Define your Service Settings](#complete-admin-configuration) to configure the [!DNL Express Checkout] extension.
1. [Click the Save Config button](#enable-live-express-checkout) to enable extension.

>[!NOTE]
>
> If you do not configure your Bolt accounts (step 2 above) you cannot set up your sandbox or production environments.

## Prerequisites

In order to use the [!DNL Express Checkout], you must have the following available for Bolt:

- Supported payment providers
- Merchant and Production account in Bolt
- API and Publishable key generated in Bolt

Refer to the [prerequisites](../express-checkout/prerequisites.md) topic for more information.

See [API credentials](#obtain-api-credentials) to learn how to create or access your API keys for your instance.

## Get extension

See the [install](../express-checkout/install.md) topic for detailed information about obtaining the extension.

## Create account with Bolt

Before configuring the [!DNL Express Checkout] in your Adobe Commerce Admin it is required to create a [production](https://merchant.bolt.com/register){target="_blank"} and [sandbox](https://merchant-sandbox.bolt.com/register){target="_blank"} merchant account in Bolt. Provide all of the required details to create an account in Bolt.

Refer to the [test and validate](../express-checkout/testing.md) topic for more information.

## Obtain API credentials

To use the [!DNL Express Checkout] you require Bolt unique keys. Obtain the following API keys by navigating to **Developers** > **API** > **Keys** in the **Bolt Merchant Dashboard**.

- API key: A private key used by your back end to interact with Bolt APIs.
- Publishable key: A key used by your front end to interact with Bolt APIs.

See the [Bolt environment details](https://help.bolt.com/developers/references/environment-details/#about-keys){target="_blank"} page to learn about API and Publishable keys for the [!DNL Express Checkout] extension.

>[!CAUTION]
>
> You must create API keys for both sandbox and production environments.

## Configure payment providers

To connect your payment services provider follow the steps described in the [processor setup](https://help.bolt.com/integrations/adobe-express-checkout/set-up/){target="_blank"} developer Bolt page.

## Enable extension

1. On the _Admin_ sidebar, navigate to **Stores** > **Configuration** > **Checkout** to access the Checkout Admin configuration page.

  ![Express Checkout](../assets/admin-view.png)

1. In the [!DNL Express Checkout] view, set **Enable** to `Yes`.
1. Select method (Production or Sandbox) to use.
1. Validate Credentials after providing your unique API and Publishable keys.

>[!CAUTION]
>
> You must provide unique API and Publishable keys before enabling the extension otherwise customers will see a payment form and will not be able to place an order.

## Complete admin configuration

1. On the _Admin_ sidebar, navigate to **Stores** > **Configuration** > **Checkout** to acess the general Checkout Admin config page.
1. In the _Service Settings_ section, provide all details required to enable the extension.
1. Set _Payment Action_ as:

   - Authorize: Do not capture transaction automatically upon authorization.
   - Authorize and Capture: Capture transaction automatically upon authorization.

For more information on the Adobe Commerce standard checkout options, refer to the [checkout](https://docs.magento.com/user-guide/configuration/sales/checkout.html) topic.

## Enable live express checkout

To enable the [!DNL Express Checkout] for Adobe Commerce extension:

1. Click **Save Config**.

## Get help

The onboarding process is designed to guide you through the required steps for setting up and enabling all [!DNL Express Checkout] functionality. Contact Adobe Commerce Support for assistance and questions.

Refer to the [test and validate](../express-checkout/testing.md) topic for more information.