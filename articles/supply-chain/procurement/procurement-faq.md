---
title: Approvvigionamento - Domande frequenti
description: Questo argomento fornisce le risposte alle domande frequenti (FAQ) sulla funzionalità di approvvigionamento di Supply Chain Management.
author: kamaybac
ms.date: 05/31/2021
ms.topic: article
ms.search.form: PurchTable, PurchTablePart, PurchRFQTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 09c99b88bc47609158805cdba1291ae462cda178
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476717"
---
# <a name="procurement-faq"></a>Approvvigionamento - Domande frequenti

[!include [banner](../includes/banner.md)]

Questo argomento fornisce le risposte alle domande frequenti (FAQ) sulla funzionalità di approvvigionamento di Supply Chain Management.

## <a name="can-i-show-only-purchase-orders-that-i-created"></a>Posso mostrare solo gli ordini fornitore che ho creato?

Questa funzionalità non è attualmente disponibile.

## <a name="can-i-reserve-inventory-and-create-transactions-against-registered-inventory-on-a-purchase-order"></a>Posso prenotare scorte e creare transazioni a partire dall'inventario registrato in un ordine fornitore?

### <a name="issue-description"></a>Descrizione del problema

Anche quando gli articoli sono in uno stato *Registrato* su un ordine fornitore, è comunque possibile prenotare scorte. In altre parole, puoi creare transazioni a fronte dell'inventario registrato.

### <a name="reproduce-the-issue"></a>Riprodurre il problema

La seguente procedura mostra un modo per riprodurre il problema.

1. Creare un ordine fornitore.
2. Registra la riga relativa all'ordine fornitore.
3. Tieni presente che puoi generare prenotazioni o transazioni a fronte dell'inventario registrato.

### <a name="issue-resolution"></a>Risoluzione dei problemi

Questo comportamento è predefinito. L'aspettativa è che gli articoli registrati siano fisicamente arrivati nel magazzino o nell'inventario e che siano quindi disponibili per la prenotazione.

## <a name="can-i-find-the-user-who-canceled-a-purchase-order"></a>Posso trovare l'utente che ha annullato un ordine fornitore?

Questa informazioni viene registrata solo se per l'ordine fornitore è soggetto alla gestione delle modifiche. Se utilizzi la gestione delle modifiche, puoi vedere chi ha inviato la modifica (l'annullamento) e chi l'ha approvata.

## <a name="why-cant-i-link-a-purchase-agreement-to-an-existing-purchase-order"></a>Perché non riesco a collegare un contratto di acquisto a un ordine fornitore?

Un contratto di acquisto deve essere associato a un ordine fornitore dopo aver creato l'ordine fornitore. In caso contrario, le righe dell'ordine fornitore non possono essere associate alle righe del contratto di acquisto.

## <a name="what-check-triggers-the-update-prices-and-discounts-entered-manually-or-external-document-message"></a>Quale controllo attiva il messaggio "Aggiorna prezzi e sconti inseriti manualmente o documento esterno"?

Quando si modifica la data di spedizione, è possibile che venga visualizzato un messaggio che indica "Aggiorna prezzi e sconti inseriti manualmente o documento esterno". Viene visualizzato questo messaggio perché, se la data di spedizione viene modificata, potrebbe essere attivato un accordo commerciale o di vendita diverso e potrebbe causare una variazione del prezzo. Una modifica alla data di spedizione può anche influire sui programmi di magazzino e su altre informazioni correlate.

Il messaggio viene attivato ogni volta che una delle date o alcuni altri parametri vengono modificati. Lo scopo del messaggio è assicurarsi di essere a conoscenza delle variazioni di prezzo che possono verificarsi a causa di tali cambiamenti.

Il messaggio è il prompt della valutazione dell'accordo commerciale (TAE). Per una descrizione completa, vedi [Criteri di valutazione degli accordi commerciali](/dynamicsax-2012/appuser-itpro/trade-agreement-evaluation-policies-white-paper).

## <a name="why-cant-i-post-more-than-one-invoice-for-a-purchase-order-line-that-has-category-based-items"></a>Perché non riesco a registrare più di una fattura per una riga di ordine fornitore con articoli basati sulla categoria?

Una quantità è obbligatoria se si desidera registrare le fatture. Pertanto, se l'intera quantità di una riga è stata fatturata solo per un importo parziale, non sarà possibile fatturare l'importo rimanente su un'altra fattura.
