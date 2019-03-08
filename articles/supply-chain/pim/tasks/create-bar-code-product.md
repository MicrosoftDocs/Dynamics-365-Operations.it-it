---
title: Creare un codice a barre per un prodotto
description: In questa procedura viene illustrato come creare un codice a barre manualmente usando il numero di articolo M0001 come esempio.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductMaintainWorkspace, EcoResProductOpenCasesFormPart, EcoResProductDetailsExtended, InventItemBarcode, InventItemBarcodeLookup
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2ae2765a125045d60566267d01e380069d5d527c
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2019
ms.locfileid: "329392"
---
# <a name="create-a-bar-code-for-a-product"></a><span data-ttu-id="1ff04-103">Creare un codice a barre per un prodotto</span><span class="sxs-lookup"><span data-stu-id="1ff04-103">Create a bar code for a product</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="1ff04-104">In questa procedura viene illustrato come creare un codice a barre manualmente usando il numero di articolo M0001 come esempio.</span><span class="sxs-lookup"><span data-stu-id="1ff04-104">This procedure shows how to manually create a bar code using the item number M0001 as an example.</span></span> <span data-ttu-id="1ff04-105">La società di dati dimostrativi utilizzata per creare questa procedura è USMF.</span><span class="sxs-lookup"><span data-stu-id="1ff04-105">The demo data company used to create this procedure is USMF.</span></span>

1. <span data-ttu-id="1ff04-106">Fare clic su Gestione prodotti rilasciati.</span><span class="sxs-lookup"><span data-stu-id="1ff04-106">Click Released product maintenance.</span></span>
2. <span data-ttu-id="1ff04-107">Fare clic su Prodotti rilasciati.</span><span class="sxs-lookup"><span data-stu-id="1ff04-107">Click Released products.</span></span>
3. <span data-ttu-id="1ff04-108">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="1ff04-108">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="1ff04-109">Nel riquadro azioni, fare clic su Gestione articoli.</span><span class="sxs-lookup"><span data-stu-id="1ff04-109">On the Action Pane, click Manage inventory.</span></span>
5. <span data-ttu-id="1ff04-110">Fare clic su Codici a barre,</span><span class="sxs-lookup"><span data-stu-id="1ff04-110">Click Bar codes.</span></span>
6. <span data-ttu-id="1ff04-111">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="1ff04-111">Click New.</span></span>
7. <span data-ttu-id="1ff04-112">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="1ff04-112">In the list, mark the selected row.</span></span>
8. <span data-ttu-id="1ff04-113">Nel campo Impostazione codice a barre immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="1ff04-113">In the Barcode setup field, enter or select a value.</span></span>
9. <span data-ttu-id="1ff04-114">Nel campo Codice a barre immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="1ff04-114">In the Bar code field, enter or select a value.</span></span>
10. <span data-ttu-id="1ff04-115">Digitare un valore nel campo Codice a barre.</span><span class="sxs-lookup"><span data-stu-id="1ff04-115">In the Bar code field, type a value.</span></span>
    * <span data-ttu-id="1ff04-116">Premere il tasto TAB.</span><span class="sxs-lookup"><span data-stu-id="1ff04-116">Press the Tab key.</span></span>  
11. <span data-ttu-id="1ff04-117">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="1ff04-117">Close the page.</span></span>
12. <span data-ttu-id="1ff04-118">Nel campo Quantità immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="1ff04-118">In the Quantity field, enter a number.</span></span>
13. <span data-ttu-id="1ff04-119">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="1ff04-119">Click Save.</span></span>
    * <span data-ttu-id="1ff04-120">Quando si fa clic su Salva, la verifica del codice a barre viene eseguito e in questo caso viene visualizzato un errore in cui viene indicato che la cifra di controllo prevista è 8, mentre è stato trovato 3.</span><span class="sxs-lookup"><span data-stu-id="1ff04-120">When you click Save, the barcode check is run, and in this case it will display an error stating that the expected check digit is 8, but that 3 was found.</span></span> <span data-ttu-id="1ff04-121">Aggiornare manualmente il numero di codice a barre in modo che 8 sia alla fine.</span><span class="sxs-lookup"><span data-stu-id="1ff04-121">Manually update the barcode number so that 8 is at the end.</span></span>  
14. <span data-ttu-id="1ff04-122">Nel campo Codice a barre immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="1ff04-122">In the Bar code field, enter or select a value.</span></span>
15. <span data-ttu-id="1ff04-123">Digitare un valore nel campo Codice a barre.</span><span class="sxs-lookup"><span data-stu-id="1ff04-123">In the Bar code field, type a value.</span></span>
    * <span data-ttu-id="1ff04-124">Premere il tasto TAB.</span><span class="sxs-lookup"><span data-stu-id="1ff04-124">Press the Tab key.</span></span>  
16. <span data-ttu-id="1ff04-125">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="1ff04-125">Close the page.</span></span>
17. <span data-ttu-id="1ff04-126">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="1ff04-126">Click Save.</span></span>
18. <span data-ttu-id="1ff04-127">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="1ff04-127">Close the page.</span></span>

