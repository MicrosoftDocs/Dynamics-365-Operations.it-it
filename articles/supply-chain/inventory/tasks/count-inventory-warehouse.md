--- 
title: Contare le scorte magazzino
description: In questa procedura vengono descritti i passaggi per creare e registrare un giornale di registrazione conteggi scorte in modo da conteggiare un articolo specifico in un'ubicazione del magazzino.
author: MarkusFogelberg
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventJournalCount, InventJournalCreate, HcmWorkerLookUp, InventItemIdLookupSimple, InventLocationIdLookup, WMSLocationIdLookup, InventTrans
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mafoge
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: fa72cb0d651f5e60797fa41f6e2b2cf1891730b5
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---
# <a name="count-inventory-in-a-warehouse"></a>Contare le scorte magazzino

[!include [task guide banner](../../includes/task-guide-banner.md)]

In questa procedura vengono descritti i passaggi per creare e registrare un giornale di registrazione conteggi scorte in modo da conteggiare un articolo specifico in un'ubicazione del magazzino. In questa procedura si applica la funzionalità di gestione magazzino di base, disponibile nel modulo Gestione articoli e non la funzionalità di gestione del magazzino disponibile nel modulo Gestione magazzino. È possibile eseguire questa procedura nella società di dati dimostrativi USMF oppure utilizzando i propri dati. Se si utilizzano propri dati, assicurarsi di aver configurato prodotti e ubicazioni e aver creato un nome di giornale di registrazione magazzino per il conteggio dei giornali di registrazione. Il conteggio delle scorte viene in genere eseguito da un dipendente del reparto magazzino.


## <a name="create-an-inventory-counting-journal"></a>Creare un giornale di registrazione conteggi scorte
1. Andare a Gestione inventario > Inserimenti nel giornale di registrazione > Conteggio articoli > Conteggio.
2. Fare clic su Nuovo.
3. Nel campo Nome fare clic sul pulsante a discesa per aprire la ricerca.
4. Nell'elenco, fare clic sul nome giornale di registrazione conteggio scorte che si desidera utilizzare.
    * Alcuni campi saranno popolati in base all'impostazione del nome giornale di registrazione conteggio scorte selezionato.  
5. Nel campo Lavoratore fare clic sul pulsante a discesa per aprire la ricerca.
6. Selezionare dall'elenco il lavoratore desiderato.
7. Fare clic su Seleziona.
8. Fare clic su OK.

## <a name="create-journal-lines"></a>Creare righe di giornale di registrazione
1. Fare clic su Nuovo.
2. Nel campo Numero articolo fare clic sul pulsante a discesa per aprire la ricerca.
3. Nell'elenco trovare e selezionare il record desiderato.
    * Se si utilizza la società di dati dimostrativi USMF, selezionare 'A0001'.  
4. Nel campo Sito fare clic sul pulsante a discesa per aprire la ricerca.
5. Nell'elenco trovare e selezionare il record desiderato.
    * Se si utilizza la società di dati dimostrativi USMF, selezionare il sito '2'.  
6. Nel campo Magazzino fare clic sul pulsante a discesa per aprire la ricerca.
7. Nell'elenco trovare e selezionare il record desiderato.
    * Se si utilizza la società di dati dimostrativi USMF, selezionare il magazzino '24'.  
8. Nel campo Ubicazione fare clic sul pulsante a discesa per aprire la ricerca.
9. Nell'elenco trovare e selezionare il record desiderato.
    * Se si utilizza la società di dati dimostrativi USMF, selezionare l'ubicazione 'BULK-001'.  
10. Nel campo Conteggiato immettere un numero.
    * Se si immette un numero diverso dal numero indicato nel campo Disponibilità, il campo Quantità viene aggiornato per visualizzare la discrepanza.  
11. Fare clic su Salva.

## <a name="post-the-inventory-counting-journal"></a>Registrare il giornale di registrazione conteggi scorte
1. Fare clic su Registra.
    * Durante la registrazione di giornale di registrazione conteggio scorte, se l'importo conteggiato è diverso dall'importo che viene dichiarato nel campo Disponibilità, viene registrata un'entrata o un'uscita dal magazzino, vengono modificati il livello e il valore delle scorte e vengono generate le transazioni contabili.  
2. Fare clic su OK.

## <a name="view-inventory-transactions"></a>Visualizza operazioni di magazzino
1. Fare clic su Scorte.
2. Fare clic su Transazioni.
    * È possibile visualizzare tutte le transazioni correlate che verranno create quando si registra il giornale di registrazione conteggi scorte.   


