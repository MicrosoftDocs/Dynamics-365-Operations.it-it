---
title: Analisi dei risultati del questionario
description: Le statistiche del questionario possono essere utilizzate per calcolare medie, totali e percentuali in base a un set di dati demografici.
author: andreabichsel
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: KMQuestionnaireStatistics, KMQuestionnaireStatisticsLine, HcmLearningWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 135d74d70023fbe1f52b292c09733e77baa14003
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/18/2021
ms.locfileid: "6052915"
---
# <a name="analyzing-questionnaire-results"></a>Analisi dei risultati del questionario

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



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



[!INCLUDE[footer-include](../includes/footer-banner.md)]