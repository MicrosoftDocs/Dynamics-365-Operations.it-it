---
title: Creare una regola kanban per più attività
description: Questa procedura mostra come creare una regola kanban che comprende più attività da un flusso di produzione.
author: ChristianRytt
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanRules, LeanProductionFlowActivityLookup, KanbanFlowSelection, InventItemIdLookupSimple, KanbanCreateScheduled, Kanban
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 68cac0f581e786cdb3801e03fb60db7bc05ffb2f
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4430867"
---
# <a name="create-a-kanban-rule-for-multiple-activities"></a>Creare una regola kanban per più attività

[!include [banner](../../includes/banner.md)]

Questa procedura mostra come creare una regola kanban che comprende più attività da un flusso di produzione. La società di dati dimostrativi utilizzata per creare questa attività è USMF. Questa attività è destinata all'addetto procedure tecniche o al responsabile flusso del valore che prepara la produzione di un prodotto nuovo o modificato in un ambiente lean manufacturing.


## <a name="create-a-new-kanban-rule"></a>Crea una nuova regola kanban
1. Andare a Gestione informazioni sul prodotto > Lean manufacturing > Regole kanban.
2. Fare clic su Nuovo.
3. Nel campo Strategia di rifornimento, selezionare 'Programmato'.
4. Nel campo Prima attività piano immettere o selezionare un valore.
    * Selezionare SpeakerAssemblyAndPolish.  
5. Selezioni la casella di controllo Attività multiple.
    * Lo scopo è includere più di una attività nella regola kanban. Scegliete un percorso nel flusso di produzione quando selezionate l'ultima attività di piano.  
6. Nel campo Ultima attività piano immettere o selezionare un valore.
    * Selezionare SpeakerTestAndPackaging. Dopo che selezionate il valore, una pagina si apre automaticamente. Selezionare il flusso kanban SpeakerAssemblyAndPolish > SpeakerTestAndPackaging. Fare clic su OK.  
7. Espandere la sezione Dettagli.
8. Nel campo Prodotto immettere o selezionare un valore.
    * Selezionare l'articolo L0006.  

## <a name="create-kanban-and-view-jobs"></a>Creare e visualizzare processi kanban
1. Espandere la sezione Kanban.
2. Scegliere Aggiungi.
3. Immettere '1' nel campo Numero di nuovi kanban.
    * Ciò creerà un kanban.  
4. Impostare la quantità prodotto su "3".
    * Kanban elaborerà 3 prodotti.  
5. Nel campo Data/ora scadenza immettere una data e un'ora.
    * È possibile immettere Oggi.  
6. Fare clic su Crea.
7. Fare clic su Dettagli.
    * Notare che il kanban ha due processi dal flusso di produzione. Il primo è SpeakerAssemblyAndPolish e il secondo è SpeakerTestAndPackaging.  
    * Questo è l'ultimo passaggio.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]