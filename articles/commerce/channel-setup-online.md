---
title: Impostare un canale online
description: In questo argomento viene descritto come creare un nuovo canale in Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: 9b7a2b8fd157df8b39e9e227d188a3802cacb4e3
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/01/2020
ms.locfileid: "3002429"
---
# <a name="set-up-an-online-channel"></a><span data-ttu-id="f3cd8-103">Impostare un canale online</span><span class="sxs-lookup"><span data-stu-id="f3cd8-103">Set up an online channel</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="f3cd8-104">In questo argomento viene descritto come creare un nuovo canale in Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="f3cd8-104">This topic describes how to create a new online channel in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="f3cd8-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="f3cd8-105">Overview</span></span>

<span data-ttu-id="f3cd8-106">In Dynamics 365 Commerce sono supportati più canali di vendita al dettaglio.</span><span class="sxs-lookup"><span data-stu-id="f3cd8-106">Dynamics 365 Commerce supports multiple retail channels.</span></span> <span data-ttu-id="f3cd8-107">Questi canali di vendita al dettaglio includono punti vendita online, call center e punti vendita al dettaglio, noti anche come punti vendita fisici.</span><span class="sxs-lookup"><span data-stu-id="f3cd8-107">These retail channels include online stores, call centers, and retail stores (also known as brick-and-mortar stores).</span></span> <span data-ttu-id="f3cd8-108">I punti vendita online offrono ai clienti la possibilità di acquistare prodotti presso il punto vendita online del fornitore oltre che nei punti vendita al dettaglio.</span><span class="sxs-lookup"><span data-stu-id="f3cd8-108">Online stores give customers the option of purchasing products from the retailer's online store in addition to its retail stores.</span></span>

<span data-ttu-id="f3cd8-109">Per creare un negozio online in Commerce, devi prima creare un canale online.</span><span class="sxs-lookup"><span data-stu-id="f3cd8-109">To create an online store in Commerce, you must first create an online channel.</span></span> 

<span data-ttu-id="f3cd8-110">Prima di creare un nuovo canale online, assicurarsi di aver completato i [prerequisiti di impostazione dei canali](channels-prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="f3cd8-110">Before you create a new online channel, ensure that you have completed the [Channel set up prerequisites](channels-prerequisites.md).</span></span>

## <a name="create-and-configure-a-new-online-channel"></a><span data-ttu-id="f3cd8-111">Creare e configurare un nuovo canale online</span><span class="sxs-lookup"><span data-stu-id="f3cd8-111">Create and configure a new online channel</span></span>

<span data-ttu-id="f3cd8-112">Per creare e configurare un nuovo canale online, effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="f3cd8-112">To create and configure a new online channel, follow these steps.</span></span>

1. <span data-ttu-id="f3cd8-113">Nel pannello di navigazione, andare a **Moduli \> Canali \> Punti vendita online**.</span><span class="sxs-lookup"><span data-stu-id="f3cd8-113">In the navigation pane, go to **Modules \> Channels \> Online Stores**.</span></span>
1. <span data-ttu-id="f3cd8-114">Nel Riquadro azioni selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="f3cd8-114">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="f3cd8-115">Nel campo **Nome** digitare un nome per il nuovo canale.</span><span class="sxs-lookup"><span data-stu-id="f3cd8-115">In the **Name** field, provide a name for the new channel.</span></span>
1. <span data-ttu-id="f3cd8-116">In **Persona giuridica**, immettere la persona giuridica appropriata.</span><span class="sxs-lookup"><span data-stu-id="f3cd8-116">In the **Legal entity** drop-down, enter the appropriate legal entity.</span></span>
1. <span data-ttu-id="f3cd8-117">In **Magazzino**, immettere il magazzino appropriato.</span><span class="sxs-lookup"><span data-stu-id="f3cd8-117">In the **Warehouse** drop-down, enter the appropriate warehouse.</span></span>
1. <span data-ttu-id="f3cd8-118">Nel campo **Fuso orario punto vendita** selezionare il fuso orario appropriato.</span><span class="sxs-lookup"><span data-stu-id="f3cd8-118">In the **Store time zone** field, select the appropriate time zone.</span></span>
1. <span data-ttu-id="f3cd8-119">Nel campo **Valuta**, selezionare la valuta appropriata.</span><span class="sxs-lookup"><span data-stu-id="f3cd8-119">In the **Currency** field, select the appropriate currency.</span></span>
1. <span data-ttu-id="f3cd8-120">Nel campo **Cliente predefinito** fornire un cliente predefinito valido.</span><span class="sxs-lookup"><span data-stu-id="f3cd8-120">In the **Default customer** field, provide a valid default customer.</span></span>
1. <span data-ttu-id="f3cd8-121">Nel campo **Rubrica clienti**, fornire una rubrica valida.</span><span class="sxs-lookup"><span data-stu-id="f3cd8-121">In the **Customer address book** field, provide a valid address book.</span></span>
1. <span data-ttu-id="f3cd8-122">Nel campo **Profilo funzionalità**, selezionare un profilo di funzionalità, se applicabile.</span><span class="sxs-lookup"><span data-stu-id="f3cd8-122">In the **Functionality profile** field, select a functionality profile if applicable.</span></span>
1. <span data-ttu-id="f3cd8-123">Nel campo **Profilo di notifica tramite posta elettronica**, fornire un profilo di notifica valido.</span><span class="sxs-lookup"><span data-stu-id="f3cd8-123">In the **Email notification profile** field, provide a valid email notification profile.</span></span>
1. <span data-ttu-id="f3cd8-124">Nel riquadro azioni selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="f3cd8-124">On the action pane, select **Save**.</span></span>

<span data-ttu-id="f3cd8-125">L'immagine seguente mostra la creazione di un nuovo canale online.</span><span class="sxs-lookup"><span data-stu-id="f3cd8-125">The following image shows the creation of a new online channel.</span></span>

![Nuovo canale online](media/channel-setup-online-1.png)

<span data-ttu-id="f3cd8-127">L'immagine seguente mostra un esempio di canale online.</span><span class="sxs-lookup"><span data-stu-id="f3cd8-127">The following image shows an example online channel.</span></span>

![Esempio di canale online](media/channel-setup-online-2.png)

## <a name="set-up-languages"></a><span data-ttu-id="f3cd8-129">Impostare le lingue</span><span class="sxs-lookup"><span data-stu-id="f3cd8-129">Set up languages</span></span>

<span data-ttu-id="f3cd8-130">Se il sito di e-commerce supporterà più lingue, espandere la sezione **Lingue** e aggiungere altre lingue come necessario.</span><span class="sxs-lookup"><span data-stu-id="f3cd8-130">If your e-Commerce site will support multiple languages, expand the **Languages** section and add additional languages as needed.</span></span>

## <a name="set-up-payment-account"></a><span data-ttu-id="f3cd8-131">Impostare un conto pagamenti</span><span class="sxs-lookup"><span data-stu-id="f3cd8-131">Set up payment account</span></span>

<span data-ttu-id="f3cd8-132">Nella sezione **Conto pagamenti**, è possibile aggiungere un fornitore di servizi di pagamento di terze parti.</span><span class="sxs-lookup"><span data-stu-id="f3cd8-132">From within the **Payment account** section, you can add a third-party payment provider.</span></span> <span data-ttu-id="f3cd8-133">Per informazioni sull'impostazione del connettore di pagamento Adyen, vedere [Connettore pagamenti di Dynamics 365 per Adyen](../retail/dev-itpro/adyen-connector.md).</span><span class="sxs-lookup"><span data-stu-id="f3cd8-133">For information on settting up an Adyen payment connector, see [Dynamics 365 Payment Connector for Adyen](../retail/dev-itpro/adyen-connector.md).</span></span>

## <a name="additional-channel-set-up"></a><span data-ttu-id="f3cd8-134">Ulteriori operazioni di impostazione di canali</span><span class="sxs-lookup"><span data-stu-id="f3cd8-134">Additional channel set up</span></span>

<span data-ttu-id="f3cd8-135">Ulteriori attività necessarie per l'impostazione di un canale online includono l'impostazione di metodi di pagamento, modalità di consegna e assegnazione del gruppo di adempimento.</span><span class="sxs-lookup"><span data-stu-id="f3cd8-135">Additional tasks required for online channel setup include setting up payment methods, modes of delivery, and the fulfillment group assignment.</span></span>

<span data-ttu-id="f3cd8-136">L'immagine seguente mostra le opzioni di impostazione **Modalità di consegna**, **Metodi di pagamento** e **Assegnazione gruppo di adempimento** nella scheda **Imposta**.</span><span class="sxs-lookup"><span data-stu-id="f3cd8-136">The following image shows **Modes of delivery**, **Payment methods**, and **Fulfillment group assignment** setup options on the **Set up** tab.</span></span>

![Ulteriori azioni di impostazione del canale online](media/channel-setup-online-3.png)

### <a name="set-up-payment-methods"></a><span data-ttu-id="f3cd8-138">Impostare i metodi di pagamento</span><span class="sxs-lookup"><span data-stu-id="f3cd8-138">Set up payment methods</span></span>

<span data-ttu-id="f3cd8-139">Per impostare i metodi di pagamento per ogni tipo di pagamento supportato per un canale, procedere come segue.</span><span class="sxs-lookup"><span data-stu-id="f3cd8-139">To set up payment methods, for each payment type supported on this channel follow these steps.</span></span>

1. <span data-ttu-id="f3cd8-140">Nel riquadro azioni, selezionare la scheda **Imposta**, quindi selezionare **Metodi di pagamento**.</span><span class="sxs-lookup"><span data-stu-id="f3cd8-140">On the action pane, select the **Set Up** tab, then select **Payment methods**.</span></span>
1. <span data-ttu-id="f3cd8-141">Nel Riquadro azioni selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="f3cd8-141">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="f3cd8-142">Nel pannello di navigazione, selezionare un metodo di pagamento desiderato.</span><span class="sxs-lookup"><span data-stu-id="f3cd8-142">In the navigation pane, select a desired payment method.</span></span>
1. <span data-ttu-id="f3cd8-143">Nella sezione **Generale**, immettere un nome in **Nome operazione** e configurare qualsiasi altra impostazione desiderata.</span><span class="sxs-lookup"><span data-stu-id="f3cd8-143">In the **General** section, provide an **Operation name** and configure any other desired settings.</span></span>
1. <span data-ttu-id="f3cd8-144">Configurare eventuali impostazioni aggiuntive come necessario per il tipo di pagamento.</span><span class="sxs-lookup"><span data-stu-id="f3cd8-144">Configure any additional settings as required for the payment type.</span></span>
1. <span data-ttu-id="f3cd8-145">Nel riquadro azioni selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="f3cd8-145">On the action pane, select **Save**.</span></span>

<span data-ttu-id="f3cd8-146">L'immagine seguente illustra un esempio di metodo di pagamento in contanti.</span><span class="sxs-lookup"><span data-stu-id="f3cd8-146">The following image shows an example of a cash payment method.</span></span>

![Esempio di metodi di pagamento](media/channel-setup-retail-5.png)

### <a name="set-up-modes-of-delivery"></a><span data-ttu-id="f3cd8-148">Impostare le modalità di consegna</span><span class="sxs-lookup"><span data-stu-id="f3cd8-148">Set up modes of delivery</span></span>

<span data-ttu-id="f3cd8-149">È possibile visualizzare le modalità di consegna configurate selezionando **Modalità di consegna** nella scheda **Imposta** del **Riquadro azioni**.</span><span class="sxs-lookup"><span data-stu-id="f3cd8-149">You can see the configured modes of delivery by selecting **Modes of delivery** from the **Set up** tab on the **Action pane**.</span></span>  

<span data-ttu-id="f3cd8-150">Per modificare o aggiungere una modalità di consegna, attenersi alla seguente procedura.</span><span class="sxs-lookup"><span data-stu-id="f3cd8-150">To change or add a mode of delivery, follow these steps.</span></span>

1. <span data-ttu-id="f3cd8-151">Nel pannello di navigazione, selezionare **Moduli \> Gestione inventario \> Modalità di consegna**.</span><span class="sxs-lookup"><span data-stu-id="f3cd8-151">In the navigation pane, go to **Modules \> Inventory management \> Modes of delivery**.</span></span>
1. <span data-ttu-id="f3cd8-152">Nel riquadro azioni, selezionare **Nuovo** per creare una nuova modalità di consegna o selezionarne una esistente.</span><span class="sxs-lookup"><span data-stu-id="f3cd8-152">On the action pane, select **New** to create a new mode of delivery, or select an existing mode.</span></span>
1. <span data-ttu-id="f3cd8-153">Nella sezione **Canali di vendita al dettaglio**, selezionare **Aggiungi riga** per aggiungere il canale.</span><span class="sxs-lookup"><span data-stu-id="f3cd8-153">In the **Retail channels** section, select **Add line** to add the channel.</span></span> <span data-ttu-id="f3cd8-154">Aggiungere canali utilizzando nodi dell'organizzazione anziché aggiungere ogni canale singolarmente può semplificare questa operazione.</span><span class="sxs-lookup"><span data-stu-id="f3cd8-154">Adding channels using organization nodes instead of adding each channel individually can streamline adding channels.</span></span>

<span data-ttu-id="f3cd8-155">L'immagine seguente illustra un esempio di modalità di consegna.</span><span class="sxs-lookup"><span data-stu-id="f3cd8-155">The following image shows an example of a mode of delivery.</span></span>

![Impostare le modalità di consegna](media/channel-setup-retail-7.png)

### <a name="set-up-a-fulfillment-group-assignment"></a><span data-ttu-id="f3cd8-157">Impostare l'assegnazione di un gruppo di adempimento</span><span class="sxs-lookup"><span data-stu-id="f3cd8-157">Set up a fulfillment group assignment</span></span>

<span data-ttu-id="f3cd8-158">Per impostare l'assegnazione di un gruppo di adempimento, effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="f3cd8-158">To set up a fulfillment group assignment, follow these steps.</span></span>

1. <span data-ttu-id="f3cd8-159">Nel riquadro azioni, selezionare la scheda **Imposta**, quindi selezionare **Assegnazione gruppo di adempimento**.</span><span class="sxs-lookup"><span data-stu-id="f3cd8-159">On the action pane, select the **Set up** tab, then select **Fulfillment group assignment**.</span></span>
1. <span data-ttu-id="f3cd8-160">Nel Riquadro azioni selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="f3cd8-160">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="f3cd8-161">Nell'elenco a discesa **Gruppo di adempimento**, selezionare un gruppo di adempimento.</span><span class="sxs-lookup"><span data-stu-id="f3cd8-161">In the **Fulfillment group** drop-down list, select a fulfillment group.</span></span>
1. <span data-ttu-id="f3cd8-162">Nel campo **Descrizione**, immettere una descrizione.</span><span class="sxs-lookup"><span data-stu-id="f3cd8-162">In the **Description** drop-down list, enter a description.</span></span>
1. <span data-ttu-id="f3cd8-163">Nel riquadro azioni selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="f3cd8-163">On the action pane, select **Save**.</span></span>

<span data-ttu-id="f3cd8-164">L'immagine seguente mostra un esempio di impostazione dell'assegnazione di un gruppo di adempimento.</span><span class="sxs-lookup"><span data-stu-id="f3cd8-164">The following image shows an example of a fulfillment group assignment setup.</span></span>

![Impostare l'assegnazione di un gruppo di adempimento](media/channel-setup-retail-9.png)

## <a name="additional-resources"></a><span data-ttu-id="f3cd8-166">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="f3cd8-166">Additional resources</span></span>

[<span data-ttu-id="f3cd8-167">Panoramica dei canali</span><span class="sxs-lookup"><span data-stu-id="f3cd8-167">Channels overview</span></span>](channels-overview.md)

[<span data-ttu-id="f3cd8-168">Prerequisiti di impostazione dei canali</span><span class="sxs-lookup"><span data-stu-id="f3cd8-168">Channel setup prerequisites</span></span>](channels-prerequisites.md)

[<span data-ttu-id="f3cd8-169">Impostare un canale di vendita al dettaglio</span><span class="sxs-lookup"><span data-stu-id="f3cd8-169">Set up a retail channel</span></span>](channel-setup-retail.md)

[<span data-ttu-id="f3cd8-170">Impostare un canale servizio clienti</span><span class="sxs-lookup"><span data-stu-id="f3cd8-170">Set up a call center channel</span></span>](channel-setup-callcenter.md)

[<span data-ttu-id="f3cd8-171">Connettore pagamenti di Dynamics 365 per Adyen</span><span class="sxs-lookup"><span data-stu-id="f3cd8-171">Dynamics 365 Payment Connector for Adyen</span></span>](../retail/dev-itpro/adyen-connector.md)