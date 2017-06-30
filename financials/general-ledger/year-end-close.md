---
title: Chiusura di fine anno
description: "In questo argomento viene descritto la configurazione e la procedura richieste per l'esecuzione del processo di chiusura di fine anno della contabilità generale."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerClosingSheet
audience: Application User
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 14091
ms.assetid: c64eed1d-df17-448e-8bb6-d94d63b14607
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 50a6a23febc725eb05d30d5db4f97ca699607461
ms.contentlocale: it-it
ms.lasthandoff: 05/25/2017


---

# <a name="year-end-close"></a>Chiusura di fine anno

[!include[banner](../includes/banner.md)]


In questo argomento viene descritto la configurazione e la procedura richieste per l'esecuzione del processo di chiusura di fine anno della contabilità generale. 

Alla fine di un anno fiscale,è necessario eseguire il processo di chiusura di fine anno per trasferire i saldi iniziali al nuovo anno. La maggior parte delle organizzazioni eseguirà il processo di chiusura di fine anno più volte. La prima volta per spostare i saldi nel nuovo anno fiscale. La chiusura di fine anno può quindi essere nuovamente eseguita, il numero di volte necessario, per spostare i saldi dalle voci di rettifica nel nuovo anno fiscale. 

Durante la chiusura di fine anno, sono creati due tipi possibili di transazioni. Una transazione di apertura sempre viene generata e viene utilizzata per creare i saldi iniziali nel nuovo anno fiscale. La transazione di apertura mostra i saldi dei conti CoGe dello stato patrimoniale nel nuovo anno fiscale e i saldi dai conti CoGe profitti e perdite nel conto CoGe per gli utili non distribuiti nel nuovo anno fiscale. La transazione di chiusura facoltativamente viene creata per riportare a zero i saldi dei conti profitti e perdite nell'anno fiscale che viene chiuso.

## <a name="prepare-to-run-the-year-end-close"></a>Prepararsi alla chiusura di fine anno
Prima di eseguire la chiusura di fine anno, convalidare le impostazioni per i seguenti elementi: 

Nella pagina **Conto principale**:

-   Verificare che il **Tipo di conto principale** è definito in modo corretto per ogni conto principale. Il tipo di conto principale viene utilizzato per determinare se il saldo del conto principale verrà riportato come saldo iniziale o verrà chiuso negli utili non distribuiti nella transazioni di apertura.
-   Il campo **Conto di apertura** può essere utilizzato per trasferire il saldo del conto principale in un nuovo conto principale durante la chiusura di fine anno. Il nuovo conto principale viene immesso nel campo **Conto di apertura**. Questo viene in genere utilizzato per i conti principali dello stato patrimoniale quando il conto principale viene disattivato e un nuovo conto principale utilizzato per il nuovo anno fiscale.

Nella pagina **Parametri di contabilità generale** in **Chiusura anno fiscale**:

-   L'opzione **Elimina transazioni di fine anno** specifica se la transazione di apertura generato dal sistema da una precedente chiusura di fine anno deve essere eliminata quando la chiusura di fine anno viene nuovamente eseguita. Se l'opzione è impostata su **Sì** ** **, la transazione di apertura precedente verrà eliminata e una nuova transazione di apertura viene creata in base ai saldi correnti. Se l'opzione è impostata su **No**, la precedente transazione di apertura rimane e una transazione di apertura aggiuntivo viene creata per spostare i saldi in avanti dalle transazioni di rettifica registrate dopo la precedente chiusura di fine anno.
-   L'opzione **Crea transazioni di chiusura durante il trasferimento** viene utilizzata per creare le transazioni di chiusura dell'anno fiscale in chiusura per riportare i saldi dei conti profitti e perdite a zero. Se l'opzione è impostata su **Sì** ** **, la transazione di apertura e di chiusura vengono entrambe create. Se l'opzione è impostata su  **No**, soltanto la transazione di apertura viene creata nell'anno fiscale successivo per trasferire i saldi. I saldi dei conti profitti e perdite rimangono a fine anno fiscale.
-   L'opzione **Imposta stato anno fiscale su chiuso in modo permanente** viene utilizzata per impostare un anno fiscale definitivamente allo stato chiuso. Utilizzare questa impostazione con attenzione, poiché tutti i periodi con stato definitivamente chiuso non possono essere riaperti, impedendo alle rettifiche di essere registrato nell'anno fiscale. È consigliabile impostare questa impostazione su **No**.
-   L'opzione **È necessario compilare il numero del giustificativo** viene utilizzata per definire se un numero di giustificativo è obbligatorio quando si esegue il processo di chiusura di fine anno. È consigliabile richiedere un numero di giustificativo per identificare facilmente la transazione di apertura.

Nella pagina **Calendario fiscale**:

-   L'anno fiscale successivo deve essere già presente prima di eseguire la chiusura di fine anno. L'anno fiscale successivo viene utilizzato per creare i saldi iniziali nel periodo di apertura.

Nella pagina **Calendario contabilità generale**:

-   Facoltativo: Ogni periodo fiscale per l'anno fiscale che viene chiuso può essere impostato su **In attesa** per impedire nuove transazioni inserite. Quando le voci di rettifica vengono identificate, i periodi in attesa possono essere riaperti per registrare le voci di rettifica, anche se la chiusura di fine anno è già stato eseguito.

## <a name="define-year-end-close-templates"></a>Definire i modelli di chiusura di fine anno
Una volta configurato il sistema, è possibile eseguire il processo di chiusura di fine anno. Nella pagina **Chiusura di fine anno**, un modello può essere definito per il gruppo di persone giuridiche per cui il processo di chiusura di fine anno verrà eseguito. Il modello verrà riutilizzato a ogni chiusura di fine anno, ma può essere modificato se l'organizzazione viene modificata. 

Innanzitutto, definire il **Nome gruppo** del modello e selezionare il calendario fiscale. Nome del gruppo deve identificare il gruppo di persone giuridiche incluse.  Ad esempio, i modelli possono essere impostati in base alla posizione geografica, con gruppi distinti creati per le persone giuridiche nordamericane, le persone giuridiche EMEA e le persone giuridiche APAC. 

A questo punto, le persone giuridiche possono essere aggiunti al modello. Le persone giuridiche possono essere aggiunti selezionando una gerarchia organizzativa o le persone giuridiche. Se una gerarchia organizzativa è selezionata, solo le persone giuridiche nella gerarchia che adottano il calendario fiscale selezionato verranno aggiunti al modello. Se si utilizzano le persone giuridiche da aggiungere al modello, soltanto le persone giuridiche con lo stesso calendario fiscale possono essere aggiunte. Lo stesso calendario fiscale è necessario perché la chiusura di fine anno viene eseguita selezionando un anno fiscale, che può variare dal calendario al calendario. 

Dopo che le persone giuridiche vengono aggiunti, definire i conti principali di utili non distribuiti per ogni persona giuridica. Il campo **Data dell'ultima chiusura di fine anno** verrà aggiornato ogni volta che la chiusura di fine anno verrà eseguita per la persona giuridica. 

La scheda **Dimensione finanziaria** consente di definire le dimensioni finanziarie da utilizzare nella transazione di apertura. Tenere presente che le impostazioni da definire sono rilevanti solo alla persona giuridica selezionata nella griglia **Persone giuridiche**. Ripeterete l'impostazione per ogni persona giuridica nella griglia. 

**Trasferisci dimensioni di conto patrimoniale** viene utilizzato per definire se le dimensioni finanziarie nelle transazioni registrate nei conti dello stato patrimoniale devono essere mantenute nella transazione di apertura. È consigliabile impostare questa impostazione su **Sì**. **Trasferisci dimensioni di profitti e perdite** viene utilizzato per definire qualie dimensioni finanziarie nelle transazioni registrate nel conto profitti e perdite verranno trasferite nel conto principale utili non distribuiti. Innanzitutto, identificare le dimensioni finanziarie pertinenti alla persona giuridica selezionata. Sono inclusi tutte le dimensioni finanziarie in cui si è registrato durante l'anno, anche se la dimensione finanziaria non fa parte di una struttura dei conti attiva. Quindi, definire ogni dimensione come **Chiudi singolo** o **Chiudi tutte**.  Il valore predefinito è **Chiudi tutte**, che mantiene i valori di dimensione finanziaria originali delle transazioni registrate e li utilizza per creare i saldi iniziali per il conto utili non distribuiti. I saldi iniziali distinti per gli utili distribuiti verranno creati per ogni combinazione specifica di valori di dimensione finanziaria. Se **Chiudi singolo** è selezionata, tutte le transazioni registrate con quella dimensione finanziaria verranno riepilogate in un saldo iniziale utili non distribuiti per il valore di dimensione immesso nel campo dopo **Chiudi singolo**. Ad esempio, si supponga che tutte le transazioni per l'anno fiscale sono state registrate con la struttura dei conti del conto principale - Reparto. Nella dimensione finanziaria Reparto nel modello, **Chiudi singolo** è selezionata e 100 è il valore immesso. Se il ricavo totale di tutte le transazioni registrate per i reparti 200, 300 e 400 è $ 100.000, un saldo iniziale verrà creati per gli utili non distribuiti - 100. Se si seleziona **Chiudi singolo** e si lascia vuoto il valore della dimensione finanziaria, tutte le transazioni verranno registrate a utili non distribuiti con tale valore di dimensione vuoto. 

Il processo di chiusura di fine anno non corrisponde alle strutture dei conti. Questo è perché le strutture dei conti possono cambiare in un anno fiscale e non è sempre possibile identificare la struttura dei conti pertinente a causa delle modifiche.  Quando vengono create transazioni di apertura, i saldi vengono riportati con le dimensioni finanziarie definite nel modello di chiusura di fine anno. Le voci dei saldi iniziali potrebbero includere dimensioni finanziarie non più nella corrente struttura dei conti e combinazioni di segmenti non più valide nella struttura dei conti corrente. Se l'organizzazione desidera escludere una dimensione finanziaria per il saldo iniziale utili non distribuiti, impostare la dimensione finanziaria su **Chiudi singolo** e lasciare il valore di dimensione vuoto.

## <a name="run-the-year-end-close-process"></a>Eseguire il processo di chiusura di fine anno
Dopo che i modelli di chiusura di fine anno vengono creati, la chiusura di fine anno viene avviata scegliendo **Esegui chiusura fiscale** nel riquadro azioni. Selezionare tutte o un sottoinsieme di persone giuridiche dal modello per cui eseguire la chiusura di fine anno. Durante l'esecuzione della chiusura di fine anno per la prima volta in un anno fiscale, si sceglieranno probabilmente tutte le persone giuridiche per creare i saldi iniziali per tutte le persone giuridiche. Se si esegue nuovamente la chiusura di fine anno, è possibile scegliere di eseguire il processo solo per le persone giuridiche per cui voci di rettifica sono state registrate. 

Selezionare l'anno fiscale di cui si desidera eseguire la chiusura di fine anno. Se più periodi di chiusura esistono per l'ultimo periodo dell'anno fiscale,  il campo  **Nome periodo** diventerà disponibile in modo che sia possibile selezionare il periodo di chiusura per registrare la transazione di chiusura, se l'impostazione è definita per creare la transazione di chiusura. 

Immettere un numero di giustificativo, che può essere o meno obbligatorio, in base all'impostazione dei parametri di contabilità generale. Lo stesso numero di giustificativo verrà utilizzato per tutte le persone giuridiche selezionate per la chiusura di fine anno. Il numero di giustificativo non viene generato usando una sequenza numerica. È consigliabile immettere un numero di giustificativo, anche se non è obbligatorio. Se si inserisce un numero di giustificativo si facilita la ricerca della transazione di apertura del nuovo anno fiscale. Se un numero di giustificativo non viene immesso, il giustificativo è vuoto per la transazione di apertura. 

Se desidera stornare una chiusura di fine anno precedente per l'anno fiscale selezionato, impostare **Annulla chiusura precedente** su **Sì**. La chiusura di fine anno verrà stornata, ma il processo può essere rieseguito in qualsiasi momento. Se si storna una chiusura di fine anno, la **Data dell'ultima chiusura di fine anno*** non sarà disponibile. 

La chiusura di fine anno viene eseguita in modalità batch per impostazione predefinita. È consigliabile eseguire il processo in modalità batch, per consentire all'utente di tornare ad altre attività. Il campo **Data dell'ultima chiusura di fine anno** verrà aggiornato con la data della sessione al completamento del processo di chiusura di fine anno.

Per ulteriori informazioni, vedere [Chiudere la contabilità generale a fine periodo](close-general-ledger-at-period-end.md).




