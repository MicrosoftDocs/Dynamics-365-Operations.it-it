---
title: Gestire le categorie di prodotti al dettaglio e i prodotti
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
ms.sourcegitcommit: 190d0b59ad2e232b33b3c0d1700cbaf95c45aeca
ms.openlocfilehash: 0bcc5989edd9913fce414c0c24068f111d8c1aeb
ms.contentlocale: it-it
ms.lasthandoff: 01/04/2019

---

# <a name="manage-retail-product-categories-and-products"></a><span data-ttu-id="7a029-103">Gestire le categorie di prodotti al dettaglio e i prodotti</span><span class="sxs-lookup"><span data-stu-id="7a029-103">Manage Retail product categories and products</span></span>

[!include [banner](./includes/banner.md)]

<span data-ttu-id="7a029-104">In questo argomento viene descritta una modalità avanzata per gestire le categorie di prodotti al dettaglio e i prodotti in Microsoft Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="7a029-104">This topic describes an enhanced way to manage Retail product categories and products in Microsoft Dynamics 365 for Retail.</span></span> <span data-ttu-id="7a029-105">I miglioramenti consentono ai responsabili del merchandising di visualizzare una struttura di proprietà dei prodotti condivisa tra la gerarchia di prodotti al dettaglio e i dettagli dei prodotti rilasciati.</span><span class="sxs-lookup"><span data-stu-id="7a029-105">The enhancements let merchandising managers view a structure of product properties that is shared between the Retail product hierarchy and released product details.</span></span>

<span data-ttu-id="7a029-106">Per ulteriori informazioni su come gestire le categorie di prodotti al dettaglio, nell'area di lavoro **Gestione categorie e prodotti** selezionare il riquadro **Gerarchia di prodotti al dettaglio**.</span><span class="sxs-lookup"><span data-stu-id="7a029-106">To learn more about how to manage Retail product categories, in the **Category and product management** workspace, select the **Retail product hierarchy** tile.</span></span>

<span data-ttu-id="7a029-107">Notare la struttura avanzata della pagina **Gerarchia di prodotti al dettaglio** che viene visualizzata.</span><span class="sxs-lookup"><span data-stu-id="7a029-107">Notice the enhanced structure of the **Retail product hierarchy** page that appears.</span></span> <span data-ttu-id="7a029-108">Nelle versioni precedenti di Retail, le proprietà di prodotto erano suddivise in *proprietà di prodotto di base* e *proprietà di prodotto al dettaglio*, a seconda dell'ambito di applicabilità.</span><span class="sxs-lookup"><span data-stu-id="7a029-108">In previous versions of Retail, product properties were divided into *basic product properties* and *Retail product properties*, based on the scope of their applicability.</span></span> <span data-ttu-id="7a029-109">Le proprietà di prodotto al dettaglio sono *globali* nell'ambito dell'applicabilità.</span><span class="sxs-lookup"><span data-stu-id="7a029-109">Retail product properties are *global* in their scope of applicability.</span></span> <span data-ttu-id="7a029-110">In altre parole, per una determinata proprietà di prodotto al dettaglio, lo stesso valore viene condiviso tra tutte le persone giuridiche.</span><span class="sxs-lookup"><span data-stu-id="7a029-110">In other words, for a given Retail product property, the same value is shared across all legal entities.</span></span> <span data-ttu-id="7a029-111">Le proprietà di prodotto di base sono invece *specifiche della persona giuridica*.</span><span class="sxs-lookup"><span data-stu-id="7a029-111">By contrast, basic product properties are *legal entity–specific*.</span></span> <span data-ttu-id="7a029-112">In altre parole, per una determinata proprietà di prodotto di base il valore può differire tra le persone giuridiche, in base ai singoli requisiti aziendali di ogni persona giuridica.</span><span class="sxs-lookup"><span data-stu-id="7a029-112">In other words, for a given basic product property, the value can differ across legal entities, depending on the individual business requirements of each legal entity.</span></span>

<span data-ttu-id="7a029-113">Nella struttura avanzata di categorie di prodotti al dettaglio, le proprietà di prodotto sono separate in modo logico in base alla relativa applicabilità in un gruppo, per riflettere la struttura del modulo dei dettagli dei prodotti rilasciati.</span><span class="sxs-lookup"><span data-stu-id="7a029-113">In the enhanced Retail product category structure, product properties are logically separated based on their applicability in a group, to reflect the structure of the released product details form structure.</span></span>

![Raggruppamento dei campi in base all'ambito di applicabilità delle proprietà](media/NoticeGroupingOfFieldsBasedOnTheirScope.PNG)

<span data-ttu-id="7a029-115">È possibile passare dalla gestione di proprietà specifiche della persona giuridica in tutte le persone giuridiche alla gestione delle stesse per una specifica persona giuridica e viceversa.</span><span class="sxs-lookup"><span data-stu-id="7a029-115">You can switch between managing legal entity–specific properties across all legal entities and managing them for a specific legal entity.</span></span>

<span data-ttu-id="7a029-116">Per visualizzare le proprietà in tutte le persone giuridiche, selezionare **Visualizza per tutte le persone giuridiche** (o **Modifica per tutte le persone giuridiche**).</span><span class="sxs-lookup"><span data-stu-id="7a029-116">To manage properties across all legal entities, select **View for all legal entities** (or **Edit for all legal entities**).</span></span>

![Visualizza/Modifica per tutte le persone giuridiche](media/ToggleBackToEditForSpecificLegalEntity.PNG)

<span data-ttu-id="7a029-118">Per gestire le proprietà di una persona giuridica specifica, selezionare **Visualizza per una specifica persona giuridica** (o **Modifica per una persona giuridica specifica**).</span><span class="sxs-lookup"><span data-stu-id="7a029-118">To manage properties for a specific legal entity, select **View for a specific legal entity** (or **Edit for a specific legal entity**).</span></span>

![Visualizza/Modifica per una specifica persona giuridica](media/ToggleToEditForAllLegalEntities.PNG)

<span data-ttu-id="7a029-120">Inoltre, nella struttura avanzata di categorie di prodotti al dettaglio un responsabile del merchandising può ora definire valori predefiniti per un insieme di proprietà di prodotto aggiuntivo a livello di singola categoria.</span><span class="sxs-lookup"><span data-stu-id="7a029-120">Additionally, in the enhanced Retail product category structure, a merchandising manager can now define default values for an additional set of product properties at the level of the individual category.</span></span> <span data-ttu-id="7a029-121">Quando i prodotti vengono creati, ereditano i valori predefiniti per le proprietà i prodotto, in base all'associazione di tali proprietà con una categoria individuale nella gerarchia di prodotti al dettaglio.</span><span class="sxs-lookup"><span data-stu-id="7a029-121">Then, when products are created, they inherit default values for their product properties, based on the association of those properties with an individual category in Retail product hierarchy.</span></span> <span data-ttu-id="7a029-122">Queste proprietà di prodotto ereditate possono anche essere modificate per ciascun prodotto allo scopo di soddisfare i requisiti aziendali.</span><span class="sxs-lookup"><span data-stu-id="7a029-122">These inherited product properties can also be modified for each product to meet individual business requirements.</span></span>

## <a name="selecting-properties-to-update-products-on-the-retail-product-hierarchy-page"></a><span data-ttu-id="7a029-123">Selezione delle proprietà per aggiornare i prodotti nella pagina della categoria di prodotti al dettaglio</span><span class="sxs-lookup"><span data-stu-id="7a029-123">Selecting properties to update products on the Retail product hierarchy page</span></span>

<span data-ttu-id="7a029-124">È possibile utilizzare la nuova struttura avanzata per le proprietà di prodotto per selezionare quali proprietà di prodotto aggiornate devono essere distribuite ai prodotti associati.</span><span class="sxs-lookup"><span data-stu-id="7a029-124">You can use the new enhanced structure for product properties to select updated product properties that must be pushed to the associated products.</span></span> <span data-ttu-id="7a029-125">Nella pagina **Gerarchia di prodotti al dettaglio**, nel Riquadro azioni, selezionare **Categoria**, quindi selezionare **Aggiorna prodotti** per aprire la finestra di dialogo **Aggiorna prodotti**.</span><span class="sxs-lookup"><span data-stu-id="7a029-125">On the **Retail product hierarchy** page, on the Action Pane, select **Category**, and then select **Update products** to open the **Update products** dialog box.</span></span>

![Finestra di dialogo Aggiorna prodotti](media/NewUpdateProductsEnhancedView.PNG)

