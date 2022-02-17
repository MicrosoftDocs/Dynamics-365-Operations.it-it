---
title: Configurare le attività parallele in un flusso di lavoro
description: Per configurare un'attività parallela, attenersi alle procedure indicate di seguito nell'editor flusso di lavoro.
author: ChrisGarty
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.custom: 195753
ms.assetid: 6d0656df-b5af-4001-96e6-6f0fcc44d022
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 054d62e2ff094aee987f8c6e04e2f2e173da633d
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/31/2022
ms.locfileid: "8068765"
---
# <a name="configure-parallel-activities-in-a-workflow"></a>Configurare le attività parallele in un flusso di lavoro

[!include [banner](../includes/banner.md)]


[!INCLUDE [PEAP](../../../includes/peap-1.md)]

Per configurare un'attività parallela, attenersi alle procedure indicate di seguito nell'editor flusso di lavoro.

Un'attività parallela è costituita da rami del flusso di lavoro eseguiti contemporaneamente.

## <a name="name-a-parallel-activity"></a>Assegnare un nome a un'attività parallela

Per immettere un nome per un'attività parallela, effettuare le operazioni indicate di seguito.

1. Fare clic con il pulsante destro del mouse sull'attività parallela e scegliere **Proprietà** per aprire il modulo **Proprietà**.
2. Nel riquadro sinistro, fare clic sull'icona **Impostazioni di base**.
3. Nel campo **Nome** immettere un nome univoco per l'attività parallela.
4. Fare clic su **Chiudi**.

## <a name="configure-the-branches-of-a-parallel-activity"></a>Configurare i rami di un'attività parallela

Per aggiungere e configurare i rami di questa attività parallela, effettuare le operazioni indicate di seguito.

1. Fare doppio clic sull'attività parallela per visualizzarne i rami.
2. Per aggiungere un ramo, trascinare l'elemento **Ramo** dall'area **Elementi flusso di lavoro** in un punto di inserimento nella canvas. Nella figura seguente viene illustrato un punto di inserimento.

    ![Punto di inserimento.](./media/workflow_insertionpoint.gif)

    > [!NOTE]
    > L'ordine dei rami non è determinante, in quanto tutti i rami di un'attività parallela vengono eseguiti contemporaneamente.

3. Per configurare ogni ramo, vedere [Configurare i rami paralleli in un flusso di lavoro](configure-parallel-branch-workflow.md).


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]