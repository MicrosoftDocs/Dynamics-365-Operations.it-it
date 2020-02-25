---
title: Creare dimensioni finanziarie per i canali di vendita al dettaglio e configurare i valori di dimensione nei punti vendita
description: In questa procedura vengono descritti i passaggi per creare una dimensione finanziaria del canale di commercio con i valori di dimensione e i passaggi per configurare i valori di dimensione finanziaria nei punti vendita.
author: jashanno
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 79abb6875e2f5b101410ca004b525c4b881621a2
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/01/2020
ms.locfileid: "3023042"
---
# <a name="create-financial-dimensions-for-retail-channels-and-configure-dimension-values-on-stores"></a><span data-ttu-id="d9e2a-103">Creare dimensioni finanziarie per i canali di vendita al dettaglio e configurare i valori di dimensione nei punti vendita</span><span class="sxs-lookup"><span data-stu-id="d9e2a-103">Create financial dimensions for retail channels and configure dimension values on stores</span></span>

[!include [task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="d9e2a-104">In questa procedura vengono descritti i passaggi per creare una dimensione finanziaria del canale di commercio con i valori di dimensione e i passaggi per configurare i valori di dimensione finanziaria nei punti vendita.</span><span class="sxs-lookup"><span data-stu-id="d9e2a-104">This procedure walks through creating a commerce channel financial dimension with dimension values and steps to configure financial dimension values on stores.</span></span> <span data-ttu-id="d9e2a-105">In questo argomento non sono inclusi altri passaggi correlati, ad esempio per creare i set di dimensioni e le strutture dei conti.</span><span class="sxs-lookup"><span data-stu-id="d9e2a-105">The topic does not include other related steps, such as creating dimension sets and account structures.</span></span> <span data-ttu-id="d9e2a-106">Questa procedura utilizza i dati dimostrativi della società USRT.</span><span class="sxs-lookup"><span data-stu-id="d9e2a-106">This procedure uses the USRT company in demo data.</span></span>

1. <span data-ttu-id="d9e2a-107">Passare a Contabilità generale > Piano dei conti > Dimensioni > Dimensioni finanziarie.</span><span class="sxs-lookup"><span data-stu-id="d9e2a-107">Go to General ledger > Chart of accounts > Dimensions > Financial dimensions.</span></span>
2. <span data-ttu-id="d9e2a-108">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="d9e2a-108">Click New.</span></span>
3. <span data-ttu-id="d9e2a-109">Nel campo Usa valori da, selezionare "Canali di commercio".</span><span class="sxs-lookup"><span data-stu-id="d9e2a-109">In the Use values from field, select 'Commerce channels'.</span></span>
4. <span data-ttu-id="d9e2a-110">Digitare un valore nel campo Nome dimensione.</span><span class="sxs-lookup"><span data-stu-id="d9e2a-110">In the Dimension name field, type a value.</span></span>
5. <span data-ttu-id="d9e2a-111">Fare clic su Attiva.</span><span class="sxs-lookup"><span data-stu-id="d9e2a-111">Click Activate.</span></span>
6. <span data-ttu-id="d9e2a-112">Fare clic su Chiudi.</span><span class="sxs-lookup"><span data-stu-id="d9e2a-112">Click Close.</span></span>
7. <span data-ttu-id="d9e2a-113">Fare clic su Attiva.</span><span class="sxs-lookup"><span data-stu-id="d9e2a-113">Click Activate.</span></span>
8. <span data-ttu-id="d9e2a-114">Fare clic su Valori di dimensione.</span><span class="sxs-lookup"><span data-stu-id="d9e2a-114">Click Dimension values.</span></span>
9. <span data-ttu-id="d9e2a-115">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="d9e2a-115">Close the page.</span></span>
10. <span data-ttu-id="d9e2a-116">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="d9e2a-116">Click Save.</span></span>
11. <span data-ttu-id="d9e2a-117">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="d9e2a-117">Close the page.</span></span>
12. <span data-ttu-id="d9e2a-118">Passare a Retail e Commerce > Canali > Punti vendita > Tutti i punti vendita.</span><span class="sxs-lookup"><span data-stu-id="d9e2a-118">Go to Retail and Commerce > Channels > Stores > All stores.</span></span>
13. <span data-ttu-id="d9e2a-119">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="d9e2a-119">In the list, click the link in the selected row.</span></span>
14. <span data-ttu-id="d9e2a-120">Attivare/disattivare l'espansione della sezione Dimensioni finanziarie.</span><span class="sxs-lookup"><span data-stu-id="d9e2a-120">Toggle the expansion of the Financial dimensions section.</span></span>
15. <span data-ttu-id="d9e2a-121">Fare clic su Modifica.</span><span class="sxs-lookup"><span data-stu-id="d9e2a-121">Click Edit.</span></span>
16. <span data-ttu-id="d9e2a-122">Nel campo Canale di commercio fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="d9e2a-122">In the Commerce channel field, click the drop-down button to open the lookup.</span></span>
17. <span data-ttu-id="d9e2a-123">Nell'elenco, individuare e selezionare il valore della dimensione per l'aggiornamento del punto vendita.</span><span class="sxs-lookup"><span data-stu-id="d9e2a-123">In the list, find and select the dimension value for the store being updated.</span></span>
18. <span data-ttu-id="d9e2a-124">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="d9e2a-124">In the list, click the link in the selected row.</span></span>
19. <span data-ttu-id="d9e2a-125">Nel campo Centro di costo fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="d9e2a-125">In the CostCenter field, click the drop-down button to open the lookup.</span></span>
20. <span data-ttu-id="d9e2a-126">Trovare e selezionare il record desiderato nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="d9e2a-126">In the list, find and select the desired record.</span></span>
21. <span data-ttu-id="d9e2a-127">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="d9e2a-127">In the list, click the link in the selected row.</span></span>
22. <span data-ttu-id="d9e2a-128">Nel campo Reparto fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="d9e2a-128">In the Department field, click the drop-down button to open the lookup.</span></span>
23. <span data-ttu-id="d9e2a-129">Trovare e selezionare il record desiderato nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="d9e2a-129">In the list, find and select the desired record.</span></span>
24. <span data-ttu-id="d9e2a-130">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="d9e2a-130">In the list, click the link in the selected row.</span></span>
25. <span data-ttu-id="d9e2a-131">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="d9e2a-131">Click Save.</span></span>

