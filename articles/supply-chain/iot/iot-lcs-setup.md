---
title: Installare il componente aggiuntivo Intelligence IoT in LCS
description: In questo argomento viene descritto come installare il componente aggiuntivo Intelligence IoT in Microsoft Dynamics Lifecycle Services (LCS).
author: robinarh
manager: tfehr
ms.date: 07/07/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.search.region: Global
ms.author: rhaertle
ms.search.validFrom: 2020-04-04
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: ae6b36c40d2f2f9e5266dfb3e2d1cbbb57755222
ms.sourcegitcommit: 5bb36b74935ffe140367fd6ecf956b4857ad12e5
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/14/2020
ms.locfileid: "3803093"
---
# <a name="install-the-iot-intelligence-add-in-in-lcs"></a><span data-ttu-id="7df31-103">Installare il componente aggiuntivo Intelligence IoT in LCS</span><span class="sxs-lookup"><span data-stu-id="7df31-103">Install the IoT Intelligence add-in in LCS</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="7df31-104">In questo argomento viene descritto come installare il componente aggiuntivo Intelligence IoT in Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="7df31-104">This topic explains how to install the IoT Intelligence add-in in Microsoft Dynamics Lifecycle Services (LCS).</span></span> <span data-ttu-id="7df31-105">Si noti che i componenti aggiuntivi non possono essere installati in un ambiente demo/di prova.</span><span class="sxs-lookup"><span data-stu-id="7df31-105">Note that add-ins cannot be installed on a demo/trial environment.</span></span> <span data-ttu-id="7df31-106">Prima di poter installare il componente aggiuntivo, devi [creare le risorse di Azure](iot-azure-setup.md).</span><span class="sxs-lookup"><span data-stu-id="7df31-106">Before you can install the add-in, you must [create the Azure resources](iot-azure-setup.md).</span></span>

## <a name="set-up-the-lcs-environment"></a><span data-ttu-id="7df31-107">Configurare l'ambiente LCS</span><span class="sxs-lookup"><span data-stu-id="7df31-107">Set up the LCS environment</span></span>

1. <span data-ttu-id="7df31-108">Apri LCS e vai al tuo ambiente Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="7df31-108">Open LCS, and go to your Microsoft Dynamics 365 Supply Chain Management environment.</span></span>
2. <span data-ttu-id="7df31-109">Scorrere fino alla sezione **Componenti aggiuntivi dell'ambiente**.</span><span class="sxs-lookup"><span data-stu-id="7df31-109">Scroll to the **Environment add-ins** section.</span></span>
3. <span data-ttu-id="7df31-110">Seleziona **Installa un nuovo componente aggiuntivo** per mostrare l'elenco dei componenti aggiuntivi che sono stati abilitati per l'ambiente.</span><span class="sxs-lookup"><span data-stu-id="7df31-110">Select **Install a new add-in** to show the list of add-ins that have been enabled for the environment.</span></span>
4. <span data-ttu-id="7df31-111">Nella finestra di dialogo **Seleziona un componente aggiuntivo da installare**, seleziona **Intelligenza IoT**.</span><span class="sxs-lookup"><span data-stu-id="7df31-111">In the **Select an add-in to install** dialog box, select **IoT Intelligence**.</span></span>
5. <span data-ttu-id="7df31-112">Nella finestra di dialogo **Configura componente aggiuntivo**, fornisci i dettagli dell'hub IoT e della cache Redis.</span><span class="sxs-lookup"><span data-stu-id="7df31-112">In the **Setup add-in** dialog box, provide the details of your IoT hub and Redis cache.</span></span> <span data-ttu-id="7df31-113">Puoi trovare i valori richiesti nell'insieme di credenziali chiave che hai creato in [Creare le risorse di Azure](iot-azure-setup.md).</span><span class="sxs-lookup"><span data-stu-id="7df31-113">You can find the required values in the key vault that you created in [Create Azure resources](iot-azure-setup.md).</span></span>

    + <span data-ttu-id="7df31-114">**ID tenant**: nel portale Azure, vai all'insieme delle credenziali chiave quindi nel pannello di navigazione a sinistra, seleziona **Panoramica** e copia il valore **ID directory**.</span><span class="sxs-lookup"><span data-stu-id="7df31-114">**Tenant ID** – In the Azure portal, go to the key vault, and then, in the left navigation pane, select **Overview**, and copy the **Directory ID** value.</span></span> <span data-ttu-id="7df31-115">Incolla quel valore nella finestra di dialogo **Configura componente aggiuntivo**.</span><span class="sxs-lookup"><span data-stu-id="7df31-115">Paste that value in the **Setup add-in** dialog box.</span></span>
    + <span data-ttu-id="7df31-116">**URI del Key Vault dell'endpoint compatibile con hub eventi IoT**: vai all'insieme di credenziali chiave quindi, nel pannello di navigazione sinistro seleziona **Panoramica**, quindi copia il valore **Nome DNS**.</span><span class="sxs-lookup"><span data-stu-id="7df31-116">**IoT Event Hub-compatible endpoint Key Vault URI** – Go to the key vault, and then, in the left navigation pane, select **Overview**, and copy the **DNS name** value.</span></span> <span data-ttu-id="7df31-117">Incolla quel valore nella finestra di dialogo **Configura componente aggiuntivo**.</span><span class="sxs-lookup"><span data-stu-id="7df31-117">Paste that value in the **Setup add-in** dialog box.</span></span>
    + <span data-ttu-id="7df31-118">**Nome segreto dell'endpoint compatibile con hub eventi IoT**: vai all'insieme di credenziali chiave, quindi nel pannello di navigazione sinistro, seleziona **Segreti** e copia il nome del segreto in cui è memorizzata la stringa di connessione dell'hub eventi per l'hub IoT.</span><span class="sxs-lookup"><span data-stu-id="7df31-118">**IoT Event Hub-compatible endpoint secret name** – Go to the key vault, and then, in the left navigation pane, select **Secrets**, and copy the name of the secret where the event hub connection string for the IoT hub is stored.</span></span> <span data-ttu-id="7df31-119">Incolla quel valore nella finestra di dialogo **Configura componente aggiuntivo**.</span><span class="sxs-lookup"><span data-stu-id="7df31-119">Paste that value in the **Setup add-in** dialog box.</span></span>
    + <span data-ttu-id="7df31-120">**URI dell'insieme di credenziali delle chiavi della cache Redis**: vai all'insieme di credenziali chiave quindi, nel pannello di navigazione sinistro seleziona **Panoramica** e copia il valore **Nome DNS**.</span><span class="sxs-lookup"><span data-stu-id="7df31-120">**Redis cache key vault URI** – Go to the key vault, and then, in the left navigation pane, select **Overview**, and copy the **DNS name** value.</span></span> <span data-ttu-id="7df31-121">Incolla quel valore nella finestra di dialogo **Configura componente aggiuntivo**.</span><span class="sxs-lookup"><span data-stu-id="7df31-121">Paste that value in the **Setup add-in** dialog box.</span></span>
    + <span data-ttu-id="7df31-122">**Nome segreto dell'endpoint della cache Redis**: vai all'insieme di credenziali chiave, quindi nel pannello di navigazione sinistro, seleziona **Segreti** e copia il nome del segreto in cui è memorizzata la stringa di connessione della cache Redis.</span><span class="sxs-lookup"><span data-stu-id="7df31-122">**Redis cache endpoint secret name** – Go to the key vault, and then, in the left navigation pane, select **Secrets**, and copy the name of the secret where the connection string for the Redis cache is stored.</span></span> <span data-ttu-id="7df31-123">Incolla quel valore nella finestra di dialogo **Configura componente aggiuntivo**.</span><span class="sxs-lookup"><span data-stu-id="7df31-123">Paste that value in the **Setup add-in** dialog box.</span></span>

6. <span data-ttu-id="7df31-124">Seleziona la casella di controllo per accettare i termini e le condizioni.</span><span class="sxs-lookup"><span data-stu-id="7df31-124">Select the check box to accept the terms and conditions.</span></span>
7. <span data-ttu-id="7df31-125">Selezionare **Installa**.</span><span class="sxs-lookup"><span data-stu-id="7df31-125">Select **Install**.</span></span>
8. <span data-ttu-id="7df31-126">Viene visualizzata una finestra di messaggio che indica "Il componente aggiuntivo è stato attivato correttamente per l'installazione".</span><span class="sxs-lookup"><span data-stu-id="7df31-126">A message box appears that states, "Add-in has been successfully triggered for installation."</span></span> <span data-ttu-id="7df31-127">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="7df31-127">Select **OK**.</span></span>

<span data-ttu-id="7df31-128">La configurazione LCS è ora completata.</span><span class="sxs-lookup"><span data-stu-id="7df31-128">LCS setup is now completed.</span></span> <span data-ttu-id="7df31-129">Il prossimo passo è [impostare gli scenari](iot-scenario-setup.md).</span><span class="sxs-lookup"><span data-stu-id="7df31-129">The next step is to [set up the scenarios](iot-scenario-setup.md).</span></span>

## <a name="uninstall-the-add-in"></a><a id="uninstall-addin"></a><span data-ttu-id="7df31-130">Disinstallare il componente aggiuntivo</span><span class="sxs-lookup"><span data-stu-id="7df31-130">Uninstall the add-in</span></span>

1. <span data-ttu-id="7df31-131">In Supply Chain Management, [disabilita gli scenari](iot-scenario-setup.md#how-to-disable-a-scenario).</span><span class="sxs-lookup"><span data-stu-id="7df31-131">In Supply Chain Management, [disable the scenarios](iot-scenario-setup.md#how-to-disable-a-scenario).</span></span>
2. <span data-ttu-id="7df31-132">In LCS, vai ai dettagli dell'ambiente Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="7df31-132">In LCS, go to your Supply Chain Management environment details.</span></span>
3. <span data-ttu-id="7df31-133">Scorrere fino alla sezione **Componenti aggiuntivi dell'ambiente**.</span><span class="sxs-lookup"><span data-stu-id="7df31-133">Scroll to the **Environment add-ins** section.</span></span>
4. <span data-ttu-id="7df31-134">Seleziona **Disinstalla** per il componente aggiuntivo Intelligence IoT.</span><span class="sxs-lookup"><span data-stu-id="7df31-134">Select **Uninstall** for the IoT Intelligence add-in.</span></span>
