---
title: Configurazione della doppia scrittura da Lifecycle Services
description: Questo argomento spiega come impostare una connessione a doppia scrittura tra un nuovo ambiente Finance and Operations e un nuovo ambiente Common Data Service da Microsoft Dynamics Lifecycle Services (LCS).
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 01/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: f49eba1748861af6ee3353a6c58005ee84ccae23
ms.sourcegitcommit: 0a741b131ed71f6345d4219a47cf5f71fec6744b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "3998110"
---
# <a name="dual-write-setup-from-lifecycle-services"></a><span data-ttu-id="a1dde-103">Configurazione della doppia scrittura da Lifecycle Services</span><span class="sxs-lookup"><span data-stu-id="a1dde-103">Dual-write setup from Lifecycle Services</span></span>

[!include [banner](../../includes/banner.md)]

[!include [preview-banner](../../includes/preview-banner.md)]

<span data-ttu-id="a1dde-104">Questo argomento spiega come impostare una connessione a doppia scrittura tra un nuovo ambiente Finance and Operations e un nuovo ambiente Common Data Service da Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="a1dde-104">This topic explains how to set up a dual-write connection between a new Finance and Operations environment and a new Common Data Service environment from Microsoft Dynamics Lifecycle Services (LCS).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a1dde-105">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="a1dde-105">Prerequisites</span></span>

<span data-ttu-id="a1dde-106">È necessario essere un amministratore per impostare una connessione a doppia scrittura.</span><span class="sxs-lookup"><span data-stu-id="a1dde-106">You must be an admin to set up a dual-write connection.</span></span>

+ <span data-ttu-id="a1dde-107">È necessario disporre dell'accesso al tenant.</span><span class="sxs-lookup"><span data-stu-id="a1dde-107">You must have access to the tenant.</span></span>
+ <span data-ttu-id="a1dde-108">È necessario essere un amministratore in entrambi gli ambienti Finance and Operations e Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="a1dde-108">You must be an admin in both Finance and Operations environments and Common Data Service environments.</span></span>

## <a name="set-up-a-dual-write-connection"></a><span data-ttu-id="a1dde-109">Configurare una connessione a doppia scrittura</span><span class="sxs-lookup"><span data-stu-id="a1dde-109">Set up a dual-write connection</span></span>

<span data-ttu-id="a1dde-110">Per impostare una connessione a doppia scrittura effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="a1dde-110">Follow these steps to set up the dual-write connection.</span></span>

1. <span data-ttu-id="a1dde-111">In LCS, andare al progetto.</span><span class="sxs-lookup"><span data-stu-id="a1dde-111">In LCS, go to your project.</span></span>
2. <span data-ttu-id="a1dde-112">Selezionare **Configura** per distribuire un nuovo ambiente.</span><span class="sxs-lookup"><span data-stu-id="a1dde-112">Select **Configure** to deploy a new environment.</span></span>
3. <span data-ttu-id="a1dde-113">Selezionare la versione.</span><span class="sxs-lookup"><span data-stu-id="a1dde-113">Select the version.</span></span> 
4. <span data-ttu-id="a1dde-114">Selezionare la topologia.</span><span class="sxs-lookup"><span data-stu-id="a1dde-114">Select the topology.</span></span> <span data-ttu-id="a1dde-115">Se è disponibile solo una topologia, viene selezionata automaticamente.</span><span class="sxs-lookup"><span data-stu-id="a1dde-115">If only one topology is available, it's automatically selected.</span></span>
5. <span data-ttu-id="a1dde-116">Completare i primi passaggi nella procedura guidata **Impostazioni di distribuzione**.</span><span class="sxs-lookup"><span data-stu-id="a1dde-116">Complete the first steps in the **Deployment settings** wizard.</span></span>
6. <span data-ttu-id="a1dde-117">Nella scheda **Common Data Service** , eseguire uno dei passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="a1dde-117">On the **Common Data Service** tab, follow one of these steps:</span></span>

    - <span data-ttu-id="a1dde-118">Se un ambiente Common Data Service è già predisposto per il tenant, è possibile selezionarlo.</span><span class="sxs-lookup"><span data-stu-id="a1dde-118">If a Common Data Service environment is already provisioned for your tenant, you can select it.</span></span>

        1. <span data-ttu-id="a1dde-119">Impostare l'opzione **Configura Common Data Service** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="a1dde-119">Set the **Configure Common Data Service** option to **Yes**.</span></span>
        2. <span data-ttu-id="a1dde-120">Nel campo **Ambienti disponibili** , selezionare l'ambiente da integrare con i dati Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="a1dde-120">In the **Available environments** field, select the environment to integrate with your Finance and Operations data.</span></span> <span data-ttu-id="a1dde-121">L'elenco include tutti gli ambienti per cui si dispone dei privilegi di amministratore.</span><span class="sxs-lookup"><span data-stu-id="a1dde-121">The list includes all environments where you have admin privileges.</span></span>
        3. <span data-ttu-id="a1dde-122">Selezionare la casella di controllo **Accetto** per indicare che si accettano le condizioni.</span><span class="sxs-lookup"><span data-stu-id="a1dde-122">Select the **Agree** check box to indicate that you agree to the terms and conditions.</span></span>

        ![Scheda Common Data Service quando un ambiente Common Data Service è già predisposto per il tenant](../dual-write/media/lcs_setup_1.png)

    - <span data-ttu-id="a1dde-124">Se il tenant non dispone già di un ambiente Common Data Service, verrà fornito un nuovo ambiente.</span><span class="sxs-lookup"><span data-stu-id="a1dde-124">If your tenant doesn't already have a Common Data Service environment, a new environment will be provisioned.</span></span>

        1. <span data-ttu-id="a1dde-125">Impostare l'opzione **Configura Common Data Service** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="a1dde-125">Set the **Configure Common Data Service** option to **Yes**.</span></span>
        2. <span data-ttu-id="a1dde-126">Immettere un nome per l'ambiente Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="a1dde-126">Enter a name for the Common Data Service environment.</span></span>
        3. <span data-ttu-id="a1dde-127">Seleziona l'area geografica in cui distribuire l'ambiente.</span><span class="sxs-lookup"><span data-stu-id="a1dde-127">Select the region to deploy the environment in.</span></span>
        4. <span data-ttu-id="a1dde-128">Seleziona la lingua e la valuta predefinite per l'ambiente.</span><span class="sxs-lookup"><span data-stu-id="a1dde-128">Select the default language and currency for the environment.</span></span>

            > [!NOTE]
            > <span data-ttu-id="a1dde-129">Non è possibile cambiare la lingua e la valuta in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="a1dde-129">You can't change the language and currency later.</span></span>

        5. <span data-ttu-id="a1dde-130">Selezionare la casella di controllo **Accetto** per indicare che si accettano le condizioni.</span><span class="sxs-lookup"><span data-stu-id="a1dde-130">Select the **Agree** check box to indicate that you agree to the terms and conditions.</span></span>

        ![Scheda Common Data Service quando il tenant non dispone già si un ambiente Common Data Service](../dual-write/media/lcs_setup_2.png)

7. <span data-ttu-id="a1dde-132">Completare i rimanenti passaggi nella procedura guidata **Impostazioni di distribuzione**.</span><span class="sxs-lookup"><span data-stu-id="a1dde-132">Complete the remaining steps in the **Deployment settings** wizard.</span></span>
8. <span data-ttu-id="a1dde-133">Dopo che l'ambiente ha lo stato **Distribuito** , aprire la pagina dei dettagli dell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="a1dde-133">After the environment has a status of **Deployed** , open the environment details page.</span></span> <span data-ttu-id="a1dde-134">La sezioni **Informazioni sull'ambiente Common Data Service** mostra i nomi dell'ambiente Finance and Operations e dell'ambiente Common Data Service collegati.</span><span class="sxs-lookup"><span data-stu-id="a1dde-134">The **Common Data Service environment information** section shows the names of the Finance and Operations environment and the Common Data Service environment that are linked.</span></span>

    ![Sezione informazioni sull'ambiente Common Data Service](../dual-write/media/lcs_setup_3.png)

9. <span data-ttu-id="a1dde-136">Un amministratore dell'ambiente Finance and Operations deve accedere a LCS e selezionare **Collega a CDS per app** per completare il collegamento.</span><span class="sxs-lookup"><span data-stu-id="a1dde-136">An admin of the Finance and Operations environment must sign in to LCS and select **Link to CDS for Apps** to complete the link.</span></span> <span data-ttu-id="a1dde-137">La pagina dei dettagli dell'ambiente mostra le informazioni di contatto dell'amministratore.</span><span class="sxs-lookup"><span data-stu-id="a1dde-137">The environment details page shows the admin's contact information.</span></span>

    <span data-ttu-id="a1dde-138">Una volta completato il collegamento, lo stato viene aggiornato su **Collegamento ambiente completato**.</span><span class="sxs-lookup"><span data-stu-id="a1dde-138">After the link is completed, the status is updated to **Environment linking successfully completed**.</span></span>

10. <span data-ttu-id="a1dde-139">Per aprire l'area di lavoro **Integrazione dei dati** nell'ambiente Finance and Operations e controllare i modelli disponibili, selezionare **Collega a CDS per app**.</span><span class="sxs-lookup"><span data-stu-id="a1dde-139">To open the **Data integration** workspace in the Finance and Operations environment and control the templates that are available, select **Link to CDS for Apps**.</span></span>

    ![Pulsante Collega a CDS per app nella sezione informazioni sull'ambiente Common Data Service](../dual-write/media/lcs_setup_4.png)

> [!NOTE]
> <span data-ttu-id="a1dde-141">Non è possibile scollegare gli ambienti utilizzando LCS.</span><span class="sxs-lookup"><span data-stu-id="a1dde-141">You can't unlink environments by using LCS.</span></span> <span data-ttu-id="a1dde-142">Per scollegare un ambiente, aprire l'area di lavoro **Integrazione dei dati** nell'ambiente Finance and Operations, quindi selezionare **Scollega**.</span><span class="sxs-lookup"><span data-stu-id="a1dde-142">To unlink an environment, open the **Data integration** workspace in the Finance and Operations environment, and then select **Unlink**.</span></span>
