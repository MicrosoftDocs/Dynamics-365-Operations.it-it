---
title: Importare dati storici per le previsioni della domanda
description: "Per ottenere le previsioni della domanda accurate, sono necessari i dati storici della domanda per singolo articolo o chiave di allocazione articolo. In questo argomento viene descritto come utilizzare le entità di dati per importare i dati storici della domanda da un sistema, in modo da disporre di uno storico più ampio dei dati di previsione della domanda."
author: YuyuScheller
manager: AnnBe
ms.date: 05/10/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.assetid: 59c0d269-9db0-48e7-b8c7-9a388781a9ca
ms.search.region: Global
ms.author: roxanad
ms.search.validFrom: 2016-11-30T00:00:00.000Z
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: 957626a283b750645adefa5176480e68cc27e4f1
ms.contentlocale: it-it
ms.lasthandoff: 06/13/2017

---

# <a name="import-historical-data-for-demand-forecasts"></a>Importare dati storici per le previsioni della domanda

[!include[banner](../includes/banner.md)]

Per contribuire a garantire la correttezza delle previsioni della domanda, sono necessari tutti i dati storici della domanda che si possono ottenere per singolo articolo o chiave di allocazione articolo. Se i dati storici della domanda non sono stati ancora importati, utilizzare l'entità di dati **Domanda esterna storica** (ReqDemPlanHistoricalExternalDemandEntity) in Microsoft Dynamics 365 for Finance and Operations per importarli.

Nell'area di lavoro **Gestione dei dati**, è possibile visualizzare una panoramica di tutti i campi relativi all'entità.

1. Aprire l'area di lavoro **Gestione dei dati**.
2. Fare clic sul riquadro **Entità di dati**.
3. Ricercare nell'elenco delle entità **Domanda esterna storica**.
4. Fare clic su **Campi di destinazione**. I seguenti campi di entità sono obbligatori: sito (**DeliveringSiteId**), data (**DemandDate**), quantità (**DemandQuantity**) e numero di articolo (**ItemNumber**) o chiave di allocazione articolo (**ProductAllocationKeyId**).

Per utilizzare questa entità di dati, è necessario disporre di un file di Microsoft Excel o un file con valori separati da virgole (CSV) contenente i dati storici della domanda. Nel seguente esempio viene illustrato come importare i dati da un file CSV.

## <a name="example"></a>Esempio

È possibile utilizzare il seguente file come esempio. Scaricare [HistoricalDemandData](https://mbs.microsoft.com/customersource/northamerica/AX/learning/documentation/how-to-articles/365OperationsDemandForecast). Questo file contiene i dati storici della domanda per l'articolo D0001. Contiene solo i seguenti campi obbligatori: sito, quantità e data della domanda.

1. Selezionare la società in cui importare i dati storici della domanda.
2. Aprire l'area di lavoro **Gestione dei dati**.
3. Fare clic sul riquadro **Importa**.
4. Immettere un nome per il progetto di importazione, ad esempio **Importare dati storici della domanda per l'articolo D0001**.
5. Nel campo **Formato dati di origine**, selezionare il formato del file da importare. Per importare il file HistoricalDemandData per questo esempio, selezionare **CSV**.
6. Nel campo **Nome entità**, selezionare **Domanda esterna storica**.
7. Salvare il file nel computer e quindi caricarlo.
8. Fare clic su **Importa**.
9. La pagina **Riepilogo esecuzione** viene visualizzata automaticamente. Verificare i dati importati nella pagina.

Dopo aver importato i dati storici della domanda, è possibile generare una previsione della domanda.

## <a name="see-also"></a>Vedere anche

[Generare una previsione di base statistica](generate-statistical-baseline-forecast.md)

