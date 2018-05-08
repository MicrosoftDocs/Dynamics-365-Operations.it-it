--- 
title: Definire gruppi di produzione snella
description: I gruppi di programmazione snella sono definiti per raggruppare e distinguere i prodotti nella programmazione kanban.
author: cvocph
manager: AnnBe
ms.date: 11/03/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 3e07fa270b47be3527c572dc53ca30a7bcde5ba6
ms.contentlocale: it-it
ms.lasthandoff: 11/03/2017

---
# <a name="define-lean-schedule-groups"></a>Definire gruppi di produzione snella

[!include [task guide banner](../../includes/task-guide-banner.md)]

I gruppi di programmazione snella sono definiti per raggruppare e distinguere i prodotti nella programmazione kanban. Il raggruppamento può essere eseguito come associazione generica per società o specifica per cella di lavoro. A ciascun gruppo è associato un codice colore per l'indicazione visiva nella pagina elenco di programmazione kanban. La società di dati dimostrativi utilizzata per creare questa procedura è USMF.


## <a name="define-lean-scheduling-group"></a>Definire un gruppo di produzione snella
1. Passare a Gestione informazioni sul prodotto > Produzione snella > Gruppi di programmazione snella.
2. Fare clic su Nuovo.
3. Digitare un valore nel campo Gruppo di programmazione.
    * Un gruppo di programmazione può essere definito come gruppo globale o specifico di una cella di lavoro. In questo esempio semplice, si definisce un gruppo globale e la cella di lavoro viene mantenuta vuota. Le impostazioni del gruppo si applicano a tutte le celle di lavoro che non dispongono di gruppi di programmazione specifici.  
4. Selezionare un colore dalla selezione colori.
    * I colori utilizzati per evidenziare i processi nella pagina elenco di programmazione kanban o nella scheda del processo kanban.  
5. Nell'elenco contrassegnare la riga selezionata.
6. Nell'elenco fare clic sul collegamento nella riga selezionata.

## <a name="associate-product"></a>Associare un prodotto
1. Associare un prodotto specifico
    * Sono disponibili due metodi per associare i prodotti ai gruppi di programmazione snella, come prodotto specifico (tipo di relazione articolo=articolo) o come parte di una chiave di allocazione articolo (tipo di relazione articolo=gruppo).    
2. Nel campo Tipo di relazione articolo selezionare l'articolo
3. Nel campo Numero articolo, digitare un valore.
4. Immettere un numero nel campo Rapporto produttività.
    * La relazione di produttività predefinita è 1, in modo da indicare che i prodotti correlati utilizzano esattamente la capacità specificata nelle attività di processo dei flussi di produzione. Rapporto produttività > 1 definisce un consumo di risorse superiore, Rapporto produttività < 1 definisce un consumo di risorse inferiore. Il rapporto viene utilizzato nel calcolo dei costi e nel calcolo dell'avanzamento processo kanban.  

## <a name="associate-item-allocation-key"></a>Associare una chiave di allocazione articolo
1. Associare una chiave di allocazione articolo
    * Aggiungere un'associazione a una chiave di allocazione articolo utilizzando il tipo di relazione articolo Gruppo.   Si noti che per questo processo, è necessario una chiave di allocazione articolo di previsione definita nei dati.  
2. Nel campo Tipo di relazione articolo selezionare Gruppo
3. Nel campo Chiave di allocazione articolo fare clic sul pulsante a discesa per aprire la ricerca.
4. Nell'elenco fare clic sul collegamento nella riga selezionata.


