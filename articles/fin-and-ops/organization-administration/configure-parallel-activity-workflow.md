---
title: "Configurare un'attività parallela in un flusso di lavoro"
description: "Per configurare un'attività parallela, attenersi alle procedure indicate di seguito nell'editor flusso di lavoro."
author: sericks007
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 195753
ms.assetid: 6d0656df-b5af-4001-96e6-6f0fcc44d022
ms.search.region: Global
ms.author: donaldc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 5473327c0665c9183746eb8125c7a368fbedc21e
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---

# <a name="configure-a-parallel-activity-in-a-workflow"></a>Configurare un'attività parallela in un flusso di lavoro

[!include[banner](../includes/banner.md)]


Per configurare un'attività parallela, attenersi alle procedure indicate di seguito nell'editor flusso di lavoro.

Un'attività parallela è costituita da rami del flusso di lavoro eseguiti contemporaneamente.

## <a name="name-a-parallel-activity"></a>Assegnare un nome a un'attività parallela
Per immettere un nome per un'attività parallela, effettuare le operazioni indicate di seguito.
1.  Fare clic con il pulsante destro del mouse sull'attività parallela e scegliere **Proprietà** per aprire il modulo **Proprietà**.
2.  Nel riquadro sinistro, fare clic sull'icona **Impostazioni di base**.
3.  Nel campo **Nome** immettere un nome univoco per l'attività parallela.
4.  Fare clic su **Chiudi**.

## <a name="configure-the-branches-of-a-parallel-activity"></a>Configurare i rami di un'attività parallela
Per aggiungere e configurare i rami di questa attività parallela, effettuare le operazioni indicate di seguito.
1.  Fare doppio clic sull'attività parallela per visualizzarne i rami.
2.  Per aggiungere un ramo, trascinare l'elemento **Ramo** dall'area **Elementi flusso di lavoro** in un punto di inserimento nella canvas. Nella figura seguente viene illustrato un punto di inserimento.![Punto di inserimento](./media/workflow_insertionpoint.gif)
    | **Nota**                                                                                                         |
    |------------------------------------------------------------------------------------------------------------------|
    | L'ordine dei rami non è determinante, in quanto tutti i rami di un'attività parallela vengono eseguiti contemporaneamente. |

3.  Per configurare ogni ramo, vedere [Configurare un ramo parallelo](configure-parallel-branch-workflow.md).






