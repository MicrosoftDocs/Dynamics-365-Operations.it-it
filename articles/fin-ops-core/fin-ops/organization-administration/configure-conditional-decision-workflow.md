---
title: Configurare le decisioni condizionali in un flusso di lavoro
description: Per configurare le proprietà di una decisione condizionale, attenersi alla procedura indicata di seguito.
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
ms.custom: 195703
ms.assetid: cd5554a4-210c-4c20-a7d3-4b1563c2b5df
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7a953d4e781db42834f0bc8daf80040c39ea5b5c
ms.sourcegitcommit: e55efd2f62bf60f678108c09ad4701a76b20cc68
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/17/2020
ms.locfileid: "3698122"
---
# <a name="configure-conditional-decisions-in-a-workflow"></a><span data-ttu-id="4884a-103">Configurare le decisioni condizionali in un flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="4884a-103">Configure conditional decisions in a workflow</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="4884a-104">Per configurare le proprietà di una decisione condizionale, attenersi alla procedura indicata di seguito.</span><span class="sxs-lookup"><span data-stu-id="4884a-104">Use the following procedure to configure the properties of a conditional decision.</span></span>

<span data-ttu-id="4884a-105">Una decisione condizionale rappresenta un punto nel quale un flusso di lavoro si divide in due rami.</span><span class="sxs-lookup"><span data-stu-id="4884a-105">A conditional decision is a point at which a workflow divides into two branches.</span></span> <span data-ttu-id="4884a-106">Per configurare una decisione condizionale, nell'editor flusso di lavoro fare clic con il pulsante destro del mouse sulla decisione e scegliere **Proprietà** per aprire il modulo **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="4884a-106">To configure a conditional decision, in the workflow editor, right-click the conditional decision, and then click **Properties** to open the **Properties** form.</span></span>

## <a name="name-a-decision"></a><span data-ttu-id="4884a-107">Assegnare un nome a una decisione</span><span class="sxs-lookup"><span data-stu-id="4884a-107">Name a decision</span></span>

<span data-ttu-id="4884a-108">Per immettere un nome per una decisione condizionale, effettuare le operazioni indicate di seguito.</span><span class="sxs-lookup"><span data-stu-id="4884a-108">Follow these steps to enter a name for a conditional decision.</span></span>

1. <span data-ttu-id="4884a-109">Nel riquadro sinistro, fare clic sull'icona **Impostazioni di base**.</span><span class="sxs-lookup"><span data-stu-id="4884a-109">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="4884a-110">Nel campo **Nome** immettere un nome univoco per la decisione condizionale.</span><span class="sxs-lookup"><span data-stu-id="4884a-110">In the **Name** field, enter a unique name for the conditional decision.</span></span>

## <a name="set-conditions"></a><span data-ttu-id="4884a-111"> Impostare condizioni</span><span class="sxs-lookup"><span data-stu-id="4884a-111">Set conditions</span></span>

<span data-ttu-id="4884a-112">Il sistema determina quale ramo utilizzare valutando il documento inviato per determinare se soddisfa le condizioni specifiche.</span><span class="sxs-lookup"><span data-stu-id="4884a-112">The system determines which branch is used by evaluating the submitted document to determine whether it meets specific conditions.</span></span>

1. <span data-ttu-id="4884a-113">Nel riquadro sinistro, fare clic sull'icona **Impostazioni di base**.</span><span class="sxs-lookup"><span data-stu-id="4884a-113">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="4884a-114">Fare clic su **Aggiungi condizione**.</span><span class="sxs-lookup"><span data-stu-id="4884a-114">Click **Add condition**.</span></span>
3. <span data-ttu-id="4884a-115">Immettere una condizione.</span><span class="sxs-lookup"><span data-stu-id="4884a-115">Enter a condition.</span></span>
4. <span data-ttu-id="4884a-116">Immettere altre condizioni, se necessario.</span><span class="sxs-lookup"><span data-stu-id="4884a-116">Enter additional conditions, if they are required.</span></span>
5. <span data-ttu-id="4884a-117">Per verificare la correttezza della configurazione delle condizioni immesse, eseguire i passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="4884a-117">To verify that the conditions that you entered are configured correctly, complete the following steps:</span></span>

    1. <span data-ttu-id="4884a-118">Fare clic su **Test** per aprire il modulo **Test condizione flusso di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="4884a-118">Click **Test** to open the **Test workflow condition** form.</span></span>
    2. <span data-ttu-id="4884a-119">Selezionare un record nell'area **Convalida condizione** del modulo.</span><span class="sxs-lookup"><span data-stu-id="4884a-119">Select a record in the **Validate condition** area of the form.</span></span>
    3. <span data-ttu-id="4884a-120">Fare clic su **Test**.</span><span class="sxs-lookup"><span data-stu-id="4884a-120">Click **Test**.</span></span> <span data-ttu-id="4884a-121">Il sistema valuta il record per determinare se soddisfa le condizioni definite.</span><span class="sxs-lookup"><span data-stu-id="4884a-121">The system evaluates the record to determine whether it meets the conditions that you defined.</span></span>
    4. <span data-ttu-id="4884a-122">Fare clic su **OK** o **Annulla** per tornare al modulo **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="4884a-122">Click **OK** or **Cancel** to return to the **Properties** form.</span></span>
