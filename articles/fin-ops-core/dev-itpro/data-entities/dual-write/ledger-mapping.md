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
ms.openlocfilehash: 6bf1c554f56c1424da9fde98f67f80a6b7c95461
ms.sourcegitcommit: 54baab2a04e5c534fc2d1fd67b67e23a152d4e57
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "3019859"
---
# <a name="integrated-ledger"></a><span data-ttu-id="8ea93-103">Contabilità integrata</span><span class="sxs-lookup"><span data-stu-id="8ea93-103">Integrated ledger</span></span>

[!include [banner](../../includes/banner.md)]

[!include [preview-banner](../../includes/preview-banner.md)]

<span data-ttu-id="8ea93-104">In un'applicazione aziendale, i dati della contabilità generale definiscono il core impostato per il modo in cui un'azienda fa affari.</span><span class="sxs-lookup"><span data-stu-id="8ea93-104">In a business application, ledger data defines the core set up for how a company does business.</span></span> <span data-ttu-id="8ea93-105">Ad esempio, i dati della contabilità generale descrivono l'anno fiscale dell'azienda, le valute in cui opera e i conti utilizzati.</span><span class="sxs-lookup"><span data-stu-id="8ea93-105">For example, ledger data describes the fiscal year the company follows, the currencies it transacts in, and the accounts it uses.</span></span> <span data-ttu-id="8ea93-106">In questo argomento viene descritta l'integrazione dei dati finanziari di base.</span><span class="sxs-lookup"><span data-stu-id="8ea93-106">This topic describes the integration of this core financial data.</span></span>

## <a name="templates"></a><span data-ttu-id="8ea93-107">Modelli</span><span class="sxs-lookup"><span data-stu-id="8ea93-107">Templates</span></span>

<span data-ttu-id="8ea93-108">I dati della contabilità generale includono una raccolta di mappe di entità finanziarie di base che funzionano in combinazione durante l'interazione con i dati, come illustrato nella seguente tabella.</span><span class="sxs-lookup"><span data-stu-id="8ea93-108">Ledger data includes a collection of core financial entity maps that work together during data interaction, as shown in the following table.</span></span>

<span data-ttu-id="8ea93-109">App di Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="8ea93-109">Finance and Operations apps</span></span>      | <span data-ttu-id="8ea93-110">Altre app Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="8ea93-110">Other Dynamics 365 apps</span></span>
---------------------------------|---------------------------------
<span data-ttu-id="8ea93-111">Valute</span><span class="sxs-lookup"><span data-stu-id="8ea93-111">Currencies</span></span>                       | <span data-ttu-id="8ea93-112">transactioncurrencies</span><span class="sxs-lookup"><span data-stu-id="8ea93-112">transactioncurrencies</span></span>
<span data-ttu-id="8ea93-113">FiscalCalendar</span><span class="sxs-lookup"><span data-stu-id="8ea93-113">FiscalCalendar</span></span>                   | <span data-ttu-id="8ea93-114">msdyn\_fiscalcalendars</span><span class="sxs-lookup"><span data-stu-id="8ea93-114">msdyn\_fiscalcalendars</span></span>
<span data-ttu-id="8ea93-115">FiscalCalendarYear</span><span class="sxs-lookup"><span data-stu-id="8ea93-115">FiscalCalendarYear</span></span>               | <span data-ttu-id="8ea93-116">msdyn\_fiscalcalendaryears</span><span class="sxs-lookup"><span data-stu-id="8ea93-116">msdyn\_fiscalcalendaryears</span></span>
<span data-ttu-id="8ea93-117">ExchRateType</span><span class="sxs-lookup"><span data-stu-id="8ea93-117">ExchRateType</span></span>                     | <span data-ttu-id="8ea93-118">msdyn\_exchangeratetypes</span><span class="sxs-lookup"><span data-stu-id="8ea93-118">msdyn\_exchangeratetypes</span></span>
<span data-ttu-id="8ea93-119">ExchangeRateCurrencyPair</span><span class="sxs-lookup"><span data-stu-id="8ea93-119">ExchangeRateCurrencyPair</span></span>         | <span data-ttu-id="8ea93-120">msdyn\_currencyexchangeratepairs</span><span class="sxs-lookup"><span data-stu-id="8ea93-120">msdyn\_currencyexchangeratepairs</span></span>
<span data-ttu-id="8ea93-121">FiscalPeriodEntity</span><span class="sxs-lookup"><span data-stu-id="8ea93-121">FiscalPeriodEntity</span></span>               | <span data-ttu-id="8ea93-122">msdyn\_fiscalcalendarperiods</span><span class="sxs-lookup"><span data-stu-id="8ea93-122">msdyn\_fiscalcalendarperiods</span></span>
<span data-ttu-id="8ea93-123">MainAccountCategory</span><span class="sxs-lookup"><span data-stu-id="8ea93-123">MainAccountCategory</span></span>              | <span data-ttu-id="8ea93-124">msdyn\_mainaccountcategory</span><span class="sxs-lookup"><span data-stu-id="8ea93-124">msdyn\_mainaccountcategory</span></span>
<span data-ttu-id="8ea93-125">MainAccount</span><span class="sxs-lookup"><span data-stu-id="8ea93-125">MainAccount</span></span>                      | <span data-ttu-id="8ea93-126">msdyn\_mainaccounts</span><span class="sxs-lookup"><span data-stu-id="8ea93-126">msdyn\_mainaccounts</span></span>
<span data-ttu-id="8ea93-127">Contabilità generale</span><span class="sxs-lookup"><span data-stu-id="8ea93-127">Ledger</span></span>                           | <span data-ttu-id="8ea93-128">msdyn\_ledgers</span><span class="sxs-lookup"><span data-stu-id="8ea93-128">msdyn\_ledgers</span></span>
<span data-ttu-id="8ea93-129">ExchangeRates</span><span class="sxs-lookup"><span data-stu-id="8ea93-129">ExchangeRates</span></span>                    | <span data-ttu-id="8ea93-130">msdyn\_currencyexchangerates</span><span class="sxs-lookup"><span data-stu-id="8ea93-130">msdyn\_currencyexchangerates</span></span>
<span data-ttu-id="8ea93-131">FinancialCalendarPeriod</span><span class="sxs-lookup"><span data-stu-id="8ea93-131">FinancialCalendarPeriod</span></span>          | <span data-ttu-id="8ea93-132">msdyn\_fiscalcalendarperiods</span><span class="sxs-lookup"><span data-stu-id="8ea93-132">msdyn\_fiscalcalendarperiods</span></span>
<span data-ttu-id="8ea93-133">DimensionAttributeEntity</span><span class="sxs-lookup"><span data-stu-id="8ea93-133">DimensionAttributeEntity</span></span>         | <span data-ttu-id="8ea93-134">msdyn\_dimensionattributes.md</span><span class="sxs-lookup"><span data-stu-id="8ea93-134">msdyn\_dimensionattributes.md</span></span>
<span data-ttu-id="8ea93-135">DimensionIntegrationFormatEntity</span><span class="sxs-lookup"><span data-stu-id="8ea93-135">DimensionIntegrationFormatEntity</span></span> | <span data-ttu-id="8ea93-136">msdyn\_financialdimensionformats.md</span><span class="sxs-lookup"><span data-stu-id="8ea93-136">msdyn\_financialdimensionformats.md</span></span>
<span data-ttu-id="8ea93-137">LedgerChartOfAccounts</span><span class="sxs-lookup"><span data-stu-id="8ea93-137">LedgerChartOfAccounts</span></span>            | <span data-ttu-id="8ea93-138">msdyn\_chartofaccounts.md</span><span class="sxs-lookup"><span data-stu-id="8ea93-138">msdyn\_chartofaccounts.md</span></span>


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




