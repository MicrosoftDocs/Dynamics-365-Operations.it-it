---
title: Creare un modello di record per facilitare l'immissione dei dati
description: Questa procedura dimostra come creare un modello di record in modo che non sia necessario inserire in modo esplicito i valori dei campi che vengono utilizzati spesso per ogni nuovo record.
author: margoc
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetTable, SysRecordInfo, SysRecordTemplatePromptOnCreate
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: margoc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 3b2ba56b6146f2495fb6a53c3cef9f549b1ad837
ms.sourcegitcommit: 16bfa0fd08feec1647829630401ce62ce2ffa1a4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/02/2019
ms.locfileid: "1848209"
---
# <a name="create-a-record-template-to-facilitate-data-entry"></a><span data-ttu-id="6d17f-103">Creare un modello di record per facilitare l'immissione dei dati</span><span class="sxs-lookup"><span data-stu-id="6d17f-103">Create a record template to facilitate data entry</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="6d17f-104">Questa procedura dimostra come creare un modello di record in modo che non sia necessario inserire in modo esplicito i valori dei campi che vengono utilizzati spesso per ogni nuovo record.</span><span class="sxs-lookup"><span data-stu-id="6d17f-104">This procedure demonstrates how to create a record template so that field values that are used often do not have to be entered explicitly for each new record.</span></span> <span data-ttu-id="6d17f-105">In questa procedura, verrà creato un nuovo record per i nuovi computer portatili che devono essere aggiunti ai cespiti.</span><span class="sxs-lookup"><span data-stu-id="6d17f-105">In this procedure, you’ll create a new record for new laptops that should be added to your fixed assets.</span></span> <span data-ttu-id="6d17f-106">Questa procedura utilizza la società di esempio USMF.</span><span class="sxs-lookup"><span data-stu-id="6d17f-106">This procedure uses the USMF sample company.</span></span>

1. <span data-ttu-id="6d17f-107">Passare a Cespiti > Cespiti > Cespiti.</span><span class="sxs-lookup"><span data-stu-id="6d17f-107">Go to Fixed assets > Fixed assets > Fixed assets.</span></span>
2. <span data-ttu-id="6d17f-108">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="6d17f-108">Click New.</span></span>
3. <span data-ttu-id="6d17f-109">Nel campo Cespiti immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="6d17f-109">In the Fixed asset group field, enter or select a value.</span></span>
4. <span data-ttu-id="6d17f-110">Digitare un valore nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="6d17f-110">In the Name field, type a value.</span></span>
    * <span data-ttu-id="6d17f-111">Ad esempio, immettere 'Corporate lead laptop'.</span><span class="sxs-lookup"><span data-stu-id="6d17f-111">For example, enter 'Corporate lead laptop'.</span></span>  
5. <span data-ttu-id="6d17f-112">Digitare un valore nel campo Nome di ricerca.</span><span class="sxs-lookup"><span data-stu-id="6d17f-112">In the Search name field, type a value.</span></span>
    * <span data-ttu-id="6d17f-113">Ad esempio, immettere 'laptop.'</span><span class="sxs-lookup"><span data-stu-id="6d17f-113">For example, enter 'laptop.'</span></span>  
6. <span data-ttu-id="6d17f-114">Espandere la sezione Informazioni tecniche.</span><span class="sxs-lookup"><span data-stu-id="6d17f-114">Expand the Technical information section.</span></span>
7. <span data-ttu-id="6d17f-115">Nel campo Marca digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="6d17f-115">In the Make field, type a value.</span></span>
8. <span data-ttu-id="6d17f-116">Nel campo Modello digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="6d17f-116">In the Model field, type a value.</span></span>
9. <span data-ttu-id="6d17f-117">Nel campo Anno modello digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="6d17f-117">In the Model year field, type a value.</span></span>
10. <span data-ttu-id="6d17f-118">Nel riquadro azioni fare clic su Opzioni.</span><span class="sxs-lookup"><span data-stu-id="6d17f-118">On the Action Pane, click Options.</span></span>
11. <span data-ttu-id="6d17f-119">Fare clic su Informazioni sui record.</span><span class="sxs-lookup"><span data-stu-id="6d17f-119">Click Record info.</span></span>
12. <span data-ttu-id="6d17f-120">Fare clic su Modello utente.</span><span class="sxs-lookup"><span data-stu-id="6d17f-120">Click User template.</span></span>
13. <span data-ttu-id="6d17f-121">Digitare un valore nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="6d17f-121">In the Name field, type a value.</span></span>
    * <span data-ttu-id="6d17f-122">Ad esempio, immettere 'Corporate laptop.'</span><span class="sxs-lookup"><span data-stu-id="6d17f-122">For example, enter 'Corporate laptop.'</span></span>  
14. <span data-ttu-id="6d17f-123">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="6d17f-123">In the Description field, type a value.</span></span>
    * <span data-ttu-id="6d17f-124">Ad esempio, immettere 'Corporate laptop'.</span><span class="sxs-lookup"><span data-stu-id="6d17f-124">For example, enter 'Corporate laptop'.</span></span>  
15. <span data-ttu-id="6d17f-125">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="6d17f-125">Click OK.</span></span>
16. <span data-ttu-id="6d17f-126">Fare clic su Chiudi.</span><span class="sxs-lookup"><span data-stu-id="6d17f-126">Click Close.</span></span>

