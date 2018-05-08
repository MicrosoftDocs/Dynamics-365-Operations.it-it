---
title: Allocazione di dati di pianificazione del budget
description: Questo articolo descrive i vari metodi di allocazione disponibili in Microsoft Dynamics 365 for Finance and Operations e come possono essere utilizzati.
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BudgetPlanningConfiguration
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 15191
ms.assetid: 89a918e8-59a4-4711-a2e9-b41989ddd0f1
ms.search.region: Global
ms.author: sigitac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: b5f262318b4defb941f1216d0bfe06961f62bad4
ms.contentlocale: it-it
ms.lasthandoff: 03/26/2018

---

# <a name="budget-planning-data-allocation"></a>Allocazione dei dati della pianificazione del budget

[!include [banner](../includes/banner.md)]

Questo articolo descrive i vari metodi di allocazione disponibili in Microsoft Dynamics 365 for Finance and Operations e come possono essere utilizzati.  

È possibile distribuire i dati in un piano di budget in vari modi per illustrare in modo preciso gli importi previsti.

## <a name="allocation-methods"></a>Metodi di allocazione
Tre metodi di allocazione (Alloca nei periodi, Alloca a dimensioni e Utilizza regole di allocazione contabilità generale) possono creare le righe del piano di budget in base alle righe dello stesso piano di budget. Altri metodi tre (Aggrega, Distribuisci e Copia da piano di budget) possono creare le righe del piano di budget in altri piani di budget. Per tutti e sei i metodi di allocazione, specificare lo scenario di destinazione. Lo scenario di destinazione può essere uguale o diverso dallo scenario di origine. Inoltre, è possibile specificare se le nuove righe vengono aggiunte al piano di budget o sostituiscono le righe correnti del piano di budget.

[![AllocateAcrossPeriods](./media/allocateacrossperiods-300x259.png)](./media/allocateacrossperiods.png)
**Alloca nei periodi**: una categoria di allocazione per periodo viene utilizzata per allocare le righe del piano di budget dallo scenario del piano di budget di origine tra i periodi dello scenario di destinazione. L'importo di origine viene assegnato a più righe nello scenario di destinazione, in base alla percentuale e alla data definite nella categoria di allocazione per periodo.         

[![AllocateToDimensions](./media/allocatetodimensions.jpg)](./media/allocatetodimensions.jpg)
**Alloca a dimensioni**: le righe del piano di budget vengono allocate dallo scenario di origine di pianificazione del budget a una o più righe dello scenario descritto di destinazione, in base alle percentuali e alle dimensioni finanziarie definite in un termine di allocazione budget selezionato.           

![AggregateChart](./media/aggregatechart-300x230.png)
**Aggrega**: le righe del piano di budget sono aggregate dallo scenario del piano di budget di origine nei piani di budget associati (figlio) allo scenario di destinazione nel piano di budget padre. Questo metodo abilita il consolidamento degli importi di budget preparati a un livello più basso nell'organizzazione a un livello superiore.          

[![DistributeChart](./media/distributechart-300x230.png)](./media/distributechart.png)
**Distribuisci**: le righe del piano di budget vengono distribuite dallo scenario di origine di pianificazione del budget del piano di budget padre nello scenario di destinazione dei piani di budget associati (figlio), in base alle dimensioni finanziarie delle unità organizzative dei piani associati. Questo metodo abilita la ripartizione degli importi di budget preparati a un livello più alto nell'organizzazione per più revisioni localizzate.           

[![LedgerAllocationRules](./media/ledgerallocationrules-300x202.png)](./media/ledgerallocationrules.png)
**Utilizza regole di allocazione contabilità generale**: le righe del piano di budget sono distribuite dallo scenario di origine di pianificazione del budget nello scenario di destinazione, in base alla regola di allocazione di contabilità generale selezionata. 

[![CopyFromBudgetPlan](./media/copyfrombudgetplan-187x300.png)](./media/copyfrombudgetplan.png)
**Copia da piano di budget**: come nel metodo di allocazione distribuzione, le righe del piano di budget vengono create nella destinazione, in base alle righe di un piano di budget correlato. Tuttavia, per questo metodo, il piano di budget di origine non deve essere padre ma può essere a un livello superiore nella gerarchia del piano di budget. Questo metodo di allocazione è utile se gli importi consolidati sono originariamente inseriti nel budget a un livello molto superiore e devono essere trasferiti a un livello più basso dell'organizzazione per la revisione e la rettifica dettagliata prima di poter ricevere l'approvazione del livello superiore.          

## <a name="using-allocation-methods-in-a-budget-plan"></a>Utilizzo dei metodi di allocazione in un piano di budget
Per eseguire le allocazioni nella pagina del piano del budget, selezionare le righe da allocare quindi fare clic su **Alloca budget**.

[![AllocateBudgetButton](./media/allocatebudgetbutton-300x84.png)](./media/allocatebudgetbutton.png) 

A questo punto, selezionare un metodo di allocazione. I campi rimanenti vengono quindi impostati, in base al metodo selezionato. Questi campi includono l'origine e la destinazione dei dati del piano del budget e un'opzione che consente di moltiplicare l'origine per un fattore specificato quando gli importi di destinazione vengono creati, per semplificare la rettifica in blocco. È inoltre possibile impostare l'opzione **Aggiungi a piano**. Selezionare **No** per sostituire le righe esistenti del piano del budget o selezionare **Sì** per mantenere le righe esistenti del piano di budget e aggiungere nuove righe per gli importi allocati.

## <a name="automating-allocations-during-a-workflow"></a>Automatizzazione delle allocazioni durante un flusso di lavoro
Una funzionalità efficace abilita l'esecuzione automatica delle allocazioni come parte di un flusso di lavoro di pianificazione del budget. Quando un piano di budget si sposta nel flusso di lavoro, le attività automatizzate possono richiamare un'allocazione in una fase specifica della pianificazione del budget. 

Per impostare l'allocazione automatizzata, è necessario innanzitutto creare una programmazione di allocazione nella pagina **Configurazione di pianificazione del budget** allocazione nella pagina. La programmazione di allocazione determina il metodo di allocazione che verrà utilizzato quando viene eseguita l'allocazione automatizzata e i valori delle varie opzioni di allocazione (vedere la sezione precedente per le descrizioni). 

Quindi, creare un'allocazione della fase nella pagina **Configurazione di pianificazione del budget**. L'allocazione di fase assegna una programmazione dell'allocazione al flusso di lavoro e alla fase di pianificazione del budget. 

Infine, aggiungere un'attività automatizzata per l'allocazione della fase di pianificazione del budget nella fase desiderata del flusso di lavoro. Nel seguente esempio, due allocazioni di fase di pianificazione del budget (evidenziate in rosso) sono state inserite nel flusso di lavoro.

[![BudgetPlanningStageAllocations](./media/budgetplanningstageallocations-300x300.png)](./media/budgetplanningstageallocations.png)




