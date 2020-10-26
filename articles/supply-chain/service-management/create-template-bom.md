---
title: Creare una DBA modello
description: È possibile creare una DBA modello utilizzando vari metodi.
author: ShylaThompson
manager: tfehr
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMATemplateBOMTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b2e06283f3b95c5ff6b4376bba63cf5a42d5feeb
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/10/2020
ms.locfileid: "3981819"
---
# <a name="create-a-template-bom"></a><span data-ttu-id="44a52-103">Creare una DBA modello</span><span class="sxs-lookup"><span data-stu-id="44a52-103">Create a template BOM</span></span>   

[!include [banner](../includes/banner.md)]


<span data-ttu-id="44a52-104">È possibile creare una DBA modello utilizzando uno dei metodi descritti di seguito.</span><span class="sxs-lookup"><span data-stu-id="44a52-104">You can create a template BOM by using any of the following methods.</span></span> <span data-ttu-id="44a52-105">Per tutti i metodi, i campi **Dal** e **Al** sono facoltativi ed esclusivamente informativi.</span><span class="sxs-lookup"><span data-stu-id="44a52-105">For all methods, the **From date** and **To date** fields are optional and for information only.</span></span>

## <a name="create-a-template-bom-manually"></a><span data-ttu-id="44a52-106">Creare manualmente una DBA modello</span><span class="sxs-lookup"><span data-stu-id="44a52-106">Create a template BOM manually</span></span>

1.  <span data-ttu-id="44a52-107">Fare clic su **Gestione assistenza** \> **Impostazione** \> **Oggetti assistenza** \> **DBA modello**.</span><span class="sxs-lookup"><span data-stu-id="44a52-107">Click **Service management** \> **Setup** \> **Service objects** \> **Template BOMs**.</span></span>

2.  <span data-ttu-id="44a52-108">Premere CTRL+N per aprire il modulo **Crea DBA modello**.</span><span class="sxs-lookup"><span data-stu-id="44a52-108">Press CTRL+N to open the **Create template BOM** form.</span></span>

3.  <span data-ttu-id="44a52-109">In **Copia righe DBA da riferimento**, selezionare l'opzione **Manuale**.</span><span class="sxs-lookup"><span data-stu-id="44a52-109">Under **Copy BOM lines from reference**, select the **Manual** option.</span></span>

4.  <span data-ttu-id="44a52-110">Nel campo **Numero articolo** immettere un articolo di tipo **DBA**.</span><span class="sxs-lookup"><span data-stu-id="44a52-110">In the **Item number** field, enter an item of the type **BOM**.</span></span>

5.  <span data-ttu-id="44a52-111">Nel campo **Nome** immettere un nome per il modello.</span><span class="sxs-lookup"><span data-stu-id="44a52-111">In the **Name** field, enter a name for the template.</span></span>

6.  <span data-ttu-id="44a52-112">Nei campi **Dal** e **Al** immettere un intervallo di date in cui la DBA modello è attiva.</span><span class="sxs-lookup"><span data-stu-id="44a52-112">In the **From date** and **To date** fields, enter a date interval in which the template BOM is active.</span></span>

7.  <span data-ttu-id="44a52-113">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="44a52-113">Click **OK**.</span></span>

<span data-ttu-id="44a52-114">Verrà creata una nuova DBA modello vuota.</span><span class="sxs-lookup"><span data-stu-id="44a52-114">A new, blank template BOM is created.</span></span>

## <a name="create-a-template-bom-based-on-another-template-bom"></a><span data-ttu-id="44a52-115">Creare una DBA modello basata su un'altra DBA modello</span><span class="sxs-lookup"><span data-stu-id="44a52-115">Create a template BOM based on another template BOM</span></span>

1.  <span data-ttu-id="44a52-116">Fare clic su **Gestione assistenza** \> **Impostazione** \> **Oggetti assistenza** \> **DBA modello**.</span><span class="sxs-lookup"><span data-stu-id="44a52-116">Click **Service management** \> **Setup** \> **Service objects** \> **Template BOMs**.</span></span>

2.  <span data-ttu-id="44a52-117">Premere CTRL+N per aprire il modulo **Crea DBA modello**.</span><span class="sxs-lookup"><span data-stu-id="44a52-117">Press CTRL+N to open the **Create template BOM** form.</span></span>

3.  <span data-ttu-id="44a52-118">In **Copia righe DBA da riferimento**, selezionare l'opzione **DBA modello**.</span><span class="sxs-lookup"><span data-stu-id="44a52-118">Under **Copy BOM lines from reference**, select the **Template BOM** option.</span></span>

4.  <span data-ttu-id="44a52-119">Nel campo **Numero di riferimento** selezionare una DBA modello esistente da copiare nella nuova DBA modello.</span><span class="sxs-lookup"><span data-stu-id="44a52-119">In the **Reference number** field, select an existing template BOM to copy to your new template BOM.</span></span>

5.  <span data-ttu-id="44a52-120">Nel campo **Nome** immettere un nome per il modello.</span><span class="sxs-lookup"><span data-stu-id="44a52-120">In the **Name** field, enter a name for the template.</span></span>

6.  <span data-ttu-id="44a52-121">Nei campi **Dal** e **Al** immettere un intervallo di date in cui la DBA modello è attiva.</span><span class="sxs-lookup"><span data-stu-id="44a52-121">In the **From date** and **To date** fields, enter a date interval in which the template BOM is active.</span></span>

7.  <span data-ttu-id="44a52-122">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="44a52-122">Click **OK**.</span></span>

<span data-ttu-id="44a52-123">Verrà creata una nuova DBA modello mediante le righe che corrispondono a quelle della DBA modello originaria.</span><span class="sxs-lookup"><span data-stu-id="44a52-123">A new template BOM is created by using lines that correspond to the lines in the original template BOM.</span></span>

## <a name="create-a-template-bom-based-on-an-item-bom"></a><span data-ttu-id="44a52-124">Creare una DBA modello basata su una DBA articolo</span><span class="sxs-lookup"><span data-stu-id="44a52-124">Create a template BOM based on an item BOM</span></span>

1.  <span data-ttu-id="44a52-125">Fare clic su **Gestione assistenza** \> **Impostazione** \> **Oggetti assistenza** \> **DBA modello**.</span><span class="sxs-lookup"><span data-stu-id="44a52-125">Click **Service management** \> **Setup** \> **Service objects** \> **Template BOMs**.</span></span>

2.  <span data-ttu-id="44a52-126">Premere CTRL+N per aprire il modulo **Crea DBA modello**.</span><span class="sxs-lookup"><span data-stu-id="44a52-126">Press CTRL+N to open the **Create template BOM** form.</span></span>

3.  <span data-ttu-id="44a52-127">In **Copia righe DBA da riferimento**, selezionare **DBA**.</span><span class="sxs-lookup"><span data-stu-id="44a52-127">Under **Copy BOM lines from reference**, select **BOM**.</span></span>

4.  <span data-ttu-id="44a52-128">Nel campo **Numero di riferimento**, selezionare una versione DBA.</span><span class="sxs-lookup"><span data-stu-id="44a52-128">In the **Reference number** field, select a BOM version.</span></span> <span data-ttu-id="44a52-129">Un articolo di tipo DBA verrà copiato nel campo **Numero articolo**.</span><span class="sxs-lookup"><span data-stu-id="44a52-129">An item of the type BOM is copied to the **Item number**.</span></span>

5.  <span data-ttu-id="44a52-130">Nel campo **Nome** immettere un nome per il modello.</span><span class="sxs-lookup"><span data-stu-id="44a52-130">In the **Name** field, enter a name for the template.</span></span>

6.  <span data-ttu-id="44a52-131">Nei campi **Dal** e **Al** immettere un intervallo di date in cui la DBA modello è attiva.</span><span class="sxs-lookup"><span data-stu-id="44a52-131">In the **From date** and **To date** fields, enter a date interval in which the template BOM is active.</span></span>

7.  <span data-ttu-id="44a52-132">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="44a52-132">Click **OK**.</span></span>

<span data-ttu-id="44a52-133">Verrà creata una nuova DBA modello con le righe corrispondenti a quelle della DBA elencata in **Distinte base**.</span><span class="sxs-lookup"><span data-stu-id="44a52-133">A new template BOM is created by using lines that correspond to the lines of the BOM listed in **Bills of materials**.</span></span>

## <a name="create-a-template-bom-based-on-a-production-bom"></a><span data-ttu-id="44a52-134">Creare una DBA modello basata su una DBA di produzione</span><span class="sxs-lookup"><span data-stu-id="44a52-134">Create a template BOM based on a production BOM</span></span>

1.  <span data-ttu-id="44a52-135">Fare clic su **Gestione assistenza** \> **Impostazione** \> **Oggetti assistenza** \> **DBA modello**.</span><span class="sxs-lookup"><span data-stu-id="44a52-135">Click **Service management** \> **Setup** \> **Service objects** \> **Template BOMs**.</span></span>

2.  <span data-ttu-id="44a52-136">Premere CTRL+N per aprire il modulo **Crea DBA modello**.</span><span class="sxs-lookup"><span data-stu-id="44a52-136">Press CTRL+N to open the **Create template BOM** form.</span></span>

3.  <span data-ttu-id="44a52-137">In **Copia righe DBA da riferimento**, selezionare **Produzione**.</span><span class="sxs-lookup"><span data-stu-id="44a52-137">Under **Copy BOM lines from reference**, select **Production**.</span></span>

4.  <span data-ttu-id="44a52-138">Nel campo **Numero di riferimento**, selezionare una DBA di produzione.</span><span class="sxs-lookup"><span data-stu-id="44a52-138">In the **Reference number** field, select a production BOM.</span></span>

5.  <span data-ttu-id="44a52-139">Nel campo **Nome** immettere un nome per il modello.</span><span class="sxs-lookup"><span data-stu-id="44a52-139">In the **Name** field, enter a name for the template.</span></span>

6.  <span data-ttu-id="44a52-140">Nei campi **Dal** e **Al** immettere un intervallo di date in cui la DBA modello è attiva.</span><span class="sxs-lookup"><span data-stu-id="44a52-140">In the **From date** and **To date** fields, enter a date interval in which the template BOM is active.</span></span>

7.  <span data-ttu-id="44a52-141">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="44a52-141">Click **OK**.</span></span>

<span data-ttu-id="44a52-142">Verrà creata una nuova DBA modello con le righe corrispondenti a quelle della DBA elencata in **DBA**.</span><span class="sxs-lookup"><span data-stu-id="44a52-142">A new template BOM is created by using lines that correspond to the lines of the BOM listed in **BOM**.</span></span>

## <a name="see-also"></a><span data-ttu-id="44a52-143">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="44a52-143">See also</span></span>

[<span data-ttu-id="44a52-144">DBA modello </span><span class="sxs-lookup"><span data-stu-id="44a52-144">Template BOMs</span></span>](template-boms.md)

  


