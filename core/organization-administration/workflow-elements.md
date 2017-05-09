---
title: Elementi flusso di lavoro
description: Questo articolo descrive i vari elementi che costituiscono un flusso di lavoro.
author: sericks007
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, IT Pro
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 56441
ms.assetid: de740262-6ffd-42b9-a325-540eae5cec94
ms.search.region: Global
ms.author: tjvass
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: ee20b567b402bf638a54f6394159f7f8a9f02da6
ms.lasthandoff: 03/31/2017


---

# <a name="workflow-elements"></a>Elementi flusso di lavoro

[!include[banner](../includes/banner.md)]


Questo articolo descrive i vari elementi che costituiscono un flusso di lavoro.

Un flusso di lavoro è costituito da elementi. Nelle sezioni indicate di seguito viene descritto ciascun tipo di elemento.

## <a name="tasks"></a>Attività
Un'*attività* è un'unità di lavoro che deve essere eseguita. Sono disponibili due tipi di attività che possono essere aggiunte a un flusso di lavoro: un'attività manuale o un'attività automatica.

### <a name="manual-task"></a>Attività manuale

Un'*attività manuale* è un'unità di lavoro che deve essere eseguita da un utente. Un flusso di lavoro relativo a una nota spese, ad esempio, può includere attività manuali che richiedono agli utenti assegnatari di completare le operazioni indicate di seguito:

-   Esaminare le ricevute inviate con una nota spese.
-   Chiamare il manager del dipendente.

### <a name="automated-task"></a>Attività automatica

Un'*attività automatica* è un'unità di lavoro che deve essere eseguita dal sistema. Non richiede interazione umana. Un flusso di lavoro relativo a un ordine cliente, ad esempio, può includere attività automatiche che prevedono il completamento delle operazioni indicate di seguito da parte del sistema:

-   Eseguire una verifica del credito.
-   Creare un record per il cliente, se non è già disponibile.

## <a name="approval-processes"></a>Processi di approvazione
Un *processo di approvazione* è costituito da vari passaggi separati. A ogni passaggio di approvazione, l'utente può eseguire le azioni seguenti:

-   Consente di approvare il documento.
-   Consente di rifiutare il documento.
-   Richiedere una modifica del documento.
-   Assegnare il documento a un altro utente per l'approvazione.

## <a name="lineitem-workflow-elements"></a>Elemento del flusso di lavoro voci
È possibile creare un flusso di lavoro per elaborare documenti o le voci in un documento. Si supponga ad esempio di aver creato un flusso di lavoro di approvazione per fogli presenze. Verrà fatto riferimento al flusso di lavoro come *flusso di lavoro del documento*. È possibile aggiungere un *flusso di lavoro voci* a tale flusso di lavoro del documento. Quando viene eseguito l'elemento voce, ogni voce nel documento viene inviata per l'elaborazione. È possibile decidere di elaborare tutte le voci tramite lo stesso flusso di lavoro voci oppure elaborare ogni singola voce tramite un flusso di lavoro voci diverso. Si supponga che un dipendente abbia inviato un foglio presenze analogo a quello illustrato nella figura indicata di seguito. ![Flusso di lavoro con voci](./media/workflow_lineitemworkflow.gif) In questo scenario è possibile creare i flussi di lavoro voci seguenti:

-   **Flusso di lavoro voci 1**: questo flusso di lavoro viene utilizzato per elaborare le voci con ID progetto 1111.
-   **Flusso di lavoro voci 2**: questo flusso di lavoro viene utilizzato per elaborare le voci con ID progetto 2222.
-   **Flusso di lavoro voci 3**: questo flusso di lavoro viene utilizzato per elaborare le voci con ID progetto 3333.

## <a name="flowcontrol-elements"></a>Elementi del controllo di flusso
Gli elementi indicati di seguito consentono di progettare flussi di lavoro con rami alternati o rami eseguiti contemporaneamente.

### <a name="manual-decision"></a>Decisione manuale

Una *decisione manuale* rappresenta un punto in cui un flusso di lavoro si suddivide in due rami. Un utente deve prendere una decisione che determinerà quale ramo del flusso di lavoro verrà utilizzato per elaborare il documento inviato.

### <a name="conditional-decision"></a>Decisione condizionale

Una *decisione condizionale* rappresenta anch'essa un punto in cui un flusso di lavoro si suddivide in due rami. Tuttavia, il sistema decide quale ramo del flusso di lavoro viene utilizzato per elaborare il documento inviato. A tale scopo, il sistema valuta il record per determinare se soddisfa le condizioni specificate.

### <a name="parallel-activity"></a>Attività parallela

Un'*attività parallela* è un elemento del flusso di lavoro che include due o più rami del flusso eseguiti contemporaneamente.

### <a name="subworkflow"></a>Flusso di lavoro secondario

Un *flusso di lavoro secondario* è un flusso di lavoro eseguito nel contesto di un altro flusso di lavoro.




