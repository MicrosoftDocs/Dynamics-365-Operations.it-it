---
title: Panoramica arrivi
description: In questo articolo vengono fornite informazioni sulle funzionalità della panoramica arrivi. La pagina della panoramica arrivi è parte di questa funzionalità e fornisce una panoramica di tutti gli articoli con arrivo previsto come articoli in arrivo.
author: yufeihuang
ms.date: 11/02/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WMSArrivalOverview, WMSArrivalOverviewProfile, WMSJournalTable
audience: Application User
ms.reviewer: kamaybac
ms.custom:
- "274363"
- intro-internal
ms.assetid: 375807b2-a426-4f1b-bc1f-2fe00fd48413
ms.search.region: global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.dyn365.ops.version: AX 7.0.0
ms.search.validFrom: 2016-02-28
ms.openlocfilehash: 8118db9469c01c43b23c64ee383ac1d383a0ba7a
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8874074"
---
# <a name="arrival-overview"></a>Panoramica arrivi

[!include [banner](../includes/banner.md)]

In questo articolo vengono fornite informazioni sulle funzionalità della panoramica arrivi. La pagina della panoramica arrivi è parte di questa funzionalità e fornisce una panoramica di tutti gli articoli con arrivo previsto come articoli in arrivo.

La pagina **Panoramica arrivi** offre una panoramica di tutti gli articoli in arrivo previsti. La pagina mostra inoltre gli arrivi che possono essere inizializzati in base alla panoramica. Questo articolo riguarda il processo di ricezione.

## <a name="business-scenario"></a>Scenario aziendale
Si prenda in considerazione il seguente scenario nei processi in entrata.

[![Scenario aziendale.](./media/arrival-overview-scenario.png)](./media/arrival-overview-scenario.png)

Sammy, un addetto alla ricezione articoli, desidera informazioni sull'arrivo di articoli previsto per il giorno corrente. Nella pagina **Panoramica arrivi**, Sammy può ottenere una panoramica delle attività correnti e visualizzare una stima approssimativa di quantità, volume, peso, tipi di ordine diversi e così via. Successivamente, una consegna arriva a una delle banchine di entrata e Sammy riceve un elenco della consegna. Nella pagina **Panoramica arrivi** Sammy può eseguire le attività seguenti:

-   Identificare l'ordine di ricezione e registrare l'entrata come **In corso**. Le righe necessarie per la registrazione vengono generate automaticamente e l'entrata può essere monitorata, anche se le transazioni non sono ancora state registrate come **Registrate**.
-   Accedere al riferimento appropriato del giornale di registrazione arrivi (ovvero il giornale di registrazione **Arrivo articoli** o il giornale di registrazione **Entrata produzione**) e identificare i giornali di registrazione pronti per un aggiornamento dell'entrata prodotti.

## <a name="arrival-overview-page"></a>Pagina panoramica arrivi
Per aprire la pagina **Panoramica arrivi** fare clic su **Gestione articoli** &gt; **Ordini in entrata** &gt; **Panoramica arrivi**. È possibile visualizzare un elenco di ordini previsti per la ricezione. La panoramica è suddivisa nell'intestazione e nelle righe. Le informazioni di intestazione vengono raggruppate per tipo di ordine, data di ricezione prevista e destinazione di consegna. Quando una riga di intestazione viene selezionata per l'arrivo, tutte le righe dei dettagli relative al riferimento della ricezione sono selezionate per l'arrivo nella parte dettagli riga della pagina. Quando tutte le righe correlate del giornale di registrazione sono state registrate, queste informazioni non vengono visualizzate.

### <a name="arrival-overview-profiles"></a>Profili panoramica arrivi

La pagina **Panoramica arrivi** fornisce una panoramica degli articoli per cui è previsto l'arrivo e la data prevista per l'arrivo. Durante il processo di arrivo, è possibile utilizzare diverse impostazioni personali. I singoli utenti possono definire le relative impostazioni personali nella pagina **Profili panoramica arrivi**.

### <a name="set-up-item-arrival"></a>Impostare l'arrivo articoli

Nell'esempio, Sammy desidera impostare un nuovo computer con un'ubicazione che verrà utilizzata per ricevere i prodotti finiti che provengono dalla produzione al Sito 1. Nella pagina **Profili panoramica arrivi**, Sammy crea una nuova impostazione denominata **Produzione Sito 1** e specifica le seguenti impostazioni come descritto di seguito.

1.  Nella scheda dettaglio **Opzioni arrivi**, nel gruppo di campi **Intervallo**, immettere le informazioni relative a un intervallo di giorni e ai magazzini da includere nella panoramica.
2.  Nella scheda dettaglio **Opzioni arrivi** nel gruppo di campi **Giornale di registrazione** immettere il magazzino ricevente, un'ubicazione e un nome di giornale di registrazione (arrivo articoli/entrata produzione).
3.  Nella scheda dettaglio **Dettagli query arrivi**, nel gruppo di campi **Sito**, in **Limita al sito**, immettere un sito per limitare la visualizzazione nell'area di panoramica.
4.  Nella scheda dettaglio **Dettagli query arrivi**, nel gruppo di campi **Tipi di transazione visualizzati**, impostare l'opzione **Ordini di produzione** su **Sì**.
5.  Nella scheda dettaglio **Dettagli query arrivi**, nel gruppo **Varie**, impostare l'opzione **Aggiorna all'avvio** su **Sì** se la visualizzazione deve essere aggiornata automaticamente all'avvio. Impostare l'opzione **Aggiorna in caso di modifica intervalli** su **Sì** se la visualizzazione deve essere aggiornata automaticamente quando i valori dell'intervallo vengono modificati.

Per questo esempio, il campo **Nome profilo panoramica arrivi** della scheda dettaglio **Opzioni arrivi** della pagina **Panoramica arrivi** è impostato su **Produzione Sito 1**.

### <a name="prerequisites-for-arrival-journals"></a>Prerequisiti per i giornali di registrazione arrivi

Per creare automaticamente i giornali di registrazione arrivi dalla pagina **Panoramica arrivi**, è necessario definire le informazioni appropriate nel gruppo di campi **Giornale di registrazione** nelle opzioni della Scheda dettaglio **Opzioni arrivi**.

-   Per creare un giornale di registrazione è necessario specificare un nome per il giornale.

[![Impostazione di un nome di giornale di registrazione.](./media/arrival-overview-journal.png)](./media/arrival-overview-journal.png)

-   Se si specificano i valori nei campi **Magazzino** e **Ubicazione**, questi valori vengono applicati alle righe del giornale di registrazione. Se non si specificano i valori, verranno utilizzati i valori della dimensione specificata nelle transazioni di magazzino.

#### <a name="items-that-are-received-from-one-expected-receipt-order"></a>Articoli ricevuti da un ordine di ricezione previsto

Nella scheda dettaglio **Entrate**, Sammy seleziona una riga e quindi fa clic su **Inizia arrivo**. Tutte le righe presenti nell'intervallo specificato e con una quantità da registrare vengono selezionate automaticamente. Viene generato un giornale di registrazione arrivi con una corrispondenza tra l'ordine di entrata prevista e il giornale di registrazione. La quantità viene inizializzata automaticamente in tutte le righe create.

#### <a name="items-that-are-received-from-more-than-one-expected-receipt-order"></a>Articoli ricevuti da più di un ordine di ricezione previsto

Nella scheda dettaglio **Entrate**, Sammy seleziona più righe e quindi fa clic su **Inizia arrivo**. Viene generato un giornale di registrazione arrivi con una corrispondenza tra tutti gli ordini di entrata prevista e il giornale di registrazione. Tutte le righe vengono create in un'intestazione del giornale di registrazione arrivi e la quantità viene inizializzata automaticamente.

### <a name="receive-items-from-one-or-more-expected-receipt-orders"></a>Ricezione di articoli da uno o più ordini di ricezione prevista

#### <a name="view-information"></a>Visualizza informazioni

Per ottenere una panoramica degli arrivi previsti in un intervallo di date, Sammy immette le seguenti informazioni nei campi della scheda dettagli **Opzioni arrivi** della pagina **Panoramica arrivi** e quindi sceglie **Aggiornamento** per aggiornare la visualizzazione:

-   Nome profilo panoramica arrivi: **Richiesta info**
-   Mostra righe: **Tutte**
-   Giorni precedenti: (vuoto)
-   Giorni successivi: **0**
-   Magazzini: **GW, MW**

Sammy può visualizzare le seguenti informazioni:

-   Tutti gli ordini di ricezione correlati per la data di sistema e un numero illimitato di giorni precedenti rispetto a tale data (l'intervallo **InventTrans.StatusDate**) e gli arrivi nei magazzini GW e MW, indipendentemente dallo stato.
-   Informazioni dettagliate sulla riga per più ordini. Sammy può selezionare più righe intestazione nella panoramica e quindi fare clic su **Mostra tutta la selezione** per visualizzare tutte le informazioni dettagliate sulla riga corrispondente per tutti gli ordini selezionati.
-   Informazioni su un ordine fornitore specifico. Per visualizzare solo le informazioni relative a un numero di riferimento specifico nella panoramica, Sammy può immettere un numero di conto nel campo **Numero conto** e un numero di ordine nel campo **Numero di riferimento**.
-   Una panoramica delle attività di registrazione in scadenza per tutte le righe ordine per cui un giornale di registrazione arrivi è stato creato ma non è ancora stato registrato. Per visualizzare queste informazioni, Sammy può selezionare **In corso** nel campo **Mostra righe**.

### <a name="update-journals"></a>Giornali di registrazione aggiornamenti

Per registrare una o più righe ordine che devono essere elaborate, Sammy può selezionare le righe nella griglia panoramica o nella griglia della riga e fare clic su **Giornali di registrazione** &gt; **Mostra arrivi da ricevimenti** Vengono mostrate le intestazioni arrivi articoli che corrispondono alle righe. Per aggiornare l'entrata prodotti ordini fornitore per gli articoli registrati, Sammy può accedere alle intestazioni del giornale di registrazione arrivi articoli pronti per l'aggiornamento. Per accedere alle intestazioni del giornale di registrazione arrivi, Sammy può fare clic su **Giornali di registrazione** &gt; **Giornali di registrazione pronti per entrata prodotti**. Tutte le righe di intestazione pronte per l'aggiornamento dell'entrata prodotti nell'intervallo di magazzini vengono visualizzate. Le righe di intestazione visualizzate non sono correlate all'intervallo giorni.

### <a name="start-an-arrival-registration"></a>Avviare una registrazione arrivi

Selezionando più righe nella pagina **Panoramica arrivi**, Sammy può avviare un arrivo di più di un riferimento di ricezione. Quando Sammy seleziona una riga dalla panoramica arrivi, i dettagli riga corrispondenti vengono selezionati. Se una quantità per la registrazione è disponibile, il pulsante **Inizia arrivo** sarà disponibile. Sammy può utilizzare due metodi per avviare la registrazione arrivi:

-   Per filtrare la pagina in modo da visualizzare solo i record che soddisfano i criteri specifici, nel campo **Riferimento fornitore**, cercare un numero di riferimento di un fornitore, ad esempio il codice a barre per una bolla di consegna.
-   Nella parte di panoramica o nella parte dei dettagli della pagina **Panoramica arrivi**, selezionare manualmente o annullare la selezione dei record per la registrazione arrivi. In seguito, quando Sammy farà clic su **Inizia arrivo**, i record selezionati verranno creati automaticamente in un giornale di registrazione arrivi articoli. I record includono le informazioni sulle righe e tutte le informazioni univoche del campo univoco vengono assegnate.

## <a name="update-arrival-information-and-process-a-product-receipt"></a>Aggiornare le informazioni arrivi ed elaborare un'entrata prodotti
Una volta registrate tutte le merci, il responsabile del magazzino o il responsabile degli acquisti può aggiornare gli articoli ricevuti con un'entrata prodotti per aggiungere il costo fisico. Per aggiornare le informazioni sull'arrivo e per registrare un'entrata prodotti, effettuare le seguenti operazioni.

1.  Fare clic su **Gestione articoli** &gt; **Ordini in entrata** &gt; **Panoramica arrivi**.
2.  Nella pagina **Panoramica arrivi**, fare clic su **Giornali di registrazione** &gt; **Giornali di registrazione pronti per entrata prodotti** per visualizzare un elenco dei giornali di registrazione pronti per l'aggiornamento dell'entrata prodotti.
3.  Selezionare i giornali che devono essere aggiornati e fare clic su **Funzioni** &gt; **Entrata prodotti**.
4.  Nella pagina **Registrazione** immettere il numero dell'entrata prodotti, se non è già disponibile nel giornale di registrazione, e fare clic su **OK** per l'elaborazione dell'entrata prodotti.

## <a name="summary"></a>Riepilogo
La pagina **Panoramica arrivi** consente al responsabile del magazzino e agli addetti al magazzino di ottenere una panoramica del lavoro previsto che deve essere svolto come parte di un processo in entrata. Nella pagina può inoltre essere utilizzata per avviare il processo di registrazione arrivi articoli, per garantire che gli articoli vengano aggiornati alla prima immissione nel magazzino.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]