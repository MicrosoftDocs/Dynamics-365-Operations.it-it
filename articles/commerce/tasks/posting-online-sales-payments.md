---
title: Registrazione di vendite e pagamenti online
description: In questa procedura vengono descritti i passaggi per configurare ed eseguire un processo batch ricorrente al fine di creare ordini cliente e pagamenti per le transazioni punto vendita online.
author: psimolin
manager: AnnBe
ms.date: 08/06/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailChannelOperationsWorkspace, RetailOperatingUnitPicker, SysRecurrence
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e24c2be8a1b0da3c34919fdb44aa744f8e7fc87c
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5215414"
---
# <a name="posting-of-online-sales-and-payments"></a><span data-ttu-id="10059-103">Registrazione di vendite e pagamenti online</span><span class="sxs-lookup"><span data-stu-id="10059-103">Posting of online sales and payments</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="10059-104">In questa procedura vengono descritti i passaggi per configurare ed eseguire un processo batch ricorrente al fine di creare ordini cliente e pagamenti per le transazioni punto vendita online.</span><span class="sxs-lookup"><span data-stu-id="10059-104">This procedure walks through configuring and running a recurrent batch job to create sales orders and payments for online store transactions.</span></span>

<span data-ttu-id="10059-105">La registrazione di vendite e pagamenti online è un processo a due fasi.</span><span class="sxs-lookup"><span data-stu-id="10059-105">Posting online sales and payments is a two-stage process.</span></span>

- <span data-ttu-id="10059-106">Pull dei dati transazione di commercio nella sede centrale.</span><span class="sxs-lookup"><span data-stu-id="10059-106">Pulling the online commerce transaction data in HQ.</span></span>
- <span data-ttu-id="10059-107">Sincronizzazione di ordini per creare ordini cliente nella sede centrale.</span><span class="sxs-lookup"><span data-stu-id="10059-107">Synchronizing orders to create sales orders in HQ.</span></span>

<span data-ttu-id="10059-108">Il pull dei dati transazione online può essere effettuato eseguendo manualmente il P-Job o creando un processo batch ricorrente.</span><span class="sxs-lookup"><span data-stu-id="10059-108">Pulling the online transaction data can be done either by manually running the P-job or by creating a recurrent batch job.</span></span>

### <a name="manually-running-the-p-job"></a><span data-ttu-id="10059-109">Esecuzione manuale del P-job</span><span class="sxs-lookup"><span data-stu-id="10059-109">Manually running the P-job</span></span>

1. <span data-ttu-id="10059-110">Passare a Tutte le aree di lavoro > Vendita al dettaglio e commercio IT.</span><span class="sxs-lookup"><span data-stu-id="10059-110">Go to All workspaces > Retail and Commerce IT.</span></span>
2. <span data-ttu-id="10059-111">Fare clic su Programmazione della distribuzione.</span><span class="sxs-lookup"><span data-stu-id="10059-111">Click Distribution schedule.</span></span>
3. <span data-ttu-id="10059-112">Selezionare P-0001.</span><span class="sxs-lookup"><span data-stu-id="10059-112">Select P-0001.</span></span>
4. <span data-ttu-id="10059-113">Modificare i gruppi di database canale, se necessario.</span><span class="sxs-lookup"><span data-stu-id="10059-113">Adjust channel database groups, if required.</span></span>
5. <span data-ttu-id="10059-114">Fare clic su Esegui adesso.</span><span class="sxs-lookup"><span data-stu-id="10059-114">Click Run now.</span></span>
6. <span data-ttu-id="10059-115">Fare clic su Sì.</span><span class="sxs-lookup"><span data-stu-id="10059-115">Click Yes.</span></span>

### <a name="scheduling-a-recurring-p-job"></a><span data-ttu-id="10059-116">Programmazione di un P-job ricorrente</span><span class="sxs-lookup"><span data-stu-id="10059-116">Scheduling a recurring P-job</span></span>

1. <span data-ttu-id="10059-117">Passare a Tutte le aree di lavoro > Vendita al dettaglio e commercio IT.</span><span class="sxs-lookup"><span data-stu-id="10059-117">Go to All workspaces > Retail and Commerce IT.</span></span>
2. <span data-ttu-id="10059-118">Fare clic su Programmazione della distribuzione.</span><span class="sxs-lookup"><span data-stu-id="10059-118">Click Distribution schedule.</span></span>
3. <span data-ttu-id="10059-119">Selezionare P-0001.</span><span class="sxs-lookup"><span data-stu-id="10059-119">Select P-0001.</span></span>
4. <span data-ttu-id="10059-120">Fare clic su Crea processo batch.</span><span class="sxs-lookup"><span data-stu-id="10059-120">Click Create batch job.</span></span>
5. <span data-ttu-id="10059-121">Fare clic su Esecuzione in background.</span><span class="sxs-lookup"><span data-stu-id="10059-121">Click Run in the background.</span></span>
5. <span data-ttu-id="10059-122">Abilitare Elaborazione batch.</span><span class="sxs-lookup"><span data-stu-id="10059-122">Enable Batch processing.</span></span>
6. <span data-ttu-id="10059-123">Fare clic su Ricorrenza.</span><span class="sxs-lookup"><span data-stu-id="10059-123">Click Recurrence..</span></span>
7. <span data-ttu-id="10059-124">Selezionare l'opzione Nessuna data di fine.</span><span class="sxs-lookup"><span data-stu-id="10059-124">Select the No end date option.</span></span>
8. <span data-ttu-id="10059-125">Nel campo Conteggio, immettere un intervallo in minuti tra le esecuzioni.</span><span class="sxs-lookup"><span data-stu-id="10059-125">In the Count field, enter interval between the runs in minutes.</span></span> <span data-ttu-id="10059-126">In genere il valore è 5-10.</span><span class="sxs-lookup"><span data-stu-id="10059-126">Typically this would be 5-10.</span></span>
9. <span data-ttu-id="10059-127">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="10059-127">Click OK.</span></span>
10. <span data-ttu-id="10059-128">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="10059-128">Click OK.</span></span>

<span data-ttu-id="10059-129">Gli ordini possono essere sincronizzati eseguendo manualmente il processo "Sincronizza ordini" o creando un processo batch ricorrente.</span><span class="sxs-lookup"><span data-stu-id="10059-129">Orders can be synchronized either by manually running the "Synchronize orders"-job or by creating a recurring batch job.</span></span>

### <a name="manually-running-order-synchronization"></a><span data-ttu-id="10059-130">Esecuzione manuale della sincronizzazione degli ordini</span><span class="sxs-lookup"><span data-stu-id="10059-130">Manually running order synchronization</span></span> 

<span data-ttu-id="10059-131">Seguire questi passaggi per eseguire manualmente il processo "Sincronizza ordini" una volta.</span><span class="sxs-lookup"><span data-stu-id="10059-131">Follow these steps to manually run "Synchronize orders" job once.</span></span>

1. <span data-ttu-id="10059-132">Passare a Tutte le aree di lavoro > Dati finanziari punto vendita al dettaglio.</span><span class="sxs-lookup"><span data-stu-id="10059-132">Go to All workspaces > Store financials.</span></span>
2. <span data-ttu-id="10059-133">Fare clic su Sincronizza ordini.</span><span class="sxs-lookup"><span data-stu-id="10059-133">Click Synchronize orders.</span></span>
3. <span data-ttu-id="10059-134">Nel campo Gerarchia organizzativa, selezionare "Punti vendita per area".</span><span class="sxs-lookup"><span data-stu-id="10059-134">In the Organization hierarchy field, select 'Stores by Region'.</span></span>
    * <span data-ttu-id="10059-135">Selezionare un punto vendita online specifico o un nodo se si desidera creare il processo batch per un gruppo di punti vendita.</span><span class="sxs-lookup"><span data-stu-id="10059-135">Select either a specific online store, or select a node if you want to create the batch job for a group of stores.</span></span>  
    * <span data-ttu-id="10059-136">Fare clic sulla freccia per aggiungere la selezione.</span><span class="sxs-lookup"><span data-stu-id="10059-136">Click the arrow to add your selection.</span></span>  
4. <span data-ttu-id="10059-137">Fare clic sulla scheda Esecuzione in background.</span><span class="sxs-lookup"><span data-stu-id="10059-137">Click the Run in the background tab.</span></span>
5. <span data-ttu-id="10059-138">Disabilitare Elaborazione batch.</span><span class="sxs-lookup"><span data-stu-id="10059-138">Disable Batch processing</span></span>
6. <span data-ttu-id="10059-139">Fare clic su Ricorrenza.</span><span class="sxs-lookup"><span data-stu-id="10059-139">Click Recurrence.</span></span>
7. <span data-ttu-id="10059-140">Selezionare l'opzione Fine dopo.</span><span class="sxs-lookup"><span data-stu-id="10059-140">Select End After option</span></span>
8. <span data-ttu-id="10059-141">Nel campo Fine dopo, immettere 1.</span><span class="sxs-lookup"><span data-stu-id="10059-141">In the End After field, enter 1.</span></span>
9. <span data-ttu-id="10059-142">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="10059-142">Click OK.</span></span>
10. <span data-ttu-id="10059-143">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="10059-143">Click OK.</span></span>

### <a name="scheduling-recurring-order-synchronization"></a><span data-ttu-id="10059-144">Programmazione della sincronizzazione di ordini ricorrenti</span><span class="sxs-lookup"><span data-stu-id="10059-144">Scheduling recurring order synchronization</span></span>

<span data-ttu-id="10059-145">In questa procedura vengono descritti i passaggi per configurare ed eseguire un processo batch ricorrente al fine di creare ordini cliente e pagamenti per le transazioni punto vendita online.</span><span class="sxs-lookup"><span data-stu-id="10059-145">This procedure walks through configuring and running a recurrent batch job to create sales orders and payments for online store transactions.</span></span> <span data-ttu-id="10059-146">Questa procedura utilizza i dati dimostrativi della società USRT.</span><span class="sxs-lookup"><span data-stu-id="10059-146">This procedure uses the USRT company in demo data.</span></span>

1. <span data-ttu-id="10059-147">Passare a Tutte le aree di lavoro > Dati finanziari punto vendita al dettaglio.</span><span class="sxs-lookup"><span data-stu-id="10059-147">Go to All workspaces > Store financials.</span></span>
2. <span data-ttu-id="10059-148">Fare clic su Sincronizza ordini.</span><span class="sxs-lookup"><span data-stu-id="10059-148">Click Synchronize orders.</span></span>
3. <span data-ttu-id="10059-149">Nel campo Gerarchia organizzativa, selezionare "Punti vendita per area".</span><span class="sxs-lookup"><span data-stu-id="10059-149">In the Organization hierarchy field, select 'Stores by Region'.</span></span>
    * <span data-ttu-id="10059-150">Selezionare un punto vendita online specifico o un nodo se si desidera creare il processo batch per un gruppo di punti vendita.</span><span class="sxs-lookup"><span data-stu-id="10059-150">Select either a specific online store, or select a node if you want to create the batch job for a group of stores.</span></span>  
    * <span data-ttu-id="10059-151">Fare clic sulla freccia per aggiungere la selezione.</span><span class="sxs-lookup"><span data-stu-id="10059-151">Click the arrow to add your selection.</span></span>  
4. <span data-ttu-id="10059-152">Fare clic sulla scheda Esecuzione in background.</span><span class="sxs-lookup"><span data-stu-id="10059-152">Click the Run in the background tab.</span></span>
5. <span data-ttu-id="10059-153">Abilitare Elaborazione batch.</span><span class="sxs-lookup"><span data-stu-id="10059-153">Enable Batch processing</span></span>
6. <span data-ttu-id="10059-154">Fare clic su Ricorrenza.</span><span class="sxs-lookup"><span data-stu-id="10059-154">Click Recurrence.</span></span>
7. <span data-ttu-id="10059-155">Selezionare l'opzione Nessuna data di fine.</span><span class="sxs-lookup"><span data-stu-id="10059-155">Select the No end date option.</span></span>
8. <span data-ttu-id="10059-156">Nel campo Conteggio, immettere un intervallo in minuti tra le esecuzioni.</span><span class="sxs-lookup"><span data-stu-id="10059-156">In the Count field, enter interval between the runs in minutes.</span></span> <span data-ttu-id="10059-157">In genere il valore è 2-20.</span><span class="sxs-lookup"><span data-stu-id="10059-157">Typically this would be 2-20</span></span>
9. <span data-ttu-id="10059-158">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="10059-158">Click OK.</span></span>
10. <span data-ttu-id="10059-159">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="10059-159">Click OK.</span></span>

## <a name="data-entities-involved-in-the-process"></a><span data-ttu-id="10059-160">Entità di dati coinvolte nel processo</span><span class="sxs-lookup"><span data-stu-id="10059-160">Data entities involved in the process</span></span>

- <span data-ttu-id="10059-161">RetailTransactionTable</span><span class="sxs-lookup"><span data-stu-id="10059-161">RetailTransactionTable</span></span>
- <span data-ttu-id="10059-162">RetailTransactionAddressTrans</span><span class="sxs-lookup"><span data-stu-id="10059-162">RetailTransactionAddressTrans</span></span>
- <span data-ttu-id="10059-163">RetailTransactionInfocodeTrans</span><span class="sxs-lookup"><span data-stu-id="10059-163">RetailTransactionInfocodeTrans</span></span>
- <span data-ttu-id="10059-164">RetailTransactionTaxTrans</span><span class="sxs-lookup"><span data-stu-id="10059-164">RetailTransactionTaxTrans</span></span>
- <span data-ttu-id="10059-165">RetailTransactionSalesTrans</span><span class="sxs-lookup"><span data-stu-id="10059-165">RetailTransactionSalesTrans</span></span>
- <span data-ttu-id="10059-166">RetailTransactionTaxMeasure</span><span class="sxs-lookup"><span data-stu-id="10059-166">RetailTransactionTaxMeasure</span></span>
- <span data-ttu-id="10059-167">RetailTransactionDiscountTrans</span><span class="sxs-lookup"><span data-stu-id="10059-167">RetailTransactionDiscountTrans</span></span>
- <span data-ttu-id="10059-168">RetailTransactionTaxTransGTE</span><span class="sxs-lookup"><span data-stu-id="10059-168">RetailTransactionTaxTransGTE</span></span>
- <span data-ttu-id="10059-169">RetailTransactionMarkupTrans</span><span class="sxs-lookup"><span data-stu-id="10059-169">RetailTransactionMarkupTrans</span></span>
- <span data-ttu-id="10059-170">RetailTransactionPaymentTrans</span><span class="sxs-lookup"><span data-stu-id="10059-170">RetailTransactionPaymentTrans</span></span>
- <span data-ttu-id="10059-171">RetailTransactionAttributeTrans</span><span class="sxs-lookup"><span data-stu-id="10059-171">RetailTransactionAttributeTrans</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]