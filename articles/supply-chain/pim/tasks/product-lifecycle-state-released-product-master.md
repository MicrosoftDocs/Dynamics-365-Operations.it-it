---
title: Assegnare uno stato del ciclo di vita prodotto a una rappresentazione generale prodotto rilasciato
description: In questa procedura viene illustrato come assegnare uno stato del ciclo di vita del prodotto a una rappresentazione generale prodotto rilasciato e alle varianti.
author: cvocph
manager: AnnBe
ms.date: 12/05/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: conradv
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 02d7e0b6f81011519b0e1bd09f8aea0c4170ffd0
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/18/2020
ms.locfileid: "3149881"
---
# <a name="assign-a-product-lifecycle-state-to-a-released-product-master"></a><span data-ttu-id="59e80-103">Assegnare uno stato del ciclo di vita prodotto a una rappresentazione generale prodotto rilasciato</span><span class="sxs-lookup"><span data-stu-id="59e80-103">Assign a product lifecycle state to a released product master</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="59e80-104">In questa procedura viene illustrato come assegnare uno stato del ciclo di vita del prodotto a una rappresentazione generale prodotto rilasciato e alle varianti.</span><span class="sxs-lookup"><span data-stu-id="59e80-104">This procedure shows how to assign a product lifecycle state to a released product master and its variants.</span></span> <span data-ttu-id="59e80-105">Prerequisito: è necessario esegure la guida di attività "Creare un nuovo stato del ciclo di vita prodotto" per verificare di avere creato almeno uno stato del ciclo di vita del prodotto prima di poter eseguire la guida attività.</span><span class="sxs-lookup"><span data-stu-id="59e80-105">Prerequisite: You need to play the task guide "Create a new product lifecycle state" first to make sure that you have at least one product lifecycle state created before you can play this task guide.</span></span>


## <a name="find-a-released-product-master"></a><span data-ttu-id="59e80-106">Trovare una rappresentazione generale prodotto rilasciata</span><span class="sxs-lookup"><span data-stu-id="59e80-106">Find a released product master</span></span>
1. <span data-ttu-id="59e80-107">Fare clic su Gestione informazioni sul prodotto > Prodotti > Prodotti rilasciati.</span><span class="sxs-lookup"><span data-stu-id="59e80-107">Go to Product information management > Products > Released products.</span></span>
2. <span data-ttu-id="59e80-108">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="59e80-108">In the list, find and select the desired record.</span></span>

> [!NOTE]
> <span data-ttu-id="59e80-109">Una rappresentazione generale prodotto include la rappresentazione generale del prodotto.</span><span class="sxs-lookup"><span data-stu-id="59e80-109">A product master has the Product subtype Product master.</span></span>  

## <a name="update-the-lifecycle-state"></a><span data-ttu-id="59e80-110">Aggiornare lo stato del ciclo di vita</span><span class="sxs-lookup"><span data-stu-id="59e80-110">Update the lifecycle state</span></span>
1. <span data-ttu-id="59e80-111">Fare clic su Modifica.</span><span class="sxs-lookup"><span data-stu-id="59e80-111">Click Edit.</span></span>
2. <span data-ttu-id="59e80-112">Nel campo Stato del ciclo di vita prodotto immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="59e80-112">In the Product lifecycle state field, enter or select a value.</span></span>
3. <span data-ttu-id="59e80-113">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="59e80-113">Click Save.</span></span>
4. <span data-ttu-id="59e80-114">Fare clic su Sì.</span><span class="sxs-lookup"><span data-stu-id="59e80-114">Click Yes.</span></span>

> [!NOTE]
> <span data-ttu-id="59e80-115">Se è stato selezionato Sì, tutte le varianti prodotto rilasciate correlati con lo stesso stato originale della rappresentazione generale prodotto rilasciata verranno aggiornate sullo stato del ciclo di vita di prodotti.</span><span class="sxs-lookup"><span data-stu-id="59e80-115">If Yes is selected, all the related released product variants that have the same original status as the released product master are also updated to the new product lifecycle state.</span></span> <span data-ttu-id="59e80-116">Se è stato selezionato No, tutte le varianti mantengono lo stato corrente.</span><span class="sxs-lookup"><span data-stu-id="59e80-116">If No is selected, all variants keep their actual state.</span></span> <span data-ttu-id="59e80-117">Le varianti con uno stato del ciclo di vita del prodotto diverso dalla rappresentazione generale prodotto rilasciato non vengono aggiornate.</span><span class="sxs-lookup"><span data-stu-id="59e80-117">Variants that have a different product lifecycle state from the released product master are not updated.</span></span>  

## <a name="verify-the-lifecycle-state-of-the-variants"></a><span data-ttu-id="59e80-118">Verificare lo stato del ciclo di vita delle varianti</span><span class="sxs-lookup"><span data-stu-id="59e80-118">Verify the lifecycle state of the variants</span></span>
1. <span data-ttu-id="59e80-119">Fare clic su Varianti prodotti rilasciati.</span><span class="sxs-lookup"><span data-stu-id="59e80-119">Click Released product variants.</span></span>

> [!NOTE]
> <span data-ttu-id="59e80-120">Tenere presente che tutte le varianti hanno ereditato lo stato selezionato del ciclo di vita della rappresentazione generale prodotto rilasciato.</span><span class="sxs-lookup"><span data-stu-id="59e80-120">Note that all variants have inherited the selected lifecycle state from the released product master.</span></span>  

2. <span data-ttu-id="59e80-121">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="59e80-121">In the list, mark the selected row.</span></span>
3. <span data-ttu-id="59e80-122">Nel campo Stato del ciclo di vita prodotto immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="59e80-122">In the Product lifecycle state field, enter or select a value.</span></span>

