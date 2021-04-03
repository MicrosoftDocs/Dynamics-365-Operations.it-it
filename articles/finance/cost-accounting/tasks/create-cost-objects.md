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
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 91c25c52a2c6dc7f096a494577b361ff30406e9c
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5236796"
---
# <a name="create-cost-objects"></a><span data-ttu-id="d3b09-103">Creare oggetti di costo  </span><span class="sxs-lookup"><span data-stu-id="d3b09-103">Create cost objects</span></span> 

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="d3b09-104">In questa procedura viene illustrato come creare oggetti di costo importando la dimensione finanziaria centro di costo nella contabilità industriale tramite un connettore dati.</span><span class="sxs-lookup"><span data-stu-id="d3b09-104">This procedure shows how to create cost objects by importing the cost center financial dimension into Cost accounting via a data connector.</span></span> <span data-ttu-id="d3b09-105">La società di dati dimostrativi USMF è stata utilizzata per creare questa procedura.</span><span class="sxs-lookup"><span data-stu-id="d3b09-105">The USMF demo company was used to create this procedure.</span></span> 


## <a name="create-new-cost-objects"></a><span data-ttu-id="d3b09-106">Creare nuovi oggetti di costo</span><span class="sxs-lookup"><span data-stu-id="d3b09-106">Create new cost objects</span></span>
1. <span data-ttu-id="d3b09-107">Passare a Contabilità industriale > Dimensioni > Dimensioni oggetto di costo.</span><span class="sxs-lookup"><span data-stu-id="d3b09-107">Go to Cost accounting > Dimensions > Cost object dimensions.</span></span>
2. <span data-ttu-id="d3b09-108">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="d3b09-108">Click New.</span></span>
3. <span data-ttu-id="d3b09-109">Digitare un valore nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="d3b09-109">In the Name field, type a value.</span></span>
4. <span data-ttu-id="d3b09-110">Nel campo Connettore dati per membri di dimensione immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="d3b09-110">In the Data connector for dimension members field, enter or select a value.</span></span>
5. <span data-ttu-id="d3b09-111">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="d3b09-111">In the Description field, type a value.</span></span>
6. <span data-ttu-id="d3b09-112">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="d3b09-112">Click Save.</span></span>

## <a name="configure-the-data-connector"></a><span data-ttu-id="d3b09-113">Configurare il connettore dati</span><span class="sxs-lookup"><span data-stu-id="d3b09-113">Configure the data connector</span></span>
1. <span data-ttu-id="d3b09-114">Fare clic su Configura provider membro di dimensione.</span><span class="sxs-lookup"><span data-stu-id="d3b09-114">Click Configure dimension member provider.</span></span>
    * <span data-ttu-id="d3b09-115">Selezionare CostCenter per importare la dimensione CostCenter nella contabilità industriale.</span><span class="sxs-lookup"><span data-stu-id="d3b09-115">Select CostCenter to import the CostCenter dimension into Cost accounting.</span></span>  
2. <span data-ttu-id="d3b09-116">Nel campo Nome dimensione, selezionare Centro di costo.</span><span class="sxs-lookup"><span data-stu-id="d3b09-116">In the Dimension name field, select Cost center.</span></span>
3. <span data-ttu-id="d3b09-117">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="d3b09-117">Click OK.</span></span>

## <a name="import-cost-centers"></a><span data-ttu-id="d3b09-118">Importare i centri di costo</span><span class="sxs-lookup"><span data-stu-id="d3b09-118">Import cost centers</span></span>
1. <span data-ttu-id="d3b09-119">Fare clic su Importa membri di dimensione.</span><span class="sxs-lookup"><span data-stu-id="d3b09-119">Click Import dimension members.</span></span>
2. <span data-ttu-id="d3b09-120">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="d3b09-120">Click OK.</span></span>

## <a name="view-the-imported-cost-centers"></a><span data-ttu-id="d3b09-121">Visualizzare i centri di costo importati</span><span class="sxs-lookup"><span data-stu-id="d3b09-121">View the imported cost centers</span></span>
1. <span data-ttu-id="d3b09-122">Fare clic su Visualizza membri di dimensione.</span><span class="sxs-lookup"><span data-stu-id="d3b09-122">Click View dimension members.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]