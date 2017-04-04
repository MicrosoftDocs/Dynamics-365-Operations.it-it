---
title: Customer orders overview
description: In questo argomento vengono fornite informazioni sugli ordini cliente in Retail moderno al dettaglio MPOS (). Gli ordini cliente anche noti come ordini speciali. Oggetto include una discussione sui parametri correlati nella transazione flussi risultanti.
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 260594
ms.assetid: 6fc835ef-d62e-4f23-9d49-50299be642ca
ms.search.region: global
ms.search.industry: Retail
ms.author: anpurush
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: 2f466dfe53ccf0be15ed0793b4a6dd371bdacc0d
ms.lasthandoff: 03/31/2017


---

# <a name="customer-orders-overview"></a>Customer orders overview

In questo argomento vengono fornite informazioni sugli ordini cliente in Retail moderno al dettaglio MPOS (). Gli ordini cliente anche noti come ordini speciali. Oggetto include una discussione sui parametri correlati nella transazione flussi risultanti.

In una situazione di vendita al dettaglio di omni- Manica, molte rivenditori sono riportate le opzioni degli ordini cliente, o ordini speciali, in base alle varie richieste di evasione e prodotto. Di seguito sono riportati alcuni scenari comuni:

-   Un cliente desidera che i prodotti essere consegnato a un indirizzo specifico in una data specifica.
-   Un cliente desidera richiedere prodotti da un punto vendita o da una posizione diversa dal punto vendita o alla posizione in cui il cliente ha acquisito i prodotti.
-   Un cliente desidera eseguire altri prodotti che il cliente ha acquistato.

I rivenditori viene utilizzato anche negli ordini cliente per ridurre le vendite perse che i guasti scorte potrebbero causare altrimenti, poiché la merce possono essere consegnate da o in una data o in una località diverso.

## <a name="set-up-customer-orders"></a>Ordini di impostazione dei clienti
Di seguito sono riportati alcuni dei parametri che è possibile impostare parametri ** al dettaglio ** nella pagina per definire la modalità delle richieste del cliente vengono soddisfatti:

-   ** Percentuale di smaltimento predefinito ** consente di specificare l'importo che il cliente deve pagare come un deposito prima di un ordine possa essere confermato. Importo del deposito predefinita viene calcolata come percentuale del valore dell'ordine. A seconda dei privilegi, un livello del punto vendita può essere possibile ignorare l'importo utilizzando ** sostituzione di deposito **.
-   ** La percentuale di spese varie di annullamento ** se una spesa verrà utilizzata quando un ordine cliente è deselezionata, specificare l'importo della spesa.
-   ** Il codice di spese varie di annullamento ** se una spesa verrà utilizzata quando un ordine cliente viene annullato, la spesa verrà visualizzato con un codice di spese nell'ordine cliente in Microsoft Dynamics AX. Utilizzare questo parametro per definire il codice di spese varie di annullamento.
-   ** Il codice di spese di spedizione ** - rivenditori possono addebitare una commissione supplementare per tipi di spedizione a un cliente. Importo della nota spese di spedizione verrà visualizzato con un codice di spese nell'ordine cliente in Dynamics AX. Utilizzare questo parametro per mappare il codice di spesa delle spedizioni alle spese di spedizione nell'ordine cliente.
-   ** Le spese di spedizione di rimborso ** consente di specificare se le spese di spedizione associate a un ordine cliente in rimborsabili.
-   ** Importo massimo senza approvazione ** se le spese di spedizione vengono rimborsabili, specificare l'importo massimo di rimborsi di spese di spedizione negli ordini di reso. Se questo importo viene superato, la forzatura del responsabile è necessaria per proseguire il rimborso. Per soddisfare i seguenti scenari, un rimborso delle spese di spedizione può superare l'importo da consegnare pagato:
    -   Le spese vengono applicate a livello di intestazione ordine cliente e quando una certa quantità della linea di prodotti verrà restituita, il rimborso massimo delle spese di spedizione consentito i prodotti e la quantità non può essere impostata in modo che opera per tutti i clienti al dettaglio.
    -   Le spese di spedizione verranno sostenute per ciascuna istanza di spedizione. Se un cliente restituisce più volte dei prodotti e i criteri del rivenditore indica che il rivenditore sopporterà il costo delle spese di spedizione reso, le spese di spedizione reso saranno più delle spese di spedizione effettive.

## <a name="transaction-flow-for-customer-orders"></a>Flusso della transazione relativo agli ordini cliente
### <a name="create-a-customer-order-in-retail-modern-pos"></a>Crea ordine cliente nel POS moderno al dettaglio

1.  Aggiungere un cliente alla transazione.
2.  Aggiungere prodotti al carrello.
3.  Fare clic su ** creare un ordine cliente ** quindi selezionare il tipo di ordine. Tipo di ordine può essere o ** ordine cliente o ** ** ** offerta.
4.  Fare clic su ** spedizione selezionata o ** ** inclusi tutti ** spedire prodotti a un indirizzo per il conto cliente, specificare la data di spedizione richiesta e specificare le spese di spedizione.
5.  Fare clic su ** opzioni selezionate in selezionato ** o ** tutti Pick-up ** selezionare i prodotti che saranno rilevati dal punto vendita corrente o da un punto vendita diverso in una data specifica.
6.  Incassare l'importo del deposito, se un deposito è obbligatorio.

### <a name="edit-an-existing-customer-order"></a>Modificare un ordine cliente esistente

1.  Nella home page, fare clic su ** individuare un ordine **.
2.  Individuare e selezionare l'ordine da modificare. Nella parte inferiore della pagina, fare clic su ** ** modifica.

### <a name="pick-up-an-order"></a>Rimuovere un ordine

1.  Nella home page, fare clic su ** individuare un ordine **.
2.  Selezionare l'ordine da eseguire. Nella parte inferiore della pagina, fare clic su ** prelievo e ** imballaggio.
3.  Fare clic su ** effettuare **.

### <a name="cancel-an-order"></a>Annullare un ordine

1.  Nella home page, fare clic su ** individuare un ordine **.
2.  Selezionare l'ordine da annullare. Nella parte inferiore della pagina, fare clic su ** ** annullamento.

#### <a name="create-a-return-order"></a>Creare un ordine di reso

1.  Nella home page, fare clic su ** individuare un ordine **.
2.  Selezionare l'ordine da restituire, selezionare la fattura per l'ordine quindi selezionare la linea di prodotti per la merce desidera restituire.
3.  Nella parte inferiore della pagina, fare clic su ** ordine di reso **.

## <a name="asynchronous-transaction-flow-for-customer-orders"></a>Flusso asincrono della transazione relativo agli ordini cliente
Gli ordini cliente possono essere creati dal client di (POS) del POS in modalità sincrona o in modalità asincrona.

### <a name="enable-customer-orders-to-be-created-in-asynchronous-mode"></a>Consentire agli ordini cliente da creare in modalità asincrona

1.  In Dynamics AX, fare clic su ** al dettaglio e il commercio ** &gt; ** il Manica impostato ** &gt; ** POS configurato ** &gt; ** profilo di Retail POS ** &gt; ** profili funzionalità **.
2.  ** Generale ** clic, impostare ** creare un ordine cliente in modalità di async ** l'opzione ** Sì **.

Quando ** creare un ordine cliente in modalità di async ** l'opzione è impostata su Sì ** **, ordini cliente vengono creati sempre in modalità asincrona, anche se Retail Transaction Service (RTS) è disponibile. Se si imposta questa opzione non ** **, ordini cliente vengono creati sempre in modalità sincrona utilizzando il RTS. Quando gli ordini cliente vengono creati in modalità asincrona, vengono estratti e immessi in Dynamics AX per i processi di Pull (P). Gli ordini cliente corrispondenti vengono creati in Dynamics AX quando ** sincronizzare gli ordini ** viene eseguita manualmente o tramite un processo batch.

<a name="see-also"></a>Vedere anche
--------

[] Ibridi Ordini cliente (hybrid-customer-orders.md)


