---
title: Prospect to cash
description: Questo argomento offre una panoramica della soluzione Prospect to cash tra Microsoft Dynamics 365 for Finance and Operations, Enterprise edition e Microsoft Dynamics 365 for Sales.
author: ChristianRytt
manager: AnnBe
ms.date: 02/08/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CustTable, SalesTable, EcoResProductListPage
audience: Application User, IT Pro
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: crytt
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: 95d5bf26c22238753586cf4a7aaf5c26f061a705
ms.openlocfilehash: 62f328c5a6bf5343c97de0b7d907bbcfe2fcde4d
ms.contentlocale: it-it
ms.lasthandoff: 02/23/2018

---

# <a name="prospect-to-cash"></a><span data-ttu-id="2608a-103">Prospect to cash</span><span class="sxs-lookup"><span data-stu-id="2608a-103">Prospect to cash</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="2608a-104">La soluzione Prospect to cash consente la sincronizzazione diretta tra Dynamics 365 for Finance and Operations, Enterprise Edition e Dynamics 365 for Sales.</span><span class="sxs-lookup"><span data-stu-id="2608a-104">The Prospect to cash solution provides direct synchronization across Dynamics 365 for Finance and Operations, Enterprise edition, and Dynamics 365 for Sales.</span></span> <span data-ttu-id="2608a-105">I modelli Prospect to cash disponibili con la funzionalità Integrazione dati consentono il flusso di dati relativo a conti, contatti, prodotti, offerte di vendita, ordini cliente e fatture di vendita tra Finance and Operations e Sales.</span><span class="sxs-lookup"><span data-stu-id="2608a-105">The Prospect to cash templates that are available with the Data Integration feature enable the flow of data for accounts, contacts, products, sales quotations, sales orders, and sales invoices between Finance and Operations and Sales.</span></span> <span data-ttu-id="2608a-106">Quando i dati fluiscono tra Finance and Operations e Sales, è possibile eseguire attività di vendita e di marketing in Sales e gestire la compilazione degli ordini utilizzando la gestione dell'inventario di Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="2608a-106">While data is flowing between Finance and Operations and Sales, you can perform sales and marketing activities in Sales, and you can handle order fulfillment by using inventory management in Finance and Operations.</span></span> 

<span data-ttu-id="2608a-107">Per ulteriori informazioni sull'integrazione Prospect to cash, guardare un breve video su YouTube:</span><span class="sxs-lookup"><span data-stu-id="2608a-107">For more information about the Prospect to cash integration, watch the short YouTube video:</span></span>

> [!Video https://www.youtube.com/embed/AVV9x5x-XCg]

<span data-ttu-id="2608a-108">Nella versione corrente, la soluzione Prospect to cash offre i seguenti tipi di sincronizzazione diretta:</span><span class="sxs-lookup"><span data-stu-id="2608a-108">In the current version, the Prospect to cash solution provides the following types of direct synchronization:</span></span>

- [<span data-ttu-id="2608a-109">Gestione degli account in Sales e sincronizzazione direttamente da Sales in Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="2608a-109">Maintain accounts in Sales and sync them directly from Sales to Finance and Operations</span></span>](accounts-template-mapping-direct.md)
- [<span data-ttu-id="2608a-110">Gestire i prodotti in Finance and Operations e sincronizzarli direttamente in Sales.</span><span class="sxs-lookup"><span data-stu-id="2608a-110">Maintain products in Finance and Operations and sync them directly to Sales</span></span>](products-template-mapping-direct.md)
- [<span data-ttu-id="2608a-111">Gestire i contatti in Sales e sincronizzarli direttamente con contatti o clienti in Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="2608a-111">Maintain contacts in Sales and sync them directly to contacts or customers in Finance and Operations</span></span>](contacts-template-mapping-direct.md)
- [<span data-ttu-id="2608a-112">Sincronizzare offerte di vendita direttamente da Sales in Finance and Operations dell'integrazione (versione con modello in sospeso)</span><span class="sxs-lookup"><span data-stu-id="2608a-112">Synchronize sales quotation directly from Sales to Finance and Operations (template pending release)</span></span>](sales-quotation-template-mapping-sales-fin.md)
- [<span data-ttu-id="2608a-113">Sincronizzare direttamente gli ordini cliente da Finance and Operations in Sales</span><span class="sxs-lookup"><span data-stu-id="2608a-113">Synchronize sales orders directly from Finance and Operations to Sales</span></span>](sales-order-template-mapping-direct.md)
- [<span data-ttu-id="2608a-114">Sincronizzare direttamente gli ordini cliente tra Sales e Finance and Operations (versione con modello in sospeso)</span><span class="sxs-lookup"><span data-stu-id="2608a-114">Synchronize sales orders directly between Sales and Finance and Operations (template pending release)</span></span>](sales-order-template-mapping-direct-two-ways.md)
- [<span data-ttu-id="2608a-115">Sincronizzare direttamente le fatture cliente da Finance and Operations in Sales</span><span class="sxs-lookup"><span data-stu-id="2608a-115">Synchronize sales invoice directly from Finance and Operations to Sales</span></span>](sales-invoice-template-mapping-direct.md)

## <a name="system-requirements-for-finance-and-operations"></a><span data-ttu-id="2608a-116">Requisiti di sistema di Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="2608a-116">System requirements for Finance and Operations</span></span>

<span data-ttu-id="2608a-117">L'integrazione Prospect to cash è supportata nelle seguenti versioni:</span><span class="sxs-lookup"><span data-stu-id="2608a-117">Prospect to cash integration is supported on the following versions:</span></span>

### <a name="microsoft-dynamics-365-for-finance-and-operations-enterprise-edition-73-december-2017"></a><span data-ttu-id="2608a-118">Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition 7.3 (dicembre 2017)</span><span class="sxs-lookup"><span data-stu-id="2608a-118">Microsoft Dynamics 365 for Finance and Operations, Enterprise edition 7.3 (December 2017)</span></span>

- <span data-ttu-id="2608a-119">Dynamics 365 for Finance and Operations, Enterprise Edition (dicembre 2017) - Build applicazione 7.3.11971.56116 con aggiornamento 12 della piattaforma (7.0.4709.41129)</span><span class="sxs-lookup"><span data-stu-id="2608a-119">Dynamics 365 for Finance and Operations, Enterprise edition (December 2017) - Application build 7.3.11971.56116 with Platform Update 12 (7.0.4709.41129)</span></span>

### <a name="dynamics-365-for-finance-and-operations-enterprise-edition-july-2017"></a><span data-ttu-id="2608a-120">Dynamics 365 for Finance and Operations, Enterprise Edition (luglio 2017)</span><span class="sxs-lookup"><span data-stu-id="2608a-120">Dynamics 365 for Finance and Operations, Enterprise edition (July 2017)</span></span>

- <span data-ttu-id="2608a-121">Dynamics 365 for Finance and Operations, Enterprise Edition (luglio 2017) - Con aggiornamento 8 della piattaforma (build applicazione 7.2.11792.56024 con build piattaforma 7.0.4565.16212).</span><span class="sxs-lookup"><span data-stu-id="2608a-121">Dynamics 365 for Finance and Operations, Enterprise edition (July 2017) - with platform update 8 (application build 7.2.11792.56024 with platform build 7.0.4565.16212).</span></span>
- <span data-ttu-id="2608a-122">Sono necessari i seguenti aggiornamenti rapidi:</span><span class="sxs-lookup"><span data-stu-id="2608a-122">The following hotfixes are required:</span></span>

    - <span data-ttu-id="2608a-123">**[KB4045570](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4045570&bugId=3851320&qc=ac1145034fd04ab71ccc4d14aa012f245176712c9af7c36bb77a118726d46160)** - Questo hotfix consente la sincronizzazione degli ordini cliente da Sales in Finance and Operations tramite la funzionalità Integrazione dati.</span><span class="sxs-lookup"><span data-stu-id="2608a-123">**[KB4045570](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4045570&bugId=3851320&qc=ac1145034fd04ab71ccc4d14aa012f245176712c9af7c36bb77a118726d46160)** – This hotfix enables sales order synchronization from Sales to Finance and Operations via the Data Integration feature.</span></span> <span data-ttu-id="2608a-124">Sono inoltre presenti molti altri miglioramenti.</span><span class="sxs-lookup"><span data-stu-id="2608a-124">It also provides several other enhancements.</span></span>
    - <span data-ttu-id="2608a-125">**[KB4036524](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4036524&bugId=3847504&qc=e2fcfae08b1a5d5ce9f53f330e8c212b0636c375368ff7d8d9b5ec6701523ad2)** - Questo hotfix consente la sincronizzazione delle righe degli ordini cliente da Finance and Operations in Sales tramite la funzionalità Integrazione dati.</span><span class="sxs-lookup"><span data-stu-id="2608a-125">**[KB4036524](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4036524&bugId=3847504&qc=e2fcfae08b1a5d5ce9f53f330e8c212b0636c375368ff7d8d9b5ec6701523ad2)** – This hotfix enables sales order line synchronization from Finance and Operations to Sales via the Data Integration feature.</span></span>
    - <span data-ttu-id="2608a-126">**[KB4036461](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4036461&bugId=3847029&qc=e2fcfae08b1a5d5ce9f53f330e8c212b0636c375368ff7d8d9b5ec6701523ad2)** - Questo hotfix consente la sincronizzazione degli ordini cliente da Finance and Operations in Sales tramite la funzionalità Integrazione dati.</span><span class="sxs-lookup"><span data-stu-id="2608a-126">**[KB4036461](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4036461&bugId=3847029&qc=e2fcfae08b1a5d5ce9f53f330e8c212b0636c375368ff7d8d9b5ec6701523ad2)** – This hotfix enables sales order synchronization from Finance and Operations to Sales via the Data Integration feature.</span></span>

    > [!NOTE]
    > <span data-ttu-id="2608a-127">È necessario installare solo KB4045570 poiché l'installazione include le modifiche di altri aggiornamenti rapidi.</span><span class="sxs-lookup"><span data-stu-id="2608a-127">You only have to install KB4045570 because the installation includes the changes from other hotfixes.</span></span> 

### <a name="dynamics-365-for-finance-and-operations-version-1611-november-2016"></a><span data-ttu-id="2608a-128">Dynamics 365 for Finance and Operations versione 1611 (novembre 2016)</span><span class="sxs-lookup"><span data-stu-id="2608a-128">Dynamics 365 for Finance and Operations version 1611 (November 2016)</span></span>

- <span data-ttu-id="2608a-129">Microsoft Dynamics 365 for Finance and Operations versione 1611 (novembre 2016) con aggiornamento della piattaforma 8 o successivo</span><span class="sxs-lookup"><span data-stu-id="2608a-129">Dynamics 365 for Finance and Operations version 1611 (November 2016)  with platform update 8 or higher</span></span>

- <span data-ttu-id="2608a-130">Sono necessari i seguenti aggiornamenti rapidi:</span><span class="sxs-lookup"><span data-stu-id="2608a-130">The following hotfixes are required:</span></span>

    - <span data-ttu-id="2608a-131">**[KB4051266](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4051266&bugId=3863566&qc=ee80faaa7bc6c77b368d5eaf456c9c08e0b9fba5903a7b6fd8c13756c3a4b757)** - Consente la sincronizzazione degli ordini cliente con l'integratore di dati da Finance and Operations a Sales.</span><span class="sxs-lookup"><span data-stu-id="2608a-131">**[KB4051266](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4051266&bugId=3863566&qc=ee80faaa7bc6c77b368d5eaf456c9c08e0b9fba5903a7b6fd8c13756c3a4b757)** - Enable sales order synchronization with Data integrator from Finance and Operations to Sales.</span></span> 
    - <span data-ttu-id="2608a-132">**[KB4037542](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4037542&bugId=3848253&qc=8323b93c15280172c5ab4159e0256e37104ced1729462c91ab2f7d00cb8d419c)** - Consente la sincronizzazione di intestazione e riga con l'integratore di dati da Finance and Operations a Sales.</span><span class="sxs-lookup"><span data-stu-id="2608a-132">**[KB4037542](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4037542&bugId=3848253&qc=8323b93c15280172c5ab4159e0256e37104ced1729462c91ab2f7d00cb8d419c)** - Enable sales order header and line synchronization with Data integrator from Finance and Operations to Sales.</span></span>
    - <span data-ttu-id="2608a-133">**[KB4033093](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4033093&bugId=3824604&qc=bd7e15e1fb56066b3a82ce48b691cf1ffbc934a7473fa888545b2211a8d416c5)** - È richiesto il supporto per l'integrazione della soluzione Prospect to cash tramite le entità di dati.</span><span class="sxs-lookup"><span data-stu-id="2608a-133">**[KB4033093](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4033093&bugId=3824604&qc=bd7e15e1fb56066b3a82ce48b691cf1ffbc934a7473fa888545b2211a8d416c5)** - Support for prospect to cash integration through data entities is required.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="2608a-134">Dopo l'installazione degli aggiornamenti rapidi, è necessario attivare il seguente processo batch dal modulo **SalesPopulateProspectToCash**.</span><span class="sxs-lookup"><span data-stu-id="2608a-134">After you install the hotfixes, you must trigger the following batch job from the **SalesPopulateProspectToCash** form.</span></span> <span data-ttu-id="2608a-135">Questo modulo è nascosto poiché serve una sola volta.</span><span class="sxs-lookup"><span data-stu-id="2608a-135">This form is hidden because you only need it once.</span></span> <span data-ttu-id="2608a-136">Per accedere al modulo, accedere all'ambiente e aggiungere quanto segue all'URL nell'indirizzo del browser: &mi=action:SalesPopulateProspectToCash, ad esempio, `https://ax123456.cloud.test.dynamics.com/?cmp=USMF&mi=action:SalesPopulateProspectToCash`.</span><span class="sxs-lookup"><span data-stu-id="2608a-136">To access the form, log in to the environment and add the following to the URL in your browser address: &mi=action:SalesPopulateProspectToCash, for example, `https://ax123456.cloud.test.dynamics.com/?cmp=USMF&mi=action:SalesPopulateProspectToCash`.</span></span> <span data-ttu-id="2608a-137">Quando il modulo si apre, fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="2608a-137">When the form opens, click OK.</span></span> <span data-ttu-id="2608a-138">Il modulo viene popolato con un nuovo campo **LineCreationSequnceNumber** nelle tabelle **SalesLine**, **SalesQuotationLine** e **CustInvoiceTrans** con valori univoci e l'elenco prodotti verrà aggiornato.</span><span class="sxs-lookup"><span data-stu-id="2608a-138">This will populate a new **LineCreationSequnceNumber** field in the **SalesLine**, **SalesQuotationLine**, and **CustInvoiceTrans** tables with unique values, and the product list will be refreshed.</span></span> <span data-ttu-id="2608a-139">Questa operazione è necessaria per il funzionamento dell'integrazione Prospect to cash.</span><span class="sxs-lookup"><span data-stu-id="2608a-139">This is required for the Prospect to cash integration to work.</span></span>


## <a name="system-requirements-for-sales"></a><span data-ttu-id="2608a-140">Requisiti di sistema per Sales</span><span class="sxs-lookup"><span data-stu-id="2608a-140">System requirements for Sales</span></span>

<span data-ttu-id="2608a-141">Per utilizzare la soluzione Prospect to cash, è necessario installare i componenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="2608a-141">To use the Prospect to cash solution, you must install the following components:</span></span>

- <span data-ttu-id="2608a-142">Dynamics 365 for Sales versione 1612 (8.2.1.207) (DB 8.2.1.207) online</span><span class="sxs-lookup"><span data-stu-id="2608a-142">Dynamics 365 for Sales version 1612 (8.2.1.207) (DB 8.2.1.207) online</span></span>
- <span data-ttu-id="2608a-143">Soluzione Prospect to cash per Dynamics 365 for Sales versione 1.15.0.0 (v15) o versioni successive</span><span class="sxs-lookup"><span data-stu-id="2608a-143">Prospect to cash solution for Dynamics 365 for Sales, version 1.15.0.0 (v15)</span></span> 

### <a name="install-the-prospect-to-cash-solution-for-sales"></a><span data-ttu-id="2608a-144">Installare la soluzione Prospect to cash per Sales</span><span class="sxs-lookup"><span data-stu-id="2608a-144">Install the Prospect to cash solution for Sales</span></span>

1. <span data-ttu-id="2608a-145">Scaricare il [File ZIP del pacchetto della soluzione Prospect to cash per Dynamics 365 for Sales](https://mbs.microsoft.com/customersource/Global/365Enterprise/downloads/product-releases/MD365FNOPENTProspectToCash) da CustomerSource.</span><span class="sxs-lookup"><span data-stu-id="2608a-145">Download the [Prospect to cash for Dynamics 365 for Sales solution package zip file](https://mbs.microsoft.com/customersource/Global/365Enterprise/downloads/product-releases/MD365FNOPENTProspectToCash) from CustomerSource.</span></span>
2. <span data-ttu-id="2608a-146">Assicurarsi che il file ZIP sia sbloccato.</span><span class="sxs-lookup"><span data-stu-id="2608a-146">Make sure that the zip file is unblocked.</span></span> <span data-ttu-id="2608a-147">In caso contrario, quando si tenta di installare il pacchetto della soluzione, potrebbe venire visualizzato il messaggio di errore seguente: "Nessun pacchetto per l'importazione trovato."</span><span class="sxs-lookup"><span data-stu-id="2608a-147">Otherwise, when you try to install the solution package, you may receive the following error message, "No import packages were found."</span></span> <span data-ttu-id="2608a-148">Per sbloccare il file ZIP, fare clic con il pulsante destro del mouse sul file e selezionare **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="2608a-148">To unblock the zip file, right-click it, and select **Properties**.</span></span> <span data-ttu-id="2608a-149">Selezionare **Sblocca**.</span><span class="sxs-lookup"><span data-stu-id="2608a-149">Select **Unblock**.</span></span>
3. <span data-ttu-id="2608a-150">Decomprimere il file ZIP ed eseguire il file **PackageDeployer.exe**.</span><span class="sxs-lookup"><span data-stu-id="2608a-150">Unzip and run **PackageDeployer.exe**.</span></span>
4. <span data-ttu-id="2608a-151">Installare la soluzione Prospect to cash nell'istanza di Sales:</span><span class="sxs-lookup"><span data-stu-id="2608a-151">Install the Prospect to cash solution on your Sales instance:</span></span>

    1. <span data-ttu-id="2608a-152">Selezionare **Office 365** come tipo di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="2608a-152">Select **Office 365** as the deployment type.</span></span>
    2. <span data-ttu-id="2608a-153">Selezionare **Mostra avanzate**.</span><span class="sxs-lookup"><span data-stu-id="2608a-153">Select **Show advanced**.</span></span>
    3. <span data-ttu-id="2608a-154">Per un'installazione rapida, selezionare un'area.</span><span class="sxs-lookup"><span data-stu-id="2608a-154">For a quick installation, select a region.</span></span> <span data-ttu-id="2608a-155">Se si seleziona **Non so**, il sistema cerca tutte le aree e l'installazione richiede più tempo.</span><span class="sxs-lookup"><span data-stu-id="2608a-155">If you select **Don't know**, the system searches for all regions, and the installation will take more time.</span></span>
    4. <span data-ttu-id="2608a-156">Immettere il nome utente e la password di un utente amministratore con diritti di installazione.</span><span class="sxs-lookup"><span data-stu-id="2608a-156">Enter the user name and password of an admin user who has installation rights.</span></span>



