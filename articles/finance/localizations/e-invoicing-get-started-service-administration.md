---
title: Introduzione all'amministrazione dei servizi per la fatturazione elettronica
description: Questo argomento spiega come iniziare a usare la fatturazione elettronica.
author: gionoder
ms.date: 03/29/2021
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: ec431cb4a3620459d905f64a80fd820a2113290f
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5840150"
---
# <a name="get-started-with-electronic-invoicing-service-administration"></a><span data-ttu-id="7c9d5-103">Introduzione all'amministrazione dei servizi per la fatturazione elettronica</span><span class="sxs-lookup"><span data-stu-id="7c9d5-103">Get started with Electronic invoicing service administration</span></span>

[!include [banner](../includes/banner.md)]

## <a name="prerequisites"></a><span data-ttu-id="7c9d5-104">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="7c9d5-104">Prerequisites</span></span>

<span data-ttu-id="7c9d5-105">Prima di poter completare le procedure in questo argomento, è necessario soddisfare i seguenti prerequisiti:</span><span class="sxs-lookup"><span data-stu-id="7c9d5-105">Before you complete the procedures in this topic, the following prerequisites must be in place:</span></span>

- <span data-ttu-id="7c9d5-106">Devi avere accesso al tuo account Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="7c9d5-106">You must have access to your Microsoft Dynamics Lifecycle Services (LCS) account.</span></span>
- <span data-ttu-id="7c9d5-107">Devi disporre di un progetto LCS che includa la versione 10.0.17 o successiva di Microsoft Dynamics 365 Finance e Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="7c9d5-107">You must have an LCS project that includes version 10.0.17 or later of Microsoft Dynamics 365 Finance and Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="7c9d5-108">Inoltre, queste app devono essere distribuite in una delle seguenti aree geografiche di Azure:</span><span class="sxs-lookup"><span data-stu-id="7c9d5-108">Additionally, these apps must be deployed in one of the following Azure geographies:</span></span>

    - <span data-ttu-id="7c9d5-109">Stati Uniti orientali</span><span class="sxs-lookup"><span data-stu-id="7c9d5-109">East US</span></span>
    - <span data-ttu-id="7c9d5-110">Stati Uniti occidentali</span><span class="sxs-lookup"><span data-stu-id="7c9d5-110">West US</span></span>
    - <span data-ttu-id="7c9d5-111">UE settentrionale</span><span class="sxs-lookup"><span data-stu-id="7c9d5-111">North EU</span></span>
    - <span data-ttu-id="7c9d5-112">UE occidentale</span><span class="sxs-lookup"><span data-stu-id="7c9d5-112">West EU</span></span>

- <span data-ttu-id="7c9d5-113">Devi avere accesso al tuo account Dynamics 365 Regulatory Configuration Services (RCS).</span><span class="sxs-lookup"><span data-stu-id="7c9d5-113">You must have access to your Dynamics 365 Regulatory Configuration Services (RCS) account.</span></span>
- <span data-ttu-id="7c9d5-114">Devi attivare la funzionalità di globalizzazione per il tuo account RCS in Gestione funzionalità.</span><span class="sxs-lookup"><span data-stu-id="7c9d5-114">You must activate the Globalization feature for your RCS account in Feature management.</span></span> <span data-ttu-id="7c9d5-115">Per altre informazioni, vedi [Regulatory Configuration Services (RCS) - Funzionalità di globalizzazione](rcs-globalization-feature.md).</span><span class="sxs-lookup"><span data-stu-id="7c9d5-115">For more information, see [Regulatory Configuration Services (RCS) - Globalization features](rcs-globalization-feature.md).</span></span>
- <span data-ttu-id="7c9d5-116">Devi creare un insieme di credenziali delle chiavi e un account di archiviazione in Azure.</span><span class="sxs-lookup"><span data-stu-id="7c9d5-116">You must create a key vault and a storage account in Azure.</span></span> <span data-ttu-id="7c9d5-117">Per ulteriori informazioni, vedi [Creare un account di archiviazione di Azure e Key Vault](e-invoicing-create-azure-storage-account-key-vault.md).</span><span class="sxs-lookup"><span data-stu-id="7c9d5-117">For more information, see [Create an Azure storage account and a key vault](e-invoicing-create-azure-storage-account-key-vault.md).</span></span>

## <a name="install-the-add-in-for-microservices-in-lifecycle-services"></a><span data-ttu-id="7c9d5-118">Installa il componente aggiuntivo per microservizi in Lifecycle Services</span><span class="sxs-lookup"><span data-stu-id="7c9d5-118">Install the add-in for microservices in Lifecycle Services</span></span>

1. <span data-ttu-id="7c9d5-119">Accedi al tuo account LCS.</span><span class="sxs-lookup"><span data-stu-id="7c9d5-119">Sign in to your LCS account.</span></span>
2. <span data-ttu-id="7c9d5-120">Seleziona il riquadro **Anteprima gestione funzionalità**.</span><span class="sxs-lookup"><span data-stu-id="7c9d5-120">Select the **Preview feature management** tile.</span></span>
3. <span data-ttu-id="7c9d5-121">Nella sezione **Funzionalità di anteprima pubblica** seleziona **Servizio di fatturazione elettronica**.</span><span class="sxs-lookup"><span data-stu-id="7c9d5-121">In the **Public Preview Features** section, select **e-Invoicing service**.</span></span>
4. <span data-ttu-id="7c9d5-122">Verifica che l'opzione **Funzionalità di anteprima abilitata** sia impostata su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="7c9d5-122">Make sure that the **Preview feature enabled** option is set to **Yes**.</span></span>
5. <span data-ttu-id="7c9d5-123">Nel dashboard LCS, selezionare il progetto di distribuzione LCS.</span><span class="sxs-lookup"><span data-stu-id="7c9d5-123">On your LCS dashboard, select your LCS deployment project.</span></span> <span data-ttu-id="7c9d5-124">Il progetto LCS deve essere in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="7c9d5-124">The LCS project must be running.</span></span>
7. <span data-ttu-id="7c9d5-125">Nella scheda **Componenti aggiuntivi dell'ambiente**, selezionare **Installa un nuovo componente aggiuntivo**.</span><span class="sxs-lookup"><span data-stu-id="7c9d5-125">On the **Environment add-ins** tab, select **Install a new add-in**.</span></span>
8. <span data-ttu-id="7c9d5-126">Seleziona **Servizi di fatturazione elettronica**.</span><span class="sxs-lookup"><span data-stu-id="7c9d5-126">Select **e-invoicing Services**.</span></span>
9. <span data-ttu-id="7c9d5-127">Nel campo **ID applicazione AAD** inserisci **091c98b0-a1c9-4b02-b62c-7753395ccabe**.</span><span class="sxs-lookup"><span data-stu-id="7c9d5-127">In the **AAD application ID** field, enter **091c98b0-a1c9-4b02-b62c-7753395ccabe**.</span></span> <span data-ttu-id="7c9d5-128">Questo è un valore fisso.</span><span class="sxs-lookup"><span data-stu-id="7c9d5-128">This is a fixed value.</span></span>
10. <span data-ttu-id="7c9d5-129">Nel campo **ID tenant AAD** immettere l'ID tenant dell'account di sottoscrizione di Azure.</span><span class="sxs-lookup"><span data-stu-id="7c9d5-129">In the **AAD tenant ID** field, enter the tenant ID of your Azure subscription account.</span></span>
11. <span data-ttu-id="7c9d5-130">Esaminare i termini e le condizioni e quindi selezionare la casella di controllo.</span><span class="sxs-lookup"><span data-stu-id="7c9d5-130">Review the terms and conditions, and then select the check box.</span></span>
12. <span data-ttu-id="7c9d5-131">Seleziona **Installa**.</span><span class="sxs-lookup"><span data-stu-id="7c9d5-131">Select **Install**.</span></span>


## <a name="set-up-the-parameters-for-rcs-integration-with-electronic-invoicing"></a><span data-ttu-id="7c9d5-132">Configurare i parametri per l'integrazione RCS con la fatturazione elettronica</span><span class="sxs-lookup"><span data-stu-id="7c9d5-132">Set up the parameters for RCS integration with Electronic invoicing</span></span>

1. <span data-ttu-id="7c9d5-133">Accedi al tuo account RCS.</span><span class="sxs-lookup"><span data-stu-id="7c9d5-133">Sign in to your RCS account.</span></span>
2. <span data-ttu-id="7c9d5-134">Nell'area di lavoro **Creazione di report elettronici**, nella sezione **Collegamenti correlati**, selezionare **Parametri per la creazione di report elettronici**.</span><span class="sxs-lookup"><span data-stu-id="7c9d5-134">In the **Electronic reporting** workspace, in the **Related links** section, select **Electronic reporting parameters**.</span></span>
3. <span data-ttu-id="7c9d5-135">Nella scheda **Servizio di fatturazione elettronica** nel campo **URI endpoint del servizio** immetti l'endpoint del servizio appropriato per l'area geografica di Azure, come mostrato nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="7c9d5-135">On the **e-Invoicing service** tab, in the **Service endpoint URI** field, enter the appropriate service endpoint for your Azure geography, as shown in the following table.</span></span>

    | <span data-ttu-id="7c9d5-136">Area geografica del data center di Azure</span><span class="sxs-lookup"><span data-stu-id="7c9d5-136">Datacenter Azure geography</span></span> | <span data-ttu-id="7c9d5-137">URI endpoint servizio</span><span class="sxs-lookup"><span data-stu-id="7c9d5-137">Service endpoint URI</span></span>                                                       |
    |----------------------------|----------------------------------------------------------------------------|
    | <span data-ttu-id="7c9d5-138">Stati Uniti orientali</span><span class="sxs-lookup"><span data-stu-id="7c9d5-138">East US</span></span>                    | `https://electronicinvoicing.eus-il301.gateway.prod.island.powerapps.com/` |
    | <span data-ttu-id="7c9d5-139">Stati Uniti occidentali</span><span class="sxs-lookup"><span data-stu-id="7c9d5-139">West US</span></span>                    | `https://electronicinvoicing.wus-il301.gateway.prod.island.powerapps.com/` |
    | <span data-ttu-id="7c9d5-140">UE settentrionale</span><span class="sxs-lookup"><span data-stu-id="7c9d5-140">North EU</span></span>                   | `https://electronicinvoicing.neu-il301.gateway.prod.island.powerapps.com/` |
    | <span data-ttu-id="7c9d5-141">UE occidentale</span><span class="sxs-lookup"><span data-stu-id="7c9d5-141">West EU</span></span>                    | `https://electronicinvoicing.weu-il301.gateway.prod.island.powerapps.com/` |

4. <span data-ttu-id="7c9d5-142">Verifica che il campo **ID applicazione** sia impostato su **0cdb527f-a8d1-4bf8-9436-b352c68682b2**.</span><span class="sxs-lookup"><span data-stu-id="7c9d5-142">Verify that the **Application Id** field is set to **0cdb527f-a8d1-4bf8-9436-b352c68682b2**.</span></span> <span data-ttu-id="7c9d5-143">Questo valore è un valore fisso.</span><span class="sxs-lookup"><span data-stu-id="7c9d5-143">This value is a fixed value.</span></span>
5. <span data-ttu-id="7c9d5-144">Nel campo **ID ambiente LCS** immetti l'ID del tuo ambiente LCS.</span><span class="sxs-lookup"><span data-stu-id="7c9d5-144">In the **LCS Environment Id** field, enter the ID of your LCS environment.</span></span>
6. <span data-ttu-id="7c9d5-145">Selezionare **Salva**, quindi chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="7c9d5-145">Select **Save**, and then close the page.</span></span>

## <a name="create-key-vault-references"></a><span data-ttu-id="7c9d5-146">Creare riferimenti insieme di credenziali delle chiavi</span><span class="sxs-lookup"><span data-stu-id="7c9d5-146">Create Key Vault references</span></span>

1. <span data-ttu-id="7c9d5-147">Accedi al tuo account RCS.</span><span class="sxs-lookup"><span data-stu-id="7c9d5-147">Sign in to your RCS account.</span></span>
2. <span data-ttu-id="7c9d5-148">Nell'area di lavoro **Funzionalità di globalizzazione**, nella sezione **Ambiente**, seleziona il riquadro **Fatturazione elettronica**.</span><span class="sxs-lookup"><span data-stu-id="7c9d5-148">In the **Globalization feature** workspace, in the **Environment** section, select the **Electronic invoicing** tile.</span></span>
3. <span data-ttu-id="7c9d5-149">Nella pagina **Configurazioni dell'ambiente** nel riquadro azioni seleziona **Ambiente del servizio** e quindi seleziona **Parametri Key Vault**.</span><span class="sxs-lookup"><span data-stu-id="7c9d5-149">On the **Environment setups** page, on the action Pane, select **Service environment**, and then select **Key Vault parameters**.</span></span>
4. <span data-ttu-id="7c9d5-150">Seleziona **Nuovo** per creare un riferimento dell'insieme di credenziali delle chiavi.</span><span class="sxs-lookup"><span data-stu-id="7c9d5-150">Select **New** to create a key vault reference.</span></span>
5. <span data-ttu-id="7c9d5-151">Nel campo **Nome** immetti il nome del riferimento dell'insieme di credenziali delle chiavi.</span><span class="sxs-lookup"><span data-stu-id="7c9d5-151">In the **Name** field, enter the name of the key vault reference.</span></span> <span data-ttu-id="7c9d5-152">Nel campo **Descrizione** immettere una descrizione.</span><span class="sxs-lookup"><span data-stu-id="7c9d5-152">In the **Description** field, enter a description.</span></span>
6. <span data-ttu-id="7c9d5-153">Nel campo **URI Key Vault** incolla il segreto dell'insieme di credenziali delle chiavi da Azure Key Vault.</span><span class="sxs-lookup"><span data-stu-id="7c9d5-153">In the **Key Vault URI** field, paste the key vault secret from Azure Key Vault.</span></span> <span data-ttu-id="7c9d5-154">Per ulteriori informazioni, vedi [Creare un account di archiviazione di Azure e Key Vault](e-invoicing-create-azure-storage-account-key-vault.md).</span><span class="sxs-lookup"><span data-stu-id="7c9d5-154">For more information, see [Create an Azure storage account and a key vault](e-invoicing-create-azure-storage-account-key-vault.md).</span></span>
7. <span data-ttu-id="7c9d5-155">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="7c9d5-155">Select **Save**.</span></span>

## <a name="create-storage-account-secret"></a><span data-ttu-id="7c9d5-156">Creare un segreto dell'account di archiviazione</span><span class="sxs-lookup"><span data-stu-id="7c9d5-156">Create Storage account secret</span></span>

1. <span data-ttu-id="7c9d5-157">Nella pagina **Configurazioni dell'ambiente** nel riquadro azioni seleziona **Ambiente del servizio** > **Parametri Key Vault**.</span><span class="sxs-lookup"><span data-stu-id="7c9d5-157">On the **Environment setups** page, on the Action Pane, select **Service environment** > **Key Vault parameters**.</span></span>
2. <span data-ttu-id="7c9d5-158">Seleziona un **Riferimento dell'insieme di credenziali delle chiavi** e nella sezione **Certificati** seleziona **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="7c9d5-158">Select a **Key Vault reference** and in the **Certificates** section, select **Add**.</span></span>
3. <span data-ttu-id="7c9d5-159">Nel campo **Nome** immetti il nome del segreto dell'account di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="7c9d5-159">In the **Name** field, enter the name of the storage account secret.</span></span> <span data-ttu-id="7c9d5-160">Per ulteriori informazioni, vedi [Creare un account di archiviazione di Azure e Key Vault](e-invoicing-create-azure-storage-account-key-vault.md).</span><span class="sxs-lookup"><span data-stu-id="7c9d5-160">For more information, see [Create an Azure storage account and a key vault](e-invoicing-create-azure-storage-account-key-vault.md).</span></span>
4. <span data-ttu-id="7c9d5-161">Nel campo **Descrizione** immettere una descrizione.</span><span class="sxs-lookup"><span data-stu-id="7c9d5-161">In the **Description** field, enter a description.</span></span>
5. <span data-ttu-id="7c9d5-162">Nel campo **Tipo** seleziona **Segreto**.</span><span class="sxs-lookup"><span data-stu-id="7c9d5-162">In the **Type** field, select **Secret**.</span></span>
6. <span data-ttu-id="7c9d5-163">Selezionare **Salva**, quindi chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="7c9d5-163">Select **Save**, and then close the page.</span></span>

## <a name="create-a-digital-certificate-secret"></a><span data-ttu-id="7c9d5-164">Creare un segreto del certificato digitale</span><span class="sxs-lookup"><span data-stu-id="7c9d5-164">Create a digital certificate secret</span></span>

1. <span data-ttu-id="7c9d5-165">Nella pagina **Configurazioni dell'ambiente** nel riquadro azioni seleziona **Ambiente del servizio** e quindi seleziona **Parametri Key Vault**.</span><span class="sxs-lookup"><span data-stu-id="7c9d5-165">On the **Environment setups** page, on the action Pane, select **Service environment** and then select **Key Vault parameters**.</span></span>
2. <span data-ttu-id="7c9d5-166">Seleziona un **Riferimento dell'insieme di credenziali delle chiavi** e quindi nella sezione **Certificati** seleziona **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="7c9d5-166">Select a **Key Vault reference** and then in the **Certificates** section, select **Add**.</span></span>
3. <span data-ttu-id="7c9d5-167">Nel campo **Nome** immetti il nome del segreto del certificato digitale.</span><span class="sxs-lookup"><span data-stu-id="7c9d5-167">In the **Name** field, enter the name of the digital certificate secret.</span></span> <span data-ttu-id="7c9d5-168">Per ulteriori informazioni, vedi [Creare un account di archiviazione di Azure e Key Vault](e-invoicing-create-azure-storage-account-key-vault.md).</span><span class="sxs-lookup"><span data-stu-id="7c9d5-168">For more information, see [Create an Azure storage account and a key vault](e-invoicing-create-azure-storage-account-key-vault.md).</span></span>
4. <span data-ttu-id="7c9d5-169">Nel campo **Descrizione** immettere una descrizione.</span><span class="sxs-lookup"><span data-stu-id="7c9d5-169">In the **Description** field, enter a description.</span></span>
5. <span data-ttu-id="7c9d5-170">Nel campo **Tipo** seleziona **Certificato**.</span><span class="sxs-lookup"><span data-stu-id="7c9d5-170">In the **Type** field, select **Certificate**.</span></span>
6. <span data-ttu-id="7c9d5-171">Selezionare **Salva**, quindi chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="7c9d5-171">Select **Save**, and then close the page.</span></span>

## <a name="create-a-service-environment"></a><span data-ttu-id="7c9d5-172">Creare un ambiente del servizio</span><span class="sxs-lookup"><span data-stu-id="7c9d5-172">Create a service environment</span></span>

1. <span data-ttu-id="7c9d5-173">Accedi al tuo account RCS.</span><span class="sxs-lookup"><span data-stu-id="7c9d5-173">Sign in to your RCS account.</span></span>
2. <span data-ttu-id="7c9d5-174">Nell'area di lavoro **Funzionalità di globalizzazione**, nella sezione **Ambiente**, seleziona il riquadro **Fatturazione elettronica**.</span><span class="sxs-lookup"><span data-stu-id="7c9d5-174">In the **Globalization feature** workspace, in the **Environment** section, select the **Electronic invoicing** tile.</span></span>
3. <span data-ttu-id="7c9d5-175">Nella pagina **Configurazioni dell'ambiente**, nel riquadro Azioni seleziona **Ambiente del servizio**.</span><span class="sxs-lookup"><span data-stu-id="7c9d5-175">On the **Environment setups** page, on the Action Pane, select **Service environment**.</span></span>
4. <span data-ttu-id="7c9d5-176">Seleziona **Nuovo** per creare un nuovo ambiente del servizio.</span><span class="sxs-lookup"><span data-stu-id="7c9d5-176">Select **New** to create a new service environment.</span></span>
5. <span data-ttu-id="7c9d5-177">Nel campo **Nome** immettere il nome dell'ambiente di fatturazione elettronica.</span><span class="sxs-lookup"><span data-stu-id="7c9d5-177">In the **Name** field, enter the name of the e-Invoicing environment.</span></span> <span data-ttu-id="7c9d5-178">Nel campo **Descrizione** immettere una descrizione.</span><span class="sxs-lookup"><span data-stu-id="7c9d5-178">In the **Description** field, enter a description.</span></span>
6. <span data-ttu-id="7c9d5-179">Nel campo **Segreto token SAS di archiviazione** seleziona il nome del segreto dell'account di archiviazione che deve essere utilizzato per autenticare l'accesso all'account di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="7c9d5-179">In the **Storage SAS token secret** field, select the name of the storage account secret that must be used to authenticate access to the storage account.</span></span>
7. <span data-ttu-id="7c9d5-180">Nella sezione **Utenti** seleziona **Aggiungi** per aggiungere un utente a cui è consentito inviare fatture elettroniche attraverso l'ambiente e connettersi anche all'account di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="7c9d5-180">In the **Users** section, select **Add** to add a user who is allowed to submit electronic invoices through the environment and also connect to the storage account.</span></span>
8. <span data-ttu-id="7c9d5-181">Nel campo **ID utente** immetti l'alias dell'utente.</span><span class="sxs-lookup"><span data-stu-id="7c9d5-181">In the **User ID** field, enter the alias of the user.</span></span> <span data-ttu-id="7c9d5-182">Nel campo **E-mail** immetti l'indirizzo di posta elettronica dell'utente.</span><span class="sxs-lookup"><span data-stu-id="7c9d5-182">In the **Email** field, enter the user's email address.</span></span>
9. <span data-ttu-id="7c9d5-183">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="7c9d5-183">Select **Save**.</span></span>
10. <span data-ttu-id="7c9d5-184">Se le fatture specifiche per paese/area geografica richiedono una catena di certificati per applicare una firma digitale, seleziona nel riquadro azioni **Parametri Key Vault**, quindi seleziona **Catena di certificati** e segui questi passaggi:</span><span class="sxs-lookup"><span data-stu-id="7c9d5-184">If your country/region-specific invoices require a chain of certificates to apply digital signatures, on the Action pane, select **Key Vault parameters**, then select **Chain of certificates**, and follow these steps:</span></span>
    1. <span data-ttu-id="7c9d5-185">Seleziona **Nuovo** per creare una catena di certificati.</span><span class="sxs-lookup"><span data-stu-id="7c9d5-185">Select **New** to create a chain of certificates.</span></span>
    2. <span data-ttu-id="7c9d5-186">Nel campo **Nome** immettere il nome della catena di certificati.</span><span class="sxs-lookup"><span data-stu-id="7c9d5-186">In the **Name** field, enter the name of the chain of certificate.</span></span> <span data-ttu-id="7c9d5-187">Nel campo **Descrizione** immettere una descrizione.</span><span class="sxs-lookup"><span data-stu-id="7c9d5-187">In the **Description** field, enter a description.</span></span>
    3. <span data-ttu-id="7c9d5-188">Nella sezione **Certificati** seleziona **Aggiungi** per aggiungere un certificato alla catena.</span><span class="sxs-lookup"><span data-stu-id="7c9d5-188">In the **Certificates** section, select **Add** to add a certificate to the chain.</span></span>
    4. <span data-ttu-id="7c9d5-189">Usa il pulsante **Su** o **Giù** per modificare la posizione del certificato nella catena.</span><span class="sxs-lookup"><span data-stu-id="7c9d5-189">Use the **Up** or **Down** button to change the position of the certificate in the chain.</span></span>
    5. <span data-ttu-id="7c9d5-190">Selezionare **Salva**, quindi chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="7c9d5-190">Select **Save**, and then close the page.</span></span>
    6. <span data-ttu-id="7c9d5-191">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="7c9d5-191">Close the page.</span></span>
11. <span data-ttu-id="7c9d5-192">Nella pagina **Ambiente del servizio** nel riquadro azioni, seleziona **Pubblica** per pubblicare l'ambiente nel cloud.</span><span class="sxs-lookup"><span data-stu-id="7c9d5-192">On **Service environment** page, on the Action Pane, select **Publish** to publish the environment to the cloud.</span></span> <span data-ttu-id="7c9d5-193">Il valore del campo **Stato** viene modificato in **Pubblicato**.</span><span class="sxs-lookup"><span data-stu-id="7c9d5-193">The value of the **Status** field is changed to **Published**.</span></span>

## <a name="create-a-connected-application"></a><span data-ttu-id="7c9d5-194">Creare un'applicazione connessa</span><span class="sxs-lookup"><span data-stu-id="7c9d5-194">Create a connected application</span></span>

1. <span data-ttu-id="7c9d5-195">Nella pagina **Configurazioni dell'ambiente**, nel riquadro azioni seleziona **Applicazioni connesse**.</span><span class="sxs-lookup"><span data-stu-id="7c9d5-195">On the **Environment setups** page, on the action Pane, select **Connected applications**.</span></span>
2. <span data-ttu-id="7c9d5-196">Seleziona **Nuovo** per creare un'applicazione connessa.</span><span class="sxs-lookup"><span data-stu-id="7c9d5-196">Select **New** to create a connected application.</span></span>
3. <span data-ttu-id="7c9d5-197">Nel campo **Nome** immettere il nome dell'applicazione da connettere.</span><span class="sxs-lookup"><span data-stu-id="7c9d5-197">In the **Name** field, enter the name of the application to connect.</span></span>
4. <span data-ttu-id="7c9d5-198">Nel campo **Applicazione** immetti l'URL dell'ambiente Finance e Supply Chain Management da connettere.</span><span class="sxs-lookup"><span data-stu-id="7c9d5-198">In the **Application** field, enter the URL of the Finance and Supply Chain Management environment to connect.</span></span>
4. <span data-ttu-id="7c9d5-199">Nel campo **Tenant** immetti il tenant dell'ambiente Finance e Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="7c9d5-199">In the **Tenant** field, enter the tenant of the Finance and Supply Chain Management environment.</span></span>
5. <span data-ttu-id="7c9d5-200">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="7c9d5-200">Select **Save**.</span></span>
6. <span data-ttu-id="7c9d5-201">Nel riquadro azioni seleziona **Verificare connessione** per testare la connessione con l'ambiente.</span><span class="sxs-lookup"><span data-stu-id="7c9d5-201">On the Action Pane, select **Check connection** to test the connection with the environment.</span></span> <span data-ttu-id="7c9d5-202">Quindi, chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="7c9d5-202">Then close the page.</span></span>

## <a name="link-connected-applications-to-environments"></a><span data-ttu-id="7c9d5-203">Collegare le applicazioni connesse agli ambienti</span><span class="sxs-lookup"><span data-stu-id="7c9d5-203">Link connected applications to environments</span></span>

1. <span data-ttu-id="7c9d5-204">Nella pagina **Configurazioni ambiente** seleziona **Nuovo** per assegnare un'applicazione connessa a un ambiente.</span><span class="sxs-lookup"><span data-stu-id="7c9d5-204">On the **Environment setups** page, select **New** to assign a connected application to an environment.</span></span>
2. <span data-ttu-id="7c9d5-205">Nel campo **Applicazione connessa** seleziona un'applicazione connessa.</span><span class="sxs-lookup"><span data-stu-id="7c9d5-205">In the **Connected application** field, select a connected application.</span></span>
3. <span data-ttu-id="7c9d5-206">Nel campo **Ambiente del servizio**, seleziona un ambiente del servizio.</span><span class="sxs-lookup"><span data-stu-id="7c9d5-206">In the **Service environment** field, select a service environment.</span></span>
4. <span data-ttu-id="7c9d5-207">Selezionare **Salva**, quindi chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="7c9d5-207">Select **Save**, and then close the page.</span></span>

## <a name="set-up-electronic-invoicing-integration-in-finance-and-supply-chain-management"></a><span data-ttu-id="7c9d5-208">Configurare l'integrazione della fatturazione elettronica in Finance o Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="7c9d5-208">Set up Electronic invoicing integration in Finance and Supply Chain Management</span></span>

### <a name="turn-on-the-electronic-invoicing-integration-feature"></a><span data-ttu-id="7c9d5-209">Attivare la funzionalità di integrazione della fatturazione elettronica</span><span class="sxs-lookup"><span data-stu-id="7c9d5-209">Turn on the Electronic invoicing integration feature</span></span>

1. <span data-ttu-id="7c9d5-210">Accedi alla tua istanza Finance o Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="7c9d5-210">Sign in to your Finance or Supply Chain Management instance.</span></span>
2. <span data-ttu-id="7c9d5-211">Nell'area di lavoro **Gestione funzionalità**, cerca la funzionalità **Integrazione della fatturazione elettronica**.</span><span class="sxs-lookup"><span data-stu-id="7c9d5-211">In the **Feature management** workspace, search for the **Electronic invoicing integration** feature.</span></span> <span data-ttu-id="7c9d5-212">Se questa funzionalità non viene visualizzata nella pagina, seleziona **Controlla aggiornamenti**.</span><span class="sxs-lookup"><span data-stu-id="7c9d5-212">If this feature doesn't appear on the page, select **Check for updates**.</span></span>
3. <span data-ttu-id="7c9d5-213">Seleziona la funzionalità, quindi seleziona **Abilita ora**.</span><span class="sxs-lookup"><span data-stu-id="7c9d5-213">Select the feature, and then select **Enable now**.</span></span>

### <a name="set-up-the-service-endpoint-url"></a><span data-ttu-id="7c9d5-214">Configurare l'URL dell'endpoint di servizio</span><span class="sxs-lookup"><span data-stu-id="7c9d5-214">Set up the service endpoint URL</span></span>

1. <span data-ttu-id="7c9d5-215">Vai a **Amministrazione organizzazione \> Impostazione \> Parametri documento elettronico**.</span><span class="sxs-lookup"><span data-stu-id="7c9d5-215">Go to **Organization administration \> Setup \> Electronic document parameters**.</span></span>
2. <span data-ttu-id="7c9d5-216">Nella scheda **Servizio di invio** nel campo **URL endpoint del servizio** immetti l'endpoint del servizio appropriato per l'area geografica di Azure, come mostrato nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="7c9d5-216">On the **Submission service** tab, in the **Service endpoint URL** field, enter the appropriate service endpoint for your Azure geography, as shown in the following table.</span></span>

    | <span data-ttu-id="7c9d5-217">Area geografica del data center di Azure</span><span class="sxs-lookup"><span data-stu-id="7c9d5-217">Datacenter Azure geography</span></span> | <span data-ttu-id="7c9d5-218">URL endpoint servizio</span><span class="sxs-lookup"><span data-stu-id="7c9d5-218">Service endpoint URL</span></span>                                                       |
    |----------------------------|----------------------------------------------------------------------------|
    | <span data-ttu-id="7c9d5-219">Stati Uniti orientali</span><span class="sxs-lookup"><span data-stu-id="7c9d5-219">East US</span></span>                    | `https://electronicinvoicing.eus-il301.gateway.prod.island.powerapps.com/` |
    | <span data-ttu-id="7c9d5-220">Stati Uniti occidentali</span><span class="sxs-lookup"><span data-stu-id="7c9d5-220">West US</span></span>                    | `https://electronicinvoicing.wus-il301.gateway.prod.island.powerapps.com/` |
    | <span data-ttu-id="7c9d5-221">UE settentrionale</span><span class="sxs-lookup"><span data-stu-id="7c9d5-221">North EU</span></span>                   | `https://electronicinvoicing.neu-il301.gateway.prod.island.powerapps.com/` |
    | <span data-ttu-id="7c9d5-222">UE occidentale</span><span class="sxs-lookup"><span data-stu-id="7c9d5-222">West EU</span></span>                    | `https://electronicinvoicing.weu-il301.gateway.prod.island.powerapps.com/` |

3. <span data-ttu-id="7c9d5-223">Nel campo **Ambiente** immetti il nome dell'ambiente del servizio pubblicato in Fatturazione elettronica.</span><span class="sxs-lookup"><span data-stu-id="7c9d5-223">In the **Environment** field, enter the name of the service environment published in Electronic invoicing.</span></span>
4. <span data-ttu-id="7c9d5-224">Selezionare **Salva**, quindi chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="7c9d5-224">Select **Save**, and then close the page.</span></span>

### <a name="enable-flighting-keys"></a><span data-ttu-id="7c9d5-225">Abilitare le chiavi della versione di anteprima</span><span class="sxs-lookup"><span data-stu-id="7c9d5-225">Enable Flighting keys</span></span>

<span data-ttu-id="7c9d5-226">Abilita le chiavi della versione di anteprima per Microsoft Dynamics 365 Finance o Microsoft Dynamics 365 Supply Chain Management versioni 10.0.17 o precedenti.</span><span class="sxs-lookup"><span data-stu-id="7c9d5-226">Enable Flight keys for  Microsoft Dynamics 365 Finance or  Microsoft Dynamics 365 Supply Chain Management versions 10.0.17 or earlier.</span></span> 
1. <span data-ttu-id="7c9d5-227">Eseguire il seguente comando SQL:</span><span class="sxs-lookup"><span data-stu-id="7c9d5-227">Execute the following SQL command:</span></span>

    <span data-ttu-id="7c9d5-228">INSERT INTO SYSFLIGHTING (FLIGHTNAME, ENABLED) VALUES ('BusinessDocumentSubmissionServiceEnabled', 1)</span><span class="sxs-lookup"><span data-stu-id="7c9d5-228">INSERT INTO SYSFLIGHTING (FLIGHTNAME, ENABLED) VALUES ('BusinessDocumentSubmissionServiceEnabled', 1)</span></span>
    
    <span data-ttu-id="7c9d5-229">INSERT INTO SYSFLIGHTING (FLIGHTNAME, ENABLED) VALUES ('ElectronicInvoicingServiceIntegrationFeature', 1)</span><span class="sxs-lookup"><span data-stu-id="7c9d5-229">INSERT INTO SYSFLIGHTING (FLIGHTNAME, ENABLED) VALUES ('ElectronicInvoicingServiceIntegrationFeature', 1)</span></span>

2. <span data-ttu-id="7c9d5-230">Esegui un comando IISreset per tutti gli AOS.</span><span class="sxs-lookup"><span data-stu-id="7c9d5-230">Perform an IISreset command for all AOS's.</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
