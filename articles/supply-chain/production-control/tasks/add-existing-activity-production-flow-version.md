---
title: Aggiungere un'attività esistente a una versione del flusso di produzione
description: Durante la creazione di nuove versioni dei flussi di produzione, è possibile scegliere di aggiungere attività create per le versioni precedenti, nella nuova versione.
author: cvocph
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LeanProductionFlow, PlanActivity, PlanActivityAddExisting, PlanActivityAddExistingLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8dc890462ac44f0471882e65b928563415aceaea
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2020
ms.locfileid: "3212436"
---
# <a name="add-an-existing-activity-to-a-production-flow-version"></a>Aggiungere un'attività esistente a una versione del flusso di produzione

[!include [banner](../../includes/banner.md)]

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

