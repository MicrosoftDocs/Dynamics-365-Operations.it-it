---
title: Guida alla risoluzione dei problemi di integrazione dei dati
description: In questo argomento vengono fornite informazioni sulla risoluzione dei problemi di integrazione dei dati tra Microsoft Dynamics 365 for Finance and Operations e Common Data Service.
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
ms.openlocfilehash: ca62a6b3aa64ec2383ee3ded3b7bbf4650a41166
ms.sourcegitcommit: efcc0dee8bde5f8f93f6291e7f059ad426843e57
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/31/2019
ms.locfileid: "1797277"
---
# <a name="troubleshooting-guide-for-data-integration"></a><span data-ttu-id="f8d36-103">Guida alla risoluzione dei problemi di integrazione dei dati</span><span class="sxs-lookup"><span data-stu-id="f8d36-103">Troubleshooting guide for data integration</span></span>

## <a name="enable-plugin-trace-in-common-data-service-and-check-the-dual-write-plugin-error-details"></a><span data-ttu-id="f8d36-104">Abilitare Traccia plug-in in Common Data Service e controllare i dettagli degli errori del plug-in di doppia scrittura</span><span class="sxs-lookup"><span data-stu-id="f8d36-104">Enable Plugin Trace in Common Data Service and check the dual-write Plugin error details</span></span>

<span data-ttu-id="f8d36-105">Se si verifica un problema o errore con la sincronizzazione della doppia scrittura, è possibile analizzare gli errori nel Registro di traccia:</span><span class="sxs-lookup"><span data-stu-id="f8d36-105">If you are facing an issue or error with dual-write synchronization, you can inspect the errors in the trace log:</span></span>

1. <span data-ttu-id="f8d36-106">Prima di poter analizzare gli errori, è necessario abilitare Traccia plug-in usando le istruzioni in [Registrare il plug-in](https://docs.microsoft.com/en-us/powerapps/developer/common-data-service/tutorial-write-plug-in#view-trace-logs).</span><span class="sxs-lookup"><span data-stu-id="f8d36-106">Before you can inspect the errors, you must enable Plugin trace using the instructions in [Register plug-in](https://docs.microsoft.com/en-us/powerapps/developer/common-data-service/tutorial-write-plug-in#view-trace-logs) to enable Plugin trace.</span></span> <span data-ttu-id="f8d36-107">A questo punto è possibile analizzare gli errori.</span><span class="sxs-lookup"><span data-stu-id="f8d36-107">Now you can inspect the errors.</span></span>
2. <span data-ttu-id="f8d36-108">Accedere a Dynamics 365 for Sales</span><span class="sxs-lookup"><span data-stu-id="f8d36-108">Login to Dynamics 365 for Sales.</span></span>
3. <span data-ttu-id="f8d36-109">Fare clic sull'icona delle impostazioni (ingranaggio) e selezionare **Impostazioni avanzate**.</span><span class="sxs-lookup"><span data-stu-id="f8d36-109">Click on the Settings icon (a gear), and select **Advanced Settings**.</span></span>
4. <span data-ttu-id="f8d36-110">Nel menu **Impostazioni**, scegliere **Personalizzazione > Registro di traccia plug-in**.</span><span class="sxs-lookup"><span data-stu-id="f8d36-110">In the **Settings** menu, choose **Customization > Plug-In Trace Log**.</span></span>
5. <span data-ttu-id="f8d36-111">Fare clic sul nome del tipo **Microsoft.Dynamics.Integrator.CrmPlugins.Plugin** per visualizzare i dettagli di errore.</span><span class="sxs-lookup"><span data-stu-id="f8d36-111">Click the type name **Microsoft.Dynamics.Integrator.CrmPlugins.Plugin** to display the error details.</span></span>

## <a name="check-dual-write-synchronization-errors-in-finance-and-operations"></a><span data-ttu-id="f8d36-112">Controllare gli errori di doppia scrittura in Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="f8d36-112">Check dual-write synchronization errors in Finance and Operations</span></span>

<span data-ttu-id="f8d36-113">È possibile controllare gli errori durante il test seguendo queste operazioni:</span><span class="sxs-lookup"><span data-stu-id="f8d36-113">You can check the errors during testing by following these steps:</span></span>

+ <span data-ttu-id="f8d36-114">Accedere a Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="f8d36-114">Login to LifeCycle Services (LCS).</span></span>
+ <span data-ttu-id="f8d36-115">Apri progetto LCS su cui si è scelto di eseguire il test di doppia scrittura.</span><span class="sxs-lookup"><span data-stu-id="f8d36-115">Open the LCS project that you chose to perform dual-write testing.</span></span>
+ <span data-ttu-id="f8d36-116">Andare a Distribuzione ambienti ospitati nel cloud.</span><span class="sxs-lookup"><span data-stu-id="f8d36-116">Go to Cloud Hosted Environments.</span></span>
+ <span data-ttu-id="f8d36-117">Desktop remoto in VM Finance and Operations utilizzando l'account locale visualizzato in LCS.</span><span class="sxs-lookup"><span data-stu-id="f8d36-117">Remote desktop to Finance and Operations VM using local account that is displayed in LCS.</span></span>
+ <span data-ttu-id="f8d36-118">Apri il visualizzatore eventi.</span><span class="sxs-lookup"><span data-stu-id="f8d36-118">Open the event viewer.</span></span> 
+ <span data-ttu-id="f8d36-119">Spostarsi a **Registri applicazioni e servizi > Microsoft > Dynamics > > AX- DualWriteSync > Operativo**.</span><span class="sxs-lookup"><span data-stu-id="f8d36-119">Navigate to **Applications and Services logs > Microsoft > Dynamics > AX-DualWriteSync > Operational**.</span></span> <span data-ttu-id="f8d36-120">Gli errori e i dettagli vengono visualizzati.</span><span class="sxs-lookup"><span data-stu-id="f8d36-120">The errors and details are displayed.</span></span>

## <a name="how-to-unlink-and-link-another-common-data-service-environment-from-finance-and-operations"></a><span data-ttu-id="f8d36-121">Come scollegare e collegare un altro ambiente Common Data Service da Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="f8d36-121">How to unlink and link another Common Data Service environment from Finance and Operations</span></span>

<span data-ttu-id="f8d36-122">È possibile aggiornare i collegamenti effettuando le seguenti operazioni:</span><span class="sxs-lookup"><span data-stu-id="f8d36-122">You can update links by following these steps:</span></span>

+ <span data-ttu-id="f8d36-123">Passare all'ambiente Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="f8d36-123">Navigate to the Finance and Operations environment.</span></span>
+ <span data-ttu-id="f8d36-124">Aprire Gestione dati.</span><span class="sxs-lookup"><span data-stu-id="f8d36-124">Open Data Management.</span></span>
+ <span data-ttu-id="f8d36-125">Fare clic su **Collega a CDS per le app**.</span><span class="sxs-lookup"><span data-stu-id="f8d36-125">Click on **Link to CDS for apps**.</span></span>
+ <span data-ttu-id="f8d36-126">Selezionare tutti i mapping in esecuzione e fare clic su **Interrompi**.</span><span class="sxs-lookup"><span data-stu-id="f8d36-126">Select all the running mappings and click **Stop**.</span></span> 
+ <span data-ttu-id="f8d36-127">Selezionare tutti i mapping e fare clic su **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="f8d36-127">Select all the mappings and click **Delete**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="f8d36-128">L'opzione **Elimina** non verrà visualizzato se il modello **CustomerV3-Account** è selezionato.</span><span class="sxs-lookup"><span data-stu-id="f8d36-128">The **Delete** option will not appear if **CustomerV3-Account** template is selected.</span></span> <span data-ttu-id="f8d36-129">Deselezionarlo se necessario.</span><span class="sxs-lookup"><span data-stu-id="f8d36-129">Unselect it if needed.</span></span> <span data-ttu-id="f8d36-130">**CustomerV3-Account** è un modello meno recente fornito e funziona con la soluzione Prospect to Cash.</span><span class="sxs-lookup"><span data-stu-id="f8d36-130">**CustomerV3-Account** is an older provisioned template and works with the Prospect to Cash solution.</span></span> <span data-ttu-id="f8d36-131">Poiché è rilasciato globalmente, appare sotto tutti i modelli.</span><span class="sxs-lookup"><span data-stu-id="f8d36-131">Because it is globally released, it shows up under all templates.</span></span>

+ <span data-ttu-id="f8d36-132">Scegliere **Scollega ambiente**.</span><span class="sxs-lookup"><span data-stu-id="f8d36-132">Click **Unlink environment**.</span></span>
+ <span data-ttu-id="f8d36-133">Fare clic su **Sì** per la conferma.</span><span class="sxs-lookup"><span data-stu-id="f8d36-133">Click **Yes** for confirmation.</span></span>
+ <span data-ttu-id="f8d36-134">Per collegare il nuovo ambiente, seguire i passaggi nella [guida all'installazione](https://aka.ms/dualwrite-docs).</span><span class="sxs-lookup"><span data-stu-id="f8d36-134">To link the new environment, follow the steps in the [installation guide](https://aka.ms/dualwrite-docs).</span></span>

