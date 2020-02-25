---
title: Abilitare ADLS in un ambiente di Dynamics 365 Commerce
description: Questo argomento spiega come abilitare e testare Azure Data Lake Storage (ADLS) per un ambiente di Dynamics 365 Commerce, che è un prerequisito per abilitare i suggerimenti sui prodotti.
author: bebeale
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: ''
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail, eCommerce
ms.author: bebeale
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 068eb522bd44e02dd31d3337a051691a956637fc
ms.sourcegitcommit: b5ecde955a69f577de46e7db10e89caaedeb2b49
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "3025257"
---
# <a name="enable-adls-in-a-dynamics-365-commerce-environment"></a><span data-ttu-id="2b0e0-103">Abilitare ADLS in un ambiente di Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="2b0e0-103">Enable ADLS in a Dynamics 365 Commerce environment</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="2b0e0-104">Questo argomento spiega come abilitare e testare Azure Data Lake Storage (ADLS) per un ambiente di Dynamics 365 Commerce, che è un prerequisito per abilitare i suggerimenti sui prodotti.</span><span class="sxs-lookup"><span data-stu-id="2b0e0-104">This topic explains how to enable and test Azure Data Lake Storage (ADLS) for a Dynamics 365 Commerce environment, which is a prerequisite for enabling product recommendations.</span></span>

## <a name="overview"></a><span data-ttu-id="2b0e0-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="2b0e0-105">Overview</span></span>

<span data-ttu-id="2b0e0-106">Nella soluzione Dynamics 365 Commerce, tutte le informazioni su prodotti e transazioni vengono tracciate nell'archivio entità dell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="2b0e0-106">In the Dynamics 365 Commerce solution, all product and transaction information is tracked in the environment's Entity store.</span></span> <span data-ttu-id="2b0e0-107">Per rendere questi dati accessibili ad altri servizi di Dynamics 365, come analisi dei dati, business intelligence e suggerimenti personalizzati, è necessario connettere l'ambiente a una soluzione Azure Data Lake Storage Gen 2 (ADLS) di proprietà del cliente.</span><span class="sxs-lookup"><span data-stu-id="2b0e0-107">To make this data accessible to other Dynamics 365 services, such as data analytics, business intelligence, and personalized recommendations, it is necessary to connect the environment to a customer-owned Azure Data Lake Storage Gen 2 (ADLS) solution.</span></span>

<span data-ttu-id="2b0e0-108">Poiché ADLS è configurato in un ambiente, tutti i dati necessari vengono sottoposti a mirroring dall'archivio entità pur essendo protetti e sotto il controllo del cliente.</span><span class="sxs-lookup"><span data-stu-id="2b0e0-108">As ADLS is configured in an environment, all necessary data is mirrored from the Entity store while still being protected and under customer's control.</span></span>

<span data-ttu-id="2b0e0-109">Se nell'ambiente sono abilitati anche suggerimenti sui prodotti o personalizzati, allo stack dei suggerimenti sui prodotti verrà concesso l'accesso alla cartella dedicata in ADLS per recuperare i dati del cliente e calcolare i suggerimenti basati sugli stessi.</span><span class="sxs-lookup"><span data-stu-id="2b0e0-109">If product recommendations or personalized recommendations are also enabled in the environment, then the product recommendations stack will be granted access to the dedicated folder in ADLS to retrieve the customer’s data and compute recommendations based on it.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="2b0e0-110">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="2b0e0-110">Prerequisites</span></span>

<span data-ttu-id="2b0e0-111">I clienti devono avere ADLS configurato in una sottoscrizione di Azure di loro proprietà.</span><span class="sxs-lookup"><span data-stu-id="2b0e0-111">Customers need to have ADLS configured in an Azure subscription that they own.</span></span> <span data-ttu-id="2b0e0-112">Questo argomento non copre l'acquisto di una sottoscrizione di Azure o la configurazione di un account di archiviazione abilitato per ADLS.</span><span class="sxs-lookup"><span data-stu-id="2b0e0-112">This topic does not cover the purchase of an Azure subscription or the setup of an ADLS-enabled storage account.</span></span>

<span data-ttu-id="2b0e0-113">Per ulteriori informazioni su ADLS, vedere la [documentazione ufficiale di ADLS](https://azure.microsoft.com/pricing/details/storage/data-lake).</span><span class="sxs-lookup"><span data-stu-id="2b0e0-113">For more information about ADLS, see [ADLS official documentation](https://azure.microsoft.com/pricing/details/storage/data-lake).</span></span>
  
## <a name="configuration-steps"></a><span data-ttu-id="2b0e0-114">Passaggi di configurazione</span><span class="sxs-lookup"><span data-stu-id="2b0e0-114">Configuration steps</span></span>

<span data-ttu-id="2b0e0-115">Questa sezione illustra i passaggi di configurazione necessari per abilitare ADLS in un ambiente.</span><span class="sxs-lookup"><span data-stu-id="2b0e0-115">This section covers the configuration steps necessary for enabling ADLS in an environment.</span></span>

### <a name="enable-adls-in-the-environment"></a><span data-ttu-id="2b0e0-116">Abilitare ADLS nell'ambiente</span><span class="sxs-lookup"><span data-stu-id="2b0e0-116">Enable ADLS in the environment</span></span>

1. <span data-ttu-id="2b0e0-117">Accedere al portale di back office dell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="2b0e0-117">Log in to the environment's back office portal.</span></span>
1. <span data-ttu-id="2b0e0-118">Cercare **Parametri di sistema** e selezionare la scheda **Connessioni dati**.</span><span class="sxs-lookup"><span data-stu-id="2b0e0-118">Search for **System Parameters** and navigate to the **Data connections** tab.</span></span> 
1. <span data-ttu-id="2b0e0-119">Impostare **Abilita l'integrazione di Data Lake** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="2b0e0-119">Set **Enable Data Lake integration** to **Yes**.</span></span>
1. <span data-ttu-id="2b0e0-120">Impostare **Aggiornamento afflusso Data Lake** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="2b0e0-120">Set **Trickle update Data Lake** to **Yes**.</span></span>
1. <span data-ttu-id="2b0e0-121">Successivamente, immettere le informazioni necessarie seguenti:</span><span class="sxs-lookup"><span data-stu-id="2b0e0-121">Next, enter the following required information:</span></span>
    1. <span data-ttu-id="2b0e0-122">**ID applicazione** // **Segreto applicazione** // **Nome DNS** - Necessario per connettersi a KeyVault in cui è archiviato il segreto ADLS.</span><span class="sxs-lookup"><span data-stu-id="2b0e0-122">**Application ID** // **Application Secret** // **DNS Name** - Needed to connect to KeyVault where the ADLS secret is stored.</span></span>
    1. <span data-ttu-id="2b0e0-123">**Nome segreto** - Il nome segreto memorizzato in KeyVault e utilizzato per l'autenticazione con ADLS.</span><span class="sxs-lookup"><span data-stu-id="2b0e0-123">**Secret name** - The secret name stored in KeyVault and used to authenticate with ADLS.</span></span>
1. <span data-ttu-id="2b0e0-124">Salvare le modifiche nell'angolo in alto a sinistra della pagina.</span><span class="sxs-lookup"><span data-stu-id="2b0e0-124">Save your changes in the top left corner of the page.</span></span>

<span data-ttu-id="2b0e0-125">L'immagine seguente mostra un esempio di configurazione ADLS.</span><span class="sxs-lookup"><span data-stu-id="2b0e0-125">The following image shows an example ADLS configuration.</span></span>

![Esempio dI configurazione ADLS](./media/exampleADLSConfig1.png)

### <a name="test-the-adls-connection"></a><span data-ttu-id="2b0e0-127">Testare la connessione ADLS</span><span class="sxs-lookup"><span data-stu-id="2b0e0-127">Test the ADLS connection</span></span>

1. <span data-ttu-id="2b0e0-128">Testare la connessione a KeyVault usando il collegamento **Testa Azure Key Vault**.</span><span class="sxs-lookup"><span data-stu-id="2b0e0-128">Test the connection to KeyVault using the **Test Azure Key Vault** link.</span></span>
1. <span data-ttu-id="2b0e0-129">Testare la connessione a ADLS usando il collegamento **Testa Archiviazione di Azure**.</span><span class="sxs-lookup"><span data-stu-id="2b0e0-129">Test the connection to ADLS using the **Test Azure Storage** link.</span></span>

> [!NOTE]
> <span data-ttu-id="2b0e0-130">Se i test falliscono, ricontrollare che tutte le informazioni KeyVault aggiunte sopra siano corrette, quindi riprovare.</span><span class="sxs-lookup"><span data-stu-id="2b0e0-130">If the tests fail, double-check that all of the KeyVault information added above is correct, then try again.</span></span>

<span data-ttu-id="2b0e0-131">Una volta che i test di connessione hanno esito positivo, è necessario abilitare l'aggiornamento automatico per l'archivio entità.</span><span class="sxs-lookup"><span data-stu-id="2b0e0-131">Once the connection tests are successful, you must enable automatic refresh for Entity store.</span></span>

<span data-ttu-id="2b0e0-132">Per abilitare l'aggiornamento automatico per l'archivio entità, attenersi alla seguente procedura.</span><span class="sxs-lookup"><span data-stu-id="2b0e0-132">To enable automatic refresh for Entity store, follow these steps.</span></span>

1. <span data-ttu-id="2b0e0-133">Cercare **Archivio entità**.</span><span class="sxs-lookup"><span data-stu-id="2b0e0-133">Search for **Entity Store**.</span></span>
1. <span data-ttu-id="2b0e0-134">Nell'elenco a sinistra, selezionare la voce **RetailSales** e selezionare **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="2b0e0-134">In the list on the left, navigate to the **RetailSales** entry, and select **Edit**.</span></span>
1. <span data-ttu-id="2b0e0-135">Assicurarsi che **Aggiornamento automatico attivato** sia impostato su **Sì**, selezionare **Aggiorna**, quindi selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="2b0e0-135">Ensure that **Automatic Refresh Enabled** is set to **Yes**, select **Refresh**, and then select **Save**.</span></span>

<span data-ttu-id="2b0e0-136">L'immagine seguente mostra un esempio di archivio entità con aggiornamento automatico abilitato.</span><span class="sxs-lookup"><span data-stu-id="2b0e0-136">The following image shows an example of Entity store with automatic refresh enabled.</span></span>

![Esempio di archivio entità con aggiornamento automatico abilitato](./media/exampleADLSConfig2.png)

<span data-ttu-id="2b0e0-138">ADLS è ora configurato per l'ambiente.</span><span class="sxs-lookup"><span data-stu-id="2b0e0-138">ADLS is now configured for the environment.</span></span> 

<span data-ttu-id="2b0e0-139">Se non è già stato fatto, seguire la procedura per [abilitare la personalizzazione e i suggerimenti sui prodotti](enable-product-recommendations.md) per l'ambiente.</span><span class="sxs-lookup"><span data-stu-id="2b0e0-139">If not completed already, follow the steps for [enabling product recommendations and personalization](enable-product-recommendations.md) for the environment.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="2b0e0-140">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="2b0e0-140">Additional resources</span></span>

[<span data-ttu-id="2b0e0-141">Panoramica suggerimenti sul prodotto</span><span class="sxs-lookup"><span data-stu-id="2b0e0-141">Product recommendations overview</span></span>](product-recommendations.md)

[<span data-ttu-id="2b0e0-142">Abilitare suggerimenti sul prodotto</span><span class="sxs-lookup"><span data-stu-id="2b0e0-142">Enable product recommendations</span></span>](enable-product-recommendations.md)

[<span data-ttu-id="2b0e0-143">Aggiungere elenchi di suggerimenti sul prodotto alle pagine</span><span class="sxs-lookup"><span data-stu-id="2b0e0-143">Add product recommendation lists to pages</span></span>](add-reco-list-to-page.md)

[<span data-ttu-id="2b0e0-144">Aggiungere un controllo di suggerimenti alla schermata della transazione su dispositivi POS</span><span class="sxs-lookup"><span data-stu-id="2b0e0-144">Add a recommendations control to the transaction screen on POS devices</span></span>](../retail/add-recommendations-control-pos-screen.md?toc=/dynamics365/commerce/toc.json)


