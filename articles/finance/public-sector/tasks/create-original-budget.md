---
title: Creare un budget originale e annullare le voci di budget preliminari nel settore pubblico
description: Quando si crea una voce di budget originale e si utilizzano il modello di budget e i valori di dimensione che contengono gli importi di budget preliminari, gli importi di budget preliminari possono essere annullati.
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
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Service industries
ms.author: twheeloc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 32d89216d49a743729de8910f738276cbddcd8bb
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/18/2020
ms.locfileid: "3144559"
---
# <a name="create-an-original-budget-and-then-reverse-preliminary-budget-entries-in-the-public-sector"></a><span data-ttu-id="a5f6d-103">Creare un budget originale e annullare le voci di budget preliminari nel settore pubblico</span><span class="sxs-lookup"><span data-stu-id="a5f6d-103">Create an original budget and then reverse preliminary budget entries in the public sector</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="a5f6d-104">Quando si crea una voce di budget originale e si utilizzano il modello di budget e i valori di dimensione che contengono gli importi di budget preliminari, gli importi di budget preliminari possono essere annullati.</span><span class="sxs-lookup"><span data-stu-id="a5f6d-104">When you create an original budget entry and use the budget model and dimension values that contain preliminary budget amounts, the preliminary budget amounts can be reversed.</span></span> <span data-ttu-id="a5f6d-105">Questa procedura è stata creata utilizzando i dati della società di dati dimostrativi PSUS nella partizione del settore pubblico.</span><span class="sxs-lookup"><span data-stu-id="a5f6d-105">This procedure was created using the PSUS demo company data in the public sector partition.</span></span>

1. <span data-ttu-id="a5f6d-106">Andare a Impostazione budget > Voci del registro di budget.</span><span class="sxs-lookup"><span data-stu-id="a5f6d-106">Go to Budgeting > Budget register entries.</span></span>
2. <span data-ttu-id="a5f6d-107">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="a5f6d-107">Click New.</span></span>
3. <span data-ttu-id="a5f6d-108">Nel campo Modello di budget fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="a5f6d-108">In the Budget model field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="a5f6d-109">Trovare e selezionare il record desiderato nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="a5f6d-109">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="a5f6d-110">Nel campo Codice budget fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="a5f6d-110">In the Budget code field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="a5f6d-111">Nell'elenco, fare clic su Budget originale.</span><span class="sxs-lookup"><span data-stu-id="a5f6d-111">In the list, click Original budget.</span></span>
7. <span data-ttu-id="a5f6d-112">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="a5f6d-112">Click Save.</span></span>
8. <span data-ttu-id="a5f6d-113">Fare clic su Aggiungi riga.</span><span class="sxs-lookup"><span data-stu-id="a5f6d-113">Click Add line.</span></span>
9. <span data-ttu-id="a5f6d-114">Facoltativo: se si desidera modificare la data presente nell'intestazione, immettere una nuova data.</span><span class="sxs-lookup"><span data-stu-id="a5f6d-114">Optional: If you want to change the date from the one in the header, enter a new date.</span></span> <span data-ttu-id="a5f6d-115">Questa data determina il periodo fiscale in cui verrà registrato il budget.</span><span class="sxs-lookup"><span data-stu-id="a5f6d-115">This date determines the fiscal period that the budget will be recorded to.</span></span>
10. <span data-ttu-id="a5f6d-116">Nel campo Struttura dei conti fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="a5f6d-116">In the Account structure field, click the drop-down button to open the lookup.</span></span>
11. <span data-ttu-id="a5f6d-117">Trovare e selezionare il record desiderato nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="a5f6d-117">In the list, find and select the desired record.</span></span>
12. <span data-ttu-id="a5f6d-118">Nel campo Valori di dimensione specificare i valori desiderati.</span><span class="sxs-lookup"><span data-stu-id="a5f6d-118">In the Dimension values field, specify the desired values.</span></span>
13. <span data-ttu-id="a5f6d-119">Nel campo Importo immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="a5f6d-119">In the Amount field, enter a number.</span></span>
14. <span data-ttu-id="a5f6d-120">Nel campo Valuta fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="a5f6d-120">In the Currency field, click the drop-down button to open the lookup.</span></span>
15. <span data-ttu-id="a5f6d-121">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="a5f6d-121">In the list, click the link in the selected row.</span></span>
16. <span data-ttu-id="a5f6d-122">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="a5f6d-122">Click Save.</span></span>
17. <span data-ttu-id="a5f6d-123">Fare clic su Aggiorna saldi budget.</span><span class="sxs-lookup"><span data-stu-id="a5f6d-123">Click Update budget balances.</span></span>
    * <span data-ttu-id="a5f6d-124">Facoltativo: è possibile selezionare l'opzione per annullare il budget preliminare.</span><span class="sxs-lookup"><span data-stu-id="a5f6d-124">Optional: You can select the Reverse preliminary budget option.</span></span> <span data-ttu-id="a5f6d-125">Si noti che è possibile annullare tutte le voci di budget preliminare o solo le voci di budget preliminare con il codice budget specificato.</span><span class="sxs-lookup"><span data-stu-id="a5f6d-125">Note that you can reverse all preliminary budget entries, or only the preliminary budget entries that have the budget code that you specify.</span></span>  
    * <span data-ttu-id="a5f6d-126">Per effettuare selezioni facoltative, fare clic sull'icona Sblocca nella parte superiore della pagina.</span><span class="sxs-lookup"><span data-stu-id="a5f6d-126">To make optional selections, click the Unlock icon at the top of the page.</span></span>  
18. <span data-ttu-id="a5f6d-127">Fare clic su Aggiorna.</span><span class="sxs-lookup"><span data-stu-id="a5f6d-127">Click Update.</span></span>

