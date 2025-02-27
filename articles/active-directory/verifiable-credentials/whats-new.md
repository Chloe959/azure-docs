---
title: What's new for Microsoft Entra Verified ID
description: Recent updates for Microsoft Entra Verified ID
author: barclayn
manager: rkarlin
ms.service: decentralized-identity
ms.subservice: verifiable-credentials
ms.topic: reference
ms.date: 07/29/2022
ms.custom: references_regions
ms.author: barclayn

#Customer intent: As an Microsoft Entra Verified ID issuer, verifier or developer, I want to know what's new in the product so that I can make full use of the functionality as it becomes available.

---

# What's new in Microsoft Entra Verified ID

[!INCLUDE [Verifiable Credentials announcement](../../../includes/verifiable-credentials-brand.md)]

This article lists the latest features, improvements, and changes in the Microsoft Entra Verified ID service.

## August 2022

Microsoft Entra Verified ID is now generally available (GA) as the new member of the Microsoft Entra portfolio! [read more](https://techcommunity.microsoft.com/t5/microsoft-entra-azure-ad-blog/microsoft-entra-verified-id-now-generally-available/ba-p/3295506) 

### Known issues 
- Tenants that [opt-out](verifiable-credentials-faq.md?#how-do-i-reset-the-entra-verified-id-service) without issuing any Verifiable Credential will get a `Specified resource does not exist` error from the Admin API and/or the Entra portal. A fix for this issue should be available by 08/20/22.

## July 2022

- The Request Service APIs have a **new hostname** `verifiedid.did.msidentity.com`. The `beta.did.msidentity` and the `beta.eu.did.msidentity` will continue to work, but you should change your application and configuration. Also, you no longer need to specify `.eu.` for an EU tenant.
- Request Service API have **new endpoints** and **updated JSON payloads**. For issuance, see [Issuance API specification](issuance-request-api.md#issuance-request-payload) and for presentation, see [Presentation API specification](presentation-request-api.md#presentation-request-payload). The old endpoints and JSON payloads will continue to work, but you should change your applications to use the new endpoints and payloads.
- Request Service API **[Error codes](error-codes.md)** have been **updated** 
- The **[Admin API](admin-api.md)** is made **public** and is documented. The Azure portal is using the Admin API and with this REST API you can automate the onboarding or your tenant and creation of credential contracts.
- Find issuers and credentials to verify via the [The Microsoft Entra Verified ID Network](how-use-vcnetwork.md).
- For migrating your Azure Storage based credentials to become Managed Credentials there is a PowerShell script in the [GitHub samples repo](https://github.com/Azure-Samples/active-directory-verifiable-credentials/tree/contractmigration/scripts/contractmigration) for the task.

- We also made the following updates to our Plan and design docs:
    - (updated) [architecture planning overview](introduction-to-verifiable-credentials-architecture.md).
    - (updated) [Plan your issuance solution](plan-issuance-solution.md).
    - (updated) [Plan your verification solution](plan-verification-solution.md).

## June 2022

- We are adding support for the [did:web](https://w3c-ccg.github.io/did-method-web/) method. Any new tenant that starts using the Verifiable Credentials Service after June 14, 2022 will have Web as a new, default, trust system when [onboarding](verifiable-credentials-configure-tenant.md#set-up-verifiable-credentials). VC Administrators can still choose to use ION when setting a tenant. If you want to use did:web instead of ION or viceversa, you will need to [reconfigure your tenant](verifiable-credentials-faq.md?#how-do-i-reset-the-entra-verified-id-service).
- We are rolling out several features to improve the overall experience of creating verifiable credentials in the Entra Verified ID platform:
  - Introducing Managed Credentials, Managed Credentials are verifiable credentials that no longer use of Azure Storage to store the [display & rules JSON definitions](rules-and-display-definitions-model.md). Their display and rule definitions are different from earlier versions.
  - Create Managed Credentials using the [new quickstart experience](how-to-use-quickstart.md).
  - Administrators can create a Verified Employee Managed Credential using the [new quick start](how-to-use-quickstart-verifiedemployee.md). The Verified Employee is a verifiable credential of type verifiedEmployee that is based on a pre-defined set of claims from your tenant's Azure Active Directory.

>[!IMPORTANT]
> You need to migrate your Azure Storage based credentials to become Managed Credentials. We'll soon provide migration instructions.

- We made the following updates to our docs:
    - (new) [Current supported open standards for Microsoft Entra Verified ID](verifiable-credentials-standards.md).
    - (new) [How to create verifiable credentials for ID token hint](how-to-use-quickstart.md).
    - (new) [How to create verifiable credentials for ID token](how-to-use-quickstart-idtoken.md).
    - (new) [How to create verifiable credentials for self-asserted claims](how-to-use-quickstart-selfissued.md). 
    - (new) [Rules and Display definition model specification](rules-and-display-definitions-model.md).
    - (new) [Creating an Azure AD tenant for development](how-to-create-a-free-developer-account.md).

## May 2022

We are expanding our service to all Azure AD customers! Verifiable credentials are now available to everyone with an Azure AD subscription (Free and Premium). Existing tenants that configured the Verifiable Credentials service prior to May 4, 2022 must make a [small change](verifiable-credentials-faq.md#updating-the-vc-service-configuration) to avoid service disruptions.

## April 2022

Starting next month, we are rolling out exciting changes to the subscription requirements for the Verifiable Credentials service. Administrators must perform a small configuration change before **May 4, 2022** to avoid service disruptions. Follow [these steps](verifiable-credentials-faq.md?#updating-the-vc-service-configuration) to apply the required configuration changes.
>[!IMPORTANT]
> If changes are not applied before **May 4, 2022**, you will experience errors on issuance and presentation for your application or service using the Microsoft Entra Verified ID Service. [Update service configuration instructions](verifiable-credentials-faq.md?#updating-the-vc-service-configuration).

## March 2022

- Microsoft Entra Verified ID customers can now change the [domain linked](how-to-dnsbind.md) to their DID easily from the Azure portal.
- We made updates to Microsoft Authenticator that change the interaction between the Issuer of a verifiable credential and the user presenting the verifiable credential. This update forces all Verifiable Credentials to be reissued in Microsoft Authenticator for iOS. [More information](whats-new.md?#microsoft-authenticator-did-generation-update)

## February 2022

We are rolling out some breaking changes to our service. These updates require Microsoft Entra Verified ID service reconfiguration. End-users need to have their verifiable credentials reissued.

- The Microsoft Entra Verified ID service can now store and handle data processing in the Azure European region.
- Microsoft Entra Verified ID customers can take advantage of enhancements to credential revocation. These changes add a higher degree of privacy through the implementation of the [W3C Status List 2021](https://w3c-ccg.github.io/vc-status-list-2021/) standard. [More information](whats-new.md?#credential-revocation-with-enhanced-privacy)
- We made updates to Microsoft Authenticator that change the interaction between the Issuer of a verifiable credential and the user presenting the verifiable credential. This update forces all Verifiable Credentials to be reissued in Microsoft Authenticator for Android. [More information](whats-new.md?#microsoft-authenticator-did-generation-update)

>[!IMPORTANT]
> All Azure AD Verifiable Credential customers receiving a banner notice in the Azure portal need to go through a service reconfiguration before March 31st 2022. On March 31st 2022 tenants that have not been reconfigured will lose access to any previous configuration. Administrators will have to set up a new instance of the Azure AD Verifiable Credential service. Learn more about how to [reconfigure your tenant](verifiable-credentials-faq.md?#how-do-i-reset-the-entra-verified-id-service).

### Microsoft Entra Verified ID available in Europe

Since the beginning of the Microsoft Entra Verified ID service public preview, the service has only been available in our Azure North America region. Now, the service is also available in our Azure Europe region.

- New customers with Azure AD European tenants now have their Verifiable Credentials data located and processed in our Azure Europe region.
- Customers with Azure AD tenants setup in Europe who start using the Microsoft Entra Verified ID service after February 15, 2022, have their data automatically processed in Europe. There's no need to take any further actions.
- Customers with Azure AD tenants setup in Europe that started using the Microsoft Entra Verified ID service before February 15, 2022, are required to reconfigure the service on their tenants before March 31, 2022.

Take the following steps to configure the Verifiable Credentials service in Europe:

1. [Check the location](verifiable-credentials-faq.md#how-can-i-check-my-azure-ad-tenants-region) of your Azure Active Directory to make sure is in Europe.
1. [Reconfigure the Verifiable Credentials service](verifiable-credentials-faq.md?#how-do-i-reset-the-entra-verified-id-service) in your tenant. 

>[!IMPORTANT]
> On March 31st, 2022 European tenants that have not been [reconfigured](verifiable-credentials-faq.md?#how-do-i-reset-the-entra-verified-id-service) in Europe will lose access to any previous configuration and will require to configure a new instance of the Azure AD Verifiable Credential service.

#### Are there any changes to the way that we use the Request API as a result of this move?

Applications that use the Microsoft Entra Verified ID service must use the Request API endpoint that corresponds to their Azure AD tenant's region.  

| Tenant region | Request API endpoint POST |
|------------|-------------------|
| Europe | `https://beta.eu.did.msidentity.com/v1.0/{tenantID}/verifiablecredentials/request` |
| Non-EU | `https://beta.did.msidentity.com/v1.0/{tenantID}/verifiablecredentials/request`  |

To confirm which endpoint you should use, we recommend checking your Azure AD tenant's region as described above. If the Azure AD tenant is in the EU, you should use the Europe endpoint.  

### Credential Revocation with Enhanced Privacy

The Azure AD Verifiable Credential service supports the [W3C Status List 2021](https://w3c-ccg.github.io/vc-status-list-2021/) standard. Each Issuer tenant now has an [Identity Hub](https://identity.foundation/identity-hub/spec/) endpoint used by verifiers to check on the status of a credential using a privacy-respecting mechanism. The identity hub endpoint for the tenant is also published in the DID document. This feature replaces the current status endpoint.

To uptake this feature follow the next steps:

1. [Check if your tenant has the Hub endpoint](verifiable-credentials-faq.md#how-can-i-check-if-my-tenant-has-the-new-hub-endpoint).
    1. If so, go to the next step.
    1. If not, [reconfigure the Verifiable Credentials service](verifiable-credentials-faq.md?#how-do-i-reset-the-entra-verified-id-service) in your tenant and go to the next step.
1. Create new verifiable credentials contracts. In the rules file you must add the ` "credentialStatusConfiguration": "anonymous" ` property to start using the new feature in combination with the Hub endpoint for your credentials:

Sample contract file:

  ``` json 
  {
    "attestations": {
      "idTokens": [
        {
          "id": "https://self-issued.me",
          "mapping": {
            "firstName": { "claim": "$.given_name" },
            "lastName": { "claim": "$.family_name" }
          },
          "configuration": "https://self-issued.me",
          "client_id": "",
          "redirect_uri": ""
        }
      ]
    },
    "validityInterval": 2592001,
  "credentialStatusConfiguration": "anonymous",
    "vc": {
      "type": [ "VerifiedCredentialExpert" ]
    }
  } 
  ```

3. You have to issue new verifiable credentials using your new configuration. All verifiable credentials previously issued continue to exist. Your previous DID remains resolvable however, they use the previous status endpoint implementation.

>[!IMPORTANT]
> You have to reconfigure your Azure AD Verifiable Credential service instance to create your new Identity hub endpoint. You have until March 31st 2022, to schedule and manage the reconfiguration of your deployment. On March 31st, 2022 deployments that have not been reconfigured will lose access to any previous Microsoft Entra Verified ID service configuration. Administrators will need to set up a new service instance.

### Microsoft Authenticator DID Generation Update

We are making protocol updates in Microsoft Authenticator to support Single Long Form DID, thus deprecating the use of pairwise. With this update, your DID in Microsoft Authenticator will be used of every issuer and relaying party exchange. Holders of verifiable credentials using Microsoft Authenticator must get their verifiable credentials reissued as any previous credentials aren't going to continue working.

## December 2021

- We added [Postman collections](https://github.com/Azure-Samples/active-directory-verifiable-credentials/tree/main/Postman) to our samples as a quick start to start using the Request Service REST API.
- New sample added that demonstrates the integration of [Microsoft Entra Verified ID with Azure AD B2C](https://github.com/Azure-Samples/active-directory-verifiable-credentials/tree/main/B2C).
- Sample for setting up the Microsoft Entra Verified ID services using [PowerShell and an ARM template](https://github.com/Azure-Samples/active-directory-verifiable-credentials/tree/main/ARM).
- Sample Verifiable Credential configuration files to show sample cards for [ID Token](https://github.com/Azure-Samples/active-directory-verifiable-credentials/tree/main/CredentialFiles/IDToken), [IDTokenHit](https://github.com/Azure-Samples/active-directory-verifiable-credentials/tree/main/CredentialFiles/IDTokenHint) and [Self-attested](https://github.com/Azure-Samples/active-directory-verifiable-credentials/tree/main/CredentialFiles/IDTokenHint) claims.

## November 2021

- We made updates to the Request Service REST API for [issuance](issuance-request-api.md?#callback-type) and [presentation](presentation-request-api.md?#callback-type)
Callback types enforcing rules so that URL endpoints for callbacks are reachable.
- UX updates to the Microsoft Authenticator verifiable credentials experience: Animations on card selection from the wallet.

## October 2021

You can now use [Request Service REST API](get-started-request-api.md) to build applications that can issue and verify credentials from any programming language. This new REST API provides an improved abstraction layer and integration to the Microsoft Entra Verified ID Service.

It's a good idea to start using the API soon, because the NodeJS SDK will be deprecated in the following months. Documentation and samples now use the Request Service REST API. For more information, see [Request Service REST API (preview)](get-started-request-api.md).

## April 2021

You can now issue [verifiable credentials](decentralized-identifier-overview.md) in Azure AD. This service is useful when you need to present proof of employment, education, or any other claim. The holder of such a credential can decide when, and with whom, to share their credentials. Each credential is signed by using cryptographic keys associated with the decentralized identity that the user owns and controls.
