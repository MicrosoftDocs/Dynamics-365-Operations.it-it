--- 
title: "Aggiungere un'attività esistente a una versione del flusso di produzione"
description: "Durante la creazione di nuove versioni dei flussi di produzione, è possibile scegliere di aggiungere attività create per le versioni precedenti, nella nuova versione."
author: cvocph
manager: AnnBe
ms.date: 10/26/2016
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
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: a74fb34db71ba4b539c1b6ede361329aaeb94920
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---
# <a name="add-an-existing-activity-to-a-production-flow-version"></a>Aggiungere un'attività esistente a una versione del flusso di produzione

[!include[task guide banner](../../includes/task-guide-banner.md)]

Durante la creazione di nuove versioni dei flussi di produzione, è possibile scegliere di aggiungere attività create per le versioni precedenti, nella nuova versione. In questa procedura viene illustrato come viene creata una nuova versione di un flusso di produzione esistente, senza copiare le attività. Nel passaggio successivo, un'attività esistente viene aggiunta alla nuova versione. 

Per questa attività è necessario un flusso di produzione con versione e attività già create.


## <a name="create-a-new-production-flow-version"></a>Crea nuova versione flusso di produzione
1. Andare a Controllo produzione > Impostazioni > Flusso di produzione snella > Flussi di produzione.
2. Nell'elenco trovare e selezionare il record desiderato.
3. Nell'elenco fare clic sul collegamento nella riga selezionata.
4. Fare clic su Modifica.
5. Nell'elenco contrassegnare la riga selezionata.
6. Nel campo Data di scadenza immettere una data e un'ora.
    * Tenere presente che prima di creare una nuova versione del flusso di produzione, accertarsi di controllare la data e l'ora di scadenza della versione attiva. La nuova versione verrà creata con una data di inizio validità, che si connetterà alla data di scadenza della versione selezionata.  
7. Scegliere Aggiungi.
8. Selezionare No nel campo Copia da versione.
    * Selezionare No per iniziare con una versione vuota se la maggior parte delle attività della versione copiata verranno sostituite da nuove attività. Aggiungere manualmente le attività immutate alla funzione Aggiungi esistente nel modulo delle attività.  
9. Selezionare No nel campo Duplica regole kanban.
    * Quando le attività non sono copiate nella nuova versione, non sarà possibile copiare le regole kanban al momento della creazione di una nuova versione.   Invece si utilizzerà successivamente la funzione di creazione di una regola kanban sostitutiva nel modulo delle regole kanban, per sostituire le regole kanban della versione precedente del flusso di produzione con le regole kanban che utilizzano le attività della nuova versione.  
10. Fare clic su OK.
11. Nell'elenco trovare e selezionare il record desiderato.

## <a name="add-an-existing-activity"></a>Aggiungere un'attività esistente
1. Fare clic su Attività.
2. Fare clic su Aggiungi esistente per aprire la finestra di dialogo a discesa.
    * Trovare e selezionare un'attività esistente da aggiungere alla nuova versione del flusso di produzione.  Tenere presente che l'elenco visualizza tutte le attività create per questo flusso di produzione per tutte le versioni precedenti del flusso.  
3. Nel campo Attività immettere o selezionare un valore.
4. Fare clic su OK.


