--- 
title: " Inviare i prodotti del centro di distribuzione al punto vendita utilizzando la distribuzione push"
description: "In questa procedura vengono descritti i passaggi per creare ed elaborare una distribuzione push da un'ubicazione a uno o più punti vendita."
author: rubencdelgado
manager: AnnBe
ms.date: 02/17/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: ceea24519d641c676521771cee274feb64ca7783
ms.openlocfilehash: ee2e3c743aee5eb7e34b0e3e79bfb4aa4ac0a029
ms.contentlocale: it-it
ms.lasthandoff: 01/19/2018

---
# <a name="push-products-from-distribution-center-to-store-using-buyers-push"></a><span data-ttu-id="0d4ae-103"> Inviare i prodotti del centro di distribuzione al punto vendita utilizzando la distribuzione push</span><span class="sxs-lookup"><span data-stu-id="0d4ae-103">Push products from distribution center to store using buyer's push</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="0d4ae-104">In questa procedura vengono descritti i passaggi per creare ed elaborare una distribuzione push da un'ubicazione a uno o più punti vendita.</span><span class="sxs-lookup"><span data-stu-id="0d4ae-104">This procedure walks through the steps to create and process a Buyer´s push to distribute products from one location to one or many stores.</span></span> <span data-ttu-id="0d4ae-105">L'utente può definire più configurazioni e seguire i suggerimenti del sistema per distribuire i prodotti oppure immettere manualmente i punti vendita a cui i prodotti vengono distribuiti e la quantità distribuita a ogni punto vendita.</span><span class="sxs-lookup"><span data-stu-id="0d4ae-105">The user can define multiple configurations and have the system suggest how to distribute the products, or manually enter where the products are distributed to and how much gets distributed to each store.</span></span> <span data-ttu-id="0d4ae-106">La procedura non include l'impostazione dei dati che possono essere utilizzati nella distribuzione push, ad esempio le regole di rifornimento, le gerarchie organizzative e i pesi dei punti vendita.</span><span class="sxs-lookup"><span data-stu-id="0d4ae-106">This procedure doesn't include setup of data that can be used in the Buyer´s push, such as replenishment rules, organizational hierarchies, and store weights.</span></span> <span data-ttu-id="0d4ae-107">Questa procedura utilizza la società dimostrativa USRT.</span><span class="sxs-lookup"><span data-stu-id="0d4ae-107">This procedure uses the USRT demo company.</span></span>

1. <span data-ttu-id="0d4ae-108">Passare a Distribuzione push.</span><span class="sxs-lookup"><span data-stu-id="0d4ae-108">Go to Buyer's push.</span></span>
2. <span data-ttu-id="0d4ae-109">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="0d4ae-109">Click New.</span></span>
3. <span data-ttu-id="0d4ae-110">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="0d4ae-110">In the Description field, type a value.</span></span>
4. <span data-ttu-id="0d4ae-111">Nel campo Sito immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="0d4ae-111">In the Site field, enter or select a value.</span></span>
5. <span data-ttu-id="0d4ae-112">Nel campo Magazzino, immettere o selezionare un magazzino con prodotti con quantità disponibili.</span><span class="sxs-lookup"><span data-stu-id="0d4ae-112">In the Warehouse field, enter or select a warehouse that has products with on-hand quantities.</span></span>
6. <span data-ttu-id="0d4ae-113">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="0d4ae-113">Click Add.</span></span>
7. <span data-ttu-id="0d4ae-114">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="0d4ae-114">In the list, mark the selected row.</span></span>
8. <span data-ttu-id="0d4ae-115">Nel campo Numero articolo immettere o selezionare un prodotto.</span><span class="sxs-lookup"><span data-stu-id="0d4ae-115">In the Item number field, enter or select a product.</span></span>
9. <span data-ttu-id="0d4ae-116">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="0d4ae-116">Click Add.</span></span>
10. <span data-ttu-id="0d4ae-117">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="0d4ae-117">In the list, mark the selected row.</span></span>
11. <span data-ttu-id="0d4ae-118">Nel campo Numero articolo immettere o selezionare un prodotto variante.</span><span class="sxs-lookup"><span data-stu-id="0d4ae-118">In the Item number field, enter or select a variant product.</span></span>
    * <span data-ttu-id="0d4ae-119">Quando si immette un prodotto variante, le righe vengono create per ogni variante.</span><span class="sxs-lookup"><span data-stu-id="0d4ae-119">When entering a variant product, lines will be created for each variant.</span></span>  
12. <span data-ttu-id="0d4ae-120">Nell'elenco selezionare una riga.</span><span class="sxs-lookup"><span data-stu-id="0d4ae-120">In the list, mark a row.</span></span>
13. <span data-ttu-id="0d4ae-121">Nel campo Quantità inviata con distribuzione push, immettere la quantità del prodotto selezionato che si desidera distribuire.</span><span class="sxs-lookup"><span data-stu-id="0d4ae-121">In the Pushed quantity field, type how many of the selected product you want to distribute.</span></span>
14. <span data-ttu-id="0d4ae-122">Nel campo Quantità aggiuntiva da distribuire, immettere la quantità di prodotti con quantità disponibile da distribuire.</span><span class="sxs-lookup"><span data-stu-id="0d4ae-122">In the Additional quantity to push field, enter the quantity of the products that have available quantity to distribute.</span></span>
15. <span data-ttu-id="0d4ae-123">Nel campo Distribuzione, immettere 'Peso ubicazione'.</span><span class="sxs-lookup"><span data-stu-id="0d4ae-123">In the Distribution field, enter 'Location weight'.</span></span>
    * <span data-ttu-id="0d4ae-124">È possibile selezionare gli altri tipi per utilizzare altre regole per la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="0d4ae-124">You can select the other types to use other rules for the distribution.</span></span>  
16. <span data-ttu-id="0d4ae-125">Nel campo Gerarchia di rifornimenti immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="0d4ae-125">In the Replenishment hierarchy field, select a value.</span></span>
17. <span data-ttu-id="0d4ae-126">Selezionare Sì nel campo Rispetta assortimento.</span><span class="sxs-lookup"><span data-stu-id="0d4ae-126">Select Yes in the Respect assortments field.</span></span>
18. <span data-ttu-id="0d4ae-127">Fare clic Calcola quantità e rivedere le quantità aggiunte alle righe nella sezione Magazzino.</span><span class="sxs-lookup"><span data-stu-id="0d4ae-127">Click Calculate quantities and review the quantities that are added to the rows in the Warehouse section.</span></span>
19. <span data-ttu-id="0d4ae-128">Fare clic su Crea ordine.</span><span class="sxs-lookup"><span data-stu-id="0d4ae-128">Click Create order.</span></span>
20. <span data-ttu-id="0d4ae-129">Fare clic su Sì.</span><span class="sxs-lookup"><span data-stu-id="0d4ae-129">Click Yes.</span></span>


