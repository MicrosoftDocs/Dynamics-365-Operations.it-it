---
title: Contare le scorte magazzino
description: In questa argomento vengono descritti i passaggi per creare e registrare un giornale di registrazione conteggi scorte in modo da conteggiare un articolo specifico in un'ubicazione del magazzino.
author: yufeihuang
ms.date: 07/09/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: InventJournalCount, InventJournalCreate, HcmWorkerLookUp, InventItemIdLookupSimple, InventLocationIdLookup, WMSLocationIdLookup, InventTrans
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4b7dd3788d3cbf80bfba373f5b6ce9d2e0ca0c07
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/29/2021
ms.locfileid: "7578418"
---
# <a name="count-inventory-in-a-warehouse"></a>Contare le scorte magazzino

[!include [banner](../../includes/banner.md)]

In questa argomento vengono descritti i passaggi per creare e registrare un giornale di registrazione conteggi scorte in modo da conteggiare un articolo specifico in un'ubicazione del magazzino. In questa procedura si applica la "funzionalità di gestione magazzino di base", disponibile nel modulo Gestione articoli e non la funzionalità di gestione del magazzino disponibile nel modulo Gestione magazzino. È possibile eseguire questa procedura nella società di dati dimostrativi USMF oppure utilizzando i propri dati. Se si utilizzano propri dati, assicurarsi di aver configurato prodotti e ubicazioni e aver creato un nome di giornale di registrazione magazzino per il conteggio dei giornali di registrazione. Il conteggio delle scorte viene in genere eseguito da un dipendente del reparto magazzino.


## <a name="create-an-inventory-counting-journal"></a>Creare un giornale di registrazione conteggi scorte
1. Andare a **Pannello di navigazione > Moduli > Gestione inventario > Inserimenti nel giornale di registrazione > Conteggio articoli > Conteggio**.
2. Selezionare **Nuovo**.
3. Nel campo **Nome**, selezionare il nome di giornale di registrazione conteggi scorte che si desidera utilizzare dall'elenco a discesa. Alcuni campi saranno popolati in base all'impostazione del nome giornale di registrazione conteggio scorte selezionato.  
4. Nel campo **Lavoratore** fare clic sul pulsante a discesa per aprire la ricerca.
5. **Selezionare** dall'elenco il lavoratore desiderato.
6. Selezionare **OK**.

## <a name="create-journal-lines"></a>Crea righe di giornale di registrazione
1. Selezionare **Nuovo**.
2. Nel campo **Numero articolo** fare clic sul record desiderato dell'elenco a discesa. Se si utilizza la società di dati dimostrativi USMF, selezionare **A0001**.  
3. Nel campo **Sito** fare clic sul record desiderato dell'elenco a discesa. Se si utilizza la società di dati dimostrativi USMF, selezionare il sito **2**.
4. Nel campo **Magazzino** fare clic sul record desiderato dell'elenco a discesa. Se si utilizza la società di dati dimostrativi USMF, selezionare il magazzino **24**.  
5. Nel campo **Ubicazione** fare clic sul record desiderato dell'elenco a discesa. Se si utilizza la società di dati dimostrativi USMF, selezionare l'ubicazione **BULK-001**.  
6. Nel campo Conteggiato immettere un numero. Se si immette un numero diverso dal numero indicato nel campo **Disponibilità**, il campo **Quantità** viene aggiornato per visualizzare la discrepanza.  
7. Selezionare **Salva**.

## <a name="post-the-inventory-counting-journal"></a>Registrare il giornale di registrazione conteggi scorte
1. Selezionare **Registra**. Durante la registrazione di giornale di registrazione conteggio scorte, se l'importo conteggiato è diverso dall'importo che viene dichiarato nel campo **Disponibilità**, viene registrata un'entrata o un'uscita dal magazzino, vengono modificati il livello e il valore delle scorte e vengono generate le transazioni contabili.
2. Selezionare **OK**.

## <a name="view-inventory-transactions"></a>Visualizza operazioni di magazzino
1. Selezionare **Scorte**.
2. Selezionare **Transazioni**. È possibile visualizzare tutte le transazioni correlate che verranno create quando si registra il giornale di registrazione conteggi scorte.   



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]