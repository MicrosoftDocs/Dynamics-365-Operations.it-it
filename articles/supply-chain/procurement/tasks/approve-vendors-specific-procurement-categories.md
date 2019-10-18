---
title: Approvare i fornitori per categorie specifiche di approvvigionamento
description: In questo argomento viene descritto come approvare i fornitori per categorie di approvvigionamento specifiche in Dynamics 365 Supply Chain Management.
author: mkirknel
manager: AnnBe
ms.date: 07/30/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendTable, DirPartyEcoResCategory, EcoResCategorySingleLookup, ProcCategoryHierarchyManagement
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e47124e22dd6c0e756bf42429327254f966b48a2
ms.sourcegitcommit: f87de0f949b5d60993b19e0f61297f02d42b5bef
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/24/2019
ms.locfileid: "2018091"
---
# <a name="approve-vendors-for-specific-procurement-categories"></a><span data-ttu-id="14c4d-103">Approvare i fornitori per categorie specifiche di approvvigionamento</span><span class="sxs-lookup"><span data-stu-id="14c4d-103">Approve vendors for specific procurement categories</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="14c4d-104">In questo argomento viene descritto come approvare i fornitori per categorie di approvvigionamento specifiche in Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="14c4d-104">This topic explains how to approve vendors for specific procurement categories in Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="14c4d-105">Quando una richiesta di acquisto viene creata, ci può essere un requisito di selezionare un fornitore approvato o preferito, in base all'impostazione dei criteri di acquisto.</span><span class="sxs-lookup"><span data-stu-id="14c4d-105">When a purchase requisition is created, there may be a requirement to select an approved or preferred vendor, depending on how the purchasing policies are set up.</span></span> <span data-ttu-id="14c4d-106">Questa procedura vi mostra come specificare che un fornitore è approvato o preferito per una categoria specifica di approvvigionamento.</span><span class="sxs-lookup"><span data-stu-id="14c4d-106">This procedure shows you how to specify that a vendor is approved or preferred for a specific procurement category.</span></span> <span data-ttu-id="14c4d-107">Questa attività in genere viene svolta da un responsabile degli approvvigionamenti.</span><span class="sxs-lookup"><span data-stu-id="14c4d-107">This task would usually be carried out by a procurement professional.</span></span> <span data-ttu-id="14c4d-108">È possibile utilizzare questa procedura nella società di dati dimostrativi USMF.</span><span class="sxs-lookup"><span data-stu-id="14c4d-108">You can use this procedure in demo data company USMF.</span></span>

1. <span data-ttu-id="14c4d-109">Nel pannello di navigazione, andare a **Moduli > Approvvigionamento > Fornitori > Tutti i fornitori**.</span><span class="sxs-lookup"><span data-stu-id="14c4d-109">In the navigation pane, go to **Modules > Procurement and sourcing > Vendors > All vendors**.</span></span>
2. <span data-ttu-id="14c4d-110">Selezionare il fornire da impostare come approvato o preferito per una categoria.</span><span class="sxs-lookup"><span data-stu-id="14c4d-110">Select the vendor that you want to set as an approved or preferred vendor for a category.</span></span>
3. <span data-ttu-id="14c4d-111">Nel riquadro azioni fare clic su **Generale**.</span><span class="sxs-lookup"><span data-stu-id="14c4d-111">On the Action Pane, select **General**.</span></span>
4. <span data-ttu-id="14c4d-112">Selezionare **Categorie**.</span><span class="sxs-lookup"><span data-stu-id="14c4d-112">Select **Categories**.</span></span>
5. <span data-ttu-id="14c4d-113">Selezionare **Aggiungi categoria**.</span><span class="sxs-lookup"><span data-stu-id="14c4d-113">Select **Add category**.</span></span>
6. <span data-ttu-id="14c4d-114">Nel campo **Categoria**, selezionare **OFFICE AND DESK ACCESSORIES (OFFICE AND DESK ACCESSORIES)**.</span><span class="sxs-lookup"><span data-stu-id="14c4d-114">In the **Category** field, select **OFFICE AND DESK ACCESSORIES (OFFICE AND DESK ACCESSORIES)**.</span></span>
7. <span data-ttu-id="14c4d-115">Selezionare **Preferito** nel campo **Stato categoria fornitore**.</span><span class="sxs-lookup"><span data-stu-id="14c4d-115">In the **Vendor category status** field, select **Preferred**.</span></span> <span data-ttu-id="14c4d-116">È possibile specificare più di un fornitore preferito per una categoria.</span><span class="sxs-lookup"><span data-stu-id="14c4d-116">It’s possible to specify more than one preferred vendor for a category.</span></span>  
8. <span data-ttu-id="14c4d-117">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="14c4d-117">Select **Save**.</span></span>
9. <span data-ttu-id="14c4d-118">Nel pannello di navigazione, andare a **Moduli > Approvvigionamento > Categorie di approvvigionamento**.</span><span class="sxs-lookup"><span data-stu-id="14c4d-118">In the navigation pane, go to **Modules > Procurement and sourcing > Procurement categories**.</span></span>
10. <span data-ttu-id="14c4d-119">Nella struttura selezionare **CORP PROCUREMENT CATEGORIES\OFFICE AND DESK ACCESSORIES**.</span><span class="sxs-lookup"><span data-stu-id="14c4d-119">In the tree, select **CORP PROCUREMENT CATEGORIES\OFFICE AND DESK ACCESSORIES**.</span></span>
11. <span data-ttu-id="14c4d-120">Espandere la sezione **Fornitori**.</span><span class="sxs-lookup"><span data-stu-id="14c4d-120">Expand the **Vendors** section.</span></span> <span data-ttu-id="14c4d-121">Controllare se il fornitore selezionato compare come fornitore preferito per la categoria degli accessori per ufficio.</span><span class="sxs-lookup"><span data-stu-id="14c4d-121">Check if the vendor that you selected appears as a preferred vendor for the Office and desk accessories category.</span></span> <span data-ttu-id="14c4d-122">Se state eseguendo questa procedura come guida attività, potrebbe essere necessario selezionare il pulsante **Sblocca** per scorrere verso il basso l'elenco dei fornitori.</span><span class="sxs-lookup"><span data-stu-id="14c4d-122">If you’re running this procedure as a task guide, you may have to select the **Unlock** button to be able to scroll down to the list of vendors.</span></span>  <span data-ttu-id="14c4d-123">È inoltre possibile aggiungere i fornitori preferiti ed approvati a questa pagina.</span><span class="sxs-lookup"><span data-stu-id="14c4d-123">It’s also possible to add preferred and approved vendors on this page.</span></span>  
12. <span data-ttu-id="14c4d-124">Nella struttura, espandere **OFFICE AND DESK ACCESSORIES** e selezionare **Scissors**.</span><span class="sxs-lookup"><span data-stu-id="14c4d-124">In the tree, expand **OFFICE AND DESK ACCESSORIES** and select **Scissors**.</span></span>
13. <span data-ttu-id="14c4d-125">Selezionare **No** nel campo **Eredita fornitori dalla categoria padre**.</span><span class="sxs-lookup"><span data-stu-id="14c4d-125">Select **No** in the **Inherit vendors from parent category:** field.</span></span>
14. <span data-ttu-id="14c4d-126">Selezionare **Sì** nel campo **Eredita fornitori dalla categoria padre**.</span><span class="sxs-lookup"><span data-stu-id="14c4d-126">Select **Yes** in the **Inherit vendors from parent category:** field.</span></span>

