---
title: Gestione di categorie di prodotti
description: In questo argomento viene descritto come i responsabili del merchandising possono utilizzare le categorie di prodotti al dettaglio per gestire le relazioni tra la gerarchia di prodotti al dettaglio e i dettagli dei prodotti rilasciati.
author: ashishmsft
manager: AnnBe
ms.date: 10/23/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations, Retail
ms.custom: 
ms.assetid: c7ed2ba5-87c6-4d99-9728-2a83e6d95ca9
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2017-09-01
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 25fa39dc81fc721d7593a25a102ce47041ebc5f0
ms.openlocfilehash: 4b7ef962b777a31e1da238a8ec1be9a42ec5bb5f
ms.contentlocale: it-it
ms.lasthandoff: 03/13/2018

---


# <a name="enhanced-product-and-category-management"></a><span data-ttu-id="a75de-103">Gestione avanzata di categorie e prodotti</span><span class="sxs-lookup"><span data-stu-id="a75de-103">Enhanced product and category management</span></span>

[!include[banner](./includes/banner.md)]

<span data-ttu-id="a75de-104">In questo argomento viene descritta una modalità avanzata per gestire le categorie di prodotti al dettaglio e i prodotti in Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="a75de-104">This topic describes an enhanced way to manage Retail product categories and products in Dynamics 365 for Retail.</span></span> <span data-ttu-id="a75de-105">Questi miglioramenti consentono ai responsabili del merchandising di visualizzare una struttura comune di proprietà dei prodotti tra la gerarchia di prodotti al dettaglio e i dettagli dei prodotti rilasciati.</span><span class="sxs-lookup"><span data-stu-id="a75de-105">These enhancements let merchandising managers view a common structure of product properties between Retail product hierarchy and released product details.</span></span>

<span data-ttu-id="a75de-106">Per ulteriori informazioni sulla gestione delle categorie di prodotti al dettaglio, passare a **Gerarchia di prodotti al dettaglio** dall'area di lavoro **Gestione categorie e prodotti** e osservare la struttura avanzata della pagina **Categoria di prodotti al dettaglio**.</span><span class="sxs-lookup"><span data-stu-id="a75de-106">To learn more about managing Retail product categories, go to **Retail product hierarchy** from the **Category and product management** workspace, and note the enhanced structure of the **Retail product category** page.</span></span>

![Area di lavoro di gestione di categorie e prodotti](media/LaunchRetailProductHierarchy.png)

<span data-ttu-id="a75de-108">Nelle versioni precedenti, le proprietà di prodotto erano suddivise in **proprietà di prodotto di base** e **proprietà di prodotto al dettaglio**, a seconda dell'ambito di applicabilità.</span><span class="sxs-lookup"><span data-stu-id="a75de-108">In previous versions, product properties were divided into **Basic product properties** and **Retail product properties**, based on the scope of their applicability.</span></span> <span data-ttu-id="a75de-109">Le **proprietà di prodotto al dettaglio** erano *globali* per ambito di applicabilità; ciò significa che per una **proprietà di prodotto al dettaglio** specificata, lo stesso valore viene condiviso da tutte le persone giuridiche.</span><span class="sxs-lookup"><span data-stu-id="a75de-109">**Retail product properties** were *global* by scope of applicability, which means that for a given **Retail product property**, the same value is shared across all legal entities.</span></span> <span data-ttu-id="a75de-110">Le **proprietà di prodotto di base** sono *specifiche della persona giuridica*.</span><span class="sxs-lookup"><span data-stu-id="a75de-110">**Basic product properties** are *legal entity specific*.</span></span> <span data-ttu-id="a75de-111">In altre parole, per una determinata **proprietà di prodotto di base** il valore può differire tra le persone giuridiche, in base ai singoli requisiti aziendali.</span><span class="sxs-lookup"><span data-stu-id="a75de-111">In other words, for a given **Basic product property** the value can differ across legal entities, based on individual business requirements.</span></span>

<span data-ttu-id="a75de-112">Nella struttura avanzata di categorie di prodotti al dettaglio, le proprietà di prodotto sono separate in modo logico in base alla relativa applicabilità in un gruppo, per riflettere la struttura del modulo dei dettagli dei prodotti rilasciati.</span><span class="sxs-lookup"><span data-stu-id="a75de-112">In the enhanced Retail product category structure, product properties are logically separated based on their applicability within a group, to reflect the released product details form structure.</span></span>

![Raggruppamento dei campi in base al loro ambito di applicabilità](media/NoticeGroupingOfFieldsBasedOnTheirScope.PNG)

<span data-ttu-id="a75de-114">È possibile passare dalla gestione di proprietà specifiche della persona giuridica in tutte le persone giuridiche alla gestione delle stesse per una specifica persona giuridica e viceversa.</span><span class="sxs-lookup"><span data-stu-id="a75de-114">You can switch between managing legal-entity specific properties across all legal entities and managing them for a specific legal entity.</span></span> <span data-ttu-id="a75de-115">Per effettuare tale operazione, selezionare **Visualizza/Modifica per tutte le persone giuridiche** o **Visualizza/Modifica per una specifica persona giuridica**.</span><span class="sxs-lookup"><span data-stu-id="a75de-115">To do this, select either **View/Edit for all legal entities** or **View/Edit for a specific legal entity**.</span></span>

![Alternare le modalità di visualizzazione tra una singola persona giuridica e tutte le persone giuridiche](media/ToggleBackToEditForSpecificLegalEntity.PNG)

![Alternare le modalità di visualizzazione tra una singola persona giuridica e tutte le persone giuridiche](media/ToggleToEditForAllLegalEntities.PNG)  

<span data-ttu-id="a75de-118">Rispetto alle versioni precedenti, nella nuova struttura di categorie di prodotti al dettaglio un responsabile del merchandising può inoltre definire valori predefiniti per un insieme di proprietà di prodotto aggiuntivo a un livello di singola categoria.</span><span class="sxs-lookup"><span data-stu-id="a75de-118">Compared to previous versions, in the new Retail product category structure a merchandising manager can also define default values for an additional set of product properties at an individual category level.</span></span> <span data-ttu-id="a75de-119">Al momento della creazione del prodotto, questi valori di proprietà del prodotto predefiniti vengono ereditati da un prodotto, in base alla relativa associazione a una singola categoria dalla gerarchia di prodotti al dettaglio.</span><span class="sxs-lookup"><span data-stu-id="a75de-119">At the time of product creation, these default product property values are inherited by a product, based on their association with an individual category from Retail product hierarchy.</span></span> <span data-ttu-id="a75de-120">Queste proprietà di prodotto ereditate possono essere anche modificate per ciascun prodotto, allo scopo di soddisfare i requisiti aziendali.</span><span class="sxs-lookup"><span data-stu-id="a75de-120">These inherited product properties can also be modified for each product, to meet individual business requirements.</span></span>

## <a name="select-properties-to-update-products-from-the-retail-product-category-form"></a><span data-ttu-id="a75de-121">Selezionare le proprietà per aggiornare i prodotti nel modulo Categoria di prodotti al dettaglio</span><span class="sxs-lookup"><span data-stu-id="a75de-121">Select properties to update products from the Retail product category form</span></span> 
 
<span data-ttu-id="a75de-122">È possibile utilizzare questa nuova struttura avanzata per le proprietà di prodotto per selezionare quali proprietà di prodotto aggiornate devono essere distribuite ai prodotti associati.</span><span class="sxs-lookup"><span data-stu-id="a75de-122">You can use this new enhanced structure for product properties to select which updated product properties must be pushed to associated products.</span></span> 

![Nuova visualizzazione avanzata di Aggiorna prodotti](media/NewUpdateProductsEnhancedView.PNG) 

<span data-ttu-id="a75de-124">I responsabili del merchandising possono modificare queste proprietà di prodotto ereditate per ciascun prodotto, allo scopo di soddisfare i requisiti aziendali.</span><span class="sxs-lookup"><span data-stu-id="a75de-124">Merchandising managers can modify these inherited product properties for each product, to meet individual business requirements.</span></span>


