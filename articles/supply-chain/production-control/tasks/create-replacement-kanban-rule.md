---
title: Creare una regola kanban di sostituzione
description: Questa procedura mostra come sostituire la regola kanban esistente con una nuova regola kanban in una data specifica.
author: johanhoffmann
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: KanbanRules, KanbanRuleDuplicate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2db44c1b43a6dc5e0ab37a7756c4eecaab468e15
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/29/2021
ms.locfileid: "7570059"
---
# <a name="create-a-replacement-kanban-rule"></a>Creare una regola kanban di sostituzione

[!include [banner](../../includes/banner.md)]

Questa procedura mostra come sostituire la regola kanban esistente con una nuova regola kanban in una data specifica. Questa opzione è utile quando le modifiche al flusso di produzione o alle regole di rifornimento devono essere coordinate e programmate. La società di dati dimostrativi utilizzata per creare la procedura è USMF. Questa procedura è destinata all'addetto procedure tecniche o al responsabile flusso del valore quando prepara la produzione di un flusso di produzione modificato o una nuova regola di rifornimento. Questa attività sostituisce la regola kanban 000022 con una nuova regola e aumenta la quantità massima da 48 a 100 per la nuova regola.


## <a name="select-a-kanban-rule-to-replace"></a>Selezionare una regola kanban da sostituire.
1. Passare a Regole kanban.
2. Nell'elenco trovare e selezionare il record desiderato.
    * Selezionare una regola kanban 000022.  

## <a name="create-a-replacement-kanban-rule"></a>Creare una regola kanban di sostituzione
1. Fare clic su Sostituisci regola kanban.
2. Nel campo Data di validità immettere una data e un'ora.
    * Selezionare una data futura, ad esempio una settimana da oggi. È la data e l'ora in cui la nuova regola kanban diventa attiva e sostituisce la regola kanban vecchia.  
    * Se la regola kanban modifica il percorso del flusso di produzione, un'altra attività può essere selezionata.  In questa procedura l'attività non verrà toccata.  
3. Fare clic su OK.
    * Viene creata una nuova regola kanban per sostituire la regola kanban 000022.  
    * La data di validità viene impostata in base alla data scelta quando si sostituisce la regola kanban.  
4. Nell'elenco trovare e selezionare il record desiderato.
    * Selezionare la regola kanban 000022 sostituita.  
    * La regola kanban sostituita ha la stessa data della data di scadenza poiché questa è la data in cui scadrà.  
5. Nell'elenco selezionare la riga 1.
    * Selezionare la nuova regola kanban in cima all'elenco. Si tratta della regola kanban con il numero più elevato.  
6. Nell'elenco fare clic sul collegamento nella riga selezionata.
    * Fare clic sul numero della regola kanban per aprire la regola.  

## <a name="modify-maximum-quantity-for-the-replacement-kanban-rule"></a>Modificare la quantità massima per la regola kanban sostitutiva
1. Impostare Quantità massima su "100".
    * Espandere la scheda dettaglio Quantità per visualizzare il campo Quantità massima. Modificare la quantità massima in 100 permetterà l'elaborazione di un massimo di 100 kanban.    Questo è l'ultimo passaggio di questa attività.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]