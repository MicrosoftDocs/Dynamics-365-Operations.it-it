---
title: Stornare registrazione del giornale di registrazione
description: Questo argomento descrive le funzionalità che consentono di stornare i voucher dall'elenco delle transazioni dei voucher o dai giornali finanziari.
author: MikeFalkner
manager: AnnBe
ms.date: 08/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerTransVoucher, LedgerJournalTable
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: mikefalkner
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5a5456e60f1f3cee5f83ac7f725f7e01ba5bd7a1
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/30/2019
ms.locfileid: "2248587"
---
# <a name="reverse-journal-posting"></a><span data-ttu-id="77740-103">Stornare registrazione del giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="77740-103">Reverse journal posting</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="77740-104">In questo argomento vengono descritte le funzionalità di Microsoft Dynamics 365 Finance che consentono di stornare un intero giornale di registrazione o stornare uno o più giustificativi dell'elenco delle transazioni giustificativi indipendentemente dall'origine.</span><span class="sxs-lookup"><span data-stu-id="77740-104">This topic describes capabilities Microsoft Dynamics 365 Finance that allows you to reverse an entire journal or reverse one or more vouchers from the voucher transaction list regardless of their origin.</span></span> 

## <a name="reversing-journals"></a><span data-ttu-id="77740-105">Storno dei giornali di registrazione</span><span class="sxs-lookup"><span data-stu-id="77740-105">Reversing journals</span></span>

<span data-ttu-id="77740-106">È possibile stornare singolarmente le righe del giornale di registrazione.</span><span class="sxs-lookup"><span data-stu-id="77740-106">You can reverse journal lines individually.</span></span> <span data-ttu-id="77740-107">Con lo storno della registrazione del giornale di registrazione, è inoltre possibile stornare un intero giornale finanziario.</span><span class="sxs-lookup"><span data-stu-id="77740-107">With reverse journal posting, you can also reverse an entire financial journal.</span></span> <span data-ttu-id="77740-108">Per stornare un giornale di registrazione:</span><span class="sxs-lookup"><span data-stu-id="77740-108">To reverse a journal:</span></span> 
- <span data-ttu-id="77740-109">Aprire il giornale finanziario e filtrare i giornali di registrazione pubblicati</span><span class="sxs-lookup"><span data-stu-id="77740-109">Open the financial journal and filter on posted journals</span></span>
- <span data-ttu-id="77740-110">Fare clic su Storna nel menu sulla parte superiore della pagina</span><span class="sxs-lookup"><span data-stu-id="77740-110">Click on the Reverse menu at the top of the page</span></span>
- <span data-ttu-id="77740-111">Viene visualizzato il numero totale di giustificativi e righe giustificativo nonché il totale delle righe stornate</span><span class="sxs-lookup"><span data-stu-id="77740-111">You will see the total number of vouchers and voucher lines as well as the total amount of the lines being reversed</span></span>
- <span data-ttu-id="77740-112">Selezionare Sì per utilizzare le date di transazione esistenti o No per immetterne una nuova.</span><span class="sxs-lookup"><span data-stu-id="77740-112">Select Yes to use the existing transaction dates or No to enter a new one.</span></span> <span data-ttu-id="77740-113">In alcuni casi, il periodo della transazione originale potrebbe essere chiuso e si desidera inserire una nuova data di transazione per lo storno.</span><span class="sxs-lookup"><span data-stu-id="77740-113">In some cases, the period of the original transaction may be closed and you want to enter a new transaction date for the reversal.</span></span>
- <span data-ttu-id="77740-114">Se si seleziona No, immettere una data di transazione per lo storno.</span><span class="sxs-lookup"><span data-stu-id="77740-114">If you selected No, enter a transaction date for the reversal.</span></span> 
- <span data-ttu-id="77740-115">Immettere un commento che si desidera aggiungere alla transazione di storno</span><span class="sxs-lookup"><span data-stu-id="77740-115">Enter a comment that you want added to the reversal transaction</span></span>
- <span data-ttu-id="77740-116">Fare clic sul pulsante Storna</span><span class="sxs-lookup"><span data-stu-id="77740-116">Click the Reverse button</span></span>

<span data-ttu-id="77740-117">Le transazioni saranno stornate.</span><span class="sxs-lookup"><span data-stu-id="77740-117">The transactions will be reversed.</span></span> 

<span data-ttu-id="77740-118">Se il numero di righe giustificativo supera le 100 righe, il processo di storno verrà eseguito utilizzando il processo batch.</span><span class="sxs-lookup"><span data-stu-id="77740-118">If the number of voucher lines exceeds 100 lines, the reversal process will be run using the batch process.</span></span> <span data-ttu-id="77740-119">È possibile rivedere i risultati dello storno visualizzando i commenti nel processo batch che è stato eseguito.</span><span class="sxs-lookup"><span data-stu-id="77740-119">You can review the results of the reversal by viewing the comments in the batch job that was run.</span></span> <span data-ttu-id="77740-120">Tutti gli errori verranno annotati nella cronologia dei processi batch.</span><span class="sxs-lookup"><span data-stu-id="77740-120">All failures will be noted in the batch job history.</span></span>

<span data-ttu-id="77740-121">Se il numero di righe giustificativo è pari o inferiore a 100 righe, il processo di storno verrà eseguito immediatamente.</span><span class="sxs-lookup"><span data-stu-id="77740-121">If the number of voucher lines is 100 lines or less, the reversal process will run immediately.</span></span> <span data-ttu-id="77740-122">I risultati verranno visualizzati in una finestra di dialogo contenente tutti i giustificativi che non è possibile stornare e il motivo per cui non possono essere stornati.</span><span class="sxs-lookup"><span data-stu-id="77740-122">The results will be presented in a dialog that shows any voucher that could not be reversed and the reason why it could not be reversed.</span></span> <span data-ttu-id="77740-123">Fare clic su OK per chiudere la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="77740-123">Click on Ok to close the dialog.</span></span>

## <a name="reversing-vouchers-from-the-voucher-transaction-list"></a><span data-ttu-id="77740-124">Storno di giustificativi dall'elenco delle transazioni giustificativi.</span><span class="sxs-lookup"><span data-stu-id="77740-124">Reversing vouchers from the voucher transaction list.</span></span> 

<span data-ttu-id="77740-125">È inoltre possibile stornare i giustificativi dall'**elenco transazioni per giustificativo** in tutti i giornali di registrazione secondari .</span><span class="sxs-lookup"><span data-stu-id="77740-125">You can also reverse vouchers from the **Voucher transaction list** across all subledgers.</span></span> <span data-ttu-id="77740-126">Inoltre, è possibile stornare più di un giustificativo per volta.</span><span class="sxs-lookup"><span data-stu-id="77740-126">In addition, you can reverse more than one voucher at a time.</span></span> 

<span data-ttu-id="77740-127">Per stornare uno o più giustificativi:</span><span class="sxs-lookup"><span data-stu-id="77740-127">To reverse one or more vouchers:</span></span> 
- <span data-ttu-id="77740-128">Fare clic su Storna nel menu sulla parte superiore della pagina</span><span class="sxs-lookup"><span data-stu-id="77740-128">Click on the Reverse menu at the top of the page</span></span>
- <span data-ttu-id="77740-129">Viene visualizzato il numero totale di giustificativi e righe giustificativo nonché il totale delle righe stornate</span><span class="sxs-lookup"><span data-stu-id="77740-129">You will see the total number of vouchers and voucher lines as well as the total amount of the lines being reversed</span></span>
- <span data-ttu-id="77740-130">Selezionare Sì per utilizzare le date di transazione esistenti o No per immetterne una nuova.</span><span class="sxs-lookup"><span data-stu-id="77740-130">Select Yes to use the existing transaction dates or No to enter a new one.</span></span> <span data-ttu-id="77740-131">In alcuni casi, il periodo della transazione originale potrebbe essere chiuso e si desidera inserire una nuova data di transazione per lo storno.</span><span class="sxs-lookup"><span data-stu-id="77740-131">In some cases, the period of the original transaction may be closed and you want to enter a new transaction date for the reversal.</span></span>
- <span data-ttu-id="77740-132">Se si seleziona No, immettere una data di transazione per lo storno.</span><span class="sxs-lookup"><span data-stu-id="77740-132">If you selected No, enter a transaction date for the reversal.</span></span> 
- <span data-ttu-id="77740-133">Immettere un commento che si desidera aggiungere alla transazione di storno</span><span class="sxs-lookup"><span data-stu-id="77740-133">Enter a comment that you want added to the reversal transaction</span></span>
- <span data-ttu-id="77740-134">Fare clic sul pulsante Storna</span><span class="sxs-lookup"><span data-stu-id="77740-134">Click the Reverse button</span></span>

<span data-ttu-id="77740-135">Le transazioni saranno stornate.</span><span class="sxs-lookup"><span data-stu-id="77740-135">The transactions will be reversed.</span></span> 

<span data-ttu-id="77740-136">Se il numero di righe giustificativo supera le 100 righe, il processo di storno verrà eseguito utilizzando il processo batch.</span><span class="sxs-lookup"><span data-stu-id="77740-136">If the number of voucher lines exceeds 100 lines, the reversal process will be run using the batch process.</span></span> <span data-ttu-id="77740-137">È possibile rivedere i risultati dello storno visualizzando i commenti nel processo batch che è stato eseguito.</span><span class="sxs-lookup"><span data-stu-id="77740-137">You can review the results of the reversal by viewing the comments in the batch job that was run.</span></span> <span data-ttu-id="77740-138">Tutti gli errori verranno annotati nella cronologia dei processi batch.</span><span class="sxs-lookup"><span data-stu-id="77740-138">All failures will be noted in the batch job history.</span></span>

<span data-ttu-id="77740-139">Se il numero di righe giustificativo è pari o inferiore a 100 righe, il processo di storno verrà eseguito immediatamente.</span><span class="sxs-lookup"><span data-stu-id="77740-139">If the number of voucher lines is 100 lines or less, the reversal process will run immediately.</span></span> <span data-ttu-id="77740-140">I risultati verranno visualizzati in una finestra di dialogo contenente tutti i giustificativi che non è possibile stornare e il motivo per cui non possono essere stornati.</span><span class="sxs-lookup"><span data-stu-id="77740-140">The results will be presented in a dialog that shows any voucher that could not be reversed and the reason why it could not be reversed.</span></span> <span data-ttu-id="77740-141">Fare clic su OK per chiudere la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="77740-141">Click on Ok to close the dialog.</span></span>

