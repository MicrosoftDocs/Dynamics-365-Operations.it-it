---
title: Contabilità generale integrata
description: In questo argomento viene descritta l'integrazione dei dati di contabilità generale tra Finance and Operations e Customer Engagement tramite Common Data Service.
author: robinarh
manager: AnnBe
ms.date: 09/06/2019
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
ms.author: ''
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: 43819e23b167663a51095546cab307e7d7c79a38
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/06/2019
ms.locfileid: "2771050"
---
## <a name="integrated-ledger"></a><span data-ttu-id="107fb-103">Contabilità generale integrata</span><span class="sxs-lookup"><span data-stu-id="107fb-103">Integrated ledger</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="107fb-104">In un'applicazione aziendale, i dati della contabilità generale definiscono il core impostato per il modo in cui un'azienda fa affari.</span><span class="sxs-lookup"><span data-stu-id="107fb-104">In a business application, ledger data defines the core set up for how a company does business.</span></span> <span data-ttu-id="107fb-105">Ad esempio, i dati della contabilità generale descrivono l'anno fiscale dell'azienda, le valute in cui opera e i conti utilizzati.</span><span class="sxs-lookup"><span data-stu-id="107fb-105">For example, ledger data describes the fiscal year the company follows, the currencies it transacts in, and the accounts it uses.</span></span> <span data-ttu-id="107fb-106">In questo argomento viene descritta l'integrazione dei dati finanziari di base.</span><span class="sxs-lookup"><span data-stu-id="107fb-106">This topic describes the integration of this core financial data.</span></span>

## <a name="templates"></a><span data-ttu-id="107fb-107">Modelli</span><span class="sxs-lookup"><span data-stu-id="107fb-107">Templates</span></span>

<span data-ttu-id="107fb-108">I dati della contabilità generale includono una raccolta di mappe di entità finanziarie di base che funzionano in combinazione durante l'interazione con i dati, come illustrato nella seguente tabella.</span><span class="sxs-lookup"><span data-stu-id="107fb-108">Ledger data includes a collection of core financial entity maps that work together during data interaction, as shown in the following table.</span></span>

<span data-ttu-id="107fb-109">App Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="107fb-109">Finance and Operations apps</span></span>      | <span data-ttu-id="107fb-110">Altre app Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="107fb-110">Other Dynamics 365 apps</span></span>
---------------------------------|---------------------------------
<span data-ttu-id="107fb-111">Valute</span><span class="sxs-lookup"><span data-stu-id="107fb-111">Currencies</span></span>                       | <span data-ttu-id="107fb-112">transactioncurrencies</span><span class="sxs-lookup"><span data-stu-id="107fb-112">transactioncurrencies</span></span>
<span data-ttu-id="107fb-113">FiscalCalendar</span><span class="sxs-lookup"><span data-stu-id="107fb-113">FiscalCalendar</span></span>                   | <span data-ttu-id="107fb-114">msdyn\_fiscalcalendars</span><span class="sxs-lookup"><span data-stu-id="107fb-114">msdyn\_fiscalcalendars</span></span>
<span data-ttu-id="107fb-115">FiscalCalendarYear</span><span class="sxs-lookup"><span data-stu-id="107fb-115">FiscalCalendarYear</span></span>               | <span data-ttu-id="107fb-116">msdyn\_fiscalcalendaryears</span><span class="sxs-lookup"><span data-stu-id="107fb-116">msdyn\_fiscalcalendaryears</span></span>
<span data-ttu-id="107fb-117">ExchRateType</span><span class="sxs-lookup"><span data-stu-id="107fb-117">ExchRateType</span></span>                     | <span data-ttu-id="107fb-118">msdyn\_exchangeratetypes</span><span class="sxs-lookup"><span data-stu-id="107fb-118">msdyn\_exchangeratetypes</span></span>
<span data-ttu-id="107fb-119">ExchangeRateCurrencyPair</span><span class="sxs-lookup"><span data-stu-id="107fb-119">ExchangeRateCurrencyPair</span></span>         | <span data-ttu-id="107fb-120">msdyn\_currencyexchangeratepairs</span><span class="sxs-lookup"><span data-stu-id="107fb-120">msdyn\_currencyexchangeratepairs</span></span>
<span data-ttu-id="107fb-121">FiscalPeriodEntity</span><span class="sxs-lookup"><span data-stu-id="107fb-121">FiscalPeriodEntity</span></span>               | <span data-ttu-id="107fb-122">msdyn\_fiscalcalendarperiods</span><span class="sxs-lookup"><span data-stu-id="107fb-122">msdyn\_fiscalcalendarperiods</span></span>
<span data-ttu-id="107fb-123">MainAccountCategory</span><span class="sxs-lookup"><span data-stu-id="107fb-123">MainAccountCategory</span></span>              | <span data-ttu-id="107fb-124">msdyn\_mainaccountcategory</span><span class="sxs-lookup"><span data-stu-id="107fb-124">msdyn\_mainaccountcategory</span></span>
<span data-ttu-id="107fb-125">MainAccount</span><span class="sxs-lookup"><span data-stu-id="107fb-125">MainAccount</span></span>                      | <span data-ttu-id="107fb-126">msdyn\_mainaccounts</span><span class="sxs-lookup"><span data-stu-id="107fb-126">msdyn\_mainaccounts</span></span>
<span data-ttu-id="107fb-127">Contabilità generale</span><span class="sxs-lookup"><span data-stu-id="107fb-127">Ledger</span></span>                           | <span data-ttu-id="107fb-128">msdyn\_ledgers</span><span class="sxs-lookup"><span data-stu-id="107fb-128">msdyn\_ledgers</span></span>
<span data-ttu-id="107fb-129">ExchangeRates</span><span class="sxs-lookup"><span data-stu-id="107fb-129">ExchangeRates</span></span>                    | <span data-ttu-id="107fb-130">msdyn\_currencyexchangerates</span><span class="sxs-lookup"><span data-stu-id="107fb-130">msdyn\_currencyexchangerates</span></span>
<span data-ttu-id="107fb-131">FinancialCalendarPeriod</span><span class="sxs-lookup"><span data-stu-id="107fb-131">FinancialCalendarPeriod</span></span>          | <span data-ttu-id="107fb-132">msdyn\_fiscalcalendarperiods</span><span class="sxs-lookup"><span data-stu-id="107fb-132">msdyn\_fiscalcalendarperiods</span></span>
<span data-ttu-id="107fb-133">DimensionAttributeEntity</span><span class="sxs-lookup"><span data-stu-id="107fb-133">DimensionAttributeEntity</span></span>         | <span data-ttu-id="107fb-134">msdyn\_dimensionattributes.md</span><span class="sxs-lookup"><span data-stu-id="107fb-134">msdyn\_dimensionattributes.md</span></span>
<span data-ttu-id="107fb-135">DimensionIntegrationFormatEntity</span><span class="sxs-lookup"><span data-stu-id="107fb-135">DimensionIntegrationFormatEntity</span></span> | <span data-ttu-id="107fb-136">msdyn\_financialdimensionformats.md</span><span class="sxs-lookup"><span data-stu-id="107fb-136">msdyn\_financialdimensionformats.md</span></span>
<span data-ttu-id="107fb-137">LedgerChartOfAccounts</span><span class="sxs-lookup"><span data-stu-id="107fb-137">LedgerChartOfAccounts</span></span>            | <span data-ttu-id="107fb-138">msdyn\_chartofaccounts.md</span><span class="sxs-lookup"><span data-stu-id="107fb-138">msdyn\_chartofaccounts.md</span></span>


[!include [banner](../includes/dual-write-symbols.md)]

[!include [Currency](dual-write/Currencies-transactioncurrencies.md)]

[!include [Fiscal calendar](dual-write/FiscalCalendar-msdyn-fiscalcalendars.md)]

[!include [Fiscal calendar year](dual-write/FiscalCalendarYear-msdyn-fiscalcalendaryears.md)]

[!include [Exchange rate types](dual-write/ExchRateType-msdyn-exchangeratetypes.md)]

[!include [Exchange rate pair](dual-write/ExchangeRateCurrencyPair-msdyn-currencyexchangeratepairs.md)]

[!include [Ledger fiscal periods](dual-write/FiscalPeriodEntity-msdyn-fiscalcalendarperiods.md)]

[!include [Main account category](dual-write/MainAccountCategory-msdyn-mainaccountcategory.md)]

[!include [Main account](dual-write/MainAccount-msdyn-mainaccounts.md)]

[!include [Ledger](dual-write/Ledger-msdyn-ledgers.md)]

[!include [Exchange rates](dual-write/ExchangeRates-msdyn-currencyexchangerates.md)]

[!include [Financial Calendar Period](dual-write/FiscalPeriodEntity-msdyn-fiscalcalendarperiods.md)]

[!include [Dimension attribute](dual-write/DimensionAttributeEntity-msdyn-dimensionattributes.md)]

[!include [Dimension integration format](dual-write/DimensionIntegrationFormatEntity-msdyn-financialdimensionformats.md)]

[!include [Chart Of Account](dual-write/LedgerChartOfAccounts-msdyn-chartofaccounts.md)]




