--- 
title: Definire il gruppo di risorse di produzione discreta
description: "Un gruppo di risorse è un set di risorse operative che in genere corrisponde all'organizzazione fisica delle celle di lavoro, definito dalle righe gialle nello shop floor di produzione."
author: sorenva
manager: AnnBe
ms.date: 11/03/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: sorenand
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 2d74620761f01e2385288263e4f229872460fa21
ms.contentlocale: it-it
ms.lasthandoff: 04/13/2018

---
# <a name="define-discrete-manufacturing-resource-group"></a><span data-ttu-id="4d01c-103">Definire il gruppo di risorse di produzione discreta</span><span class="sxs-lookup"><span data-stu-id="4d01c-103">Define discrete manufacturing resource group</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="4d01c-104">Un gruppo di risorse è un set di risorse operative che in genere corrisponde all'organizzazione fisica delle celle di lavoro, definito dalle righe gialle nello shop floor di produzione.</span><span class="sxs-lookup"><span data-stu-id="4d01c-104">A resource group is a set of operations resources that typically correspond to the physical organization of work cells, defined by yellow lines on the production shop floor.</span></span> <span data-ttu-id="4d01c-105">In questa procedura viene illustrato come definire un gruppo di risorse da utilizzare nella produzione discreta.</span><span class="sxs-lookup"><span data-stu-id="4d01c-105">This procedure shows you how to define a resource group for use in discrete production.</span></span> <span data-ttu-id="4d01c-106">È possibile eseguire questa procedura nella società di dati dimostrativi USMF oppure utilizzare i propri dati.</span><span class="sxs-lookup"><span data-stu-id="4d01c-106">You can walk through this procedure in demo data company USMF, or use your own data.</span></span>

1. <span data-ttu-id="4d01c-107">Fare clic su Gruppo di risorse.</span><span class="sxs-lookup"><span data-stu-id="4d01c-107">Go to Resource groups.</span></span>
2. <span data-ttu-id="4d01c-108">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="4d01c-108">Click New.</span></span>
3. <span data-ttu-id="4d01c-109">Digitare un valore nel campo Gruppo di risorse.</span><span class="sxs-lookup"><span data-stu-id="4d01c-109">In the Resource group field, type a value.</span></span>
4. <span data-ttu-id="4d01c-110">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="4d01c-110">In the Description field, type a value.</span></span>
5. <span data-ttu-id="4d01c-111">Nel campo Sito immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="4d01c-111">In the Site field, enter or select a value.</span></span>
6. <span data-ttu-id="4d01c-112">Nel campo Unità di produzione immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="4d01c-112">In the Production unit field, enter or select a value.</span></span>

## <a name="define-default-operational-parameters"></a><span data-ttu-id="4d01c-113">Definisce i parametri operativi predefiniti</span><span class="sxs-lookup"><span data-stu-id="4d01c-113">Define default operational parameters</span></span>
1. <span data-ttu-id="4d01c-114">Espandere la sezione Operazione.</span><span class="sxs-lookup"><span data-stu-id="4d01c-114">Expand the Operation section.</span></span>
2. <span data-ttu-id="4d01c-115">Immettere un numero nel campo Percentuale scarti.</span><span class="sxs-lookup"><span data-stu-id="4d01c-115">In the Scrap percentage field, enter a number.</span></span>
3. <span data-ttu-id="4d01c-116">Nel campo Categoria tempo di attrezzaggio immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="4d01c-116">In the Setup category field, enter or select a value.</span></span>
4. <span data-ttu-id="4d01c-117">Nel campo Categoria tempo di esecuzione immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="4d01c-117">In the Run time category field, enter or select a value.</span></span>
5. <span data-ttu-id="4d01c-118">Nel campo Percentuale programmazione operazioni, immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="4d01c-118">In the Operations scheduling percentage field, enter a number.</span></span>

## <a name="define-operating-hours"></a><span data-ttu-id="4d01c-119">Definisce le ore di funzionamento</span><span class="sxs-lookup"><span data-stu-id="4d01c-119">Define operating hours</span></span>
1. <span data-ttu-id="4d01c-120">Espandere la sezione Calendari.</span><span class="sxs-lookup"><span data-stu-id="4d01c-120">Expand the Calendars section.</span></span>
2. <span data-ttu-id="4d01c-121">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="4d01c-121">Click Add.</span></span>
3. <span data-ttu-id="4d01c-122">Nel campo Calendario immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="4d01c-122">In the Calendar field, enter or select a value.</span></span>

## <a name="add-operations-resources"></a><span data-ttu-id="4d01c-123">Aggiunge le risorse operative</span><span class="sxs-lookup"><span data-stu-id="4d01c-123">Add operations resources</span></span>
1. <span data-ttu-id="4d01c-124">Espandere la sezione Risorse.</span><span class="sxs-lookup"><span data-stu-id="4d01c-124">Expand the Resources section.</span></span>
2. <span data-ttu-id="4d01c-125">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="4d01c-125">Click Add.</span></span>
3. <span data-ttu-id="4d01c-126">Nel campo Risorsa immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="4d01c-126">In the Resource field, enter or select a value.</span></span>
4. <span data-ttu-id="4d01c-127">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="4d01c-127">Click Add.</span></span>
5. <span data-ttu-id="4d01c-128">Nel campo Risorsa immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="4d01c-128">In the Resource field, enter or select a value.</span></span>
6. <span data-ttu-id="4d01c-129">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="4d01c-129">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="4d01c-130">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="4d01c-130">In the list, click the link in the selected row.</span></span>


