--- 
title: Analizzare i risultati del questionario
description: Le statistiche del questionario possono essere utilizzate per calcolare medie, totali e percentuali in base a un set di dati demografici.
author: ShielaSogge
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Operations
ms.search.region: Global
ms.author: shielas
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: c243a84b63215ab44e2929c64dbc4aced7061474
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---
# <a name="analyze-questionnaire-results"></a>Analizzare i risultati del questionario

[!include[task guide banner](../../includes/task-guide-banner.md)]

Le statistiche del questionario possono essere utilizzate per calcolare medie, totali e percentuali in base a un set di dati demografici. Per iniziare questa procedura, andare a Questionario > Visualizza e analizza risultati > Statistiche questionario. La società di dati dimostrativi utilizzata per creare questa procedura è USMF.


## <a name="create-a-questionnaire-statistics-record"></a>Creare un record di statistiche questionario
1. Andare a Statistiche questionario.
2. Fare clic su Nuovo.
3. Nell'elenco contrassegnare la riga selezionata.
4. Digitare un valore nel campo Statistiche.
5. Digitare un valore nel campo Descrizione.
6. Nel campo Questionario fare clic sul pulsante a discesa per aprire la ricerca.
7. Nell'elenco fare clic sul collegamento nella riga selezionata.
8. Fare clic sulla scheda Generale.
    * Selezionare se si desidera includere risultati anonimi o risultati di lavoratori, contatti e candidati.  
9. Selezionare o deselezionare la casella di controllo Lavoratore.
    * Se vengono visualizzati i risultati in base ad anzianità o età, specificare gli intervalli da utilizzare per raggruppare i risultati.  
    * Se si immette 5 per l'intervallo di età, i risultati verranno raggruppati in base a intervalli di cinque anni.  
10. Nel campo Età immettere un numero.
    * Selezionare se si desidera eseguire il calcolo per l'intero questionario, per ciascun gruppo di risultati, per ciascuna domanda o per ogni riga della domanda.  
    * Selezionare il modo in cui si desidera raggruppare i risultati.  
    * Ad esempio, se si calcolano i punti medi per domanda, è consigliabile visualizzare le domande raggruppate per gruppo di risultati.  
    * Selezionare i dati su cui basare il calcolo.  
    * Ad esempio, può essere opportuno visualizzare le percentuali medie ricevute nel questionario tra i lavoratori rispetto al numero medio di punti raggiunti tra i lavoratori.  
11. Fare clic sulla scheda Intervallo.
    * Utilizzare gli intervalli per limitare il set di risultati solo a quelli che soddisfano i criteri dell'intervallo.  
12. Fare clic sulla scheda Raggruppamento per.
    * Utilizzare i raggruppamenti per determinare il modo in cui i risultati devono essere visualizzati.  
    * Ad esempio, raggruppare i risultati prima per sesso, quindi per età.  
13. Nell'elenco trovare e selezionare il record desiderato.
    * Spostare i raggruppamenti nel lato selezionato e posizionarli nell'ordine desiderato.  

## <a name="execute-the-statistics-calculation"></a>Eseguire il calcolo delle statistiche
1. Fare clic su Esegui.
    * Selezionare la funzione di calcolo da eseguire sui risultati.  
    * Ad esempio, calcolare le percentuali medie nel questionario per i raggruppamenti selezionati o sommare i punti tra i gruppi di risultati per i raggruppamenti selezionati.  
2. Selezionare o deselezionare la casella di controllo Elimina le ricerche precedenti.
3. Fare clic su OK.

## <a name="view-the-results-of-the-questionnaire-statistics-run"></a>Visualizzare i risultati dell'esecuzione delle statistiche del questionario.
1. Fare clic su Risultato.
2. Fare clic su Risultato.
3. Chiudere la pagina.


