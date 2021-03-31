---
title: Esempio di integrazione di stampante fiscale per l'Italia
description: In questo argomento viene fornita una panoramica dell'esempio di integrazione fiscale per l'Italia.
author: josaw
manager: annbe
ms.date: 10/08/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailFunctionalityProfile, RetailFormLayout, RetailParameters
audience: Application User
ms.reviewer: josaw
ms.search.region: Italy
ms.search.industry: Retail
ms.author: sepism
ms.search.validFrom: 2018-11-1
ms.dyn365.ops.version: 8.1.1
ms.openlocfilehash: 478c9f9b0dc85229926537137c30892c8057bbb2
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5225695"
---
# <a name="fiscal-printer-integration-sample-for-italy"></a><span data-ttu-id="76faa-103">Esempio di integrazione di stampante fiscale per l'Italia</span><span class="sxs-lookup"><span data-stu-id="76faa-103">Fiscal printer integration sample for Italy</span></span>

[!include [banner](../includes/banner.md)]

## <a name="introduction"></a><span data-ttu-id="76faa-104">Introduzione</span><span class="sxs-lookup"><span data-stu-id="76faa-104">Introduction</span></span>

<span data-ttu-id="76faa-105">La funzionalità di Commerce per l'Italia include un'integrazione di esempio del POS con una stampante fiscale.</span><span class="sxs-lookup"><span data-stu-id="76faa-105">The Commerce functionality for Italy includes a sample integration of the point of sale (POS) with a fiscal printer.</span></span> <span data-ttu-id="76faa-106">L'esempio estende la [funzionalità di integrazione fiscale](fiscal-integration-for-retail-channel.md) di modo che sia utilizzabile con le stampanti [Epson FP-90III Series](https://www.epson.it/products/sd/pos-printer/epson-fp-90iii-series) di Epson e abilita la comunicazione con una stampante fiscale in modalità server Web via il servizio Web EpsonFPMate utilizzando l'API Fiscal ePOS-Print.</span><span class="sxs-lookup"><span data-stu-id="76faa-106">The sample extends the [fiscal integration functionality](fiscal-integration-for-retail-channel.md) so that it works with [Epson FP-90III Series](https://www.epson.it/products/sd/pos-printer/epson-fp-90iii-series) printers from Epson, and it enables communication with a fiscal printer in the web server mode via the EpsonFPMate web-service using Fiscal ePOS-Print API.</span></span> <span data-ttu-id="76faa-107">L'esempio supporta soltanto la modalità Registratore Telematico (RT).</span><span class="sxs-lookup"><span data-stu-id="76faa-107">The sample supports the Registratore Telematico (RT) mode only.</span></span> <span data-ttu-id="76faa-108">L'esempio viene fornito sotto forma di codice sorgente e fa parte del kit SDK.</span><span class="sxs-lookup"><span data-stu-id="76faa-108">The sample is provided in the form of source code and is part of the Retail software development kit (SDK).</span></span>

<span data-ttu-id="76faa-109">Microsoft non rilascia hardware, software o documentazione di Epson.</span><span class="sxs-lookup"><span data-stu-id="76faa-109">Microsoft doesn't release any hardware, software, or documentation from Epson.</span></span> <span data-ttu-id="76faa-110">Per informazioni su come ottenere la stampante fiscale e utilizzarla, contattare [Epson Italia S.p.A](https://www.epson.it).</span><span class="sxs-lookup"><span data-stu-id="76faa-110">For information about how to get the fiscal printer and operate it, contact [Epson Italia S.p.A](https://www.epson.it).</span></span>

## <a name="scenarios"></a><span data-ttu-id="76faa-111">Scenari</span><span class="sxs-lookup"><span data-stu-id="76faa-111">Scenarios</span></span>

<span data-ttu-id="76faa-112">Gli scenari seguenti sono coperti dall'esempio di integrazione di stampante fiscale per l'Italia:</span><span class="sxs-lookup"><span data-stu-id="76faa-112">The following scenarios are covered by the fiscal printer integration sample for Italy:</span></span>

- <span data-ttu-id="76faa-113">Scenari di vendita:</span><span class="sxs-lookup"><span data-stu-id="76faa-113">Sales scenarios:</span></span>

    - <span data-ttu-id="76faa-114">Stampare una ricevuta fiscale per le vendite cash and carry e i resi.</span><span class="sxs-lookup"><span data-stu-id="76faa-114">Print a fiscal receipt for cash-and-carry sales and returns.</span></span>
    - <span data-ttu-id="76faa-115">Ottenure una risposta dalla stampante fiscale e archiviarla nel database del canale.</span><span class="sxs-lookup"><span data-stu-id="76faa-115">Capture a response from the fiscal printer, and store it in the channel database.</span></span>
    - <span data-ttu-id="76faa-116">Imposte:</span><span class="sxs-lookup"><span data-stu-id="76faa-116">Taxes:</span></span>

        - <span data-ttu-id="76faa-117">Eseguire il mapping ai codici imposta (reparti) della stampante fiscale.</span><span class="sxs-lookup"><span data-stu-id="76faa-117">Map to the fiscal printer's tax codes (departments).</span></span>
        - <span data-ttu-id="76faa-118">Trasferire i dati fiscali mappati alla stampante fiscale.</span><span class="sxs-lookup"><span data-stu-id="76faa-118">Transfer mapped tax data to the fiscal printer.</span></span>
        - <span data-ttu-id="76faa-119">Stampare le imposte su una ricevuta fiscale.</span><span class="sxs-lookup"><span data-stu-id="76faa-119">Print taxes on a fiscal receipt.</span></span>

    - <span data-ttu-id="76faa-120">Pagamenti:</span><span class="sxs-lookup"><span data-stu-id="76faa-120">Payments:</span></span>

        - <span data-ttu-id="76faa-121">Eseguire il mapping ai metodi di pagamento della stampante fiscale.</span><span class="sxs-lookup"><span data-stu-id="76faa-121">Map to the fiscal printer's methods of payment.</span></span>
        - <span data-ttu-id="76faa-122">Stampare i pagamenti su una ricevuta fiscale.</span><span class="sxs-lookup"><span data-stu-id="76faa-122">Print payments on a fiscal receipt.</span></span>
        - <span data-ttu-id="76faa-123">Stampare le informazioni sulle modifiche.</span><span class="sxs-lookup"><span data-stu-id="76faa-123">Print change information.</span></span>

    - <span data-ttu-id="76faa-124">Stampare gli sconti riga</span><span class="sxs-lookup"><span data-stu-id="76faa-124">Print line discounts.</span></span>
    - <span data-ttu-id="76faa-125">Gift card:</span><span class="sxs-lookup"><span data-stu-id="76faa-125">Gift cards:</span></span>

        - <span data-ttu-id="76faa-126">Escludere una riga gift card emessa/ricaricata da una ricevuta fiscale per una vendita.</span><span class="sxs-lookup"><span data-stu-id="76faa-126">Exclude an issued/re-charged gift card line from a fiscal receipt for a sale.</span></span>
        - <span data-ttu-id="76faa-127">Stampare un pagamento che utilizza una gift card come metodo di pagamento normale.</span><span class="sxs-lookup"><span data-stu-id="76faa-127">Print a payment that uses a gift card as a regular method of payment.</span></span>

    - <span data-ttu-id="76faa-128">Stampare ricevute fiscali per operazioni di ordini cliente:</span><span class="sxs-lookup"><span data-stu-id="76faa-128">Print fiscal receipts for customer order operations:</span></span>

        - <span data-ttu-id="76faa-129">Una ricevuta fiscale non viene stampata per un deposito ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="76faa-129">A fiscal receipt isn't printed for a customer order deposit.</span></span>
        - <span data-ttu-id="76faa-130">Stampare una ricevuta fiscale per righe di esecuzione di un ordine cliente ibrido.</span><span class="sxs-lookup"><span data-stu-id="76faa-130">Print a fiscal receipt for carry-out lines of a hybrid customer order.</span></span>
        - <span data-ttu-id="76faa-131">Stampare una ricevuta fiscale per l'operazione di prelievo per un ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="76faa-131">Print a fiscal receipt for the pickup operation for a customer order.</span></span>
        - <span data-ttu-id="76faa-132">Stampare una ricevuta fiscale per un ordine di reso.</span><span class="sxs-lookup"><span data-stu-id="76faa-132">Print a fiscal receipt for a return order.</span></span>

    - <span data-ttu-id="76faa-133">Stampare un codice a barre per il numero di ricevuta su una ricevuta fiscale.</span><span class="sxs-lookup"><span data-stu-id="76faa-133">Print a bar code for the receipt number on a fiscal receipt.</span></span>
    - <span data-ttu-id="76faa-134">Stampare le [informazioni del cliente](emea-ita-customer-information.md) specificate per una transazione di vendita in una ricevuta fiscale.</span><span class="sxs-lookup"><span data-stu-id="76faa-134">Print the [customer information](emea-ita-customer-information.md) that is specified for a sales transaction on a fiscal receipt.</span></span> <span data-ttu-id="76faa-135">Un esempio di queste informazioni è il codice fiscale del cliente.</span><span class="sxs-lookup"><span data-stu-id="76faa-135">An example of this information is the customer's lottery code.</span></span> 

- <span data-ttu-id="76faa-136">Rendiconti di riepilogo giornalieri (report X e Z fiscali).</span><span class="sxs-lookup"><span data-stu-id="76faa-136">End of day statements (fiscal X and fiscal Z reports).</span></span>
- <span data-ttu-id="76faa-137">Gestione degli errori, ad esempio le seguenti opzioni:</span><span class="sxs-lookup"><span data-stu-id="76faa-137">Error handling, such as the following options:</span></span>

    - <span data-ttu-id="76faa-138">Se possibile, ripetere la registrazione fiscale nel caso la stampante fiscale non sia collegata, pronta o non risponda o se la carta risulta mancante o inceppata.</span><span class="sxs-lookup"><span data-stu-id="76faa-138">Retry fiscal registration if a retry is possible, such as if the fiscal printer isn't connected, isn't ready or isn't responding, the printer is out of paper, or there is a paper jam.</span></span>
    - <span data-ttu-id="76faa-139">Posticipare la registrazione fiscale.</span><span class="sxs-lookup"><span data-stu-id="76faa-139">Postpone fiscal registration.</span></span>
    - <span data-ttu-id="76faa-140">Ignorare la registrazione fiscale, o contrassegnare la transazione come registrata, e includere i codici informativi per acquisire il motivo dell'errore e ulteriori informazioni.</span><span class="sxs-lookup"><span data-stu-id="76faa-140">Skip fiscal registration, or mark the transaction as registered, and include info codes to capture the reason for the failure and additional information.</span></span>
    - <span data-ttu-id="76faa-141">Verificare la disponibilità della stampante fiscale prima dell'apertura di una nuova transazione di vendita o della finalizzazione di una transazione di vendita.</span><span class="sxs-lookup"><span data-stu-id="76faa-141">Check the availability of the fiscal printer before a new sales transaction is opened or a sales transaction is finalized.</span></span>

### <a name="default-data-mapping"></a><span data-ttu-id="76faa-142">Mapping dei dati predefiniti</span><span class="sxs-lookup"><span data-stu-id="76faa-142">Default data mapping</span></span>

<span data-ttu-id="76faa-143">Il mapping dei dati predefiniti seguente è incluso nella configurazione di fornitore di documenti fiscali fornita nell'esempio di integrazione fiscale:</span><span class="sxs-lookup"><span data-stu-id="76faa-143">The following default data mapping is included in the fiscal document provider configuration that is provided as part of the fiscal integration sample:</span></span>

- <span data-ttu-id="76faa-144">Mapping delle aliquote IVA:</span><span class="sxs-lookup"><span data-stu-id="76faa-144">Value-added tax (VAT) rates mapping:</span></span>

    <span data-ttu-id="76faa-145">*1 : 22.00 ; 2 : 10.00 ; 3 : 4.00 ; 4 : 0.00*</span><span class="sxs-lookup"><span data-stu-id="76faa-145">*1 : 22.00 ; 2 : 10.00 ; 3 : 4.00 ; 4 : 0.00*</span></span>

- <span data-ttu-id="76faa-146">Mapping del tipo di metodo di pagamento:</span><span class="sxs-lookup"><span data-stu-id="76faa-146">Tender type mapping:</span></span>

    <span data-ttu-id="76faa-147">*1 : 0 ; 2 : 1 ; 3 : 2 ; 4 : 2 ; 5 : 0 ; 6 : 0 ; 7 : 0 ; 8 : 2 ; 9 : 0 ; 10 : 2 ; 11 : 1*</span><span class="sxs-lookup"><span data-stu-id="76faa-147">*1 : 0 ; 2 : 1 ; 3 : 2 ; 4 : 2 ; 5 : 0 ; 6 : 0 ; 7 : 0 ; 8 : 2 ; 9 : 0 ; 10 : 2 ; 11 : 1*</span></span>

### <a name="gift-cards"></a><span data-ttu-id="76faa-148">Gift card</span><span class="sxs-lookup"><span data-stu-id="76faa-148">Gift cards</span></span>

<span data-ttu-id="76faa-149">L'esempio di integrazione della stampante fiscale implementa le seguenti regole relative alle gift card:</span><span class="sxs-lookup"><span data-stu-id="76faa-149">The fiscal printer integration sample implements the following rules that are related to gift cards:</span></span>

- <span data-ttu-id="76faa-150">Escludere le righe di vendita correlate alle operazioni *Emetti gift card* e *Aggiungi a gift card* della ricevuta fiscale.</span><span class="sxs-lookup"><span data-stu-id="76faa-150">Exclude sales lines that are related to the *Issue gift card* and *Add to gift card* operations from the fiscal receipt.</span></span>
- <span data-ttu-id="76faa-151">Non stampare una ricevuta fiscale se comporta soltanto righe gift card.</span><span class="sxs-lookup"><span data-stu-id="76faa-151">Don't print a fiscal receipt if it consists only of gift card lines.</span></span>
- <span data-ttu-id="76faa-152">Dedurre l'importo totale delle gift card emesse o ricaricate in una transazione dalle righe di pagamento della ricevuta fiscale.</span><span class="sxs-lookup"><span data-stu-id="76faa-152">Deduct the total amount of gift cards that are issued or re-charged in a transaction from payment lines of the fiscal receipt.</span></span>
- <span data-ttu-id="76faa-153">Salvare le rettifiche calcolate delle righe di pagamento nel database del canale con un riferimento a una transazione fiscale corrispondente.</span><span class="sxs-lookup"><span data-stu-id="76faa-153">Save calculated adjustments of payment lines in the channel database with a reference to a corresponding fiscal transaction.</span></span>
- <span data-ttu-id="76faa-154">Il pagamento tramite gift card è considerato un pagamento normale.</span><span class="sxs-lookup"><span data-stu-id="76faa-154">Payment by gift card is considered a regular payment.</span></span>

### <a name="customer-deposits-and-customer-order-deposits"></a><span data-ttu-id="76faa-155">Depositi cliente e depositi ordine cliente</span><span class="sxs-lookup"><span data-stu-id="76faa-155">Customer deposits and customer order deposits</span></span>

<span data-ttu-id="76faa-156">L'esempio di integrazione della stampante fiscale implementa le seguenti regole relative a depositi cliente e a depositi ordine cliente:</span><span class="sxs-lookup"><span data-stu-id="76faa-156">The fiscal printer integration sample implements the following rules that are related to customer deposits and customer order deposits:</span></span>

- <span data-ttu-id="76faa-157">Non stampare una ricevuta fiscale se una transazione è un deposito cliente.</span><span class="sxs-lookup"><span data-stu-id="76faa-157">Don't print a fiscal receipt if a transaction is a customer deposit.</span></span>
- <span data-ttu-id="76faa-158">Non stampare una ricevuta fiscale se una transazione contiene solo un deposito ordine cliente o un rimborso di deposito ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="76faa-158">Don't print a fiscal receipt if a transaction contains only a customer order deposit or a customer order deposit refund.</span></span>
- <span data-ttu-id="76faa-159">Stampare l'importo del deposito pagato in precedenza su una ricevuta fiscale per un'operazione di prelievo ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="76faa-159">Print the amount of the previously paid deposit on a fiscal receipt for a customer order pickup operation.</span></span>
- <span data-ttu-id="76faa-160">Dedurre l'importo del deposito ordine cliente dalle righe di pagamento quando si crea un ordine cliente ibrido.</span><span class="sxs-lookup"><span data-stu-id="76faa-160">Deduct the customer order deposit amount from payment lines when a hybrid customer order is created.</span></span>
- <span data-ttu-id="76faa-161">Salvare le rettifiche calcolate delle righe di pagamento nel database del canale con un riferimento a una transazione fiscale per un ordine cliente ibrido.</span><span class="sxs-lookup"><span data-stu-id="76faa-161">Save calculated adjustments of payment lines in the channel database with a reference to a fiscal transaction for a hybrid customer order.</span></span>

### <a name="limitations-of-the-sample"></a><span data-ttu-id="76faa-162">Limitazioni dell'esempio</span><span class="sxs-lookup"><span data-stu-id="76faa-162">Limitations of the sample</span></span>

- <span data-ttu-id="76faa-163">La stampante fiscale supporta solo gli scenari in cui l'IVA è inclusa nel prezzo.</span><span class="sxs-lookup"><span data-stu-id="76faa-163">The fiscal printer supports only scenarios where sales tax is included in the price.</span></span> <span data-ttu-id="76faa-164">Di conseguenza, l'opzione **Prezzi IVA inclusa** deve essere impostata su **Sì** per i punti vendita e i clienti.</span><span class="sxs-lookup"><span data-stu-id="76faa-164">Therefore, the **Price include sales tax** option must be set to **Yes** for both stores and customers.</span></span>
- <span data-ttu-id="76faa-165">I report giornalieri (X e Z fiscali) vengono stampati utilizzando il formato incorporato nel firmware della stampante fiscale.</span><span class="sxs-lookup"><span data-stu-id="76faa-165">Daily reports (fiscal X and fiscal Z) are printed by using the format that is embedded in the fiscal printer's firmware.</span></span>
- <span data-ttu-id="76faa-166">Le transazioni miste non sono supportate dalla stampante fiscale.</span><span class="sxs-lookup"><span data-stu-id="76faa-166">The fiscal printer doesn't support mixed transactions.</span></span> <span data-ttu-id="76faa-167">L'opzione **Impedisci di combinare vendite e resi in una ricevuta** deve essere impostata su **Sì** nei profili funzionalità POS.</span><span class="sxs-lookup"><span data-stu-id="76faa-167">The **Prohibit mixing sales and returns in one receipt** option should be set to **Yes** in POS functionality profiles.</span></span>
- <span data-ttu-id="76faa-168">L'esempio supporta l'integrazione solo con una stampante fiscale che funziona in modalità RT (Registrazione Telematico).</span><span class="sxs-lookup"><span data-stu-id="76faa-168">The sample supports integration only with a fiscal printer that is working in the RT (Registratore Telematico) mode.</span></span>

## <a name="set-up-commerce-for-italy"></a><span data-ttu-id="76faa-169">Impostazione di Commerce per l'Italia</span><span class="sxs-lookup"><span data-stu-id="76faa-169">Set up Commerce for Italy</span></span>

### <a name="configure-fiscal-integration"></a><span data-ttu-id="76faa-170">Configurare l'integrazione fiscale</span><span class="sxs-lookup"><span data-stu-id="76faa-170">Configure fiscal integration</span></span>

<span data-ttu-id="76faa-171">Completare la procedura di configurazione dell'integrazione fiscale come descritto in [Impostare l'integrazione fiscale per canali di Commerce](setting-up-fiscal-integration-for-retail-channel.md):</span><span class="sxs-lookup"><span data-stu-id="76faa-171">Complete the fiscal integration setup steps as described in [Set up the fiscal integration for Commerce channels](setting-up-fiscal-integration-for-retail-channel.md):</span></span>

- <span data-ttu-id="76faa-172">[Configurare un processo di registrazione fiscale](setting-up-fiscal-integration-for-retail-channel.md#set-up-a-fiscal-registration-process).</span><span class="sxs-lookup"><span data-stu-id="76faa-172">[Set up a fiscal registration process](setting-up-fiscal-integration-for-retail-channel.md#set-up-a-fiscal-registration-process).</span></span> <span data-ttu-id="76faa-173">Da notare anche le impostazioni per il processo di registrazione fiscale che sono [specifiche dell'esempio di integrazione della stampante fiscale](#set-up-the-registration-process).</span><span class="sxs-lookup"><span data-stu-id="76faa-173">Note also the settings for the fiscal registration process that are [specific to this fiscal printer integration sample](#set-up-the-registration-process).</span></span>
- <span data-ttu-id="76faa-174">[Impostare testi fiscali per sconti](setting-up-fiscal-integration-for-retail-channel.md#set-up-fiscal-texts-for-discounts).</span><span class="sxs-lookup"><span data-stu-id="76faa-174">[Set up fiscal texts for discounts](setting-up-fiscal-integration-for-retail-channel.md#set-up-fiscal-texts-for-discounts).</span></span>
- <span data-ttu-id="76faa-175">[Configurare le impostazioni di gestione degli errori](setting-up-fiscal-integration-for-retail-channel.md#set-error-handling-settings).</span><span class="sxs-lookup"><span data-stu-id="76faa-175">[Set error handling settings](setting-up-fiscal-integration-for-retail-channel.md#set-error-handling-settings).</span></span>
- <span data-ttu-id="76faa-176">[Configurare report X/Z fiscali dal POS](setting-up-fiscal-integration-for-retail-channel.md#set-up-fiscal-xz-reports-from-the-pos).</span><span class="sxs-lookup"><span data-stu-id="76faa-176">[Set up fiscal X/Z reports from the POS](setting-up-fiscal-integration-for-retail-channel.md#set-up-fiscal-xz-reports-from-the-pos).</span></span>
- <span data-ttu-id="76faa-177">[Abilitare l'esecuzione manuale della registrazione fiscale posticipata](setting-up-fiscal-integration-for-retail-channel.md#enable-manual-execution-of-postponed-fiscal-registration).</span><span class="sxs-lookup"><span data-stu-id="76faa-177">[Enable manual execution of postponed fiscal registration](setting-up-fiscal-integration-for-retail-channel.md#enable-manual-execution-of-postponed-fiscal-registration).</span></span>
- [<span data-ttu-id="76faa-178">Impostare la funzionalità per la gestione delle informazioni del cliente nel POS</span><span class="sxs-lookup"><span data-stu-id="76faa-178">Set up the functionality for management of customer information in POS</span></span>](emea-ita-customer-information.md#setup)

### <a name="enable-extensions"></a><span data-ttu-id="76faa-179">Abilitare le estensioni</span><span class="sxs-lookup"><span data-stu-id="76faa-179">Enable extensions</span></span>

#### <a name="commerce-runtime-extension-components"></a><span data-ttu-id="76faa-180">Componenti dell'estensione di Commerce Runtime</span><span class="sxs-lookup"><span data-stu-id="76faa-180">Commerce runtime extension components</span></span>

<span data-ttu-id="76faa-181">I componenti dell'estensione di Commerce Runtime sono inclusi in Retail SDK.</span><span class="sxs-lookup"><span data-stu-id="76faa-181">The Commerce runtime extension components are included in the Retail SDK.</span></span> <span data-ttu-id="76faa-182">Per completare le seguenti procedure, aprire la soluzione CRT, **CommerceRuntimeSamples.sln**, in **RetailSdk\\SampleExtensions\\CommerceRuntime**.</span><span class="sxs-lookup"><span data-stu-id="76faa-182">To complete the following procedures, open the CRT solution, **CommerceRuntimeSamples.sln**, under **RetailSdk\\SampleExtensions\\CommerceRuntime**.</span></span>

1. <span data-ttu-id="76faa-183">Individuare il progetto **Runtime.Extensions.DocumentProvider.EpsonFP90IIISample** e compilarlo.</span><span class="sxs-lookup"><span data-stu-id="76faa-183">Find the **Runtime.Extensions.DocumentProvider.EpsonFP90IIISample** project, and build it.</span></span>
1. <span data-ttu-id="76faa-184">Nella cartella **Extensions.DocumentProvider.EpsonFP90IIISample\\bin\\Debug**, trovare il file assembly **Contoso.Commerce.Runtime.DocumentProvider.EpsonFP90IIISample.dll**.</span><span class="sxs-lookup"><span data-stu-id="76faa-184">In the **Extensions.DocumentProvider.EpsonFP90IIISample\\bin\\Debug** folder, find the **Contoso.Commerce.Runtime.DocumentProvider.EpsonFP90IIISample.dll** assembly file.</span></span>
1. <span data-ttu-id="76faa-185">Copiare il file assembly alla cartella dell'estensione CRT:</span><span class="sxs-lookup"><span data-stu-id="76faa-185">Copy the assembly file to the CRT extensions folder:</span></span>

    - <span data-ttu-id="76faa-186">**Commerce Scale Unit**: copiare l'assembly nella cartella **\\bin\\ext** nella posizione del sito di Commerce Scale Unit Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="76faa-186">**Commerce Scale Unit:** Copy the assembly to the **\\bin\\ext** folder under the Microsoft Internet Information Services (IIS) Commerce Scale Unit site location.</span></span>
    - <span data-ttu-id="76faa-187">**CRT locale su POS moderno**: copiare l'assembly nella cartella **\\ext** nella posizione del broker client CRT locale.</span><span class="sxs-lookup"><span data-stu-id="76faa-187">**Local CRT on Modern POS:** Copy the assembly to the **\\ext** folder under the local CRT client broker location.</span></span>

1. <span data-ttu-id="76faa-188">Individuare il file di configurazione di estensioni per il CRT:</span><span class="sxs-lookup"><span data-stu-id="76faa-188">Find the extensions configuration file for CRT:</span></span>

    - <span data-ttu-id="76faa-189">**Commerce Scale Unit**: il file si chiama **commerceruntime.ext.config** e si trova nella cartella bin\\ext nella posizione del sito di Commerce Scale Unit IIS.</span><span class="sxs-lookup"><span data-stu-id="76faa-189">**Commerce Scale Uni:** The file is named **commerceruntime.ext.config**, and it's in the bin\\ext folder under the IIS Commerce Scale Uni site location.</span></span>
    - <span data-ttu-id="76faa-190">**CRT locale sul POS moderno:** il file si chiama **CommerceRuntime.MPOSOffline.Ext.config** e si trova nella posizione del broker client CRT locale.</span><span class="sxs-lookup"><span data-stu-id="76faa-190">**Local CRT on Modern POS:** The file is named **CommerceRuntime.MPOSOffline.Ext.config**, and it's under the local CRT client broker location.</span></span>

1. <span data-ttu-id="76faa-191">Registrare la modifica CRT nel file di configurazione di estensioni.</span><span class="sxs-lookup"><span data-stu-id="76faa-191">Register the CRT change in the extensions configuration file.</span></span> <span data-ttu-id="76faa-192">Aggiungere **source="assembly" value="Contoso.Commerce.Runtime.DocumentProvider.EpsonFP90IIISample"**.</span><span class="sxs-lookup"><span data-stu-id="76faa-192">Add **source="assembly" value="Contoso.Commerce.Runtime.DocumentProvider.EpsonFP90IIISample"**.</span></span>
1. <span data-ttu-id="76faa-193">Riavviare Commerce Scale Unit:</span><span class="sxs-lookup"><span data-stu-id="76faa-193">Restart the Commerce Scale Unit:</span></span>

    - <span data-ttu-id="76faa-194">**Commerce Scale Unit:** riavviare il sito Commerce Scale Unit da IIS Manager.</span><span class="sxs-lookup"><span data-stu-id="76faa-194">**Commerce Scale Uni:** Restart the Commerce Scale Uni site from IIS Manager.</span></span>
    - <span data-ttu-id="76faa-195">**Broker client**: terminare il processo **dllhost.exe** in Gestione attività quindi riavviare il POS moderno.</span><span class="sxs-lookup"><span data-stu-id="76faa-195">**Client broker:** End the **dllhost.exe** process in Task Manager, and then restart Modern POS.</span></span>

#### <a name="hardware-station-extension-components"></a><span data-ttu-id="76faa-196">Componenti dell'estensione stazione hardware</span><span class="sxs-lookup"><span data-stu-id="76faa-196">Hardware station extension components</span></span>

<span data-ttu-id="76faa-197">I componenti dell'estensione stazione hardware sono inclusi in Retail SDK.</span><span class="sxs-lookup"><span data-stu-id="76faa-197">The Hardware station extension components are included in the Retail SDK.</span></span> <span data-ttu-id="76faa-198">Per completare le seguenti procedure, aprire la soluzione Stazione hardware, **HardwareStationSamples.sln**, in **RetailSdk\\SampleExtensions\\HardwareStation**.</span><span class="sxs-lookup"><span data-stu-id="76faa-198">To complete the following procedures, open the Hardware Station solution, **HardwareStationSamples.sln**, under **RetailSdk\\SampleExtensions\\HardwareStation**.</span></span>

1. <span data-ttu-id="76faa-199">Individuare il progetto **HardwareStation.Extensions.EpsonFP90IIIFiscalDeviceSample** e compilarlo.</span><span class="sxs-lookup"><span data-stu-id="76faa-199">Find the **HardwareStation.Extensions.EpsonFP90IIIFiscalDeviceSample** project, and build it.</span></span>
2. <span data-ttu-id="76faa-200">Nella cartella **Extensions.EpsonFP90IIIFiscalDeviceSample\\bin\\Debug**, trovare il file assembly **Contoso.Commerce.HardwareStation.EpsonFP90IIIFiscalDeviceSample.dll**.</span><span class="sxs-lookup"><span data-stu-id="76faa-200">In the **Extensions.EpsonFP90IIIFiscalDeviceSample\\bin\\Debug** folder, find the **Contoso.Commerce.HardwareStation.EpsonFP90IIIFiscalDeviceSample.dll** assembly file.</span></span>
3. <span data-ttu-id="76faa-201">Copiare i file in un computer stazione hardware distribuito:</span><span class="sxs-lookup"><span data-stu-id="76faa-201">Copy the files to a deployed Hardware station machine:</span></span>

    - <span data-ttu-id="76faa-202">**Stazione hardware remota**: copiare i file nella cartella **bin** nella posizione del sito stazione hardware IIS.</span><span class="sxs-lookup"><span data-stu-id="76faa-202">**Remote Hardware station:** Copy the files to the **bin** folder under the IIS Hardware station site location.</span></span>
    - <span data-ttu-id="76faa-203">**Stazione hardware locale**: copiare i file nella posizione del broker client POS moderno.</span><span class="sxs-lookup"><span data-stu-id="76faa-203">**Local Hardware station:** Copy the files to the Modern POS client broker location.</span></span>

4. <span data-ttu-id="76faa-204">Individuare il file di configurazione per le estensioni della stazione hardware.</span><span class="sxs-lookup"><span data-stu-id="76faa-204">Find the configuration file for the Hardware station's extensions.</span></span> <span data-ttu-id="76faa-205">Il file si chiama **HardwareStation.Extension.config**:</span><span class="sxs-lookup"><span data-stu-id="76faa-205">The file is named **HardwareStation.Extension.config**:</span></span>

    - <span data-ttu-id="76faa-206">**Stazione hardware remota**: il file si trova sotto la posizione del sito della stazione hardware IIS.</span><span class="sxs-lookup"><span data-stu-id="76faa-206">**Remote Hardware station:** The file is located under the IIS Hardware station site location.</span></span>
    - <span data-ttu-id="76faa-207">**Stazione hardware locale**: il file si trova nella posizione del broker client POS moderno.</span><span class="sxs-lookup"><span data-stu-id="76faa-207">**Local Hardware station:** The file is located under the Modern POS client broker location.</span></span>
    
5. <span data-ttu-id="76faa-208">Aggiungere la sezione seguente alla sezione di **composizione** del file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="76faa-208">Add the following section to the **composition** section of the config file.</span></span>

    ``` xml
    <add source="assembly" value="Contoso.Commerce.HardwareStation.Extension.EpsonFP90IIIFiscalDeviceSample" />
    ```

6. <span data-ttu-id="76faa-209">Riavviare il servizio della stazione hardware:</span><span class="sxs-lookup"><span data-stu-id="76faa-209">Restart the Hardware station service:</span></span>

    - <span data-ttu-id="76faa-210">**Stazione hardware remota**: Riavviare il sito della stazione hardware da Gestione IIS.</span><span class="sxs-lookup"><span data-stu-id="76faa-210">**Remote Hardware station:** Restart the Hardware station site from IIS Manager.</span></span>
    - <span data-ttu-id="76faa-211">**Stazione hardware locale**: terminare il processo **dllhost.exe** in Gestione attività quindi riavviare il POS moderno.</span><span class="sxs-lookup"><span data-stu-id="76faa-211">**Local Hardware station:** End the **dllhost.exe** process in Task Manager, and then restart Modern POS.</span></span>

### <a name="set-up-the-registration-process"></a><span data-ttu-id="76faa-212">Impostare il processo di registrazione</span><span class="sxs-lookup"><span data-stu-id="76faa-212">Set up the registration process</span></span>

<span data-ttu-id="76faa-213">Per abilitare il processo di registrazione, seguire questi passaggi per configurare Headquarters:</span><span class="sxs-lookup"><span data-stu-id="76faa-213">To enable the registration process, follow these steps to set up Headquarters.</span></span> <span data-ttu-id="76faa-214">Per ulteriori informazioni, vedere [Configurare un processo di registrazione fiscale](setting-up-fiscal-integration-for-retail-channel.md#set-up-a-fiscal-registration-process).</span><span class="sxs-lookup"><span data-stu-id="76faa-214">For more details, see [Set up a fiscal registration process](setting-up-fiscal-integration-for-retail-channel.md#set-up-a-fiscal-registration-process).</span></span>

1. <span data-ttu-id="76faa-215">Accedere a **Retail e Commerce \> Impostazione canale \> Integrazione fiscale \> Connettori fiscali**.</span><span class="sxs-lookup"><span data-stu-id="76faa-215">Go to **Retail and Commerce \> Channel Setup \> Fiscal Integration \> Fiscal Connectors**.</span></span> <span data-ttu-id="76faa-216">Importare la configurazione da **RetailSdk\\SampleExtensions\\HardwareStation\\Entension.EpsonFP90IIIFiscalDeviceSample\\Configuration\\ConnectorEpsonFP90IIISample.xml**.</span><span class="sxs-lookup"><span data-stu-id="76faa-216">Import the configuration from **RetailSdk\\SampleExtensions\\HardwareStation\\Entension.EpsonFP90IIIFiscalDeviceSample\\Configuration\\ConnectorEpsonFP90IIISample.xml**.</span></span>
2. <span data-ttu-id="76faa-217">Accedere a **Retail e Commerce \> Impostazione canale \> Integrazione fiscale \> Fornitori di documenti fiscali**.</span><span class="sxs-lookup"><span data-stu-id="76faa-217">Go to **Retail and Commerce \> Channel Setup \> Fiscal Integration \> Fiscal Document providers**.</span></span> <span data-ttu-id="76faa-218">Importare la configurazione da **RetailSdk\\SampleExtensions\\CommerceRuntime\\Entension.DocumentProvider.EpsonFP90IIISample\\Configuration\\DocumentProviderEpsonFP90IIISample.xml**.</span><span class="sxs-lookup"><span data-stu-id="76faa-218">Import the configuration from **RetailSdk\\SampleExtensions\\CommerceRuntime\\Entension.DocumentProvider.EpsonFP90IIISample\\Configuration\\DocumentProviderEpsonFP90IIISample.xml**.</span></span>
3. <span data-ttu-id="76faa-219">Accedere a **Retail e Commerce \> Impostazione canale \> Integrazione fiscale \> Profili tecnici del connettore**.</span><span class="sxs-lookup"><span data-stu-id="76faa-219">Go to **Retail and Commerce \> Channel Setup \> Fiscal Integration \> Connector Technical profiles**.</span></span> <span data-ttu-id="76faa-220">Creare un nuovo profilo e selezionare il connettore caricato nel passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="76faa-220">Create a new profile, and select the loaded connector from the earlier step.</span></span> <span data-ttu-id="76faa-221">Aggiornare le impostazioni di connessione se un aggiornamento è necessario.</span><span class="sxs-lookup"><span data-stu-id="76faa-221">Update the connection settings if an update is required.</span></span>
4. <span data-ttu-id="76faa-222">Accedere a **Retail e Commerce \> Impostazione canale \> Integrazione fiscale \> Profili funzionali del connettore**.</span><span class="sxs-lookup"><span data-stu-id="76faa-222">Go to **Retail and Commerce \> Channel Setup \> Fiscal Integration \> Connector Functional profiles**.</span></span> <span data-ttu-id="76faa-223">Creare un nuovo profilo e selezionare il connettore e il fornitore di documenti caricati nei passaggi precedenti.</span><span class="sxs-lookup"><span data-stu-id="76faa-223">Create a new profile, and select the loaded connector and document provider from the earlier steps.</span></span> <span data-ttu-id="76faa-224">Aggiornare le impostazioni di mapping dei dati se un aggiornamento è necessario.</span><span class="sxs-lookup"><span data-stu-id="76faa-224">Update data mapping settings if an update is required.</span></span>
5. <span data-ttu-id="76faa-225">Accedere a **Retail e Commerce \> Impostazione canale \> Integrazione fiscale \> Gruppo funzionale di connettori**.</span><span class="sxs-lookup"><span data-stu-id="76faa-225">Go to **Retail and Commerce \> Channel Setup \> Fiscal Integration \> Connector Functional group**.</span></span> <span data-ttu-id="76faa-226">Creare un nuovo gruppo e selezionare il profilo funzionale del connettore del passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="76faa-226">Create a new group, and select the connector functional profile from the earlier step.</span></span>
6. <span data-ttu-id="76faa-227">Accedere a **Retail e Commerce \> Impostazione canale \> Integrazione fiscale \> Processo di registrazione**.</span><span class="sxs-lookup"><span data-stu-id="76faa-227">Go to **Retail and Commerce \> Channel Setup \> Fiscal Integration \> Registration process**.</span></span> <span data-ttu-id="76faa-228">Creare un nuovo processo e selezionare il gruppo funzionale di connettori del passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="76faa-228">Create a new process, and select the connector functional group from the earlier step.</span></span>
7. <span data-ttu-id="76faa-229">Passare a **Retail e Commerce \> Impostazione canale \> Impostazione POS \> Profili POS \> Profili funzionalità**.</span><span class="sxs-lookup"><span data-stu-id="76faa-229">Go to **Retail and Commerce \> Channel setup \> POS setup \> POS profiles \> Functionality profiles**.</span></span> <span data-ttu-id="76faa-230">Aprire il profilo funzionalità collegato al punto vendita in cui il processo di registrazione deve essere attivato.</span><span class="sxs-lookup"><span data-stu-id="76faa-230">Open the functionality profile that is linked to the store where the registration process should be activated.</span></span> <span data-ttu-id="76faa-231">Nella scheda Dettaglio **Processo di registrazione fiscale**, selezionare il processo di registrazione creato nel precedentemente.</span><span class="sxs-lookup"><span data-stu-id="76faa-231">On the **Fiscal registration process** FastTab, select the registration process that was created earlier.</span></span>
8. <span data-ttu-id="76faa-232">Andare a **Retail e Commerce \> Impostazione canale \> Impostazioni POS \> Profili POS \> Profili hardware**.</span><span class="sxs-lookup"><span data-stu-id="76faa-232">Go to **Retail and Commerce \> Channel setup \> POS setup \> POS profiles \> Hardware profiles**.</span></span> <span data-ttu-id="76faa-233">Aprire il profilo hardware collegato alla stazione hardware a cui la stampante fiscale sarà collegata.</span><span class="sxs-lookup"><span data-stu-id="76faa-233">Open the hardware profile that is linked to the Hardware station that the fiscal printer will be connected to.</span></span> <span data-ttu-id="76faa-234">Nella scheda Dettaglio **Periferiche fiscali**, selezionare il profilo tecnico del connettore.</span><span class="sxs-lookup"><span data-stu-id="76faa-234">On the **Fiscal peripherals** FastTab, select the connector technical profile.</span></span>
9. <span data-ttu-id="76faa-235">Aprire la programmazione della distribuzione (**Retail e Commerce \> Vendita al dettaglio e commercio IT \> Programmazione della distribuzione**) e selezionare i processi **1070** e **1090** per trasferire i dati al database del canale.</span><span class="sxs-lookup"><span data-stu-id="76faa-235">Open the distribution schedule (**Retail and Commerce \> Retail and Commerce IT \> Distribution schedule**), and select jobs **1070** and **1090** to transfer data to the channel database.</span></span>

### <a name="production-environment"></a><span data-ttu-id="76faa-236">Ambiente di produzione</span><span class="sxs-lookup"><span data-stu-id="76faa-236">Production environment</span></span>

<span data-ttu-id="76faa-237">Attenersi alla procedura seguente per creare pacchetti distribuibili contenenti componenti Commerce e per applicare quei pacchetti a un ambiente di produzione.</span><span class="sxs-lookup"><span data-stu-id="76faa-237">Follow these steps to create deployable packages that contain Commerce components, and to apply those packages in a production environment.</span></span>

1. <span data-ttu-id="76faa-238">Completare la procedura descritta nella sezione [Abilitare le estensioni](#enable-extensions) vista in precedenza in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="76faa-238">Complete the steps that are described in the [Enable extensions](#enable-extensions) section earlier in this topic.</span></span>
2. <span data-ttu-id="76faa-239">Apportare le seguenti modifiche nei file di configurazione dei pacchetti nella cartella **RetailSdk\\Assets** :</span><span class="sxs-lookup"><span data-stu-id="76faa-239">Make the following changes in the package configuration files under the **RetailSdk\\Assets** folder:</span></span>

    - <span data-ttu-id="76faa-240">Nei file di configurazione **CommerceRuntime.MPOSOffline.Ext.config** e **commerceruntime.ext.config**, aggiungere la seguente riga alla sezione **composition**.</span><span class="sxs-lookup"><span data-stu-id="76faa-240">In the **commerceruntime.ext.config** and **CommerceRuntime.MPOSOffline.Ext.config** configuration files, add the following line to the **composition** section.</span></span>

        ``` xml 
        <add source="assembly" value="Contoso.Commerce.Runtime.DocumentProvider.EpsonFP90IIISample" />
        ```

    - <span data-ttu-id="76faa-241">Nel file di configurazione **HardwareStation.Extension.config**, aggiungere la seguente riga alla sezione **composition**.</span><span class="sxs-lookup"><span data-stu-id="76faa-241">In the **HardwareStation.Extension.config** configuration file, add the following line to the **composition** section.</span></span>

        ``` xml 
        <add source="assembly" value="Contoso.Commerce.HardwareStation.Extension.EpsonFP90IIIFiscalDeviceSample" />
        ```

3. <span data-ttu-id="76faa-242">Apportare le seguenti modifiche nel file di configurazione di personalizzazione dei pacchetti **BuildTools\\Customization.settings**:</span><span class="sxs-lookup"><span data-stu-id="76faa-242">Make the following changes in the **BuildTools\\Customization.settings** package customization configuration file:</span></span>

    - <span data-ttu-id="76faa-243">Aggiungere la seguente riga per includere l'estensione CRT nei pacchetti distribuibili.</span><span class="sxs-lookup"><span data-stu-id="76faa-243">Add the following line to include the CRT extension in the deployable packages.</span></span>

        ``` xml 
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.DocumentProvider.EpsonFP90IIISample.dll"/>
        ```

    - <span data-ttu-id="76faa-244">Aggiungere la seguente riga per includere l'estensione stazione hardware nei pacchetti distribuibili.</span><span class="sxs-lookup"><span data-stu-id="76faa-244">Add the following line to include the Hardware station extension in the deployable packages.</span></span>

        ``` xml 
        <ISV_HardwareStation_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.HardwareStation.EpsonFP90IIIFiscalDeviceSample.dll"/>
        ```

4. <span data-ttu-id="76faa-245">Avviare il prompt dei comandi di MSBuild per l'utilità Visual Studio ed eseguire **msbuild** nella cartella Retail SDK per creare pacchetti distribuibili.</span><span class="sxs-lookup"><span data-stu-id="76faa-245">Start the MSBuild Command Prompt for Visual Studio utility, and run **msbuild** under the Retail SDK folder to create deployable packages.</span></span>
5. <span data-ttu-id="76faa-246">Applicare i pacchetti via Microsoft Dynamics Lifecycle Services (LCS) o manualmente.</span><span class="sxs-lookup"><span data-stu-id="76faa-246">Apply the packages via Microsoft Dynamics Lifecycle Services (LCS) or manually.</span></span> <span data-ttu-id="76faa-247">Per ulteriori informazioni, vedere [Creare pacchetti distribuibili](../dev-itpro/retail-sdk/retail-sdk-packaging.md).</span><span class="sxs-lookup"><span data-stu-id="76faa-247">For more information, see [Create deployable packages](../dev-itpro/retail-sdk/retail-sdk-packaging.md).</span></span>

## <a name="design-of-extensions"></a><span data-ttu-id="76faa-248">Progettazione delle estensioni</span><span class="sxs-lookup"><span data-stu-id="76faa-248">Design of extensions</span></span>

### <a name="commerce-runtime-extension-design"></a><span data-ttu-id="76faa-249">Progettazione dell'estensione di Commerce Runtime</span><span class="sxs-lookup"><span data-stu-id="76faa-249">Commerce runtime extension design</span></span>

<span data-ttu-id="76faa-250">Lo scopo dell'estensione (fornitore di documenti) è di generare documenti specifici per la stampante e di gestire le risposte dalla stampante fiscale.</span><span class="sxs-lookup"><span data-stu-id="76faa-250">The purpose of the extension that is a fiscal document provider is to generate printer-specific documents and handle responses from the fiscal printer.</span></span>

<span data-ttu-id="76faa-251">L'estensione di Commerce Runtime è **Runtime.Extensions.DocumentProvider.EpsonFP90IIISample**.</span><span class="sxs-lookup"><span data-stu-id="76faa-251">The Commerce runtime extension is **Runtime.Extensions.DocumentProvider.EpsonFP90IIISample**.</span></span>

<span data-ttu-id="76faa-252">Per ulteriori informazioni sulla progettazione della soluzione di integrazione fiscale, vedere [Processo di registrazione fiscale ed esempi di integrazione fiscale per dispositivi fiscali](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices).</span><span class="sxs-lookup"><span data-stu-id="76faa-252">For more details about the design of the fiscal integration solution, see [Fiscal registration process and fiscal integration samples for fiscal devices](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices).</span></span>

#### <a name="request-handler"></a><span data-ttu-id="76faa-253">Gestore richieste</span><span class="sxs-lookup"><span data-stu-id="76faa-253">Request handler</span></span>
    
<span data-ttu-id="76faa-254">Il gestore richieste **DocumentProviderEpsonFP90III** è il punto di ingresso per la richiesta di generare documenti dalla stampante fiscale.</span><span class="sxs-lookup"><span data-stu-id="76faa-254">The **DocumentProviderEpsonFP90III** request handler is the entry point for the request to generate documents from the fiscal printer.</span></span>

<span data-ttu-id="76faa-255">Il gestore viene ereditato dall'interfaccia **INamedRequestHandler**.</span><span class="sxs-lookup"><span data-stu-id="76faa-255">The handler is inherited from the **INamedRequestHandler** interface.</span></span> <span data-ttu-id="76faa-256">Il metodo **HandlerName** è responsabile della restituzione del nome del gestore.</span><span class="sxs-lookup"><span data-stu-id="76faa-256">The **HandlerName** method is responsible for returning the name of the handler.</span></span> <span data-ttu-id="76faa-257">Il nome del gestore deve corrispondere al nome del fornitore di documenti del connettore specificato in Headquarters.</span><span class="sxs-lookup"><span data-stu-id="76faa-257">The handler name should match the connector document provider name that is specified in Headquarters.</span></span>

<span data-ttu-id="76faa-258">Il connettore supporta le seguenti richieste:</span><span class="sxs-lookup"><span data-stu-id="76faa-258">The connector supports the following requests:</span></span>

- <span data-ttu-id="76faa-259">**GetFiscalDocumentDocumentProviderRequest** - Contiene informazioni su quale documento dovrà essere generato.</span><span class="sxs-lookup"><span data-stu-id="76faa-259">**GetFiscalDocumentDocumentProviderRequest** – This request contains information about what document should be generated.</span></span> <span data-ttu-id="76faa-260">Restituisce un documento specifico della stampante che deve essere registrato nella stampante fiscale.</span><span class="sxs-lookup"><span data-stu-id="76faa-260">It returns a printer-specific document that should be registered in the fiscal printer.</span></span>
- <span data-ttu-id="76faa-261">**GetSupportedRegistrableEventsDocumentProviderRequest** - Restituisce l'elenco degli eventi da sottoscrivere.</span><span class="sxs-lookup"><span data-stu-id="76faa-261">**GetSupportedRegistrableEventsDocumentProviderRequest** – This request returns the list of events to subscribe to.</span></span> <span data-ttu-id="76faa-262">Attualmente, i seguenti eventi sono supportati: vendita, stampa del report X e stampa del report Z.</span><span class="sxs-lookup"><span data-stu-id="76faa-262">Currently, the following events are supported: sales, printing X report, and printing Z report.</span></span>

#### <a name="configuration"></a><span data-ttu-id="76faa-263">Configurazione</span><span class="sxs-lookup"><span data-stu-id="76faa-263">Configuration</span></span>

<span data-ttu-id="76faa-264">Il file di configurazione si trova nella cartella **Configuration** del progetto di estensione.</span><span class="sxs-lookup"><span data-stu-id="76faa-264">The configuration file is located in the **Configuration** folder of the extension project.</span></span> <span data-ttu-id="76faa-265">Lo scopo del file è di consentire la configurazione delle impostazioni per il fornitore di documenti da Headquarters.</span><span class="sxs-lookup"><span data-stu-id="76faa-265">The purpose of the file is to enable settings for the document provider to be configured from Headquarters.</span></span> <span data-ttu-id="76faa-266">Il formato di file è allineato ai requisiti per la configurazione dell'integrazione fiscale.</span><span class="sxs-lookup"><span data-stu-id="76faa-266">The file format is aligned with the requirements for fiscal integration configuration.</span></span> <span data-ttu-id="76faa-267">Vengono aggiunte le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="76faa-267">The following settings are added:</span></span>

- <span data-ttu-id="76faa-268">Mapping codici IVA</span><span class="sxs-lookup"><span data-stu-id="76faa-268">VAT codes mapping</span></span>
- <span data-ttu-id="76faa-269">Mapping aliquote IVA</span><span class="sxs-lookup"><span data-stu-id="76faa-269">VAT rates mapping</span></span>
- <span data-ttu-id="76faa-270">Mapping tipo di metodo di pagamento</span><span class="sxs-lookup"><span data-stu-id="76faa-270">Tender type mapping</span></span>
- <span data-ttu-id="76faa-271">Tipo di codice a barre per numero ricevuta</span><span class="sxs-lookup"><span data-stu-id="76faa-271">Barcode type for receipt number</span></span>
- <span data-ttu-id="76faa-272">Tipo di pagamento deposito</span><span class="sxs-lookup"><span data-stu-id="76faa-272">Deposit payment type</span></span>

### <a name="hardware-station-extension-design"></a><span data-ttu-id="76faa-273">Progettazione dell'estensione stazione hardware</span><span class="sxs-lookup"><span data-stu-id="76faa-273">Hardware station extension design</span></span>

<span data-ttu-id="76faa-274">Lo scopo dell'estensione (connettore fiscale) è di comunicare con la stampante fiscale.</span><span class="sxs-lookup"><span data-stu-id="76faa-274">The purpose of the extension that is a fiscal connector is to communicate with the fiscal printer.</span></span>

<span data-ttu-id="76faa-275">L'estensione stazione hardware è **HardwareStation.Extension.EpsonFP90IIIFiscalDeviceSample**.</span><span class="sxs-lookup"><span data-stu-id="76faa-275">The Hardware station extension is **HardwareStation.Extension.EpsonFP90IIIFiscalDeviceSample**.</span></span> <span data-ttu-id="76faa-276">Questa estensione utilizza il protocollo HTTP per inviare documenti generati dall'estensione di Commerce Runtime per la stampante fiscale.</span><span class="sxs-lookup"><span data-stu-id="76faa-276">This extension uses the HTTP protocol to submit documents that the Commerce runtime extension generates to the fiscal printer.</span></span> <span data-ttu-id="76faa-277">Gestisce inoltre le risposte ricevute dalla stampante fiscale.</span><span class="sxs-lookup"><span data-stu-id="76faa-277">It also handles the responses that are received from the fiscal printer.</span></span>

#### <a name="request-handler"></a><span data-ttu-id="76faa-278">Gestore richieste</span><span class="sxs-lookup"><span data-stu-id="76faa-278">Request handler</span></span>

<span data-ttu-id="76faa-279">Il gestore richieste **EpsonFP90IIISample** è il punto di ingresso per la trasmissione della richiesta alla periferica fiscale.</span><span class="sxs-lookup"><span data-stu-id="76faa-279">The **EpsonFP90IIISample** request handler is the entry point for handling request to the fiscal peripheral device.</span></span>

<span data-ttu-id="76faa-280">Il gestore viene ereditato dall'interfaccia **INamedRequestHandler**.</span><span class="sxs-lookup"><span data-stu-id="76faa-280">The handler is inherited from the **INamedRequestHandler** interface.</span></span> <span data-ttu-id="76faa-281">Il metodo **HandlerName** è responsabile della restituzione del nome del gestore.</span><span class="sxs-lookup"><span data-stu-id="76faa-281">The **HandlerName** method is responsible for returning the name of the handler.</span></span> <span data-ttu-id="76faa-282">Il nome del gestore deve corrispondere al nome del connettore fiscale specificato in Headquarters.</span><span class="sxs-lookup"><span data-stu-id="76faa-282">The handler name should match the fiscal connector name that is specified in Headquarters.</span></span>

<span data-ttu-id="76faa-283">Il connettore supporta le seguenti richieste:</span><span class="sxs-lookup"><span data-stu-id="76faa-283">The connector supports the following requests:</span></span>

- <span data-ttu-id="76faa-284">**SubmitDocumentFiscalDeviceRequest** - Invia documenti alle stampanti e restituisce la risposta dalla stampante fiscale.</span><span class="sxs-lookup"><span data-stu-id="76faa-284">**SubmitDocumentFiscalDeviceRequest** – This request sends documents to printers and returns the response from the fiscal printer.</span></span>
- <span data-ttu-id="76faa-285">**IsReadyFiscalDeviceRequest** - Viene utilizzata per un controllo di integrità del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="76faa-285">**IsReadyFiscalDeviceRequest** – This request is used for a health check of the device.</span></span>
- <span data-ttu-id="76faa-286">**InitializeFiscalDeviceRequest** - È utilizzata per l'inizializzazione della stampante.</span><span class="sxs-lookup"><span data-stu-id="76faa-286">**InitializeFiscalDeviceRequest** – This request is used for printer initialization.</span></span>

#### <a name="configuration"></a><span data-ttu-id="76faa-287">Configurazione</span><span class="sxs-lookup"><span data-stu-id="76faa-287">Configuration</span></span>

<span data-ttu-id="76faa-288">Il file di configurazione si trova nella cartella **Configuration** del progetto di estensione.</span><span class="sxs-lookup"><span data-stu-id="76faa-288">The configuration file is located in the **Configuration** folder of the extension project.</span></span> <span data-ttu-id="76faa-289">Lo scopo del file è di consentire la configurazione delle impostazioni per il connettore da Headquarters.</span><span class="sxs-lookup"><span data-stu-id="76faa-289">The purpose of the file is to enable settings for the connector to be configured from Headquarters.</span></span> <span data-ttu-id="76faa-290">Il formato di file è allineato ai requisiti per la configurazione dell'integrazione fiscale.</span><span class="sxs-lookup"><span data-stu-id="76faa-290">The file format is aligned with the requirements for fiscal integration configuration.</span></span> <span data-ttu-id="76faa-291">Vengono aggiunte le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="76faa-291">The following settings are added:</span></span>

- <span data-ttu-id="76faa-292">**Indirizzo endpoint** - L'URL della stampante.</span><span class="sxs-lookup"><span data-stu-id="76faa-292">**Endpoint address** – The URL of the printer.</span></span>
- <span data-ttu-id="76faa-293">**Sincronizzazione data e ora** - Questa impostazione specifica se la data e l'ora della stampante devono essere sincronizzate con la stazione hardware collegata.</span><span class="sxs-lookup"><span data-stu-id="76faa-293">**Date and time synchronization** – This setting specifies whether the date and time of the printer must be synced with the connected Hardware station.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]