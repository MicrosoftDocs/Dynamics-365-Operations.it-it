---
title: Monitorare la precisione della previsione
description: In questo argomento vengono descritti i tipi di previsione di previsione calcolati in Dynamics 365 Supply Chain Management e viene illustrato come è possibile visualizzare i valori di previsione.
author: roxanadiaconu
manager: tfehr
ms.date: 01/07/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqDemPlanForecastDetails
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 72863
ms.assetid: 810a0d63-f4c6-4167-b2b3-a178b74ead89
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ab74ba88ba9eb683107ef82bc105f5a3ed8fac08
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2020
ms.locfileid: "3209814"
---
# <a name="monitor-forecast-accuracy"></a>Monitorare la precisione della previsione

[!include [banner](../includes/banner.md)]

In questo argomento vengono descritti i tipi di previsione di previsione calcolati in Microsoft Dynamics 365 Supply Chain Management e viene illustrato come è possibile visualizzare i valori di previsione.

Supply Chain Management calcola i seguenti tipi di precisione della previsione:

-   Previsione di precisione storica, confrontando la previsione storica utilizzata nella pianificazione generale con la domanda storica. Per visualizzare i valori (sia i valori assoluti che i valori percentuali) per la precisione di previsione storica, fare clic su **Visualizza precisione** nella pagina **Dettagli previsione della domanda**.
-   Precisione stimata del modello previsionale utilizzato per generare previsioni. È possibile visualizzare la percentuale di previsione in **Dettagli modello - Errore medio assoluto percentuale** nella pagina **Dettagli previsione della domanda**. 

> [!NOTE]
> Se si utilizza Microsoft Azure Machine Learning di previsione della domanda, il calcolo della precisione del modello interno si basa sul set di dati di prova. Per specificare le dimensioni del set di dati di prova, impostare il parametro **TEST\_SET\_SIZE\_PERCENT** nella pagina **Parametri di previsione della domanda**. Ad esempio, se si imposta il valore su **20**, l'ultimo 20% dei dati storici verrà utilizzato per calcolare la previsione del modello interno.


<a name="additional-resources"></a>Risorse aggiuntive
--------

[Autorizzare una previsione corretta](authorize-adjusted-forecast.md)

[Eliminare gli outlier dai dati di transazione storici quando si calcolo una previsione della domanda](remove-historical-outliers-calculating-demand-forecast.md)



