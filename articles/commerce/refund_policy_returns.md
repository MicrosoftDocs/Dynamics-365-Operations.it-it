---
title: Creare e aggiornare una politica su resi e rimborsi per un canale
description: Questo argomento spiega come impostare una politica su resi e rimborsi per un canale.
author: ShalabhjainMSFT
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rapraj
ms.search.validFrom: 2020-01-21
ms.dyn365.ops.version: Retail 10.0.9 update
ms.openlocfilehash: 03e46a7f8d110bd9ef3b353b150116bbf8a70ad5
ms.sourcegitcommit: c88b54ba13a4dfe39b844ffaced4dc435560c47d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2021
ms.locfileid: "5478118"
---
# <a name="create-and-update-a-returns-and-refunds-policy-for-a-channel"></a><span data-ttu-id="0038f-103">Creare e aggiornare i criteri per resi e rimborsi di un canale</span><span class="sxs-lookup"><span data-stu-id="0038f-103">Create and update a returns and refunds policy for a channel</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="0038f-104">La politica sui resi in Dynamics 365 Commerce consente ai rivenditori di impostare le applicazioni per le quali le offerte di pagamento possono essere consentite per l'elaborazione di un reso su un dispositivo POS.</span><span class="sxs-lookup"><span data-stu-id="0038f-104">The channel return policy in Dynamics 365 Commerce enables retailers to set enforcements on which payment tenders can be allowed for processing a return on a point of sale (POS) device.</span></span>  

<span data-ttu-id="0038f-105">Questo argomento descrive i passaggi per impostare una politica su resi e rimborsi per un canale.</span><span class="sxs-lookup"><span data-stu-id="0038f-105">This topic describes the steps to set up a returns and refunds policy for a channel.</span></span>

<span data-ttu-id="0038f-106">L'ambito della politica è attualmente limitato alla definizione delle offerte di pagamento che possono essere consentite per un canale.</span><span class="sxs-lookup"><span data-stu-id="0038f-106">The scope of the policy is currently limited to setting the payment tenders that can be allowed for a channel.</span></span> <span data-ttu-id="0038f-107">L'elenco "Consentite" si basa sui metodi di pagamento utilizzati per effettuare l'acquisto.</span><span class="sxs-lookup"><span data-stu-id="0038f-107">The "allowed" list is based on the payment methods used to make the purchase.</span></span> <span data-ttu-id="0038f-108">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="0038f-108">For example:</span></span>

- <span data-ttu-id="0038f-109">Se un acquisto è stato effettuato utilizzando una gift card, la politica del punto vendita prevede di elaborare i rimborsi solo su una nuova gift card o per fornire un buono acquisto.</span><span class="sxs-lookup"><span data-stu-id="0038f-109">If a purchase was made using a gift card, the store policy is to process refunds only to a new gift card or to give store credit.</span></span> 
- <span data-ttu-id="0038f-110">Se una vendita viene effettuata in contanti, le opzioni consentite per il rimborso sono contanti, gift card e conto cliente, ma non la carta di credito.</span><span class="sxs-lookup"><span data-stu-id="0038f-110">If a sale is made using cash, the options allowed for refund are cash, gift card, and customer account, but not credit card.</span></span> 


## <a name="enable-return-policy"></a><span data-ttu-id="0038f-111">Abilitare la politica sui resi</span><span class="sxs-lookup"><span data-stu-id="0038f-111">Enable return policy</span></span>

<span data-ttu-id="0038f-112">Per abilitare la politica sui resi, procedere come segue:</span><span class="sxs-lookup"><span data-stu-id="0038f-112">To enable the channel return policy functionality, do the following:</span></span>

1. <span data-ttu-id="0038f-113">Andare all'area di lavoro **Gestione funzionalità** in Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="0038f-113">Go to the **Feature Management** workspace in Dynamics 365 Commerce.</span></span>
2. <span data-ttu-id="0038f-114">Cercare la funzionalità **Abilita politiche sui resi del canale** nell'elenco dei nomi di funzionalità.</span><span class="sxs-lookup"><span data-stu-id="0038f-114">Search for the **Enable channel return policies** feature in the list of feature names.</span></span>
3. <span data-ttu-id="0038f-115">Selezionare **Abilita ora**.</span><span class="sxs-lookup"><span data-stu-id="0038f-115">Select **Enable now**.</span></span> 

## <a name="configure-return-policy"></a><span data-ttu-id="0038f-116">Configurare la politica sui resi</span><span class="sxs-lookup"><span data-stu-id="0038f-116">Configure return policy</span></span>

<span data-ttu-id="0038f-117">Seguire questi passaggi per configurare una politica sui resi per un punto vendita al dettaglio o un canale di vendita al dettaglio online.</span><span class="sxs-lookup"><span data-stu-id="0038f-117">Follow these steps to configure a return policy for a retail store or online retail channel.</span></span>

1. <span data-ttu-id="0038f-118">Andare a **Retail e Commerce** \> **Impostazione canale** \> **Resi** \> **Politica sui resi del canale**.</span><span class="sxs-lookup"><span data-stu-id="0038f-118">Go to **Retail and Commerce** \> **Channel Setup** \> **Returns** \> **Channel return policy**.</span></span>

2. <span data-ttu-id="0038f-119">Selezionare **Nuovo** per creare un nuovo modello di politica sui resi.</span><span class="sxs-lookup"><span data-stu-id="0038f-119">Select **New** to create a new return policy template.</span></span> <span data-ttu-id="0038f-120">Per utilizzare un modello esistente, selezionare il modello nel riquadro sinistro.</span><span class="sxs-lookup"><span data-stu-id="0038f-120">To use an existing template, select the template in the left pane.</span></span> <span data-ttu-id="0038f-121">Per i nuovi modelli, aggiungere un nome e una descrizione che consentiranno di identificare la politica quando viene applicata al canale.</span><span class="sxs-lookup"><span data-stu-id="0038f-121">For new templates, add a name and description that will help you identify the policy when it is being applied to the channel.</span></span>

   <span data-ttu-id="0038f-122">![Aggiungere un nuova politica sui resi](media/Return-policy-page1.png "Aggiungere un nuova politica sui resi")</span><span class="sxs-lookup"><span data-stu-id="0038f-122">![Add new return policy](media/Return-policy-page1.png "Add new return rolicy")</span></span>
     
   
3. <span data-ttu-id="0038f-123">Nella sezione **Metodi di pagamento per rimborso consentiti**, definire le offerte di pagamento per resi **Consentite** specifiche a ogni metodo di pagamento.</span><span class="sxs-lookup"><span data-stu-id="0038f-123">In the **Allowed refund payment methods** section, define **Allowed** return payment tenders that are specific to each payment method.</span></span>
   <span data-ttu-id="0038f-124">![Aggiungere metodi di pagamento](media/Return-policy-page2.PNG "Impostare i metodi di pagamento consentiti per tipo di pagamento")</span><span class="sxs-lookup"><span data-stu-id="0038f-124">![Add payment methods](media/Return-policy-page2.PNG "Set allowed payment methods per payment type")</span></span>
   
    > [!IMPORTANT]
    > - <span data-ttu-id="0038f-125">I metodi di pagamento sono derivati da quelli impostati per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="0038f-125">The payment methods are derived from the payment methods set for the organization.</span></span>
    > - <span data-ttu-id="0038f-126">L'aggiunta di un tipo di offerta di reso consentita per ogni metodo di pagamento elencato garantirà la possibilità di effettuare i resi per il tipo di offerta di reso consentito.</span><span class="sxs-lookup"><span data-stu-id="0038f-126">Adding an allowed return tender type for each listed payment method will ensure that returns can be made to the allowed return tender type.</span></span>
    
4. <span data-ttu-id="0038f-127">Associare il modello di politica sui resi ai punti vendita in cui verrà utilizzato.</span><span class="sxs-lookup"><span data-stu-id="0038f-127">Associate the return policy template with the stores where it will be used.</span></span> <span data-ttu-id="0038f-128">Selezionare **Aggiungi** nella scheda **Canali di vendita al dettaglio** e associare i canali disponibili.</span><span class="sxs-lookup"><span data-stu-id="0038f-128">Select **Add** in the **Retail Channels** tab and associate the available channels.</span></span> 

    - <span data-ttu-id="0038f-129">Nella finestra di dialogo **Scegli nodi organizzazione**, selezionare i punti vendita, le aree geografiche e le organizzazioni a cui il modello deve essere associato.</span><span class="sxs-lookup"><span data-stu-id="0038f-129">In the **Choose organization nodes** dialog box, select the stores, regions, and organizations that the template should be associated with.</span></span>
    - <span data-ttu-id="0038f-130">Un solo modello di politica sui resi può essere associato a ogni punto vendita.</span><span class="sxs-lookup"><span data-stu-id="0038f-130">Only one return policy template can be associated with each store.</span></span>
    - <span data-ttu-id="0038f-131">Utilizzare i pulsanti freccia per selezionare punti vendita, aree geoagrafiche o organizzazioni.</span><span class="sxs-lookup"><span data-stu-id="0038f-131">Use the arrow buttons to select stores, regions, or organizations.</span></span>
    - <span data-ttu-id="0038f-132">La data di entrata in vigore della politica sarà la data alla quale le politiche vengono applicate ai canali e vengono eseguiti i processi del canale.</span><span class="sxs-lookup"><span data-stu-id="0038f-132">The effective date on the policy will be the date on which the policies are applied to the channels and the channel jobs are run.</span></span> 

    <span data-ttu-id="0038f-133">![Finestra di dialogo Scegli nodi organizzazione](media/Return-policy-page3.PNG "Finestra di dialogo Scegli nodi organizzazione")</span><span class="sxs-lookup"><span data-stu-id="0038f-133">![Choose organization nodes dialog box](media/Return-policy-page3.PNG "Choose organization nodes dialog box")</span></span>

5. <span data-ttu-id="0038f-134">Nella pagina **Programmazione della distribuzione**, eseguire il processo **1070** per rendere la politica sui resi del canale disponibile nel POS.</span><span class="sxs-lookup"><span data-stu-id="0038f-134">On the **Distribution schedule** page, run the **1070** job to make the channel return policy available to the POS.</span></span>

## <a name="preview-the-channel-return-policy-in-the-pos"></a><span data-ttu-id="0038f-135">Visualizzare in anteprima la politica sui resi del canale nel POS</span><span class="sxs-lookup"><span data-stu-id="0038f-135">Preview the channel return policy in the POS</span></span>

<span data-ttu-id="0038f-136">Seguire i passaggi in uno dei seguenti esempi per visualizzare i tipi di offerte di reso consentite nel POS.</span><span class="sxs-lookup"><span data-stu-id="0038f-136">Follow the steps in either of the following examples to view the allowed return tender types in POS.</span></span>

1. <span data-ttu-id="0038f-137">Accedere al POS come cassiere o responsabile.</span><span class="sxs-lookup"><span data-stu-id="0038f-137">Sign in to the POS as a cashier or manager.</span></span>
2. <span data-ttu-id="0038f-138">Sotto **Turno e cassetto**, selezionare **Mostra giornale di registrazione**.</span><span class="sxs-lookup"><span data-stu-id="0038f-138">Under **Shift and Drawer**, select **Show journal**.</span></span>
3. <span data-ttu-id="0038f-139">Seleziona la transazione che fa parte del reso.</span><span class="sxs-lookup"><span data-stu-id="0038f-139">Select the transaction that is part of the return.</span></span> 
4. <span data-ttu-id="0038f-140">Selezionare gli articoli da rimborsare e scegliere il metodo di pagamento.</span><span class="sxs-lookup"><span data-stu-id="0038f-140">Select the items to refund, and choose the payment method.</span></span>  
- <span data-ttu-id="0038f-141">Se l'offerta di pagamento selezionata è nell'elenco dei tipi di offerte di reso consentiti, il cassiere può completare la transazione.</span><span class="sxs-lookup"><span data-stu-id="0038f-141">If the payment tender selected is in the allowed list of return tender types, the cashier can complete the transaction.</span></span>
- <span data-ttu-id="0038f-142">Se l'offerta di pagamento selezionata non è consentita, viene visualizzato un messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="0038f-142">If the payment tender selected is not allowed, an error message is displayed.</span></span>
- <span data-ttu-id="0038f-143">Selezionare **Importo dovuto** per visualizzare un elenco di tutti i tipi di offerte di reso consentiti.</span><span class="sxs-lookup"><span data-stu-id="0038f-143">Select **Amount Due** to display a list of all the allowed return tender types.</span></span>

<span data-ttu-id="0038f-144">oppure</span><span class="sxs-lookup"><span data-stu-id="0038f-144">-or-</span></span>

1. <span data-ttu-id="0038f-145">Accedere al POS come cassiere o responsabile.</span><span class="sxs-lookup"><span data-stu-id="0038f-145">Sign in to the POS as a cashier or manager.</span></span>
2. <span data-ttu-id="0038f-146">Selezionare **Transazione di reso** e immettere l'ID ricevuta utilizzando un lettore di codici a barre oppure manualmente.</span><span class="sxs-lookup"><span data-stu-id="0038f-146">Select **Return Transaction** and enter the receipt ID using a barcode scan or by manual entry.</span></span> 
3. <span data-ttu-id="0038f-147">Seleziona la transazione che fa parte del reso.</span><span class="sxs-lookup"><span data-stu-id="0038f-147">Select the transaction that is part of the return.</span></span> 
4. <span data-ttu-id="0038f-148">Selezionare gli articoli da rimborsare e scegliere il metodo di pagamento.</span><span class="sxs-lookup"><span data-stu-id="0038f-148">Select the items to refund, and choose the payment method.</span></span>  
- <span data-ttu-id="0038f-149">Se l'offerta di pagamento selezionata è nell'elenco dei tipi di offerte di reso consentiti, il cassiere può completare la transazione.</span><span class="sxs-lookup"><span data-stu-id="0038f-149">If the payment tender selected is in the allowed list of return tender types, the cashier can complete the transaction.</span></span>
- <span data-ttu-id="0038f-150">Se l'offerta di pagamento selezionata non è consentita, viene visualizzato un messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="0038f-150">If the payment tender selected is not allowed, an error message is displayed.</span></span>
- <span data-ttu-id="0038f-151">Selezionare **Importo dovuto** per visualizzare un elenco di tutti i tipi di offerte di reso consentiti.</span><span class="sxs-lookup"><span data-stu-id="0038f-151">Select **Amount Due** to display a list of all the allowed return tender types.</span></span>

<span data-ttu-id="0038f-152">![Rimborso non consentito](media/Return-policy-page6.png "Tipo di rimborso non consentito")</span><span class="sxs-lookup"><span data-stu-id="0038f-152">![Refund not allowed](media/Return-policy-page6.png "Refund type not allowed")</span></span>



<span data-ttu-id="0038f-153">![Elenco di metodi di pagamento](media/Return-policy-page5.PNG "Tipo di rimborso consentito")</span><span class="sxs-lookup"><span data-stu-id="0038f-153">![List of payment methods](media/Return-policy-page5.PNG "Refund types allowed")</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
