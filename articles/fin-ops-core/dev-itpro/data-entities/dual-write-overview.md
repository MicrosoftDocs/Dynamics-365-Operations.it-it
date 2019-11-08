---
title: Integrazione dati quasi in tempo reale con Common Data Service
description: Questo argomento fornisce una panoramica dell'integrazione tra Finance and Operations e Common Data Service.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 07/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: d70bce4e47c05a7974c1b974fdca17682e5370aa
ms.sourcegitcommit: 75db3b75d35d27034f9b56e7119c9d0cb7666830
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/03/2019
ms.locfileid: "2550859"
---
# <a name="near-real-time-data-integration-with-common-data-service"></a><span data-ttu-id="8cd5e-103">Integrazione dati quasi in tempo reale con Common Data Service</span><span class="sxs-lookup"><span data-stu-id="8cd5e-103">Near-real-time data integration with Common Data Service</span></span>

[!include [banner](../includes/banner.md)]

[!include [preview](../includes/preview-banner.md)]

<span data-ttu-id="8cd5e-104">Nel mondo digitale corrente, gli ecosistemi aziendali utilizzano le applicazioni Microsoft Dynamics 365 nel loro insieme.</span><span class="sxs-lookup"><span data-stu-id="8cd5e-104">In the current digital world, business ecosystems use Microsoft Dynamics 365 applications as a whole.</span></span> <span data-ttu-id="8cd5e-105">Poiché i dati di persone, clienti, operazioni e dai dispositivi IoT (Internet of Things, Internet delle Cose) fluiscono in una sola origine, c'è un'opportunità di cicli di feedback digitali.</span><span class="sxs-lookup"><span data-stu-id="8cd5e-105">Because data from people, customers, operations, and Internet of Things (IoT) devices flows into one source, there is an opportunity for digital feedback loops.</span></span> <span data-ttu-id="8cd5e-106">Per ottenere questa esperienza, l'integrazione tra le app Finance and Operations e le applicazioni Dynamics 365 è essenziale.</span><span class="sxs-lookup"><span data-stu-id="8cd5e-106">To achieve this experience, integration between Finance and Operations apps and other Dynamics 365 applications is essential.</span></span> <span data-ttu-id="8cd5e-107">Alcune applicazioni si basano su Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="8cd5e-107">Some applications are built on top of Common Data Service.</span></span> <span data-ttu-id="8cd5e-108">L'integrazione tra i dati delle app Finance and Operations e Common Data Service consente ad altre applicazioni di comunicare coerentemente e in modo fluente con Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="8cd5e-108">Integration between Finance and Operations apps data with Common Data Service lets other applications communicate coherently and fluently with Finance and Operations.</span></span>

<span data-ttu-id="8cd5e-109">Le app Finance and Operations e Common Data Service forniscono la sincronizzazione dei dati quasi in tempo reale tra le app Finance and Operations e altre applicazioni Dynamics 365 tramite un framework di doppia scrittura.</span><span class="sxs-lookup"><span data-stu-id="8cd5e-109">Finance and Operations apps and Common Data Service provide near-real-time data synchronization between Finance and Operations apps and other Dynamics 365 applications via a dual-write framework.</span></span> <span data-ttu-id="8cd5e-110">La copertura è ampia e riguarda 28 aree dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="8cd5e-110">The coverage is broad and spans 28 surface areas of the application.</span></span> <span data-ttu-id="8cd5e-111">L'obiettivo è fornire "Un'unica esperienza Dynamics 365" agli utenti tramite flussi integrati di dati che collegano i processi aziendali di tutte le applicazioni.</span><span class="sxs-lookup"><span data-stu-id="8cd5e-111">The goal is to provide a "One Dynamics 365" user experience through seamless data flows that connect business processes across applications.</span></span>

![Diagramma di panoramica dell'architettura](media/dual-write-overview.jpg)

<span data-ttu-id="8cd5e-113">Le seguenti proposte di valore sono disponibili per i clienti:</span><span class="sxs-lookup"><span data-stu-id="8cd5e-113">The following value propositions are available for customers:</span></span>

+ [<span data-ttu-id="8cd5e-114">Gerarchia organizzativa in Common Data Service</span><span class="sxs-lookup"><span data-stu-id="8cd5e-114">Organization hierarchy in Common Data Service</span></span>](dual-write-organization.md)
+ [<span data-ttu-id="8cd5e-115">Concetto di società in Common Data Service</span><span class="sxs-lookup"><span data-stu-id="8cd5e-115">Company concept in Common Data Service</span></span>](dual-write-company.md)
+ [<span data-ttu-id="8cd5e-116">Gestione integrata dei dati dei clienti</span><span class="sxs-lookup"><span data-stu-id="8cd5e-116">Integrated customer master</span></span>](dual-write-customer.md)
+ [<span data-ttu-id="8cd5e-117">Gestione integrata dei dati dei fornitori</span><span class="sxs-lookup"><span data-stu-id="8cd5e-117">Integrated vendor master</span></span>](dual-write-vendor.md)
+ <span data-ttu-id="8cd5e-118">Rappresentazione generale prodotto unificata</span><span class="sxs-lookup"><span data-stu-id="8cd5e-118">Unified product master</span></span>

## <a name="system-requirements"></a><span data-ttu-id="8cd5e-119">Requisiti di sistema</span><span class="sxs-lookup"><span data-stu-id="8cd5e-119">System requirements</span></span>

<span data-ttu-id="8cd5e-120">I flussi di dati sincroni, bidirezionali, quasi in tempo reale richiedono le seguenti versioni:</span><span class="sxs-lookup"><span data-stu-id="8cd5e-120">Synchronous, bidirectional, near-real-time data flows require the following versions:</span></span>

+ <span data-ttu-id="8cd5e-121">Microsoft Dynamics 365 for Finance and Operations versione 10.0.4 (luglio 2019) con aggiornamento della piattaforma 28 o successivo</span><span class="sxs-lookup"><span data-stu-id="8cd5e-121">Microsoft Dynamics 365 for Finance and Operations version 10.0.4 (July 2019) with Platform update 28, or later</span></span>
+ <span data-ttu-id="8cd5e-122">Microsoft Dynamics 365 for Customer Engagement, piattaforma versione 9.1 (4.2) o versione successiva</span><span class="sxs-lookup"><span data-stu-id="8cd5e-122">Microsoft Dynamics 365 for Customer Engagement, Platform version 9.1 (4.2) or later</span></span>

## <a name="setup-instructions"></a><span data-ttu-id="8cd5e-123">Istruzioni di impostazione</span><span class="sxs-lookup"><span data-stu-id="8cd5e-123">Setup instructions</span></span>

<span data-ttu-id="8cd5e-124">Seguire questi passaggi per impostare l'integrazione tra le app Finance and Operations e Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="8cd5e-124">Follow these steps to set up integration between Finance and Operations apps and Common Data Service.</span></span>
    
1. <span data-ttu-id="8cd5e-125">Per l'impostazione del sistema di doppia scrittura, vedere la [guida dettagliata](https://aka.ms/dualwrite-docs) nell'annuncio sull'anteprima della doppia scrittura.</span><span class="sxs-lookup"><span data-stu-id="8cd5e-125">For the setup of the dual-write system, see the [step-by-step guide](https://aka.ms/dualwrite-docs) on Announcing Dual Write Preview.</span></span>
2. <span data-ttu-id="8cd5e-126">Scaricare e installare la soluzione [Integrazione tra Finance and Operations, Common Data Service e Customer Engagement](https://www.yammer.com/dynamicsaxfeedbackprograms/#/threads/inGroup?type=in_group&feedId=66052096) dal gruppo Yammer.</span><span class="sxs-lookup"><span data-stu-id="8cd5e-126">Download and install the solution from the [Finance and Operations, Common Data Service, and Customer Engagement Integration](https://www.yammer.com/dynamicsaxfeedbackprograms/#/threads/inGroup?type=in_group&feedId=66052096) Yammer group.</span></span> <span data-ttu-id="8cd5e-127">Il pacchetto contiene cinque soluzioni:</span><span class="sxs-lookup"><span data-stu-id="8cd5e-127">The package contains five solutions:</span></span>

    + <span data-ttu-id="8cd5e-128">Dynamics365Company</span><span class="sxs-lookup"><span data-stu-id="8cd5e-128">Dynamics365Company</span></span>
    + <span data-ttu-id="8cd5e-129">CurrencyExchangeRates</span><span class="sxs-lookup"><span data-stu-id="8cd5e-129">CurrencyExchangeRates</span></span>
    + <span data-ttu-id="8cd5e-130">Dynamics365FinanceAndOperationsCommon</span><span class="sxs-lookup"><span data-stu-id="8cd5e-130">Dynamics365FinanceAndOperationsCommon</span></span>
    + <span data-ttu-id="8cd5e-131">Dynamics365FinanceCommon</span><span class="sxs-lookup"><span data-stu-id="8cd5e-131">Dynamics365FinanceCommon</span></span>
    + <span data-ttu-id="8cd5e-132">Dynamics365SupplyChainCommon</span><span class="sxs-lookup"><span data-stu-id="8cd5e-132">Dynamics365SupplyChainCommon</span></span>

3. <span data-ttu-id="8cd5e-133">Seguire l'ordine di esecuzione per [sincronizzare i dati di riferimento iniziali](dual-write-initial.md).</span><span class="sxs-lookup"><span data-stu-id="8cd5e-133">Follow the execution order for [synchronizing initial reference data](dual-write-initial.md).</span></span>
4. <span data-ttu-id="8cd5e-134">Se si verificano problemi di sincronizzazione della doppia scrittura, vedere [Guida alla risoluzione dei problemi di integrazione dei dati](dual-write-troubleshooting.md).</span><span class="sxs-lookup"><span data-stu-id="8cd5e-134">If you encounter dual-write synchronization issues, see the [Troubleshooting guide for data integration](dual-write-troubleshooting.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8cd5e-135">Non è possibile eseguire la doppia scrittura e [Prospect to cash](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/accounts-template-mapping-direct) in parallelo.</span><span class="sxs-lookup"><span data-stu-id="8cd5e-135">You can’t run dual-write and [Prospect to cash](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/accounts-template-mapping-direct) side-by-side.</span></span> <span data-ttu-id="8cd5e-136">Se si sta eseguendo la soluzione Prospect to cash, è necessario disinstallarla.</span><span class="sxs-lookup"><span data-stu-id="8cd5e-136">If you're running the Prospect to cash solution, you must uninstall it.</span></span> <span data-ttu-id="8cd5e-137">È inoltre necessario disabilitare i modelli di doppia scrittura di cliente e fornitore che fanno parte della soluzione Prospect to cash.</span><span class="sxs-lookup"><span data-stu-id="8cd5e-137">You must also disable the customer and vendor dual-write templates that are part of the Prospect to cash solution.</span></span>
