---
title: Il collegamento di accesso reindirizza a un sito di e-commerce
description: Questo argomento fornisce indicazioni per la risoluzione dei problemi che possono essere utili quando un collegamento di accesso reindirizza al sito di e-commerce anziché alla pagina di accesso.
author: Reza-Assadi
manager: AnnBe
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.service: dynamics-365-retail
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
ms.openlocfilehash: 36f10c9f68570a6c67da6b4b6e4155f4634f633a
ms.sourcegitcommit: 6c108be3378b365e6ec596a1a8666d59b758db25
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2021
ms.locfileid: "5585385"
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

    ![Voci dell'URL di risposta Azure AD B2C](media/aad-b2c-reply-url.jpg)

> [!NOTE]
> L'URL del dominio del sito e l'URL generato dall'e-commerce devono essere in un formato URL valido che non include barre iniziali o finali.

## <a name="additional-resources"></a>Risorse aggiuntive

[Registrare un'applicazione Web in Azure Active Directory B2C](https://docs.microsoft.com/azure/active-directory-b2c/tutorial-register-applications?tabs=app-reg-ga#register-a-web-application)

[Impostare un tenant B2C in Commerce](../set-up-b2c-tenant.md)
