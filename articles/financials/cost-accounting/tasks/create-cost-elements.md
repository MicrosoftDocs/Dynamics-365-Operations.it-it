--- 
title: 'Creare elementi di costo  '
description: "Esistono vari modi per creare gli elementi di costo nella contabilità industriale."
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
ms.openlocfilehash: 1e665fc53455e457a2488f4ec28ebb5b715d90eb
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---
# <a name="create-cost-elements"></a><span data-ttu-id="2a28e-103">Creare elementi di costo  </span><span class="sxs-lookup"><span data-stu-id="2a28e-103">Create cost elements</span></span> 

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="2a28e-104">Esistono vari modi per creare gli elementi di costo nella contabilità industriale.</span><span class="sxs-lookup"><span data-stu-id="2a28e-104">There are several ways to create cost elements in Cost accounting.</span></span> <span data-ttu-id="2a28e-105">In questa procedura viene illustrato come creare elementi di costo importando i conti principali tramite un connettore dati.</span><span class="sxs-lookup"><span data-stu-id="2a28e-105">This procedure shows how to create cost elements by importing main accounts via a data connector.</span></span> <span data-ttu-id="2a28e-106">La società di dati dimostrativi USMF è stata utilizzata per creare questa procedura.</span><span class="sxs-lookup"><span data-stu-id="2a28e-106">The USMF demo company was used to create this procedure.</span></span> <span data-ttu-id="2a28e-107">Questa procedura è per una funzionalità di Contabilità industriale che è stata aggiunta in Dynamics 365 for Operations, versione 1611.</span><span class="sxs-lookup"><span data-stu-id="2a28e-107">This procedure is for a Cost accounting feature that was added in Dynamics 365 for Operations, version 1611.</span></span>


## <a name="create-new-cost-elements"></a><span data-ttu-id="2a28e-108">Creare nuovi elementi di costo</span><span class="sxs-lookup"><span data-stu-id="2a28e-108">Create new cost elements</span></span>
1. <span data-ttu-id="2a28e-109">Passare a Contabilità industriale > Dimensioni > Dimensioni elemento di costo.</span><span class="sxs-lookup"><span data-stu-id="2a28e-109">Go to Cost accounting > Dimensions > Cost element dimensions.</span></span>
2. <span data-ttu-id="2a28e-110">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="2a28e-110">Click New.</span></span>
3. <span data-ttu-id="2a28e-111">Digitare un valore nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="2a28e-111">In the Name field, type a value.</span></span>
4. <span data-ttu-id="2a28e-112">Nel campo Connettore dati per membri di dimensione immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="2a28e-112">In the Data connector for dimension members field, enter or select a value.</span></span>
5. <span data-ttu-id="2a28e-113">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="2a28e-113">In the Description field, type a value.</span></span>
6. <span data-ttu-id="2a28e-114">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="2a28e-114">Click Save.</span></span>

## <a name="configure-the-data-connector"></a><span data-ttu-id="2a28e-115">Configurare il connettore dati</span><span class="sxs-lookup"><span data-stu-id="2a28e-115">Configure the data connector</span></span>
1. <span data-ttu-id="2a28e-116">Fare clic su Configura provider membro di dimensione.</span><span class="sxs-lookup"><span data-stu-id="2a28e-116">Click Configure dimension member provider.</span></span>
2. <span data-ttu-id="2a28e-117">Nel campo Piano dei conti immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="2a28e-117">In the Chart of accounts field, enter or select a value.</span></span>
    * <span data-ttu-id="2a28e-118">Selezionare Condiviso per utilizzare un piano dei conti condiviso.</span><span class="sxs-lookup"><span data-stu-id="2a28e-118">Select Shared to use the shared chart of accounts.</span></span>  
3. <span data-ttu-id="2a28e-119">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="2a28e-119">Click New.</span></span>
4. <span data-ttu-id="2a28e-120">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="2a28e-120">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="2a28e-121">È possibile applicare filtri ai conti per soddisfare i criteri.</span><span class="sxs-lookup"><span data-stu-id="2a28e-121">You can apply filters to accounts to meet your criteria.</span></span>  
5. <span data-ttu-id="2a28e-122">Nel campo Da conto principale, immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="2a28e-122">In the From main account field, enter or select a value.</span></span>
6. <span data-ttu-id="2a28e-123">Nel campo A conto principale, immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="2a28e-123">In the To main account field, enter or select a value.</span></span>
7. <span data-ttu-id="2a28e-124">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="2a28e-124">Click OK.</span></span>

## <a name="import-main-accounts"></a><span data-ttu-id="2a28e-125">Importa conti principali</span><span class="sxs-lookup"><span data-stu-id="2a28e-125">Import main accounts</span></span>
1. <span data-ttu-id="2a28e-126">Fare clic su Importa membri di dimensione.</span><span class="sxs-lookup"><span data-stu-id="2a28e-126">Click Import dimension members.</span></span>
    * <span data-ttu-id="2a28e-127">I conti principali verranno importati nella contabilità industriale e utilizzati come elementi di costo.</span><span class="sxs-lookup"><span data-stu-id="2a28e-127">Main accounts will be imported into Cost accounting and used as cost elements.</span></span>  
2. <span data-ttu-id="2a28e-128">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="2a28e-128">Click OK.</span></span>

## <a name="view-the-imported-accounts-as-cost-elements"></a><span data-ttu-id="2a28e-129">Visualizzare i conti importati come elementi di costo</span><span class="sxs-lookup"><span data-stu-id="2a28e-129">View the imported accounts as cost elements</span></span>
1. <span data-ttu-id="2a28e-130">Fare clic su Visualizza membri di dimensione.</span><span class="sxs-lookup"><span data-stu-id="2a28e-130">Click View dimension members.</span></span>
    * <span data-ttu-id="2a28e-131">Consente di visualizzare i conti CoGe importati come elementi di costo nell'azienda in cui i costi possono fluire.</span><span class="sxs-lookup"><span data-stu-id="2a28e-131">View the imported ledger accounts as cost elements in your business that costs can flow to.</span></span>  


