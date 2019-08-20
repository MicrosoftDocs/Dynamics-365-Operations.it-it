---
title: Creare regole di configurazione
description: Questa procedura crea le regole di configurazione che possono essere utilizzate per la configurazione basata su dimensioni per applicare o impedire determinate combinazioni di righe DBA.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BOMTable, BOMConfigRule, ConfigItemIdLookup
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0f15c0328e391d81c4c977f974553ae9135b207c
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/01/2019
ms.locfileid: "1844899"
---
# <a name="create-configuration-rules"></a><span data-ttu-id="57ae8-103">Creare regole di configurazione</span><span class="sxs-lookup"><span data-stu-id="57ae8-103">Create configuration rules</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="57ae8-104">Questa procedura crea le regole di configurazione che possono essere utilizzate per la configurazione basata su dimensioni per applicare o impedire determinate combinazioni di righe DBA.</span><span class="sxs-lookup"><span data-stu-id="57ae8-104">This procedure creates configuration rules that can be used for dimension-based configuration to enforce or prevent certain combinations of BOM lines.</span></span> <span data-ttu-id="57ae8-105">La società di dati dimostrativi utilizzata per creare questa procedura è USMF.</span><span class="sxs-lookup"><span data-stu-id="57ae8-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="57ae8-106">Questa è la settima procedura di otto che illustra come sviluppare le combinazioni per la configurazione basata su dimensioni.</span><span class="sxs-lookup"><span data-stu-id="57ae8-106">This is the seventh procedure out of eight that explains how to build combinations for dimension-based configuration.</span></span>

1. <span data-ttu-id="57ae8-107">Andare a Gestione informazioni sul prodotto > Distinte base e formule > Distinte base.</span><span class="sxs-lookup"><span data-stu-id="57ae8-107">Go to Product information management > Bills of materials and formulas > Bills of materials.</span></span>
2. <span data-ttu-id="57ae8-108">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="57ae8-108">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="57ae8-109">Trovare e selezionare la DBA per la configurazione basata su dimensioni.</span><span class="sxs-lookup"><span data-stu-id="57ae8-109">Find and select the BOM for the dimension-based configuration.</span></span>  
3. <span data-ttu-id="57ae8-110">Nel riquadro azioni fare clic su Opzioni.</span><span class="sxs-lookup"><span data-stu-id="57ae8-110">On the Action Pane, click Options.</span></span>
4. <span data-ttu-id="57ae8-111">Fare clic su Cambia visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="57ae8-111">Click Change view.</span></span>
5. <span data-ttu-id="57ae8-112">Fare clic su Visualizzazione intestazione.</span><span class="sxs-lookup"><span data-stu-id="57ae8-112">Click Header view.</span></span>
    * <span data-ttu-id="57ae8-113">Aprire la visualizzazione intestazione per accedere alla Scheda dettaglio del Ciclo di lavorazione di configurazione.</span><span class="sxs-lookup"><span data-stu-id="57ae8-113">Open the header view to access the Configuration route FastTab.</span></span>  
6. <span data-ttu-id="57ae8-114">Espandere o comprimere la sezione Ciclo di lavorazione di configurazione.</span><span class="sxs-lookup"><span data-stu-id="57ae8-114">Expand or collapse the Configuration route section.</span></span>
    * <span data-ttu-id="57ae8-115">La Scheda dettaglio del Ciclo di lavorazione di configurazione deve essere in modalità espansa.</span><span class="sxs-lookup"><span data-stu-id="57ae8-115">The Configuration route FastTab must be in the expanded mode.</span></span>  
7. <span data-ttu-id="57ae8-116">Fare clic su Regole di configurazione.</span><span class="sxs-lookup"><span data-stu-id="57ae8-116">Click Configuration rules.</span></span>
8. <span data-ttu-id="57ae8-117">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="57ae8-117">Click New.</span></span>
9. <span data-ttu-id="57ae8-118">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="57ae8-118">In the list, mark the selected row.</span></span>
10. <span data-ttu-id="57ae8-119">Nel campo Numero articolo fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="57ae8-119">In the Item number field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="57ae8-120">Sono visualizzati gli articoli del gruppo corrente di configurazioni.</span><span class="sxs-lookup"><span data-stu-id="57ae8-120">The items in the current configuration group are displayed.</span></span> <span data-ttu-id="57ae8-121">Selezionare quello che rappresenta la condizione della regola.</span><span class="sxs-lookup"><span data-stu-id="57ae8-121">Select the one that represents the condition in the rule.</span></span>  
11. <span data-ttu-id="57ae8-122">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="57ae8-122">In the list, click the link in the selected row.</span></span>
12. <span data-ttu-id="57ae8-123">Selezionare un'opzione nel campo Metodo.</span><span class="sxs-lookup"><span data-stu-id="57ae8-123">In the Method field, select an option.</span></span>
    * <span data-ttu-id="57ae8-124">È possibile applicare una selezione o un deselezione di un articolo da un altro gruppo di configurazioni.</span><span class="sxs-lookup"><span data-stu-id="57ae8-124">It is possible to enforce either a selection or a deselection of an item from another configuration group.</span></span>  
13. <span data-ttu-id="57ae8-125">Nel campo Gruppo derivato fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="57ae8-125">In the Derived group field, click the drop-down button to open the lookup.</span></span>
14. <span data-ttu-id="57ae8-126">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="57ae8-126">In the list, find and select the desired record.</span></span>
15. <span data-ttu-id="57ae8-127">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="57ae8-127">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="57ae8-128">Selezionare il gruppo di configurazioni desiderato.</span><span class="sxs-lookup"><span data-stu-id="57ae8-128">Select the desired configuration group.</span></span>  
16. <span data-ttu-id="57ae8-129">Nel campo Numero articolo derivato fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="57ae8-129">In the Derived item number field, click the drop-down button to open the lookup.</span></span>
17. <span data-ttu-id="57ae8-130">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="57ae8-130">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="57ae8-131">Selezionare il numero di articolo da selezionare o deselezionare, a seconda del metodo scelto.</span><span class="sxs-lookup"><span data-stu-id="57ae8-131">Select the item number that will be either selected or deselected depending on the chosen method.</span></span>  
18. <span data-ttu-id="57ae8-132">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="57ae8-132">Close the page.</span></span>

