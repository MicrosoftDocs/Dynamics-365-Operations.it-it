---
title: 'Creare oggetti di costo  '
description: In questa procedura viene illustrato come creare oggetti di costo importando la dimensione finanziaria centro di costo nella contabilità industriale tramite un connettore dati.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CAMDimension, CAMAXFinancialDimensionMemberProviderConfiguration, CAMDimensionMember
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 55f5f6e5048f70e744cb3dc82a2a279aae69b4af
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4444919"
---
# <a name="create-cost-objects"></a><span data-ttu-id="72e10-103">Creare oggetti di costo  </span><span class="sxs-lookup"><span data-stu-id="72e10-103">Create cost objects</span></span> 

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="72e10-104">In questa procedura viene illustrato come creare oggetti di costo importando la dimensione finanziaria centro di costo nella contabilità industriale tramite un connettore dati.</span><span class="sxs-lookup"><span data-stu-id="72e10-104">This procedure shows how to create cost objects by importing the cost center financial dimension into Cost accounting via a data connector.</span></span> <span data-ttu-id="72e10-105">La società di dati dimostrativi USMF è stata utilizzata per creare questa procedura.</span><span class="sxs-lookup"><span data-stu-id="72e10-105">The USMF demo company was used to create this procedure.</span></span> 


## <a name="create-new-cost-objects"></a><span data-ttu-id="72e10-106">Creare nuovi oggetti di costo</span><span class="sxs-lookup"><span data-stu-id="72e10-106">Create new cost objects</span></span>
1. <span data-ttu-id="72e10-107">Passare a Contabilità industriale > Dimensioni > Dimensioni oggetto di costo.</span><span class="sxs-lookup"><span data-stu-id="72e10-107">Go to Cost accounting > Dimensions > Cost object dimensions.</span></span>
2. <span data-ttu-id="72e10-108">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="72e10-108">Click New.</span></span>
3. <span data-ttu-id="72e10-109">Digitare un valore nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="72e10-109">In the Name field, type a value.</span></span>
4. <span data-ttu-id="72e10-110">Nel campo Connettore dati per membri di dimensione immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="72e10-110">In the Data connector for dimension members field, enter or select a value.</span></span>
5. <span data-ttu-id="72e10-111">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="72e10-111">In the Description field, type a value.</span></span>
6. <span data-ttu-id="72e10-112">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="72e10-112">Click Save.</span></span>

## <a name="configure-the-data-connector"></a><span data-ttu-id="72e10-113">Configurare il connettore dati</span><span class="sxs-lookup"><span data-stu-id="72e10-113">Configure the data connector</span></span>
1. <span data-ttu-id="72e10-114">Fare clic su Configura provider membro di dimensione.</span><span class="sxs-lookup"><span data-stu-id="72e10-114">Click Configure dimension member provider.</span></span>
    * <span data-ttu-id="72e10-115">Selezionare CostCenter per importare la dimensione CostCenter nella contabilità industriale.</span><span class="sxs-lookup"><span data-stu-id="72e10-115">Select CostCenter to import the CostCenter dimension into Cost accounting.</span></span>  
2. <span data-ttu-id="72e10-116">Nel campo Nome dimensione, selezionare Centro di costo.</span><span class="sxs-lookup"><span data-stu-id="72e10-116">In the Dimension name field, select Cost center.</span></span>
3. <span data-ttu-id="72e10-117">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="72e10-117">Click OK.</span></span>

## <a name="import-cost-centers"></a><span data-ttu-id="72e10-118">Importare i centri di costo</span><span class="sxs-lookup"><span data-stu-id="72e10-118">Import cost centers</span></span>
1. <span data-ttu-id="72e10-119">Fare clic su Importa membri di dimensione.</span><span class="sxs-lookup"><span data-stu-id="72e10-119">Click Import dimension members.</span></span>
2. <span data-ttu-id="72e10-120">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="72e10-120">Click OK.</span></span>

## <a name="view-the-imported-cost-centers"></a><span data-ttu-id="72e10-121">Visualizzare i centri di costo importati</span><span class="sxs-lookup"><span data-stu-id="72e10-121">View the imported cost centers</span></span>
1. <span data-ttu-id="72e10-122">Fare clic su Visualizza membri di dimensione.</span><span class="sxs-lookup"><span data-stu-id="72e10-122">Click View dimension members.</span></span>

