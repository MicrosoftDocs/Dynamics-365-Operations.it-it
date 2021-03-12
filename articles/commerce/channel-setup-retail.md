---
title: Impostare un canale di vendita al dettaglio
description: In questo argomento viene descritto come creare un nuovo canale di vendita al dettaglio in Microsoft Dynamics 365 Commerce.
author: samjarawan
manager: annbe
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 100822ecea03d03267f98654c66e74f2f5924bd9
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4997727"
---
# <a name="set-up-a-retail-channel"></a><span data-ttu-id="f2e3b-103">Impostare un canale di vendita al dettaglio</span><span class="sxs-lookup"><span data-stu-id="f2e3b-103">Set up a retail channel</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="f2e3b-104">In questo argomento viene descritto come creare un nuovo canale di vendita al dettaglio in Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="f2e3b-104">This topic describes how to create a new retail channel in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="f2e3b-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="f2e3b-105">Overview</span></span>

<span data-ttu-id="f2e3b-106">In Dynamics 365 Commerce sono supportati più canali di vendita al dettaglio.</span><span class="sxs-lookup"><span data-stu-id="f2e3b-106">Dynamics 365 Commerce supports multiple retail channels.</span></span> <span data-ttu-id="f2e3b-107">Questi canali di vendita al dettaglio includono punti vendita online, call center e punti vendita al dettaglio, noti anche come punti vendita fisici.</span><span class="sxs-lookup"><span data-stu-id="f2e3b-107">These retail channels include online stores, call centers, and retail stores (also known as brick-and-mortar stores).</span></span> <span data-ttu-id="f2e3b-108">Ogni canale di vendita al dettaglio può disporre di propri metodi di pagamento, gruppi di prezzi, POS, conti ricavi/spese e personale.</span><span class="sxs-lookup"><span data-stu-id="f2e3b-108">Each retail store channel can have its own payment methods, price groups, point of sale (POS) registers, income accounts and expense accounts, and staff.</span></span> <span data-ttu-id="f2e3b-109">È necessario impostare tutti questi elementi prima di creare un canale di vendita al dettaglio.</span><span class="sxs-lookup"><span data-stu-id="f2e3b-109">You must set up all of these elements before you can create a retail store channel.</span></span> 

<span data-ttu-id="f2e3b-110">Prima di creare un canale di vendita al dettaglio, assicurarsi di soddisfare i [prerequisiti per i canali](channels-prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="f2e3b-110">Before a retail channel is created, ensure you follow the [channel prerequisites](channels-prerequisites.md).</span></span>

## <a name="create-and-configure-a-new-retail-channel"></a><span data-ttu-id="f2e3b-111">Creare e configurare un nuovo canale di vendita al dettaglio</span><span class="sxs-lookup"><span data-stu-id="f2e3b-111">Create and configure a new retail channel</span></span>

1. <span data-ttu-id="f2e3b-112">Nel pannello di navigazione, andare a **Moduli \> Canali \> Punti vendita \> Tutti i punti vendita**.</span><span class="sxs-lookup"><span data-stu-id="f2e3b-112">In the navigation pane, go to **Modules \> Channels \> Stores \> All stores**.</span></span>
1. <span data-ttu-id="f2e3b-113">Nel Riquadro azioni selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="f2e3b-113">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="f2e3b-114">Nel campo **Nome** digitare un nome per il nuovo canale.</span><span class="sxs-lookup"><span data-stu-id="f2e3b-114">In the **Name** field, provide a name for the new channel.</span></span>
1. <span data-ttu-id="f2e3b-115">Nel campo **Numero punto vendita** immettere un numero di punto vendita univoco.</span><span class="sxs-lookup"><span data-stu-id="f2e3b-115">In the **Store number** field, provide a unique store number.</span></span> <span data-ttu-id="f2e3b-116">Il numero può essere alfanumerico con un massimo di 10 caratteri.</span><span class="sxs-lookup"><span data-stu-id="f2e3b-116">The number can be alphanumeric with a maximum of 10 characters.</span></span>
1. <span data-ttu-id="f2e3b-117">Nell'elenco a discesa **Persona giuridica**, immettere la persona giuridica appropriata.</span><span class="sxs-lookup"><span data-stu-id="f2e3b-117">In the **Legal entity** drop-down list, enter the appropriate legal entity.</span></span>
1. <span data-ttu-id="f2e3b-118">Nell'elenco a discesa **Magazzino**, immettere il magazzino appropriato.</span><span class="sxs-lookup"><span data-stu-id="f2e3b-118">In the **Warehouse** drop-down list, enter the appropriate warehouse.</span></span>
1. <span data-ttu-id="f2e3b-119">Nel campo **Fuso orario punto vendita** selezionare il fuso orario appropriato.</span><span class="sxs-lookup"><span data-stu-id="f2e3b-119">In the **Store time zone** field, select the appropriate time zone.</span></span>
1. <span data-ttu-id="f2e3b-120">Nell'elenco a discesa **Fascia IVA**, selezionare una fascia IVA appropriata per il punto vendita.</span><span class="sxs-lookup"><span data-stu-id="f2e3b-120">In the **Sales tax group** drop-down list, select an appropriate sales tax group for the store.</span></span>
1. <span data-ttu-id="f2e3b-121">Nel campo **Valuta**, selezionare la valuta appropriata.</span><span class="sxs-lookup"><span data-stu-id="f2e3b-121">In the **Currency** field, select the appropriate currency.</span></span>
1. <span data-ttu-id="f2e3b-122">Nel campo **Rubrica clienti**, fornire una rubrica valida.</span><span class="sxs-lookup"><span data-stu-id="f2e3b-122">In the **Customer address book** field, provide a valid address book.</span></span>
1. <span data-ttu-id="f2e3b-123">Nel campo **Cliente predefinito** fornire un cliente predefinito valido.</span><span class="sxs-lookup"><span data-stu-id="f2e3b-123">In the **Default customer** field, provide a valid default customer.</span></span>
1. <span data-ttu-id="f2e3b-124">Nel campo **Profilo funzionalità**, selezionare un profilo di funzionalità, se applicabile.</span><span class="sxs-lookup"><span data-stu-id="f2e3b-124">In the **Functionality profile** field, select a functionality profile if applicable.</span></span>
1. <span data-ttu-id="f2e3b-125">Nel campo **Profilo di notifica tramite posta elettronica**, fornire un profilo di notifica valido.</span><span class="sxs-lookup"><span data-stu-id="f2e3b-125">In the **Email notification profile** field, provide a valid email notification profile.</span></span>
1. <span data-ttu-id="f2e3b-126">Nel riquadro azioni selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="f2e3b-126">On the action pane, select **Save**.</span></span>

<span data-ttu-id="f2e3b-127">L'immagine seguente mostra la creazione di un nuovo canale di vendita al dettaglio.</span><span class="sxs-lookup"><span data-stu-id="f2e3b-127">The following image shows the creation of a new retail channel.</span></span>

![Nuovo canale di vendita al dettaglio](media/channel-setup-retail-1.png)

<span data-ttu-id="f2e3b-129">L'immagine seguente mostra un esempio di canale di vendita al dettaglio.</span><span class="sxs-lookup"><span data-stu-id="f2e3b-129">The following image shows an example retail channel.</span></span>

![Esempio di canale di vendita al dettaglio](media/channel-setup-retail-2.png)

## <a name="other-settings"></a><span data-ttu-id="f2e3b-131">Altre impostazioni</span><span class="sxs-lookup"><span data-stu-id="f2e3b-131">Other settings</span></span>

<span data-ttu-id="f2e3b-132">Ci sono numerose altre impostazioni facoltative che possono essere impostate nelle sezioni **Rendiconto/Chiusura** e **Varie**, in base alle esigenze del punto vendita al dettaglio.</span><span class="sxs-lookup"><span data-stu-id="f2e3b-132">There are numerous other optional settings that can be set in the **Statement/closing** and **Miscellaneous** sections, based on the needs of the retail store.</span></span>

<span data-ttu-id="f2e3b-133">Inoltre, vedere [Layout di schermo per il POS](pos-screen-layouts.md) per informazioni sulla configurazione del layout di schermo predefinito nella sezione **Layout schermo** e [Configurare e installare Retail hardware station](retail-hardware-station-configuration-installation.md) per informazioni sulla configurazione della sezione **Stazioni hardware**.</span><span class="sxs-lookup"><span data-stu-id="f2e3b-133">In addition, see [Screen layouts for the point of sale (POS)](pos-screen-layouts.md) for information on setting up the default screen layout in the **Screen layout** section and [Configure and install Retail hardware station](retail-hardware-station-configuration-installation.md) for setup information about the **Hardware stations** section.</span></span>

<span data-ttu-id="f2e3b-134">L'immagine seguente mostra un esempio di configurazione di un canale di vendita al dettaglio.</span><span class="sxs-lookup"><span data-stu-id="f2e3b-134">The following image shows an example retail channel setup configuration.</span></span>

![Esempio di configurazione di un canale di vendita al dettaglio](media/channel-setup-retail-3.png)

## <a name="additional-channel-set-up"></a><span data-ttu-id="f2e3b-136">Ulteriori operazioni di impostazione di canali</span><span class="sxs-lookup"><span data-stu-id="f2e3b-136">Additional channel set up</span></span>

<span data-ttu-id="f2e3b-137">Ulteriori elementi che devono essere impostati per un canale si trovano nel **Riquadro azioni** sotto la sezione **Imposta**.</span><span class="sxs-lookup"><span data-stu-id="f2e3b-137">There are additional items that need to be set up for a channel that can be found on the **Action pane** under the **Set up** section.</span></span>

<span data-ttu-id="f2e3b-138">Ulteriori attività necessarie per l'impostazione di un canale online includono l'impostazione di metodi di pagamento, riepilogo di cassa, modalità di consegna, conto ricavi/spese, sezioni, assegnazione del gruppo di adempimento e casseforti.</span><span class="sxs-lookup"><span data-stu-id="f2e3b-138">Additional tasks required for online channel setup include setting up payment methods, cash declaration, modes of delivery, income/expense account, sections, the fulfillment group assignment, and safes.</span></span>

<span data-ttu-id="f2e3b-139">L'immagine seguente mostra varie ulteriori opzioni di impostazione dei canali di vendita al dettaglio nella scheda **Imposta**.</span><span class="sxs-lookup"><span data-stu-id="f2e3b-139">The following image shows various additional retail channel setup options on the **Set up** tab.</span></span>

![Impostare un canale](media/channel-setup-retail-4.png)

### <a name="set-up-payment-methods"></a><span data-ttu-id="f2e3b-141">Impostare i metodi di pagamento</span><span class="sxs-lookup"><span data-stu-id="f2e3b-141">Set up payment methods</span></span>

<span data-ttu-id="f2e3b-142">Per impostare i metodi di pagamento per ogni tipo di pagamento supportato per un canale, procedere come segue.</span><span class="sxs-lookup"><span data-stu-id="f2e3b-142">To set up payment methods, for each payment type supported on this channel follow these steps.</span></span>

1. <span data-ttu-id="f2e3b-143">Nel riquadro azioni, selezionare la scheda **Imposta**, quindi selezionare **Metodi di pagamento**.</span><span class="sxs-lookup"><span data-stu-id="f2e3b-143">On the action pane, select the **Set Up** tab, then select **Payment methods**.</span></span>
1. <span data-ttu-id="f2e3b-144">Nel Riquadro azioni selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="f2e3b-144">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="f2e3b-145">Nel pannello di navigazione, selezionare un metodo di pagamento desiderato.</span><span class="sxs-lookup"><span data-stu-id="f2e3b-145">In the navigation pane, select a desired payment method.</span></span>
1. <span data-ttu-id="f2e3b-146">Nella sezione **Generale**, immettere un nome in **Nome operazione** e configurare qualsiasi altra impostazione desiderata.</span><span class="sxs-lookup"><span data-stu-id="f2e3b-146">In the **General** section, provide an **Operation name** and configure any other desired settings.</span></span>
1. <span data-ttu-id="f2e3b-147">Configurare eventuali impostazioni aggiuntive come necessario per il tipo di pagamento.</span><span class="sxs-lookup"><span data-stu-id="f2e3b-147">Configure any additional settings as required for the payment type.</span></span>
1. <span data-ttu-id="f2e3b-148">Nel riquadro azioni selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="f2e3b-148">On the action pane, select **Save**.</span></span>

<span data-ttu-id="f2e3b-149">L'immagine seguente illustra un esempio di metodo di pagamento in contanti.</span><span class="sxs-lookup"><span data-stu-id="f2e3b-149">The following image shows an example of a cash payment method.</span></span>

![Esempio di metodi di pagamento](media/channel-setup-retail-5.png)

### <a name="set-up-cash-declaration"></a><span data-ttu-id="f2e3b-151">Impostare il riepilogo di cassa</span><span class="sxs-lookup"><span data-stu-id="f2e3b-151">Set up cash declaration</span></span>

1. <span data-ttu-id="f2e3b-152">Nel riquadro azioni, selezionare la scheda **Imposta**, quindi selezionare **Riepilogo di cassa**.</span><span class="sxs-lookup"><span data-stu-id="f2e3b-152">On the action pane, select the **Set Up** tab, and then select **Cash declaration**.</span></span>
1. <span data-ttu-id="f2e3b-153">Nel riquadro azioni, selezionare **Nuovo** e quindi creare tutte le denominazioni **Moneta** e **Banconota** applicabili.</span><span class="sxs-lookup"><span data-stu-id="f2e3b-153">On the action pane, select **New**, and then create all **Coin** and **Note** denominations that are applicable.</span></span>

<span data-ttu-id="f2e3b-154">L'immagine seguente illustra un esempio di riepilogo di cassa.</span><span class="sxs-lookup"><span data-stu-id="f2e3b-154">The following image shows an example of a cash declaration.</span></span>

![Impostare riepiloghi di cassa](media/channel-setup-retail-6.png)

### <a name="set-up-modes-of-delivery"></a><span data-ttu-id="f2e3b-156">Impostare le modalità di consegna</span><span class="sxs-lookup"><span data-stu-id="f2e3b-156">Set up modes of delivery</span></span>

<span data-ttu-id="f2e3b-157">È possibile visualizzare le modalità di consegna configurate selezionando **Modalità di consegna** nella scheda **Imposta** del **Riquadro azioni**.</span><span class="sxs-lookup"><span data-stu-id="f2e3b-157">You can see the configured modes of delivery by selecting **Modes of delivery** from the **Set up** tab on the **Action pane**.</span></span>  

<span data-ttu-id="f2e3b-158">Per modificare o aggiungere una modalità di consegna, attenersi alla seguente procedura.</span><span class="sxs-lookup"><span data-stu-id="f2e3b-158">To change or add a mode of delivery, follow these steps.</span></span>

1. <span data-ttu-id="f2e3b-159">Nel pannello di navigazione, selezionare **Moduli \> Gestione inventario \> Modalità di consegna**.</span><span class="sxs-lookup"><span data-stu-id="f2e3b-159">In the navigation pane, go to **Modules \> Inventory management \> Modes of delivery**.</span></span>
1. <span data-ttu-id="f2e3b-160">Nel riquadro azioni, selezionare **Nuovo** per creare una nuova modalità di consegna o selezionarne una esistente.</span><span class="sxs-lookup"><span data-stu-id="f2e3b-160">On the action pane, select **New** to create a new mode of delivery, or select an existing mode.</span></span>
1. <span data-ttu-id="f2e3b-161">Nella sezione **Canali di vendita al dettaglio**, selezionare **Aggiungi riga** per aggiungere il canale.</span><span class="sxs-lookup"><span data-stu-id="f2e3b-161">In the **Retail channels** section, select **Add line** to add the channel.</span></span> <span data-ttu-id="f2e3b-162">Aggiungere canali utilizzando nodi dell'organizzazione anziché aggiungere ogni canale singolarmente può semplificare questa operazione.</span><span class="sxs-lookup"><span data-stu-id="f2e3b-162">Adding channels using organization nodes instead of adding each channel individually can streamline adding channels.</span></span>

<span data-ttu-id="f2e3b-163">L'immagine seguente illustra un esempio di modalità di consegna.</span><span class="sxs-lookup"><span data-stu-id="f2e3b-163">The following image shows an example of a mode of delivery.</span></span>

![Impostare le modalità di consegna](media/channel-setup-retail-7.png)

### <a name="set-up-incomeexpense-account"></a><span data-ttu-id="f2e3b-165">Impostare un conto ricavi/spese</span><span class="sxs-lookup"><span data-stu-id="f2e3b-165">Set up income/expense account</span></span>

<span data-ttu-id="f2e3b-166">Per impostare un conto ricavi/spese, effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="f2e3b-166">To set up income/expense account, follow these steps.</span></span>

1. <span data-ttu-id="f2e3b-167">Nel riquadro azioni, selezionare la scheda **Imposta**, quindi selezionare **Conto ricavi/spese**.</span><span class="sxs-lookup"><span data-stu-id="f2e3b-167">On the action pane, select the **Set Up** tab, and then select **Income/Expense account**.</span></span>
1. <span data-ttu-id="f2e3b-168">Nel Riquadro azioni selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="f2e3b-168">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="f2e3b-169">Sotto **Nome**, immettere un nome.</span><span class="sxs-lookup"><span data-stu-id="f2e3b-169">Under **Name**, enter a name.</span></span>
1. <span data-ttu-id="f2e3b-170">Sotto **Nome di ricerca** immettere un nome di ricerca.</span><span class="sxs-lookup"><span data-stu-id="f2e3b-170">Under **Search name**, enter a search name.</span></span>
1. <span data-ttu-id="f2e3b-171">Sotto **Tipo di conto**, immettere un tipo di conto.</span><span class="sxs-lookup"><span data-stu-id="f2e3b-171">Under **Account type**, enter the account type.</span></span>
1. <span data-ttu-id="f2e3b-172">Immettere il testo per **Riga messaggio 1**, **Riga messaggio 2**, **Testo distinta 1** e **Testo distinta 2** come necessario.</span><span class="sxs-lookup"><span data-stu-id="f2e3b-172">Enter text for **Message line 1**, **Message line 2**, **Slip text 1**, and **Slip text 2** as needed.</span></span>
1. <span data-ttu-id="f2e3b-173">Sotto **Registrazione**, immettere le informazioni di registrazione.</span><span class="sxs-lookup"><span data-stu-id="f2e3b-173">Under **Posting**, enter posting information.</span></span>
1. <span data-ttu-id="f2e3b-174">Nel riquadro azioni selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="f2e3b-174">On the action pane, select **Save**.</span></span>

<span data-ttu-id="f2e3b-175">L'immagine seguente mostra un esempio di conto ricavi/spese.</span><span class="sxs-lookup"><span data-stu-id="f2e3b-175">The following image shows an example of an income/expense account.</span></span>

![Impostare conti ricavi/spese](media/channel-setup-retail-8.png)

### <a name="set-up-sections"></a><span data-ttu-id="f2e3b-177">Impostare sezioni</span><span class="sxs-lookup"><span data-stu-id="f2e3b-177">Set up sections</span></span>

<span data-ttu-id="f2e3b-178">Per impostare sezioni, effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="f2e3b-178">To set up sections, follow these steps.</span></span>

1. <span data-ttu-id="f2e3b-179">Nel riquadro azioni, selezionare la scheda **Imposta**, quindi fare clic su **Sezioni**.</span><span class="sxs-lookup"><span data-stu-id="f2e3b-179">On the action pane, select the **Set Up** tab and click **Sections**.</span></span>
1. <span data-ttu-id="f2e3b-180">Nel Riquadro azioni selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="f2e3b-180">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="f2e3b-181">Sotto **Numero sezione**, immettere un numero di sezione.</span><span class="sxs-lookup"><span data-stu-id="f2e3b-181">Under **Section number**, enter a section number.</span></span>
1. <span data-ttu-id="f2e3b-182">Sotto **Descrizione** immettere una descrizione.</span><span class="sxs-lookup"><span data-stu-id="f2e3b-182">Under **Description**, enter a description.</span></span>
1. <span data-ttu-id="f2e3b-183">Sotto **Dimensioni sezione**, immettere le dimensioni della sezione.</span><span class="sxs-lookup"><span data-stu-id="f2e3b-183">Under **Section size**, enter a section size.</span></span>
1. <span data-ttu-id="f2e3b-184">Configurare impostazioni aggiuntive per **Generale** e **Statistiche vendite** come necessario.</span><span class="sxs-lookup"><span data-stu-id="f2e3b-184">Configure additional settings for **General** and **Sales statistics** as needed.</span></span>
1. <span data-ttu-id="f2e3b-185">Nel riquadro azioni selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="f2e3b-185">On the action pane, select **Save**.</span></span>

### <a name="set-up-a-fulfillment-group-assignment"></a><span data-ttu-id="f2e3b-186">Impostare l'assegnazione di un gruppo di adempimento</span><span class="sxs-lookup"><span data-stu-id="f2e3b-186">Set up a fulfillment group assignment</span></span>

<span data-ttu-id="f2e3b-187">Per impostare l'assegnazione di un gruppo di adempimento, effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="f2e3b-187">To set up a fulfillment group assignment, follow these steps.</span></span>

1. <span data-ttu-id="f2e3b-188">Nel riquadro azioni, selezionare la scheda **Imposta**, quindi selezionare **Assegnazione gruppo di adempimento**.</span><span class="sxs-lookup"><span data-stu-id="f2e3b-188">On the action pane, select the **Set up** tab, then select **Fulfillment group assignment**.</span></span>
1. <span data-ttu-id="f2e3b-189">Nel Riquadro azioni selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="f2e3b-189">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="f2e3b-190">Nell'elenco a discesa **Gruppo di adempimento**, selezionare un gruppo di adempimento.</span><span class="sxs-lookup"><span data-stu-id="f2e3b-190">In the **Fulfillment group** drop-down list, select a fulfillment group.</span></span>
1. <span data-ttu-id="f2e3b-191">Nel campo **Descrizione**, immettere una descrizione.</span><span class="sxs-lookup"><span data-stu-id="f2e3b-191">In the **Description** drop-down list, enter a description.</span></span>
1. <span data-ttu-id="f2e3b-192">Nel riquadro azioni selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="f2e3b-192">On the action pane, select **Save**</span></span>

<span data-ttu-id="f2e3b-193">L'immagine seguente mostra un esempio di impostazione dell'assegnazione di un gruppo di adempimento.</span><span class="sxs-lookup"><span data-stu-id="f2e3b-193">The following image shows an example of a fulfillment group assignment setup.</span></span>

![Impostare l'assegnazione di un gruppo di adempimento](media/channel-setup-retail-9.png)

### <a name="set-up-safes"></a><span data-ttu-id="f2e3b-195">Impostare casseforti</span><span class="sxs-lookup"><span data-stu-id="f2e3b-195">Set up safes</span></span>

<span data-ttu-id="f2e3b-196">Per impostare casseforti, effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="f2e3b-196">To set up safes, follow these steps.</span></span>

1. <span data-ttu-id="f2e3b-197">Nel riquadro azioni, selezionare la scheda **Imposta**, quindi fare clic su **Casseforti**.</span><span class="sxs-lookup"><span data-stu-id="f2e3b-197">On the action pane, select the **Set Up** tab and click **Safes**.</span></span>
1. <span data-ttu-id="f2e3b-198">Nel Riquadro azioni selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="f2e3b-198">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="f2e3b-199">Immettere un nome per la cassaforte.</span><span class="sxs-lookup"><span data-stu-id="f2e3b-199">Enter a name for the safe.</span></span>
1. <span data-ttu-id="f2e3b-200">Nel riquadro azioni selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="f2e3b-200">On the action pane, select **Save**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="f2e3b-201">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="f2e3b-201">Additional resources</span></span>

[<span data-ttu-id="f2e3b-202">Panoramica dei canali</span><span class="sxs-lookup"><span data-stu-id="f2e3b-202">Channels overview</span></span>](channels-overview.md)

[<span data-ttu-id="f2e3b-203">Prerequisiti di impostazione dei canali</span><span class="sxs-lookup"><span data-stu-id="f2e3b-203">Channel setup prerequisites</span></span>](channels-prerequisites.md)

[<span data-ttu-id="f2e3b-204">Impostare un canale online</span><span class="sxs-lookup"><span data-stu-id="f2e3b-204">Set up an online channel</span></span>](channel-setup-online.md)

[<span data-ttu-id="f2e3b-205">Impostare un canale servizio clienti</span><span class="sxs-lookup"><span data-stu-id="f2e3b-205">Set up a call center channel</span></span>](channel-setup-callcenter.md)

