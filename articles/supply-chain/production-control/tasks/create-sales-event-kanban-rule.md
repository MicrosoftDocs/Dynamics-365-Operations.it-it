--- 
title: Creare una regola kanban eventi di vendita
description: "Questa procedura è incentrata sull'impostazione necessaria per creare una regola kanban che è attivata durante la creazione di un ordine cliente."
author: ChristianRytt
manager: AnnBe
ms.date: 03/02/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: f1f66157b2e74ad1b490e10112cbc121ac9826fb
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---
# <a name="create-a-sales-event-kanban-rule"></a>Creare una regola kanban eventi di vendita

[!include [task guide banner](../../includes/task-guide-banner.md)]

Questa procedura è incentrata sull'impostazione necessaria per creare una regola kanban che è attivata durante la creazione di un ordine cliente. La regola kanban eventi soddisfa i requisiti che derivano dalle righe di ordine cliente. La società di dati dimostrativi utilizzata per creare questa procedura è USMF. Questa procedura è destinata all'addetto procedure tecniche o al responsabile flusso del valore che prepara la produzione di un prodotto nuovo o modificato.




## <a name="create-a-new-kanban-rule"></a>Crea una nuova regola kanban
1. Passare a Regole kanban.
2. Fare clic su Nuovo.
3. Nel campo Strategia di rifornimento, selezionare 'Evento'.
    * Selezionare un evento indica che la regola kanban è attivata da un evento, ad esempio, la creazione di una riga ordine cliente.   Applicabile alle aree in cui ogni kanban deve coprire una richiesta specifica.  
4. Nel campo Prima attività piano immettere o selezionare un valore.
    * Selezionare Assembly finale.  
5. Espandere la sezione Dettagli.
6. Nel campo Prodotto immettere o selezionare un valore.
    * Selezionare L0050.  

## <a name="define-an-event"></a>Definire un evento
1. Espandere la sezione Eventi.
2. Nel campo Evento vendite selezionare 'Automatico'.
    * Selezionando l'evento vendite Automatico, la regola kanban verrà attivata automaticamente quando una riga di vendita corrisponde al prodotto e all'ubicazione di entrata. In questa procedura, si tratta del prodotto L0050 nel magazzino 13.  
3. Impostare Quantità minima evento su '50'.
    * Con una quantità di evento minima di 50, la regola kanban verrà attivata solo gli eventi con una quantità di 50 o più.  
4. Espandere la sezione Flusso di produzione.
    * Si noti che l'ubicazione di entrata è il magazzino 13. Ciò significa che la regola kanban verrà attivata per questa ubicazione.  
    * In questo esempio, una riga di vendita per il prodotto L0050, con una quantità di 50 o più, nel magazzino 13, attiverà questa regola kanban.  

## <a name="create-sales-line-to-trigger-event-kanban-rule"></a>Creare la riga di vendita per attivare la regola kanban eventi
1. Fare clic su Tutti gli ordini cliente.
    * Un avviso viene visualizzato quando la regola kanban viene salvata, pertanto i kanban verranno creati in tempo reale durante la creazione dell'ordine cliente.  
2. Fare clic su Nuovo.
3. Nel campo Conto cliente, immettere o selezionare un valore.
    * Selezionare, ad esempio, US-003.  
4. Fare clic su OK.
5. Nel campo Numero articolo digitare "L0050".
6. Nel campo Sito digitare '1'.
    * Selezionare Sito 1 poiché il magazzino 13 si trova nel sito 1.  
7. Nel campo Magazzino immettere o selezionare un valore.
    * Impostare Magazzino su 13.  
8. Impostare la quantità su "75".
    * Impostare una quantità pari a 50 o maggiore per attivare la regola kanban creata.  

## <a name="verify-that-kanban-is-created"></a>Verificare che il kanban venga creato
1. Fare clic su Prodotto e fornitura.
2. Fare clic su Visualizza struttura di pegging.
    * Si noti che viene creato un kanban con la stessa quantità della riga di vendita. È inoltre possibile visualizzare le uscite materiali necessarie per la produzione di L0050. Si tratta dell'ultimo passaggio di questa procedura.  


