---
title: Creare un budget preliminare per il settore pubblico
description: È possibile creare voci del registro di budget preliminare per un modello di budget e valori di dimensione specifici.
author: twheeloc
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BudgetTransaction, BudgetAccountStructureLookup, BudgetTransactionMultiPost
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.search.industry: Service industries
ms.author: twheeloc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 40371809f3855e57db4bc12f5466f7cef5cec600
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5235558"
---
# <a name="create-a-preliminary-budget-for-public-sector"></a><span data-ttu-id="6ed5c-103">Creare un budget preliminare per il settore pubblico</span><span class="sxs-lookup"><span data-stu-id="6ed5c-103">Create a preliminary budget for Public sector</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="6ed5c-104">È possibile creare voci del registro di budget preliminare per un modello di budget e valori di dimensione specifici.</span><span class="sxs-lookup"><span data-stu-id="6ed5c-104">You can create preliminary budget register entries for a specific budget model and dimension values.</span></span> <span data-ttu-id="6ed5c-105">Una volta approvato il budget effettivo, è possibile creare le voci del registro di budget originale.</span><span class="sxs-lookup"><span data-stu-id="6ed5c-105">After the actual budget is approved, you can create original budget register entries.</span></span> <span data-ttu-id="6ed5c-106">Questa procedura è stata creata utilizzando i dati della società di dati dimostrativi PSUS nella partizione del settore pubblico.</span><span class="sxs-lookup"><span data-stu-id="6ed5c-106">This procedure was created using the PSUS demo company data in the public sector partition.</span></span>

1. <span data-ttu-id="6ed5c-107">Andare a Impostazione budget > Voci del registro di budget.</span><span class="sxs-lookup"><span data-stu-id="6ed5c-107">Go to Budgeting > Budget register entries.</span></span>
2. <span data-ttu-id="6ed5c-108">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="6ed5c-108">Click New.</span></span>
3. <span data-ttu-id="6ed5c-109">Nel campo Modello di budget fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="6ed5c-109">In the Budget model field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="6ed5c-110">Trovare e selezionare il record desiderato nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="6ed5c-110">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="6ed5c-111">Nel campo Codice budget fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="6ed5c-111">In the Budget code field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="6ed5c-112">Trovare e selezionare il record desiderato nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="6ed5c-112">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="6ed5c-113">Nel campo Codice motivo fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="6ed5c-113">In the Reason code field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="6ed5c-114">Fare clic sul record desiderato nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="6ed5c-114">In the list, click the desired record.</span></span>
9. <span data-ttu-id="6ed5c-115">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="6ed5c-115">Click Save.</span></span>
10. <span data-ttu-id="6ed5c-116">Fare clic su Aggiungi riga.</span><span class="sxs-lookup"><span data-stu-id="6ed5c-116">Click Add line.</span></span>
    * <span data-ttu-id="6ed5c-117">Facoltativo: se si desidera modificare la data presente nell'intestazione, immettere una nuova data.</span><span class="sxs-lookup"><span data-stu-id="6ed5c-117">Optional: If you want to change the date from the one in the header, enter a new date.</span></span> <span data-ttu-id="6ed5c-118">Questa data determina il periodo fiscale in cui verrà registrato il budget.</span><span class="sxs-lookup"><span data-stu-id="6ed5c-118">This date determines the fiscal period that the budget will be recorded to.</span></span> <span data-ttu-id="6ed5c-119">Quando si visualizza la guida di attività, per completare gli altri campi, fare clic su Sblocca nella parte superiore della pagina.</span><span class="sxs-lookup"><span data-stu-id="6ed5c-119">When viewing the task guide, to fill out other fields, click Unlock at the top of the page.</span></span>  
11. <span data-ttu-id="6ed5c-120">Nel campo Struttura dei conti fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="6ed5c-120">In the Account structure field, click the drop-down button to open the lookup.</span></span>
12. <span data-ttu-id="6ed5c-121">Trovare e selezionare il record desiderato nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="6ed5c-121">In the list, find and select the desired record.</span></span>
13. <span data-ttu-id="6ed5c-122">Nel campo Valori di dimensione specificare i valori desiderati.</span><span class="sxs-lookup"><span data-stu-id="6ed5c-122">In the Dimension values field, specify the desired values.</span></span>
14. <span data-ttu-id="6ed5c-123">Nel campo Importo immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="6ed5c-123">In the Amount field, enter a number.</span></span>
    * <span data-ttu-id="6ed5c-124">È inoltre possibile immettere un tipo di importo.</span><span class="sxs-lookup"><span data-stu-id="6ed5c-124">You can also enter an amount type.</span></span>  
15. <span data-ttu-id="6ed5c-125">Nel campo Valuta fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="6ed5c-125">In the Currency field, click the drop-down button to open the lookup.</span></span>
16. <span data-ttu-id="6ed5c-126">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="6ed5c-126">In the list, find and select the desired record.</span></span>
17. <span data-ttu-id="6ed5c-127">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="6ed5c-127">Click Save.</span></span>
18. <span data-ttu-id="6ed5c-128">Fare clic su Aggiorna saldi budget.</span><span class="sxs-lookup"><span data-stu-id="6ed5c-128">Click Update budget balances.</span></span>
19. <span data-ttu-id="6ed5c-129">Fare clic su Aggiorna.</span><span class="sxs-lookup"><span data-stu-id="6ed5c-129">Click Update.</span></span>
    * <span data-ttu-id="6ed5c-130">Per visualizzare i risultati dell'aggiornamento, fare clic su Dettagli messaggio nella barra blu.</span><span class="sxs-lookup"><span data-stu-id="6ed5c-130">To see the results of the update, click Message details on the blue bar.</span></span>  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]