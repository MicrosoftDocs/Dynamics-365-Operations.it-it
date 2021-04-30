---
title: Configurazione delle risorse Azure per Intelligence IoT
description: Questo argomento spiega come creare e configurare le risorse Microsoft Azure necessarie per l'Intelligence IoT.
author: robinarh
ms.date: 08/16/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: rhaertle
ms.custom: ''
ms.search.region: Global
ms.author: rhaertle
ms.search.validFrom: 2020-04-04
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 33c28f8e7982c6ec9b892e975525de69fc637892
ms.sourcegitcommit: d18d9cdb175c9d42eafbed66352c24b2aa94258b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2021
ms.locfileid: "5881374"
---
# <a name="set-up-azure-resources-for-iot-intelligence"></a><span data-ttu-id="ad08d-103">Configurazione delle risorse Azure per Intelligence IoT</span><span class="sxs-lookup"><span data-stu-id="ad08d-103">Set up Azure resources for IoT Intelligence</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="ad08d-104">Questo argomento spiega come creare e configurare le risorse Microsoft Azure necessarie per l'Intelligence IoT.</span><span class="sxs-lookup"><span data-stu-id="ad08d-104">This topic explains how to create and configure the Microsoft Azure resources that you require for IoT Intelligence.</span></span>

## <a name="create-azure-resources"></a><span data-ttu-id="ad08d-105">Creare risorse Azure</span><span class="sxs-lookup"><span data-stu-id="ad08d-105">Create Azure resources</span></span>

<span data-ttu-id="ad08d-106">Seguire questi passaggi per creare un hub IoT, una cache Redis e un vault chiave a cui può accedere Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="ad08d-106">Follow these steps to create an IoT hub, a Redis cache, and a key vault that can be accessed by Microsoft Dynamics 365 Supply Chain Management.</span></span>

### <a name="verify-that-the-microsoft-dynamics-erp-microservices-first-party-app-id-is-in-your-tenant"></a><span data-ttu-id="ad08d-107">Verificare che l'app del produttore dell'ERP Microsoft Dynamics Microservices sia nel tuo tenant</span><span class="sxs-lookup"><span data-stu-id="ad08d-107">Verify that the Microsoft Dynamics ERP Microservices first-party app ID is in your tenant</span></span>

<span data-ttu-id="ad08d-108">Per verificare che l'ID dell'app per l'app del produttore dell'ERP Microsoft Dynamics Microservices sia nel tuo tenant, segui questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="ad08d-108">To verify that the app ID for the Microsoft Dynamics ERP Microservices first-party app is in your tenant, follow these steps.</span></span>

1. <span data-ttu-id="ad08d-109">Accedere al portale Azure all'indirizzo <https://portal.azure.com>.</span><span class="sxs-lookup"><span data-stu-id="ad08d-109">Sign in to the Azure portal at <https://portal.azure.com>.</span></span>
2. <span data-ttu-id="ad08d-110">Accedere a **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="ad08d-110">Go to **Azure Active Directory**.</span></span>
3. <span data-ttu-id="ad08d-111">Vai ad **Applicazioni aziendali**.</span><span class="sxs-lookup"><span data-stu-id="ad08d-111">Go to **Enterprise applications**.</span></span>
4. <span data-ttu-id="ad08d-112">Nel campo **Tipo di applicazione**, seleziona **Applicazioni Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="ad08d-112">In the **Application type** field, select **Microsoft applications**.</span></span>
5. <span data-ttu-id="ad08d-113">Nel campo di ricerca, immetti **Microsoft Dynamics ERP Microservices**.</span><span class="sxs-lookup"><span data-stu-id="ad08d-113">In the search field, enter **Microsoft Dynamics ERP Microservices**.</span></span>
6. <span data-ttu-id="ad08d-114">Verifica che **Microsoft Dynamics ERP Microservices** sia nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="ad08d-114">Verify that **Microsoft Dynamics ERP Microservices** is in the list.</span></span> <span data-ttu-id="ad08d-115">Altre applicazioni hanno nomi simili.</span><span class="sxs-lookup"><span data-stu-id="ad08d-115">Other applications have similar names.</span></span> <span data-ttu-id="ad08d-116">È pertanto importante accertarsi di trovare l'applicazione corretta.</span><span class="sxs-lookup"><span data-stu-id="ad08d-116">Therefore, make sure that you find the correct application.</span></span> <span data-ttu-id="ad08d-117">L'ID app è **0cdb527f-a8d1-4bf8-9436-b352c68682b2**.</span><span class="sxs-lookup"><span data-stu-id="ad08d-117">The app ID is **0cdb527f-a8d1-4bf8-9436-b352c68682b2**.</span></span>

    <span data-ttu-id="ad08d-118">Se l'applicazione non è nell'elenco, è necessario aggiungerla al tenant:</span><span class="sxs-lookup"><span data-stu-id="ad08d-118">If the application isn't in the list, you must add it to your tenant:</span></span>

    1. <span data-ttu-id="ad08d-119">Nel portale di Azure, sulla barra degli strumenti, seleziona il pulsante per aprire Azure Cloud Shell.</span><span class="sxs-lookup"><span data-stu-id="ad08d-119">In the Azure portal, on the toolbar, select the button to open Azure Cloud Shell.</span></span>
    2. <span data-ttu-id="ad08d-120">Esegui il comando **Install-Module AzureAD**.</span><span class="sxs-lookup"><span data-stu-id="ad08d-120">Run the command **Install-Module AzureAD**.</span></span> <span data-ttu-id="ad08d-121">Immetti **Y** per installare il modulo.</span><span class="sxs-lookup"><span data-stu-id="ad08d-121">Enter **Y** to install the module.</span></span>
    3. <span data-ttu-id="ad08d-122">Esegui il comando **Get-InstalledModule -Name "AzureAD"** per verificare che il modulo sia installato.</span><span class="sxs-lookup"><span data-stu-id="ad08d-122">Run the command **Get-InstalledModule -Name "AzureAD"** to verify that the module is installed.</span></span>
    4. <span data-ttu-id="ad08d-123">Esegui il comando **Connect-AzureAD -Confirm** per eseguire l'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="ad08d-123">Run the command **Connect-AzureAD -Confirm** to run the authentication.</span></span>
    5. <span data-ttu-id="ad08d-124">Esegui il comando **New-AzureADServicePrincipal -AppId 0cdb527f-a8d1-4bf8-9436-b352c68682b2**.</span><span class="sxs-lookup"><span data-stu-id="ad08d-124">Run the command **New-AzureADServicePrincipal -AppId 0cdb527f-a8d1-4bf8-9436-b352c68682b2**.</span></span>

    <span data-ttu-id="ad08d-125">Ora puoi ripetere i passaggi da 1 a 6 per verificare che l'ID dell'app sia nel tuo titolare.</span><span class="sxs-lookup"><span data-stu-id="ad08d-125">You can now repeat steps 1 through 6 to verify that the app ID is in your tenant.</span></span>

### <a name="create-a-key-vault-resource"></a><span data-ttu-id="ad08d-126">Creare una risorsa insieme di credenziali</span><span class="sxs-lookup"><span data-stu-id="ad08d-126">Create a key vault resource</span></span>

<span data-ttu-id="ad08d-127">Per creare una risorsa insieme di credenziali chiave, completa i passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="ad08d-127">To create a key vault resource, follow these steps.</span></span>

1. <span data-ttu-id="ad08d-128">Nel portale di Azure, creare o andare a un gruppo di risorse.</span><span class="sxs-lookup"><span data-stu-id="ad08d-128">In the Azure portal, create or go to a resource group.</span></span>
2. <span data-ttu-id="ad08d-129">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="ad08d-129">Select **Add**.</span></span>
3. <span data-ttu-id="ad08d-130">Nella pagina **Nuovo**, nel campo di ricerca, inserisci **Insieme di credenziali chiave**.</span><span class="sxs-lookup"><span data-stu-id="ad08d-130">On the **New** page, in the search field, enter **Key vault**.</span></span> <span data-ttu-id="ad08d-131">Selezionare **Crea**.</span><span class="sxs-lookup"><span data-stu-id="ad08d-131">Then select **Create**.</span></span>
4. <span data-ttu-id="ad08d-132">Nella pagina **Crea insieme di credenziali chiave**, nel campo **Nome insieme di credenziali chiave**, inserisci un nome.</span><span class="sxs-lookup"><span data-stu-id="ad08d-132">On the **Create key vault** page, in the **Key vault name** field, enter a name.</span></span>
5. <span data-ttu-id="ad08d-133">Rivedi i valori predefiniti, quindi seleziona **Rivedi + crea**.</span><span class="sxs-lookup"><span data-stu-id="ad08d-133">Review the default values, and then select **Review + create**.</span></span>
6. <span data-ttu-id="ad08d-134">Selezionare **Crea**.</span><span class="sxs-lookup"><span data-stu-id="ad08d-134">Select **Create**.</span></span>

<span data-ttu-id="ad08d-135">L'insieme di credenziali chiave viene creato in background.</span><span class="sxs-lookup"><span data-stu-id="ad08d-135">The key vault is created in the background.</span></span>

### <a name="create-an-iot-hub-resource"></a><span data-ttu-id="ad08d-136">Creare una risorsa dell'hub IoT</span><span class="sxs-lookup"><span data-stu-id="ad08d-136">Create an IoT hub resource</span></span>

<span data-ttu-id="ad08d-137">Per creare una risorsa dell'hub IoT, completa i passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="ad08d-137">To create an IoT hub resource, follow these steps.</span></span>

1. <span data-ttu-id="ad08d-138">Crea o vai a un gruppo di risorse.</span><span class="sxs-lookup"><span data-stu-id="ad08d-138">Create or go to a resource group.</span></span>
2. <span data-ttu-id="ad08d-139">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="ad08d-139">Select **Add**.</span></span>
3. <span data-ttu-id="ad08d-140">Nella pagina **Nuovo**, nel campo di ricerca, inserisci **Hub IoT**.</span><span class="sxs-lookup"><span data-stu-id="ad08d-140">On the **New** page, in the search field, enter **Iot Hub**.</span></span> <span data-ttu-id="ad08d-141">Selezionare **Crea**.</span><span class="sxs-lookup"><span data-stu-id="ad08d-141">Then select **Create**.</span></span>
4. <span data-ttu-id="ad08d-142">Nel campo **Nome hub IoT** immetti un nome.</span><span class="sxs-lookup"><span data-stu-id="ad08d-142">In the **IoT hub name** field, enter a name.</span></span>
5. <span data-ttu-id="ad08d-143">Rivedi i valori predefiniti, quindi seleziona **Rivedi + crea**.</span><span class="sxs-lookup"><span data-stu-id="ad08d-143">Review the default values, and then select **Review + create**.</span></span>
6. <span data-ttu-id="ad08d-144">Selezionare **Crea**.</span><span class="sxs-lookup"><span data-stu-id="ad08d-144">Select **Create**.</span></span>

<span data-ttu-id="ad08d-145">L'hub IoT viene creato in background.</span><span class="sxs-lookup"><span data-stu-id="ad08d-145">The IoT hub is created in the background.</span></span>

> [!NOTE]
> <span data-ttu-id="ad08d-146">Ti consigliamo di creare una sola risorsa hub IoT per ambiente.</span><span class="sxs-lookup"><span data-stu-id="ad08d-146">We recommend that you create only one IoT hub resource per environment.</span></span>

### <a name="create-a-redis-cache-resource"></a><span data-ttu-id="ad08d-147">Creare una risorsa cache Redis</span><span class="sxs-lookup"><span data-stu-id="ad08d-147">Create a Redis cache resource</span></span>

<span data-ttu-id="ad08d-148">Per creare una risorsa cache Redis, completa i passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="ad08d-148">To create a Redis cache resource, follow these steps.</span></span>

1. <span data-ttu-id="ad08d-149">Crea o vai a un gruppo di risorse.</span><span class="sxs-lookup"><span data-stu-id="ad08d-149">Create or go to a resource group.</span></span>
2. <span data-ttu-id="ad08d-150">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="ad08d-150">Select **Add**.</span></span>
3. <span data-ttu-id="ad08d-151">Nella pagina **Nuovo**, nel campo di ricerca, inserisci **Cache di Azure per Redis**.</span><span class="sxs-lookup"><span data-stu-id="ad08d-151">On the **New** page, in the search field, enter **Azure Cache for Redis**.</span></span> <span data-ttu-id="ad08d-152">Selezionare **Crea**.</span><span class="sxs-lookup"><span data-stu-id="ad08d-152">Then select **Create**.</span></span>
4. <span data-ttu-id="ad08d-153">Nel campo **Nome DNS** immetti un nome.</span><span class="sxs-lookup"><span data-stu-id="ad08d-153">In the **DNS name** field, enter a name.</span></span>
5. <span data-ttu-id="ad08d-154">Rivedi i valori predefiniti, quindi seleziona **Crea**.</span><span class="sxs-lookup"><span data-stu-id="ad08d-154">Review the default values, and then select **Create**.</span></span>

<span data-ttu-id="ad08d-155">La cache Redis viene creato in background.</span><span class="sxs-lookup"><span data-stu-id="ad08d-155">The Redis cache is created in the background.</span></span>

> [!NOTE]
> <span data-ttu-id="ad08d-156">Ti consigliamo di creare una sola cache Redis per ambiente.</span><span class="sxs-lookup"><span data-stu-id="ad08d-156">We recommend that you create only one Redis cache per environment.</span></span>

<span data-ttu-id="ad08d-157">Tutte le risorse sono state ora create.</span><span class="sxs-lookup"><span data-stu-id="ad08d-157">All the resources have now been created.</span></span>

## <a name="configure-the-azure-resources"></a><span data-ttu-id="ad08d-158">Configura le risorse di Azure</span><span class="sxs-lookup"><span data-stu-id="ad08d-158">Configure the Azure resources</span></span>

### <a name="configure-the-iot-hub"></a><span data-ttu-id="ad08d-159">Configura l'hub IoT</span><span class="sxs-lookup"><span data-stu-id="ad08d-159">Configure the IoT hub</span></span>

<span data-ttu-id="ad08d-160">Per configurare l'hub IoT, attieniti a questa procedura.</span><span class="sxs-lookup"><span data-stu-id="ad08d-160">To configure the IoT hub, follow these steps.</span></span>

1. <span data-ttu-id="ad08d-161">Nelle risorse, seleziona la risorsa dell'hub IoT.</span><span class="sxs-lookup"><span data-stu-id="ad08d-161">In your resources, select the IoT hub resource.</span></span>
2. <span data-ttu-id="ad08d-162">Nel riquadro di navigazione sinistro, seleziona **Endpoint predefiniti**.</span><span class="sxs-lookup"><span data-stu-id="ad08d-162">In the left navigation pane, select **Built-in endpoints**.</span></span>
3. <span data-ttu-id="ad08d-163">In **Gruppi di consumer**, incolla i seguenti gruppi di consumatori.</span><span class="sxs-lookup"><span data-stu-id="ad08d-163">Under **Consumer groups**, paste the following consumer groups.</span></span> <span data-ttu-id="ad08d-164">Questi gruppi di consumatori corrispondono agli scenari predefiniti.</span><span class="sxs-lookup"><span data-stu-id="ad08d-164">These consumer groups correspond to the out-of-box scenarios.</span></span>

    + <span data-ttu-id="ad08d-165">microsoft.dynamics.iotintelligence-1</span><span class="sxs-lookup"><span data-stu-id="ad08d-165">microsoft.dynamics.iotintelligence-1</span></span>
    + <span data-ttu-id="ad08d-166">microsoft.dynamics.iotintelligence-2</span><span class="sxs-lookup"><span data-stu-id="ad08d-166">microsoft.dynamics.iotintelligence-2</span></span>
    + <span data-ttu-id="ad08d-167">microsoft.dynamics.iotintelligence-3</span><span class="sxs-lookup"><span data-stu-id="ad08d-167">microsoft.dynamics.iotintelligence-3</span></span>

### <a name="configure-the-key-vault"></a><span data-ttu-id="ad08d-168">Configura l'insieme di credenziali chiave</span><span class="sxs-lookup"><span data-stu-id="ad08d-168">Configure the key vault</span></span>

<span data-ttu-id="ad08d-169">Per configurare l'insieme di credenziali chiave, segui questa procedura.</span><span class="sxs-lookup"><span data-stu-id="ad08d-169">To configure the key vault, follow these steps.</span></span>

1. <span data-ttu-id="ad08d-170">Nelle risorse, seleziona la risorsa dell'insieme di credenziali chiave.</span><span class="sxs-lookup"><span data-stu-id="ad08d-170">In your resources, select the key vault resource.</span></span>
2. <span data-ttu-id="ad08d-171">Nel riquadro di spostamento sinistro, seleziona **Criteri di accesso**.</span><span class="sxs-lookup"><span data-stu-id="ad08d-171">In the left navigation pane, select **Access policies**.</span></span>
3. <span data-ttu-id="ad08d-172">Seleziona **Aggiungi un nuovo criterio di accesso**.</span><span class="sxs-lookup"><span data-stu-id="ad08d-172">Select **Add an access policy**.</span></span>
4. <span data-ttu-id="ad08d-173">Nella pagina **Aggiungi un criterio di accesso**, nel campo **Autorizzazioni segrete**, seleziona **Ottieni** ed **Elenco**.</span><span class="sxs-lookup"><span data-stu-id="ad08d-173">On the **Add access policy** page, in the **Secret permissions** field, select **Get** and **List**.</span></span>
5. <span data-ttu-id="ad08d-174">Fai clic su **Seleziona un'entità**.</span><span class="sxs-lookup"><span data-stu-id="ad08d-174">Click in the **Select principal**.</span></span>
6. <span data-ttu-id="ad08d-175">Nella finestra di dialogo **Entità di protezione**, cerca e seleziona **Microsoft Dynamics ERP Microservices**.</span><span class="sxs-lookup"><span data-stu-id="ad08d-175">In the **Principal** dialog box, search for and select **Microsoft Dynamics ERP Microservices**.</span></span> <span data-ttu-id="ad08d-176">Quindi seleziona **Seleziona**.</span><span class="sxs-lookup"><span data-stu-id="ad08d-176">Then select **Select**.</span></span>
7. <span data-ttu-id="ad08d-177">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="ad08d-177">Select **Add**.</span></span>
8. <span data-ttu-id="ad08d-178">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="ad08d-178">Select **Save**.</span></span>

<span data-ttu-id="ad08d-179">L'app ora ha accesso ai segreti nell'insieme di credenziali chiave.</span><span class="sxs-lookup"><span data-stu-id="ad08d-179">The app now has access to the secrets in the key vault.</span></span>

### <a name="save-the-iot-hub-connection-string-secret"></a><span data-ttu-id="ad08d-180">Salva il segreto della stringa di connessione dell'hub IoT</span><span class="sxs-lookup"><span data-stu-id="ad08d-180">Save the IoT hub connection string secret</span></span>

<span data-ttu-id="ad08d-181">Per salvare il segreto per la stringa di connessione dell'hub IoT, attieniti alla seguente procedura.</span><span class="sxs-lookup"><span data-stu-id="ad08d-181">To save the secret for the IoT hub connection string, follow these steps.</span></span>

1. <span data-ttu-id="ad08d-182">Nelle risorse, seleziona la risorsa dell'hub IoT.</span><span class="sxs-lookup"><span data-stu-id="ad08d-182">In your resources, select the IoT hub resource.</span></span>
2. <span data-ttu-id="ad08d-183">Nel riquadro di navigazione sinistro, seleziona **Endpoint predefiniti**.</span><span class="sxs-lookup"><span data-stu-id="ad08d-183">In the left navigation pane, select **Built-in endpoints**.</span></span>
3. <span data-ttu-id="ad08d-184">Copia il valore nel campo **Endpoint compatibile con hub eventi**.</span><span class="sxs-lookup"><span data-stu-id="ad08d-184">Copy the value in the **Event Hub-compatible endpoint** field.</span></span>
4. <span data-ttu-id="ad08d-185">Vai alla risorsa dell'insieme di credenziali chiave.</span><span class="sxs-lookup"><span data-stu-id="ad08d-185">Go to the key vault resource.</span></span>
5. <span data-ttu-id="ad08d-186">Nel pannello di navigazione a sinistra, selezionare **Segreti**.</span><span class="sxs-lookup"><span data-stu-id="ad08d-186">In the left navigation pane, select **Secrets**.</span></span>
6. <span data-ttu-id="ad08d-187">Seleziona **Genera/Importa**.</span><span class="sxs-lookup"><span data-stu-id="ad08d-187">Select **Generate/Import**.</span></span>
7. <span data-ttu-id="ad08d-188">Nel campo **Nome** immettere un nome.</span><span class="sxs-lookup"><span data-stu-id="ad08d-188">In the **Name** field, enter a name.</span></span>
8. <span data-ttu-id="ad08d-189">Nel campo **Valore**, incolla il valore dell'endpoint che hai copiato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="ad08d-189">In the **Value** field, paste the endpoint value that you copied earlier.</span></span>
9. <span data-ttu-id="ad08d-190">Selezionare **Crea**.</span><span class="sxs-lookup"><span data-stu-id="ad08d-190">Select **Create**.</span></span>

### <a name="save-the-redis-cache-connection-string-secret"></a><span data-ttu-id="ad08d-191">Salva il segreto della stringa di connessione della cache Redis</span><span class="sxs-lookup"><span data-stu-id="ad08d-191">Save the Redis cache connection string secret</span></span>

<span data-ttu-id="ad08d-192">Per salvare il segreto per la stringa di connessione della cache Redis, attieniti alla seguente procedura.</span><span class="sxs-lookup"><span data-stu-id="ad08d-192">To save the secret for the Redis cache connection string, follow these steps.</span></span>

1. <span data-ttu-id="ad08d-193">Nelle risorse, seleziona la risorsa della cache Redis.</span><span class="sxs-lookup"><span data-stu-id="ad08d-193">In your resources, select the Redis cache resource.</span></span>
2. <span data-ttu-id="ad08d-194">Seleziona **Chiavi di accesso**.</span><span class="sxs-lookup"><span data-stu-id="ad08d-194">Select **Access keys**.</span></span>
3. <span data-ttu-id="ad08d-195">Copia il valore nel campo **Stringa di connessione primaria**.</span><span class="sxs-lookup"><span data-stu-id="ad08d-195">Copy the value in the **Primary connection string** field.</span></span>
4. <span data-ttu-id="ad08d-196">Vai alla risorsa dell'insieme di credenziali chiave.</span><span class="sxs-lookup"><span data-stu-id="ad08d-196">Go to the key vault resource.</span></span>
5. <span data-ttu-id="ad08d-197">Nel pannello di navigazione a sinistra, selezionare **Segreti**.</span><span class="sxs-lookup"><span data-stu-id="ad08d-197">In the left navigation pane, select **Secrets**.</span></span>
6. <span data-ttu-id="ad08d-198">Seleziona **Genera/Importa**.</span><span class="sxs-lookup"><span data-stu-id="ad08d-198">Select **Generate/Import**.</span></span>
7. <span data-ttu-id="ad08d-199">Nel campo **Nome** immettere un nome.</span><span class="sxs-lookup"><span data-stu-id="ad08d-199">In the **Name** field, enter a name.</span></span>
8. <span data-ttu-id="ad08d-200">Nel campo **Valore**, incolla la stringa di connessione che hai copiato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="ad08d-200">In the **Value** field, paste the connection string that you copied earlier.</span></span>
9. <span data-ttu-id="ad08d-201">Selezionare **Crea**.</span><span class="sxs-lookup"><span data-stu-id="ad08d-201">Select **Create**.</span></span>

> [!NOTE]
> <span data-ttu-id="ad08d-202">Ogni volta che aggiorni una delle stringhe di connessione, devi anche aggiornare i valori segreti.</span><span class="sxs-lookup"><span data-stu-id="ad08d-202">Whenever you update one of the connection strings, you must also update the secret values.</span></span>

<span data-ttu-id="ad08d-203">Ora hai completato il provisioning delle risorse di Azure richieste.</span><span class="sxs-lookup"><span data-stu-id="ad08d-203">You've now finished provisioning the required Azure resources.</span></span> <span data-ttu-id="ad08d-204">Il prossimo passo è [Installare l'add-in Intelligence IoT in Microsoft Dynamics Lifecycle Services (LCS)](iot-lcs-setup.md).</span><span class="sxs-lookup"><span data-stu-id="ad08d-204">The next step is to [install the IoT Intelligence add-in in Microsoft Dynamics Lifecycle Services (LCS)](iot-lcs-setup.md).</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
