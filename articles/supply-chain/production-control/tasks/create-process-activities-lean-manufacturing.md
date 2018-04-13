--- 
title: "Creare le attività di processo per la lean manufacturing"
description: "Creare un'attività di processo per lean manufacturing."
author: cvocph
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: dd77c20b622fd8a14e1cdf77883043699f9a6317
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---
# <a name="create-process-activities-for-lean-manufacturing"></a>Creare le attività di processo per la lean manufacturing

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

Creare un'attività di processo per lean manufacturing. 

Prerequisiti: 

1. Un flusso di produzione e una versione non attiva devono essere creati.

2. Una cella di lavoro deve essere creata.


## <a name="find-the-production-flow-version"></a>Trovare la versione del flusso di produzione
1. Andare a Controllo produzione > Impostazioni > Flusso di produzione snella > Flussi di produzione.
2. Nell'elenco trovare e selezionare il record desiderato.
3. Nell'elenco fare clic sul collegamento nella riga selezionata.

## <a name="create-a-new-activity"></a>Creare una nuova attività
1. Fare clic su Attività.
    * Verificare che il flusso di produzione selezionato abbia una versione in bozza e selezionare tale versione.  
2. Fare clic su Crea nuova attività piano.
3. Scegliere Avanti.
4. Digitare un valore nel campo Nome.
5. Digitare un valore nel campo Nome.
    * Si noti che il nome deve essere univoco per un flusso di produzione specificato per tutte le versioni.  
6. Nel campo Quantità di lavorazione immettere un numero.
    * Si noti che qualsiasi quantità di processo venga elaborata, questa è la quantità minima per processo per calcolare il costo della manodopera. Se le quantità di processo deviano da questa quantità, uno scostamento costo della manodopera verrà creato.  
7. Scegliere Avanti.

## <a name="select-the-work-cell"></a>Selezionare la cella di lavoro
1. Nel campo Cella di lavoro fare clic sul pulsante a discesa per aprire la ricerca.
2. Nell'elenco fare clic sul collegamento nella riga selezionata.

## <a name="define-the-inventory-updates"></a>Definire gli aggiornamenti di inventario
1. Selezionare o deselezionare la casella di controllo Aggiorna entrata disponibile.
    * Se Aggiorna disponibilità = No, è possibile definire l'attività in modo da ricevere un prodotto semilavorato (l'attività non raggiunge il livello DBA successivo).    È inoltre possibile scegliere di utilizzare prodotti semilavorati.  

## <a name="define-the-picking-activities"></a>Definire le attività di prelievo
1. Scegliere Avanti.
2. Nell'elenco contrassegnare la riga selezionata.
    * Un'attività di prelievo predefinita viene creata per l'ubicazione di entrata della cella di lavoro selezionata.  
3. Scegliere Aggiungi.
    * È possibile creare attività di prelievo aggiuntive per prodotti specifici che non sono approntate nell'attività di entrata della cella di lavoro.  
4. Nell'elenco trovare e selezionare il record desiderato.
5. Nel campo Numero articolo, digitare un valore.
6. Nel campo Magazzino fare clic sul pulsante a discesa per aprire la ricerca.
    * Con questa definizione, tutti i materiali utilizzati nell'attività vengono prelevati dal magazzino e dall'ubicazione di entrata predefiniti ad eccezione dell'articolo definito nella seconda attività di prelievo. Questo articolo verrà prelevato da un magazzino e da un'ubicazione diversi.  
7. Nell'elenco trovare e selezionare il record desiderato.
8. Nell'elenco fare clic sul collegamento nella riga selezionata.
9. Selezionare o deselezionare la casella di controllo Registra scarti.
10. Scegliere Avanti.

## <a name="define-the-activity-times"></a>Definire gli orari per le attività
1. Nell'elenco trovare e selezionare il record desiderato.
    * La definizione di un runtime è richiesta. Il runtime viene utilizzato per calcolare i costi e i tempi di lavorazione dei processi kanban. I runtime non vengono utilizzati per calcolare il carico di capacità e il consumo, questo viene calcolato in base alla durata ciclo, derivata dall'attività della versione del flusso di produzione.  
2. Immettere un numero nel campo Tempo.
3. Digitare un valore nel campo Unità.
4. Selezionare l'unità di tempo.
5. Nel campo Per quantità immettere un numero.
6. Nell'elenco trovare e selezionare il record desiderato.
    * I tempi di attesa sono facoltativi.  
7. Immettere un numero nel campo Tempo.
8. Digitare un valore nel campo Unità.
9. Selezionare l'unità di tempo.
10. Nel campo Per quantità immettere un numero.
11. Scegliere Avanti.
12. Scegliere Fine.
13. Chiudere la pagina.


