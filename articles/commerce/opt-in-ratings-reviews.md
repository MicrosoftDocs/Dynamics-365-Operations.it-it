---
title: Consentire l'utilizzo di valutazioni e recensioni
description: In questo argomento viene descritto come consentire l'utilizzo di valutazioni e recensioni sul sito di Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
manager: annbe
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: gmohanv
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 10e3c33af232fa46df09a103b2e73eae09a909eb
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/01/2019
ms.locfileid: "2697982"
---
# <a name="opt-in-to-use-ratings-and-reviews"></a>Consentire l'utilizzo di valutazioni e recensioni

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

In questo argomento viene descritto come consentire l'utilizzo di valutazioni e recensioni sul sito di Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Panoramica

La soluzione con valutazioni e recensioni è una soluzione multicanale che è possibile rendere disponibile in Dynamics 365 Commerce mediante Microsoft Dynamics Lifecycle Services (LCS). LCS è un portale di amministrazione che i rivenditori utilizzano per gestire i loro ambienti dal provisioning alla rimozione.

Se si desidera utilizzare la soluzione con valutazioni e recensioni sul sito Web di Commerce, è necessario dapprima consentirne l'utilizzo.

## <a name="opt-in-to-use-ratings-and-reviews"></a>Consentire l'utilizzo di valutazioni e recensioni

Per consentire l'utilizzo di valutazioni e recensioni sul sito, procedere come segue.

1. Seguire i passaggi in [Distribuire un nuovo sito di e-Commerce](deploy-ecommerce-site.md).
1. Quando si è ancora in LCS, andare a **Configurazione distribuzione Retail \> Altre impostazioni**.
1. Impostare l'opzione **Abilita servizio Valutazioni e recensioni** su **Sì**.
1. Nel campo **Gruppo di sicurezza ADD per moderatore di valutazioni e recensioni (ID oggetto gruppo di sicurezza)**, immettere l'ID gruppo di sicurezza di Microsoft Azure Active Directory (Azure AD) che include moderatori di valutazioni e recensioni.

    ![Consentire l'utilizzo di valutazioni e recensioni](media/LCS_RnR_Preference.png)

1. Completare il processo di inizializzazione di e-Commerce.

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica valutazioni e recensioni](ratings-reviews-overview.md)

[Gestire valutazioni e recensioni](manage-reviews.md)

[Configurare valutazioni e recensioni](configure-ratings-reviews.md)

[Sincronizzare valutazioni sul prodotto in Dynamics 365 Retail](sync-product-ratings.md)
