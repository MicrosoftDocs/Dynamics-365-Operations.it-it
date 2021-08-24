---
title: Migliorare il modello di previsione (anteprima)
description: In questo argomento vengono descritte le funzionalità che puoi utilizzare per migliorare le prestazioni dei modelli di previsione.
author: ShivamPandey-msft
ms.date: 07/16/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-05-28
ms.dyn365.ops.version: AX 10.0.8
ms.openlocfilehash: 0bf4dd0f7edc528393af628eb3776c32957c459d3eaa166b0bc54d9318b54916
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6768797"
---
# <a name="improve-the-prediction-model-preview"></a>Migliorare il modello di previsione (anteprima)

[!include [banner](../includes/banner.md)]

In questo argomento vengono descritte le funzionalità che puoi utilizzare per migliorare le prestazioni dei modelli di previsione. Il miglioramento del tuo modello inizia nell'area di lavoro **Previsioni di pagamento dei clienti** in Microsoft Dynamics 365 Finance. I passaggi di miglioramento vengono quindi completati in AI Builder.

## <a name="select-historical-outcomes"></a>Selezionare risultati cronologici

Seleziona prima uno o più dei tre possibili risultati per le fatture: **Puntuale**, **In ritardo** e **Molto in ritardo**. Tutti e tre i risultati dovrebbero essere selezionati. Se deselezioni la selezione di uno qualsiasi dei risultati, le fatture verranno escluse dal processo di training e l'accuratezza della previsione verrà ridotta.

[![Conferma dei risultati.](./media/confirm-3-outcomes.png)](./media/confirm-3-outcomes.png)

Se la tua organizzazione richiede solo due risultati, modifica le soglie **In ritardo** e **Molto in ritardo** su 0 (zero) giorni. In questo modo, si comprime efficacemente la previsione in uno stato binario di **Puntuale** o **In ritardo**.

## <a name="select-fields"></a>Seleziona campi

Quando selezioni i campi da includere nel modello, tieni presente che l'elenco include tutti i campi disponibili nella tabella Microsoft Dataverse mappata ai dati data lake di Azure. Alcuni di questi campi **non** dovrebbero essere selezionati. I campi che non dovrebbero essere selezionati rientrano in una delle tre categorie:

- Il campo è obbligatorio per la tabella Dataverse, ma non ci sono dati di supporto per essa nel data lake.
- Il campo è un ID e quindi non ha senso per una funzionalità di apprendimento automatico.
- Il campo rappresenta le informazioni che non saranno disponibili durante la previsione.

Le sezioni seguenti mostrano i campi disponibili per la fattura e le entità cliente ed elencano i campi che **non** dovrebbero essere selezionati per il training. La categoria specificata per ciascuno di questi campi fa riferimento alle categorie nell'elenco precedente.
 
### <a name="invoice-dataverse-table"></a>Tabella delle fatture Dataverse

Nella figura seguente vengono mostrati i campi disponibili per la tabella fattura.

[![Campi disponibili per la tabella fattura.](./media/available-fields.png)](./media/available-fields.png)

I seguenti campi non devono essere selezionati per il training:

- **Conto fattura** (categoria 2)
- **È chiuso** (categoria 3): questo campo viene utilizzato per filtrare le fatture per il training (chiuso) e la previsione (non chiuso).
- **Nome** (categoria 1)
- **ID origine** (categoria 2)
- **Record di origine** (categoria 2)
- **Tabella di origine** (categoria 2)

### <a name="customer-dataverse-table"></a>Tabella clienti Dataverse

Nella figura seguente vengono mostrati i campi disponibili per la tabella cliente.

[![Campi disponibili per la tabella cliente.](./media/related-entities.png)](./media/related-entities.png)

Il campo seguente non deve essere selezionato per il training:

- **Chiave univoca riga** (categoria 2)

## <a name="filters"></a>Filtri

È possibile filtrare le fatture utilizzate per la formazione impostando criteri filtro per i campi nella fattura o nelle tabelle cliente. Ad esempio, è possibile impostare una soglia per includere solo le fatture il cui il totale è uguale o superiore a un importo specifico. In alternativa, è possibile escludere le fatture associate ai clienti in uno specifico gruppo di clienti.

Per ulteriori informazioni sul filtraggio dei dati, vedere [Creare un modello di previsione](https://docs.microsoft.com/ai-builder/prediction-create-model#filter-your-data).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
