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
ms.search.scope: Operations, Retail
ms.custom: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rapraj
ms.search.validFrom: 2020-01-21
ms.dyn365.ops.version: Retail 10.0.9 update
ms.openlocfilehash: c2a9325f09ffe43c3436b7e0ca2ab511e1f57f83
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4413556"
---
# <a name="create-and-update-a-returns-and-refunds-policy-for-a-channel"></a><span data-ttu-id="27ff1-103">Creare e aggiornare una politica su resi e rimborsi per un canale</span><span class="sxs-lookup"><span data-stu-id="27ff1-103">Create and update a returns and refunds policy for a channel</span></span>

[!include [banner](includes/banner.md)]

## <a name="overview"></a><span data-ttu-id="27ff1-104">Panoramica</span><span class="sxs-lookup"><span data-stu-id="27ff1-104">Overview</span></span>

<span data-ttu-id="27ff1-105">La politica sui resi in Dynamics 365 Commerce consente ai rivenditori di impostare le applicazioni per le quali le offerte di pagamento possono essere consentite per l'elaborazione di un reso su un dispositivo POS.</span><span class="sxs-lookup"><span data-stu-id="27ff1-105">The channel return policy in Dynamics 365 Commerce enables retailers to set enforcements on which payment tenders can be allowed for processing a return on a point of sale (POS) device.</span></span>  

<span data-ttu-id="27ff1-106">Questo argomento descrive i passaggi per impostare una politica su resi e rimborsi per un canale.</span><span class="sxs-lookup"><span data-stu-id="27ff1-106">This topic describes the steps to set up a returns and refunds policy for a channel.</span></span>

<span data-ttu-id="27ff1-107">L'ambito della politica è attualmente limitato alla definizione delle offerte di pagamento che possono essere consentite per un canale.</span><span class="sxs-lookup"><span data-stu-id="27ff1-107">The scope of the policy is currently limited to setting the payment tenders that can be allowed for a channel.</span></span> <span data-ttu-id="27ff1-108">L'elenco "Consentite" si basa sui metodi di pagamento utilizzati per effettuare l'acquisto.</span><span class="sxs-lookup"><span data-stu-id="27ff1-108">The "allowed" list is based on the payment methods used to make the purchase.</span></span> <span data-ttu-id="27ff1-109">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="27ff1-109">For example:</span></span>

- <span data-ttu-id="27ff1-110">Se un acquisto è stato effettuato utilizzando una gift card, la politica del punto vendita prevede di elaborare i rimborsi solo su una nuova gift card o per fornire un buono acquisto.</span><span class="sxs-lookup"><span data-stu-id="27ff1-110">If a purchase was made using a gift card, the store policy is to process refunds only to a new gift card or to give store credit.</span></span> 
- <span data-ttu-id="27ff1-111">Se una vendita viene effettuata in contanti, le opzioni consentite per il rimborso sono contanti, gift card e conto cliente, ma non la carta di credito.</span><span class="sxs-lookup"><span data-stu-id="27ff1-111">If a sale is made using cash, the options allowed for refund are cash, gift card, and customer account, but not credit card.</span></span> 


## <a name="enable-return-policy"></a><span data-ttu-id="27ff1-112">Abilitare la politica sui resi</span><span class="sxs-lookup"><span data-stu-id="27ff1-112">Enable return policy</span></span>

<span data-ttu-id="27ff1-113">Per abilitare la politica sui resi, procedere come segue:</span><span class="sxs-lookup"><span data-stu-id="27ff1-113">To enable the channel return policy functionality, do the following:</span></span>

1. <span data-ttu-id="27ff1-114">Andare all'area di lavoro **Gestione funzionalità** in Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="27ff1-114">Go to the **Feature Management** workspace in Dynamics 365 Commerce.</span></span>
2. <span data-ttu-id="27ff1-115">Cercare la funzionalità **Abilita politiche sui resi del canale** nell'elenco dei nomi di funzionalità.</span><span class="sxs-lookup"><span data-stu-id="27ff1-115">Search for the **Enable channel return policies** feature in the list of feature names.</span></span>
3. <span data-ttu-id="27ff1-116">Selezionare **Abilita ora**.</span><span class="sxs-lookup"><span data-stu-id="27ff1-116">Select **Enable now**.</span></span> 

## <a name="configure-return-policy"></a><span data-ttu-id="27ff1-117">Configurare la politica sui resi</span><span class="sxs-lookup"><span data-stu-id="27ff1-117">Configure return policy</span></span>

<span data-ttu-id="27ff1-118">Seguire questi passaggi per configurare una politica sui resi per un punto vendita al dettaglio o un canale di vendita al dettaglio online.</span><span class="sxs-lookup"><span data-stu-id="27ff1-118">Follow these steps to configure a return policy for a retail store or online retail channel.</span></span>

1. <span data-ttu-id="27ff1-119">Andare a **Retail e Commerce** \> **Impostazione canale** \> **Resi** \> **Politica sui resi del canale**.</span><span class="sxs-lookup"><span data-stu-id="27ff1-119">Go to **Retail and Commerce** \> **Channel Setup** \> **Returns** \> **Channel return policy**.</span></span>

2. <span data-ttu-id="27ff1-120">Selezionare **Nuovo** per creare un nuovo modello di politica sui resi.</span><span class="sxs-lookup"><span data-stu-id="27ff1-120">Select **New** to create a new return policy template.</span></span> <span data-ttu-id="27ff1-121">Per utilizzare un modello esistente, selezionare il modello nel riquadro sinistro.</span><span class="sxs-lookup"><span data-stu-id="27ff1-121">To use an existing template, select the template in the left pane.</span></span> <span data-ttu-id="27ff1-122">Per i nuovi modelli, aggiungere un nome e una descrizione che consentiranno di identificare la politica quando viene applicata al canale.</span><span class="sxs-lookup"><span data-stu-id="27ff1-122">For new templates, add a name and description that will help you identify the policy when it is being applied to the channel.</span></span>

   <span data-ttu-id="27ff1-123">![Aggiungere un nuova politica sui resi](media/Return-policy-page1.png "Aggiungere un nuova politica sui resi")</span><span class="sxs-lookup"><span data-stu-id="27ff1-123">![Add new return policy](media/Return-policy-page1.png "Add new return rolicy")</span></span>
     
   
3. <span data-ttu-id="27ff1-124">Nella sezione **Metodi di pagamento per rimborso consentiti**, definire le offerte di pagamento per resi **Consentite** specifiche a ogni metodo di pagamento.</span><span class="sxs-lookup"><span data-stu-id="27ff1-124">In the **Allowed refund payment methods** section, define **Allowed** return payment tenders that are specific to each payment method.</span></span>
   <span data-ttu-id="27ff1-125">![Aggiungere metodi di pagamento](media/Return-policy-page2.PNG "Impostare i metodi di pagamento consentiti per tipo di pagamento")</span><span class="sxs-lookup"><span data-stu-id="27ff1-125">![Add payment methods](media/Return-policy-page2.PNG "Set allowed payment methods per payment type")</span></span>
   
    > [!IMPORTANT]
    > - <span data-ttu-id="27ff1-126">I metodi di pagamento sono derivati da quelli impostati per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="27ff1-126">The payment methods are derived from the payment methods set for the organization.</span></span>
    > - <span data-ttu-id="27ff1-127">L'aggiunta di un tipo di offerta di reso consentita per ogni metodo di pagamento elencato garantirà la possibilità di effettuare i resi per il tipo di offerta di reso consentito.</span><span class="sxs-lookup"><span data-stu-id="27ff1-127">Adding an allowed return tender type for each listed payment method will ensure that returns can be made to the allowed return tender type.</span></span>
    
4. <span data-ttu-id="27ff1-128">Associare il modello di politica sui resi ai punti vendita in cui verrà utilizzato.</span><span class="sxs-lookup"><span data-stu-id="27ff1-128">Associate the return policy template with the stores where it will be used.</span></span> <span data-ttu-id="27ff1-129">Selezionare **Aggiungi** nella scheda **Canali di vendita al dettaglio** e associare i canali disponibili.</span><span class="sxs-lookup"><span data-stu-id="27ff1-129">Select **Add** in the **Retail Channels** tab and associate the available channels.</span></span> 

    - <span data-ttu-id="27ff1-130">Nella finestra di dialogo **Scegli nodi organizzazione**, selezionare i punti vendita, le aree geografiche e le organizzazioni a cui il modello deve essere associato.</span><span class="sxs-lookup"><span data-stu-id="27ff1-130">In the **Choose organization nodes** dialog box, select the stores, regions, and organizations that the template should be associated with.</span></span>
    - <span data-ttu-id="27ff1-131">Un solo modello di politica sui resi può essere associato a ogni punto vendita.</span><span class="sxs-lookup"><span data-stu-id="27ff1-131">Only one return policy template can be associated with each store.</span></span>
    - <span data-ttu-id="27ff1-132">Utilizzare i pulsanti freccia per selezionare punti vendita, aree geoagrafiche o organizzazioni.</span><span class="sxs-lookup"><span data-stu-id="27ff1-132">Use the arrow buttons to select stores, regions, or organizations.</span></span>
    - <span data-ttu-id="27ff1-133">La data di entrata in vigore della politica sarà la data alla quale le politiche vengono applicate ai canali e vengono eseguiti i processi del canale.</span><span class="sxs-lookup"><span data-stu-id="27ff1-133">The effective date on the policy will be the date on which the policies are applied to the channels and the channel jobs are run.</span></span> 

    <span data-ttu-id="27ff1-134">![Finestra di dialogo Scegli nodi organizzazione](media/Return-policy-page3.PNG "Finestra di dialogo Scegli nodi organizzazione")</span><span class="sxs-lookup"><span data-stu-id="27ff1-134">![Choose organization nodes dialog box](media/Return-policy-page3.PNG "Choose organization nodes dialog box")</span></span>

5. <span data-ttu-id="27ff1-135">Nella pagina **Programmazione della distribuzione**, eseguire il processo **1070** per rendere la politica sui resi del canale disponibile nel POS.</span><span class="sxs-lookup"><span data-stu-id="27ff1-135">On the **Distribution schedule** page, run the **1070** job to make the channel return policy available to the POS.</span></span>

## <a name="preview-the-channel-return-policy-in-the-pos"></a><span data-ttu-id="27ff1-136">Visualizzare in anteprima la politica sui resi del canale nel POS</span><span class="sxs-lookup"><span data-stu-id="27ff1-136">Preview the channel return policy in the POS</span></span>

<span data-ttu-id="27ff1-137">Seguire i passaggi in uno dei seguenti esempi per visualizzare i tipi di offerte di reso consentite nel POS.</span><span class="sxs-lookup"><span data-stu-id="27ff1-137">Follow the steps in either of the following examples to view the allowed return tender types in POS.</span></span>

1. <span data-ttu-id="27ff1-138">Accedere al POS come cassiere o responsabile.</span><span class="sxs-lookup"><span data-stu-id="27ff1-138">Sign in to the POS as a cashier or manager.</span></span>
2. <span data-ttu-id="27ff1-139">Sotto **Turno e cassetto**, selezionare **Mostra giornale di registrazione**.</span><span class="sxs-lookup"><span data-stu-id="27ff1-139">Under **Shift and Drawer**, select **Show journal**.</span></span>
3. <span data-ttu-id="27ff1-140">Seleziona la transazione che fa parte del reso.</span><span class="sxs-lookup"><span data-stu-id="27ff1-140">Select the transaction that is part of the return.</span></span> 
4. <span data-ttu-id="27ff1-141">Selezionare gli articoli da rimborsare e scegliere il metodo di pagamento.</span><span class="sxs-lookup"><span data-stu-id="27ff1-141">Select the items to refund, and choose the payment method.</span></span>  
- <span data-ttu-id="27ff1-142">Se l'offerta di pagamento selezionata è nell'elenco dei tipi di offerte di reso consentiti, il cassiere può completare la transazione.</span><span class="sxs-lookup"><span data-stu-id="27ff1-142">If the payment tender selected is in the allowed list of return tender types, the cashier can complete the transaction.</span></span>
- <span data-ttu-id="27ff1-143">Se l'offerta di pagamento selezionata non è consentita, viene visualizzato un messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="27ff1-143">If the payment tender selected is not allowed, an error message is displayed.</span></span>
- <span data-ttu-id="27ff1-144">Selezionare **Importo dovuto** per visualizzare un elenco di tutti i tipi di offerte di reso consentiti.</span><span class="sxs-lookup"><span data-stu-id="27ff1-144">Select **Amount Due** to display a list of all the allowed return tender types.</span></span>

<span data-ttu-id="27ff1-145">oppure</span><span class="sxs-lookup"><span data-stu-id="27ff1-145">-or-</span></span>

1. <span data-ttu-id="27ff1-146">Accedere al POS come cassiere o responsabile.</span><span class="sxs-lookup"><span data-stu-id="27ff1-146">Sign in to the POS as a cashier or manager.</span></span>
2. <span data-ttu-id="27ff1-147">Selezionare **Transazione di reso** e immettere l'ID ricevuta utilizzando un lettore di codici a barre oppure manualmente.</span><span class="sxs-lookup"><span data-stu-id="27ff1-147">Select **Return Transaction** and enter the receipt ID using a barcode scan or by manual entry.</span></span> 
3. <span data-ttu-id="27ff1-148">Seleziona la transazione che fa parte del reso.</span><span class="sxs-lookup"><span data-stu-id="27ff1-148">Select the transaction that is part of the return.</span></span> 
4. <span data-ttu-id="27ff1-149">Selezionare gli articoli da rimborsare e scegliere il metodo di pagamento.</span><span class="sxs-lookup"><span data-stu-id="27ff1-149">Select the items to refund, and choose the payment method.</span></span>  
- <span data-ttu-id="27ff1-150">Se l'offerta di pagamento selezionata è nell'elenco dei tipi di offerte di reso consentiti, il cassiere può completare la transazione.</span><span class="sxs-lookup"><span data-stu-id="27ff1-150">If the payment tender selected is in the allowed list of return tender types, the cashier can complete the transaction.</span></span>
- <span data-ttu-id="27ff1-151">Se l'offerta di pagamento selezionata non è consentita, viene visualizzato un messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="27ff1-151">If the payment tender selected is not allowed, an error message is displayed.</span></span>
- <span data-ttu-id="27ff1-152">Selezionare **Importo dovuto** per visualizzare un elenco di tutti i tipi di offerte di reso consentiti.</span><span class="sxs-lookup"><span data-stu-id="27ff1-152">Select **Amount Due** to display a list of all the allowed return tender types.</span></span>

<span data-ttu-id="27ff1-153">![Rimborso non consentito](media/Return-policy-page6.png "Tipo di rimborso non consentito")</span><span class="sxs-lookup"><span data-stu-id="27ff1-153">![Refund not allowed](media/Return-policy-page6.png "Refund type not allowed")</span></span>



<span data-ttu-id="27ff1-154">![Elenco di metodi di pagamento](media/Return-policy-page5.PNG "Tipo di rimborso consentito")</span><span class="sxs-lookup"><span data-stu-id="27ff1-154">![List of payment methods](media/Return-policy-page5.PNG "Refund types allowed")</span></span>
