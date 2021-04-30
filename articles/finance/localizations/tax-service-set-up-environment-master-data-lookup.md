---
title: Configurare un ambiente per la ricerca dei dati master
description: In questo argomento viene descritto come configurare l'ambiente per l'utilizzo della funzionalità di ricerca di dati master Calcolo imposte.
author: kai-cloud
ms.date: 03/31/2021
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
ms.openlocfilehash: eda093a75898bace2f3c7968933b83ccafa7fabb
ms.sourcegitcommit: 66095f1b7e0fd2756aa29fd7deb9ce5392b7e0b2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2021
ms.locfileid: "5869076"
---
# <a name="set-up-an-environment-for-master-data-lookup"></a><span data-ttu-id="731f6-103">Configurare un ambiente per la ricerca dei dati master</span><span class="sxs-lookup"><span data-stu-id="731f6-103">Set up an environment for master data lookup</span></span>

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

<span data-ttu-id="731f6-104">In questo argomento viene descritto come configurare l'ambiente per l'utilizzo della funzionalità di ricerca di dati master Calcolo imposte.</span><span class="sxs-lookup"><span data-stu-id="731f6-104">This topic explains how to set up your environment to use the Tax Calculation master data lookup functionality.</span></span>

1. <span data-ttu-id="731f6-105">Configurare l'integrazione di Power Platform in Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="731f6-105">Set up power platform integration in Lifecycle Services (LCS).</span></span> <span data-ttu-id="731f6-106">Per ulteriori informazioni, vedere [Panoramica di Integrazione di Microsoft Power Platform - Componenti aggiuntivi](../../fin-ops-core/dev-itpro/power-platform/add-ins-overview.md).</span><span class="sxs-lookup"><span data-stu-id="731f6-106">For more information, see [Microsoft Power Platform integration - Add-ins overview](../../fin-ops-core/dev-itpro/power-platform/add-ins-overview.md).</span></span>
2. <span data-ttu-id="731f6-107">Configurare Dynamics 365 Finance e Microsoft Dataverse.</span><span class="sxs-lookup"><span data-stu-id="731f6-107">Set up Dynamics 365 Finance and Microsoft Dataverse.</span></span> <span data-ttu-id="731f6-108">Per ulteriori informazioni, vedere [Ottenere la soluzione](../../fin-ops-core/dev-itpro/power-platform/admin-reference.md#getting-the-solution) e [Autenticazione e autorizzazione](../../fin-ops-core/dev-itpro/power-platform/admin-reference.md#authentication-and-authorization).</span><span class="sxs-lookup"><span data-stu-id="731f6-108">For more information, see [Getting the solution](../../fin-ops-core/dev-itpro/power-platform/admin-reference.md#getting-the-solution) and [Authentication and authorization](../../fin-ops-core/dev-itpro/power-platform/admin-reference.md#authentication-and-authorization).</span></span>
3. <span data-ttu-id="731f6-109">Importare la *soluzione per entità virtuale del servizio fiscale prerequisito* da [Entità virtuale servizio fiscale](https://go.microsoft.com/fwlink/?linkid=2158160).</span><span class="sxs-lookup"><span data-stu-id="731f6-109">Import the *Prerequisite tax service virtual entity solution* from the [Tax service virtual entity](https://go.microsoft.com/fwlink/?linkid=2158160).</span></span>
4. <span data-ttu-id="731f6-110">Configurare Dynamics 365 Regulatory Configuration Service (RCS).</span><span class="sxs-lookup"><span data-stu-id="731f6-110">Set up the Dynamics 365 Regulatory Configuration Service (RCS).</span></span> 
5. <span data-ttu-id="731f6-111">Creare una richiesta di servizio per Microsoft per abilitare le versioni di anteprima delle seguenti funzionalità:</span><span class="sxs-lookup"><span data-stu-id="731f6-111">Create a service request for Microsoft to enable flighting of the following features:</span></span>

      - <span data-ttu-id="731f6-112">ERCdsFeature</span><span class="sxs-lookup"><span data-stu-id="731f6-112">ERCdsFeature</span></span>
      - <span data-ttu-id="731f6-113">TaxServiceCDSFeature</span><span class="sxs-lookup"><span data-stu-id="731f6-113">TaxServiceCDSFeature</span></span>

6. <span data-ttu-id="731f6-114">In Finance, accedere all'area di lavoro **Gestione funzionalità** e abilitare le seguente funzionalità:</span><span class="sxs-lookup"><span data-stu-id="731f6-114">In Finance, go to the **Feature management** workspace, and enable the following features:</span></span>

      - <span data-ttu-id="731f6-115">(Anteprima) Supporto origini dati Dataverse per creazione di report elettronici</span><span class="sxs-lookup"><span data-stu-id="731f6-115">(Preview) Electronic reporting Dataverse datasources support</span></span>
      - <span data-ttu-id="731f6-116">(Anteprima) Supporto origini dati Dataverse per servizio imposte</span><span class="sxs-lookup"><span data-stu-id="731f6-116">(Preview) Tax Service Dataverse datasources support</span></span>
      - <span data-ttu-id="731f6-117">(Anteprima) Funzionalità di globalizzazione</span><span class="sxs-lookup"><span data-stu-id="731f6-117">(Preview) Globalization features</span></span>

5. <span data-ttu-id="731f6-118">Accedere a RCS utilizzando un account amministratore tenant.</span><span class="sxs-lookup"><span data-stu-id="731f6-118">Sign in to RCS using a tenant admin account.</span></span>
6. <span data-ttu-id="731f6-119">Selezionare **Creazione di report elettronici** > **Applicazioni connesse**.</span><span class="sxs-lookup"><span data-stu-id="731f6-119">Go to **Electronic reporting** > **Connected applications**.</span></span> 
7. <span data-ttu-id="731f6-120">Selezionare **Nuovo** per aggiungere un record e immettere le seguenti informazioni sul campo.</span><span class="sxs-lookup"><span data-stu-id="731f6-120">Select **New** to add a record, and enter the following field information.</span></span> 

   - <span data-ttu-id="731f6-121">Nel campo **Nome** immettere un nome.</span><span class="sxs-lookup"><span data-stu-id="731f6-121">In the **Name** field, enter a name.</span></span>
   - <span data-ttu-id="731f6-122">Nel campo **Tipo** selezionare **Dataverse**.</span><span class="sxs-lookup"><span data-stu-id="731f6-122">In the **Type** field, select **Dataverse**.</span></span>
   - <span data-ttu-id="731f6-123">Nel campo **Applicazione**, immettere l'URL di Dataverse.</span><span class="sxs-lookup"><span data-stu-id="731f6-123">In the **Application** field, enter your Dataverse URL.</span></span>
   - <span data-ttu-id="731f6-124">Nel campo **Tenant**, immettere il tenant.</span><span class="sxs-lookup"><span data-stu-id="731f6-124">In the **Tenant** field, enter your tenant.</span></span>
   - <span data-ttu-id="731f6-125">Nel campo **URL personalizzato**, immettere l'URL di Dataverse e aggiungilo con "/api/data/v9.1".</span><span class="sxs-lookup"><span data-stu-id="731f6-125">In the **Custom URL** field, enter your Dataverse URL and append it with "/api/data/v9.1".</span></span>

8. <span data-ttu-id="731f6-126">Selezionare **Verifica connessione** e terminare il processo di connessione.</span><span class="sxs-lookup"><span data-stu-id="731f6-126">Select **Check connection**, and finish the connection process.</span></span> 

   <span data-ttu-id="731f6-127">[![Pulsante Verifica connessione](./media/tax-service-setup-environment-for-mater-date-pic1.png)](./media/tax-service-setup-environment-for-mater-date-pic1.png)</span><span class="sxs-lookup"><span data-stu-id="731f6-127">[![Check connection button](./media/tax-service-setup-environment-for-mater-date-pic1.png)](./media/tax-service-setup-environment-for-mater-date-pic1.png)</span></span>

9. <span data-ttu-id="731f6-128">Selezionare **Creazione di report elettronici** > **Configurazioni fiscali** e importare le configurazioni fiscali da [Configurazioni fiscali](https://go.microsoft.com/fwlink/?linkid=2158352).</span><span class="sxs-lookup"><span data-stu-id="731f6-128">Go to **Electronic reporting** > **Tax configurations**, and import tax configurations from [Tax configurations](https://go.microsoft.com/fwlink/?linkid=2158352).</span></span>

   <span data-ttu-id="731f6-129">[![Pagina Configurazioni fiscali, albero del modello di dati fiscali](./media/tax-service-setup-environment-for-mater-date-pic2.png)](./media/tax-service-setup-environment-for-mater-date-pic2.png)</span><span class="sxs-lookup"><span data-stu-id="731f6-129">[![Tax configurations page, Tax data model tree](./media/tax-service-setup-environment-for-mater-date-pic2.png)](./media/tax-service-setup-environment-for-mater-date-pic2.png)</span></span>

10. <span data-ttu-id="731f6-130">Selezionare **Mapping modello di documento tassabile**, o **Mapping modello di Dataverse** se si utilizza una configurazione Microsoft e nel campo **Applicazione connessa** selezionare il record creato nel passaggio 7.</span><span class="sxs-lookup"><span data-stu-id="731f6-130">Go to the **Taxable document model mapping**, or **Dataverse Model Mapping** if you are using a Microsoft configuration, and in the **Connected application** field, select the record that you created in step 7.</span></span>
11. <span data-ttu-id="731f6-131">Impostare **Impostazione predefinita per mapping di modello** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="731f6-131">Set **Default for model mapping** to **Yes**.</span></span>

   <span data-ttu-id="731f6-132">[![Pagina Mapping modello](./media/tax-service-setup-environment-for-mater-date-pic3.png)](./media/tax-service-setup-environment-for-mater-date-pic3.png)</span><span class="sxs-lookup"><span data-stu-id="731f6-132">[![Model mapping page](./media/tax-service-setup-environment-for-mater-date-pic3.png)](./media/tax-service-setup-environment-for-mater-date-pic3.png)</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
