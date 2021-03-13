---
title: Progettare l'interfaccia di esecuzione dell'area di produzione
description: Questo argomento descrive come progettare il contenuto dell'interfaccia utente per ciascuna configurazione.
author: johanhoffmann
manager: tfehr
ms.date: 12/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2020-12-01
ms.dyn365.ops.version: Release 10.0.16
ms.openlocfilehash: 786ea9a3da98e9f1812b007d4301cb47680e6894
ms.sourcegitcommit: b7a7a14f8650913f6797ae1c4a82ad8adfe415fd
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2021
ms.locfileid: "5077580"
---
# <a name="design-the-production-floor-execution-interface"></a><span data-ttu-id="25194-103">Progettare l'interfaccia di esecuzione dell'area di produzione</span><span class="sxs-lookup"><span data-stu-id="25194-103">Design the production floor execution interface</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="25194-104">È possibile progettare il contenuto dell'interfaccia utente per ciascuna configurazione utilizzata dall'interfaccia di esecuzione dell'area di produzione.</span><span class="sxs-lookup"><span data-stu-id="25194-104">You can design the content of the user interface for each configuration used by the production floor execution interface.</span></span> <span data-ttu-id="25194-105">Ad esempio, i lavoratori di una cella di lavoro potrebbero dover essere in grado di aprire le istruzioni di lavoro nell'area di produzione, mentre in un'altra cella di lavoro le istruzioni non sono necessarie.</span><span class="sxs-lookup"><span data-stu-id="25194-105">For example, workers in one work cell might need to be able to open job instructions on the production floor, while in another work cell, instructions are not needed.</span></span> <span data-ttu-id="25194-106">In tal caso, è necessario creare due configurazioni, una con un pulsante per l'apertura degli allegati dei documenti e una senza questo pulsante.</span><span class="sxs-lookup"><span data-stu-id="25194-106">In that case, two configurations should be created, one with a button for opening document attachments and one without this button.</span></span>

## <a name="design-a-tab"></a><span data-ttu-id="25194-107">Progettare una scheda</span><span class="sxs-lookup"><span data-stu-id="25194-107">Design a tab</span></span>

<span data-ttu-id="25194-108">Nella pagina **Configura esecuzione area di produzione** è possibile creare e configurare le schede selezionando **Progettazione schede** nel riquadro azioni.</span><span class="sxs-lookup"><span data-stu-id="25194-108">On the **Configure production floor execution** page, you can create and configure tabs by selecting **Design tabs** on the Action Pane.</span></span>

<span data-ttu-id="25194-109">Ciascuna scheda è suddivisa in quattro sezioni, come mostrato nell'illustrazione seguente.</span><span class="sxs-lookup"><span data-stu-id="25194-109">Each tab is divided into four sections, as shown in the following illustration.</span></span>

<span data-ttu-id="25194-110">![Layout della schede](media/pfe-tab-layout.png "Layout della schede")</span><span class="sxs-lookup"><span data-stu-id="25194-110">![Tab layout](media/pfe-tab-layout.png "Tab layout")</span></span>

<span data-ttu-id="25194-111">I seguenti elementi sono mostrati nell'illustrazione:</span><span class="sxs-lookup"><span data-stu-id="25194-111">The following elements are shown in the illustration:</span></span>

1. <span data-ttu-id="25194-112">Barra degli strumenti principale</span><span class="sxs-lookup"><span data-stu-id="25194-112">Primary toolbar</span></span>
1. <span data-ttu-id="25194-113">Barra degli strumenti secondaria</span><span class="sxs-lookup"><span data-stu-id="25194-113">Secondary toolbar</span></span>
1. <span data-ttu-id="25194-114">Visualizzazione principale</span><span class="sxs-lookup"><span data-stu-id="25194-114">Main view</span></span>
1. <span data-ttu-id="25194-115">Visualizzazione dettagliata</span><span class="sxs-lookup"><span data-stu-id="25194-115">Detailed view</span></span>

<span data-ttu-id="25194-116">Per creare e configurare una nuova scheda, effettuare le seguenti operazioni:</span><span class="sxs-lookup"><span data-stu-id="25194-116">To create and configure a new tab, follow these steps:</span></span>

1. <span data-ttu-id="25194-117">Passare a **Controllo produzione &gt; Impostazione &gt; Esecuzione produzione**.</span><span class="sxs-lookup"><span data-stu-id="25194-117">Go to **Production control &gt; Setup &gt; Manufacturing execution**.</span></span>

1. <span data-ttu-id="25194-118">Selezionare **Progettazione schede** nel riquadro azioni per aprire la pagina **Progettazione schede**.</span><span class="sxs-lookup"><span data-stu-id="25194-118">Select **Design tabs** on the Action Pane to open the **Design tabs** page.</span></span>

    <span data-ttu-id="25194-119">![La pagina Progettazione schede](media/pfe-design-tabs.png "La pagina Progettazione schede")</span><span class="sxs-lookup"><span data-stu-id="25194-119">![The Design tabs page](media/pfe-design-tabs.png "The Design tabs page")</span></span>

1. <span data-ttu-id="25194-120">Nel Riquadro azioni seleziona **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="25194-120">Select **New** on the Action Pane.</span></span>

1. <span data-ttu-id="25194-121">Effettuare le seguenti impostazioni nell'intestazione della pagina:</span><span class="sxs-lookup"><span data-stu-id="25194-121">Make the following settings in the header of the page:</span></span>

    - <span data-ttu-id="25194-122">**Nome scheda** - Specificare un nome per la scheda.</span><span class="sxs-lookup"><span data-stu-id="25194-122">**Tab name** - Specify a name for the tab.</span></span>
    - <span data-ttu-id="25194-123">**Visualizzazione principale** - Selezionare tra i due elenchi di processi predefiniti (*Processi attivi*, *Tutti i processi* o *Macchina personale*).</span><span class="sxs-lookup"><span data-stu-id="25194-123">**Main view** - Select between the two pre-defined job lists (*Active jobs*, *All jobs*, or *My machine*).</span></span>
    - <span data-ttu-id="25194-124">**Visualizzazione dei dettagli** - Selezionare tra un valore vuoto o **Dettagli processo**.</span><span class="sxs-lookup"><span data-stu-id="25194-124">**Details view** - Select between a blank value or **Job details**.</span></span> <span data-ttu-id="25194-125">Se si seleziona il valore vuoto, non ci sarà una visualizzazione dettagliata nella scheda. Se si seleziona **Dettagli processo**, la visualizzazione dettagliata conterrà una descrizione dettagliata del processo selezionato nell'elenco dei processi nella visualizzazione principale.</span><span class="sxs-lookup"><span data-stu-id="25194-125">If you select the blank value, there will be no detailed view in the tab. If you select **Job details**, the detailed view will contain a detailed description of the job selected in the job list in the main view.</span></span>

1. <span data-ttu-id="25194-126">Nella sezione **Barra degli strumenti principale** scegliere quali pulsanti devono essere disponibili nella barra degli strumenti principale.</span><span class="sxs-lookup"><span data-stu-id="25194-126">In the **Primary toolbar** section, choose which buttons should be available in the primary toolbar.</span></span> <span data-ttu-id="25194-127">La colonna **Azioni disponibili** mostra un elenco di tutti i pulsanti che possono essere aggiunti.</span><span class="sxs-lookup"><span data-stu-id="25194-127">The **Available actions** column shows a list of all the buttons that can be added.</span></span> <span data-ttu-id="25194-128">Le colonne **Azioni selezionate** mostrano un elenco di tutti i pulsanti inclusi nella configurazione corrente.</span><span class="sxs-lookup"><span data-stu-id="25194-128">The **Selected actions** columns shows a list of all the buttons that are included in the current configuration.</span></span> <span data-ttu-id="25194-129">Utilizzare i pulsanti tra le colonne per spostare gli elementi selezionati tra le colonne secondo necessità.</span><span class="sxs-lookup"><span data-stu-id="25194-129">Use the buttons between the columns to move selected items between the columns as needed.</span></span> <span data-ttu-id="25194-130">Utilizzare i pulsanti su e giù accanto alla colonna **Azioni selezionate** per controllare l'ordine in cui i pulsanti vengono presentati nell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="25194-130">Use the up and down buttons next to the **Selected actions** column to control the order in which the buttons are presented in the user interface.</span></span>

1. <span data-ttu-id="25194-131">Nella sezione **Barra degli strumenti** **secondaria** scegliere quali pulsanti devono essere disponibili nella barra degli strumenti secondaria.</span><span class="sxs-lookup"><span data-stu-id="25194-131">In the **Secondary** **toolbar** section, choose which buttons should be available in the secondary toolbar.</span></span> <span data-ttu-id="25194-132">La colonna **Azioni disponibili** mostra un elenco di tutti i pulsanti che possono essere aggiunti.</span><span class="sxs-lookup"><span data-stu-id="25194-132">The **Available actions** column shows a list of all the buttons that can be added.</span></span> <span data-ttu-id="25194-133">Le colonne **Azioni selezionate** mostrano un elenco di tutti i pulsanti inclusi nella configurazione corrente.</span><span class="sxs-lookup"><span data-stu-id="25194-133">The **Selected actions** columns shows a list of all the buttons that are included in the current configuration.</span></span> <span data-ttu-id="25194-134">Utilizzare i pulsanti tra le colonne per spostare gli elementi selezionati tra le colonne secondo necessità.</span><span class="sxs-lookup"><span data-stu-id="25194-134">Use the buttons between the columns to move selected items between the columns as needed.</span></span> <span data-ttu-id="25194-135">Utilizzare i pulsanti su e giù accanto alla colonna **Azioni selezionate** per controllare l'ordine in cui i pulsanti vengono presentati nell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="25194-135">Use the up and down buttons next to the **Selected actions** column to control the order in which the buttons are presented in the user interface.</span></span>

## <a name="associate-a-tab-with-a-configuration"></a><span data-ttu-id="25194-136">Associare una scheda a una configurazione</span><span class="sxs-lookup"><span data-stu-id="25194-136">Associate a tab with a configuration</span></span>

<span data-ttu-id="25194-137">Dopo aver progettato tutte le schede necessarie, è possibile associarle a una configurazione.</span><span class="sxs-lookup"><span data-stu-id="25194-137">After you designed all the tabs you need, you can associate them with a configuration.</span></span>

1. <span data-ttu-id="25194-138">Andare a **Controllo produzione &gt; Impostazione &gt; Configura esecuzione area di produzione**.</span><span class="sxs-lookup"><span data-stu-id="25194-138">Go to **Production control &gt; Setup &gt; Configure production floor execution**.</span></span>

    <span data-ttu-id="25194-139">![Configura esecuzione area di produzione](media/pfe-config-prod-floor-execution.png "Configura esecuzione area di produzione")</span><span class="sxs-lookup"><span data-stu-id="25194-139">![Configure production floor execution](media/pfe-config-prod-floor-execution.png "Configure production floor execution")</span></span>

1. <span data-ttu-id="25194-140">Nella Scheda dettaglio **Selezione scheda** selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="25194-140">On the **Tab selection** FastTab, select **Add**.</span></span>

1. <span data-ttu-id="25194-141">Una nuova riga viene aggiunta alla griglia.</span><span class="sxs-lookup"><span data-stu-id="25194-141">A new row is added to the grid.</span></span> <span data-ttu-id="25194-142">Per questa nuova riga, selezionare il nome di una scheda che si desidera aggiungere alla configurazione.</span><span class="sxs-lookup"><span data-stu-id="25194-142">For this new row, select the name of a tab that you want to add to the configuration.</span></span>

1. <span data-ttu-id="25194-143">Continuare ad aggiungere altre schede secondo necessità.</span><span class="sxs-lookup"><span data-stu-id="25194-143">Continue to add additional tabs as needed.</span></span>

1. <span data-ttu-id="25194-144">Utilizzare i pulsanti **Sposta su** e **Sposta giù** sulla barra degli strumenti per disporre le schede secondo necessità.</span><span class="sxs-lookup"><span data-stu-id="25194-144">Use the **Move up** and **Move down** buttons on the toolbar to arrange the tabs as needed.</span></span> <span data-ttu-id="25194-145">Le schede verranno visualizzate da sinistra a destra nell'ordine mostrato nella schermata sopra (la scheda in alto è mostrata a sinistra).</span><span class="sxs-lookup"><span data-stu-id="25194-145">The tabs will be displayed from left to right in the order shown in the above screenshot (the tab at the top is shown on the left).</span></span>
