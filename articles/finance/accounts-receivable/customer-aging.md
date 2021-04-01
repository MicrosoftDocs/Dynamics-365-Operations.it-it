---
title: Report Aging clienti
description: Nel report Aging clienti vengono visualizzati i saldi esigibili dai clienti ordinati per intervallo di date o per periodo di aging.
author: JodiChristiansen
manager: AnnBe
ms.date: 10/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 384e44ef07771a174aaed4f8fb893e75b0206da7
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5236988"
---
# <a name="customer-aging-report"></a><span data-ttu-id="115e3-103">Report di aging clienti</span><span class="sxs-lookup"><span data-stu-id="115e3-103">Customer aging report</span></span> 

<span data-ttu-id="115e3-104">Nel report **Aging clienti** vengono visualizzati i saldi esigibili dai clienti ordinati per intervallo di date o per periodo di aging.</span><span class="sxs-lookup"><span data-stu-id="115e3-104">The **Customer aging** report displays the balances that are due from customers, sorted by date interval, or aging period.</span></span>

<span data-ttu-id="115e3-105">Quando si genera questo report, vengono visualizzati i seguenti parametri predefiniti.</span><span class="sxs-lookup"><span data-stu-id="115e3-105">When you generate this report, the following default parameters are displayed.</span></span> <span data-ttu-id="115e3-106">È possibile utilizzare tali parametri per filtrare i dati che verranno visualizzati nel report.</span><span class="sxs-lookup"><span data-stu-id="115e3-106">You can use these parameters to filter the data that will be displayed on the report.</span></span> <span data-ttu-id="115e3-107">Per ulteriori informazioni, vedere [Impostare la riscossione](set-up-collections.md).</span><span class="sxs-lookup"><span data-stu-id="115e3-107">For more information, see [Set up collections](set-up-collections.md).</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="115e3-108">Campo</span><span class="sxs-lookup"><span data-stu-id="115e3-108">Field</span></span></p></th>
<th><p><span data-ttu-id="115e3-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="115e3-109">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="115e3-110"><strong>Classificazione della priorità di pagamento</strong></span><span class="sxs-lookup"><span data-stu-id="115e3-110"><strong>Billing classification</strong></span></span></p></td>
<td><p><span data-ttu-id="115e3-111">Selezionare una o più classificazioni della priorità di pagamento da includere nel report.</span><span class="sxs-lookup"><span data-stu-id="115e3-111">Select one or more billing classifications to include on the report.</span></span></p>
<div class="alert">

<span data-ttu-id="115e3-112">**Nota:** questo controllo è disponibile solo se è stata selezionata la chiave di configurazione <STRONG>Settore pubblico</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="115e3-112">**Note:** This control is available only if the <STRONG>Public Sector</STRONG> configuration key is selected.</span></span></P>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="115e3-113"><strong>Includi transazioni senza una classificazione della priorità di pagamento</strong></span><span class="sxs-lookup"><span data-stu-id="115e3-113"><strong>Include transactions without a billing classification</strong></span></span></p></td>
<td><p><span data-ttu-id="115e3-114">Se questa casella di controllo è selezionata, verranno incluse nel report tutte le transazioni alle quali non è assegnata una classificazione della priorità di pagamento.</span><span class="sxs-lookup"><span data-stu-id="115e3-114">If this check box is selected, all transactions that do not have a billing classification assigned to them will be displayed on the report.</span></span></p>
<div class="alert">

<span data-ttu-id="115e3-115">**Nota:** questo controllo è disponibile solo se è stata selezionata la chiave di configurazione <STRONG>Settore pubblico</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="115e3-115">**Note:** This control is available only if the <STRONG>Public sector</STRONG> configuration key is selected.</span></span></P>

</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="115e3-116"><strong>Aging a partire dal</strong></span><span class="sxs-lookup"><span data-stu-id="115e3-116"><strong>Aging as of</strong></span></span></p></td>
<td><p><span data-ttu-id="115e3-117">Immettere la data utilizzata nel bucket di aging corrente.</span><span class="sxs-lookup"><span data-stu-id="115e3-117">Enter the date used on the current aging bucket.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="115e3-118"><strong>Saldo a partire da</strong></span><span class="sxs-lookup"><span data-stu-id="115e3-118"><strong>Balance as of</strong></span></span></p></td>
<td><p><span data-ttu-id="115e3-119">Immettere la data per cui si desidera visualizzare i saldi dei clienti,</span><span class="sxs-lookup"><span data-stu-id="115e3-119">Enter the date to view the customer balances for.</span></span> <span data-ttu-id="115e3-120">nota anche come data limite per le transazioni.</span><span class="sxs-lookup"><span data-stu-id="115e3-120">This is also known as a cutoff date for transactions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="115e3-121"><strong>Data di inizio</strong></span><span class="sxs-lookup"><span data-stu-id="115e3-121"><strong>Start date</strong></span></span></p></td>
<td><p><span data-ttu-id="115e3-122">Immettere una data compresa nel primo intervallo periodico o periodo di aging da includere nel report.</span><span class="sxs-lookup"><span data-stu-id="115e3-122">Enter a date that is in the first period interval or aging period to include on the report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="115e3-123"><strong>Criteri</strong></span><span class="sxs-lookup"><span data-stu-id="115e3-123"><strong>Criteria</strong></span></span></p></td>
<td><p><span data-ttu-id="115e3-124">Selezionare il tipo di data su cui basare il report.</span><span class="sxs-lookup"><span data-stu-id="115e3-124">Select the type of date to base the report on.</span></span></p>
<ul>
<li><p><span data-ttu-id="115e3-125"><strong>Data della transazione</strong>: la data di registrazione della transazione selezionata.</span><span class="sxs-lookup"><span data-stu-id="115e3-125"><strong>Transaction date</strong> – The posting date of the transactions.</span></span> <span data-ttu-id="115e3-126">Ad esempio potrebbe essere la data di una fattura su cui è basato il calcolo della data di scadenza.</span><span class="sxs-lookup"><span data-stu-id="115e3-126">For example, this might be an invoice date that is the basis for the calculation of the due date.</span></span></p></li>
<li><p><span data-ttu-id="115e3-127"><strong>Data di scadenza</strong>: la data di scadenza delle transazioni basata sui termini di pagamento.</span><span class="sxs-lookup"><span data-stu-id="115e3-127"><strong>Due date</strong> – The due date of the transactions, based on the terms of payment.</span></span></p></li>
<li><p><span data-ttu-id="115e3-128"><strong>Data documento</strong>: la data del documento definita dall'utente su cui è basato il calcolo della data di scadenza.</span><span class="sxs-lookup"><span data-stu-id="115e3-128"><strong>Document date</strong> – A user-defined document date that is the basis for the calculation of the due date.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="115e3-129"><strong>Definizione periodo di aging</strong></span><span class="sxs-lookup"><span data-stu-id="115e3-129"><strong>Aging period definition</strong></span></span></p></td>
<td><p><span data-ttu-id="115e3-130">Consente di selezionare una definizione del periodo di aging.</span><span class="sxs-lookup"><span data-stu-id="115e3-130">Select an aging period definition.</span></span> <span data-ttu-id="115e3-131">Se si seleziona una definizione del periodo di aging, il campo <strong>Intervallo</strong> non viene utilizzato.</span><span class="sxs-lookup"><span data-stu-id="115e3-131">The <strong>Interval</strong> field is not used if you select an aging period definition.</span></span></p>
<p><span data-ttu-id="115e3-132">Per la stampa del report non è possibile utilizzare definizioni del periodo di aging con più di sei periodi di aging.</span><span class="sxs-lookup"><span data-stu-id="115e3-132">Aging period definitions that have more than six aging periods cannot be used on the printed report.</span></span></p>
<div class="alert">

<span data-ttu-id="115e3-133">**Nota:** è possibile impostare periodi di aging nella pagina <STRONG>Definizioni periodo di aging</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="115e3-133">**Note:** You can set up aging periods on the <STRONG>Aging period definitions</STRONG> page.</span></span></P>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="115e3-134"><strong>Stampa descrizione periodo di aging</strong></span><span class="sxs-lookup"><span data-stu-id="115e3-134"><strong>Print aging period description</strong></span></span></p></td>
<td><p><span data-ttu-id="115e3-135">Selezionare <strong>Sì</strong> per includere nel report le descrizioni dei periodi di aging nella parte superiore di ciascuna colonna del periodo di aging.</span><span class="sxs-lookup"><span data-stu-id="115e3-135">Select <strong>Yes</strong> to include aging period descriptions at the top of each aging period column on the report.</span></span> <span data-ttu-id="115e3-136">Selezionare <strong>No</strong> per stampare il report senza le intestazioni di colonna.</span><span class="sxs-lookup"><span data-stu-id="115e3-136">Select <strong>No</strong> to print the report without column headers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="115e3-137"><strong>Intervallo</strong></span><span class="sxs-lookup"><span data-stu-id="115e3-137"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="115e3-138">Definire il periodo da utilizzare immettendo il numero di unità, espresso in giorni o mesi, per ciascun periodo.</span><span class="sxs-lookup"><span data-stu-id="115e3-138">Define the period to use by entering the number of the day or month units in each period.</span></span> <span data-ttu-id="115e3-139">Ad esempio, per visualizzare le informazioni di aging per settimana, immettere 7 in questo campo e selezionare <strong>Giorno</strong> nel campo <strong>Giorni/Mese</strong>.</span><span class="sxs-lookup"><span data-stu-id="115e3-139">For example, to view aging information by week, enter 7 in this field and select <strong>Day</strong> in the <strong>Day/Mth</strong> field.</span></span></p>
<div class="alert">

<span data-ttu-id="115e3-140">**Nota:** le informazioni immesse in questo campo vengono utilizzate solo se non è stata selezionata una definizione del periodo di aging.</span><span class="sxs-lookup"><span data-stu-id="115e3-140">**Note:** The information that you enter in this field is used only if you have not selected an aging period definition.</span></span> <span data-ttu-id="115e3-141">In caso contrario, la direzione di stampa viene definita nella definizione del periodo di aging.</span><span class="sxs-lookup"><span data-stu-id="115e3-141">Otherwise, the printing direction is defined on the aging period definition.</span></span></P>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="115e3-142"><strong>Giorno/mese</strong></span><span class="sxs-lookup"><span data-stu-id="115e3-142"><strong>Day/Mth</strong></span></span></p></td>
<td><p><span data-ttu-id="115e3-143">Selezionare l'unità, <strong>Giorno</strong> o <strong>Mese</strong>, utilizzata per definire il periodo nel campo <strong>Intervallo</strong>.</span><span class="sxs-lookup"><span data-stu-id="115e3-143">Select the unit, either <strong>Day</strong> or <strong>Month</strong>, that is used to define the period in the <strong>Interval</strong> field.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="115e3-144"><strong>Direzione di stampa</strong></span><span class="sxs-lookup"><span data-stu-id="115e3-144"><strong>Printing direction</strong></span></span></p></td>
<td><p><span data-ttu-id="115e3-145">Specificare se calcolare i saldi e stampare il report di aging per periodi trascorsi o futuri.</span><span class="sxs-lookup"><span data-stu-id="115e3-145">Select whether to calculate balances and print the aging report for past or future periods.</span></span> <span data-ttu-id="115e3-146">Le date vengono valutate rispetto alla data selezionata nel campo <strong>Saldo a partire da</strong>.</span><span class="sxs-lookup"><span data-stu-id="115e3-146">The dates are evaluated relative to the date that is selected in the <strong>Balance as on</strong> field.</span></span> <span data-ttu-id="115e3-147">Per visualizzare le informazioni relative ai periodi trascorsi, selezionare <strong>Indietro</strong>.</span><span class="sxs-lookup"><span data-stu-id="115e3-147">Select <strong>Backward</strong> to show information for past periods.</span></span> <span data-ttu-id="115e3-148">Per visualizzare le informazioni relative ai periodi futuri, selezionare <strong>Avanti</strong>.</span><span class="sxs-lookup"><span data-stu-id="115e3-148">Select <strong>Forward</strong> to show information for future periods.</span></span></p>
<div class="alert"><span data-ttu-id="115e3-149">
  
<STRONG>Nota:</STRONG> le informazioni immesse in questo campo vengono utilizzate solo se non è stata selezionata una definizione del periodo di aging.</span><span class="sxs-lookup"><span data-stu-id="115e3-149">
  
<STRONG>Note:</STRONG> The information that you enter in this field is used only if you have not selected an aging period definition.</span></span></P>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="115e3-150"><strong>Dettagli</strong></span><span class="sxs-lookup"><span data-stu-id="115e3-150"><strong>Details</strong></span></span></p></td>
<td><p><span data-ttu-id="115e3-151">Selezionare questo campo per elencare le transazioni incluse nei saldi visualizzati nel report.</span><span class="sxs-lookup"><span data-stu-id="115e3-151">Select to list the transactions that are included in the balances that are shown on the report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="115e3-152"><strong>Includi importi in valuta della transazione</strong></span><span class="sxs-lookup"><span data-stu-id="115e3-152"><strong>Include amounts in transaction currency</strong></span></span></p></td>
<td><p><span data-ttu-id="115e3-153">Selezionare questo campo per includere gli importi nella valuta della transazione oltre agli importi nella valuta di contabilizzazione.</span><span class="sxs-lookup"><span data-stu-id="115e3-153">Select to include amounts in the transaction currency in addition to amounts in the accounting currency.</span></span> <span data-ttu-id="115e3-154">Se questa casella di controllo non è selezionata, gli importi nel report vengono visualizzati solo nella valuta di contabilizzazione.</span><span class="sxs-lookup"><span data-stu-id="115e3-154">If this check box is not selected, the amounts on the report are displayed only in the accounting currency.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="115e3-155"><strong>Saldo negativo</strong></span><span class="sxs-lookup"><span data-stu-id="115e3-155"><strong>Negative balance</strong></span></span></p></td>
<td><p><span data-ttu-id="115e3-156">Selezionare questo campo per includere i conti cliente con saldi negativi.</span><span class="sxs-lookup"><span data-stu-id="115e3-156">Select to include customer accounts that have negative balances.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="115e3-157"><strong>Escludi conti con saldo zero</strong></span><span class="sxs-lookup"><span data-stu-id="115e3-157"><strong>Exclude zero balance accounts</strong></span></span></p></td>
<td><p><span data-ttu-id="115e3-158">Selezionare questo campo per escludere i conti cliente con saldo zero.</span><span class="sxs-lookup"><span data-stu-id="115e3-158">Select to exclude customer accounts that have a zero balance.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="115e3-159"><strong>Posizionamento pagamento</strong></span><span class="sxs-lookup"><span data-stu-id="115e3-159"><strong>Payment positioning</strong></span></span></p></td>
<td><p><span data-ttu-id="115e3-160">Seleziona questo campo per visualizzare i pagamenti non liquidati.</span><span class="sxs-lookup"><span data-stu-id="115e3-160">Select to display payments that have not been settled.</span></span> <span data-ttu-id="115e3-161">Vengono visualizzati nella prima colonna del report.</span><span class="sxs-lookup"><span data-stu-id="115e3-161">These are displayed in the first column of the report.</span></span></p></td>
</tr>
</tbody>
</table>



[!INCLUDE[footer-include](../../includes/footer-banner.md)]