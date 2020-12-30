---
title: Definizioni di registrazione
description: Questo articolo fornisce informazioni sulle definizioni di registrazione e sul modo in cui definirle e collegarle. Per i tipi di registrazione e i documenti supportati è possibile utilizzare definizioni di registrazione anziché profili di registrazione per classificare i conti principali e le dimensioni finanziarie nelle voci contabili.
author: ShylaThompson
manager: AnnBe
ms.date: 09/03/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: JournalizingDefinition, JournalizingDefinitionTrans, LedgerParameters
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 15741
ms.assetid: 1495e7e0-2e39-464c-8da9-f55b1ca1c6bb
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 22a7b0acae02738e4f14905edb13fac1da0d0213
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4444807"
---
# <a name="posting-definitions"></a><span data-ttu-id="d42f0-104">Definizioni di registrazione</span><span class="sxs-lookup"><span data-stu-id="d42f0-104">Posting definitions</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d42f0-105">Questo articolo fornisce informazioni sulle definizioni di registrazione e sul modo in cui definirle e collegarle.</span><span class="sxs-lookup"><span data-stu-id="d42f0-105">This article provides information about posting definitions, and how to define and link them.</span></span>
<span data-ttu-id="d42f0-106">Per i tipi di registrazione e i documenti supportati è possibile utilizzare definizioni di registrazione anziché profili di registrazione per classificare i conti principali e le dimensioni finanziarie nelle voci contabili.</span><span class="sxs-lookup"><span data-stu-id="d42f0-106">For supported posting types and documents, you can use posting definitions instead of posting profiles to classify main accounts and financial dimensions on accounting entries.</span></span> <span data-ttu-id="d42f0-107">È possibile visualizzare i documenti e i tipi di registrazione supportati nella pagina **Definizioni di registrazione transazioni**.</span><span class="sxs-lookup"><span data-stu-id="d42f0-107">You can view the supported documents and posting types on the **Transaction posting definitions** page.</span></span> 

<span data-ttu-id="d42f0-108">Per iniziare a utilizzare le definizioni di registrazione, selezionare l'opzione **Usa definizioni di registrazione** nella pagina **Parametri di contabilità generale**.</span><span class="sxs-lookup"><span data-stu-id="d42f0-108">To start using posting definitions, select the **Use posting definitions** option on the **General ledger parameters** page.</span></span> <span data-ttu-id="d42f0-109">Anche quando si utilizzano le definizioni di registrazione, è ancora necessario definire i profili di registrazione per le voci di origine e i documenti e i tipi di registrazione non supportati.</span><span class="sxs-lookup"><span data-stu-id="d42f0-109">Even when you use posting definitions, you must still define posting profiles for the originating entries and non-supported posting types and documents.</span></span> 

<span data-ttu-id="d42f0-110">Le definizioni di registrazione devono essere utilizzate per consentire la contabilità degli impegni di spesa per gli ordini fornitore e la contabilità degli impegni preliminari di spesa per le richieste di acquisto.</span><span class="sxs-lookup"><span data-stu-id="d42f0-110">You must use posting definitions in order to enable encumbrance accounting for purchase orders and pre-encumbrance accounting for purchase requisitions.</span></span>

## <a name="defining-posting-definitions"></a><span data-ttu-id="d42f0-111">Definizioni di registrazione</span><span class="sxs-lookup"><span data-stu-id="d42f0-111">Defining posting definitions</span></span>
<span data-ttu-id="d42f0-112">Utilizzare la pagina **Definizioni di registrazione** per specificare i criteri di corrispondenza e definire le voci che devono essere generate quando una corrispondenza si verifica.</span><span class="sxs-lookup"><span data-stu-id="d42f0-112">Use the **Posting definitions** page to specify the match criteria and define the entries that should be generated when a match occurs.</span></span> <span data-ttu-id="d42f0-113">I criteri di corrispondenza vengono valutati per le voci di origine come distribuzioni contabili.</span><span class="sxs-lookup"><span data-stu-id="d42f0-113">The match criteria are evaluated for the originating entries as accounting distributions.</span></span> 

<span data-ttu-id="d42f0-114">Nella pagina **Definizioni di registrazione** è possibile anche assegnare numeri di priorità alle righe di immissione per definire l'ordine in cui vengono valutate le righe.</span><span class="sxs-lookup"><span data-stu-id="d42f0-114">On the **Posting definitions** page, you can also assign priority numbers to entry lines to control the order in which the lines are evaluated.</span></span> <span data-ttu-id="d42f0-115">Le righe con il numero di priorità inferiore vengono valutate per prime.</span><span class="sxs-lookup"><span data-stu-id="d42f0-115">The lines that have the lowest priority number are evaluated first.</span></span> <span data-ttu-id="d42f0-116">Ad esempio, vengono valutate tutte le righe con priorità 1, quindi le righe con priorità 2 e così via.</span><span class="sxs-lookup"><span data-stu-id="d42f0-116">For example, all lines that have a priority of 1 are evaluated, and then lines that have a priority of 2, and so on.</span></span> <span data-ttu-id="d42f0-117">Quando viene rilevata una corrispondenza, gli altri criteri di corrispondenza vengono ignorati.</span><span class="sxs-lookup"><span data-stu-id="d42f0-117">When a match is found, the other match criteria are ignored.</span></span> <span data-ttu-id="d42f0-118">Inoltre, solo per i criteri del gruppo corrispondenti alla transazione di origine vengono create voci generate.</span><span class="sxs-lookup"><span data-stu-id="d42f0-118">Additionally, only the criteria in the group that match the originating transaction create generated entries.</span></span> 

<span data-ttu-id="d42f0-119">È possibile convalidare le definizioni di registrazione utilizzando **Test guidato definizione di registrazione**.</span><span class="sxs-lookup"><span data-stu-id="d42f0-119">You can validate your posting definitions by using the **Test posting definition** wizard.</span></span> <span data-ttu-id="d42f0-120">Dopo aver definito una voce di origine di esempio per una definizione di registrazione, saranno visibili le voci generate.</span><span class="sxs-lookup"><span data-stu-id="d42f0-120">After you define a sample originating entry for a posting definition, you'll see the generated entries.</span></span> 

<span data-ttu-id="d42f0-121">È possibile utilizzare le versioni delle definizioni di registrazione insieme alle date di validità.</span><span class="sxs-lookup"><span data-stu-id="d42f0-121">You can use posting definition versions together with effective dates.</span></span> <span data-ttu-id="d42f0-122">È possibile creare, ad esempio, una versione futura di una definizione di registrazione per la registrazione in un conto CoGe diverso in un nuovo anno fiscale.</span><span class="sxs-lookup"><span data-stu-id="d42f0-122">For example, you can create a future version of a posting definition to post to a different ledger account in a new fiscal year.</span></span> 

<span data-ttu-id="d42f0-123">Utilizzare la pagina **Definizioni di registrazione transazioni** per assegnare le definizioni di registrazione ai tipi di transazioni.</span><span class="sxs-lookup"><span data-stu-id="d42f0-123">Use the **Transaction posting definitions** page to assign posting definitions to transaction types.</span></span>

## <a name="linking-posting-definitions"></a><span data-ttu-id="d42f0-124">Collegamento delle definizioni di registrazione</span><span class="sxs-lookup"><span data-stu-id="d42f0-124">Linking posting definitions</span></span>
<span data-ttu-id="d42f0-125">Quando si creano le definizioni di registrazione, è possibile collegarne una all'altra.</span><span class="sxs-lookup"><span data-stu-id="d42f0-125">You can link from one posting definition to another when you create posting definitions.</span></span> <span data-ttu-id="d42f0-126">I criteri per la definizione alla quale è stato effettuato il collegamento sono quindi considerati in aggiunta a quelli per la definizione di registrazione corrente.</span><span class="sxs-lookup"><span data-stu-id="d42f0-126">The criteria for the definition that you linked to are then considered in addition to the criteria for the current posting definition.</span></span> <span data-ttu-id="d42f0-127">Questa funzionalità consente di risparmiare tempo, perché non è necessario immettere di nuovo i criteri nella scheda dettaglio **Voci** della pagina **Definizioni di registrazione** per la definizione di registrazione corrente, se tali righe sono già state immesse per un'altra definizione.</span><span class="sxs-lookup"><span data-stu-id="d42f0-127">This feature helps save you time, because you don't have to reenter criteria on the **Entries** FastTab on the **Posting definitions** page for the current posting definition if you already entered those lines for another definition.</span></span> 

<span data-ttu-id="d42f0-128">Includere nei diagrammi o nelle tabelle tutti i collegamenti che potrebbero essere utilizzati.</span><span class="sxs-lookup"><span data-stu-id="d42f0-128">In the diagrams or tables, include any links that you might use.</span></span> <span data-ttu-id="d42f0-129">Per evitare conflitti con la definizione di registrazione corrente, verificare che le righe in tutte le definizioni di registrazione alle quali si sta effettuando il collegamento siano univoche.</span><span class="sxs-lookup"><span data-stu-id="d42f0-129">To avoid conflicts with the current posting definition, make sure that the lines in any posting definitions that you link to are unique.</span></span> 

<span data-ttu-id="d42f0-130">Quando si creano collegamenti nelle definizioni di registrazione vengono applicate le restrizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="d42f0-130">The following restrictions apply when you create links in posting definitions:</span></span>

-   <span data-ttu-id="d42f0-131">È possibile stabilire un collegamento da o verso una determinata definizione di registrazione da un'altra definizione di registrazione, ma non in entrambe le direzioni.</span><span class="sxs-lookup"><span data-stu-id="d42f0-131">A given posting definition can either link to another posting definition or be linked to from another posting definition, but not both.</span></span> <span data-ttu-id="d42f0-132">Tuttavia, una definizione di registrazione può collegare a più definizioni di registrazione.</span><span class="sxs-lookup"><span data-stu-id="d42f0-132">However, a posting definition can link to multiple posting definitions.</span></span>
-   <span data-ttu-id="d42f0-133">È possibile impostare i collegamenti solo tra definizioni di registrazione incluse nello stesso modulo.</span><span class="sxs-lookup"><span data-stu-id="d42f0-133">You can set up links only among posting definitions that are in the same module.</span></span>
-   <span data-ttu-id="d42f0-134">È possibile assegnare una definizione di registrazione a qualsiasi tipo di transazione, tuttavia tale tipo di transazione deve trovarsi nello stesso modulo della definizione di registrazione.</span><span class="sxs-lookup"><span data-stu-id="d42f0-134">You can assign a posting definition to any transaction type, but the transaction type must be in the same module as the posting definition.</span></span> <span data-ttu-id="d42f0-135">Utilizzare la pagina **Definizioni di registrazione transazioni** per visualizzare in quale modulo si trova un tipo di transazione.</span><span class="sxs-lookup"><span data-stu-id="d42f0-135">Use the **Transaction posting definitions** page to see what module a transaction type is in.</span></span>


<span data-ttu-id="d42f0-136">Per ulteriori informazioni, vedere [Esempi di definizione di registrazione](example-posting-definitions.md).</span><span class="sxs-lookup"><span data-stu-id="d42f0-136">For more information, see [Posting definition examples](example-posting-definitions.md).</span></span> 


