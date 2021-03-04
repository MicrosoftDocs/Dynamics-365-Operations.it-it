---
title: Creare una regola kanban a quantità fissa per la produzione
description: Questa procedura è incentrata sull'impostazione necessaria per creare una regola kanban di produzione fissa per attivare le attività di trasformazione, in una cella di lavoro, in un ambiente lean manufacturing.
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
ms.openlocfilehash: 24eb705bf2de0d175a8a03a4e89ad11c51f15d15
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4430871"
---
# <a name="create-a-fixed-quantity-kanban-rule-for-manufacturing"></a>Creare una regola kanban a quantità fissa per la produzione

[!include [banner](../../includes/banner.md)]

Questa procedura è incentrata sull'impostazione necessaria per creare una regola kanban di produzione fissa per attivare le attività di trasformazione, in una cella di lavoro, in un ambiente lean manufacturing. La società di dati dimostrativi utilizzata per creare questa procedura è USMF. Questa procedura è destinata all'addetto procedure tecniche o al responsabile flusso del valore che prepara la produzione di un prodotto nuovo o modificato.


## <a name="create-new-kanban-rule"></a>Creare una nuova regola kanban
1. Passare a Regole kanban.
2. Fare clic su Nuovo.
    * Si noti che il tipo predefinito è Produzione e la Strategia di rifornimento è Fisso. Non è necessario modificare questi parametri.  
3. Nel campo Prima attività piano immettere o selezionare un valore.
    * Si tratta dell'attività che verrà eseguita per i kanban creati in base alla regola kanban.  Selezionare 'SpeakerTestAndPackaging'.  
4. Espandere la sezione Dettagli.
5. Nel campo Prodotto immettere o selezionare un valore.
    * Selezionare L0050.  
6. Nel campo Unità di misura immettere o selezionare un valore.
    * Selezionare i minuti.  
7. Nel campo Lead time immettere un numero.
    * Immettere 5.  

## <a name="set-quantities"></a>Impostare le quantità
1. Espandere la sezione Quantità.
2. Impostare Quantità predefinita su '10'.
    * Si tratta della quantità che verrà trasferita per ogni kanban.  
3. Selezionare la casella di controllo Scostamento quantità prodotto.
    * Con questo, i kanban selezionati possono essere completati con uno scostamento dalla quantità predefinita.  Per consentire il completamento dei kanban con una quantità da 8 a 12, impostare entrambi gli scostamenti su 2.  
4. Impostare Scostamento al di sotto su '2'.
    * Questo permetterà il completamento sul valore inferiore 10 - 2 = 8  
5. Impostare Scostamento al di sopra su '2'.
    * Questo permetterà il completamento sul valore superiore 10 + 2 = 12  
6. Nel campo Kanban a quantità fissa immettere un numero.
    * Si tratta della quantità di kanban che devono essere attivi. In questo caso, 5 kanban che elaborano 10 ognuno.  
7. Nel campo Avviso per limite minimo immettere '2'.
    * Utilizzato per tenere traccia dell'importo minimo di kanban completi che devono essere nella destinazione. Ad esempio, questo viene utilizzato nella panoramica della quantità kanban.  
8. Nel campo Avviso per limite massimo immettere '4'.
    * Utilizzato per tenere traccia dell'importo massimo di kanban completi che devono essere nella destinazione. Ad esempio, questo viene utilizzato nella panoramica della quantità kanban.  
9. Nel campo Quantità di pianificazione automatica immettere '1'.
    * Impostare questo su 1 indica che ogni kanban verrà automaticamente pianificato.   Se fosse specificato 3, i kanban non verrebbero pianificati fino a che 3 kanban vuoti sono pronti per la pianificazione. Questa opzione è utile per raggruppare il lavoro ed evitare troppe impostazioni.  

## <a name="create-kanbans"></a>Creare kanban
1. Espandere la sezione Kanban.
2. Fare clic su Salva.
    * La regola kanban deve essere salvata prima di poter creare i kanban.  
3. Scegliere Aggiungi.
    * Si noti che non sono presenti kanban attivi, in quanto il 'Numero di nuovi kanban' suggerito è 5. Questo corrisponde a 'Kanban a quantità fissa'.  
4. Fare clic su Crea.
    * Ciò creerà 5 kanban.  
    * Si noti che 5 kanban, ciascuno per 10, sono stati creati per questa regola kanban di produzione. Si tratta dell'ultimo passaggio di questa procedura.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]