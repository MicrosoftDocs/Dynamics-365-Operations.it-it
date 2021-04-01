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
ms.reviewer: roschlom
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 6627e7fa9a1eb1a9131ec7e2c3cc823b49b286cc
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5257563"
---
# <a name="set-up-bonus-depreciation"></a><span data-ttu-id="d1e32-103">Impostare l'ammortamento straordinario</span><span class="sxs-lookup"><span data-stu-id="d1e32-103">Set up bonus depreciation</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="d1e32-104">In questa procedura viene illustrato come creare un fondo di ammortamento speciale e associarlo a un libro cespiti.</span><span class="sxs-lookup"><span data-stu-id="d1e32-104">This procedure shows how to create a special depreciation allowance and associate it with a fixed asset book.</span></span> <span data-ttu-id="d1e32-105">Utilizza il ruolo Ragioniere e i dati dimostrativi della persona giuridica USMF.</span><span class="sxs-lookup"><span data-stu-id="d1e32-105">It uses the accountant role and demo data for the USMF legal entity.</span></span>


## <a name="create-a-special-depreciation-allowance"></a><span data-ttu-id="d1e32-106">Creare un fondo di ammortamento speciale</span><span class="sxs-lookup"><span data-stu-id="d1e32-106">Create a special depreciation allowance</span></span>
1. <span data-ttu-id="d1e32-107">Andare a Cespiti > Impostazioni > Fondo di ammortamento speciale.</span><span class="sxs-lookup"><span data-stu-id="d1e32-107">Go to Fixed assets > Setup > Special depreciation allowance.</span></span>
2. <span data-ttu-id="d1e32-108">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="d1e32-108">Click New.</span></span>
3. <span data-ttu-id="d1e32-109">Nel campo Fondo di ammortamento speciale digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="d1e32-109">In the Special depreciation allowance field, type a value.</span></span>
4. <span data-ttu-id="d1e32-110">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="d1e32-110">In the Description field, type a value.</span></span>
5. <span data-ttu-id="d1e32-111">Nel campo Percentuale immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="d1e32-111">In the Percentage field, enter a number.</span></span>
    * <span data-ttu-id="d1e32-112">Impostare un importo se non è stata indicata una percentuale.</span><span class="sxs-lookup"><span data-stu-id="d1e32-112">If a percentage was not indicated, set an amount.</span></span>  

## <a name="associate-a-special-depreciation-allowance-with-a-fixed-asset-group-book"></a><span data-ttu-id="d1e32-113">Associare un fondo di ammortamento speciale a un libro gruppo cespite</span><span class="sxs-lookup"><span data-stu-id="d1e32-113">Associate a special depreciation allowance with a fixed asset group book</span></span>
1. <span data-ttu-id="d1e32-114">Andare a Cespiti > Impostazioni > Gruppi cespite.</span><span class="sxs-lookup"><span data-stu-id="d1e32-114">Go to Fixed assets > Setup > Fixed asset groups.</span></span>
2. <span data-ttu-id="d1e32-115">Nell'elenco selezionare un gruppo cespite associato al fondo di ammortamento speciale.</span><span class="sxs-lookup"><span data-stu-id="d1e32-115">In the list, select the fixed asset group associated with the special depreciation allowance.</span></span>
3. <span data-ttu-id="d1e32-116">Fare clic su Libri.</span><span class="sxs-lookup"><span data-stu-id="d1e32-116">Click Books.</span></span>
4. <span data-ttu-id="d1e32-117">Nell'elenco selezionare il libro associato al fondo di ammortamento speciale.</span><span class="sxs-lookup"><span data-stu-id="d1e32-117">In the list, select the book that is associated with the special depreciation allowance.</span></span>
5. <span data-ttu-id="d1e32-118">Fare clic su Fondo di ammortamento speciale.</span><span class="sxs-lookup"><span data-stu-id="d1e32-118">Click Special depreciation allowance.</span></span>
6. <span data-ttu-id="d1e32-119">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="d1e32-119">Click New.</span></span>
7. <span data-ttu-id="d1e32-120">Nel campo Fondo di ammortamento speciale immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="d1e32-120">In the Special depreciation allowance field, enter or select a value.</span></span>
    * <span data-ttu-id="d1e32-121">Il valore predefinito di Percentuale o Importo viene dall'impostazione del fondo di ammortamento speciale.</span><span class="sxs-lookup"><span data-stu-id="d1e32-121">The default for Percentage or Amount comes from the special depreciation allowance setup.</span></span>  
8. <span data-ttu-id="d1e32-122">Nel campo Priorità immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="d1e32-122">In the Priority field, enter a number.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]