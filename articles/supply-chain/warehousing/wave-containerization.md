---
title: Containerizzazione
description: In questo argomento viene descritto come automatizzare la containerizzazione dei carichi. La containerizzazione automatica consente di creare contenitori e il lavoro di prelievo per le spedizioni al momento dell'elaborazione del ciclo.
author: Mirzaab
ms.date: 03/08/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSWaveTemplateTable, InventLocationIdLookup, WHSContainerType, WHSContainerGroup, WHSContainerizationTable, WHSContainerizationBreak, WHSCreateContainerBreak, WHSContainerStructure, WHSContainerTable, WHSContainerizatonHistory, WHSContainerPackingPolicyChange, WHSManifestShipmentContainers, WHSAllowedContainerTypeGroup, WHSPostMethod, WHSContainerCreateDialog, WHSContainerCloseDiag, WHSContainer
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-03-08
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 9293beba6a251a670b918fecbb2315a5e94660b9
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/29/2021
ms.locfileid: "7572267"
---
# <a name="containerization"></a>Containerizzazione

[!include [banner](../includes/banner.md)]

In questo argomento viene descritto come automatizzare la containerizzazione dei carichi. La containerizzazione automatica consente di creare contenitori e il lavoro di prelievo per le spedizioni al momento dell'elaborazione del ciclo.

Per impostare la containerizzazione, è necessario creare quanto segue:

- **Tipo di contenitore**: definisce le caratteristiche fisiche dei contenitori. Utilizza i tipi di contenitore per imballare gli articoli di magazzino in un imballaggio di tipo e dimensioni specifiche, ad esempio contenitori o pallet.
- **Gruppi di contenitori**: crea gruppi di tipi di contenitore simili. Ad esempio, un gruppo di contenitori può includere i tipi di contenitore con dimensioni simili. Un gruppo di contenitori specifica la sequenza in cui i contenitori vengono imballati e la percentuale di riempimento di ciascun contenitore.
- **Modello di versione contenitore**: Crea modelli che definiscono le regole per la containerizzazione. Ad esempio, le regole per combinare l'inventario e altre strategie di imballaggio.
- **Modelli ciclo**: imposta uno o più modelli di ciclo per creare il lavoro di prelievo per la containerizzazione.

## <a name="create-wave-templates-for-containerization"></a>Creare modelli di ciclo per la containerizzazione

È necessario impostare uno o più modelli di ciclo di spedizione per la containerizzazione. I modelli di ciclo includono i criteri che determinano quanto segue:

- La modalità di elaborazione dei cicli. Può essere sia manuale che automatica.
- Come creare un lavoro di prelievo. Questo è determinato dai metodi di ciclo. Il modello di ciclo deve includere il metodo di **containerizzazione**.
- Come abbinare gli articoli o le righe di allocazione al ciclo.

Per ulteriori informazioni, vedi [Modelli di ciclo](wave-templates.md).

## <a name="create-container-types"></a>Creare tipi di contenitore

Utilizza i tipi di contenitore per creare le descrizioni dei contenitori, inclusi i valori massimi per le dimensioni di tipo Dimensione e la capacità di peso fisiche. Quando viene elaborato un ciclo nei contenitori, i contenitori vengono creati in base alle informazioni sul tipo di contenitore.

Per impostare un tipo di contenitore, effettua le seguenti operazioni:

1. Vai a **Gestione magazzino** \> **Impostazioni** \> **Contenitori** \> **Tipi di contenitore**.
1. Seleziona **Nuovo** per creare un tipo di contenitore.
1. Immetti un ID (identificatore univoco) e una descrizione per il tipo di contenitore.
1. Nel campo **Tara** immetti il peso effettivo o stimato del contenitore.
1. Nel campo **Peso massimo** immetti la capacità di peso massima del contenitore.
1. Nei campi **Volume massimo di containerizzazione**, **Lunghezza massima di containerizzazione**, **Larghezza massima di containerizzazione** e **Altezza massima di containerizzazione**, specifica le dimensioni fisiche del contenitore.

    > [!NOTE]
    > I valori della lunghezza e della larghezza sono intercambiabili. Questo significa che è possibile ruotare gli articoli lateralmente o sull'asse x, se necessario. Ad esempio, se la lunghezza è di 2 metri e larghezza è di 1 metro, è possibile modificare la lunghezza in 1 metro e la larghezza in 2 metri. Nota che questo non è applicabile alla dimensione altezza. Non è possibile modificare il valore dell'altezza per ruotare l'articolo verticalmente.

1. Seleziona i valori degli attributi personalizzati per il contenitore nei campi per gli attributi. Gli attributi sono valori personalizzati utilizzati per filtrare o ordinare gli articoli in base a un valore che in caso contrario non è disponibile. Ad esempio, se vuoi imballare gli articoli per un cliente specifico, puoi creare un attributo per il nome del cliente. Puoi creare questi attributi nella pagina **Attributi contenitore**.

## <a name="create-container-groups"></a>Creare gruppi di contenitori

È possibile impostare i gruppi logici dei tipi di contenitore. Per ciascun gruppo è possibile specificare la sequenza in cui i contenitori vengono imballati e la percentuale di riempimento dei contenitori. Le dimensioni di tipo Dimensione dell'articolo determinano se potrà essere inserito in un contenitore. Viene utilizzato il contenitore più vicino alle dimensioni di tipo Dimensione dell'articolo. Se in un gruppo sono presenti più tipi di contenitore, è consigliabile disporre la sequenza in base alla dimensione, in modo che il contenitore più grande sia il primo, il numero 1 della sequenza, e il contenitore più piccolo sia l'ultimo.

Per impostare un gruppo di contenitori, effettua le seguenti operazioni:

1. Vai a **Gestione magazzino** \> **Impostazioni** \> **Contenitori** \> **Gruppi di contenitori**.
1. Seleziona **Nuovo** per creare un gruppo di contenitori.
1. Immetti un ID (identificatore univoco) e una descrizione per il gruppo di contenitori.
1. Nella Scheda dettaglio **Dettagli** seleziona **Nuovo** per aggiungere un tipo di contenitore al gruppo.
1. Nel campo **Tipo di contenitore** seleziona un tipo di contenitore.
1. Seleziona **Sposta su** o **Sposta giù** per specificare la sequenza in cui vengono imballati i tipi di contenitore.

## <a name="create-container-build-templates"></a>Creare modelli di versione del contenitore

Puoi impostare le regole per il processo di containerizzazione, ad esempio le regole di combinazione dell'inventario e altre strategie di imballaggio. È ad esempio possibile impostare una regola in modo che i lavoratori non possano imballare righe di allocazione che rappresentano ordini cliente di diversi clienti nello stesso contenitore.

Per impostare un modello di versione del contenitore, effettua le operazioni seguenti.

1. Vai a **Gestione magazzino** \> **Impostazioni** \> **Contenitori** \> **Modello di versione contenitore**.
1. Crea un nuovo modello di versione del contenitore.
1. INei campi **Nome containerizzazione** e **Numero sequenza** immetti il nome del modello di containerizzazione e l'ordine abbinato alle righe di allocazione.

    > [!NOTE]
    > Il sistema applicherà il primo modello per cui la riga di allocazione soddisfa i criteri di query. È pertanto necessario inserire il modello con i criteri più specifici in cima all'elenco. Quanto più ampi sono i criteri, tanto maggiori sono le probabilità che una riga di allocazione soddisfi i criteri. Ciò può determinare l'assegnazione delle righe al contenitore sbagliato. Se necessario puoi selezionare **Sposta su** o **Sposta su** per cambiare la sequenza dei modelli.

1. Nel campo **ID gruppo di contenitori** seleziona il gruppo di contenitori da cui creare i contenitori.
1. Nel campo **Tipi di query di base** seleziona il tipo di query che determinerà cosa imballare e su cosa basare la query del filtro. Di seguito vengono illustrate le opzioni disponibili.

      - **Riga allocazione vendite**: imballa le righe di allocazione create per gli ordini cliente.
      - **Riga allocazione trasferimenti**: imballa le righe di allocazione create per gli ordini di trasferimento.
      - **Contenitore**: imballa un contenitore già creato dal processo di containerizzazione. Viene ad esempio utilizzato per l'annidamento dei contenitori.

        > [!NOTE]
        > Per utilizzare l'annidamento dei contenitori, devi rendere ripetibile il metodo di containerizzazione. Per ulteriori informazioni, vedi [Modelli di ciclo](wave-templates.md).

1. Nel campo **Codice del passaggio ciclo** della Scheda dettaglio **Generale** immetti l'identificatore univoco del metodo di elaborazione dei cicli che consente di collegare il modello di versione del contenitore ai passaggi di un modello di ciclo.
1. Seleziona la casella di controllo **Consenti prelievi condivisi** per consentire ai lavoratori di imballare gli articoli di un ordine di lavoro in contenitori separati. A questo scopo, è necessario che l'intera quantità stia nel contenitore. Viene sempre utilizzata l'unità di misura più grande della riga di allocazione.
1. Nel campo **Imballa per unità** seleziona l'unità di misura che rappresenterà il contenitore. Ad esempio, puoi indicare che una cassa è un contenitore. Se imballi in base all'unità di misura, non è possibile specificare un gruppo di contenitori poiché l'unità di misura è il contenitore.
1. Nel campo **Strategia di imballaggio contenitore** seleziona la strategia di imballaggio da utilizzare. Di seguito vengono illustrate le opzioni disponibili.

    > [!NOTE]
    > La strategia si applica solo alle righe di allocazione vendite e alle righe di allocazione trasferimento.

      - **Imballa in tutti i contenitori aperti**: il sistema valuta se la riga di allocazione potrà essere inserita in qualsiasi contenitore creato durante il ciclo di containerizzazione.
      - **Imballa solo nel contenitore corrente**: il sistema valuta solo se la riga di allocazione potrà essere inserita nell'ultimo contenitore creato.

    Per ulteriori informazioni ed esempi che mostrano come lavorare con le strategie di imballaggio dei contenitori, vedi [Strategie di imballaggio dei contenitori](container-packing-strategy-overview.md).

1. Per impostare le regole di imballaggio delle righe di allocazione in contenitori seleziona **Suddivisioni logica combinazione**. È ad esempio possibile creare una regola di permetterà ai lavoratori di imballare le righe di allocazione di due articoli diversi nello stesso contenitore. Per definire una regola di combinazione, completa i passaggi seguenti:

    1. Nella pagina **Suddivisioni logica combinazione** seleziona **Nuovo**.
    1. Nel campo **Tabella** seleziona la tabella contenente il campo da utilizzare come criterio per la suddivisione della logica di combinazione.
    1. Nel campo **Selezione campo** seleziona il campo da utilizzare come criterio per la suddivisione della logica di combinazione.
    1. Ripeti questi passaggi finché non sono stati aggiunti tutti i criteri relativi alla suddivisione della logica di combinazione.

    > [!NOTE]
    > Se usi la logica di combinazione, è consigliabile ordinare gli stessi campi nella query dei criteri di filtro. Ciò ridurrà il numero di contenitori creati.
