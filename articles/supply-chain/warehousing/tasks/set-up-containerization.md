--- 
title: Impostare la containerizzazione
description: Questa procedura descrive come automatizzare la containerizzazione dei carichi in Gestione magazzino.
author: YuyuScheller
manager: AnnBe
ms.date: 06/07/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mirzaab
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: aeb7d956560c513c08d5e20dcf20989b49137a52
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---
# <a name="set-up-containerization"></a>Impostare la containerizzazione

[!include[task guide banner](../../includes/task-guide-banner.md)]

Questa procedura descrive come automatizzare la containerizzazione dei carichi in Gestione magazzino. La containerizzazione automatica crea contenitori e il lavoro di prelievo per le spedizioni quando un'ondata viene elaborata e le righe di lavoro possono essere divise in quantità adatte ai contenitori. In questo modo i magazzinieri possono prelevare gli articoli direttamente dal contenitore specificato. Rispetto al processo manuale di imballaggio, attività quali la creazione di contenitori, l'assegnazione di articoli e la chiusura di contenitori vengono automatizzate dal sistema. Questa procedura utilizza per la società dimostrativa USMF e viene eseguita da un responsabile magazzino.


## <a name="set-up-a-wave-template"></a>Impostare un modello di ondata
1. Andare a Gestione magazzino > Impostazioni > Ondate > Modelli ondata.
2. Fare clic su Nuovo.
3. Digitare un valore nel campo Nome modello ondata.
4. Nel campo Descrizione modello ondata immettere un valore.
5. Nel campo Sito immettere o selezionare un valore.
6. Nel campo Magazzino immettere o selezionare un valore.
7. Espandere la sezione Metodi.
    * Nel riquadro Metodi selezionati sono elencati i metodi per il tipo di modello di ondata selezionato. Il modello di ondata deve includere il metodo di containerizzazione.  
8. Nell'elenco trovare e selezionare il record desiderato.
9. Digitare un valore nel campo Codice passaggio ondata.
    * Immettere un codice passaggio ondata per il metodo aggiunto, che può essere qualsiasi codice. È possibile aggiungere più volte il metodo e assegnare codici passaggio ondata diversi. A questo scopo, selezionare Ripetibile per questo metodo nella pagina Metodi di elaborazione ondata.  
10. Fare clic su Salva.
11. Chiudere la pagina.

## <a name="set-up-a-container-type"></a>Impostare un tipo di contenitore
1. Andare a Gestione magazzino > Impostazioni > Contenitori > Tipi di contenitore.
    * È possibile definire i contenitori nella pagina Tipi di contenitore. È possibile configurare le dimensioni fisiche dei contenitori, inclusi tara, peso massimo, volume massimo, lunghezza, larghezza, peso e altezza. In questo esempio sono presenti tre dimensioni diverse di caselle.  
2. Fare clic su Nuovo.
3. Nel campo Codice tipo di contenitore immettere un valore.
4. Immettere un numero nel campo Tara.
5. Nel campo Peso massimo immettere un numero.
6. Nel campo Volume immettere un numero.
7. Immettere un numero nel campo Lunghezza.
8. Nel campo Larghezza immettere un numero.
9. Nel campo Altezza immettere un numero.
10. Nel campo Descrizione digitare un valore.
11. Fare clic su Salva.
12. Fare clic su Nuovo.
13. Nel campo Codice tipo di contenitore immettere un valore.
14. Nel campo Descrizione digitare un valore.
15. Immettere un numero nel campo Tara.
16. Nel campo Peso massimo immettere un numero.
17. Nel campo Volume immettere un numero.
18. Immettere un numero nel campo Lunghezza.
19. Nel campo Larghezza immettere un numero.
20. Nel campo Altezza immettere un numero.
21. Fare clic su Salva.
22. Fare clic su Nuovo.
23. Nel campo Codice tipo di contenitore immettere un valore.
24. Nel campo Descrizione digitare un valore.
25. Immettere un numero nel campo Tara.
26. Nel campo Peso massimo immettere un numero.
27. Nel campo Volume immettere un numero.
28. Immettere un numero nel campo Lunghezza.
29. Nel campo Larghezza immettere un numero.
30. Nel campo Altezza immettere un numero.
31. Fare clic su Salva.
32. Chiudere la pagina.

## <a name="set-up-a-container-group"></a>Impostare un gruppo di contenitori
1. Andare a Gestione magazzino > Impostazioni > Contenitori > Gruppi di contenitori.
2. Fare clic su Nuovo.
    * È possibile impostare i gruppi logici dei tipi di contenitore. Per ogni gruppo è possibile specificare la sequenza in cui imballare i contenitori e la percentuale di riempimento dei contenitori. Vengono utilizzate le dimensioni di tipo Dimensione dell'articolo per determinare se potrà essere inserito in un contenitore. Viene utilizzato il contenitore più vicino alle dimensioni di tipo Dimensione dell'articolo. Se in un gruppo sono presenti più tipi di contenitore, è consigliabile disporre la sequenza in base alla dimensione, in modo che il contenitore più grande sia il primo, il numero 1 della sequenza, e il contenitore più piccolo sia l'ultimo.    
3. Digitare un valore nel campo ID gruppo contenitori.
4. Nel campo Descrizione digitare un valore.
5. Fare clic su Nuovo.
6. Nell'elenco contrassegnare la riga selezionata.
7. Nel campo Tipo di contenitore immettere o selezionare un valore.
8. Fare clic su Nuovo.
9. Nell'elenco contrassegnare la riga selezionata.
10. Nel campo Tipo di contenitore immettere o selezionare un valore.
11. Fare clic su Nuovo.
12. Nell'elenco contrassegnare la riga selezionata.
13. Nel campo Tipo di contenitore immettere o selezionare un valore.
14. Fare clic su Salva.
15. Chiudere la pagina.

## <a name="set-up-a-container-build-template"></a>Impostare un modello di versione del contenitore
1. Andare a Gestione magazzino > Impostazioni > Contenitori > Modelli di build contenitore.
2. Fare clic su Nuovo.
    * Il modello di compilazione contenitore dipende da quale processo di containerizzazione viene eseguito. Ogni modello di compilazione contenitore definisce un processo di containerizzazione che verrà utilizzato da un modello di ondata. L'opzione Modifica query consente di definire le condizioni in cui il modello selezionato verrà elaborato. Ad esempio, potrebbe essere necessario eseguire solo la containerizzazione per clienti, prodotti o magazzini specifici oppure è possibile aggiungere gli intervalli corrispondenti di query al modello. Il campo Codice passaggio ondata è come un modello di compilazione contenitore è collegato ai passaggi nel modello di ondata. Quando un'ondata viene eseguita, determina quali modelli di compilazione contenitore vengono utilizzati per avviare la containerizzazione. Il campo Tipo di query di base determina che cosa imballare e su cosa basare la query del filtro.  
3. Nell'elenco contrassegnare la riga selezionata.
4. Digitare un valore nel campo ID modello contenitore.
5. Nel campo ID gruppo contenitori immettere o selezionare un valore.
6. Digitare un valore nel campo Codice passaggio ondata.
7. Selezionare la casella di controllo Consenti prelievi condivisi.
8. Fare clic su Salva.
9. Fare clic su Vincoli combinazione contenitore.
    * L'opzione Suddivisioni logica combinazione consente di impostare le regole di imballaggio delle righe di allocazione in contenitori. Ad esempio, se si aggiunge il campo Numero articolo, quando gli articoli vengono assegnati ai contenitori, un nuovo contenitore verrà creato quando è presente un nuovo numero di articolo. Ciò impedirà ai lavoratori di imballare righe di allocazioni per due diversi clienti nello stesso contenitore.  
10. Fare clic su Nuovo.
11. Selezionare un'opzione nel campo Tabella.
12. Nel campo Selezione campi immettere o selezionare un valore.
13. Fare clic su OK.


