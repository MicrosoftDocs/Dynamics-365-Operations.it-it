---
title: Accumulo delle sottoscrizioni
description: Con le sottoscrizioni di assistenza è possibile accumulare ricavi manualmente nei periodi successivi alla data in cui è stata fatturata una transazione sbilanciata.
author: ShylaThompson
manager: tfehr
ms.date: 04/30/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMASubscriptionGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a9fba99eeea605f35abfe00068fe9a4cda4db0b6
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2020
ms.locfileid: "3203114"
---
# <a name="accruing-subscriptions"></a><span data-ttu-id="a1c70-103">Accumulo delle sottoscrizioni</span><span class="sxs-lookup"><span data-stu-id="a1c70-103">Accruing subscriptions</span></span> 

[!include [banner](../includes/banner.md)]


<span data-ttu-id="a1c70-104">Con le sottoscrizioni di assistenza è possibile accumulare ricavi manualmente nei periodi successivi alla data in cui è stata fatturata una transazione sbilanciata.</span><span class="sxs-lookup"><span data-stu-id="a1c70-104">With service subscriptions, you manually accrue revenue in the periods following the date when you invoiced a fee transaction.</span></span>

<span data-ttu-id="a1c70-105">Per il periodo di fatturazione impostato per la commissione di sottoscrizione vengono creati periodi di attribuzione per competenza basati sul codice periodo della sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="a1c70-105">Accrual periods are created for the invoice period that you set up for the subscription fee, and the accrual periods are based on the period code of the subscription.</span></span>

<span data-ttu-id="a1c70-106">È possibile accumulare e stornare i ricavi sospesi.</span><span class="sxs-lookup"><span data-stu-id="a1c70-106">You can accrue and reverse accrued revenue.</span></span>

## <a name="reverse-accruals-of-credit-amounts"></a><span data-ttu-id="a1c70-107">Stornare i ricavi degli importi in Avere</span><span class="sxs-lookup"><span data-stu-id="a1c70-107">Reverse accruals of credit amounts</span></span>

<span data-ttu-id="a1c70-108">Se si accreditano gli importi delle sottoscrizioni fatturate, è possibile utilizzare due metodi per stornare gli importi di attribuzione per competenza:</span><span class="sxs-lookup"><span data-stu-id="a1c70-108">If you credit invoiced subscription amounts, you can use two methods to reverse the accrual amounts:</span></span>

  - <span data-ttu-id="a1c70-109">È possibile stornare ciascuna transazione relativa ai ricavi sospesi separatamente, prima di creare la proposta di nota di accredito per la transazione.</span><span class="sxs-lookup"><span data-stu-id="a1c70-109">You can reverse each accrued revenue transaction individually before you create the credit note proposal for the transaction.</span></span> <span data-ttu-id="a1c70-110">Si tratta del metodo manuale.</span><span class="sxs-lookup"><span data-stu-id="a1c70-110">This is the manual method.</span></span> <span data-ttu-id="a1c70-111">(manuale)</span><span class="sxs-lookup"><span data-stu-id="a1c70-111">(manual)</span></span>

  - <span data-ttu-id="a1c70-112">È possibile fare in modo che gli importi accumulati vengano stornati automaticamente nella data in cui la nota di accredito viene registrata o nella data di registrazione originaria dell'attribuzione per competenza.</span><span class="sxs-lookup"><span data-stu-id="a1c70-112">You can have the accrued amounts reversed on the date where the credit note is posted or on the original posting date of the accrual.</span></span>

<span data-ttu-id="a1c70-113">Per ulteriori informazioni, vedere [Parametri sottoscrizione (modulo)](https://technet.microsoft.com/library/aa619615.aspx).</span><span class="sxs-lookup"><span data-stu-id="a1c70-113">For more information, see [Subscription parameters (form)](https://technet.microsoft.com/library/aa619615.aspx).</span></span>

## <a name="setup-requirements"></a><span data-ttu-id="a1c70-114">Imposta requisiti</span><span class="sxs-lookup"><span data-stu-id="a1c70-114">Setup requirements</span></span>

<span data-ttu-id="a1c70-115">Per accumulare ricavi, assicurarsi che vengano soddisfatti i seguenti requisiti per i dati:</span><span class="sxs-lookup"><span data-stu-id="a1c70-115">To accrue revenue, make sure that the following data requirements are met:</span></span>

## <a name="account-setup"></a><span data-ttu-id="a1c70-116">Impostazione dei conti</span><span class="sxs-lookup"><span data-stu-id="a1c70-116">Account setup</span></span>

<span data-ttu-id="a1c70-117">I conti **WIP - Sottoscrizione** e **Ricavi sospesi - Sottoscrizione** devono essere impostati nel modulo **Gestione progetti**.</span><span class="sxs-lookup"><span data-stu-id="a1c70-117">The **WIP - subscription** and the **Accrued revenue - subscription** accounts must be set up in the **Project** module.</span></span>

<span data-ttu-id="a1c70-118">Quando si registrano i ricavi sospesi, l'importo di attribuzione per competenza viene addebitato sul conto **WIP - Sottoscrizione**. Tale importo viene invece accreditato sul conto **Ricavi sospesi - Sottoscrizione**.</span><span class="sxs-lookup"><span data-stu-id="a1c70-118">When you post accrued revenue, the **WIP - subscription** account is debited with the accrual amount, and the **Accrued revenue - subscription** account is credited with the accrual amount.</span></span>

## <a name="set-up-accounts-for-accrual-of-subscription-revenue"></a><span data-ttu-id="a1c70-119">Impostare i conti per l'attribuzione per competenza dei ricavi delle sottoscrizioni</span><span class="sxs-lookup"><span data-stu-id="a1c70-119">Set up accounts for accrual of subscription revenue</span></span>

1.  <span data-ttu-id="a1c70-120">Fare clic su **Gestione progetti e contabilità** \> **Impostazioni** \> **Registrazione** \> **Impostazioni registrazione contabile**.</span><span class="sxs-lookup"><span data-stu-id="a1c70-120">Click **Project management and accounting** \> **Setup** \> **Posting** \> **Ledger posting setup**.</span></span>

2.  <span data-ttu-id="a1c70-121">Fare clic sulla scheda **Conti ricavi** e selezionare **WIP - Sottoscrizione** o **Ricavi sospesi - Sottoscrizione** per impostare i conti.</span><span class="sxs-lookup"><span data-stu-id="a1c70-121">Click the **Revenue accounts** tab, and select **WIP - subscription** or **Accrued revenue - subscription** to set up the accounts.</span></span>

## <a name="subscription-group-setup"></a><span data-ttu-id="a1c70-122">Impostazione dei gruppi di sottoscrizioni</span><span class="sxs-lookup"><span data-stu-id="a1c70-122">Subscription group setup</span></span>

<span data-ttu-id="a1c70-123">Per poter accumulare ricavi per le sottoscrizioni, è necessario che la casella di controllo **Accumula ricavi** sia selezionata.</span><span class="sxs-lookup"><span data-stu-id="a1c70-123">To be able to accrue revenue for subscriptions, the **Accrue revenue** check box must be selected.</span></span> <span data-ttu-id="a1c70-124">La casella di controllo si trova nel modulo **Gruppi di sottoscrizioni** per il gruppo associato alla sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="a1c70-124">This is found on the **Subscription groups** form for the group that is attached to the subscription.</span></span> <span data-ttu-id="a1c70-125">Fare clic su **Gestione assistenza** \> **Impostazione** \> **Sottoscrizioni assistenza** \> **Gruppo di sottoscrizioni**.</span><span class="sxs-lookup"><span data-stu-id="a1c70-125">Click **Service management** \> **Setup** \> **Service subscriptions** \> **Subscription groups**.</span></span>

## <a name="enable-revenue-accrual-on-a-subscription-group"></a><span data-ttu-id="a1c70-126">Attivare l'attribuzione per competenza dei ricavi per un gruppo di sottoscrizioni</span><span class="sxs-lookup"><span data-stu-id="a1c70-126">Enable revenue accrual on a subscription group</span></span>

1.  <span data-ttu-id="a1c70-127">Fare clic su **Gestione assistenza** \> **Impostazione** \> **Sottoscrizioni assistenza** \> **Gruppo di sottoscrizioni**.</span><span class="sxs-lookup"><span data-stu-id="a1c70-127">Click **Service management** \> **Setup** \> **Service subscriptions** \> **Subscription groups**.</span></span>

## <a name="periods"></a><span data-ttu-id="a1c70-128">Periodi</span><span class="sxs-lookup"><span data-stu-id="a1c70-128">Periods</span></span>

<span data-ttu-id="a1c70-129">È necessario impostare un codice periodo di fatturazione.</span><span class="sxs-lookup"><span data-stu-id="a1c70-129">You must set up an invoicing period code.</span></span> <span data-ttu-id="a1c70-130">È inoltre necessario impostare un periodo di attribuzione per competenza, a meno che non si desideri che i ricavi vengano accumulati entro gli stessi intervalli di tempo utilizzati per la fatturazione.</span><span class="sxs-lookup"><span data-stu-id="a1c70-130">Unless you want to accrue revenue in the same time intervals as you use for invoicing, you must also set up an accrual period.</span></span>

<span data-ttu-id="a1c70-131">Nella seguente tabella viene fornita una panoramica dei periodi di attribuzione per competenza che è possibile impostare per ogni periodo di fatturazione.</span><span class="sxs-lookup"><span data-stu-id="a1c70-131">The following table provides an overview of which accrual periods can be set up for each invoicing period:</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="a1c70-132">Periodo di fatturazione</span><span class="sxs-lookup"><span data-stu-id="a1c70-132">Invoicing period</span></span></p></th>
<th><p><span data-ttu-id="a1c70-133">Periodo di attribuzione per competenza</span><span class="sxs-lookup"><span data-stu-id="a1c70-133">Accrual period</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a1c70-134"><strong>Anni</strong></span><span class="sxs-lookup"><span data-stu-id="a1c70-134"><strong>Years</strong></span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="a1c70-135"><strong>Anni</strong></span><span class="sxs-lookup"><span data-stu-id="a1c70-135"><strong>Years</strong></span></span></p></li>
<li><p><span data-ttu-id="a1c70-136"><strong>Trimestre</strong></span><span class="sxs-lookup"><span data-stu-id="a1c70-136"><strong>Quarter</strong></span></span></p></li>
<li><p><span data-ttu-id="a1c70-137"><strong>Mese</strong></span><span class="sxs-lookup"><span data-stu-id="a1c70-137"><strong>Month</strong></span></span></p></li>
<li><p><span data-ttu-id="a1c70-138"><strong>Giorno</strong></span><span class="sxs-lookup"><span data-stu-id="a1c70-138"><strong>Day</strong></span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a1c70-139"><strong>Trimestre</strong></span><span class="sxs-lookup"><span data-stu-id="a1c70-139"><strong>Quarter</strong></span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="a1c70-140"><strong>Trimestre</strong></span><span class="sxs-lookup"><span data-stu-id="a1c70-140"><strong>Quarter</strong></span></span></p></li>
<li><p><span data-ttu-id="a1c70-141"><strong>Mese</strong></span><span class="sxs-lookup"><span data-stu-id="a1c70-141"><strong>Month</strong></span></span></p></li>
<li><p><span data-ttu-id="a1c70-142"><strong>Giorno</strong></span><span class="sxs-lookup"><span data-stu-id="a1c70-142"><strong>Day</strong></span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a1c70-143"><strong>Mese</strong></span><span class="sxs-lookup"><span data-stu-id="a1c70-143"><strong>Month</strong></span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="a1c70-144"><strong>Mese</strong></span><span class="sxs-lookup"><span data-stu-id="a1c70-144"><strong>Month</strong></span></span></p></li>
<li><p><span data-ttu-id="a1c70-145"><strong>Giorno</strong></span><span class="sxs-lookup"><span data-stu-id="a1c70-145"><strong>Day</strong></span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a1c70-146"><strong>Settimana</strong></span><span class="sxs-lookup"><span data-stu-id="a1c70-146"><strong>Week</strong></span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="a1c70-147"><strong>Giorno</strong></span><span class="sxs-lookup"><span data-stu-id="a1c70-147"><strong>Day</strong></span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a1c70-148"><strong>Giorno</strong></span><span class="sxs-lookup"><span data-stu-id="a1c70-148"><strong>Day</strong></span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="a1c70-149"><strong>Giorno</strong></span><span class="sxs-lookup"><span data-stu-id="a1c70-149"><strong>Day</strong></span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>

<span data-ttu-id="a1c70-150">L'impostazione del periodo di fatturazione rappresenta una parte obbligatoria dell'impostazione generale dei gruppi di sottoscrizioni.</span><span class="sxs-lookup"><span data-stu-id="a1c70-150">Setting up the invoicing period is a mandatory part of the overall subscription group setup.</span></span> <span data-ttu-id="a1c70-151">È possibile decidere se impostare anche un periodo di attribuzione per competenza per il gruppo di sottoscrizioni.</span><span class="sxs-lookup"><span data-stu-id="a1c70-151">You can decide whether to also set up an accrual period for the subscription group.</span></span> <span data-ttu-id="a1c70-152">Se si imposta, il periodo di attribuzione per competenza per il gruppo di sottoscrizioni viene suggerito nel campo **Codice periodo**,</span><span class="sxs-lookup"><span data-stu-id="a1c70-152">If you set up an accrual period for the subscription group, this period is suggested in the **Period code** field.</span></span> <span data-ttu-id="a1c70-153">che si trova nel modulo **Accumula ricavi sottoscrizione** quando vengono accumulati i ricavi della sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="a1c70-153">This field is found in the **Accrue subscription revenue** form, when you accrue subscription revenue.</span></span> <span data-ttu-id="a1c70-154">Tale informazione relativa al gruppo di sottoscrizioni è comunque facoltativa.</span><span class="sxs-lookup"><span data-stu-id="a1c70-154">However, the accrual period is optional information about the subscription group.</span></span>


> [!NOTE]
> <P><span data-ttu-id="a1c70-155">Utilizzare il seguente percorso per aprire il modulo <STRONG>Accumula ricavi sottoscrizione</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="a1c70-155">Use the following path to open the <STRONG>Accrue subscription revenue</STRONG> form.</span></span> <span data-ttu-id="a1c70-156">Fare clic su <STRONG>Gestione assistenza</STRONG> &gt; <STRONG>Periodico</STRONG> &gt; <STRONG>Sottoscrizioni assistenza</STRONG> &gt; <STRONG>Accumula ricavi sottoscrizione</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="a1c70-156">Click <STRONG>Service management</STRONG> &gt; <STRONG>Periodic</STRONG> &gt; <STRONG>Service subscriptions</STRONG> &gt; <STRONG>Accrue subscription revenue</STRONG>.</span></span></P>


## <a name="transactions"></a><span data-ttu-id="a1c70-157">Transazioni</span><span class="sxs-lookup"><span data-stu-id="a1c70-157">Transactions</span></span>

<span data-ttu-id="a1c70-158">È possibile controllare il numero di transazioni contabili create quando si registrano i ricavi sospesi.</span><span class="sxs-lookup"><span data-stu-id="a1c70-158">You can control the number of ledger transactions that are created when you post accrued revenue.</span></span> <span data-ttu-id="a1c70-159">Nelle sottoscrizioni definire se le transazioni contabili devono essere create come totale o per riga.</span><span class="sxs-lookup"><span data-stu-id="a1c70-159">On subscriptions, define if the ledger transactions should be created as a total or per line.</span></span>

## <a name="specify-the-level-of-posting-details-to-display-for-accrued-transactions"></a><span data-ttu-id="a1c70-160">Specificare il livello di dettagli di registrazione da visualizzare per le transazioni di attribuzione per competenza</span><span class="sxs-lookup"><span data-stu-id="a1c70-160">Specify the level of posting details to display for accrued transactions</span></span>

1.  <span data-ttu-id="a1c70-161">Fare clic su **Gestione progetti e contabilità** \> **Impostazione** \> **Parametri Gestione progetti e contabilità**.</span><span class="sxs-lookup"><span data-stu-id="a1c70-161">Click **Project management and accounting** \> **Setup** \> **Project management and accounting parameters**.</span></span>

2.  <span data-ttu-id="a1c70-162">Nel campo **Fattura** disponibile nella scheda **Finanziario** selezionare **Totale** o **Riga**.</span><span class="sxs-lookup"><span data-stu-id="a1c70-162">On the **Financial** tab, in the **Invoice** field, select **Total** or **Line**.</span></span>


## <a name="see-also"></a><span data-ttu-id="a1c70-163">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a1c70-163">See also</span></span>

[<span data-ttu-id="a1c70-164">Accumula ricavi sottoscrizione</span><span class="sxs-lookup"><span data-stu-id="a1c70-164">Accrue subscription revenue</span></span>](accrue-subscription-revenue.md)

  


