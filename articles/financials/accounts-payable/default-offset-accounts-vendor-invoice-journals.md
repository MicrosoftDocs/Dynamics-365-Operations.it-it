---
title: Conti di contropartita predefiniti per i giornali di registrazione fatture fornitore e i giornali di registrazione approvazione fatture
description: Le informazioni contenute in questo argomento consentono di decidere se assegnare i conti predefiniti per i giornali di registrazione fatture.
author: abruer
manager: AnnBe
ms.date: 01/12/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTable
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 62093
ms.assetid: 553933ca-928d-4031-bb8c-f9cff458320b
ms.search.region: global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5cf772a0f0f9f99519322be1f37f961dc0ab2500
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2019
ms.locfileid: "1509108"
---
# <a name="default-offset-accounts-for-vendor-invoice-journals-and-invoice-approval-journals"></a><span data-ttu-id="35097-103">Conti di contropartita predefiniti per i giornali di registrazione fatture fornitore e i giornali di registrazione approvazione fatture</span><span class="sxs-lookup"><span data-stu-id="35097-103">Default offset accounts for vendor invoice journals and invoice approval journals</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="35097-104">I conti di contropartita predefiniti vengono utilizzati nelle pagine seguenti del giornale di registrazione fatture fornitore:</span><span class="sxs-lookup"><span data-stu-id="35097-104">Default offset accounts are used on the following vendor invoice journal pages:</span></span>

-   <span data-ttu-id="35097-105">Giornale di registrazione fatture</span><span class="sxs-lookup"><span data-stu-id="35097-105">Invoice journal</span></span>
-   <span data-ttu-id="35097-106">Giornale di approvazione fatture</span><span class="sxs-lookup"><span data-stu-id="35097-106">Invoice approval journal</span></span>

<span data-ttu-id="35097-107">Utilizzare la seguente tabella per consentire di decidere se assegnare i conti predefiniti per i giornali di registrazione fatture.</span><span class="sxs-lookup"><span data-stu-id="35097-107">Use the following table to help decide where you should assign default accounts for invoice journals.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="35097-108">Impostare i conti di contropartita predefiniti qui</span><span class="sxs-lookup"><span data-stu-id="35097-108">Set up default accounts here</span></span></th>
<th><span data-ttu-id="35097-109">Punto in cui i conti predefiniti sono forniti</span><span class="sxs-lookup"><span data-stu-id="35097-109">Where default accounts are provided</span></span></th>
<th><span data-ttu-id="35097-110">Influenza sull'elaborazione</span><span class="sxs-lookup"><span data-stu-id="35097-110">How this option affects processing</span></span></th>
<th><span data-ttu-id="35097-111">Momento in cui è necessario utilizzare questa opzione</span><span class="sxs-lookup"><span data-stu-id="35097-111">When you should use this option</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="35097-112"><strong>Gruppo di fornitori</strong>: impostare i conti di contropartita predefiniti per i gruppi di fornitori nella pagina <strong>Impostazione conto predefinito</strong> che è possibile aprire nella pagina <strong>Gruppi di fornitori</strong>.</span><span class="sxs-lookup"><span data-stu-id="35097-112"><strong>Vendor group</strong> – Set up default offset accounts for vendor groups on the <strong>Default account setup</strong> page, which you can open from the <strong>Vendor groups</strong> page.</span></span></td>
<td><ul>
<li><span data-ttu-id="35097-113">Account fornitore</span><span class="sxs-lookup"><span data-stu-id="35097-113">Vendor account</span></span></li>
<li><span data-ttu-id="35097-114">Inserimenti nel giornale di registrazione per i conti fornitore nel gruppo di fornitori se i conti predefiniti non vengono specificati per i conti fornitore</span><span class="sxs-lookup"><span data-stu-id="35097-114">Journal entries for vendor accounts in the vendor group, if default accounts aren’t specified for vendor accounts</span></span></li>
</ul></td>
<td><span data-ttu-id="35097-115">I conti di contropartita predefiniti per i gruppi di fornitori vengono visualizzati come conti predefiniti per i fornitori nella pagina <strong>Impostazione conto predefinito</strong>.</span><span class="sxs-lookup"><span data-stu-id="35097-115">The default offset accounts for vendor groups are shown as default offset accounts for vendors on the <strong>Default account setup</strong> page.</span></span> <span data-ttu-id="35097-116">È possibile aprire questa pagina dalla pagina elenco <strong>Tutti i fornitori</strong>.</span><span class="sxs-lookup"><span data-stu-id="35097-116">You can open this page from the <strong>All vendors</strong> list page.</span></span></td>
<td><span data-ttu-id="35097-117">Utilizzare questa opzione se in genere si pagano gli stessi tipi di articoli dagli stessi gruppi di fornitori nel tempo.</span><span class="sxs-lookup"><span data-stu-id="35097-117">Use this option if you typically pay for the same types of things from the same vendor groups over time.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="35097-118"><strong>Conto fornitore</strong>: impostare i conti predefiniti per i conti fornitore nella pagina <strong>Impostazione conto predefinito</strong> che è possibile aprire nella pagina <strong>Fornitori</strong>.</span><span class="sxs-lookup"><span data-stu-id="35097-118"><strong>Vendor account</strong> – Set up default accounts for vendor accounts on the <strong>Default account setup</strong> page, which you can open from the <strong>Vendors</strong> page.</span></span></td>
<td><span data-ttu-id="35097-119">Inserimenti nel giornale di registrazione per il conto fornitore</span><span class="sxs-lookup"><span data-stu-id="35097-119">Journal entries for the vendor account</span></span></td>
<td><span data-ttu-id="35097-120">I conti di contropartita predefiniti per i conti fornitore vengono visualizzati come conti di contropartita predefiniti per gli inserimenti nel giornale di registrazione per il conto fornitore.</span><span class="sxs-lookup"><span data-stu-id="35097-120">The default offset accounts for vendor accounts are shown as default offset accounts for journal entries for the vendor account.</span></span></td>
<td><span data-ttu-id="35097-121">Utilizzare questa opzione se in genere si pagano gli stessi tipi di articoli dagli stessi fornitori nel tempo.</span><span class="sxs-lookup"><span data-stu-id="35097-121">Use this option if you typically pay for the same types of things from the same vendors over time.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="35097-122"><strong>Nomi giornale di registrazione</strong>: impostare i conti di contropartita predefiniti per i giornali di registrazione nella pagina <strong>Nomi giornale di registrazione</strong>.</span><span class="sxs-lookup"><span data-stu-id="35097-122"><strong>Journal names</strong> – Set up default offset accounts for journals on the <strong>Journal names</strong> page.</span></span> <span data-ttu-id="35097-123">Selezionare <strong>Conto di contropartita fisso</strong>.</span><span class="sxs-lookup"><span data-stu-id="35097-123">Select the <strong>Fixed offset account</strong> option.</span></span> <span data-ttu-id="35097-124">Si noti che non è possibile specificare i conti di contropartita predefiniti nei nomi del giornale di registrazione se il tipo di giornale di registrazione dei nomi è <strong>Registro fatture</strong> o <strong>Approvazione</strong>.</span><span class="sxs-lookup"><span data-stu-id="35097-124">Note that you can&#39;t specify default offset accounts on journal names if the journal type of the journal names is <strong>Invoice register</strong> or <strong>Approval</strong>.</span></span></td>
<td><ul>
<li><span data-ttu-id="35097-125">Intestazione giornale di registrazione che utilizza il nome del giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="35097-125">Journal header that uses the journal name</span></span></li>
<li><span data-ttu-id="35097-126">Inserimenti nei giornali di registrazione che utilizzano il nome del giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="35097-126">Journal entries in journals that use the journal name</span></span></li>
</ul></td>
<td><span data-ttu-id="35097-127">Se viene selezionata la casella di controllo <strong>Conto di contropartita fisso</strong> nella pagina <strong>Nomi giornale di registrazione</strong>, il conto di contropartita per il nome del giornale di registrazione sostituisce il conto di contropartita predefinito per il fornitore o per il gruppo di fornitori.</span><span class="sxs-lookup"><span data-stu-id="35097-127">If the <strong>Fixed offset account</strong> option on the <strong>Journal names</strong> page is selected, the offset account for the journal name overrides the default offset account for the vendor or vendor group.</span></span></td>
<td><span data-ttu-id="35097-128">Utilizzare questa opzione per impostare i giornali di registrazione per costi e spese specifici che vengono addebitati a conti specifici, indipendentemente dal fornitore o dal gruppo di fornitori di cui il fornitore fa parte.</span><span class="sxs-lookup"><span data-stu-id="35097-128">Use this option to set up journals for specific costs and expenses that are charged to specific accounts, regardless of the vendor or the vendor group that the vendor belongs to.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="35097-129"><strong>Nomi giornale di registrazione</strong>: impostare i conti di contropartita predefiniti per i giornali di registrazione nella pagina <strong>Nomi giornale di registrazione</strong>.</span><span class="sxs-lookup"><span data-stu-id="35097-129"><strong>Journal names</strong> – Set up default offset accounts for journals on the <strong>Journal names</strong> page.</span></span> <span data-ttu-id="35097-130">Deselezionare l'opzione <strong>Conto di contropartita fisso</strong>.</span><span class="sxs-lookup"><span data-stu-id="35097-130">Clear the <strong>Fixed offset account</strong> option.</span></span> <span data-ttu-id="35097-131">Si noti che non è possibile specificare i conti di contropartita predefiniti nei nomi del giornale di registrazione se il tipo di giornale di registrazione dei nomi è <strong>Registro fatture</strong> o <strong>Approvazione</strong>.</span><span class="sxs-lookup"><span data-stu-id="35097-131">Note that you can&#39;t specify default offset accounts on journal names if the journal type of the journal names is <strong>Invoice register</strong> or <strong>Approval</strong>.</span></span></td>
<td><ul>
<li><span data-ttu-id="35097-132">Intestazione giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="35097-132">Journal header</span></span></li>
<li><span data-ttu-id="35097-133">Inserimenti nei giornali di registrazione che utilizzano il nome del giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="35097-133">Journal entries in journals that use the journal name</span></span></li>
</ul></td>
<td><span data-ttu-id="35097-134">Questi valori predefiniti vengono utilizzati nelle pagine di intestazione del giornale di registrazione e il conto di contropartita nella pagina di intestazione del giornale di registrazione viene utilizzato come valore predefinito nelle pagine di giustificativo del giornale di registrazione.</span><span class="sxs-lookup"><span data-stu-id="35097-134">These default entries are used on journal header pages, and the offset account on the journal header page is used as a default entry on the journal voucher pages.</span></span> <span data-ttu-id="35097-135">I conti predefiniti della pagina <strong>Nomi giornale di registrazione</strong> vengono utilizzati solo se i conti predefiniti non sono impostati per il conto fornitore.</span><span class="sxs-lookup"><span data-stu-id="35097-135">Default accounts from the <strong>Journal names </strong>page are used only if default accounts aren’t set up for the vendor account.</span></span></td>
<td><span data-ttu-id="35097-136">Utilizzare questa opzione per impostare i conti predefiniti da utilizzare quando un conto di contropartita predefinito del fornitore non è assegnato.</span><span class="sxs-lookup"><span data-stu-id="35097-136">Use this option to set up default accounts that are used when a default vendor offset account isn&#39;t assigned.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="35097-137"><strong>Intestazione giornale di registrazione</strong>: impostare un conto di contropartita predefinito per un giornale di registrazione da utilizzare come valore predefinito nelle pagine di giustificativo giornale di registrazione.</span><span class="sxs-lookup"><span data-stu-id="35097-137"><strong>Journal header</strong> – Set up a default offset account for a journal as a default entry on the journal voucher pages.</span></span> <span data-ttu-id="35097-138">Si noti che non è possibile specificare i conti di contropartita predefiniti nell'intestazione del giornale di registrazione se il tipo di giornale di registrazione dei nomi è <strong>Registro fatture</strong> o <strong>Approvazione</strong>.</span><span class="sxs-lookup"><span data-stu-id="35097-138">Note that you can&#39;t specify default offset accounts on the journal header if the journal type of the journal names is <strong>Invoice register</strong> or <strong>Approval</strong>.</span></span></td>
<td><span data-ttu-id="35097-139">Inserimenti nel giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="35097-139">Journal entries in the journal</span></span></td>
<td><span data-ttu-id="35097-140">Il conto di contropartita predefinito per un giornale di registrazione viene utilizzato come valore predefinito nelle pagine del giustificativo giornale di registrazione.</span><span class="sxs-lookup"><span data-stu-id="35097-140">The default offset account for a journal is used as the default entry on the journal voucher pages.</span></span></td>
<td><span data-ttu-id="35097-141">Utilizzare questa opzione per velocizzare l'immissione di dati se la maggior parte delle voci in un giornale di registrazione hanno lo stesso conto di contropartita.</span><span class="sxs-lookup"><span data-stu-id="35097-141">Use this option to help speed up data entry if most entries in a journal have the same offset account.</span></span></td>
</tr>
</tbody>
</table>





