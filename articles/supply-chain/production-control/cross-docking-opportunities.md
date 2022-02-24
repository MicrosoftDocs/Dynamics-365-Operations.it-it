---
title: Eseguire il cross-docking da ordini di produzione a banchine di uscita
description: In questo argomento viene descritto come gestire il processo del materiale di cross-docking che viene dichiarato finito in una riga di produzione per una banchina di trasporto di uscita.
author: johanhoffmann
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSCrossDockOpportunityPolicy, WHSReservationHierarchy, WHSInventTableReservationHierarchy, WHSItemGroupLoadTemplate
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 1705903
ms.assetid: 427e01b3-4968-4cff-9b85-1717530f72e4
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 948db1f7308896209e195613d50b1d66b807b1bf
ms.sourcegitcommit: 827d77c638555396b32d36af5d22d1b61dafb0e8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "4431496"
---
# <a name="cross-docking-from-production-orders-to-outbound-docks"></a>Eseguire il cross-docking da ordini di produzione a banchine di uscita

[!include [banner](../includes/banner.md)]

In questo argomento viene descritto come gestire il processo del materiale di cross-docking che viene dichiarato finito in una riga di produzione per una banchina di trasporto di uscita.

<a name="introduction"></a>Introduzione
------------

Il cross-docking dalla produzione a una posizione di uscita è rilevante per i produttori che producono alti volumi e idealmente desiderano spedire i prodotti finiti non appena vengono dichiarati finiti nelle righe di produzione. L'obiettivo è la spedizione dei prodotti ai centri di distribuzione che si trovano fisicamente vicini alla richiesta di approvvigionamento, anziché l'accumulo nel sito di fabbricazione.

Nel caso non vi sia la domanda immediata di un prodotto, quest'ultimo deve essere stoccato nelle ubicazioni di magazzino presso il sito di fabbricazione. Questo processo viene detto *cross-docking opportunistico*, ossia indica se è presente una richiesta di spedizione del prodotto, nel qual caso si deve utilizzare questa opportunità anziché stoccare il prodotto per l'archiviazione interna.

Nel seguente esempio vengono illustrate tre variazioni di flusso che inizia alla fine della riga di produzione (2).

Un prodotto viene dichiarato finito per l'ubicazione di uscita di produzione (3) e un conducente di carrello elevatore prende il pallet nell'ubicazione (3).

-   Se è presente un'attività pianificata (6) per il trasferimento del prodotto dalla produzione (1) a un centro di distribuzione (7), l'autista del camion verrà istruito dal sistema di mettere il pallet presso un'ubicazione hangar (4).
-   Se un rimorchio è già assegnato all'hangar, l'autista del camion verrà istruito per caricare il prodotto direttamente nel rimorchio.
-   Se non è presente alcuna attività pianificata per il trasferimento del prodotto, il conducente del carrello elevatore verrà istruito di stoccare il prodotto in un'ubicazione del magazzino interno (5).

[![cross-docking opportunistico](./media/scenario1.png)](./media/scenario1.png)

## <a name="configure-cross-docking"></a>Configurare il cross-docking
Il processo di cross-docking si configura nei **criteri di lavoro**. I criteri di lavoro includono un tipo di ordine di lavoro, un'ubicazione e un prodotto. Nel seguente esempio, il cross-docking è configurato per il prodotto X e l'ubicazione Y.

#### <a name="work-order-types"></a>Tipi di ordine di lavoro

-   Tipo di ordine di lavoro: stoccaggio dei prodotti finiti
-   Metodo della creazione del lavoro: Cross-docking
-   Nome criteri di cross-docking: Ordini di trasferimento

#### <a name="inventory-locations"></a>Ubicazioni di magazzino

-   Magazzino: 51
-   Ubicazione: Y

#### <a name="products"></a>Prodotti

-   Numero articolo: X

Attualmente, il cross-docking può essere configurato per solo due tipi di ordini di lavoro:

-   Stoccaggio prodotti finiti
-   Stoccaggio co-prodotti e sottoprodotti

Nei **criteri di cross-docking** si definiscono i tipi di documento applicabili per il cross-docking. Attualmente, l'unico tipo di documento supportato è **Ordini di trasferimento**. Nel seguente esempio viene illustrata la configurazione dei criteri di cross-docking.

### <a name="cross-docking-policy-name-transfer-order"></a>Nome criteri di cross-docking: Ordine di trasferimento

- Numero progressivo: 10
  -   Tipo di ordine di lavoro: Uscita di trasferimento
- La domanda di cross-docking richiede un'ubicazione: Falso
- Strategia di cross-docking: Data e ora

### <a name="sequence-number"></a>Numero progressivo

Il **numero progressivo** indica la priorità del tipo di documento. Attualmente, l'unico tipo di documento supportato è **Uscita di trasferimento**. Di conseguenza, il numero progressivo è rilevante solo quando più tipi di ordine di lavoro sono supportati.

### <a name="cross-docking-policy"></a>Criteri di cross-docking

I criteri di cross-docking inoltre impostano i criteri per la priorità della richiesta dell'ordine di trasferimento. Ad esempio, se più ordini di trasferimento sono presenti per lo stesso prodotto, la data e l'ora programmate impostate nel carico e associate all'ordine di trasferimento stabiliscono la priorità tra gli ordini. La data e l'ora programmate possono essere impostate direttamente nel carico oppure possono essere impostate in una **programmazione appuntamenti** associata al carico. La priorità viene determinata dalla strategia di cross-docking. Attualmente, è presente una sola strategia: **Data e ora**.

### <a name="cross-docking-demand-requires-location"></a>La domanda di cross-docking richiede un'ubicazione

Nei criteri di cross-docking, è possibile impostare un criterio per richiedere che gli ordini di trasferimento siano assegnati a un'ubicazione per essere idonei al cross-docking. Questo criterio viene impostato nel campo **La domanda di cross-docking richiede un'ubicazione**. L'ubicazione della programmazione appuntamenti associata al carico viene utilizzata come ubicazione finale per le merci che vengono sottoposte al cross-docking. L'ubicazione finale per le merci sottoposte al cross-docking viene determinata dalla direttiva di ubicazione per **Uscita di trasferimento** per il tipo di ordine di lavoro **Inserisci**. È utile impostare il campo **La domanda di cross-docking richiede un'ubicazione** in uno scenario in cui i prodotti finiti devono essere sottoposti al cross-docking solo se un rimorchio è assegnato a un hangar. In questo scenario, le merci vengono spostate direttamente dalla riga di produzione nel rimorchio. Quando un rimorchio è assegnato all'hangar, l'utente assegna l'ubicazione alla programmazione appuntamenti rendendo così l'ubicazione valida per il cross-docking. Nelle seguenti sezioni vengono descritti due esempi.

#### <a name="scenario-1--cross-docking-from-production-to-transfer-orders"></a>Scenario 1: eseguire il cross-docking da ordini di produzione a ordini di trasferimento

Dopo che un prodotto viene dichiarato finito nella riga di produzione, viene trasferito in un'ubicazione di hangar dove viene caricato in un camion e trasferito a un centro di distribuzione. Usare la società USMF.

1.  Abilitare una nuova sequenza numerica per il cross-docking. Andare alla pagina **Sequenze numeriche** e selezionare il pulsante **Genera**. Il processo viene indicato da una procedura guidata.
2.  Creare i criteri di cross-docking. Andare alla pagina **Criteri di cross-docking** e creare i nuovi criteri denominandoli **Cross-docking per ordine di trasferimento**. Tenere presente che l'unico tipo di ordine che è possibile selezionare è **Uscita di trasferimento** e l'unica strategia di cross-docking disponibile è **Data e ora**.
3.  Creare i criteri di lavoro. Andare alla pagina **Criteri di lavoro** e creare i nuovi criteri di lavoro denominandoli **Cross-docking L0101**.
4.  Impostare i carichi in modo che vengano creati automaticamente per gli ordini di trasferimento. Nei parametri di magazzino, impostare i carichi in modo che vengano creati automaticamente alla creazione degli ordini di trasferimento. Un carico è un prerequisito per rendere l'ordine di trasferimento idoneo al cross-docking.
5.  Configurare il mapping carico articolo. Andare alla pagina **Mapping carico articolo** e impostare un modello predefinito di carico di lavoro per il gruppo di articoli **CarAudio**. Questo mapping inserisce automaticamente il modello di carico nel carico alla creazione dell'ordine di trasferimento.
6.  Creare un ordine di trasferimento. Creare l'ordine di trasferimento per il numero di articolo L0101. Quantità = 20.
7.  Rilasciare l'ordine di trasferimento dal workbench pianificazione del carico. Nella scheda **Spedizione**, selezionare la voce di menu per il workbench pianificazione del carico e nel menu **Rilascia** della riga di carico selezionare **Rilascia in magazzino**. Una riga di ondata aperta di tipo **Uscita di trasferimento** viene creata per l'ordine di trasferimento.
8.  Creare un ordine di produzione. Andare alla pagina elenco **Ordine di produzione** e creare un ordine di produzione per il prodotto L0101. Quantità = 20. Stimare e avviare l'ordine di produzione. Il campo **Registra distinta di prelievo ora** resta impostato su **No**.
9.  Dichiarare finito dal dispositivo mobile. Andare al portale del dispositivo mobile e selezionare la voce **Dichiarato di finito e stoccato**. Dichiarare finito L0101 dal dispositivo portatile. Quantità = 10. Si noti che l'ubicazione di stoccaggio è **BAYDOOR**. Questa ubicazione viene rilevata dalla direttiva di ubicazione **Uscita di trasferimento** per il tipo di ordine di lavoro **Inserisci**. Si noti anche che il lavoro di tipo **Uscita di trasferimento** è stato creato e completato. Passare ai dettagli dell'ordine di trasferimento per verificare il lavoro.
10. Ora dichiarare altri 10 pezzi dal dispositivo mobile. Si noti che l'ubicazione di stoccaggio è ancora **BAYDOOR**. Si noti anche che è stato creato un nuovo lavoro di tipo **Uscita di trasferimento** per i 10 pezzi.
11. Provare iniziando con 20 pezzi in più nell'ordine di produzione e quindi provare a definire finite 20 unità utilizzando il dispositivo portatile. Questa volta, l'ubicazione **LP-001** viene suggerita come ubicazione di stoccaggio. Questa ubicazione viene rilevata dalla direttiva di posizione per **Stoccaggio prodotti finiti**. Questa direttiva ubicazione viene utilizzata poiché non esiste alcuna opportunità per il cross-docking. L'ordine di trasferimento per LP-001 è stato completato dalla due attività di cross-docking nei passaggi 9 e 10. Si noti che è stato creato ed elaborato il lavoro di tipo **Stoccaggio prodotti finiti**.

#### <a name="scenario-2---cross-docking-from-production-to-transfer-orders-with-an-appointment-schedule"></a>Scenario 2: cross-docking dalla produzione agli ordini di trasferimento con una programmazione appuntamenti

Dopo che un prodotto viene dichiarato finito nella riga di produzione, viene trasferito a un'ubicazione hangar identificata da una programmazione appuntamenti per ubicazioni hangar. Usare la società USMF.

1.  Modificare i criteri di cross-docking. Modificare i criteri di cross-docking creati nello scenario 1 selezionando la casella di controllo **La domanda di cross-docking richiede un'ubicazione**.
2.  Consente di creare un nuovo ordine di trasferimento.
3.  Aprire la pagina **Workbench pianificazione carico**.
4.  Dal workbench pianificazione del carico, passare alla sezione **Carichi** e selezionare **Programma appuntamento** dal menu **Trasporti** per creare una nuova programmazione appuntamenti. Si noti che la programmazione appuntamenti contiene un riferimento all'ordine di trasferimento nel campo **Numero di ordine**. Nel campo **Data/ora di inizio pianificate nella postazione**, è possibile impostare la data e l'ora dell'appuntamento. Questa data e ora verranno utilizzate per stabilire la priorità della domanda di cross-docking durante il processo di cross-docking. La data e l'ora impostate in questo campo aggiorneranno il campo **Data e ora di spedizione programmata carico** del carico corrispondente. L'ubicazione nella scheda dettaglio **Dettagli di spedizione** determina l'ubicazione in cui l'ordine di trasferimento viene spedito.
5.  Nel rilascio **Workbench pianificazione carico** nel magazzino.
6.  Creare un ordine di produzione per il numero di articolo **L0101** e impostare lo stato su **Iniziato** con una quantità pari a 20.
7.  Dichiarare finito dal dispositivo mobile.
8.  Andare al portale del dispositivo mobile e selezionare la voce di menu **Dichiarato di finito e stoccato**.
9.  Dichiarare finito il numero di articolo **L0101** dal dispositivo portatile. Si noti che l'ubicazione di stoccaggio ora è **BAYDOOR 2**. Questa ubicazione deriva dalla programmazione appuntamenti anziché dalla direttiva di posizione **Entrata trasferimento**.

### <a name="additional-information"></a>Informazioni aggiuntive

-   Lo scenario di cross-docking è supportato per gli articoli controllati di serie e batch, entrambi con dimensioni di numero di serie e batch definite sopra e sotto l'ubicazione nella gerarchia di prenotazione. 


