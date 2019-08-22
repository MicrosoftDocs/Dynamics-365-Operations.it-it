---
title: Creare una regola kanban tramite un evento scorte minime
description: Questa procedura si concentra sulla configurazione necessaria per creare una regola kanban facendo uso di un evento di scorte minime per assicurarsi che un prodotto specifico sia sempre disponibile in una ubicazione specifica.
author: ChristianRytt
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanRules, LeanProductionFlowActivityLookup, InventItemIdLookupSimple, EcoResProductInformationDialog, EcoResProductDetailsExtended, ReqItemTable, InventLocationIdLookup
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4b578a664e9e3b6496e5665b2eefd9d75f86ecc3
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/01/2019
ms.locfileid: "1837832"
---
# <a name="create-a-kanban-rule-using-a-minimum-stock-event"></a>Creare una regola kanban tramite un evento scorte minime

[!include [task guide banner](../../includes/task-guide-banner.md)]

Questa procedura si concentra sulla configurazione necessaria per creare una regola kanban facendo uso di un evento di scorte minime per assicurarsi che un prodotto specifico sia sempre disponibile in una ubicazione specifica. Una regola kanban è creata per trasferire il materiale all'ubicazione quando il livello delle scorte scende sotto 200 pezzi. Eseguendo l'elaborazione dell'evento di pegging, i kanbans necessari vengono creati. La società di dati dimostrativi utilizzata per creare questa attività è USMF. Questa attività è destinata all'addetto procedure tecniche o al responsabile flusso del valore che prepara la produzione di un prodotto nuovo o modificato in un ambiente lean manufacturing.


## <a name="create-a-new-kanban-rule"></a>Crea una nuova regola kanban
1. Andare a Gestione informazioni sul prodotto > Lean manufacturing > Regole kanban.
2. Fare clic su Nuovo.
3. Selezionare "Prelievo" nel campo Tipo.
    * Questo tipo viene utilizzato per creare kanban di trasferimento.  
4. Nel campo Strategia di rifornimento, selezionare 'Evento'.
    * La strategia di evento è utilizzata per creare i kanban di trasferimento basati su un evento. Successivamente nella procedura, si attiveranno i kanban di trasferimento usando il rifornimento scorte.  
5. Nel campo Prima attività piano immettere o selezionare un valore.
    * Immettere o selezionare ReplenishSpeakerComponents. Questa attività di trasferimento ha magazzino e ubicazione di entrata (output) 12, pertanto il materiale verrà spostato in ubicazione 12 in magazzino 12.  
6. Espandere la sezione Dettagli.
7. Nel campo Prodotto immettere o selezionare un valore.
    * Selezionare M0007.  
8. Espandere la sezione Eventi.
9. Nel campo Evento rifornimento scorte, selezionare 'Batch'.
    * Ciò crea i kanban per soddisfare il fabbisogno di materiali all'ubicazione correlata durante l'elaborazione dell'evento di pegging.  

## <a name="set-the-minimum-quantity-for-the-item"></a>Impostare la quantità minima per l'articolo
1. Fare clic per seguire il collegamento nel campo Prodotto.
2. Fare clic per seguire il collegamento nel campo Numero articolo.
3. Espandere il Dettaglio informazioni Immagine prodotto.
4. Nel riquadro azioni fare clic su Piano.
5. Fare clic su Copertura articoli.
6. Fare clic su Nuovo.
7. Nell'elenco contrassegnare la riga selezionata.
8. Nel campo Magazzino immettere o selezionare un valore.
    * Impostare Magazzino su 12.  
9. Impostare il minimo su '200'.

## <a name="run-the-batch-event-creation-job"></a>Eseguire il processo di creazione evento batch
1. Andare a Controllo produzione > Attività periodiche > Elaborazione batch processo kanban > Elaborazione evento di pegging.
2. Fare clic su OK.
3. Andare a Gestione informazioni sul prodotto > Lean manufacturing > Regole kanban.
4. Nell'elenco fare clic sul collegamento nella riga selezionata.
    * Selezionare la regola kanban creata in precedenza.  
5. Espandere la sezione Kanban.
    * Notare che un kanban è stato creato per trasferire il materiale necessario per il magazzino 12.  

