---
title: Rettifica scorte magazzino
description: In questo argomento vengono fornite informazioni sul giornale di registrazione e sull'elaborazione della rettifica scorte magazzino quando si utilizzano unità di scala.
author: perlynne
ms.date: 04/22/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSInventoryAdjustmentJournal, InventJournalCount
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: SCM
ms.author: perlynne
ms.search.validFrom: 2021-04-21
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: a451816078ca2e77f30379828777209dc48bd849
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026135"
---
# <a name="warehouse-inventory-adjustment"></a>Rettifica scorte magazzino

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

La funzionalità di rettifica scorte magazzino viene utilizzata durante l'esecuzione di unità di scala per cloud e rete perimetrale per [carichi di lavoro di produzione](cloud-edge-workload-manufacturing.md) e [carichi di lavoro di gestione del magazzino](cloud-edge-workload-warehousing.md).

Quando un lavoratore esegue una rettifica magazzino utilizzando l'app di magazzino rispetto a un carico di lavoro di gestione del magazzino per unità di scala, l'aggiornamento delle scorte fisiche disponibili deve essere elaborato dal processo batch **Giornale di registrazione rettifica scorte di magazzino** , che esegui e pianifichi andando a **Gestione magazzino> Attività periodiche> Giornale di registrazione rettifica scorte magazzino**.

I seguenti processi di lavoro dell'app di magazzino utilizzano attualmente il **Giornale di registrazione rettifica scorte di magazzino** su carichi di lavoro per unità di scala:

- Rettifica (in ingresso/uscita)
- Conteggio ciclo
- Caricamento targa

Diverse transazioni di magazzino vengono create come parte di ogni processo di rettifica magazzino su cloud e rete perimetrale perché le distribuzioni hub e unità di scala condividono i record di inventario.

## <a name="inventory-adjustment-example"></a>Esempio di rettifica magazzino

In questo esempio, un addetto al magazzino ha utilizzato l'app del magazzino per registrare l'aggiunta di scorte disponibili.

Innanzitutto, il carico di lavoro per unità di scala crea una transazione di rettifica scorte di magazzino per la rettifica fisica positiva, che viene quindi sincronizzata con l'hub e si traduce in un aumento delle scorte disponibili sull'hub.

| Tipo                                    | Unità di scala | Direzione | Hub |
|-----------------------------------------|------------|-----------|-----|
| Rettifica scorte magazzino          | +1         | ->        | +1  |

L'hub elabora quindi una registrazione a giornale di conteggio, che viene ricevuta tramite i [messaggi dell'elaboratore di messaggi](cloud-edge-message-processor-messages.md). Questo aggiorna le scorte aggiuntive disponibili. Per evitare il doppio delle scorte disponibili, l'hub crea una transazione di contropartita come parte di questo processo e rimuove le scorte disponibili registrate in precedenza correlate alla rettifica scorte magazzino.

| Tipo                                    | Unità di scala | Direzione | Hub |
|-----------------------------------------|------------|-----------|-----|
| Conteggio                                | +1         | <-        | +1  |
| Rettifica scorte magazzino (contropartita) | -1         | <-        | -1  |

Dopo che un'unità di scala ha creato un **Giornale di registrazione rettifica scorte magazzino** sull'hub, puoi rivedere sia il **Giornale di registrazione di conteggio** che il **Giornale di registrazione di contropartita** che vengono creati dall'hub come parte del processo di rettifica.

È possibile rivedere ciascuna di queste registrazioni e transazioni in Supply Chain Management effettuando le seguenti operazioni:

1. Accedi all'unità di scala.
1. Vai a **Gestione magazzino \> Attività periodiche \> Giornale di registrazione rettifica scorte magazzino**.
1. Nella pagina **Giornale di registrazione rettifica scorte magazzino**, trova e apri il giornale che ha registrato la modifica delle scorte disponibili. La sezione **Righe giornale di registrazione** mostra ogni rettifica registrata da questo giornale.
1. Accedi all'hub.
1. Vai a **Gestione magazzino \> Attività periodiche \> Giornale di registrazione rettifica scorte magazzino**.
1. Nella pagina **Giornale di registrazione rettifica scorte magazzino**, dovresti vedere lo stesso giornale di registrazione elencato se l'hub e l'unità di scala sono stati sincronizzati.
1. Apri il giornale di registrazione. Se i [messaggi dell'elaboratore di messaggi](cloud-edge-message-processor-messages.md) sono stati elaborati, vedrai i collegamenti al **Giornale di registrazione di conteggio** e al **Giornale di registrazione di contropartita** nell'intestazione.
    - Il **Giornale di registrazione di conteggio** dovrebbe mostrare gli stessi valori di dimensione delle righe del giornale di registrazione.
    - Il **Giornale di registrazione di contropartita** dovrebbe mostrare la contropartita, che rimuove la doppia rettifica magazzino.
    > [!NOTE]
    > Quando tutta la sincronizzazione e l'elaborazione sono state completate, il **Giornale doi registrazione di conteggio** e il **Giornale di registrazione di contropartita** vengono sincronizzati di nuovo con l'unità di scala. Possono anche essere visualizzati dalla pagina **Giornale di registrazione rettifica scorte magazzino** pertinente.
