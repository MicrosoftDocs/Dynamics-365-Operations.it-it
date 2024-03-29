---
title: Panoramica della creazione di flussi di lavoro
description: In questo articolo viene illustrato come creare un flusso di lavoro.
author: ChrisGarty
ms.date: 07/25/2019
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: WorkflowSelectTemplateRnr, WorkflowTableListPageRnr
audience: Application User, IT Pro
ms.reviewer: sericks
ms.custom:
- "195583"
- intro-internal
ms.assetid: 836ddd01-cc34-45c3-a4b0-20647357dbc6
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-08-30
ms.dyn365.ops.version: Platform update 2
ms.openlocfilehash: 1343061ba06d13e68a98b05c013867af0a4d07a6
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8864488"
---
# <a name="create-workflows-overview"></a>Panoramica della creazione di flussi di lavoro

[!include [banner](../includes/banner.md)]


[!INCLUDE [PEAP](../../../includes/peap-1.md)]

In questo articolo viene illustrato come creare un flusso di lavoro.

## <a name="open-the-workflow-editor"></a>Aprire l'editor flusso di lavoro

Il modulo in uso determina i tipi di flusso di lavoro che è possibile creare. Per selezionare il tipo di flusso di lavoro da creare e aprire l'editor flusso di lavoro, eseguire i passaggi indicati di seguito.

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
3. Segui le procedure nell'articolo [Configurare le proprietà del flusso di lavoro](configure-workflow-properties.md).

## <a name="configure-the-elements-of-the-workflow"></a>Configurare gli elementi del flusso di lavoro

Configurare ogni elemento trascinato nella canvas. Per ulteriori informazioni su come configurare ciascun elemento del flusso di lavoro, vedere i seguenti argomenti:

- [Configurare le attività manuali in un flusso di lavoro](configure-manual-task-workflow.md)
- [Configurare le attività automatiche in un flusso di lavoro](configure-automated-task-workflow.md)
- [Configurare i processi di approvazione in un flusso di lavoro](configure-approval-process-workflow.md)
- [Configurare i passaggi di approvazione in un flusso di lavoro](configure-approval-step-workflow.md)
- [Configurare le decisioni manuali in un flusso di lavoro](configure-manual-decision-workflow.md)
- [Configurare le decisioni condizionali in un flusso di lavoro](configure-conditional-decision-workflow.md)
- [Configurare i rami paralleli in un flusso di lavoro](configure-parallel-activity-workflow.md)
- [Configurare un ramo parallelo](configure-parallel-branch-workflow.md)
- [Configurare flussi di lavoro voci](configure-line-item-workflow.md)

## <a name="resolve-any-errors-or-warnings"></a>Risolvere eventuali errori o avvisi

Nel riquadro **Errori e avvisi** situato nella parte inferiore dell'editor flusso di lavoro vengono visualizzati i messaggi generati per il flusso. Per individuare l'elemento in cui si è verificato un errore o un avviso, fare doppio clic sul relativo messaggio. Per rendere il flusso di lavoro attivo, è necessario risolvere tutti gli errori e gli avvisi.

## <a name="save-and-activate-the-workflow"></a>Salvare e attivare il flusso di lavoro

Per salvare e attivare il flusso di lavoro, attenersi alla procedura indicata di seguito.

1. Fare clic su **Salva e chiudi** per chiudere l'editor flusso di lavoro e aprire la pagina **Salva flusso di lavoro**.
2. Immettere commenti sulle modifiche apportate al flusso di lavoro, quindi fare clic su **OK**.
3. Se sono stati risolti tutti gli errori e gli avvisi, verrà visualizzata la pagina **Attiva flusso di lavoro**. Consente di selezionare una delle opzioni indicate di seguito.

    - Per attivare questa versione del flusso di lavoro, fare clic su **Attiva la nuova versione**. Quando un flusso di lavoro è attivo, l'utente è in grado di inviare documenti per l'elaborazione.
    - Se non si desidera attivare questa versione, fare clic su **Non attivare la nuova versione**. Sarà possibile attivare il flusso di lavoro in un secondo momento.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]