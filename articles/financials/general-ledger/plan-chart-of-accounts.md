---
title: Definire il piano dei conti
description: Questo argomento fornisce le informazioni che consentono di pianificare il piano dei conti per l'organizzazione.
author: aprilolson
manager: AnnBe
ms.date: 04/02/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: DimensionConfigureAccountStructure, LedgerChartOfAccounts
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 14051
ms.assetid: 10edb129-33f0-4cf9-b2a7-4b7ffa09b229
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: 93d5ef19a4b1cb2885c611c8675ac06fd841ac56
ms.contentlocale: it-it
ms.lasthandoff: 08/07/2018

---

# <a name="plan-your-chart-of-accounts"></a><span data-ttu-id="edf15-103">Definire il piano dei conti</span><span class="sxs-lookup"><span data-stu-id="edf15-103">Plan your chart of accounts</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="edf15-104">Questo argomento fornisce le informazioni che consentono di pianificare il piano dei conti per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="edf15-104">This topic provides information that will help you plan the chart of accounts for your organization.</span></span>

<span data-ttu-id="edf15-105">Per tenere traccia e gestire le informazioni finanziarie in un'organizzazione, è possibile impostare un piano dei conti.</span><span class="sxs-lookup"><span data-stu-id="edf15-105">To track and maintain financial information in an organization, you can set up a chart of accounts.</span></span> <span data-ttu-id="edf15-106">Un piano dei conti è un insieme di conti che definiscono una struttura finanziaria.</span><span class="sxs-lookup"><span data-stu-id="edf15-106">A chart of accounts is a collection of accounts that define a financial framework.</span></span> <span data-ttu-id="edf15-107">Per tenere ulteriormente traccia delle transazioni in tali conti, è possibile aggiungere segmenti.</span><span class="sxs-lookup"><span data-stu-id="edf15-107">To further track the transactions in these accounts, you can add segments.</span></span> <span data-ttu-id="edf15-108">Questi segmenti sono noti con il nome di dimensioni finanziarie.</span><span class="sxs-lookup"><span data-stu-id="edf15-108">These segments are known as financial dimensions.</span></span> <span data-ttu-id="edf15-109">Ad esempio, un conto spese potrebbe includere dimensioni finanziarie denominate Reparto, Centro di costo e Scopo.</span><span class="sxs-lookup"><span data-stu-id="edf15-109">For example, an expense account might include financial dimensions that are named Department, Cost center, and Purpose.</span></span> <span data-ttu-id="edf15-110">Le regole definite dall'utente determinano le modalità di collegamento delle dimensioni finanziarie ai conti principali e ad altre dimensioni finanziarie, nonché quelle di immissione delle transazioni.</span><span class="sxs-lookup"><span data-stu-id="edf15-110">User-defined rules determine how financial dimensions are attached to the main accounts and to other financial dimensions, and also how transactions are entered.</span></span> <span data-ttu-id="edf15-111">Queste regole definite dall'utente sono note come strutture dei conti e regole avanzate.</span><span class="sxs-lookup"><span data-stu-id="edf15-111">These user-defined rules are known as account structures and advanced rules.</span></span>

<span data-ttu-id="edf15-112">Il piano dei conti consiste in un elenco strutturato dei conti CoGe di una persona giuridica.</span><span class="sxs-lookup"><span data-stu-id="edf15-112">The chart of accounts is a structured list of a legal entity's general ledger accounts.</span></span> <span data-ttu-id="edf15-113">Questo elenco viene utilizzato per preparare i report finanziari destinati agli uffici competenti e ai proprietari.</span><span class="sxs-lookup"><span data-stu-id="edf15-113">The list is used to prepare financial reports for authorities and owners.</span></span> <span data-ttu-id="edf15-114">I conti vengono innanzitutto raggruppati in tipi di conti, quindi ulteriormente aggregati in categorie più ampie.</span><span class="sxs-lookup"><span data-stu-id="edf15-114">The accounts are first grouped into types of accounts and then further aggregated into larger categories.</span></span> <span data-ttu-id="edf15-115">A livello generale, i conti vengono raggruppati in costi e ricavi (conti di gestione) e in attività e passività (conti collettivi).</span><span class="sxs-lookup"><span data-stu-id="edf15-115">At the most general level, the accounts are grouped as revenues and costs (operating accounts), and assets and liabilities (balance accounts).</span></span>

<span data-ttu-id="edf15-116">Un piano dei conti può essere condiviso e utilizzato da qualsiasi persona giuridica in un'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="edf15-116">A chart of accounts can be shared and used by any legal entity in an organization.</span></span> <span data-ttu-id="edf15-117">Il piano dei conti utilizzato da una persona giuridica è definito nella pagina **Contabilità generale**.</span><span class="sxs-lookup"><span data-stu-id="edf15-117">The chart of accounts that is used by a legal entity is defined on the **Ledger** page.</span></span>

<span data-ttu-id="edf15-118">Di seguito vengono indicati alcuni fattori da prendere in considerazione quando si pianifica la struttura del piano dei conti per l'organizzazione:</span><span class="sxs-lookup"><span data-stu-id="edf15-118">Here are some of the factors that you must consider when you plan the structure of the chart of accounts for your organization:</span></span>

- <span data-ttu-id="edf15-119">Gli adempimenti richiesti dal paese o dalla regione in cui ha sede l'organizzazione per quanto riguarda i report finanziari</span><span class="sxs-lookup"><span data-stu-id="edf15-119">The reporting requirements of the country or region where your organization is based</span></span>
- <span data-ttu-id="edf15-120">Gli adempimenti richiesti dalla persona giuridica</span><span class="sxs-lookup"><span data-stu-id="edf15-120">The reporting requirements of your legal entity</span></span>
- <span data-ttu-id="edf15-121">Il grado di specifica richiesto, sia per le organizzazioni esterne che per la propria</span><span class="sxs-lookup"><span data-stu-id="edf15-121">The degree of specification that is required, both for both external organizations and for your organization</span></span>

<span data-ttu-id="edf15-122">Si crea il piano dei conti nella pagina **Piano dei conti**.</span><span class="sxs-lookup"><span data-stu-id="edf15-122">You create the chart of accounts on the **Chart of accounts** page.</span></span> <span data-ttu-id="edf15-123">È possibile creare conti principali dalla pagina **Piano dei conti** o dalla pagina **Conti principali**.</span><span class="sxs-lookup"><span data-stu-id="edf15-123">You can create main accounts from the **Chart of accounts** page or the **Main accounts** page.</span></span> <span data-ttu-id="edf15-124">Nei conti principali non è consigliabile utilizzare caratteri speciali come delimitatori del piano dei conti.</span><span class="sxs-lookup"><span data-stu-id="edf15-124">Your main accounts shouldn't use any special characters that are used as delimiters for chart of accounts.</span></span> <span data-ttu-id="edf15-125">Si potrebbe sperimentare instabilità oppure potrebbe essere necessario utilizzare sempre le ricerche o la finestra di dialogo quando si immettono combinazioni di conti e dimensioni.</span><span class="sxs-lookup"><span data-stu-id="edf15-125">Otherwise, you might experience instability, or you might always have to use lookups or the dialog box when you enter combinations of accounts and dimensions.</span></span> <span data-ttu-id="edf15-126">Per ulteriori informazioni, vedere [Creare un conto principale](tasks/create-main-account.md).</span><span class="sxs-lookup"><span data-stu-id="edf15-126">For more information, see [Create a main account](tasks/create-main-account.md).</span></span>

> [!NOTE]
> <span data-ttu-id="edf15-127">In Microsoft Dynamics for Finance and Operations versione 8.0 (aprile 2018), è possibile modificare il delimitatore del piano dei conti nella pagina **Parametri di contabilità generale**.</span><span class="sxs-lookup"><span data-stu-id="edf15-127">In Microsoft Dynamics for Finance and Operations version 8.0 (April 2018), you can modify the chart of accounts delimiter from the **General ledger parameters** page.</span></span>

<span data-ttu-id="edf15-128">È consigliabile collegare i conti principali alle categorie dei conti principali, in modo da poter sfruttare i report finanziari predefiniti senza dover apportare eventuali modifiche.</span><span class="sxs-lookup"><span data-stu-id="edf15-128">It's a good idea to link the main accounts to main account categories, so that you can take advantage of the default financial reports without having to make any modifications.</span></span> <span data-ttu-id="edf15-129">Di conseguenza, è possibile progettare e gestire i report in modo più rapido e facile.</span><span class="sxs-lookup"><span data-stu-id="edf15-129">Therefore, you can more quickly and easily design and maintain reports.</span></span>

<span data-ttu-id="edf15-130">Si creano strutture dei conti nella pagina **Configura strutture dei conti**.</span><span class="sxs-lookup"><span data-stu-id="edf15-130">You create account structures on the **Configure account structures** page.</span></span> <span data-ttu-id="edf15-131">Le strutture dei conti consentono di definire combinazioni valide.</span><span class="sxs-lookup"><span data-stu-id="edf15-131">Account structures define valid combinations.</span></span> <span data-ttu-id="edf15-132">Queste combinazioni, insieme ai conti principali, formano un piano dei conti.</span><span class="sxs-lookup"><span data-stu-id="edf15-132">These combinations, together with main accounts, form a chart of accounts.</span></span> <span data-ttu-id="edf15-133">Per ulteriori informazioni, vedere [Creare strutture dei conti](tasks/create-account-structures.md).</span><span class="sxs-lookup"><span data-stu-id="edf15-133">For more information, see [Create account structures](tasks/create-account-structures.md).</span></span>

<span data-ttu-id="edf15-134">**Sostituzioni persona giuridica**</span><span class="sxs-lookup"><span data-stu-id="edf15-134">**Legal entity overrides**</span></span>

<span data-ttu-id="edf15-135">Non tutti i conti principali sono validi per tutte le persone giuridiche e alcuni conti principali potrebbero essere pertinenti solo per un periodo di tempo specifico.</span><span class="sxs-lookup"><span data-stu-id="edf15-135">Not all main accounts are valid for all legal entities, and some main account might be relevant only for a specific period.</span></span> <span data-ttu-id="edf15-136">In questo scenario, è possibile usare la sezione **Sostituzioni persona giuridica** per identificare quali sono le società per cui è necessario sospendere il conto principale, l'identità del proprietario e il periodo di tempo durante il quale la dimensione è attiva.</span><span class="sxs-lookup"><span data-stu-id="edf15-136">In this scenario, you can use the **Legal entity overrides** section to identify the companies that the main account should be suspended for, the owner, and the period when the dimension is active.</span></span> <span data-ttu-id="edf15-137">Le sostituzioni a livello condiviso non possono essere più restrittive di quelle a livello di persona giuridica.</span><span class="sxs-lookup"><span data-stu-id="edf15-137">The overrides at the shared level can't be more restrictive than the overrides at the legal entity level.</span></span>

<span data-ttu-id="edf15-138">Per ulteriori informazioni, vedere i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="edf15-138">For more information, see the following topics:</span></span>

- [<span data-ttu-id="edf15-139">Dimensioni finanziarie</span><span class="sxs-lookup"><span data-stu-id="edf15-139">Financial dimensions</span></span>](financial-dimensions.md)
- [<span data-ttu-id="edf15-140">Creare e assegnare strutture di regole avanzate</span><span class="sxs-lookup"><span data-stu-id="edf15-140">Create and assign advanced rule structures</span></span>](tasks/create-assign-advanced-rule-structures.md)

