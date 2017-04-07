---
title: Chiusura di fine anno
description: "In questo argomento viene descritto impostazione richiesta e Passaggi per l&quot;esecuzione del processo di chiusura di fine anno contabilità generale."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: LedgerClosingSheet
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 14091
ms.assetid: c64eed1d-df17-448e-8bb6-d94d63b14607
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 926ee087a0e0c4743f29315b1d82c7d37e95be28
ms.openlocfilehash: 22233cfa1df79076c8ea42f75ea309bac990d574
ms.lasthandoff: 03/31/2017


---

# <a name="year-end-close"></a>Chiusura di fine anno

In questo argomento viene descritto impostazione richiesta e Passaggi per l'esecuzione del processo di chiusura di fine anno contabilità generale. 

Alla fine di un anno fiscale, è necessario eseguire la chiusura di fine anno ai saldi iniziali di trasferimento nel nuovo anno. La maggior parte delle organizzazioni eseguirà i tempi di lavorazione più vicina di fine anno. La prima volta che sia di ottenere i saldi spostati nel nuovo anno fiscale. La chiusura di fine anno può quindi essere nuovamente eseguita, il numero di volte necessario, è necessaria per immettere i saldi dalle voci di rettifica nel nuovo anno fiscale. 

Durante la chiusura di fine anno, sono presenti due tipi possibili di transazioni create. Transazione di apertura sempre viene generata e viene utilizzata per creare i saldi iniziali nel nuovo anno fiscale. La transazione di apertura sono indicati i saldi dei conti CoGe dello stato patrimoniale nel nuovo anno fiscale e i saldi dai conti profitti e perdite di conto CoGe nel conto CoGe per gli utili distribuiti nel nuovo anno fiscale. La transazione di chiusura facoltativamente viene creata per riportare i saldi dei conti profitti e perdite per azzerare il drill-down nell'anno fiscale che è chiuso.

## <a name="prepare-to-run-the-year-end-close"></a>Prepararsi alla chiusura di fine anno
Prima di eseguire la chiusura di fine anno, convalidare le impostazioni per i seguenti elementi: 

Nella pagina **Conto principale**:

-   Convalida ** tipo di conto principale ** è definito in modo corretto per ogni conto principale. Il tipo di conto principale viene utilizzato per determinare se il saldo del conto principale verrà riportare come saldo di apertura o verrà chiuso negli utili non distribuiti nelle transazioni di apertura.
-   ** Conto di apertura ** il campo può essere utilizzato per trasferire il saldo del conto principale in un nuovo conto principale durante la chiusura di fine anno. Il nuovo conto principale viene immesso ** conto di apertura ** nel campo. Questo viene in genere utilizzato per i conti principali dello stato patrimoniale in cui il conto principale viene disattivato e un nuovo conto principale utilizzato per il nuovo anno fiscale.

** Parametri di contabilità generale ** alla pagina in ** chiusura anno fiscale **:

-   ** Eliminazione delle transazioni di anno ** l'opzione è possibile specificare se la transazione di apertura generato da una precedente chiusura di fine anno deve essere eliminata quando la chiusura di fine anno viene nuovamente eseguita. Se l'opzione è impostata su Sì ** **, la transazione di apertura precedente verrà eliminata e una nuova transazione di apertura viene creata in base ai saldi correnti. Se l'opzione è impostata alcuna ** **, il riportare precedente delle transazioni di apertura e una transazione di apertura aggiuntivo viene creata per spostare i saldi in avanti dalla rettifica delle transazioni registrate dopo la precedente chiusura di fine anno.
-   ** Creare transazioni di chiusura durante il trasferimento ** l'opzione viene utilizzata per creare le transazioni di chiusura dell'anno fiscale che è bloccato per riportare i saldi dei conti profitti e perdite a zero. Se l'opzione è impostata su Sì ** **, la transazione della transazione di chiusura di apertura viene creata. Se l'opzione è impostata alcuna ** **, soltanto le transazioni di apertura viene creata durante l'anno fiscale successivo per trasferire i saldi. I saldi dei conti profitti e perdite rimangono a fine anno fiscale.
-   ** Stato disponibile dell'anno fiscale a un chiuso ** l'opzione viene utilizzata per impostare un anno fiscale definitivamente allo stato chiuso. Utilizzare questa impostazione con attenzione, poiché tutti i periodi con stato definitivamente chiuso non possono essere riaperti, impedendo le rettifiche essere registrato all'anno fiscale. È consigliabile impostare questo consigliate ** non **.
-   ** Il numero di giustificativo deve essere inserito ** l'opzione viene utilizzata per definire se un numero è obbligatorio quando si esegue il processo di chiusura di fine anno. È consigliabile consigliate richiedere un numero di giustificativo per identificare facilmente la transazione di apertura.

** Calendario fiscale ** nella pagina:

-   Anno fiscale successivo deve essere già presente prima di eseguire la chiusura di fine anno. Anno fiscale successivo viene utilizzato per creare i saldi iniziali nel periodo di apertura.

** Calendario contabilità generale ** nella pagina:

-   Facoltativo: Ogni periodo fiscale per l'anno fiscale che viene chiuso può essere impostato su ** ** in attesa per impedire nuove transazioni inserire. Quando le voci di rettifica vengono identificate, in attesa i periodi possono essere riaperti per registrare le voci di rettifica, anche se la chiusura di fine anno è già stato eseguito.

## <a name="define-year-end-close-templates"></a>Consente di definire i modelli vicina di fine anno
Dopo che il sistema è configurato, la chiusura di fine anno può essere eseguito. ** Fine anno ** vicina alla pagina, un modello può essere definito per il gruppo di persone giuridiche per cui la chiusura di fine anno verrà eseguito. Il modello verrà riutilizzato a ogni chiusura di fine anno, ma può essere modificato se l'organizzazione viene modificato. 

Innanzitutto, definire ** nome del gruppo ** per il modello e selezionare il calendario fiscale. Nome del gruppo deve identificare il gruppo di persone giuridiche incluse.  Ad esempio, i modelli possono essere impostati in base alla posizione geografica, ai gruppi distinti creati per le persone giuridiche nordamericane, le persone giuridiche EMEA e le persone giuridiche APAC. 

A questo punto, le persone giuridiche possono essere aggiunti al modello. Le persone giuridiche possono essere aggiunti selezionando una gerarchia organizzativa o selezionando le persone giuridiche. Se una gerarchia organizzativa è selezionata, solo le persone giuridiche nella gerarchia che adottano il calendario fiscale selezionato verranno aggiunti al modello. Se si utilizzano le persone giuridiche da aggiungere al modello, soltanto le persone giuridiche con lo stesso calendario fiscale è possibile aggiungere. Lo stesso calendario fiscale è necessario perché la chiusura di fine anno viene eseguita selezionando un anno fiscale, che può variare dal calendario al calendario. 

Dopo che le persone giuridiche vengono aggiunti, definire gli utili non distribuiti ai conti principali per ogni persona giuridica. ** Data di chiusura di fine dell'anno precedente ** il campo verrà aggiornato automaticamente ogni chiusura di fine anno verrà eseguita per la persona giuridica. 

** Dimensione finanziaria ** la scheda consente di definire le dimensioni finanziarie da utilizzare nella transazione di apertura. Tenere presente che le impostazioni da definire sono rilevanti solo alla persona giuridica selezionata ** persone giuridiche ** nella griglia. Ripeterete l'impostazione per ogni persona giuridica nella griglia. 

** Dimensioni dello stato patrimoniale di trasferimento ** viene utilizzato per definire se le dimensioni finanziarie nelle transazioni registrate nei conti dello stato patrimoniale devono essere gestite nella transazione di apertura. È consigliabile consigliate impostare questa opzione su Sì ** **. ** Dimensioni profitti e perdite di trasferimento ** viene utilizzato per definire le dimensioni finanziarie nelle transazioni registrate nel conto profitti e perdite verrà trasferito nel conto principale utili non distribuiti. Innanzitutto, identificare le dimensioni finanziarie correlate alla persona giuridica selezionata. Sono inclusi tutte le dimensioni finanziarie registrate a fronte dell'anno, anche se la dimensione finanziaria non fa parte di una struttura dei conti attiva. A questo punto, definire tutte le dimensioni come o ** da selezionare o ** ** ** prodotti selezionati.  Il valore predefinito è ** prodotti selezionati **, che gestisce i valori di dimensione finanziaria originale delle transazioni registrate e le utilizzato per creare i saldi iniziali per il conto utili non distribuiti. I saldi iniziali distinti per gli utili distribuiti verranno creati per ogni combinazione specifica di valori di dimensione finanziaria. ** Se per singolo ** è selezionata, tutte le transazioni registrate con la dimensione finanziaria verranno riepilogate in un saldo iniziale utili non distribuiti per il valore di dimensione immesso nel campo dopo aver ** da scegliere **. Ad esempio, si supponga che tutte le transazioni per l'anno fiscale sono state registrate con la struttura dei conti del conto principale - Reparto. Nella dimensione finanziaria Reparto sul modello, ** singolo da ** è selezionata e il 100 al valore immesso. Se il ricavo totale di tutte le transazioni ha registrato ai reparti 200, 300 e 400 in $100,000, il saldo iniziale verranno creati per gli utili distribuiti a 100. ** Se si seleziona da scegliere ** e si lasciano vuoti di valori di dimensione finanziaria, tutte le transazioni registreranno a utili non distribuiti tale valore di dimensione che è vuoto. 

Il processo di chiusura di fine anno non corrisponde alle strutture dei conti. Poiché le strutture dei conti può essere modificato in un anno fiscale e non è sempre possibile identificare la struttura dei conti pertinenti a causa delle modifiche.  Quando vengono create transazioni di apertura, i saldi riportati con dimensioni finanziarie come definiti nel modello di chiusura di fine anno. Le voci dei saldi di apertura non possono includere le dimensioni finanziarie in più combinazioni di segmento corrente e della struttura dei conti non sono più validi nella struttura dei conti corrente. Se l'organizzazione desidera escludere una dimensione finanziaria per il saldo iniziale dell'utile non distribuiti, impostare la dimensione finanziaria da ** da scegliere ** e lasciare il valore di dimensione vuoto.

## <a name="run-the-year-end-close-process"></a>Eseguire la chiusura di fine anno
Dopo che i modelli vicina di fine anno vengono creati, la chiusura di fine anno viene avviato scegliendo ** anno fiscale di esecuzione ** nel riquadro azioni. Seleziona tutte le o un sottoinsieme persone giuridiche dal modello per cui eseguire la chiusura di fine anno. Durante l'esecuzione della chiusura di fine anno per la prima volta in un anno fiscale, attenersi sceglierete tutte le persone giuridiche per creare i saldi iniziali per tutte le persone giuridiche. Se si desidera eseguire nuovamente la chiusura di fine anno, è possibile scegliere di eseguire il processo solo per le persone giuridiche per cui le voci di rettifica registrate. 

Selezionare l'anno fiscale cui si desidera eseguire la chiusura di fine anno in base. Se più periodi di chiusura dell'ultimo periodo di un anno fiscale, ** nome del periodo ** il campo sarà disponibile in modo che sia possibile selezionare il periodo di chiusura per registrare la transazione di chiusura, se l'impostazione è definita per creare la transazione di chiusura. 

Immettere un numero di giustificativo, o che non sia obbligatorio, in base all'impostazione dei parametri di contabilità generale. Lo stesso numero di giustificativo verrà utilizzato per tutte le persone giuridiche selezionate per la chiusura di fine anno. Numero del giustificativo non viene generato in base a una sequenza numerica. È consigliabile consigliate immettere un numero di giustificativo, anche se non è obbligatorio. Se si inserisce un numero di giustificativo in modo più semplice la ricerca la transazione di apertura del nuovo anno fiscale. Se un numero di giustificativo viene lasciato vuoto, il giustificativo è vuoto per la transazione di apertura. 

Se desidera stornare una fine anno precedente chiusura per l'anno fiscale selezionato, con ** annullare una precedente chiusura ** ** Sì **. La chiusura di fine anno verrà stornata, ma il processo può essere ripetuta in qualsiasi momento. Se si storna una chiusura di fine anno, ** data di chiusura di fine dell'anno precedente ** non sia disponibile. 

Il processo di chiusura di fine anno viene impostato per l'esecuzione del processo batch. È consigliabile consigliate eseguire il processo batch, per consentire all'utente torna ad altre attività. Dopo la chiusura di fine anno è completato, ** data di chiusura di fine dell'anno precedente ** verrà aggiornato con la data della sessione.

Per ulteriori informazioni, vedere [chiudere la contabilità generale] alla fine del periodo (close-general-ledger-at-period-end.md).


