---
title: Integrazione con Microsoft Dynamics 365 for Field Service
description: In questo argomento viene fornita una panoramica dell'integrazione con Microsoft Dynamics 365 for Field Service.
author: ChristianRytt
manager: AnnBe
ms.date: 04/25/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
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
ms.sourcegitcommit: 841ea53f754f61c2930e77fdafc85eac72f47d7a
ms.openlocfilehash: 29e5748a1e1c381febae80d02b4ac311c3f0008e
ms.contentlocale: it-it
ms.lasthandoff: 07/21/2018

---


# <a name="integration-with-microsoft-dynamics-365-for-field-service"></a><span data-ttu-id="bf006-103">Integrazione con Microsoft Dynamics 365 for Field Service</span><span class="sxs-lookup"><span data-stu-id="bf006-103">Integration with Microsoft Dynamics 365 for Field Service</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="bf006-104">Microsoft Dynamics 365 for Finance and Operations consente di sincronizzare i processi aziendali tra Finance and Operations e Microsoft Dynamics 365 for Field Service.</span><span class="sxs-lookup"><span data-stu-id="bf006-104">Microsoft Dynamics 365 for Finance and Operations enables synchronization of business processes between Finance and Operations and Microsoft Dynamics 365 for Field Service.</span></span> <span data-ttu-id="bf006-105">Gli scenari di integrazione vengono configurati utilizzando modelli di integrazione dati estendibili e Common Data Service (CDS) per abilitare la sincronizzazione dei processi aziendali.</span><span class="sxs-lookup"><span data-stu-id="bf006-105">The integration scenarios are configured by using extensible Data integrator templates and the Common Data Service (CDS) to enable the synchronization of business processes.</span></span>

<span data-ttu-id="bf006-106">[![Sincronizzazione dei processi aziendali tra Finance and Operations e Field Service](./media/field-service-integration.png)](./media/field-service-integration.png)</span><span class="sxs-lookup"><span data-stu-id="bf006-106">[![Synchronization of business processes between Finance and Operations and Field Service](./media/field-service-integration.png)](./media/field-service-integration.png)</span></span>

<span data-ttu-id="bf006-107">La prima fase dell'integrazione tra Field Service e Finance and Operations è incentrata sull'abilitazione degli ordini di lavoro e dei contratti in Field Service in modo che possano essere fatturati in Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="bf006-107">The first phase  of the integration between Field Service and Finance and Operations is focused on enabling work orders and agreements in Field Service to be invoiced in Finance and Operations.</span></span> <span data-ttu-id="bf006-108">Il flusso supportato inizia in Field Service, dove le informazioni degli ordini di lavoro vengono sincronizzate con Finance and Operations sotto forma di ordini cliente.</span><span class="sxs-lookup"><span data-stu-id="bf006-108">The supported flow starts in Field Service, where information from work orders is synchronized to Finance and Operations as sales orders.</span></span> <span data-ttu-id="bf006-109">In Finance and Operations, gli ordini cliente vengono fatturati per generare documenti fattura.</span><span class="sxs-lookup"><span data-stu-id="bf006-109">In Finance and Operations, the sales orders are invoiced to generate invoice documents.</span></span> <span data-ttu-id="bf006-110">Inoltre, le informazioni contenute nelle fatture di contratto di Field Service vengono sincronizzate con Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="bf006-110">In addition, the information from Field Service agreement invoices is synchronized to Finance and Operations.</span></span> <span data-ttu-id="bf006-111">L'integratore di dati Microsoft Dynamics 365 sincronizza i dati utilizzando progetti personalizzabili.</span><span class="sxs-lookup"><span data-stu-id="bf006-111">The Microsoft Dynamics 365 Data integrator synchronizes data by using customizable projects.</span></span> <span data-ttu-id="bf006-112">È possibile utilizzare modelli standard per creare progetti di integrazione personalizzati in cui mappare campi personalizzati e standard aggiuntivi, nonché entità, per ottimizzare l'integrazione e soddisfare requisiti specifici.</span><span class="sxs-lookup"><span data-stu-id="bf006-112">Standard templates can be used to create custom integration projects where additional standard and custom fields, and also entities, can be mapped to adjust the integration and meet specific requirements.</span></span>

<span data-ttu-id="bf006-113">La prima fase dell'integrazione tra Field Service e Finance and Operations consente la sincronizzazione degli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="bf006-113">The first phase of the integration between Field Service and Finance and Operations enables synchronization of the following items:</span></span>

- [<span data-ttu-id="bf006-114">Prodotti in Finance and Operations con prodotti in Field Service che includono informazioni sul tipo di prodotto</span><span class="sxs-lookup"><span data-stu-id="bf006-114">Products in Finance and Operations to products in Field Service that include Product Type information</span></span>](field-service-product.md)
- [<span data-ttu-id="bf006-115">Ordini di lavoro in Field Service con ordini cliente in Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="bf006-115">Work orders in Field Service to sales orders in Finance and Operations</span></span>](field-service-work-order.md)
- [<span data-ttu-id="bf006-116">Fatture in Field Service con fatture a testo libero in Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="bf006-116">Invoices in Field Service to free text invoices in Finance and Operations</span></span>](field-service-invoice.md)

<span data-ttu-id="bf006-117">Per visualizzare un esempio di come sincronizzare un ordine di lavoro tra Field Service e Finance and Operations, guardare il breve video su YouTube [Sincronizzare un ordine di lavoro tra Dynamics 365 for Field Service e Finance and Operations](https://www.youtube.com/watch?v=hAB4TDVMjxU).</span><span class="sxs-lookup"><span data-stu-id="bf006-117">To see an example of how you can synchronize a work order between Field Service and Finance and Operations, watch the short YouTube video [Synchronize a work order between Dynamics 365 for Field Service and Finance and Operations](https://www.youtube.com/watch?v=hAB4TDVMjxU).</span></span>

[![](https://img.youtube.com/vi/hAB4TDVMjxU/0.jpg)](https://www.youtube.com/watch?v=hAB4TDVMjxU)

## <a name="system-requirements-for-finance-and-operations"></a><span data-ttu-id="bf006-118">Requisiti di sistema di Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="bf006-118">System requirements for Finance and Operations</span></span>
<span data-ttu-id="bf006-119">L'integrazione di Field Service supporta le versioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="bf006-119">Field Service integration supports the following versions:</span></span>

### <a name="dynamics-365-for-finance-and-operations-version-80-april-2018-or-later"></a><span data-ttu-id="bf006-120">Dynamics 365 for Finance and Operations versione 8.0 (aprile 2018) o successive</span><span class="sxs-lookup"><span data-stu-id="bf006-120">Dynamics 365 for Finance and Operations version 8.0 (April 2018) or later</span></span>

- <span data-ttu-id="bf006-121">Dynamics 365 for Finance and Operations versione 8.0 (aprile 2018) è stata rilasciata in aprile 2018 con numero di build 8.0.30.8020 e aggiornamento 15 della piattaforma (7.0.4841.35234).</span><span class="sxs-lookup"><span data-stu-id="bf006-121">Dynamics 365 for Finance and Operations version 8.0 (April 2018) was released in April 2018 and has an application build number 8.0.30.8020 with Platform Update 15 (7.0.4841.35234).</span></span> 

## <a name="system-requirements-for-field-service"></a><span data-ttu-id="bf006-122">Requisiti di sistema per Field Service</span><span class="sxs-lookup"><span data-stu-id="bf006-122">System requirements for Field Service</span></span>
<span data-ttu-id="bf006-123">Per utilizzare la soluzione di integrazione di Field Service, è necessario installare i componenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="bf006-123">To use the Field Service integration solution, you must install the following components:</span></span>

### <a name="microsoft-dynamics-365-for-field-service-90-or-later"></a><span data-ttu-id="bf006-124">Microsoft Dynamics 365 for Field Service 9.0 o versioni successive</span><span class="sxs-lookup"><span data-stu-id="bf006-124">Microsoft Dynamics 365 for Field Service 9.0 or later</span></span>

- <span data-ttu-id="bf006-125">Dynamics 365 for Field Service versione 1612 (9.0.1.733) (DB 9.0.1.733) online o una versione successiva.</span><span class="sxs-lookup"><span data-stu-id="bf006-125">Dynamics 365 for Field Service version 1612 (9.0.1.733) (DB 9.0.1.733) online or a later version.</span></span>
- <span data-ttu-id="bf006-126">Soluzione Prospect to Cash (P2C) per Dynamics 365, versione 1.15.0.1 o una versione successiva.</span><span class="sxs-lookup"><span data-stu-id="bf006-126">Prospect to Cash (P2C) solution for Dynamics 365, version 1.15.0.1 or a later version.</span></span> <span data-ttu-id="bf006-127">La soluzione può essere scaricata da [AppSource](https://appsource.microsoft.com/en-us/product/dynamics-365/mscrm.c7a48b40-eed3-4d67-93ba-f2364281feb3).</span><span class="sxs-lookup"><span data-stu-id="bf006-127">The solution is available for download from [AppSource](https://appsource.microsoft.com/en-us/product/dynamics-365/mscrm.c7a48b40-eed3-4d67-93ba-f2364281feb3).</span></span>
- <span data-ttu-id="bf006-128">Soluzione di integrazione di Field Service per Dynamics 365, versione 1.0.0.0 o una versione successiva.</span><span class="sxs-lookup"><span data-stu-id="bf006-128">Field Service integration solution for Dynamics 365, version 1.0.0.0 or a later version.</span></span> <span data-ttu-id="bf006-129">La soluzione può essere scaricata da [AppSource](https://appsource.microsoft.com/en-us/product/dynamics-365/mscrm.p2cfieldserviceintegration).</span><span class="sxs-lookup"><span data-stu-id="bf006-129">The solution is available for download from [AppSource](https://appsource.microsoft.com/en-us/product/dynamics-365/mscrm.p2cfieldserviceintegration).</span></span>

