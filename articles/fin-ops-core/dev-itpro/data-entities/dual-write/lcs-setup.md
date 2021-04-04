---
title: Configurazione a doppia scrittura da Lifecycle Services
description: Questo argomento spiega come configurare una connessione a doppia scrittura da Microsoft Dynamics Lifecycle Services (LCS).
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 01/06/2020
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 6971c8e2d5fa03c2991b9a3054c638cff6322c8b
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2021
ms.locfileid: "5567722"
---
# <a name="dual-write-setup-from-lifecycle-services"></a><span data-ttu-id="4e973-103">Configurazione a doppia scrittura da Lifecycle Services</span><span class="sxs-lookup"><span data-stu-id="4e973-103">Dual-write setup from Lifecycle Services</span></span>

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="4e973-104">Questo argomento spiega come impostare una connessione a doppia scrittura tra un nuovo ambiente Finance and Operations e un nuovo ambiente Dataverse da Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="4e973-104">This topic explains how to set up a dual-write connection between a new Finance and Operations environment and a new Dataverse environment from Microsoft Dynamics Lifecycle Services (LCS).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="4e973-105">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="4e973-105">Prerequisites</span></span>

<span data-ttu-id="4e973-106">È necessario essere un amministratore per impostare una connessione a doppia scrittura.</span><span class="sxs-lookup"><span data-stu-id="4e973-106">You must be an admin to set up a dual-write connection.</span></span>

+ <span data-ttu-id="4e973-107">È necessario disporre dell'accesso al tenant.</span><span class="sxs-lookup"><span data-stu-id="4e973-107">You must have access to the tenant.</span></span>
+ <span data-ttu-id="4e973-108">È necessario essere un amministratore in entrambi gli ambienti Finance and Operations e Dataverse.</span><span class="sxs-lookup"><span data-stu-id="4e973-108">You must be an admin in both Finance and Operations environments and Dataverse environments.</span></span>

## <a name="set-up-a-dual-write-connection"></a><span data-ttu-id="4e973-109">Configurare una connessione a doppia scrittura</span><span class="sxs-lookup"><span data-stu-id="4e973-109">Set up a dual-write connection</span></span>

<span data-ttu-id="4e973-110">Per impostare una connessione a doppia scrittura effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="4e973-110">Follow these steps to set up the dual-write connection.</span></span>

1. <span data-ttu-id="4e973-111">In LCS, andare al progetto.</span><span class="sxs-lookup"><span data-stu-id="4e973-111">In LCS, go to your project.</span></span>
2. <span data-ttu-id="4e973-112">Selezionare **Configura** per distribuire un nuovo ambiente.</span><span class="sxs-lookup"><span data-stu-id="4e973-112">Select **Configure** to deploy a new environment.</span></span>
3. <span data-ttu-id="4e973-113">Selezionare la versione.</span><span class="sxs-lookup"><span data-stu-id="4e973-113">Select the version.</span></span> 
4. <span data-ttu-id="4e973-114">Selezionare la topologia.</span><span class="sxs-lookup"><span data-stu-id="4e973-114">Select the topology.</span></span> <span data-ttu-id="4e973-115">Se è disponibile solo una topologia, viene selezionata automaticamente.</span><span class="sxs-lookup"><span data-stu-id="4e973-115">If only one topology is available, it's automatically selected.</span></span>
5. <span data-ttu-id="4e973-116">Completare i primi passaggi nella procedura guidata **Impostazioni di distribuzione**.</span><span class="sxs-lookup"><span data-stu-id="4e973-116">Complete the first steps in the **Deployment settings** wizard.</span></span>
6. <span data-ttu-id="4e973-117">Nella scheda **Dataverse**, eseguire uno dei passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="4e973-117">On the **Dataverse** tab, follow one of these steps:</span></span>

    - <span data-ttu-id="4e973-118">Se un ambiente Dataverse è già predisposto per il tenant, è possibile selezionarlo.</span><span class="sxs-lookup"><span data-stu-id="4e973-118">If a Dataverse environment is already provisioned for your tenant, you can select it.</span></span>

        1. <span data-ttu-id="4e973-119">Impostare l'opzione **Configura Dataverse** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="4e973-119">Set the **Configure Dataverse** option to **Yes**.</span></span>
        2. <span data-ttu-id="4e973-120">Nella colonna **Ambienti disponibili**, selezionare l'ambiente da integrare con i dati Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="4e973-120">In the **Available environments** column, select the environment to integrate with your Finance and Operations data.</span></span> <span data-ttu-id="4e973-121">L'elenco include tutti gli ambienti per cui si dispone dei privilegi di amministratore.</span><span class="sxs-lookup"><span data-stu-id="4e973-121">The list includes all environments where you have admin privileges.</span></span>
        3. <span data-ttu-id="4e973-122">Selezionare la casella di controllo **Accetto** per indicare che si accettano le condizioni.</span><span class="sxs-lookup"><span data-stu-id="4e973-122">Select the **Agree** check box to indicate that you agree to the terms and conditions.</span></span>

        ![Scheda Dataverse quando un ambiente Dataverse è già predisposto per il tenant](../dual-write/media/lcs_setup_1.png)

    - <span data-ttu-id="4e973-124">Se il tenant non dispone già di un ambiente Dataverse, verrà fornito un nuovo ambiente.</span><span class="sxs-lookup"><span data-stu-id="4e973-124">If your tenant doesn't already have a Dataverse environment, a new environment will be provisioned.</span></span>

        1. <span data-ttu-id="4e973-125">Impostare l'opzione **Configura Dataverse** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="4e973-125">Set the **Configure Dataverse** option to **Yes**.</span></span>
        2. <span data-ttu-id="4e973-126">Immettere un nome per l'ambiente Dataverse.</span><span class="sxs-lookup"><span data-stu-id="4e973-126">Enter a name for the Dataverse environment.</span></span>
        3. <span data-ttu-id="4e973-127">Seleziona l'area geografica in cui distribuire l'ambiente.</span><span class="sxs-lookup"><span data-stu-id="4e973-127">Select the region to deploy the environment in.</span></span>
        4. <span data-ttu-id="4e973-128">Seleziona la lingua e la valuta predefinite per l'ambiente.</span><span class="sxs-lookup"><span data-stu-id="4e973-128">Select the default language and currency for the environment.</span></span>

            > [!NOTE]
            > <span data-ttu-id="4e973-129">Non è possibile cambiare la lingua e la valuta in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="4e973-129">You can't change the language and currency later.</span></span>

        5. <span data-ttu-id="4e973-130">Selezionare la casella di controllo **Accetto** per indicare che si accettano le condizioni.</span><span class="sxs-lookup"><span data-stu-id="4e973-130">Select the **Agree** check box to indicate that you agree to the terms and conditions.</span></span>

        ![Scheda Dataverse quando il tenant non dispone già si un ambiente Dataverse](../dual-write/media/lcs_setup_2.png)

7. <span data-ttu-id="4e973-132">Completare i rimanenti passaggi nella procedura guidata **Impostazioni di distribuzione**.</span><span class="sxs-lookup"><span data-stu-id="4e973-132">Complete the remaining steps in the **Deployment settings** wizard.</span></span>
8. <span data-ttu-id="4e973-133">Dopo che l'ambiente ha lo stato **Distribuito**, aprire la pagina dei dettagli dell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="4e973-133">After the environment has a status of **Deployed**, open the environment details page.</span></span> <span data-ttu-id="4e973-134">La sezione **Integrazione Power Platform** mostra i nomi dell'ambiente Finance and Operations e dell'ambiente Dataverse collegati.</span><span class="sxs-lookup"><span data-stu-id="4e973-134">The **Power Platform Integration** section shows the names of the Finance and Operations environment and the Dataverse environment that are linked.</span></span>

    ![Sezione Integrazione Power Platform](../dual-write/media/lcs_setup_3.png)

9. <span data-ttu-id="4e973-136">Un amministratore dell'ambiente Finance and Operations deve accedere a LCS e selezionare **Collega a CDS per app** per completare il collegamento.</span><span class="sxs-lookup"><span data-stu-id="4e973-136">An admin of the Finance and Operations environment must sign in to LCS and select **Link to CDS for Apps** to complete the link.</span></span> <span data-ttu-id="4e973-137">La pagina dei dettagli dell'ambiente mostra le informazioni di contatto dell'amministratore.</span><span class="sxs-lookup"><span data-stu-id="4e973-137">The environment details page shows the admin's contact information.</span></span>

    <span data-ttu-id="4e973-138">Una volta completato il collegamento, lo stato viene aggiornato su **Collegamento ambiente completato**.</span><span class="sxs-lookup"><span data-stu-id="4e973-138">After the link is completed, the status is updated to **Environment linking successfully completed**.</span></span>

10. <span data-ttu-id="4e973-139">Per aprire l'area di lavoro **Integrazione dei dati** nell'ambiente Finance and Operations e controllare i modelli disponibili, selezionare **Collega a CDS per app**.</span><span class="sxs-lookup"><span data-stu-id="4e973-139">To open the **Data integration** workspace in the Finance and Operations environment and control the templates that are available, select **Link to CDS for Apps**.</span></span>

    ![Pulsante Collega a CDS per app nella sezione Integrazione Power Platform](../dual-write/media/lcs_setup_4.png)

> [!NOTE]
> <span data-ttu-id="4e973-141">Non è possibile scollegare gli ambienti utilizzando LCS.</span><span class="sxs-lookup"><span data-stu-id="4e973-141">You can't unlink environments by using LCS.</span></span> <span data-ttu-id="4e973-142">Per scollegare un ambiente, aprire l'area di lavoro **Integrazione dei dati** nell'ambiente Finance and Operations, quindi selezionare **Scollega**.</span><span class="sxs-lookup"><span data-stu-id="4e973-142">To unlink an environment, open the **Data integration** workspace in the Finance and Operations environment, and then select **Unlink**.</span></span>



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]