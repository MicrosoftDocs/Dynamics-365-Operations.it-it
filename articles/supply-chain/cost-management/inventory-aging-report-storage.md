---
title: Archiviazione report di aging delle scorte
description: Questo argomento descrive la funzionalità che consente di eseguire un report di aging dell'inventario e di rendere disponibile l'output come modulo e grafico.
author: AndersGirke
manager: tfehr
ms.date: 11/11/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CostAdminWorkspace, CostAnalysisWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: aevengir
ms.search.validFrom: 2019-01-10
ms.dyn365.ops.version: ''
ms.openlocfilehash: 9148a9032615222a1fdfe453488e716bacadbabc
ms.sourcegitcommit: e06da171b9cba8163893e30244c52a9ce0901146
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "3275581"
---
# <a name="inventory-aging-report-storage"></a>Archiviazione report di aging delle scorte


[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

In Microsoft Dynamics 365 Supply Chain Management, è possibile eseguire un report **Archiviazione report di aging delle scorte** e rendere l'output disponibile come modulo e grafico. Nel modulo, le colonne e i saldi aggregati vengono modificati in modo dinamico, a seconda del layout configurato. Il grafico offre una panoramica visiva che supporta il filtro e consente di approfondire i dettagli. Inoltre, un'entità dati denominata **Report aging delle scorte** consente di esportare i risultati di un report **Archiviazione report di aging delle scorte** eseguito in un formato file Microsoft Excel o un file PDF.

Questo metodo di esecuzione del report **Archiviazione report di aging delle scorte** è utile nei casi in cui l'output contiene più righe. Ad esempio, l'output contiene molte righe se si dispone di 50.000 articoli e 300 negozi creati come magazzini e si richiede l'aging delle scorte per articolo, sito e magazzino.

## <a name="enable-the-inventory-value-storage-report-feature"></a>Abilitare la funzione report di archiviazione valori di magazzino

Prima di utilizzare questa funzionalità, è necessario abilitarla nel sistema. Gli amministratori possono utilizzare le impostazioni della [gestione delle funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) per controllare lo stato della funzione e abilitarla se necessario. La funzione viene elencata come:

- **Modulo** - Gestione costi
- **Nome della funzione** - Archiviazione report di aging delle scorte

## <a name="run-an-inventory-aging-report-storage"></a>Eseguire un'archiviazione report di aging delle scorte

1. Passare **Gestione costi \> Richieste di informazioni e report \> Archiviazione del report di aging delle scorte**.
1. Selezionare **Nuovo**.
1. Nel campo **Identificatore processo - Nome** immettere un nome univoco per il report.
1. Selezionare il report **Identificazione - ID** e filtrarlo come necessario.

    L'esecuzione del report è sempre effettuata in un processo batch.

1. Al termine del processo batch, l'output viene visualizzato nella pagina **Archiviazione del report di aging delle scorte**.
1. Per visualizzare l'output come modulo con un layout tradizionale a griglia, selezionare **Visualizza dettagli**. Per visualizzare l'output sotto forma di grafico aggregato, selezionare **Visualizza grafico**.

    > [!NOTE]
    > Nel modulo non vengono inclusi i subtotali che sono definiti nel layout del report.

L'entità di dati **Report di aging delle scorte** consente di esportare l'output di un report **Archiviazione report di aging delle scorte** applicando un filtro per il campo **Identificatore di processo - Nome** in qualsiasi formato supportato della gestione dei dati.
