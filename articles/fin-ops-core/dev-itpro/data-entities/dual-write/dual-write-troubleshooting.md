---
title: Guida alla risoluzione dei problemi di integrazione dei dati
description: In questo argomento vengono fornite informazioni sulla risoluzione dei problemi di integrazione dei dati tra le app Finance and Operations e Common Data Service.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: 87bdb72024c1c3844ff61e832a92f7edcc77c5d6
ms.sourcegitcommit: 54baab2a04e5c534fc2d1fd67b67e23a152d4e57
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "3019861"
---
# <a name="troubleshooting-guide-for-data-integration"></a><span data-ttu-id="c9213-103">Guida alla risoluzione dei problemi di integrazione dei dati</span><span class="sxs-lookup"><span data-stu-id="c9213-103">Troubleshooting guide for data integration</span></span>

[!include [banner](../../includes/banner.md)]

[!include [preview-banner](../../includes/preview-banner.md)]

## <a name="enable-plug-in-trace-logs-in-common-data-service-and-inspect-the-dual-write-plug-in-error-details"></a><span data-ttu-id="c9213-104">Abilitare i registri di traccia plug-in in Common Data Service ed analizzare i dettagli degli errori del plug-in di doppia scrittura.</span><span class="sxs-lookup"><span data-stu-id="c9213-104">Enable plug-in trace logs in Common Data Service and inspect the dual-write plug-in error details</span></span>

<span data-ttu-id="c9213-105">Se si verifica un problema o un errore durante la sincronizzazione della doppia scrittura, seguire i passaggi seguenti per analizzare gli errori nel registro di traccia:</span><span class="sxs-lookup"><span data-stu-id="c9213-105">If you experience an issue or error during dual-write synchronization, follow these steps to inspect the errors in the trace log.</span></span>

1. <span data-ttu-id="c9213-106">Per poter analizzare gli errori, è necessario abilitare i registri di traccia plug-in.</span><span class="sxs-lookup"><span data-stu-id="c9213-106">Before you can inspect the errors, you must enable plug-in trace logs.</span></span> <span data-ttu-id="c9213-107">Per istruzioni, vedere la sezione "Visualizzare registri di traccia in [Esercitazione: Scrivere e registrare un plug-in](https://docs.microsoft.com/powerapps/developer/common-data-service/tutorial-write-plug-in#view-trace-logs).</span><span class="sxs-lookup"><span data-stu-id="c9213-107">For instructions, see the "View trace logs" section of [Tutorial: Write and register a plug-in](https://docs.microsoft.com/powerapps/developer/common-data-service/tutorial-write-plug-in#view-trace-logs).</span></span>

    <span data-ttu-id="c9213-108">A questo punto è possibile analizzare gli errori.</span><span class="sxs-lookup"><span data-stu-id="c9213-108">You can now inspect the errors.</span></span>

2. <span data-ttu-id="c9213-109">Accedere a Microsoft Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="c9213-109">Sign in to Microsoft Dynamics 365 Sales.</span></span>
3. <span data-ttu-id="c9213-110">Selezionare il pulsante **Impostazioni** (il simbolo di ingranaggio) e quindi selezionare **Impostazioni avanzate**.</span><span class="sxs-lookup"><span data-stu-id="c9213-110">Select the **Settings** button (the gear symbol), and then select **Advanced Settings**.</span></span>
4. <span data-ttu-id="c9213-111">Nel menu **Impostazioni**, scegliere **Personalizzazione \> Registro di traccia plug-in**.</span><span class="sxs-lookup"><span data-stu-id="c9213-111">On the **Settings** menu, select **Customization \> Plug-In Trace Log**.</span></span>
5. <span data-ttu-id="c9213-112">Selezionare **Microsoft.Dynamics.Integrator.CrmPlugins.Plugin** come nome di tipo per visualizzare i dettagli dell'errore.</span><span class="sxs-lookup"><span data-stu-id="c9213-112">Select **Microsoft.Dynamics.Integrator.CrmPlugins.Plugin** as the type name to show the error details.</span></span>

## <a name="inspect-dual-write-synchronization-errors"></a><span data-ttu-id="c9213-113">Analizzare gli errori di sincronizzazione della doppia scrittura</span><span class="sxs-lookup"><span data-stu-id="c9213-113">Inspect dual-write synchronization errors</span></span>

<span data-ttu-id="c9213-114">Seguire questi passaggi per analizzare gli errori durante i test.</span><span class="sxs-lookup"><span data-stu-id="c9213-114">Follow these steps to inspect errors during testing.</span></span>

1. <span data-ttu-id="c9213-115">Accedere a Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="c9213-115">Sign in to Microsoft Dynamics Lifecycle Services (LCS).</span></span>
2. <span data-ttu-id="c9213-116">Aprire il progetto LCS per il quale eseguire i test della doppia scrittura.</span><span class="sxs-lookup"><span data-stu-id="c9213-116">Open the LCS project to do dual-write testing for.</span></span>
3. <span data-ttu-id="c9213-117">Selezionare **Distribuzione ambienti ospitati nel cloud**.</span><span class="sxs-lookup"><span data-stu-id="c9213-117">Select **Cloud-hosted environments**.</span></span>
4. <span data-ttu-id="c9213-118">Eseguire una connessione Desktop remoto alla macchina virtuale (VM) dell'applicazione utilizzando l'account locale visualizzato in LCS.</span><span class="sxs-lookup"><span data-stu-id="c9213-118">Make a Remote desktop connection to the application virtual machine (VM) by using local account that is shown in LCS.</span></span>
5. <span data-ttu-id="c9213-119">Aprire il visualizzatore eventi.</span><span class="sxs-lookup"><span data-stu-id="c9213-119">Open Event Viewer.</span></span> 
6. <span data-ttu-id="c9213-120">Andare a **Registri applicazioni e servizi \> Microsoft \> Dynamics \> AX-DualWriteSync \> Operativo**.</span><span class="sxs-lookup"><span data-stu-id="c9213-120">Go to **Applications and Services Logs \> Microsoft \> Dynamics \> AX-DualWriteSync \> Operational**.</span></span> <span data-ttu-id="c9213-121">Gli errori e i dettagli vengono visualizzati.</span><span class="sxs-lookup"><span data-stu-id="c9213-121">The errors and details are shown.</span></span>

## <a name="unlink-one-common-data-service-environment-from-the-application-and-link-another-environment"></a><span data-ttu-id="c9213-122">Scollegare un ambiente Common Data Service dall'applicazione e collegare un altro ambiente</span><span class="sxs-lookup"><span data-stu-id="c9213-122">Unlink one Common Data Service environment from the application and link another environment</span></span>

<span data-ttu-id="c9213-123">Seguire i passaggi seguenti per aggiornare i collegamenti.</span><span class="sxs-lookup"><span data-stu-id="c9213-123">Follow these steps to update links.</span></span>

1. <span data-ttu-id="c9213-124">Accedere all'ambiente dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="c9213-124">Go to the application environment.</span></span>
2. <span data-ttu-id="c9213-125">Aprire Gestione dati.</span><span class="sxs-lookup"><span data-stu-id="c9213-125">Open Data Management.</span></span>
3. <span data-ttu-id="c9213-126">Selezionare **Collega a CDS per le app**.</span><span class="sxs-lookup"><span data-stu-id="c9213-126">Select **Link to CDS for apps**.</span></span>
4. <span data-ttu-id="c9213-127">Selezionare tutti i mapping in esecuzione, quindi selezionare **Interrompi**.</span><span class="sxs-lookup"><span data-stu-id="c9213-127">Select all the mappings that are running, and then select **Stop**.</span></span>
5. <span data-ttu-id="c9213-128">Selezionare tutti i mapping e quindi selezionare **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="c9213-128">Select all the mappings, and then select **Delete**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c9213-129">L'opzione **Elimina** non è disponibile se il modello **CustomerV3-Account** è selezionato.</span><span class="sxs-lookup"><span data-stu-id="c9213-129">The **Delete** option isn't available if the **CustomerV3-Account** template is selected.</span></span> <span data-ttu-id="c9213-130">Annullare la selezione di questo modello come necessario.</span><span class="sxs-lookup"><span data-stu-id="c9213-130">Clear the selection of this template as required.</span></span> <span data-ttu-id="c9213-131">**CustomerV3-Account** è un modello meno recente fornito e funziona con la soluzione Prospect to Cash.</span><span class="sxs-lookup"><span data-stu-id="c9213-131">**CustomerV3-Account** is an older provisioned template and works with the Prospect to Cash solution.</span></span> <span data-ttu-id="c9213-132">Poiché è rilasciato a livello globale, è visualizzato sotto tutti i modelli.</span><span class="sxs-lookup"><span data-stu-id="c9213-132">Because it's globally released, it appears under all templates.</span></span>

6. <span data-ttu-id="c9213-133">Selezionare **Scollega ambiente**.</span><span class="sxs-lookup"><span data-stu-id="c9213-133">Select **Unlink environment**.</span></span>
7. <span data-ttu-id="c9213-134">Selezionare **Sì** per confermare l'operazione.</span><span class="sxs-lookup"><span data-stu-id="c9213-134">Select **Yes** to confirm the operation.</span></span>
8. <span data-ttu-id="c9213-135">Per collegare il nuovo ambiente, seguire i passaggi nella [guida all'installazione](https://aka.ms/dualwrite-docs).</span><span class="sxs-lookup"><span data-stu-id="c9213-135">To link the new environment, follow the steps in the [installation guide](https://aka.ms/dualwrite-docs).</span></span>
