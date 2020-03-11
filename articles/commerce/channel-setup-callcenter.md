---
title: Impostare un canale servizio clienti
description: In questo argomento viene descritto come creare un nuovo canale servizio clienti in Microsoft Dynamics 365 Commerce.
author: samjarawan
manager: annbe
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 42448bd54c00b8642b158f422e17d2b46ee25579
ms.sourcegitcommit: 12b9d6f2dd24e52e46487748c848864909af6967
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "3057881"
---
# <a name="set-up-a-call-center-channel"></a><span data-ttu-id="5e435-103">Impostare un canale servizio clienti</span><span class="sxs-lookup"><span data-stu-id="5e435-103">Set up a call center channel</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="5e435-104">In questo argomento viene descritto come creare un nuovo canale servizio clienti in Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="5e435-104">This topic describes how to create a new call center channel in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="5e435-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="5e435-105">Overview</span></span>

<span data-ttu-id="5e435-106">In Dynamics 365 Commerce, un servizio clienti è un tipo di canale di commercio che può essere definito nell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="5e435-106">In Dynamics 365 Commerce, a call center is a type of channel that can be defined in the application.</span></span> <span data-ttu-id="5e435-107">La definizione di un canale per le entità del servizio clienti consente al sistema di associare specifici valori predefiniti di dati e di elaborazione di ordini a ordini cliente.</span><span class="sxs-lookup"><span data-stu-id="5e435-107">Defining a channel for your call center entities allows the system to tie specific data and order processing defaults to sales orders.</span></span> <span data-ttu-id="5e435-108">Una società può definire più canali servizio clienti in Commerce.</span><span class="sxs-lookup"><span data-stu-id="5e435-108">A company can define multiple call center channels in Commerce.</span></span> 

<span data-ttu-id="5e435-109">Prima di creare un nuovo canale servizio clienti, assicurarsi di aver completato i [prerequisiti di impostazione dei canali](channels-prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="5e435-109">Before you create a new call center channel, ensure that you have completed the [Channel set up prerequisites](channels-prerequisites.md).</span></span>

## <a name="create-and-configure-a-new-call-center-channel"></a><span data-ttu-id="5e435-110">Creare e configurare un nuovo canale servizio clienti</span><span class="sxs-lookup"><span data-stu-id="5e435-110">Create and configure a new call center channel</span></span>

<span data-ttu-id="5e435-111">Per creare e configurare un nuovo canale servizio clienti, effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="5e435-111">To create and configure a new call center channel, follow these steps.</span></span>

1. <span data-ttu-id="5e435-112">Nel pannello di navigazione andare a **Moduli \> Canali \> Servizi clienti \> Tutti i servizi clienti**.</span><span class="sxs-lookup"><span data-stu-id="5e435-112">In the navigation pane, go to **Modules \> Channels \> Call centers \> All call centers**.</span></span>
1. <span data-ttu-id="5e435-113">Nel Riquadro azioni selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="5e435-113">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="5e435-114">Nel campo **Nome** digitare un nome per il nuovo canale.</span><span class="sxs-lookup"><span data-stu-id="5e435-114">In the **Name** field, provide a name for the new channel.</span></span>
1. <span data-ttu-id="5e435-115">Selezionare la **persona giuridica** appropriata nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="5e435-115">Select the appropriate **Legal entity** from the drop down.</span></span>
1. <span data-ttu-id="5e435-116">Selezionare l'ubicazione **magazzino** appropriata nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="5e435-116">Select the appropriate **Warehouse** location from the drop down.</span></span>
1. <span data-ttu-id="5e435-117">Nel campo **Cliente predefinito** fornire un cliente predefinito valido.</span><span class="sxs-lookup"><span data-stu-id="5e435-117">In the **Default customer** field, provide a valid default customer.</span></span>
1. <span data-ttu-id="5e435-118">Nel campo **Profilo di notifica tramite posta elettronica**, fornire un profilo di notifica valido.</span><span class="sxs-lookup"><span data-stu-id="5e435-118">In the **Email notification profile** field, provide a valid email notification profile.</span></span>
1. <span data-ttu-id="5e435-119">Fornire un codice informativo **Forzatura prezzo**.</span><span class="sxs-lookup"><span data-stu-id="5e435-119">Provide a **Price override** info code.</span></span> <span data-ttu-id="5e435-120">Notare che potrebbe essere necessario creare dapprima un codice informativo.</span><span class="sxs-lookup"><span data-stu-id="5e435-120">Note you may need to create an info code for this first.</span></span>
1. <span data-ttu-id="5e435-121">Fornire un codice informativo **Codice sospensione**.</span><span class="sxs-lookup"><span data-stu-id="5e435-121">Provide a **Hold code** info code.</span></span> <span data-ttu-id="5e435-122">Notare che potrebbe essere necessario creare dapprima un codice informativo.</span><span class="sxs-lookup"><span data-stu-id="5e435-122">Note you may need to create an info code for this first.</span></span>
1. <span data-ttu-id="5e435-123">Fornire un codice informativo **Credito**.</span><span class="sxs-lookup"><span data-stu-id="5e435-123">Provide a **Credit** info code.</span></span> <span data-ttu-id="5e435-124">Notare che potrebbe essere necessario creare dapprima un codice informativo.</span><span class="sxs-lookup"><span data-stu-id="5e435-124">Note you may need to create an info code for this first.</span></span>
1. <span data-ttu-id="5e435-125">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="5e435-125">Select **Save**.</span></span>

<span data-ttu-id="5e435-126">L'immagine seguente mostra la creazione di un nuovo canale servizio clienti.</span><span class="sxs-lookup"><span data-stu-id="5e435-126">The following image shows the creation of a new call center channel.</span></span>

![Nuovo canale servizio clienti](media/channel-setup-callcenter-1.png)

<span data-ttu-id="5e435-128">L'immagine seguente mostra un esempio di canale servizio clienti.</span><span class="sxs-lookup"><span data-stu-id="5e435-128">The following image shows an example call center channel.</span></span>

![Esempio di canale servizio clienti](media/channel-setup-callcenter-2.png)

## <a name="additional-channel-setup"></a><span data-ttu-id="5e435-130">Ulteriori azioni di impostazione di canali</span><span class="sxs-lookup"><span data-stu-id="5e435-130">Additional channel setup</span></span>

<span data-ttu-id="5e435-131">Ulteriori attività necessarie per l'impostazione di canali servizio clienti includono l'impostazione di metodi di pagamento e di modalità di consegna.</span><span class="sxs-lookup"><span data-stu-id="5e435-131">Additional tasks required for call center channel setup include setting up payment methods and modes of delivery.</span></span>

<span data-ttu-id="5e435-132">L'immagine seguente mostra le opzioni di impostazione **Modalità di consegna** e **Metodi di pagamento** nella scheda **Imposta**.</span><span class="sxs-lookup"><span data-stu-id="5e435-132">The following image shows **Modes of delivery** and **Payment methods** set up options on the **Set up** tab.</span></span>

![Ulteriori azioni di impostazione dei canali servizio clienti](media/channel-setup-callcenter-3.png)

### <a name="set-up-payment-methods"></a><span data-ttu-id="5e435-134">Impostare i metodi di pagamento</span><span class="sxs-lookup"><span data-stu-id="5e435-134">Set up payment methods</span></span>

<span data-ttu-id="5e435-135">Per impostare i metodi di pagamento per ogni tipo di pagamento supportato per un canale, procedere come segue.</span><span class="sxs-lookup"><span data-stu-id="5e435-135">To set up payment methods, for each payment type supported on this channel follow these steps.</span></span>

1. <span data-ttu-id="5e435-136">Nel riquadro azioni, selezionare la scheda **Imposta**, quindi selezionare **Metodi di pagamento**.</span><span class="sxs-lookup"><span data-stu-id="5e435-136">On the action pane, select the **Set up** tab, and then select **Payment methods**.</span></span>
1. <span data-ttu-id="5e435-137">Nel Riquadro azioni selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="5e435-137">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="5e435-138">Nel pannello di navigazione, selezionare un metodo di pagamento desiderato.</span><span class="sxs-lookup"><span data-stu-id="5e435-138">In the navigation pane, select a desired payment method.</span></span>
1. <span data-ttu-id="5e435-139">Nella sezione **Generale**, immettere un nome in **Nome operazione** e configurare qualsiasi altra impostazione desiderata.</span><span class="sxs-lookup"><span data-stu-id="5e435-139">In the **General** section, provide an **Operation name** and configure any other desired settings.</span></span>
1. <span data-ttu-id="5e435-140">Configurare eventuali impostazioni aggiuntive come necessario per il tipo di pagamento.</span><span class="sxs-lookup"><span data-stu-id="5e435-140">Configure any additional settings as required for the payment type.</span></span>
1. <span data-ttu-id="5e435-141">Nel riquadro azioni selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="5e435-141">On the action pane, select **Save**.</span></span>

<span data-ttu-id="5e435-142">L'immagine seguente illustra un esempio di metodo di pagamento in contanti.</span><span class="sxs-lookup"><span data-stu-id="5e435-142">The following image shows an example of a cash payment method.</span></span>

![Esempio di metodi di pagamento](media/channel-setup-retail-5.png)

### <a name="set-up-modes-of-delivery"></a><span data-ttu-id="5e435-144">Impostare le modalità di consegna</span><span class="sxs-lookup"><span data-stu-id="5e435-144">Set up modes of delivery</span></span>

<span data-ttu-id="5e435-145">È possibile visualizzare le modalità di consegna configurate selezionando **Modalità di consegna** nella scheda **Imposta** del **Riquadro azioni**.</span><span class="sxs-lookup"><span data-stu-id="5e435-145">You can see the configured modes of delivery by selecting **Modes of delivery** from the **Set up** tab on the **Action pane**.</span></span>  

<span data-ttu-id="5e435-146">Per modificare o aggiungere una modalità di consegna, attenersi alla seguente procedura.</span><span class="sxs-lookup"><span data-stu-id="5e435-146">To change or add a mode of delivery, follow these steps.</span></span>

1. <span data-ttu-id="5e435-147">Nel pannello di navigazione, selezionare **Moduli \> Gestione inventario \> Modalità di consegna**.</span><span class="sxs-lookup"><span data-stu-id="5e435-147">In the navigation pane, go to **Modules \> Inventory management \> Modes of delivery**.</span></span>
1. <span data-ttu-id="5e435-148">Nel riquadro azioni, selezionare **Nuovo** per creare una nuova modalità di consegna o selezionarne una esistente.</span><span class="sxs-lookup"><span data-stu-id="5e435-148">On the action pane, select **New** to create a new mode of delivery, or select an existing mode.</span></span>
1. <span data-ttu-id="5e435-149">Nella sezione **Canali di vendita al dettaglio**, selezionare **Aggiungi riga** per aggiungere il canale.</span><span class="sxs-lookup"><span data-stu-id="5e435-149">In the **Retail channels** section, select **Add line** to add the channel.</span></span> <span data-ttu-id="5e435-150">Aggiungere canali utilizzando nodi dell'organizzazione anziché aggiungere ogni canale singolarmente può semplificare questa operazione.</span><span class="sxs-lookup"><span data-stu-id="5e435-150">Adding channels using organization nodes instead of adding each channel individually can streamline adding channels.</span></span>

<span data-ttu-id="5e435-151">L'immagine seguente illustra un esempio di modalità di consegna.</span><span class="sxs-lookup"><span data-stu-id="5e435-151">The following image shows an example of a mode of delivery.</span></span>

![Impostare le modalità di consegna](media/channel-setup-retail-7.png)

## <a name="additional-resources"></a><span data-ttu-id="5e435-153">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="5e435-153">Additional resources</span></span>

[<span data-ttu-id="5e435-154">Prerequisiti di impostazione dei canali</span><span class="sxs-lookup"><span data-stu-id="5e435-154">Channel setup prerequisites</span></span>](channels-prerequisites.md)

[<span data-ttu-id="5e435-155">Funzionalità di vendita del servizio clienti</span><span class="sxs-lookup"><span data-stu-id="5e435-155">Call center sales functionality</span></span>](call-center-functionality.md)

[<span data-ttu-id="5e435-156">Impostare le opzioni di elaborazione dell'ordine</span><span class="sxs-lookup"><span data-stu-id="5e435-156">Set up call center order processing options</span></span>](set-up-order-processing-options.md)

[<span data-ttu-id="5e435-157">Cataloghi del servizio clienti</span><span class="sxs-lookup"><span data-stu-id="5e435-157">Call center catalogs</span></span>](call-center-catalogs.md)

[<span data-ttu-id="5e435-158">Impostare e utilizzare gli avvisi di frode</span><span class="sxs-lookup"><span data-stu-id="5e435-158">Set up and work with fraud alerts</span></span>](set-up-fraud-alerts.md)

[<span data-ttu-id="5e435-159">Impostare programmi di continuità per i servizi clienti</span><span class="sxs-lookup"><span data-stu-id="5e435-159">Set up continuity programs for call centers</span></span>](set-up-continuity-program.md)
