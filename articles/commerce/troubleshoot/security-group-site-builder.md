---
title: Impossibile configurare un gruppo di sicurezza per Creazione di siti di Commerce durante la distribuzione iniziale
description: Questo argomento fornisce indicazioni per la risoluzione dei problemi che possono essere utili quando il gruppo di sicurezza Microsoft Azure Active Directory (Azure AD) per Creazione di siti di Commerce non appare come opzione quando si creano componenti di e-commerce in Microsoft Dynamics Lifecycle Services (LCS) durante la distribuzione iniziale di un nuovo tenant di e-commerce.
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
ms.author: shajain
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 36ea43e19f395e3914d3eda1a9b8f5487b0926c5
ms.sourcegitcommit: 6c108be3378b365e6ec596a1a8666d59b758db25
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2021
ms.locfileid: "5585396"
---
# <a name="cant-configure-a-security-group-for-commerce-site-builder-during-initial-deployment"></a>Impossibile configurare un gruppo di sicurezza per Creazione di siti di Commerce durante la distribuzione iniziale

[!include [banner](../../includes/banner.md)]

Questo argomento fornisce indicazioni per la risoluzione dei problemi che possono essere utili quando il gruppo di sicurezza Microsoft Azure Active Directory (Azure AD) per Creazione di siti di Commerce non appare come opzione quando si creano componenti di e-commerce in Microsoft Dynamics Lifecycle Services (LCS) durante la distribuzione iniziale di un nuovo tenant di e-commerce.

## <a name="description"></a>Descrizione

Quando si creano i componenti di e-commerce come parte del processo di distribuzione di un nuovo tenant di e-commerce che include il componente Creazione di siti di Commerce, il gruppo di sicurezza Azure AD non viene visualizzato come opzione nella finestra di dialogo.

## <a name="resolution"></a>Risoluzione

### <a name="provision-the-e-commerce-site-with-a-user-in-the-correct-tenant"></a>Effettuare il provisioning del sito di e-commerce con un utente nel tenant corretto

1. Accedi al [portale di Azure](https://portal.azure.com/).
1. Sotto il tenant per cui è stato eseguito il provisioning del progetto LCS per il sito di e-commerce, seguire le istruzioni in [Creare un gruppo di base e aggiungere membri utilizzando Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal).
1. Accedere a [LCS](https://lcs.dynamics.com/) utilizzando un account che condivide lo stesso tenant del gruppo di sicurezza Azure AD appena creato. L'account deve avere accesso per visualizzare il gruppo di sicurezza Azure AD.
1. Completa i passaggi di configurazione per configurare il sito di e-commerce. Quando si esegue il provisioning dei componenti di e-commerce, il gruppo di sicurezza deve apparire come opzione nella finestra di dialogo.

> [!NOTE]
> Per assicurarsi che il campo nella finestra di dialogo sia riempito con l'elenco di gruppi di sicurezza, è necessario selezionare **Immetti** dopo aver inserito il nome del gruppo di sicurezza Azure AD creato. I risultati della ricerca elencheranno tutti i gruppi di sicurezza Azure AD che iniziano con il testo di ricerca e a cui l'utente ha accesso. È possibile utilizzare un termine di ricerca più breve per consentire risultati di ricerca più ampi.

## <a name="additional-resources"></a>Risorse aggiuntive

[Creare un gruppo di base e aggiungere membri utilizzando Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)

[Distribuire un nuovo tenant di e-commerce](../deploy-ecommerce-site.md)
