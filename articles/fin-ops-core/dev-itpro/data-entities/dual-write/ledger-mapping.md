---
title: Contabilità generale integrata
description: In questo argomento viene descritta l'integrazione dei dati di contabilità generale tra Finance and Operations e altre applicazioni Dynamics 365 tramite Common Data Service.
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
ms.openlocfilehash: d9bcec1d4bb0207a2c3e0d46f7661b666fea3736
ms.sourcegitcommit: 48c39c0c0949fe48b3536d9d2d0e451d561ff5c6
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2020
ms.locfileid: "3112216"
---
# <a name="integrated-ledger"></a><span data-ttu-id="49fa9-103">Contabilità integrata</span><span class="sxs-lookup"><span data-stu-id="49fa9-103">Integrated ledger</span></span>

[!include [banner](../../includes/banner.md)]

[!include [preview-banner](../../includes/preview-banner.md)]

<span data-ttu-id="49fa9-104">In un'applicazione aziendale, i dati della contabilità generale definiscono il core impostato per il modo in cui un'azienda fa affari.</span><span class="sxs-lookup"><span data-stu-id="49fa9-104">In a business application, ledger data defines the core set up for how a company does business.</span></span> <span data-ttu-id="49fa9-105">Ad esempio, i dati della contabilità generale descrivono l'anno fiscale dell'azienda, le valute in cui opera e i conti utilizzati.</span><span class="sxs-lookup"><span data-stu-id="49fa9-105">For example, ledger data describes the fiscal year the company follows, the currencies it transacts in, and the accounts it uses.</span></span> <span data-ttu-id="49fa9-106">In questo argomento viene descritta l'integrazione dei dati finanziari di base.</span><span class="sxs-lookup"><span data-stu-id="49fa9-106">This topic describes the integration of this core financial data.</span></span>

## <a name="templates"></a><span data-ttu-id="49fa9-107">Modelli</span><span class="sxs-lookup"><span data-stu-id="49fa9-107">Templates</span></span>

<span data-ttu-id="49fa9-108">I dati della contabilità generale includono una raccolta di mappe di entità finanziarie di base che funzionano in combinazione durante l'interazione con i dati, come illustrato nella seguente tabella.</span><span class="sxs-lookup"><span data-stu-id="49fa9-108">Ledger data includes a collection of core financial entity maps that work together during data interaction, as shown in the following table.</span></span>

<span data-ttu-id="49fa9-109">App di Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="49fa9-109">Finance and Operations apps</span></span>      | <span data-ttu-id="49fa9-110">App basata su modello in Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="49fa9-110">Model-driven app in Dynamics 365</span></span> | <span data-ttu-id="49fa9-111">descrizione</span><span class="sxs-lookup"><span data-stu-id="49fa9-111">Description</span></span>
---------------------------------|----------------------------------|------------
<span data-ttu-id="49fa9-112">Valute</span><span class="sxs-lookup"><span data-stu-id="49fa9-112">Currencies</span></span>                       | <span data-ttu-id="49fa9-113">transactioncurrencies</span><span class="sxs-lookup"><span data-stu-id="49fa9-113">transactioncurrencies</span></span>            |
<span data-ttu-id="49fa9-114">FiscalCalendar</span><span class="sxs-lookup"><span data-stu-id="49fa9-114">FiscalCalendar</span></span>                   | <span data-ttu-id="49fa9-115">msdyn\_fiscalcalendars</span><span class="sxs-lookup"><span data-stu-id="49fa9-115">msdyn\_fiscalcalendars</span></span>        |
<span data-ttu-id="49fa9-116">FiscalCalendarYear</span><span class="sxs-lookup"><span data-stu-id="49fa9-116">FiscalCalendarYear</span></span>               | <span data-ttu-id="49fa9-117">msdyn\_fiscalcalendaryears</span><span class="sxs-lookup"><span data-stu-id="49fa9-117">msdyn\_fiscalcalendaryears</span></span>        |
<span data-ttu-id="49fa9-118">ExchRateType</span><span class="sxs-lookup"><span data-stu-id="49fa9-118">ExchRateType</span></span>                     | <span data-ttu-id="49fa9-119">msdyn\_exchangeratetypes</span><span class="sxs-lookup"><span data-stu-id="49fa9-119">msdyn\_exchangeratetypes</span></span>        |
<span data-ttu-id="49fa9-120">ExchangeRateCurrencyPair</span><span class="sxs-lookup"><span data-stu-id="49fa9-120">ExchangeRateCurrencyPair</span></span>         | <span data-ttu-id="49fa9-121">msdyn\_currencyexchangeratepairs</span><span class="sxs-lookup"><span data-stu-id="49fa9-121">msdyn\_currencyexchangeratepairs</span></span>        |
<span data-ttu-id="49fa9-122">FiscalPeriodEntity</span><span class="sxs-lookup"><span data-stu-id="49fa9-122">FiscalPeriodEntity</span></span>               | <span data-ttu-id="49fa9-123">msdyn\_fiscalcalendarperiods</span><span class="sxs-lookup"><span data-stu-id="49fa9-123">msdyn\_fiscalcalendarperiods</span></span>        |
<span data-ttu-id="49fa9-124">MainAccountCategory</span><span class="sxs-lookup"><span data-stu-id="49fa9-124">MainAccountCategory</span></span>              | <span data-ttu-id="49fa9-125">msdyn\_mainaccountcategory</span><span class="sxs-lookup"><span data-stu-id="49fa9-125">msdyn\_mainaccountcategory</span></span>        |
<span data-ttu-id="49fa9-126">MainAccount</span><span class="sxs-lookup"><span data-stu-id="49fa9-126">MainAccount</span></span>                      | <span data-ttu-id="49fa9-127">msdyn\_mainaccounts</span><span class="sxs-lookup"><span data-stu-id="49fa9-127">msdyn\_mainaccounts</span></span>        |
<span data-ttu-id="49fa9-128">Contabilità generale</span><span class="sxs-lookup"><span data-stu-id="49fa9-128">Ledger</span></span>                           | <span data-ttu-id="49fa9-129">msdyn\_ledgers</span><span class="sxs-lookup"><span data-stu-id="49fa9-129">msdyn\_ledgers</span></span>        |
<span data-ttu-id="49fa9-130">ExchangeRates</span><span class="sxs-lookup"><span data-stu-id="49fa9-130">ExchangeRates</span></span>                    | <span data-ttu-id="49fa9-131">msdyn\_currencyexchangerates</span><span class="sxs-lookup"><span data-stu-id="49fa9-131">msdyn\_currencyexchangerates</span></span>        |
<span data-ttu-id="49fa9-132">FinancialCalendarPeriod</span><span class="sxs-lookup"><span data-stu-id="49fa9-132">FinancialCalendarPeriod</span></span>          | <span data-ttu-id="49fa9-133">msdyn\_fiscalcalendarperiods</span><span class="sxs-lookup"><span data-stu-id="49fa9-133">msdyn\_fiscalcalendarperiods</span></span>        |
<span data-ttu-id="49fa9-134">DimensionAttributeEntity</span><span class="sxs-lookup"><span data-stu-id="49fa9-134">DimensionAttributeEntity</span></span>         | <span data-ttu-id="49fa9-135">msdyn\_dimensionattributes</span><span class="sxs-lookup"><span data-stu-id="49fa9-135">msdyn\_dimensionattributes</span></span>        |
<span data-ttu-id="49fa9-136">DimensionIntegrationFormatEntity</span><span class="sxs-lookup"><span data-stu-id="49fa9-136">DimensionIntegrationFormatEntity</span></span> | <span data-ttu-id="49fa9-137">msdyn\_financialdimensionformats</span><span class="sxs-lookup"><span data-stu-id="49fa9-137">msdyn\_financialdimensionformats</span></span>        |
<span data-ttu-id="49fa9-138">LedgerChartOfAccounts</span><span class="sxs-lookup"><span data-stu-id="49fa9-138">LedgerChartOfAccounts</span></span>            | <span data-ttu-id="49fa9-139">msdyn\_chartofaccounts</span><span class="sxs-lookup"><span data-stu-id="49fa9-139">msdyn\_chartofaccounts</span></span>        |


[!include [banner](../../includes/dual-write-symbols.md)]

[!include [Currency](includes/Currencies-transactioncurrencies.md)]

[!include [Fiscal calendar](includes/FiscalCalendar-msdyn-fiscalcalendars.md)]

[!include [Fiscal calendar year](includes/FiscalCalendarYear-msdyn-fiscalcalendaryears.md)]

[!include [Exchange rate types](includes/ExchRateType-msdyn-exchangeratetypes.md)]

[!include [Exchange rate pair](includes/ExchangeRateCurrencyPair-msdyn-currencyexchangeratepairs.md)]

[!include [Ledger fiscal periods](includes/FiscalPeriodEntity-msdyn-fiscalcalendarperiods.md)]

[!include [Main account category](includes/MainAccountCategory-msdyn-mainaccountcategory.md)]

[!include [Main account](includes/MainAccount-msdyn-mainaccounts.md)]

[!include [Ledger](includes/Ledger-msdyn-ledgers.md)]

[!include [Exchange rates](includes/ExchangeRates-msdyn-currencyexchangerates.md)]

[!include [Financial Calendar Period](includes/FiscalPeriodEntity-msdyn-fiscalcalendarperiods.md)]

[!include [Dimension attribute](includes/DimensionAttributeEntity-msdyn-dimensionattributes.md)]

[!include [Dimension integration format](includes/DimensionIntegrationFormatEntity-msdyn-financialdimensionformats.md)]

[!include [Chart Of Account](includes/LedgerChartOfAccounts-msdyn-chartofaccounts.md)]




