---
title: Consente di verificare l&quot;accuratezza di previsione
description: "In questo articolo viene descritto i tipi di accuratezze programmate di Microsoft Dynamics 365 per le operazioni vengono calcolati e illustra come è possibile visualizzare i valori di accuratezza."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 72863
ms.assetid: 810a0d63-f4c6-4167-b2b3-a178b74ead89
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: d3f88a4fa54217cea909c54955de05e2175db0cd
ms.lasthandoff: 03/29/2017


---

# <a name="monitor-forecast-accuracy"></a>Consente di verificare l'accuratezza di previsione

In questo articolo viene descritto i tipi di accuratezze programmate di Microsoft Dynamics 365 per le operazioni vengono calcolati e illustra come è possibile visualizzare i valori di accuratezza.

Dynamics 365 per le operazioni vengono calcolati i seguenti tipi di accuratezze programmate:

-   Previsione di precisione storica, confrontando la previsione storica utilizzata nella pianificazione generale con la domanda storica. Per visualizzare i valori (sia i valori assoluti che i valori percentuali) per la precisione di previsione storica, fare clic su **Visualizza precisione** nella pagina **Dettagli previsione della domanda**.
-   Precisione stimata del modello previsionale utilizzato per generare previsioni. È possibile visualizzare la percentuale di previsione in **Dettagli modello - Errore medio assoluto percentuale** nella pagina **Dettagli previsione della domanda**. 

** Nota: ** Se si utilizza Dynamics 365 per l'utilizzo di apprendimento automatico di Microsoft Azure di previsione della domanda operazioni, il calcolo di precisione di modelli interna è basato sul set di dati di test. Per specificare la dimensione del set di dati di test, impostare PERCENT ** STABILITO\_di DIMENSIONE\_\_del TEST ** il parametro ** parametri di previsione della domanda ** nella pagina. Ad esempio, se si imposta il valore su **20**, l'ultimo 20% dei dati storici verrà utilizzato per calcolare la previsione del modello interno.


<a name="see-also"></a>Vedere anche
--------

[Authorizing the adjusted forecast](authorize-adjusted-forecast.md)

[Remove outliers from historical transaction data when calculating a demand forecast](remove-historical-outliers-calculating-demand-forecast.md)


