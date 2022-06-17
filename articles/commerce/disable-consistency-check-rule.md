---
title: Disabilitare le regole usate nel processo di convalida delle transazioni
description: In questo articolo viene descritta la funzionalità per disabilitare le regole di convalida delle transazioni in Microsoft Dynamics 365 Commerce.
author: analpert
ms.date: 12/11/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: ''
ms.openlocfilehash: 7d566aa3b829dad281528925a341382f9637fdba
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8884878"
---
# <a name="disable-rules-used-in-the-transaction-validation-process"></a>Disabilitare le regole usate nel processo di convalida delle transazioni

[!include [banner](../includes/banner.md)]

Ogni rivenditore può avere scenari e processi aziendali molto specifici. Non tutte le regole incluse nel processo di convalida delle transazioni di commercio sono pertanto applicabili a tutti i rivenditori. Per soddisfare le diverse esigenze, Microsoft Dynamics 365 Commerce offre funzionalità che possono essere usate per disabilitare le regole che non sono applicabili.

Per visualizzare l'elenco delle regole disponibili nel processo di convalida delle transazioni nel proprio ambiente e visualizzare lo stato di ciascuna regola, andare a **Retail e Commerce \> Impostazione sedi centrali \> Parametri \> Parametri Commerce** e selezionare la scheda **Convalida transazioni**. Tutte le regole abilitate vengono usate per convalidare le transazioni durante il processo **Convalida transazioni punto vendita**. La convalida deve inoltre essere superata affinché le transazioni vengano raccolte e registrate in un rendiconto transazionale.

Per impostazione predefinita, lo stato di ogni regola è impostato su **Abilitato**. Tutte le regole vengono pertanto usate per convalidare le transazioni affinché possano essere inserite nei rendiconti transazionali. Per disabilitare una regola, modificarne lo stato in **Disabilitato**. Le regole disabilitate non vengono prese in considerazione per convalidare le transazioni durante il processo **Convalida transazioni punto vendita**.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
