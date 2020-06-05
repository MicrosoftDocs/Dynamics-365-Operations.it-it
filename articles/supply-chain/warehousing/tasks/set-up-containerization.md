---
title: Impostare containerizzazione
description: Questa argomento descrive come automatizzare la containerizzazione dei carichi in Gestione magazzino.
author: ShylaThompson
manager: tfehr
ms.date: 07/22/19
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSWaveTemplateTable, InventLocationIdLookup, WHSContainerType, WHSContainerGroup, WHSContainerizationTable, WHSContainerizationBreak, WHSCreateContainerBreak
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mirzaab
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f0f042e6ffe5ecf01b9e5044fc83d081528fbc56
ms.sourcegitcommit: 8a2127c5af6cdbda30ccc1f9bef9bd4ab61e9e50
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/18/2020
ms.locfileid: "3383299"
---
# <a name="set-up-containerization"></a>Impostare containerizzazione

[!include [banner](../../includes/banner.md)]

Questa argomento descrive come automatizzare la containerizzazione dei carichi in Gestione magazzino. La containerizzazione automatica crea contenitori e il lavoro di prelievo per le spedizioni quando un'ondata viene elaborata e le righe di lavoro possono essere divise in quantità adatte ai contenitori. In questo modo i magazzinieri possono prelevare gli articoli direttamente dal contenitore specificato. Rispetto al processo manuale di imballaggio, attività quali la creazione di contenitori, l'assegnazione di articoli e la chiusura di contenitori vengono automatizzate dal sistema. Questa procedura utilizza per la società dimostrativa USMF e viene eseguita da un responsabile magazzino.


## <a name="set-up-a-wave-template"></a>Impostare un modello di ondata
1. Nel pannello di navigazione andare a **Moduli > Gestione magazzino > Impostazioni > Ondate > Modelli ondata**.
2. Selezionare **Nuovo**.
3. Digitare un valore nel campo **Nome modello ondata**.
4. Nel campo **Descrizione modello ondata** immettere un valore.
5. Nel campo **Sito** immettere o selezionare un valore.
6. Nel campo **Magazzino** immettere o selezionare un valore.
7. Espandere la sezione **Metodi**. Nel riquadro **Metodi selezionati** sono elencati i metodi per il tipo di modello di ondata selezionato. Il modello di ondata deve includere il metodo di containerizzazione.  
8. Digitare un valore nel campo **Codice passaggio ondata**. Immettere un codice passaggio ondata per il metodo aggiunto, che può essere qualsiasi codice. È possibile aggiungere più volte il metodo e assegnare codici passaggio ondata diversi. A questo scopo, selezionare **Ripetibile per questo metodo** nella pagina **Metodi di elaborazione ondata**.  
9. Selezionare **Salva**.
10. Chiudere la pagina.

## <a name="set-up-a-container-type"></a>Impostare un tipo di contenitore
1. Nel pannello di navigazione andare a **Moduli > Gestione magazzino > Impostazioni > Contenitori > Tipi di contenitore**. È possibile definire i contenitori nella pagina **Tipi di contenitore**. È possibile configurare le dimensioni fisiche dei contenitori, inclusi tara, peso massimo, volume massimo, lunghezza, larghezza, peso e altezza. In questo esempio sono presenti tre dimensioni diverse di caselle.  
2. Selezionare **Nuovo**.
3. Nel campo **Codice tipo di contenitore** immettere un valore.
4. Immettere un numero nel campo **Tara**.
5. Nel campo **Peso massimo** immettere un numero.
6. Nel campo **Volume** immettere un numero.
7. Immettere un numero nel campo **Lunghezza.**
8. Nel campo **Larghezza** immettere un numero.
9. Nel campo **Altezza** immettere un numero.
10. Digitare un valore nel campo **Descrizione**
11. Selezionare **Salva**.
13. Ripetere i passaggi 2-11 altre due volte per creare tre tipi di contenitori totali.
14. Chiudere la pagina.

## <a name="set-up-a-container-group"></a>Impostare un gruppo di contenitori
1. Nel pannello di navigazione andare a **Moduli > Gestione magazzino > Impostazioni > Contenitori > Gruppo di contenitori**.
2. Nel Riquadro azioni selezionare **Nuovo**. È possibile impostare i gruppi logici dei tipi di contenitore. Per ogni gruppo è possibile specificare la sequenza in cui imballare i contenitori e la percentuale di riempimento dei contenitori. Vengono utilizzate le dimensioni di tipo Dimensione dell'articolo per determinare se potrà essere inserito in un contenitore. Viene utilizzato il contenitore più vicino alle dimensioni di tipo Dimensione dell'articolo. Se in un gruppo sono presenti più tipi di contenitore, è consigliabile disporre la sequenza in base alla dimensione, in modo che il contenitore più grande sia il primo, il numero 1 della sequenza, e il contenitore più piccolo sia l'ultimo.    
3. Nel campo **ID gruppo contenitori**, immettere un valore creato in precedenza.
4. Digitare un valore nel campo **Descrizione**
5. Ripetere i passaggi 2-4 per tutti e tre i tipi di contenitore creati in precedenza.
6. Selezionare **Salva**.
7. Chiudere la pagina.

## <a name="set-up-a-container-build-template"></a>Impostare un modello di versione del contenitore
1. Nel pannello di navigazione andare a **Moduli > Gestione magazzino > Impostazioni > Contenitori > Modelli di build contenitore**.
2. Selezionare **Nuovo**. Il modello di compilazione contenitore dipende da quale processo di containerizzazione viene eseguito. Ogni modello di compilazione contenitore definisce un processo di containerizzazione che verrà utilizzato da un modello di ondata. L'opzione **Modifica query** consente di definire le condizioni in cui il modello selezionato verrà elaborato. Ad esempio, potrebbe essere necessario eseguire solo la containerizzazione per clienti, prodotti o magazzini specifici oppure è possibile aggiungere gli intervalli corrispondenti di query al modello. Il campo **Codice passaggio ondata** è come un modello di build contenitore è collegato ai passaggi nel modello di ondata. Quando un'ondata viene eseguita, determina quali modelli di compilazione contenitore vengono utilizzati per avviare la containerizzazione. Il campo Tipo di query di base determina che cosa imballare e su cosa basare la query del filtro. 
3. Digitare un valore nel campo **ID modello contenitore**.
4. Nel campo **ID gruppo contenitori** immettere o selezionare un valore.
5. Digitare un valore nel campo **Codice passaggio ondata**.
6. Selezionare la casella di controllo **Consenti prelievi condivisi**.
7. Selezionare **Salva**.
8. Fare clic su **Vincoli combinazione contenitore**. L'opzione Suddivisioni logica combinazione consente di impostare le regole di imballaggio delle righe di allocazione in contenitori. Ad esempio, se si aggiunge il campo **Numero articolo**, quando gli articoli vengono assegnati ai contenitori, un nuovo contenitore verrà creato quando è presente un nuovo numero di articolo. Ciò impedirà ai lavoratori di imballare righe di allocazioni per due diversi clienti nello stesso contenitore.  
9. Selezionare **Nuovo**.
10. Selezionare un'opzione nel campo **Tabella**.
11. Nel campo **Selezione campi** immettere o selezionare un valore.
12. Selezionare **OK**.

