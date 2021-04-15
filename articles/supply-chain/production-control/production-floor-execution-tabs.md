---
title: Progettare l'interfaccia di esecuzione dell'area di produzione
description: Questo argomento descrive come progettare il contenuto dell'interfaccia utente per ciascuna configurazione.
author: johanhoffmann
ms.date: 12/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: JmgProductionFloorExecutionConfiguration, JmgProductionFloorExecutionConfigurationTab
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2020-12-01
ms.dyn365.ops.version: Release 10.0.16
ms.openlocfilehash: 4e2b3746e690623e347e0319ab1b55f2645a5e23
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5814682"
---
# <a name="design-the-production-floor-execution-interface"></a><span data-ttu-id="6de7e-103">Progettare l'interfaccia di esecuzione dell'area di produzione</span><span class="sxs-lookup"><span data-stu-id="6de7e-103">Design the production floor execution interface</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="6de7e-104">È possibile progettare il contenuto dell'interfaccia utente per ciascuna configurazione utilizzata dall'interfaccia di esecuzione dell'area di produzione.</span><span class="sxs-lookup"><span data-stu-id="6de7e-104">You can design the content of the user interface for each configuration used by the production floor execution interface.</span></span> <span data-ttu-id="6de7e-105">Ad esempio, i lavoratori di una cella di lavoro potrebbero dover essere in grado di aprire le istruzioni di lavoro nell'area di produzione, mentre in un'altra cella di lavoro le istruzioni non sono necessarie.</span><span class="sxs-lookup"><span data-stu-id="6de7e-105">For example, workers in one work cell might need to be able to open job instructions on the production floor, while in another work cell, instructions are not needed.</span></span> <span data-ttu-id="6de7e-106">In tal caso, è necessario creare due configurazioni, una con un pulsante per l'apertura degli allegati dei documenti e una senza questo pulsante.</span><span class="sxs-lookup"><span data-stu-id="6de7e-106">In that case, two configurations should be created, one with a button for opening document attachments and one without this button.</span></span>

## <a name="design-a-tab"></a><span data-ttu-id="6de7e-107">Progettare una scheda</span><span class="sxs-lookup"><span data-stu-id="6de7e-107">Design a tab</span></span>

<span data-ttu-id="6de7e-108">Nella pagina **Configura esecuzione area di produzione** è possibile creare e configurare le schede selezionando **Progettazione schede** nel riquadro azioni.</span><span class="sxs-lookup"><span data-stu-id="6de7e-108">On the **Configure production floor execution** page, you can create and configure tabs by selecting **Design tabs** on the Action Pane.</span></span>

<span data-ttu-id="6de7e-109">Ciascuna scheda è suddivisa in quattro sezioni, come mostrato nell'illustrazione seguente.</span><span class="sxs-lookup"><span data-stu-id="6de7e-109">Each tab is divided into four sections, as shown in the following illustration.</span></span>

<span data-ttu-id="6de7e-110">![Layout della schede](media/pfe-tab-layout.png "Layout della schede")</span><span class="sxs-lookup"><span data-stu-id="6de7e-110">![Tab layout](media/pfe-tab-layout.png "Tab layout")</span></span>

<span data-ttu-id="6de7e-111">I seguenti elementi sono mostrati nell'illustrazione:</span><span class="sxs-lookup"><span data-stu-id="6de7e-111">The following elements are shown in the illustration:</span></span>

1. <span data-ttu-id="6de7e-112">Barra degli strumenti principale</span><span class="sxs-lookup"><span data-stu-id="6de7e-112">Primary toolbar</span></span>
1. <span data-ttu-id="6de7e-113">Barra degli strumenti secondaria</span><span class="sxs-lookup"><span data-stu-id="6de7e-113">Secondary toolbar</span></span>
1. <span data-ttu-id="6de7e-114">Visualizzazione principale</span><span class="sxs-lookup"><span data-stu-id="6de7e-114">Main view</span></span>
1. <span data-ttu-id="6de7e-115">Visualizzazione dettagliata</span><span class="sxs-lookup"><span data-stu-id="6de7e-115">Detailed view</span></span>

<span data-ttu-id="6de7e-116">Per creare e configurare una nuova scheda, effettuare le seguenti operazioni:</span><span class="sxs-lookup"><span data-stu-id="6de7e-116">To create and configure a new tab, follow these steps:</span></span>

1. <span data-ttu-id="6de7e-117">Andare a **Controllo produzione \> Imposta \> Esecuzione produzione \> Configura esecuzione area di produzione**.</span><span class="sxs-lookup"><span data-stu-id="6de7e-117">Go to **Production control \> Setup \> Manufacturing execution \> Configure production floor execution**.</span></span>

1. <span data-ttu-id="6de7e-118">Selezionare **Progettazione schede** nel riquadro azioni per aprire la pagina **Progettazione schede**.</span><span class="sxs-lookup"><span data-stu-id="6de7e-118">Select **Design tabs** on the Action Pane to open the **Design tabs** page.</span></span>

    <span data-ttu-id="6de7e-119">![La pagina Progettazione schede](media/pfe-design-tabs.png "La pagina Progettazione schede")</span><span class="sxs-lookup"><span data-stu-id="6de7e-119">![The Design tabs page](media/pfe-design-tabs.png "The Design tabs page")</span></span>

1. <span data-ttu-id="6de7e-120">Nel Riquadro azioni seleziona **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="6de7e-120">Select **New** on the Action Pane.</span></span>

1. <span data-ttu-id="6de7e-121">Effettuare le seguenti impostazioni nell'intestazione della pagina:</span><span class="sxs-lookup"><span data-stu-id="6de7e-121">Make the following settings in the header of the page:</span></span>

    - <span data-ttu-id="6de7e-122">**Nome scheda** - Specificare un nome per la scheda.</span><span class="sxs-lookup"><span data-stu-id="6de7e-122">**Tab name** - Specify a name for the tab.</span></span>
    - <span data-ttu-id="6de7e-123">**Visualizzazione principale** - Selezionare tra i due elenchi di processi predefiniti (*Processi attivi*, *Tutti i processi* o *Macchina personale*).</span><span class="sxs-lookup"><span data-stu-id="6de7e-123">**Main view** - Select between the two pre-defined job lists (*Active jobs*, *All jobs*, or *My machine*).</span></span>
    - <span data-ttu-id="6de7e-124">**Visualizzazione dei dettagli** - Selezionare tra un valore vuoto o **Dettagli processo**.</span><span class="sxs-lookup"><span data-stu-id="6de7e-124">**Details view** - Select between a blank value or **Job details**.</span></span> <span data-ttu-id="6de7e-125">Se si seleziona il valore vuoto, non ci sarà una visualizzazione dettagliata nella scheda. Se si seleziona **Dettagli processo**, la visualizzazione dettagliata conterrà una descrizione dettagliata del processo selezionato nell'elenco dei processi nella visualizzazione principale.</span><span class="sxs-lookup"><span data-stu-id="6de7e-125">If you select the blank value, there will be no detailed view in the tab. If you select **Job details**, the detailed view will contain a detailed description of the job selected in the job list in the main view.</span></span>

1. <span data-ttu-id="6de7e-126">Nella sezione **Barra degli strumenti principale** scegliere quali pulsanti devono essere disponibili nella barra degli strumenti principale.</span><span class="sxs-lookup"><span data-stu-id="6de7e-126">In the **Primary toolbar** section, choose which buttons should be available in the primary toolbar.</span></span> <span data-ttu-id="6de7e-127">La colonna **Azioni disponibili** mostra un elenco di tutti i pulsanti che possono essere aggiunti.</span><span class="sxs-lookup"><span data-stu-id="6de7e-127">The **Available actions** column shows a list of all the buttons that can be added.</span></span> <span data-ttu-id="6de7e-128">Le colonne **Azioni selezionate** mostrano un elenco di tutti i pulsanti inclusi nella configurazione corrente.</span><span class="sxs-lookup"><span data-stu-id="6de7e-128">The **Selected actions** columns shows a list of all the buttons that are included in the current configuration.</span></span> <span data-ttu-id="6de7e-129">Utilizzare i pulsanti tra le colonne per spostare gli elementi selezionati tra le colonne secondo necessità.</span><span class="sxs-lookup"><span data-stu-id="6de7e-129">Use the buttons between the columns to move selected items between the columns as needed.</span></span> <span data-ttu-id="6de7e-130">Utilizzare i pulsanti su e giù accanto alla colonna **Azioni selezionate** per controllare l'ordine in cui i pulsanti vengono presentati nell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="6de7e-130">Use the up and down buttons next to the **Selected actions** column to control the order in which the buttons are presented in the user interface.</span></span>

1. <span data-ttu-id="6de7e-131">Nella sezione **Barra degli strumenti** **secondaria** scegliere quali pulsanti devono essere disponibili nella barra degli strumenti secondaria.</span><span class="sxs-lookup"><span data-stu-id="6de7e-131">In the **Secondary** **toolbar** section, choose which buttons should be available in the secondary toolbar.</span></span> <span data-ttu-id="6de7e-132">La colonna **Azioni disponibili** mostra un elenco di tutti i pulsanti che possono essere aggiunti.</span><span class="sxs-lookup"><span data-stu-id="6de7e-132">The **Available actions** column shows a list of all the buttons that can be added.</span></span> <span data-ttu-id="6de7e-133">Le colonne **Azioni selezionate** mostrano un elenco di tutti i pulsanti inclusi nella configurazione corrente.</span><span class="sxs-lookup"><span data-stu-id="6de7e-133">The **Selected actions** columns shows a list of all the buttons that are included in the current configuration.</span></span> <span data-ttu-id="6de7e-134">Utilizzare i pulsanti tra le colonne per spostare gli elementi selezionati tra le colonne secondo necessità.</span><span class="sxs-lookup"><span data-stu-id="6de7e-134">Use the buttons between the columns to move selected items between the columns as needed.</span></span> <span data-ttu-id="6de7e-135">Utilizzare i pulsanti su e giù accanto alla colonna **Azioni selezionate** per controllare l'ordine in cui i pulsanti vengono presentati nell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="6de7e-135">Use the up and down buttons next to the **Selected actions** column to control the order in which the buttons are presented in the user interface.</span></span>

## <a name="associate-a-tab-with-a-configuration"></a><span data-ttu-id="6de7e-136">Associare una scheda a una configurazione</span><span class="sxs-lookup"><span data-stu-id="6de7e-136">Associate a tab with a configuration</span></span>

<span data-ttu-id="6de7e-137">Dopo aver progettato tutte le schede necessarie, è possibile associarle a una configurazione.</span><span class="sxs-lookup"><span data-stu-id="6de7e-137">After you designed all the tabs you need, you can associate them with a configuration.</span></span>

1. <span data-ttu-id="6de7e-138">Andare a **Controllo produzione \> Imposta \> Esecuzione produzione \> Configura esecuzione area di produzione**.</span><span class="sxs-lookup"><span data-stu-id="6de7e-138">Go to **Production control \> Setup \> Manufacturing execution \> Configure production floor execution**.</span></span>

    <span data-ttu-id="6de7e-139">![Configura esecuzione area di produzione](media/pfe-config-prod-floor-execution.png "Configura esecuzione area di produzione")</span><span class="sxs-lookup"><span data-stu-id="6de7e-139">![Configure production floor execution](media/pfe-config-prod-floor-execution.png "Configure production floor execution")</span></span>

1. <span data-ttu-id="6de7e-140">Nella Scheda dettaglio **Selezione scheda** selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="6de7e-140">On the **Tab selection** FastTab, select **Add**.</span></span>

1. <span data-ttu-id="6de7e-141">Una nuova riga viene aggiunta alla griglia.</span><span class="sxs-lookup"><span data-stu-id="6de7e-141">A new row is added to the grid.</span></span> <span data-ttu-id="6de7e-142">Per questa nuova riga, selezionare il nome di una scheda che si desidera aggiungere alla configurazione.</span><span class="sxs-lookup"><span data-stu-id="6de7e-142">For this new row, select the name of a tab that you want to add to the configuration.</span></span>

1. <span data-ttu-id="6de7e-143">Continuare ad aggiungere altre schede secondo necessità.</span><span class="sxs-lookup"><span data-stu-id="6de7e-143">Continue to add additional tabs as needed.</span></span>

1. <span data-ttu-id="6de7e-144">Utilizzare i pulsanti **Sposta su** e **Sposta giù** sulla barra degli strumenti per disporre le schede secondo necessità.</span><span class="sxs-lookup"><span data-stu-id="6de7e-144">Use the **Move up** and **Move down** buttons on the toolbar to arrange the tabs as needed.</span></span> <span data-ttu-id="6de7e-145">Le schede verranno visualizzate da sinistra a destra nell'ordine mostrato nella schermata sopra (la scheda in alto è mostrata a sinistra).</span><span class="sxs-lookup"><span data-stu-id="6de7e-145">The tabs will be displayed from left to right in the order shown in the above screenshot (the tab at the top is shown on the left).</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]