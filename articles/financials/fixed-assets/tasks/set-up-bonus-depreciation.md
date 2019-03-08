---
title: Impostare l'ammortamento straordinario
description: In questa procedura viene illustrato come creare un fondo di ammortamento speciale e associarlo a un libro cespiti.
author: saraschi2
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetBonus, AssetGroup, AssetGroupBookSetup, AssetGroupSetupBonus
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 6bbd6b78d05fcc9d95f6e6409db2619a210ad760
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2019
ms.locfileid: "339213"
---
# <a name="set-up-bonus-depreciation"></a><span data-ttu-id="db5c5-103">Impostare l'ammortamento straordinario</span><span class="sxs-lookup"><span data-stu-id="db5c5-103">Set up bonus depreciation</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="db5c5-104">In questa procedura viene illustrato come creare un fondo di ammortamento speciale e associarlo a un libro cespiti.</span><span class="sxs-lookup"><span data-stu-id="db5c5-104">This procedure shows how to create a special depreciation allowance and associate it with a fixed asset book.</span></span> <span data-ttu-id="db5c5-105">Utilizza il ruolo Ragioniere e i dati dimostrativi della persona giuridica USMF.</span><span class="sxs-lookup"><span data-stu-id="db5c5-105">It uses the accountant role and demo data for the USMF legal entity.</span></span>


## <a name="create-a-special-depreciation-allowance"></a><span data-ttu-id="db5c5-106">Creare un fondo di ammortamento speciale</span><span class="sxs-lookup"><span data-stu-id="db5c5-106">Create a special depreciation allowance</span></span>
1. <span data-ttu-id="db5c5-107">Andare a Cespiti > Impostazioni > Fondo di ammortamento speciale.</span><span class="sxs-lookup"><span data-stu-id="db5c5-107">Go to Fixed assets > Setup > Special depreciation allowance.</span></span>
2. <span data-ttu-id="db5c5-108">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="db5c5-108">Click New.</span></span>
3. <span data-ttu-id="db5c5-109">Nel campo Fondo di ammortamento speciale digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="db5c5-109">In the Special depreciation allowance field, type a value.</span></span>
4. <span data-ttu-id="db5c5-110">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="db5c5-110">In the Description field, type a value.</span></span>
5. <span data-ttu-id="db5c5-111">Nel campo Percentuale immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="db5c5-111">In the Percentage field, enter a number.</span></span>
    * <span data-ttu-id="db5c5-112">Impostare un importo se non è stata indicata una percentuale.</span><span class="sxs-lookup"><span data-stu-id="db5c5-112">If a percentage was not indicated, set an amount.</span></span>  

## <a name="associate-a-special-depreciation-allowance-with-a-fixed-asset-group-book"></a><span data-ttu-id="db5c5-113">Associare un fondo di ammortamento speciale a un libro gruppo cespite</span><span class="sxs-lookup"><span data-stu-id="db5c5-113">Associate a special depreciation allowance with a fixed asset group book</span></span>
1. <span data-ttu-id="db5c5-114">Andare a Cespiti > Impostazioni > Gruppi cespite.</span><span class="sxs-lookup"><span data-stu-id="db5c5-114">Go to Fixed assets > Setup > Fixed asset groups.</span></span>
2. <span data-ttu-id="db5c5-115">Nell'elenco selezionare un gruppo cespite associato al fondo di ammortamento speciale.</span><span class="sxs-lookup"><span data-stu-id="db5c5-115">In the list, select the fixed asset group associated with the special depreciation allowance.</span></span>
3. <span data-ttu-id="db5c5-116">Fare clic su Libri.</span><span class="sxs-lookup"><span data-stu-id="db5c5-116">Click Books.</span></span>
4. <span data-ttu-id="db5c5-117">Nell'elenco selezionare il libro associato al fondo di ammortamento speciale.</span><span class="sxs-lookup"><span data-stu-id="db5c5-117">In the list, select the book that is associated with the special depreciation allowance.</span></span>
5. <span data-ttu-id="db5c5-118">Fare clic su Fondo di ammortamento speciale.</span><span class="sxs-lookup"><span data-stu-id="db5c5-118">Click Special depreciation allowance.</span></span>
6. <span data-ttu-id="db5c5-119">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="db5c5-119">Click New.</span></span>
7. <span data-ttu-id="db5c5-120">Nel campo Fondo di ammortamento speciale immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="db5c5-120">In the Special depreciation allowance field, enter or select a value.</span></span>
    * <span data-ttu-id="db5c5-121">Il valore predefinito di Percentuale o Importo viene dall'impostazione del fondo di ammortamento speciale.</span><span class="sxs-lookup"><span data-stu-id="db5c5-121">The default for Percentage or Amount comes from the special depreciation allowance setup.</span></span>  
8. <span data-ttu-id="db5c5-122">Nel campo Priorità immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="db5c5-122">In the Priority field, enter a number.</span></span>

