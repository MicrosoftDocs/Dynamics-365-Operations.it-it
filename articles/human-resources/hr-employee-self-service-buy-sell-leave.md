---
title: Acquista e vendi congedo
description: Questo argomento descrive come inviare richieste di acquisto e vendita congedo in Dynamics 365 Human Resources.
author: twheeloc
ms.date: 08/26/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ESSLeaveBuyRequestEntry, EssWorkspace
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-06-01
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 695840516849dcfeb69895f6808d828d5878c59b
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2022
ms.locfileid: "8688178"
---
# <a name="buy-and-sell-leave"></a>Acquistare e vendere congedo


>[!Important]
>La funzionalità indicata in questo argomento è attualmente disponibile per i clienti di Dynamics 365 Human Resources standalone. Alcune o tutte le funzionalità saranno disponibili come parte di una versione futura dell'infrastruttura Finance dopo la versione Finance 10.0.26.

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

In Dynamics 365 Human Resources, è possibile inviare richieste di acquisto e vendita di congedi in base ai criteri di acquisto e vendita stabiliti dalla società.  

## <a name="request-to-buy-leave"></a>Richiesta di acquisto di congedi

1. Nell'area di lavoro **Self-service dipendenti**, seleziona **Richiesta di acquisto di congedi** nel riquadro **Saldi permessi**. 

2. Aggiungere un **Tipo di congedo** e immettere una **Quantità** per la quantità di congedi che si desidera acquistare. 

3. Selezionare **Invia** quando si è pronti per inviare la richiesta. 

I saldi verranno aggiornati automaticamente o verranno sottoposti a un processo di approvazione prima dell'aggiornamento. Dipende da come sono stati configurati i criteri di acquisto.

## <a name="request-to-sell-leave"></a>Richiesta di vendita di congedi

1. Nell'area di lavoro **Self-service dipendenti**, selezionare **Richiesta di vendita di congedi** nel riquadro **Saldi permessi**. 

2. Aggiungere un **Tipo di congedo** e immettere una **Quantità** per la quantità di congedi che si desidera vendere. 

3. Selezionare **Invia** quando si è pronti per inviare la richiesta.

I saldi verranno aggiornati automaticamente o verranno sottoposti a un processo di approvazione prima dell'aggiornamento. Dipende da come sono stati configurati i criteri di acquisto.


## <a name="troubleshooting"></a>Risoluzione dei problemi 

Se un flusso di lavoro di richiesta per l'acquisto e la vendita di congedi non riesce, gli utenti con il privilegio **EssLeaveBuySellRequestApprover** possono rivedere il registro dei messaggi per tutte le richieste di acquisto e vendita di congedi. Per farlo, andare a **Congedo e assenza > Collegamenti > Richieste di acquisto e vendita congedo > Registro messaggi** (in alto a sinistra). Il **registro messaggi** mostra agli utenti come sono state elaborate le transazioni e la cronologia del flusso di lavoro associata.


## <a name="see-also"></a>Vedere anche

[Panoramica di congedo e assenza](hr-leave-and-absence-overview.md)</br>
[Gestire i criteri di acquisto e vendita congedo](hr-leave-and-absence-manage-buy-and-sell-leave-policies.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
