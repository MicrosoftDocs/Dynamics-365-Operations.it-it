---
title: Creare un codice interessi con un intervallo
description: I codici interessi possono essere impostati per calcolare importi d'interesse diversi in base a un intervallo di valori.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: Interest, CustInterestRange
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c0c5b20ff6fff2bc62daca68c46e949a38df8d92
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/18/2020
ms.locfileid: "3140275"
---
# <a name="create-an-interest-code-with-a-range"></a><span data-ttu-id="e0288-103">Creare un codice interessi con un intervallo</span><span class="sxs-lookup"><span data-stu-id="e0288-103">Create an interest code with a range</span></span>

[!include [banner](../../includes/banner.md)]
<span data-ttu-id="e0288-104">I codici interessi possono essere impostati per calcolare importi d'interesse diversi in base a un intervallo di valori.</span><span class="sxs-lookup"><span data-stu-id="e0288-104">Interest codes can be set up to calculate different interest amounts based on a range of values.</span></span> <span data-ttu-id="e0288-105">Questa procedura consente di aggiungere un codice interessi e un intervallo.</span><span class="sxs-lookup"><span data-stu-id="e0288-105">This procedure will show you how to add an interest code and add a range to it.</span></span>

1. <span data-ttu-id="e0288-106">Andare a Crediti e riscossioni > Interessi > Imposta codici interessi.</span><span class="sxs-lookup"><span data-stu-id="e0288-106">Go to Credit and collections > Interest > Set up interest codes.</span></span>
2. <span data-ttu-id="e0288-107">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="e0288-107">Click New.</span></span>
3. <span data-ttu-id="e0288-108">Nel campo Codice interessi, immettere il nome del codice interessi.</span><span class="sxs-lookup"><span data-stu-id="e0288-108">In the Interest code field, enter the name of the interest code.</span></span>
4. <span data-ttu-id="e0288-109">Nel campo Descrizione immettere una descrizione per il codice interessi.</span><span class="sxs-lookup"><span data-stu-id="e0288-109">In the Description field, enter a description for the interest code.</span></span>
5. <span data-ttu-id="e0288-110">Selezionare Mese.</span><span class="sxs-lookup"><span data-stu-id="e0288-110">Select Month.</span></span>
6. <span data-ttu-id="e0288-111">Espandere la sezione Redditi.</span><span class="sxs-lookup"><span data-stu-id="e0288-111">Expand the Earnings section.</span></span>
7. <span data-ttu-id="e0288-112">Espandere la sezione Utili per valuta.</span><span class="sxs-lookup"><span data-stu-id="e0288-112">Expand the Earnings by currency section.</span></span>
8. <span data-ttu-id="e0288-113">Nel campo Conto di registrazione contabile, specificare i valori desiderati.</span><span class="sxs-lookup"><span data-stu-id="e0288-113">In the Ledger posting account field, specify the desired values.</span></span>
9. <span data-ttu-id="e0288-114">Nel campo Interessi in base a intervallo, selezionare 'Mesi'.</span><span class="sxs-lookup"><span data-stu-id="e0288-114">In the Interest by range field, select 'Months'.</span></span>
10. <span data-ttu-id="e0288-115">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="e0288-115">Click Add.</span></span>
11. <span data-ttu-id="e0288-116">Nel campo Descrizione immettere una descrizione per la valuta e l'intervallo.</span><span class="sxs-lookup"><span data-stu-id="e0288-116">In the Description field, enter a description for this currency and range.</span></span>
12. <span data-ttu-id="e0288-117">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="e0288-117">Click Save.</span></span>
13. <span data-ttu-id="e0288-118">Fare clic su Intervalli.</span><span class="sxs-lookup"><span data-stu-id="e0288-118">Click Ranges.</span></span>
14. <span data-ttu-id="e0288-119">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="e0288-119">Click New.</span></span>
15. <span data-ttu-id="e0288-120">Immettere il valore Dal come 0 e immettere la percentuale di interesse per mese da utilizzare per calcolare gli interessi.</span><span class="sxs-lookup"><span data-stu-id="e0288-120">Enter the From value as 0 and then enter the interest percent per month that will be used to calculate the interest.</span></span> <span data-ttu-id="e0288-121">In questo esempio, è 1,5.</span><span class="sxs-lookup"><span data-stu-id="e0288-121">For our example, it is 1.5.</span></span>
16. <span data-ttu-id="e0288-122">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="e0288-122">Click New.</span></span>
17. <span data-ttu-id="e0288-123">Immettere il successivo valore Dal come 4, ovvero il primo mese in cui verrà calcolato un nuovo importo d'interesse.</span><span class="sxs-lookup"><span data-stu-id="e0288-123">Enter the next From value as 4, which is the first month that you will be calculating a new interest amount.</span></span>
18. <span data-ttu-id="e0288-124">Immettere la percentuale di interesse per mese da utilizzare per calcolare gli interessi a partire dal mese 4.</span><span class="sxs-lookup"><span data-stu-id="e0288-124">Enter the interest percent per month that will be used to calculate the interest starting in month 4.</span></span> <span data-ttu-id="e0288-125">In questo esempio, è 2,0.</span><span class="sxs-lookup"><span data-stu-id="e0288-125">For this example, it is 2.0.</span></span>
19. <span data-ttu-id="e0288-126">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="e0288-126">Click New.</span></span>
20. <span data-ttu-id="e0288-127">Immettere il successivo valore Dal come 7, ovvero il mese successivo in cui verrà calcolato un nuovo importo d'interesse.</span><span class="sxs-lookup"><span data-stu-id="e0288-127">Enter the next From value as 7, which is the next month that you will be calculating a new interest amount.</span></span>
21. <span data-ttu-id="e0288-128">Immettere la percentuale di interesse per mese da utilizzare per calcolare gli interessi a partire dal mese 7.</span><span class="sxs-lookup"><span data-stu-id="e0288-128">Enter the interest percent per month that will be used to calculate the interest starting in month 7.</span></span> <span data-ttu-id="e0288-129">In questo esempio, è 2,5.</span><span class="sxs-lookup"><span data-stu-id="e0288-129">For this example, it is 2.5.</span></span>
22. <span data-ttu-id="e0288-130">Fare clic su Chiudi per completare l'impostazione.</span><span class="sxs-lookup"><span data-stu-id="e0288-130">Click Close to complete the setup.</span></span>

