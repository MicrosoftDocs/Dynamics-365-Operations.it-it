---
title: Migliorare il modello di previsione (anteprima)
description: In questo argomento vengono descritte le funzionalità che puoi utilizzare per migliorare le prestazioni dei modelli di previsione.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 05/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-05-28
ms.dyn365.ops.version: AX 10.0.8
ms.openlocfilehash: 23c9062dcc13951792306c955b54cae6f656fec5
ms.sourcegitcommit: deb711c92251ed48cdf20ea514d03461c26a2262
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/25/2020
ms.locfileid: "4646081"
---
# <a name="improve-the-prediction-model-preview"></a>Migliorare il modello di previsione (anteprima)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

In questo argomento vengono descritte le funzionalità che puoi utilizzare per migliorare le prestazioni dei modelli di previsione. Il miglioramento del tuo modello inizia nell'area di lavoro **Previsioni di pagamento dei clienti** in Microsoft Dynamics 365 Finance. I passaggi di miglioramento vengono quindi completati in AI Builder.

## <a name="select-historical-outcomes"></a>Selezionare risultati cronologici

Seleziona prima uno o più dei tre possibili risultati per le fatture: **Puntuale**, **In ritardo** e **Molto in ritardo**. Tutti e tre i risultati dovrebbero essere selezionati. Se deselezioni la selezione di uno qualsiasi dei risultati, le fatture verranno escluse dal processo di training e l'accuratezza della previsione verrà ridotta.

[![Conferma dei risultati](./media/confirm-3-outcomes.png)](./media/confirm-3-outcomes.png)

Se la tua organizzazione richiede solo due risultati, modifica le soglie **In ritardo** e **Molto in ritardo** su 0 (zero) giorni. In questo modo, si comprime efficacemente la previsione in uno stato binario di **Puntuale** o **In ritardo**.

## <a name="select-fields"></a>Seleziona campi

Quando selezioni i campi da includere nel modello, tieni presente che l'elenco include tutti i campi disponibili nell'entità Common Data Service mappata ai dati data lake di Azure. Alcuni di questi campi **non** dovrebbero essere selezionati. I campi che non dovrebbero essere selezionati rientrano in una delle tre categorie:

- Il campo è obbligatorio per l'entità Common Data Service, ma non ci sono dati di supporto per essa nel data lake.
- Il campo è un ID e quindi non ha senso per una funzionalità di apprendimento automatico.
- Il campo rappresenta le informazioni che non saranno disponibili durante la previsione.

Le sezioni seguenti mostrano i campi disponibili per la fattura e le entità cliente ed elencano i campi che **non** dovrebbero essere selezionati per il training. La categoria specificata per ciascuno di questi campi fa riferimento alle categorie nell'elenco precedente.
 
### <a name="invoice-common-data-model-entity"></a>Entità Common Data Model fattura

Nella figura seguente vengono mostrati i campi disponibili per l'entità fattura.

[![Campi disponibili per l'entità fattura](./media/available-fields.png)](./media/available-fields.png)

I seguenti campi non devono essere selezionati per il training:

- **Conto fattura** (categoria 2)
- **È chiuso** (categoria 3): questo campo viene utilizzato per filtrare le fatture per il training (chiuso) e la previsione (non chiuso).
- **Nome** (categoria 1)
- **ID origine** (categoria 2)
- **Record di origine** (categoria 2)
- **Tabella di origine** (categoria 2)

### <a name="customer-common-data-model-entity"></a>Entità Common Data Model cliente

Nella figura seguente vengono mostrati i campi disponibili per l'entità cliente.

[![Campi disponibili per l'entità cliente](./media/related-entities.png)](./media/related-entities.png)

Il campo seguente non deve essere selezionato per il training:

- **Chiave univoca riga** (categoria 2)

## <a name="filters"></a>Filtri

I filtri attualmente non supportano lo scenario di previsione dei pagamenti del cliente. Pertanto, seleziona **Ignora questo passaggio** e vai alla pagina di riepilogo.

[![Modello stato attivo con filtri](./media/focus-model-with-filters.png)](./media/focus-model-with-filters.png)

#### <a name="privacy-notice"></a>Informativa sulla privacy
Le anteprime (1) potrebbero utilizzare meno misure di sicurezza e di privacy rispetto al servizio Dynamics 365 Finance and Operations, (2) non sono incluse nel contratto di servizio di questo servizio, (3) non devono essere utilizzate per elaborare i dati personali o altri dati soggetti a requisiti legati e normativi, e (4) hanno supporto limitato.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]