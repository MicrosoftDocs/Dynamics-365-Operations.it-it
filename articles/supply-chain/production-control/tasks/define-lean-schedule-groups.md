---
title: Definire gruppi di produzione snella
description: I gruppi di programmazione snella sono definiti per raggruppare e distinguere i prodotti nella programmazione kanban.
author: johanhoffmann
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LeanScheduleGroup, GanttColorTableLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c9d16c0d3192773c32c8dcc57a430607c6b60f97
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/29/2021
ms.locfileid: "7574451"
---
# <a name="define-lean-schedule-groups"></a>Definire gruppi di produzione snella

[!include [banner](../../includes/banner.md)]

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
    * La relazione di produttività predefinita è 1, in modo da indicare che i prodotti correlati utilizzano esattamente la capacità specificata nelle attività di elaborazione dei flussi di produzione. Rapporto produttività > 1 definisce un consumo di risorse superiore, Rapporto produttività < 1 definisce un consumo di risorse inferiore. Il rapporto viene utilizzato nel calcolo dei costi e nel calcolo dell'avanzamento processo kanban.  

## <a name="associate-item-allocation-key"></a>Associare una chiave di allocazione articolo
1. Associare una chiave di allocazione articolo
    * Aggiungere un'associazione a una chiave di allocazione articolo utilizzando il tipo di relazione articolo Gruppo.   Si noti che per questo processo, è necessario una chiave di allocazione articolo di previsione definita nei dati.  
2. Nel campo Tipo di relazione articolo selezionare Gruppo
3. Nel campo Chiave di allocazione articolo fare clic sul pulsante a discesa per aprire la ricerca.
4. Nell'elenco fare clic sul collegamento nella riga selezionata.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]