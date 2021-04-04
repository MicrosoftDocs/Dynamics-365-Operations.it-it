---
title: Introduzione all'amministrazione del servizio del componente aggiuntivo per la fatturazione elettronica
description: Questo argomento spiega come iniziare a usare il componente aggiuntivo per la fatturazione elettronica.
author: gionoder
manager: AnnBe
ms.date: 03/12/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 05b00380cec7511adad2467d3f252799a4aaee5c
ms.sourcegitcommit: 543772ee97efe215cf6f2ec6e092cc1568919f20
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/13/2021
ms.locfileid: "5592528"
---
# <a name="get-started-with-electronic-invoicing-add-on-service-administration"></a><span data-ttu-id="a51a7-103">Introduzione all'amministrazione del servizio del componente aggiuntivo per la fatturazione elettronica</span><span class="sxs-lookup"><span data-stu-id="a51a7-103">Get started with Electronic invoicing add-on service administration</span></span>

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

## <a name="prerequisites"></a><span data-ttu-id="a51a7-104">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="a51a7-104">Prerequisites</span></span>

<span data-ttu-id="a51a7-105">Prima di poter completare le procedure in questo argomento, è necessario soddisfare i seguenti prerequisiti:</span><span class="sxs-lookup"><span data-stu-id="a51a7-105">Before you complete the procedures in this topic, the following prerequisites must be in place:</span></span>

- <span data-ttu-id="a51a7-106">Devi avere accesso al tuo account Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="a51a7-106">You must have access to your Microsoft Dynamics Lifecycle Services (LCS) account.</span></span>
- <span data-ttu-id="a51a7-107">Devi disporre di un progetto LCS che includa la versione 10.0.17 o successiva di Microsoft Dynamics 365 Finance e Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="a51a7-107">You must have an LCS project that includes version 10.0.17 or later of Microsoft Dynamics 365 Finance and Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="a51a7-108">Inoltre, queste app devono essere distribuite in una delle seguenti aree geografiche di Azure:</span><span class="sxs-lookup"><span data-stu-id="a51a7-108">Additionally, these apps must be deployed in one of the following Azure geographies:</span></span>

    - <span data-ttu-id="a51a7-109">Stati Uniti orientali</span><span class="sxs-lookup"><span data-stu-id="a51a7-109">East US</span></span>
    - <span data-ttu-id="a51a7-110">Stati Uniti occidentali</span><span class="sxs-lookup"><span data-stu-id="a51a7-110">West US</span></span>
    - <span data-ttu-id="a51a7-111">UE settentrionale</span><span class="sxs-lookup"><span data-stu-id="a51a7-111">North EU</span></span>
    - <span data-ttu-id="a51a7-112">UE occidentale</span><span class="sxs-lookup"><span data-stu-id="a51a7-112">West EU</span></span>

- <span data-ttu-id="a51a7-113">Devi avere accesso al tuo account Dynamics 365 Regulatory Configuration Services (RCS).</span><span class="sxs-lookup"><span data-stu-id="a51a7-113">You must have access to your Dynamics 365 Regulatory Configuration Services (RCS) account.</span></span>
- <span data-ttu-id="a51a7-114">Devi attivare la funzionalità di globalizzazione per il tuo account RCS in Gestione funzionalità.</span><span class="sxs-lookup"><span data-stu-id="a51a7-114">You must activate the Globalization feature for your RCS account in Feature management.</span></span> <span data-ttu-id="a51a7-115">Per altre informazioni, vedi [Regulatory Configuration Services (RCS) - Funzionalità di globalizzazione](rcs-globalization-feature.md).</span><span class="sxs-lookup"><span data-stu-id="a51a7-115">For more information, see [Regulatory Configuration Services (RCS) - Globalization features](rcs-globalization-feature.md).</span></span>
- <span data-ttu-id="a51a7-116">Devi creare un insieme di credenziali delle chiavi e un account di archiviazione in Azure.</span><span class="sxs-lookup"><span data-stu-id="a51a7-116">You must create a key vault and a storage account in Azure.</span></span> <span data-ttu-id="a51a7-117">Per ulteriori informazioni, vedi [Creare un account di archiviazione di Azure e Key Vault](e-invoicing-create-azure-storage-account-key-vault.md).</span><span class="sxs-lookup"><span data-stu-id="a51a7-117">For more information, see [Create an Azure storage account and a key vault](e-invoicing-create-azure-storage-account-key-vault.md).</span></span>

## <a name="install-the-add-on-for-microservices-in-lifecycle-services"></a><span data-ttu-id="a51a7-118">Installa il componente aggiuntivo per microservizi in Lifecycle Services</span><span class="sxs-lookup"><span data-stu-id="a51a7-118">Install the add-on for microservices in Lifecycle Services</span></span>

1. <span data-ttu-id="a51a7-119">Accedi al tuo account LCS.</span><span class="sxs-lookup"><span data-stu-id="a51a7-119">Sign in to your LCS account.</span></span>
2. <span data-ttu-id="a51a7-120">Seleziona il riquadro **Anteprima gestione funzionalità**.</span><span class="sxs-lookup"><span data-stu-id="a51a7-120">Select the **Preview feature management** tile.</span></span>
3. <span data-ttu-id="a51a7-121">Nella sezione **Funzionalità di anteprima pubblica** seleziona **Servizio di fatturazione elettronica**.</span><span class="sxs-lookup"><span data-stu-id="a51a7-121">In the **Public Preview Features** section, select **e-Invoicing service**.</span></span>
4. <span data-ttu-id="a51a7-122">Verifica che l'opzione **Funzionalità di anteprima abilitata** sia impostata su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="a51a7-122">Make sure that the **Preview feature enabled** option is set to **Yes**.</span></span>
5. <span data-ttu-id="a51a7-123">Nel dashboard LCS, selezionare il progetto di distribuzione LCS.</span><span class="sxs-lookup"><span data-stu-id="a51a7-123">On your LCS dashboard, select your LCS deployment project.</span></span> <span data-ttu-id="a51a7-124">Il progetto LCS deve essere in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="a51a7-124">The LCS project must be running.</span></span>
7. <span data-ttu-id="a51a7-125">Nella scheda **Componenti aggiuntivi dell'ambiente**, selezionare **Installa un nuovo componente aggiuntivo**.</span><span class="sxs-lookup"><span data-stu-id="a51a7-125">On the **Environment add-ins** tab, select **Install a new add-in**.</span></span>
8. <span data-ttu-id="a51a7-126">Selezionare **Servizi di fatturazione elettronica** e nel campo **ID applicazione AAD**, immettere **091c98b0-a1c9-4b02-b62c-7753395ccabe**.</span><span class="sxs-lookup"><span data-stu-id="a51a7-126">Select **e-invoicing Services** and in the **AAD application ID** field, enter **091c98b0-a1c9-4b02-b62c-7753395ccabe**.</span></span> <span data-ttu-id="a51a7-127">Questo è un valore fisso.</span><span class="sxs-lookup"><span data-stu-id="a51a7-127">This is a fixed value.</span></span>
10. <span data-ttu-id="a51a7-128">Nel campo **ID tenant AAD** immettere l'ID tenant dell'account di sottoscrizione di Azure.</span><span class="sxs-lookup"><span data-stu-id="a51a7-128">In the **AAD tenant ID** field, enter the tenant ID of your Azure subscription account.</span></span>
11. <span data-ttu-id="a51a7-129">Esaminare i termini e le condizioni e quindi selezionare la casella di controllo.</span><span class="sxs-lookup"><span data-stu-id="a51a7-129">Review the terms and conditions, and then select the check box.</span></span>
12. <span data-ttu-id="a51a7-130">Seleziona **Installa**.</span><span class="sxs-lookup"><span data-stu-id="a51a7-130">Select **Install**.</span></span>


## <a name="set-up-the-parameters-for-rcs-integration-with-the-electronic-invoicing-add-on"></a><span data-ttu-id="a51a7-131">Configurare i parametri per l'integrazione RCS con il componente aggiuntivo per la fatturazione elettronica</span><span class="sxs-lookup"><span data-stu-id="a51a7-131">Set up the parameters for RCS integration with the Electronic invoicing add-on</span></span>

1. <span data-ttu-id="a51a7-132">Accedi al tuo account RCS.</span><span class="sxs-lookup"><span data-stu-id="a51a7-132">Sign in to your RCS account.</span></span>
2. <span data-ttu-id="a51a7-133">Nell'area di lavoro **Creazione di report elettronici**, nella sezione **Collegamenti correlati**, selezionare **Parametri per la creazione di report elettronici**.</span><span class="sxs-lookup"><span data-stu-id="a51a7-133">In the **Electronic reporting** workspace, in the **Related links** section, select **Electronic reporting parameters**.</span></span>
3. <span data-ttu-id="a51a7-134">Nella scheda **Servizio di fatturazione elettronica** nel campo **URI endpoint del servizio** immetti l'endpoint del servizio appropriato per l'area geografica di Azure, come mostrato nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="a51a7-134">On the **e-Invoicing service** tab, in the **Service endpoint URI** field, enter the appropriate service endpoint for your Azure geography, as shown in the following table.</span></span>

    | <span data-ttu-id="a51a7-135">Area geografica del data center di Azure</span><span class="sxs-lookup"><span data-stu-id="a51a7-135">Datacenter Azure geography</span></span> | <span data-ttu-id="a51a7-136">URI endpoint servizio</span><span class="sxs-lookup"><span data-stu-id="a51a7-136">Service endpoint URI</span></span>                                                       |
    |----------------------------|----------------------------------------------------------------------------|
    | <span data-ttu-id="a51a7-137">Stati Uniti orientali</span><span class="sxs-lookup"><span data-stu-id="a51a7-137">East US</span></span>                    | `https://electronicinvoicing.eus-il301.gateway.prod.island.powerapps.com/` |
    | <span data-ttu-id="a51a7-138">Stati Uniti occidentali</span><span class="sxs-lookup"><span data-stu-id="a51a7-138">West US</span></span>                    | `https://electronicinvoicing.wus-il301.gateway.prod.island.powerapps.com/` |
    | <span data-ttu-id="a51a7-139">UE settentrionale</span><span class="sxs-lookup"><span data-stu-id="a51a7-139">North EU</span></span>                   | `https://electronicinvoicing.neu-il301.gateway.prod.island.powerapps.com/` |
    | <span data-ttu-id="a51a7-140">UE occidentale</span><span class="sxs-lookup"><span data-stu-id="a51a7-140">West EU</span></span>                    | `https://electronicinvoicing.weu-il301.gateway.prod.island.powerapps.com/` |

4. <span data-ttu-id="a51a7-141">Verifica che il campo **ID applicazione** sia impostato su **0cdb527f-a8d1-4bf8-9436-b352c68682b2**.</span><span class="sxs-lookup"><span data-stu-id="a51a7-141">Verify that the **Application Id** field is set to **0cdb527f-a8d1-4bf8-9436-b352c68682b2**.</span></span> <span data-ttu-id="a51a7-142">Questo valore è un valore fisso.</span><span class="sxs-lookup"><span data-stu-id="a51a7-142">This value is a fixed value.</span></span>
5. <span data-ttu-id="a51a7-143">Nel campo **ID ambiente LCS** immetti l'ID del tuo account di sottoscrizione LCS.</span><span class="sxs-lookup"><span data-stu-id="a51a7-143">In the **LCS Environment Id** field, enter the ID of your LCS subscription account.</span></span>
6. <span data-ttu-id="a51a7-144">Selezionare **Salva**, quindi chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="a51a7-144">Select **Save**, and then close the page.</span></span>

## <a name="create-key-vault-secret"></a><span data-ttu-id="a51a7-145">Creare il segreto Key Vault</span><span class="sxs-lookup"><span data-stu-id="a51a7-145">Create Key Vault secret</span></span>

1. <span data-ttu-id="a51a7-146">Accedi al tuo account RCS.</span><span class="sxs-lookup"><span data-stu-id="a51a7-146">Sign in to your RCS account.</span></span>
2. <span data-ttu-id="a51a7-147">Nell'area di lavoro **Funzionalità di globalizzazione**, nella sezione **Ambiente**, seleziona il riquadro **Componente aggiuntivo per la fatturazione elettronica**.</span><span class="sxs-lookup"><span data-stu-id="a51a7-147">In the **Globalization feature** workspace, in the **Environment** section, select the **Electronic invoicing add-on** tile.</span></span>
3. <span data-ttu-id="a51a7-148">Nella pagina **Configurazioni dell'ambiente** nel riquadro azioni seleziona **Ambiente del servizio** e quindi seleziona **Parametri Key Vault**.</span><span class="sxs-lookup"><span data-stu-id="a51a7-148">On the **Environment setups** page, on the action Pane, select **Service environment**, and then select **Key Vault parameters**.</span></span>
4. <span data-ttu-id="a51a7-149">Seleziona **Nuovo** per creare un segreto dell'insieme di credenziali delle chiavi.</span><span class="sxs-lookup"><span data-stu-id="a51a7-149">Select **New** to create a key vault secret.</span></span>
5. <span data-ttu-id="a51a7-150">Nel campo **Nome** immettere il nome del segreto dell'insieme di credenziali delle chiavi.</span><span class="sxs-lookup"><span data-stu-id="a51a7-150">In the **Name** field, enter the name of the key vault secret.</span></span> <span data-ttu-id="a51a7-151">Nel campo **Descrizione** immettere una descrizione.</span><span class="sxs-lookup"><span data-stu-id="a51a7-151">In the **Description** field, enter a description.</span></span>
6. <span data-ttu-id="a51a7-152">Nel campo **URI Key Vault** incolla il segreto da Azure Key Vault.</span><span class="sxs-lookup"><span data-stu-id="a51a7-152">In the **Key Vault URI** field, paste the secret from Azure Key Vault.</span></span>
7. <span data-ttu-id="a51a7-153">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="a51a7-153">Select **Save**.</span></span>

## <a name="create-storage-account-secret"></a><span data-ttu-id="a51a7-154">Creare un segreto dell'account di archiviazione</span><span class="sxs-lookup"><span data-stu-id="a51a7-154">Create Storage account secret</span></span>

1. <span data-ttu-id="a51a7-155">Selezionare **Amministrazione sistema** > **Imposta** > **Parametri insieme di credenziali delle chiavi** e selezionare un segreto dell'insieme di credenziali delle chiavi.</span><span class="sxs-lookup"><span data-stu-id="a51a7-155">Go to **System administration** > **Setup** > **Key Vault parameters**, and select a Key vault secret.</span></span>
2. <span data-ttu-id="a51a7-156">Nella sezione **Certificati**, selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="a51a7-156">In the **Certificates** section, select **Add**.</span></span>
3. <span data-ttu-id="a51a7-157">Nel campo **Nome**, immettere il nome del segreto dell'account di archiviazione e nel campo **Descrizione** , immettere una descrizione.</span><span class="sxs-lookup"><span data-stu-id="a51a7-157">In the **Name** field, enter the name of the storage account secret and in the **Description** field, enter a description.</span></span>
4. <span data-ttu-id="a51a7-158">Nel campo **Tipo** seleziona **Certificato**.</span><span class="sxs-lookup"><span data-stu-id="a51a7-158">In the **Type** field, select **Certificate**.</span></span>
5. <span data-ttu-id="a51a7-159">Selezionare **Salva**, quindi chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="a51a7-159">Select **Save**, and then close the page.</span></span>

## <a name="create-a-digital-certificate-secret"></a><span data-ttu-id="a51a7-160">Creare un segreto del certificato digitale</span><span class="sxs-lookup"><span data-stu-id="a51a7-160">Create a digital certificate secret</span></span>

1. <span data-ttu-id="a51a7-161">Selezionare **Amministrazione sistema** > **Imposta** > **Parametri insieme di credenziali delle chiavi** e selezionare un segreto dell'insieme di credenziali delle chiavi.</span><span class="sxs-lookup"><span data-stu-id="a51a7-161">Go to **System administration** > **Setup** > **Key Vault parameters**, and select a Key vault secret.</span></span>
2. <span data-ttu-id="a51a7-162">Nella sezione **Certificati**, selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="a51a7-162">In the **Certificates** section, select **Add**.</span></span>
3. <span data-ttu-id="a51a7-163">Nel campo **Nome**, immettere il nome del segreto del certificato digitale e nel campo **Descrizione** , immettere una descrizione.</span><span class="sxs-lookup"><span data-stu-id="a51a7-163">In the **Name** field, enter the name of the digital certificate secret and in the **Description** field, enter a description.</span></span>
4. <span data-ttu-id="a51a7-164">Nel campo **Tipo** seleziona **Certificato**.</span><span class="sxs-lookup"><span data-stu-id="a51a7-164">In the **Type** field, select **Certificate**.</span></span>
5. <span data-ttu-id="a51a7-165">Selezionare **Salva**, quindi chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="a51a7-165">Select **Save**, and then close the page.</span></span>

## <a name="create-an-electronic-invoicing-add-on-environment"></a><span data-ttu-id="a51a7-166">Creare un ambiente del componente aggiuntivo per la fatturazione elettronica</span><span class="sxs-lookup"><span data-stu-id="a51a7-166">Create an Electronic invoicing add-on environment</span></span>

1. <span data-ttu-id="a51a7-167">Accedi al tuo account RCS.</span><span class="sxs-lookup"><span data-stu-id="a51a7-167">Sign in to your RCS account.</span></span>
2. <span data-ttu-id="a51a7-168">Nell'area di lavoro **Funzionalità di globalizzazione**, nella sezione **Ambiente**, seleziona il riquadro **Componente aggiuntivo per la fatturazione elettronica**.</span><span class="sxs-lookup"><span data-stu-id="a51a7-168">In the **Globalization feature** workspace, in the **Environment** section, select the **Electronic invoicing add-on** tile.</span></span>

## <a name="create-a-service-environment"></a><span data-ttu-id="a51a7-169">Creare un ambiente del servizio</span><span class="sxs-lookup"><span data-stu-id="a51a7-169">Create a service environment</span></span>

1. <span data-ttu-id="a51a7-170">Nella pagina **Configurazioni dell'ambiente**, nel riquadro Azioni seleziona **Ambiente del servizio**.</span><span class="sxs-lookup"><span data-stu-id="a51a7-170">On the **Environment setups** page, on the Action Pane, select **Service environment**.</span></span>
2. <span data-ttu-id="a51a7-171">Seleziona **Nuovo** per creare un nuovo ambiente del servizio.</span><span class="sxs-lookup"><span data-stu-id="a51a7-171">Select **New** to create a new service environment.</span></span>
3. <span data-ttu-id="a51a7-172">Nel campo **Nome** immettere il nome dell'ambiente di fatturazione elettronica.</span><span class="sxs-lookup"><span data-stu-id="a51a7-172">In the **Name** field, enter the name of the e-Invoicing environment.</span></span> <span data-ttu-id="a51a7-173">Nel campo **Descrizione** immettere una descrizione.</span><span class="sxs-lookup"><span data-stu-id="a51a7-173">In the **Description** field, enter a description.</span></span>
4. <span data-ttu-id="a51a7-174">Nel campo **Segreto token SAS di archiviazione** seleziona il nome del segreto dell'account di archiviazione che deve essere utilizzato per autenticare l'accesso all'account di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="a51a7-174">In the **Storage SAS token secret** field, select the name of the storage account secret that must be used to authenticate access to the storage account.</span></span>
5. <span data-ttu-id="a51a7-175">Nella sezione **Utenti** seleziona **Aggiungi** per aggiungere un utente a cui è consentito inviare fatture elettroniche attraverso l'ambiente e connettersi anche all'account di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="a51a7-175">In the **Users** section, select **Add** to add a user who is allowed to submit electronic invoices through the environment and also connect to the storage account.</span></span>
6. <span data-ttu-id="a51a7-176">Nel campo **ID utente** immetti l'alias dell'utente.</span><span class="sxs-lookup"><span data-stu-id="a51a7-176">In the **User ID** field, enter the alias of the user.</span></span> <span data-ttu-id="a51a7-177">Nel campo **E-mail** immetti l'indirizzo di posta elettronica dell'utente.</span><span class="sxs-lookup"><span data-stu-id="a51a7-177">In the **Email** field, enter the user's email address.</span></span>
7. <span data-ttu-id="a51a7-178">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="a51a7-178">Select **Save**.</span></span>
8. <span data-ttu-id="a51a7-179">Se le fatture specifiche per paese/area geografica richiedono una catena di certificati per applicare una firma digitale, seleziona nel riquadro azioni **Parametri Key Vault**, quindi seleziona **Catena di certificati** e segui questi passaggi:</span><span class="sxs-lookup"><span data-stu-id="a51a7-179">If your country/region-specific invoices require a chain of certificates to apply digital signatures, on the Action pane, select **Key Vault parameters**, then select **Chain of certificates**, and follow these steps:</span></span>

    1. <span data-ttu-id="a51a7-180">Seleziona **Nuovo** per creare una catena di certificati.</span><span class="sxs-lookup"><span data-stu-id="a51a7-180">Select **New** to create a chain of certificates.</span></span>
    2. <span data-ttu-id="a51a7-181">Nel campo **Nome** immettere il nome della catena di certificati.</span><span class="sxs-lookup"><span data-stu-id="a51a7-181">In the **Name** field, enter the name of the chain of certificate.</span></span> <span data-ttu-id="a51a7-182">Nel campo **Descrizione** immettere una descrizione.</span><span class="sxs-lookup"><span data-stu-id="a51a7-182">In the **Description** field, enter a description.</span></span>
    3. <span data-ttu-id="a51a7-183">Nella sezione **Certificati** seleziona **Aggiungi** per aggiungere un certificato alla catena.</span><span class="sxs-lookup"><span data-stu-id="a51a7-183">In the **Certificates** section, select **Add** to add a certificate to the chain.</span></span>
    4. <span data-ttu-id="a51a7-184">Usa il pulsante **Su** o **Giù** per modificare la posizione del certificato nella catena.</span><span class="sxs-lookup"><span data-stu-id="a51a7-184">Use the **Up** or **Down** button to change the position of the certificate in the chain.</span></span>
    5. <span data-ttu-id="a51a7-185">Selezionare **Salva**, quindi chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="a51a7-185">Select **Save**, and then close the page.</span></span>
    6. <span data-ttu-id="a51a7-186">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="a51a7-186">Close the page.</span></span>
9. <span data-ttu-id="a51a7-187">Nella pagina **Ambiente del servizio** nel riquadro azioni, seleziona **Pubblica** per pubblicare l'ambiente nel cloud.</span><span class="sxs-lookup"><span data-stu-id="a51a7-187">On **Service environment** page, on the Action Pane, select **Publish** to publish the environment to the cloud.</span></span> <span data-ttu-id="a51a7-188">Il valore del campo **Stato** viene modificato in **Pubblicato**.</span><span class="sxs-lookup"><span data-stu-id="a51a7-188">The value of the **Status** field is changed to **Published**.</span></span>

## <a name="create-a-connected-application"></a><span data-ttu-id="a51a7-189">Creare un'applicazione connessa</span><span class="sxs-lookup"><span data-stu-id="a51a7-189">Create a connected application</span></span>

1. <span data-ttu-id="a51a7-190">Nella pagina **Configurazioni dell'ambiente**, nel riquadro azioni seleziona **Applicazioni connesse**.</span><span class="sxs-lookup"><span data-stu-id="a51a7-190">On the **Environment setups** page, on the action Pane, select **Connected applications**.</span></span>
2. <span data-ttu-id="a51a7-191">Seleziona **Nuovo** per creare un'applicazione connessa.</span><span class="sxs-lookup"><span data-stu-id="a51a7-191">Select **New** to create a connected application.</span></span>
3. <span data-ttu-id="a51a7-192">Nel campo **Nome** immettere il nome dell'applicazione da connettere.</span><span class="sxs-lookup"><span data-stu-id="a51a7-192">In the **Name** field, enter the name of the application to connect.</span></span>
4. <span data-ttu-id="a51a7-193">Nel campo **Applicazione** immetti l'URL dell'ambiente Finance e Supply Chain Management da connettere.</span><span class="sxs-lookup"><span data-stu-id="a51a7-193">In the **Application** field, enter the URL of the Finance and Supply Chain Management environment to connect.</span></span>
4. <span data-ttu-id="a51a7-194">Nel campo **Tenant** immetti il tenant dell'ambiente Finance e Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="a51a7-194">In the **Tenant** field, enter the tenant of the Finance and Supply Chain Management environment.</span></span>
5. <span data-ttu-id="a51a7-195">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="a51a7-195">Select **Save**.</span></span>
6. <span data-ttu-id="a51a7-196">Nel riquadro azioni seleziona **Verificare connessione** per testare la connessione con l'ambiente.</span><span class="sxs-lookup"><span data-stu-id="a51a7-196">On the Action Pane, select **Check connection** to test the connection with the environment.</span></span> <span data-ttu-id="a51a7-197">Quindi, chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="a51a7-197">Then close the page.</span></span>

## <a name="link-connected-applications-to-environments"></a><span data-ttu-id="a51a7-198">Collegare le applicazioni connesse agli ambienti</span><span class="sxs-lookup"><span data-stu-id="a51a7-198">Link connected applications to environments</span></span>

1. <span data-ttu-id="a51a7-199">Nella pagina **Configurazioni ambiente** seleziona **Nuovo** per assegnare un'applicazione connessa a un ambiente.</span><span class="sxs-lookup"><span data-stu-id="a51a7-199">On the **Environment setups** page, select **New** to assign a connected application to an environment.</span></span>
2. <span data-ttu-id="a51a7-200">Nel campo **Applicazione connessa** seleziona un'applicazione connessa.</span><span class="sxs-lookup"><span data-stu-id="a51a7-200">In the **Connected application** field, select a connected application.</span></span>
3. <span data-ttu-id="a51a7-201">Nel campo **Ambiente del servizio**, seleziona un ambiente del servizio.</span><span class="sxs-lookup"><span data-stu-id="a51a7-201">In the **Service environment** field, select a service environment.</span></span>
4. <span data-ttu-id="a51a7-202">Selezionare **Salva**, quindi chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="a51a7-202">Select **Save**, and then close the page.</span></span>

## <a name="set-up-the-electronic-invoicing-add-on-integration-in-finance-and-supply-chain-management"></a><span data-ttu-id="a51a7-203">Configurare l'integrazione del componente aggiuntivo per la fatturazione elettronica in Finance e Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="a51a7-203">Set up the Electronic invoicing add-on integration in Finance and Supply Chain Management</span></span>

### <a name="turn-on-the-electronic-invoicing-add-on-integration-feature"></a><span data-ttu-id="a51a7-204">Attivare la funzionalità di integrazione del componente aggiuntivo per la fatturazione elettronica</span><span class="sxs-lookup"><span data-stu-id="a51a7-204">Turn on the Electronic invoicing add-on integration feature</span></span>

1. <span data-ttu-id="a51a7-205">Accedi alla tua istanza Finance o Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="a51a7-205">Sign in to your Finance or Supply Chain Management instance.</span></span>
2. <span data-ttu-id="a51a7-206">Nell'area di lavoro **Gestione funzionalità**, cerca la funzionalità **Integrazione del componente aggiuntivo per la fatturazione elettronica**.</span><span class="sxs-lookup"><span data-stu-id="a51a7-206">In the **Feature management** workspace, search for the **Electronic invoicing add-on integration** feature.</span></span> <span data-ttu-id="a51a7-207">Se questa funzionalità non viene visualizzata nella pagina, seleziona **Controlla aggiornamenti**.</span><span class="sxs-lookup"><span data-stu-id="a51a7-207">If this feature doesn't appear on the page, select **Check for updates**.</span></span>
3. <span data-ttu-id="a51a7-208">Seleziona la funzionalità, quindi seleziona **Abilita ora**.</span><span class="sxs-lookup"><span data-stu-id="a51a7-208">Select the feature, and then select **Enable now**.</span></span>

### <a name="set-up-the-service-endpoint-url"></a><span data-ttu-id="a51a7-209">Configurare l'URL dell'endpoint di servizio</span><span class="sxs-lookup"><span data-stu-id="a51a7-209">Set up the service endpoint URL</span></span>

1. <span data-ttu-id="a51a7-210">Vai a **Amministrazione organizzazione \> Impostazione \> Parametri documento elettronico**.</span><span class="sxs-lookup"><span data-stu-id="a51a7-210">Go to **Organization administration \> Setup \> Electronic document parameters**.</span></span>
2. <span data-ttu-id="a51a7-211">Nella scheda **Servizio di invio** nel campo **URL endpoint del servizio** immetti l'endpoint del servizio appropriato per l'area geografica di Azure, come mostrato nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="a51a7-211">On the **Submission service** tab, in the **Service endpoint URL** field, enter the appropriate service endpoint for your Azure geography, as shown in the following table.</span></span>

    | <span data-ttu-id="a51a7-212">Area geografica del data center di Azure</span><span class="sxs-lookup"><span data-stu-id="a51a7-212">Datacenter Azure geography</span></span> | <span data-ttu-id="a51a7-213">URL endpoint servizio</span><span class="sxs-lookup"><span data-stu-id="a51a7-213">Service endpoint URL</span></span>                                                       |
    |----------------------------|----------------------------------------------------------------------------|
    | <span data-ttu-id="a51a7-214">Stati Uniti orientali</span><span class="sxs-lookup"><span data-stu-id="a51a7-214">East US</span></span>                    | `https://electronicinvoicing.eus-il301.gateway.prod.island.powerapps.com/` |
    | <span data-ttu-id="a51a7-215">Stati Uniti occidentali</span><span class="sxs-lookup"><span data-stu-id="a51a7-215">West US</span></span>                    | `https://electronicinvoicing.wus-il301.gateway.prod.island.powerapps.com/` |
    | <span data-ttu-id="a51a7-216">UE settentrionale</span><span class="sxs-lookup"><span data-stu-id="a51a7-216">North EU</span></span>                   | `https://electronicinvoicing.neu-il301.gateway.prod.island.powerapps.com/` |
    | <span data-ttu-id="a51a7-217">UE occidentale</span><span class="sxs-lookup"><span data-stu-id="a51a7-217">West EU</span></span>                    | `https://electronicinvoicing.weu-il301.gateway.prod.island.powerapps.com/` |

3. <span data-ttu-id="a51a7-218">Nel campo **Ambiente** immettere il nome dell'ambiente del componente aggiuntivo Fatturazione elettronica.</span><span class="sxs-lookup"><span data-stu-id="a51a7-218">In the **Environment** field, enter the name of the Electronic invoicing add-on environment.</span></span>
4. <span data-ttu-id="a51a7-219">Selezionare **Salva**, quindi chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="a51a7-219">Select **Save**, and then close the page.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
