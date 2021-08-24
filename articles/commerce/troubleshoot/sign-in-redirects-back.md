---
title: Il collegamento di accesso reindirizza a un sito di e-commerce
description: Questo argomento fornisce indicazioni per la risoluzione dei problemi che possono essere utili quando un collegamento di accesso reindirizza al sito di e-commerce anziché alla pagina di accesso.
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rassadi
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 94afc339bd156d26c5057c1e401d707aa7d517a041493659a40c7b69ad4d377a
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6715286"
---
# <a name="sign-in-link-redirects-back-to-an-e-commerce-site"></a>Il collegamento di accesso reindirizza a un sito di e-commerce

[!include [banner](../../includes/banner.md)]

Questo argomento fornisce indicazioni per la risoluzione dei problemi che possono essere utili quando un collegamento di accesso reindirizza al sito di e-commerce anziché alla pagina di accesso.

## <a name="description"></a>Descrizione

Dopo aver configurato un nuovo tenant di Microsoft Azure Active Directory B2C (Azure AD B2C) in Creazione di siti di Commerce, gli utenti che selezionano il collegamento di **accesso** vengono reindirizzati alla pagina di destinazione di e-commerce principale senza passare alla pagina di accesso.

## <a name="resolution"></a>Risoluzione

### <a name="confirm-that-the-reply-url-is-correctly-configured-in-the-azure-ad-b2c-application"></a>Verificare che l'URL di risposta sia configurato correttamente nell'applicazione Azure AD B2C

Per confermare che l'URL di risposta sia configurato correttamente nell'applicazione Azure AD B2C, procedere come segue.

1. Accedi al [portale di Azure](https://portal.azure.com/).
1. Selezionare l'applicazione Azure AD B2C creata per l'accesso al sito.
1. Selezionare l'applicazione creata durante la configurazione di Azure AD.
1. Sotto **URL di risposta**, assicurarsi che l'elenco includa voci per l'URL del dominio del sito e per l'URL generato dall'e-commerce, come mostrato nell'esempio nella figura seguente.

    ![Voci dell'URL di risposta Azure AD B2C.](media/aad-b2c-reply-url.jpg)

> [!NOTE]
> L'URL del dominio del sito e l'URL generato dall'e-commerce devono essere in un formato URL valido che non include barre iniziali o finali.

## <a name="additional-resources"></a>Risorse aggiuntive

[Registrare un'applicazione Web in Azure Active Directory B2C](/azure/active-directory-b2c/tutorial-register-applications?tabs=app-reg-ga#register-a-web-application)

[Impostare un tenant B2C in Commerce](../set-up-b2c-tenant.md)