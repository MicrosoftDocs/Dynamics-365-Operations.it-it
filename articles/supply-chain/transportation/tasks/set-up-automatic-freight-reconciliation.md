---
title: Impostare la riconciliazione trasporto automatica
description: In questa procedura viene illustrato come impostare i dati per la riconciliazione automatica di trasporto.
author: ShylaThompson
manager: tfehr
ms.date: 10/16/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TMSFreightBillType, TMSFreightBillTypeAssignment, TMSCarrierCodeLookup, DefaultDashboard, TMSAuditMaster
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4bfd96fcae78fd0fe383781112c17c7a3b5ea1d3
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4974012"
---
# <a name="set-up-automatic-freight-reconciliation"></a><span data-ttu-id="bc727-103">Impostare la riconciliazione trasporto automatica</span><span class="sxs-lookup"><span data-stu-id="bc727-103">Set up automatic freight reconciliation</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="bc727-104">In questa procedura viene illustrato come impostare i dati per la riconciliazione automatica di trasporto.</span><span class="sxs-lookup"><span data-stu-id="bc727-104">This procedure shows how to set up data for automatic freight reconciliation.</span></span> <span data-ttu-id="bc727-105">Il processo è in genere eseguito da un amministratore di magazzino.</span><span class="sxs-lookup"><span data-stu-id="bc727-105">This is typically done by a warehouse manager.</span></span> <span data-ttu-id="bc727-106">È possibile utilizzare questa procedura nella società di dati dimostrativi USMF.</span><span class="sxs-lookup"><span data-stu-id="bc727-106">You can use this procedure in demo data company USMF.</span></span>


## <a name="set-up-the-freight-bill-type"></a><span data-ttu-id="bc727-107">Impostare il tipo di fattura di trasporto</span><span class="sxs-lookup"><span data-stu-id="bc727-107">Set up the freight bill type</span></span>
1. <span data-ttu-id="bc727-108">Passare a Gestione trasporto > Impostazione > Riconciliazione trasporto > Tipo di fattura trasporto.</span><span class="sxs-lookup"><span data-stu-id="bc727-108">Go to Transportation management > Setup > Freight reconciliation > Freight bill type.</span></span>
    * <span data-ttu-id="bc727-109">Il tipo di fattura di trasporto determina come le fatture di trasporto e le fatture vettore devono essere associate.</span><span class="sxs-lookup"><span data-stu-id="bc727-109">The freight bill type defines how freight bills and carrier invoices  should be matched.</span></span>  
2. <span data-ttu-id="bc727-110">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="bc727-110">Click New.</span></span>
3. <span data-ttu-id="bc727-111">Nel campo Tipo di fattura trasporto, digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="bc727-111">In the Freight bill type field, type a value.</span></span>
4. <span data-ttu-id="bc727-112">Nel campo Assembly motore digitare "Microsoft.Dynamics.Ax.Tms.dll".</span><span class="sxs-lookup"><span data-stu-id="bc727-112">In the Engine assembly field, type 'Microsoft.Dynamics.Ax.Tms.dll'.</span></span>
    * <span data-ttu-id="bc727-113">Si tratta della libreria di codice del motore di associazione gestione trasporto standard.</span><span class="sxs-lookup"><span data-stu-id="bc727-113">This is the standard Transportation management matching engine code library.</span></span>  
5. <span data-ttu-id="bc727-114">Nel campo Classe motore digitare "Microsoft.Dynamics.Ax.Tms.Bll.GenericNormalizer".</span><span class="sxs-lookup"><span data-stu-id="bc727-114">In the Engine class field, type 'Microsoft.Dynamics.Ax.Tms.Bll.GenericNormalizer'.</span></span>
    * <span data-ttu-id="bc727-115">Si tratta della classe del motore di associazione gestione trasporto standard.</span><span class="sxs-lookup"><span data-stu-id="bc727-115">This is the standard Transportation management matching engine class.</span></span>  
6. <span data-ttu-id="bc727-116">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="bc727-116">Click New.</span></span>
7. <span data-ttu-id="bc727-117">Nel campo Descrizione, selezionare il valore che deve corrispondere sulla fattura di trasporto e sulla fattura del vettore.</span><span class="sxs-lookup"><span data-stu-id="bc727-117">In the Description field, choose the value that should match on the freight bill and the carrier invoice.</span></span>  
8. <span data-ttu-id="bc727-118">Selezionare 'Sì' nel campo Corrispondenza necessaria.</span><span class="sxs-lookup"><span data-stu-id="bc727-118">In the Match required field, select 'Yes'.</span></span>
    * <span data-ttu-id="bc727-119">Se si imposta il campo su Sì questo significa che il valore selezionato nel campo Descrizione deve corrispondere sia sulla fattura di trasporto che sulla fattura del vettore.</span><span class="sxs-lookup"><span data-stu-id="bc727-119">If you set this field to Yes this means that the value selected in the Description field needs to match on both the freight bill and the carrier invoice.</span></span> <span data-ttu-id="bc727-120">Se viene impostato su No, il campo può essere vuoto in una di queste.</span><span class="sxs-lookup"><span data-stu-id="bc727-120">If you set it to No, the field can be blank on one of these.</span></span>  
9. <span data-ttu-id="bc727-121">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="bc727-121">Click Save.</span></span>

## <a name="set-up-the-freight-bill-type-assignment"></a><span data-ttu-id="bc727-122">Impostare l'assegnazione del tipo di fattura di trasporto</span><span class="sxs-lookup"><span data-stu-id="bc727-122">Set up the freight bill type assignment</span></span>
1. <span data-ttu-id="bc727-123">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="bc727-123">Close the page.</span></span>
2. <span data-ttu-id="bc727-124">Passare a Gestione trasporto > Impostazione > Riconciliazione trasporto > Assegnazioni tipo di fattura di trasporto.</span><span class="sxs-lookup"><span data-stu-id="bc727-124">Go to Transportation management > Setup > Freight reconciliation > Freight bill type assignments.</span></span>
    * <span data-ttu-id="bc727-125">L'assegnazione del tipo di fattura di trasporto viene utilizzata per specificare il tipo di fattura di trasporto utilizzato per un vettore specifico.</span><span class="sxs-lookup"><span data-stu-id="bc727-125">The freight bill type assignment is used to specify which freight bill type is used for a particular carrier.</span></span>   
3. <span data-ttu-id="bc727-126">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="bc727-126">Click New.</span></span>
4. <span data-ttu-id="bc727-127">Nel campo Modo immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="bc727-127">In the Mode field, enter or select a value.</span></span>
5. <span data-ttu-id="bc727-128">Nel campo Vettore spedizione immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="bc727-128">In the Shipping carrier field, enter or select a value.</span></span>
6. <span data-ttu-id="bc727-129">Nel campo Tipo di fattura trasporto, selezionare il tipo di fattura trasporto creato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="bc727-129">In the Freight bill type field, select the freight bill type that you created earlier.</span></span>
7. <span data-ttu-id="bc727-130">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="bc727-130">Close the page.</span></span>

## <a name="set-up-the-audit-master"></a><span data-ttu-id="bc727-131">Impostare l'audit principale</span><span class="sxs-lookup"><span data-stu-id="bc727-131">Set up the audit master</span></span>
1. <span data-ttu-id="bc727-132">Passare a Gestione trasporto > Impostazione > Riconciliazione trasporto > Audit principale.</span><span class="sxs-lookup"><span data-stu-id="bc727-132">Go to Transportation management > Setup > Freight reconciliation > Audit master.</span></span>
    * <span data-ttu-id="bc727-133">I dati master di controllo definiscono i limiti di tolleranza per la riconciliazione automatica di trasporto.</span><span class="sxs-lookup"><span data-stu-id="bc727-133">The audit master defines the tolerance limits for automatic freight reconciliation.</span></span> <span data-ttu-id="bc727-134">Specificano di quanto gli importi monetari nella fattura di trasporto e nella fattura vettore possono differire e ancora ammettere la riconciliazione.</span><span class="sxs-lookup"><span data-stu-id="bc727-134">It specifies by how much the monetary amounts on the freight bill and the carrier invoice can differ and still allow reconciliation to occur.</span></span> <span data-ttu-id="bc727-135">Definiscono inoltre la modalità di gestione delle discrepanze.</span><span class="sxs-lookup"><span data-stu-id="bc727-135">It also defines how to handle discrepancies.</span></span>  
2. <span data-ttu-id="bc727-136">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="bc727-136">Click New.</span></span>
3. <span data-ttu-id="bc727-137">Immettere un valore nel campo ID audit principale.</span><span class="sxs-lookup"><span data-stu-id="bc727-137">In the Audit master ID field, type a value.</span></span>
4. <span data-ttu-id="bc727-138">Nel campo Vettore spedizione selezionare lo stesso vettore di spedizione della selezione precedente.</span><span class="sxs-lookup"><span data-stu-id="bc727-138">In the Shipping carrier  field, select the same shipping carrier as you did earlier.</span></span>
5. <span data-ttu-id="bc727-139">Nel campo Tipo di fattura trasporto, selezionare il tipo di fattura trasporto creato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="bc727-139">In the Freight bill type field, select the freight bill type that you created earlier.</span></span>
6. <span data-ttu-id="bc727-140">Espandere la sezione Tolleranza.</span><span class="sxs-lookup"><span data-stu-id="bc727-140">Expand the Tolerance section.</span></span>
7. <span data-ttu-id="bc727-141">Nel campo Livello tolleranza minima immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="bc727-141">In the Minimum tolerance level field, enter a number.</span></span>
8. <span data-ttu-id="bc727-142">Nel campo Livello tolleranza massima immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="bc727-142">In the Maximum tolerance level field, enter a number.</span></span>
9. <span data-ttu-id="bc727-143">Espandere la sezione Risultato.</span><span class="sxs-lookup"><span data-stu-id="bc727-143">Expand the Result section.</span></span>
10. <span data-ttu-id="bc727-144">Nel campo Codice motivo eccedenza di pagamento immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="bc727-144">In the Overpayment reason code field, enter or select a value.</span></span>
    * <span data-ttu-id="bc727-145">Se gli importi monetari differiscono nella fattura di trasporto e la fattura vettore, i codici motivo di eccedenza e insufficienza di pagamento specificano i conti in cui la differenza deve essere registrata, a condizione che la differenza sia nei livelli di tolleranza.</span><span class="sxs-lookup"><span data-stu-id="bc727-145">If the monetary amounts differ on the freight bill and the carrier invoice, the overpayment and underpayment reason codes specify the accounts that the difference should be registered on, as long as the difference is within the tolerance levels.</span></span>  
11. <span data-ttu-id="bc727-146">Nel campo Codice motivo insufficienza di pagamento immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="bc727-146">In the Underpayment reason code field, enter or select a value.</span></span>
12. <span data-ttu-id="bc727-147">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="bc727-147">Close the page.</span></span>

