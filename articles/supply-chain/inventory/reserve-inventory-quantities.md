---
title: Prenotare quantità di scorte
description: In questo argomento vengono descritte le diverse opzioni disponibili per prenotare le scorte.
author: perlynne
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventModelGroup
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 207264
ms.assetid: 47537e4f-cdf6-4813-96fd-c945b2dfe9d4
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 89441ee4c799e2d1215fbd82e0490d7168e2aa1b
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "1570811"
---
# <a name="reserve-inventory-quantities"></a>Prenotare quantità di scorte

[!include [banner](../includes/banner.md)]

In questo argomento vengono descritte le diverse opzioni disponibili per prenotare le scorte.

È possibile prenotare automaticamente quantità di scorte per uno specifico ordine cliente. Le scorte prenotate non potranno quindi essere prelevate dal magazzino per altri ordini, a meno che la prenotazione o parte di questa non venga annullata.

Le scorte possono essere prenotate per diversi motivi:
-   Articoli ordinati per primi, consegnati per primi. I clienti ricevono gli articoli disponibili nella stessa sequenza in cui inseriscono gli ordini.
-   Carenza di articoli dovuta a tempi di consegna prolungati o non specificati da parte del fornitore. Potrebbe essere utile assicurare che a determinati clienti o ordini vengano consegnati i primi articoli disponibili.
-   Alcuni clienti e alcuni tipi di ordini hanno la massima priorità di consegna.
-   Articoli con numeri batch o di serie. È possibile contrassegnare determinati articoli che sono stati o saranno consegnati a ordini specifici.
-   Articoli ordinati in modo speciale e prenotati per determinati ordini.
-   Ordini di produzione. È possibile, ad esempio, contrassegnare gli articoli prodotti e rettificati per ordini specifici.

È possibile prenotare le scorte automaticamente quando si crea una nuova riga ordine oppure manualmente per i singoli ordini utilizzando È inoltre possibile prenotare le scorte nelle diverse fasi di un processo di produzione. Solo i prodotti stoccati possono essere prenotati. Non è possibile prenotare servizi perché non sono presenti scorte disponibili. È possibile prenotare sia scorte fisiche disponibili sia scorte ordinate ma non ancora ricevute. Se viene prenotata una quantità maggiore di quella presente nelle scorte disponibili, verrà visualizzato un messaggio per segnalare che non è possibile prenotare una quantità di questa entità. Sarà quindi possibile scegliere di prenotare comunque la quantità specificata oppure di modificare la quantità ordinata. La quantità può essere prenotata o modificata. Se viene prenotato un numero maggiore di articoli rispetto a quelli disponibili, la carenza verrà coperta la volta successiva in cui gli articoli saranno disponibili per la consegna.

## <a name="inventory-reservation-policies"></a>Criteri di prenotazione scorte
I criteri di prenotazione scorte sono impostati nella pagina **Gruppi di modelli di articoli**, la pagina **Parametri di gestione articoli e magazzino** e la pagina **Parametri di produzione**.
### <a name="policies-on-the-item-model-groups-page"></a>Criteri nella pagina dei gruppi di modelli di articoli

La sezione **Criteri di inventario** contiene i criteri di prenotazione seguenti.

|                         |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
|-------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Criterio di prenotazione**  | **Descrizione**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| Controllo in base a data FIFO    | Se si seleziona l'opzione **Controllo in base a data FIFO**, la prenotazione delle scorte viene controllata in base alla data di ordinamento secondo il principio FIFO (First In, First Out). I batch sono prenotati in base alla prima data di entrata degli articoli secondo il principio FIFO (First In, First Out).                                                                                                                                                                                                                                                                       |
| Indietro da data di spedizione | Questa opzione diventa disponibile se è stata selezionata l'opzione **Controllo in base a data FIFO**. Se si seleziona **Indietro da data di spedizione**, la prenotazione delle scorte verrà effettuata a ritroso dalla data di spedizione desiderata secondo il principio LIFO (Last In, First Out). Se non sono disponibili entrate prima della data di spedizione, verrà utilizzata una prenotazione FIFO.                                                                                                                                                                                                           |
| Prenotazione vendite articolo  | Determina se la prenotazione dell'articolo viene eseguita manualmente o automaticamente. Se la prenotazione è automatica, le scorte sono prenotate alla creazione delle righe ordine. È possibile effettuare prenotazioni a livello del numero di articolo per DBA (opzione **Automatico**), o per i singoli elementi di una DBA (opzione **Esplosione**). Il valore predefinito per **Prenotazione vendite articolo** può essere ereditato da **Parametri contabilità clienti**. In questa pagina, il valore viene impostato nel campo Prenotazione della **sezione** **Valori predefiniti vendite** della scheda **Generale**. |
| Selezione stesso batch    | La prenotazione dello stesso batch consente di prenotare le scorte per una riga di ordine cliente da un unico lotto di magazzino. Se si desidera utilizzare questa opzione, è inoltre necessario impostare l'opzione **Fabbisogno consolidato** su **Sì**. Esistono alcune impostazioni aggiuntive necessarie per il gruppo di dimensioni di tracciabilità e il gruppo di dimensioni di immagazzinamento. Per ulteriori informazioni, vedere [Prenotazione dello stesso batch per un ordine cliente](../sales-marketing/reserve-same-batch-sales-order.md).                                                          |
| Fabbisogno consolidato | Questa opzione è simile all'opzione **Selezione stesso batch** e consolida le scorte prenotate per le righe di ordine cliente in un unico fabbisogno.                                                                                                                                                                                                                                                                                                                                                                                      |
| Controllo in base a data FEFO    | Questa opzione consente di prenotare batch vicini alla data di scadenza o data di consumo consigliata. È inoltre necessario impostare il campo **Criteri di prelievo** per selezionare **Data di scadenza** o**Data di consumo consigliata**.                                                                                                                                                                                                                                                                                                                              |

#### <a name="example-for-fifo-date-controlled-and-backward-from-ship-date"></a>Esempio di Controllo in base a data FIFO e Indietro da data di spedizione

In questo esempio, le scorte disponibili per il numero articolo A esistono per tre numeri batch diversi.

| Numero articolo | Numero batch | Quantità | Data             |
|-------------|--------------|----------|------------------|
| A           | 1000         | 5        | 2 febbraio 2016 |
| A           | 1001         | 3        | 1 gennaio 2016  |
| A           | 1002         | 7        | 3 marzo 2016    |

Per un ordine cliente che dovrà essere prenotato automaticamente e consegnato in data 4 aprile 2016 viene prenotato il batch indicato di seguito:
-   Se entrambe le caselle di controllo **Controllo in base a data FIFO** e **Indietro da data di spedizione** sono deselezionate, viene prenotato il batch 1000 perché è quello con il numero inferiore.
-   Se la casella di controllo **Controllo in base a data FIFO** è selezionata e la casella di controllo **Indietro da data di spedizione** è deselezionata, viene prenotato il batch 1001 perché è quello con la prima data di entrata (FIFO).
-   Se entrambe le caselle di controllo **Controllo in base a data FIFO** e **Indietro da data di spedizione** sono deselezionate, viene prenotato il batch 1002 perché è quello con l'entrata più vicina alla data di spedizione dell'ordine cliente.

### <a name="policies-on-the-inventory-and-warehouse-management-parameter-page"></a>Criteri nella pagina Parametri di gestione articoli e magazzino

Sono disponibili due opzioni relative alle prenotazioni nella pagina **Parametri di gestione articoli e magazzino**.
-   L'opzione **Prenota articoli ordinati** nella scheda **Generale** consente di prenotare le entrate di articoli ordinati in base alle uscite di articoli nelle sezioni Contabilità clienti, Gestione progetti e contabilità e Controllo produzione. Se questa opzione viene deselezionata, sarà possibile prenotare solo articoli già fisicamente ricevuti. Se un determinato articolo è stato impostato per l'accettazione di scorte negative, questo campo non è rilevante.
-   L'opzione **Prenota articoli automaticamente** nella scheda **Trasporto** determina l'impostazione predefinita se gli articoli sono prenotati automaticamente per gli ordini di trasferimento. L'impostazione predefinita può essere sostituita per singoli ordini di trasferimento.

### <a name="inventory-reservation-policies-on-the-production-parameters-page"></a>Criteri di prenotazione scorte nella pagina Parametri di produzione

Il valore del campo **Prenotazione** nella scheda **Generale** della pagina **Parametri di produzione** determina il punto predefinito nel processo di produzione in cui dovranno essere prenotate le scorte. Ad esempio, le scorte possono essere prenotate quando il lavoro viene programmato oppure iniziato.
