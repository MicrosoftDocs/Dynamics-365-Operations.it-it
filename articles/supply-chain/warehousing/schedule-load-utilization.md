---
title: Programma spazio esterno utilizzato
description: In questo argomento viene descritto come impostare e programmare il carico per un magazzino.
author: MarkusFogelberg
ms.date: 05/26/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WMSSpaceUtilSetup
audience: Application User
ms.reviewer: kamaybac
ms.custom: 269384
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f4d259fd6c27ac96475c49c431e347ca0c03a9e7
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5817319"
---
# <a name="schedule-load-utilization"></a>Programma spazio esterno utilizzato

[!include[banner](../includes/banner.md)]

È possibile programmare l'utilizzo del carico per i tipi di ubicazione selezionati, nonché proiettare l'utilizzo del carico corrente e futuro. Il carico può essere proiettato per uno o più siti, per le unità di carico (magazzino o area) o per una combinazione di area e magazzino.

## <a name="schedule-and-view-the-load-for-a-warehouse-or-site"></a>Programmare e visualizzare il carico per un magazzino o sito

Per programmare il carico di siti, magazzini o aree, è necessario creare un'impostazione di utilizzo dello spazio e associarla a un piano generale.

Nell'impostazione di utilizzo dello spazio, si utilizzano i tipi di posizione, quali **Ubicazione di stoccaggio** e **Ubicazione di prelievo**, per specificare come proiettare l'utilizzo dello spazio. È inoltre possibile specificare una modalità di carico di immagazzinamento, ad esempio **Zona**.

La proiezione dell'utilizzo dello spazio futuro si basa sulle informazioni che vengono calcolate nel piano generale associato. Nei piani generali è prevista la pianificazione delle risorse per gli ordini in ingresso e in uscita per la produzione e le operazioni. La proiezione dello spazio disponibile si basa sulla relazione tra l'impostazione di utilizzo dello spazio e il piano generale selezionato.

Utilizzando la modalità di carico di immagazzinamento selezionata nell'impostazione di utilizzo dello spazio, è possibile specificare se il carico deve essere proiettato per ciascun magazzino o per ciascuna area o se le proiezioni devono includere informazioni relative a magazzini e aree. È inoltre necessario specificare se le ubicazioni bloccate devono essere escluse dal calcolo dell'utilizzo del carico.

È possibile proiettare l'utilizzo dello generando il report **Spazio esterno di magazzino utilizzato**. Quando si genera questo report, è possibile specificare se l'utilizzo del carico deve essere proiettato per ogni sito, tra più siti o per l'unità di carico selezionata, ad esempio l'area o il magazzino.

### <a name="create-a-space-utilization-setup-for-a-warehouse"></a>Creare un'impostazione di utilizzo dello spazio per un magazzino

1. Selezionare **Gestione articoli** \> **Impostazione** \> **Monitoraggio di magazzino** \> **Utilizzo di spazio**.
2. Selezionare **Nuovo** per creare un'impostazione di utilizzo dello spazio. Specificare un ID e un nome per la nuova impostazione.
3. Nel campo **Modalità di carico di immagazzinamento** selezionare se la panoramica di utilizzo dello spazio deve visualizzare informazioni in base al magazzino, all'area o al magazzino e all'area.
4. Impostare l'opzione **Escludi ubicazioni bloccate** su **Sì** per escludere le ubicazioni di magazzino bloccate dal calcolo dello spazio disponibile. È possibile bloccare un'ubicazione di magazzino per l'ingresso e l'uscita specificando una causa di bloccaggio per l'ubicazione nei campi **Entrata bloccata** o **Uscita bloccata** nella Scheda dettaglio **Altro** della pagina **Ubicazioni di magazzino**.
5. Nella Scheda dettaglio **Tipo di ubicazione** selezionare i tipi di ubicazione da includere nel calcolo dell'utilizzo dello spazio. È necessario selezionare almeno un tipo di ubicazione per la proiezione.

### <a name="associate-a-space-utilization-setup-with-a-master-plan"></a>Associare un'impostazione di utilizzo dello spazio a un piano generale

1. Selezionare **Gestione articoli** \> **Attività periodiche** \> **Programma spazio esterno utilizzato**.
2. Nel campo **Piano generale** selezionare un piano generale.
3. Nel campo **Numero di giorni** specificare il numero di giorni da includere nella proiezione dei carichi di lavoro correnti e futuri.
4. Nel campo **Utilizzo dello spazio** selezionare l'impostazione di utilizzo dello spazio da utilizzare per la proiezione dei carichi di lavoro correnti e futuri.

### <a name="specify-the-load-utilization-projection-and-view-information"></a>Specificare la proiezione di utilizzo del carico e visualizzare le informazioni

1. Selezionare **Gestione inventario** \> **Richieste di informazioni e report** \> **Report inventario fisico** \> **Spazio esterno di magazzino utilizzato**.
2. Nel campo **Mostra per** selezionare il livello di proiezione di utilizzo dello spazio:

    - **Sito**, per proiettare l'utilizzo dello spazio per ogni sito. La proiezione è utile se, ad esempio, si desidera visualizzare tutti i magazzini per un sito in modo che sia possibile bilanciare l'utilizzo dello spazio tra i magazzini.
    - **Unità di carico**, per proiettare l'utilizzo dello spazio per aree o magazzini. Lo spazio disponibile viene quindi proiettato in base al valore selezionato nel campo **Modalità di carico di immagazzinamento** della pagina **Utilizzo dello spazio** alla creazione dell'impostazione di utilizzo dello spazio.

3. Eseguire uno dei passaggi riportati di seguito, in base al valore selezionato nel passaggio precedente:

    - Se è stato selezionato **Sito** nel campo **Mostra per**, il campo **Sito** è disponibile. Selezionare uno o più siti da includere nella proiezione.
    - Se è stato selezionato **Unità di carico** nel campo **Mostra per**, il campo **Unità di carico** è disponibile. Selezionare l'unità di carico.

4. Nel campo **Tipo di carico** selezionare **Volume** o **Peso** per indicare l'unità operativa di magazzino per la proiezione dello spazio.
5. Nel campo **Impostazioni di utilizzo dello spazio** selezionare l'impostazione di utilizzo dello spazio su cui deve essere basata la proiezione.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]