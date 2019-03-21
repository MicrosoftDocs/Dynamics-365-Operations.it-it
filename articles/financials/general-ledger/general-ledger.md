---
title: Home page di report finanziari e contabilità generale
description: È possibile utilizzare la contabilità generale per definire e gestire i record finanziari della persona giuridica.
author: ShylaThompson
manager: AnnBe
ms.date: 08/31/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: GeneralJournalEntryWorkspace
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 65431
ms.assetid: d2c604df-daae-42cd-82d9-c80e3dee4a60
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0b6683107f4b2dbe36af78749612ce950ea19582
ms.sourcegitcommit: afab5269613d1d1dfd79cd39370b747dee13d3fc
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2019
ms.locfileid: "403239"
---
# <a name="general-ledger"></a><span data-ttu-id="4797f-103">Contabilità generale</span><span class="sxs-lookup"><span data-stu-id="4797f-103">General ledger</span></span> 

[!include [banner](../includes/banner.md)]

<span data-ttu-id="4797f-104">È possibile utilizzare la contabilità generale per definire e gestire i record finanziari della persona giuridica.</span><span class="sxs-lookup"><span data-stu-id="4797f-104">Use General ledger to define and manage the legal entity’s financial records.</span></span> <span data-ttu-id="4797f-105">La contabilità generale è un registro di voci in Dare e Avere.</span><span class="sxs-lookup"><span data-stu-id="4797f-105">The general ledger is a register of debit and credit entries.</span></span> <span data-ttu-id="4797f-106">Tali voci vengono classificate utilizzando i conti elencati in un piano dei conti.</span><span class="sxs-lookup"><span data-stu-id="4797f-106">These entries are classified using the accounts that are listed in a chart of accounts.</span></span> 

 - [<span data-ttu-id="4797f-107">Definire il piano dei conti</span><span class="sxs-lookup"><span data-stu-id="4797f-107">Plan your chart of accounts</span></span>](plan-chart-of-accounts.md)
 - [<span data-ttu-id="4797f-108">Tipi di conto principale</span><span class="sxs-lookup"><span data-stu-id="4797f-108">Main account types</span></span>](main-account-types.md)

<span data-ttu-id="4797f-109">È possibile allocare o distribuire gli importi monetari a uno o più conti o combinazioni di conto e dimensione in base alle regole di allocazione.</span><span class="sxs-lookup"><span data-stu-id="4797f-109">You can allocate, or distribute, monetary amounts to one or more accounts or account and dimension combinations based on allocation rules.</span></span> <span data-ttu-id="4797f-110">Sono disponibili due tipi di allocazione: fissa e variabile.</span><span class="sxs-lookup"><span data-stu-id="4797f-110">There are two types of allocations: fixed and variable.</span></span> <span data-ttu-id="4797f-111">È inoltre possibile liquidate transazioni tra conti CoGe e rivalutazione degli importi in valuta.</span><span class="sxs-lookup"><span data-stu-id="4797f-111">You can also settle transactions between ledger accounts and revalue currency amounts.</span></span> <span data-ttu-id="4797f-112">Al termine di un esercizio è necessario generare transazioni di chiusura e preparare i conti per l'anno fiscale successivo.</span><span class="sxs-lookup"><span data-stu-id="4797f-112">At the end of a fiscal year, you must generate closing transactions and prepare your accounts for the next fiscal year.</span></span> <span data-ttu-id="4797f-113">È possibile utilizzare la funzionalità di consolidamento per combinare i risultati finanziari di più persone giuridiche affiliate ottenendo un risultato per un'unica organizzazione consolidata.</span><span class="sxs-lookup"><span data-stu-id="4797f-113">You can use the consolidation functionality to combine the financial results for several subsidiary legal entities into results for a single, consolidated organization.</span></span> <span data-ttu-id="4797f-114">Le affiliate possono essere nello stesso database di Microsoft Dynamics 365 for Finance and Operations o in database separati.</span><span class="sxs-lookup"><span data-stu-id="4797f-114">The subsidiaries can be in the same Microsoft Dynamics 365 for Finance and Operations database or in separate databases.</span></span>

- [<span data-ttu-id="4797f-115">Panoramica dell'eliminazione e del consolidamento</span><span class="sxs-lookup"><span data-stu-id="4797f-115">Consolidation and elimination overview</span></span>](../budgeting/consolidation-elimination-overview.md)
- [<span data-ttu-id="4797f-116">Saldi dei conti della contabilità generale</span><span class="sxs-lookup"><span data-stu-id="4797f-116">General ledger account balances</span></span>](general-ledger-account-balances.md)
- [<span data-ttu-id="4797f-117">Dimensioni finanziarie</span><span class="sxs-lookup"><span data-stu-id="4797f-117">Financial dimensions</span></span>](financial-dimensions.md)

<span data-ttu-id="4797f-118">[![Processo aziendale](./media/GL-process.PNG)](./media/GL-process.PNG)</span><span class="sxs-lookup"><span data-stu-id="4797f-118">[![Business process](./media/GL-process.PNG)](./media/GL-process.PNG)</span></span>

## <a name="sales-tax"></a><span data-ttu-id="4797f-119">IVA</span><span class="sxs-lookup"><span data-stu-id="4797f-119">Sales tax</span></span>
<span data-ttu-id="4797f-120">Ogni società riscuote imposte e versa gli importi corrispondenti a vari uffici tributari.</span><span class="sxs-lookup"><span data-stu-id="4797f-120">Every company collects and pays taxes to various tax authorities.</span></span> <span data-ttu-id="4797f-121">Le norme e le aliquote variano a seconda del paese, dello stato/regione, della provincia e della città.</span><span class="sxs-lookup"><span data-stu-id="4797f-121">The rules and rates vary by country/region, state, county, and city.</span></span>
<span data-ttu-id="4797f-122">Le regole devono inoltre essere aggiornate periodicamente ogni volta che vengono modificati i requisiti dagli uffici tributari.</span><span class="sxs-lookup"><span data-stu-id="4797f-122">In addition, the rules must be updated periodically when tax authorities change their requirements.</span></span> <span data-ttu-id="4797f-123">I codici IVA includono le informazioni di base sugli importi da riscuotere e da versare.</span><span class="sxs-lookup"><span data-stu-id="4797f-123">Sales tax codes contain the basic information about how much you collect and pay to the authorities.</span></span> <span data-ttu-id="4797f-124">Quando si impostano i codici IVA, vengono definiti gli importi o le percentuali da riscuotere.</span><span class="sxs-lookup"><span data-stu-id="4797f-124">When you set up sales tax codes, you define the amounts or percentages that must be collected.</span></span> <span data-ttu-id="4797f-125">È inoltre necessario definire i vari metodi tramite cui tali importi o percentuali vengono applicati agli importi delle transazioni.</span><span class="sxs-lookup"><span data-stu-id="4797f-125">You also define the various methods by which those amounts or percentages are applied to transaction amounts.</span></span> <span data-ttu-id="4797f-126">Negli argomenti inclusi in questa sezione sono riportate informazioni sull'impostazione dei codici IVA in base alle aliquote e ai metodi richiesti dagli uffici tributari locali.</span><span class="sxs-lookup"><span data-stu-id="4797f-126">The topics in this section provide information about how to set up sales tax codes for the methods and rates that your tax authorities require.</span></span>

 - [<span data-ttu-id="4797f-127">Panoramica dell'IVA</span><span class="sxs-lookup"><span data-stu-id="4797f-127">Sales tax overview</span></span>](indirect-taxes-overview.md)
 - [<span data-ttu-id="4797f-128">Aliquote IVA basate su Imponibile marginale e Metodo di calcolo</span><span class="sxs-lookup"><span data-stu-id="4797f-128">Sales tax rates based on the Marginal base and Calculation methods</span></span>](marginal-base-field.md)
 - [<span data-ttu-id="4797f-129">Pagamenti IVA e regole di arrotondamento</span><span class="sxs-lookup"><span data-stu-id="4797f-129">Sales tax payments and rounding rules</span></span>](round-sales-tax-payments.md)


## <a name="additional-resources"></a><span data-ttu-id="4797f-130">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="4797f-130">Additional resources</span></span>

#### <a name="whats-new-and-in-development"></a><span data-ttu-id="4797f-131">Novità rilasciate e in via di sviluppo</span><span class="sxs-lookup"><span data-stu-id="4797f-131">What's new and in development</span></span>

<span data-ttu-id="4797f-132">Consultare le [Note sulla versione di Microsoft Dynamics 365](https://go.microsoft.com/fwlink/?linkid=2010158) per informazioni sulle nuove funzionalità pianificate.</span><span class="sxs-lookup"><span data-stu-id="4797f-132">Go to the [Microsoft Dynamics 365 Release Notes](https://go.microsoft.com/fwlink/?linkid=2010158) to see what new features have been planned.</span></span> 

#### <a name="blogs"></a><span data-ttu-id="4797f-133">Blog</span><span class="sxs-lookup"><span data-stu-id="4797f-133">Blogs</span></span>

<span data-ttu-id="4797f-134">È possibile trovare pareri, notizie e altre informazioni sul [blog di Microsoft Dynamics 365](https://community.dynamics.com/b/msftdynamicsblog?c=Enterprise) e il [blog di Microsoft Dynamics Finance and Operations - Financials](https://community.dynamics.com/365/financeandoperations/b/financials).</span><span class="sxs-lookup"><span data-stu-id="4797f-134">You can find opinions, news, and other information on the [Microsoft Dynamics 365 blog](https://community.dynamics.com/b/msftdynamicsblog?c=Enterprise) and the [Microsoft Dynamics 365 Finance and Operations - Financials blog](https://community.dynamics.com/365/financeandoperations/b/financials).</span></span>

<span data-ttu-id="4797f-135">Il [blog della community di partner di Microsoft Dynamics Operations](https://community.dynamics.com/partner/b/operationspartnercommunityblog) offre ai partner Microsoft Dynamics una singola risorsa per conoscere le novità e le tendenze di MBS Operations.</span><span class="sxs-lookup"><span data-stu-id="4797f-135">The [Microsoft Dynamics Operations Partner Community Blog](https://community.dynamics.com/partner/b/operationspartnercommunityblog) gives Microsoft Dynamics Partners a single resource where they can learn what is new and trending in MBS Operations.</span></span>

### <a name="videos"></a><span data-ttu-id="4797f-136">Video</span><span class="sxs-lookup"><span data-stu-id="4797f-136">Videos</span></span>

<span data-ttu-id="4797f-137">Vedere i video dimostrativi disponibili nel [canale di Microsoft Dynamics 365 su YouTube](https://www.youtube.com/channel/UCJGCg4rB3QSs8y_1FquelBQ).</span><span class="sxs-lookup"><span data-stu-id="4797f-137">Check out the how-to videos that are now available on the [Microsoft Dynamics 365 YouTube Channel](https://www.youtube.com/channel/UCJGCg4rB3QSs8y_1FquelBQ).</span></span>

#### <a name="community-blogs"></a><span data-ttu-id="4797f-138">Blog della Community</span><span class="sxs-lookup"><span data-stu-id="4797f-138">Community blogs</span></span>

- [<span data-ttu-id="4797f-139">Informazioni di cui è necessario disporre sulla contabilità generale in Dynamics 365 for Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="4797f-139">What you should know about ledger in Dynamics 365 for Finance and Operations</span></span>](https://financefunction.tech/2018/04/29/what-you-should-know-about-ledger-in-dynamics-365-for-finance-and-operations)

