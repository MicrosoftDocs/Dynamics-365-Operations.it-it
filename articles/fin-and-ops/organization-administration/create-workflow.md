---
title: Creare flusso di lavoro
description: In questo argomento viene illustrato come creare un flusso di lavoro.
author: sericks007
manager: AnnBe
ms.date: 11/03/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WorkflowSelectTemplateRnr, WorkflowTableListPageRnr
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 195583
ms.assetid: 836ddd01-cc34-45c3-a4b0-20647357dbc6
ms.search.region: Global
ms.author: donaldc
ms.search.validFrom: 2016-08-30
ms.dyn365.ops.version: Platform update 2
ms.openlocfilehash: 7d4a3c5e12b226a7d801d8db9abcbd15738c1ce0
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2019
ms.locfileid: "353358"
---
# <a name="create-workflows"></a>Creare flusso di lavoro

[!include [banner](../includes/banner.md)]

In questo argomento viene illustrato come creare un flusso di lavoro.

## <a name="open-the-workflow-editor"></a>Aprire l'editor flusso di lavoro

Il modulo Microsoft Dynamics 365 for Finance and Operations in uso determina i tipi di flusso di lavoro che è possibile creare. Per selezionare il tipo di flusso di lavoro da creare e aprire l'editor flusso di lavoro, eseguire i passaggi indicati di seguito.

1. Aprire il modulo per il quale si desidera creare un nuovo flusso di lavoro. Ad esempio, per creare un flusso di lavoro per le richieste di acquisto, fare clic su **Approvvigionamento**.
2. Fare clic su **Impostazione** &gt; **\[Nome modulo\] - flussi di lavoro**.
3. Nella pagina elenco visualizzata, nel riquadro azioni, fare clic su **Nuovo**.
4. Nella pagina **Crea flusso di lavoro**, selezionare il tipo di flusso di lavoro da creare e fare clic su **Crea flusso di lavoro**. Viene visualizzato l'editor flusso di lavoro. Per progettare il flusso di lavoro, è ora possibile usare le procedure indicate di seguito.

## <a name="drag-workflow-elements-onto-the-canvas"></a>Trascinare gli elementi del flusso di lavoro nella canvas

L'area **Elementi flusso di lavoro** dell'editor flusso di lavoro contiene gli elementi che è possibile aggiungere al flusso. Per aggiungere elementi al flusso di lavoro, trascinarli nella canvas.

## <a name="connect-the-elements"></a>Connettere gli elementi

Per connettere un elemento del flusso di lavoro a un altro, tenere premuto il puntatore su un elemento finché non verranno visualizzati punti di connessione. Fare clic su un punto di connessione e trascinarlo su un altro elemento. Verificare di connettere tutti gli elementi.

## <a name="configure-the-properties-of-the-workflow"></a>Configurare le proprietà del flusso di lavoro

Per configurare le proprietà del flusso di lavoro, eseguire i passaggi indicati di seguito.

1. Per verificare che non sia selezionato alcun elemento del flusso di lavoro, fare clic sulla canvas.
2. Fare clic su **Proprietà** per aprire la pagina **Proprietà** per il flusso di lavoro.
3. Seguire le procedure nell'argomento [Configurare le proprietà di un flusso di lavoro](configure-workflow-properties.md).

## <a name="configure-the-elements-of-the-workflow"></a>Configurare gli elementi del flusso di lavoro

Configurare ogni elemento trascinato nella canvas. Per ulteriori informazioni su come configurare ciascun elemento del flusso di lavoro, vedere i seguenti argomenti:

- [Configurare un'attività manuale](configure-manual-task-workflow.md)
- [Configurare un'attività automatica](configure-automated-task-workflow.md)
- [Configurare un processo di approvazione](configure-approval-process-workflow.md)
- [Configurare un passaggio di approvazione](configure-approval-step-workflow.md)
- [Configurare una decisione manuale](configure-manual-decision-workflow.md)
- [Configurare una decisione condizionale](configure-conditional-decision-workflow.md)
- [Configurare un'attività parallela](configure-parallel-activity-workflow.md)
- [Configurare un ramo parallelo](configure-parallel-branch-workflow.md)
- [Configurare un flusso di lavoro voci](configure-line-item-workflow.md)

## <a name="resolve-any-errors-or-warnings"></a>Risolvere eventuali errori o avvisi

Nel riquadro **Errori e avvisi** situato nella parte inferiore dell'editor flusso di lavoro vengono visualizzati i messaggi generati per il flusso. Per individuare l'elemento in cui si è verificato un errore o un avviso, fare doppio clic sul relativo messaggio. Per rendere il flusso di lavoro attivo, è necessario risolvere tutti gli errori e gli avvisi.

## <a name="save-and-activate-the-workflow"></a>Salvare e attivare il flusso di lavoro

Per salvare e attivare il flusso di lavoro, attenersi alla procedura indicata di seguito.

1. Fare clic su **Salva e chiudi** per chiudere l'editor flusso di lavoro e aprire la pagina **Salva flusso di lavoro**.
2. Immettere commenti sulle modifiche apportate al flusso di lavoro, quindi fare clic su **OK**.
3. Se sono stati risolti tutti gli errori e gli avvisi, verrà visualizzata la pagina **Attiva flusso di lavoro**. Consente di selezionare una delle opzioni indicate di seguito.

    - Per attivare questa versione del flusso di lavoro, fare clic su **Attiva la nuova versione**. Quando un flusso di lavoro è attivo, l'utente è in grado di inviare documenti per l'elaborazione.
    - Se non si desidera attivare questa versione, fare clic su **Non attivare la nuova versione**. Sarà possibile attivare il flusso di lavoro in un secondo momento.
