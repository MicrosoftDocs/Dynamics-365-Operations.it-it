---
title: Introduzione all'amministrazione del servizio del componente aggiuntivo per la fatturazione elettronica
description: Questo argomento spiega come iniziare a usare il componente aggiuntivo per la fatturazione elettronica.
author: gionoder
manager: AnnBe
ms.date: 01/28/2021
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
ms.openlocfilehash: 111ec65aa826795125d4a9ce835f72e1a0f41b7b
ms.sourcegitcommit: e88c96d1cb817a22db81856cadb563c095ab2671
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/02/2021
ms.locfileid: "5104398"
---
# <a name="get-started-with-electronic-invoicing-add-on-service-administration"></a><span data-ttu-id="8b770-103">Introduzione all'amministrazione del servizio del componente aggiuntivo per la fatturazione elettronica</span><span class="sxs-lookup"><span data-stu-id="8b770-103">Get started with Electronic invoicing add-on service administration</span></span>

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

## <a name="prerequisites"></a><span data-ttu-id="8b770-104">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="8b770-104">Prerequisites</span></span>

<span data-ttu-id="8b770-105">Prima di poter completare le procedure in questo argomento, è necessario soddisfare i seguenti prerequisiti:</span><span class="sxs-lookup"><span data-stu-id="8b770-105">Before you complete the procedures in this topic, the following prerequisites must be in place:</span></span>

- <span data-ttu-id="8b770-106">Devi avere accesso al tuo account Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="8b770-106">You must have access to your Microsoft Dynamics Lifecycle Services (LCS) account.</span></span>
- <span data-ttu-id="8b770-107">Devi disporre di un progetto LCS che includa la versione 10.0.13 o successiva di Microsoft Dynamics 365 Finance e Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="8b770-107">You must have an LCS project that includes version 10.0.13 or later of Microsoft Dynamics 365 Finance and Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="8b770-108">Inoltre, queste app devono essere distribuite in una delle seguenti aree geografiche di Azure:</span><span class="sxs-lookup"><span data-stu-id="8b770-108">Additionally, these apps must be deployed in one of the following Azure geographies:</span></span>

    - <span data-ttu-id="8b770-109">Stati Uniti orientali</span><span class="sxs-lookup"><span data-stu-id="8b770-109">East US</span></span>
    - <span data-ttu-id="8b770-110">Stati Uniti occidentali</span><span class="sxs-lookup"><span data-stu-id="8b770-110">West US</span></span>
    - <span data-ttu-id="8b770-111">UE settentrionale</span><span class="sxs-lookup"><span data-stu-id="8b770-111">North EU</span></span>
    - <span data-ttu-id="8b770-112">UE occidentale</span><span class="sxs-lookup"><span data-stu-id="8b770-112">West EU</span></span>

- <span data-ttu-id="8b770-113">Devi avere accesso al tuo account Dynamics 365 Regulatory Configuration Services (RCS).</span><span class="sxs-lookup"><span data-stu-id="8b770-113">You must have access to your Dynamics 365 Regulatory Configuration Services (RCS) account.</span></span>
- <span data-ttu-id="8b770-114">Devi attivare la funzionalità di globalizzazione per il tuo account RCS in Gestione funzionalità.</span><span class="sxs-lookup"><span data-stu-id="8b770-114">You must activate the Globalization feature for your RCS account in Feature management.</span></span> <span data-ttu-id="8b770-115">Per altre informazioni, vedi [Regulatory Configuration Services (RCS) - Funzionalità di globalizzazione](rcs-globalization-feature.md).</span><span class="sxs-lookup"><span data-stu-id="8b770-115">For more information, see [Regulatory Configuration Services (RCS) - Globalization features](rcs-globalization-feature.md).</span></span>
- <span data-ttu-id="8b770-116">Devi creare un insieme di credenziali delle chiavi e un account di archiviazione in Azure.</span><span class="sxs-lookup"><span data-stu-id="8b770-116">You must create a key vault and a storage account in Azure.</span></span> <span data-ttu-id="8b770-117">Per ulteriori informazioni, vedi [Creare un account di archiviazione di Azure e Key Vault](e-invoicing-create-azure-storage-account-key-vault.md).</span><span class="sxs-lookup"><span data-stu-id="8b770-117">For more information, see [Create an Azure storage account and a key vault](e-invoicing-create-azure-storage-account-key-vault.md).</span></span>

## <a name="install-the-add-on-for-microservices-in-lifecycle-services"></a><span data-ttu-id="8b770-118">Installa il componente aggiuntivo per microservizi in Lifecycle Services</span><span class="sxs-lookup"><span data-stu-id="8b770-118">Install the add-on for microservices in Lifecycle Services</span></span>

1. <span data-ttu-id="8b770-119">Accedi al tuo account LCS.</span><span class="sxs-lookup"><span data-stu-id="8b770-119">Sign in to your LCS account.</span></span>
2. <span data-ttu-id="8b770-120">Seleziona il riquadro **Anteprima gestione funzionalità**.</span><span class="sxs-lookup"><span data-stu-id="8b770-120">Select the **Preview feature management** tile.</span></span>
3. <span data-ttu-id="8b770-121">Nella sezione **Funzionalità di anteprima pubblica** seleziona **Servizio di fatturazione elettronica**.</span><span class="sxs-lookup"><span data-stu-id="8b770-121">In the **Public Preview Features** section, select **e-Invoicing service**.</span></span>
4. <span data-ttu-id="8b770-122">Verifica che l'opzione **Funzionalità di anteprima abilitata** sia impostata su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="8b770-122">Make sure that the **Preview feature enabled** option is set to **Yes**.</span></span>

## <a name="set-up-the-parameters-for-rcs-integration-with-the-electronic-invoicing-add-on"></a><span data-ttu-id="8b770-123">Configurare i parametri per l'integrazione RCS con il componente aggiuntivo per la fatturazione elettronica</span><span class="sxs-lookup"><span data-stu-id="8b770-123">Set up the parameters for RCS integration with the Electronic invoicing add-on</span></span>

1. <span data-ttu-id="8b770-124">Accedi al tuo account RCS.</span><span class="sxs-lookup"><span data-stu-id="8b770-124">Sign in to your RCS account.</span></span>
2. <span data-ttu-id="8b770-125">Nell'area di lavoro **Creazione di report elettronici**, nella sezione **Collegamenti correlati**, selezionare **Parametri per la creazione di report elettronici**.</span><span class="sxs-lookup"><span data-stu-id="8b770-125">In the **Electronic reporting** workspace, in the **Related links** section, select **Electronic reporting parameters**.</span></span>
3. <span data-ttu-id="8b770-126">Nella scheda **Servizio di fatturazione elettronica** nel campo **URI endpoint del servizio** immetti l'endpoint del servizio appropriato per l'area geografica di Azure, come mostrato nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="8b770-126">On the **e-Invoicing service** tab, in the **Service endpoint URI** field, enter the appropriate service endpoint for your Azure geography, as shown in the following table.</span></span>

    | <span data-ttu-id="8b770-127">Area geografica del data center di Azure</span><span class="sxs-lookup"><span data-stu-id="8b770-127">Datacenter Azure geography</span></span> | <span data-ttu-id="8b770-128">URI endpoint servizio</span><span class="sxs-lookup"><span data-stu-id="8b770-128">Service endpoint URI</span></span>                                                       |
    |----------------------------|----------------------------------------------------------------------------|
    | <span data-ttu-id="8b770-129">Stati Uniti orientali</span><span class="sxs-lookup"><span data-stu-id="8b770-129">East US</span></span>                    | `https://electronicinvoicing.eus-il301.gateway.prod.island.powerapps.com/` |
    | <span data-ttu-id="8b770-130">Stati Uniti occidentali</span><span class="sxs-lookup"><span data-stu-id="8b770-130">West US</span></span>                    | `https://electronicinvoicing.wus-il301.gateway.prod.island.powerapps.com/` |
    | <span data-ttu-id="8b770-131">UE settentrionale</span><span class="sxs-lookup"><span data-stu-id="8b770-131">North EU</span></span>                   | `https://electronicinvoicing.neu-il301.gateway.prod.island.powerapps.com/` |
    | <span data-ttu-id="8b770-132">UE occidentale</span><span class="sxs-lookup"><span data-stu-id="8b770-132">West EU</span></span>                    | `https://electronicinvoicing.weu-il301.gateway.prod.island.powerapps.com/` |

4. <span data-ttu-id="8b770-133">Verifica che il campo **ID applicazione** sia impostato su **0cdb527f-a8d1-4bf8-9436-b352c68682b2**.</span><span class="sxs-lookup"><span data-stu-id="8b770-133">Verify that the **Application Id** field is set to **0cdb527f-a8d1-4bf8-9436-b352c68682b2**.</span></span> <span data-ttu-id="8b770-134">Questo valore è un valore fisso.</span><span class="sxs-lookup"><span data-stu-id="8b770-134">This value is a fixed value.</span></span>
5. <span data-ttu-id="8b770-135">Nel campo **ID ambiente LCS** immetti l'ID del tuo account di sottoscrizione LCS.</span><span class="sxs-lookup"><span data-stu-id="8b770-135">In the **LCS Environment Id** field, enter the ID of your LCS subscription account.</span></span>
6. <span data-ttu-id="8b770-136">Selezionare **Salva**, quindi chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="8b770-136">Select **Save**, and then close the page.</span></span>

## <a name="create-key-vault-secret"></a><span data-ttu-id="8b770-137">Creare il segreto Key Vault</span><span class="sxs-lookup"><span data-stu-id="8b770-137">Create Key Vault secret</span></span>

1. <span data-ttu-id="8b770-138">Accedi al tuo account RCS.</span><span class="sxs-lookup"><span data-stu-id="8b770-138">Sign in to your RCS account.</span></span>
2. <span data-ttu-id="8b770-139">Nell'area di lavoro **Funzionalità di globalizzazione**, nella sezione **Ambiente**, seleziona il riquadro **Fatturazione elettronica**.</span><span class="sxs-lookup"><span data-stu-id="8b770-139">In the **Globalization feature** workspace, in the **Environment** section, select the **e-Invoicing** tile.</span></span>
3. <span data-ttu-id="8b770-140">Nella pagina **Configurazioni dell'ambiente** nel riquadro azioni seleziona **Ambiente del servizio** e quindi seleziona **Parametri Key Vault**.</span><span class="sxs-lookup"><span data-stu-id="8b770-140">On the **Environment setups** page, on the action Pane, select **Service environment**, and then select **Key Vault parameters**.</span></span>
4. <span data-ttu-id="8b770-141">Seleziona **Nuovo** per creare un segreto dell'insieme di credenziali delle chiavi.</span><span class="sxs-lookup"><span data-stu-id="8b770-141">Select **New** to create a key vault secret.</span></span>
5. <span data-ttu-id="8b770-142">Nel campo **Nome** immettere il nome del segreto dell'insieme di credenziali delle chiavi.</span><span class="sxs-lookup"><span data-stu-id="8b770-142">In the **Name** field, enter the name of the key vault secret.</span></span> <span data-ttu-id="8b770-143">Nel campo **Descrizione** immettere una descrizione.</span><span class="sxs-lookup"><span data-stu-id="8b770-143">In the **Description** field, enter a description.</span></span>
6. <span data-ttu-id="8b770-144">Nel campo **URI Key Vault** incolla il segreto da Azure Key Vault.</span><span class="sxs-lookup"><span data-stu-id="8b770-144">In the **Key Vault URI** field, paste the secret from Azure Key Vault.</span></span>
7. <span data-ttu-id="8b770-145">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="8b770-145">Select **Save**.</span></span>

## <a name="create-storage-account-secret"></a><span data-ttu-id="8b770-146">Creare un segreto dell'account di archiviazione</span><span class="sxs-lookup"><span data-stu-id="8b770-146">Create Storage account secret</span></span>

1. <span data-ttu-id="8b770-147">Nella pagina **Parametri insieme di credenziali delle chiavi** nella sezione **Certificati** seleziona **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="8b770-147">On **Key vault parameters** page, in the **Certificates** section, select **Add**.</span></span>
2. <span data-ttu-id="8b770-148">Nel campo **Nome** immettere lo stesso nome del segreto dell'account di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="8b770-148">In the **Name** field, enter the same of the storage account secret.</span></span> <span data-ttu-id="8b770-149">Nel campo **Descrizione** immettere una descrizione.</span><span class="sxs-lookup"><span data-stu-id="8b770-149">In the **Description** field, enter a description.</span></span>
3. <span data-ttu-id="8b770-150">Nel campo **Tipo** seleziona **Certificato**.</span><span class="sxs-lookup"><span data-stu-id="8b770-150">In the **Type** field, select **Certificate**.</span></span>
4. <span data-ttu-id="8b770-151">Selezionare **Salva**, quindi chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="8b770-151">Select **Save**, and then close the page.</span></span>

## <a name="create-an-electronic-invoicing-add-on-environment"></a><span data-ttu-id="8b770-152">Creare un ambiente del componente aggiuntivo per la fatturazione elettronica</span><span class="sxs-lookup"><span data-stu-id="8b770-152">Create an Electronic invoicing add-on environment</span></span>

1. <span data-ttu-id="8b770-153">Accedi al tuo account RCS.</span><span class="sxs-lookup"><span data-stu-id="8b770-153">Sign in to your RCS account.</span></span>
2. <span data-ttu-id="8b770-154">Nell'area di lavoro **Funzionalità di globalizzazione**, nella sezione **Ambiente**, seleziona il riquadro **Fatturazione elettronica**.</span><span class="sxs-lookup"><span data-stu-id="8b770-154">In the **Globalization feature** workspace, in the **Environment** section, select the **e-Invoicing** tile.</span></span>

## <a name="create-a-service-environment"></a><span data-ttu-id="8b770-155">Creare un ambiente del servizio</span><span class="sxs-lookup"><span data-stu-id="8b770-155">Create a service environment</span></span>

1. <span data-ttu-id="8b770-156">Nella pagina **Configurazioni dell'ambiente**, nel riquadro azioni seleziona **Ambiente del servizio**.</span><span class="sxs-lookup"><span data-stu-id="8b770-156">On the **Environment setups** page, on the action Pane, select **Service environment**.</span></span>
2. <span data-ttu-id="8b770-157">Seleziona **Nuovo** per creare un nuovo ambiente del servizio.</span><span class="sxs-lookup"><span data-stu-id="8b770-157">Select **New** to create a new service environment.</span></span>
3. <span data-ttu-id="8b770-158">Nel campo **Nome** immettere il nome dell'ambiente di fatturazione elettronica.</span><span class="sxs-lookup"><span data-stu-id="8b770-158">In the **Name** field, enter the name of the e-Invoicing environment.</span></span> <span data-ttu-id="8b770-159">Nel campo **Descrizione** immettere una descrizione.</span><span class="sxs-lookup"><span data-stu-id="8b770-159">In the **Description** field, enter a description.</span></span>
4. <span data-ttu-id="8b770-160">Nel campo **Segreto token SAS di archiviazione** seleziona il nome del certificato che deve essere utilizzato per autenticare l'accesso all'account di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="8b770-160">In the **Storage SAS token secret** field, select the name of the certificate that must be used to authenticate access to the storage account.</span></span>
5. <span data-ttu-id="8b770-161">Nella sezione **Utenti** seleziona **Aggiungi** per aggiungere un utente a cui è consentito inviare fatture elettroniche attraverso l'ambiente e connettersi anche all'account di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="8b770-161">In the **Users** section, select **Add** to add a user who is allowed to submit electronic invoices through the environment and also connect to the storage account.</span></span>
6. <span data-ttu-id="8b770-162">Nel campo **ID utente** immetti l'alias dell'utente.</span><span class="sxs-lookup"><span data-stu-id="8b770-162">In the **User ID** field, enter the alias of the user.</span></span> <span data-ttu-id="8b770-163">Nel campo **E-mail** immetti l'indirizzo di posta elettronica dell'utente.</span><span class="sxs-lookup"><span data-stu-id="8b770-163">In the **Email** field, enter the user's email address.</span></span>
7. <span data-ttu-id="8b770-164">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="8b770-164">Select **Save**.</span></span>
8. <span data-ttu-id="8b770-165">Se le fatture specifiche per paese/area geografica richiedono una catena di certificati per applicare una firma digitale, seleziona nel riquadro azioni **Parametri Key Vault**, quindi seleziona **Catena di certificati** e segui questi passaggi:</span><span class="sxs-lookup"><span data-stu-id="8b770-165">If your country/region-specific invoices require a chain of certificates to apply digital signatures, on the Action pane, select **Key Vault parameters**, then select **Chain of certificates**, and follow these steps:</span></span>

    1. <span data-ttu-id="8b770-166">Seleziona **Nuovo** per creare una catena di certificati.</span><span class="sxs-lookup"><span data-stu-id="8b770-166">Select **New** to create a chain of certificates.</span></span>
    2. <span data-ttu-id="8b770-167">Nel campo **Nome** immettere il nome della catena di certificati.</span><span class="sxs-lookup"><span data-stu-id="8b770-167">In the **Name** field, enter the name of the chain of certificate.</span></span> <span data-ttu-id="8b770-168">Nel campo **Descrizione** immettere una descrizione.</span><span class="sxs-lookup"><span data-stu-id="8b770-168">In the **Description** field, enter a description.</span></span>
    3. <span data-ttu-id="8b770-169">Nella sezione **Certificati** seleziona **Aggiungi** per aggiungere un certificato alla catena.</span><span class="sxs-lookup"><span data-stu-id="8b770-169">In the **Certificates** section, select **Add** to add a certificate to the chain.</span></span>
    4. <span data-ttu-id="8b770-170">Usa il pulsante **Su** o **Giù** per modificare la posizione del certificato nella catena.</span><span class="sxs-lookup"><span data-stu-id="8b770-170">Use the **Up** or **Down** button to change the position of the certificate in the chain.</span></span>
    5. <span data-ttu-id="8b770-171">Selezionare **Salva**, quindi chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="8b770-171">Select **Save**, and then close the page.</span></span>
    6. <span data-ttu-id="8b770-172">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="8b770-172">Close the page.</span></span>
9. <span data-ttu-id="8b770-173">Nella pagina **Ambiente del servizio** nel riquadro azioni, seleziona **Pubblica** per pubblicare l'ambiente nel cloud.</span><span class="sxs-lookup"><span data-stu-id="8b770-173">On **Service environment** page, on the Action Pane, select **Publish** to publish the environment to the cloud.</span></span> <span data-ttu-id="8b770-174">Il valore del campo **Stato** viene modificato in **Pubblicato**.</span><span class="sxs-lookup"><span data-stu-id="8b770-174">The value of the **Status** field is changed to **Published**.</span></span>

## <a name="create-a-connected-application"></a><span data-ttu-id="8b770-175">Creare un'applicazione connessa</span><span class="sxs-lookup"><span data-stu-id="8b770-175">Create a connected application</span></span>

1. <span data-ttu-id="8b770-176">Nella pagina **Configurazioni dell'ambiente**, nel riquadro azioni seleziona **Applicazioni connesse**.</span><span class="sxs-lookup"><span data-stu-id="8b770-176">On the **Environment setups** page, on the action Pane, select **Connected applications**.</span></span>
2. <span data-ttu-id="8b770-177">Seleziona **Nuovo** per creare un'applicazione connessa.</span><span class="sxs-lookup"><span data-stu-id="8b770-177">Select **New** to create a connected application.</span></span>
3. <span data-ttu-id="8b770-178">Nel campo **Nome** immettere il nome dell'applicazione da connettere.</span><span class="sxs-lookup"><span data-stu-id="8b770-178">In the **Name** field, enter the name of the application to connect.</span></span>
4. <span data-ttu-id="8b770-179">Nel campo **Applicazione** immetti l'URL dell'ambiente Finance e Supply Chain Management da connettere.</span><span class="sxs-lookup"><span data-stu-id="8b770-179">In the **Application** field, enter the URL of the Finance and Supply Chain Management environment to connect.</span></span>
4. <span data-ttu-id="8b770-180">Nel campo **Tenant** immetti il tenant dell'ambiente Finance e Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="8b770-180">In the **Tenant** field, enter the tenant of the Finance and Supply Chain Management environment.</span></span>
5. <span data-ttu-id="8b770-181">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="8b770-181">Select **Save**.</span></span>
6. <span data-ttu-id="8b770-182">Nel riquadro azioni seleziona **Verificare connessione** per testare la connessione con l'ambiente.</span><span class="sxs-lookup"><span data-stu-id="8b770-182">On the Action Pane, select **Check connection** to test the connection with the environment.</span></span> <span data-ttu-id="8b770-183">Quindi, chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="8b770-183">Then close the page.</span></span>

## <a name="link-connected-applications-to-environments"></a><span data-ttu-id="8b770-184">Collegare le applicazioni connesse agli ambienti</span><span class="sxs-lookup"><span data-stu-id="8b770-184">Link connected applications to environments</span></span>

1. <span data-ttu-id="8b770-185">Nella pagina **Configurazioni ambiente** seleziona **Nuovo** per assegnare un'applicazione connessa a un ambiente.</span><span class="sxs-lookup"><span data-stu-id="8b770-185">On the **Environment setups** page, select **New** to assign a connected application to an environment.</span></span>
2. <span data-ttu-id="8b770-186">Nel campo **Applicazione connessa** seleziona un'applicazione connessa.</span><span class="sxs-lookup"><span data-stu-id="8b770-186">In the **Connected application** field, select a connected application.</span></span>
3. <span data-ttu-id="8b770-187">Nel campo **Ambiente del servizio**, seleziona un ambiente del servizio.</span><span class="sxs-lookup"><span data-stu-id="8b770-187">In the **Service environment** field, select a service environment.</span></span>
4. <span data-ttu-id="8b770-188">Selezionare **Salva**, quindi chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="8b770-188">Select **Save**, and then close the page.</span></span>

## <a name="set-up-the-electronic-invoicing-add-on-integration-in-finance-and-supply-chain-management"></a><span data-ttu-id="8b770-189">Configurare l'integrazione del componente aggiuntivo per la fatturazione elettronica in Finance e Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="8b770-189">Set up the Electronic invoicing add-on integration in Finance and Supply Chain Management</span></span>

### <a name="turn-on-the-electronic-invoicing-add-on-integration-feature"></a><span data-ttu-id="8b770-190">Attivare la funzionalità di integrazione del componente aggiuntivo per la fatturazione elettronica</span><span class="sxs-lookup"><span data-stu-id="8b770-190">Turn on the Electronic invoicing add-on integration feature</span></span>

1. <span data-ttu-id="8b770-191">Accedi alla tua istanza Finance o Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="8b770-191">Sign in to your Finance or Supply Chain Management instance.</span></span>
2. <span data-ttu-id="8b770-192">Nell'area di lavoro **Gestione funzionalità**, cerca la funzionalità **Integrazione del componente aggiuntivo per la fatturazione elettronica**.</span><span class="sxs-lookup"><span data-stu-id="8b770-192">In the **Feature management** workspace, search for the **Electronic invoicing add-on integration** feature.</span></span> <span data-ttu-id="8b770-193">Se questa funzionalità non viene visualizzata nella pagina, seleziona **Controlla aggiornamenti**.</span><span class="sxs-lookup"><span data-stu-id="8b770-193">If this feature doesn't appear on the page, select **Check for updates**.</span></span>
3. <span data-ttu-id="8b770-194">Seleziona la funzionalità, quindi seleziona **Abilita ora**.</span><span class="sxs-lookup"><span data-stu-id="8b770-194">Select the feature, and then select **Enable now**.</span></span>

### <a name="set-up-the-service-endpoint-url"></a><span data-ttu-id="8b770-195">Configurare l'URL dell'endpoint di servizio</span><span class="sxs-lookup"><span data-stu-id="8b770-195">Set up the service endpoint URL</span></span>

1. <span data-ttu-id="8b770-196">Vai a **Amministrazione organizzazione \> Impostazione \> Parametri documento elettronico**.</span><span class="sxs-lookup"><span data-stu-id="8b770-196">Go to **Organization administration \> Setup \> Electronic document parameters**.</span></span>
2. <span data-ttu-id="8b770-197">Nella scheda **Servizio di invio** nel campo **URL endpoint del servizio** immetti l'endpoint del servizio appropriato per l'area geografica di Azure, come mostrato nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="8b770-197">On the **Submission service** tab, in the **Service endpoint URL** field, enter the appropriate service endpoint for your Azure geography, as shown in the following table.</span></span>

    | <span data-ttu-id="8b770-198">Area geografica del data center di Azure</span><span class="sxs-lookup"><span data-stu-id="8b770-198">Datacenter Azure geography</span></span> | <span data-ttu-id="8b770-199">URL endpoint servizio</span><span class="sxs-lookup"><span data-stu-id="8b770-199">Service endpoint URL</span></span>                                                       |
    |----------------------------|----------------------------------------------------------------------------|
    | <span data-ttu-id="8b770-200">Stati Uniti orientali</span><span class="sxs-lookup"><span data-stu-id="8b770-200">East US</span></span>                    | `https://electronicinvoicing.eus-il301.gateway.prod.island.powerapps.com/` |
    | <span data-ttu-id="8b770-201">Stati Uniti occidentali</span><span class="sxs-lookup"><span data-stu-id="8b770-201">West US</span></span>                    | `https://electronicinvoicing.wus-il301.gateway.prod.island.powerapps.com/` |
    | <span data-ttu-id="8b770-202">UE settentrionale</span><span class="sxs-lookup"><span data-stu-id="8b770-202">North EU</span></span>                   | `https://electronicinvoicing.neu-il301.gateway.prod.island.powerapps.com/` |
    | <span data-ttu-id="8b770-203">UE occidentale</span><span class="sxs-lookup"><span data-stu-id="8b770-203">West EU</span></span>                    | `https://electronicinvoicing.weu-il301.gateway.prod.island.powerapps.com/` |

3. <span data-ttu-id="8b770-204">Nel campo **Ambiente** immettere il nome dell'ambiente del componente aggiuntivo Fatturazione elettronica.</span><span class="sxs-lookup"><span data-stu-id="8b770-204">In the **Environment** field, enter the name of the Electronic invoicing add-on environment.</span></span>
4. <span data-ttu-id="8b770-205">Selezionare **Salva**, quindi chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="8b770-205">Select **Save**, and then close the page.</span></span>
