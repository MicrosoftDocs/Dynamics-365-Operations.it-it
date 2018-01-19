---
title: Gestione e creazione di categorie di prodotti
description: In questo argomento vengono descritti i miglioramenti apportati alla gestione delle categorie di prodotti al dettaglio. Questi miglioramenti consentono ai responsabili del merchandising di avere una correlazione tra la gerarchia di prodotti al dettaglio e i dettagli dei prodotti rilasciati.
author: ashishmsft
manager: AnnBe
ms.date: 09/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-retail
ms.technology: 
ms.search.form: RetailCategoryAndProductWorkspace, RetailCategory
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.search.region: Global
ms.search.industry: retail
ms.author: asharchw
ms.search.validFrom: 2017-09-01
ms.dyn365.ops.version: 
ms.translationtype: HT
ms.sourcegitcommit: ceea24519d641c676521771cee274feb64ca7783
ms.openlocfilehash: 2aa9f913b7faac393c4b403c6c36b99cc9acc80c
ms.contentlocale: it-it
ms.lasthandoff: 01/19/2018

---

# <a name="product-category-management-and-creation"></a><span data-ttu-id="91c34-104">Gestione e creazione di categorie di prodotti</span><span class="sxs-lookup"><span data-stu-id="91c34-104">Product category management and creation</span></span>

[!include[banner](./includes/banner.md)]

<span data-ttu-id="91c34-105">I miglioramenti apportati alla gestione delle categorie di prodotti al dettaglio consentono ai responsabili del merchandising di avere una correlazione tra la gerarchia di prodotti al dettaglio e i dettagli dei prodotti rilasciati.</span><span class="sxs-lookup"><span data-stu-id="91c34-105">Enhancements that have been made to the management experience for Retail product categories let merchandising managers have a correlation between Retail product hierarchy and released product details.</span></span> <span data-ttu-id="91c34-106">Per visualizzare questi miglioramenti, nell'area di lavoro **Gestione categorie e prodotti**, selezionare **Gerarchia di prodotti al dettaglio** per aprire la pagina **Nuova struttura della categoria di prodotti al dettaglio**.</span><span class="sxs-lookup"><span data-stu-id="91c34-106">To view these enhancements, in the **Category & product management**  workspace, select **Retail product hierarchy** to open the **New structure of Retail product category** page.</span></span> 

<span data-ttu-id="91c34-107">Nelle versioni precedenti, le proprietà di prodotto erano suddivise in proprietà di prodotto di base e proprietà di prodotto al dettaglio, a seconda dell'ambito della relativa applicabilità.</span><span class="sxs-lookup"><span data-stu-id="91c34-107">In previous releases, product properties were divided into Basic product properties and Retail product properties, based on the scope of their applicability.</span></span> <span data-ttu-id="91c34-108">Le proprietà di prodotto al dettaglio erano *globali*.</span><span class="sxs-lookup"><span data-stu-id="91c34-108">Retail product properties were *global*.</span></span> <span data-ttu-id="91c34-109">In altre parole, per una determinata proprietà di prodotto, lo stesso valore viene condiviso tra tutte le persone giuridiche.</span><span class="sxs-lookup"><span data-stu-id="91c34-109">In other words, for a given product property, the same value is shared across all legal entities.</span></span> <span data-ttu-id="91c34-110">Le proprietà di prodotto di base erano *specifiche della persona giuridica*.</span><span class="sxs-lookup"><span data-stu-id="91c34-110">Basic product properties were *legal entity–specific*.</span></span> <span data-ttu-id="91c34-111">In altre parole, una determinata proprietà di prodotto può differire nelle persone giuridiche in base a singoli requisiti aziendali.</span><span class="sxs-lookup"><span data-stu-id="91c34-111">In other words, a given product property might differ across legal entities, based on individual business requirements.</span></span>

<span data-ttu-id="91c34-112">Con questi miglioramenti, per le proprietà di prodotto nella categoria di prodotti al dettaglio, i campi rimangono distinti, in base alla relativa applicabilità in un gruppo, per riflettere la struttura del modulo Dettagli prodotto rilasciato.</span><span class="sxs-lookup"><span data-stu-id="91c34-112">With these enhancements, for product properties in the Retail product category, we continue to separate the fields, based on their applicability within a group, to reflect the released product details form structure.</span></span>

<span data-ttu-id="91c34-113">È possibile passare dalla gestione di proprietà specifiche della persona giuridica in tutte le persone giuridiche alla gestione delle stesse per una specifica persona giuridica e viceversa.</span><span class="sxs-lookup"><span data-stu-id="91c34-113">You can switch between managing legal-entity specific properties across all legal entities and managing them for a specific legal entity.</span></span> <span data-ttu-id="91c34-114">A questo proposito, selezionare **Visualizza/Modifica per tutte le persone giuridiche** o **Visualizza/Modifica per una specifica persona giuridica** come necessario.</span><span class="sxs-lookup"><span data-stu-id="91c34-114">Just select **View/Edit for all legal entities** or **View/Edit for a specific legal entity** as you require.</span></span>

<span data-ttu-id="91c34-115">I responsabili del merchandising possono inoltre definire valori predefiniti per un ulteriore insieme di proprietà di prodotto a livello di una singola categoria.</span><span class="sxs-lookup"><span data-stu-id="91c34-115">Merchandising managers can also define default values for an additional set of product properties at the level of an individual category.</span></span> <span data-ttu-id="91c34-116">Questi valori di proprietà vengono ereditati da un prodotto, in base alla relativa associazione a una categoria al momento della creazione del prodotto.</span><span class="sxs-lookup"><span data-stu-id="91c34-116">These property values are inherited by a product, based on their association with a category at the time of product creation.</span></span>

## <a name="select-properties-to-update-products-from-the-retail-product-category-form"></a><span data-ttu-id="91c34-117">Selezionare le proprietà per aggiornare i prodotti nel modulo Categoria di prodotti al dettaglio</span><span class="sxs-lookup"><span data-stu-id="91c34-117">Select properties to update products from the Retail product category form</span></span>

<span data-ttu-id="91c34-118">È possibile utilizzare proprietà di raggruppamento logiche per determinare quali proprietà di prodotto aggiornate devono essere incluse nei prodotti associati.</span><span class="sxs-lookup"><span data-stu-id="91c34-118">You can use logical grouping properties to select which updated product properties should be pushed to associated products.</span></span>

<span data-ttu-id="91c34-119">I responsabili del merchandising possono modificare queste proprietà di prodotto ereditate per ciascun prodotto, allo scopo di soddisfare i requisiti aziendali.</span><span class="sxs-lookup"><span data-stu-id="91c34-119">Merchandising managers can modify these inherited product properties for each product, to meet individual business requirements.</span></span>

