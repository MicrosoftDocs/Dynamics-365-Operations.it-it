---
title: Registrare le provvigioni di vendita
description: In questo argomento viene descritto come vengono calcolate e registrate le provvigioni di vendita.
author: omulvad
manager: tfehr
ms.date: 08/06/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable, SalesEditLines,  CustInvoiceJournal, CommissionTrans, LedgerTransVoucher, CustClassificationGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 82c8dc2f284923b5583bf983413a015b9ece8252
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5205931"
---
# <a name="register-sales-commissions"></a><span data-ttu-id="77493-103">Registrare le provvigioni di vendita</span><span class="sxs-lookup"><span data-stu-id="77493-103">Register sales commissions</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="77493-104">In questo argomento viene descritto come vengono calcolate e registrate le provvigioni di vendita.</span><span class="sxs-lookup"><span data-stu-id="77493-104">This topic explains how sales commissions are calculated and registered.</span></span> <span data-ttu-id="77493-105">È possibile eseguire questa procedura nella società di dati dimostrativi USMF oppure nei propri dati.</span><span class="sxs-lookup"><span data-stu-id="77493-105">You can run this procedure in demo data company USMF or on your own data.</span></span> <span data-ttu-id="77493-106">Prima di iniziare questa guida, eseguire la guida chiamata “Impostare regole per la provvigione vendite" per assicurarsi che tutto il necessario per il calcolo della provvigione sia impostato.</span><span class="sxs-lookup"><span data-stu-id="77493-106">Before starting this guide, run the guide called "Set up sales commission rules" to make sure that you have all the necessary commission calculation setup.</span></span>

<span data-ttu-id="77493-107">Prendere nota dei numeri cliente e articolo scelti per il processo di provvigione e usarli quando chiesto per creare un ordine cliente nella guida.</span><span class="sxs-lookup"><span data-stu-id="77493-107">Take note of the customer and item numbers that you have chosen for the commission process and use them when asked to create a sales order in this guide.</span></span>


## <a name="invoice-a-sales-order-that-qualifies-a-salesperson-for-a-commission"></a><span data-ttu-id="77493-108">Fatturare un ordine cliente che qualifica un venditore per una provvigione</span><span class="sxs-lookup"><span data-stu-id="77493-108">Invoice a sales order that qualifies a salesperson for a commission</span></span>
1. <span data-ttu-id="77493-109">Nel pannello di navigazione, andare a **Moduli > Vendite e marketing > Ordini cliente > Tutti gli ordini cliente**.</span><span class="sxs-lookup"><span data-stu-id="77493-109">In the navigation pane, go to **Modules > Sales and marketing > Sales orders > All sales orders**.</span></span>
2. <span data-ttu-id="77493-110">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="77493-110">Select **New**.</span></span>
3. <span data-ttu-id="77493-111">Nel campo **Conto cliente** selezionare il record desiderato nel menu a discesa.</span><span class="sxs-lookup"><span data-stu-id="77493-111">In the **Customer account** field, select the desired record from the drop-down menu.</span></span>
4. <span data-ttu-id="77493-112">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="77493-112">Select **OK**.</span></span>
5. <span data-ttu-id="77493-113">Nel riquadro azioni selezionare **Opzioni**.</span><span class="sxs-lookup"><span data-stu-id="77493-113">On the Action Pane, select **Options**.</span></span>
6. <span data-ttu-id="77493-114">Selezionare **Cambia visualizzazione**.</span><span class="sxs-lookup"><span data-stu-id="77493-114">Select **Change view**.</span></span>
7. <span data-ttu-id="77493-115">Selezionare **Visualizzazione intestazione**.</span><span class="sxs-lookup"><span data-stu-id="77493-115">Select **Header view**.</span></span>
8. <span data-ttu-id="77493-116">Espandere la sezione **Impostazione**.</span><span class="sxs-lookup"><span data-stu-id="77493-116">Expand the **Setup** section.</span></span>

    - <span data-ttu-id="77493-117">Il valore nel campo **Gruppo vendite** rappresenta un gruppo a cui sono assegnati uno o più rappresentanti.</span><span class="sxs-lookup"><span data-stu-id="77493-117">The value in the **Sales group** field represents a group with one or more sales representatives assigned to it.</span></span> <span data-ttu-id="77493-118">Le persone nel gruppo sono quelle che ricevono le provvigioni quando l'ordine viene fatturato, secondo le percentuali e la distribuzione predefinite.</span><span class="sxs-lookup"><span data-stu-id="77493-118">The people in the group are the ones who will receive commissions when the order is invoiced, as per predefined rates and distribution.</span></span>   
    - <span data-ttu-id="77493-119">Il valore viene copiato dalla scheda Cliente, ma è possibile modificarlo se si desidera.</span><span class="sxs-lookup"><span data-stu-id="77493-119">The value is copied from the Customer card, but you can change it if you wish.</span></span>  
    - <span data-ttu-id="77493-120">Il gruppo vendite verrà copiato anche nella riga ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="77493-120">The Sales group is also copied to the sales order line.</span></span> <span data-ttu-id="77493-121">È possibile modificarlo in modo che sia diverso da quello nell'intestazione e/o tra le righe.</span><span class="sxs-lookup"><span data-stu-id="77493-121">You can change it so that it can differ from the one in the header and/or between lines.</span></span>  
    - <span data-ttu-id="77493-122">Il valore nel campo **Gruppo provvigioni** rappresenta un gruppo creato per uno o più clienti a scopo di tracciabilità delle provvigioni.</span><span class="sxs-lookup"><span data-stu-id="77493-122">The value in the **Commission group** field represents a group that you have created for one or more customers with the purpose of tracking commissions.</span></span>   
    - <span data-ttu-id="77493-123">Il valore viene copiato dalla scheda Cliente, ma è possibile modificarlo se si desidera.</span><span class="sxs-lookup"><span data-stu-id="77493-123">The value is copied from the Customer card, but you can change it if you wish.</span></span>   

9. <span data-ttu-id="77493-124">Nel riquadro azioni selezionare **Opzioni**.</span><span class="sxs-lookup"><span data-stu-id="77493-124">On the Action Pane, select **Options**.</span></span>
10. <span data-ttu-id="77493-125">Selezionare **Cambia visualizzazione**.</span><span class="sxs-lookup"><span data-stu-id="77493-125">Select **Change view**.</span></span>
11. <span data-ttu-id="77493-126">Seleziona **Visualizzazione riga**.</span><span class="sxs-lookup"><span data-stu-id="77493-126">Select **Line view**.</span></span>
12. <span data-ttu-id="77493-127">Nel menu a discesa del campo **Numero articolo**, selezionare l'articolo impostato per le provvigioni.</span><span class="sxs-lookup"><span data-stu-id="77493-127">In the drop down menu of the **Item number** field, select the item you have set up for commissions.</span></span> 
13. <span data-ttu-id="77493-128">Nel campo **Quantità** immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="77493-128">In the **Quantity** field, enter a number.</span></span> <span data-ttu-id="77493-129">Prendere nota dell'importo netto della riga.</span><span class="sxs-lookup"><span data-stu-id="77493-129">Take note of the line's Net amount.</span></span> <span data-ttu-id="77493-130">Rappresenta i ricavi di vendita, che in questo esempio costituiscono la base per il calcolo della provvigione.</span><span class="sxs-lookup"><span data-stu-id="77493-130">It represents the sales revenue, which in this example is the basis for commission calculation.</span></span>  
14. <span data-ttu-id="77493-131">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="77493-131">Select **Save**.</span></span>
15. <span data-ttu-id="77493-132">Nel riquadro azioni selezionare **Fattura**.</span><span class="sxs-lookup"><span data-stu-id="77493-132">On the Action Pane, select **Invoice**.</span></span>
16. <span data-ttu-id="77493-133">Selezionare **Fattura**.</span><span class="sxs-lookup"><span data-stu-id="77493-133">Select **Invoice**.</span></span>
17. <span data-ttu-id="77493-134">Espandere la sezione **Parametri**.</span><span class="sxs-lookup"><span data-stu-id="77493-134">Expand the **Parameters** section.</span></span>
18. <span data-ttu-id="77493-135">Nel campo **Quantità** selezionare **Tutto**.</span><span class="sxs-lookup"><span data-stu-id="77493-135">In the **Quantity** field, select **All**.</span></span>
19. <span data-ttu-id="77493-136">Selezionare **Sì** nel campo **Registrazione**.</span><span class="sxs-lookup"><span data-stu-id="77493-136">Select **Yes** in the **Posting** field.</span></span>
20. <span data-ttu-id="77493-137">Selezionare **OK**, quindi selezionare **OK** nel riquadro successivo.</span><span class="sxs-lookup"><span data-stu-id="77493-137">Select **OK**, then select **OK** in the next pane.</span></span> <span data-ttu-id="77493-138">Può richiedere qualche minuto registrare la transazione.</span><span class="sxs-lookup"><span data-stu-id="77493-138">It may take a minute or so to post the transaction.</span></span> <span data-ttu-id="77493-139">Attendere il completamento dell'elaborazione e non chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="77493-139">Allow the processing to complete and don't close the page.</span></span>  

## <a name="review-the-registered-sales-commissions"></a><span data-ttu-id="77493-140">Verificare le provvigioni vendite registrate</span><span class="sxs-lookup"><span data-stu-id="77493-140">Review the registered sales commissions</span></span>
1. <span data-ttu-id="77493-141">Nel riquadro azioni selezionare **Fattura**, quindi selezionare di nuovo **Fattura**.</span><span class="sxs-lookup"><span data-stu-id="77493-141">On the Action Pane, select **Invoice**, then select **Invoice** again.</span></span>
2. <span data-ttu-id="77493-142">Nel riquadro azioni selezionare **Fattura**, quindi selezionare **Transazioni provvigione**.</span><span class="sxs-lookup"><span data-stu-id="77493-142">On the Action Pane, select **Invoice**, then select **Commission transactions**.</span></span>

    - <span data-ttu-id="77493-143">La scheda **Panoramica** visualizza le righe che rappresentano gli importi di provvigione dovuti ai rappresentanti associati all'ordine cliente fatturato.</span><span class="sxs-lookup"><span data-stu-id="77493-143">The **Overview** tab displays lines representing the commission amounts payable to sales representatives who are associated with the invoiced sales order.</span></span> <span data-ttu-id="77493-144">Esaminiamo i dettagli.</span><span class="sxs-lookup"><span data-stu-id="77493-144">Let's review the details.</span></span>  
    - <span data-ttu-id="77493-145">Se è stata utilizzata la guida "Impostare regole per la provvigione vendite" per impostare il gruppo **vendite con provvigione**, sono presenti due venditori per ricevere le provvigioni di vendita e la provvigione è divisa equamente tra loro.</span><span class="sxs-lookup"><span data-stu-id="77493-145">If you used the "Set up sales commission rules" guide to set up the **Commission sales** group, there are two sales people to receive a sales commissions, and the commission is split equally between them.</span></span>  
    - <span data-ttu-id="77493-146">In questo esempio, l'importo totale delle provvigioni viene calcolato come percentuale di ricavi da vendite (l'importo netto della riga ordine).</span><span class="sxs-lookup"><span data-stu-id="77493-146">In this example, the total amount of the commission is calculated as a percentage of the sales revenue (the net amount of order line).</span></span>  
3. <span data-ttu-id="77493-147">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="77493-147">Close the page.</span></span>
4. <span data-ttu-id="77493-148">Seleziona **Giustificativo**.</span><span class="sxs-lookup"><span data-stu-id="77493-148">Select **Voucher**.</span></span> <span data-ttu-id="77493-149">È possibile esaminare le transazioni giustificativo per gli importi della provvigione registrati nei conti predefiniti Commissioni e Importo a debito provvigioni.</span><span class="sxs-lookup"><span data-stu-id="77493-149">You can review the voucher transactions for the commission amounts that have been posted to the predefined commission expense and commission payable accounts.</span></span>  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]