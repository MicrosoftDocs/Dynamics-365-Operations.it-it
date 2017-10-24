---
title: Conti di contropartita predefiniti per i giornali di registrazione fatture fornitore e giornali di registrazione di approvazione fatture
description: 
author: ShivamPandey-msft
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 62093
ms.assetid: 553933ca-928d-4031-bb8c-f9cff458320b
ms.search.region: global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: c2b62eafc71b5d1ad4eaaf252efd1dcbb97b86f3
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---

# <a name="default-offset-accounts-for-vendor-invoice-journals-and-invoice-approval-journals"></a><span data-ttu-id="f0cdc-102">Conti di contropartita predefiniti per i giornali di registrazione fatture fornitore e giornali di registrazione di approvazione fatture</span><span class="sxs-lookup"><span data-stu-id="f0cdc-102">Default offset accounts for vendor invoice journals and invoice approval journals</span></span>

[!include[banner](../includes/banner.md)]




<span data-ttu-id="f0cdc-103">I conti di contropartita predefiniti vengono utilizzati nelle pagine seguenti del giornale di registrazione fatture fornitore:</span><span class="sxs-lookup"><span data-stu-id="f0cdc-103">Default offset accounts are used on the following vendor invoice journal pages:</span></span>

-   <span data-ttu-id="f0cdc-104">Giornale di registrazione fatture</span><span class="sxs-lookup"><span data-stu-id="f0cdc-104">Invoice journal</span></span>
-   <span data-ttu-id="f0cdc-105">Giornale di approvazione fatture</span><span class="sxs-lookup"><span data-stu-id="f0cdc-105">Invoice approval journal</span></span>

<span data-ttu-id="f0cdc-106">Utilizzare la seguente tabella per consentire di decidere se assegnare i conti predefiniti per i giornali di registrazione fatture.</span><span class="sxs-lookup"><span data-stu-id="f0cdc-106">Use the following table to help decide where you should assign default accounts for invoice journals.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f0cdc-107">Impostare i conti di contropartita predefiniti qui</span><span class="sxs-lookup"><span data-stu-id="f0cdc-107">Set up default accounts here</span></span></th>
<th><span data-ttu-id="f0cdc-108">Punto in cui i conti predefiniti sono forniti</span><span class="sxs-lookup"><span data-stu-id="f0cdc-108">Where default accounts are provided</span></span></th>
<th><span data-ttu-id="f0cdc-109">Influenza sull'elaborazione</span><span class="sxs-lookup"><span data-stu-id="f0cdc-109">How this option affects processing</span></span></th>
<th><span data-ttu-id="f0cdc-110">Momento in cui è necessario utilizzare questa opzione</span><span class="sxs-lookup"><span data-stu-id="f0cdc-110">When you should use this option</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="f0cdc-111"><strong>Gruppo di fornitori</strong>: impostare i conti di contropartita predefiniti per i gruppi di fornitori nella pagina <strong>Impostazione conto predefinito</strong> che è possibile aprire nella pagina <strong>Gruppi di fornitori</strong>.</span><span class="sxs-lookup"><span data-stu-id="f0cdc-111"><strong>Vendor group</strong> – Set up default offset accounts for vendor groups on the <strong>Default account setup</strong> page, which you can open from the <strong>Vendor groups</strong> page.</span></span></td>
<td><ul>
<li><span data-ttu-id="f0cdc-112">Account fornitore</span><span class="sxs-lookup"><span data-stu-id="f0cdc-112">Vendor account</span></span></li>
<li><span data-ttu-id="f0cdc-113">Inserimenti nel giornale di registrazione per i conti fornitore nel gruppo di fornitori se i conti predefiniti non vengono specificati per i conti fornitore</span><span class="sxs-lookup"><span data-stu-id="f0cdc-113">Journal entries for vendor accounts in the vendor group, if default accounts aren’t specified for vendor accounts</span></span></li>
</ul></td>
<td><span data-ttu-id="f0cdc-114">I conti di contropartita predefiniti per i gruppi di fornitori vengono visualizzati come conti predefiniti per i fornitori nella pagina <strong>Impostazione conto predefinito</strong>.</span><span class="sxs-lookup"><span data-stu-id="f0cdc-114">The default offset accounts for vendor groups are shown as default offset accounts for vendors on the <strong>Default account setup</strong> page.</span></span> <span data-ttu-id="f0cdc-115">È possibile aprire questa pagina dalla pagina elenco <strong>Tutti i fornitori</strong>.</span><span class="sxs-lookup"><span data-stu-id="f0cdc-115">You can open this page from the <strong>All vendors</strong> list page.</span></span></td>
<td><span data-ttu-id="f0cdc-116">Utilizzare questa opzione se in genere si pagano gli stessi tipi di articoli dagli stessi gruppi di fornitori nel tempo.</span><span class="sxs-lookup"><span data-stu-id="f0cdc-116">Use this option if you typically pay for the same types of things from the same vendor groups over time.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="f0cdc-117"><strong>Conto fornitore</strong>: impostare i conti predefiniti per i conti fornitore nella pagina <strong>Impostazione conto predefinito</strong> che è possibile aprire nella pagina <strong>Fornitori</strong>.</span><span class="sxs-lookup"><span data-stu-id="f0cdc-117"><strong>Vendor account</strong> – Set up default accounts for vendor accounts on the <strong>Default account setup</strong> page, which you can open from the <strong>Vendors</strong> page.</span></span></td>
<td><span data-ttu-id="f0cdc-118">Inserimenti nel giornale di registrazione per il conto fornitore</span><span class="sxs-lookup"><span data-stu-id="f0cdc-118">Journal entries for the vendor account</span></span></td>
<td><span data-ttu-id="f0cdc-119">I conti di contropartita predefiniti per i conti fornitore vengono visualizzati come conti di contropartita predefiniti per gli inserimenti nel giornale di registrazione per il conto fornitore.</span><span class="sxs-lookup"><span data-stu-id="f0cdc-119">The default offset accounts for vendor accounts are shown as default offset accounts for journal entries for the vendor account.</span></span></td>
<td><span data-ttu-id="f0cdc-120">Utilizzare questa opzione se in genere si pagano gli stessi tipi di articoli dagli stessi fornitori nel tempo.</span><span class="sxs-lookup"><span data-stu-id="f0cdc-120">Use this option if you typically pay for the same types of things from the same vendors over time.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="f0cdc-121"><strong>Nomi giornale di registrazione</strong>: impostare i conti di contropartita predefiniti per i giornali di registrazione nella pagina <strong>Nomi giornale di registrazione</strong>.</span><span class="sxs-lookup"><span data-stu-id="f0cdc-121"><strong>Journal names</strong> – Set up default offset accounts for journals on the <strong>Journal names</strong> page.</span></span> <span data-ttu-id="f0cdc-122">Selezionare <strong>Conto di contropartita fisso</strong>.</span><span class="sxs-lookup"><span data-stu-id="f0cdc-122">Select the <strong>Fixed offset account</strong> option.</span></span> <span data-ttu-id="f0cdc-123">Si noti che non è possibile specificare i conti di contropartita predefiniti nei nomi del giornale di registrazione se il tipo di giornale di registrazione dei nomi è <strong>Registro fatture</strong> o <strong>Approvazione</strong>.</span><span class="sxs-lookup"><span data-stu-id="f0cdc-123">Note that you can't specify default offset accounts on journal names if the journal type of the journal names is <strong>Invoice register</strong> or <strong>Approval</strong>.</span></span></td>
<td><ul>
<li><span data-ttu-id="f0cdc-124">Intestazione giornale di registrazione che utilizza il nome del giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="f0cdc-124">Journal header that uses the journal name</span></span></li>
<li><span data-ttu-id="f0cdc-125">Inserimenti nei giornali di registrazione che utilizzano il nome del giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="f0cdc-125">Journal entries in journals that use the journal name</span></span></li>
</ul></td>
<td><span data-ttu-id="f0cdc-126">Se viene selezionata la casella di controllo <strong>Conto di contropartita fisso</strong> nella pagina <strong>Nomi giornale di registrazione</strong>, il conto di contropartita per il nome del giornale di registrazione sostituisce il conto di contropartita predefinito per il fornitore o per il gruppo di fornitori.</span><span class="sxs-lookup"><span data-stu-id="f0cdc-126">If the <strong>Fixed offset account</strong> option on the <strong>Journal names</strong> page is selected, the offset account for the journal name overrides the default offset account for the vendor or vendor group.</span></span></td>
<td><span data-ttu-id="f0cdc-127">Utilizzare questa opzione per impostare i giornali di registrazione per costi e spese specifici che vengono addebitati a conti specifici, indipendentemente dal fornitore o dal gruppo di fornitori di cui il fornitore fa parte.</span><span class="sxs-lookup"><span data-stu-id="f0cdc-127">Use this option to set up journals for specific costs and expenses that are charged to specific accounts, regardless of the vendor or the vendor group that the vendor belongs to.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="f0cdc-128"><strong>Nomi giornale di registrazione</strong>: impostare i conti di contropartita predefiniti per i giornali di registrazione nella pagina <strong>Nomi giornale di registrazione</strong>.</span><span class="sxs-lookup"><span data-stu-id="f0cdc-128"><strong>Journal names</strong> – Set up default offset accounts for journals on the <strong>Journal names</strong> page.</span></span> <span data-ttu-id="f0cdc-129">Deselezionare l'opzione <strong>Conto di contropartita fisso</strong>.</span><span class="sxs-lookup"><span data-stu-id="f0cdc-129">Clear the <strong>Fixed offset account</strong> option.</span></span> <span data-ttu-id="f0cdc-130">Si noti che non è possibile specificare i conti di contropartita predefiniti nei nomi del giornale di registrazione se il tipo di giornale di registrazione dei nomi è <strong>Registro fatture</strong> o <strong>Approvazione</strong>.</span><span class="sxs-lookup"><span data-stu-id="f0cdc-130">Note that you can't specify default offset accounts on journal names if the journal type of the journal names is <strong>Invoice register</strong> or <strong>Approval</strong>.</span></span></td>
<td><ul>
<li><span data-ttu-id="f0cdc-131">Intestazione giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="f0cdc-131">Journal header</span></span></li>
<li><span data-ttu-id="f0cdc-132">Inserimenti nei giornali di registrazione che utilizzano il nome del giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="f0cdc-132">Journal entries in journals that use the journal name</span></span></li>
</ul></td>
<td><span data-ttu-id="f0cdc-133">Questi valori predefiniti vengono utilizzati nelle pagine di intestazione del giornale di registrazione e il conto di contropartita nella pagina di intestazione del giornale di registrazione viene utilizzato come valore predefinito nelle pagine di giustificativo del giornale di registrazione.</span><span class="sxs-lookup"><span data-stu-id="f0cdc-133">These default entries are used on journal header pages, and the offset account on the journal header page is used as a default entry on the journal voucher pages.</span></span> <span data-ttu-id="f0cdc-134">I conti predefiniti della pagina <strong>Nomi giornale di registrazione</strong> vengono utilizzati solo se i conti predefiniti non sono impostati per il conto fornitore.</span><span class="sxs-lookup"><span data-stu-id="f0cdc-134">Default accounts from the <strong>Journal names </strong>page are used only if default accounts aren’t set up for the vendor account.</span></span></td>
<td><span data-ttu-id="f0cdc-135">Utilizzare questa opzione per impostare i conti predefiniti da utilizzare quando un conto di contropartita predefinito del fornitore non è assegnato.</span><span class="sxs-lookup"><span data-stu-id="f0cdc-135">Use this option to set up default accounts that are used when a default vendor offset account isn't assigned.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="f0cdc-136"><strong>Intestazione giornale di registrazione</strong>: impostare un conto di contropartita predefinito per un giornale di registrazione da utilizzare come valore predefinito nelle pagine di giustificativo giornale di registrazione.</span><span class="sxs-lookup"><span data-stu-id="f0cdc-136"><strong>Journal header</strong> – Set up a default offset account for a journal as a default entry on the journal voucher pages.</span></span> <span data-ttu-id="f0cdc-137">Si noti che non è possibile specificare i conti di contropartita predefiniti nell'intestazione del giornale di registrazione se il tipo di giornale di registrazione dei nomi è <strong>Registro fatture</strong> o <strong>Approvazione</strong>.</span><span class="sxs-lookup"><span data-stu-id="f0cdc-137">Note that you can't specify default offset accounts on the journal header if the journal type of the journal names is <strong>Invoice register</strong> or <strong>Approval</strong>.</span></span></td>
<td><span data-ttu-id="f0cdc-138">Inserimenti nel giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="f0cdc-138">Journal entries in the journal</span></span></td>
<td><span data-ttu-id="f0cdc-139">Il conto di contropartita predefinito per un giornale di registrazione viene utilizzato come valore predefinito nelle pagine del giustificativo giornale di registrazione.</span><span class="sxs-lookup"><span data-stu-id="f0cdc-139">The default offset account for a journal is used as the default entry on the journal voucher pages.</span></span></td>
<td><span data-ttu-id="f0cdc-140">Utilizzare questa opzione per velocizzare l'immissione di dati se la maggior parte delle voci in un giornale di registrazione hanno lo stesso conto di contropartita.</span><span class="sxs-lookup"><span data-stu-id="f0cdc-140">Use this option to help speed up data entry if most entries in a journal have the same offset account.</span></span></td>
</tr>
</tbody>
</table>






