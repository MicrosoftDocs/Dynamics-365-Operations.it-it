---
title: Stornare registrazione del giornale di registrazione
description: Questo argomento descrive le funzionalità che consentono di stornare i voucher dall'elenco delle transazioni dei voucher o dai giornali finanziari.
author: MikeFalkner
ms.date: 10/08/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerTransVoucher, LedgerJournalTable
audience: Application User
ms.reviewer: roschloma
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5ab53f4b8888f77cd41ccbd7956ed307ba1b54ff
ms.sourcegitcommit: 7d0cfb359a4abc7392ddb3f0b3e9539c40b7204d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/14/2021
ms.locfileid: "5897138"
---
# <a name="reverse-journal-posting"></a><span data-ttu-id="00dc1-103">Stornare registrazione del giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="00dc1-103">Reverse journal posting</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="00dc1-104">In questo argomento vengono descritte le funzionalità di Microsoft Dynamics 365 Finance che consentono di stornare un intero giornale di registrazione o stornare uno o più giustificativi dell'elenco delle transazioni giustificativi indipendentemente dall'origine.</span><span class="sxs-lookup"><span data-stu-id="00dc1-104">This topic describes capabilities Microsoft Dynamics 365 Finance that allows you to reverse an entire journal, or reverse one or more vouchers from the voucher transaction list, regardless of their origin.</span></span> 

## <a name="reversing-journals"></a><span data-ttu-id="00dc1-105">Storno dei giornali di registrazione</span><span class="sxs-lookup"><span data-stu-id="00dc1-105">Reversing journals</span></span>

<span data-ttu-id="00dc1-106">È possibile stornare singolarmente le righe del giornale di registrazione.</span><span class="sxs-lookup"><span data-stu-id="00dc1-106">You can reverse journal lines individually.</span></span> <span data-ttu-id="00dc1-107">Con lo storno della registrazione del giornale di registrazione, è inoltre possibile stornare un intero giornale finanziario.</span><span class="sxs-lookup"><span data-stu-id="00dc1-107">With reverse journal posting, you can also reverse an entire financial journal.</span></span> <span data-ttu-id="00dc1-108">Per stornare un giornale di registrazione:</span><span class="sxs-lookup"><span data-stu-id="00dc1-108">To reverse a journal:</span></span> 

- <span data-ttu-id="00dc1-109">Aprire il giornale finanziario e filtrare i giornali di registrazione pubblicati.</span><span class="sxs-lookup"><span data-stu-id="00dc1-109">Open the financial journal and filter on posted journals.</span></span>
- <span data-ttu-id="00dc1-110">Selezionare il menu **Storna** nella parte superiore della pagina.</span><span class="sxs-lookup"><span data-stu-id="00dc1-110">Select the **Reverse** menu at the top of the page.</span></span>
- <span data-ttu-id="00dc1-111">Viene visualizzato il numero totale di giustificativi e righe giustificativo nonché il totale delle righe stornate</span><span class="sxs-lookup"><span data-stu-id="00dc1-111">You will see the total number of vouchers and voucher lines as well as the total amount of the lines being reversed</span></span>
- <span data-ttu-id="00dc1-112">Selezionare **Sì** per utilizzare le date di transazione esistenti o **No** per immetterne una nuova.</span><span class="sxs-lookup"><span data-stu-id="00dc1-112">Select **Yes** to use the existing transaction dates or **No** to enter a new one.</span></span> <span data-ttu-id="00dc1-113">In alcuni casi, il periodo della transazione originale potrebbe essere chiuso ed è necessario immettere una nuova data di transazione per lo storno.</span><span class="sxs-lookup"><span data-stu-id="00dc1-113">In some cases, the period of the original transaction may be closed and you must enter a new transaction date for the reversal.</span></span>
- <span data-ttu-id="00dc1-114">Se si seleziona **No**, immettere una data di transazione per lo storno.</span><span class="sxs-lookup"><span data-stu-id="00dc1-114">If you select **No**, enter a transaction date for the reversal.</span></span> 
- <span data-ttu-id="00dc1-115">Immettere un commento che si desidera aggiungere alla transazione di storno.</span><span class="sxs-lookup"><span data-stu-id="00dc1-115">Enter a comment that you want added to the reversal transaction.</span></span>
- <span data-ttu-id="00dc1-116">Selezionare il pulsante **Storna**.</span><span class="sxs-lookup"><span data-stu-id="00dc1-116">Select the **Reverse** button.</span></span>

<span data-ttu-id="00dc1-117">Le transazioni saranno stornate.</span><span class="sxs-lookup"><span data-stu-id="00dc1-117">The transactions will be reversed.</span></span> 

<span data-ttu-id="00dc1-118">Se il giustificativo contiene più di 100 righe, il processo di storno verrà eseguito utilizzando il processo batch.</span><span class="sxs-lookup"><span data-stu-id="00dc1-118">If the voucher contains more than 100 lines, the reversal process will run using the batch process.</span></span> <span data-ttu-id="00dc1-119">È possibile esaminare i risultati visualizzando i commenti nel processo batch.</span><span class="sxs-lookup"><span data-stu-id="00dc1-119">You can review the results by viewing the comments in the batch job.</span></span> <span data-ttu-id="00dc1-120">Tutte le transazioni che non vengono stornate sono elencate nello storico dei processi batch.</span><span class="sxs-lookup"><span data-stu-id="00dc1-120">Any transactions that couldn't be reversed will be listed in the batch job history.</span></span>

<span data-ttu-id="00dc1-121">Se il numero di righe giustificativo è pari o inferiore a 100 righe, il processo di storno verrà eseguito immediatamente.</span><span class="sxs-lookup"><span data-stu-id="00dc1-121">If the voucher contains 100 lines or fewer, the reversal process will run immediately.</span></span> <span data-ttu-id="00dc1-122">I risultati verranno visualizzati in una finestra di dialogo contenente tutti i giustificativi che non è possibile stornare con il motivo per cui non possono essere stornati.</span><span class="sxs-lookup"><span data-stu-id="00dc1-122">The results will be presented in a dialog box that shows any voucher that could not be reversed, along with the reason why it could not be reversed.</span></span> <span data-ttu-id="00dc1-123">Selezionare **OK** per chiudere la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="00dc1-123">Select **OK** to close the dialog box.</span></span>

## <a name="reversing-vouchers-from-the-voucher-transaction-list"></a><span data-ttu-id="00dc1-124">Storno di giustificativi dall'elenco delle transazioni giustificativi.</span><span class="sxs-lookup"><span data-stu-id="00dc1-124">Reversing vouchers from the voucher transaction list.</span></span> 

<span data-ttu-id="00dc1-125">È inoltre possibile stornare i giustificativi dall'**elenco transazioni per giustificativo** in tutti i giornali di registrazione secondari .</span><span class="sxs-lookup"><span data-stu-id="00dc1-125">You can also reverse vouchers from the **Voucher transaction list** across all subledgers.</span></span> <span data-ttu-id="00dc1-126">Inoltre, è possibile stornare più di un giustificativo per volta.</span><span class="sxs-lookup"><span data-stu-id="00dc1-126">In addition, you can reverse more than one voucher at a time.</span></span> 

<span data-ttu-id="00dc1-127">Per stornare uno o più giustificativi:</span><span class="sxs-lookup"><span data-stu-id="00dc1-127">To reverse one or more vouchers:</span></span> 

- <span data-ttu-id="00dc1-128">Selezionare il menu **Storna** nella parte superiore della pagina</span><span class="sxs-lookup"><span data-stu-id="00dc1-128">Select the **Reverse** menu at the top of the page</span></span>
- <span data-ttu-id="00dc1-129">Viene visualizzato il numero totale di giustificativi e righe giustificativo nonché il totale delle righe stornate.</span><span class="sxs-lookup"><span data-stu-id="00dc1-129">You will see the total number of vouchers and voucher lines as well as the total amount of the lines being reversed.</span></span>
- <span data-ttu-id="00dc1-130">Selezionare **Sì** per utilizzare le date di transazione esistenti o **No** per immetterne una nuova.</span><span class="sxs-lookup"><span data-stu-id="00dc1-130">Select **Yes** to use the existing transaction dates or **No** to enter a new one.</span></span> <span data-ttu-id="00dc1-131">In alcuni casi, il periodo della transazione originale potrebbe essere chiuso ed è necessario immettere una nuova data di transazione per lo storno.</span><span class="sxs-lookup"><span data-stu-id="00dc1-131">In some cases, the period of the original transaction may be closed and you must enter a new transaction date to reverse it.</span></span>
- <span data-ttu-id="00dc1-132">Se si seleziona **No**, immettere una data di transazione per lo storno.</span><span class="sxs-lookup"><span data-stu-id="00dc1-132">If you select **No**, enter a transaction date for the reversal.</span></span> 
- <span data-ttu-id="00dc1-133">Immettere un commento per descrivere la transazione di storno.</span><span class="sxs-lookup"><span data-stu-id="00dc1-133">Enter a comment to describe the reversal transaction.</span></span>
- <span data-ttu-id="00dc1-134">Selezionare il pulsante **Storna**.</span><span class="sxs-lookup"><span data-stu-id="00dc1-134">Select the **Reverse** button.</span></span>

<span data-ttu-id="00dc1-135">Le transazioni saranno stornate.</span><span class="sxs-lookup"><span data-stu-id="00dc1-135">The transactions will be reversed.</span></span> 

<span data-ttu-id="00dc1-136">Se il giustificativo include più di 100 righe, il processo di storno verrà eseguito utilizzando il processo batch.</span><span class="sxs-lookup"><span data-stu-id="00dc1-136">If there are more than 100 voucher lines, the reversal process will run using the batch process.</span></span> <span data-ttu-id="00dc1-137">È possibile esaminare i risultati visualizzando i commenti nel processo batch.</span><span class="sxs-lookup"><span data-stu-id="00dc1-137">You can review the results by viewing the comments in the batch job.</span></span> <span data-ttu-id="00dc1-138">Tutte le transazioni che non vengono stornate sono riportate nello storico dei processi batch.</span><span class="sxs-lookup"><span data-stu-id="00dc1-138">Any transactions that couldn't be reversed will be noted in the batch job history.</span></span>

<span data-ttu-id="00dc1-139">Se il numero di righe giustificativo è pari o inferiore a 100 righe, il processo di storno verrà eseguito immediatamente.</span><span class="sxs-lookup"><span data-stu-id="00dc1-139">If the number of voucher lines is 100 lines or fewer, the reversal process will run immediately.</span></span> <span data-ttu-id="00dc1-140">I risultati verranno visualizzati in una finestra di dialogo contenente tutti i giustificativi che non è possibile stornare insieme al motivo.</span><span class="sxs-lookup"><span data-stu-id="00dc1-140">The results will display in a dialog box that shows any voucher that couldn't be reversed, along with the reason why.</span></span> <span data-ttu-id="00dc1-141">Selezionare **OK** per chiudere la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="00dc1-141">Select **OK** to close the dialog box.</span></span>

<span data-ttu-id="00dc1-142">Le transazioni possono essere stornate solo se soddisfano le regole business per lo storno.</span><span class="sxs-lookup"><span data-stu-id="00dc1-142">Transactions can be reversed only if they meet the business rules for reversing them.</span></span> <span data-ttu-id="00dc1-143">I pagamenti fornitore non possono essere stornati utilizzando la funzionalità descritta in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="00dc1-143">Vendor payments cannot be reversed using the capability described in this topic.</span></span> <span data-ttu-id="00dc1-144">I pagamenti fornitore devono essere stornati tramite i passaggi elencati in [Stornare un pagamento fornitore](../accounts-payable/reverse-vendor-payment.md).</span><span class="sxs-lookup"><span data-stu-id="00dc1-144">Vendor payments must be reversed by following the steps listed in [Reverse a vendor payment](../accounts-payable/reverse-vendor-payment.md).</span></span>



[!INCLUDE[footer-include](../../includes/footer-banner.md)]