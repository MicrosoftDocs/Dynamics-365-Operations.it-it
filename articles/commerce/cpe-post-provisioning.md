---
title: Configurare un ambiente di valutazione Dynamics 365 Commerce
description: Questo argomento illustra come configurare un ambiente di valutazione di Microsoft Dynamics 365 Commerce dopo il provisioning.
author: psimolin
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-12-10
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 10e80830a1cb0864c7eef19857b91e36ad27cdef
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5795861"
---
# <a name="configure-a-dynamics-365-commerce-evaluation-environment"></a><span data-ttu-id="11ba6-103">Configurare un ambiente di valutazione Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="11ba6-103">Configure a Dynamics 365 Commerce evaluation environment</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="11ba6-104">Questo argomento illustra come configurare un ambiente di valutazione di Microsoft Dynamics 365 Commerce dopo il provisioning.</span><span class="sxs-lookup"><span data-stu-id="11ba6-104">This topic explains how to configure a Microsoft Dynamics 365 Commerce evaluation environment after it's provisioned.</span></span>

<span data-ttu-id="11ba6-105">Completare le procedure in questo argomento solo dopo aver effettuato il provisioning dell'ambiente di valutazione Commerce.</span><span class="sxs-lookup"><span data-stu-id="11ba6-105">Complete the procedures in this topic only after your Commerce evaluation environment has been provisioned.</span></span> <span data-ttu-id="11ba6-106">Per informazioni relative a come effettuare il provisioning dell'ambiente di valutazione Commerce, consultare [Provisioning di un ambiente di valutazione Commerce ](provisioning-guide.md).</span><span class="sxs-lookup"><span data-stu-id="11ba6-106">For information about how to provision your Commerce evaluation environment, see [Provision a Commerce evaluation environment](provisioning-guide.md).</span></span>

<span data-ttu-id="11ba6-107">Una volta eseguito il provisioning completo dell'ambiente di valutazione Commerce, è necessario completare ulteriori passaggi di configurazione post-provisioning prima di poter iniziare a valutare l'ambiente.</span><span class="sxs-lookup"><span data-stu-id="11ba6-107">After your Commerce evaluation environment has been provisioned end to end, additional post-provisioning configuration steps must be completed before you can start to evaluate the environment.</span></span> <span data-ttu-id="11ba6-108">Per completare questi passaggi, è necessario utilizzare Microsoft Dynamics Lifecycle Services (LCS) e Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="11ba6-108">To complete these steps, you must use Microsoft Dynamics Lifecycle Services (LCS) and Dynamics 365 Commerce.</span></span>

## <a name="before-you-start"></a><span data-ttu-id="11ba6-109">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="11ba6-109">Before you start</span></span>

1. <span data-ttu-id="11ba6-110">Accedere al [portale LCS](https://lcs.dynamics.com).</span><span class="sxs-lookup"><span data-stu-id="11ba6-110">Sign in to the [LCS portal](https://lcs.dynamics.com).</span></span>
1. <span data-ttu-id="11ba6-111">Andare al progetto.</span><span class="sxs-lookup"><span data-stu-id="11ba6-111">Go to your project.</span></span>
1. <span data-ttu-id="11ba6-112">Nel menu superiore, selezionare **Distribuzione ambienti ospitati nel cloud**.</span><span class="sxs-lookup"><span data-stu-id="11ba6-112">On the top menu, select **Cloud-hosted environments**.</span></span>
1. <span data-ttu-id="11ba6-113">Selezionare l'ambiente nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="11ba6-113">Select your environment in the list.</span></span>
1. <span data-ttu-id="11ba6-114">Nelle informazioni sull'ambiente a destra, selezionare **Accedi all'ambiente**.</span><span class="sxs-lookup"><span data-stu-id="11ba6-114">In the environment information on the right, select **Log on to environment**.</span></span> <span data-ttu-id="11ba6-115">Si accederà a Commerce Headquarters.</span><span class="sxs-lookup"><span data-stu-id="11ba6-115">You will be sent to Commerce headquarters.</span></span>
1. <span data-ttu-id="11ba6-116">Assicurarsi che la persona giuridica **USRT** sia selezionata nell'angolo in alto a destra.</span><span class="sxs-lookup"><span data-stu-id="11ba6-116">Make sure that the **USRT** legal entity is selected in the upper-right corner.</span></span>

<span data-ttu-id="11ba6-117">Durante le attività di post-provisioning in Commerce headquarters, assicurarsi che la persona giuridica **USRT** sia sempre selezionata.</span><span class="sxs-lookup"><span data-stu-id="11ba6-117">During post-provisioning activities in Commerce headquarters, make sure that the **USRT** legal entity is always selected.</span></span>

## <a name="configure-the-point-of-sale"></a><span data-ttu-id="11ba6-118">Configurare il POS</span><span class="sxs-lookup"><span data-stu-id="11ba6-118">Configure the point of sale</span></span>

### <a name="associate-a-worker-with-your-identity"></a><span data-ttu-id="11ba6-119">Associare un lavoratore all'identità</span><span class="sxs-lookup"><span data-stu-id="11ba6-119">Associate a worker with your identity</span></span>

<span data-ttu-id="11ba6-120">Per associare un lavoratore all'identità, effettuare le seguenti operazioni in Commerce headquarters.</span><span class="sxs-lookup"><span data-stu-id="11ba6-120">To associate a worker with your identity, follow these steps in Commerce headquarters.</span></span>

1. <span data-ttu-id="11ba6-121">Utilizzare il menu a sinistra e scegliere **Moduli \> Vendita al dettaglio e commercio \> Dipendenti \> Lavoratori**.</span><span class="sxs-lookup"><span data-stu-id="11ba6-121">Use the menu on the left to go to **Modules \> Retail and commerce \> Employees \> Workers**.</span></span>
1. <span data-ttu-id="11ba6-122">Nell'elenco trovare e selezionare il seguente record **000713 - Andrew Collette**.</span><span class="sxs-lookup"><span data-stu-id="11ba6-122">In the list, find and select the following record: **000713 - Andrew Collette**.</span></span>
1. <span data-ttu-id="11ba6-123">Nel riquadro azioni selezionare **Commerce**.</span><span class="sxs-lookup"><span data-stu-id="11ba6-123">On the Action Pane, select **Commerce**.</span></span>
1. <span data-ttu-id="11ba6-124">Selezionare **Associa identità esistente**.</span><span class="sxs-lookup"><span data-stu-id="11ba6-124">Select **Associate existing identity**.</span></span>
1. <span data-ttu-id="11ba6-125">Nel campo **Indirizzo di posta elettronica** a destra di **Cerca tramite posta elettronica**, digitare il proprio indirizzo di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="11ba6-125">In the **Email** field to the right of **Search using email**, enter your email address.</span></span>
1. <span data-ttu-id="11ba6-126">Selezionare **Cerca**.</span><span class="sxs-lookup"><span data-stu-id="11ba6-126">Select **Search**.</span></span>
1. <span data-ttu-id="11ba6-127">Selezionare il record con il proprio nome.</span><span class="sxs-lookup"><span data-stu-id="11ba6-127">Select the record that has your name.</span></span>
1. <span data-ttu-id="11ba6-128">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="11ba6-128">Select **OK**.</span></span>
1. <span data-ttu-id="11ba6-129">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="11ba6-129">Select **Save**.</span></span>

### <a name="activate-cloud-pos"></a><span data-ttu-id="11ba6-130">Attivare il Cloud POS</span><span class="sxs-lookup"><span data-stu-id="11ba6-130">Activate Cloud POS</span></span>

<span data-ttu-id="11ba6-131">Per attivare Cloud POS in LCS, attenersi alla seguente procedura.</span><span class="sxs-lookup"><span data-stu-id="11ba6-131">To activate Cloud POS, follow these steps in LCS.</span></span>

1. <span data-ttu-id="11ba6-132">Nel menu superiore, selezionare **Distribuzione ambienti ospitati nel cloud**.</span><span class="sxs-lookup"><span data-stu-id="11ba6-132">On the top menu, select **Cloud-hosted environments**.</span></span>
1. <span data-ttu-id="11ba6-133">Selezionare l'ambiente nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="11ba6-133">Select your environment in the list.</span></span>
1. <span data-ttu-id="11ba6-134">Nelle informazioni sull'ambiente a destra, selezionare **Accedi a POS Cloud**.</span><span class="sxs-lookup"><span data-stu-id="11ba6-134">In the environment information on the right, select **Log on to Cloud Point of Sale**.</span></span>
1. <span data-ttu-id="11ba6-135">Selezionare **Avanti** per aprire la finestra di dialogo **Prima di iniziare**.</span><span class="sxs-lookup"><span data-stu-id="11ba6-135">Select **Next** to open the **Before you start** dialog box.</span></span>
1. <span data-ttu-id="11ba6-136">Lasciare invariato il campo **URL server**.</span><span class="sxs-lookup"><span data-stu-id="11ba6-136">Leave the **Server URL** field as it is.</span></span> <span data-ttu-id="11ba6-137">Selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="11ba6-137">Select **Next**.</span></span>
1. <span data-ttu-id="11ba6-138">Accedere usando l'account Microsoft Azure Active Directory ( Azure AD).</span><span class="sxs-lookup"><span data-stu-id="11ba6-138">Sign in by using your Microsoft Azure Active Directory (Azure AD) account.</span></span>
1. <span data-ttu-id="11ba6-139">Sotto **Nome punto vendita**, selezionare **San Francisco**, quindi selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="11ba6-139">Under **Store name**, select **San Francisco**, and then select **Next**.</span></span>
1. <span data-ttu-id="11ba6-140">In **Registro e dispositivo**, scegliere **SANFRAN-1**.</span><span class="sxs-lookup"><span data-stu-id="11ba6-140">Under **Register and device**, select **SANFRAN-1**.</span></span>
1. <span data-ttu-id="11ba6-141">Selezionare **Attiva**.</span><span class="sxs-lookup"><span data-stu-id="11ba6-141">Select **Activate**.</span></span> <span data-ttu-id="11ba6-142">Si verrà disconnessi e indirizzati alla pagina di accesso POS.</span><span class="sxs-lookup"><span data-stu-id="11ba6-142">You're signed out and taken to the POS sign-in page.</span></span>
1. <span data-ttu-id="11ba6-143">A questo punto è possibile accedere all'esperienza Cloud POS utilizzando l'ID operatore **000713** e la password **123**.</span><span class="sxs-lookup"><span data-stu-id="11ba6-143">You can now sign in to the Cloud POS experience by using operator ID **000713** and password **123**.</span></span>

## <a name="set-up-your-site-in-commerce"></a><span data-ttu-id="11ba6-144">Configurare il sito in Commerce</span><span class="sxs-lookup"><span data-stu-id="11ba6-144">Set up your site in Commerce</span></span>

<span data-ttu-id="11ba6-145">Per iniziare a configurare il sito di valutazione in Commerce, attenersi alla seguente procedura.</span><span class="sxs-lookup"><span data-stu-id="11ba6-145">To start to set up your evaluation site in Commerce, follow these steps.</span></span>

1. <span data-ttu-id="11ba6-146">Accedi a Creazione di siti Web utilizzando l'URL di cui hai preso nota quando hai inizializzato l'e-Commerce durante il provisioning (vedere [Inizializzare l'e-Commerce](provisioning-guide.md#initialize-e-commerce)).</span><span class="sxs-lookup"><span data-stu-id="11ba6-146">Sign in to site builder by using the URL that you made a note of when you initialized e-Commerce during provisioning (see [Initialize e-Commerce](provisioning-guide.md#initialize-e-commerce)).</span></span>
1. <span data-ttu-id="11ba6-147">Selezionare il sito **Fabrikam** per aprire la finestra di dialogo di impostazione del sito.</span><span class="sxs-lookup"><span data-stu-id="11ba6-147">Select the **Fabrikam** site to open the site setup dialog box.</span></span>
1. <span data-ttu-id="11ba6-148">Selezionare il dominio inserito quando è stato inizializzato e-Commerce.</span><span class="sxs-lookup"><span data-stu-id="11ba6-148">Select the domain that you entered when you initialized e-Commerce.</span></span>
1. <span data-ttu-id="11ba6-149">Come canale predefinito, selezionare **Punto vendita online esteso Fabrikam**.</span><span class="sxs-lookup"><span data-stu-id="11ba6-149">Select **Fabrikam extended online store** as the default channel.</span></span> <span data-ttu-id="11ba6-150">Assicurarsi di selezionare il punto vendita online **esteso**.</span><span class="sxs-lookup"><span data-stu-id="11ba6-150">(Make sure that you select the **extended** online store.)</span></span>
1. <span data-ttu-id="11ba6-151">Come lingua predefinita, selezionare **en-us**.</span><span class="sxs-lookup"><span data-stu-id="11ba6-151">Select **en-us** as the default language.</span></span>
1. <span data-ttu-id="11ba6-152">Lascia invariato valore del campo **Percorso**.</span><span class="sxs-lookup"><span data-stu-id="11ba6-152">Leave the value of the **Path** field as it is.</span></span>
1. <span data-ttu-id="11ba6-153">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="11ba6-153">Select **OK**.</span></span> <span data-ttu-id="11ba6-154">Viene visualizzato l'elenco delle pagine del sito.</span><span class="sxs-lookup"><span data-stu-id="11ba6-154">The list of pages on the site appears.</span></span>

## <a name="enable-jobs"></a><span data-ttu-id="11ba6-155">Abilitare i processi</span><span class="sxs-lookup"><span data-stu-id="11ba6-155">Enable jobs</span></span>

<span data-ttu-id="11ba6-156">Per abilitare i processi in Commerce, effettuare le operazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="11ba6-156">To enable jobs in Commerce, follow these steps.</span></span>

1. <span data-ttu-id="11ba6-157">Accedere all'ambiente (HQ).</span><span class="sxs-lookup"><span data-stu-id="11ba6-157">Sign in to the environment (HQ).</span></span>
1. <span data-ttu-id="11ba6-158">Utilizzare il menu a sinistra per andare a **Vendita al dettaglio e commercio \> Richieste di informazioni e report \> Processi batch**.</span><span class="sxs-lookup"><span data-stu-id="11ba6-158">Use the menu on the left to go to **Retail and commerce \> Inquiries and reports \> Batch jobs**.</span></span>

    <span data-ttu-id="11ba6-159">Le fasi restanti di questa procedura devono essere completate per ciascuno dei seguenti processi:</span><span class="sxs-lookup"><span data-stu-id="11ba6-159">The remaining steps of this procedure must be completed for each of the following jobs:</span></span>

    * <span data-ttu-id="11ba6-160">Elabora notifica tramite posta elettronica di ordine di vendita al dettaglio</span><span class="sxs-lookup"><span data-stu-id="11ba6-160">Process retail order email notification</span></span>
    * <span data-ttu-id="11ba6-161">Disponibilità prodotto</span><span class="sxs-lookup"><span data-stu-id="11ba6-161">Product availability</span></span>
    * <span data-ttu-id="11ba6-162">P-0001</span><span class="sxs-lookup"><span data-stu-id="11ba6-162">P-0001</span></span>
    * <span data-ttu-id="11ba6-163">Sincronizza processo di ordini</span><span class="sxs-lookup"><span data-stu-id="11ba6-163">Synchronize orders job</span></span>

1. <span data-ttu-id="11ba6-164">Utilizzare il filtro rapido per cercare il processo per nome.</span><span class="sxs-lookup"><span data-stu-id="11ba6-164">Use the Quick Filter to search for the job by name.</span></span>
1. <span data-ttu-id="11ba6-165">Se lo stato del processo è **Esecuzione**, effettuare le seguenti operazioni:</span><span class="sxs-lookup"><span data-stu-id="11ba6-165">If the status of the job is **Executing**, follow these steps:</span></span>

    1. <span data-ttu-id="11ba6-166">Selezionare il record.</span><span class="sxs-lookup"><span data-stu-id="11ba6-166">Select the record.</span></span>
    1. <span data-ttu-id="11ba6-167">Nel riquadro azioni, sulla scheda **Processo batch** selezionare **Cambia stato**.</span><span class="sxs-lookup"><span data-stu-id="11ba6-167">On the Action Pane, on **Batch job** tab, select **Change status**.</span></span>
    1. <span data-ttu-id="11ba6-168">Selezionare **Annullamento** e quindi **OK**.</span><span class="sxs-lookup"><span data-stu-id="11ba6-168">Select **Canceling**, and then select **OK**.</span></span>

<span data-ttu-id="11ba6-169">Facoltativamente, è anche possibile impostare l'intervallo di ricorrenza su un (1) minuto per i seguenti lavori:</span><span class="sxs-lookup"><span data-stu-id="11ba6-169">Optionally, you can also set the recurrence interval to one (1) minute for the following jobs:</span></span>

* <span data-ttu-id="11ba6-170">Elabora processo di notifica tramite posta elettronica di ordine di vendita al dettaglio</span><span class="sxs-lookup"><span data-stu-id="11ba6-170">Process retail order email notification job</span></span>
* <span data-ttu-id="11ba6-171">Processo P-0001</span><span class="sxs-lookup"><span data-stu-id="11ba6-171">P-0001 job</span></span>
* <span data-ttu-id="11ba6-172">Sincronizza processo di ordini</span><span class="sxs-lookup"><span data-stu-id="11ba6-172">Synchronize orders job</span></span>

### <a name="run-full-data-synchronization"></a><span data-ttu-id="11ba6-173">Eseguire la sincronizzazione dati completa</span><span class="sxs-lookup"><span data-stu-id="11ba6-173">Run full data synchronization</span></span>

<span data-ttu-id="11ba6-174">Per eseguire la sincronizzazione completa dei dati in Commerce, attenersi alla seguente procedura in Commerce headquarters.</span><span class="sxs-lookup"><span data-stu-id="11ba6-174">To run full data synchronization in Commerce, follow these steps in Commerce headquarters.</span></span>

1. <span data-ttu-id="11ba6-175">Utilizzare il menu a sinistra per andare a **Moduli \> Vendita al dettaglio e commercio \> Impostazione sedi centrali \> Utilità di pianificazione commercio \> Database canale**.</span><span class="sxs-lookup"><span data-stu-id="11ba6-175">Use the menu on the left to go to **Modules \> Retail and commerce \> Headquarters setup \> Commerce scheduler \> Channel database**.</span></span>
1. <span data-ttu-id="11ba6-176">Selezionare il canale denominato **scXXXXXXXXX**.</span><span class="sxs-lookup"><span data-stu-id="11ba6-176">Select the channel that is named **scXXXXXXXXX**.</span></span>
1. <span data-ttu-id="11ba6-177">Selezionare **Sincronizzazione dati completa** nel riquadro azioni.</span><span class="sxs-lookup"><span data-stu-id="11ba6-177">On the Action Pane, select **Full data sync**.</span></span>
1. <span data-ttu-id="11ba6-178">Immettere **9999** come programmazione della distribuzione.</span><span class="sxs-lookup"><span data-stu-id="11ba6-178">Enter **9999** as the distribution schedule.</span></span>
1. <span data-ttu-id="11ba6-179">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="11ba6-179">Select **OK**.</span></span>
1. <span data-ttu-id="11ba6-180">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="11ba6-180">Select **OK**.</span></span>

### <a name="test-credit-card-information-to-do-test-purchases"></a><span data-ttu-id="11ba6-181">Verificare le informazioni sulla carta di credito per effettuare acquisti di prova</span><span class="sxs-lookup"><span data-stu-id="11ba6-181">Test credit card information to do test purchases</span></span>

<span data-ttu-id="11ba6-182">Per eseguire transazioni di prova nel sito, è possibile utilizzare le seguenti informazioni della carta di credito di prova:</span><span class="sxs-lookup"><span data-stu-id="11ba6-182">To perform test transactions on the site, you can use the following test credit card information:</span></span>

- <span data-ttu-id="11ba6-183">**Numero carta:** 4111-1111-1111-1111</span><span class="sxs-lookup"><span data-stu-id="11ba6-183">**Card number:** 4111-1111-1111-1111</span></span>
- <span data-ttu-id="11ba6-184">**Data di scadenza:** 10/20</span><span class="sxs-lookup"><span data-stu-id="11ba6-184">**Expiration date:** 10/20</span></span>
- <span data-ttu-id="11ba6-185">**Codice valore di verifica carta (CVV):** 737</span><span class="sxs-lookup"><span data-stu-id="11ba6-185">**Card verification value (CVV) code:** 737</span></span>

> [!IMPORTANT]
> <span data-ttu-id="11ba6-186">Non utilizzare mai le informazioni di una carta di credito reale nel sito di prova.</span><span class="sxs-lookup"><span data-stu-id="11ba6-186">Never, under any circumstances, try to use actual credit card information on the test site.</span></span>

## <a name="next-steps"></a><span data-ttu-id="11ba6-187">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="11ba6-187">Next steps</span></span>

<span data-ttu-id="11ba6-188">Dopo aver completato le fasi di provisioning e configurazione, è possibile iniziare a usare l'ambiente di valutazione.</span><span class="sxs-lookup"><span data-stu-id="11ba6-188">After the provisioning and configuration steps are completed, you can start to use your evaluation environment.</span></span> <span data-ttu-id="11ba6-189">Utilizzare l'URL di Creazione di siti Web di Commerce per accedere all'esperienza di creazione.</span><span class="sxs-lookup"><span data-stu-id="11ba6-189">Use the Commerce site builder URL to go to the authoring experience.</span></span> <span data-ttu-id="11ba6-190">Utilizzare l'URL del sito di Commerce per accedere all'esperienza del sito dei clienti di vendita al dettaglio.</span><span class="sxs-lookup"><span data-stu-id="11ba6-190">Use the Commerce site URL to go to the retail customer site experience.</span></span>

<span data-ttu-id="11ba6-191">Per configurare funzionalità facoltative per l'ambiente di valutazione Commerce, vedere [Configurare le funzionalità facoltative per un ambiente di valutazione Commerce](cpe-optional-features.md).</span><span class="sxs-lookup"><span data-stu-id="11ba6-191">To configure optional features for your Commerce evaluation environment, see [Configure optional features for a Commerce evaluation environment](cpe-optional-features.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="11ba6-192">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="11ba6-192">Additional resources</span></span>

[<span data-ttu-id="11ba6-193">Panoramica dell'ambiente di valutazione Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="11ba6-193">Dynamics 365 Commerce evaluation environment overview</span></span>](cpe-overview.md)

[<span data-ttu-id="11ba6-194">Provisioning di un ambiente di valutazione Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="11ba6-194">Provision a Dynamics 365 Commerce evaluation environment</span></span>](provisioning-guide.md)

[<span data-ttu-id="11ba6-195">Configurare le funzioni facoltative per un ambiente di valutazione Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="11ba6-195">Configure optional features for a Dynamics 365 Commerce evaluation environment</span></span>](cpe-optional-features.md)

[<span data-ttu-id="11ba6-196">Configurare uno scenario BOPIS in un ambiente di valutazione Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="11ba6-196">Configure BOPIS in a Dynamics 365 Commerce evaluation environment</span></span>](cpe-bopis.md)

[<span data-ttu-id="11ba6-197">Domande frequenti sull'ambiente di valutazione Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="11ba6-197">Dynamics 365 Commerce evaluation environment FAQ</span></span>](cpe-faq.md)

[<span data-ttu-id="11ba6-198">Microsoft Lifecycle Services (LCS)</span><span class="sxs-lookup"><span data-stu-id="11ba6-198">Microsoft Lifecycle Services (LCS)</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide)

[<span data-ttu-id="11ba6-199">Retail Cloud Scale Unit (RCSU)</span><span class="sxs-lookup"><span data-stu-id="11ba6-199">Retail Cloud Scale Unit (RCSU)</span></span>](https://docs.microsoft.com/business-applications-release-notes/october18/dynamics365-retail/retail-cloud-scale-unit)

[<span data-ttu-id="11ba6-200">Portale di Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="11ba6-200">Microsoft Azure portal</span></span>](https://azure.microsoft.com/features/azure-portal)

[<span data-ttu-id="11ba6-201">Sito Web di Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="11ba6-201">Dynamics 365 Commerce website</span></span>](https://aka.ms/Dynamics365CommerceWebsite)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
