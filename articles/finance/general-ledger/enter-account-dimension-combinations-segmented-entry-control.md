---
title: Immettere le combinazioni di conto e dimensione (controllo di voci segmentato)
description: Questo articolo descrive come immettere le combinazioni di conto e dimensioni o conti CoGe. All'esperienza di inserimento si fa spesso riferimento come controllo di voci segmentato.
author: aprilolson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DimensionConfigureAccountStructure
audience: Application User
ms.reviewer: roschlom
ms.custom: 14071
ms.assetid: e6fce826-c403-4d91-a78b-e9a58c44ac03
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e1e35f5fb4400f849e9a139e1a96b18e8b9df384
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4968781"
---
# <a name="enter-account-and-dimension-combinations-segmented-entry-control"></a><span data-ttu-id="60eac-104">Immettere le combinazioni di conto e dimensione (controllo di voci segmentato)</span><span class="sxs-lookup"><span data-stu-id="60eac-104">Enter account and dimension combinations (segmented entry control)</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="60eac-105">Questo articolo descrive come immettere le combinazioni di conto e dimensioni o conti CoGe.</span><span class="sxs-lookup"><span data-stu-id="60eac-105">This article describes how to enter account and dimension combinations or ledger accounts.</span></span> <span data-ttu-id="60eac-106">All'esperienza di inserimento si fa spesso riferimento come controllo di voci segmentato.</span><span class="sxs-lookup"><span data-stu-id="60eac-106">The entry experience is often referred to as segmented entry control.</span></span>

<span data-ttu-id="60eac-107">Gli utenti immettono le combinazioni di conto e dimensione su diverse pagine, ad esempio pagine per i giornali di registrazione generali, impostazione del budget e definizioni di registrazione.</span><span class="sxs-lookup"><span data-stu-id="60eac-107">Users enter account and dimension combinations on various pages, such as pages for general journals, budgeting, and posting definitions.</span></span> <span data-ttu-id="60eac-108">Le combinazioni di conto e dimensione valide dipendono dalle strutture dei conti assegnate alla contabilità generale e alle regole avanzate assegnate alle strutture dei conti.</span><span class="sxs-lookup"><span data-stu-id="60eac-108">The valid account and dimension combinations depend on the account structures that are assigned to the ledger and the advanced rules that are assigned to the account structures.</span></span> <span data-ttu-id="60eac-109">Quando gli utenti immettono una combinazione, possono digitare il valori manualmente o sfruttare un'esperienza di ricerca complessa.</span><span class="sxs-lookup"><span data-stu-id="60eac-109">When users enter a combination, they can either manually type the values or take advantage of a rich, lookup experience.</span></span> <span data-ttu-id="60eac-110">Quando si immette il campo, è possibile iniziare a digitare e verranno cercati il valore e la descrizione.</span><span class="sxs-lookup"><span data-stu-id="60eac-110">When you enter the field, you can start to type and it will search the value and the description.</span></span> <span data-ttu-id="60eac-111">Ad esempio, se si digita 180 verrà cercato qualsiasi valore che inizia con quella combinazione di numeri.</span><span class="sxs-lookup"><span data-stu-id="60eac-111">For example, if you type 180 it will search any value that begins with that number combination.</span></span> <span data-ttu-id="60eac-112">Oppure è possibile digitare Contanti e verrà cercato qualsiasi valore con una descrizione che inizia con Contanti.</span><span class="sxs-lookup"><span data-stu-id="60eac-112">Or you may type Cash and it will search any value that has a description that begins with Cash.</span></span> <span data-ttu-id="60eac-113">È inoltre possibile utilizzare un jolly, ad esempio  \*Contanti o \*180  per cercare se il valore o la descrizione contiene i criteri di ricerca.</span><span class="sxs-lookup"><span data-stu-id="60eac-113">You can also use a wildcard, such as \*Cash or \*180 to search if the value or description contain the search criteria.</span></span> 

<span data-ttu-id="60eac-114">Nella seguente tabella sono descritti i tasti di scelta rapida che possono essere utilizzati quando la ricerca viene chiusa.</span><span class="sxs-lookup"><span data-stu-id="60eac-114">The following table describes the keyboard shortcuts that can be used when the lookup is closed.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="60eac-115">Tasto di scelta rapida</span><span class="sxs-lookup"><span data-stu-id="60eac-115">Keyboard shortcut</span></span></th>
<th><span data-ttu-id="60eac-116">Azione</span><span class="sxs-lookup"><span data-stu-id="60eac-116">Action</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="60eac-117">Freccia ALT + Giù</span><span class="sxs-lookup"><span data-stu-id="60eac-117">Alt+Down Arrow</span></span></td>
<td><span data-ttu-id="60eac-118">Aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="60eac-118">Open the lookup.</span></span> <span data-ttu-id="60eac-119">Se si preme la freccia ALT + Giù una seconda volta, lo stato attivo passa ai segmenti nel riquadro a comparsa.</span><span class="sxs-lookup"><span data-stu-id="60eac-119">If you press Alt+Down Arrow a second time, the focus moves to the segments in the flyout.</span></span></td>
</tr>
<tr class="even">
<td><ul>
<li><span data-ttu-id="60eac-120">Invio e MAIUSC + Invio</span><span class="sxs-lookup"><span data-stu-id="60eac-120">Enter and Shift+Enter</span></span></li>
<li><span data-ttu-id="60eac-121">Delimitatore piano dei conti</span><span class="sxs-lookup"><span data-stu-id="60eac-121">Chart of accounts delimiter</span></span></li>
<li><span data-ttu-id="60eac-122">Freccia destra e freccia sinistra</span><span class="sxs-lookup"><span data-stu-id="60eac-122">Right Arrow and Left Arrow</span></span></li>
</ul></td>
<td><span data-ttu-id="60eac-123">Passare al segmento successivo o precedente.</span><span class="sxs-lookup"><span data-stu-id="60eac-123">Move to the next or previous segment.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="60eac-124">TAB</span><span class="sxs-lookup"><span data-stu-id="60eac-124">Tab</span></span></td>
<td><span data-ttu-id="60eac-125">Passare al campo successivo nella griglia.</span><span class="sxs-lookup"><span data-stu-id="60eac-125">Move to the next field in the grid.</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="60eac-126">Nella seguente tabella sono descritti i tasti di scelta rapida che possono essere utilizzati quando la ricerca viene aperta.</span><span class="sxs-lookup"><span data-stu-id="60eac-126">The following table describes the keyboard shortcuts that can be used when the lookup is open.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="60eac-127">Tasto di scelta rapida</span><span class="sxs-lookup"><span data-stu-id="60eac-127">Keyboard shortcut</span></span></th>
<th><span data-ttu-id="60eac-128">Azione</span><span class="sxs-lookup"><span data-stu-id="60eac-128">Action</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="60eac-129">ESC</span><span class="sxs-lookup"><span data-stu-id="60eac-129">Esc</span></span></td>
<td><span data-ttu-id="60eac-130">Chiudere la ricerca.</span><span class="sxs-lookup"><span data-stu-id="60eac-130">Close the lookup.</span></span></td>
</tr>
<tr class="even">
<td><ul>
<li><span data-ttu-id="60eac-131">Freccia Su e freccia Giù</span><span class="sxs-lookup"><span data-stu-id="60eac-131">Up Arrow and Down Arrow</span></span></li>
<li><span data-ttu-id="60eac-132">Pagina Su e pagina Giù</span><span class="sxs-lookup"><span data-stu-id="60eac-132">Page Up and Page Down</span></span></li>
<li><span data-ttu-id="60eac-133">Home e Fine</span><span class="sxs-lookup"><span data-stu-id="60eac-133">Home and End</span></span></li>
</ul></td>
<td><span data-ttu-id="60eac-134">Passare al valore precedente o successivo negli elenchi, al gruppo di valori precedente o successivo o al primo o all'ultimo elemento nella ricerca.</span><span class="sxs-lookup"><span data-stu-id="60eac-134">Move to the previous or next value in the lists, to the previous or next group of values, or to the first or last element in the lookup.</span></span></td>
</tr>
<tr class="odd">
<td><ul>
<li><span data-ttu-id="60eac-135">Delimitatore piano dei conti</span><span class="sxs-lookup"><span data-stu-id="60eac-135">Chart of accounts delimiter</span></span></li>
<li><span data-ttu-id="60eac-136">Freccia destra e freccia sinistra</span><span class="sxs-lookup"><span data-stu-id="60eac-136">Right Arrow and Left Arrow</span></span></li>
</ul></td>
<td><span data-ttu-id="60eac-137">Passare al segmento successivo o precedente.</span><span class="sxs-lookup"><span data-stu-id="60eac-137">Move to the next or previous segment.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="60eac-138">Scheda</span><span class="sxs-lookup"><span data-stu-id="60eac-138">Tab</span></span></td>
<td><span data-ttu-id="60eac-139">Passare al campo successivo nella griglia.</span><span class="sxs-lookup"><span data-stu-id="60eac-139">Move to the next field in the grid.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="60eac-140">ALT + W</span><span class="sxs-lookup"><span data-stu-id="60eac-140">Alt+W</span></span></td>
<td><span data-ttu-id="60eac-141">Passare tra <strong>Mostra tutti</strong> e <strong>Visualizza validi</strong>.</span><span class="sxs-lookup"><span data-stu-id="60eac-141">Switch between <strong>Show all</strong> and <strong>Show valid</strong>.</span></span></td>
</tr>
</tbody>
</table>





