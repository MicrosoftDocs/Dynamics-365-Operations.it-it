---
title: Creare le attività di trasferimento per la lean manufacturing
description: Creare un'attività di trasferimento per lean manufacturing
author: johanhoffmann
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LeanProductionFlow, PlanActivity, PlanActivityWizard, LeanWorkCellLookup, InventLocationIdLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3eee0fd510639f2dad78fecb6395c0e31154db6b
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/29/2021
ms.locfileid: "7568041"
---
# <a name="create-transfer-activities-for-lean-manufacturing"></a>Creare le attività di trasferimento per la lean manufacturing

[!include [banner](../../includes/banner.md)]

Creare un'attività di trasferimento per lean manufacturing 

Prerequisiti: 

1. Un flusso di produzione e una versione non attiva devono essere creati.

2. Il magazzino e le ubicazioni di origine e di destinazione devono essere creati. Facoltativamente, la cella di lavoro di rifornimento o rifornita deve essere creata.


## <a name="find-the-production-flow-version"></a>Trovare la versione del flusso di produzione
1. Andare a Controllo produzione > Impostazioni > Flusso di produzione snella > Flussi di produzione.
2. Nell'elenco trovare e selezionare il record desiderato.
    * Si noti che il flusso di produzione deve avere una versione in stato bozza.  
3. Nell'elenco fare clic sul collegamento nella riga selezionata.

## <a name="create-a-new-activity"></a>Creare una nuova attività
1. Fare clic su Attività.
    * Verificare che il flusso di produzione selezionato abbia una versione in bozza e selezionare tale versione.  
2. Fare clic su Crea nuova attività piano.
3. Scegliere Avanti.
4. Digitare un valore nel campo Nome.
5. Selezionare 'Trasferimento' nel campo Tipo di attività.
6. Nel campo Quantità di lavorazione immettere un numero.
7. Scegliere Avanti.

## <a name="select-the-work-cells"></a>Selezionare le celle di lavoro
1. Nel campo Rifornimento fare clic sul pulsante a discesa per aprire la ricerca.
    * Per utilizzare l'ubicazione di uscita della cella di lavoro come ubicazione di origine nell'attività di trasferimento, selezionare una cella di lavoro. Lo stesso può essere effettuato con la cella di lavoro rifornita, che imposta l'ubicazione di destinazione dell'attività di trasferimento.  
2. Nell'elenco fare clic sul collegamento nella riga selezionata.

## <a name="define-the-inventory-updates"></a>Definire gli aggiornamenti di inventario
1. Nel campo Tipo di prodotto selezionare un'opzione.
    * Si noti che un trasferimento non modifica il tipo di prodotto. È possibile trasferire i prodotti finiti o i prodotti semilavorati (trasferimento tra due attività del flusso di produzione ed eventualemnte un flusso kanban).     Nel trasferimento dei prodotti finiti, è possibile scegliere se prelevare o ricevere i risultati in una transazione di magazzino.  

## <a name="define-the-transfer-locations"></a>Definire le ubicazioni di trasferimento
1. Scegliere Avanti.
2. Nel campo Magazzino fare clic sul pulsante a discesa per aprire la ricerca.
3. Trovare e selezionare il record desiderato nell'elenco.
4. Nell'elenco fare clic sul collegamento nella riga selezionata.
5. Nel campo Ubicazione fare clic sul pulsante a discesa per aprire la ricerca.
6. Nell'elenco fare clic sul collegamento nella riga selezionata.
7. Nel campo Noleggiato da, selezionare 'Spedizioniere'.
    * Le opzioni includono: Spedizioniere: l'organizzazione che gestisce il magazzino di spedizione, Destinatario: l'organizzazione che gestisce il magazzino ricevente, Vettore: un fornitore di terze parti. Se l'organizzazione è un fornitore, l'attività di trasferimento richiede un contratto di conto lavoro.  
8. Scegliere Avanti.

## <a name="define-the-activity-times"></a>Definire gli orari per le attività
1. Nell'elenco trovare e selezionare il record desiderato.
    * La definizione di un runtime è richiesta. Il runtime viene utilizzato per calcolare i costi e i tempi di lavorazione dei processi kanban. I runtime non vengono utilizzati per calcolare il carico di capacità e il consumo, che viene calcolato in base alla durata ciclo, derivata dall'attività della versione del flusso di produzione.  
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



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]