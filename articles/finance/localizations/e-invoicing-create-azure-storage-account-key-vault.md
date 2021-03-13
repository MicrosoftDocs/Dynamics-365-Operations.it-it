---
title: Creare un account di Archiviazione di Azure e un Azure Key Vault
description: Questo argomento spiega come creare un account di Archiviazione di Azure e Azure Key Vault.
author: gionoder
manager: AnnBe
ms.date: 09/22/2020
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
ms.openlocfilehash: d076aa5230437d1ef90f6b46d49ee4dea526db24
ms.sourcegitcommit: e88c96d1cb817a22db81856cadb563c095ab2671
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/02/2021
ms.locfileid: "5104231"
---
# <a name="create-an-azure-storage-account-and-a-key-vault"></a><span data-ttu-id="37dbb-103">Creare un account di Archiviazione di Azure e un Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="37dbb-103">Create an Azure storage account and a key vault</span></span>

[!include [banner](../includes/banner.md)]

## <a name="prerequisites"></a><span data-ttu-id="37dbb-104">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="37dbb-104">Prerequisites</span></span>

<span data-ttu-id="37dbb-105">Prima di poter completare i passaggi in questo argomento, è necessario accertarsi che le seguenti attività siano state completate:</span><span class="sxs-lookup"><span data-stu-id="37dbb-105">Before you can complete the steps in this topic, you must make sure that the following tasks have been completed:</span></span>

- <span data-ttu-id="37dbb-106">Crea una risorsa Azure Key Vault.</span><span class="sxs-lookup"><span data-stu-id="37dbb-106">Create a key vault resource in Azure.</span></span> <span data-ttu-id="37dbb-107">Per ulteriori informazioni sulle misure, vedi [Informazioni su Azure Key Vault](https://docs.microsoft.com/azure/key-vault/general/overview).</span><span class="sxs-lookup"><span data-stu-id="37dbb-107">For more information, see [About Azure Key Vault](https://docs.microsoft.com/azure/key-vault/general/overview).</span></span>
- <span data-ttu-id="37dbb-108">Creare un account di Archiviazione di Azure (archiviazione BLOB).</span><span class="sxs-lookup"><span data-stu-id="37dbb-108">Create an Azure storage account (Blob storage).</span></span> <span data-ttu-id="37dbb-109">Per ulteriori informazioni, vedi [Gestione dell'account di Archiviazione di Azure](https://docs.microsoft.com/azure/storage/blobs/).</span><span class="sxs-lookup"><span data-stu-id="37dbb-109">For more information, see [Maintaining Azure Storage Account](https://docs.microsoft.com/azure/storage/blobs/).</span></span>

## <a name="overview"></a><span data-ttu-id="37dbb-110">Panoramica</span><span class="sxs-lookup"><span data-stu-id="37dbb-110">Overview</span></span>

<span data-ttu-id="37dbb-111">In questo argomento, completerai due passaggi principali:</span><span class="sxs-lookup"><span data-stu-id="37dbb-111">In this topic, you will complete two main steps:</span></span>

- <span data-ttu-id="37dbb-112">Configura l'account di Archiviazione di Azure per ottenere l'URI dell'account di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="37dbb-112">Set up the Azure storage account to get the storage account URI.</span></span>
- <span data-ttu-id="37dbb-113">Configura Azure Key Vault per archiviare l'URI dell'account di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="37dbb-113">Set up the key vault to store the storage account URI.</span></span>

## <a name="set-up-the-azure-storage-account-to-get-the-storage-account-uri"></a><span data-ttu-id="37dbb-114">Configurare l'account di Archiviazione di Azure per ottenere l'URI dell'account di archiviazione</span><span class="sxs-lookup"><span data-stu-id="37dbb-114">Set up the Azure storage account to get the storage account URI</span></span>

1. <span data-ttu-id="37dbb-115">Apri l'account di archiviazione che intendi utilizzare con il componente aggiuntivo per la fatturazione elettronica.</span><span class="sxs-lookup"><span data-stu-id="37dbb-115">Open the storage account that you plan to use with the Electronic invoicing add-on.</span></span>
2. <span data-ttu-id="37dbb-116">Vai a **Servizio BLOB** \> **Contenitori** e crea un nuovo contenitore.</span><span class="sxs-lookup"><span data-stu-id="37dbb-116">Go to **Blob service** \> **Containers**, and create a new container.</span></span>
3. <span data-ttu-id="37dbb-117">Immetti un nome per il contenitore e imposta il campo **Livello di accesso pubblico** su **Privato (nessun accesso anonimo)**.</span><span class="sxs-lookup"><span data-stu-id="37dbb-117">Enter a name for the container, and set the **Public access level** field to **Private (no anonymous access)**.</span></span>
4. <span data-ttu-id="37dbb-118">Apri il contenitore e vai a **Impostazioni \> Criteri di accesso**.</span><span class="sxs-lookup"><span data-stu-id="37dbb-118">Open the container, and go to **Settings \> Access policy**.</span></span>
5. <span data-ttu-id="37dbb-119">Seleziona **Aggiungi criteri** per aggiungere un criterio di accesso archiviato.</span><span class="sxs-lookup"><span data-stu-id="37dbb-119">Select **Add policy** to add a stored access policy.</span></span>
6. <span data-ttu-id="37dbb-120">Imposta i campi **Identificatore** e **Autorizzazioni** in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="37dbb-120">Set the **Identifier** and **Permissions** fields as appropriate.</span></span> <span data-ttu-id="37dbb-121">Nel campo **Autorizzazioni**, è consigliabile selezionare tutte le autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="37dbb-121">In the **Permissions** field, you should select all permissions.</span></span>

    ![Concessione dell'autorizzazione per l'archiviazione BLOB](media/e-Invoicing-services-create-azure-resources-grant-blob-permissions.png)

7. <span data-ttu-id="37dbb-123">Immetti le date di inizio e di scadenza.</span><span class="sxs-lookup"><span data-stu-id="37dbb-123">Enter the start and expiry dates.</span></span> <span data-ttu-id="37dbb-124">La data di scadenza dovrebbe essere nel futuro.</span><span class="sxs-lookup"><span data-stu-id="37dbb-124">The expiry date should be in future.</span></span>
8. <span data-ttu-id="37dbb-125">Seleziona **OK** per salvare i criteri, quindi salva le modifiche nel contenitore.</span><span class="sxs-lookup"><span data-stu-id="37dbb-125">Select **OK** to save the policy, and then save your changes to the container.</span></span>
9. <span data-ttu-id="37dbb-126">Torna all'account di archiviazione e apri **Storage Explorer (anteprima)**.</span><span class="sxs-lookup"><span data-stu-id="37dbb-126">Return to the storage account, and open **Storage Explorer (preview)**.</span></span>
10. <span data-ttu-id="37dbb-127">Fai clic con il pulsante destro del mouse sul contenitore e quindi seleziona **Ottieni firma di accesso condiviso**.</span><span class="sxs-lookup"><span data-stu-id="37dbb-127">Right-click the container, and then select **Get Shared Access Signature**.</span></span>
11. <span data-ttu-id="37dbb-128">Nella finestra di dialogo **Firma di accesso condiviso**, copiare e archivia il valore nel campo **URI**.</span><span class="sxs-lookup"><span data-stu-id="37dbb-128">In the **Shared Access Signature** dialog box, copy and store the value in the **URI** field.</span></span> <span data-ttu-id="37dbb-129">Questo valore verrà utilizzato nella procedura successiva e verrà indicato come *URI della firma di accesso condiviso*.</span><span class="sxs-lookup"><span data-stu-id="37dbb-129">This value will be used in the next procedure and will be referred to as the *shared access signature URI*.</span></span>

    ![Selezione e copia del valore URI](media/e-Invoicing-services-create-azure-resources-select-and-copy-uri.png)

## <a name="set-up-the-key-vault-to-store-the-storage-account-uri"></a><span data-ttu-id="37dbb-131">Configurare Azure Key Vault per archiviare l'URI dell'account di archiviazione</span><span class="sxs-lookup"><span data-stu-id="37dbb-131">Set up the key vault to store the storage account URI</span></span>

1. <span data-ttu-id="37dbb-132">Apri l'Azure Key Vault che intendi utilizzare con il componente aggiuntivo per la fatturazione elettronica.</span><span class="sxs-lookup"><span data-stu-id="37dbb-132">Open the key vault that you intend to use with the Electronic invoicing add-on.</span></span>
2. <span data-ttu-id="37dbb-133">Vai a **Impostazioni** \> **Segreti**, quindi seleziona **Genera/Importa** per creare un nuovo segreto.</span><span class="sxs-lookup"><span data-stu-id="37dbb-133">Go to **Settings** \> **Secrets**, and then select **Generate/Import** to create a new secret.</span></span>
3. <span data-ttu-id="37dbb-134">Nella pagina **Crea un segreto**, nel campo **Opzioni di caricamento**, seleziona **Manuale**.</span><span class="sxs-lookup"><span data-stu-id="37dbb-134">On the **Create a secret** page, in the **Upload options** field, select **Manual**.</span></span>
4. <span data-ttu-id="37dbb-135">Immettere il nome del segreto.</span><span class="sxs-lookup"><span data-stu-id="37dbb-135">Enter the name of the secret.</span></span> <span data-ttu-id="37dbb-136">Questo nome verrà utilizzato durante la configurazione del servizio in Regulatory Configuration Service (RCS) e verrà indicato come *nome segreto di Azure Key Vault*.</span><span class="sxs-lookup"><span data-stu-id="37dbb-136">This name will be used during setup of the service in Regulatory Configuration Service (RCS) and will be referred to as the *key vault secret name*.</span></span>
5. <span data-ttu-id="37dbb-137">Nel campo **Valore**, seleziona **URI della firma di accesso condiviso** e quindi seleziona **Crea**.</span><span class="sxs-lookup"><span data-stu-id="37dbb-137">In the **Value** field, select **Shared Access Signature URI**, and then select **Create**.</span></span>
6. <span data-ttu-id="37dbb-138">Configura i criteri di accesso per concedere al componente aggiuntivo per la fatturazione elettronica il livello corretto di accesso protetto al segreto creato.</span><span class="sxs-lookup"><span data-stu-id="37dbb-138">Set up the access policy to grant the Electronic invoicing add-on the correct level of secure access to the secret you created.</span></span> <span data-ttu-id="37dbb-139">Vai a **Impostazioni \> Criteri di accesso** e seleziona **Aggiungi criteri di accesso**.</span><span class="sxs-lookup"><span data-stu-id="37dbb-139">Go to **Settings \> Access policy**, and select **Add Access Policy**.</span></span>
7. <span data-ttu-id="37dbb-140">Imposta le autorizzazioni segrete per le operazioni **Ottieni** ed **Elenco**.</span><span class="sxs-lookup"><span data-stu-id="37dbb-140">Set the secret permissions for the **Get** and **List** operations.</span></span>

    ![Concessione dell'accesso al servizio](media/e-Invoicing-services-create-azure-resources-grant-service-access.png)

8. <span data-ttu-id="37dbb-142">Imposta le autorizzazioni del certificato per le operazioni **Ottieni** ed **Elenco**.</span><span class="sxs-lookup"><span data-stu-id="37dbb-142">Set the certificate permissions for **Get** and **List** operations.</span></span>

    ![Concessione dell'autorizzazione al certificato](media/e-Invoicing-services-create-azure-resources-grant-certificate-permission.png)

9. <span data-ttu-id="37dbb-144">Nella finestra di dialogo **Entità di sicurezza**, seleziona l'entità di sicurezza aggiungendo **Componente aggiuntivo per la fatturazione elettronica**.</span><span class="sxs-lookup"><span data-stu-id="37dbb-144">In the **Principal** dialog box, select the principal by adding **Electronic invoicing add-on**.</span></span>
10. <span data-ttu-id="37dbb-145">Seleziona **Aggiungi** e quindi seleziona **Salva le modifiche di Key Vault**.</span><span class="sxs-lookup"><span data-stu-id="37dbb-145">Select **Add**, and then select **Save Key Vault changes**.</span></span>
11. <span data-ttu-id="37dbb-146">Nella pagina **Panoramica**, copia il valore **Nome DNS** valore per il Key Vault.</span><span class="sxs-lookup"><span data-stu-id="37dbb-146">On the **Overview** page, copy the **DNS name** value for the key vault.</span></span> <span data-ttu-id="37dbb-147">Questo valore verrà utilizzato durante la configurazione del servizio in RCS e verrà indicato come *URI di Key Vault*.</span><span class="sxs-lookup"><span data-stu-id="37dbb-147">This value will be used during setup of the service in RCS and will be referred as the *key vault URI*.</span></span>
