---
title: Creare un budget da conti transazioni e conti totali
description: "Questo articolo fornisce una panoramica del processo per creare budget basati sui conti totali. Illustra inoltre come attivare il controllo del budget per i conti totali, se il controllo del budget è necessario."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BudgetControlConfiguration, BudgetPlanGenerate
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 13051
ms.assetid: fb1bb2d3-445c-402f-a9a3-aa6503eed78e
ms.search.region: Global
ms.author: sigitac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: fd6dc5173fd37f0257c98c1a41f3e6ce40b5b680
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---

# <a name="create-a-budget-from-transaction-accounts-and-total-accounts"></a><span data-ttu-id="811eb-104">Creare un budget da conti transazioni e conti totali</span><span class="sxs-lookup"><span data-stu-id="811eb-104">Create a budget from transaction accounts and total accounts</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="811eb-105">Questo articolo fornisce una panoramica del processo per creare budget basati sui conti totali.</span><span class="sxs-lookup"><span data-stu-id="811eb-105">This article provides an overview of the process for creating budgets based on total accounts.</span></span> <span data-ttu-id="811eb-106">Illustra inoltre come attivare il controllo del budget per i conti totali, se il controllo del budget è necessario.</span><span class="sxs-lookup"><span data-stu-id="811eb-106">It also explains how to turn on budget control for total accounts, if budget control is required.</span></span>

<span data-ttu-id="811eb-107">Il piano di budget e i documenti della voce del registro di budget consentono l'impostazione del budget sui conti principali di tipo **Totale**.</span><span class="sxs-lookup"><span data-stu-id="811eb-107">Both budget plan and budget register entry documents allow for budgeting on main accounts that have a main account type of **Total**.</span></span> <span data-ttu-id="811eb-108">I valori effettivi possono essere registrati solo sul conti principali transazionali.</span><span class="sxs-lookup"><span data-stu-id="811eb-108">Actuals can be posted only to transactional main accounts.</span></span> 

<span data-ttu-id="811eb-109">Per il processo periodico **Genera piano di budget da contabilità generale**, sulla scheda **Origine**, è possibile specificare il tipo di conto principale **Totale** come criterio.</span><span class="sxs-lookup"><span data-stu-id="811eb-109">For the **Generate budget plan from General ledger** periodic process, on the **Source** tab, you can specify the **Total** main account type as a criterion.</span></span> <span data-ttu-id="811eb-110">In questo caso, ogni conto principale totale verrà incluso nel piano di budget di destinazione e l'importo sarà pari all'importo totale dell'intervallo di conti principali selezionati.</span><span class="sxs-lookup"><span data-stu-id="811eb-110">In this case, each total main account will be included in the target budget plan, and the amount will equal the total amount of the range of selected main accounts.</span></span> 

<span data-ttu-id="811eb-111">È possibile attivare il controllo del budget per i conti principali di tipo **Totale**.</span><span class="sxs-lookup"><span data-stu-id="811eb-111">You can activate budget control for main accounts of the **Total** type.</span></span> <span data-ttu-id="811eb-112">Questa funzionalità è supportata tramite l'utilizzo dei gruppi di budget.</span><span class="sxs-lookup"><span data-stu-id="811eb-112">This functionality is supported through the use of budget groups.</span></span> <span data-ttu-id="811eb-113">Per ciascun conto principale totale, il budget da controllare per un gruppo di budget deve essere creato nella pagina **Configurazione controllo del budget**.</span><span class="sxs-lookup"><span data-stu-id="811eb-113">For each total main account, the budget that should be controlled for a budget group must be created on the **Budget control configuration **page.</span></span> <span data-ttu-id="811eb-114">I criteri specificati devono includere il conto principale totale e l'intervallo di conti.</span><span class="sxs-lookup"><span data-stu-id="811eb-114">The criteria that you specify must include the total main account and the range of accounts.</span></span> <span data-ttu-id="811eb-115">Per rendere più rapido il processo di creazione di gruppi di budget, è possibile usufruire dell'entità di dati Gruppi di controllo del budget.</span><span class="sxs-lookup"><span data-stu-id="811eb-115">To speed up the process of creating budget groups, you can take advantage of the Budget control groups data entity.</span></span> 

<span data-ttu-id="811eb-116">Quando un budget viene utilizzato nella creazione di report, ad esempio in un rendiconto finanziario, la somma del budget per il conto totale è costituita dai seguenti importi:</span><span class="sxs-lookup"><span data-stu-id="811eb-116">When a budget is used in reporting, such as on a financial statement, the budget sum for the total account consists of the following amounts:</span></span>

-   <span data-ttu-id="811eb-117">I budget creati da ciascun conto CoGe per transazioni nell'intervallo del conto totale.</span><span class="sxs-lookup"><span data-stu-id="811eb-117">The budgets that are created from each transaction ledger account in the interval of the total account.</span></span>
-   <span data-ttu-id="811eb-118">L'importo del budget immesso direttamente nel conto totale.</span><span class="sxs-lookup"><span data-stu-id="811eb-118">The budget amount that is entered directly on the total account.</span></span>

<span data-ttu-id="811eb-119">Pertanto, è possibile creare budget distinti per i conti transazioni più significativi nell'intervallo del conto totale e quindi aggiungere l'importo del budget disponibile al conto totale.</span><span class="sxs-lookup"><span data-stu-id="811eb-119">Therefore, you can create separate budgets for the most significant transaction accounts in the interval of the total account, and then add the available budget amount to the total account.</span></span>




