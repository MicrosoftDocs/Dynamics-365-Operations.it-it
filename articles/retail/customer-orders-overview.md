---
title: Ordini cliente in Retail Modern POS (MPOS)
description: In questo argomento vengono fornite informazioni sugli ordini cliente in Retail Modern POS (MPOS). Gli ordini cliente sono anche noti come ordini speciali. Questo argomento include una discussione sui parametri e i flussi di transazioni correlati.
author: josaw1
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: RetailFunctionalityProfile
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 260594
ms.assetid: 6fc835ef-d62e-4f23-9d49-50299be642ca
ms.search.region: global
ms.search.industry: Retail
ms.author: anpurush
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 5098fb3339403b6f2779dfe3bb7ef5c4ca78051f
ms.openlocfilehash: 8025df4f8498efa867f71892b253f71631b731c7
ms.contentlocale: it-it
ms.lasthandoff: 08/09/2018

---

# <a name="customer-orders-in-retail-modern-pos-mpos"></a>Ordini cliente in Retail Modern POS (MPOS)

[!include [banner](includes/banner.md)]

In questo argomento vengono fornite informazioni sugli ordini cliente in Retail Modern POS (MPOS). Gli ordini cliente sono anche noti come ordini speciali. Questo argomento include una discussione sui parametri e i flussi di transazioni correlati.

In un mondo di vendita al dettaglio omni-canale, molti rivenditori offrono l'opzione degli ordini cliente, o ordini speciali, per soddisfare vari requisiti di prodotti ed evasione. Di seguito sono riportati alcuni scenari comuni:

-   Un cliente desidera che i prodotti siano consegnati a un indirizzo specifico in una data specifica.
-   Un cliente desidera prelevare i prodotti da un punto vendita o da una posizione diversa dal punto vendita o posizione in cui il cliente ha acquisito i prodotti.
-   Un cliente desidera che qualcun altro prelevi i prodotti che il cliente ha acquistato.

I rivenditori utilizzano gli ordini cliente anche per ridurre al minimo le vendite perse che l'esaurimento delle scorte potrebbero causare altrimenti, poiché la merce può essere consegnata o prelevata in una data o in una località diversa.

## <a name="set-up-customer-orders"></a>Impostare gli ordini cliente
Di seguito sono riportati alcuni dei parametri che è possibile impostare nella pagina **Parametri di vendita al dettaglio** per definire la modalità di evasione degli ordini cliente:

-   **Percentuale di deposito predefinita** - consente di specificare l'importo che il cliente deve pagare come deposito prima che un ordine possa essere confermato. L'importo del deposito predefinito viene calcolato come percentuale del valore dell'ordine. A seconda dei privilegi, un associato del punto vendita può ignorare l'importo utilizzando **Sostituzione deposito**.
-   **Percentuale spese di annullamento** - se un addebito verrà applicato quando un ordine cliente viene annullato, specificare l'importo dell'addebito.
-   **Codice spese di annullamento** - se un addebito verrà applicato quando un ordine cliente viene annullato, l'addebito verrà visualizzato con un codice spese nell'ordine cliente. Utilizzare questo parametro per definire il codice spese di annullamento.
-   **Codice spese di spedizione** - rivenditori possono addebitare una commissione supplementare per la spedizione della merce a un cliente. L'importo delle spese di spedizione verrà visualizzato con un codice spese nell'ordine cliente. Utilizzare questo parametro per mappare il codice spese di spedizione alle spese di spedizione nell'ordine cliente.
-   **Rimborso spese di spedizione** - consente di specificare se le spese di spedizione associate a un ordine cliente sono rimborsabili.
-   **Importo massimo senza approvazione** - se le spese di spedizione sono rimborsabili, specificare l'importo massimo di rimborsi di spese di spedizione negli ordini di reso. Se questo importo viene superato, la sostituzione del responsabile è necessaria per proseguire con il rimborso. Per soddisfare i seguenti scenari, un rimborso delle spese di spedizione può superare l'importo originariamente pagato:
    -   Le spese vengono applicate a livello di intestazione ordine cliente e quando una certa quantità di una riga prodotto viene restituita, il rimborso massimo delle spese di spedizione consentito per i prodotti e la quantità non può essere determinato in un modo che funziona per tutti i clienti al dettaglio.
    -   Le spese di spedizione vengono sostenute per ciascuna istanza di spedizione. Se un cliente restituisce più volte dei prodotti e i criteri del rivenditore indicano che il rivenditore sopporterà il costo delle spese di spedizione reso, le spese di spedizione reso saranno superiori alle spese di spedizione effettive.

## <a name="transaction-flow-for-customer-orders"></a>Flusso della transazione per gli ordini cliente
### <a name="create-a-customer-order-in-retail-modern-pos"></a>Creare un ordine cliente in Retail Modern POS

1.  Aggiungere un cliente alla transazione.
2.  Aggiungere prodotti al carrello.
3.  Fare clic su **Crea ordine cliente** quindi selezionare il tipo di ordine. Tipo di ordine può essere **Ordine cliente** o **Offerta**.
4.  Fare clic su **Spedizione selezionata** o **Spedisci tutto** per spedire i prodotti a un indirizzo nel conto cliente, specificare la data di spedizione richiesta e specificare le spese di spedizione.
5.  Fare clic su **Prelievo selezionato** o **Preleva tutto** per selezionare i prodotti che saranno prelevati dal punto vendita corrente o da un punto vendita diverso in una data specifica.
6.  Incassare l'importo del deposito, se un deposito è obbligatorio.

### <a name="edit-an-existing-customer-order"></a>Modificare un ordine cliente esistente

1.  Nella home page, fare clic su **Trova ordine**.
2.  Trovare e selezionare l'ordine da modificare. In fondo alla pagina fare clic su **Modifica**.

### <a name="pick-up-an-order"></a>Prelevare un ordine

1.  Nella home page, fare clic su **Trova ordine**.
2.  Selezionare l'ordine da prelevare. In fondo alla pagina fare clic su **Prelievo e imballaggio**.
3.  Fare clic su **Preleva**.

### <a name="cancel-an-order"></a>Annullare un ordine

1.  Nella home page, fare clic su **Trova ordine**.
2.  Selezionare l'ordine cliente da annullare. In fondo alla pagina fare clic su **Annulla**.

#### <a name="create-a-return-order"></a>Creare un ordine di reso

1.  Nella home page, fare clic su **Trova ordine**.
2.  Selezionare l'ordine da restituire, selezionare la fattura per l'ordine quindi selezionare la riga prodotto della merce da restituire.
3.  In fondo alla pagina fare clic su **Ordine di reso**.

## <a name="asynchronous-transaction-flow-for-customer-orders"></a>Flusso asincrono della transazione per gli ordini cliente
Gli ordini cliente possono essere creati dal client POS in modalità sincrona o in modalità asincrona.

### <a name="enable-customer-orders-to-be-created-in-asynchronous-mode"></a>Abilitare la creazione degli ordini cliente in modalità asincrona

1.  Fare clic su **Vendita al dettaglio** &gt; **Impostazione canale** &gt; **Impostazioni POS** &gt; **Profilo POS** &gt; **Profili funzionalità**.
2.  Nella Scheda dettaglio **Generale** , impostare l'opzione **Crea ordine cliente in modalità asincrona** su **Sì**.

Quando l'opzione **Crea ordine cliente in modalità asincrona** è impostata su **Sì**, ordini cliente vengono creati sempre in modalità asincrona, anche se Retail Transaction Service (RTS) è disponibile. Se si imposta questa opzione su **No**, ordini cliente vengono creati sempre in modalità sincrona utilizzando RTS. Quando gli ordini cliente vengono creati in modalità asincrona, vengono estratti e immessi in Retail tramite i processi Pull (P). Gli ordini cliente corrispondenti vengono creati in Retail quando **Sincronizza ordini** viene eseguito manualmente o tramite un processo batch.

<a name="additional-resources"></a>Risorse aggiuntive
--------

[Ordini cliente ibridi](hybrid-customer-orders.md)




