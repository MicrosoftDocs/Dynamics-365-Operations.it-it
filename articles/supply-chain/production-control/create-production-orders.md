---
title: Creare ordini di produzione
description: "Quando si crea un ordine di produzione, si esegue una richiesta di avvio della produzione di un articolo. Nell'ordine di produzione sono contenute informazioni sull'articolo che verrà prodotto, sulla quantità da produrre e sulla data di fine pianificata. Sono contenute anche informazioni sui materiali da utilizzare e sul processo da seguire per produrre l'articolo."
author: johanhoffmann
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ProdTable, ProdTableCreate
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 19741
ms.assetid: bbb6e69d-479c-45fc-a0a8-66da5df16c7f
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: d962dbf5a5a4e3847252171d3631f78341640bc7
ms.contentlocale: it-it
ms.lasthandoff: 11/03/2017

---

# <a name="create-production-orders"></a><span data-ttu-id="270c7-105">Creare ordini di produzione</span><span class="sxs-lookup"><span data-stu-id="270c7-105">Create production orders</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="270c7-106">Quando si crea un ordine di produzione, si esegue una richiesta di avvio della produzione di un articolo.</span><span class="sxs-lookup"><span data-stu-id="270c7-106">When a production order is created, a request is initiated to start producing an item.</span></span> <span data-ttu-id="270c7-107">Nell'ordine di produzione sono contenute informazioni sull'articolo che verrà prodotto, sulla quantità da produrre e sulla data di fine pianificata.</span><span class="sxs-lookup"><span data-stu-id="270c7-107">The production order contains information about what will be produced, the quantity to produce, and the planned finish date.</span></span> <span data-ttu-id="270c7-108">Sono contenute anche informazioni sui materiali da utilizzare e sul processo da seguire per produrre l'articolo.</span><span class="sxs-lookup"><span data-stu-id="270c7-108">It also contains information about which materials to consume and which process to follow to produce the item.</span></span>

<span data-ttu-id="270c7-109">Un ordine di produzione attraversa le fasi del ciclo di vita della produzione.</span><span class="sxs-lookup"><span data-stu-id="270c7-109">A production order passes through stages of the production life cycle.</span></span> <span data-ttu-id="270c7-110">Al momento della creazione, a un ordine viene assegnato lo stato **Creato**.</span><span class="sxs-lookup"><span data-stu-id="270c7-110">When an order is created, it is assigned the status **Created**.</span></span> <span data-ttu-id="270c7-111">Al termine della creazione, a un ordine viene assegnato lo stato **Terminato**.</span><span class="sxs-lookup"><span data-stu-id="270c7-111">When an order is finished, it is assigned the status **Ended**.</span></span> <span data-ttu-id="270c7-112">L'impostazione dei parametri in ogni fase consente a un utente di configurare ogni fase.</span><span class="sxs-lookup"><span data-stu-id="270c7-112">A parameter setting in each stage allows a user to configure each step.</span></span> <span data-ttu-id="270c7-113">L'impostazione può essere impostata per un singolo utente o per tutti gli utenti.</span><span class="sxs-lookup"><span data-stu-id="270c7-113">The setting can be set up for a single user or for all users.</span></span>

<span data-ttu-id="270c7-114">La distinta base di produzione e il ciclo di lavorazione di produzione sono le entità principali dell'ordine di produzione.</span><span class="sxs-lookup"><span data-stu-id="270c7-114">The production bill of material and the production route are the main entities of the production order.</span></span> <span data-ttu-id="270c7-115">Vengono copiati nell'ordine di produzione in base all'articolo e alla quantità che saranno prodotti.</span><span class="sxs-lookup"><span data-stu-id="270c7-115">They are copied to the production order based on the selected item and quantity that are going to be produced.</span></span> <span data-ttu-id="270c7-116">Prima che venga avviato l'ordine di produzione, è possibile modificare la distinta base di produzione e il ciclo.</span><span class="sxs-lookup"><span data-stu-id="270c7-116">Before the production order is started, the production bill of material and route can be edited.</span></span>

<span data-ttu-id="270c7-117">Un ordine di produzione può essere creato negli scenari seguenti:</span><span class="sxs-lookup"><span data-stu-id="270c7-117">A production order can be created in the following scenarios:</span></span>

-   <span data-ttu-id="270c7-118">Creato dall'esecuzione di pianificazione generale in base alla richiesta di materiale.</span><span class="sxs-lookup"><span data-stu-id="270c7-118">Created by master planning execution based on material demand.</span></span>
-   <span data-ttu-id="270c7-119">Creato direttamente da una riga ordine cliente o quando un ordine di produzione di livello superiore viene creato e stimato (offerta sottoposta a pegging).</span><span class="sxs-lookup"><span data-stu-id="270c7-119">Created directly from a sales order line or when a higher-level production order is created and estimated (pegged supply).</span></span>
-   <span data-ttu-id="270c7-120">Creato manualmente.</span><span class="sxs-lookup"><span data-stu-id="270c7-120">Created manually.</span></span>





