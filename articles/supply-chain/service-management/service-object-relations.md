---
title: Relazioni oggetti assistenza
description: "È possibile creare relazioni tra un oggetto assistenza e un contratto di assistenza o un ordine di assistenza."
author: ShylaThompson
manager: AnnBe
ms.date: 02/21/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SMAServiceObjectRelation
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: 03047b3eccf3c90d4cf7426ddaec83f10dbea1b0
ms.contentlocale: it-it
ms.lasthandoff: 08/07/2018

---

# <a name="service-object-relations"></a><span data-ttu-id="f6854-103">Relazioni oggetti assistenza</span><span class="sxs-lookup"><span data-stu-id="f6854-103">Service object relations</span></span> 

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f6854-104">È possibile creare relazioni tra un oggetto assistenza e un contratto di assistenza o un ordine di assistenza.</span><span class="sxs-lookup"><span data-stu-id="f6854-104">You can create service object relations between a service object and a service agreement or service order.</span></span> <span data-ttu-id="f6854-105">Per creare una relazione, è necessario collegare l'oggetto assistenza al contratto o all'ordine di assistenza.</span><span class="sxs-lookup"><span data-stu-id="f6854-105">When you create a relation, you attach the service object to the service agreement or service order.</span></span>

<span data-ttu-id="f6854-106">Una volta creata la relazione, sarà possibile collegare l'oggetto assistenza a qualsiasi riga nel contratto o ordine di assistenza.</span><span class="sxs-lookup"><span data-stu-id="f6854-106">After the relation is created, you can attach the service object to any lines on the service agreement or service order.</span></span>

## <a name="template-boms"></a><span data-ttu-id="f6854-107">DBA modello</span><span class="sxs-lookup"><span data-stu-id="f6854-107">Template BOMs</span></span>

<span data-ttu-id="f6854-108">È inoltre possibile specificare una DBA modello per la relazione di oggetto.</span><span class="sxs-lookup"><span data-stu-id="f6854-108">You can also specify a template BOM for the object relation.</span></span> <span data-ttu-id="f6854-109">La DBA modello è una distinta base relativa all'oggetto sul quale si esegue l'attività di assistenza.</span><span class="sxs-lookup"><span data-stu-id="f6854-109">The template BOM is a bill of materials for the object on which you perform service.</span></span> <span data-ttu-id="f6854-110">Se nel corso di un intervento viene sostituito un componente dell'oggetto assistenza, è possibile registrare questa modifica nella DBA assistenza utilizzando il modulo Oggetti assistenza.</span><span class="sxs-lookup"><span data-stu-id="f6854-110">If you replace a component part of the service object during a service visit, you can register this change in the service BOM by using the Service objects form.</span></span>

## <a name="example"></a><span data-ttu-id="f6854-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="f6854-111">Example</span></span>

<span data-ttu-id="f6854-112">Viene creato un contratto di assistenza per la riparazione di due ascensori presso la sede del cliente.</span><span class="sxs-lookup"><span data-stu-id="f6854-112">You create a service agreement for servicing two elevators at a customer site.</span></span>
<span data-ttu-id="f6854-113">Il contratto di assistenza ha come identificazione (ID) il codice SAL-001.</span><span class="sxs-lookup"><span data-stu-id="f6854-113">The service agreement has the identifier ID SAL-001.</span></span>

<span data-ttu-id="f6854-114">Nel modulo Oggetti assistenza gli ascensori sono stati impostati come oggetti EL-S/1000 e EL-L/1000.</span><span class="sxs-lookup"><span data-stu-id="f6854-114">The elevators are set up in the Service objects form as objects, EL-S/1000 and EL-L/1000.</span></span>

<span data-ttu-id="f6854-115">È possibile collegare gli oggetti assistenza EL-S/1000 e EL-L/1000 al contratto di assistenza.</span><span class="sxs-lookup"><span data-stu-id="f6854-115">You attach the service objects, EL-S/1000 and EL-L/1000, to the service agreement.</span></span>

<span data-ttu-id="f6854-116">Per registrare le modifiche nella DBA relativa all'oggetto assistenza man mano che si sostituiscono i componenti dell'oggetto, è possibile collegare una DBA assistenza alla relazione di oggetto, secondo quanto descritto nella seguente tabella.</span><span class="sxs-lookup"><span data-stu-id="f6854-116">You want to register changes in the BOM for the service object as you replace component parts of the object, so you attach a service BOM to the service object relation, as described in the following table.</span></span>

| <span data-ttu-id="f6854-117">Oggetto assistenza</span><span class="sxs-lookup"><span data-stu-id="f6854-117">Service object</span></span> | <span data-ttu-id="f6854-118">Relazione - Contratto di assistenza</span><span class="sxs-lookup"><span data-stu-id="f6854-118">Relation – Service agreement</span></span> | <span data-ttu-id="f6854-119">DBA assistenza</span><span class="sxs-lookup"><span data-stu-id="f6854-119">Service BOM</span></span>   |
|----------------|------------------------------|---------------|
| <span data-ttu-id="f6854-120">EL-S/1000</span><span class="sxs-lookup"><span data-stu-id="f6854-120">EL-S/1000</span></span>      | <span data-ttu-id="f6854-121">ID SAL-001</span><span class="sxs-lookup"><span data-stu-id="f6854-121">ID SAL-001</span></span>                   | <span data-ttu-id="f6854-122">DBA-EL-S/1000</span><span class="sxs-lookup"><span data-stu-id="f6854-122">BOM-EL-S/1000</span></span> |
| <span data-ttu-id="f6854-123">EL-L/1000</span><span class="sxs-lookup"><span data-stu-id="f6854-123">EL-L/1000</span></span>      | <span data-ttu-id="f6854-124">ID SAL-001</span><span class="sxs-lookup"><span data-stu-id="f6854-124">ID SAL-001</span></span>                   | <span data-ttu-id="f6854-125">DBA-EL-L/1000</span><span class="sxs-lookup"><span data-stu-id="f6854-125">BOM-EL-L/1000</span></span> |

<span data-ttu-id="f6854-126">Poiché sono disponibili relazioni di oggetti assistenza per il contratto, sarà possibile creare righe del contratto di assistenza con questi oggetti, secondo quanto descritto nella seguente tabella.</span><span class="sxs-lookup"><span data-stu-id="f6854-126">Because there are service object relations for the agreement, you can now create service agreement lines with these objects, as shown in the following table.</span></span>

| <span data-ttu-id="f6854-127">Tipo di transazione</span><span class="sxs-lookup"><span data-stu-id="f6854-127">Transaction type</span></span> | <span data-ttu-id="f6854-128">Categoria</span><span class="sxs-lookup"><span data-stu-id="f6854-128">Category</span></span>           | <span data-ttu-id="f6854-129">Oggetto assistenza</span><span class="sxs-lookup"><span data-stu-id="f6854-129">Service object</span></span> |
|------------------|--------------------|----------------|
| <span data-ttu-id="f6854-130">Ora</span><span class="sxs-lookup"><span data-stu-id="f6854-130">Hour</span></span>             | <span data-ttu-id="f6854-131">Ispezione</span><span class="sxs-lookup"><span data-stu-id="f6854-131">Inspection</span></span>         | <span data-ttu-id="f6854-132">EL-S/1000</span><span class="sxs-lookup"><span data-stu-id="f6854-132">EL-S/1000</span></span>      |
| <span data-ttu-id="f6854-133">Ora</span><span class="sxs-lookup"><span data-stu-id="f6854-133">Hour</span></span>             | <span data-ttu-id="f6854-134">Pulizia riduttore</span><span class="sxs-lookup"><span data-stu-id="f6854-134">Gear box cleaning</span></span>  | <span data-ttu-id="f6854-135">EL-S/1000</span><span class="sxs-lookup"><span data-stu-id="f6854-135">EL-S/1000</span></span>      |
| <span data-ttu-id="f6854-136">Elemento</span><span class="sxs-lookup"><span data-stu-id="f6854-136">Item</span></span>             | <span data-ttu-id="f6854-137">Materiali pulizia</span><span class="sxs-lookup"><span data-stu-id="f6854-137">Cleaning materials</span></span> | <span data-ttu-id="f6854-138">EL-S/1000</span><span class="sxs-lookup"><span data-stu-id="f6854-138">EL-S/1000</span></span>      |
| <span data-ttu-id="f6854-139">Ora</span><span class="sxs-lookup"><span data-stu-id="f6854-139">Hour</span></span>             | <span data-ttu-id="f6854-140">Ispezione</span><span class="sxs-lookup"><span data-stu-id="f6854-140">Inspection</span></span>         | <span data-ttu-id="f6854-141">EL-L/1000</span><span class="sxs-lookup"><span data-stu-id="f6854-141">EL-L/1000</span></span>      |
| <span data-ttu-id="f6854-142">Ora</span><span class="sxs-lookup"><span data-stu-id="f6854-142">Hour</span></span>             | <span data-ttu-id="f6854-143">Pulizia riduttore</span><span class="sxs-lookup"><span data-stu-id="f6854-143">Gearbox cleaning</span></span>   | <span data-ttu-id="f6854-144">EL-L/1000</span><span class="sxs-lookup"><span data-stu-id="f6854-144">EL-L/1000</span></span>      |
| <span data-ttu-id="f6854-145">Elemento</span><span class="sxs-lookup"><span data-stu-id="f6854-145">Item</span></span>             | <span data-ttu-id="f6854-146">Materiali pulizia</span><span class="sxs-lookup"><span data-stu-id="f6854-146">Cleaning materials</span></span> | <span data-ttu-id="f6854-147">EL-L/1000</span><span class="sxs-lookup"><span data-stu-id="f6854-147">EL-L/1000</span></span>      |

<span data-ttu-id="f6854-148">Durante un sopralluogo si presenta la necessità di sostituire il riduttore dell'ascensore EL-S/1000.</span><span class="sxs-lookup"><span data-stu-id="f6854-148">On a service visit, you have to replace the gearbox for elevator EL-S/1000.</span></span> <span data-ttu-id="f6854-149">Per sostituire un componente dell'oggetto, è possibile accedere a Designer DBA utilizzando la relazione di oggetti assistenza impostata per l'ordine di assistenza corrente.</span><span class="sxs-lookup"><span data-stu-id="f6854-149">To replace a component part of the object, you can access the BOM Designer by using the service object relation that you set up for the current service agreement.</span></span>

<span data-ttu-id="f6854-150">Accedere a Designer DBA utilizzando una relazione di oggetti assistenza</span><span class="sxs-lookup"><span data-stu-id="f6854-150">Access the BOM Designer by using a service object relation</span></span>

1. <span data-ttu-id="f6854-151">Contratti di assistenza</span><span class="sxs-lookup"><span data-stu-id="f6854-151">Service agreements</span></span>
2. <span data-ttu-id="f6854-152">Fare doppio clic su un contratto di assistenza oppure fare clic su Contratto di assistenza per crearne uno nuovo.</span><span class="sxs-lookup"><span data-stu-id="f6854-152">Double-click a service agreement, or click Service agreement to create a service agreement.</span></span>
3. <span data-ttu-id="f6854-153">Fare clic sulla scheda Impostazioni.</span><span class="sxs-lookup"><span data-stu-id="f6854-153">Click the Setup tab.</span></span>
4. <span data-ttu-id="f6854-154">Per collegare una DBA modello al contratto di assistenza, fare clic su Oggetti assistenza.</span><span class="sxs-lookup"><span data-stu-id="f6854-154">Click Service objects to attach a template BOM to the service agreement.</span></span>
5. <span data-ttu-id="f6854-155">Nel modulo Oggetti assistenza fare clic su Progettazione per aprire il modulo Progettazione e modificare la DBA modello.</span><span class="sxs-lookup"><span data-stu-id="f6854-155">In the Service objects form, click Designer to open the Designer form to modify the template BOM.</span></span>

## <a name="automatically-created-service-orders"></a><span data-ttu-id="f6854-156">Creazione automatica degli ordini di assistenza</span><span class="sxs-lookup"><span data-stu-id="f6854-156">Automatically created service orders</span></span>

<span data-ttu-id="f6854-157">Se gli ordini relativi a un contratto di assistenza vengono creati automaticamente, le relazioni di oggetti assistenza del contratto vengono riportate anche negli ordini di assistenza creati.</span><span class="sxs-lookup"><span data-stu-id="f6854-157">If you automatically create service orders for a service agreement, the service object relations in the agreement are also created in the service orders.</span></span>


