---
title: Mappare negozi e team se ci sono team preesistenti in Microsoft Teams
description: In questo argomento viene illustrato come mappare i negozi e i team corrispondenti in Dynamics 365 Commerce headquarters se la tua organizzazione ha già creato team in Microsoft Teams prima dell'integrazione di Commerce.
author: gvrmohanreddy
manager: annbe
ms.date: 03/31/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2021-01-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 3edd176788b24a5f5246e9b7bcb3c6fbcdca2254
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5842690"
---
# <a name="map-stores-and-teams-if-there-are-pre-existing-teams-in-microsoft-teams"></a><span data-ttu-id="c01bc-103">Mappare negozi e team se ci sono team preesistenti in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c01bc-103">Map stores and teams if there are pre-existing teams in Microsoft Teams</span></span>

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

<span data-ttu-id="c01bc-104">In questo argomento viene illustrato come mappare i negozi e i team corrispondenti in Dynamics 365 Commerce headquarters se la tua organizzazione ha già creato team in Microsoft Teams prima dell'integrazione di Commerce.</span><span class="sxs-lookup"><span data-stu-id="c01bc-104">This topic covers how to map stores and corresponding teams in Dynamics 365 Commerce headquarters if your organization has already created teams in Microsoft Teams before Commerce integration.</span></span>

<span data-ttu-id="c01bc-105">La tua organizzazione potrebbe avere creato dei team per alcuni o tutti i tuoi negozi prima dell'integrazione di Dynamics 365 Commerce e Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="c01bc-105">Your organization may have teams created for some or all of your stores before integrating Dynamics 365 Commerce and Microsoft Teams.</span></span> <span data-ttu-id="c01bc-106">In questo caso, per stabilire la sincronizzazione delle attività tra Commerce POS e Microsoft Teams devi fornire la mappatura dei negozi e del team corrispondente in Commerce headquarters.</span><span class="sxs-lookup"><span data-stu-id="c01bc-106">If this is the case, to establish task synchronization between Commerce POS and Microsoft Teams you must provide the mapping of stores and corresponding team in Commerce headquarters.</span></span>

## <a name="map-stores-and-corresponding-teams-in-commerce-headquarters"></a><span data-ttu-id="c01bc-107">Mappare i negozi e i team corrispondenti in Commerce headquarters</span><span class="sxs-lookup"><span data-stu-id="c01bc-107">Map stores and corresponding teams in Commerce headquarters</span></span> 

<span data-ttu-id="c01bc-108">Per mappare i negozi e i team corrispondenti in Commerce headquarters, segui questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="c01bc-108">To map stores and corresponding teams in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="c01bc-109">Vai ad **Amministrazione sistema \> Area di lavoro \> Gestione dati**.</span><span class="sxs-lookup"><span data-stu-id="c01bc-109">Go to **System Administration \> Workspace \> Data management**.</span></span>
1. <span data-ttu-id="c01bc-110">Selezionare **Esporta**.</span><span class="sxs-lookup"><span data-stu-id="c01bc-110">Select **Export**.</span></span> 
1. <span data-ttu-id="c01bc-111">Nel Riquadro azioni selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="c01bc-111">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="c01bc-112">Sotto **Nome gruppo**, immetti "Esporta mappatura Teams".</span><span class="sxs-lookup"><span data-stu-id="c01bc-112">Under **Group name**, enter "Export Teams mapping".</span></span>
1. <span data-ttu-id="c01bc-113">Nella scheda dettaglio **Entità selezionate**, seleziona **Aggiungi entità**.</span><span class="sxs-lookup"><span data-stu-id="c01bc-113">On the **Selected entities** FastTab, select **Add entity**.</span></span> <span data-ttu-id="c01bc-114">Viene visualizzata la finestra di dialogo **Aggiungi entità**.</span><span class="sxs-lookup"><span data-stu-id="c01bc-114">The **Add entity** dialog box appears.</span></span>  
1. <span data-ttu-id="c01bc-115">Nell'elenco a discesa **Nome entità** seleziona **Mapping di Teams tra origine e team**.</span><span class="sxs-lookup"><span data-stu-id="c01bc-115">In the **Entity name** drop-down list, select **Teams mapping between source and team**.</span></span>
1. <span data-ttu-id="c01bc-116">Nell'elenco a discesa **Formato dati di destinazione** seleziona **CSV**.</span><span class="sxs-lookup"><span data-stu-id="c01bc-116">In the **Target data format** drop-down list, select **CSV**.</span></span>
1. <span data-ttu-id="c01bc-117">Seleziona **Aggiungi** e quindi seleziona **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="c01bc-117">Select **Add**, and then select **Close**.</span></span>
1. <span data-ttu-id="c01bc-118">In alto a sinistra, sotto il riquadro azioni, seleziona **Esporta ora**.</span><span class="sxs-lookup"><span data-stu-id="c01bc-118">On the top left under the Action Pane, select **Export now**.</span></span>
1. <span data-ttu-id="c01bc-119">Sotto **Stato elaborazione entità**, seleziona **Scarica file**.</span><span class="sxs-lookup"><span data-stu-id="c01bc-119">Under **Entity processing status**, select **Download file**.</span></span>
1. <span data-ttu-id="c01bc-120">Nel file CSV esportato, inserisci i valori per **SOURCETYPE**, **SOURCEID**, e **TEAMID** come segue:</span><span class="sxs-lookup"><span data-stu-id="c01bc-120">In the exported CSV file, enter values for **SOURCETYPE**, **SOURCEID**, and **TEAMID** as follows:</span></span>
    - <span data-ttu-id="c01bc-121">Per **SOURCETYPE**, inserisci "RetailStore".</span><span class="sxs-lookup"><span data-stu-id="c01bc-121">For **SOURCETYPE**, enter "RetailStore".</span></span> 
    - <span data-ttu-id="c01bc-122">Per **SOURCEID**, inserisci il numero del negozio (ad esempio, "000135" per il negozio di San Francisco).</span><span class="sxs-lookup"><span data-stu-id="c01bc-122">For **SOURCEID**, enter the store number (for example, "000135" for the San Francisco store).</span></span> <span data-ttu-id="c01bc-123">Puoi trovare i numeri dei negozi in **Retail e Commerce \> Canali \> Negozi**.</span><span class="sxs-lookup"><span data-stu-id="c01bc-123">You can find store numbers at **Retail and Commerce \> Channels \> Stores**.</span></span>
    - <span data-ttu-id="c01bc-124">Per **TEAMID**, inserisci l'ID team corrispondente da Microsoft Teams (per esempio, "5f8bc92b-6aa8-451e-85d1-3949c01ddc6c").</span><span class="sxs-lookup"><span data-stu-id="c01bc-124">For **TEAMID**, enter the corresponding team ID from Microsoft Teams (for example, "5f8bc92b-6aa8-451e-85d1-3949c01ddc6c").</span></span> <span data-ttu-id="c01bc-125">Puoi trovare le informazioni sull'ID del team all'indirizzo [admin.teams.microsoft.com](https://admin.teams.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="c01bc-125">You can find team ID information at [admin.teams.microsoft.com](https://admin.teams.microsoft.com).</span></span>
1. <span data-ttu-id="c01bc-126">Salva il file CSV sul tuo computer locale.</span><span class="sxs-lookup"><span data-stu-id="c01bc-126">Save the CSV file to your local machine.</span></span>
1. <span data-ttu-id="c01bc-127">Vai ad **Amministrazione sistema \> Area di lavoro \> Gestione dati** e seleziona **Importa**.</span><span class="sxs-lookup"><span data-stu-id="c01bc-127">Go to **System Administration \> Workspace \> Data management**, and then select **Import**.</span></span>
1. <span data-ttu-id="c01bc-128">Nella scheda dettaglio **Entità selezionate**, seleziona **Aggiungi file**.</span><span class="sxs-lookup"><span data-stu-id="c01bc-128">On the **Selected entities** FastTab, select **Add file**.</span></span> <span data-ttu-id="c01bc-129">Viene visualizzata la finestra di dialogo **Aggiungi file**.</span><span class="sxs-lookup"><span data-stu-id="c01bc-129">The **Add file** dialog box appears.</span></span>
1. <span data-ttu-id="c01bc-130">Nell'elenco a discesa **Nome entità** seleziona **Mapping di Teams tra origine e team**.</span><span class="sxs-lookup"><span data-stu-id="c01bc-130">In the **Entity name** drop-down list, select **Teams mapping between source and team**.</span></span>
1. <span data-ttu-id="c01bc-131">Nell'elenco a discesa **Formato dati di origine** seleziona **CSV**.</span><span class="sxs-lookup"><span data-stu-id="c01bc-131">In the **Source data format** drop-down list, select **CSV**.</span></span>
1. <span data-ttu-id="c01bc-132">Seleziona **Carica e aggiungi**, seleziona il file CSV salvato in precedenza, quindi seleziona **Apri**.</span><span class="sxs-lookup"><span data-stu-id="c01bc-132">Select **Upload and add**, select the CSV file that you saved previously, and then select **Open**.</span></span>
1. <span data-ttu-id="c01bc-133">Nella finestra di dialogo **Aggiungi file** seleziona **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="c01bc-133">In the **Add file** dialog box, select **Close**.</span></span>
1. <span data-ttu-id="c01bc-134">Nel riquadro azioni seleziona **Salva** e quindi **Importa**.</span><span class="sxs-lookup"><span data-stu-id="c01bc-134">On the Action Pane, select **Save** , and then select **Import**.</span></span>

<span data-ttu-id="c01bc-135">L'immagine di esempio seguente mostra il gruppo **Esporta mapping di Teams** in Commerce con gli elementi **Aggiungi entità** e le intestazioni del file CSV esportato evidenziate.</span><span class="sxs-lookup"><span data-stu-id="c01bc-135">The following example image shows the **Export teams mapping** group in Commerce with **Add entity** elements and the exported CSV file headers highlighted.</span></span>

![Gruppo Esporta mapping di Teams in Commerce con gli elementi Aggiungi entità e le intestazioni del file CSV esportato evidenziate](media/d365-commerce-data-mgmt-export-entity.png)

> [!NOTE]
> <span data-ttu-id="c01bc-137">Dopo aver completato i passaggi precedenti, segui i passaggi in [Sincronizzare la gestione delle attività tra Microsoft Teams e POS](synchronize-tasks-teams-pos.md) per sincronizzare la gestione delle attività.</span><span class="sxs-lookup"><span data-stu-id="c01bc-137">After you complete the preceeding steps, follow the steps in [Synchronize task management between Microsoft Teams and POS](synchronize-tasks-teams-pos.md) to synchronize task management.</span></span> 

## <a name="additional-resources"></a><span data-ttu-id="c01bc-138">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="c01bc-138">Additional resources</span></span>

[<span data-ttu-id="c01bc-139">Panoramica dell'integrazione di Dynamics 365 Commerce e Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c01bc-139">Dynamics 365 Commerce and Microsoft Teams integration overview</span></span>](commerce-teams-integration.md)

[<span data-ttu-id="c01bc-140">Abilitare l'integrazione di Dynamics 365 Commerce e Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c01bc-140">Enable Dynamics 365 Commerce and Microsoft Teams integration</span></span>](enable-teams-integration.md)

[<span data-ttu-id="c01bc-141">Provisioning di Microsoft Teams da Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="c01bc-141">Provision Microsoft Teams from Dynamics 365 Commerce</span></span>](provision-teams-from-commerce.md)

[<span data-ttu-id="c01bc-142">Sincronizzare la gestione delle attività tra POS di Microsoft Teams e Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="c01bc-142">Synchronize task management between Microsoft Teams and Dynamics 365 Commerce POS</span></span>](synchronize-tasks-teams-pos.md)

[<span data-ttu-id="c01bc-143">Gestire i ruoli utente in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c01bc-143">Manage user roles in Microsoft Teams</span></span>](manage-user-roles-teams.md)

[<span data-ttu-id="c01bc-144">Domande frequenti sull'integrazione di Dynamics 365 Commerce e Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c01bc-144">Dynamics 365 Commerce and Microsoft Teams integration FAQ</span></span>](teams-integration-faq.md)