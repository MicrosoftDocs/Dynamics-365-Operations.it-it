---
title: Creare una regola kanban eventi riga DBA
description: Questa attività mostra la configurazione necessaria per creare una regola kanban evento per garantire il rifornimento per le righe DBA di produzione in un ambiente di produzione misto lean e classico.
author: ChristianRytt
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: KanbanRules, LeanProductionFlowActivityLookup, InventItemIdLookupSimple, ProdTableListPage, ProdTableCreate, InventItemIdLookupPurchase, ProdTable, ProdBOM, ProdParmCostEstimation
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 27d415e146f33224bcbbfb73498040d584e07f10
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5829212"
---
# <a name="create-a-bom-line-event-kanban-rule"></a>Creare una regola kanban eventi riga DBA

[!include [banner](../../includes/banner.md)]

Questa attività mostra la configurazione necessaria per creare una regola kanban evento per garantire il rifornimento per le righe DBA di produzione in un ambiente di produzione misto lean e classico. La società di dati dimostrativi utilizzata per creare questa attività è USMF. Questa attività è destinata all'addetto procedure tecniche o al responsabile flusso del valore che prepara la produzione di un prodotto nuovo o modificato.


## <a name="create-a-new-kanban-rule"></a>Crea una nuova regola kanban
1. Andare a Controllo produzione > Attività periodiche > Calcolo quantità kanban > Regole kanban.
2. Fare clic su Nuovo.
3. Selezionare "Prelievo" nel campo Tipo.
    * Il tipo Prelievo viene utilizzato per creare kanban di trasferimento.  
4. Nel campo Strategia di rifornimento, selezionare 'Evento'.
    * La strategia di evento è selezionata per creare il trasferimento dei kanban in base a un evento. Più avanti nella guida di attività verrà attivata con la stima di un ordine di produzione.  
5. Nel campo Prima attività piano immettere o selezionare un valore.
    * Immettere o selezionare ReplenishSpeakerComponents. Questa attività di trasferimento ha magazzino e ubicazione di entrata (output) 12, pertanto il materiale verrà spostato in ubicazione 12 in magazzino 12.  
6. Espandere la sezione Dettagli.
7. Nel campo Prodotto immettere o selezionare M0001.
8. Espandere la sezione Eventi.
9. Nel campo Evento riga DBA selezionare "Automatico".
    * Con il campo Evento riga DBA impostato su Automatico, il kanban verrà creato per soddisfare le esigenze di materiale delle righe DBA dell'ordine di produzione.  
10. Chiudere la pagina.

## <a name="create-and-modify-a-new-production-order"></a>Creare e modificare un nuovo ordine di produzione
1. Andare a Controllo produzione > Ordini di produzione > Tutti gli ordini di produzione.
2. Fare clic su Nuovo ordine di produzione.
3. Nel campo Numero di articoli immettere o selezionare un valore.
    * Immettere o selezionare "L0001". Viene utilizzato l'articolo L0001 poiché l'articolo M0001 è incluso nella DBA per l'articolo L0001.  
4. Fare clic su Crea.
5. Nell'elenco fare clic sul collegamento nella riga per L0001
6. Fare clic su DBA.
7. Nell'elenco fare clic sul collegamento nella riga selezionata.
8. Fare clic su Modifica.
9. Nel campo Tipo di riga selezionare "Fornitura sottoposta a pegging".
    * La fornitura sottoposta a pegging è selezionata per avviare la creazione della fornitura di un kanban.  
10. Selezionare No nel campo Consumo risorsa.
    * Deselezionando la casella di controllo Consumo risorsa è possibile modificare il magazzino.  
11. Espandere la sezione Dimensioni inventariali.
12. Nel campo Magazzino digitare "12".
    * Il magazzino viene impostato su 12 poiché questo è il magazzino di output per l'attività di prelievo.  
13. Nel campo Ubicazione digitare "12".
    * L'ubicazione viene impostata su 12 poiché questa è l'ubicazione di output per l'attività di prelievo.  
14. Chiudere la pagina.
15. Chiudere la pagina.

## <a name="estimate-the-production-order-and-view-the-kanban-created"></a>Stimare l'ordine di produzione e visualizzare il kanban creato
1. Fare clic su Stima.
    * La stima dell'ordine di produzione avvierà la creazione del kanban collegato per fornire l'articolo M0001.  
2. Fare clic su OK.
3. Chiudere la pagina.
4. Chiudere la pagina.
5. Andare a Gestione informazioni sul prodotto > Lean manufacturing > Regole kanban.
6. Nell'elenco fare clic sul collegamento nella riga selezionata.
    * Selezionare la regola kanban evento creata per l'articolo M0001.  
7. Espandere la sezione Kanban.
8. Nell'elenco contrassegnare la riga selezionata.
    * Si noti il kanban creato per fornire M0001 per l'ordine di produzione stimato.  
    * Questo è l'ultimo passaggio.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]