---
title: Impostare una gerarchia di categorie di approvvigionamento
description: Questa procedura illustra come creare nuovi nodi in una gerarchia di categorie di approvvigionamento e come configurare una categoria di approvvigionamento per essere utilizzata in un processo di approvvigionamento.
author: mkirknel
manager: AnnBe
ms.date: 06/21/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c7010fb702d16dc276bfee397066ccf95bf5d25a
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/18/2020
ms.locfileid: "3147275"
---
# <a name="set-up-a-procurement-category-hierarchy"></a><span data-ttu-id="4e0fd-103">Impostare una gerarchia di categorie di approvvigionamento</span><span class="sxs-lookup"><span data-stu-id="4e0fd-103">Set up a procurement category hierarchy</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="4e0fd-104">Questa procedura illustra come creare nuovi nodi in una gerarchia di categorie di approvvigionamento e come configurare una categoria di approvvigionamento per essere utilizzata in un processo di approvvigionamento.</span><span class="sxs-lookup"><span data-stu-id="4e0fd-104">This procedure shows you how to create new nodes in a procurement category hierarchy and how to configure a procurement category to be used in a procurement process.</span></span> <span data-ttu-id="4e0fd-105">Queste attività verranno in genere svolte da un responsabile degli acquisti.</span><span class="sxs-lookup"><span data-stu-id="4e0fd-105">These tasks would typically be carried out by a Purchasing manager.</span></span> <span data-ttu-id="4e0fd-106">Prima di iniziare questa procedura, deve essere presente una gerarchia di categorie di tipo approvvigionamento.</span><span class="sxs-lookup"><span data-stu-id="4e0fd-106">Before you can start this procedure, there must be a category hierarchy of type Procurement.</span></span> <span data-ttu-id="4e0fd-107">Se si utilizza una società di dati dimostrativi, è possibile eseguire questa procedura nella società USMF.</span><span class="sxs-lookup"><span data-stu-id="4e0fd-107">If you're using a demo data company, you can run this procedure in the USMF company.</span></span>


## <a name="add-a-new-procurement-category"></a><span data-ttu-id="4e0fd-108">Aggiungere una categoria di approvvigionamento</span><span class="sxs-lookup"><span data-stu-id="4e0fd-108">Add a new procurement category</span></span>
1. <span data-ttu-id="4e0fd-109">Andare a **Pannello di navigazione >Moduli > Approvvigionamento > Spedizione > Categorie di approvvigionamento**.</span><span class="sxs-lookup"><span data-stu-id="4e0fd-109">Go to **Navigation pane > Modules > Procurement and sourcing > Consignment > Procurement categories**.</span></span>
2. <span data-ttu-id="4e0fd-110">Nel riquadro Azioni selezionare **Modifica gerarchia di categorie**.</span><span class="sxs-lookup"><span data-stu-id="4e0fd-110">On the action pane, select **Edit category hierarchy**.</span></span> <span data-ttu-id="4e0fd-111">La gerarchia di categorie di approvvigionamento corrente viene visualizzata nella parte sinistra della pagina.</span><span class="sxs-lookup"><span data-stu-id="4e0fd-111">The current procurement category hierarchy is displayed in the left side of the page.</span></span> <span data-ttu-id="4e0fd-112">Si sta per modificare la gerarchia.</span><span class="sxs-lookup"><span data-stu-id="4e0fd-112">You  are about to modify the hierarchy.</span></span>  
3. <span data-ttu-id="4e0fd-113">Nel riquadro Azioni selezionare **Nuovo nodo di categoria**.</span><span class="sxs-lookup"><span data-stu-id="4e0fd-113">On the action pane, select **New category node**.</span></span> <span data-ttu-id="4e0fd-114">Il sistema selezionare il nodo di primo livello per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="4e0fd-114">The system selects the top node by default.</span></span> <span data-ttu-id="4e0fd-115">Se si esegue la procedura come guida attività, è possibile fare clic sul pulsante Sblocca e selezionare un altro nodo padre per inserire il nuovo nodo.</span><span class="sxs-lookup"><span data-stu-id="4e0fd-115">If you are running this procedure as a task guide, you can click the Unlock button and select another parent node to insert your new node into.</span></span> <span data-ttu-id="4e0fd-116">Una volta eseguita l'operazione, bloccare ancora la guida attività e quindi fare clic sul nodo Nuova categoria.</span><span class="sxs-lookup"><span data-stu-id="4e0fd-116">Once that is done, lock the task guide again and then click New category node.</span></span>  
4. <span data-ttu-id="4e0fd-117">Digitare un valore nel campo **Nome**.</span><span class="sxs-lookup"><span data-stu-id="4e0fd-117">In the **Name** field, type a value.</span></span>
5. <span data-ttu-id="4e0fd-118">Digitare un valore nel campo **Descrizione**</span><span class="sxs-lookup"><span data-stu-id="4e0fd-118">In the **Description** field, type a value.</span></span>
6. <span data-ttu-id="4e0fd-119">Digitare un valore nel campo **Nome descrittivo**.</span><span class="sxs-lookup"><span data-stu-id="4e0fd-119">In the **Friendly name** field, type a value.</span></span> <span data-ttu-id="4e0fd-120">Il nome descrittivo è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="4e0fd-120">The friendly name is optional.</span></span> <span data-ttu-id="4e0fd-121">Verrà visualizzato le ricerche di categoria insieme al nome della categoria.</span><span class="sxs-lookup"><span data-stu-id="4e0fd-121">It will be displayed in category lookups together with the category name.</span></span>  
7. <span data-ttu-id="4e0fd-122">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="4e0fd-122">Select **Save**.</span></span>

## <a name="add-products-to-your-new-procurement-category"></a><span data-ttu-id="4e0fd-123">Aggiungere prodotti alla nuova categoria di approvvigionamento</span><span class="sxs-lookup"><span data-stu-id="4e0fd-123">Add products to your new procurement category</span></span>
1. <span data-ttu-id="4e0fd-124">Andare a **Approvvigionamento > Spedizione > Categorie di approvvigionamento**.</span><span class="sxs-lookup"><span data-stu-id="4e0fd-124">Go to **Procurement and sourcing > Consignment > Procurement categories**.</span></span> <span data-ttu-id="4e0fd-125">Selezionare il nodo aggiunto.</span><span class="sxs-lookup"><span data-stu-id="4e0fd-125">Select the node you just added.</span></span> <span data-ttu-id="4e0fd-126">Se si esegue la procedura come guida attività, potrebbe essere necessario sbloccare quest'ultima per selezionare il nodo.</span><span class="sxs-lookup"><span data-stu-id="4e0fd-126">If you're running this procedure as a task guide you might need to unlock the task guide to select the node.</span></span>  
2. <span data-ttu-id="4e0fd-127">Attivare/disattivare l'espansione della sezione **Prodotti**.</span><span class="sxs-lookup"><span data-stu-id="4e0fd-127">Toggle the expansion of the **Products** section.</span></span>
3. <span data-ttu-id="4e0fd-128">Fare clic su **Aggiungi** per associare i prodotti alla categoria di approvvigionamento.</span><span class="sxs-lookup"><span data-stu-id="4e0fd-128">Select **Add** to associate products with the procurement category.</span></span>
4. <span data-ttu-id="4e0fd-129">Selezionare i prodotti che si desidera aggiungere alla categoria di approvvigionamento.</span><span class="sxs-lookup"><span data-stu-id="4e0fd-129">Select the products you want to add to the procurement category.</span></span>
5. <span data-ttu-id="4e0fd-130">Selezionare la freccia per aggiungere i prodotti alla tabella **Selezionati**.</span><span class="sxs-lookup"><span data-stu-id="4e0fd-130">Select the arrow to add the products to the **Selected** table.</span></span>
6. <span data-ttu-id="4e0fd-131">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="4e0fd-131">Select **OK**.</span></span>
