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
ms.openlocfilehash: dd9d40bb331b9e024617c8be55330dfce8ba1cc6
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2019
ms.locfileid: "309474"
---
# <a name="assign-a-product-lifecycle-state-to-a-released-product-master"></a><span data-ttu-id="1c05c-103">Assegnare uno stato del ciclo di vita prodotto a una rappresentazione generale prodotto rilasciato</span><span class="sxs-lookup"><span data-stu-id="1c05c-103">Assign a product lifecycle state to a released product master</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="1c05c-104">In questa procedura viene illustrato come assegnare uno stato del ciclo di vita del prodotto a una rappresentazione generale prodotto rilasciato e alle varianti.</span><span class="sxs-lookup"><span data-stu-id="1c05c-104">This procedure shows how to assign a product lifecycle state to a released product master and its variants.</span></span> <span data-ttu-id="1c05c-105">Prerequisito: è necessario esegure la guida di attività "Creare un nuovo stato del ciclo di vita prodotto" per verificare di avere creato almeno uno stato del ciclo di vita del prodotto prima di poter eseguire la guida attività.</span><span class="sxs-lookup"><span data-stu-id="1c05c-105">Prerequisite: You need to play the task guide "Create a new product lifecycle state" first to make sure that you have at least one product lifecycle state created before you can play this task guide.</span></span>


## <a name="find-a-released-product-master"></a><span data-ttu-id="1c05c-106">Trovare una rappresentazione generale prodotto rilasciata</span><span class="sxs-lookup"><span data-stu-id="1c05c-106">Find a released product master</span></span>
1. <span data-ttu-id="1c05c-107">Fare clic su Gestione informazioni sul prodotto > Prodotti > Prodotti rilasciati.</span><span class="sxs-lookup"><span data-stu-id="1c05c-107">Go to Product information management > Products > Released products.</span></span>
2. <span data-ttu-id="1c05c-108">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="1c05c-108">In the list, find and select the desired record.</span></span>

> [!NOTE]
> <span data-ttu-id="1c05c-109">Una rappresentazione generale prodotto include la rappresentazione generale del prodotto.</span><span class="sxs-lookup"><span data-stu-id="1c05c-109">A product master has the Product subtype Product master.</span></span>  

## <a name="update-the-lifecycle-state"></a><span data-ttu-id="1c05c-110">Aggiornare lo stato del ciclo di vita</span><span class="sxs-lookup"><span data-stu-id="1c05c-110">Update the lifecycle state</span></span>
1. <span data-ttu-id="1c05c-111">Fare clic su Modifica.</span><span class="sxs-lookup"><span data-stu-id="1c05c-111">Click Edit.</span></span>
2. <span data-ttu-id="1c05c-112">Nel campo Stato del ciclo di vita prodotto immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="1c05c-112">In the Product lifecycle state field, enter or select a value.</span></span>
3. <span data-ttu-id="1c05c-113">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="1c05c-113">Click Save.</span></span>
4. <span data-ttu-id="1c05c-114">Fare clic su Sì.</span><span class="sxs-lookup"><span data-stu-id="1c05c-114">Click Yes.</span></span>

> [!NOTE]
> <span data-ttu-id="1c05c-115">Se è stato selezionato Sì, tutte le varianti prodotto rilasciate correlati con lo stesso stato originale della rappresentazione generale prodotto rilasciata verranno aggiornate sullo stato del ciclo di vita di prodotti.</span><span class="sxs-lookup"><span data-stu-id="1c05c-115">If Yes is selected, all the related released product variants that have the same original status as the released product master are also updated to the new product lifecycle state.</span></span> <span data-ttu-id="1c05c-116">Se è stato selezionato No, tutte le varianti mantengono lo stato corrente.</span><span class="sxs-lookup"><span data-stu-id="1c05c-116">If No is selected, all variants keep their actual state.</span></span> <span data-ttu-id="1c05c-117">Le varianti con uno stato del ciclo di vita del prodotto diverso dalla rappresentazione generale prodotto rilasciato non vengono aggiornate.</span><span class="sxs-lookup"><span data-stu-id="1c05c-117">Variants that have a different product lifecycle state from the released product master are not updated.</span></span>  

## <a name="verify-the-lifecycle-state-of-the-variants"></a><span data-ttu-id="1c05c-118">Verificare lo stato del ciclo di vita delle varianti</span><span class="sxs-lookup"><span data-stu-id="1c05c-118">Verify the lifecycle state of the variants</span></span>
1. <span data-ttu-id="1c05c-119">Fare clic su Varianti prodotti rilasciati.</span><span class="sxs-lookup"><span data-stu-id="1c05c-119">Click Released product variants.</span></span>

> [!NOTE]
> <span data-ttu-id="1c05c-120">Tenere presente che tutte le varianti hanno ereditato lo stato selezionato del ciclo di vita della rappresentazione generale prodotto rilasciato.</span><span class="sxs-lookup"><span data-stu-id="1c05c-120">Note that all variants have inherited the selected lifecycle state from the released product master.</span></span>  

2. <span data-ttu-id="1c05c-121">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="1c05c-121">In the list, mark the selected row.</span></span>
3. <span data-ttu-id="1c05c-122">Nel campo Stato del ciclo di vita prodotto immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="1c05c-122">In the Product lifecycle state field, enter or select a value.</span></span>

