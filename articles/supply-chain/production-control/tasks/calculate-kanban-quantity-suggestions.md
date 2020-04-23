---
title: Calcolare suggerimenti su quantità kanban
description: Questa procedura riguarda l'ottimizzazione della dimensione e delle quantità kanban per una regola kanban specifica tramite il calcolo della quantità kanban.
author: ChristianRytt
manager: tfehr
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: aa6a01d8f918c45aaa454e5234f80c312d7a5061
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2020
ms.locfileid: "3212390"
---
# <a name="calculate-kanban-quantity-suggestions"></a>Calcolare suggerimenti su quantità kanban

[!include [banner](../../includes/banner.md)]

Questa procedura riguarda l'ottimizzazione della dimensione e delle quantità kanban per una regola kanban specifica tramite il calcolo della quantità kanban. La società di dati dimostrativi utilizzata per creare questa procedura è USMF. Questa procedura è destinata al responsabile del flusso del valore. Per seguire questa procedura, è necessario aver completato la procedura Aggiungere criteri di calcolo quantità kanban a una regola kanban.


## <a name="create-a-kanban-quantity-calculation"></a>Creare un calcolo di quantità kanban
1. Andare a Controllo produzione > Attività periodiche > Calcolo quantità kanban > Calcola quantità kanban.
2. Fare clic su Nuovo.
3. Nel campo Nome digitare "Speaker2016".
4. Nel campo Nome fare clic sul pulsante a discesa per aprire la ricerca.
    * Selezionare i criteri creati nella procedura Aggiungere criteri di calcolo quantità kanban a una regola kanban. Ad esempio, Speaker2016.  
5. Nell'elenco fare clic sul collegamento nella riga selezionata.
6. Nel campo Regola attiva dalla data impostare la data e l'ora su "17-12-2012T08.00.00".
    * Questa data viene utilizzata come base per determinare quali regole kanban fisse vengono incluse nel calcolo della quantità kanban.  
7. Nel campo Data di inizio periodo evasione domanda impostare la data e l'ora su "17-11-2012T09.00.00".
    * Data dalla quale vengono incluse le transazioni della domanda passata per calcolare la quantità kanban.  
8. Nel campo Data di fine periodo evasione domanda impostare la data e l'ora su "17-12-2012T07.59.59".
    * Data fino alla quale vengono incluse le transazioni della domanda passata per calcolare la quantità kanban.  
9. Nel campo Data di inizio periodo domanda impostare la data e l'ora su "17-12-2012T08.00.00".
    * Data dalla quale vengono incluse le transazioni della domanda corrente per calcolare la quantità kanban.  
10. Nel campo Data di fine periodo domanda impostare la data e l'ora su "16-01-2013T07.59.59".
    * Data fino alla quale vengono incluse le transazioni della domanda corrente per calcolare la quantità kanban.  

## <a name="generate-kanban-quantity-proposal"></a>Generare una proposta di quantità kanban
1. Fare clic su Salva.
2. Fare clic su Genera.
    * Viene generata una riga di proposta di quantità kanban per la regola kanban 000020.  

## <a name="run-kanban-quantity-calculation"></a>Eseguire il calcolo della quantità kanban
1. Fare clic su Calcola.
    * Viene calcolata la proposta di quantità kanban.  
2. Fare clic su OK.
3. Nell'elenco contrassegnare la riga selezionata.
    * Si noti che la quantità kanban consentita è 2.  

## <a name="change-product-quantity-and-calculate-again"></a>Modificare la quantità di prodotto e calcolarla nuovamente
1. Impostare la quantità prodotto su "5".
2. Fare clic su Calcola.
3. Fare clic su OK.
    * Si noti che con una quantità kanban pari a 5, il suggerimento viene modificato in una quantità kanban pari a 4.  
    * Questa situazione è causata dal fatto che con una quantità di prodotto inferiore sono necessarie quantità kanban maggiori per soddisfare la richiesta.  

## <a name="update-kanban-rule"></a>Aggiornare la quantità kanban
1. Nel campo Data di validità regola immettere una data e un'ora.
    * Impostare "Regola attiva dalla data" su una data successiva a quella corrente. Ad esempio, oggi + un anno.  
2. Fare clic su Aggiorna.
3. Fare clic su OK.
4. Chiudere la pagina.

## <a name="validate-change-on-kanban-rule"></a>Convalidare la modifica della regola kanban
1. Andare a Gestione informazioni sul prodotto > Lean manufacturing > Regole kanban.
2. Nell'elenco fare clic sul collegamento nella riga selezionata.
    * Selezionare la regola kanban creata nella sottoattività precedente. Questa deve essere la prima regola kanban nell'elenco ordinato per numero.  
3. Attivare/disattivare l'espansione della sezione Dettagli.
    * Si noti la data di validità, che indica che questa regola non è attivata fino a tale data.  
4. Attivare/disattivare l'espansione della sezione Quantità.
    * Si noti che si tratta della quantità predefinita immessa nel calcolo della quantità kanban.  
    * Si noti che si tratta della quantità kanban fissa pari a 4 derivata dal calcolo della quantità kanban.  
5. Fare clic sulla scheda ListPanel.

