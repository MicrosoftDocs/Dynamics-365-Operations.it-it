---
title: Impostare un canale online
description: In questo argomento viene descritto come creare un nuovo canale in Microsoft Dynamics 365 Commerce.
author: samjarawan
ms.date: 07/02/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: b6bf158361f95b6551b29f195616cf21f908b802
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5800641"
---
# <a name="set-up-an-online-channel"></a><span data-ttu-id="fe5fd-103">Impostare un canale online</span><span class="sxs-lookup"><span data-stu-id="fe5fd-103">Set up an online channel</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="fe5fd-104">In questo argomento viene descritto come creare un nuovo canale in Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="fe5fd-104">This topic describes how to create a new online channel in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="fe5fd-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="fe5fd-105">Overview</span></span>

<span data-ttu-id="fe5fd-106">In Dynamics 365 Commerce sono supportati più canali di vendita al dettaglio.</span><span class="sxs-lookup"><span data-stu-id="fe5fd-106">Dynamics 365 Commerce supports multiple retail channels.</span></span> <span data-ttu-id="fe5fd-107">Questi canali di vendita al dettaglio includono punti vendita online, call center e punti vendita al dettaglio, noti anche come punti vendita fisici.</span><span class="sxs-lookup"><span data-stu-id="fe5fd-107">These retail channels include online stores, call centers, and retail stores (also known as brick-and-mortar stores).</span></span> <span data-ttu-id="fe5fd-108">I punti vendita online offrono ai clienti la possibilità di acquistare prodotti presso il punto vendita online del fornitore oltre che nei punti vendita al dettaglio.</span><span class="sxs-lookup"><span data-stu-id="fe5fd-108">Online stores give customers the option of purchasing products from the retailer's online store in addition to its retail stores.</span></span>

<span data-ttu-id="fe5fd-109">Per creare un negozio online in Commerce, devi prima creare un canale online.</span><span class="sxs-lookup"><span data-stu-id="fe5fd-109">To create an online store in Commerce, you must first create an online channel.</span></span> <span data-ttu-id="fe5fd-110">Prima di creare un nuovo canale online, assicurarsi di aver completato i [prerequisiti di impostazione dei canali](channels-prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="fe5fd-110">Before you create a new online channel, ensure that you have completed the [Channel set up prerequisites](channels-prerequisites.md).</span></span>

<span data-ttu-id="fe5fd-111">Prima di poter creare un nuovo sito, almeno un punto vendita online deve essere creato in Commerce.</span><span class="sxs-lookup"><span data-stu-id="fe5fd-111">Before you can create a new site, at least one online store must be created in Commerce.</span></span> <span data-ttu-id="fe5fd-112">Per ulteriori informazioni, vedi [Creare un sito di e-commerce](create-ecommerce-site.md).</span><span class="sxs-lookup"><span data-stu-id="fe5fd-112">For more information, see [Create an e-Commerce site](create-ecommerce-site.md).</span></span>

## <a name="create-and-configure-a-new-online-channel"></a><span data-ttu-id="fe5fd-113">Creare e configurare un nuovo canale online</span><span class="sxs-lookup"><span data-stu-id="fe5fd-113">Create and configure a new online channel</span></span>

<span data-ttu-id="fe5fd-114">Per creare e configurare un nuovo canale online, effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="fe5fd-114">To create and configure a new online channel, follow these steps.</span></span>

1. <span data-ttu-id="fe5fd-115">Nel pannello di navigazione, andare a **Moduli \> Canali \> Punti vendita online**.</span><span class="sxs-lookup"><span data-stu-id="fe5fd-115">In the navigation pane, go to **Modules \> Channels \> Online Stores**.</span></span>
1. <span data-ttu-id="fe5fd-116">Nel Riquadro azioni selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="fe5fd-116">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="fe5fd-117">Nel campo **Nome** digitare un nome per il nuovo canale.</span><span class="sxs-lookup"><span data-stu-id="fe5fd-117">In the **Name** field, provide a name for the new channel.</span></span>
1. <span data-ttu-id="fe5fd-118">In **Persona giuridica**, immettere la persona giuridica appropriata.</span><span class="sxs-lookup"><span data-stu-id="fe5fd-118">In the **Legal entity** drop-down, enter the appropriate legal entity.</span></span>
1. <span data-ttu-id="fe5fd-119">In **Magazzino**, immettere il magazzino appropriato.</span><span class="sxs-lookup"><span data-stu-id="fe5fd-119">In the **Warehouse** drop-down, enter the appropriate warehouse.</span></span>
1. <span data-ttu-id="fe5fd-120">Nel campo **Fuso orario punto vendita** selezionare il fuso orario appropriato.</span><span class="sxs-lookup"><span data-stu-id="fe5fd-120">In the **Store time zone** field, select the appropriate time zone.</span></span>
1. <span data-ttu-id="fe5fd-121">Nel campo **Valuta**, selezionare la valuta appropriata.</span><span class="sxs-lookup"><span data-stu-id="fe5fd-121">In the **Currency** field, select the appropriate currency.</span></span>
1. <span data-ttu-id="fe5fd-122">Nel campo **Cliente predefinito** fornire un cliente predefinito valido.</span><span class="sxs-lookup"><span data-stu-id="fe5fd-122">In the **Default customer** field, provide a valid default customer.</span></span>
1. <span data-ttu-id="fe5fd-123">Nel campo **Rubrica clienti**, fornire una rubrica valida.</span><span class="sxs-lookup"><span data-stu-id="fe5fd-123">In the **Customer address book** field, provide a valid address book.</span></span>
1. <span data-ttu-id="fe5fd-124">Nel campo **Profilo funzionalità**, selezionare un profilo di funzionalità, se applicabile.</span><span class="sxs-lookup"><span data-stu-id="fe5fd-124">In the **Functionality profile** field, select a functionality profile if applicable.</span></span>
1. <span data-ttu-id="fe5fd-125">Nel campo **Profilo di notifica tramite posta elettronica**, fornire un profilo di notifica valido.</span><span class="sxs-lookup"><span data-stu-id="fe5fd-125">In the **Email notification profile** field, provide a valid email notification profile.</span></span>
1. <span data-ttu-id="fe5fd-126">Nel riquadro azioni selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="fe5fd-126">On the action pane, select **Save**.</span></span>

<span data-ttu-id="fe5fd-127">L'immagine seguente mostra la creazione di un nuovo canale online.</span><span class="sxs-lookup"><span data-stu-id="fe5fd-127">The following image shows the creation of a new online channel.</span></span>

![Nuovo canale online](media/channel-setup-online-1.png)

<span data-ttu-id="fe5fd-129">L'immagine seguente mostra un esempio di canale online.</span><span class="sxs-lookup"><span data-stu-id="fe5fd-129">The following image shows an example online channel.</span></span>

![Esempio di canale online](media/channel-setup-online-2.png)

## <a name="set-up-languages"></a><span data-ttu-id="fe5fd-131">Impostare le lingue</span><span class="sxs-lookup"><span data-stu-id="fe5fd-131">Set up languages</span></span>

<span data-ttu-id="fe5fd-132">Se il sito di e-commerce supporterà più lingue, espandere la sezione **Lingue** e aggiungere altre lingue come necessario.</span><span class="sxs-lookup"><span data-stu-id="fe5fd-132">If your e-Commerce site will support multiple languages, expand the **Languages** section and add additional languages as needed.</span></span>

## <a name="set-up-payment-account"></a><span data-ttu-id="fe5fd-133">Impostare un conto pagamenti</span><span class="sxs-lookup"><span data-stu-id="fe5fd-133">Set up payment account</span></span>

<span data-ttu-id="fe5fd-134">Nella sezione **Conto pagamenti**, è possibile aggiungere un fornitore di servizi di pagamento di terze parti.</span><span class="sxs-lookup"><span data-stu-id="fe5fd-134">From within the **Payment account** section, you can add a third-party payment provider.</span></span> <span data-ttu-id="fe5fd-135">Per informazioni sull'impostazione del connettore di pagamento Adyen, vedere [Connettore pagamenti di Dynamics 365 per Adyen](../retail/dev-itpro/adyen-connector.md).</span><span class="sxs-lookup"><span data-stu-id="fe5fd-135">For information on setting up an Adyen payment connector, see [Dynamics 365 Payment Connector for Adyen](../retail/dev-itpro/adyen-connector.md).</span></span>

## <a name="additional-channel-setup"></a><span data-ttu-id="fe5fd-136">Ulteriori azioni di impostazione di canali</span><span class="sxs-lookup"><span data-stu-id="fe5fd-136">Additional channel setup</span></span>

<span data-ttu-id="fe5fd-137">Ulteriori attività necessarie per l'impostazione di un canale online includono l'impostazione di metodi di pagamento, modalità di consegna e assegnazione del gruppo di adempimento.</span><span class="sxs-lookup"><span data-stu-id="fe5fd-137">Additional tasks that are required for online channel setup include setting up payment methods, modes of delivery, and the fulfillment group assignment.</span></span>

<span data-ttu-id="fe5fd-138">L'immagine seguente mostra le opzioni di impostazione **Modalità di consegna**, **Metodi di pagamento** e **Assegnazione gruppo di adempimento** nella scheda **Imposta**.</span><span class="sxs-lookup"><span data-stu-id="fe5fd-138">The following image shows **Modes of delivery**, **Payment methods**, and **Fulfillment group assignment** setup options on the **Set up** tab.</span></span>

![Ulteriori azioni di impostazione del canale online](media/channel-setup-online-3.png)

### <a name="set-up-payment-methods"></a><span data-ttu-id="fe5fd-140">Impostare i metodi di pagamento</span><span class="sxs-lookup"><span data-stu-id="fe5fd-140">Set up payment methods</span></span>

<span data-ttu-id="fe5fd-141">Per impostare i metodi di pagamento per ogni tipo di pagamento supportato per un canale, procedere come segue.</span><span class="sxs-lookup"><span data-stu-id="fe5fd-141">To set up payment methods, for each payment type supported on this channel follow these steps.</span></span>

1. <span data-ttu-id="fe5fd-142">Nel riquadro azioni, selezionare la scheda **Imposta**, quindi selezionare **Metodi di pagamento**.</span><span class="sxs-lookup"><span data-stu-id="fe5fd-142">On the action pane, select the **Set Up** tab, then select **Payment methods**.</span></span>
1. <span data-ttu-id="fe5fd-143">Nel Riquadro azioni selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="fe5fd-143">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="fe5fd-144">Nel pannello di navigazione, selezionare un metodo di pagamento desiderato.</span><span class="sxs-lookup"><span data-stu-id="fe5fd-144">In the navigation pane, select a desired payment method.</span></span>
1. <span data-ttu-id="fe5fd-145">Nella sezione **Generale**, immettere un nome in **Nome operazione** e configurare qualsiasi altra impostazione desiderata.</span><span class="sxs-lookup"><span data-stu-id="fe5fd-145">In the **General** section, provide an **Operation name** and configure any other desired settings.</span></span>
1. <span data-ttu-id="fe5fd-146">Configurare eventuali impostazioni aggiuntive come necessario per il tipo di pagamento.</span><span class="sxs-lookup"><span data-stu-id="fe5fd-146">Configure any additional settings as required for the payment type.</span></span>
1. <span data-ttu-id="fe5fd-147">Nel riquadro azioni selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="fe5fd-147">On the action pane, select **Save**.</span></span>

<span data-ttu-id="fe5fd-148">L'immagine seguente illustra un esempio di metodo di pagamento in contanti.</span><span class="sxs-lookup"><span data-stu-id="fe5fd-148">The following image shows an example of a cash payment method.</span></span>

![Esempio di metodi di pagamento](media/channel-setup-retail-5.png)

### <a name="set-up-modes-of-delivery"></a><span data-ttu-id="fe5fd-150">Impostare le modalità di consegna</span><span class="sxs-lookup"><span data-stu-id="fe5fd-150">Set up modes of delivery</span></span>

<span data-ttu-id="fe5fd-151">È possibile visualizzare le modalità di consegna configurate selezionando **Modalità di consegna** nella scheda **Imposta** del **Riquadro azioni**.</span><span class="sxs-lookup"><span data-stu-id="fe5fd-151">You can see the configured modes of delivery by selecting **Modes of delivery** from the **Set up** tab on the **Action pane**.</span></span>  

<span data-ttu-id="fe5fd-152">Per modificare o aggiungere una modalità di consegna, attenersi alla seguente procedura.</span><span class="sxs-lookup"><span data-stu-id="fe5fd-152">To change or add a mode of delivery, follow these steps.</span></span>

1. <span data-ttu-id="fe5fd-153">Nel pannello di navigazione, selezionare **Moduli \> Gestione inventario \> Modalità di consegna**.</span><span class="sxs-lookup"><span data-stu-id="fe5fd-153">In the navigation pane, go to **Modules \> Inventory management \> Modes of delivery**.</span></span>
1. <span data-ttu-id="fe5fd-154">Nel riquadro azioni, selezionare **Nuovo** per creare una nuova modalità di consegna o selezionarne una esistente.</span><span class="sxs-lookup"><span data-stu-id="fe5fd-154">On the action pane, select **New** to create a new mode of delivery, or select an existing mode.</span></span>
1. <span data-ttu-id="fe5fd-155">Nella sezione **Canali di vendita al dettaglio**, selezionare **Aggiungi riga** per aggiungere il canale.</span><span class="sxs-lookup"><span data-stu-id="fe5fd-155">In the **Retail channels** section, select **Add line** to add the channel.</span></span> <span data-ttu-id="fe5fd-156">Aggiungere canali utilizzando nodi dell'organizzazione anziché aggiungere ogni canale singolarmente può semplificare questa operazione.</span><span class="sxs-lookup"><span data-stu-id="fe5fd-156">Adding channels using organization nodes instead of adding each channel individually can streamline adding channels.</span></span>

<span data-ttu-id="fe5fd-157">L'immagine seguente illustra un esempio di modalità di consegna.</span><span class="sxs-lookup"><span data-stu-id="fe5fd-157">The following image shows an example of a mode of delivery.</span></span>

![Impostare le modalità di consegna](media/channel-setup-retail-7.png)

### <a name="set-up-a-fulfillment-group-assignment"></a><span data-ttu-id="fe5fd-159">Impostare l'assegnazione di un gruppo di adempimento</span><span class="sxs-lookup"><span data-stu-id="fe5fd-159">Set up a fulfillment group assignment</span></span>

<span data-ttu-id="fe5fd-160">Per impostare l'assegnazione di un gruppo di adempimento, effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="fe5fd-160">To set up a fulfillment group assignment, follow these steps.</span></span>

1. <span data-ttu-id="fe5fd-161">Nel riquadro azioni, selezionare la scheda **Imposta**, quindi selezionare **Assegnazione gruppo di adempimento**.</span><span class="sxs-lookup"><span data-stu-id="fe5fd-161">On the action pane, select the **Set up** tab, then select **Fulfillment group assignment**.</span></span>
1. <span data-ttu-id="fe5fd-162">Nel Riquadro azioni selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="fe5fd-162">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="fe5fd-163">Nell'elenco a discesa **Gruppo di adempimento**, selezionare un gruppo di adempimento.</span><span class="sxs-lookup"><span data-stu-id="fe5fd-163">In the **Fulfillment group** drop-down list, select a fulfillment group.</span></span>
1. <span data-ttu-id="fe5fd-164">Nel campo **Descrizione**, immettere una descrizione.</span><span class="sxs-lookup"><span data-stu-id="fe5fd-164">In the **Description** drop-down list, enter a description.</span></span>
1. <span data-ttu-id="fe5fd-165">Nel riquadro azioni selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="fe5fd-165">On the action pane, select **Save**.</span></span>

<span data-ttu-id="fe5fd-166">L'immagine seguente mostra un esempio di impostazione dell'assegnazione di un gruppo di adempimento.</span><span class="sxs-lookup"><span data-stu-id="fe5fd-166">The following image shows an example of a fulfillment group assignment setup.</span></span>

![Impostare l'assegnazione di un gruppo di adempimento](media/channel-setup-retail-9.png)

## <a name="additional-resources"></a><span data-ttu-id="fe5fd-168">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="fe5fd-168">Additional resources</span></span>

[<span data-ttu-id="fe5fd-169">Panoramica dei canali</span><span class="sxs-lookup"><span data-stu-id="fe5fd-169">Channels overview</span></span>](channels-overview.md)

[<span data-ttu-id="fe5fd-170">Prerequisiti di impostazione dei canali</span><span class="sxs-lookup"><span data-stu-id="fe5fd-170">Channel setup prerequisites</span></span>](channels-prerequisites.md)

[<span data-ttu-id="fe5fd-171">Impostare un canale di vendita al dettaglio</span><span class="sxs-lookup"><span data-stu-id="fe5fd-171">Set up a retail channel</span></span>](channel-setup-retail.md)

[<span data-ttu-id="fe5fd-172">Impostare un canale servizio clienti</span><span class="sxs-lookup"><span data-stu-id="fe5fd-172">Set up a call center channel</span></span>](channel-setup-callcenter.md)

[<span data-ttu-id="fe5fd-173">Connettore pagamenti di Dynamics 365 per Adyen</span><span class="sxs-lookup"><span data-stu-id="fe5fd-173">Dynamics 365 Payment Connector for Adyen</span></span>](../retail/dev-itpro/adyen-connector.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]