---
title: Configurare un ambiente di anteprima Dynamics 365 Commerce
description: Questo argomento illustra come configurare un ambiente di anteprima di Microsoft Dynamics 365 Commerce dopo il provisioning.
author: psimolin
manager: annbe
ms.date: 07/02/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-12-10
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: ad05996eaabd3965308370649a27b8bc3080c7ce
ms.sourcegitcommit: f72e90dccc80718e99cab2752eaf8931dcbb915e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/02/2020
ms.locfileid: "3534069"
---
# <a name="configure-a-dynamics-365-commerce-preview-environment"></a><span data-ttu-id="6ce4b-103">Configurare un ambiente di anteprima Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="6ce4b-103">Configure a Dynamics 365 Commerce preview environment</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="6ce4b-104">Questo argomento illustra come configurare un ambiente di anteprima di Microsoft Dynamics 365 Commerce dopo il provisioning.</span><span class="sxs-lookup"><span data-stu-id="6ce4b-104">This topic explains how to configure a Microsoft Dynamics 365 Commerce preview environment after it's provisioned.</span></span>

## <a name="overview"></a><span data-ttu-id="6ce4b-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="6ce4b-105">Overview</span></span>

<span data-ttu-id="6ce4b-106">Completare le procedure in questo argomento solo dopo aver effettuato il provisioning dell'ambiente di anteprima di Commerce.</span><span class="sxs-lookup"><span data-stu-id="6ce4b-106">Complete the procedures in this topic only after your Commerce preview environment has been provisioned.</span></span> <span data-ttu-id="6ce4b-107">Per informazioni relative a come effettuare il provisioning dell'ambiente di anteprima di Commerce, consultare [Provisioning di un ambiente di anteprima Commerce ](provisioning-guide.md).</span><span class="sxs-lookup"><span data-stu-id="6ce4b-107">For information about how to provision your Commerce preview environment, see [Provision a Commerce preview environment](provisioning-guide.md).</span></span>

<span data-ttu-id="6ce4b-108">Una volta eseguito il provisioning completo dell'ambiente di anteprima di Commerce, è necessario completare ulteriori passaggi di configurazione post-provisioning prima di poter iniziare a valutare l'ambiente.</span><span class="sxs-lookup"><span data-stu-id="6ce4b-108">After your Commerce preview environment has been provisioned end to end, additional post-provisioning configuration steps must be completed before you can start to evaluate the environment.</span></span> <span data-ttu-id="6ce4b-109">Per completare questi passaggi, è necessario utilizzare Microsoft Dynamics Lifecycle Services (LCS) e Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="6ce4b-109">To complete these steps, you must use Microsoft Dynamics Lifecycle Services (LCS) and Dynamics 365 Commerce.</span></span>

## <a name="before-you-start"></a><span data-ttu-id="6ce4b-110">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="6ce4b-110">Before you start</span></span>

1. <span data-ttu-id="6ce4b-111">Accedere al [portale LCS](https://lcs.dynamics.com).</span><span class="sxs-lookup"><span data-stu-id="6ce4b-111">Sign in to the [LCS portal](https://lcs.dynamics.com).</span></span>
1. <span data-ttu-id="6ce4b-112">Andare al progetto.</span><span class="sxs-lookup"><span data-stu-id="6ce4b-112">Go to your project.</span></span>
1. <span data-ttu-id="6ce4b-113">Nel menu superiore, selezionare **Distribuzione ambienti ospitati nel cloud**.</span><span class="sxs-lookup"><span data-stu-id="6ce4b-113">On the top menu, select **Cloud-hosted environments**.</span></span>
1. <span data-ttu-id="6ce4b-114">Selezionare l'ambiente nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="6ce4b-114">Select your environment in the list.</span></span>
1. <span data-ttu-id="6ce4b-115">Nelle informazioni sull'ambiente a destra, selezionare **Dettagli completi**.</span><span class="sxs-lookup"><span data-stu-id="6ce4b-115">In the environment information on the right, select **Full details**.</span></span>
1. <span data-ttu-id="6ce4b-116">Selezionare **Accesso** per aprire un menu, quindi scegliere **Accedi all'ambiente**.</span><span class="sxs-lookup"><span data-stu-id="6ce4b-116">Select **Login** to open a menu, and then select **Log on to environment**.</span></span>
1. <span data-ttu-id="6ce4b-117">Assicurarsi che la persona giuridica **USRT** sia selezionata nell'angolo in alto a destra.</span><span class="sxs-lookup"><span data-stu-id="6ce4b-117">Make sure that the **USRT** legal entity is selected in the upper-right corner.</span></span>

## <a name="configure-the-point-of-sale-in-lcs"></a><span data-ttu-id="6ce4b-118">Configurare il POS in LCS</span><span class="sxs-lookup"><span data-stu-id="6ce4b-118">Configure the point of sale in LCS</span></span>

### <a name="associate-a-worker-with-your-identity"></a><span data-ttu-id="6ce4b-119">Associare un lavoratore all'identità</span><span class="sxs-lookup"><span data-stu-id="6ce4b-119">Associate a worker with your identity</span></span>

<span data-ttu-id="6ce4b-120">Per associare un lavoratore all'identità in LCS, effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="6ce4b-120">To associate a worker with your identity in LCS, follow these steps.</span></span>

1. <span data-ttu-id="6ce4b-121">Utilizzare il menu a sinistra e scegliere **Moduli \> Vendita al dettaglio e commercio \> Dipendenti \> Lavoratori**.</span><span class="sxs-lookup"><span data-stu-id="6ce4b-121">Use the menu on the left to go to **Modules \> Retail and commerce \> Employees \> Workers**.</span></span>
1. <span data-ttu-id="6ce4b-122">Nell'elenco trovare e selezionare il seguente record **000713 - Andrew Collette**.</span><span class="sxs-lookup"><span data-stu-id="6ce4b-122">In the list, find and select the following record: **000713 - Andrew Collette**.</span></span>
1. <span data-ttu-id="6ce4b-123">Nel riquadro azioni fare clic su **Vendita al dettaglio**.</span><span class="sxs-lookup"><span data-stu-id="6ce4b-123">On the Action Pane, select **Retail**.</span></span>
1. <span data-ttu-id="6ce4b-124">Selezionare **Associa identità esistente**.</span><span class="sxs-lookup"><span data-stu-id="6ce4b-124">Select **Associate existing identity**.</span></span>
1. <span data-ttu-id="6ce4b-125">Nel campo **Indirizzo di posta elettronica** a destra di **Cerca tramite posta elettronica**, digitare il proprio indirizzo di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="6ce4b-125">In the **Email** field to the right of **Search using email**, enter your email address.</span></span>
1. <span data-ttu-id="6ce4b-126">Selezionare **Cerca**.</span><span class="sxs-lookup"><span data-stu-id="6ce4b-126">Select **Search**.</span></span>
1. <span data-ttu-id="6ce4b-127">Selezionare il record con il proprio nome.</span><span class="sxs-lookup"><span data-stu-id="6ce4b-127">Select the record that has your name.</span></span>
1. <span data-ttu-id="6ce4b-128">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="6ce4b-128">Select **OK**.</span></span>
1. <span data-ttu-id="6ce4b-129">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="6ce4b-129">Select **Save**.</span></span>

### <a name="activate-cloud-pos"></a><span data-ttu-id="6ce4b-130">Attivare il Cloud POS</span><span class="sxs-lookup"><span data-stu-id="6ce4b-130">Activate Cloud POS</span></span>

<span data-ttu-id="6ce4b-131">Per attivare Cloud POS in LCS, attenersi alla seguente procedura.</span><span class="sxs-lookup"><span data-stu-id="6ce4b-131">To activate Cloud POS in LCS, follow these steps.</span></span>

1. <span data-ttu-id="6ce4b-132">Nel menu superiore, selezionare **Distribuzione ambienti ospitati nel cloud**.</span><span class="sxs-lookup"><span data-stu-id="6ce4b-132">On the top menu, select **Cloud-hosted environments**.</span></span>
1. <span data-ttu-id="6ce4b-133">Selezionare l'ambiente nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="6ce4b-133">Select your environment in the list.</span></span>
1. <span data-ttu-id="6ce4b-134">Nelle informazioni sull'ambiente a destra, selezionare **Dettagli completi**.</span><span class="sxs-lookup"><span data-stu-id="6ce4b-134">In the environment information on the right, select **Full details**.</span></span>
1. <span data-ttu-id="6ce4b-135">Selezionare **Accesso**per aprire un menu, quindi selezionare **Accedi a POS Cloud** per aprire il POS.</span><span class="sxs-lookup"><span data-stu-id="6ce4b-135">Select **Login** to open a menu, and then select **Log on to Cloud Point of Sale** to open the point of sale (POS).</span></span>
1. <span data-ttu-id="6ce4b-136">Selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="6ce4b-136">Select **Next**.</span></span>
1. <span data-ttu-id="6ce4b-137">Accedere usando l'account Microsoft Azure Active Directory ( Azure AD).</span><span class="sxs-lookup"><span data-stu-id="6ce4b-137">Sign in by using your Microsoft Azure Active Directory (Azure AD) account.</span></span>
1. <span data-ttu-id="6ce4b-138">In **Nome punto vendita**, scegliere **San Francisco**.</span><span class="sxs-lookup"><span data-stu-id="6ce4b-138">Under **Store name**, select **San Francisco**.</span></span>
1. <span data-ttu-id="6ce4b-139">Selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="6ce4b-139">Select **Next**.</span></span>
1. <span data-ttu-id="6ce4b-140">In **Registro e dispositivo**, scegliere **SANFRAN-1**.</span><span class="sxs-lookup"><span data-stu-id="6ce4b-140">Under **Register and device**, select **SANFRAN-1**.</span></span>
1. <span data-ttu-id="6ce4b-141">Selezionare **Attiva**.</span><span class="sxs-lookup"><span data-stu-id="6ce4b-141">Select **Activate**.</span></span> <span data-ttu-id="6ce4b-142">Si verrà disconnessi e indirizzati alla pagina di accesso POS.</span><span class="sxs-lookup"><span data-stu-id="6ce4b-142">You're signed out and taken to the POS sign-in page.</span></span>
1. <span data-ttu-id="6ce4b-143">A questo punto è possibile accedere all'esperienza Cloud POS utilizzando l'ID operatore **000713** e la password **123**.</span><span class="sxs-lookup"><span data-stu-id="6ce4b-143">You can now sign in to the Cloud POS experience by using operator ID **000713** and password **123**.</span></span>

## <a name="set-up-your-site-in-commerce"></a><span data-ttu-id="6ce4b-144">Configurare il sito in Commerce</span><span class="sxs-lookup"><span data-stu-id="6ce4b-144">Set up your site in Commerce</span></span>

<span data-ttu-id="6ce4b-145">Per iniziare a configurare il sito di anteprima in Commerce, attenersi alla seguente procedura.</span><span class="sxs-lookup"><span data-stu-id="6ce4b-145">To start to set up your preview site in Commerce, follow these steps.</span></span>

1. <span data-ttu-id="6ce4b-146">Accedere allo strumento di gestione del sito Commerce utilizzando l'URL annotato durante l'inizializzazione di e-Commerce durante il provisioning (vedere [Inizializzare e-Commerce ](provisioning-guide.md#initialize-e-commerce)).</span><span class="sxs-lookup"><span data-stu-id="6ce4b-146">Sign in to the site management tool by using the URL that you made a note of when you initialized e-Commerce during provisioning (see [Initialize e-Commerce](provisioning-guide.md#initialize-e-commerce)).</span></span>
1. <span data-ttu-id="6ce4b-147">Selezionare il sito **Fabrikam** per aprire la finestra di dialogo di impostazione del sito.</span><span class="sxs-lookup"><span data-stu-id="6ce4b-147">Select the **Fabrikam** site to open the site setup dialog box.</span></span>
1. <span data-ttu-id="6ce4b-148">Selezionare il dominio inserito quando è stato inizializzato e-Commerce.</span><span class="sxs-lookup"><span data-stu-id="6ce4b-148">Select the domain that you entered when you initialized e-Commerce.</span></span>
1. <span data-ttu-id="6ce4b-149">Come canale predefinito, selezionare **Punto vendita online esteso Fabrikam**.</span><span class="sxs-lookup"><span data-stu-id="6ce4b-149">Select **Fabrikam extended online store** as the default channel.</span></span> <span data-ttu-id="6ce4b-150">Assicurarsi di selezionare il punto vendita online **esteso**.</span><span class="sxs-lookup"><span data-stu-id="6ce4b-150">(Make sure that you select the **extended** online store.)</span></span>
1. <span data-ttu-id="6ce4b-151">Come lingua predefinita, selezionare **en-us**.</span><span class="sxs-lookup"><span data-stu-id="6ce4b-151">Select **en-us** as the default language.</span></span>
1. <span data-ttu-id="6ce4b-152">Lascia invariato valore del campo **Percorso**.</span><span class="sxs-lookup"><span data-stu-id="6ce4b-152">Leave the value of the **Path** field as it is.</span></span>
1. <span data-ttu-id="6ce4b-153">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="6ce4b-153">Select **OK**.</span></span> <span data-ttu-id="6ce4b-154">Viene visualizzato l'elenco delle pagine del sito.</span><span class="sxs-lookup"><span data-stu-id="6ce4b-154">The list of pages on the site appears.</span></span>

## <a name="enable-jobs"></a><span data-ttu-id="6ce4b-155">Abilitare i processi</span><span class="sxs-lookup"><span data-stu-id="6ce4b-155">Enable jobs</span></span>

<span data-ttu-id="6ce4b-156">Per abilitare i processi in Commerce, effettuare le operazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="6ce4b-156">To enable jobs in Commerce, follow these steps.</span></span>

1. <span data-ttu-id="6ce4b-157">Accedere all'ambiente (HQ).</span><span class="sxs-lookup"><span data-stu-id="6ce4b-157">Sign in to the environment (HQ).</span></span>
1. <span data-ttu-id="6ce4b-158">Utilizzare il menu a sinistra per andare a **Vendita al dettaglio e commercio \> Richieste di informazioni e report \> Processi batch**.</span><span class="sxs-lookup"><span data-stu-id="6ce4b-158">Use the menu on the left to go to **Retail and commerce \> Inquiries and reports \> Batch jobs**.</span></span>

    <span data-ttu-id="6ce4b-159">Le fasi restanti di questa procedura devono essere completate per ciascuno dei seguenti processi:</span><span class="sxs-lookup"><span data-stu-id="6ce4b-159">The remaining steps of this procedure must be completed for each of the following jobs:</span></span>

    * <span data-ttu-id="6ce4b-160">Elabora notifica tramite posta elettronica di ordine di vendita al dettaglio</span><span class="sxs-lookup"><span data-stu-id="6ce4b-160">Process retail order email notification</span></span>
    * <span data-ttu-id="6ce4b-161">Disponibilità prodotto</span><span class="sxs-lookup"><span data-stu-id="6ce4b-161">Product availability</span></span>
    * <span data-ttu-id="6ce4b-162">P-0001</span><span class="sxs-lookup"><span data-stu-id="6ce4b-162">P-0001</span></span>
    * <span data-ttu-id="6ce4b-163">Sincronizza processo di ordini</span><span class="sxs-lookup"><span data-stu-id="6ce4b-163">Synchronize orders job</span></span>

1. <span data-ttu-id="6ce4b-164">Utilizzare il filtro rapido per cercare il processo per nome.</span><span class="sxs-lookup"><span data-stu-id="6ce4b-164">Use the Quick Filter to search for the job by name.</span></span>
1. <span data-ttu-id="6ce4b-165">Se lo stato del processo è **Trattenuto**, effettuare le seguenti operazioni:</span><span class="sxs-lookup"><span data-stu-id="6ce4b-165">If the status of the job is **Withhold**, follow these steps:</span></span>

    1. <span data-ttu-id="6ce4b-166">Selezionare il record.</span><span class="sxs-lookup"><span data-stu-id="6ce4b-166">Select the record.</span></span>
    1. <span data-ttu-id="6ce4b-167">Nel riquadro azioni, sulla scheda **Processo batch** selezionare **Cambia stato**.</span><span class="sxs-lookup"><span data-stu-id="6ce4b-167">On the Action Pane, on **Batch job** tab, select **Change status**.</span></span>
    1. <span data-ttu-id="6ce4b-168">Selezionare **In attesa** e quindi **OK**.</span><span class="sxs-lookup"><span data-stu-id="6ce4b-168">Select **Waiting**, and then select **OK**.</span></span>

### <a name="run-full-data-synchronization"></a><span data-ttu-id="6ce4b-169">Eseguire la sincronizzazione dati completa</span><span class="sxs-lookup"><span data-stu-id="6ce4b-169">Run full data synchronization</span></span>

<span data-ttu-id="6ce4b-170">Per eseguire la sincronizzazione completa dei dati in Commerce, attenersi alla seguente procedura.</span><span class="sxs-lookup"><span data-stu-id="6ce4b-170">To run full data synchronization in Commerce, follow these steps.</span></span>

1. <span data-ttu-id="6ce4b-171">Utilizzare il menu a sinistra per andare a **Moduli \> Vendita al dettaglio e commercio \> Impostazione sedi centrali \> Utilità di pianificazione commercio \> Database canale**.</span><span class="sxs-lookup"><span data-stu-id="6ce4b-171">Use the menu on the left to go to **Modules \> Retail and commerce \> Headquarters setup \> Commerce scheduler \> Channel database**.</span></span>
1. <span data-ttu-id="6ce4b-172">Il canale**Predefinito** è selezionato nell'elenco a sinistra.</span><span class="sxs-lookup"><span data-stu-id="6ce4b-172">In the list on the left, the **Default** channel is selected.</span></span> <span data-ttu-id="6ce4b-173">Selezionare l'altro canale disponibile.</span><span class="sxs-lookup"><span data-stu-id="6ce4b-173">Select the other available channel.</span></span> <span data-ttu-id="6ce4b-174">Questo canale è denominato **scXXXXXXXXX**.</span><span class="sxs-lookup"><span data-stu-id="6ce4b-174">This channel is named **scXXXXXXXXX**.</span></span>
1. <span data-ttu-id="6ce4b-175">Selezionare **Sincronizzazione dati completa** nel riquadro azioni.</span><span class="sxs-lookup"><span data-stu-id="6ce4b-175">On the Action Pane, select **Full data sync**.</span></span>
1. <span data-ttu-id="6ce4b-176">Immettere **9999** come programmazione della distribuzione.</span><span class="sxs-lookup"><span data-stu-id="6ce4b-176">Enter **9999** as the distribution schedule.</span></span>
1. <span data-ttu-id="6ce4b-177">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="6ce4b-177">Select **OK**.</span></span>
1. <span data-ttu-id="6ce4b-178">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="6ce4b-178">Select **OK**.</span></span>

### <a name="test-credit-card-information-to-do-test-purchases"></a><span data-ttu-id="6ce4b-179">Verificare le informazioni sulla carta di credito per effettuare acquisti di prova</span><span class="sxs-lookup"><span data-stu-id="6ce4b-179">Test credit card information to do test purchases</span></span>

<span data-ttu-id="6ce4b-180">Per eseguire transazioni di prova nel sito, è possibile utilizzare le seguenti informazioni della carta di credito di prova:</span><span class="sxs-lookup"><span data-stu-id="6ce4b-180">To perform test transactions on the site, you can use the following test credit card information:</span></span>

- <span data-ttu-id="6ce4b-181">**Numero carta:** 4111-1111-1111-1111</span><span class="sxs-lookup"><span data-stu-id="6ce4b-181">**Card number:** 4111-1111-1111-1111</span></span>
- <span data-ttu-id="6ce4b-182">**Data di scadenza:** 10/20</span><span class="sxs-lookup"><span data-stu-id="6ce4b-182">**Expiration date:** 10/20</span></span>
- <span data-ttu-id="6ce4b-183">**Codice valore di verifica carta (CVV):** 737</span><span class="sxs-lookup"><span data-stu-id="6ce4b-183">**Card verification value (CVV) code:** 737</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6ce4b-184">Non utilizzare mai le informazioni di una carta di credito reale nel sito di prova.</span><span class="sxs-lookup"><span data-stu-id="6ce4b-184">Never, under any circumstances, try to use actual credit card information on the test site.</span></span>

## <a name="next-steps"></a><span data-ttu-id="6ce4b-185">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="6ce4b-185">Next steps</span></span>

<span data-ttu-id="6ce4b-186">Dopo aver completato le fasi di provisioning e configurazione, sei pronto per valutare l'ambiente di anteprima.</span><span class="sxs-lookup"><span data-stu-id="6ce4b-186">After the provisioning and configuration steps are completed, you're ready to evaluate your preview environment.</span></span> <span data-ttu-id="6ce4b-187">Utilizzare l'URL dello strumento di gestione del sito di Commerce per accedere all'esperienza di creazione.</span><span class="sxs-lookup"><span data-stu-id="6ce4b-187">Use the URL of the Commerce site management tool to go to the authoring experience.</span></span> <span data-ttu-id="6ce4b-188">Utilizzare l'URL dello strumento di gestione del sito di Commerce per accedere all'esperienza del sito dei clienti di vendita al dettaglio.</span><span class="sxs-lookup"><span data-stu-id="6ce4b-188">Use the URL of the Commerce site to go to the retail customer site experience.</span></span>

<span data-ttu-id="6ce4b-189">Per configurare funzionalità facoltative per l'ambiente di anteprima Commerce, vedere [Configurare le funzionalità facoltative per un ambiente di anteprima Commerce](cpe-optional-features.md).</span><span class="sxs-lookup"><span data-stu-id="6ce4b-189">To configure optional features for your Commerce preview environment, see [Configure optional features for a Commerce preview environment](cpe-optional-features.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="6ce4b-190">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="6ce4b-190">Additional resources</span></span>

[<span data-ttu-id="6ce4b-191">Panoramica dell'ambiente di anteprima Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="6ce4b-191">Dynamics 365 Commerce preview environment overview</span></span>](cpe-overview.md)

[<span data-ttu-id="6ce4b-192">Eseguire il provisioning dell'ambiente di anteprima di Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="6ce4b-192">Provision a Dynamics 365 Commerce preview environment</span></span>](provisioning-guide.md)

[<span data-ttu-id="6ce4b-193">Configurare le funzionalità facoltative per un ambiente di anteprima Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="6ce4b-193">Configure optional features for a Dynamics 365 Commerce preview environment</span></span>](cpe-optional-features.md)

[<span data-ttu-id="6ce4b-194">Domande frequenti sull'ambiente di anteprima Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="6ce4b-194">Dynamics 365 Commerce preview environment FAQ</span></span>](cpe-faq.md)

[<span data-ttu-id="6ce4b-195">Microsoft Lifecycle Services (LCS)</span><span class="sxs-lookup"><span data-stu-id="6ce4b-195">Microsoft Lifecycle Services (LCS)</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide)

[<span data-ttu-id="6ce4b-196">Retail Cloud Scale Unit (RCSU)</span><span class="sxs-lookup"><span data-stu-id="6ce4b-196">Retail Cloud Scale Unit (RCSU)</span></span>](https://docs.microsoft.com/business-applications-release-notes/october18/dynamics365-retail/retail-cloud-scale-unit)

[<span data-ttu-id="6ce4b-197">Portale di Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="6ce4b-197">Microsoft Azure portal</span></span>](https://azure.microsoft.com/features/azure-portal)

[<span data-ttu-id="6ce4b-198">Sito Web di Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="6ce4b-198">Dynamics 365 Commerce website</span></span>](https://aka.ms/Dynamics365CommerceWebsite)
