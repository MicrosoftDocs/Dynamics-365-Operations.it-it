---
title: Spedizione pacchi di piccole dimensioni
description: In questo argomento vengono fornite informazioni sulla funzionalità di spedizione di pacchi di piccole dimensioni. Questa funzionalità consente a Microsoft Dynamics 365 Supply Chain Management di inviare i dettagli su un contenitore imballato al vettore, quindi ricevere un'etichetta di spedizione, una tariffa di spedizione e un numero di riferimento da quel vettore.
author: Mirzaab
manager: tfehr
ms.date: 01/08/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TMSRateEngine, TMSCarrier, CustTable, TMSShippingCarrierCustomerAccount, TMSSmallParcelShippingFeature
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-01-08
ms.dyn365.ops.version: Release 10.0.16
ms.openlocfilehash: 350193a0054ef879ece3dd2dfcc4105476981837
ms.sourcegitcommit: b7a7a14f8650913f6797ae1c4a82ad8adfe415fd
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2021
ms.locfileid: "5078277"
---
# <a name="small-parcel-shipping"></a><span data-ttu-id="51f4e-104">Spedizione pacchi di piccole dimensioni</span><span class="sxs-lookup"><span data-stu-id="51f4e-104">Small parcel shipping</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="51f4e-105">La funzionalità per la spedizione di pacchi di piccole dimensioni consente a Microsoft Dynamics 365 Supply Chain Management di interagire direttamente con i vettori fornendo un framework per la comunicazione tramite le API del vettore.</span><span class="sxs-lookup"><span data-stu-id="51f4e-105">The small parcel shipping (SPS) feature enables Microsoft Dynamics 365 Supply Chain Management to interact directly with shipping carriers by providing a framework for communication through carrier APIs.</span></span> <span data-ttu-id="51f4e-106">Questa funzionalità è utile quando si spediscono singoli ordini cliente tramite vettori di spedizione commerciali invece di utilizzare la spedizione in container o la spedizione a carico parziale (LTL).</span><span class="sxs-lookup"><span data-stu-id="51f4e-106">This functionality is useful when you're shipping individual sales orders via commercial shipping carriers instead of using container shipping or less-than-truckload (LTL) shipping.</span></span>

<span data-ttu-id="51f4e-107">La funzione di spedizione di pacchi di piccole dimensioni con il tuo corriere tramite un apposito *motore tariffe*.</span><span class="sxs-lookup"><span data-stu-id="51f4e-107">The SPS feature interacts with your shipping carrier through a dedicated *rate engine*.</span></span> <span data-ttu-id="51f4e-108">La tua organizzazione deve sviluppare questo motore tariffe in collaborazione con il vettore o il servizio hub del vettore.</span><span class="sxs-lookup"><span data-stu-id="51f4e-108">Your organization must develop this rate engine in collaboration with your carrier or carrier hub service.</span></span> <span data-ttu-id="51f4e-109">Il motore tariffe consente a Supply Chain Management di inviare i dettagli su un contenitore imballato al vettore, quindi ricevere un'etichetta di spedizione, una tariffa di spedizione e un numero di riferimento da quel vettore.</span><span class="sxs-lookup"><span data-stu-id="51f4e-109">The rate engine enables Supply Chain Management to submit details about a packed container to your carrier, and then receive a shipping label, shipping rate, and tracking number back from that carrier.</span></span>

<span data-ttu-id="51f4e-110">La tariffa di spedizione restituita viene aggiunta all'ordine cliente associato come addebito vario.</span><span class="sxs-lookup"><span data-stu-id="51f4e-110">The shipping rate that is returned is added to the associated sales order as a miscellaneous charge.</span></span> <span data-ttu-id="51f4e-111">L'etichetta di spedizione restituita può quindi essere stampata automaticamente utilizzando una stampante Zebra Programming Language (ZPL) e applicata alla spedizione.</span><span class="sxs-lookup"><span data-stu-id="51f4e-111">The shipping label that is returned can then automatically be printed by using a Zebra Programming Language (ZPL) printer and applied to the shipment.</span></span> <span data-ttu-id="51f4e-112">Il vettore eseguirà la scansione di questa etichetta di spedizione quando ritira i pacchi presso il magazzino.</span><span class="sxs-lookup"><span data-stu-id="51f4e-112">The carrier will scan this shipping label when it picks up the packages at your warehouse.</span></span>

## <a name="prepare-your-system-to-support-sps"></a><span data-ttu-id="51f4e-113">Preparare il sistema per supportare la spedizione di pacchi di piccole dimensioni</span><span class="sxs-lookup"><span data-stu-id="51f4e-113">Prepare your system to support SPS</span></span>

<span data-ttu-id="51f4e-114">Prima di poter iniziare a utilizzare la funzionalità di spedizione di pacchi di piccole dimensioni:, è necessario attivare la funzionalità spedizione di pacchi di piccole dimensioni: in Gestione delle funzionalità, aggiungere il motore tariffe e configurare i moduli **Gestione trasporti** e **Gestione magazzino** per supportarlo.</span><span class="sxs-lookup"><span data-stu-id="51f4e-114">Before you can start to use SPS functionality, you must turn on the SPS feature in Feature management, add your rate engine, and set up the **Transportation management** and **Warehouse management** modules to support it.</span></span>

### <a name="turn-on-the-sps-feature"></a><span data-ttu-id="51f4e-115">Attivare la funzionalità di spedizione di pacchi di piccole dimensioni</span><span class="sxs-lookup"><span data-stu-id="51f4e-115">Turn on the SPS feature</span></span>

<span data-ttu-id="51f4e-116">Prima di poter utilizzare questa funzionalità, è necessario attivarla nel sistema.</span><span class="sxs-lookup"><span data-stu-id="51f4e-116">Before you can use the SPS feature, it must be turned on in your system.</span></span> <span data-ttu-id="51f4e-117">Gli amministratori possono utilizzare l'area di lavoro della [gestione delle funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) per controllare lo stato della funzione e se necessario abilitarla.</span><span class="sxs-lookup"><span data-stu-id="51f4e-117">Administrators can use the [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) workspace to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="51f4e-118">Nell'area di lavoro, la funzionalità è elencata nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="51f4e-118">There, the feature is listed in the following way:</span></span>

- <span data-ttu-id="51f4e-119">**Modulo:** *Gestione trasporto*</span><span class="sxs-lookup"><span data-stu-id="51f4e-119">**Module:** *Transportation management*</span></span>
- <span data-ttu-id="51f4e-120">**Nome funzionalità:** *Spedizione di pacchi di piccole dimensioni*</span><span class="sxs-lookup"><span data-stu-id="51f4e-120">**Feature name:** *Small parcel shipping*</span></span>

### <a name="deploy-and-set-up-rate-engines"></a><span data-ttu-id="51f4e-121">Distribuire e configurare i motori tariffe</span><span class="sxs-lookup"><span data-stu-id="51f4e-121">Deploy and set up rate engines</span></span>

<span data-ttu-id="51f4e-122">Supply Chain Management non include motori tariffe.</span><span class="sxs-lookup"><span data-stu-id="51f4e-122">Supply Chain Management doesn't include any rate engines.</span></span> <span data-ttu-id="51f4e-123">È necessario ottenere o creare tutti i motori tariffe richiesti e quindi aggiungerli al sistema.</span><span class="sxs-lookup"><span data-stu-id="51f4e-123">You must obtain or create any rate engines that you require, and then add them to your system.</span></span> <span data-ttu-id="51f4e-124">Tuttavia, Microsoft fornisce un motore tariffe demo che è possibile utilizzare per i test.</span><span class="sxs-lookup"><span data-stu-id="51f4e-124">However, Microsoft provides a demo rate engine that you can use for testing.</span></span>

#### <a name="download-and-deploy-the-demo-rate-engine"></a><span data-ttu-id="51f4e-125">Scaricare e distribuire il motore tariffe demo</span><span class="sxs-lookup"><span data-stu-id="51f4e-125">Download and deploy the demo rate engine</span></span>

<span data-ttu-id="51f4e-126">Seguire questi passaggi per scaricare il motore tariffe demo.</span><span class="sxs-lookup"><span data-stu-id="51f4e-126">Follow these steps to get the demo rate engine.</span></span>

1. <span data-ttu-id="51f4e-127">Su GitHub, scaricare la [libreria di collegamento dinamico (DLL) per il motore tariffe demo](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/tree/master/SCM/SPS).</span><span class="sxs-lookup"><span data-stu-id="51f4e-127">On GitHub, download the [dynamic-link library (DLL) for the demo rate engine](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/tree/master/SCM/SPS).</span></span>
1. <span data-ttu-id="51f4e-128">Sul server di Supply Chain Management, salvare la DLL nella cartella **\\AOSService\\PackagesLocalDirectory\\ApplicationSuite\\bin**.</span><span class="sxs-lookup"><span data-stu-id="51f4e-128">On your Supply Chain Management server, save the DLL in the **\\AOSService\\PackagesLocalDirectory\\ApplicationSuite\\bin** folder.</span></span>

#### <a name="create-and-deploy-functional-rate-engines"></a><span data-ttu-id="51f4e-129">Creare e distribuire motori tariffe funzionali</span><span class="sxs-lookup"><span data-stu-id="51f4e-129">Create and deploy functional rate engines</span></span>

<span data-ttu-id="51f4e-130">Per informazioni su come creare e distribuire motori tariffe funzionali in modo che possano essere utilizzati in un ambiente di produzione o di test, vedere i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="51f4e-130">For information about how to create and deploy functional rate engines so that they can be used in a production or test environment, see the following topics:</span></span>

- [<span data-ttu-id="51f4e-131">Creare un nuovo motore di gestione del trasporto</span><span class="sxs-lookup"><span data-stu-id="51f4e-131">Create a new transportation management engine</span></span>](../transportation/create-new-transportation-management-engine.md)
- [<span data-ttu-id="51f4e-132">Impostare i motori di gestione del trasporto</span><span class="sxs-lookup"><span data-stu-id="51f4e-132">Set up transportation management engines</span></span>](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-transportation-management-engines)

<span data-ttu-id="51f4e-133">Per altre informazioni su come creare un motore tariffe per spedizione di pacchi di piccole dimensioni:, vedere il seguente post di blog: [Spedizione di pacchi di piccole dimensioni: come sfruttare la funzionalità di spedizione di pacchi di piccole dimensioni: in Microsoft Dynamics 365](https://hub.bhsolutions.com/creating-a-mock-parcel-engine-in-d365?submissionGuid=46a1fccf-80b0-4b70-a6a0-4bf45a8756b5).</span><span class="sxs-lookup"><span data-stu-id="51f4e-133">For more information about how to create an SPS rate engine, see the following blog post: [Small Parcel Shipping: How to leverage small parcel shipping functionality in Microsoft Dynamics 365](https://hub.bhsolutions.com/creating-a-mock-parcel-engine-in-d365?submissionGuid=46a1fccf-80b0-4b70-a6a0-4bf45a8756b5).</span></span>

#### <a name="set-up-a-rate-engine-in-supply-chain-management"></a><span data-ttu-id="51f4e-134">Configurare un motore tariffe in Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="51f4e-134">Set up a rate engine in Supply Chain Management</span></span>

<span data-ttu-id="51f4e-135">Dopo aver creato e distribuito un motore tariffe per spedizione di pacchi di piccole dimensioni, segui questi passaggi per configurarlo.</span><span class="sxs-lookup"><span data-stu-id="51f4e-135">After you've created and deployed a rate engine for SPS, follow these steps to set it up.</span></span>

1. <span data-ttu-id="51f4e-136">Passare a **Gestione trasporto \> Impostazioni \> Motori \> Motore tariffe**.</span><span class="sxs-lookup"><span data-stu-id="51f4e-136">Go to **Transportation management \> Setup \> Engines \> Rate engine**.</span></span>
1. <span data-ttu-id="51f4e-137">Nel riquadro azioni seleziona **Nuova** per aggiungere una riga alla griglia.</span><span class="sxs-lookup"><span data-stu-id="51f4e-137">On the Action Pane, select **New** to add a row to the grid.</span></span>
1. <span data-ttu-id="51f4e-138">Nella nuova riga, impostare i seguenti campi.</span><span class="sxs-lookup"><span data-stu-id="51f4e-138">In the new row, set the following fields:</span></span>

    - <span data-ttu-id="51f4e-139">**Motore tariffe**: immettere un nome univoco per il motore tariffe.</span><span class="sxs-lookup"><span data-stu-id="51f4e-139">**Rating engine** – Enter a unique name for the rate engine.</span></span> <span data-ttu-id="51f4e-140">Se si utilizza il motore tariffe demo, immettere *Motore tariffe demo*.</span><span class="sxs-lookup"><span data-stu-id="51f4e-140">If you're using the demo rate engine, enter *Demo rate engine*.</span></span>
    - <span data-ttu-id="51f4e-141">**Nome**: immettere una breve descrizione del motore tariffe.</span><span class="sxs-lookup"><span data-stu-id="51f4e-141">**Name** – Enter a short description of the rate engine.</span></span> <span data-ttu-id="51f4e-142">Se si utilizza il motore tariffe demo, immettere *Motore tariffe demo*.</span><span class="sxs-lookup"><span data-stu-id="51f4e-142">If you're using the demo rate engine, enter *Demo rate engine*.</span></span>
    - <span data-ttu-id="51f4e-143">**ID di valutazione dei metadati**: selezionare la base da utilizzare per calcolare la tariffa.</span><span class="sxs-lookup"><span data-stu-id="51f4e-143">**Rating metadata ID** – Select the basis that should be used to calculate your rate.</span></span> <span data-ttu-id="51f4e-144">Ad esempio, la tariffa potrebbe essere calcolata in base alla distanza.</span><span class="sxs-lookup"><span data-stu-id="51f4e-144">For example, your rate might be calculated based on distance.</span></span> <span data-ttu-id="51f4e-145">Se si sta utilizzando il motore tariffe demo, è possibile lasciare vuoto questo campo.</span><span class="sxs-lookup"><span data-stu-id="51f4e-145">If you're using the demo rate engine, you can leave this field blank.</span></span>
    - <span data-ttu-id="51f4e-146">**Assembly motore**: immettere il nome file del pacchetto DLL distribuito.</span><span class="sxs-lookup"><span data-stu-id="51f4e-146">**Engine assembly** – Enter the file name of the DLL package that you deployed.</span></span> <span data-ttu-id="51f4e-147">Se si utilizza il motore tariffe demo, immettere *TMSSmallParcelShippingEngine.dll*.</span><span class="sxs-lookup"><span data-stu-id="51f4e-147">If you're using the demo rate engine, enter *TMSSmallParcelShippingEngine.dll*.</span></span>
    - <span data-ttu-id="51f4e-148">**Classe motore**: immettere il nome della classe che è stato stabilito per il motore tariffe.</span><span class="sxs-lookup"><span data-stu-id="51f4e-148">**Engine class** – Enter the class name that was established for your rate engine.</span></span> <span data-ttu-id="51f4e-149">Se si utilizza il motore tariffe demo, immettere *TMSSmallParcelShippingEngine.SmallParcelShippingRateEngine*.</span><span class="sxs-lookup"><span data-stu-id="51f4e-149">If you're using the demo rate engine, enter *TMSSmallParcelShippingEngine.SmallParcelShippingRateEngine*.</span></span>

## <a name="example-scenario"></a><span data-ttu-id="51f4e-150">Scenario di esempio</span><span class="sxs-lookup"><span data-stu-id="51f4e-150">Example scenario</span></span>

<span data-ttu-id="51f4e-151">Questo scenario di esempio mostra come configurare e utilizzare la spedizione di pacchi di piccole dimensioni dopo aver preparato il sistema come descritto in precedenza in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="51f4e-151">This example scenario shows how to set up and use SPS after you've prepared your system as described earlier in this topic.</span></span> <span data-ttu-id="51f4e-152">Questo scenario utilizza il motore tariffe demo citato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="51f4e-152">This scenario uses the previously mentioned demo rate engine.</span></span>

### <a name="make-demo-data-available"></a><span data-ttu-id="51f4e-153">Rendi disponibili i dati dimostrativi</span><span class="sxs-lookup"><span data-stu-id="51f4e-153">Make demo data available</span></span>

<span data-ttu-id="51f4e-154">Per elaborare lo scenario utilizzando i record e i valori demo specificati qui, devi utilizzare un sistema in cui sono installati i [dati dimostrativi](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) standard.</span><span class="sxs-lookup"><span data-stu-id="51f4e-154">To work through this scenario by using the demo records and values that are specified here, you must be on a system where the standard [demo data](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) is installed.</span></span> <span data-ttu-id="51f4e-155">È inoltre necessario selezionare la persona giuridica **USMF** prima di iniziare.</span><span class="sxs-lookup"><span data-stu-id="51f4e-155">Additionally, you must select the **USMF** legal entity before you begin.</span></span>

### <a name="set-up-the-scenario"></a><span data-ttu-id="51f4e-156">Impostare lo scenario</span><span class="sxs-lookup"><span data-stu-id="51f4e-156">Set up the scenario</span></span>

<span data-ttu-id="51f4e-157">Per questo scenario di esempio, è necessario disporre di un vettore demo, gruppo di vettori, criteri di imballaggio e profilo di imballaggio.</span><span class="sxs-lookup"><span data-stu-id="51f4e-157">For this example scenario, you must have a demo carrier, carrier group, packing policy, and packing profile.</span></span> <span data-ttu-id="51f4e-158">Le seguenti sottosezioni spiegano come preparare i record necessari per lo scenario.</span><span class="sxs-lookup"><span data-stu-id="51f4e-158">The following subsections explain how to prepare the records that are required for the scenario.</span></span> <span data-ttu-id="51f4e-159">In uno scenario di produzione, il processo di installazione configurazione in genere è simile al processo descritto qui.</span><span class="sxs-lookup"><span data-stu-id="51f4e-159">In a production scenario, the setup process typically resembles the process that is described here.</span></span> <span data-ttu-id="51f4e-160">Tuttavia, verranno impostati valori diversi.</span><span class="sxs-lookup"><span data-stu-id="51f4e-160">However, you will set different values.</span></span>

#### <a name="set-up-carriers"></a><span data-ttu-id="51f4e-161">Configurare i vettori</span><span class="sxs-lookup"><span data-stu-id="51f4e-161">Set up carriers</span></span>

<span data-ttu-id="51f4e-162">Per configurare un vettore, seguire questi passaggi:</span><span class="sxs-lookup"><span data-stu-id="51f4e-162">Follow these steps to set up a carrier.</span></span>

1. <span data-ttu-id="51f4e-163">Vai a **Gestione trasporto \> Impostazioni \> Vettori \> Vettori spedizione**.</span><span class="sxs-lookup"><span data-stu-id="51f4e-163">Go to **Transportation management \> Setup \> Carriers \> Shipping carriers**.</span></span>
1. <span data-ttu-id="51f4e-164">Nel riquadro azioni selezionare **Nuovo** per aggiungere un vettore.</span><span class="sxs-lookup"><span data-stu-id="51f4e-164">On the Action Pane, select **New** to add a carrier.</span></span>
1. <span data-ttu-id="51f4e-165">Nell'intestazione, impostare i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="51f4e-165">On the header, set the following values:</span></span>

    - <span data-ttu-id="51f4e-166">**Vettore spedizione:** *vettore demo*</span><span class="sxs-lookup"><span data-stu-id="51f4e-166">**Shipping carrier:** *Demo Carrier*</span></span>
    - <span data-ttu-id="51f4e-167">**Nome:** *vettore demo*</span><span class="sxs-lookup"><span data-stu-id="51f4e-167">**Name:** *Demo Carrier*</span></span>
    - <span data-ttu-id="51f4e-168">**Modalità:** *Terra*</span><span class="sxs-lookup"><span data-stu-id="51f4e-168">**Mode:** *Ground*</span></span>

1. <span data-ttu-id="51f4e-169">Nella Scheda dettaglio **Panoramica**, impostare i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="51f4e-169">On the **Overview** FastTab, set the following values:</span></span>

    - <span data-ttu-id="51f4e-170">**Attiva vettore di spedizione:** *Sì*</span><span class="sxs-lookup"><span data-stu-id="51f4e-170">**Activate shipping carrier:** *Yes*</span></span>
    - <span data-ttu-id="51f4e-171">**Attiva valutazione vettore:** *Sì*</span><span class="sxs-lookup"><span data-stu-id="51f4e-171">**Activate carrier rating:** *Yes*</span></span>

1. <span data-ttu-id="51f4e-172">Nella Scheda dettaglio **Servizi**, seleziona **Nuovo** per aggiungere una servizio alla griglia.</span><span class="sxs-lookup"><span data-stu-id="51f4e-172">On the **Services** FastTab, select **New** to add a service to the grid.</span></span>
1. <span data-ttu-id="51f4e-173">Impostare i seguenti valori per il nuovo servizio:</span><span class="sxs-lookup"><span data-stu-id="51f4e-173">Set the following values for the new service:</span></span>

    - <span data-ttu-id="51f4e-174">**Servizio vettore:** *servizio vettore demo*</span><span class="sxs-lookup"><span data-stu-id="51f4e-174">**Carrier service:** *Demo carrier service*</span></span>
    - <span data-ttu-id="51f4e-175">**Nome:** *servizio vettore demo*</span><span class="sxs-lookup"><span data-stu-id="51f4e-175">**Name:** *Demo carrier service*</span></span>
    - <span data-ttu-id="51f4e-176">**Metodo di trasporto:** *Terra*</span><span class="sxs-lookup"><span data-stu-id="51f4e-176">**Transportation method:** *Ground*</span></span>

    <span data-ttu-id="51f4e-177">Immettere valori arbitrari per tutti gli altri campi, come richiesto.</span><span class="sxs-lookup"><span data-stu-id="51f4e-177">Enter arbitrary values for all the other fields, as required.</span></span> <span data-ttu-id="51f4e-178">(Quando si salva il nuovo record del vettore di spedizione, verrà creata una nuova modalità di consegna e il campo **Modalità di spedizione** verrà impostato automaticamente.)</span><span class="sxs-lookup"><span data-stu-id="51f4e-178">(When you save the new shipping carrier record, a new mode of delivery will be created, and the **Mode of delivery** field will be set automatically.)</span></span>

1. <span data-ttu-id="51f4e-179">Nella Scheda dettaglio **Profili valutazione** selezionare **Nuovo** per aggiungere un profilo di valutazione alla griglia.</span><span class="sxs-lookup"><span data-stu-id="51f4e-179">On the **Rating profiles** FastTab, select **New** to add a rating profile to the grid.</span></span>
1. <span data-ttu-id="51f4e-180">Impostare i seguenti valori per il nuovo profilo:</span><span class="sxs-lookup"><span data-stu-id="51f4e-180">Set the following values for the new profile:</span></span>

    - <span data-ttu-id="51f4e-181">**Profilo di valutazione:** *Servizio vettore demo*</span><span class="sxs-lookup"><span data-stu-id="51f4e-181">**Rating profile:** *Demo carrier service*</span></span>
    - <span data-ttu-id="51f4e-182">**Nome:** *servizio vettore demo*</span><span class="sxs-lookup"><span data-stu-id="51f4e-182">**Name:** *Demo carrier service*</span></span>
    - <span data-ttu-id="51f4e-183">**Motore tariffe:** *Motore tariffe demo*</span><span class="sxs-lookup"><span data-stu-id="51f4e-183">**Rate engine:** *Demo rate engine*</span></span>

    <span data-ttu-id="51f4e-184">Immettere valori arbitrari per tutti gli altri campi, come richiesto.</span><span class="sxs-lookup"><span data-stu-id="51f4e-184">Enter arbitrary values for all the other fields, as required.</span></span>

1. <span data-ttu-id="51f4e-185">Nel riquadro azioni selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="51f4e-185">On the Action Pane, select **Save**.</span></span>

<span data-ttu-id="51f4e-186">Per ulteriori informazioni su come configurare i vettori, vedere [Configurare vettori di spedizione](../transportation/tasks/set-up-shipping-carriers.md).</span><span class="sxs-lookup"><span data-stu-id="51f4e-186">For more information about how to set up carriers, see [Set up shipping carriers](../transportation/tasks/set-up-shipping-carriers.md).</span></span>

#### <a name="set-up-carrier-service-accounts"></a><span data-ttu-id="51f4e-187">Configurare gli account del servizio vettori</span><span class="sxs-lookup"><span data-stu-id="51f4e-187">Set up carrier service accounts</span></span>

<span data-ttu-id="51f4e-188">Seguire questi passaggi per configurare un account di servizio vettore.</span><span class="sxs-lookup"><span data-stu-id="51f4e-188">Follow these steps to set up a carrier service account.</span></span>

1. <span data-ttu-id="51f4e-189">Andare a **Gestione trasporto \> Impostazioni \> Valutazione \> Account di servizio vettore**.</span><span class="sxs-lookup"><span data-stu-id="51f4e-189">Go to **Transportation management \> Setup \> Rating \> Carrier service account**.</span></span>
1. <span data-ttu-id="51f4e-190">Nel riquadro azioni seleziona **Nuovo** per aggiungere un account di servizio vettore.</span><span class="sxs-lookup"><span data-stu-id="51f4e-190">On the Action Pane, select **New** to add a carrier service account.</span></span>
1. <span data-ttu-id="51f4e-191">Impostare i seguenti valori per il nuovo account:</span><span class="sxs-lookup"><span data-stu-id="51f4e-191">Set the following values for the new account:</span></span>

    - <span data-ttu-id="51f4e-192">**Vettore spedizione:** *vettore demo*</span><span class="sxs-lookup"><span data-stu-id="51f4e-192">**Shipping Carrier:** *Demo Carrier*</span></span>
    - <span data-ttu-id="51f4e-193">**Servizio vettore:** *servizio vettore demo*</span><span class="sxs-lookup"><span data-stu-id="51f4e-193">**Carrier service:** *Demo carrier service*</span></span>
    - <span data-ttu-id="51f4e-194">**Numero di conto cliente del vettore:** il numero di conto cliente del vettore utilizzato per verificare e autenticare la connessione al vettore di spedizione.</span><span class="sxs-lookup"><span data-stu-id="51f4e-194">**Carrier customer account number:** The carrier customer account number that is used to verify and authenticate the connection to the shipping carrier.</span></span> <span data-ttu-id="51f4e-195">Il vettore fornirà questo valore.</span><span class="sxs-lookup"><span data-stu-id="51f4e-195">Your carrier will provide this value.</span></span> <span data-ttu-id="51f4e-196">Se stai utilizzando il servizio demo, puoi inserire un valore arbitrario.</span><span class="sxs-lookup"><span data-stu-id="51f4e-196">If you're using the demo service, you can enter an arbitrary value.</span></span>
    - <span data-ttu-id="51f4e-197">**Sito:** *6*</span><span class="sxs-lookup"><span data-stu-id="51f4e-197">**Site:** *6*</span></span>
    - <span data-ttu-id="51f4e-198">**Magazzino:** *62*</span><span class="sxs-lookup"><span data-stu-id="51f4e-198">**Warehouse:** *62*</span></span>

    > [!NOTE]
    > <span data-ttu-id="51f4e-199">Spesso, il valore **Numero di conto cliente del vettore** è l'unico valore richiesto per autenticare la connessione.</span><span class="sxs-lookup"><span data-stu-id="51f4e-199">Often, the **Carrier customer account number** value is the only value that is required to authenticate the connection.</span></span> <span data-ttu-id="51f4e-200">Tuttavia, se l'operatore richiede parametri di autenticazione aggiuntivi, l'organizzazione dovrebbe personalizzare questa pagina per aggiungere campi extra come appropriato.</span><span class="sxs-lookup"><span data-stu-id="51f4e-200">However, if your carrier requires additional authentication parameters, your organization should customize this page to add extra fields as appropriate.</span></span>

#### <a name="set-up-a-container-packing-policy"></a><span data-ttu-id="51f4e-201">COnfigurare i criteri di imballaggio dei contenitori</span><span class="sxs-lookup"><span data-stu-id="51f4e-201">Set up a container packing policy</span></span>

<span data-ttu-id="51f4e-202">Per configurare i criteri di imballaggio del contenitore, seguire questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="51f4e-202">Follow these steps to set up a container packing policy.</span></span>

1. <span data-ttu-id="51f4e-203">Se non hai già configurato una definizione di stampante ZPL, utilizza l'applicazione dell'agente di distribuzione documenti per configurarla.</span><span class="sxs-lookup"><span data-stu-id="51f4e-203">If you haven't already set up a ZPL printer definition, use the Document Routing Agent application to set it up.</span></span> <span data-ttu-id="51f4e-204">Per ulteriori informazioni, vedere [Panoramica sulla stampa dei documenti](../../fin-ops-core/dev-itpro/analytics/print-documents.md) e argomenti correlati.</span><span class="sxs-lookup"><span data-stu-id="51f4e-204">For more information, see [Document printing overview](../../fin-ops-core/dev-itpro/analytics/print-documents.md) and related topics.</span></span>
1. <span data-ttu-id="51f4e-205">Passare a **Gestione magazzino \> Impostazioni \> Contenitori \> Criteri imballaggio contenitore**.</span><span class="sxs-lookup"><span data-stu-id="51f4e-205">Go to **Warehouse Management \> Setup \> Containers \> Container packing policies**.</span></span>
1. <span data-ttu-id="51f4e-206">Nel riquadro azioni selezionare **Nuovo** per aggiungere un criteri di imballaggio dei contenitori.</span><span class="sxs-lookup"><span data-stu-id="51f4e-206">On the Action Pane, select **New** to add a container packing policy.</span></span>
1. <span data-ttu-id="51f4e-207">Nell'intestazione dei nuovi criteri, impostare i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="51f4e-207">On the header of the new policy, set the following values:</span></span>

    - <span data-ttu-id="51f4e-208">**Criteri di imballaggio del contenitore:** *Criteri di imballaggio demo*</span><span class="sxs-lookup"><span data-stu-id="51f4e-208">**Container packing policy:** *Demo packing policy*</span></span>
    - <span data-ttu-id="51f4e-209">**Descrizione:** una descrizione dei criteri</span><span class="sxs-lookup"><span data-stu-id="51f4e-209">**Description:** A description of the policy</span></span>

1. <span data-ttu-id="51f4e-210">Nella Scheda dettaglio **Panoramica**, impostare i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="51f4e-210">On the **Overview** FastTab, set the following values:</span></span>

    - <span data-ttu-id="51f4e-211">**Magazzino:** *62*</span><span class="sxs-lookup"><span data-stu-id="51f4e-211">**Warehouse:** *62*</span></span>
    - <span data-ttu-id="51f4e-212">**Ubicazione predefinita per spedizione finale:** *Portellone*</span><span class="sxs-lookup"><span data-stu-id="51f4e-212">**Default location for final shipment:** *Baydoor*</span></span>
    - <span data-ttu-id="51f4e-213">**Unità peso:** *KG*</span><span class="sxs-lookup"><span data-stu-id="51f4e-213">**Weight unit:** *KG*</span></span>
    - <span data-ttu-id="51f4e-214">**Criteri chiusura contenitore:** *Rilascio automatico*</span><span class="sxs-lookup"><span data-stu-id="51f4e-214">**Container closing policy:** *Automatic release*</span></span>
    - <span data-ttu-id="51f4e-215">**Criteri rilascio contenitore:** *Rendi disponibile in ubicazione di spedizione finale*</span><span class="sxs-lookup"><span data-stu-id="51f4e-215">**Container release policy:** *Make available at final shipping location*</span></span>

1. <span data-ttu-id="51f4e-216">Nella scheda Dettagli **Manifesto contenitore**, è possibile impostare i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="51f4e-216">On the **Container manifest** FastTab, set the following values:</span></span>

    - <span data-ttu-id="51f4e-217">**Manifesto automatico alla chiusura del contenitore:** *Sì*</span><span class="sxs-lookup"><span data-stu-id="51f4e-217">**Automatic manifest at container close:** *Yes*</span></span>
    - <span data-ttu-id="51f4e-218">**Requisiti manifesto per contenitore:** *Gestione trasporto*</span><span class="sxs-lookup"><span data-stu-id="51f4e-218">**Manifest requirements for container:** *Transportation management*</span></span>
    - <span data-ttu-id="51f4e-219">**Stampa contenuto contenitore:** *No*</span><span class="sxs-lookup"><span data-stu-id="51f4e-219">**Print container contents:** *No*</span></span>

1. <span data-ttu-id="51f4e-220">Nella scheda Dettagli **Stampa etichetta vettore**, è possibile impostare i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="51f4e-220">On the **Carrier label printing** FastTab, set the following values:</span></span>

    - <span data-ttu-id="51f4e-221">**Stampa etichetta spedizione contenitore:** *Sempre*</span><span class="sxs-lookup"><span data-stu-id="51f4e-221">**Print container shipping label:** *Always*</span></span>
    - <span data-ttu-id="51f4e-222">**Nome stampante:** il nome della stampante ZPL che deve stampare le etichette di spedizione</span><span class="sxs-lookup"><span data-stu-id="51f4e-222">**Printer name:** The name of the ZPL printer that should print shipping labels</span></span>

#### <a name="set-up-a-packing-profile"></a><span data-ttu-id="51f4e-223">Configurare un profilo imballaggio</span><span class="sxs-lookup"><span data-stu-id="51f4e-223">Set up a packing profile</span></span>

<span data-ttu-id="51f4e-224">Per configurare un profilo di imballaggio, seguire questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="51f4e-224">Follow these steps to set up a packing profile.</span></span>

1. <span data-ttu-id="51f4e-225">Andare a **Gestione magazzino \> Impostazioni \> Imballaggio \> Profili imballaggio**.</span><span class="sxs-lookup"><span data-stu-id="51f4e-225">Go to **Warehouse Management \> Setup \> Packing \> Packing profiles**.</span></span>
1. <span data-ttu-id="51f4e-226">Nel riquadro azioni seleziona **Nuova** per aggiungere un profilo di imballaggio.</span><span class="sxs-lookup"><span data-stu-id="51f4e-226">On the Action Pane, select **New** to add a packing profile to the grid.</span></span>
1. <span data-ttu-id="51f4e-227">Impostare i seguenti valori per il nuovo profilo:</span><span class="sxs-lookup"><span data-stu-id="51f4e-227">Set the following values for the new profile:</span></span>

    - <span data-ttu-id="51f4e-228">**ID profilo imballaggio:** *Profilo di imballaggio demo*</span><span class="sxs-lookup"><span data-stu-id="51f4e-228">**Packing profile ID:** *Demo packing profile*</span></span>
    - <span data-ttu-id="51f4e-229">**Descrizione:** una descrizione del profilo</span><span class="sxs-lookup"><span data-stu-id="51f4e-229">**Description:** A description of the profile</span></span>
    - <span data-ttu-id="51f4e-230">**Criteri di imballaggio del contenitore:** *Criteri di imballaggio demo*</span><span class="sxs-lookup"><span data-stu-id="51f4e-230">**Container packing policy:** *Demo packing policy*</span></span>
    - <span data-ttu-id="51f4e-231">**Modalità ID contenitore:** *Auto*</span><span class="sxs-lookup"><span data-stu-id="51f4e-231">**Container ID mode:** *Auto*</span></span>
    - <span data-ttu-id="51f4e-232">**Tipo di contenitore:** *Piccola scatola*</span><span class="sxs-lookup"><span data-stu-id="51f4e-232">**Container type:** *SmallBox*</span></span>

#### <a name="set-up-a-customer-to-use-the-sps-carrier"></a><span data-ttu-id="51f4e-233">Configurare un cliente per utilizzare il vettore per la spedizione di pacchi di piccole dimensioni</span><span class="sxs-lookup"><span data-stu-id="51f4e-233">Set up a customer to use the SPS carrier</span></span>

<span data-ttu-id="51f4e-234">Segui questi passaggi per configurare un cliente in modo che possa utilizzare il vettore che hai creato.</span><span class="sxs-lookup"><span data-stu-id="51f4e-234">Follow these steps to set up a customer so that it can use the carrier that you created.</span></span>

1. <span data-ttu-id="51f4e-235">Passare a **Contabilità clienti \> clienti \> Tutti i clienti**.</span><span class="sxs-lookup"><span data-stu-id="51f4e-235">Go to **Accounts receivable \> customers \> All customers**.</span></span>
1. <span data-ttu-id="51f4e-236">Nella griglia, trovare e selezionare il cliente *US-027*.</span><span class="sxs-lookup"><span data-stu-id="51f4e-236">In the grid, find and select customer *US-027*.</span></span>
1. <span data-ttu-id="51f4e-237">Nel riquadro azioni, nella scheda **Generale**, nel gruppo **Configura**, selezionare **Conti cliente vettore**.</span><span class="sxs-lookup"><span data-stu-id="51f4e-237">On the Action Pane, on the **General** tab, in the **Set up** group, select **Carrier customer accounts**.</span></span>
1. <span data-ttu-id="51f4e-238">Nella pagina **Conti cliente vettore**, nel riquadro Azioni selezionare **Nuovo** per aggiungere un conto alla griglia.</span><span class="sxs-lookup"><span data-stu-id="51f4e-238">On the **Carrier customer accounts** page, on the Action Pane, select **New** to add an account to the grid.</span></span>
1. <span data-ttu-id="51f4e-239">Impostare i seguenti valori per il nuovo account:</span><span class="sxs-lookup"><span data-stu-id="51f4e-239">Set the following values for the new account:</span></span>

    - <span data-ttu-id="51f4e-240">**Vettore spedizione:** *vettore demo*</span><span class="sxs-lookup"><span data-stu-id="51f4e-240">**Shipping carrier:** *Demo Carrier*</span></span>
    - <span data-ttu-id="51f4e-241">**Numero di conto cliente del vettore:** *12345* (il valore non è importante per questo scenario, ma verrà indicato nella sezione successiva.)</span><span class="sxs-lookup"><span data-stu-id="51f4e-241">**Carrier customer account number:** *12345* (The value isn't important for this scenario, but it will be referred to in the next section.)</span></span>

### <a name="go-through-the-example-scenario"></a><span data-ttu-id="51f4e-242">Seguire lo scenario di esempio</span><span class="sxs-lookup"><span data-stu-id="51f4e-242">Go through the example scenario</span></span>

<span data-ttu-id="51f4e-243">Dopo aver configurato tutti i dati di esempio come descritto nella sezione precedente, sei pronto per passare allo scenario di esempio.</span><span class="sxs-lookup"><span data-stu-id="51f4e-243">After you've set up all the sample data as described in the previous section, you're ready to go through the example scenario.</span></span>

#### <a name="create-a-sales-order-and-process-the-work"></a><span data-ttu-id="51f4e-244">Creare un ordine cliente ed elaborare il lavoro</span><span class="sxs-lookup"><span data-stu-id="51f4e-244">Create a sales order and process the work</span></span>

<span data-ttu-id="51f4e-245">Segui questi passaggi per creare un ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="51f4e-245">Follow these steps to create a sales order.</span></span>

1. <span data-ttu-id="51f4e-246">Selezionare **Vendite e marketing \> Ordini cliente \> Tutti gli ordini cliente**.</span><span class="sxs-lookup"><span data-stu-id="51f4e-246">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="51f4e-247">Selezionare **Nuovo** per creare un ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="51f4e-247">Select **New** to create a sales order.</span></span>
1. <span data-ttu-id="51f4e-248">Nella finestra di dialogo **Crea ordine cliente**, imposta il campo **Conto cliente**, su *US-027*.</span><span class="sxs-lookup"><span data-stu-id="51f4e-248">In the **Create sales order** dialog box, set the **Customer account** field to *US-027*.</span></span>
1. <span data-ttu-id="51f4e-249">Scegli **OK** per creare l'ordine cliente e chiudere la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="51f4e-249">Select **OK** to create the sales order and close the dialog box.</span></span>
1. <span data-ttu-id="51f4e-250">Viene aperto il nuovo ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="51f4e-250">The new sales order is opened.</span></span> <span data-ttu-id="51f4e-251">Nella Scheda dettaglio **Intestazione ordine cliente**, imposta il campo **Numero di conto cliente del vettore** sul valore che hai selezionato per questo cliente in precedenza (*12345*).</span><span class="sxs-lookup"><span data-stu-id="51f4e-251">On the **Sales order header** FastTab, set the **Carrier customer account number** field to the value that you selected for this customer earlier (*12345*).</span></span>
1. <span data-ttu-id="51f4e-252">Nella sezione **Righe ordine cliente**, aggiungi una riga di vendita e imposta i seguenti valori per essa:</span><span class="sxs-lookup"><span data-stu-id="51f4e-252">In the **Sales order lines** section, add a sales line, and set the following values for it:</span></span>

    - <span data-ttu-id="51f4e-253">**Numero articolo:** *A0002*</span><span class="sxs-lookup"><span data-stu-id="51f4e-253">**Item number:** *A0002*</span></span>
    - <span data-ttu-id="51f4e-254">**Quantità:** *1*</span><span class="sxs-lookup"><span data-stu-id="51f4e-254">**Quantity:** *1*</span></span>
    - <span data-ttu-id="51f4e-255">**Sito:** *6*</span><span class="sxs-lookup"><span data-stu-id="51f4e-255">**Site:** *6*</span></span>
    - <span data-ttu-id="51f4e-256">**Magazzino:** *62*</span><span class="sxs-lookup"><span data-stu-id="51f4e-256">**Warehouse:** *62*</span></span>

1. <span data-ttu-id="51f4e-257">Passa alla visualizzazione **Intestazione**.</span><span class="sxs-lookup"><span data-stu-id="51f4e-257">Switch to the **Header** view.</span></span>
1. <span data-ttu-id="51f4e-258">Nella Scheda dettaglio **Consegna**, imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="51f4e-258">On the **Delivery** FastTab, set the following values:</span></span>

    - <span data-ttu-id="51f4e-259">**Vettore spedizione:** *vettore demo*</span><span class="sxs-lookup"><span data-stu-id="51f4e-259">**Shipping carrier:** *Demo Carrier*</span></span>
    - <span data-ttu-id="51f4e-260">**Servizio vettore:** *servizio vettore demo*</span><span class="sxs-lookup"><span data-stu-id="51f4e-260">**Carrier service:** *Demo carrier service*</span></span>

1. <span data-ttu-id="51f4e-261">Torna alla visualizzazione **Righe**.</span><span class="sxs-lookup"><span data-stu-id="51f4e-261">Switch back to the **Lines** view.</span></span> <span data-ttu-id="51f4e-262">Se viene richiesto di aggiornare la modalità di consegna per le righe di vendita, seleziona **Sì**.</span><span class="sxs-lookup"><span data-stu-id="51f4e-262">If you're prompted to update the mode of delivery for the sales lines, select **Yes**.</span></span>
1. <span data-ttu-id="51f4e-263">Nella sezione **Righe ordine cliente**, seleziona la riga dell'ordine che hai configurato in precedenza, quindi seleziona **Inventario \> Prenotazione**.</span><span class="sxs-lookup"><span data-stu-id="51f4e-263">In the **Sales order lines** section, select the order line that you set up earlier, and then select **Inventory \> Reservation**.</span></span>
1. <span data-ttu-id="51f4e-264">Nella pagina **Prenotazione**, seleziona **Prenota lotto** per prenotare l'intera quantità della riga selezionata nel magazzino.</span><span class="sxs-lookup"><span data-stu-id="51f4e-264">On the **Reservation** page, select **Reserve lot** to reserve the selected line's full quantity in the warehouse.</span></span>
1. <span data-ttu-id="51f4e-265">Chiudi la pagina **Prenotazione** per tornare all'ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="51f4e-265">Close the **Reservation** page to return to the sales order.</span></span>
1. <span data-ttu-id="51f4e-266">Nel riquadro azioni, nella scheda **Magazzino**, seleziona **Rilascia in magazzino**.</span><span class="sxs-lookup"><span data-stu-id="51f4e-266">On the Action Pane, on the **Warehouse** tab, select **Release to warehouse**.</span></span>

    <span data-ttu-id="51f4e-267">Viene creato il lavoro per spostare gli articoli dall'ubicazione di prelievo alla stazione di imballaggio.</span><span class="sxs-lookup"><span data-stu-id="51f4e-267">Work is created to move items from the picking location to the packing station.</span></span>

1. <span data-ttu-id="51f4e-268">Nella sezione **Righe ordine di vendita**, seleziona **Magazzino \> Dettagli spedizione**.</span><span class="sxs-lookup"><span data-stu-id="51f4e-268">In the **Sales order lines** section, select **Warehouse \> Shipment details**.</span></span>
1. <span data-ttu-id="51f4e-269">Nella pagina **Dettagli spedizione**, prendi nota dell'ID spedizione.</span><span class="sxs-lookup"><span data-stu-id="51f4e-269">On the **Shipment details** page, make a note of the shipment ID.</span></span> <span data-ttu-id="51f4e-270">Ne avrai bisogno quando imballerai il pacco per spedizione alla stazione di imballaggio.</span><span class="sxs-lookup"><span data-stu-id="51f4e-270">You will need it when you pack the pack the shipment at the packing station.</span></span>
1. <span data-ttu-id="51f4e-271">Chiudi la pagina **Dettagli spedizione** per tornare all'ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="51f4e-271">Close the **Shipment details** page to return to the sales order.</span></span>
1. <span data-ttu-id="51f4e-272">Prendi nota del numero dell'ordine cliente, quindi passa a **Gestione magazzino \> Lavoro \> Tutti i lavori**.</span><span class="sxs-lookup"><span data-stu-id="51f4e-272">Make a note of the sales order number, and then go to **Warehouse management \> Work \> All work**.</span></span>
1. <span data-ttu-id="51f4e-273">Utilizza il numero dell'ordine cliente per trovare e selezionare il lavoro creato per l'ordine.</span><span class="sxs-lookup"><span data-stu-id="51f4e-273">Use the sales order number to find and select the work that was created for the order.</span></span>
1. <span data-ttu-id="51f4e-274">Nel riquadro Azioni, nella scheda **Lavoro**, seleziona **Lavoro completato**.</span><span class="sxs-lookup"><span data-stu-id="51f4e-274">On the Action Pane, on the **Work** tab, select **Complete work**.</span></span>
1. <span data-ttu-id="51f4e-275">Nella pagina **Completamento del lavoro**, nel campo **ID utente** seleziona un ID utente.</span><span class="sxs-lookup"><span data-stu-id="51f4e-275">On the **Work completion** page, in the **User ID** field, select a user ID.</span></span> <span data-ttu-id="51f4e-276">Quindi, nel riquadro azioni seleziona **Convalida lavoro**.</span><span class="sxs-lookup"><span data-stu-id="51f4e-276">Then, on the Action Pane, select **Validate work**.</span></span>
1. <span data-ttu-id="51f4e-277">Se il lavoro supera la convalida, seleziona **Completa lavoro** nel riquadro Azioni.</span><span class="sxs-lookup"><span data-stu-id="51f4e-277">If the work passes validation, select **Complete work** on the Action Pane.</span></span>

    <span data-ttu-id="51f4e-278">Il lavoro viene contrassegnato come completato per simulare lo spostamento degli articoli verso la stazione di imballaggio.</span><span class="sxs-lookup"><span data-stu-id="51f4e-278">The work is marked as completed to simulate the movement of items to the packing station.</span></span>

#### <a name="pack-the-shipment"></a><span data-ttu-id="51f4e-279">Imballare la spedizione</span><span class="sxs-lookup"><span data-stu-id="51f4e-279">Pack the shipment</span></span>

<span data-ttu-id="51f4e-280">Segui questi passaggi per imballare la spedizione.</span><span class="sxs-lookup"><span data-stu-id="51f4e-280">Follow these steps to pack the shipment.</span></span>

1. <span data-ttu-id="51f4e-281">Vai a **Gestione magazzino \> Configura \> Lavoratore** e assicurati che il tuo account utente sia associato a un account lavoratore per la gestione del magazzino.</span><span class="sxs-lookup"><span data-stu-id="51f4e-281">Go to **Warehouse management \> Setup \> Worker**, and make sure that your user account is associated with a worker account for warehouse management.</span></span>
1. <span data-ttu-id="51f4e-282">Vai a **Gestione magazzino \> Prelievo e containerizzazione \> Imballaggio**.</span><span class="sxs-lookup"><span data-stu-id="51f4e-282">Go to **Warehouse management \> Picking and containerization \> Pack**.</span></span>
1. <span data-ttu-id="51f4e-283">Nella finestra di dialogo **Seleziona stazione di imballaggio**, imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="51f4e-283">In the **Select packing station** dialog box, set the following values:</span></span>

    - <span data-ttu-id="51f4e-284">**Sito:** *6*</span><span class="sxs-lookup"><span data-stu-id="51f4e-284">**Site:** *6*</span></span>
    - <span data-ttu-id="51f4e-285">**Magazzino:** *62*</span><span class="sxs-lookup"><span data-stu-id="51f4e-285">**Warehouse:** *62*</span></span>
    - <span data-ttu-id="51f4e-286">**Ubicazione:** *Imballaggio*</span><span class="sxs-lookup"><span data-stu-id="51f4e-286">**Location:** *Pack*</span></span>
    - <span data-ttu-id="51f4e-287">**ID profilo imballaggio:** *Profilo di imballaggio demo*</span><span class="sxs-lookup"><span data-stu-id="51f4e-287">**Packing profile ID:** *Demo packing profile*</span></span>

1. <span data-ttu-id="51f4e-288">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="51f4e-288">Select **OK**.</span></span>
1. <span data-ttu-id="51f4e-289">Viene visualizzata la pagina **Imballa**.</span><span class="sxs-lookup"><span data-stu-id="51f4e-289">The **Pack** page appears.</span></span> <span data-ttu-id="51f4e-290">In uno scenario di produzione, un lavoratore eseguirà la scansione di una targa o un ID spedizione.</span><span class="sxs-lookup"><span data-stu-id="51f4e-290">In a production scenario, a worker will scan a license plate or shipment ID.</span></span> <span data-ttu-id="51f4e-291">Tuttavia, per questo scenario, apri la pagina **Tutte le spedizioni** e cerca il numero di spedizione per la spedizione appena creata.</span><span class="sxs-lookup"><span data-stu-id="51f4e-291">However, for this scenario, open the **All shipments** page, and look up the shipment number for the shipment that you just created.</span></span> <span data-ttu-id="51f4e-292">Quindi immetti questo valore nel campo **Targa o spedizione** della pagina **Imballa**.</span><span class="sxs-lookup"><span data-stu-id="51f4e-292">Then enter this value in the **License plate or shipment** field on the **Pack** page.</span></span> <span data-ttu-id="51f4e-293">In alternativa, immetti l'ID della spedizione di cui hai preso nota in precedenza.</span><span class="sxs-lookup"><span data-stu-id="51f4e-293">Alternatively, enter the shipment ID that you made a note of earlier.</span></span>
1. <span data-ttu-id="51f4e-294">Nel riquadro azioni selezionare **Nuovo contenitore**.</span><span class="sxs-lookup"><span data-stu-id="51f4e-294">On the Action Pane, select **New container**.</span></span>
1. <span data-ttu-id="51f4e-295">La finestra di dialogo che appare mostra i dettagli sul nuovo contenitore.</span><span class="sxs-lookup"><span data-stu-id="51f4e-295">The dialog box that appears shows details about the new container.</span></span> <span data-ttu-id="51f4e-296">Lascia i valori predefiniti, quindi seleziona **OK**.</span><span class="sxs-lookup"><span data-stu-id="51f4e-296">Leave the default values, and then select **OK**.</span></span>
1. <span data-ttu-id="51f4e-297">Nella pagina **Imballa**, nella Scheda dettaglio **Imballaggio articolo**, nel campo **Identificatore**, seleziona *A0002* per imballare quell'articolo.</span><span class="sxs-lookup"><span data-stu-id="51f4e-297">On the **Pack** page, on the **Item packing** FastTab, in the **Identifier** field, select *A0002* to pack that item.</span></span> <span data-ttu-id="51f4e-298">L'articolo viene aggiunto al contenitore.</span><span class="sxs-lookup"><span data-stu-id="51f4e-298">The item is added to the container.</span></span>
1. <span data-ttu-id="51f4e-299">Nel riquadro azioni, seleziona **Contenitori per spedizione**.</span><span class="sxs-lookup"><span data-stu-id="51f4e-299">On the Action Pane, select **Containers for shipment**.</span></span>

    <span data-ttu-id="51f4e-300">La pagina **Contenitori per spedizione** visualizzata ha una riga per il contenitore che hai appena creato.</span><span class="sxs-lookup"><span data-stu-id="51f4e-300">The **Containers for shipment** page that appears has a row for the container that you just created.</span></span> <span data-ttu-id="51f4e-301">Tuttavia, il campo **ID manifesto contenitore** in quella riga è attualmente vuoto, perché non hai ancora ricevuto l'etichetta di spedizione e il numero di tracciamento dal corriere.</span><span class="sxs-lookup"><span data-stu-id="51f4e-301">However, the **Container manifest ID** field in that row is currently blank, because you haven't yet received the shipping label and tracking number from the carrier.</span></span>

1. <span data-ttu-id="51f4e-302">Nel riquadro azioni selezionare **Chiudi contenitore**.</span><span class="sxs-lookup"><span data-stu-id="51f4e-302">On the Action Pane, select **Close container**.</span></span>
1. <span data-ttu-id="51f4e-303">Nella finestra di dialogo **Chiudi contenitore**, imposta il campo **Peso lordo** su *1 kg* e quindi seleziona **OK**.</span><span class="sxs-lookup"><span data-stu-id="51f4e-303">In the **Close container** dialog box, set the **Gross weight** field to *1 kg*, and then select **OK**.</span></span>

    <span data-ttu-id="51f4e-304">L'etichetta di spedizione dovrebbe ora essere stampata sulla stampante ZPL selezionata in precedenza.</span><span class="sxs-lookup"><span data-stu-id="51f4e-304">The shipping label should now be printed on the ZPL printer that you selected earlier.</span></span> <span data-ttu-id="51f4e-305">Il risultato sarà simile all'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="51f4e-305">It should resemble the following example.</span></span>

    <span data-ttu-id="51f4e-306">![Etichetta di spedizione di esempio](media/sps-label-example.png "Etichetta di spedizione di esempio")</span><span class="sxs-lookup"><span data-stu-id="51f4e-306">![Example shipping label](media/sps-label-example.png "Example shipping label")</span></span>

1. <span data-ttu-id="51f4e-307">Tieni presente che i valori **ID manifesto contenitore** e **Trasporto totale** sono stati aggiunti come ricevuti dal vettore.</span><span class="sxs-lookup"><span data-stu-id="51f4e-307">Notice that the **Container manifest ID** and **Total freight** values have been added as received from the carrier.</span></span>
