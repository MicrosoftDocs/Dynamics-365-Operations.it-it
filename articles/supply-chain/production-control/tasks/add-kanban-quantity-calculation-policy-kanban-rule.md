--- 
title: "Aggiungere criteri di calcolo di quantità kanban a una regola kanban"
description: "Questa procedura riguarda la creazione dei criteri di calcolo della quantità kanban e la relativa aggiunta a una regola kanban per ottimizzare la dimensione e le quantità kanban."
author: ChristianRytt
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 6a947d4a5302c6ed1848396d50cfbfcb78aabf97
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---
# <a name="add-a-kanban-quantity-calculation-policy-to-a-kanban-rule"></a>Aggiungere criteri di calcolo di quantità kanban a una regola kanban

[!include [task guide banner](../../includes/task-guide-banner.md)]

Questa procedura riguarda la creazione dei criteri di calcolo della quantità kanban e la relativa aggiunta a una regola kanban per ottimizzare la dimensione e le quantità kanban. La società di dati dimostrativi utilizzata per creare questa procedura è USMF. Questa procedura è destinata al responsabile del flusso del valore. Questa procedura è un prerequisito per creare la procedura Calcolare suggerimenti su quantità kanban. 


## <a name="create-a-kanban-quantity-calculation-policy"></a>Creare criteri di calcolo delle quantità kanban
1. Andare a Controllo produzione > Attività periodiche > Calcolo quantità kanban > Criteri di calcolo quantità kanban.
2. Fare clic su Nuovo.
3. Digitare un valore nel campo Nome.
    * Ad esempio, digitare Speaker2016.  
4. Nel campo Piano generale fare clic sul pulsante a discesa per aprire la ricerca.
5. Nell'elenco trovare e selezionare il record desiderato.
    * Selezionare StaticPlan per calcolare la domanda.  
6. Nell'elenco fare clic sul collegamento nella riga selezionata.
7. Fare clic su Salva.
8. Nel campo Quantità kanban minima immettere "1".
    * Numero aggiuntivo di kanban incluso nel calcolo della quantità kanban.  
9. Impostare il fattore di sicurezza su "1".
    * Fattore utilizzato per calcolare la quantità aggiuntiva di scorte di sicurezza.  
10. Nel campo Giorni di anticipo immettere "30".
    * Numero di giorni precedenti alla data di calcolo della quantità kanban inclusa nel calcolo della domanda.  
11. Nel campo Giorni di ritardo immettere "30".
    * Numero di giorni successivi alla data di calcolo della quantità kanban inclusa nel calcolo della domanda.  La formula utilizzata per il calcolo viene visualizzata con i valori effettivi. Ad esempio, quantità kanban = ((Domanda giornaliera media x lead time x 2)/Quantità prodotto per unità movimentazione) + 1  
12. Chiudere la pagina.

## <a name="add-the-kanban-quantity-calculation-policy-to-a-kanban-rule"></a>Aggiungere i criteri di calcolo della quantità kanban a una regola kanban
1. Andare a Gestione informazioni sul prodotto > Lean manufacturing > Regole kanban.
2. Nell'elenco trovare e selezionare il record desiderato.
    * Selezionare la regola kanban 000020 per questa procedura.  
3. Nell'elenco fare clic sul collegamento nella riga selezionata.
4. Attivare/disattivare l'espansione della sezione Criteri di calcolo quantità kanban.
5. Scegliere Aggiungi.
    * Aggiungere i criteri di calcolo della quantità kanban creati nella sottoattività precedente.  
6. Nell'elenco contrassegnare la riga selezionata.
7. Nel campo Nome fare clic sul pulsante a discesa per aprire la ricerca.
8. Nell'elenco fare clic sul collegamento nella riga selezionata.
    * Selezionare il criterio Speaker2016 creato nella sottoattività precedente.  


