---
title: Creare una gerarchia organizzativa
description: Per creare una gerarchia organizzativa, attenersi alla seguente procedura.
author: sericks007
manager: AnnBe
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: OMHierarchyManager, OMHierarchyPurposeAssociation, OMHierarchySelection, HierarchyDesigner
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: dde06f758be57fb646696c861218565476abcadc
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/18/2020
ms.locfileid: "3140561"
---
# <a name="create-an-organization-hierarchy"></a><span data-ttu-id="72207-103">Creare una gerarchia organizzativa</span><span class="sxs-lookup"><span data-stu-id="72207-103">Create an organization hierarchy</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="72207-104">Per creare una gerarchia organizzativa, attenersi alla seguente procedura.</span><span class="sxs-lookup"><span data-stu-id="72207-104">Use the following procedure to create an organizational hierarchy.</span></span> <span data-ttu-id="72207-105">È possibile utilizzare le gerarchie organizzative per la visualizzazione e il reporting dell'attività aziendale da varie prospettive.</span><span class="sxs-lookup"><span data-stu-id="72207-105">You can use organizational hierarchies to view and report on your business from various perspectives.</span></span> <span data-ttu-id="72207-106">È possibile impostare, ad esempio, una gerarchia per una dichiarazione fiscale, legale o statutaria.</span><span class="sxs-lookup"><span data-stu-id="72207-106">For example, you can set up one hierarchy for tax, legal, or statutory reporting.</span></span> <span data-ttu-id="72207-107">È quindi possibile impostare un'altra gerarchia per il reporting di informazioni finanziarie non obbligatorio per legge, ma utilizzato per la creazione di report interni.</span><span class="sxs-lookup"><span data-stu-id="72207-107">You can then set up another hierarchy to report financial information that is not legally required, but that is used for internal reporting.</span></span> 

<span data-ttu-id="72207-108">Prima di creare una gerarchia organizzativa, è necessario creare organizzazioni.</span><span class="sxs-lookup"><span data-stu-id="72207-108">Before you create an organizational hierarchy, you must create organizations.</span></span> <span data-ttu-id="72207-109">Per ulteriori informazioni, vedere l'attività "Creare una nuova persona giuridica" o "Creare un'unità operativa".</span><span class="sxs-lookup"><span data-stu-id="72207-109">For more information, see the "Create a legal entity" or "Create an operating unit" tasks.</span></span> <span data-ttu-id="72207-110">È inoltre possibile creare reparti e team,.</span><span class="sxs-lookup"><span data-stu-id="72207-110">You can also create departments and teams.</span></span> 

<span data-ttu-id="72207-111">La società di dati dimostrativi utilizzata per creare questa procedura è USMF.</span><span class="sxs-lookup"><span data-stu-id="72207-111">The demo data company used to create this procedure is USMF.</span></span>

## <a name="create-a-hierarchy"></a><span data-ttu-id="72207-112">Crea una gerarchia</span><span class="sxs-lookup"><span data-stu-id="72207-112">Create a hierarchy</span></span>
1. <span data-ttu-id="72207-113">Andare a **Pannello di navigazione > Moduli > Amministrazione organizzazione > Organizzazioni > Gerarchie organizzative**.</span><span class="sxs-lookup"><span data-stu-id="72207-113">Go to **Navigation pane > Modules > Organization administration > Organizations > Organization hierarchies**.</span></span>
2. <span data-ttu-id="72207-114">Fare clic su **Nuova** nel **riquadro azioni**.</span><span class="sxs-lookup"><span data-stu-id="72207-114">On the **Action pane**, click **New**.</span></span>
3. <span data-ttu-id="72207-115">Digitare un valore nel campo **Nome**.</span><span class="sxs-lookup"><span data-stu-id="72207-115">In the **Name** field, type a value.</span></span>
4. <span data-ttu-id="72207-116">Nella sezione **Scopo**, fare clic su **Assegna scopo**.</span><span class="sxs-lookup"><span data-stu-id="72207-116">In the **Purpose** section, click **Assign purpose**.</span></span>
5. <span data-ttu-id="72207-117">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="72207-117">In the list, find and select the desired record.</span></span> <span data-ttu-id="72207-118">Selezionare uno scopo da assegnare alla propria gerarchia organizzativa.</span><span class="sxs-lookup"><span data-stu-id="72207-118">Select a purpose to assign to your organization hierarchy.</span></span>  
6. <span data-ttu-id="72207-119">Nella sezione sectiom **Gerarchie assegnate**, fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="72207-119">In the **Assigned hierarchies** sectiom, click **Add**.</span></span>
7. <span data-ttu-id="72207-120">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="72207-120">In the list, mark the selected row.</span></span> <span data-ttu-id="72207-121">Individuare la gerarchia appena creata.</span><span class="sxs-lookup"><span data-stu-id="72207-121">Find the hierarchy you just created.</span></span>  
8. <span data-ttu-id="72207-122">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="72207-122">Click **OK**.</span></span>

## <a name="add-organizations-to-the-hierarchy"></a><span data-ttu-id="72207-123">Aggiungere organizzazioni alla gerarchia</span><span class="sxs-lookup"><span data-stu-id="72207-123">Add organizations to the hierarchy</span></span>
1. <span data-ttu-id="72207-124">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="72207-124">In the list, find and select the desired record.</span></span> <span data-ttu-id="72207-125">Selezionare la propria gerarchia.</span><span class="sxs-lookup"><span data-stu-id="72207-125">Select your hierarchy.</span></span>  
2. <span data-ttu-id="72207-126">Nella sezione **Gerarchie assegnate**, fare clic su **Visualizza gerarchia**.</span><span class="sxs-lookup"><span data-stu-id="72207-126">In the **Assigned hierarchies** section, click **View hierarchy**.</span></span>
    - <span data-ttu-id="72207-127">Aggiungere organizzazioni in base alle necessità.</span><span class="sxs-lookup"><span data-stu-id="72207-127">Add organizations, as necessary.</span></span>  
    - <span data-ttu-id="72207-128">Per aggiungere un'organizzazione, fare clic su **Modifica**, quindi su **Inserisci**.</span><span class="sxs-lookup"><span data-stu-id="72207-128">To add an organization, click **Edit** and then **Insert** to add the organization.</span></span> <span data-ttu-id="72207-129">Dopo avere apportato le modifiche, è possibile **salvare** una bozza e/o **pubblicare** le modifiche.</span><span class="sxs-lookup"><span data-stu-id="72207-129">When you are done making changes you can **Save** a draft and/or **Publish** the changes.</span></span>  

