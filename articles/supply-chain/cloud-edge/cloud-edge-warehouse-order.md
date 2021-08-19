---
title: Ordini di magazzino per unità di scala nel cloud e nella rete perimetrale
description: In questo argomento vengono fornite informazioni sulla capacità degli ordini di magazzino utilizzata come parte del carico di lavoro dell'unità di scala di magazzino.
author: perlynne
ms.date: 04/22/2021
ms.topic: article
ms.search.form: WHSWarehouseOrderLine, WHSWarehouseReceiptEntry, PurchTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-04-13
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 4a77b157e9dd5ee1f551cbb59abbc89aaa28d325cc74a77e6624f25902c5b19e
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6731891"
---
# <a name="warehouse-orders-for-cloud-and-edge-scale-units"></a>Ordini di magazzino per unità di scala nel cloud e nella rete perimetrale

[!include [banner](../includes/banner.md)]

> [!WARNING]
> Non tutte le funzionalità aziendali sono completamente supportate nell'anteprima pubblica quando vengono utilizzati i carichi di lavoro delle unità di scala. Se stai utilizzando le unità di scala, assicurati di utilizzare solo i processi che in questo argomento vengono descritti come supportati in modo esplicito.

## <a name="what-are-warehouse-orders"></a>Cosa sono gli ordini di magazzino?

Gli *ordini di magazzino* sono un tipo di ordine creato per supportare le distribuzioni di hub e unità di scala in magazzino. Ti consentono di ricevere le scorte quando esegui un carico di lavoro di magazzino su un'unità di scala. Attualmente sono utilizzati solo con ordini fornitore.

Gli ordini di magazzino vengono utilizzati come parte dell'elaborazione della gestione del magazzino, ad esempio quando l'app per dispositivi mobili Gestione magazzino viene utilizzata per registrare le scorte fisiche disponibili durante l'elaborazione di un ordine fornitore in entrata. Gli ordini di magazzino vengono creati come parte del processo *Rilascia in magazzino* disponibile per ordini fornitore che specificano un magazzino di unità di scala e articoli abilitati all'utilizzo dei processi di gestione magazzino.

> [!IMPORTANT]
> Gli ordini di magazzino sono disponibili solo nelle distribuzioni che utilizzano [carichi di lavoro di gestione del magazzino per unità di scala cloud e perimetrali](cloud-edge-workload-warehousing.md).

## <a name="create-a-warehouse-order"></a>Creare un ordine di magazzino

Per creare un ordine di magazzino, segui questi passaggi.

1. Accedi all'istanza di Microsoft Dynamics 365 Supply Chain Management in esecuzione nell'hub. Devi avviare il processo *Rilascia in magazzino* mentre sei connesso all'hub.
1. Andare ad **Approvvigionamento \> Ordini fornitore \> Tutti gli ordini fornitore**.
1. Nel riquadro azioni, nella scheda **Magazzino**, nel gruppo **Azioni**, selezionare **Rilascia in magazzino**.
1. Per visualizzare le righe dell'ordine di magazzino correlate, apri l'ordine fornitore acquisto pertinente, seleziona una riga nella sezione **Righe ordine fornitore**, quindi, sulla barra degli strumenti, seleziona **Magazzino \> Righe ordine di magazzino**. Per visualizzare tutte le righe, vai a **Gestione magazzino \> Richieste e segnalazioni \> Righe ordine di magazzino**.

Puoi anche attivare il processo *Rilascia in magazzino* da un processo batch selezionando **Gestione del magazzino > Rilascio in magazzino > Rilascio automatico degli ordini cliente**. Quando si imposta il processo batch, è possibile selezionare righe di ordine fornitore specifiche in base a una query. Uno scenario tipico sarebbe impostare un processo batch ricorrente che rilascia tutte le righe di ordine fornitore confermate che dovrebbero arrivare il giorno successivo.

## <a name="cancel-a-warehouse-order"></a>Annullare un ordine di magazzino

Come parte del processo *Rilascia in magazzino*, le transazioni di magazzino dell'ordine fornitore sono collegate agli ordini di magazzino e bloccate dall'aggiornamento dall'hub. Se hai rilasciato al magazzino per errore o se hai altri motivi per annullare la creazione di righe ordine di magazzino, puoi richiedere di annullare le righe ordine di magazzino.

Per annullare le righe dell'ordine di magazzino, segui questi passaggi.

1. Accedi all'istanza di Supply Chain Management in esecuzione nell'hub.
1. Vai a **Gestione magazzino \> Richieste e segnalazioni \> Righe ordine di magazzino**.
1. Seleziona la riga pertinente.
1. Nel riquadro azioni seleziona **Annulla righe ordine di magazzino**.

> [!NOTE]
> La richiesta di annullamento delle righe verrà rifiutata per tutte le righe che sono già in attesa di annullamento o che sono attivamente elaborate in un magazzino che esegue il proprio carico di lavoro su un'unità di scala.

## <a name="monitor-a-warehouse-order"></a>Monitorare un ordine di magazzino

Nella visualizzazione **Righe ordine di magazzino** è possibile monitorare l'avanzamento del ricevimento in entrata rivedendo i valori nella colonna **Quantità rimasta da ricevere**. Per visualizzare i dettagli relativi al lavoro svolto utilizzando l'app per dispositivi mobili Gestione magazzino, segui uno di questi passaggi.

- Vai a **Gestione magazzino \> Richieste e segnalazioni \> Righe ordine di magazzino** e utilizza il filtro per trovare le righe che stai cercando.
- Vai a **Approvvigionamento \> Ordini fornitore \> Tutti gli ordini fornitore** e apri l'ordine fornitore pertinente. Nella sezione **Righe ordine fornitore**, seleziona una o più righe, quindi, sulla barra degli strumenti, seleziona **Magazzino \> Voci di ricevimento magazzino**.

[!INCLUDE [cloud-edge-privacy-notice](../../includes/cloud-edge-privacy-notice.md)]


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
