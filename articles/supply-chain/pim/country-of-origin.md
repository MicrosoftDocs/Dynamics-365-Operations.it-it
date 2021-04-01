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
ms.search.form: COOVendorCerts
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: damadipa
ms.search.validFrom: 2020-07-15
ms.dyn365.ops.version: Release 10.0.9
ms.openlocfilehash: bb35770f32c21a685b21a41dc7c369ee01fe3891
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5243299"
---
# <a name="country-of-origin"></a><span data-ttu-id="1e382-105">Paese di origine</span><span class="sxs-lookup"><span data-stu-id="1e382-105">Country of origin</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="1e382-106">Molte organizzazioni rilasciano certificati ai propri fornitori per garantire che i prodotti soddisfino specifici standard di certificazione.</span><span class="sxs-lookup"><span data-stu-id="1e382-106">Many organizations issue certificates to their vendors to ensure that products meet specific certification standards.</span></span> <span data-ttu-id="1e382-107">Questi certificati dipendono spesso dal paese di origine.</span><span class="sxs-lookup"><span data-stu-id="1e382-107">These certificates often depend on the country of origin.</span></span> <span data-ttu-id="1e382-108">La funzionalità del paese di origine consente di collegare un prodotto al relativo paese di origine e di tenere traccia delle certificazioni del prodotto.</span><span class="sxs-lookup"><span data-stu-id="1e382-108">The country of origin feature lets you link a product to its country of origin and keep track of its product certifications.</span></span>

## <a name="turn-on-the-country-of-origin-feature"></a><span data-ttu-id="1e382-109">Attivare la funzionalità del paese di origine</span><span class="sxs-lookup"><span data-stu-id="1e382-109">Turn on the country of origin feature</span></span>

<span data-ttu-id="1e382-110">Prima di poter utilizzare questa funzione, è necessario attivarla nel sistema.</span><span class="sxs-lookup"><span data-stu-id="1e382-110">Before you can use this feature, it must be turned on in your system.</span></span> <span data-ttu-id="1e382-111">Gli amministratori possono utilizzare le impostazioni della [gestione delle funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) per controllare lo stato della funzione e abilitarla.</span><span class="sxs-lookup"><span data-stu-id="1e382-111">Admins can use the [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the status of the feature and turn it on.</span></span> <span data-ttu-id="1e382-112">Nell'area di lavoro **Gestione funzionalità**, la funzione è elencata nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="1e382-112">In the **Feature management** workspace, the feature is listed in the following way:</span></span>

- <span data-ttu-id="1e382-113">**Modulo:** *Gestione informazioni sul prodotto*</span><span class="sxs-lookup"><span data-stu-id="1e382-113">**Module:** *Product information management*</span></span>
- <span data-ttu-id="1e382-114">**Nome funzionalità:** *Funzionalità di gestione del paese di origine*</span><span class="sxs-lookup"><span data-stu-id="1e382-114">**Feature name:** *Country of origin management feature*</span></span>

## <a name="configure-source-and-destination-countries"></a><span data-ttu-id="1e382-115">Configura i paesi di origine e di destinazione</span><span class="sxs-lookup"><span data-stu-id="1e382-115">Configure source and destination countries</span></span>

<span data-ttu-id="1e382-116">Prima di emettere un certificato per un prodotto, è necessario collegare il prodotto al relativo paese di destinazione e a quello di origine.</span><span class="sxs-lookup"><span data-stu-id="1e382-116">Before you issue a certificate for a product, you must link the product to its destination country and its country of origin.</span></span>

1. <span data-ttu-id="1e382-117">Andare a **Gestione informazioni sul prodotto \> Impostazione \> Conformità prodotto \> Paese d'origine \> Regole del paese di origine**.</span><span class="sxs-lookup"><span data-stu-id="1e382-117">Go to **Product information management \> Setup \> Product compliance \> Country of origin \> Country of origin rules**.</span></span>
2. <span data-ttu-id="1e382-118">Selezionare l'impostazione di un paese esistente da modificare oppure selezionare **Nuovo** nel riquadro azioni per creare una nuova impostazione del paese.</span><span class="sxs-lookup"><span data-stu-id="1e382-118">Select an existing country setup to edit, or select **New** on the Action Pane to create a new country setup.</span></span>
3. <span data-ttu-id="1e382-119">Impostare i seguenti valori per il paese selezionato o nuovo.</span><span class="sxs-lookup"><span data-stu-id="1e382-119">Set the following values for the selected or new country.</span></span>

    | <span data-ttu-id="1e382-120">Campo</span><span class="sxs-lookup"><span data-stu-id="1e382-120">Field</span></span> | <span data-ttu-id="1e382-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1e382-121">Description</span></span> |
    |---|---|
    | <span data-ttu-id="1e382-122">Numero articolo</span><span class="sxs-lookup"><span data-stu-id="1e382-122">Item number</span></span> | <span data-ttu-id="1e382-123">Selezionare il numero di articolo del prodotto.</span><span class="sxs-lookup"><span data-stu-id="1e382-123">Select the item number of the product.</span></span> |
    | <span data-ttu-id="1e382-124">Paese di destinazione</span><span class="sxs-lookup"><span data-stu-id="1e382-124">Destination country</span></span> | <span data-ttu-id="1e382-125">Selezionare il paese a cui si sta inviando il prodotto.</span><span class="sxs-lookup"><span data-stu-id="1e382-125">Select the country that you're sending the product to.</span></span> |
    | <span data-ttu-id="1e382-126">Paese di origine</span><span class="sxs-lookup"><span data-stu-id="1e382-126">Origin country</span></span> | <span data-ttu-id="1e382-127">Selezionare il paese da cui si sta spedendo il prodotto.</span><span class="sxs-lookup"><span data-stu-id="1e382-127">Select the country that you're shipping the product from.</span></span> |

<span data-ttu-id="1e382-128">Lo scopo di questa impostazione è di consentire la generazione di un report distinta base (DBA) in cui è possibile includere il paese di origine per ogni parte per cui sono specificati i paesi di origine e destinazione.</span><span class="sxs-lookup"><span data-stu-id="1e382-128">The purpose of this setup is to help you generate a bill of materials (BOM) report where you can include the country of origin for each part that source and destination countries are specified for.</span></span> <span data-ttu-id="1e382-129">Questo report consentirà di ottenere un quadro olistico di dove provengono le parti e dove stanno andando.</span><span class="sxs-lookup"><span data-stu-id="1e382-129">This report will help you get a holistic picture of where your parts come from and where they are going.</span></span>

## <a name="keep-track-of-vendor-certificates"></a><span data-ttu-id="1e382-130">Tenere traccia dei certificati del fornitore</span><span class="sxs-lookup"><span data-stu-id="1e382-130">Keep track of vendor certificates</span></span>

<span data-ttu-id="1e382-131">È possibile usare la pagina **Certificati fornitori del paese di origine** per tenere traccia dei certificati rilasciati ai fornitori.</span><span class="sxs-lookup"><span data-stu-id="1e382-131">You can use the **Country of origin vendor certificates** page to keep track of certificates that you issue to vendors.</span></span>

<span data-ttu-id="1e382-132">È necessario decidere quali documenti del certificato emettere e come verranno segnalati ai clienti.</span><span class="sxs-lookup"><span data-stu-id="1e382-132">You must decide which certificate documents you're issuing and how you will report them to customers.</span></span> <span data-ttu-id="1e382-133">Questa funzionalità consente di tenere traccia dei certificati.</span><span class="sxs-lookup"><span data-stu-id="1e382-133">This feature helps you keep track of your certificates.</span></span> <span data-ttu-id="1e382-134">Inoltre, consente di scegliere se visualizzare i numeri di certificato pertinenti su fatture, documenti di trasporto e/o conferme di ordini.</span><span class="sxs-lookup"><span data-stu-id="1e382-134">It also lets you choose whether the relevant certificate numbers appear on invoices, packing slips, and/or order confirmations.</span></span>

<span data-ttu-id="1e382-135">Per configurare l'impostazione dei certificati, procedere come descritto di seguito.</span><span class="sxs-lookup"><span data-stu-id="1e382-135">To set up your certificate information, follow these steps.</span></span>

1. <span data-ttu-id="1e382-136">Andare a **Gestione informazioni sul prodotto \> Impostazione \> Conformità prodotto \> Paese d'origine \> Certificati fornitori del paese di origine**.</span><span class="sxs-lookup"><span data-stu-id="1e382-136">Go to **Product information management \> Setup \> Product compliance \> Country of origin \> Country of origin vendor certificates**.</span></span>
2. <span data-ttu-id="1e382-137">Selezionare un'impostazione del certificato esistente da modificare o selezionare **Nuovo** nel riquadro azioni per creare una nuova impostazione del certificato.</span><span class="sxs-lookup"><span data-stu-id="1e382-137">Select an existing certificate setup to edit, or select **New** on the Action Pane to create a new certificate setup.</span></span>
3. <span data-ttu-id="1e382-138">Impostare le seguenti impostazioni per il certificato selezionato o nuovo.</span><span class="sxs-lookup"><span data-stu-id="1e382-138">Set the following settings for the selected or new certificate.</span></span>

    | <span data-ttu-id="1e382-139">Campo</span><span class="sxs-lookup"><span data-stu-id="1e382-139">Field</span></span> | <span data-ttu-id="1e382-140">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1e382-140">Description</span></span> |
    |---|---|
    | <span data-ttu-id="1e382-141">Account fornitore</span><span class="sxs-lookup"><span data-stu-id="1e382-141">Vendor account</span></span> | <span data-ttu-id="1e382-142">Selezionare il fornitore a cui è stato rilasciato il certificato.</span><span class="sxs-lookup"><span data-stu-id="1e382-142">Select the vendor that you issued the certificate to.</span></span> |
    | <span data-ttu-id="1e382-143">Numero articolo</span><span class="sxs-lookup"><span data-stu-id="1e382-143">Item number</span></span> | <span data-ttu-id="1e382-144">Selezionare l'articolo per il quale è stato rilasciato il certificato.</span><span class="sxs-lookup"><span data-stu-id="1e382-144">Select the item that you issued the certificate for.</span></span> |
    | <span data-ttu-id="1e382-145">Paese</span><span class="sxs-lookup"><span data-stu-id="1e382-145">Country/region</span></span> | <span data-ttu-id="1e382-146">Il paese in cui è necessario utilizzare questo certificato.</span><span class="sxs-lookup"><span data-stu-id="1e382-146">The destination country or region where you must use this certificate.</span></span> |
    | <span data-ttu-id="1e382-147">Numero certificato</span><span class="sxs-lookup"><span data-stu-id="1e382-147">Certificate number</span></span> | <span data-ttu-id="1e382-148">Immettere il numero di identificazione del certificato emesso.</span><span class="sxs-lookup"><span data-stu-id="1e382-148">Enter the identification number of the certificate that you issued.</span></span> |
    | <span data-ttu-id="1e382-149">Validità</span><span class="sxs-lookup"><span data-stu-id="1e382-149">Effective</span></span> | <span data-ttu-id="1e382-150">Selezionare la data di inizio della validità del certificato corrente.</span><span class="sxs-lookup"><span data-stu-id="1e382-150">Select the first date when the current certificate is valid.</span></span>|
    | <span data-ttu-id="1e382-151">Scadenza</span><span class="sxs-lookup"><span data-stu-id="1e382-151">Expiration</span></span> | <span data-ttu-id="1e382-152">Selezionare la data di fine della validità del certificato corrente.</span><span class="sxs-lookup"><span data-stu-id="1e382-152">Select the last date when the current certificate is valid.</span></span> |
    | <span data-ttu-id="1e382-153">Stampa su fattura</span><span class="sxs-lookup"><span data-stu-id="1e382-153">Print on invoice</span></span> | <span data-ttu-id="1e382-154">Selezionare questa casella di controllo per stampare il numero di certificato sulle fatture indirizzate al paese specificato durante l'intervallo di date specificato.</span><span class="sxs-lookup"><span data-stu-id="1e382-154">Select this check box to print the certificate number on invoices that are addressed to the specified country during the specified date range.</span></span> |
    | <span data-ttu-id="1e382-155">Stampa su documento di trasporto</span><span class="sxs-lookup"><span data-stu-id="1e382-155">Print on packing slip</span></span> | <span data-ttu-id="1e382-156">Selezionare questa casella di controllo per stampare il numero di certificato sui documenti di trasporto indirizzati al paese specificato durante l'intervallo di date specificato.</span><span class="sxs-lookup"><span data-stu-id="1e382-156">Select this check box to print the certificate number on packing slips that are addressed to the specified country during the specified date range.</span></span> |
    | <span data-ttu-id="1e382-157">Stampa su ordine cliente</span><span class="sxs-lookup"><span data-stu-id="1e382-157">Print on sales order</span></span> | <span data-ttu-id="1e382-158">Selezionare questa casella di controllo per stampare il numero di certificato su ordini cliente indirizzati al paese specificato durante l'intervallo di date specificato.</span><span class="sxs-lookup"><span data-stu-id="1e382-158">Select this check box to print the certificate number on sales orders that are addressed to the specified country during the specified date range.</span></span> |

## <a name="include-the-country-of-origin-on-bom-reports"></a><span data-ttu-id="1e382-159">Includere il paese di origine nei report DBA</span><span class="sxs-lookup"><span data-stu-id="1e382-159">Include the country of origin on BOM reports</span></span>

<span data-ttu-id="1e382-160">Quando si genera un report DBA, è possibile includere il paese di origine per ciascuna parte per la quale sono stati specificati i paesi di origine e destinazione nella pagina **Regole del Paese di origine**.</span><span class="sxs-lookup"><span data-stu-id="1e382-160">When you generate a BOM report, you can include the country of origin for each part that you specified source and destination countries for on the **Country of origin rules** page.</span></span>

1. <span data-ttu-id="1e382-161">Fare clic su **Gestione informazioni sul prodotto \> Prodotti \> Prodotti rilasciati**.</span><span class="sxs-lookup"><span data-stu-id="1e382-161">Go to **Product information management \> Products \> Released products**.</span></span>
1. <span data-ttu-id="1e382-162">Selezionare o creare un prodotto per aprire la relativa pagina **Dettagli prodotto rilasciato**.</span><span class="sxs-lookup"><span data-stu-id="1e382-162">Select or create a product to open its **Released product details** page.</span></span>
1. <span data-ttu-id="1e382-163">Nel riquadro azioni, scheda **Progetta**, gruppo **DBA**, selezionare **Progettazione**.</span><span class="sxs-lookup"><span data-stu-id="1e382-163">On the Action Pane, on the **Engineer** tab, in the **BOM** group, select **Designer**.</span></span>
1. <span data-ttu-id="1e382-164">Nella pagina visualizzata, nel riquadro azioni, selezionare **DBA \> Stampa**.</span><span class="sxs-lookup"><span data-stu-id="1e382-164">On the page that appears, on the Action Pane, select **BOM \> Print**.</span></span>
1. <span data-ttu-id="1e382-165">Nella finestra di dialogo **Righe della distinta base**, impostare il campo **Paese di destinazione** nel paese di destinazione che si desidera visualizzare nel report.</span><span class="sxs-lookup"><span data-stu-id="1e382-165">In **Bill of materials lines** dialog box, set the **Destination country** field to the destination country that you want to view on your report.</span></span>
1. <span data-ttu-id="1e382-166">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="1e382-166">Select **OK**.</span></span>

<span data-ttu-id="1e382-167">Viene generato e visualizzato un report con informazioni sul paese di origine di ciascuna parte.</span><span class="sxs-lookup"><span data-stu-id="1e382-167">A report that shows information about the country of origin of each part is generated and shown.</span></span> <span data-ttu-id="1e382-168">Di seguito è riportato un esempio del report.</span><span class="sxs-lookup"><span data-stu-id="1e382-168">Here is an example of the report.</span></span>

<span data-ttu-id="1e382-169">![Report del paese di origine](media/country-of-origin-report.png "Report del paese di origine")</span><span class="sxs-lookup"><span data-stu-id="1e382-169">![Country of origin report](media/country-of-origin-report.png "Country of origin report")</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]