--- 
title: Creare un codice interessi con un intervallo
description: I codici interessi possono essere impostati per calcolare importi d'interesse diversi in base a un intervallo di valori.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 4ee037fbf166a64f126ee6ffa3fbb8d749daec02
ms.contentlocale: it-it
ms.lasthandoff: 05/08/2018

---
# <a name="create-an-interest-code-with-a-range"></a><span data-ttu-id="e5d42-103">Creare un codice interessi con un intervallo</span><span class="sxs-lookup"><span data-stu-id="e5d42-103">Create an interest code with a range</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="e5d42-104">I codici interessi possono essere impostati per calcolare importi d'interesse diversi in base a un intervallo di valori.</span><span class="sxs-lookup"><span data-stu-id="e5d42-104">Interest codes can be set up to calculate different interest amounts based on a range of values.</span></span> <span data-ttu-id="e5d42-105">Questa procedura consente di aggiungere un codice interessi e un intervallo.</span><span class="sxs-lookup"><span data-stu-id="e5d42-105">This procedure will show you how to add an interest code and add a range to it.</span></span>

1. <span data-ttu-id="e5d42-106">Andare a Crediti e riscossioni > Interessi > Imposta codici interessi.</span><span class="sxs-lookup"><span data-stu-id="e5d42-106">Go to Credit and collections > Interest > Set up interest codes.</span></span>
2. <span data-ttu-id="e5d42-107">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="e5d42-107">Click New.</span></span>
3. <span data-ttu-id="e5d42-108">Nel campo Codice interessi, immettere il nome del codice interessi.</span><span class="sxs-lookup"><span data-stu-id="e5d42-108">In the Interest code field, enter the name of the interest code.</span></span>
4. <span data-ttu-id="e5d42-109">Nel campo Descrizione immettere una descrizione per il codice interessi.</span><span class="sxs-lookup"><span data-stu-id="e5d42-109">In the Description field, enter a description for the interest code.</span></span>
5. <span data-ttu-id="e5d42-110">Selezionare Mese.</span><span class="sxs-lookup"><span data-stu-id="e5d42-110">Select Month.</span></span>
6. <span data-ttu-id="e5d42-111">Espandere la sezione Redditi.</span><span class="sxs-lookup"><span data-stu-id="e5d42-111">Expand the Earnings section.</span></span>
7. <span data-ttu-id="e5d42-112">Espandere la sezione Utili per valuta.</span><span class="sxs-lookup"><span data-stu-id="e5d42-112">Expand the Earnings by currency section.</span></span>
8. <span data-ttu-id="e5d42-113">Nel campo Conto di registrazione contabile, specificare i valori desiderati.</span><span class="sxs-lookup"><span data-stu-id="e5d42-113">In the Ledger posting account field, specify the desired values.</span></span>
9. <span data-ttu-id="e5d42-114">Nel campo Interessi in base a intervallo, selezionare 'Mesi'.</span><span class="sxs-lookup"><span data-stu-id="e5d42-114">In the Interest by range field, select 'Months'.</span></span>
10. <span data-ttu-id="e5d42-115">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="e5d42-115">Click Add.</span></span>
11. <span data-ttu-id="e5d42-116">Nel campo Descrizione immettere una descrizione per la valuta e l'intervallo.</span><span class="sxs-lookup"><span data-stu-id="e5d42-116">In the Description field, enter a description for this currency and range.</span></span>
12. <span data-ttu-id="e5d42-117">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="e5d42-117">Click Save.</span></span>
13. <span data-ttu-id="e5d42-118">Fare clic su Intervalli.</span><span class="sxs-lookup"><span data-stu-id="e5d42-118">Click Ranges.</span></span>
14. <span data-ttu-id="e5d42-119">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="e5d42-119">Click New.</span></span>
15. <span data-ttu-id="e5d42-120">Immettere il valore Dal come 0 e immettere la percentuale di interesse per mese da utilizzare per calcolare gli interessi.</span><span class="sxs-lookup"><span data-stu-id="e5d42-120">Enter the From value as 0 and then enter the interest percent per month that will be used to calculate the interest.</span></span> <span data-ttu-id="e5d42-121">In questo esempio, è 1,5.</span><span class="sxs-lookup"><span data-stu-id="e5d42-121">For our example, it is 1.5.</span></span>
16. <span data-ttu-id="e5d42-122">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="e5d42-122">Click New.</span></span>
17. <span data-ttu-id="e5d42-123">Immettere il successivo valore Dal come 4, ovvero il primo mese in cui verrà calcolato un nuovo importo d'interesse.</span><span class="sxs-lookup"><span data-stu-id="e5d42-123">Enter the next From value as 4, which is the first month that you will be calculating a new interest amount.</span></span>
18. <span data-ttu-id="e5d42-124">Immettere la percentuale di interesse per mese da utilizzare per calcolare gli interessi a partire dal mese 4.</span><span class="sxs-lookup"><span data-stu-id="e5d42-124">Enter the interest percent per month that will be used to calculate the interest starting in month 4.</span></span> <span data-ttu-id="e5d42-125">In questo esempio, è 2,0.</span><span class="sxs-lookup"><span data-stu-id="e5d42-125">For this example, it is 2.0.</span></span>
19. <span data-ttu-id="e5d42-126">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="e5d42-126">Click New.</span></span>
20. <span data-ttu-id="e5d42-127">Immettere il successivo valore Dal come 7, ovvero il mese successivo in cui verrà calcolato un nuovo importo d'interesse.</span><span class="sxs-lookup"><span data-stu-id="e5d42-127">Enter the next From value as 7, which is the next month that you will be calculating a new interest amount.</span></span>
21. <span data-ttu-id="e5d42-128">Immettere la percentuale di interesse per mese da utilizzare per calcolare gli interessi a partire dal mese 7.</span><span class="sxs-lookup"><span data-stu-id="e5d42-128">Enter the interest percent per month that will be used to calculate the interest starting in month 7.</span></span> <span data-ttu-id="e5d42-129">In questo esempio, è 2,5.</span><span class="sxs-lookup"><span data-stu-id="e5d42-129">For this example, it is 2.5.</span></span>
22. <span data-ttu-id="e5d42-130">Fare clic su Chiudi per completare l'impostazione.</span><span class="sxs-lookup"><span data-stu-id="e5d42-130">Click Close to complete the setup.</span></span>


