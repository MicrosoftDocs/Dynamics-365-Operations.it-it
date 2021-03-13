---
title: Approvare i fornitori per categorie specifiche di approvvigionamento
description: In questo argomento viene descritto come approvare i fornitori per categorie di approvvigionamento specifiche in Dynamics 365 Supply Chain Management.
author: RichardLuan
manager: tfehr
ms.date: 07/30/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendTable, DirPartyEcoResCategory, EcoResCategorySingleLookup, ProcCategoryHierarchyManagement
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 159d918a4dd3b6502bc8ab411d0353545eb4fcba
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/16/2021
ms.locfileid: "5016351"
---
# <a name="approve-vendors-for-specific-procurement-categories"></a><span data-ttu-id="efbe7-103">Approvare i fornitori per categorie specifiche di approvvigionamento</span><span class="sxs-lookup"><span data-stu-id="efbe7-103">Approve vendors for specific procurement categories</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="efbe7-104">In questo argomento viene descritto come approvare i fornitori per categorie di approvvigionamento specifiche in Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="efbe7-104">This topic explains how to approve vendors for specific procurement categories in Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="efbe7-105">Quando una richiesta di acquisto viene creata, ci può essere un requisito di selezionare un fornitore approvato o preferito, in base all'impostazione dei criteri di acquisto.</span><span class="sxs-lookup"><span data-stu-id="efbe7-105">When a purchase requisition is created, there may be a requirement to select an approved or preferred vendor, depending on how the purchasing policies are set up.</span></span> <span data-ttu-id="efbe7-106">Questa procedura vi mostra come specificare che un fornitore è approvato o preferito per una categoria specifica di approvvigionamento.</span><span class="sxs-lookup"><span data-stu-id="efbe7-106">This procedure shows you how to specify that a vendor is approved or preferred for a specific procurement category.</span></span> <span data-ttu-id="efbe7-107">Questa attività in genere viene svolta da un responsabile degli approvvigionamenti.</span><span class="sxs-lookup"><span data-stu-id="efbe7-107">This task would usually be carried out by a procurement professional.</span></span> <span data-ttu-id="efbe7-108">È possibile utilizzare questa procedura nella società di dati dimostrativi USMF.</span><span class="sxs-lookup"><span data-stu-id="efbe7-108">You can use this procedure in demo data company USMF.</span></span>

1. <span data-ttu-id="efbe7-109">Nel pannello di navigazione, andare a **Moduli > Approvvigionamento > Fornitori > Tutti i fornitori**.</span><span class="sxs-lookup"><span data-stu-id="efbe7-109">In the navigation pane, go to **Modules > Procurement and sourcing > Vendors > All vendors**.</span></span>
2. <span data-ttu-id="efbe7-110">Selezionare il fornire da impostare come approvato o preferito per una categoria.</span><span class="sxs-lookup"><span data-stu-id="efbe7-110">Select the vendor that you want to set as an approved or preferred vendor for a category.</span></span>
3. <span data-ttu-id="efbe7-111">Nel riquadro azioni fare clic su **Generale**.</span><span class="sxs-lookup"><span data-stu-id="efbe7-111">On the Action Pane, select **General**.</span></span>
4. <span data-ttu-id="efbe7-112">Selezionare **Categorie**.</span><span class="sxs-lookup"><span data-stu-id="efbe7-112">Select **Categories**.</span></span>
5. <span data-ttu-id="efbe7-113">Selezionare **Aggiungi categoria**.</span><span class="sxs-lookup"><span data-stu-id="efbe7-113">Select **Add category**.</span></span>
6. <span data-ttu-id="efbe7-114">Nel campo **Categoria**, selezionare **OFFICE AND DESK ACCESSORIES (OFFICE AND DESK ACCESSORIES)**.</span><span class="sxs-lookup"><span data-stu-id="efbe7-114">In the **Category** field, select **OFFICE AND DESK ACCESSORIES (OFFICE AND DESK ACCESSORIES)**.</span></span>
7. <span data-ttu-id="efbe7-115">Selezionare **Preferito** nel campo **Stato categoria fornitore**.</span><span class="sxs-lookup"><span data-stu-id="efbe7-115">In the **Vendor category status** field, select **Preferred**.</span></span> <span data-ttu-id="efbe7-116">È possibile specificare più di un fornitore preferito per una categoria.</span><span class="sxs-lookup"><span data-stu-id="efbe7-116">It's possible to specify more than one preferred vendor for a category.</span></span>  
8. <span data-ttu-id="efbe7-117">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="efbe7-117">Select **Save**.</span></span>
9. <span data-ttu-id="efbe7-118">Nel pannello di navigazione, andare a **Moduli > Approvvigionamento > Categorie di approvvigionamento**.</span><span class="sxs-lookup"><span data-stu-id="efbe7-118">In the navigation pane, go to **Modules > Procurement and sourcing > Procurement categories**.</span></span>
10. <span data-ttu-id="efbe7-119">Nella struttura selezionare **CORP PROCUREMENT CATEGORIES\OFFICE AND DESK ACCESSORIES**.</span><span class="sxs-lookup"><span data-stu-id="efbe7-119">In the tree, select **CORP PROCUREMENT CATEGORIES\OFFICE AND DESK ACCESSORIES**.</span></span>
11. <span data-ttu-id="efbe7-120">Espandere la sezione **Fornitori**.</span><span class="sxs-lookup"><span data-stu-id="efbe7-120">Expand the **Vendors** section.</span></span> <span data-ttu-id="efbe7-121">Controllare se il fornitore selezionato compare come fornitore preferito per la categoria degli accessori per ufficio.</span><span class="sxs-lookup"><span data-stu-id="efbe7-121">Check if the vendor that you selected appears as a preferred vendor for the Office and desk accessories category.</span></span> <span data-ttu-id="efbe7-122">Se state eseguendo questa procedura come guida attività, potrebbe essere necessario selezionare il pulsante **Sblocca** per scorrere verso il basso l'elenco dei fornitori.</span><span class="sxs-lookup"><span data-stu-id="efbe7-122">If you're running this procedure as a task guide, you may have to select the **Unlock** button to be able to scroll down to the list of vendors.</span></span>  <span data-ttu-id="efbe7-123">È inoltre possibile aggiungere i fornitori preferiti ed approvati a questa pagina.</span><span class="sxs-lookup"><span data-stu-id="efbe7-123">It's also possible to add preferred and approved vendors on this page.</span></span>  
12. <span data-ttu-id="efbe7-124">Nella struttura, espandere **OFFICE AND DESK ACCESSORIES** e selezionare **Scissors**.</span><span class="sxs-lookup"><span data-stu-id="efbe7-124">In the tree, expand **OFFICE AND DESK ACCESSORIES** and select **Scissors**.</span></span>
13. <span data-ttu-id="efbe7-125">Selezionare **No** nel campo **Eredita fornitori dalla categoria padre**.</span><span class="sxs-lookup"><span data-stu-id="efbe7-125">Select **No** in the **Inherit vendors from parent category:** field.</span></span>
14. <span data-ttu-id="efbe7-126">Selezionare **Sì** nel campo **Eredita fornitori dalla categoria padre**.</span><span class="sxs-lookup"><span data-stu-id="efbe7-126">Select **Yes** in the **Inherit vendors from parent category:** field.</span></span>

