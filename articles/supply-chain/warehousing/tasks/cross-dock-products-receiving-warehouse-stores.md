---
title: Cross-docking di prodotti da magazzino ricevente a punti vendita
description: In questa procedura vengono descritti i passaggi per creare ed elaborare un cross-docking per distribuire i prodotti dall'ubicazione di ricevimento di un ordine fornitore a uno o più punti vendita.
author: ShylaThompson
manager: tfehr
ms.date: 02/17/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f17585359d93030d7830eb60ce07af7c48f5d49f
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/10/2020
ms.locfileid: "3979577"
---
# <a name="cross-dock-products-from-receiving-warehouse-to-stores"></a><span data-ttu-id="1e576-103">Cross-docking di prodotti da magazzino ricevente a punti vendita</span><span class="sxs-lookup"><span data-stu-id="1e576-103">Cross-dock products from receiving warehouse to stores</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="1e576-104">In questa procedura vengono descritti i passaggi per creare ed elaborare un cross-docking per distribuire i prodotti dall'ubicazione di ricevimento di un ordine fornitore a uno o più punti vendita.</span><span class="sxs-lookup"><span data-stu-id="1e576-104">This procedure walks through the steps to create and process a Cross-dock to distribute products from the receiving location of a purchase order to one or many stores.</span></span> <span data-ttu-id="1e576-105">L'utente può definire più configurazioni e seguire i suggerimenti del sistema per distribuire i prodotti oppure immettere manualmente i punti vendita a cui i prodotti vengono distribuiti e la quantità distribuita a ogni punto vendita.</span><span class="sxs-lookup"><span data-stu-id="1e576-105">The user can define multiple configurations and have the system suggest how to distribute the products, or manually enter where the products are distributed to and how much gets distributed to each store.</span></span> <span data-ttu-id="1e576-106">La procedura non include l'impostazione dei dati che possono essere utilizzati nel cross-docking, ad esempio le regole di rifornimento, le gerarchie organizzative e i pesi dei punti vendita.</span><span class="sxs-lookup"><span data-stu-id="1e576-106">The procedure doesn't include setup of data that can be used in the Cross-dock, such as replenishment rules, organizational hierarchies, and store weights.</span></span> <span data-ttu-id="1e576-107">La procedura utilizza la società dimostrativa USRT.</span><span class="sxs-lookup"><span data-stu-id="1e576-107">The procedure uses the USRT demo company.</span></span>

1. <span data-ttu-id="1e576-108">Fare clic su Tutti gli ordini fornitore.</span><span class="sxs-lookup"><span data-stu-id="1e576-108">Go to All purchase orders.</span></span>
2. <span data-ttu-id="1e576-109">Selezionare l'ordine fornitore nell'elenco e fare clic sul collegamento per aprire l'ordine.</span><span class="sxs-lookup"><span data-stu-id="1e576-109">Select a purchase order in the list and click the link to open the order.</span></span>
3. <span data-ttu-id="1e576-110">Nel riquadro azioni fare clic su Retail e Commerce.</span><span class="sxs-lookup"><span data-stu-id="1e576-110">On the Action Pane, click Retail and Commerce.</span></span>
4. <span data-ttu-id="1e576-111">Fare clic su Cross-docking.</span><span class="sxs-lookup"><span data-stu-id="1e576-111">Click Cross docking.</span></span>
5. <span data-ttu-id="1e576-112">Fare clic su Modifica.</span><span class="sxs-lookup"><span data-stu-id="1e576-112">Click Edit.</span></span>
    * <span data-ttu-id="1e576-113">La categoria può essere utilizzata per filtrare gli articoli nella sezione Righe.</span><span class="sxs-lookup"><span data-stu-id="1e576-113">The category can be used to filter the items in the Lines section.</span></span>  
6. <span data-ttu-id="1e576-114">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="1e576-114">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="1e576-115">Nel campo Quantità cross-docking, immettere un valore per specificare la quantità acquistata del prodotto selezionato che deve essere distribuita.</span><span class="sxs-lookup"><span data-stu-id="1e576-115">In the Cross docking quantity field, type a value to specify how much of the quantity being purchased of the selected product should be distributed.</span></span>
8. <span data-ttu-id="1e576-116">Nel campo Quantità cross-docking aggiuntiva, immettere un valore per specificare le quantità da distribuire per i prodotti disponibili acquistati</span><span class="sxs-lookup"><span data-stu-id="1e576-116">In the Additional cross docking quantity field, enter a value to specify the quantities to distribute for the available products being purchased</span></span>
9. <span data-ttu-id="1e576-117">Nel campo Distribuzione, immettere 'Peso ubicazione'.</span><span class="sxs-lookup"><span data-stu-id="1e576-117">In the Distribution field, enter 'Location weight'.</span></span>
    * <span data-ttu-id="1e576-118">È possibile selezionare gli altri tipi per utilizzare regole diverse per la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="1e576-118">You can select the other types to use different rules for the distribution.</span></span>  
10. <span data-ttu-id="1e576-119">Nel campo Gerarchia di rifornimenti immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="1e576-119">In the Replenishment hierarchy field, select a value.</span></span>
11. <span data-ttu-id="1e576-120">Selezionare Sì nel campo Rispetta assortimento.</span><span class="sxs-lookup"><span data-stu-id="1e576-120">Select Yes in the Respect assortments field.</span></span>
12. <span data-ttu-id="1e576-121">Fare clic su Calcola quantità.</span><span class="sxs-lookup"><span data-stu-id="1e576-121">Click Calculate quantities.</span></span>
13. <span data-ttu-id="1e576-122">Fare clic su Crea ordine.</span><span class="sxs-lookup"><span data-stu-id="1e576-122">Click Create order.</span></span>
14. <span data-ttu-id="1e576-123">Fare clic su Sì.</span><span class="sxs-lookup"><span data-stu-id="1e576-123">Click Yes.</span></span>
15. <span data-ttu-id="1e576-124">Nell'elenco, individuare e selezionare il magazzino di ricezione dei prodotti</span><span class="sxs-lookup"><span data-stu-id="1e576-124">In the list, find and select a warehouse that received products</span></span>
16. <span data-ttu-id="1e576-125">Fare clic su Ordine per visualizzare gli ordini creati per il magazzino selezionato</span><span class="sxs-lookup"><span data-stu-id="1e576-125">Click Order to view the orders that got created for the selected warehouse</span></span>

