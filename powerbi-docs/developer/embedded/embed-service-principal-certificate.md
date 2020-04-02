---
title: Embedding Power BI content with service principal and a certificate
description: Learn how to authenticate for embedded analytics using an Azure Active Directory application service principal and a certificate.
author: KesemSharabi
ms.author: kesharab
ms.reviewer: nishalit
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.custom: ""
ms.date: 03/31/2020
---

# Embedding Power BI content with service principal and a certificate

[!INCLUDE[service principal overview](../../includes/service-principal-overview.md)]

## What is certificate-based authentication?

Certificate-based authentication enables you to be authenticated by Azure Active Directory (Azure AD) with a client certificate on a Windows, Android or iOS device, or in an [Azure Key Vault](https://docs.microsoft.com/azure/key-vault/basic-concepts).

Certificate-based authentication offers a strong security solution. This is because a signed certificate makes it possible to connect only to an approved server.

The secure connection is achieved by authenticating both the client and the server against a trusted Certification Authority (CA), during the TLS handshake.

Using this method of authentication, allows central management of  certificates using the CA, for rotation or revocation.

You can learn more about certificates in Azure AD in the [Client credential flows](https://github.com/AzureAD/microsoft-authentication-library-for-dotnet/wiki/Client-credential-flows) GitHub page.

## Method

To use service principal and a certificate with embedded analytics, follow these steps:

1. Create a certificate.

2. Set up certificate authentication.

3. Authenticate using the certificate.

## Step 1 - Creating a certificate

You can procure a certificate from a trusted *Certificate Authority*, or generate a certificate yourself.

This section describes creating a certificate using [Azure Key Vault](https://docs.microsoft.com/azure/key-vault/create-certificate).

1. Log into [Microsoft Azure](https://ms.portal.azure.com/#allservices).

2. Search for **Key Vaults** and click the **App Service Certificate** link.

    ![key vault](media/embed-service-principal-certificate/key-vault.png)

3. Click the key vault you want to add a certificate to.

4. Click **Certificates**.

    ![certificates](media/embed-service-principal-certificate/certificates.png)

5. Click **Generate/Import**.

    ![generate](media/embed-service-principal-certificate/generate.png)

6. Configure the **Create a certificate** fields as follows:

    ![certificate  properties](media/embed-service-principal-certificate/certificate-properties.png)

    * **Method of Certificate Creation** - General
    * **Certificate Name** - Enter a name for your certificate
    * **Type of Certificate Authority (CA)** - Self-signed certificate
    * **Subject** - `"CN=microsoft.com"`
    * **DNS Names** - 0 DNS names
    * **Validity Period (in months)** - Enter the certificate's validity duration
    * **Content Type** - PKCS #12
    * **Lifetime Action Type** - Automatically renew at a given percentage lifetime
    * **Percentage Lifetime** - 80
    * **Advanced Policy Configuration** - Not configured

7. Click **Create**. The newly created certificate is disabled by default. It can take up to five minutes to become enabled.

8. Click the certificate you created.

9. Click **Download in CER format**.

## Step 2 - Create an Azure AD Application

[!INCLUDE[service principal overview](../../includes/service-principal-create-app.md)]

## Step 3 - Set up certificate authentication

1. In your Azure AD application, click the **Certificates & secrets** tab.

     ![application ID](media/embed-service-principal/certificates-and-secrets.png)

2. Click **Upload certificate** and upload the certificate you created in [step 1](step-1---creating-a-certificate)

## Step 4 - Authenticate using the certificate

## Set up Managed Service Identity in Visual Studio 

## Next steps

* [Register an app](register-app.md)
* [Power BI Embedded for your customers](embed-sample-for-customers.md)
* [Application and service principal objects in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/develop/app-objects-and-service-principals)
* [Row-level security using on-premises data gateway with service principal](embedded-row-level-security.md#on-premises-data-gateway-with-service-principal)
