---
title: Cespiti multilivello
description: In questo argomento viene descritto come creare ed eliminare i cespiti multilivello.
author: josaw1
manager: tfehr
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a69fd8b7d81700a62ae96d679372b1d6c8a70bbf
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5253208"
---
# <a name="multi-level-assets"></a><span data-ttu-id="f267f-103">Cespiti multilivello</span><span class="sxs-lookup"><span data-stu-id="f267f-103">Multi-level assets</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="f267f-104">In questo argomento viene descritto come creare ed eliminare i cespiti multilivello.</span><span class="sxs-lookup"><span data-stu-id="f267f-104">This topic explains how to create and delete multi-level assets.</span></span> <span data-ttu-id="f267f-105">È possibile creare i cespiti e cespiti secondari correlati in una struttura gerarchica.</span><span class="sxs-lookup"><span data-stu-id="f267f-105">You can create assets and related sub-assets in a hierarchical tree structure.</span></span> <span data-ttu-id="f267f-106">In questo modo, è possibile visualizzare le relazioni e le dipendenze tra i cespiti.</span><span class="sxs-lookup"><span data-stu-id="f267f-106">In this way, you can show relations and dependencies among assets.</span></span> <span data-ttu-id="f267f-107">I processi di manutenzione possono essere correlati a tutti i livelli della struttura.</span><span class="sxs-lookup"><span data-stu-id="f267f-107">Maintenance jobs can be related to all levels of the tree structure.</span></span> <span data-ttu-id="f267f-108">Possono inoltre essere create statistiche per un singolo livello o come somma di tutti i livelli dei cespiti secondari.</span><span class="sxs-lookup"><span data-stu-id="f267f-108">Statistics can also be created for an individual level or as a sum of all sub-asset levels.</span></span>

<span data-ttu-id="f267f-109">Nella pagina elenco **Tutti i cespiti** (**Gestione cespiti** \> **Comune** \> **Cespiti** \> **Tutti i cespiti**), la colonna **Cespite** elenca i cespiti nell'ordine gerarchico.</span><span class="sxs-lookup"><span data-stu-id="f267f-109">On the **All Assets** list page (**Asset management** \> **Common** \> **Assets** \> **All assets**), the **Asset** column lists assets in hierarchical order.</span></span> <span data-ttu-id="f267f-110">Nella colonna **Padre** viene visualizzato il padre correlato.</span><span class="sxs-lookup"><span data-stu-id="f267f-110">The **Parent** column shows the related parent.</span></span> <span data-ttu-id="f267f-111">Inoltre, se i cespiti e i cespiti secondari sono già stati creati, la sezione **Struttura cespiti** nel riquadro **Informazioni correlate** mostra i cespiti in una struttura.</span><span class="sxs-lookup"><span data-stu-id="f267f-111">Additionally, if assets and sub-assets have already been created, the **Asset tree** section in the **Related information** pane shows the assets in a tree structure.</span></span>

<span data-ttu-id="f267f-112">Per informazioni sulla modalità di creazione dei cespiti, vedere [Creare un cespite](../objects/create-an-object.md).</span><span class="sxs-lookup"><span data-stu-id="f267f-112">For information about how to create an asset, see [Create an asset](../objects/create-an-object.md).</span></span> <span data-ttu-id="f267f-113">Per creare un cespite secondario, selezionare il cespite padre nel campo **Padre** della scheda dettaglio **Generale**.</span><span class="sxs-lookup"><span data-stu-id="f267f-113">To create a sub-asset, select the parent asset in the **Parent** field on the **General** FastTab.</span></span>

## <a name="copy-an-asset-or-asset-structure"></a><span data-ttu-id="f267f-114">Copiare un cespite o una struttura di cespiti</span><span class="sxs-lookup"><span data-stu-id="f267f-114">Copy an asset or asset structure</span></span>

<span data-ttu-id="f267f-115">Se la società ha più strutture di cespiti simili, è possibile utilizzare la funzione di copia in Gestione cespiti per crearli rapidamente.</span><span class="sxs-lookup"><span data-stu-id="f267f-115">If your company has several similar asset structures, you can use the Copy function in Asset Management to quickly create them.</span></span>

1. <span data-ttu-id="f267f-116">Selezionare **Gestione cespiti** \> **Comune** \> **Cespiti** \> **Tutti i cespiti**.</span><span class="sxs-lookup"><span data-stu-id="f267f-116">Select **Asset management** \> **Common** \> **Assets** \> **All assets**.</span></span>
2. <span data-ttu-id="f267f-117">Nella pagina elenco **Tutti i cespiti**, selezionare il cespite da copiare.</span><span class="sxs-lookup"><span data-stu-id="f267f-117">On the **All assets** list page, select the asset to copy.</span></span> <span data-ttu-id="f267f-118">Ad esempio, per copiare l'intera struttura di cespiti, inclusi i cespiti secondari, selezionare un cespite padre.</span><span class="sxs-lookup"><span data-stu-id="f267f-118">For example, if you want to copy the whole asset structure, including sub-assets, select a parent asset.</span></span>
3. <span data-ttu-id="f267f-119">Selezionare **Copia cespite**.</span><span class="sxs-lookup"><span data-stu-id="f267f-119">Select **Copy asset**.</span></span> <span data-ttu-id="f267f-120">Nella sezione **Copia da**, il campo **Cespite** è impostato sul cespite selezionato nella pagina elenco.</span><span class="sxs-lookup"><span data-stu-id="f267f-120">In the **Copy from** section, the **Asset** field is set to the asset that you selected on the list page.</span></span>
4. <span data-ttu-id="f267f-121">Nella sezione **Copia in**, nel campo **Cespite**, immettere il nome del nuovo cespite.</span><span class="sxs-lookup"><span data-stu-id="f267f-121">In the **Copy to** section, in the **Asset** field, enter the name of the new asset.</span></span>
5. <span data-ttu-id="f267f-122">Se il cespite che si sta creando deve fare parte di una struttura di cespiti esistente, nella sezione **Cespite padre**, nel campo **Cespite**, selezionare un ID padre.</span><span class="sxs-lookup"><span data-stu-id="f267f-122">If the asset that you're creating should be part of an existing asset structure, in the **Parent asset** section, in the **Asset** field, select a parent ID.</span></span>
6. <span data-ttu-id="f267f-123">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="f267f-123">Select **OK**.</span></span> <span data-ttu-id="f267f-124">La nuova struttura di cespiti viene visualizzata nella pagina elenco **Tutti i cespiti**.</span><span class="sxs-lookup"><span data-stu-id="f267f-124">The new asset structure is shown on the **All assets** list page.</span></span> <span data-ttu-id="f267f-125">Tutti gli attributi cespite, piani di manutenzione e cicli di manutenzione relativi al cespite copiato verranno trasferiti al nuovo cespite o struttura del cespite.</span><span class="sxs-lookup"><span data-stu-id="f267f-125">All asset attributes, maintenance plans, and maintenance rounds that are related to the asset that you copied are transferred to the new asset or asset structure.</span></span>

<span data-ttu-id="f267f-126">Quando si copia una struttura di cespiti, i cespiti secondari nella nuova struttura hanno lo stesso nome dei cespiti secondari copiati.</span><span class="sxs-lookup"><span data-stu-id="f267f-126">When you copy an asset structure, the sub-assets in the new structure have the same name as the sub-assets that you copied.</span></span> <span data-ttu-id="f267f-127">Al termine della procedura di copia, è possibile cambiare facilmente il nome e altre impostazioni di un cespite.</span><span class="sxs-lookup"><span data-stu-id="f267f-127">After the copy procedure is completed, you can easily change the name and other settings for an asset.</span></span> <span data-ttu-id="f267f-128">Selezionare il cespite nella pagina elenco **Tutti i cespiti** e quindi fare clic sul pulsante **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="f267f-128">Select the asset on the **All assets** list page, and then select the **Edit** button.</span></span>

> [!NOTE]
> <span data-ttu-id="f267f-129">Quando si copia un cespite o struttura di cespiti, lo stato del ciclo di vita di nuovi cespiti viene reimpostato su qualsiasi stato è definito come stato iniziale del ciclo di vita dei cespiti.</span><span class="sxs-lookup"><span data-stu-id="f267f-129">When you copy an asset or asset structure, the lifecycle state of the new assets is reset to whatever state you defined as the initial lifecycle state for assets.</span></span> <span data-ttu-id="f267f-130">L'unità funzionale viene reimpostata sull'unità funzionale predefinita.</span><span class="sxs-lookup"><span data-stu-id="f267f-130">The functional location is reset to the default functional location.</span></span>

## <a name="delete-an-asset-or-asset-structure"></a><span data-ttu-id="f267f-131">Eliminare un cespite o una struttura di cespiti</span><span class="sxs-lookup"><span data-stu-id="f267f-131">Delete an asset or asset structure</span></span>

<span data-ttu-id="f267f-132">Se un cespite ha cespiti secondari correlati, è possibile eliminarlo solo se non sono presenti richieste di intervento di manutenzione, processi di ordine di lavoro, registrazioni di problemi, o valutazioni delle condizioni registrate in uno dei cespiti.</span><span class="sxs-lookup"><span data-stu-id="f267f-132">If an asset has related sub-assets, you can delete it only if no maintenance requests, work order jobs, fault registrations, or condition assessments are registered on any of the assets.</span></span>

1. <span data-ttu-id="f267f-133">Nella pagina elenco **Tutti i cespiti**, selezionare il cespite da eliminare.</span><span class="sxs-lookup"><span data-stu-id="f267f-133">On the **All assets** list page, select the asset to delete.</span></span>
2. <span data-ttu-id="f267f-134">Selezionare **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="f267f-134">Select **Delete**.</span></span>

> [!NOTE]
> <span data-ttu-id="f267f-135">Se non è possibile eliminare un cespite utilizzando questa procedura, un altro metodo per gestire l'eliminazione è di impostare uno stato del ciclo di vita del cespite a questo scopo.</span><span class="sxs-lookup"><span data-stu-id="f267f-135">If you can't delete an asset by using this procedure, another way to handle deletion is to set up an asset lifecycle state for this purpose.</span></span> <span data-ttu-id="f267f-136">Ad esempio, è possibile impostare uno stato del ciclo di vita su **Eliminato** o **Rottamato** nella pagina **Stati del ciclo di vita del cespite**.</span><span class="sxs-lookup"><span data-stu-id="f267f-136">For example, you can set up a **Scrapped** or **Deleted** lifecycle state on the **Asset lifecycle states** page.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]