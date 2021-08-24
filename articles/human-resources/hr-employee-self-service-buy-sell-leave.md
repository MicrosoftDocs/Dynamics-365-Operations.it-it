---
title: Acquista e vendi congedo
description: In Dynamics 365 Human Resources, è possibile inviare richieste di acquisto e vendita di congedi in base ai criteri di acquisto e vendita stabiliti dalla società.
author: andreabichsel
ms.date: 08/20/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ESSLeaveBuyRequestEntry, EssWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-06-01
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 1225bcfd0c7c9dfecde2aec54983fca8a298f1cf92d2929d8b1fbe2bdf05e5f9
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6779736"
---
# <a name="buy-and-sell-leave"></a>Acquista e vendi congedo

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

Se un flusso di lavoro di richiesta per l'acquisto e la vendita di congedi non riesce, gli utenti con il privilegio **EssLeaveBuySellRequestApprover** possono rivedere il registro dei messaggi per tutte le richieste di acquisto e vendita di congedi. Per farlo, vai su **Congedo e assenza > Collega > Acquista e vendi richieste di congedo > Registro messaggi** (in alto a sinistra). Il **registro messaggi** mostra agli utenti come sono state elaborate le transazioni e la cronologia del flusso di lavoro associata.


## <a name="see-also"></a>Vedere anche

[Panoramica di congedo e assenza](hr-leave-and-absence-overview.md)</br>
[Gestire i criteri di acquisto e vendita congedo](hr-leave-and-absence-manage-buy-and-sell-leave-policies.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
