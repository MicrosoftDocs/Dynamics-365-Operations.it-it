---
title: Importare dati storici per le previsioni della domanda
description: Per ottenere le previsioni della domanda accurate, sono necessari i dati storici della domanda per singolo articolo o chiave di allocazione articolo. In questo argomento viene descritto come utilizzare le entità di dati per importare i dati storici della domanda da un sistema, in modo da disporre di uno storico più ampio dei dati di previsione della domanda.
author: roxanadiaconu
manager: tfehr
ms.date: 05/10/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqDemPlanCreateForecastDialog
audience: Application User
ms.reviewer: kamaybac
ms.assetid: 59c0d269-9db0-48e7-b8c7-9a388781a9ca
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d6ba2e1a3a884d29bff491f914aa2d5f9ece2b84
ms.sourcegitcommit: 79621e667cd7f48ba3bdbf2731f6f33d8e9f57f6
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/10/2021
ms.locfileid: "5154229"
---
# <a name="import-historical-data-for-demand-forecasts"></a>Importare dati storici per le previsioni della domanda

[!include [banner](../includes/banner.md)]

Per contribuire a garantire la correttezza delle previsioni della domanda, sono necessari tutti i dati storici della domanda che si possono ottenere per singolo articolo o chiave di allocazione articolo. Se i dati storici della domanda non sono stati ancora importati, utilizzare l'entità di dati **Domanda esterna storica** (ReqDemPlanHistoricalExternalDemandEntity) in Dynamics 365 Supply Chain Management per importarli.

Nell'area di lavoro **Gestione dei dati**, è possibile visualizzare una panoramica di tutti i campi relativi all'entità.

1. Aprire l'area di lavoro **Gestione dei dati**.
2. Selezionare il riquadro **Entità di dati**.
3. Ricercare nell'elenco delle entità **Domanda esterna storica**.
4. Selezionare **Campi di destinazione**. I seguenti campi di entità sono obbligatori: sito (**DeliveringSiteId**), data (**DemandDate**), quantità (**DemandQuantity**) e numero di articolo (**ItemNumber**) o chiave di allocazione articolo (**ProductAllocationKeyId**).

Per utilizzare questa entità di dati, è necessario disporre di un file di Microsoft Excel o un file con valori separati da virgole (CSV) contenente i dati storici della domanda. Nel seguente esempio viene illustrato come importare i dati da un file CSV.

Per ulteriori informazioni su come importare i dati, incluso come pulire i dati dopo un'importazione, vedere [Panoramica dei processi di importazione ed esportazione dei dati](../../fin-ops-core/dev-itpro/data-entities/data-import-export-job.md) ed argomenti correlati.

## <a name="example"></a>Esempio

È possibile utilizzare il seguente file come esempio. Scaricare [HistoricalDemandData](https://docs.microsoft.com/dynamics/s-e/). Questo file contiene i dati storici della domanda per l'articolo D0001. Contiene solo i seguenti campi obbligatori: sito, quantità e data della domanda.

1. Selezionare la società in cui importare i dati storici della domanda.
2. Aprire l'area di lavoro **Gestione dei dati**.
3. Selezionare il riquadro **Importa**.
4. Immettere un nome per il progetto di importazione, ad esempio **Importare dati storici della domanda per l'articolo D0001**.
5. Nel campo **Formato dati di origine**, selezionare il formato del file da importare. Per importare il file HistoricalDemandData per questo esempio, selezionare **CSV**.
6. Nel campo **Nome entità**, selezionare **Domanda esterna storica**.
7. Salvare il file nel computer e quindi caricarlo.
8. Selezionare **Importa**.
9. La pagina **Riepilogo esecuzione** viene visualizzata automaticamente. Verificare i dati importati nella pagina.

Dopo aver importato i dati storici della domanda, è possibile generare una previsione della domanda.

## <a name="additional-resources"></a>Risorse aggiuntive

[Generare una previsione di base statistica](generate-statistical-baseline-forecast.md)  
[Panoramica processi di importazione ed esportazione dati](../../fin-ops-core/dev-itpro/data-entities/data-import-export-job.md)
