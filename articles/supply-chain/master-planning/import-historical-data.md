---
title: Importare dati storici per le previsioni della domanda
description: Per ottenere le previsioni della domanda accurate, sono necessari i dati storici della domanda per singolo articolo o chiave di allocazione articolo. In questo argomento viene descritto come utilizzare le entità di dati per importare i dati storici della domanda da un sistema, in modo da disporre di uno storico più ampio dei dati di previsione della domanda.
author: t-benebo
ms.date: 05/10/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqDemPlanCreateForecastDialog
audience: Application User
ms.reviewer: kamaybac
ms.assetid: 59c0d269-9db0-48e7-b8c7-9a388781a9ca
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c52d27d6e3aa8a20d6cc1dc81e4ade981c6a8091
ms.sourcegitcommit: ad1afc6893a8dc32d1363395666b0fe1d50e983a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2022
ms.locfileid: "8470403"
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

Vedi anche [Generare una previsione di base statistica](generate-statistical-baseline-forecast.md).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]