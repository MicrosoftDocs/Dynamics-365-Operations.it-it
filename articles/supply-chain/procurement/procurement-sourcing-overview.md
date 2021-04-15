---
title: Panoramica dell'approvvigionamento
description: In questo articolo viene fornita una panoramica della funzionalità disponibile nel modulo Approvvigionamento.
author: kamaybac
ms.date: 05/06/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CatProcureCatalogListPage, CatVendorCatalogListPage, PurchTable, PurchTablePart
audience: Application User
ms.reviewer: kamaybac
ms.custom: 58021
ms.assetid: eea24e23-a803-4de0-a218-6485757cde1b
ms.search.region: Global
ms.author: dabourq
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1dc0e3b503b71092062c1f70bc8cd1b8cf882e02
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5807970"
---
# <a name="procurement-and-sourcing-overview"></a>Panoramica dell'approvvigionamento

[!include [banner](../includes/banner.md)]

In questo articolo viene fornita una panoramica della funzionalità disponibile nel modulo Approvvigionamento.

L'approvvigionamento interessa tutti i passaggi del processo: dalla verifica della necessità di prodotti e servizi, all'approvvigionamento vero e proprio del prodotto, a ricezione, fatturazione ed elaborazione dei pagamenti ai fornitori. I processi di approvvigionamento possono essere configurati in base a esigenze specifiche definendo i criteri di acquisto e i flussi di lavoro.

## <a name="identifying-a-need-for-product-and-services"></a>Verifica della necessità di prodotti e servizi

La necessità di prodotti o servizi può sorgere da *richieste di approvvigionamento*, ad esempio quando un dipendente richiede un prodotto. I *cataloghi prodotti* possono essere impostati per guidare la selezione dei prodotti disponibili. In alternativa le richieste possono essere effettuate per prodotti non ancora disponibili in un catalogo e permettere al reparto acquisti di verificare il modo in cui il prodotto può essere fornito.  

Il parametro *Limiti spesa* consente di impostare vincoli relativi alla spesa della richiesta di acquisto. Il *flusso di lavoro di acquisto* aggiunge l'opzione di richiesta di approvazione prima che venga effettuato l'ordine. È inoltre possibile specificare delle allocazioni dei fondi di budget, se necessario.  

Il reparto di approvvigionamento identifica i fornitori per i prodotti e i servizi richiesti e questo può determinare l'invio di una *richiesta di offerta* a più fornitori potenziali. È possibile condividere le specifiche del prodotto richiesto e i fornitori potenziali possono visualizzare e controllare se possono consegnare un prodotto conforme a tali specifiche. I fornitori restituiscono le offerte che vengono verificate dal reparto di approvvigionamento prima di selezionare il fornitore desiderato.  

Gli ordini fornitore includono un'opzione per inviare la *richiesta di acquisto* al fornitore come alternativa a un processo più completo della richiesta di offerta. La richiesta di acquisto può essere utilizzata per contribuire a stabilire termini quali prezzi, sconti e data di consegna dell'ordine. Se i fornitori sono impostati per l'uso del portale **Fornitore**, la funzionalità di richiesta di acquisto è disabilitata. L'ordine viene condiviso nel portale **fornitori** e quando viene inviata una *richiesta di conferma* il fornitore può direttamente confermare l'ordine.  

*Cataloghi fornitore* è possibile utilizzare i cataloghi per raccogliere informazioni sull'assortimento di prodotti che i fornitori possono fornire. I fornitori possono pubblicare il proprio catalogo, pertanto è più semplice mantenere aggiornato il catalogo. È possibile allegare un *elenco di fornitori approvati* a un prodotto e questo può agevolare la selezione del fornitore quando i nuovi ordini fornitore vengono aperti e impedire l'utilizzo dei fornitori non desiderati.

## <a name="procurement"></a>Approvvigionamento

Gli *ordini fornitore* possono essere creati in modi diversi inclusi:

- Come risultato di pianificazione generale che ha identificato una richiesta che richiede un acquisto. Questo processo genera gli ordini fornitore pianificati e quando questi vengono rilasciati, gli ordini fornitore verranno generati.
- Tramite l'elaborazione di richieste di acquisto che determinano un approvvigionamento.
- Tramite l'elaborazione dei contratti di acquisto, in cui gli ordini fornitore vengono creati come ordini rilasciati dai contratti. Questo modo viene comunemente usato quando i contratti di acquisto vengono utilizzati per gli ordini di copertura.
- Manualmente, quando l'ordine fornitore creato non è basato su un altro documento.

Gli ordini fornitore configurati con *flussi di lavoro di approvazione di acquisto* richiedono l'approvazione prima della registrazione come approvato e questa è necessaria prima che l'ordine possa essere elaborato ulteriormente.

Gli ordini fornitore vengono *confermati* per confermare che è stato definito un contratto con il fornitore. L'ordine fornitore progredirà quindi gradualmente attraverso i diversi stati finché verrà infine fatturato o annullato.  

Quando si crea un ordine fornitore, molti campi vengono prepopolati in modo automatico con i valori predefiniti delle informazioni sul fornitore memorizzate nella pagina **Fornitori**. Ciò significa solo un numero limitato di campi necessita di essere compilato nell'ordine fornitore, benché sia possibile scegliere di sostituire i valori predefiniti.

### <a name="prices-and-discounts"></a>Prezzi e sconti

I prezzi e gli sconti includono informazioni sui prezzi, gli sconti e i termini di sconto che i fornitori offrono. I prezzi e gli sconti possono essere rappresentati come *accordi commerciali*. Gli accordi commerciali presentano listino prezzi del fornitore con i prezzi e gli sconti e con un set specifico di date di validità del contratto. I prezzi e gli sconti possono essere negoziati e rappresentati tramite i *contratti di acquisto* secondo termini quali l'impegno ad acquistare determinati volumi o importi monetari di merce come condizione preliminare per i termini negoziati. Gli *accordi sugli sconti* possono essere definiti con i fornitori nei casi in cui l'approvvigionamento di prodotti specifici o di gruppi di prodotti può attivare uno sconto da parte del fornitore a seconda dell'importo o del volume di acquisto.

### <a name="delivery-options"></a>Opzioni di consegna

Sono disponibili opzioni diverse per il processo di consegna associato a un ordine fornitore. I prodotti ordinati possono essere suddivisi nella programmazione della *consegna* in cui le parti della quantità ordinata possono essere pianificate per la consegna in date differenti. La consegna può anche includere la *consegna diretta* a partire da un ordine cliente, questo automatizza la creazione del documento di trasporto nell'ordine cliente nel momento in cui l'entrata prodotti viene registrata nell'ordine fornitore. Gli ordini fornitore possono inoltre fare parte di una catena di *ordini interaziendali*, noti anche come ordini fornitore interaziendali, in cui i prodotti vengono ordinati a partire da un ordine cliente interaziendale corrispondente. In questo caso, alcuni passaggi sono automatizzati nei due ordini interaziendali correlati.

### <a name="supplementary-items"></a>Articoli supplementari

I prodotti possono essere impostati per includere *articoli supplementari*. In questo modo vengono proposti prodotti correlati al prodotto principale in fase di preparazione dell'ordine. I prodotti aggiuntivi possono essere obbligatori oppure facoltativi. In alcuni casi, gli articoli supplementari possono anche essere aggiunti come prodotti gratuiti associati all'acquisto di altri prodotti.

### <a name="purchase-order-charges"></a>Spese ordine fornitore

Gli addebiti possono essere assegnati all'ordine fornitore. Questa assegnazione può essere automatica mediante l'impostazione delle spese automatiche oppure manuale. Le spese possono essere associate all'ordine sia a livello di intestazione che a livello di riga. La contabilità delle spese può essere impostata in vari modi. Ad esempio, è possibile impostare una spesa come costo del prodotto. In questo caso, le spese devono essere assegnate a livello di riga ordine fornitore prima che l'ordine possa essere confermato. È disponibile un'opzione che consente di allocare le spese dall'intestazione ordine alle righe.

## <a name="product-receipt-and-invoicing"></a>Entrata prodotti e fatturazione

Gli ordini fornitore che includono prodotti fisici in genere vengono prima elaborati tramite la *registrazione degli arrivi* nel magazzino e successivamente viene registrata un'*entrata prodotti* per l'ordine. Gli ordini fornitore con prodotti che soddisfano richieste di approvvigionamento possono essere configurati in modo che il dipendente che ha richiesto i prodotti debba fornire una *conferma di entrata*.  

Alcuni ordini fornitore includono prodotti che corrispondono a servizi o ad altri prodotti non fisici che non richiedono l'entrata in un magazzino. I prodotti possono essere creati come servizi o *categorie di approvvigionamento* e possono essere utilizzati direttamente nell'ordine fornitore corrispondente. Con tali ordini, l'entrata dei prodotti talvolta viene ignorata e la fatturazione dell'ordine avviene direttamente o, in alternativa, la registrazione dell'entrata prodotti viene effettuata nell'ordine fornitore senza alcuna precedente registrazione arrivi.  

L'entrata prodotti può determinare il consumo automatico per uno scopo specifico. Ciò include il consumo implicito con consegna diretta, il consumo per un progetto o la contabilizzazione del prodotto come cespite.  

Quando le *fatture fornitore* arrivano dal fornitore è necessario prima registrale nel *registro fatture*, indipendentemente dall'ordine fornitore, e quindi successivamente approvarle come record a fronte dell'ordine fornitore. La registrazione della fattura fornitore con l'ordine fornitore include la corrispondenza dell'entrata prodotti rispetto alla fattura.  

Le *distribuzioni contabili* possono essere specificate nell'ordine fornitore per descrivere come deve essere effettuata la registrazione in contabilità generale ed è inoltre possibile definire la modalità di allocazione dei fondi di budget se questa è inclusa nella configurazione.  

Per gli ordini fornitore fatturati verrà registrata la passività nel conto fornitore all'interno della contabilità fornitori da cui sarà possibile elaborare il *pagamento fornitore*.

## <a name="vendor-performance"></a>Prestazioni fornitore

Le prestazioni e la verifica dell'acquisto sono supportati tramite i *report di contabilità fornitori e approvvigionamento* che includono l'analisi della spesa e delle prestazioni del fornitore.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]