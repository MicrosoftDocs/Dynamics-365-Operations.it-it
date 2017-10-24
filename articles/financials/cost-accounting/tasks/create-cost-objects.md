--- 
title: 'Creare oggetti di costo  '
description: "In questa procedura viene illustrato come creare oggetti di costo importando la dimensione finanziaria centro di costo di Dynamics 365 for Finance and Operations, Enterprise edition nella contabilità industriale tramite un connettore dati."
author: YuyuScheller
manager: AnnBe
ms.date: 10/25/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 5d43274aed2edbb91fd4e399cb8d45e91646b055
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---
# <a name="create-cost-objects"></a><span data-ttu-id="59f10-103">Creare oggetti di costo  </span><span class="sxs-lookup"><span data-stu-id="59f10-103">Create cost objects</span></span> 

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="59f10-104">In questa procedura viene illustrato come creare oggetti di costo importando la dimensione finanziaria centro di costo di Dynamics 365 for Finance and Operations, Enterprise edition nella contabilità industriale tramite un connettore dati.</span><span class="sxs-lookup"><span data-stu-id="59f10-104">This procedure shows how to create cost objects by importing the Dynamics 365 for Finance and Operations, Enterprise edition cost center financial dimension into Cost accounting via a data connector.</span></span> <span data-ttu-id="59f10-105">La società di dati dimostrativi USMF è stata utilizzata per creare questa procedura.</span><span class="sxs-lookup"><span data-stu-id="59f10-105">The USMF demo company was used to create this procedure.</span></span> <span data-ttu-id="59f10-106">Questa procedura è per una funzionalità di Contabilità industriale che è stata aggiunta in Dynamics 365 for Operations, versione 1611.</span><span class="sxs-lookup"><span data-stu-id="59f10-106">This procedure is for a Cost accounting feature that was added in Dynamics 365 for Operations, version 1611.</span></span>


## <a name="create-new-cost-objects"></a><span data-ttu-id="59f10-107">Creare nuovi oggetti di costo</span><span class="sxs-lookup"><span data-stu-id="59f10-107">Create new cost objects</span></span>
1. <span data-ttu-id="59f10-108">Passare a Contabilità industriale > Dimensioni > Dimensioni oggetto di costo.</span><span class="sxs-lookup"><span data-stu-id="59f10-108">Go to Cost accounting > Dimensions > Cost object dimensions.</span></span>
2. <span data-ttu-id="59f10-109">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="59f10-109">Click New.</span></span>
3. <span data-ttu-id="59f10-110">Digitare un valore nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="59f10-110">In the Name field, type a value.</span></span>
4. <span data-ttu-id="59f10-111">Nel campo Connettore dati per membri di dimensione immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="59f10-111">In the Data connector for dimension members field, enter or select a value.</span></span>
5. <span data-ttu-id="59f10-112">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="59f10-112">In the Description field, type a value.</span></span>
6. <span data-ttu-id="59f10-113">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="59f10-113">Click Save.</span></span>

## <a name="configure-the-data-connector"></a><span data-ttu-id="59f10-114">Configurare il connettore dati</span><span class="sxs-lookup"><span data-stu-id="59f10-114">Configure the data connector</span></span>
1. <span data-ttu-id="59f10-115">Fare clic su Configura provider membro di dimensione.</span><span class="sxs-lookup"><span data-stu-id="59f10-115">Click Configure dimension member provider.</span></span>
    * <span data-ttu-id="59f10-116">Selezionare CostCenter per importare la dimensione CostCenter nella contabilità industriale.</span><span class="sxs-lookup"><span data-stu-id="59f10-116">Select CostCenter to import the CostCenter dimension into Cost accounting.</span></span>  
2. <span data-ttu-id="59f10-117">Nel campo Nome dimensione, selezionare Centro di costo.</span><span class="sxs-lookup"><span data-stu-id="59f10-117">In the Dimension name field, select Cost center.</span></span>
3. <span data-ttu-id="59f10-118">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="59f10-118">Click OK.</span></span>

## <a name="import-cost-centers"></a><span data-ttu-id="59f10-119">Importare i centri di costo</span><span class="sxs-lookup"><span data-stu-id="59f10-119">Import cost centers</span></span>
1. <span data-ttu-id="59f10-120">Fare clic su Importa membri di dimensione.</span><span class="sxs-lookup"><span data-stu-id="59f10-120">Click Import dimension members.</span></span>
2. <span data-ttu-id="59f10-121">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="59f10-121">Click OK.</span></span>

## <a name="view-the-imported-cost-centers"></a><span data-ttu-id="59f10-122">Visualizzare i centri di costo importati</span><span class="sxs-lookup"><span data-stu-id="59f10-122">View the imported cost centers</span></span>
1. <span data-ttu-id="59f10-123">Fare clic su Visualizza membri di dimensione.</span><span class="sxs-lookup"><span data-stu-id="59f10-123">Click View dimension members.</span></span>


