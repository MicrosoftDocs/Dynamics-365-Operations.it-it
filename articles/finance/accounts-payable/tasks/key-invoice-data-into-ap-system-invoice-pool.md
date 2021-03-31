---
title: Inserire dati fattura nel sistema di contabilità fornitore tramite un pool di fatture
description: In questo argomento viene descritto come utilizzare il registro fatture per creare fatture.
author: abruer
manager: AnnBe
ms.date: 07/31/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 670dd2ec15aa26791758ec4bea2b431482499436
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5227162"
---
# <a name="key-invoice-data-into-the-ap-system-using-invoice-pool"></a><span data-ttu-id="98b0c-103">Inserire dati fattura nel sistema di contabilità fornitore tramite un pool di fatture</span><span class="sxs-lookup"><span data-stu-id="98b0c-103">Key invoice data into the AP system using invoice pool</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="98b0c-104">In questo argomento viene descritto come utilizzare il registro fatture per creare fatture.</span><span class="sxs-lookup"><span data-stu-id="98b0c-104">This topic describes how to use the invoice register to create invoices.</span></span> <span data-ttu-id="98b0c-105">Utilizzare quindi il pool di fatture per abbinare la fattura a un ordine fornitore e per finalizzare la spesa nella pagina della fattura fornitore.</span><span class="sxs-lookup"><span data-stu-id="98b0c-105">Then use the invoice pool to match the invoice to a purchase order and finalize the expense in the vendor invoice page.</span></span>


## <a name="create-a-purchase-order"></a><span data-ttu-id="98b0c-106">Creare un ordine fornitore</span><span class="sxs-lookup"><span data-stu-id="98b0c-106">Create a purchase order</span></span>
1. <span data-ttu-id="98b0c-107">Nel pannello di navigazione, andare a **Moduli > Contabilità fornitori > Ordini fornitore > Ordini fornitore**.</span><span class="sxs-lookup"><span data-stu-id="98b0c-107">In the navigation pane, go to **Modules > Accounts payable > Purchase orders > Purchase orders**.</span></span>
2. <span data-ttu-id="98b0c-108">Selezionare **Nuovo** per creare un ordine fornitore.</span><span class="sxs-lookup"><span data-stu-id="98b0c-108">Select **New** to create a purchase order.</span></span>
3. <span data-ttu-id="98b0c-109">Nel campo **Conto fornitore** selezionare un fornitore per l'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="98b0c-109">In the **Vendor account** field, select a vendor for the drop-down list.</span></span> <span data-ttu-id="98b0c-110">Selezionare, ad esempio, il fornitore **1001**.</span><span class="sxs-lookup"><span data-stu-id="98b0c-110">For example, select vendor **1001**.</span></span>
4. <span data-ttu-id="98b0c-111">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="98b0c-111">Select **OK**.</span></span>
5. <span data-ttu-id="98b0c-112">Nel campo **Numero articolo** selezionare il numero di articolo servizi nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="98b0c-112">In the **Item number** field, select the services item number in the drop-down list.</span></span> <span data-ttu-id="98b0c-113">Selezionare, ad esempio **S0001**.</span><span class="sxs-lookup"><span data-stu-id="98b0c-113">For example, select **S0001**.</span></span> <span data-ttu-id="98b0c-114">L'importo netto è 75,00.</span><span class="sxs-lookup"><span data-stu-id="98b0c-114">The net amount is 75.00.</span></span>  <span data-ttu-id="98b0c-115">Si tratta dell'importo previsto nella fattura.</span><span class="sxs-lookup"><span data-stu-id="98b0c-115">That is the amount that we will expect on the invoice.</span></span>  
6. <span data-ttu-id="98b0c-116">Nel riquadro azioni selezionare **Acquisto**.</span><span class="sxs-lookup"><span data-stu-id="98b0c-116">On the action pane, select **Purchase**.</span></span>
7. <span data-ttu-id="98b0c-117">Selezionare **Conferma**.</span><span class="sxs-lookup"><span data-stu-id="98b0c-117">Select **Confirm**.</span></span>

## <a name="create-and-post-and-invoice"></a><span data-ttu-id="98b0c-118">Creare e registrare una fattura</span><span class="sxs-lookup"><span data-stu-id="98b0c-118">Create and post and invoice</span></span>
1. <span data-ttu-id="98b0c-119">Nel pannello di navigazione andare a **Moduli > Contabilità fornitori > Fatture > Registro fatture**.</span><span class="sxs-lookup"><span data-stu-id="98b0c-119">In the navigation pane, go to **Modules > Accounts payable > Invoices > Invoice register**.</span></span>
2. <span data-ttu-id="98b0c-120">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="98b0c-120">Select **New**.</span></span>
3. <span data-ttu-id="98b0c-121">Aprire la ricerca per selezionare il nome del registro fatture che si desidera utilizzare.</span><span class="sxs-lookup"><span data-stu-id="98b0c-121">Open the lookup to select the name of the invoice register that you want to use.</span></span>
4. <span data-ttu-id="98b0c-122">Selezionare il nome del registro fatture che si desidera utilizzare.</span><span class="sxs-lookup"><span data-stu-id="98b0c-122">Select the name of the invoice register that you want to use.</span></span>
5. <span data-ttu-id="98b0c-123">Selezionare **Righe** per aprire il registro e immettere le righe di spesa.</span><span class="sxs-lookup"><span data-stu-id="98b0c-123">Select **Lines** to open the register and enter expense lines.</span></span>
6. <span data-ttu-id="98b0c-124">Nella ricerca selezionare un fornitore.</span><span class="sxs-lookup"><span data-stu-id="98b0c-124">In the lookup, select a vendor.</span></span> <span data-ttu-id="98b0c-125">Selezionare, ad esempio, il fornitore **1001**.</span><span class="sxs-lookup"><span data-stu-id="98b0c-125">For example, select vendor **1001**.</span></span>
7. <span data-ttu-id="98b0c-126">Nel campo **Fattura** immettere il numero di fattura.</span><span class="sxs-lookup"><span data-stu-id="98b0c-126">In the **Invoice** field, enter the invoice number.</span></span>
8. <span data-ttu-id="98b0c-127">Digitare un valore nel campo **Descrizione**</span><span class="sxs-lookup"><span data-stu-id="98b0c-127">In the **Description** field, type a value.</span></span>
9. <span data-ttu-id="98b0c-128">Nel campo **Credito** immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="98b0c-128">In the **Credit** field, enter a number.</span></span>
10. <span data-ttu-id="98b0c-129">Nel campo **Ordine fornitore**, aprire l'elenco a discesa per selezionare l'ordine fornitore creato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="98b0c-129">In the **Purchase order** field, open the drop-down list to select the purchase order that you created earlier.</span></span>
11. <span data-ttu-id="98b0c-130">Nel campo **Approvata da**, evidenziare un approvatore nell'elenco a discesa e fare clic su **Seleziona** per selezionare tale approvatore.</span><span class="sxs-lookup"><span data-stu-id="98b0c-130">In the **Approved by** field, highlight an approver in the drop-down list and click **Select** to select that approver.</span></span>
12. <span data-ttu-id="98b0c-131">Selezionare **Registra**.</span><span class="sxs-lookup"><span data-stu-id="98b0c-131">Select **Post**.</span></span>

## <a name="open-an-invoice-from-the-pool-and-match-it-to-a-purchase-order-to-complete-the-invoice-process"></a><span data-ttu-id="98b0c-132">Aprire una fattura dal pool e abbinarla a un ordine fornitore per completare il processo di fatturazione</span><span class="sxs-lookup"><span data-stu-id="98b0c-132">Open an invoice from the pool and match it to a purchase order to complete the invoice process</span></span>
1. <span data-ttu-id="98b0c-133">Nel pannello di navigazione andare a **Moduli > Contabilità fornitori > Fatture > Pool fatture**.</span><span class="sxs-lookup"><span data-stu-id="98b0c-133">In the navigation pane, go to **Modules > Accounts payable > Invoices > Invoice pool**.</span></span>
2. <span data-ttu-id="98b0c-134">Selezionare **Ordine fornitore** per creare una fattura fornitore dalla fattura nel pool.</span><span class="sxs-lookup"><span data-stu-id="98b0c-134">Select **Purchase order** to create a vendor invoice from the invoice in the pool.</span></span>
3. <span data-ttu-id="98b0c-135">Selezionare la fattura che si desidera rivedere.</span><span class="sxs-lookup"><span data-stu-id="98b0c-135">Select the invoice that you want to review.</span></span>
4. <span data-ttu-id="98b0c-136">Selezionare **Aggiorna stato di abbinamento** per completare l'abbinamento.</span><span class="sxs-lookup"><span data-stu-id="98b0c-136">Select **Update match status** to complete the matching.</span></span>
5. <span data-ttu-id="98b0c-137">Nel riquadro azioni selezionare **Opzioni**.</span><span class="sxs-lookup"><span data-stu-id="98b0c-137">On the action pane, select **Options**.</span></span>
6. <span data-ttu-id="98b0c-138">Selezionare **Cambia visualizzazione**.</span><span class="sxs-lookup"><span data-stu-id="98b0c-138">Select **Change view**.</span></span>
7. <span data-ttu-id="98b0c-139">Selezionare **Visualizzazione griglia**.</span><span class="sxs-lookup"><span data-stu-id="98b0c-139">Select **Grid view**.</span></span>
8. <span data-ttu-id="98b0c-140">Selezionare **Registra**.</span><span class="sxs-lookup"><span data-stu-id="98b0c-140">Select **Post**.</span></span>
9. <span data-ttu-id="98b0c-141">Chiudere il modulo.</span><span class="sxs-lookup"><span data-stu-id="98b0c-141">Close the form.</span></span>
10. <span data-ttu-id="98b0c-142">Nel pannello di navigazione andare a **Moduli > Contabilità fornitori > Fornitori > Fornitori**.</span><span class="sxs-lookup"><span data-stu-id="98b0c-142">In the navigation pane, go to **Modules > Accounts payable > Vendors > Vendors**.</span></span>
11. <span data-ttu-id="98b0c-143">Selezionare il fornitore dell'ordine fornitore.</span><span class="sxs-lookup"><span data-stu-id="98b0c-143">Select the vendor that was on the purchase order.</span></span> <span data-ttu-id="98b0c-144">Selezionare, ad esempio, il fornitore **1001**.</span><span class="sxs-lookup"><span data-stu-id="98b0c-144">For example, select vendor **1001**.</span></span>
12. <span data-ttu-id="98b0c-145">Nel riquadro azioni, selezionare **Fornitore**.</span><span class="sxs-lookup"><span data-stu-id="98b0c-145">On the action pane, select **Vendor**.</span></span>
13. <span data-ttu-id="98b0c-146">Selezionare **Transazioni**.</span><span class="sxs-lookup"><span data-stu-id="98b0c-146">Select **Transactions**.</span></span>
14. <span data-ttu-id="98b0c-147">Selezionare la fattura creata.</span><span class="sxs-lookup"><span data-stu-id="98b0c-147">Select the invoice that you created.</span></span> <span data-ttu-id="98b0c-148">Il rateo del registro fatture è stato stornato e registrato nel conto spese appropriato.</span><span class="sxs-lookup"><span data-stu-id="98b0c-148">The invoice register accrual was reversed and posted to the appropriate expense account.</span></span>  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]