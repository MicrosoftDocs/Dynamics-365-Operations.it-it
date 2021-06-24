---
title: Dashboard di gestione dell'utilizzo
description: Questo argomento spiega come utilizzare il dashboard di gestione dell'utilizzo per monitorare l'utilizzo del servizio di fatturazione elettronica mantenendo la conformità.
author: gionoder
ms.date: 06/02/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 411c2d33c81738dcacfb7c8feec991d0fd06fb78
ms.sourcegitcommit: 9069a8511dfe11d09a2b51d32547ba10fea48bed
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2021
ms.locfileid: "6130508"
---
# <a name="usage-management-dashboard"></a><span data-ttu-id="a83b6-103">Dashboard di gestione dell'utilizzo</span><span class="sxs-lookup"><span data-stu-id="a83b6-103">Usage management dashboard</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a83b6-104">Il dashboard **Gestione dell'utilizzo** permette di monitorare l'utilizzo del servizio di fatturazione elettronica e quindi aiuta l'organizzazione a rimanere conforme in termini di utilizzo mensile.</span><span class="sxs-lookup"><span data-stu-id="a83b6-104">The **Usage management** dashboard helps you monitor usage of the Electronic Invoicing service, and therefore helps your organization remain compliant in terms of its monthly usage.</span></span> <span data-ttu-id="a83b6-105">La conformità viene determinata calcolando il volume di invii e confrontandolo con il volume di invii acquisito per identificare eventuali scostamenti tra il volume acquisito e il volume utilizzato.</span><span class="sxs-lookup"><span data-stu-id="a83b6-105">Compliance is determined by calculating the submission volume and comparing it with the acquired volume of submissions to identify any deviations between the acquired volume and the used volume.</span></span>

<span data-ttu-id="a83b6-106">La dashboard include i seguenti indicatori:</span><span class="sxs-lookup"><span data-stu-id="a83b6-106">The dashboard includes the following indicators:</span></span>

- <span data-ttu-id="a83b6-107">Un indicatore dei costi che è possibile utilizzare per monitorare il consumo ai fini della conformità delle licenze:</span><span class="sxs-lookup"><span data-stu-id="a83b6-107">One cost indicator that you can use to monitor consumption for licensing compliance purposes:</span></span>

    - <span data-ttu-id="a83b6-108">Utilizzo mensile (esportazione)</span><span class="sxs-lookup"><span data-stu-id="a83b6-108">Usage per month (export)</span></span>

- <span data-ttu-id="a83b6-109">Tre indicatori operativi che è possibile utilizzare per monitorare l'utilizzo del servizio di fatturazione elettronica a fini gestionali:</span><span class="sxs-lookup"><span data-stu-id="a83b6-109">Three operational indicators that you can use to track usage of the Electronic Invoicing service for management purposes:</span></span>

    - <span data-ttu-id="a83b6-110">Utilizzo per funzionalità</span><span class="sxs-lookup"><span data-stu-id="a83b6-110">Usage by feature</span></span>
    - <span data-ttu-id="a83b6-111">Utilizzo per ambiente</span><span class="sxs-lookup"><span data-stu-id="a83b6-111">Usage by environment</span></span>
    - <span data-ttu-id="a83b6-112">Utilizzo mensile (importazione)</span><span class="sxs-lookup"><span data-stu-id="a83b6-112">Usage per month (import)</span></span>

## <a name="measurement-scope"></a><span data-ttu-id="a83b6-113">Ambito della misurazione</span><span class="sxs-lookup"><span data-stu-id="a83b6-113">Measurement scope</span></span>

- <span data-ttu-id="a83b6-114">Unità di misura:</span><span class="sxs-lookup"><span data-stu-id="a83b6-114">Unit of measure:</span></span> 

    <span data-ttu-id="a83b6-115">Il dashboard **Gestione dell'utilizzo** conta l'invio di documenti aziendali e fatture elettroniche importate.</span><span class="sxs-lookup"><span data-stu-id="a83b6-115">The **Usage management** dashboard counts the submission of business documents and imported electronic invoices.</span></span>

- <span data-ttu-id="a83b6-116">Organizzazione:</span><span class="sxs-lookup"><span data-stu-id="a83b6-116">Organization:</span></span> 

    <span data-ttu-id="a83b6-117">Il conteggio viene riepilogato dall'ID tenant dell'organizzazione, indipendentemente dal numero di istanze di Microsoft Dynamics 365 Finance o Dynamics 365 Supply Chain Management, ovvero il numero di persone giuridiche in cui è abilitato il servizio di fatturazione elettronica.</span><span class="sxs-lookup"><span data-stu-id="a83b6-117">Counting is summarized by the tenant ID of your organization, regardless of the number of instances of Microsoft Dynamics 365 Finance or Dynamics 365 Supply Chain Management, or the number of legal entities where the Electronic Invoicing service is enabled.</span></span>


## <a name="indicator-usage-per-month-export"></a><span data-ttu-id="a83b6-118">Indicatore: utilizzo mensile (esportazione)</span><span class="sxs-lookup"><span data-stu-id="a83b6-118">Indicator: Usage per month (export)</span></span>

<span data-ttu-id="a83b6-119">Questo indicatore fornisce dettagli sulle fatture elettroniche emesse dall'organizzazione durante un periodo definito.</span><span class="sxs-lookup"><span data-stu-id="a83b6-119">This indicator provides details about the electronic invoices that your organization issues during a defined period.</span></span>

### <a name="scope"></a><span data-ttu-id="a83b6-120">Ambito</span><span class="sxs-lookup"><span data-stu-id="a83b6-120">Scope</span></span>
- <span data-ttu-id="a83b6-121">Il numero di documenti commerciali inviati da Finance e Supply Chain Management al servizio di fatturazione elettronica, indipendentemente dal numero di righe contenute in tali documenti commerciali.</span><span class="sxs-lookup"><span data-stu-id="a83b6-121">The number of business documents that are submitted from Finance and Supply Chain Management to the Electronic Invoicing service, regardless of number of lines that those business documents contain.</span></span>
- <span data-ttu-id="a83b6-122">Il numero di documenti commerciali inviati che vengono elaborati correttamente dal servizio di fatturazione elettronica.</span><span class="sxs-lookup"><span data-stu-id="a83b6-122">The number of submitted business documents that are successfully processed by the Electronic Invoicing service.</span></span> <span data-ttu-id="a83b6-123">Un documento viene considerato elaborato correttamente quando viene completato il flusso di azioni definito nell'impostazione della funzionalità.</span><span class="sxs-lookup"><span data-stu-id="a83b6-123">A document is considered successfully processed when the flow of actions that are defined in the feature setup is completed.</span></span>

> [!NOTE]
> <span data-ttu-id="a83b6-124">Quando una fattura elettronica viene inviata a un servizio Web esterno, il conteggio è indipendente dai risultati dell'elaborazione del servizio Web (accettato, rifiutato o errore di convalida dello schema).</span><span class="sxs-lookup"><span data-stu-id="a83b6-124">When an electronic invoice is submitted to an external web service, counting is independent of the results of web service processing (accepted, rejected, or schema validation error).</span></span> <span data-ttu-id="a83b6-125">Se il servizio Web ha ricevuto e risposto alla richiesta del servizio di fatturazione elettronica, l'invio è considerato un conteggio valido.</span><span class="sxs-lookup"><span data-stu-id="a83b6-125">If the web service received and responded to the request from the Electronic Invoicing service, the submission is considered a valid counting.</span></span>

- <span data-ttu-id="a83b6-126">**Eccezione:** i documenti commerciali non vengono conteggiati se vengono reinviati da Finance e Supply Chain Management al servizio di fatturazione elettronica, ad esempio negli scenari in cui è necessario inviare nuovamente lo stesso documento commerciale per modificare lo stato della fattura elettronica.</span><span class="sxs-lookup"><span data-stu-id="a83b6-126">**Exception:** Business documents aren't counted if they are resubmitted from Finance and Supply Chain Management to the Electronic Invoicing service, such as in the scenarios where a resubmission of the same business document is required to change the status of the electronic invoice.</span></span> <span data-ttu-id="a83b6-127">Ad esempio, l'emissione di una fattura elettronica brasiliana (documento fiscale) viene considerata valida, ma la richiesta di annullamento non viene conteggiata.</span><span class="sxs-lookup"><span data-stu-id="a83b6-127">For example, issuance of a Brazilian electronic invoice (fiscal document) is counted as valid, but the cancellation request for it isn't counted.</span></span>


### <a name="calculation"></a><span data-ttu-id="a83b6-128">Calcolo</span><span class="sxs-lookup"><span data-stu-id="a83b6-128">Calculation</span></span>

<span data-ttu-id="a83b6-129">Il calcolo del saldo è calcolato come segue:</span><span class="sxs-lookup"><span data-stu-id="a83b6-129">The calculation of the balance is calculated as follows:</span></span>

<span data-ttu-id="a83b6-130">Saldo = Gratuito + Acquistato – Usato</span><span class="sxs-lookup"><span data-stu-id="a83b6-130">Balance = Free + Purchased – Used</span></span>

<span data-ttu-id="a83b6-131">Percorso:</span><span class="sxs-lookup"><span data-stu-id="a83b6-131">Where:</span></span>

- <span data-ttu-id="a83b6-132">Gratuito:</span><span class="sxs-lookup"><span data-stu-id="a83b6-132">Free:</span></span>
  
    <span data-ttu-id="a83b6-133">Un volume gratuito di documenti commerciali che il cliente può inviare ogni mese.</span><span class="sxs-lookup"><span data-stu-id="a83b6-133">A free volume of business documents the customer can submit per month.</span></span> <span data-ttu-id="a83b6-134">Include un pacchetto di 100 documenti commerciali che possono essere inviati al servizio di fatturazione elettronica.</span><span class="sxs-lookup"><span data-stu-id="a83b6-134">It includes a package of 100 business documents that can be submitted to the Electronic Invoicing service.</span></span> <span data-ttu-id="a83b6-135">Il volume gratuito non è cumulativo e l'eventuale saldo residuo non viene riportato al periodo successivo.</span><span class="sxs-lookup"><span data-stu-id="a83b6-135">Free volume isn't cumulative, and any remaining balance isn't rolled over to the next period.</span></span>
  
- <span data-ttu-id="a83b6-136">Acquistato:</span><span class="sxs-lookup"><span data-stu-id="a83b6-136">Purchased:</span></span>
  
    <span data-ttu-id="a83b6-137">Un pacchetto di 1.000 documenti commerciali che possono essere inviati al servizio di fatturazione elettronica.</span><span class="sxs-lookup"><span data-stu-id="a83b6-137">A package of 1,000 business documents that can be submitted to the Electronic Invoicing service.</span></span> <span data-ttu-id="a83b6-138">Questo pacchetto deve essere acquistato per l'organizzazione su base mensile.</span><span class="sxs-lookup"><span data-stu-id="a83b6-138">This package must be acquired for your organization on a monthly basis.</span></span> <span data-ttu-id="a83b6-139">Il volume acquistato non è cumulativo e l'eventuale saldo residuo non viene riportato al periodo successivo.</span><span class="sxs-lookup"><span data-stu-id="a83b6-139">Purchased volume isn't cumulative, and any remaining balance isn't rolled over to the next period.</span></span>
  
- <span data-ttu-id="a83b6-140">Usato:</span><span class="sxs-lookup"><span data-stu-id="a83b6-140">Used:</span></span> 

    <span data-ttu-id="a83b6-141">Il conteggio dei documenti commerciali inviati al servizio di fatturazione elettronica secondo criteri definiti.</span><span class="sxs-lookup"><span data-stu-id="a83b6-141">The count of business document submissions to the Electronic Invoicing service according to defined criteria.</span></span>
   
> [!IMPORTANT]
> <span data-ttu-id="a83b6-142">Se l'organizzazione prevede di superare il volume mensile di 100 invii gratuiti, sarà necessari acquistare il volume di picco per garantire la conformità ai criteri di licenza Microsoft per il servizio di fatturazione elettronica.</span><span class="sxs-lookup"><span data-stu-id="a83b6-142">If your organization plans to exceed the monthly volume of 100 free submissions, purchase the peak volume to ensure that you remain compliant with the Microsoft licensing policy for the Electronic Invoicing service.</span></span>
>
> <span data-ttu-id="a83b6-143">Attualmente, il volume acquistato deve essere immesso manualmente, in base alla data di acquisizione, come pacchetti multipli di 1.000 invii.</span><span class="sxs-lookup"><span data-stu-id="a83b6-143">Currently, purchased volume must be manually entered, according to the date of acquisition, as multiple packages of 1,000 submissions.</span></span>

## <a name="indicator-usage-by-feature"></a><span data-ttu-id="a83b6-144">Indicatore: utilizzo per funzione</span><span class="sxs-lookup"><span data-stu-id="a83b6-144">Indicator: Usage by feature</span></span>

<span data-ttu-id="a83b6-145">Questo indicatore mostra l'utilizzo delle funzionalità di fatturazione elettronica per l'emissione di fatture elettroniche durante un periodo definito.</span><span class="sxs-lookup"><span data-stu-id="a83b6-145">This indicator shows the usage of electronic invoicing features for issuance of electronic invoices during a defined period.</span></span>

- <span data-ttu-id="a83b6-146">Calcolo:</span><span class="sxs-lookup"><span data-stu-id="a83b6-146">Calculation:</span></span>
  
    <span data-ttu-id="a83b6-147">Usato = Il numero di volte in cui ciascuna funzionalità di fatturazione elettronica è stata utilizzata durante l'invio di documenti commerciali al servizio di fatturazione elettronica.</span><span class="sxs-lookup"><span data-stu-id="a83b6-147">Used = The count of how many times each electronic invoicing feature was used during the submission of business documents to the Electronic Invoicing service.</span></span>

## <a name="indicator-usage-by-environment"></a><span data-ttu-id="a83b6-148">Indicatore: utilizzo per ambiente</span><span class="sxs-lookup"><span data-stu-id="a83b6-148">Indicator: Usage by environment</span></span>

<span data-ttu-id="a83b6-149">Questo indicatore mostra l'utilizzo degli ambienti del servizio di fatturazione elettronica durante un periodo definito.</span><span class="sxs-lookup"><span data-stu-id="a83b6-149">This indicator shows the usage of electronic invoicing service environments during a defined period.</span></span>

- <span data-ttu-id="a83b6-150">Calcolo:</span><span class="sxs-lookup"><span data-stu-id="a83b6-150">Calculation:</span></span>
    
    <span data-ttu-id="a83b6-151">Usato = Il numero di volte in cui ciascun ambiente del servizio di fatturazione elettronica è stato utilizzato durante l'invio di documenti commerciali al servizio di fatturazione elettronica.</span><span class="sxs-lookup"><span data-stu-id="a83b6-151">Used = The count of how many times each electronic invoicing service environment was used during the submission of business documents to the Electronic Invoicing service.</span></span>

## <a name="indicator-usage-per-month-import"></a><span data-ttu-id="a83b6-152">Indicatore: utilizzo mensile (importazione)</span><span class="sxs-lookup"><span data-stu-id="a83b6-152">Indicator: Usage per month (import)</span></span>

<span data-ttu-id="a83b6-153">Questo indicatore mostra il volume di importazione delle fatture elettroniche da parte del servizio di fatturazione elettronica in Finance e Supply Chain Management durante un periodo definito.</span><span class="sxs-lookup"><span data-stu-id="a83b6-153">This indicator shows the volume of importation of electronic invoices by Electronic Invoicing service into Finance and Supply Chain Management during a defined period.</span></span>

- <span data-ttu-id="a83b6-154">Ambito:</span><span class="sxs-lookup"><span data-stu-id="a83b6-154">Scope:</span></span>

    <span data-ttu-id="a83b6-155">Fatture elettroniche importate in Finance e Supply Chain Management, indipendentemente dal numero di righe contenute in tali fatture elettroniche.</span><span class="sxs-lookup"><span data-stu-id="a83b6-155">Electronic invoices that are imported into Finance and Supply Chain Management, regardless of the number of lines that those electronic invoices contain.</span></span>

- <span data-ttu-id="a83b6-156">Calcolo:</span><span class="sxs-lookup"><span data-stu-id="a83b6-156">Calculation:</span></span>

    <span data-ttu-id="a83b6-157">Ricevute = Il conteggio delle fatture elettroniche importate in Finance e Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="a83b6-157">Received = The count of imported electronic invoices into Finance and Supply Chain Management.</span></span>

## <a name="functions"></a><span data-ttu-id="a83b6-158">Funzioni</span><span class="sxs-lookup"><span data-stu-id="a83b6-158">Functions</span></span>
### <a name="purchase"></a><span data-ttu-id="a83b6-159">Acquisti</span><span class="sxs-lookup"><span data-stu-id="a83b6-159">Purchase</span></span>

<span data-ttu-id="a83b6-160">Nella scheda **Utilizzo mensile (esportazione)**, selezionare **Acquisto** per registrare manualmente l'importo degli invii acquisiti.</span><span class="sxs-lookup"><span data-stu-id="a83b6-160">On the **Usage per month (export)** tab, select **Purchase** to manually register the amount of acquired submissions.</span></span>

<span data-ttu-id="a83b6-161">Per una data specifica, selezionare **Nuovo** e immettere il numero di **pacchetti** acquisiti in quella data.</span><span class="sxs-lookup"><span data-stu-id="a83b6-161">For a given date, select **New** and enter the number of **Packages** acquired for on that date.</span></span>

<span data-ttu-id="a83b6-162">La **quantità** viene calcolata nel seguente modo:</span><span class="sxs-lookup"><span data-stu-id="a83b6-162">The **Quantity** is calculated as:</span></span>

<span data-ttu-id="a83b6-163">Quantità = Pacchetti \* 1.000</span><span class="sxs-lookup"><span data-stu-id="a83b6-163">Quantity = Packages \* 1.000</span></span>

<span data-ttu-id="a83b6-164">La **quantità** calcolata si riflette in **Acquistato** dall'indicatore **Utilizzo mensile (esportazione)**.</span><span class="sxs-lookup"><span data-stu-id="a83b6-164">The calculated **Quantity** reflects in the **Purchased** from the indicator **Usage per month (export)**.</span></span>

### <a name="update"></a><span data-ttu-id="a83b6-165">Aggiornamento</span><span class="sxs-lookup"><span data-stu-id="a83b6-165">Update</span></span>

<span data-ttu-id="a83b6-166">Nel riquadro delle azioni, selezionare **Aggiorna** per aggiornare il calcolo e i dati mostrati nella pagina e nel grafico.</span><span class="sxs-lookup"><span data-stu-id="a83b6-166">On the Action Pane, select **Update** to refresh the calculation and update the data shown on the page and in the chart.</span></span>

### <a name="reset-history-data"></a><span data-ttu-id="a83b6-167">Reimposta dati dello storico</span><span class="sxs-lookup"><span data-stu-id="a83b6-167">Reset history data</span></span>

<span data-ttu-id="a83b6-168">Nel riquadro delle azioni, selezionare **Ripristina dati cronologia** per aggiornare il database da cui vengono calcolati gli indicatori.</span><span class="sxs-lookup"><span data-stu-id="a83b6-168">On the Action Pane, select **Reset history data** to refresh the database from where the indicators are calculated.</span></span>




> [!NOTE]
> <span data-ttu-id="a83b6-169">Il dashboard **Gestione dell'utilizzo** non mostra gli importi monetari.</span><span class="sxs-lookup"><span data-stu-id="a83b6-169">The **Usage management** dashboard doesn't show monetary amounts.</span></span> <span data-ttu-id="a83b6-170">Al contrario, mostra solo il volume degli invii conteggiati e dei documenti importati.</span><span class="sxs-lookup"><span data-stu-id="a83b6-170">Instead, it shows only the volume of counted submissions and imported documents.</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
