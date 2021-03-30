---
title: Gestire le categorie di prodotti e i prodotti
description: In questo argomento viene descritto come i responsabili del merchandising possono utilizzare le categorie di prodotti per gestire le relazioni tra la gerarchia di prodotti di Commerce e i dettagli dei prodotti rilasciati.
author: ashishmsft
manager: AnnBe
ms.date: 10/23/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: EcoResCategorySearchList, EcoResAttribute, COODualUseCategories, EcoResProductCategory, EcoResCategoryAddProduct, EcoResAttributeValue
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: c7ed2ba5-87c6-4d99-9728-2a83e6d95ca9
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2017-09-01
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 95a4bac6beeaf5fad449027d93132fc1499288a0
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5215488"
---
# <a name="manage-product-categories-and-products"></a><span data-ttu-id="c10f1-103">Gestire le categorie di prodotti e i prodotti</span><span class="sxs-lookup"><span data-stu-id="c10f1-103">Manage product categories and products</span></span>

[!include [banner](./includes/banner.md)]

<span data-ttu-id="c10f1-104">In questo argomento viene descritta una modalità avanzata per gestire le categorie di prodotti e i prodotti in Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="c10f1-104">This topic describes an enhanced way to manage product categories and products in Dynamics 365 Commerce.</span></span> <span data-ttu-id="c10f1-105">I miglioramenti consentono ai responsabili del merchandising di visualizzare una struttura di proprietà dei prodotti condivisa tra la gerarchia di prodotti e i dettagli dei prodotti rilasciati.</span><span class="sxs-lookup"><span data-stu-id="c10f1-105">The enhancements let merchandising managers view a structure of product properties that is shared between the product hierarchy and released product details.</span></span>

<span data-ttu-id="c10f1-106">Per ulteriori informazioni su come gestire le categorie di prodotti, nell'area di lavoro **Gestione categorie e prodotti** selezionare il riquadro **Gerarchia di prodotti di Commerce**.</span><span class="sxs-lookup"><span data-stu-id="c10f1-106">To learn more about how to manage product categories, in the **Category and product management** workspace, select the **Commerce product hierarchy** tile.</span></span>

<span data-ttu-id="c10f1-107">Notare la struttura avanzata della pagina **Gerarchia di prodotti di Commerce** che viene visualizzata.</span><span class="sxs-lookup"><span data-stu-id="c10f1-107">Notice the enhanced structure of the **Commerce product hierarchy** page that appears.</span></span> <span data-ttu-id="c10f1-108">Nelle versioni precedenti dell'app, le proprietà di prodotto erano suddivise in *proprietà di prodotto di base* e *proprietà di prodotto al dettaglio*, a seconda dell'ambito di applicabilità.</span><span class="sxs-lookup"><span data-stu-id="c10f1-108">In previous versions of the app, product properties were divided into *basic product properties* and *Retail product properties*, based on the scope of their applicability.</span></span> <span data-ttu-id="c10f1-109">Le proprietà di prodotto al dettaglio sono *globali* nell'ambito dell'applicabilità.</span><span class="sxs-lookup"><span data-stu-id="c10f1-109">Retail product properties are *global* in their scope of applicability.</span></span> <span data-ttu-id="c10f1-110">In altre parole, per una determinata proprietà di prodotto, lo stesso valore viene condiviso tra tutte le persone giuridiche.</span><span class="sxs-lookup"><span data-stu-id="c10f1-110">In other words, for a given product property, the same value is shared across all legal entities.</span></span> <span data-ttu-id="c10f1-111">Le proprietà di prodotto di base sono invece *specifiche della persona giuridica*.</span><span class="sxs-lookup"><span data-stu-id="c10f1-111">By contrast, basic product properties are *legal entity–specific*.</span></span> <span data-ttu-id="c10f1-112">In altre parole, per una determinata proprietà di prodotto di base il valore può differire tra le persone giuridiche, in base ai singoli requisiti aziendali di ogni persona giuridica.</span><span class="sxs-lookup"><span data-stu-id="c10f1-112">In other words, for a given basic product property, the value can differ across legal entities, depending on the individual business requirements of each legal entity.</span></span>

<span data-ttu-id="c10f1-113">Nella struttura avanzata di categorie di prodotti, le proprietà di prodotto sono separate in modo logico in base alla relativa applicabilità in un gruppo, per riflettere la struttura del modulo dei dettagli dei prodotti rilasciati.</span><span class="sxs-lookup"><span data-stu-id="c10f1-113">In the enhanced product category structure, product properties are logically separated based on their applicability in a group, to reflect the structure of the released product details form structure.</span></span>

![Raggruppamento dei campi in base all'ambito di applicabilità delle proprietà](media/NoticeGroupingOfFieldsBasedOnTheirScope.PNG)

<span data-ttu-id="c10f1-115">È possibile passare dalla gestione di proprietà specifiche della persona giuridica in tutte le persone giuridiche alla gestione delle stesse per una specifica persona giuridica e viceversa.</span><span class="sxs-lookup"><span data-stu-id="c10f1-115">You can switch between managing legal entity–specific properties across all legal entities and managing them for a specific legal entity.</span></span>

<span data-ttu-id="c10f1-116">Per visualizzare le proprietà in tutte le persone giuridiche, selezionare **Visualizza per tutte le persone giuridiche** (o **Modifica per tutte le persone giuridiche**).</span><span class="sxs-lookup"><span data-stu-id="c10f1-116">To manage properties across all legal entities, select **View for all legal entities** (or **Edit for all legal entities**).</span></span>

![Visualizza/Modifica per tutte le persone giuridiche](media/ToggleBackToEditForSpecificLegalEntity.PNG)

<span data-ttu-id="c10f1-118">Per gestire le proprietà di una persona giuridica specifica, selezionare **Visualizza per una specifica persona giuridica** (o **Modifica per una persona giuridica specifica**).</span><span class="sxs-lookup"><span data-stu-id="c10f1-118">To manage properties for a specific legal entity, select **View for a specific legal entity** (or **Edit for a specific legal entity**).</span></span>

![Visualizza/Modifica per una specifica persona giuridica](media/ToggleToEditForAllLegalEntities.PNG)

<span data-ttu-id="c10f1-120">Inoltre, nella struttura avanzata di categorie di prodotti, un responsabile del merchandising può ora definire valori predefiniti per un insieme di proprietà di prodotto aggiuntivo a livello di singola categoria.</span><span class="sxs-lookup"><span data-stu-id="c10f1-120">Additionally, in the enhanced product category structure, a merchandising manager can now define default values for an additional set of product properties at the level of the individual category.</span></span> <span data-ttu-id="c10f1-121">Quando i prodotti vengono creati, ereditano i valori predefiniti per le proprietà i prodotto, in base all'associazione di tali proprietà con una categoria individuale nella gerarchia di prodotti.</span><span class="sxs-lookup"><span data-stu-id="c10f1-121">Then, when products are created, they inherit default values for their product properties, based on the association of those properties with an individual category in the product hierarchy.</span></span> <span data-ttu-id="c10f1-122">Queste proprietà di prodotto ereditate possono anche essere modificate per ciascun prodotto allo scopo di soddisfare i requisiti aziendali.</span><span class="sxs-lookup"><span data-stu-id="c10f1-122">These inherited product properties can also be modified for each product to meet individual business requirements.</span></span>

## <a name="selecting-properties-to-update-products-on-the-commerce-product-hierarchy-page"></a><span data-ttu-id="c10f1-123">Selezione delle proprietà per aggiornare i prodotti nella pagina della categoria di prodotti di Commerce</span><span class="sxs-lookup"><span data-stu-id="c10f1-123">Selecting properties to update products on the Commerce product hierarchy page</span></span>

<span data-ttu-id="c10f1-124">È possibile utilizzare la nuova struttura avanzata per le proprietà di prodotto per selezionare quali proprietà di prodotto aggiornate devono essere distribuite ai prodotti associati.</span><span class="sxs-lookup"><span data-stu-id="c10f1-124">You can use the new enhanced structure for product properties to select updated product properties that must be pushed to the associated products.</span></span> <span data-ttu-id="c10f1-125">Nella pagina **Gerarchia di prodotti di Commerce**, nel Riquadro azioni, selezionare **Categoria**, quindi selezionare **Aggiorna prodotti** per aprire la finestra di dialogo **Aggiorna prodotti**.</span><span class="sxs-lookup"><span data-stu-id="c10f1-125">On the **Commerce product hierarchy** page, on the Action Pane, select **Category**, and then select **Update products** to open the **Update products** dialog box.</span></span>

![Finestra di dialogo Aggiorna prodotti](media/NewUpdateProductsEnhancedView.PNG)


[!INCLUDE[footer-include](../includes/footer-banner.md)]