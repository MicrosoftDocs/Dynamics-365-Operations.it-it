---
title: Convertire valute di contabilizzazione o di dichiarazione
description: "Una società che deve cambiare la valuta di contabilizzazione o la valuta di dichiarazione ha due opzioni."
author: aprilolson
manager: AnnBe
ms.date: 10/25/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 78223
ms.assetid: 31c56f9a-9c64-40a2-90e3-1969a760614b
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: ad840f4ed2cf27615e699a13fcd8be7f3c2cd5c8
ms.contentlocale: it-it
ms.lasthandoff: 11/03/2017

---

# <a name="convert-accounting-or-reporting-currencies"></a>Convertire valute di contabilizzazione o di dichiarazione

[!INCLUDE [banner](../includes/banner.md)]

Una società che deve cambiare la valuta di contabilizzazione o la valuta di dichiarazione ha due opzioni. La prima opzione è creare una nuova società e iniziare da zero. La seconda opzione è eseguire il processo di conversione delle valute di contabilizzazione e di dichiarazione. Si tratta di un processo molto lungo che modifica ogni transazione nel sistema. Prima di eseguire il processo, è necessario effettuare alcune impostazioni.

## <a name="preparing-the-legal-entity-for-currency-conversion"></a>Preparazione della persona giuridica per la conversione valutaria
Prima di poter convertire la valuta della persona giuridica, è necessario ripristinare tutti gli importi di rivalutazione valuta estera per i conti cliente e fornitore e chiudere gli anni fiscali precedenti. È inoltre necessario preparare il database per la conversione e quindi apportare le modifiche necessarie al conto della persona giuridica che viene sottoposto alla conversione valutaria. Dopo aver completato una conversione valutaria, è necessario completare alcune procedure aggiuntive. È necessario riconciliare le differenze di arrotondamento degli importi convertiti, ricalcolare le statistiche aziendali, inserire nel giornale di registrazione le transazioni contabili, limitare l'accesso allo strumento di conversione e rivalutare gli importi in valuta estera per i conti cliente e fornitore.

## <a name="setting-up-accounts-for-automatic-transactions"></a>Impostazione dei conti per le transazioni automatiche
Durante il processo di conversione valutaria i profitti o le perdite oppure le differenze in centesimi vengono registrate nei conti definiti nella pagina **Conti per transazioni automatiche**. I conti principali devono essere assegnati ai seguenti tipi di transazione prima dell'esecuzione del processo di conversione:

-   Profitto da conversione nella valuta di contabilizzazione
-   Perdita da conversione nella valuta di contabilizzazione
-   Differenza in centesimi nella valuta di contabilizzazione
-   Differenza in centesimi nella valuta di dichiarazione
-   Risultato di fine anno

## <a name="posting-rounding-differences-and-sum-recalculations"></a>Registrazione delle differenze di arrotondamento e ricalcolo delle somme
Di seguito vengono descritte le possibili differenze nell'arrotondamento:

-   Generazione di un report in cui vengono visualizzati il numero di prodotto, il tipo di modulo, il prezzo prima della conversione e l'unità, nel caso in cui i prezzi dei prodotti siano stati convertiti in 0 (zero).
-   Registrazione nel giornale di registrazione generale delle differenze di arrotondamento tra IVA e contabilità generale.
-   Ricalcolo degli importi di rivalutazione valuta estera e degli importi delle transazioni cliente e fornitore.
-   Creazione dei record di liquidazione cliente e fornitore per le differenze di arrotondamento per ogni transazione cliente e fornitore.
-   Registrazione nel giornale di registrazione generale delle differenze di arrotondamento per clienti e fornitori.
-   Ricalcolo degli importi dei costi liquidati e degli importi di rettifica dei costi nelle operazioni di magazzino chiuse.
-   Registrazione nel giornale di registrazione generale delle differenze di arrotondamento in Gestione articoli.
-   Ricalcolo delle scorte disponibili.
-   Ricalcolo degli importi totali nei giornali di registrazione generale.
-   Ricalcolo dei bilanci di chiusura di contabilità generale.
-   Ricalcolo dei saldi contabili.
-   Registrazione nel giornale di registrazione generale delle differenze di arrotondamento nella contabilità generale.
-   Ricalcolo delle transazioni contabili di apertura.
-   Ricalcolo dell'importo finale nei saldi contabili.

Se si effettua la conversione in una nuova valuta di contabilizzazione per la contabilità generale e si verifica un errore durante il ricalcolo degli importi totali o durante la registrazione delle differenze di arrotondamento, è necessario chiudere la pagina **Conversione valuta di contabilizzazione per la contabilità generale**. Vengono quindi ricalcolati gli importi totali e vengono registrate le differenze di arrotondamento.

## <a name="processing-the-currency-conversion"></a>Elaborazione della conversione valutaria
Quando si avvia il processo di conversione della valuta, tutti gli utenti devono disconnettersi dal sistema. È necessario definire la nuova valuta per la contabilità generale o di dichiarazione e i tassi di cambio. Quando si fa clic su **OK**, il processo viene eseguito e vengono aggiornate tutte le transazioni nel sistema. La conversione valutaria è un processo molto lungo. Una volta completato, sarà possibile vedere che la valuta di contabilizzazione o di dichiarazione è stata aggiornata nella pagina **Contabilità generale**.

## <a name="completing-the-currency-conversion"></a>Completamento della conversione valutaria
Dopo la conversione valutaria è necessario generare di nuovo tutti i report di riconciliazione per assicurarsi che tutti gli importi convertiti siano corretti.

-   Se la conversione della valuta di contabilizzazione per la contabilità generale causa differenze di arrotondamento, tali differenze non vengono registrate utilizzando il giustificativo in cui si è verificata la differenza di arrotondamento, bensì tramite il giustificativo immesso per le registrazioni di conversione. Dopo la conversione queste differenze di arrotondamento verranno incluse in tutti i report che effettuano la verifica per giustificativo e data. Questo comportamento è corretto e può essere ignorato.
-   Se nella riga del totale dei report di riconciliazione cliente e fornitore è presente un importo per la differenza che non era indicato prima della conversione, tale importo deve essere registrato. Il conto da utilizzare è il conto riepilogativo per clienti e fornitori. Il conto di contropartita è il conto CoGe per la perdita o il profitto da conversione.

Dopo aver eliminato tutti i giornali di registrazione transazioni contabili, è possibile inserire le transazioni contabili nel giornale di registrazione. Fare clic su **Contabilità generale** &gt; **Periodico** &gt; **Giornali di registrazione** &gt; **Inserimento nel giornale di registrazione**. È possibile rivalutare gli importi in valuta estera dopo la conversione valutaria, se la rivalutazione è obbligatoria. Si rivalutano gli importi in valuta estera selezionando **Standard** nel campo per la rivalutazione **Metodo**.

Per ulteriori informazioni, vedere [Inserire voci registrate nel giornale di registrazione](tasks/journalize-posted-journal-entries.md).


