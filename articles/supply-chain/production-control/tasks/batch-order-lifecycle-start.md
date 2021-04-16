---
title: Ciclo di vita di ordini batch dalla creazione all'avvio
description: In questa procedura vengono descritti i passaggi della prima parte del ciclo di vita di un ordine batch.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ProdTableListPage, ProdTableCreate, ProdBOM, PmfProdCoBy, ProdParmCostEstimation, ProdCalcTrans, ProdParmRelease, ProdSchedule, ProdRouteJob, ProdParmStartUp, ProdJournalTransBOM, ProdJournalTransRoute
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8d9ed44c9e05ea815e78ae041234ad61f76d89d8
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5825040"
---
# <a name="batch-order-lifecycle-from-create-to-start"></a>Ciclo di vita di ordini batch dalla creazione all'avvio

[!include [banner](../../includes/banner.md)]

In questa procedura vengono descritti i passaggi della prima parte del ciclo di vita di un ordine batch.

Dalla creazione, stima dei costi e programmazione de processo di produzione all'inizio effettivo di un ordine batch.



La società di dati dimostrativi utilizzata per creare questa procedura è USMF. 



I prerequisiti per eseguire la procedura con un altro set di dati sono un prodotto rilasciato con una versione attiva del ciclo di lavorazione e della formula.


## <a name="create-a-batch-order"></a>Creazione di un ordine lotto
1. Passare a Tutti gli ordini di produzione.
2. Fare clic su Nuovo ordine batch.
3. Nel campo Numero di articoli immettere o selezionare un valore.
4. Fare clic su Crea.
5. Utilizzare il filtro rapido per filtrare il campo Produzione in base a un valore di 'b'.

## <a name="view-production-formula-and-expected-co-products"></a>Visualizzare la formula di produzione e i co-prodotti previsti
1. Nel riquadro azioni fare clic su Ordine di produzione.
2. Fare clic su Formula.
3. Chiudere la pagina.
4. Fare clic su Co-prodotti.
5. Chiudere la pagina.

## <a name="estimate-the-batch-order"></a>Stimare l'ordine batch
1. Fare clic su Stima.
2. Fare clic su OK.
3. Nel riquadro azioni, fare clic su Gestisci costi.
4. Fare clic su Visualizza dettagli calcolo.
5. Chiudere la pagina.

## <a name="release-the-batch-order"></a>Rilasciare l'ordine batch
1. Nel riquadro azioni fare clic su Ordine di produzione.
2. Fare clic su Rilascia.
3. Fare clic su OK.

## <a name="schedule-production-jobs"></a>Programmare i processi di produzione
1. Nel riquadro azioni fare clic su Programmazione.
2. Fare clic su Programma processi.
3. Selezionare No nel campo Capacità limitata.
4. Selezionare No nel campo Materiale limitato.
5. Fare clic su OK.
6. Nel riquadro azioni fare clic su Ordine di produzione.
7. Fare clic su Tutti i processi.
8. Chiudere la pagina.

## <a name="start-the-batch-order"></a>Iniziare l'ordine batch
1. Fare clic su Inizia.
2. Fare clic sulla scheda Generale.
3. Selezionare No nel campo Registra distinta di prelievo ora.
4. Fare clic su OK.
5. Nel riquadro azioni fare clic su Visualizza.
6. Fare clic su Distinta di prelievo.
7. Nell'elenco fare clic sul collegamento nella riga selezionata.
8. Chiudere la pagina.
9. Chiudere la pagina.
10. Fare clic su Scheda ciclo di lavorazione.
11. Nell'elenco fare clic sul collegamento nella riga selezionata.
12. Chiudere la pagina.
13. Chiudere la pagina.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]