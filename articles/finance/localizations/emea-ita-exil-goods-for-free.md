---
title: Fattura fiscale per le merci consegnate gratuitamente
description: Questo argomento fornisce informazioni sulle fatture imposta per le merci che sono state consegnate gratuitamente.
author: ilkond
manager: AnnBe
ms.date: 12/18/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Italy
ms.author: mrolecki
ms.search.validFrom: 2019-11-01
ms.dyn365.ops.version: 10.0.8
ms.openlocfilehash: 4d8f9901a33cecfa0617bcaaa92738c0f527971e
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4408109"
---
# <a name="tax-invoice-for-goods-delivered-for-free"></a><span data-ttu-id="b1ae0-103">Fattura fiscale per le merci consegnate gratuitamente</span><span class="sxs-lookup"><span data-stu-id="b1ae0-103">Tax invoice for goods delivered for free</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b1ae0-104">Questo argomento descrive come gestire le merci che sono state consegnate gratuitamente.</span><span class="sxs-lookup"><span data-stu-id="b1ae0-104">This topic describes how to manage goods that were delivered free of charge.</span></span> <span data-ttu-id="b1ae0-105">La funzionalità disponibile tramite **Fattura fiscale per le merci consegnate gratuitamente** consente di generare fatture che includono le parole "Fattura gratuita".</span><span class="sxs-lookup"><span data-stu-id="b1ae0-105">The functionality that is available through the **Tax invoice for goods delivered for free** feature lets you generate invoices that include the words "Free invoice."</span></span> <span data-ttu-id="b1ae0-106">Il totale di queste fatture equivale solo all'importo delle imposte.</span><span class="sxs-lookup"><span data-stu-id="b1ae0-106">The total of these invoices equals the tax amount only.</span></span>

<span data-ttu-id="b1ae0-107">Per generare queste fatture, è necessario impostare le causali per la consegna che possono essere utilizzate nell'ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="b1ae0-107">To generate these invoices, you must set up delivery reasons that can be used in the sales order.</span></span>

<span data-ttu-id="b1ae0-108">Queste fatture possono essere utilizzate in due casi, a seconda di chi paga le tasse sugli articoli:</span><span class="sxs-lookup"><span data-stu-id="b1ae0-108">These invoices can be used in two cases, depending on who pays the taxes on the items:</span></span>

- <span data-ttu-id="b1ae0-109">La tua azienda paga l'imposta sulle vendite e il sistema genera una fattura automatica e voci contabili per il pagamento.</span><span class="sxs-lookup"><span data-stu-id="b1ae0-109">Your company pays the sales tax, and the system generates a self-invoice and accounting entries for the payment.</span></span>
- <span data-ttu-id="b1ae0-110">Il cliente paga l'imposta sulle vendite.</span><span class="sxs-lookup"><span data-stu-id="b1ae0-110">The customer pays the sales tax.</span></span>

<span data-ttu-id="b1ae0-111">la causale della consegna sulla fattura determina il caso da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="b1ae0-111">The delivery reason on the invoice determines which case you use.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b1ae0-112">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="b1ae0-112">Prerequisites</span></span>

- <span data-ttu-id="b1ae0-113">L'indirizzo principale della persona giuridica deve essere in Italia.</span><span class="sxs-lookup"><span data-stu-id="b1ae0-113">The primary address of the legal entity must be in Italy.</span></span>
- <span data-ttu-id="b1ae0-114">Nell'area di lavoro **Gestione funzionalità**, attivare la funzionalità **Fattura fiscale per le merci consegnate gratuitamente**.</span><span class="sxs-lookup"><span data-stu-id="b1ae0-114">In the **Feature management** workspace, turn on the **Tax invoice for goods delivered for free** feature.</span></span> <span data-ttu-id="b1ae0-115">Per ulteriori informazioni, vedere [Panoramica della gestione funzionalità](../../fin-and-ops/get-started/feature-management/feature-management-overview.md).</span><span class="sxs-lookup"><span data-stu-id="b1ae0-115">For more information, see [Feature management overview](../../fin-and-ops/get-started/feature-management/feature-management-overview.md).</span></span>

## <a name="set-up-the-summary-update-parameters"></a><span data-ttu-id="b1ae0-116">Impostare i parametri di aggiornamento riepilogativo</span><span class="sxs-lookup"><span data-stu-id="b1ae0-116">Set up the summary update parameters</span></span>

<span data-ttu-id="b1ae0-117">È possibile impostare i parametri di aggiornamento riepilogativo solo se è disponibile una causale della consegna sia per il documento di trasporto che per la fattura.</span><span class="sxs-lookup"><span data-stu-id="b1ae0-117">You can set up the summary update parameters only if a delivery reason is available for both the packing slip and the invoice.</span></span>

1. <span data-ttu-id="b1ae0-118">Andare a **Contabilità clienti** \> **Impostazioni** \> **Parametri contabilità clienti**.</span><span class="sxs-lookup"><span data-stu-id="b1ae0-118">Go to **Accounts receivable** \> **Setup** \> **Accounts receivable parameters**.</span></span>
2. <span data-ttu-id="b1ae0-119">Sulla scheda **Aggiornamento riepilogativo**, selezionare **Parametri di aggiornamento riepilogativo**.</span><span class="sxs-lookup"><span data-stu-id="b1ae0-119">On the **Summary update** tab, select **Summary update parameters**.</span></span>
3. <span data-ttu-id="b1ae0-120">Il parametro di aggiornamento riepilogativo **Causale consegna** deve essere selezionato sia per i documenti di trasporto che per le fatture.</span><span class="sxs-lookup"><span data-stu-id="b1ae0-120">The **Delivery reason** summary update parameter must be selected for both packing slips and invoices.</span></span> <span data-ttu-id="b1ae0-121">Sulla scheda **Fattura**, nell'elenco **Disponibili**, selezionare **Causale consegna**.</span><span class="sxs-lookup"><span data-stu-id="b1ae0-121">On the **Invoice** tab, in the **Available** list, select **Delivery reason**.</span></span> <span data-ttu-id="b1ae0-122">Quindi selezionare il pulsante freccia destra per spostare **Causale consegna** nell'elenco **Selezionato**.</span><span class="sxs-lookup"><span data-stu-id="b1ae0-122">Then select the right arrow button to move **Delivery reason** to the **Selected** list.</span></span> <span data-ttu-id="b1ae0-123">Ripetere questo passaggio sulla scheda **Documento di trasporto**.</span><span class="sxs-lookup"><span data-stu-id="b1ae0-123">Repeat this step on the **Packing slip** tab.</span></span>

![Parametri aggiornamento riepilogativo](media/emea-ita-exil-free-goods-summary-update-parameters.jpg)

## <a name="set-up-a-sales-for-free-account"></a><span data-ttu-id="b1ae0-125">Configura un account Vendite gratuite</span><span class="sxs-lookup"><span data-stu-id="b1ae0-125">Set up a Sales for free account</span></span>

<span data-ttu-id="b1ae0-126">Attenersi alla seguente procedura per configurare l'account di contabilità per le vendite gratuite.</span><span class="sxs-lookup"><span data-stu-id="b1ae0-126">Follow these steps to set up the accounting account for free sales.</span></span>

1. <span data-ttu-id="b1ae0-127">Andare a **Gestione scorte**\>**Impostazioni**\>**Registrazione**\>**Registrazione**.</span><span class="sxs-lookup"><span data-stu-id="b1ae0-127">Go to **Inventory management** \> **Setup** \> **Posting** \> **Posting**.</span></span>
2. <span data-ttu-id="b1ae0-128">Selezionare l'opzione **Vendite gratuite**.</span><span class="sxs-lookup"><span data-stu-id="b1ae0-128">Select the **Sales for free** option.</span></span>
3. <span data-ttu-id="b1ae0-129">Impostare l'account principale selezionando le relazioni e i codici conto richiesti.</span><span class="sxs-lookup"><span data-stu-id="b1ae0-129">Set up the main account by selecting the required relations and account codes.</span></span>

![Account Vendite gratuite](media/emea-ita-exil-free-goods-sales-free-account.jpg)

## <a name="set-up-miscellaneous-charges"></a><span data-ttu-id="b1ae0-131">Impostare le spese varie</span><span class="sxs-lookup"><span data-stu-id="b1ae0-131">Set up miscellaneous charges</span></span>

<span data-ttu-id="b1ae0-132">Le spese varie non sono sempre richieste o desiderate quando vengono emesse fatture di vendite gratuite.</span><span class="sxs-lookup"><span data-stu-id="b1ae0-132">Miscellaneous charges aren't always required or wanted when free sales invoices are issued.</span></span> <span data-ttu-id="b1ae0-133">Seguire questa procedura per escludere le spese varie quando vengono generate automaticamente.</span><span class="sxs-lookup"><span data-stu-id="b1ae0-133">Follow these steps to exclude miscellaneous charges when they are automatically generated.</span></span>

1. <span data-ttu-id="b1ae0-134">Andare a **Contabilità clienti** \> **Impostazione spese** \> **Codice spese**.</span><span class="sxs-lookup"><span data-stu-id="b1ae0-134">Go to **Accounts receivable** \> **Charges setup** \> **Charges code**.</span></span>
2. <span data-ttu-id="b1ae0-135">Selezionare o creare un codice spese esistente.</span><span class="sxs-lookup"><span data-stu-id="b1ae0-135">Create or select an existing charges code.</span></span>
2. <span data-ttu-id="b1ae0-136">Impostare l'opzione **Escludi spese nelle fatture gratuite** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="b1ae0-136">Set the **Exclude charge in free invoices** option to **Yes**.</span></span>

![Codici di spese](media/emea-ita-exil-free-goods-charges-codes.jpg)

## <a name="set-up-delivery-reasons"></a><span data-ttu-id="b1ae0-138">Impostare i motivi della consegna</span><span class="sxs-lookup"><span data-stu-id="b1ae0-138">Set up delivery reasons</span></span>

1. <span data-ttu-id="b1ae0-139">Andare a **Vendite e marketing** \> **Impostazioni** \> **Distribuzione** \> **Causali per la consegna**.</span><span class="sxs-lookup"><span data-stu-id="b1ae0-139">Go to **Sales and marketing** \> **Setup** \> **Distribution** \> **Reasons for delivery**.</span></span>
2. <span data-ttu-id="b1ae0-140">Selezionare la casella di controllo **Merci gratuite**.</span><span class="sxs-lookup"><span data-stu-id="b1ae0-140">Select the **Goods for free** check box.</span></span>
3. <span data-ttu-id="b1ae0-141">Nel campo **Conto fattura**, selezionare l'account cliente che rappresenta l'azienda.</span><span class="sxs-lookup"><span data-stu-id="b1ae0-141">In the **Invoice account** field, select the customer account that represents your company.</span></span>
4. <span data-ttu-id="b1ae0-142">Nel campo **Termini di pagamento** specificare i termini di pagamento in contanti.</span><span class="sxs-lookup"><span data-stu-id="b1ae0-142">In the **Terms of payment** field, specify cash terms of payment.</span></span>

![Causali per la consegna](media/emea-ita-exil-free-goods-delivery-reason.jpg)

> [!NOTE]
> <span data-ttu-id="b1ae0-144">La società emette una fattura automatica per contabilizzare le imposte richieste per le merci che vengono consegnate gratuitamente.</span><span class="sxs-lookup"><span data-stu-id="b1ae0-144">The company issues a self-invoice to account for required taxes for goods that are delivered for free.</span></span> <span data-ttu-id="b1ae0-145">Oltre alla registrazione della fattura, devono essere generate le voci contabili per il pagamento.</span><span class="sxs-lookup"><span data-stu-id="b1ae0-145">In addition to the invoice posting, the accounting entries for the payment must be generated.</span></span> <span data-ttu-id="b1ae0-146">Per rendere disponibile tale processo, è necessario disporre di un account cliente che rappresenti la propria azienda.</span><span class="sxs-lookup"><span data-stu-id="b1ae0-146">To make that process available, you must have a customer account that represents your company.</span></span> <span data-ttu-id="b1ae0-147">In questo caso, il conto fattura in un ordine cliente verrà impostato sul conto cliente dell'azienda per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="b1ae0-147">In this case, the invoice account on a sales order will be set to the company customer account by default.</span></span> <span data-ttu-id="b1ae0-148">Pertanto, la fattura emessa sarà una fattura automatica.</span><span class="sxs-lookup"><span data-stu-id="b1ae0-148">Therefore, the invoice that is issued will be a self-invoice.</span></span> <span data-ttu-id="b1ae0-149">Quando si specificano i termini di pagamento in contanti, il pagamento si verifica in aggiunta alla fattura automatica.</span><span class="sxs-lookup"><span data-stu-id="b1ae0-149">When you specify cash term of payments, the payment occurs in addition to the self-invoice.</span></span> <span data-ttu-id="b1ae0-150">Infine, la transazione del cliente viene chiusa e l'importo viene registrato nel conto di cassa specificato nel campo **Modalità di pagamento**.</span><span class="sxs-lookup"><span data-stu-id="b1ae0-150">Finally, the customer transaction is closed, and the amount is posted to the cash account that is specified in the **Terms of payment** field.</span></span> <span data-ttu-id="b1ae0-151">Questo campo verrà inoltre impostato per impostazione predefinita su un'intestazione dell'ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="b1ae0-151">This field will be also set by default on a sales order header.</span></span>
>
> <span data-ttu-id="b1ae0-152">Se il cliente paga le tasse, i campi **Conto fatture** e **Termini di pagamento** devono essere lasciati vuoti.</span><span class="sxs-lookup"><span data-stu-id="b1ae0-152">If your customer pays the taxes, the **Invoice account** and **Terms of payment** fields must be left blank.</span></span>

## <a name="posting-tax-invoices-for-goods-delivered-for-free"></a><span data-ttu-id="b1ae0-153">Registrazione delle fatture imposte per le merci consegnate gratuitamente</span><span class="sxs-lookup"><span data-stu-id="b1ae0-153">Posting tax invoices for goods delivered for free</span></span>

<span data-ttu-id="b1ae0-154">Quando si crea un ordine cliente per merci consegnate gratuitamente, il motivo di consegna specificato determina se viene generata una fattura automatica per l'azienda o se viene generata una fattura per il cliente.</span><span class="sxs-lookup"><span data-stu-id="b1ae0-154">When you create a sales order for goods that are delivered for free, the specified delivery reason determines whether a self-invoice is generated for your company, or whether an invoice is generated for your customer.</span></span> <span data-ttu-id="b1ae0-155">Se si utilizzano termini di pagamento in contanti, le voci della contabilità di pagamento verranno create anche quando si registra la fattura di vendita.</span><span class="sxs-lookup"><span data-stu-id="b1ae0-155">If you use cash terms of payment, payment accounting entries will also be created when you post the sales invoice.</span></span>

## <a name="printing-tax-invoices-for-goods-delivered-for-free"></a><span data-ttu-id="b1ae0-156">Stampa delle fatture imposte per le merci consegnate gratuitamente</span><span class="sxs-lookup"><span data-stu-id="b1ae0-156">Printing tax invoices for goods delivered for free</span></span>

<span data-ttu-id="b1ae0-157">La stampa della fattura mostrerà il titolo **Fattura gratuita**.</span><span class="sxs-lookup"><span data-stu-id="b1ae0-157">The invoice printout will show the title **Free invoice**.</span></span> <span data-ttu-id="b1ae0-158">Inoltre, agli articoli verrà aggiunto il prefisso **Articolo gratuito:** se il flag **Merci gratuite** è attivo sul motivo di consegna utilizzato per l'ordine.</span><span class="sxs-lookup"><span data-stu-id="b1ae0-158">Additionally, items will be prefixed with **Free item:** if the **Goods for free** flag is active on the delivery reason that is used for the order.</span></span>

![Stampa della fattura gratuita](media/emea-ita-exil-free-tax-invoice-printout.jpg)
