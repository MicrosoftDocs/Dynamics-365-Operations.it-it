---
title: Prospect to cash
description: Questo argomento offre una panoramica della soluzione Prospect to cash tra Dynamics 365 Supply Chain Management e Dynamics 365 Sales.
author: ChristianRytt
manager: tfehr
ms.date: 04/25/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustTable, SalesTable, EcoResProductListPage
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: crytt
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.openlocfilehash: 55c39fac40498488519fcb539b3c3f7560a46b30
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4431076"
---
# <a name="prospect-to-cash"></a><span data-ttu-id="ad378-103">Prospect per uno scenario di liquidazione</span><span class="sxs-lookup"><span data-stu-id="ad378-103">Prospect to cash</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ad378-104">La soluzione Prospect to cash consente la sincronizzazione diretta tra Dynamics 365 Supply Chain Management e Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="ad378-104">The Prospect to cash solution provides direct synchronization across Dynamics 365 Supply Chain Management and Dynamics 365 Sales.</span></span> <span data-ttu-id="ad378-105">I modelli Prospect to cash disponibili con la funzionalità Integrazione dati consentono il flusso di dati relativo a conti, contatti, prodotti, offerte di vendita, ordini cliente e fatture di vendita.</span><span class="sxs-lookup"><span data-stu-id="ad378-105">The Prospect to cash templates that are available with the Data Integration feature enable the flow of data for accounts, contacts, products, sales quotations, sales orders, and sales invoices.</span></span> <span data-ttu-id="ad378-106">Quando i dati fluiscono, è possibile eseguire attività di vendita e di marketing in Sales e gestire la compilazione degli ordini utilizzando la gestione dell'inventario di Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="ad378-106">While data is flowing, you can perform sales and marketing activities in Sales, and you can handle order fulfillment by using inventory management in Supply Chain Management.</span></span> 

<span data-ttu-id="ad378-107">Per ulteriori informazioni sull'integrazione di Prospect to cash, vedere il video su YouTube [Prospect to cash integration](https://www.youtube.com/watch?v=AVV9x5x-XCg).</span><span class="sxs-lookup"><span data-stu-id="ad378-107">For more information about the Prospect to cash integration, watch the short YouTube video [Prospect to cash integration](https://www.youtube.com/watch?v=AVV9x5x-XCg).</span></span>

<span data-ttu-id="ad378-108">Nella versione corrente, la soluzione Prospect to cash offre i seguenti tipi di sincronizzazione diretta:</span><span class="sxs-lookup"><span data-stu-id="ad378-108">In the current version, the Prospect to cash solution provides the following types of direct synchronization:</span></span>

- [<span data-ttu-id="ad378-109">Sincronizzare conti direttamente da Sales con clienti in Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="ad378-109">Synchronize accounts directly from Sales to customers in Supply Chain Management</span></span>](accounts-template-mapping-direct.md)
- [<span data-ttu-id="ad378-110">Sincronizzare prodotti direttamente da Supply Chain Management con prodotti in Sales</span><span class="sxs-lookup"><span data-stu-id="ad378-110">Synchronize products directly from Supply Chain Management to products in Sales</span></span>](products-template-mapping-direct.md)
- [<span data-ttu-id="ad378-111">Sincronizzare contatti direttamente da Sales con contatti o clienti in Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="ad378-111">Synchronize contacts directly from Sales to contacts or customers in Supply Chain Management</span></span>](contacts-template-mapping-direct.md)
- [<span data-ttu-id="ad378-112">Sincronizzare intestazioni e righe di offerte di vendita direttamente da Sales in Supply Chain Management…</span><span class="sxs-lookup"><span data-stu-id="ad378-112">Synchronize sales quotation headers and lines directly from Sales to Supply Chain Management</span></span>](sales-quotation-template-mapping-sales-fin.md)
- [<span data-ttu-id="ad378-113">Sincronizzazione degli ordini cliente direttamente tra Sales e Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="ad378-113">Synchronization of sales orders directly between Sales and Supply Chain Management</span></span>](sales-order-template-mapping-direct-two-ways.md)
- [<span data-ttu-id="ad378-114">Sincronizzare intestazioni e righe di fatture di vendita direttamente da Supply Chain Management in Sales</span><span class="sxs-lookup"><span data-stu-id="ad378-114">Synchronize sales invoice headers and lines directly from Supply Chain Management to Sales</span></span>](sales-invoice-template-mapping-direct.md)

## <a name="system-requirements-for-supply-chain-management"></a><span data-ttu-id="ad378-115">Requisiti di sistema per Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="ad378-115">System requirements for Supply Chain Management</span></span>
<span data-ttu-id="ad378-116">L'integrazione Prospect to cash è supportata nelle seguenti versioni:</span><span class="sxs-lookup"><span data-stu-id="ad378-116">Prospect to cash integration is supported on the following versions:</span></span>

### <a name="microsoft-dynamics-365-for-finance-and-operations-enterprise-edition-73-december-2017"></a><span data-ttu-id="ad378-117">Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition 7.3 (dicembre 2017)</span><span class="sxs-lookup"><span data-stu-id="ad378-117">Microsoft Dynamics 365 for Finance and Operations, Enterprise edition 7.3 (December 2017)</span></span>

- <span data-ttu-id="ad378-118">Dynamics 365 for Finance and Operations, Enterprise Edition (dicembre 2017) - Build applicazione 7.3.11971.56116 con aggiornamento 12 della piattaforma (7.0.4709.41129)</span><span class="sxs-lookup"><span data-stu-id="ad378-118">Dynamics 365 for Finance and Operations, Enterprise edition (December 2017) - Application build 7.3.11971.56116 with Platform Update 12 (7.0.4709.41129)</span></span>

### <a name="dynamics-365-for-finance-and-operations-enterprise-edition-july-2017"></a><span data-ttu-id="ad378-119">Dynamics 365 for Finance and Operations, Enterprise edition (luglio 2017)</span><span class="sxs-lookup"><span data-stu-id="ad378-119">Dynamics 365 for Finance and Operations, Enterprise edition (July 2017)</span></span>

- <span data-ttu-id="ad378-120">Dynamics 365 for Finance and Operations, Enterprise edition (July 2017) - Con aggiornamento 8 della piattaforma (build applicazione 7.2.11792.56024 con build piattaforma 7.0.4565.16212).</span><span class="sxs-lookup"><span data-stu-id="ad378-120">Dynamics 365 for Finance and Operations, Enterprise edition (July 2017) - with platform update 8 (application build 7.2.11792.56024 with platform build 7.0.4565.16212).</span></span>
- <span data-ttu-id="ad378-121">Sono necessari i seguenti aggiornamenti rapidi:</span><span class="sxs-lookup"><span data-stu-id="ad378-121">The following hotfixes are required:</span></span>

  - <span data-ttu-id="ad378-122">**[KB4045570](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4045570&bugId=3851320&qc=ac1145034fd04ab71ccc4d14aa012f245176712c9af7c36bb77a118726d46160)** - Questo hotfix consente la sincronizzazione degli ordini cliente da Sales in Supply Chain Management tramite la funzionalità Integrazione dati.</span><span class="sxs-lookup"><span data-stu-id="ad378-122">**[KB4045570](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4045570&bugId=3851320&qc=ac1145034fd04ab71ccc4d14aa012f245176712c9af7c36bb77a118726d46160)** – This hotfix enables sales order synchronization from Sales to Supply Chain Management via the Data Integration feature.</span></span> <span data-ttu-id="ad378-123">Sono inoltre presenti molti altri miglioramenti.</span><span class="sxs-lookup"><span data-stu-id="ad378-123">It also provides several other enhancements.</span></span>
  - <span data-ttu-id="ad378-124">**[KB4036524](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4036524&bugId=3847504&qc=e2fcfae08b1a5d5ce9f53f330e8c212b0636c375368ff7d8d9b5ec6701523ad2)** - Questo hotfix consente la sincronizzazione delle righe degli ordini cliente da Supply Chain Management in Sales tramite la funzionalità Integrazione dati.</span><span class="sxs-lookup"><span data-stu-id="ad378-124">**[KB4036524](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4036524&bugId=3847504&qc=e2fcfae08b1a5d5ce9f53f330e8c212b0636c375368ff7d8d9b5ec6701523ad2)** – This hotfix enables sales order line synchronization from Supply Chain Management to Sales via the Data Integration feature.</span></span>
  - <span data-ttu-id="ad378-125">**[KB4036461](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4036461&bugId=3847029&qc=e2fcfae08b1a5d5ce9f53f330e8c212b0636c375368ff7d8d9b5ec6701523ad2)** - Questo hotfix consente la sincronizzazione degli ordini cliente da Supply Chain Management in Sales tramite la funzionalità Integrazione dati.</span><span class="sxs-lookup"><span data-stu-id="ad378-125">**[KB4036461](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4036461&bugId=3847029&qc=e2fcfae08b1a5d5ce9f53f330e8c212b0636c375368ff7d8d9b5ec6701523ad2)** – This hotfix enables sales order synchronization from Supply Chain Management to Sales via the Data Integration feature.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ad378-126">È necessario installare solo KB4045570 poiché l'installazione include le modifiche di altri aggiornamenti rapidi.</span><span class="sxs-lookup"><span data-stu-id="ad378-126">You only have to install KB4045570 because the installation includes the changes from other hotfixes.</span></span> 

### <a name="dynamics-365-for-finance-and-operations-version-1611-november-2016"></a><span data-ttu-id="ad378-127">Dynamics 365 for Finance and Operations versione 1611 (novembre 2016)</span><span class="sxs-lookup"><span data-stu-id="ad378-127">Dynamics 365 for Finance and Operations version 1611 (November 2016)</span></span>

- <span data-ttu-id="ad378-128">Dynamics 365 for Finance and Operations versione 1611 (novembre 2016) con aggiornamento della piattaforma 8 o successivo</span><span class="sxs-lookup"><span data-stu-id="ad378-128">Dynamics 365 for Finance and Operations version 1611 (November 2016)  with platform update 8 or higher</span></span>

- <span data-ttu-id="ad378-129">Sono necessari i seguenti aggiornamenti rapidi:</span><span class="sxs-lookup"><span data-stu-id="ad378-129">The following hotfixes are required:</span></span>

  - <span data-ttu-id="ad378-130">**[KB4051266](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4051266&bugId=3863566&qc=ee80faaa7bc6c77b368d5eaf456c9c08e0b9fba5903a7b6fd8c13756c3a4b757)** - Consente la sincronizzazione degli ordini cliente con l'integratore di dati da Supply Chain Management a Sales.</span><span class="sxs-lookup"><span data-stu-id="ad378-130">**[KB4051266](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4051266&bugId=3863566&qc=ee80faaa7bc6c77b368d5eaf456c9c08e0b9fba5903a7b6fd8c13756c3a4b757)** - Enable sales order synchronization with Data integrator from Supply Chain Management to Sales.</span></span> 
  - <span data-ttu-id="ad378-131">**[KB4037542](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4037542&bugId=3848253&qc=8323b93c15280172c5ab4159e0256e37104ced1729462c91ab2f7d00cb8d419c)** - Consente la sincronizzazione delle righe e delle intestazioni degli ordini cliente con l'integratore di dati da Supply Chain Management a Sales.</span><span class="sxs-lookup"><span data-stu-id="ad378-131">**[KB4037542](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4037542&bugId=3848253&qc=8323b93c15280172c5ab4159e0256e37104ced1729462c91ab2f7d00cb8d419c)** - Enable sales order header and line synchronization with Data integrator from Supply Chain Management to Sales.</span></span>
  - <span data-ttu-id="ad378-132">**[KB4033093](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4033093&bugId=3824604&qc=bd7e15e1fb56066b3a82ce48b691cf1ffbc934a7473fa888545b2211a8d416c5)** - È richiesto il supporto per l'integrazione della soluzione Prospect to cash tramite le entità di dati.</span><span class="sxs-lookup"><span data-stu-id="ad378-132">**[KB4033093](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4033093&bugId=3824604&qc=bd7e15e1fb56066b3a82ce48b691cf1ffbc934a7473fa888545b2211a8d416c5)** - Support for prospect to cash integration through data entities is required.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="ad378-133">Dopo l'installazione degli aggiornamenti rapidi, è necessario attivare il seguente processo batch dal modulo **SalesPopulateProspectToCash**.</span><span class="sxs-lookup"><span data-stu-id="ad378-133">After you install the hotfixes, you must trigger the following batch job from the **SalesPopulateProspectToCash** form.</span></span> <span data-ttu-id="ad378-134">Questo modulo è nascosto poiché serve una sola volta.</span><span class="sxs-lookup"><span data-stu-id="ad378-134">This form is hidden because you only need it once.</span></span> <span data-ttu-id="ad378-135">Per accedere al modulo, accedere all'ambiente e aggiungere quanto segue all'URL nell'indirizzo del browser: *&mi=action:SalesPopulateProspectToCash*, ad esempio, `https://ax123456.cloud.test.dynamics.com/?cmp=USMF&mi=action:SalesPopulateProspectToCash`.</span><span class="sxs-lookup"><span data-stu-id="ad378-135">To access the form, log in to the environment and add the following to the URL in your browser address: *&mi=action:SalesPopulateProspectToCash*, for example, `https://ax123456.cloud.test.dynamics.com/?cmp=USMF&mi=action:SalesPopulateProspectToCash`.</span></span> <span data-ttu-id="ad378-136">Quando il modulo si apre, fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="ad378-136">When the form opens, click OK.</span></span> <span data-ttu-id="ad378-137">Il modulo viene popolato con un nuovo campo **LineCreationSequnceNumber** nelle tabelle **SalesLine**, **SalesQuotationLine** e **CustInvoiceTrans** con valori univoci e l'elenco prodotti verrà aggiornato.</span><span class="sxs-lookup"><span data-stu-id="ad378-137">This will populate a new **LineCreationSequnceNumber** field in the **SalesLine**, **SalesQuotationLine**, and **CustInvoiceTrans** tables with unique values, and the product list will be refreshed.</span></span> <span data-ttu-id="ad378-138">Questa operazione è necessaria per il funzionamento dell'integrazione Prospect to cash.</span><span class="sxs-lookup"><span data-stu-id="ad378-138">This is required for the Prospect to cash integration to work.</span></span>


## <a name="system-requirements-for-sales"></a><span data-ttu-id="ad378-139">Requisiti di sistema per Sales</span><span class="sxs-lookup"><span data-stu-id="ad378-139">System requirements for Sales</span></span>

<span data-ttu-id="ad378-140">Per utilizzare la soluzione Prospect to cash, è necessario installare i componenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="ad378-140">To use the Prospect to cash solution, you must install the following components:</span></span>

- <span data-ttu-id="ad378-141">Dynamics 365 Sales versione 1612 (8.2.1.207) (DB 8.2.1.207) online o una versione successiva</span><span class="sxs-lookup"><span data-stu-id="ad378-141">Dynamics 365 Sales version 1612 (8.2.1.207) (DB 8.2.1.207) online or a later version</span></span>
- <span data-ttu-id="ad378-142">Soluzione Prospect to Cash per Dynamics 365 Sales, versione 1.15.0.0 o una versione successiva.</span><span class="sxs-lookup"><span data-stu-id="ad378-142">Prospect to cash solution for Dynamics 365 Sales, version 1.15.0.0 or a later version.</span></span> <span data-ttu-id="ad378-143">La soluzione può essere scaricata da AppSource.</span><span class="sxs-lookup"><span data-stu-id="ad378-143">The solution is available for download from AppSource.</span></span> <span data-ttu-id="ad378-144">[Scaricare Dynamics 365, Prospect to Cash](https://appsource.microsoft.com/product/dynamics-365/mscrm.c7a48b40-eed3-4d67-93ba-f2364281feb3).</span><span class="sxs-lookup"><span data-stu-id="ad378-144">[Download Dynamics 365, Prospect to Cash](https://appsource.microsoft.com/product/dynamics-365/mscrm.c7a48b40-eed3-4d67-93ba-f2364281feb3).</span></span>
