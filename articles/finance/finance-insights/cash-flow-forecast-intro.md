---
title: Previsione di cassa (anteprima)
description: Questo argomento descrive la funzionalità di previsione di cassa.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 05/19/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-05-19
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 3e9237980144ea65e1ff5135e277151970dbfdbb
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5208607"
---
# <a name="cash-flow-forecast-preview"></a><span data-ttu-id="d1b62-103">Previsione di cassa (anteprima)</span><span class="sxs-lookup"><span data-stu-id="d1b62-103">Cash flow forecast (preview)</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="d1b62-104">Il flusso di cassa è fondamentale per qualsiasi azienda.</span><span class="sxs-lookup"><span data-stu-id="d1b62-104">Cash flow is critical to any business.</span></span> <span data-ttu-id="d1b62-105">Anche le aziende redditizie possono affrontare l'insolvenza se non mantengono il flusso di cassa per soddisfare le esigenze immediate.</span><span class="sxs-lookup"><span data-stu-id="d1b62-105">Even profitable companies can face insolvency if they don't maintain the cash flow to meet immediate needs.</span></span> <span data-ttu-id="d1b62-106">La funzionalità di previsione di cassa in Finance Insights può aiutare le aziende a monitorare e gestire i propri saldi di cassa in modo efficace.</span><span class="sxs-lookup"><span data-stu-id="d1b62-106">The cash flow forecasting capability in Finance insights can help companies monitor and manage their cash balances effectively.</span></span> <span data-ttu-id="d1b62-107">Questa funzionalità utilizza l'apprendimento automatico per aiutare le aziende a prevedere i flussi di cassa in modo più accurato rispetto a prima.</span><span class="sxs-lookup"><span data-stu-id="d1b62-107">This feature uses machine learning to help businesses forecast cash flows more accurately than they have previously.</span></span> <span data-ttu-id="d1b62-108">Può anche aiutare i responsabili a prendere decisioni che ottimizzano le opportunità nel contesto della loro attuale posizione di cassa.</span><span class="sxs-lookup"><span data-stu-id="d1b62-108">It can also help managers make decisions that optimize opportunities in the context of their current cash position.</span></span> 

<span data-ttu-id="d1b62-109">Per la maggior parte delle aziende, la gestione del flusso di cassa e l'esecuzione della previsione di cassa è un processo noioso, ripetitivo e manuale.</span><span class="sxs-lookup"><span data-stu-id="d1b62-109">For most companies, managing cash flow and running cash flow forecasting is a tedious, repetitive, and manual process.</span></span> <span data-ttu-id="d1b62-110">La maggior parte delle aziende fa affidamento alle soluzioni di Microsoft Excel che hanno diversi gradi di complessità.</span><span class="sxs-lookup"><span data-stu-id="d1b62-110">Most companies rely on Microsoft Excel solutions that have varying degrees of complexity.</span></span> <span data-ttu-id="d1b62-111">Le sfide della previsione accurata del flusso di cassa includono quanto segue:</span><span class="sxs-lookup"><span data-stu-id="d1b62-111">The challenges of accurately forecasting cash flow include the following:</span></span>

- <span data-ttu-id="d1b62-112">I dati non sono disponibili per i decision maker perché sono dispersi in più posizioni, tra cui:</span><span class="sxs-lookup"><span data-stu-id="d1b62-112">Data isn't available to decision makers because it's scattered in multiple places, including:</span></span> 
  - <span data-ttu-id="d1b62-113">Sistema di pianificazione delle risorse aziendali o contabilità</span><span class="sxs-lookup"><span data-stu-id="d1b62-113">The accounting or enterprise resource planning system</span></span>
  - <span data-ttu-id="d1b62-114">Software di pianificazione finanziaria</span><span class="sxs-lookup"><span data-stu-id="d1b62-114">Financial planning software</span></span>
  - <span data-ttu-id="d1b62-115">Excel</span><span class="sxs-lookup"><span data-stu-id="d1b62-115">Excel</span></span>
  - <span data-ttu-id="d1b62-116">Applicazioni software aggiuntive</span><span class="sxs-lookup"><span data-stu-id="d1b62-116">Additional software applications</span></span> 
- <span data-ttu-id="d1b62-117">La previsione si basa sulla Knowledge Base interna che risiede in "silo" all'interno di ogni dominio o reparto.</span><span class="sxs-lookup"><span data-stu-id="d1b62-117">Forecasting is based on internal knowledge that resides in "silos" within each domain or department.</span></span>
- <span data-ttu-id="d1b62-118">La misurazione dell'accuratezza della di cassa dopo che i dati finanziari sono stati realizzati è incerta e difficile.</span><span class="sxs-lookup"><span data-stu-id="d1b62-118">Measuring the accuracy of cash flow forecasting after the financials have been realized is uncertain and difficult.</span></span>
    
## <a name="details-of-the-cash-flow-forecasts-capability"></a><span data-ttu-id="d1b62-119">Dettagli sulla funzionalità di previsione di cassa</span><span class="sxs-lookup"><span data-stu-id="d1b62-119">Details of the Cash flow forecasts capability</span></span>
<span data-ttu-id="d1b62-120">La funzionalità Previsioni di cassa include le seguenti funzionalità.</span><span class="sxs-lookup"><span data-stu-id="d1b62-120">The Cash flow forecasts feature includes the following functionality.</span></span> 

- <span data-ttu-id="d1b62-121">Semplifica l'integrazione dei dati sul flusso di cassa da sistemi esterni a Dynamics 365 Finance.</span><span class="sxs-lookup"><span data-stu-id="d1b62-121">Makes it easy to integrate cash flow data from external systems to Dynamics 365 Finance.</span></span> <span data-ttu-id="d1b62-122">Le previsioni di cassa possono anche utilizzare il framework di importazione/esportazione dei dati.</span><span class="sxs-lookup"><span data-stu-id="d1b62-122">Cash flow forecasts can also use the data import-export framework.</span></span> <span data-ttu-id="d1b62-123">Questo framework semplifica l'integrazione con Excel OData.</span><span class="sxs-lookup"><span data-stu-id="d1b62-123">This framework makes it easy to integrate with Excel OData.</span></span> <span data-ttu-id="d1b62-124">È inoltre possibile combinare i dati da più origini per creare una soluzione completa per il flusso di cassa.</span><span class="sxs-lookup"><span data-stu-id="d1b62-124">You can also combine data from multiple sources to create a comprehensive cash flow solution.</span></span> 

- <span data-ttu-id="d1b62-125">Introduce una posizione di cassa intelligente.</span><span class="sxs-lookup"><span data-stu-id="d1b62-125">Introduces intelligent cash position.</span></span> <span data-ttu-id="d1b62-126">La posizione di cassa viene creata in base al comportamento di pagamento del cliente per prevedere quando un'azienda può aspettarsi l'arrivo di liquidità nei suoi conti.</span><span class="sxs-lookup"><span data-stu-id="d1b62-126">Cash position is created  based on customer’s payment behavior to predict when a company can expect cash to arrive in their accounts.</span></span> <span data-ttu-id="d1b62-127">Analizza inoltre i modelli storici di pagamento dei fornitori, per prevedere quando è probabile che le fatture e gli ordini futuri verranno pagati.</span><span class="sxs-lookup"><span data-stu-id="d1b62-127">It also analyzes the historical patterns of paying vendors, to predict when future invoices and orders are likely to be paid.</span></span> 

- <span data-ttu-id="d1b62-128">Introduce la previsione di cassa intelligente per previsioni a lungo termine, utilizzando previsioni di serie temporali attraverso l'integrazione automatizzata con AI Builder.</span><span class="sxs-lookup"><span data-stu-id="d1b62-128">Introduces intelligent cash flow forecasting for long-term forecasting, using time series forecasting through automated integration with AI Builder.</span></span>

- <span data-ttu-id="d1b62-129">Offre la possibilità di salvare posizioni o previsioni specifiche di cassa, modificarle e quindi confrontare e misurare facilmente le prestazioni previste con i dati finanziari effettivi.</span><span class="sxs-lookup"><span data-stu-id="d1b62-129">Provides the ability to save specific cash flow position or forecasts, edit them, and then easily compare and measure the forecast performance to the actual financials.</span></span>

- <span data-ttu-id="d1b62-130">Consente l'analisi what-if attraverso il confronto di snapshot.</span><span class="sxs-lookup"><span data-stu-id="d1b62-130">Enables what-if analysis through snapshot comparison.</span></span> <span data-ttu-id="d1b62-131">Ad esempio, è possibile creare più snapshot che rappresentano visualizzazioni ottimistiche, pessimistiche e più realistiche del flusso di cassa, quindi confrontare e visualizzare le differenze.</span><span class="sxs-lookup"><span data-stu-id="d1b62-131">For example, you can create multiple snapshots that represent optimistic, pessimistic, and the most realistic views of your cash flow, and then compare and view the differences.</span></span>

- <span data-ttu-id="d1b62-132">Offre la possibilità di visualizzare la previsione di cassa in più valute, tra persone giuridiche e filtrare e visualizzare il flusso di cassa relativo a un conto bancario.</span><span class="sxs-lookup"><span data-stu-id="d1b62-132">Provides the ability to view the cash flow forecast in multiple currencies, across legal entities, and filter and view cash flow related to a bank account.</span></span> 

- <span data-ttu-id="d1b62-133">Consente di filtrare e visualizzare i conti bancari correlati alle dimensioni finanziarie.</span><span class="sxs-lookup"><span data-stu-id="d1b62-133">Lets you filter and view bank accounts that are related to financial dimensions.</span></span>

<span data-ttu-id="d1b62-134">La funzionalità di previsione di cassa in Dynamics 365 Finance consentirà alla tua organizzazione di trasformare la proiezione del flusso di cassa noiose, complesse e ripetitive in un processo semplice e automatizzato.</span><span class="sxs-lookup"><span data-stu-id="d1b62-134">The cash flow forecasting functionality in Dynamics 365 Finance will empower your organization to transform tedious, complex, yet repetitive cash flow projection to a simple, automated process.</span></span> <span data-ttu-id="d1b62-135">L'automazione degli aspetti più noiosi della previsione di cassa consente di concentrarsi sul processo decisionale critico per ottenere i risultati aziendali desiderati.</span><span class="sxs-lookup"><span data-stu-id="d1b62-135">Automating the most tedious aspects of cash flow forecasting lets you focus on critical decision making to drive desired business outcomes.</span></span>

## <a name="setting-up-dimensions-for-cash-flow-forecasting"></a><span data-ttu-id="d1b62-136">Configurazione di dimensioni per la previsione di cassa</span><span class="sxs-lookup"><span data-stu-id="d1b62-136">Setting up Dimensions for Cash flow forecasting</span></span>
<span data-ttu-id="d1b62-137">Una nuova scheda nella pagina **Configurazione della previsione di cassa** consente di controllare quali dimensioni finanziarie utilizzare per filtrare nell'area di lavoro **Previsione di cassa**.</span><span class="sxs-lookup"><span data-stu-id="d1b62-137">A new tab on the **Cash flow forecasting setup** page lets you control what financial dimensions to use for filtering in the **Cash flow forecasting** workspace.</span></span> <span data-ttu-id="d1b62-138">Questa scheda verrà visualizzata solo quando la funzione Previsioni di cassa è abilitata.</span><span class="sxs-lookup"><span data-stu-id="d1b62-138">This tab will only appear when the Cash flow forecasts feature is enabled.</span></span> 

<span data-ttu-id="d1b62-139">Nella scheda **Dimensioni**, scegli dall'elenco delle dimensioni da utilizzare per i filtri e utilizza i tasti freccia per spostarle nella colonna di destra.</span><span class="sxs-lookup"><span data-stu-id="d1b62-139">On the **Dimensions** tab, choose from the list of dimensions to use for filtering, and use the arrow keys to move them to the right-hand column.</span></span> <span data-ttu-id="d1b62-140">È possibile selezionare solo due dimensioni per filtrare i dati di previsione di cassa.</span><span class="sxs-lookup"><span data-stu-id="d1b62-140">Only two dimensions can be selected for filtering cash flow forecast data.</span></span> 

#### <a name="privacy-notice"></a><span data-ttu-id="d1b62-141">Informativa sulla privacy</span><span class="sxs-lookup"><span data-stu-id="d1b62-141">Privacy notice</span></span>
<span data-ttu-id="d1b62-142">Le anteprime (1) potrebbero utilizzare meno misure di sicurezza e di privacy rispetto al servizio Dynamics 365 Finance and Operations, (2) non sono incluse nel contratto di servizio di questo servizio, (3) non devono essere utilizzate per elaborare i dati personali o altri dati soggetti a requisiti legati e normativi, e (4) hanno supporto limitato.</span><span class="sxs-lookup"><span data-stu-id="d1b62-142">Previews (1) might use less privacy and fewer security measures than the Dynamics 365 Finance and Operations service, (2) aren't included in the service level agreement (SLA) for this service, (3) should not be used to process personal data or other data that is subject to legal or regulatory compliance requirements, and (4) have limited support.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]