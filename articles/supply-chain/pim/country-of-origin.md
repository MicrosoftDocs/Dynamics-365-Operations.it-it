---
title: Paese di origine
description: Molte organizzazioni rilasciano certificati ai propri fornitori per garantire che i prodotti soddisfino specifici standard di certificazione. Questi certificati dipendono spesso dal paese di origine. Questo argomento fornisce informazioni sulla funzionalità del paese di origine, che consente di collegare un prodotto al relativo paese di origine e di tenere traccia delle certificazioni del prodotto.
author: dasani-madipalli
manager: tfehr
ms.date: 07/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: damadipa
ms.search.validFrom: 2020-07-15
ms.dyn365.ops.version: Release 10.0.9
ms.openlocfilehash: d0d93a02817bab8e188818862c1bb7f84b498fc1
ms.sourcegitcommit: 5bb36b74935ffe140367fd6ecf956b4857ad12e5
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/14/2020
ms.locfileid: "3802799"
---
# <a name="country-of-origin"></a><span data-ttu-id="bfeb1-105">Paese di origine</span><span class="sxs-lookup"><span data-stu-id="bfeb1-105">Country of origin</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="bfeb1-106">Molte organizzazioni rilasciano certificati ai propri fornitori per garantire che i prodotti soddisfino specifici standard di certificazione.</span><span class="sxs-lookup"><span data-stu-id="bfeb1-106">Many organizations issue certificates to their vendors to ensure that products meet specific certification standards.</span></span> <span data-ttu-id="bfeb1-107">Questi certificati dipendono spesso dal paese di origine.</span><span class="sxs-lookup"><span data-stu-id="bfeb1-107">These certificates often depend on the country of origin.</span></span> <span data-ttu-id="bfeb1-108">La funzionalità del paese di origine consente di collegare un prodotto al relativo paese di origine e di tenere traccia delle certificazioni del prodotto.</span><span class="sxs-lookup"><span data-stu-id="bfeb1-108">The country of origin feature lets you link a product to its country of origin and keep track of its product certifications.</span></span>

## <a name="turn-on-the-country-of-origin-feature"></a><span data-ttu-id="bfeb1-109">Attivare la funzionalità del paese di origine</span><span class="sxs-lookup"><span data-stu-id="bfeb1-109">Turn on the country of origin feature</span></span>

<span data-ttu-id="bfeb1-110">Prima di poter utilizzare questa funzione, è necessario attivarla nel sistema.</span><span class="sxs-lookup"><span data-stu-id="bfeb1-110">Before you can use this feature, it must be turned on in your system.</span></span> <span data-ttu-id="bfeb1-111">Gli amministratori possono utilizzare le impostazioni della [gestione delle funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) per controllare lo stato della funzione e abilitarla.</span><span class="sxs-lookup"><span data-stu-id="bfeb1-111">Admins can use the [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the status of the feature and turn it on.</span></span> <span data-ttu-id="bfeb1-112">Nell'area di lavoro **Gestione funzionalità**, la funzione è elencata nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="bfeb1-112">In the **Feature management** workspace, the feature is listed in the following way:</span></span>

- <span data-ttu-id="bfeb1-113">**Modulo:** *Gestione informazioni sul prodotto*</span><span class="sxs-lookup"><span data-stu-id="bfeb1-113">**Module:** *Product information management*</span></span>
- <span data-ttu-id="bfeb1-114">**Nome funzionalità:** *Funzionalità di gestione del paese di origine*</span><span class="sxs-lookup"><span data-stu-id="bfeb1-114">**Feature name:** *Country of origin management feature*</span></span>

## <a name="configure-source-and-destination-countries"></a><span data-ttu-id="bfeb1-115">Configura i paesi di origine e di destinazione</span><span class="sxs-lookup"><span data-stu-id="bfeb1-115">Configure source and destination countries</span></span>

<span data-ttu-id="bfeb1-116">Prima di emettere un certificato per un prodotto, è necessario collegare il prodotto al relativo paese di destinazione e a quello di origine.</span><span class="sxs-lookup"><span data-stu-id="bfeb1-116">Before you issue a certificate for a product, you must link the product to its destination country and its country of origin.</span></span>

1. <span data-ttu-id="bfeb1-117">Andare a **Gestione informazioni sul prodotto \> Impostazione \> Conformità prodotto \> Paese d'origine \> Regole del paese di origine**.</span><span class="sxs-lookup"><span data-stu-id="bfeb1-117">Go to **Product information management \> Setup \> Product compliance \> Country of origin \> Country of origin rules**.</span></span>
2. <span data-ttu-id="bfeb1-118">Selezionare l'impostazione di un paese esistente da modificare oppure selezionare **Nuovo** nel riquadro azioni per creare una nuova impostazione del paese.</span><span class="sxs-lookup"><span data-stu-id="bfeb1-118">Select an existing country setup to edit, or select **New** on the Action Pane to create a new country setup.</span></span>
3. <span data-ttu-id="bfeb1-119">Impostare i seguenti valori per il paese selezionato o nuovo.</span><span class="sxs-lookup"><span data-stu-id="bfeb1-119">Set the following values for the selected or new country.</span></span>

    | <span data-ttu-id="bfeb1-120">Campo</span><span class="sxs-lookup"><span data-stu-id="bfeb1-120">Field</span></span> | <span data-ttu-id="bfeb1-121">descrizione</span><span class="sxs-lookup"><span data-stu-id="bfeb1-121">Description</span></span> |
    |---|---|
    | <span data-ttu-id="bfeb1-122">Numero articolo</span><span class="sxs-lookup"><span data-stu-id="bfeb1-122">Item number</span></span> | <span data-ttu-id="bfeb1-123">Selezionare il numero di articolo del prodotto.</span><span class="sxs-lookup"><span data-stu-id="bfeb1-123">Select the item number of the product.</span></span> |
    | <span data-ttu-id="bfeb1-124">Paese di destinazione</span><span class="sxs-lookup"><span data-stu-id="bfeb1-124">Destination country</span></span> | <span data-ttu-id="bfeb1-125">Selezionare il paese a cui si sta inviando il prodotto.</span><span class="sxs-lookup"><span data-stu-id="bfeb1-125">Select the country that you're sending the product to.</span></span> |
    | <span data-ttu-id="bfeb1-126">Paese di origine</span><span class="sxs-lookup"><span data-stu-id="bfeb1-126">Origin country</span></span> | <span data-ttu-id="bfeb1-127">Selezionare il paese da cui si sta spedendo il prodotto.</span><span class="sxs-lookup"><span data-stu-id="bfeb1-127">Select the country that you're shipping the product from.</span></span> |

<span data-ttu-id="bfeb1-128">Lo scopo di questa impostazione è di consentire la generazione di un report distinta base (DBA) in cui è possibile includere il paese di origine per ogni parte per cui sono specificati i paesi di origine e destinazione.</span><span class="sxs-lookup"><span data-stu-id="bfeb1-128">The purpose of this setup is to help you generate a bill of materials (BOM) report where you can include the country of origin for each part that source and destination countries are specified for.</span></span> <span data-ttu-id="bfeb1-129">Questo report consentirà di ottenere un quadro olistico di dove provengono le parti e dove stanno andando.</span><span class="sxs-lookup"><span data-stu-id="bfeb1-129">This report will help you get a holistic picture of where your parts come from and where they are going.</span></span>

## <a name="keep-track-of-vendor-certificates"></a><span data-ttu-id="bfeb1-130">Tenere traccia dei certificati del fornitore</span><span class="sxs-lookup"><span data-stu-id="bfeb1-130">Keep track of vendor certificates</span></span>

<span data-ttu-id="bfeb1-131">È possibile usare la pagina **Certificati fornitori del paese di origine** per tenere traccia dei certificati rilasciati ai fornitori.</span><span class="sxs-lookup"><span data-stu-id="bfeb1-131">You can use the **Country of origin vendor certificates** page to keep track of certificates that you issue to vendors.</span></span>

<span data-ttu-id="bfeb1-132">È necessario decidere quali documenti del certificato emettere e come verranno segnalati ai clienti.</span><span class="sxs-lookup"><span data-stu-id="bfeb1-132">You must decide which certificate documents you're issuing and how you will report them to customers.</span></span> <span data-ttu-id="bfeb1-133">Questa funzionalità consente di tenere traccia dei certificati.</span><span class="sxs-lookup"><span data-stu-id="bfeb1-133">This feature helps you keep track of your certificates.</span></span> <span data-ttu-id="bfeb1-134">Inoltre, consente di scegliere se visualizzare i numeri di certificato pertinenti su fatture, documenti di trasporto e/o conferme di ordini.</span><span class="sxs-lookup"><span data-stu-id="bfeb1-134">It also lets you choose whether the relevant certificate numbers appear on invoices, packing slips, and/or order confirmations.</span></span>

<span data-ttu-id="bfeb1-135">Per configurare l'impostazione dei certificati, procedere come descritto di seguito.</span><span class="sxs-lookup"><span data-stu-id="bfeb1-135">To set up your certificate information, follow these steps.</span></span>

1. <span data-ttu-id="bfeb1-136">Andare a **Gestione informazioni sul prodotto \> Impostazione \> Conformità prodotto \> Paese d'origine \> Certificati fornitori del paese di origine**.</span><span class="sxs-lookup"><span data-stu-id="bfeb1-136">Go to **Product information management \> Setup \> Product compliance \> Country of origin \> Country of origin vendor certificates**.</span></span>
2. <span data-ttu-id="bfeb1-137">Selezionare un'impostazione del certificato esistente da modificare o selezionare **Nuovo** nel riquadro azioni per creare una nuova impostazione del certificato.</span><span class="sxs-lookup"><span data-stu-id="bfeb1-137">Select an existing certificate setup to edit, or select **New** on the Action Pane to create a new certificate setup.</span></span>
3. <span data-ttu-id="bfeb1-138">Impostare le seguenti impostazioni per il certificato selezionato o nuovo.</span><span class="sxs-lookup"><span data-stu-id="bfeb1-138">Set the following settings for the selected or new certificate.</span></span>

    | <span data-ttu-id="bfeb1-139">Campo</span><span class="sxs-lookup"><span data-stu-id="bfeb1-139">Field</span></span> | <span data-ttu-id="bfeb1-140">descrizione</span><span class="sxs-lookup"><span data-stu-id="bfeb1-140">Description</span></span> |
    |---|---|
    | <span data-ttu-id="bfeb1-141">Account fornitore</span><span class="sxs-lookup"><span data-stu-id="bfeb1-141">Vendor account</span></span> | <span data-ttu-id="bfeb1-142">Selezionare il fornitore a cui è stato rilasciato il certificato.</span><span class="sxs-lookup"><span data-stu-id="bfeb1-142">Select the vendor that you issued the certificate to.</span></span> |
    | <span data-ttu-id="bfeb1-143">Numero articolo</span><span class="sxs-lookup"><span data-stu-id="bfeb1-143">Item number</span></span> | <span data-ttu-id="bfeb1-144">Selezionare l'articolo per il quale è stato rilasciato il certificato.</span><span class="sxs-lookup"><span data-stu-id="bfeb1-144">Select the item that you issued the certificate for.</span></span> |
    | <span data-ttu-id="bfeb1-145">Paese</span><span class="sxs-lookup"><span data-stu-id="bfeb1-145">Country/region</span></span> | <span data-ttu-id="bfeb1-146">Il paese in cui è necessario utilizzare questo certificato.</span><span class="sxs-lookup"><span data-stu-id="bfeb1-146">The destination country or region where you must use this certificate.</span></span> |
    | <span data-ttu-id="bfeb1-147">Numero certificato</span><span class="sxs-lookup"><span data-stu-id="bfeb1-147">Certificate number</span></span> | <span data-ttu-id="bfeb1-148">Immettere il numero di identificazione del certificato emesso.</span><span class="sxs-lookup"><span data-stu-id="bfeb1-148">Enter the identification number of the certificate that you issued.</span></span> |
    | <span data-ttu-id="bfeb1-149">Validità</span><span class="sxs-lookup"><span data-stu-id="bfeb1-149">Effective</span></span> | <span data-ttu-id="bfeb1-150">Selezionare la data di inizio della validità del certificato corrente.</span><span class="sxs-lookup"><span data-stu-id="bfeb1-150">Select the first date when the current certificate is valid.</span></span>|
    | <span data-ttu-id="bfeb1-151">Scadenza</span><span class="sxs-lookup"><span data-stu-id="bfeb1-151">Expiration</span></span> | <span data-ttu-id="bfeb1-152">Selezionare la data di fine della validità del certificato corrente.</span><span class="sxs-lookup"><span data-stu-id="bfeb1-152">Select the last date when the current certificate is valid.</span></span> |
    | <span data-ttu-id="bfeb1-153">Stampa su fattura</span><span class="sxs-lookup"><span data-stu-id="bfeb1-153">Print on invoice</span></span> | <span data-ttu-id="bfeb1-154">Selezionare questa casella di controllo per stampare il numero di certificato sulle fatture indirizzate al paese specificato durante l'intervallo di date specificato.</span><span class="sxs-lookup"><span data-stu-id="bfeb1-154">Select this check box to print the certificate number on invoices that are addressed to the specified country during the specified date range.</span></span> |
    | <span data-ttu-id="bfeb1-155">Stampa su documento di trasporto</span><span class="sxs-lookup"><span data-stu-id="bfeb1-155">Print on packing slip</span></span> | <span data-ttu-id="bfeb1-156">Selezionare questa casella di controllo per stampare il numero di certificato sui documenti di trasporto indirizzati al paese specificato durante l'intervallo di date specificato.</span><span class="sxs-lookup"><span data-stu-id="bfeb1-156">Select this check box to print the certificate number on packing slips that are addressed to the specified country during the specified date range.</span></span> |
    | <span data-ttu-id="bfeb1-157">Stampa su ordine cliente</span><span class="sxs-lookup"><span data-stu-id="bfeb1-157">Print on sales order</span></span> | <span data-ttu-id="bfeb1-158">Selezionare questa casella di controllo per stampare il numero di certificato su ordini cliente indirizzati al paese specificato durante l'intervallo di date specificato.</span><span class="sxs-lookup"><span data-stu-id="bfeb1-158">Select this check box to print the certificate number on sales orders that are addressed to the specified country during the specified date range.</span></span> |

## <a name="include-the-country-of-origin-on-bom-reports"></a><span data-ttu-id="bfeb1-159">Includere il paese di origine nei report DBA</span><span class="sxs-lookup"><span data-stu-id="bfeb1-159">Include the country of origin on BOM reports</span></span>

<span data-ttu-id="bfeb1-160">Quando si genera un report DBA, è possibile includere il paese di origine per ciascuna parte per la quale sono stati specificati i paesi di origine e destinazione nella pagina **Regole del Paese di origine**.</span><span class="sxs-lookup"><span data-stu-id="bfeb1-160">When you generate a BOM report, you can include the country of origin for each part that you specified source and destination countries for on the **Country of origin rules** page.</span></span>

1. <span data-ttu-id="bfeb1-161">Fare clic su **Gestione informazioni sul prodotto \> Prodotti \> Prodotti rilasciati**.</span><span class="sxs-lookup"><span data-stu-id="bfeb1-161">Go to **Product information management \> Products \> Released products**.</span></span>
1. <span data-ttu-id="bfeb1-162">Selezionare o creare un prodotto per aprire la relativa pagina **Dettagli prodotto rilasciato**.</span><span class="sxs-lookup"><span data-stu-id="bfeb1-162">Select or create a product to open its **Released product details** page.</span></span>
1. <span data-ttu-id="bfeb1-163">Nel riquadro azioni, scheda **Progetta**, gruppo **DBA**, selezionare **Progettazione**.</span><span class="sxs-lookup"><span data-stu-id="bfeb1-163">On the Action Pane, on the **Engineer** tab, in the **BOM** group, select **Designer**.</span></span>
1. <span data-ttu-id="bfeb1-164">Nella pagina visualizzata, nel riquadro azioni, selezionare **DBA \> Stampa**.</span><span class="sxs-lookup"><span data-stu-id="bfeb1-164">On the page that appears, on the Action Pane, select **BOM \> Print**.</span></span>
1. <span data-ttu-id="bfeb1-165">Nella finestra di dialogo **Righe della distinta base**, impostare il campo **Paese di destinazione** nel paese di destinazione che si desidera visualizzare nel report.</span><span class="sxs-lookup"><span data-stu-id="bfeb1-165">In **Bill of materials lines** dialog box, set the **Destination country** field to the destination country that you want to view on your report.</span></span>
1. <span data-ttu-id="bfeb1-166">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="bfeb1-166">Select **OK**.</span></span>

<span data-ttu-id="bfeb1-167">Viene generato e visualizzato un report con informazioni sul paese di origine di ciascuna parte.</span><span class="sxs-lookup"><span data-stu-id="bfeb1-167">A report that shows information about the country of origin of each part is generated and shown.</span></span> <span data-ttu-id="bfeb1-168">Di seguito è riportato un esempio del report.</span><span class="sxs-lookup"><span data-stu-id="bfeb1-168">Here is an example of the report.</span></span>

<span data-ttu-id="bfeb1-169">![Report del paese di origine](media/country-of-origin-report.png "Report del paese di origine")</span><span class="sxs-lookup"><span data-stu-id="bfeb1-169">![Country of origin report](media/country-of-origin-report.png "Country of origin report")</span></span>
