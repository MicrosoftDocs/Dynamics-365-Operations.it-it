---
title: Creare una regola kanban di prelievo
description: Questa procedura illustra l'impostazione necessaria per creare una regola kanban di prelievo per il trasferimento di materiale in un ambiente lean manufacturing.
author: ChristianRytt
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanRules, LeanProductionFlowActivityLookup, InventItemIdLookupSimple, UnitOfMeasureLookup, KanbanCreate
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 963a6dce8affc23f001dcb04219821ceff3a2d92
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2020
ms.locfileid: "3210734"
---
# <a name="create-a-withdrawal-kanban-rule"></a>Creare una regola kanban di prelievo

[!include [banner](../../includes/banner.md)]

Questa procedura illustra l'impostazione necessaria per creare una regola kanban di prelievo per il trasferimento di materiale in un ambiente lean manufacturing. La società di dati dimostrativi utilizzata per creare questa procedura è USMF. Questa procedura è destinata all'addetto procedure tecniche o al responsabile flusso del valore che prepara il rifornimento di un materiale nuovo o modificato.


## <a name="create-new-kanban-rule"></a>Creare una nuova regola kanban
1. Passare a Regole kanban.
2. Fare clic su Nuovo.
3. Selezionare "Prelievo" nel campo Tipo.
    * Il tipo Prelievo viene utilizzato per le regole kanban per trasferire materiale o merci.  
4. Nel campo Prima attività piano immettere o selezionare un valore.
    * Selezionare ReplenishSpeakerComponents.   Questa attività viene impostata per spostare i componenti dal magazzino 11, ubicazione 11 al magazzino 12 e ubicazione 12.  
5. Nel campo Prodotto immettere o selezionare un valore.
    * Selezionare M0007.  
6. Nel campo Lead time immettere un numero.
    * Ad esempio, 60.  
7. Nel campo Unità di misura immettere o selezionare un valore.
    * Ad esempio, Minuti.  

## <a name="set-quantities-for-kanban"></a>Impostare le quantità per il kanban
1. Impostare Quantità predefinita su '5'.
    * Si tratta della quantità che verrà trasferita per ogni kanban.  
2. Nel campo Kanban a quantità fissa immettere "2".
    * Si tratta della quantità di kanban che devono essere attivi. In questo caso, 2 kanban che ne trasferiscono 5 ognuno.  
3. Nel campo Avviso per limite minimo immettere '1'.
    * Utilizzato per tenere traccia dell'importo minimo di kanban completi che devono essere nella destinazione. Ad esempio, questo viene utilizzato nella panoramica della quantità kanban.  
4. Nel campo Avviso per limite massimo immettere '2'.
    * Utilizzato per tenere traccia dell'importo massimo di kanban completi che devono essere nella destinazione. Ad esempio, questo viene utilizzato nella panoramica della quantità kanban.  

## <a name="create-kanbans"></a>Crea kanban
1. Fare clic su Salva.
    * La regola kanban deve essere salvata prima di poter creare i kanban.  
2. Scegliere Aggiungi.
    * Non sono presenti kanban attivi, in quanto il "Numero di nuovi kanban" suggerito è 2, che corrisponde a "Kanban a quantità fissa".  
3. Fare clic su Crea.
    * Ciò creerà due kanban.  
    * 2 kanban, ciascuno per 5, sono stati creati per questa regola kanban di prelievo.  Si tratta dell'ultimo passaggio di questa procedura.  

