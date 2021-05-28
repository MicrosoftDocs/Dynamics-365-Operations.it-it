---
title: Le prestazioni di calcolo delle imposte influiscono sulle transazioni
description: In questo argomento vengono fornite informazioni sulla risoluzione dei problemi relativi alle prestazioni del calcolo delle imposte e al relativo effetto sulle transazioni.
author: shtao
ms.date: 04/07/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: 6fce4e2cb8c5507769533a875e23ccc4531abf51
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2021
ms.locfileid: "6020141"
---
# <a name="tax-calculation-performance-affects-transactions"></a><span data-ttu-id="208ab-103">Le prestazioni di calcolo delle imposte influiscono sulle transazioni</span><span class="sxs-lookup"><span data-stu-id="208ab-103">Tax calculation performance affects transactions</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="208ab-104">A volte, una transazione è influenzata da problemi di prestazioni dovuti al calcolo delle imposte.</span><span class="sxs-lookup"><span data-stu-id="208ab-104">Sometimes, a transaction is affected by performance issues that tax calculation is having.</span></span> <span data-ttu-id="208ab-105">Per risolvere questo problema, seguire i passaggi nelle sezioni seguenti come richiesto.</span><span class="sxs-lookup"><span data-stu-id="208ab-105">To troubleshoot this issue, follow the steps in the following sections as required.</span></span>

## <a name="review-the-transaction-line-count"></a><span data-ttu-id="208ab-106">Esaminare il numero di righe della transazione</span><span class="sxs-lookup"><span data-stu-id="208ab-106">Review the transaction line count</span></span>

<span data-ttu-id="208ab-107">Determina se la transazione ha un numero elevato di righe (ad esempio, più di diverse centinaia).</span><span class="sxs-lookup"><span data-stu-id="208ab-107">Determine whether the transaction has a large number of lines (for example, more than several hundred).</span></span> <span data-ttu-id="208ab-108">In caso contrario, passa alla sezione successiva.</span><span class="sxs-lookup"><span data-stu-id="208ab-108">If it doesn't, move on to the next section.</span></span> <span data-ttu-id="208ab-109">Se la transazione ha diverse centinaia di righe, differire il calcolo delle imposte.</span><span class="sxs-lookup"><span data-stu-id="208ab-109">If the transaction does have several hundred lines, delay the tax calculation.</span></span> <span data-ttu-id="208ab-110">Per ulteriori informazioni, vedere [Abilitare il calcolo IVA differito nei giornali di registrazione](enable-delayed-tax-calculation.md).</span><span class="sxs-lookup"><span data-stu-id="208ab-110">For more information, see [Enable delayed tax calculation on journals](enable-delayed-tax-calculation.md).</span></span> 

<span data-ttu-id="208ab-111">Successivamente, puoi determinare se una delle seguenti condizioni è soddisfatta:</span><span class="sxs-lookup"><span data-stu-id="208ab-111">Next, you can determine whether any of the following conditions are met:</span></span>

- <span data-ttu-id="208ab-112">Sono presenti transazioni di importazione da file di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="208ab-112">There are import transactions from large files.</span></span>
- <span data-ttu-id="208ab-113">Più sessioni elaborano lo stesso calcolo dell'imposta sulle transazioni contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="208ab-113">Multiple sessions process the same transaction tax calculation at the same time.</span></span>
- <span data-ttu-id="208ab-114">La transazione ha più righe e le visualizzazioni vengono aggiornate in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="208ab-114">The transaction has multiple lines, and the views are updated in real time.</span></span> <span data-ttu-id="208ab-115">Ad esempio, il campo **Importo IVA calcolato** nella pagina **Giornale di registrazione generale** viene aggiornato in tempo reale quando vengono modificati i campi di una riga.</span><span class="sxs-lookup"><span data-stu-id="208ab-115">For example, the **Calculated sales tax amount** field on the **General journal** page is updated in real time when a line's fields are changed.</span></span>

   <span data-ttu-id="208ab-116">[![Campo dell'importo IVA calcolato nella pagina del giustificativo giornale di registrazione](./media/tax-calculation-bad-performance-impacts-transaction-Picture1.png)](./media/tax-calculation-bad-performance-impacts-transaction-Picture1.png)</span><span class="sxs-lookup"><span data-stu-id="208ab-116">[![Calculated sales tax amount field on the Jounal voucher page](./media/tax-calculation-bad-performance-impacts-transaction-Picture1.png)](./media/tax-calculation-bad-performance-impacts-transaction-Picture1.png)</span></span>

<span data-ttu-id="208ab-117">Se una di queste condizioni è soddisfatta, differire il calcolo dell'imposta.</span><span class="sxs-lookup"><span data-stu-id="208ab-117">If any of these conditions are met, delay the tax calculation.</span></span>

## <a name="review-the-call-stack"></a><span data-ttu-id="208ab-118">Esaminare lo stack di chiamate</span><span class="sxs-lookup"><span data-stu-id="208ab-118">Review the call stack</span></span>

<span data-ttu-id="208ab-119">Esamina lo stack di chiamate per determinare se il calcolo delle imposte viene richiamato più volte.</span><span class="sxs-lookup"><span data-stu-id="208ab-119">Review the call stack to determine whether tax calculation is called multiple times.</span></span> <span data-ttu-id="208ab-120">In caso contrario, passa alla sezione successiva.</span><span class="sxs-lookup"><span data-stu-id="208ab-120">If it isn't, move on to the next section.</span></span> <span data-ttu-id="208ab-121">Se lo stack di chiamate viene chiamato più volte, attenersi alla seguente procedura per ridurre i tempi di calcolo delle imposte.</span><span class="sxs-lookup"><span data-stu-id="208ab-121">If the call stack is called multiple times, follow these steps to help reduce the tax calculation times.</span></span>

1. <span data-ttu-id="208ab-122">Se il giornale di registrazione ha considerato la transazione, differire il calcolo dell'imposta.</span><span class="sxs-lookup"><span data-stu-id="208ab-122">If the journal has considered the transaction, delay the tax calculation.</span></span> <span data-ttu-id="208ab-123">Per ulteriori informazioni, vedere [Abilitare il calcolo IVA differito nei giornali di registrazione](enable-delayed-tax-calculation.md).</span><span class="sxs-lookup"><span data-stu-id="208ab-123">For more information, see [Enable delayed tax calculation on journals](enable-delayed-tax-calculation.md).</span></span>
2. <span data-ttu-id="208ab-124">Se la transazione è un ordine fornitore e la versione dell'applicazione è successiva alla 10.0.15, è possibile differire il calcolo delle imposte fino al calcolo finale abilitando la versione di anteprima per **PurchTableChangeMgmtDistributionUpdateOnToggle_KillSwitch**.</span><span class="sxs-lookup"><span data-stu-id="208ab-124">If the transaction is a purchase order, and the application version is later than 10.0.15, you can delay the tax calculation until the final calculation by enabling the flighting for **PurchTableChangeMgmtDistributionUpdateOnToggle_KillSwitch**.</span></span>

## <a name="review-the-call-stack-timeline"></a><span data-ttu-id="208ab-125">Esaminare la sequenza temporale dello stack di chiamate</span><span class="sxs-lookup"><span data-stu-id="208ab-125">Review the call stack timeline</span></span>

<span data-ttu-id="208ab-126">Esaminare la sequenza temporale dello stack di chiamate per determinare se esistono i seguenti problemi.</span><span class="sxs-lookup"><span data-stu-id="208ab-126">Review the call stack timeline to determine whether the following issues exist.</span></span> <span data-ttu-id="208ab-127">Se esistono, abilita la versione di anteprima per **TaxUncommittedDoIsolateScopeFlighting** per risolvere il problema.</span><span class="sxs-lookup"><span data-stu-id="208ab-127">If they do, enable the flighting for **TaxUncommittedDoIsolateScopeFlighting** to fix the issue.</span></span>

- <span data-ttu-id="208ab-128">La transazione fa sì che il sistema smetta di rispondere fino al termine della sessione.</span><span class="sxs-lookup"><span data-stu-id="208ab-128">The transaction causes the system to stop responding until the session ends.</span></span> <span data-ttu-id="208ab-129">Pertanto, la transazione non può calcolare il risultato fiscale.</span><span class="sxs-lookup"><span data-stu-id="208ab-129">Therefore, the transaction can't calculate the tax result.</span></span> <span data-ttu-id="208ab-130">La figura seguente mostra la finestra di messaggio "Sessione terminata" ricevuta.</span><span class="sxs-lookup"><span data-stu-id="208ab-130">The following illustration shows the "Session ended" message box that you receive.</span></span>

    <span data-ttu-id="208ab-131">[![Messaggio di sessione termimata](./media/tax-calculation-bad-performance-impacts-transaction-Picture2.png)](./media/tax-calculation-bad-performance-impacts-transaction-Picture2.png)</span><span class="sxs-lookup"><span data-stu-id="208ab-131">[![Session ended message](./media/tax-calculation-bad-performance-impacts-transaction-Picture2.png)](./media/tax-calculation-bad-performance-impacts-transaction-Picture2.png)</span></span>

- <span data-ttu-id="208ab-132">I metodi **TaxUncommitted** richiedono più tempo rispetto ad altri metodi.</span><span class="sxs-lookup"><span data-stu-id="208ab-132">The **TaxUncommitted** methods take more time than other methods.</span></span> <span data-ttu-id="208ab-133">Ad esempio, nella figura seguente, il metodo **TaxUncommitted::updateTaxUncommitted()** richiede 43.347,42 secondi, ma gli altri metodi richiedono 0,09 secondi.</span><span class="sxs-lookup"><span data-stu-id="208ab-133">For example, in the following illustration, the **TaxUncommitted::updateTaxUncommitted()** method takes 43,347.42 seconds, but other methods take 0.09 seconds.</span></span>

    <span data-ttu-id="208ab-134">[![Durata dei metodi](./media/tax-calculation-bad-performance-impacts-transaction-Picture3.png)](./media/tax-calculation-bad-performance-impacts-transaction-Picture3.png)</span><span class="sxs-lookup"><span data-stu-id="208ab-134">[![Method durations](./media/tax-calculation-bad-performance-impacts-transaction-Picture3.png)](./media/tax-calculation-bad-performance-impacts-transaction-Picture3.png)</span></span>

## <a name="customizing-and-calling-tax-calculation"></a><span data-ttu-id="208ab-135">Personalizzare e chiamare il calcolo delle imposte</span><span class="sxs-lookup"><span data-stu-id="208ab-135">Customizing and calling tax calculation</span></span>

<span data-ttu-id="208ab-136">Quando personalizzi, non chiamare il calcolo delle imposte nel metodo **insert()** o **update()** per ogni riga.</span><span class="sxs-lookup"><span data-stu-id="208ab-136">When you customize, don't call tax calculation at the **insert()** or **update()** method for each line.</span></span> <span data-ttu-id="208ab-137">Il calcolo delle imposte dovrebbe essere chiamato a livello di transazione.</span><span class="sxs-lookup"><span data-stu-id="208ab-137">Tax calculation should be called at the transaction level.</span></span>

## <a name="determine-whether-customization-exists"></a><span data-ttu-id="208ab-138">Determinare se esiste la personalizzazione</span><span class="sxs-lookup"><span data-stu-id="208ab-138">Determine whether customization exists</span></span>

<span data-ttu-id="208ab-139">Se hai completato i passaggi nelle sezioni precedenti ma non hai riscontrato alcun problema, determina se esiste la personalizzazione.</span><span class="sxs-lookup"><span data-stu-id="208ab-139">If you've completed the steps in the previous sections but have found no issue, determine whether customization exists.</span></span> <span data-ttu-id="208ab-140">Se non esiste alcuna personalizzazione, creare una richiesta di assistenza Microsoft per ulteriore supporto.</span><span class="sxs-lookup"><span data-stu-id="208ab-140">If no customization exists, create a Microsoft service request for further support.</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
