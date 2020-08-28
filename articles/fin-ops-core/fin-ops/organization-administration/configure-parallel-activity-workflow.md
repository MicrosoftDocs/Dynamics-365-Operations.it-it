---
title: Configurare le attività parallele in un flusso di lavoro
description: Per configurare un'attività parallela, attenersi alle procedure indicate di seguito nell'editor flusso di lavoro.
author: ChrisGarty
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 195753
ms.assetid: 6d0656df-b5af-4001-96e6-6f0fcc44d022
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 998ee559a092c4acd34a6df05e893bdbf4289099
ms.sourcegitcommit: e55efd2f62bf60f678108c09ad4701a76b20cc68
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/17/2020
ms.locfileid: "3698317"
---
# <a name="configure-parallel-activities-in-a-workflow"></a><span data-ttu-id="44dc0-103">Configurare le attività parallele in un flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="44dc0-103">Configure parallel activities in a workflow</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="44dc0-104">Per configurare un'attività parallela, attenersi alle procedure indicate di seguito nell'editor flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="44dc0-104">To configure a parallel activity, complete the following procedures in the workflow editor.</span></span>

<span data-ttu-id="44dc0-105">Un'attività parallela è costituita da rami del flusso di lavoro eseguiti contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="44dc0-105">A parallel activity consists of workflow branches that run at the same time.</span></span>

## <a name="name-a-parallel-activity"></a><span data-ttu-id="44dc0-106">Assegnare un nome a un'attività parallela</span><span class="sxs-lookup"><span data-stu-id="44dc0-106">Name a parallel activity</span></span>

<span data-ttu-id="44dc0-107">Per immettere un nome per un'attività parallela, effettuare le operazioni indicate di seguito.</span><span class="sxs-lookup"><span data-stu-id="44dc0-107">Follow these steps to enter a name for a parallel activity.</span></span>

1. <span data-ttu-id="44dc0-108">Fare clic con il pulsante destro del mouse sull'attività parallela e scegliere **Proprietà** per aprire il modulo **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="44dc0-108">Right-click the parallel activity, and then click **Properties** to open the **Properties** form.</span></span>
2. <span data-ttu-id="44dc0-109">Nel riquadro sinistro, fare clic sull'icona **Impostazioni di base**.</span><span class="sxs-lookup"><span data-stu-id="44dc0-109">In the left pane, click **Basic Settings**.</span></span>
3. <span data-ttu-id="44dc0-110">Nel campo **Nome** immettere un nome univoco per l'attività parallela.</span><span class="sxs-lookup"><span data-stu-id="44dc0-110">In the **Name** field, enter a unique name for the parallel activity.</span></span>
4. <span data-ttu-id="44dc0-111">Fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="44dc0-111">Click **Close**.</span></span>

## <a name="configure-the-branches-of-a-parallel-activity"></a><span data-ttu-id="44dc0-112">Configurare i rami di un'attività parallela</span><span class="sxs-lookup"><span data-stu-id="44dc0-112">Configure the branches of a parallel activity</span></span>

<span data-ttu-id="44dc0-113">Per aggiungere e configurare i rami di questa attività parallela, effettuare le operazioni indicate di seguito.</span><span class="sxs-lookup"><span data-stu-id="44dc0-113">Follow these steps to add and configure the branches of this parallel activity.</span></span>

1. <span data-ttu-id="44dc0-114">Fare doppio clic sull'attività parallela per visualizzarne i rami.</span><span class="sxs-lookup"><span data-stu-id="44dc0-114">Double-click the parallel activity to display the branches of the parallel activity.</span></span>
2. <span data-ttu-id="44dc0-115">Per aggiungere un ramo, trascinare l'elemento **Ramo** dall'area **Elementi flusso di lavoro** in un punto di inserimento nella canvas.</span><span class="sxs-lookup"><span data-stu-id="44dc0-115">To add a branch, drag the **Branch** element from the **Workflow elements** area to an insertion point on the canvas.</span></span> <span data-ttu-id="44dc0-116">Nella figura seguente viene illustrato un punto di inserimento.</span><span class="sxs-lookup"><span data-stu-id="44dc0-116">The following figure shows an insertion point.</span></span>

    ![Punto di inserimento](./media/workflow_insertionpoint.gif)

    > [!NOTE]
    > <span data-ttu-id="44dc0-118">L'ordine dei rami non è determinante, in quanto tutti i rami di un'attività parallela vengono eseguiti contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="44dc0-118">The order of the branches is not important because all the branches of a parallel activity run at the same time.</span></span>

3. <span data-ttu-id="44dc0-119">Per configurare ogni ramo, vedere [Configurare i rami paralleli in un flusso di lavoro](configure-parallel-branch-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="44dc0-119">To configure each branch, see [Configure parallel branches in a workflow](configure-parallel-branch-workflow.md).</span></span>
