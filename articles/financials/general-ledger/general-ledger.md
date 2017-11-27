---
title: "Home page di report finanziari e contabilità generale"
description: "È possibile utilizzare la contabilità generale per definire e gestire i record finanziari della persona giuridica."
author: twheeloc
manager: AnnBe
ms.date: 08/31/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 65431
ms.assetid: d2c604df-daae-42cd-82d9-c80e3dee4a60
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: e544c592429d00b1ce464740f4e82cb75d10412b
ms.contentlocale: it-it
ms.lasthandoff: 11/03/2017

---

# <a name="general-ledger"></a><span data-ttu-id="8ed88-103">Contabilità generale</span><span class="sxs-lookup"><span data-stu-id="8ed88-103">General ledger</span></span> 

[!include[banner](../includes/banner.md)]


<span data-ttu-id="8ed88-104">È possibile utilizzare la contabilità generale per definire e gestire i record finanziari della persona giuridica.</span><span class="sxs-lookup"><span data-stu-id="8ed88-104">Use General ledger to define and manage the legal entity’s financial records.</span></span> <span data-ttu-id="8ed88-105">La contabilità generale è un registro di voci in Dare e Avere.</span><span class="sxs-lookup"><span data-stu-id="8ed88-105">The general ledger is a register of debit and credit entries.</span></span> <span data-ttu-id="8ed88-106">Tali voci vengono classificate utilizzando i conti elencati in un piano dei conti.</span><span class="sxs-lookup"><span data-stu-id="8ed88-106">These entries are classified using the accounts that are listed in a chart of accounts.</span></span> 

 - [<span data-ttu-id="8ed88-107">Definire il piano dei conti</span><span class="sxs-lookup"><span data-stu-id="8ed88-107">Plan your chart of accounts</span></span>](plan-chart-of-accounts.md)
 - [<span data-ttu-id="8ed88-108">Tipi di conto principale</span><span class="sxs-lookup"><span data-stu-id="8ed88-108">Main account types</span></span>](main-account-types.md)

<span data-ttu-id="8ed88-109">È possibile allocare o distribuire gli importi monetari a uno o più conti o combinazioni di conto e dimensione in base alle regole di allocazione.</span><span class="sxs-lookup"><span data-stu-id="8ed88-109">You can allocate, or distribute, monetary amounts to one or more accounts or account and dimension combinations based on allocation rules.</span></span> <span data-ttu-id="8ed88-110">Sono disponibili due tipi di allocazione: fissa e variabile.</span><span class="sxs-lookup"><span data-stu-id="8ed88-110">There are two types of allocations: fixed and variable.</span></span> <span data-ttu-id="8ed88-111">È inoltre possibile liquidate transazioni tra conti CoGe e rivalutazione degli importi in valuta.</span><span class="sxs-lookup"><span data-stu-id="8ed88-111">You can also settle transactions between ledger accounts and revalue currency amounts.</span></span> <span data-ttu-id="8ed88-112">Al termine di un esercizio è necessario generare transazioni di chiusura e preparare i conti per l'anno fiscale successivo.</span><span class="sxs-lookup"><span data-stu-id="8ed88-112">At the end of a fiscal year, you must generate closing transactions and prepare your accounts for the next fiscal year.</span></span> <span data-ttu-id="8ed88-113">È possibile utilizzare la funzionalità di consolidamento per combinare i risultati finanziari di più persone giuridiche affiliate ottenendo un risultato per un'unica organizzazione consolidata.</span><span class="sxs-lookup"><span data-stu-id="8ed88-113">You can use the consolidation functionality to combine the financial results for several subsidiary legal entities into results for a single, consolidated organization.</span></span> <span data-ttu-id="8ed88-114">Le affiliate possono essere nello stesso database di Microsoft Dynamics 365 for Finance and Operations o in database separati.</span><span class="sxs-lookup"><span data-stu-id="8ed88-114">The subsidiaries can be in the same Microsoft Dynamics 365 for Finance and Operations database or in separate databases.</span></span>

- [<span data-ttu-id="8ed88-115">Panoramica dell'eliminazione e del consolidamento</span><span class="sxs-lookup"><span data-stu-id="8ed88-115">Consolidation and elimination overview</span></span>](../budgeting/consolidation-elimination-overview.md)
- [<span data-ttu-id="8ed88-116">Saldi dei conti della contabilità generale</span><span class="sxs-lookup"><span data-stu-id="8ed88-116">General ledger account balances</span></span>](general-ledger-account-balances.md)
- [<span data-ttu-id="8ed88-117">Dimensioni finanziarie</span><span class="sxs-lookup"><span data-stu-id="8ed88-117">Financial dimensions</span></span>](financial-dimensions.md)

<span data-ttu-id="8ed88-118">[![Processo aziendale](./media/GL-process.PNG)](./media/GL-process.PNG)</span><span class="sxs-lookup"><span data-stu-id="8ed88-118">[![Business process](./media/GL-process.PNG)](./media/GL-process.PNG)</span></span>

# <a name="sales-tax"></a><span data-ttu-id="8ed88-119">IVA</span><span class="sxs-lookup"><span data-stu-id="8ed88-119">Sales tax</span></span>
<span data-ttu-id="8ed88-120">Ogni società riscuote imposte e versa gli importi corrispondenti a vari uffici tributari.</span><span class="sxs-lookup"><span data-stu-id="8ed88-120">Every company collects and pays taxes to various tax authorities.</span></span> <span data-ttu-id="8ed88-121">Le norme e le aliquote variano a seconda del paese, dello stato/regione, della provincia e della città.</span><span class="sxs-lookup"><span data-stu-id="8ed88-121">The rules and rates vary by country/region, state, county, and city.</span></span>
<span data-ttu-id="8ed88-122">Le regole devono inoltre essere aggiornate periodicamente ogni volta che vengono modificati i requisiti dagli uffici tributari.</span><span class="sxs-lookup"><span data-stu-id="8ed88-122">In addition, the rules must be updated periodically when tax authorities change their requirements.</span></span> <span data-ttu-id="8ed88-123">I codici IVA includono le informazioni di base sugli importi da riscuotere e da versare.</span><span class="sxs-lookup"><span data-stu-id="8ed88-123">Sales tax codes contain the basic information about how much you collect and pay to the authorities.</span></span> <span data-ttu-id="8ed88-124">Quando si impostano i codici IVA, vengono definiti gli importi o le percentuali da riscuotere.</span><span class="sxs-lookup"><span data-stu-id="8ed88-124">When you set up sales tax codes, you define the amounts or percentages that must be collected.</span></span> <span data-ttu-id="8ed88-125">È inoltre necessario definire i vari metodi tramite cui tali importi o percentuali vengono applicati agli importi delle transazioni.</span><span class="sxs-lookup"><span data-stu-id="8ed88-125">You also define the various methods by which those amounts or percentages are applied to transaction amounts.</span></span> <span data-ttu-id="8ed88-126">Negli argomenti inclusi in questa sezione sono riportate informazioni sull'impostazione dei codici IVA in base alle aliquote e ai metodi richiesti dagli uffici tributari locali.</span><span class="sxs-lookup"><span data-stu-id="8ed88-126">The topics in this section provide information about how to set up sales tax codes for the methods and rates that your tax authorities require.</span></span>

 - [<span data-ttu-id="8ed88-127">Panoramica dell'IVA</span><span class="sxs-lookup"><span data-stu-id="8ed88-127">Sales tax overview</span></span>](indirect-taxes-overview.md)
 - [<span data-ttu-id="8ed88-128">Aliquote IVA basate su Imponibile marginale e Metodo di calcolo</span><span class="sxs-lookup"><span data-stu-id="8ed88-128">Sales tax rates based on the Marginal base and Calculation methods</span></span>](marginal-base-field.md)
 - [<span data-ttu-id="8ed88-129">Pagamenti IVA e regole di arrotondamento</span><span class="sxs-lookup"><span data-stu-id="8ed88-129">Sales tax payments and rounding rules</span></span>](round-sales-tax-payments.md)


### <a name="additional-resources"></a><span data-ttu-id="8ed88-130">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="8ed88-130">Additional resources</span></span>

#### <a name="whats-new-and-in-development"></a><span data-ttu-id="8ed88-131">Novità rilasciate e in via di sviluppo</span><span class="sxs-lookup"><span data-stu-id="8ed88-131">What's new and in development</span></span>

<span data-ttu-id="8ed88-132">Passare alla [roadmap di Microsoft Dynamics 365](https://roadmap.dynamics.com/) per un elenco delle nuove funzionalità rilasciate e di quelle che sono in via di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="8ed88-132">Go to the [Microsoft Dynamics 365 Roadmap](https://roadmap.dynamics.com/) to see what new features have been released and what new features are in development.</span></span> 

#### <a name="blogs"></a><span data-ttu-id="8ed88-133">Blog</span><span class="sxs-lookup"><span data-stu-id="8ed88-133">Blogs</span></span>

<span data-ttu-id="8ed88-134">Per opinioni, notizie e altre informazioni sulla contabilità fornitori e su altre soluzioni, fare riferimento al [blog di Microsoft Dynamics 365](https://community.dynamics.com/b/msftdynamicsblog?c=Enterprise).</span><span class="sxs-lookup"><span data-stu-id="8ed88-134">You can find opinions, news, and other information about Accounts payable and other solutions on the [Microsoft Dynamics 365 blog](https://community.dynamics.com/b/msftdynamicsblog?c=Enterprise).</span></span>

<span data-ttu-id="8ed88-135">Sono disponibili numerosi post sulla contabilità generale nel [blog del team di prodotto Microsoft Dynamics AX](https://blogs.msdn.microsoft.com/dax/).</span><span class="sxs-lookup"><span data-stu-id="8ed88-135">There are many posts about General ledger on the [Microsoft Dynamics AX product team blog](https://blogs.msdn.microsoft.com/dax/).</span></span> <span data-ttu-id="8ed88-136">Sebbene alcuni di questi post siano stati scritti per la versione precedente della contabilità generale, gli stessi concetti si applicano ancora e le procedure sono simili nella versione corrente.</span><span class="sxs-lookup"><span data-stu-id="8ed88-136">Although some of these posts were written for the previous version of General ledger, the same concepts still apply, and the procedures are also similar in the current version.</span></span>

<span data-ttu-id="8ed88-137">Il [blog della community di partner di Microsoft Dynamics Operations](https://community.dynamics.com/partner/b/operationspartnercommunityblog) offre ai partner Microsoft Dynamics una singola risorsa per conoscere le novità e le tendenze di MBS Operations.</span><span class="sxs-lookup"><span data-stu-id="8ed88-137">The [Microsoft Dynamics Operations Partner Community Blog](https://community.dynamics.com/partner/b/operationspartnercommunityblog) gives Microsoft Dynamics Partners a single resource where they can learn what is new and trending in MBS Operations.</span></span>

#### <a name="task-guides"></a><span data-ttu-id="8ed88-138">Guide attività</span><span class="sxs-lookup"><span data-stu-id="8ed88-138">Task guides</span></span>
<span data-ttu-id="8ed88-139">Informazioni aggiuntive sono disponibili come guide attività in Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="8ed88-139">Additional help is available as task guides inside Finance and Operations.</span></span> <span data-ttu-id="8ed88-140">Per accedere alle guide attività, fare clic sul pulsante ? in qualsiasi pagina.</span><span class="sxs-lookup"><span data-stu-id="8ed88-140">To access task guides, click the Help button on any page.</span></span>

#### <a name="videos"></a><span data-ttu-id="8ed88-141">Video</span><span class="sxs-lookup"><span data-stu-id="8ed88-141">Videos</span></span>

<span data-ttu-id="8ed88-142">Controllare i video illustrativi disponibili nel [canale YouTube di Microsoft Dynamics 365](https://www.youtube.com/channel/UCJGCg4rB3QSs8y_1FquelBQ).</span><span class="sxs-lookup"><span data-stu-id="8ed88-142">Check out the how-to videos that are now available on the [Microsoft Dynamics 365 YouTube Channel](https://www.youtube.com/channel/UCJGCg4rB3QSs8y_1FquelBQ).</span></span>


