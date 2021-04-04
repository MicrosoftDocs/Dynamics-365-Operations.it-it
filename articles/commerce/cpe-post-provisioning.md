---
title: Configurare un ambiente di valutazione Dynamics 365 Commerce
description: Questo argomento illustra come configurare un ambiente di valutazione di Microsoft Dynamics 365 Commerce dopo il provisioning.
author: psimolin
manager: annbe
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-12-10
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 9b11ab600bb2aa17cf330947304f5b22dd522081
ms.sourcegitcommit: c88b54ba13a4dfe39b844ffaced4dc435560c47d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2021
ms.locfileid: "5477975"
---
# <a name="configure-a-dynamics-365-commerce-evaluation-environment"></a><span data-ttu-id="0f90b-103">Configurare un ambiente di valutazione Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="0f90b-103">Configure a Dynamics 365 Commerce evaluation environment</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="0f90b-104">Questo argomento illustra come configurare un ambiente di valutazione di Microsoft Dynamics 365 Commerce dopo il provisioning.</span><span class="sxs-lookup"><span data-stu-id="0f90b-104">This topic explains how to configure a Microsoft Dynamics 365 Commerce evaluation environment after it's provisioned.</span></span>

<span data-ttu-id="0f90b-105">Completare le procedure in questo argomento solo dopo aver effettuato il provisioning dell'ambiente di valutazione Commerce.</span><span class="sxs-lookup"><span data-stu-id="0f90b-105">Complete the procedures in this topic only after your Commerce evaluation environment has been provisioned.</span></span> <span data-ttu-id="0f90b-106">Per informazioni relative a come effettuare il provisioning dell'ambiente di valutazione Commerce, consultare [Provisioning di un ambiente di valutazione Commerce ](provisioning-guide.md).</span><span class="sxs-lookup"><span data-stu-id="0f90b-106">For information about how to provision your Commerce evaluation environment, see [Provision a Commerce evaluation environment](provisioning-guide.md).</span></span>

<span data-ttu-id="0f90b-107">Una volta eseguito il provisioning completo dell'ambiente di valutazione Commerce, è necessario completare ulteriori passaggi di configurazione post-provisioning prima di poter iniziare a valutare l'ambiente.</span><span class="sxs-lookup"><span data-stu-id="0f90b-107">After your Commerce evaluation environment has been provisioned end to end, additional post-provisioning configuration steps must be completed before you can start to evaluate the environment.</span></span> <span data-ttu-id="0f90b-108">Per completare questi passaggi, è necessario utilizzare Microsoft Dynamics Lifecycle Services (LCS) e Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="0f90b-108">To complete these steps, you must use Microsoft Dynamics Lifecycle Services (LCS) and Dynamics 365 Commerce.</span></span>

## <a name="before-you-start"></a><span data-ttu-id="0f90b-109">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="0f90b-109">Before you start</span></span>

1. <span data-ttu-id="0f90b-110">Accedere al [portale LCS](https://lcs.dynamics.com).</span><span class="sxs-lookup"><span data-stu-id="0f90b-110">Sign in to the [LCS portal](https://lcs.dynamics.com).</span></span>
1. <span data-ttu-id="0f90b-111">Andare al progetto.</span><span class="sxs-lookup"><span data-stu-id="0f90b-111">Go to your project.</span></span>
1. <span data-ttu-id="0f90b-112">Nel menu superiore, selezionare **Distribuzione ambienti ospitati nel cloud**.</span><span class="sxs-lookup"><span data-stu-id="0f90b-112">On the top menu, select **Cloud-hosted environments**.</span></span>
1. <span data-ttu-id="0f90b-113">Selezionare l'ambiente nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="0f90b-113">Select your environment in the list.</span></span>
1. <span data-ttu-id="0f90b-114">Nelle informazioni sull'ambiente a destra, selezionare **Accedi all'ambiente**.</span><span class="sxs-lookup"><span data-stu-id="0f90b-114">In the environment information on the right, select **Log on to environment**.</span></span> <span data-ttu-id="0f90b-115">Si accederà a Commerce Headquarters.</span><span class="sxs-lookup"><span data-stu-id="0f90b-115">You will be sent to Commerce headquarters.</span></span>
1. <span data-ttu-id="0f90b-116">Assicurarsi che la persona giuridica **USRT** sia selezionata nell'angolo in alto a destra.</span><span class="sxs-lookup"><span data-stu-id="0f90b-116">Make sure that the **USRT** legal entity is selected in the upper-right corner.</span></span>

<span data-ttu-id="0f90b-117">Durante le attività di post-provisioning in Commerce headquarters, assicurarsi che la persona giuridica **USRT** sia sempre selezionata.</span><span class="sxs-lookup"><span data-stu-id="0f90b-117">During post-provisioning activities in Commerce headquarters, make sure that the **USRT** legal entity is always selected.</span></span>

## <a name="configure-the-point-of-sale"></a><span data-ttu-id="0f90b-118">Configurare il POS</span><span class="sxs-lookup"><span data-stu-id="0f90b-118">Configure the point of sale</span></span>

### <a name="associate-a-worker-with-your-identity"></a><span data-ttu-id="0f90b-119">Associare un lavoratore all'identità</span><span class="sxs-lookup"><span data-stu-id="0f90b-119">Associate a worker with your identity</span></span>

<span data-ttu-id="0f90b-120">Per associare un lavoratore all'identità, effettuare le seguenti operazioni in Commerce headquarters.</span><span class="sxs-lookup"><span data-stu-id="0f90b-120">To associate a worker with your identity, follow these steps in Commerce headquarters.</span></span>

1. <span data-ttu-id="0f90b-121">Utilizzare il menu a sinistra e scegliere **Moduli \> Vendita al dettaglio e commercio \> Dipendenti \> Lavoratori**.</span><span class="sxs-lookup"><span data-stu-id="0f90b-121">Use the menu on the left to go to **Modules \> Retail and commerce \> Employees \> Workers**.</span></span>
1. <span data-ttu-id="0f90b-122">Nell'elenco trovare e selezionare il seguente record **000713 - Andrew Collette**.</span><span class="sxs-lookup"><span data-stu-id="0f90b-122">In the list, find and select the following record: **000713 - Andrew Collette**.</span></span>
1. <span data-ttu-id="0f90b-123">Nel riquadro azioni selezionare **Commerce**.</span><span class="sxs-lookup"><span data-stu-id="0f90b-123">On the Action Pane, select **Commerce**.</span></span>
1. <span data-ttu-id="0f90b-124">Selezionare **Associa identità esistente**.</span><span class="sxs-lookup"><span data-stu-id="0f90b-124">Select **Associate existing identity**.</span></span>
1. <span data-ttu-id="0f90b-125">Nel campo **Indirizzo di posta elettronica** a destra di **Cerca tramite posta elettronica**, digitare il proprio indirizzo di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="0f90b-125">In the **Email** field to the right of **Search using email**, enter your email address.</span></span>
1. <span data-ttu-id="0f90b-126">Selezionare **Cerca**.</span><span class="sxs-lookup"><span data-stu-id="0f90b-126">Select **Search**.</span></span>
1. <span data-ttu-id="0f90b-127">Selezionare il record con il proprio nome.</span><span class="sxs-lookup"><span data-stu-id="0f90b-127">Select the record that has your name.</span></span>
1. <span data-ttu-id="0f90b-128">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="0f90b-128">Select **OK**.</span></span>
1. <span data-ttu-id="0f90b-129">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="0f90b-129">Select **Save**.</span></span>

### <a name="activate-cloud-pos"></a><span data-ttu-id="0f90b-130">Attivare il Cloud POS</span><span class="sxs-lookup"><span data-stu-id="0f90b-130">Activate Cloud POS</span></span>

<span data-ttu-id="0f90b-131">Per attivare Cloud POS in LCS, attenersi alla seguente procedura.</span><span class="sxs-lookup"><span data-stu-id="0f90b-131">To activate Cloud POS, follow these steps in LCS.</span></span>

1. <span data-ttu-id="0f90b-132">Nel menu superiore, selezionare **Distribuzione ambienti ospitati nel cloud**.</span><span class="sxs-lookup"><span data-stu-id="0f90b-132">On the top menu, select **Cloud-hosted environments**.</span></span>
1. <span data-ttu-id="0f90b-133">Selezionare l'ambiente nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="0f90b-133">Select your environment in the list.</span></span>
1. <span data-ttu-id="0f90b-134">Nelle informazioni sull'ambiente a destra, selezionare **Accedi a POS Cloud**.</span><span class="sxs-lookup"><span data-stu-id="0f90b-134">In the environment information on the right, select **Log on to Cloud Point of Sale**.</span></span>
1. <span data-ttu-id="0f90b-135">Selezionare **Avanti** per aprire la finestra di dialogo **Prima di iniziare**.</span><span class="sxs-lookup"><span data-stu-id="0f90b-135">Select **Next** to open the **Before you start** dialog box.</span></span>
1. <span data-ttu-id="0f90b-136">Lasciare invariato il campo **URL server**.</span><span class="sxs-lookup"><span data-stu-id="0f90b-136">Leave the **Server URL** field as it is.</span></span> <span data-ttu-id="0f90b-137">Selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="0f90b-137">Select **Next**.</span></span>
1. <span data-ttu-id="0f90b-138">Accedere usando l'account Microsoft Azure Active Directory ( Azure AD).</span><span class="sxs-lookup"><span data-stu-id="0f90b-138">Sign in by using your Microsoft Azure Active Directory (Azure AD) account.</span></span>
1. <span data-ttu-id="0f90b-139">Sotto **Nome punto vendita**, selezionare **San Francisco**, quindi selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="0f90b-139">Under **Store name**, select **San Francisco**, and then select **Next**.</span></span>
1. <span data-ttu-id="0f90b-140">In **Registro e dispositivo**, scegliere **SANFRAN-1**.</span><span class="sxs-lookup"><span data-stu-id="0f90b-140">Under **Register and device**, select **SANFRAN-1**.</span></span>
1. <span data-ttu-id="0f90b-141">Selezionare **Attiva**.</span><span class="sxs-lookup"><span data-stu-id="0f90b-141">Select **Activate**.</span></span> <span data-ttu-id="0f90b-142">Si verrà disconnessi e indirizzati alla pagina di accesso POS.</span><span class="sxs-lookup"><span data-stu-id="0f90b-142">You're signed out and taken to the POS sign-in page.</span></span>
1. <span data-ttu-id="0f90b-143">A questo punto è possibile accedere all'esperienza Cloud POS utilizzando l'ID operatore **000713** e la password **123**.</span><span class="sxs-lookup"><span data-stu-id="0f90b-143">You can now sign in to the Cloud POS experience by using operator ID **000713** and password **123**.</span></span>

## <a name="set-up-your-site-in-commerce"></a><span data-ttu-id="0f90b-144">Configurare il sito in Commerce</span><span class="sxs-lookup"><span data-stu-id="0f90b-144">Set up your site in Commerce</span></span>

<span data-ttu-id="0f90b-145">Per iniziare a configurare il sito di valutazione in Commerce, attenersi alla seguente procedura.</span><span class="sxs-lookup"><span data-stu-id="0f90b-145">To start to set up your evaluation site in Commerce, follow these steps.</span></span>

1. <span data-ttu-id="0f90b-146">Accedi a Creazione di siti Web utilizzando l'URL di cui hai preso nota quando hai inizializzato l'e-Commerce durante il provisioning (vedere [Inizializzare l'e-Commerce](provisioning-guide.md#initialize-e-commerce)).</span><span class="sxs-lookup"><span data-stu-id="0f90b-146">Sign in to site builder by using the URL that you made a note of when you initialized e-Commerce during provisioning (see [Initialize e-Commerce](provisioning-guide.md#initialize-e-commerce)).</span></span>
1. <span data-ttu-id="0f90b-147">Selezionare il sito **Fabrikam** per aprire la finestra di dialogo di impostazione del sito.</span><span class="sxs-lookup"><span data-stu-id="0f90b-147">Select the **Fabrikam** site to open the site setup dialog box.</span></span>
1. <span data-ttu-id="0f90b-148">Selezionare il dominio inserito quando è stato inizializzato e-Commerce.</span><span class="sxs-lookup"><span data-stu-id="0f90b-148">Select the domain that you entered when you initialized e-Commerce.</span></span>
1. <span data-ttu-id="0f90b-149">Come canale predefinito, selezionare **Punto vendita online esteso Fabrikam**.</span><span class="sxs-lookup"><span data-stu-id="0f90b-149">Select **Fabrikam extended online store** as the default channel.</span></span> <span data-ttu-id="0f90b-150">Assicurarsi di selezionare il punto vendita online **esteso**.</span><span class="sxs-lookup"><span data-stu-id="0f90b-150">(Make sure that you select the **extended** online store.)</span></span>
1. <span data-ttu-id="0f90b-151">Come lingua predefinita, selezionare **en-us**.</span><span class="sxs-lookup"><span data-stu-id="0f90b-151">Select **en-us** as the default language.</span></span>
1. <span data-ttu-id="0f90b-152">Lascia invariato valore del campo **Percorso**.</span><span class="sxs-lookup"><span data-stu-id="0f90b-152">Leave the value of the **Path** field as it is.</span></span>
1. <span data-ttu-id="0f90b-153">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="0f90b-153">Select **OK**.</span></span> <span data-ttu-id="0f90b-154">Viene visualizzato l'elenco delle pagine del sito.</span><span class="sxs-lookup"><span data-stu-id="0f90b-154">The list of pages on the site appears.</span></span>

## <a name="enable-jobs"></a><span data-ttu-id="0f90b-155">Abilitare i processi</span><span class="sxs-lookup"><span data-stu-id="0f90b-155">Enable jobs</span></span>

<span data-ttu-id="0f90b-156">Per abilitare i processi in Commerce, effettuare le operazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="0f90b-156">To enable jobs in Commerce, follow these steps.</span></span>

1. <span data-ttu-id="0f90b-157">Accedere all'ambiente (HQ).</span><span class="sxs-lookup"><span data-stu-id="0f90b-157">Sign in to the environment (HQ).</span></span>
1. <span data-ttu-id="0f90b-158">Utilizzare il menu a sinistra per andare a **Vendita al dettaglio e commercio \> Richieste di informazioni e report \> Processi batch**.</span><span class="sxs-lookup"><span data-stu-id="0f90b-158">Use the menu on the left to go to **Retail and commerce \> Inquiries and reports \> Batch jobs**.</span></span>

    <span data-ttu-id="0f90b-159">Le fasi restanti di questa procedura devono essere completate per ciascuno dei seguenti processi:</span><span class="sxs-lookup"><span data-stu-id="0f90b-159">The remaining steps of this procedure must be completed for each of the following jobs:</span></span>

    * <span data-ttu-id="0f90b-160">Elabora notifica tramite posta elettronica di ordine di vendita al dettaglio</span><span class="sxs-lookup"><span data-stu-id="0f90b-160">Process retail order email notification</span></span>
    * <span data-ttu-id="0f90b-161">Disponibilità prodotto</span><span class="sxs-lookup"><span data-stu-id="0f90b-161">Product availability</span></span>
    * <span data-ttu-id="0f90b-162">P-0001</span><span class="sxs-lookup"><span data-stu-id="0f90b-162">P-0001</span></span>
    * <span data-ttu-id="0f90b-163">Sincronizza processo di ordini</span><span class="sxs-lookup"><span data-stu-id="0f90b-163">Synchronize orders job</span></span>

1. <span data-ttu-id="0f90b-164">Utilizzare il filtro rapido per cercare il processo per nome.</span><span class="sxs-lookup"><span data-stu-id="0f90b-164">Use the Quick Filter to search for the job by name.</span></span>
1. <span data-ttu-id="0f90b-165">Se lo stato del processo è **Esecuzione**, effettuare le seguenti operazioni:</span><span class="sxs-lookup"><span data-stu-id="0f90b-165">If the status of the job is **Executing**, follow these steps:</span></span>

    1. <span data-ttu-id="0f90b-166">Selezionare il record.</span><span class="sxs-lookup"><span data-stu-id="0f90b-166">Select the record.</span></span>
    1. <span data-ttu-id="0f90b-167">Nel riquadro azioni, sulla scheda **Processo batch** selezionare **Cambia stato**.</span><span class="sxs-lookup"><span data-stu-id="0f90b-167">On the Action Pane, on **Batch job** tab, select **Change status**.</span></span>
    1. <span data-ttu-id="0f90b-168">Selezionare **Annullamento** e quindi **OK**.</span><span class="sxs-lookup"><span data-stu-id="0f90b-168">Select **Canceling**, and then select **OK**.</span></span>

<span data-ttu-id="0f90b-169">Facoltativamente, è anche possibile impostare l'intervallo di ricorrenza su un (1) minuto per i seguenti lavori:</span><span class="sxs-lookup"><span data-stu-id="0f90b-169">Optionally, you can also set the recurrence interval to one (1) minute for the following jobs:</span></span>

* <span data-ttu-id="0f90b-170">Elabora processo di notifica tramite posta elettronica di ordine di vendita al dettaglio</span><span class="sxs-lookup"><span data-stu-id="0f90b-170">Process retail order email notification job</span></span>
* <span data-ttu-id="0f90b-171">Processo P-0001</span><span class="sxs-lookup"><span data-stu-id="0f90b-171">P-0001 job</span></span>
* <span data-ttu-id="0f90b-172">Sincronizza processo di ordini</span><span class="sxs-lookup"><span data-stu-id="0f90b-172">Synchronize orders job</span></span>

### <a name="run-full-data-synchronization"></a><span data-ttu-id="0f90b-173">Eseguire la sincronizzazione dati completa</span><span class="sxs-lookup"><span data-stu-id="0f90b-173">Run full data synchronization</span></span>

<span data-ttu-id="0f90b-174">Per eseguire la sincronizzazione completa dei dati in Commerce, attenersi alla seguente procedura in Commerce headquarters.</span><span class="sxs-lookup"><span data-stu-id="0f90b-174">To run full data synchronization in Commerce, follow these steps in Commerce headquarters.</span></span>

1. <span data-ttu-id="0f90b-175">Utilizzare il menu a sinistra per andare a **Moduli \> Vendita al dettaglio e commercio \> Impostazione sedi centrali \> Utilità di pianificazione commercio \> Database canale**.</span><span class="sxs-lookup"><span data-stu-id="0f90b-175">Use the menu on the left to go to **Modules \> Retail and commerce \> Headquarters setup \> Commerce scheduler \> Channel database**.</span></span>
1. <span data-ttu-id="0f90b-176">Selezionare il canale denominato **scXXXXXXXXX**.</span><span class="sxs-lookup"><span data-stu-id="0f90b-176">Select the channel that is named **scXXXXXXXXX**.</span></span>
1. <span data-ttu-id="0f90b-177">Selezionare **Sincronizzazione dati completa** nel riquadro azioni.</span><span class="sxs-lookup"><span data-stu-id="0f90b-177">On the Action Pane, select **Full data sync**.</span></span>
1. <span data-ttu-id="0f90b-178">Immettere **9999** come programmazione della distribuzione.</span><span class="sxs-lookup"><span data-stu-id="0f90b-178">Enter **9999** as the distribution schedule.</span></span>
1. <span data-ttu-id="0f90b-179">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="0f90b-179">Select **OK**.</span></span>
1. <span data-ttu-id="0f90b-180">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="0f90b-180">Select **OK**.</span></span>

### <a name="test-credit-card-information-to-do-test-purchases"></a><span data-ttu-id="0f90b-181">Verificare le informazioni sulla carta di credito per effettuare acquisti di prova</span><span class="sxs-lookup"><span data-stu-id="0f90b-181">Test credit card information to do test purchases</span></span>

<span data-ttu-id="0f90b-182">Per eseguire transazioni di prova nel sito, è possibile utilizzare le seguenti informazioni della carta di credito di prova:</span><span class="sxs-lookup"><span data-stu-id="0f90b-182">To perform test transactions on the site, you can use the following test credit card information:</span></span>

- <span data-ttu-id="0f90b-183">**Numero carta:** 4111-1111-1111-1111</span><span class="sxs-lookup"><span data-stu-id="0f90b-183">**Card number:** 4111-1111-1111-1111</span></span>
- <span data-ttu-id="0f90b-184">**Data di scadenza:** 10/20</span><span class="sxs-lookup"><span data-stu-id="0f90b-184">**Expiration date:** 10/20</span></span>
- <span data-ttu-id="0f90b-185">**Codice valore di verifica carta (CVV):** 737</span><span class="sxs-lookup"><span data-stu-id="0f90b-185">**Card verification value (CVV) code:** 737</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0f90b-186">Non utilizzare mai le informazioni di una carta di credito reale nel sito di prova.</span><span class="sxs-lookup"><span data-stu-id="0f90b-186">Never, under any circumstances, try to use actual credit card information on the test site.</span></span>

## <a name="next-steps"></a><span data-ttu-id="0f90b-187">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="0f90b-187">Next steps</span></span>

<span data-ttu-id="0f90b-188">Dopo aver completato le fasi di provisioning e configurazione, è possibile iniziare a usare l'ambiente di valutazione.</span><span class="sxs-lookup"><span data-stu-id="0f90b-188">After the provisioning and configuration steps are completed, you can start to use your evaluation environment.</span></span> <span data-ttu-id="0f90b-189">Utilizzare l'URL di Creazione di siti Web di Commerce per accedere all'esperienza di creazione.</span><span class="sxs-lookup"><span data-stu-id="0f90b-189">Use the Commerce site builder URL to go to the authoring experience.</span></span> <span data-ttu-id="0f90b-190">Utilizzare l'URL del sito di Commerce per accedere all'esperienza del sito dei clienti di vendita al dettaglio.</span><span class="sxs-lookup"><span data-stu-id="0f90b-190">Use the Commerce site URL to go to the retail customer site experience.</span></span>

<span data-ttu-id="0f90b-191">Per configurare funzionalità facoltative per l'ambiente di valutazione Commerce, vedere [Configurare le funzionalità facoltative per un ambiente di valutazione Commerce](cpe-optional-features.md).</span><span class="sxs-lookup"><span data-stu-id="0f90b-191">To configure optional features for your Commerce evaluation environment, see [Configure optional features for a Commerce evaluation environment](cpe-optional-features.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="0f90b-192">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="0f90b-192">Additional resources</span></span>

[<span data-ttu-id="0f90b-193">Panoramica dell'ambiente di valutazione Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="0f90b-193">Dynamics 365 Commerce evaluation environment overview</span></span>](cpe-overview.md)

[<span data-ttu-id="0f90b-194">Provisioning di un ambiente di valutazione Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="0f90b-194">Provision a Dynamics 365 Commerce evaluation environment</span></span>](provisioning-guide.md)

[<span data-ttu-id="0f90b-195">Configurare le funzioni facoltative per un ambiente di valutazione Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="0f90b-195">Configure optional features for a Dynamics 365 Commerce evaluation environment</span></span>](cpe-optional-features.md)

[<span data-ttu-id="0f90b-196">Configurare uno scenario BOPIS in un ambiente di valutazione Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="0f90b-196">Configure BOPIS in a Dynamics 365 Commerce evaluation environment</span></span>](cpe-bopis.md)

[<span data-ttu-id="0f90b-197">Domande frequenti sull'ambiente di valutazione Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="0f90b-197">Dynamics 365 Commerce evaluation environment FAQ</span></span>](cpe-faq.md)

[<span data-ttu-id="0f90b-198">Microsoft Lifecycle Services (LCS)</span><span class="sxs-lookup"><span data-stu-id="0f90b-198">Microsoft Lifecycle Services (LCS)</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide)

[<span data-ttu-id="0f90b-199">Retail Cloud Scale Unit (RCSU)</span><span class="sxs-lookup"><span data-stu-id="0f90b-199">Retail Cloud Scale Unit (RCSU)</span></span>](https://docs.microsoft.com/business-applications-release-notes/october18/dynamics365-retail/retail-cloud-scale-unit)

[<span data-ttu-id="0f90b-200">Portale di Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="0f90b-200">Microsoft Azure portal</span></span>](https://azure.microsoft.com/features/azure-portal)

[<span data-ttu-id="0f90b-201">Sito Web di Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="0f90b-201">Dynamics 365 Commerce website</span></span>](https://aka.ms/Dynamics365CommerceWebsite)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
