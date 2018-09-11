--- 
title: Creare una regola kanban tramite un evento riga kanban
description: "Questa procedura crea una regola kanban usando l'impostazione di evento riga kanban che attiva il pull da un'attività di processo."
author: ChristianRytt
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: KanbanRules, LeanProductionFlowActivityLookup, SalesTableListPage, SalesCreateOrder, SalesTable
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 9ef7b8e920d22cbc4f96676e68a263f2da7f232c
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---
# <a name="create-a-kanban-rule-using-a-kanban-line-event"></a>Creare una regola kanban tramite un evento riga kanban

[!include [task guide banner](../../includes/task-guide-banner.md)]

Questa procedura crea una regola kanban usando l'impostazione di evento riga kanban che attiva il pull da un'attività di processo. La regola kanban è attivata da un'attività di processo kanban, con una quantità uguale o maggiore di 25 ciascuna. La società di dati dimostrativi utilizzata per creare questa attività è USMF. Questa attività è destinata all'addetto procedure tecniche o al responsabile flusso del valore che prepara la produzione di un prodotto nuovo o modificato in un ambiente lean manufacturing.


## <a name="create-a-kanban-rule"></a>Creare una regola kanban
1. Andare a Gestione informazioni sul prodotto > Lean manufacturing > Regole kanban.
2. Fare clic su Nuovo.
3. Nel campo Strategia di rifornimento, selezionare 'Evento'.
    * Con questa azione i kanban vengono generati direttamente a partire dalla domanda. Viene utilizzata per impostare le regole che definiscono uno scenario di produzione su ordine.  
4. Nel campo Prima attività piano immettere o selezionare un valore.
    * Immettere o selezionare SpeakerAssemblyAndPolish. La prima attività di una regola kanban di produzione è essere un'attività di processo nel flusso di produzione. Quando si seleziona l'attività, le date di validità di quest'ultima vengono copiate nelle date di validità della regola kanban.  
5. Espandere la sezione Dettagli.
6. Nel campo Prodotto digitare 'L0001'.
7. Espandere la sezione Eventi.
8. Nel campo Evento riga Kanban selezionare 'Automatico'.
    * Ciò genera i kanban di evento su richiesta.  Il campo viene usato per configurare le regole kanban per il rifornimento di materiale richiesto per un'attività di processo downstream. Quando si seleziona Automatico, i kanban di evento vengono creati con la domanda. Questa impostazione è consigliata se si prevede di eseguire la produzione lo stesso giorno.  
9. Impostare Quantità minima evento su '25'.
    * Vengono generati kanban evento quando la quantità di domanda è uguale o superiore al valore di questo campo. Ciò è utile se volete produrre una quantità di ordine minore di questo campo su una macchina e maggiore di questo campo su un'altra macchina.  
10. Fare clic su Salva.

## <a name="create-sales-order-and-trigger-kanban-chain"></a>Creare l'ordine cliente e attivare la catena kanban
1. Passare a Vendite e marketing > Ordini cliente > Tutti gli ordini cliente.
2. Fare clic su Nuovo.
3. Nel campo Conto cliente, immettere o selezionare un valore.
    * Selezionare il conto cliente US-003, Forest Wholesales.  
4. Fare clic su OK.
5. Nel campo Numero articolo digitare "L0001".
    * L0001 è l'articolo per cui viene creata la regola kanban.  
6. Impostare la quantità su "27".
    * Poiché 27 è maggiore della quantità minima di 25 nella regola kanban, ciò attiverà kanban evento.  
7. Nel campo Sito digitare '1'.
8. Nel campo Magazzino immettere o selezionare un valore.
    * Selezionare magazzino 13.  
9. Fare clic su Salva.

## <a name="view-the-kanban-generated-by-the-kanban-rule"></a>Visualizzare il kanban generato dalla regola kanban
1. Andare a Gestione informazioni sul prodotto > Lean manufacturing > Regole kanban.
2. Nell'elenco trovare e selezionare il record desiderato.
3. Espandere la sezione Kanban.
    * Notare che un kanban per 27 è stato creato per elaborare l'attività basata sulla regola kanban creata.  
    * Questo è l'ultimo passaggio.  


