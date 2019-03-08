---
title: Impostare i codici di ritenuta d'acconto
description: La ritenuta d'acconto è un'imposta sui fornitori che non dà origine a transazioni IVA.
author: twheeloc
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxWithholdTable, TaxWithholdData, TaxWithholdGroup
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 382b6332665af2491563960a75d498a4f007aba8
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2019
ms.locfileid: "337235"
---
# <a name="set-up-withholding-tax"></a><span data-ttu-id="817dd-103">Impostare i codici di ritenuta d'acconto</span><span class="sxs-lookup"><span data-stu-id="817dd-103">Set up withholding tax</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="817dd-104">La ritenuta d'acconto è un'imposta sui fornitori che non dà origine a transazioni IVA.</span><span class="sxs-lookup"><span data-stu-id="817dd-104">Withholding tax is a tax on vendors that does not create sales tax transactions.</span></span> <span data-ttu-id="817dd-105">La ritenuta d'acconto calcolata sui pagamenti fornitore è considerata una passività</span><span class="sxs-lookup"><span data-stu-id="817dd-105">Withholding tax that is calculated on vendor payments is a liability.</span></span> <span data-ttu-id="817dd-106">e può pertanto essere registrata solo nei conti dello stato patrimoniale o nei conti passivi.</span><span class="sxs-lookup"><span data-stu-id="817dd-106">Therefore, only balance sheet accounts or liability accounts are valid accounts for posting withholding tax.</span></span> <span data-ttu-id="817dd-107">Questa guida attività dimostra l'impostazione della ritenuta d'acconto.</span><span class="sxs-lookup"><span data-stu-id="817dd-107">This task guide demonstrates how to set up withholding tax.</span></span>

1. <span data-ttu-id="817dd-108">Andare a Imposta > Imposte indirette > Ritenuta d'acconto > Codici ritenuta d'acconto.</span><span class="sxs-lookup"><span data-stu-id="817dd-108">Go to Tax > Indirect taxes > Withholding tax > Withholding tax codes.</span></span>
2. <span data-ttu-id="817dd-109">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="817dd-109">Click New.</span></span>
3. <span data-ttu-id="817dd-110">Nel campo Codice ritenuta d'acconto digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="817dd-110">In the Withholding tax code field, type a value.</span></span>
4. <span data-ttu-id="817dd-111">Nel campo Nome ritenuta d'acconto immettere il nome del codice di ritenuta d'acconto.</span><span class="sxs-lookup"><span data-stu-id="817dd-111">In the Withholding tax name field, enter the name of the withholding tax code.</span></span>
5. <span data-ttu-id="817dd-112">Nel campo Conto principale selezionare il conto principale per registrare la ritenuta d'acconto dovuta.</span><span class="sxs-lookup"><span data-stu-id="817dd-112">In the Main account field, select the main account for posting the withholding tax liability.</span></span>
6. <span data-ttu-id="817dd-113">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="817dd-113">Click Save.</span></span>
7. <span data-ttu-id="817dd-114">Fare clic su Valori.</span><span class="sxs-lookup"><span data-stu-id="817dd-114">Click Values.</span></span>
8. <span data-ttu-id="817dd-115">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="817dd-115">In the list, mark the selected row.</span></span>
9. <span data-ttu-id="817dd-116">Nel campo Valore, immettere una percentuale utilizzata per il calcolo della ritenuta d'acconto.</span><span class="sxs-lookup"><span data-stu-id="817dd-116">In the Value field, enter a percentage used for the calculation of the withholding tax.</span></span>
10. <span data-ttu-id="817dd-117">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="817dd-117">Click Save.</span></span>
11. <span data-ttu-id="817dd-118">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="817dd-118">Close the page.</span></span>
12. <span data-ttu-id="817dd-119">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="817dd-119">Click Save.</span></span>
13. <span data-ttu-id="817dd-120">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="817dd-120">Close the page.</span></span>
14. <span data-ttu-id="817dd-121">Andare a Imposta > Imposte indirette > Ritenuta d'acconto > Gruppi ritenute d'acconto.</span><span class="sxs-lookup"><span data-stu-id="817dd-121">Go to Tax > Indirect taxes > Withholding tax > Withholding tax groups.</span></span>
15. <span data-ttu-id="817dd-122">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="817dd-122">Click New.</span></span>
16. <span data-ttu-id="817dd-123">Nel campo Gruppo ritenute d'acconto immettere l'identificatore del gruppo di ritenute d'acconto.</span><span class="sxs-lookup"><span data-stu-id="817dd-123">In the Withholding tax group field, enter the identifier of the withholding tax group.</span></span>
17. <span data-ttu-id="817dd-124">Nel campo Descrizione immettere il nome del gruppo di ritenute d'acconto.</span><span class="sxs-lookup"><span data-stu-id="817dd-124">In the Description field, enter the name of the withholding tax group.</span></span>
18. <span data-ttu-id="817dd-125">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="817dd-125">In the list, mark the selected row.</span></span>
19. <span data-ttu-id="817dd-126">Nel campo Codice ritenuta d'acconto selezionare il codice ritenuta d'acconto.</span><span class="sxs-lookup"><span data-stu-id="817dd-126">In the Withholding tax code field, select the withholding tax code.</span></span>
20. <span data-ttu-id="817dd-127">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="817dd-127">In the list, click the link in the selected row.</span></span>
21. <span data-ttu-id="817dd-128">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="817dd-128">Click Save.</span></span>

