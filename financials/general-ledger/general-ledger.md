---
title: "Home page di report finanziari e contabilità generale"
description: "È possibile utilizzare la contabilità generale per definire e gestire i record finanziari della persona giuridica. La contabilità generale è un registro di voci in Dare e Avere. Tali voci vengono classificate utilizzando i conti elencati in un piano dei conti."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 65431
ms.assetid: d2c604df-daae-42cd-82d9-c80e3dee4a60
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 08c38aada355583c5a6872f75b57db95d9b81786
ms.openlocfilehash: 78f3d9c27767c089ac686f333cae3cb50c03ee18
ms.contentlocale: it-it
ms.lasthandoff: 07/18/2017

---

# <a name="general-ledger"></a><span data-ttu-id="daa8c-105">Contabilità generale</span><span class="sxs-lookup"><span data-stu-id="daa8c-105">General ledger</span></span> 

[!include[banner](../includes/banner.md)]


<span data-ttu-id="daa8c-106">È possibile utilizzare la contabilità generale per definire e gestire i record finanziari della persona giuridica.</span><span class="sxs-lookup"><span data-stu-id="daa8c-106">Use General ledger to define and manage the legal entity’s financial records.</span></span> <span data-ttu-id="daa8c-107">La contabilità generale è un registro di voci in Dare e Avere.</span><span class="sxs-lookup"><span data-stu-id="daa8c-107">The general ledger is a register of debit and credit entries.</span></span> <span data-ttu-id="daa8c-108">Tali voci vengono classificate utilizzando i conti elencati in un piano dei conti.</span><span class="sxs-lookup"><span data-stu-id="daa8c-108">These entries are classified using the accounts that are listed in a chart of accounts.</span></span> 

<span data-ttu-id="daa8c-109">È possibile allocare o distribuire gli importi monetari a uno o più conti o combinazioni di conto e dimensione in base alle regole di allocazione.</span><span class="sxs-lookup"><span data-stu-id="daa8c-109">You can allocate, or distribute, monetary amounts to one or more accounts or account and dimension combinations based on allocation rules.</span></span> <span data-ttu-id="daa8c-110">Sono disponibili due tipi di allocazione: fissa e variabile.</span><span class="sxs-lookup"><span data-stu-id="daa8c-110">There are two types of allocations: fixed and variable.</span></span> <span data-ttu-id="daa8c-111">È inoltre possibile liquidate transazioni tra conti CoGe e rivalutazione degli importi in valuta.</span><span class="sxs-lookup"><span data-stu-id="daa8c-111">You can also settle transactions between ledger accounts and revalue currency amounts.</span></span> <span data-ttu-id="daa8c-112">Al termine di un esercizio è necessario generare transazioni di chiusura e preparare i conti per l'anno fiscale successivo.</span><span class="sxs-lookup"><span data-stu-id="daa8c-112">At the end of a fiscal year, you must generate closing transactions and prepare your accounts for the next fiscal year.</span></span> <span data-ttu-id="daa8c-113">È possibile utilizzare la funzionalità di consolidamento per combinare i risultati finanziari di più persone giuridiche affiliate ottenendo un risultato per un'unica organizzazione consolidata.</span><span class="sxs-lookup"><span data-stu-id="daa8c-113">You can use the consolidation functionality to combine the financial results for several subsidiary legal entities into results for a single, consolidated organization.</span></span> <span data-ttu-id="daa8c-114">Le affiliate possono essere nello stesso database di Microsoft Dynamics 365 for Finance and Operations o in database separati.</span><span class="sxs-lookup"><span data-stu-id="daa8c-114">The subsidiaries can be in the same Microsoft Dynamics 365 for Finance and Operations database or in separate databases.</span></span>

# <a name="sales-tax"></a><span data-ttu-id="daa8c-115">IVA</span><span class="sxs-lookup"><span data-stu-id="daa8c-115">Sales tax</span></span>
<span data-ttu-id="daa8c-116">Ogni società riscuote imposte e versa gli importi corrispondenti a vari uffici tributari.</span><span class="sxs-lookup"><span data-stu-id="daa8c-116">Every company collects and pays taxes to various tax authorities.</span></span> <span data-ttu-id="daa8c-117">Le norme e le aliquote variano a seconda del paese, dello stato/regione, della provincia e della città.</span><span class="sxs-lookup"><span data-stu-id="daa8c-117">The rules and rates vary by country/region, state, county, and city.</span></span> <span data-ttu-id="daa8c-118">Le regole devono inoltre essere aggiornate periodicamente ogni volta che vengono modificati i requisiti dagli uffici tributari.</span><span class="sxs-lookup"><span data-stu-id="daa8c-118">In addition, the rules must be updated periodically when tax authorities change their requirements.</span></span> <span data-ttu-id="daa8c-119">I codici IVA includono le informazioni di base sugli importi da riscuotere e da versare.</span><span class="sxs-lookup"><span data-stu-id="daa8c-119">Sales tax codes contain the basic information about how much you collect and pay to the authorities.</span></span> <span data-ttu-id="daa8c-120">Quando si impostano i codici IVA, vengono definiti gli importi o le percentuali da riscuotere.</span><span class="sxs-lookup"><span data-stu-id="daa8c-120">When you set up sales tax codes, you define the amounts or percentages that must be collected.</span></span> <span data-ttu-id="daa8c-121">È inoltre necessario definire i vari metodi tramite cui tali importi o percentuali vengono applicati agli importi delle transazioni.</span><span class="sxs-lookup"><span data-stu-id="daa8c-121">You also define the various methods by which those amounts or percentages are applied to transaction amounts.</span></span> <span data-ttu-id="daa8c-122">Negli argomenti inclusi in questa sezione sono riportate informazioni sull'impostazione dei codici IVA in base alle aliquote e ai metodi richiesti dagli uffici tributari locali.</span><span class="sxs-lookup"><span data-stu-id="daa8c-122">The topics in this section provide information about how to set up sales tax codes for the methods and rates that your tax authorities require.</span></span>







