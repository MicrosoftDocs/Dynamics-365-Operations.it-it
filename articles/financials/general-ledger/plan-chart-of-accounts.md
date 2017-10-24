---
title: Pianificare il piano dei conti
description: Questo articolo fornisce le informazioni che consentono di pianificare il piano dei conti per l'organizzazione.
author: aprilolson
manager: AnnBe
ms.date: 08/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: DimensionConfigureAccountStructure, LedgerChartOfAccounts
audience: Application User
ms.reviewer: robinr
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 14051
ms.assetid: 10edb129-33f0-4cf9-b2a7-4b7ffa09b229
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 848da7ec8f4a7915f3b78945b808b564f4510434
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---

# <a name="plan-your-chart-of-accounts"></a><span data-ttu-id="4e158-103">Pianificare il piano dei conti</span><span class="sxs-lookup"><span data-stu-id="4e158-103">Plan your chart of accounts</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="4e158-104">Questo articolo fornisce le informazioni che consentono di pianificare il piano dei conti per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="4e158-104">This article provides information that will help you plan the chart of accounts for your organization.</span></span>

<span data-ttu-id="4e158-105">Per tenere traccia e gestire le informazioni finanziarie in un'organizzazione, è possibile impostare un piano dei conti.</span><span class="sxs-lookup"><span data-stu-id="4e158-105">To track and maintain financial information in an organization, you can set up a chart of accounts.</span></span> <span data-ttu-id="4e158-106">Un piano dei conti è un insieme di conti che definiscono una struttura finanziaria.</span><span class="sxs-lookup"><span data-stu-id="4e158-106">A chart of accounts is a collection of accounts that define a financial framework.</span></span> <span data-ttu-id="4e158-107">Per tenere ulteriormente traccia delle transazioni in tali conti, è possibile aggiungere segmenti, definiti dimensioni finanziarie.</span><span class="sxs-lookup"><span data-stu-id="4e158-107">To further track the transactions in these accounts, you can add segments, which are known as financial dimensions.</span></span> <span data-ttu-id="4e158-108">Ad esempio, un conto spese potrebbe includere dimensioni finanziarie denominate Reparto, Centro di costo e Scopo.</span><span class="sxs-lookup"><span data-stu-id="4e158-108">For example, an expense account might include financial dimensions that are named Department, Cost center, and Purpose.</span></span> <span data-ttu-id="4e158-109">Le regole definite dall'utente, definite strutture dei conti e regole avanzate, determinano le modalità di collegamento delle dimensioni finanziarie ai conti principali e ad altre dimensioni finanziarie, nonché quelle di immissione delle transazioni.</span><span class="sxs-lookup"><span data-stu-id="4e158-109">User-defined rules, which are known as account structures and advanced rules, determine how financial dimensions are attached to the main accounts and other financial dimensions, and also how transactions are entered.</span></span> 

<span data-ttu-id="4e158-110">Il piano dei conti consiste in un elenco strutturato dei conti CoGe di una persona giuridica.</span><span class="sxs-lookup"><span data-stu-id="4e158-110">The chart of accounts is a structured list of a legal entity’s general ledger accounts.</span></span> <span data-ttu-id="4e158-111">Questo elenco viene utilizzato per preparare i report finanziari destinati agli uffici competenti e ai proprietari.</span><span class="sxs-lookup"><span data-stu-id="4e158-111">The list is used to prepare financial reports for authorities and owners.</span></span> <span data-ttu-id="4e158-112">I conti vengono raggruppati in tipi di conti, quindi ulteriormente aggregati in categorie più ampie.</span><span class="sxs-lookup"><span data-stu-id="4e158-112">The accounts are grouped into types of accounts and then further aggregated into larger categories.</span></span> <span data-ttu-id="4e158-113">A livello generale, i conti vengono raggruppati in costi e ricavi (conti di gestione) e in attività e passività (conti collettivi).</span><span class="sxs-lookup"><span data-stu-id="4e158-113">At the most general level, the accounts are grouped as revenues and costs (operating accounts), and assets and liabilities (balance accounts).</span></span> 

<span data-ttu-id="4e158-114">Un piano dei conti può essere condiviso e utilizzato da qualsiasi persona giuridica in un'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="4e158-114">A chart of accounts can be shared and used by any legal entity in an organization.</span></span> <span data-ttu-id="4e158-115">Il piano dei conti utilizzato da una persona giuridica è definito nella pagina **Contabilità generale**.</span><span class="sxs-lookup"><span data-stu-id="4e158-115">The chart of accounts that is used by a legal entity is defined on the **Ledger** page.</span></span> 

<span data-ttu-id="4e158-116">Di seguito vengono indicati alcuni fattori da prendere in considerazione quando si pianifica la struttura del piano dei conti per l'organizzazione:</span><span class="sxs-lookup"><span data-stu-id="4e158-116">Here are some of the factors that you must consider when you plan the structure of the chart of accounts for your organization:</span></span>

-   <span data-ttu-id="4e158-117">Gli adempimenti richiesti dal paese in cui ha sede l'organizzazione per quanto riguarda i report finanziari</span><span class="sxs-lookup"><span data-stu-id="4e158-117">The reporting requirements of the country/region where your organization is based</span></span>
-   <span data-ttu-id="4e158-118">Gli adempimenti richiesti dalla persona giuridica</span><span class="sxs-lookup"><span data-stu-id="4e158-118">The reporting requirements of your legal entity</span></span>
-   <span data-ttu-id="4e158-119">Il grado di specifica richiesto, sia per le organizzazioni esterne che per la propria</span><span class="sxs-lookup"><span data-stu-id="4e158-119">The degree of specification that is required, both for both external organizations and for your organization</span></span>

<span data-ttu-id="4e158-120">Creare i piani dei conti nella pagina **Piano dei conti**.</span><span class="sxs-lookup"><span data-stu-id="4e158-120">Create the chart of accounts on the **Chart of accounts** page.</span></span> <span data-ttu-id="4e158-121">I conti principali possono essere creati dalla pagina **Piano dei conti** o **Conti principali**.</span><span class="sxs-lookup"><span data-stu-id="4e158-121">Main accounts can be created from the **Chart of accounts** page or the **Main accounts** page.</span></span> <span data-ttu-id="4e158-122">Nei conti principali non è possibile utilizzare caratteri speciali come delimitatori del piano dei conti.</span><span class="sxs-lookup"><span data-stu-id="4e158-122">Your main accounts shouldn't use any special characters that are used as chart of accounts delimiters.</span></span> <span data-ttu-id="4e158-123">Se si dispone di un carattere speciale uguale al delimitatore del piano dei conti, è possibile che il sistema diventi instabile o che sia necessario utilizzare sempre le ricerche o il riquadro a comparsa quando si immettono combinazioni di conto e dimensione.</span><span class="sxs-lookup"><span data-stu-id="4e158-123">If you do have a special character that is the same as your chart of accounts delimiter, you may experience instability, or the need to always use lookups or the flyout when entering account and dimension combinations.</span></span> <span data-ttu-id="4e158-124">Per ulteriori informazioni, vedere [Creare un conto principale](tasks/create-account-structures.md).</span><span class="sxs-lookup"><span data-stu-id="4e158-124">For more information, see [Create a main account](tasks/create-account-structures.md).</span></span>


<span data-ttu-id="4e158-125">È consigliabile collegare i conti principali alle categorie dei conti principali, in modo da poter sfruttare i report finanziari predefiniti senza dover apportare eventuali modifiche.</span><span class="sxs-lookup"><span data-stu-id="4e158-125">It's a good idea to link the main accounts to main account categories, so that you can take advantage of the default financial reports without having to make any modifications.</span></span> <span data-ttu-id="4e158-126">Di conseguenza, è possibile progettare e gestire i report in modo più rapido e facile.</span><span class="sxs-lookup"><span data-stu-id="4e158-126">Therefore, you can more quickly and easily design and maintain reports.</span></span> 

<span data-ttu-id="4e158-127">Utilizzare la pagina **Configura strutture dei conti** per creare strutture dei conti.</span><span class="sxs-lookup"><span data-stu-id="4e158-127">Use the **Configure account structures** page to create account structures.</span></span> <span data-ttu-id="4e158-128">Le strutture dei conti consentono di definire combinazioni valide.</span><span class="sxs-lookup"><span data-stu-id="4e158-128">Account structures define valid combinations.</span></span> <span data-ttu-id="4e158-129">Le combinazioni, insieme ai conti principali, formano un piano dei conti.</span><span class="sxs-lookup"><span data-stu-id="4e158-129">The combinations, together with main accounts, form a chart of accounts.</span></span>  <span data-ttu-id="4e158-130">Per ulteriori informazioni, vedere [Creare strutture dei conti](tasks/create-main-account.md).</span><span class="sxs-lookup"><span data-stu-id="4e158-130">For more information, see [Create account structures](tasks/create-main-account.md).</span></span>

<span data-ttu-id="4e158-131">**Sostituzioni persona giuridica**</span><span class="sxs-lookup"><span data-stu-id="4e158-131">**Legal entity overrides**</span></span> 

<span data-ttu-id="4e158-132">Non tutti i conti principali sono validi per tutte le persone giuridiche e alcuni potrebbero essere pertinenti solo per un periodo di tempo specifico.</span><span class="sxs-lookup"><span data-stu-id="4e158-132">Not all main accounts are valid for all legal entities and some may only be relevant for a specific time period.</span></span> <span data-ttu-id="4e158-133">In questo scenario la sezione Sostituzioni persona giuridica può essere utilizzata per identificare quali sono le società per cui è necessario sospendere il conto principale, l'identità del proprietario e il periodo di tempo durante il quale la dimensione è attiva.</span><span class="sxs-lookup"><span data-stu-id="4e158-133">In this scenario the Legal entity overrides section can be used to identify which companies the main account should be suspended for, who the owner is and the time period the dimension is active.</span></span> <span data-ttu-id="4e158-134">Le sostituzioni a livello condiviso non possono essere più restrittive di quelle a livello della persona giuridica.</span><span class="sxs-lookup"><span data-stu-id="4e158-134">The overrides at the shared level cannot be more restrictive than the overrides at the legal entity level.</span></span>

<span data-ttu-id="4e158-135">Per ulteriori informazioni, vedere i seguenti argomenti: [Dimensioni finanziarie](financial-dimensions.md)
[Creare e assegnare strutture di regole avanzate](tasks/create-assign-advanced-rule-structures.md)</span><span class="sxs-lookup"><span data-stu-id="4e158-135">For more information, see the following topics: [Financial dimensions](financial-dimensions.md)
[Create and assign advanced rule structures](tasks/create-assign-advanced-rule-structures.md)</span></span>




