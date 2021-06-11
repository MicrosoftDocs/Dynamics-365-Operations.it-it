---
title: Configurazione a doppia scrittura da Lifecycle Services
description: Questo argomento spiega come configurare una connessione a doppia scrittura da Microsoft Dynamics Lifecycle Services (LCS).
author: RamaKrishnamoorthy
ms.date: 05/11/2021
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.region: global
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: eb4170ef6cb09c862f6a4163670c519d5d8077fb
ms.sourcegitcommit: 365092f735310990e82516110141d42aaf04e654
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2021
ms.locfileid: "6103571"
---
# <a name="dual-write-setup-from-lifecycle-services"></a><span data-ttu-id="73a94-103">Configurazione a doppia scrittura da Lifecycle Services</span><span class="sxs-lookup"><span data-stu-id="73a94-103">Dual-write setup from Lifecycle Services</span></span>

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="73a94-104">Questo argomento spiega come abilitare la doppia scrittura da Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="73a94-104">This topic explains how to enable dual-write from Microsoft Dynamics Lifecycle Services (LCS).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="73a94-105">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="73a94-105">Prerequisites</span></span>

<span data-ttu-id="73a94-106">Devi completare l'integrazione di Power Platform come descritto nei seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="73a94-106">You must complete the Power Platform integration as described in the following topics:</span></span>

+ [<span data-ttu-id="73a94-107">Integrazione di Power Platform: abilita durante la distribuzione dell'ambiente</span><span class="sxs-lookup"><span data-stu-id="73a94-107">Power Platform Integration - Enable during environment deployment</span></span>](../../power-platform/overview.md#enable-during-environment-deployment)
+ [<span data-ttu-id="73a94-108">Integrazione di Power Platform: configura dopo la distribuzione dell'ambiente</span><span class="sxs-lookup"><span data-stu-id="73a94-108">Power Platform integration - Set up after environment deployment</span></span>](../../power-platform/overview.md#set-up-after-environment-deployment)

## <a name="set-up-dual-write-for-new-dataverse-environments"></a><span data-ttu-id="73a94-109">Configurare la doppia scrittura per i nuovi ambienti Dataverse</span><span class="sxs-lookup"><span data-stu-id="73a94-109">Set up dual-write for new Dataverse environments</span></span>

<span data-ttu-id="73a94-110">Segui questi passaggi per configurare la doppia scrittura dalla pagina **Dettagli ambiente** di LCS:</span><span class="sxs-lookup"><span data-stu-id="73a94-110">Follow these steps to set up dual-write from LCS **Environment Details** page:</span></span>

1. <span data-ttu-id="73a94-111">Nella pagina **Dettagli ambiente**, espandi la sezione **Integrazione Power Platform**.</span><span class="sxs-lookup"><span data-stu-id="73a94-111">On the **Environment Details** page, expand the **Power Platform Integration** section.</span></span>

2. <span data-ttu-id="73a94-112">Seleziona il pulsante **Applicazione a doppia scrittura**.</span><span class="sxs-lookup"><span data-stu-id="73a94-112">Select the **Dual-write application** button.</span></span>

    ![Integrazione di Power Platform](media/powerplat_integration_step2.png)

3. <span data-ttu-id="73a94-114">Esamina i termini e le condizioni e quindi seleziona **Configura**.</span><span class="sxs-lookup"><span data-stu-id="73a94-114">Review the terms and conditions, and then select **Configure**.</span></span>

4. <span data-ttu-id="73a94-115">Selezionare **OK** per continuare.</span><span class="sxs-lookup"><span data-stu-id="73a94-115">Select **OK** to continue.</span></span>

5. <span data-ttu-id="73a94-116">Puoi monitorare l'avanzamento aggiornando periodicamente la pagina dei dettagli dell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="73a94-116">You can monitor the progress by periodically refreshing the environment details page.</span></span> <span data-ttu-id="73a94-117">La configurazione richiede in genere 30 minuti o meno.</span><span class="sxs-lookup"><span data-stu-id="73a94-117">Setup typically takes 30 minutes or less.</span></span>  

6. <span data-ttu-id="73a94-118">Quando la configurazione è completa, un messaggio ti informerà se il processo è andato a buon fine o se si è verificato un errore.</span><span class="sxs-lookup"><span data-stu-id="73a94-118">When the setup is complete, a message will inform you if the process was successful or if there was a failure.</span></span> <span data-ttu-id="73a94-119">Se la configurazione non è riuscita, viene visualizzato un messaggio di errore correlato.</span><span class="sxs-lookup"><span data-stu-id="73a94-119">If the setup failed, then a related error message is displayed.</span></span> <span data-ttu-id="73a94-120">È necessario correggere eventuali errori prima di passare alla fase successiva.</span><span class="sxs-lookup"><span data-stu-id="73a94-120">You must fix any errors before moving to the next step.</span></span>

7. <span data-ttu-id="73a94-121">Seleziona **Collegamento all'ambiente Power Platform** per creare un collegamento tra Dataverse e i database dell'ambiente corrente.</span><span class="sxs-lookup"><span data-stu-id="73a94-121">Select **Link to Power Platform environment** to create a link between Dataverse and the current environment's databases.</span></span> <span data-ttu-id="73a94-122">La configurazione richiede in genere 5 minuti o meno.</span><span class="sxs-lookup"><span data-stu-id="73a94-122">This typically takes less than 5 minutes.</span></span>

    :::image type="content" source="media/powerplat_integration_step3.png" alt-text="Collegamento all'ambiente Power Platform":::

8. <span data-ttu-id="73a94-124">Quando il collegamento è completo, viene visualizzato un collegamento ipertestuale.</span><span class="sxs-lookup"><span data-stu-id="73a94-124">When the linking is complete, a hyperlink is displayed.</span></span> <span data-ttu-id="73a94-125">Utilizza il collegamento per accedere all'area di amministrazione a doppia scrittura nell'ambiente Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="73a94-125">Use the link to sign in to the dual-write administration area in the Finance and Operations environment.</span></span> <span data-ttu-id="73a94-126">Da lì, puoi configurare le mappature delle entità.</span><span class="sxs-lookup"><span data-stu-id="73a94-126">From there, you can set up entity mappings.</span></span>

## <a name="set-up-dual-write-for-an-existing-dataverse-environment"></a><span data-ttu-id="73a94-127">Configurare la doppia scrittura per un ambiente Dataverse esistente</span><span class="sxs-lookup"><span data-stu-id="73a94-127">Set up dual-write for an existing Dataverse environment</span></span>

<span data-ttu-id="73a94-128">Per configurare la doppia scrittura per un ambiente Dataverse, è necessario creare un [ticket di supporto](../../lifecycle-services/lcs-support.md) Microsoft.</span><span class="sxs-lookup"><span data-stu-id="73a94-128">To set up dual-write for an existing Dataverse environment, you must create a Microsoft [support ticket](../../lifecycle-services/lcs-support.md).</span></span> <span data-ttu-id="73a94-129">Il ticket deve includere:</span><span class="sxs-lookup"><span data-stu-id="73a94-129">The ticket must include:</span></span>

+ <span data-ttu-id="73a94-130">L'ID ambiente Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="73a94-130">Your Finance and Operations environment ID.</span></span>
+ <span data-ttu-id="73a94-131">Il nome del tuo ambiente da Lifecycle Services.</span><span class="sxs-lookup"><span data-stu-id="73a94-131">Your environment name from Lifecycle Services.</span></span>
+ <span data-ttu-id="73a94-132">L'ID organizzazione Dataverse o ID ambiente Power Platform dall'interfaccia di amministrazione di Power Platform.</span><span class="sxs-lookup"><span data-stu-id="73a94-132">The Dataverse organization ID or Power Platform Environment ID from Power Platform Admin Center.</span></span> <span data-ttu-id="73a94-133">Nel tuo ticket, richiedi che l'ID sia l'istanza utilizzata per l'integrazione Power Platform.</span><span class="sxs-lookup"><span data-stu-id="73a94-133">In your ticket, request that the ID be the instance used for Power Platform integration.</span></span>

> [!NOTE]
> <span data-ttu-id="73a94-134">Non è possibile scollegare gli ambienti utilizzando LCS.</span><span class="sxs-lookup"><span data-stu-id="73a94-134">You can't unlink environments by using LCS.</span></span> <span data-ttu-id="73a94-135">Per scollegare un ambiente, aprire l'area di lavoro **Integrazione dei dati** nell'ambiente Finance and Operations, quindi selezionare **Scollega**.</span><span class="sxs-lookup"><span data-stu-id="73a94-135">To unlink an environment, open the **Data integration** workspace in the Finance and Operations environment, and then select **Unlink**.</span></span>

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
