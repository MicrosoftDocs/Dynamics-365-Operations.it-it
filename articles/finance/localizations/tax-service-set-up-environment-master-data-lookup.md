---
title: Configurare un ambiente per la ricerca dei dati master
description: In questo argomento viene descritto come configurare l'ambiente per l'utilizzo della funzionalità di ricerca di dati master Calcolo imposte.
author: kai-cloud
ms.date: 04/21/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.search.region: Global
ms.author: pashao
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 9f9b385df1db60b27698d90281c43fabb574af49
ms.sourcegitcommit: 5f5afb46431e1abd8fb6e92e0189914b598dc7fd
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2021
ms.locfileid: "5924156"
---
# <a name="set-up-an-environment-for-master-data-lookup"></a><span data-ttu-id="d16b6-103">Configurare un ambiente per la ricerca dei dati master</span><span class="sxs-lookup"><span data-stu-id="d16b6-103">Set up an environment for master data lookup</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d16b6-104">In questo argomento viene descritto come configurare l'ambiente per l'utilizzo della funzionalità di ricerca di dati master Calcolo imposte.</span><span class="sxs-lookup"><span data-stu-id="d16b6-104">This topic explains how to set up your environment to use the Tax Calculation master data lookup functionality.</span></span>

1. <span data-ttu-id="d16b6-105">Configurare l'integrazione di Power Platform in Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="d16b6-105">Set up power platform integration in Lifecycle Services (LCS).</span></span> <span data-ttu-id="d16b6-106">Per ulteriori informazioni, vedere [Panoramica di Integrazione di Microsoft Power Platform - Componenti aggiuntivi](../../fin-ops-core/dev-itpro/power-platform/add-ins-overview.md).</span><span class="sxs-lookup"><span data-stu-id="d16b6-106">For more information, see [Microsoft Power Platform integration - Add-ins overview](../../fin-ops-core/dev-itpro/power-platform/add-ins-overview.md).</span></span>
2. <span data-ttu-id="d16b6-107">Configurare Dynamics 365 Finance e Microsoft Dataverse.</span><span class="sxs-lookup"><span data-stu-id="d16b6-107">Set up Dynamics 365 Finance and Microsoft Dataverse.</span></span> <span data-ttu-id="d16b6-108">Per ulteriori informazioni, vedere [Ottenere la soluzione](../../fin-ops-core/dev-itpro/power-platform/admin-reference.md#getting-the-solution) e [Autenticazione e autorizzazione](../../fin-ops-core/dev-itpro/power-platform/admin-reference.md#authentication-and-authorization).</span><span class="sxs-lookup"><span data-stu-id="d16b6-108">For more information, see [Getting the solution](../../fin-ops-core/dev-itpro/power-platform/admin-reference.md#getting-the-solution) and [Authentication and authorization](../../fin-ops-core/dev-itpro/power-platform/admin-reference.md#authentication-and-authorization).</span></span>
3. <span data-ttu-id="d16b6-109">Impostare le seguenti entità.</span><span class="sxs-lookup"><span data-stu-id="d16b6-109">Set up the following entities.</span></span> <span data-ttu-id="d16b6-110">Per ulteriori informazioni, vedere [Abilitare entità virtuali](../../fin-ops-core/dev-itpro/power-platform/admin-reference.md#enabling-virtual-entities).</span><span class="sxs-lookup"><span data-stu-id="d16b6-110">For more information, see [Enabling virtual entities](../../fin-ops-core/dev-itpro/power-platform/admin-reference.md#enabling-virtual-entities).</span></span>
      - <span data-ttu-id="d16b6-111">CompanyInfoEntity</span><span class="sxs-lookup"><span data-stu-id="d16b6-111">CompanyInfoEntity</span></span>
      - <span data-ttu-id="d16b6-112">CurrencyEntity</span><span class="sxs-lookup"><span data-stu-id="d16b6-112">CurrencyEntity</span></span>
      - <span data-ttu-id="d16b6-113">CustCustomerV3Entity</span><span class="sxs-lookup"><span data-stu-id="d16b6-113">CustCustomerV3Entity</span></span>
      - <span data-ttu-id="d16b6-114">DeliveryTermsEntity</span><span class="sxs-lookup"><span data-stu-id="d16b6-114">DeliveryTermsEntity</span></span>
      - <span data-ttu-id="d16b6-115">EcoResProductCategoryEntity</span><span class="sxs-lookup"><span data-stu-id="d16b6-115">EcoResProductCategoryEntity</span></span>
      - <span data-ttu-id="d16b6-116">EcoResReleasedProductV2Entity</span><span class="sxs-lookup"><span data-stu-id="d16b6-116">EcoResReleasedProductV2Entity</span></span>
      - <span data-ttu-id="d16b6-117">LogisticsAddressCityEntity</span><span class="sxs-lookup"><span data-stu-id="d16b6-117">LogisticsAddressCityEntity</span></span>
      - <span data-ttu-id="d16b6-118">LogisticsAddressCountryRegionTranslationEntity</span><span class="sxs-lookup"><span data-stu-id="d16b6-118">LogisticsAddressCountryRegionTranslationEntity</span></span>
      - <span data-ttu-id="d16b6-119">LogisticsAddressStateEntity</span><span class="sxs-lookup"><span data-stu-id="d16b6-119">LogisticsAddressStateEntity</span></span>
      - <span data-ttu-id="d16b6-120">PurchProcurementChargeCDSEntity</span><span class="sxs-lookup"><span data-stu-id="d16b6-120">PurchProcurementChargeCDSEntity</span></span>
      - <span data-ttu-id="d16b6-121">SalesChargeCDSEntity</span><span class="sxs-lookup"><span data-stu-id="d16b6-121">SalesChargeCDSEntity</span></span>
      - <span data-ttu-id="d16b6-122">TaxGroupEntity</span><span class="sxs-lookup"><span data-stu-id="d16b6-122">TaxGroupEntity</span></span>
      - <span data-ttu-id="d16b6-123">TaxItemGroupHeadingEntity</span><span class="sxs-lookup"><span data-stu-id="d16b6-123">TaxItemGroupHeadingEntity</span></span>
      - <span data-ttu-id="d16b6-124">VendVendorV2Entity</span><span class="sxs-lookup"><span data-stu-id="d16b6-124">VendVendorV2Entity</span></span>
4. <span data-ttu-id="d16b6-125">Configurare Dynamics 365 Regulatory Configuration Service (RCS).</span><span class="sxs-lookup"><span data-stu-id="d16b6-125">Set up the Dynamics 365 Regulatory Configuration Service (RCS).</span></span> 
5. <span data-ttu-id="d16b6-126">Creare una richiesta di servizio per Microsoft per abilitare le versioni di anteprima delle seguenti funzionalità:</span><span class="sxs-lookup"><span data-stu-id="d16b6-126">Create a service request for Microsoft to enable flighting of the following features:</span></span>

      - <span data-ttu-id="d16b6-127">ERCdsFeature</span><span class="sxs-lookup"><span data-stu-id="d16b6-127">ERCdsFeature</span></span>
      - <span data-ttu-id="d16b6-128">TaxServiceCDSFeature</span><span class="sxs-lookup"><span data-stu-id="d16b6-128">TaxServiceCDSFeature</span></span>

6. <span data-ttu-id="d16b6-129">Accedere all'area di lavoro **Gestione funzionalità** e abilitare le seguente funzionalità:</span><span class="sxs-lookup"><span data-stu-id="d16b6-129">Go to the **Feature management** workspace, and enable the following features:</span></span>

      - <span data-ttu-id="d16b6-130">(Anteprima) Supporto origini dati Dataverse per creazione di report elettronici</span><span class="sxs-lookup"><span data-stu-id="d16b6-130">(Preview) Electronic reporting Dataverse datasources support</span></span>
      - <span data-ttu-id="d16b6-131">(Anteprima) Supporto origini dati Dataverse per servizio imposte</span><span class="sxs-lookup"><span data-stu-id="d16b6-131">(Preview) Tax Service Dataverse datasources support</span></span>
      - <span data-ttu-id="d16b6-132">(Anteprima) Funzionalità di globalizzazione</span><span class="sxs-lookup"><span data-stu-id="d16b6-132">(Preview) Globalization features</span></span>

5. <span data-ttu-id="d16b6-133">Accedere a RCS utilizzando un account amministratore tenant.</span><span class="sxs-lookup"><span data-stu-id="d16b6-133">Sign in to RCS using a tenant admin account.</span></span>
6. <span data-ttu-id="d16b6-134">Selezionare **Creazione di report elettronici** > **Applicazioni connesse**.</span><span class="sxs-lookup"><span data-stu-id="d16b6-134">Go to **Electronic reporting** > **Connected applications**.</span></span> 
7. <span data-ttu-id="d16b6-135">Selezionare **Nuovo** per aggiungere un record e immettere le seguenti informazioni sul campo.</span><span class="sxs-lookup"><span data-stu-id="d16b6-135">Select **New** to add a record, and enter the following field information.</span></span> 

   - <span data-ttu-id="d16b6-136">Nel campo **Nome** immettere un nome.</span><span class="sxs-lookup"><span data-stu-id="d16b6-136">In the **Name** field, enter a name.</span></span>
   - <span data-ttu-id="d16b6-137">Nel campo **Tipo** selezionare **Dataverse**.</span><span class="sxs-lookup"><span data-stu-id="d16b6-137">In the **Type** field, select **Dataverse**.</span></span>
   - <span data-ttu-id="d16b6-138">Nel campo **Applicazione**, immettere l'URL di Dataverse.</span><span class="sxs-lookup"><span data-stu-id="d16b6-138">In the **Application** field, enter your Dataverse URL.</span></span>
   - <span data-ttu-id="d16b6-139">Nel campo **Tenant**, immettere il tenant.</span><span class="sxs-lookup"><span data-stu-id="d16b6-139">In the **Tenant** field, enter your tenant.</span></span>
   - <span data-ttu-id="d16b6-140">Nel campo **URL personalizzato**, immettere l'URL di Dataverse e aggiungilo con "/api/data/v9.1".</span><span class="sxs-lookup"><span data-stu-id="d16b6-140">In the **Custom URL** field, enter your Dataverse URL and append it with "/api/data/v9.1".</span></span>

8. <span data-ttu-id="d16b6-141">Selezionare **Verifica connessione** e terminare il processo di connessione.</span><span class="sxs-lookup"><span data-stu-id="d16b6-141">Select **Check connection**, and finish the connection process.</span></span> 

   <span data-ttu-id="d16b6-142">[![Pulsante Verifica connessione](./media/tax-service-setup-environment-for-mater-date-pic1.png)](./media/tax-service-setup-environment-for-mater-date-pic1.png)</span><span class="sxs-lookup"><span data-stu-id="d16b6-142">[![Check connection button](./media/tax-service-setup-environment-for-mater-date-pic1.png)](./media/tax-service-setup-environment-for-mater-date-pic1.png)</span></span>

9. <span data-ttu-id="d16b6-143">Selezionare **Creazione di report elettronici** > **Configurazioni fiscali** e importare le configurazioni fiscali da [Configurazioni fiscali](https://go.microsoft.com/fwlink/?linkid=2158352).</span><span class="sxs-lookup"><span data-stu-id="d16b6-143">Go to **Electronic reporting** > **Tax configurations**, and import tax configurations from [Tax configurations](https://go.microsoft.com/fwlink/?linkid=2158352).</span></span>

   <span data-ttu-id="d16b6-144">[![Pagina Configurazioni fiscali, albero del modello di dati fiscali](./media/tax-service-setup-environment-for-mater-date-pic2.png)](./media/tax-service-setup-environment-for-mater-date-pic2.png)</span><span class="sxs-lookup"><span data-stu-id="d16b6-144">[![Tax configurations page, Tax data model tree](./media/tax-service-setup-environment-for-mater-date-pic2.png)](./media/tax-service-setup-environment-for-mater-date-pic2.png)</span></span>

10. <span data-ttu-id="d16b6-145">Selezionare **Mapping modello di documento tassabile**, o **Mapping modello di Dataverse** se si utilizza una configurazione Microsoft e nel campo **Applicazione connessa** selezionare il record creato nel passaggio 7.</span><span class="sxs-lookup"><span data-stu-id="d16b6-145">Go to the **Taxable document model mapping**, or **Dataverse Model Mapping** if you are using a Microsoft configuration, and in the **Connected application** field, select the record that you created in step 7.</span></span>
11. <span data-ttu-id="d16b6-146">Impostare **Impostazione predefinita per mapping di modello** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="d16b6-146">Set **Default for model mapping** to **Yes**.</span></span>

   <span data-ttu-id="d16b6-147">[![Pagina Mapping modello](./media/tax-service-setup-environment-for-mater-date-pic3.png)](./media/tax-service-setup-environment-for-mater-date-pic3.png)</span><span class="sxs-lookup"><span data-stu-id="d16b6-147">[![Model mapping page](./media/tax-service-setup-environment-for-mater-date-pic3.png)](./media/tax-service-setup-environment-for-mater-date-pic3.png)</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
