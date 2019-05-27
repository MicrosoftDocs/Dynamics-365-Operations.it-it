---
title: 'Creare oggetti di costo  '
description: In questa procedura viene illustrato come creare oggetti di costo importando la dimensione finanziaria centro di costo di Dynamics 365 for Finance and Operations, edizione Enterprise, nella contabilità industriale tramite un connettore dati.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CAMDimension, CAMAXFinancialDimensionMemberProviderConfiguration, CAMDimensionMember
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1e12de1d51658092fb19f652cef7c1cc78b255b5
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "1543773"
---
# <a name="create-cost-objects"></a><span data-ttu-id="a1589-103">Creare oggetti di costo  </span><span class="sxs-lookup"><span data-stu-id="a1589-103">Create cost objects</span></span> 

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="a1589-104">In questa procedura viene illustrato come creare oggetti di costo importando la dimensione finanziaria centro di costo di Dynamics 365 for Finance and Operations, edizione Enterprise, nella contabilità industriale tramite un connettore dati.</span><span class="sxs-lookup"><span data-stu-id="a1589-104">This procedure shows how to create cost objects by importing the Dynamics 365 for Finance and Operations, Enterprise edition cost center financial dimension into Cost accounting via a data connector.</span></span> <span data-ttu-id="a1589-105">La società di dati dimostrativi USMF è stata utilizzata per creare questa procedura.</span><span class="sxs-lookup"><span data-stu-id="a1589-105">The USMF demo company was used to create this procedure.</span></span> <span data-ttu-id="a1589-106">Questa procedura è per una funzionalità di contabilità industriale che è stata aggiunta in Dynamics 365 for Operations, versione 1611.</span><span class="sxs-lookup"><span data-stu-id="a1589-106">This procedure is for a Cost accounting feature that was added in Dynamics 365 for Operations, version 1611.</span></span>


## <a name="create-new-cost-objects"></a><span data-ttu-id="a1589-107">Creare nuovi oggetti di costo</span><span class="sxs-lookup"><span data-stu-id="a1589-107">Create new cost objects</span></span>
1. <span data-ttu-id="a1589-108">Passare a Contabilità industriale > Dimensioni > Dimensioni oggetto di costo.</span><span class="sxs-lookup"><span data-stu-id="a1589-108">Go to Cost accounting > Dimensions > Cost object dimensions.</span></span>
2. <span data-ttu-id="a1589-109">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="a1589-109">Click New.</span></span>
3. <span data-ttu-id="a1589-110">Digitare un valore nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="a1589-110">In the Name field, type a value.</span></span>
4. <span data-ttu-id="a1589-111">Nel campo Connettore dati per membri di dimensione immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="a1589-111">In the Data connector for dimension members field, enter or select a value.</span></span>
5. <span data-ttu-id="a1589-112">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="a1589-112">In the Description field, type a value.</span></span>
6. <span data-ttu-id="a1589-113">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="a1589-113">Click Save.</span></span>

## <a name="configure-the-data-connector"></a><span data-ttu-id="a1589-114">Configurare il connettore dati</span><span class="sxs-lookup"><span data-stu-id="a1589-114">Configure the data connector</span></span>
1. <span data-ttu-id="a1589-115">Fare clic su Configura provider membro di dimensione.</span><span class="sxs-lookup"><span data-stu-id="a1589-115">Click Configure dimension member provider.</span></span>
    * <span data-ttu-id="a1589-116">Selezionare CostCenter per importare la dimensione CostCenter nella contabilità industriale.</span><span class="sxs-lookup"><span data-stu-id="a1589-116">Select CostCenter to import the CostCenter dimension into Cost accounting.</span></span>  
2. <span data-ttu-id="a1589-117">Nel campo Nome dimensione, selezionare Centro di costo.</span><span class="sxs-lookup"><span data-stu-id="a1589-117">In the Dimension name field, select Cost center.</span></span>
3. <span data-ttu-id="a1589-118">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="a1589-118">Click OK.</span></span>

## <a name="import-cost-centers"></a><span data-ttu-id="a1589-119">Importare i centri di costo</span><span class="sxs-lookup"><span data-stu-id="a1589-119">Import cost centers</span></span>
1. <span data-ttu-id="a1589-120">Fare clic su Importa membri di dimensione.</span><span class="sxs-lookup"><span data-stu-id="a1589-120">Click Import dimension members.</span></span>
2. <span data-ttu-id="a1589-121">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="a1589-121">Click OK.</span></span>

## <a name="view-the-imported-cost-centers"></a><span data-ttu-id="a1589-122">Visualizzare i centri di costo importati</span><span class="sxs-lookup"><span data-stu-id="a1589-122">View the imported cost centers</span></span>
1. <span data-ttu-id="a1589-123">Fare clic su Visualizza membri di dimensione.</span><span class="sxs-lookup"><span data-stu-id="a1589-123">Click View dimension members.</span></span>

