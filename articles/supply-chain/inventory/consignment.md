---
title: Spedizione
description: In questo argomento viene illustrato come usare i processi di inventario spedizione in entrata.
author: perlynne
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ConsignmentDraftReplenishmentOrderJournal, ConsignmentProductReceiptLines, ConsignmentReplenishmentOrder, ConsignmentVendorPortalOnHand, InventJournalOwnershipChange, InventOnHandItemListPage, PurchTable, PurchVendorPortalConfirmedOrders
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 220834
ms.assetid: 3c9d6de4-45d4-459a-aef7-0d9ad2c22b3a
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: a6e3f0e58e14cc4d68d2249a4e3b69515f23e838
ms.contentlocale: it-it
ms.lasthandoff: 05/25/2017

---

# <a name="consignment"></a>Spedizione

[!include[banner](../includes/banner.md)]


In questo argomento viene illustrato come usare i processi di inventario spedizione in entrata.

L'inventario spedizione è l'inventario che appartiene a un fornitore ma immagazzinato presso il sito del cliente. Quando si è pronti per consumare o utilizzare l'inventario, si assume la proprietà dell'inventario. In questo argomento vengono fornite informazioni su come ricevere fisicamente inventario disponibile di proprietà del fornitore senza creare transazioni di contabilità generale, come avviare un processo di produzione in cui l'inventario di proprietà del fornitore può essere prenotato fisicamente e come modificare la proprietà di materie prime per poter elaborare il consumo come parte dell'elaborazione degli ordini di produzione. Sono incluse anche alcune informazioni su come i fornitori possono monitorare il consumo del loro inventario mediante l'interfaccia di collaborazione fornitore. Per informazioni su come abilitare e configurare i processi di spedizione in entrata, vedere [Impostazione della spedizione](set-up-consignment.md).

## <a name="overview-of-the-consignment-process"></a>Panoramica del processo di spedizione
In questo scenario di esempio, la società USMF ha un accordo di spedizione con il fornitore US-104 per le materie prime M9211CI.

1.  Un ordine di rifornimento spedizione viene creato manualmente da un utente in USMF, in base alla domanda prevista. L'ordine viene creato per il fornitore US-104 e viene aggiunta una riga per l'articolo MS9211CI.
2.  Il fornitore viene notificato sulla consegna prevista. Questo può verificarsi in uno dei tre modi seguenti:
    -   Qualcuno che lavora in USMF invia le informazioni sull'ordine al fornitore.
    -   Il fornitore può monitorare l'inventario disponibile previsto cliente utilizzando l'interfaccia di collaborazione fornitore.
    -   Qualcuno che lavora in USMF filtra i dati nella pagina **Scorte disponibili** per visualizzare solo i record per il fornitore US-104 in cui lo stato di entrata è **Ordinato** e invia queste informazioni al fornitore.

3.  L'inventario viene consegnato da US-104 a USMF.
4.  Quando arriva il materiale a USMF, l'ordine di rifornimento spedizione viene aggiornato con un'entrata prodotti. Solo le quantità fisiche stato dell'inventario di proprietà del fornitore vengono registrate. Non sono create transazioni di contabilità generale, poiché l'inventario è ancora di proprietà del fornitore.
5.  Il fornitore monitora gli aggiornamenti all'inventario fisico disponibile utilizzando la pagina **Inventario spedizione disponibile**.
6.  Ora che l'inventario fisico è disponibile, il processo di produzione prenota l'inventario di proprietà del fornitore e avvia l'ordine di produzione per i prodotti finiti che utilizzeranno le materie prime M9211CI.
7.  Il proprietario delle materie prime prenotate che verranno consumate nella produzione odierna verrà modificato da US-104 a USMF. Questa operazione può essere effettuata mediante un giornale di registrazione modifiche proprietà inventario. Questo processo crea gli ordini fornitore dove il campo **Origine** è impostato su **Spedizione**.
8.  Il fornitore monitora il consumo (cambio di proprietà) nella pagina **Prodotti entrati da inventario spedizione** ed emette una fattura in base agli accordi tra le due società.
9.  Il processo di produzione utilizza le materie prime tramite una distinta di prelievo produzione. La prenotazione fisica viene aggiornata automaticamente per riflettere che l'inventario disponibile è di proprietà di USMF.
10. La fattura da US-104 viene elaborata a fronte degli ordini fornitore generati automaticamente quando il giornale di registrazione modifiche proprietà inventario è stato elaborato. Il pagamento viene effettuato al fornitore US-104 per l'inventario consumato.

USMF eseguirà i processi periodici aggiuntivi:

-   Lo spostamento fisico dell'inventario di proprietà del fornitore tra magazzini diversi viene elaborato tramite un giornale di registrazione trasferimenti.
-   L'inventario fisico disponibile viene aggiornato utilizzando un giornale**Conteggio articoli**. Il conteggio può essere utilizzato dal fornitore per aggiornare l'inventario disponibile, se è autorizzato a tale operazione.

Il fornitore, US-104, può monitorare gli aggiornamenti utilizzando la pagina **Inventario spedizione disponibile**.

## <a name="consignment-replenishment-orders"></a>Ordini di rifornimento spedizione
Un ordine di rifornimento spedizione è un documento utilizzato per richiedere e tenere traccia delle quantità delle scorte di prodotti che un fornitore desidera consegnare all'interno di un determinato intervallo di date creando transazioni di magazzino ordinato. In genere, questo verrà base alla previsione e sulla domanda effettiva dei prodotti specifici. L'inventario che verrà ricevuto rispetto all'ordine di rifornimento spedizione rimane di proprietà del fornitore. Solo il possesso dei prodotti correlati all'aggiornamento dell'entrata fisica viene registrato e quindi non si verifica alcuna transazione di contabilità generale. La dimensione **Proprietario** viene utilizzata per separare le informazioni su quale inventario appartiene al fornitore e quale appartiene alla persona giuridica ricevente. Le righe ordine di rifornimento spedizione hanno uno stato **Ordine aperto** fino a quando l'intera quantità delle righe non è stata ricevuta o annullata. Quando la quantità totale è stata ricevuta o annullata, lo stato viene cambia in **Completato**. L'inventario fisico disponibile correlato a un ordine di rifornimento spedizione può essere registrato mediante un processo di registrazione oltre che un processo di aggiornamento di entrata prodotti. La registrazione può essere effettuata durante il processo di arrivo articoli o manualmente mediante l'aggiornamento delle righe ordine. Quando il processo di aggiornamento dell'entrata prodotti viene utilizzato, viene aggiunta una registrazione nel giornale di registrazione entrata prodotti, che può essere utilizzata per confermare le entrate di merci ai fornitori.

[![consignment-replenishment-order](./media/consignment-replenishment-order.png)](./media/consignment-replenishment-order.png)

## <a name="inventory-ownership-change-journal"></a>Giornale di registrazione modifiche proprietà inventario
Il processo di modifica del proprietario dal fornitore alla persona giuridica ricevente viene eseguito mediante un giornale di registrazione modifiche proprietà inventario. Non vengono create transazioni di magazzino previste per il giornale di registrazione. Le sole transazioni di magazzino creare sono quelle relative al giornale registrato. Quando il giornale viene registrato:

-   L'inventario di proprietà del fornitore viene emesso utilizzando un riferimento **Modifica proprietà** con stato **Venduto**.
-   L'inventario disponibile verrà ricevuto dalla persone giuridica che lo consuma utilizzando una transazione di magazzino entrata prodotti nell'ordine fornitore. In questo modo viene impostato lo stato dell'ordine su **Ricevuto**.. Gli ordini fornitore utilizzati per la spedizione hanno il campo **Origine** impostato su **Spedizione**.

Non è possibile aggiornare la quantità nelle righe di ordine fornitore spedizione dopo che l'ordine è stato creato.

[![inventory-ownership-change-journal](./media/inventory-ownership-change-journal.png)](./media/inventory-ownership-change-journal.png)

## <a name="vendor-collaboration-in-consignment-processes"></a>Collaborazione fornitore nei processi di spedizione
L'interfaccia di collaborazione fornitore ha tre pagine correlate al processo di spedizione in entrata:

-   **Ordini fornitore** **che utilizzano inventario spedizione** - Mostra informazioni dettagliate sugli ordini fornitore relativi alla modifica di proprietà dal processo di spedizione.
-   **Prodotti entrati da inventario spedizione** - Mostra informazioni su articoli e le quantità con entrate prodotti aggiornate durante il processo di modifica proprietà.
-   **Inventario spedizione disponibile** - Consente di visualizzare le informazioni sugli articoli di spedizione previsti per la consegna e gli articoli fisicamente disponibili il sito del cliente.
