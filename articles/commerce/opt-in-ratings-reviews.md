---
title: Consentire l'utilizzo di valutazioni e recensioni
description: In questo argomento viene descritto come consentire l'utilizzo di valutazioni e recensioni sul sito di Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 01/30/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: gmohanv
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 9fe8e9403ccbdc1e26620ae33c6a3866af06b23c
ms.sourcegitcommit: 81bc42551e6c9af6ad38908afb606ee1f8d3c44b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/03/2021
ms.locfileid: "7473431"
---
# <a name="opt-in-to-use-ratings-and-reviews"></a>Consentire utilizzo di valutazioni e sulle revisioni

[!include [banner](includes/banner.md)]

In questo argomento viene descritto come consentire l'utilizzo di valutazioni e recensioni sul sito di Microsoft Dynamics 365 Commerce.

La soluzione con valutazioni e recensioni è una soluzione multicanale che è possibile rendere disponibile in Dynamics 365 Commerce mediante Microsoft Dynamics Lifecycle Services (LCS). LCS è un portale di amministrazione che i rivenditori utilizzano per gestire i loro ambienti dal provisioning alla rimozione.

Se si desidera utilizzare la soluzione con valutazioni e recensioni sul sito Web di Commerce, è necessario consentire l'utilizzo di valutazioni e recensioni durante la distribuzione del sito di e-commerce in Dynamics 365 Commerce.

## <a name="opt-in-to-use-ratings-and-reviews"></a>Consentire utilizzo di valutazioni e sulle revisioni

Per consentire l'utilizzo di valutazioni e recensioni sul sito, procedere come segue.

1. Seguire i passaggi in [Distribuire un nuovo sito di e-Commerce](deploy-ecommerce-site.md).
1. Quando si è ancora in LCS, andare a **Configurazione distribuzione Retail \> Altre impostazioni**.
1. Impostare l'opzione **Abilita servizio Valutazioni e recensioni** su **Sì**.
1. Nel campo **Gruppo di sicurezza ADD per moderatore di valutazioni e recensioni (ID oggetto gruppo di sicurezza)**, immettere l'ID gruppo di sicurezza di Microsoft Azure Active Directory (Azure AD) che include moderatori di valutazioni e recensioni.

    ![Consentire utilizzo di valutazioni e recensioni.](media/LCS_RnR_Preference.png)

1. Completare il processo di inizializzazione di e-Commerce.

> [!NOTE] 
> Se si è un cliente Dynamics 365 Commerce esistente che ha già distribuito un sito di e-commerce senza aver fornito il consenso per l'utilizzo di valutazioni e recensioni e ora si desidera utilizzare valutazioni e recensioni del pacchetto Dynamics 365 Commerce, inviare una richiesta di assistenza. Per informazioni su come inviare una richiesta di assistenza, vedere [Processo per inviare richieste di servizio](../fin-ops-core/dev-itpro/lifecycle-services/submit-request-dynamics-service-engineering-team.md?toc=/dynamics365/commerce/toc.json). 

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica valutazioni e revisioni](ratings-reviews-overview.md)

[Gestire valutazioni e recensioni](manage-reviews.md)

[Configurare valutazioni e recensioni](configure-ratings-reviews.md)

[Sincronizzare valutazioni sul prodotto in Dynamics 365 Commerce](sync-product-ratings.md)




[!INCLUDE[footer-include](../includes/footer-banner.md)]
