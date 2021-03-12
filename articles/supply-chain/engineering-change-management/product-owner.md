---
title: Proprietari del prodotto
description: Vengono fornite le informazioni sui proprietari di prodotto. Un proprietario di prodotto è un gruppo di utenti responsabili di prodotti specifici. Solo i membri del gruppo possono rilasciare questi prodotti. Il proprietario di prodotto può essere utilizzato anche nel flusso di lavoro di approvazione.
author: t-benebo
manager: tfehr
ms.date: 09/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EngChgProductOwner
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-09-28
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: 90f5596f9b5fc45e78cc49a3309c45864e07e70b
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4967335"
---
# <a name="product-owners"></a><span data-ttu-id="03491-106">Proprietari del prodotto</span><span class="sxs-lookup"><span data-stu-id="03491-106">Product owners</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="03491-107">Il proprietario di prodotto è un gruppo di utenti responsabili di prodotti specifici.</span><span class="sxs-lookup"><span data-stu-id="03491-107">The product owner is a group of users who are responsible for specific products.</span></span> <span data-ttu-id="03491-108">Quando un gruppo di proprietari di prodotto viene assegnato a un prodotto, solo i membri di quel gruppo possono rilasciare il prodotto.</span><span class="sxs-lookup"><span data-stu-id="03491-108">When a product owner group is assigned to a product, only the members of that group can release the product.</span></span> <span data-ttu-id="03491-109">Il proprietario di prodotto può essere utilizzato nel flusso di lavoro di approvazione nella gestione delle modifiche di progettazione.</span><span class="sxs-lookup"><span data-stu-id="03491-109">The product owner can also be used in the approval workflow in engineering change management.</span></span>

<span data-ttu-id="03491-110">I proprietari di prodotto sono impostazioni globali.</span><span class="sxs-lookup"><span data-stu-id="03491-110">Product owners are global settings.</span></span> <span data-ttu-id="03491-111">Pertanto, sono disponibili per tutte le persone giuridiche.</span><span class="sxs-lookup"><span data-stu-id="03491-111">Therefore, they are available to all legal entities.</span></span>

## <a name="create-a-product-owner-group"></a><span data-ttu-id="03491-112">Creare un gruppo di proprietari di prodotto</span><span class="sxs-lookup"><span data-stu-id="03491-112">Create a product owner group</span></span>

<span data-ttu-id="03491-113">Per creare un gruppo di proprietari di prodotto e aggiungervi membri, seguire questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="03491-113">To create a product owner group and add members to it, follow these steps.</span></span>

1. <span data-ttu-id="03491-114">Andare a **Gestione modifiche di progettazione \> Impostazione \> Proprietari di prodotti**.</span><span class="sxs-lookup"><span data-stu-id="03491-114">Go to **Engineering change management \> Setup \> Product owners**.</span></span>
2. <span data-ttu-id="03491-115">Nel Riquadro azioni selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="03491-115">On the Action Pane, select **New**.</span></span>
3. <span data-ttu-id="03491-116">Nel campo **Proprietario di prodotto** immettere un nome per il gruppo.</span><span class="sxs-lookup"><span data-stu-id="03491-116">In the **Product owner** field, enter a name for the group.</span></span>
4. <span data-ttu-id="03491-117">Nel campo **Nome** immettere una descrizione del gruppo.</span><span class="sxs-lookup"><span data-stu-id="03491-117">In the **Name** field, enter a description of the group.</span></span>
5. <span data-ttu-id="03491-118">Nella scheda dettaglio **Membri** aggiungere i lavoratori che devono essere membri del gruppo.</span><span class="sxs-lookup"><span data-stu-id="03491-118">On the **Members** FastTab, add the workers who should be members of the group.</span></span>

## <a name="assign-a-product-owner-to-a-product"></a><span data-ttu-id="03491-119">Assegnare un proprietario di prodotto a un prodotto</span><span class="sxs-lookup"><span data-stu-id="03491-119">Assign a product owner to a product</span></span>

<span data-ttu-id="03491-120">Per assegnare un proprietario di prodotto a un prodotto, attenersi alla procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="03491-120">To assign a product owner to a product, follow these steps.</span></span>

1. <span data-ttu-id="03491-121">Aprire la pagina **Dettagli prodotto** per il prodotto o la rappresentazione generale prodotto in questione.</span><span class="sxs-lookup"><span data-stu-id="03491-121">Open the **Product details** page for the relevant product or product master.</span></span>
1. <span data-ttu-id="03491-122">Nella Scheda dettaglio **Generale** impostare il campo **Proprietario del prodotto** sul nome del gruppo di proprietari di prodotto pertinente.</span><span class="sxs-lookup"><span data-stu-id="03491-122">On the **General** FastTab, set the **Product owner** field to the name of the relevant product owner group.</span></span>

<span data-ttu-id="03491-123">Mentre un proprietario di prodotto è assegnato a un prodotto, solo i membri del gruppo del proprietario di prodotto possono modificare l'impostazione **Proprietario del prodotto**.</span><span class="sxs-lookup"><span data-stu-id="03491-123">While a product owner is assigned to a product, only the members of the product owner group can edit the **Product owner** setting.</span></span>

<span data-ttu-id="03491-124">Il proprietario del prodotto è visibile anche nella pagina **Prodotti rilasciati**.</span><span class="sxs-lookup"><span data-stu-id="03491-124">The product owner is also visible on the **Released products** page.</span></span>

## <a name="product-owners-and-product-releases"></a><span data-ttu-id="03491-125">Proprietari di prodotto e versioni del prodotto</span><span class="sxs-lookup"><span data-stu-id="03491-125">Product owners and product releases</span></span>

<span data-ttu-id="03491-126">Solo gli utenti del gruppo di proprietari di un prodotto possono rilasciare quel prodotto.</span><span class="sxs-lookup"><span data-stu-id="03491-126">Only users from a product's product owner group can release that product.</span></span> <span data-ttu-id="03491-127">Tuttavia, esiste un'eccezione quando il prodotto è un articolo figlio e il suo elemento padre viene rilasciato dal proprietario dell'elemento padre.</span><span class="sxs-lookup"><span data-stu-id="03491-127">However, there is an exception when the product is a child item, and its parent is released by the parent's owner.</span></span> <span data-ttu-id="03491-128">In altre parole, se il prodotto fa parte della DBA di un altro prodotto, il sistema non controlla il proprietario del prodotto di ogni articolo nella DBA.</span><span class="sxs-lookup"><span data-stu-id="03491-128">In other words, if the product is part of the BOM of another product, the system doesn't check the product owner of each item in the BOM.</span></span> <span data-ttu-id="03491-129">Controlla solo il proprietario del prodotto dell'articolo padre.</span><span class="sxs-lookup"><span data-stu-id="03491-129">It checks only the product owner of the parent item.</span></span>

<span data-ttu-id="03491-130">Ad esempio, il prodotto X è assegnato al gruppo di proprietari di prodotto *Armadi di design*.</span><span class="sxs-lookup"><span data-stu-id="03491-130">For example, product X is assigned to the *Design cabinets* product owner group.</span></span> <span data-ttu-id="03491-131">Il prodotto X fa anche parte della distinta base del prodotto Y, che è assegnato a gruppo di proprietari del prodotto *Altoparlanti di design*.</span><span class="sxs-lookup"><span data-stu-id="03491-131">Product X is also part of the BOM of product Y, which is assigned to the *Design Speakers* product owner group.</span></span> <span data-ttu-id="03491-132">Se un utente del gruppo di proprietari del prodotto *Altoparlanti di design* rilascia il prodotto Y e la relativa distinta base, il prodotto X verrà rilasciato insieme al prodotto Y.</span><span class="sxs-lookup"><span data-stu-id="03491-132">If a user from the *Design Speakers* product owner group releases product Y and its BOM, product X will be released together with product Y.</span></span>

## <a name="product-owners-and-approvals"></a><span data-ttu-id="03491-133">Proprietari e approvazioni dei prodotti</span><span class="sxs-lookup"><span data-stu-id="03491-133">Product owners and approvals</span></span>

<span data-ttu-id="03491-134">Poiché i proprietari dei prodotti sanno se modifiche di progettazione specifiche andranno a vantaggio dei loro prodotti, spesso ha senso includerle come parte del processo di approvazione nella gestione delle modifiche di progettazione.</span><span class="sxs-lookup"><span data-stu-id="03491-134">Because product owners know whether specific engineering changes will benefit their products, it often makes sense to include them as part of the approval process in engineering change management.</span></span> <span data-ttu-id="03491-135">È possibile implementare questo approccio impostando i proprietari di prodotto come fornitori partecipanti nei flussi di lavoro utilizzati per la gestione delle modifiche di progettazione.</span><span class="sxs-lookup"><span data-stu-id="03491-135">You can implement this approach by setting up the product owners as participant providers in the workflows that are used for engineering change management.</span></span> <span data-ttu-id="03491-136">Il sistema assegnerà quindi le attività di approvazione nei flussi di lavoro, in base ai prodotti presenti nelle richieste di modifica di progettazione e negli ordini di modifica di progettazione.</span><span class="sxs-lookup"><span data-stu-id="03491-136">The system will then assign approval tasks in the workflows, based on the products that are in engineering change requests and engineering change orders.</span></span> <span data-ttu-id="03491-137">Per ulteriori informazioni, vedere [Gestire le modifiche ai prodotti di progettazione](engineering-change-management.md).</span><span class="sxs-lookup"><span data-stu-id="03491-137">For more information, see [Manage changes to engineering products](engineering-change-management.md).</span></span>
