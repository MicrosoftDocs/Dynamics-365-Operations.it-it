---
title: Sincronizzare valutazioni di prodotti in Dynamics 365 Retail
description: In questo argomento viene descritto come sincronizzare valutazioni di prodotti in Microsoft Dynamics 365 Retail.
author: gvrmohanreddy
manager: annbe
ms.date: 10/01/2019
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
ms.search.industry: ''
ms.author: gmohanv
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: db5a4e1f78797d20ded2274cc99bef422fd50acc
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/01/2019
ms.locfileid: "2698167"
---
# <a name="sync-product-ratings-in-dynamics-365-retail"></a><span data-ttu-id="8aa5d-103">Sincronizzare valutazioni di prodotti in Dynamics 365 Retail</span><span class="sxs-lookup"><span data-stu-id="8aa5d-103">Sync product ratings in Dynamics 365 Retail</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="8aa5d-104">In questo argomento viene descritto come sincronizzare valutazioni di prodotti in Microsoft Dynamics 365 Retail.</span><span class="sxs-lookup"><span data-stu-id="8aa5d-104">This topic describes how to sync product ratings in Microsoft Dynamics 365 Retail.</span></span>

## <a name="overview"></a><span data-ttu-id="8aa5d-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="8aa5d-105">Overview</span></span>

<span data-ttu-id="8aa5d-106">Per utilizzare valutazioni di prodotti nei multicanali, ad esempio nel POS e nei servizi clienti, le valutazioni di prodotti del servizio Valutazioni e recensioni devono essere importate nel database del canale di Retail.</span><span class="sxs-lookup"><span data-stu-id="8aa5d-106">To consume product ratings in omnichannels, such as at the point of sale (POS) and in call centers, product ratings from the ratings and reviews service must be imported into the Retail channel database.</span></span> <span data-ttu-id="8aa5d-107">Quando le valutazioni di prodotti diventano disponibili nei multicanali, possono aiutare indirettamente i clienti durante le interazioni con gli addetti alle vendite.</span><span class="sxs-lookup"><span data-stu-id="8aa5d-107">When product ratings are made available in omnichannels, they can help customers indirectly during their interactions with sales associates.</span></span>

<span data-ttu-id="8aa5d-108">In questo argomento vengono descritte le seguenti attività:</span><span class="sxs-lookup"><span data-stu-id="8aa5d-108">This topic describes following tasks:</span></span>

1. <span data-ttu-id="8aa5d-109">Configurare un processo batch di Retail per importare valutazioni di prodotti.</span><span class="sxs-lookup"><span data-stu-id="8aa5d-109">Configure a Retail batch job to import product ratings.</span></span>
1. <span data-ttu-id="8aa5d-110">Verificare che il processo batch per la sincronizzazione delle valutazioni di prodotti sia stato eseguito correttamente.</span><span class="sxs-lookup"><span data-stu-id="8aa5d-110">Verify that the batch job for product rating synchronization was successful.</span></span>
1. <span data-ttu-id="8aa5d-111">Rendere le valutazioni di prodotti disponibili nel POS.</span><span class="sxs-lookup"><span data-stu-id="8aa5d-111">Make product ratings available at the POS.</span></span>

## <a name="configure-a-retail-batch-job-to-import-product-ratings"></a><span data-ttu-id="8aa5d-112">Configurare un processo batch di Retail per importare valutazioni di prodotti</span><span class="sxs-lookup"><span data-stu-id="8aa5d-112">Configure a Retail batch job to import product ratings</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8aa5d-113">Prima di iniziare, assicurarsi che sia installata la versione 10.0.6 o successiva di Retail.</span><span class="sxs-lookup"><span data-stu-id="8aa5d-113">Before you start, make sure that version 10.0.6 or later of Retail is installed.</span></span>

### <a name="initialize-the-retail-scheduler"></a><span data-ttu-id="8aa5d-114">Inizializzare Retail Scheduler</span><span class="sxs-lookup"><span data-stu-id="8aa5d-114">Initialize the retail scheduler</span></span>

<span data-ttu-id="8aa5d-115">Per inizializzare Retail Scheduler, effettuare le operazioni indicate di seguito.</span><span class="sxs-lookup"><span data-stu-id="8aa5d-115">To initialize the retail scheduler, follow these steps.</span></span>

1. <span data-ttu-id="8aa5d-116">Andare a **Vendita al dettaglio \> Impostazione sedi centrali \> Retail Scheduler \> Inizializza Retail Scheduler**.</span><span class="sxs-lookup"><span data-stu-id="8aa5d-116">Go to **Retail \> Headquarters setup \> Retail scheduler \> Initialize retail scheduler**.</span></span> <span data-ttu-id="8aa5d-117">In alternativa, cercare "Inizializza Retail Scheduler".</span><span class="sxs-lookup"><span data-stu-id="8aa5d-117">Alternatively, search for "Initialize retail scheduler."</span></span>
1. <span data-ttu-id="8aa5d-118">Nella finestra di dialogo **Inizializza Retail Scheduler**, verificare che l'opzione **Elimina configurazione esistente** sia impostata su **No** e selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="8aa5d-118">In the **Initialize retail scheduler** dialog box, make sure that the **Delete existing configuration** option is set to **No**, and then select **OK**.</span></span>

### <a name="verify-the-retailproductrating-subjob"></a><span data-ttu-id="8aa5d-119">Verificare il processo secondario RetailProductRating</span><span class="sxs-lookup"><span data-stu-id="8aa5d-119">Verify the RetailProductRating subjob</span></span>

<span data-ttu-id="8aa5d-120">Per verificare che il processo secondario **RetailProductRating** esista, effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="8aa5d-120">To verify that the **RetailProductRating** subjob exists, follow these steps.</span></span>

1. <span data-ttu-id="8aa5d-121">Andare a **Vendita al dettaglio \> Impostazione sedi centrali \> Retail Scheduler \> Processi secondari Retail Scheduler**.</span><span class="sxs-lookup"><span data-stu-id="8aa5d-121">Go to **Retail \> Headquarters setup \> Retail scheduler \> Scheduler subjobs**.</span></span> <span data-ttu-id="8aa5d-122">In alternativa, cercare "Processi secondari Retail Scheduler".</span><span class="sxs-lookup"><span data-stu-id="8aa5d-122">Alternatively, search for "Scheduler subjobs."</span></span>
1. <span data-ttu-id="8aa5d-123">Nell'elenco di processi secondari, trovare o cercare il processo secondario **RetailProductRating**.</span><span class="sxs-lookup"><span data-stu-id="8aa5d-123">In the subjob list, find or search for the **RetailProductRating** subjob.</span></span>

<span data-ttu-id="8aa5d-124">Nella figura seguente è illustrato un esempio dei dettagli del processo secondario in Retail.</span><span class="sxs-lookup"><span data-stu-id="8aa5d-124">The following illustration shows an example of the subjob details in Retail.</span></span>

![Dettagli del processo secondario RetailProductRating](media/rnr-hq-ratings-sub-job.png)

> [!NOTE]
> <span data-ttu-id="8aa5d-126">Se non si trova il processo secondario **RetailProductRating**, è possibile che il processo **Sincronizzare valutazioni di prodotti** e il processo **1040 CDX** siano già stati eseguiti prima di inizializzare Retail Scheduler.</span><span class="sxs-lookup"><span data-stu-id="8aa5d-126">If you don't find the **RetailProductRating** subjob, you might already have run the **Sync product ratings** job and the **1040 CDX** job before you initialized the retail scheduler.</span></span> <span data-ttu-id="8aa5d-127">In tal caso, effettuare le operazioni indicate di seguito per eseguire il processo **Sincronizzazione dati completa**.</span><span class="sxs-lookup"><span data-stu-id="8aa5d-127">In this case, follow these steps to run the **Full data sync** job.</span></span>
>
> 1. <span data-ttu-id="8aa5d-128">Andare a **Vendita al dettaglio \> Impostazione sedi centrali \> Retail Scheduler \> Database canale**.</span><span class="sxs-lookup"><span data-stu-id="8aa5d-128">Go to **Retail \> Headquarters setup \> Retail scheduler \> Channel database**.</span></span> <span data-ttu-id="8aa5d-129">In alternativa, cercare "Database canale".</span><span class="sxs-lookup"><span data-stu-id="8aa5d-129">Alternatively, search for "Channel database."</span></span>
> 1. <span data-ttu-id="8aa5d-130">Selezionare il database del canale da sincronizzare.</span><span class="sxs-lookup"><span data-stu-id="8aa5d-130">Select the channel database to sync.</span></span>
> 1. <span data-ttu-id="8aa5d-131">Selezionare **Sincronizzazione dati completa** nel riquadro azioni.</span><span class="sxs-lookup"><span data-stu-id="8aa5d-131">On the Action Pane, select **Full data sync**.</span></span>
> 1. <span data-ttu-id="8aa5d-132">Nella finestra di dialogo a discesa **Seleziona programmazione distribuzione** selezionare **1040 - prodotti**, e quindi **OK**.</span><span class="sxs-lookup"><span data-stu-id="8aa5d-132">In the **Select a distribution schedule** drop-down dialog box, select **1040 - products**, and then select **OK**.</span></span>
> 1. <span data-ttu-id="8aa5d-133">Ripetere i passaggi della procedura precedente per verificare che il processo secondario **RetailProductRating** sia stato creato.</span><span class="sxs-lookup"><span data-stu-id="8aa5d-133">Repeat the steps of the previous procedure to verify that the **RetailProductRating** subjob has been created.</span></span>

### <a name="import-product-ratings"></a><span data-ttu-id="8aa5d-134">Importare valutazioni di prodotti</span><span class="sxs-lookup"><span data-stu-id="8aa5d-134">Import product ratings</span></span>

<span data-ttu-id="8aa5d-135">Per importare valutazioni di prodotti in Retail dal servizio Salutazioni e recensioni, effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="8aa5d-135">To import product ratings into Retail from the ratings and reviews service, follow these steps.</span></span>

1. <span data-ttu-id="8aa5d-136">Andare a **Vendita al dettaglio \> Impostazione sedi centrali \> Retail Scheduler \> Processo Sincronizza valutazioni di prodotti**.</span><span class="sxs-lookup"><span data-stu-id="8aa5d-136">Go to **Retail \> Headquarters setup \> Retail scheduler \> Sync product ratings job**.</span></span> <span data-ttu-id="8aa5d-137">In alternativa, cercare "Processo Sincronizza valutazioni di prodotti".</span><span class="sxs-lookup"><span data-stu-id="8aa5d-137">Alternatively, search for "Sync product ratings job."</span></span>
1. <span data-ttu-id="8aa5d-138">Nella finestra di dialogo **Esegui pull di valutazioni di prodotti**, nella Scheda dettaglio **Esecuzione in background**, selezionare **Ricorrenza**.</span><span class="sxs-lookup"><span data-stu-id="8aa5d-138">In the **Pull product ratings** dialog box, on the **Run in the background** FastTab, select **Recurrence**.</span></span>
1. <span data-ttu-id="8aa5d-139">Nella finestra di dialogo **Definisci ricorrenza**, impostare un criterio di ricorrenza</span><span class="sxs-lookup"><span data-stu-id="8aa5d-139">In the **Define recurrence** dialog box, set up a recurrence pattern.</span></span> <span data-ttu-id="8aa5d-140">(il valore suggerito è due ore). Non programmare una ricorrenza inferiore a un'ora.</span><span class="sxs-lookup"><span data-stu-id="8aa5d-140">(The suggested value is two hours.) Don't schedule a recurrence that is less than one hour.</span></span>
1. <span data-ttu-id="8aa5d-141">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="8aa5d-141">Select **OK**.</span></span>
1. <span data-ttu-id="8aa5d-142">Impostare l'opzione **Processo batch** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="8aa5d-142">Set the **Batch process** option to **Yes**.</span></span> <span data-ttu-id="8aa5d-143">Questa impostazione assicura la possibilità di esaminare i log e di verificare lo stato delle esecuzioni dei processi batch.</span><span class="sxs-lookup"><span data-stu-id="8aa5d-143">This setting helps guarantee that you will be able to audit the logs and verify the status of batch job runs.</span></span>
1. <span data-ttu-id="8aa5d-144">Selezionare **OK** per programmare il processo batch.</span><span class="sxs-lookup"><span data-stu-id="8aa5d-144">Select **OK** to schedule the batch job.</span></span>

<span data-ttu-id="8aa5d-145">Nella figura seguente è illustrato un esempio di configurazione di processo batch in Retail.</span><span class="sxs-lookup"><span data-stu-id="8aa5d-145">The following illustration shows an example of batch job configuration in Retail.</span></span>

![Configurazione del processo batch Sincronizza valutazioni di prodotti](media/rnr-hq-batchjob-recurrence.png)

## <a name="verify-that-the-batch-job-for-product-rating-synchronization-was-successful"></a><span data-ttu-id="8aa5d-147">Verificare che il processo batch per la sincronizzazione delle valutazioni di prodotti sia stato eseguito correttamente</span><span class="sxs-lookup"><span data-stu-id="8aa5d-147">Verify that the batch job for product rating synchronization was successful</span></span>

<span data-ttu-id="8aa5d-148">Per verificare l'esito positivo del processo batch **Sincronizza valutazioni di prodotti**, effettuare le operazioni indicate di seguito.</span><span class="sxs-lookup"><span data-stu-id="8aa5d-148">To verify that the **Sync product ratings** batch job was successful, follow these steps.</span></span>

1. <span data-ttu-id="8aa5d-149">Andare a **Vendita al dettaglio \> Amministratore di sistema \> Informazioni \> Processi batch** oppure, se si utilizza un'unità di stockkeeping solo di Retail, andare a **Vendita al dettaglio \> Richieste di informazioni e report \> Processi batch**.</span><span class="sxs-lookup"><span data-stu-id="8aa5d-149">Go to **Retail \> System administrator \> Inquiries \> Batch jobs** or, if you're using a Retail-only stock keeping unit (SKU), **Retail \> Inquiries and reports \> Batch jobs** instead.</span></span> <span data-ttu-id="8aa5d-150">In alternativa, cercare "Processi batch".</span><span class="sxs-lookup"><span data-stu-id="8aa5d-150">Alternatively, search for "Batch jobs."</span></span>
1. <span data-ttu-id="8aa5d-151">Per visualizzare i dettagli del processo batch, nell'elenco dei processi batch, nella colonna **Descrizione processo**, cercare una descrizione che contiene "Esegui pull di valutazioni di prodotti".</span><span class="sxs-lookup"><span data-stu-id="8aa5d-151">To view the details of the batch job, in the batch job list, in the **Job description** column, search for a description that contains "Pull product ratings."</span></span>
1. <span data-ttu-id="8aa5d-152">Selezionare l'ID processo per visualizzare i dettagli del processo batch, come la data e l'ora di inizio pianificate e il testo di ricorrenza.</span><span class="sxs-lookup"><span data-stu-id="8aa5d-152">Select the job ID to view the batch job details, such as the scheduled start date/time and the recurrence text.</span></span>

<span data-ttu-id="8aa5d-153">Nella figura seguente è illustrato un esempio di dettagli di un processo batch in Retail quando l'esecuzione del processo batch deve avvenire ogni due ore.</span><span class="sxs-lookup"><span data-stu-id="8aa5d-153">The following illustration shows an example of the batch job details in Retail when the batch job is scheduled to run at two-hour intervals.</span></span>

![Dettagli del processo batch Sincronizza valutazioni di prodotti](media/rnr-hq-batchjob-status-checking.png)

## <a name="make-product-ratings-available-at-the-pos"></a><span data-ttu-id="8aa5d-155">Rendere le valutazioni di prodotti disponibili nel POS</span><span class="sxs-lookup"><span data-stu-id="8aa5d-155">Make product ratings available at the POS</span></span>

<span data-ttu-id="8aa5d-156">Il servizio Valutazioni e recensioni in Dynamics 365 Commerce è una soluzione multicanale.</span><span class="sxs-lookup"><span data-stu-id="8aa5d-156">The ratings and reviews solution in Dynamics 365 Commerce is an omnichannel solution.</span></span> <span data-ttu-id="8aa5d-157">Tuttavia, le valutazioni di prodotti non sono visualizzate nel POS per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="8aa5d-157">However, products ratings aren't shown at the POS by default.</span></span> <span data-ttu-id="8aa5d-158">Per consentire ai clienti nei punti vendita di visualizzare valutazioni e recensioni quando interagiscono con gli addetti alle vendite, è necessario attivare le valutazioni di prodotti nel POS.</span><span class="sxs-lookup"><span data-stu-id="8aa5d-158">To help customers in stores see ratings and reviews when they are being helped by sales associates, you must turn on product ratings at the POS.</span></span>

<span data-ttu-id="8aa5d-159">Per attivare le valutazioni di prodotti nel POS, effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="8aa5d-159">To turn on product ratings at the POS, follow these steps.</span></span>

1. <span data-ttu-id="8aa5d-160">Accedere a **Vendita al dettaglio \> Impostazioni vendita al dettaglio \> Parametri \> Parametri di vendita al dettaglio**.</span><span class="sxs-lookup"><span data-stu-id="8aa5d-160">Go to **Retail \> Retail setup \> Parameters \> Retail parameters**.</span></span> <span data-ttu-id="8aa5d-161">In alternativa, cercare "Parametri di vendita al dettaglio".</span><span class="sxs-lookup"><span data-stu-id="8aa5d-161">Alternatively, search for "Retail parameters."</span></span>
1. <span data-ttu-id="8aa5d-162">Nella scheda **Parametri di configurazione**, selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="8aa5d-162">On the **Configuration parameters** tab, select **New**.</span></span>
1. <span data-ttu-id="8aa5d-163">Immettere un nome ad esempio **RatingsAndReviews.EnableProductRatingsForRetailStores** e impostare il valore su **true**.</span><span class="sxs-lookup"><span data-stu-id="8aa5d-163">Enter a name such as **RatingsAndReviews.EnableProductRatingsForRetailStores**, and set the value to **true**.</span></span>
1. <span data-ttu-id="8aa5d-164">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="8aa5d-164">Select **Save**.</span></span>
1. <span data-ttu-id="8aa5d-165">Andare a **Vendita al dettaglio \> Vendita al dettaglio IT \> Programmazione della distribuzione**.</span><span class="sxs-lookup"><span data-stu-id="8aa5d-165">Go to **Retail \> Retail IT \> Distribution schedule**.</span></span> <span data-ttu-id="8aa5d-166">In alternativa, cercare "Programmazione della distribuzione".</span><span class="sxs-lookup"><span data-stu-id="8aa5d-166">Alternatively, search for "Distribution schedule."</span></span>
1. <span data-ttu-id="8aa5d-167">Nell'elenco dei processi, selezionare **1110** (**Configurazione globale**) e quindi **Esegui adesso**.</span><span class="sxs-lookup"><span data-stu-id="8aa5d-167">In the job list, select **1110** (**Global configuration**), and then select **Run now**.</span></span>
1. <span data-ttu-id="8aa5d-168">Dopo la corretta esecuzione del processo, verificare che le valutazioni di prodotti siano visualizzate nel POS.</span><span class="sxs-lookup"><span data-stu-id="8aa5d-168">After the job has successfully run, verify that products ratings are now shown at the POS.</span></span>

<span data-ttu-id="8aa5d-169">Nella figura seguente è illustrato un esempio di configurazione dei parametri di vendita al dettaglio per attivare le valutazioni di prodotti nel POS.</span><span class="sxs-lookup"><span data-stu-id="8aa5d-169">The following illustration shows an example of the configuration of the Retail parameters to turn on product ratings at the POS.</span></span>

![Configurazione dei parametri di vendita al dettaglio per la valutazioni di prodotti nel POS](media/rnr-hq-enable-ratings-in-pos.png)

<span data-ttu-id="8aa5d-171">Di seguito viene illustrato un esempio delle valutazioni di prodotti nel POS.</span><span class="sxs-lookup"><span data-stu-id="8aa5d-171">The following illustration shows an example of product ratings at the POS.</span></span>

![Valutazioni di prodotti nel POS](media/rnr-pos-catalog-ratings.png)

<span data-ttu-id="8aa5d-173">Di seguito viene illustrato un esempio delle valutazioni di prodotti nei canali del servizio clienti.</span><span class="sxs-lookup"><span data-stu-id="8aa5d-173">The following illustration shows an example of product ratings in call center channels.</span></span>

![Valutazioni di prodotti in un canale del servizio clienti](media/rnr-call-center-ratings.png)

## <a name="additional-resources"></a><span data-ttu-id="8aa5d-175">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="8aa5d-175">Additional resources</span></span>

[<span data-ttu-id="8aa5d-176">Panoramica valutazioni e recensioni</span><span class="sxs-lookup"><span data-stu-id="8aa5d-176">Ratings and reviews overview</span></span>](ratings-reviews-overview.md)

[<span data-ttu-id="8aa5d-177">Consentire l'utilizzo di valutazioni e recensioni</span><span class="sxs-lookup"><span data-stu-id="8aa5d-177">Opt in to use ratings and reviews</span></span>](opt-in-ratings-reviews.md)

[<span data-ttu-id="8aa5d-178">Gestire valutazioni e recensioni</span><span class="sxs-lookup"><span data-stu-id="8aa5d-178">Manage ratings and reviews</span></span>](manage-reviews.md)

[<span data-ttu-id="8aa5d-179">Configurare valutazioni e recensioni</span><span class="sxs-lookup"><span data-stu-id="8aa5d-179">Configure ratings and reviews</span></span>](configure-ratings-reviews.md)
