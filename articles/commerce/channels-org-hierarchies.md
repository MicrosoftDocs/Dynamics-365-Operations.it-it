---
title: Impostare gerarchie organizzative
description: In questo argomento viene descritto come impostare gerarchie organizzative in Microsoft Dynamics 365 Commerce.
author: samjarawan
manager: annbe
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 490d466c10cfe0640f8fbcf8fe2298536e499d9b
ms.sourcegitcommit: c88b54ba13a4dfe39b844ffaced4dc435560c47d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2021
ms.locfileid: "5477998"
---
# <a name="set-up-organization-hierarchies"></a><span data-ttu-id="8a344-103">Impostare gerarchie organizzative</span><span class="sxs-lookup"><span data-stu-id="8a344-103">Set up organization hierarchies</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="8a344-104">In questo argomento viene descritto come impostare gerarchie organizzative in Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="8a344-104">This topic describes how to set up organization hierarchies in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="8a344-105">Prima di creare canali, è necessario confermare che le gerarchie organizzative siano state impostate.</span><span class="sxs-lookup"><span data-stu-id="8a344-105">Before creating channels, you'll want to ensure you have set up your organization hierarchies.</span></span>

<span data-ttu-id="8a344-106">È possibile utilizzare gerarchie organizzative per la visualizzazione e il reporting dell'attività aziendale da varie prospettive.</span><span class="sxs-lookup"><span data-stu-id="8a344-106">You can use organization hierarchies to view and report on your business from various perspectives.</span></span> <span data-ttu-id="8a344-107">È possibile impostare, ad esempio, una gerarchia per una dichiarazione fiscale, legale o statutaria.</span><span class="sxs-lookup"><span data-stu-id="8a344-107">For example, you can set up one hierarchy for tax, legal, or statutory reporting.</span></span> <span data-ttu-id="8a344-108">È quindi possibile impostare un'altra gerarchia per il reporting di informazioni finanziarie non obbligatorio per legge, ma utilizzato per la creazione di report interni.</span><span class="sxs-lookup"><span data-stu-id="8a344-108">You can then set up another hierarchy to report financial information that is not legally required, but that is used for internal reporting.</span></span>

<span data-ttu-id="8a344-109">Prima di creare una gerarchia organizzativa, è necessario creare organizzazioni.</span><span class="sxs-lookup"><span data-stu-id="8a344-109">Before you create an organization hierarchy, you must create organizations.</span></span> <span data-ttu-id="8a344-110">Per ulteriori informazioni, vedere [Creare persone giuridiche](channels-legal-entities.md) o [Creare un'unità operativa](../fin-ops-core/fin-ops/organization-administration/tasks/create-operating-unit.md?toc=/dynamics365/commerce/toc.json).</span><span class="sxs-lookup"><span data-stu-id="8a344-110">For more information, see [Create legal entities](channels-legal-entities.md) or [Create operating units](../fin-ops-core/fin-ops/organization-administration/tasks/create-operating-unit.md?toc=/dynamics365/commerce/toc.json).</span></span>


<span data-ttu-id="8a344-111">Per ulteriori informazioni, vedere i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="8a344-111">For more information, see the following topics.</span></span>
- [<span data-ttu-id="8a344-112">Panoramica organizzazioni e gerarchie organizzative</span><span class="sxs-lookup"><span data-stu-id="8a344-112">Organizations and organizational hierarchies overview</span></span>](../fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies.md?toc=/dynamics365/commerce/toc.json)
- [<span data-ttu-id="8a344-113">Pianificazione della gerarchia organizzativa</span><span class="sxs-lookup"><span data-stu-id="8a344-113">Plan your organization hierarchy</span></span>](../fin-ops-core/fin-ops/organization-administration/plan-organizational-hierarchy.md?toc=/dynamics365/commerce/toc.json)
- [<span data-ttu-id="8a344-114">Creare una gerarchia organizzativa</span><span class="sxs-lookup"><span data-stu-id="8a344-114">Create an organization hierarchy</span></span>](../fin-ops-core/fin-ops/organization-administration/tasks/create-organization-hierarchy.md?toc=/dynamics365/commerce/toc.json)

## <a name="create-an-organizational-hierarchy"></a><span data-ttu-id="8a344-115">Creare una gerarchia organizzativa</span><span class="sxs-lookup"><span data-stu-id="8a344-115">Create an organizational hierarchy</span></span>

<span data-ttu-id="8a344-116">Per creare una gerarchia organizzativa, effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="8a344-116">To create an organizational hierarchy, follow these steps.</span></span>

1. <span data-ttu-id="8a344-117">Nel pannello di navigazione, andare a **Moduli \> Vendita al dettaglio e commercio \> Impostazione canale \> Gerarchie organizzative**.</span><span class="sxs-lookup"><span data-stu-id="8a344-117">In the navigation pane, go to **Modules \> Retail and commerce \> Channel Setup \> Organization hierarchies**.</span></span>
1. <span data-ttu-id="8a344-118">Nel Riquadro azioni selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="8a344-118">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="8a344-119">Nel campo **Nome** immettere un valore.</span><span class="sxs-lookup"><span data-stu-id="8a344-119">In the **Name** field, enter a value.</span></span>
1. <span data-ttu-id="8a344-120">Nella sezione **Scopo**, selezionare **Assegna scopo**.</span><span class="sxs-lookup"><span data-stu-id="8a344-120">In the **Purpose** section, select **Assign purpose**.</span></span>
1. <span data-ttu-id="8a344-121">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="8a344-121">In the list, find and select the desired record.</span></span> <span data-ttu-id="8a344-122">Selezionare uno scopo da assegnare alla propria gerarchia organizzativa.</span><span class="sxs-lookup"><span data-stu-id="8a344-122">Select a purpose to assign to your organization hierarchy.</span></span>
1. <span data-ttu-id="8a344-123">Nella sezione **Gerarchie assegnate**, selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="8a344-123">In the **Assigned hierarchies** section, select **Add**.</span></span>
1. <span data-ttu-id="8a344-124">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="8a344-124">In the list, mark the selected row.</span></span> <span data-ttu-id="8a344-125">Individuare la gerarchia appena creata.</span><span class="sxs-lookup"><span data-stu-id="8a344-125">Find the hierarchy you just created.</span></span>
1. <span data-ttu-id="8a344-126">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="8a344-126">Select **OK**.</span></span>

<span data-ttu-id="8a344-127">L'immagine seguente mostra un esempio di gerarchia organizzativa creata per un gruppo di punti vendita fittizio "Adventure Works".</span><span class="sxs-lookup"><span data-stu-id="8a344-127">The following image shows an example organizational hierarchy created for a fictitious "Adventure Works" set of stores.</span></span>

![Esempio di gerarchie organizzative](media/organizational-hierarchies.png)

### <a name="add-organizations-to-a-hierarchy"></a><span data-ttu-id="8a344-129">Aggiungere organizzazioni a una gerarchia</span><span class="sxs-lookup"><span data-stu-id="8a344-129">Add organizations to a hierarchy</span></span>

<span data-ttu-id="8a344-130">Per aggiungere organizzazioni a una gerarchia, effettuare le operazioni indicate di seguito.</span><span class="sxs-lookup"><span data-stu-id="8a344-130">To add organizations to a hierarchy, follow these steps.</span></span>

1. <span data-ttu-id="8a344-131">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="8a344-131">In the list, find and select the desired record.</span></span> <span data-ttu-id="8a344-132">Selezionare la propria gerarchia.</span><span class="sxs-lookup"><span data-stu-id="8a344-132">Select your hierarchy.</span></span>
1. <span data-ttu-id="8a344-133">Nel riquadro azioni selezionare **Visualizza**.</span><span class="sxs-lookup"><span data-stu-id="8a344-133">On the action pane, select **View**.</span></span>
1. <span data-ttu-id="8a344-134">Aggiungere organizzazioni in base alle necessità.</span><span class="sxs-lookup"><span data-stu-id="8a344-134">Add organizations, as necessary.</span></span>
1. <span data-ttu-id="8a344-135">Per aggiungere un'organizzazione, selezionare **Modifica** e quindi selezionare **Inserisci**.</span><span class="sxs-lookup"><span data-stu-id="8a344-135">To add an organization, select **Edit** and then select **Insert**.</span></span> <span data-ttu-id="8a344-136">Dopo avere apportato le modifiche, è possibile salvare una bozza e pubblicare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="8a344-136">When you are done making changes you can save a draft and publish the changes.</span></span>

<span data-ttu-id="8a344-137">L'immagine seguente mostra una persona giuridica aggiunta alla radice della gerarchia con quattro centri di costo aggiunti per i canali "Centro commerciale", "Outlet", "Online" e "Servizio clienti".</span><span class="sxs-lookup"><span data-stu-id="8a344-137">The following image shows a legal entity added at the hierarchy root with four cost centers added for "Mall", "Outlet", "Online" and "Call Center" channels.</span></span> <span data-ttu-id="8a344-138">A ognuno di questi possono quindi essere aggiunti vari canali di vendita al dettaglio, servizio clienti e online.</span><span class="sxs-lookup"><span data-stu-id="8a344-138">Various retail, call center and online channels can then be added to each.</span></span>

![Esempio di finestra di progettazione delle gerarchie](media/hierarchy-designer.png)

## <a name="additional-resources"></a><span data-ttu-id="8a344-140">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="8a344-140">Additional resources</span></span>

[<span data-ttu-id="8a344-141">Panoramica organizzazioni e gerarchie organizzative</span><span class="sxs-lookup"><span data-stu-id="8a344-141">Organizations and organizational hierarchies overview</span></span>](../fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies.md?toc=/dynamics365/commerce/toc.json)

[<span data-ttu-id="8a344-142">Pianificazione della gerarchia organizzativa</span><span class="sxs-lookup"><span data-stu-id="8a344-142">Plan your organizational hierarchy</span></span>](../fin-ops-core/fin-ops/organization-administration/plan-organizational-hierarchy.md?toc=/dynamics365/commerce/toc.json)

[<span data-ttu-id="8a344-143">Creare persone giuridiche</span><span class="sxs-lookup"><span data-stu-id="8a344-143">Create legal entities</span></span>](channels-legal-entities.md)

[<span data-ttu-id="8a344-144">Creare unità operative</span><span class="sxs-lookup"><span data-stu-id="8a344-144">Create operating units</span></span>](../fin-ops-core/fin-ops/organization-administration/tasks/create-operating-unit.md?toc=/dynamics365/commerce/toc.json)

[<span data-ttu-id="8a344-145">Panoramica dei canali</span><span class="sxs-lookup"><span data-stu-id="8a344-145">Channels overview</span></span>](channels-overview.md)

[<span data-ttu-id="8a344-146">Prerequisiti di impostazione dei canali</span><span class="sxs-lookup"><span data-stu-id="8a344-146">Channel setup prerequisites</span></span>](channels-prerequisites.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
