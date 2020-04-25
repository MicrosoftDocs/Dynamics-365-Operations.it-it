---
title: Processi di produzione in sequenza per la produzione di processo
description: Questa procedura utilizza i prodotti di vernice come esempio per mostrare come ordinare gli ordini pianificati in sequenza in base alla priorità di colore e dimensione del collo.
author: ChristianRytt
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqTransPo, PMFSeqReqRouteChangesListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 422f05c6edcc8856192ba944c97c551eaba8a7c3
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2020
ms.locfileid: "3210412"
---
# <a name="sequence-production-jobs-for-process-manufacturing"></a>Processi di produzione in sequenza per la produzione di processo

[!include [banner](../../includes/banner.md)]

Questa procedura utilizza i prodotti di vernice come esempio per mostrare come ordinare gli ordini pianificati in sequenza in base alla priorità di colore e dimensione del collo. La società di dati dimostrativi utilizzata per creare questa procedura è USPI. Questa procedura è destinata al responsabile pianificazione produzione.


## <a name="run-master-planning-for-uspi"></a>Eseguire la pianificazione generale per USPI
1. Andare a Pianificazione generale > Pianificazione generale > Esegui > Pianificazione generale.
2. Nel campo Piano generale fare clic sul pulsante a discesa per aprire la ricerca.
3. Nell'elenco fare clic sul collegamento nella riga selezionata.
    * Selezionare Piano generale.  
4. Fare clic su OK.
    * Si avvia la pianificazione generale, incluso il processo di sequenza. Il processo può richiedere alcuni minuti.  

## <a name="view-planned-orders-for-the-paint-products"></a>Visualizzare gli ordini pianificati per i prodotti di vernice
1. Andare a Pianificazione generale > Pianificazione generale > Ordini pianificati.
2. Espandere il riquadro Dettaglio informazioni dei dettagli articolo.
3. Espandere il riquadro Dettaglio informazioni della programmazione.
4. Nel campo Piano fare clic sul pulsante a discesa per aprire la ricerca.
5. Nell'elenco trovare e selezionare il record desiderato.
    * Selezionare Piano generale.  
6. Nell'elenco fare clic sul collegamento nella riga selezionata.
7. Utilizzare il filtro rapido per filtrare il campo Numero articolo in base al valore "P300".
    * Sbloccare per scorrere a destra e visualizzare la data dell'ordine e la data di consegna. Questi articoli con data dell'ordine odierna e le date di consegna degli ordini pianificati non vengono ordinati in sequenza dopo la priorità di colore e di dimensione del collo, come illustrato nel nome del prodotto. È possibile passare il mouse su un numero di articolo per visualizzare il nome del prodotto e la priorità.  

## <a name="sequence-planned-orders-for-paint"></a>Mettere in sequenza gli ordini pianificati di vernice
1. Chiudere la pagina.
2. Andare a Pianificazione generale > Pianificazione generale > Ordini pianificati in sequenza.
3. Espandere il riquadro Dettaglio informazioni dei dettagli articolo.
4. Espandere il riquadro Dettaglio informazioni della programmazione.
    * Nota: in questo campo la data e l'ora di inizio degli ordini pianificati sono ordinate in sequenza in base al colore e alla dimensione del collo in un periodo dell'intervallo di tempo di 28 giorni. Questi periodi sono definiti da un numero nel campo Campagna. Il modulo dell'ordine pianificato in sequenza agisce come il normale modulo ordine pianificato e il pianificatore di produzione può stabilizzare gli ordini pianificati in questo campo.  
5. Contrassegnare tutte le righe.
6. Fare clic su Accetta.
    * Questa operazione aggiornerà gli ordini pianificati con l'azione di sequenza selezionata Posticipa o Anticipa.  

## <a name="verify-the-sequence-of-the-planned-orders"></a>Verificare la sequenza degli ordini pianificati
1. Chiudere la pagina.
2. Andare a Pianificazione generale > Pianificazione generale > Ordini pianificati.
3. Espandere il riquadro Dettaglio informazioni dei dettagli articolo.
4. Espandere il riquadro Dettaglio informazioni della programmazione.
5. Nel campo Piano fare clic sul pulsante a discesa per aprire la ricerca.
6. Nell'elenco trovare e selezionare il record desiderato.
    * Selezionare Piano generale.  
7. Nell'elenco fare clic sul collegamento nella riga selezionata.
8. Utilizzare il filtro rapido per filtrare il campo Numero articolo in base al valore "P300".
    * Gli ordini vengono ora ordinati in sequenza in base alla priorità di colore e dimensioni e gli ordini pianificati cominciano alla prima data dell'ordine e alla prima data di consegna. Convalidare la colonna relativa alla data dell'ordine o alla data di inizio in Dettagli programmazione nel riquadro Dettaglio informazioni.  

