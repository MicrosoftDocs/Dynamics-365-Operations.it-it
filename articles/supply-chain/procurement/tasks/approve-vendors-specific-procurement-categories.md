--- 
title: Approvare i fornitori per categorie specifiche di approvvigionamento
description: "Quando una richiesta di acquisto viene creata, ci può essere un requisito di selezionare un fornitore approvato o preferito, in base all'impostazione dei criteri di acquisto."
author: mkirknel
manager: AnnBe
ms.date: 08/23/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 83945932d56abf6bf44476e5647f8ae7abdc3602
ms.contentlocale: it-it
ms.lasthandoff: 08/29/2017

---
# <a name="approve-vendors-for-specific-procurement-categories"></a><span data-ttu-id="982cc-103">Approvare i fornitori per categorie specifiche di approvvigionamento</span><span class="sxs-lookup"><span data-stu-id="982cc-103">Approve vendors for specific procurement categories</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="982cc-104">Quando una richiesta di acquisto viene creata, ci può essere un requisito di selezionare un fornitore approvato o preferito, in base all'impostazione dei criteri di acquisto.</span><span class="sxs-lookup"><span data-stu-id="982cc-104">When a purchase requisition is created, there may be a requirement to select an approved or preferred vendor, depending on how the purchasing policies are set up.</span></span> <span data-ttu-id="982cc-105">Questa procedura vi mostra come specificare che un fornitore è approvato o preferito per una categoria specifica di approvvigionamento.</span><span class="sxs-lookup"><span data-stu-id="982cc-105">This procedure shows you how to specify that a vendor is approved or preferred for a specific procurement category.</span></span> <span data-ttu-id="982cc-106">Questa attività in genere viene svolta da un responsabile degli approvvigionamenti.</span><span class="sxs-lookup"><span data-stu-id="982cc-106">This task would usually be carried out by a procurement professional.</span></span> <span data-ttu-id="982cc-107">È possibile utilizzare questa procedura nella società di dati dimostrativi USMF.</span><span class="sxs-lookup"><span data-stu-id="982cc-107">You can use this procedure in demo data company USMF.</span></span>

1. <span data-ttu-id="982cc-108">Andare ad Approvvigionamento > Fornitori > Tutti i fornitori.</span><span class="sxs-lookup"><span data-stu-id="982cc-108">Go to Procurement and sourcing > Vendors > All vendors.</span></span>
2. <span data-ttu-id="982cc-109">Selezionare il fornire da impostare come approvato o preferito per una categoria.</span><span class="sxs-lookup"><span data-stu-id="982cc-109">Select the vendor that you want to set as an approved or preferred vendor for a category.</span></span>
3. <span data-ttu-id="982cc-110">Nel riquadro azioni fare clic su Generale.</span><span class="sxs-lookup"><span data-stu-id="982cc-110">On the Action Pane, click General.</span></span>
4. <span data-ttu-id="982cc-111">Fare clic su Categorie.</span><span class="sxs-lookup"><span data-stu-id="982cc-111">Click Categories.</span></span>
5. <span data-ttu-id="982cc-112">Fare clic su Aggiungi categoria.</span><span class="sxs-lookup"><span data-stu-id="982cc-112">Click Add category.</span></span>
6. <span data-ttu-id="982cc-113">Nel campo Categoria, selezionare OFFICE AND DESK ACCESSORIES (OFFICE AND DESK ACCESSORIES).</span><span class="sxs-lookup"><span data-stu-id="982cc-113">In the Category field, select OFFICE AND DESK ACCESSORIES (OFFICE AND DESK ACCESSORIES).</span></span>
7. <span data-ttu-id="982cc-114">Selezionare 'Preferito' nel campo Stato categoria fornitore.</span><span class="sxs-lookup"><span data-stu-id="982cc-114">In the Vendor category status field, select 'Preferred'.</span></span>
    * <span data-ttu-id="982cc-115">È possibile specificare più di un fornitore preferito per una categoria.</span><span class="sxs-lookup"><span data-stu-id="982cc-115">It’s possible to specify more than one preferred vendor for a category.</span></span>  
8. <span data-ttu-id="982cc-116">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="982cc-116">Click Save.</span></span>
9. <span data-ttu-id="982cc-117">Passare a Approvvigionamento > Categorie di approvvigionamento.</span><span class="sxs-lookup"><span data-stu-id="982cc-117">Go to Procurement and sourcing > Procurement categories.</span></span>
10. <span data-ttu-id="982cc-118">Nella struttura selezionare 'CORP PROCUREMENT CATEGORIES\OFFICE AND DESK ACCESSORIES'.</span><span class="sxs-lookup"><span data-stu-id="982cc-118">In the tree, select 'CORP PROCUREMENT CATEGORIES\OFFICE AND DESK ACCESSORIES'.</span></span>
11. <span data-ttu-id="982cc-119">Espandere la sezione Fornitori.</span><span class="sxs-lookup"><span data-stu-id="982cc-119">Expand the Vendors section.</span></span>
    * <span data-ttu-id="982cc-120">Controllare se il fornitore selezionato compare come fornitore preferito per la categoria degli accessori per ufficio.</span><span class="sxs-lookup"><span data-stu-id="982cc-120">Check if the vendor that you selected  appears as a preferred vendor for the Office and desk accessories category.</span></span> <span data-ttu-id="982cc-121">Se state eseguendo questa procedura come guida attività, potrebbe essere neecssario fare clic sul pulsante Sblocca per scorrere verso il basso l'elenco dei fornitori.</span><span class="sxs-lookup"><span data-stu-id="982cc-121">If you’re running this procedure as a task guide, you may have to click the Unlock button to be able to scroll down to the list of vendors.</span></span>  <span data-ttu-id="982cc-122">È inoltre possibile aggiungere i fornitori preferiti ed approvati a questa pagina.</span><span class="sxs-lookup"><span data-stu-id="982cc-122">It’s also possible to add preferred and approved vendors on this page.</span></span>  
12. <span data-ttu-id="982cc-123">Nella struttura espandere 'OFFICE AND DESK ACCESSORIES'.</span><span class="sxs-lookup"><span data-stu-id="982cc-123">In the tree, expand 'OFFICE AND DESK ACCESSORIES'.</span></span>
13. <span data-ttu-id="982cc-124">Nella struttura, selezionare 'Scissors'.</span><span class="sxs-lookup"><span data-stu-id="982cc-124">In the tree, select 'Scissors'.</span></span>
14. <span data-ttu-id="982cc-125">Selezionare No nel campo Eredita fornitori dalla categoria padre.</span><span class="sxs-lookup"><span data-stu-id="982cc-125">Select No in the Inherit vendors from parent category: field.</span></span>
15. <span data-ttu-id="982cc-126">Selezionare Sì nel campo Eredita fornitori dalla categoria padre.</span><span class="sxs-lookup"><span data-stu-id="982cc-126">Select Yes in the Inherit vendors from parent category: field.</span></span>


