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
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-06-01
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 716afdc4e52c3e4a0432b987cb82077012d4d0c2
ms.sourcegitcommit: a8ac6d9b63eb67d14dd17a086ef4f1eccd7f9fc1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2021
ms.locfileid: "7431512"
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

Se un flusso di lavoro di richiesta per l'acquisto e la vendita di congedi non riesce, gli utenti con il privilegio **EssLeaveBuySellRequestApprover** possono rivedere il registro dei messaggi per tutte le richieste di acquisto e vendita di congedi. Per farlo, andare a **Congedo e assenza > Collegamenti > Richieste di acquisto e vendita congedo > Registro messaggi** (in alto a sinistra). Il **registro messaggi** mostra agli utenti come sono state elaborate le transazioni e la cronologia del flusso di lavoro associata.


## <a name="see-also"></a>Vedere anche

[Panoramica di congedo e assenza](hr-leave-and-absence-overview.md)</br>
[Gestire i criteri di acquisto e vendita congedo](hr-leave-and-absence-manage-buy-and-sell-leave-policies.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
