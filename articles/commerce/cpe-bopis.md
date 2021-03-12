---
title: Configurare uno scenario BOPIS in un ambiente di valutazione Dynamics 365 Commerce
description: Questo argomento spiega come configurare "acquisto online, ritiro in negozio" (BOPIS) in un ambiente di valutazione Microsoft Dynamics 365 Commerce dopo il provisioning.
author: rubendel
manager: annbe
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: rubendel
ms.search.validFrom: 2020-04-20
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: ec1c556a70ed92a40d3cb2bf45fb6156b7dbf7fd
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4993477"
---
# <a name="configure-bopis-in-a-dynamics-365-commerce-evaluation-environment"></a><span data-ttu-id="51889-103">Configurare uno scenario BOPIS in un ambiente di valutazione Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="51889-103">Configure BOPIS in a Dynamics 365 Commerce evaluation environment</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="51889-104">Questo argomento spiega come configurare "acquisto online, ritiro in negozio" (BOPIS) in un ambiente di valutazione Microsoft Dynamics 365 Commerce dopo il provisioning dell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="51889-104">This topic explains how to configure buy online, pickup in store (BOPIS) in a Microsoft Dynamics 365 Commerce evaluation environment after the environment has been provisioned.</span></span>

## <a name="prerequisite"></a><span data-ttu-id="51889-105">Prerequisito</span><span class="sxs-lookup"><span data-stu-id="51889-105">Prerequisite</span></span>

<span data-ttu-id="51889-106">Completare le procedure in questo argomento solo dopo aver effettuato il provisioning e la configurazione dell'ambiente di valutazione Commerce.</span><span class="sxs-lookup"><span data-stu-id="51889-106">Complete the procedures in this topic only after your Commerce evaluation environment has been provisioned and configured.</span></span> <span data-ttu-id="51889-107">Per informazioni relative a come effettuare il provisioning e la configurazione dell'ambiente, consultare [Provisioning di un ambiente di valutazione Dynamics 365 Commerce](provisioning-guide.md) e [Configurare un ambiente di valutazione Dynamics 365 Commerce](https://docs.microsoft.com/dynamics365/commerce/cpe-post-provisioning).</span><span class="sxs-lookup"><span data-stu-id="51889-107">For information about how to provision and configure your environment, see [Provision a Dynamics 365 Commerce evaluation environment](provisioning-guide.md) and [Configure a Dynamics 365 Commerce evaluation environment](https://docs.microsoft.com/dynamics365/commerce/cpe-post-provisioning).</span></span>

<span data-ttu-id="51889-108">Dopo aver eseguito il provisioning e la configurazione dell'ambiente Commerce end-to-end, è possibile utilizzare questo argomento per abilitare gli scenari BOPIS.</span><span class="sxs-lookup"><span data-stu-id="51889-108">After your Commerce environment has been provisioned and configured end to end, you can use this topic to enable BOPIS scenarios.</span></span>

## <a name="configure-the-pos"></a><span data-ttu-id="51889-109">Configurare il POS</span><span class="sxs-lookup"><span data-stu-id="51889-109">Configure the POS</span></span>

### <a name="configure-modern-pos"></a><span data-ttu-id="51889-110">Configurare Modern POS</span><span class="sxs-lookup"><span data-stu-id="51889-110">Configure Modern POS</span></span>

<span data-ttu-id="51889-111">Gli scenari BOPIS che prevedono il pagamento con carta di credito richiedono una stazione hardware.</span><span class="sxs-lookup"><span data-stu-id="51889-111">BOPIS scenarios that involve a credit card payment require a hardware station.</span></span> <span data-ttu-id="51889-112">La stazione hardware è integrata nei client Modern POS per Windows e Android.</span><span class="sxs-lookup"><span data-stu-id="51889-112">The hardware station is built into Modern POS for Windows and Android clients.</span></span> <span data-ttu-id="51889-113">Se si utilizza Cloud POS o Modern POS per iOS, il client del punto vendita (POS) deve essere associato a una stazione hardware condivisa.</span><span class="sxs-lookup"><span data-stu-id="51889-113">If you're using Cloud POS or Modern POS for iOS, the point of sale (POS) client must be paired with a shared hardware station.</span></span> <span data-ttu-id="51889-114">Questo argomento spiega come configurare BOPIS per client Windows e Android.</span><span class="sxs-lookup"><span data-stu-id="51889-114">This topic explains how to configure BOPIS for Windows and Android clients.</span></span> <span data-ttu-id="51889-115">Per ulteriori informazioni su come configurare una stazione hardware condivisa, vedere [Configurare e installare Retail Hardware Station](https://docs.microsoft.com/dynamics365/commerce/retail-hardware-station-configuration-installation).</span><span class="sxs-lookup"><span data-stu-id="51889-115">For information about how to set up a shared hardware station, see [Configure and install Retail hardware station](https://docs.microsoft.com/dynamics365/commerce/retail-hardware-station-configuration-installation).</span></span>

1. <span data-ttu-id="51889-116">Passare a **Retail e Commerce \> Impostazione canale \> Impostazione POS \> Registratori di cassa**.</span><span class="sxs-lookup"><span data-stu-id="51889-116">Go to **Retail and Commerce \> Channel setup \> POS setup \> Registers**.</span></span>
2. <span data-ttu-id="51889-117">Selezionare il registratore **SANFRAN-5**, quindi selezionare **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="51889-117">Select register **SANFRAN-5**, and then select **Edit**.</span></span>
3. <span data-ttu-id="51889-118">Modificare il valore del campo **Profilo hardware** da **HW002** in **HW001**, quindi selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="51889-118">Change the value of the **Hardware profile** field from **HW002** to **HW001**, and then select **Save**.</span></span>
4. <span data-ttu-id="51889-119">Per sincronizzare le modifiche, andare a **Retail e Commerce \> Vendita al dettaglio e commercio IT \> Programmazione della distribuzione**.</span><span class="sxs-lookup"><span data-stu-id="51889-119">To synchronize the changes, go to **Retail and Commerce \> Retail and Commerce IT \> Distribution schedule**.</span></span>
5. <span data-ttu-id="51889-120">Selezionare la programmazione della distribuzione **1090**, quindi nel riquadro azioni selezionare **Esegui adesso**.</span><span class="sxs-lookup"><span data-stu-id="51889-120">Select distribution schedule **1090**, and then, on the Action Pane, select **Run now**.</span></span>
6. <span data-ttu-id="51889-121">Selezionare **Sì** e poi **OK** per avviare la sincronizzazione dei dati.</span><span class="sxs-lookup"><span data-stu-id="51889-121">Select **Yes** and then **OK** to initiate data synchronization.</span></span> 

### <a name="install-modern-pos"></a><span data-ttu-id="51889-122">Installare Modern POS</span><span class="sxs-lookup"><span data-stu-id="51889-122">Install Modern POS</span></span>

1. <span data-ttu-id="51889-123">Passare a **Retail e Commerce \> Impostazione canale \> Impostazione POS \> Dispositivi**.</span><span class="sxs-lookup"><span data-stu-id="51889-123">Go to **Retail and Commerce \> Channel setup \> POS setup \> Devices**.</span></span>
2. <span data-ttu-id="51889-124">Selezionare il dispositivo **SANFRANCIS-5**.</span><span class="sxs-lookup"><span data-stu-id="51889-124">Select device **SANFRANCIS-5**.</span></span>
3. <span data-ttu-id="51889-125">Nel riquadro azioni selezionare **Scarica**, quindi selezionare **File di configurazione**.</span><span class="sxs-lookup"><span data-stu-id="51889-125">On the Action Pane, select **Download**, and then select **Configuration file**.</span></span>
4. <span data-ttu-id="51889-126">Selezionare **Scarica** e quindi **Retail Modern POS**.</span><span class="sxs-lookup"><span data-stu-id="51889-126">Select **Download**, and then select **Retail Modern POS**.</span></span> 
5. <span data-ttu-id="51889-127">Quando il download del file **ModernPOSSetup.exe** è completato, selezionare **Apri file**.</span><span class="sxs-lookup"><span data-stu-id="51889-127">When download of the **ModernPOSSetup.exe** file is completed, select **Open file**.</span></span>

    ![Apri file](./dev-itpro/media/PAYMENTS/openfile.png)

6. <span data-ttu-id="51889-129">Selezionare **Avanti** per passare al processo di installazione.</span><span class="sxs-lookup"><span data-stu-id="51889-129">Select **Next** to go through the installation process.</span></span> <span data-ttu-id="51889-130">Al termine dell'installazione, selezionare **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="51889-130">When installation is completed, select **Close**.</span></span>

### <a name="activate-modern-pos"></a><span data-ttu-id="51889-131">Attivare Modern POS</span><span class="sxs-lookup"><span data-stu-id="51889-131">Activate Modern POS</span></span>

1. <span data-ttu-id="51889-132">Sul desktop di Windows, selezionare il pulsante **Start** e immettere **Retail Modern POS**.</span><span class="sxs-lookup"><span data-stu-id="51889-132">On the Windows desktop, select the **Start** button, and enter **Retail Modern POS**.</span></span>
2. <span data-ttu-id="51889-133">Selezionare l'applicazione **Retail Modern POS** per avviare l'attivazione.</span><span class="sxs-lookup"><span data-stu-id="51889-133">Select the **Retail Modern POS** application to initiate activation.</span></span>
3. <span data-ttu-id="51889-134">Selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="51889-134">Select **Next**.</span></span> <span data-ttu-id="51889-135">I campi **URL server**, **ID dispositivo** e **Numero registratore di cassa** devono essere preimpostati con le informazioni del file di configurazione scaricato nella procedura precedente.</span><span class="sxs-lookup"><span data-stu-id="51889-135">The **Server URL**, **Device ID**, and **Register number** fields should be preset by using information from the configuration file that you downloaded in the previous procedure.</span></span>
4. <span data-ttu-id="51889-136">Selezionare **Attiva**.</span><span class="sxs-lookup"><span data-stu-id="51889-136">Select **Activate**.</span></span>
5. <span data-ttu-id="51889-137">Viene visualizzata una finestra di dialogo di autenticazione.</span><span class="sxs-lookup"><span data-stu-id="51889-137">An authentication dialog box appears.</span></span> <span data-ttu-id="51889-138">Selezionare l'account che utilizza l'indirizzo di posta elettronica precedentemente associato al lavoratore **000713 - Andrew Collette**.</span><span class="sxs-lookup"><span data-stu-id="51889-138">Select the account that uses the email address that was previously associated with worker **000713 - Andrew Collette**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="51889-139">Se non hai ancora associato un lavoratore all'identità, l'attivazione avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="51889-139">If you haven't yet associated a worker with your identity, activation will be unsuccessful.</span></span> <span data-ttu-id="51889-140">In questo caso, seguire i passaggi nella sezione "Associare un lavoratore all'identità" nell'argomento [Configurare un ambiente di valutazione Dynamics 365 Commerce](cpe-post-provisioning.md#associate-a-worker-with-your-identity).</span><span class="sxs-lookup"><span data-stu-id="51889-140">In this case, follow the steps under the "Associate a worker with your identity" section in the [Configure a Dynamics 365 Commerce evaluation environment](cpe-post-provisioning.md#associate-a-worker-with-your-identity) topic.</span></span>
    
6. <span data-ttu-id="51889-141">Quando viene richiesto di consentire all'organizzazione di gestire il dispositivo, selezionare **Solo questa app**.</span><span class="sxs-lookup"><span data-stu-id="51889-141">When you're prompted to let your organization manage the device, select **This app only**.</span></span>
7. <span data-ttu-id="51889-142">Al termine dell'attivazione, selezionare **Inizia**.</span><span class="sxs-lookup"><span data-stu-id="51889-142">When activation is completed, select **Get started**.</span></span>

### <a name="enable-bopis-in-modern-pos"></a><span data-ttu-id="51889-143">Abilitare BOPIS in Modern POS</span><span class="sxs-lookup"><span data-stu-id="51889-143">Enable BOPIS in Modern POS</span></span>

1. <span data-ttu-id="51889-144">Accedere a Modern POS utilizzando **000713** come ID operatore e **123** come password.</span><span class="sxs-lookup"><span data-stu-id="51889-144">Sign in to Modern POS by using **000713** as the operator ID and **123** as the password.</span></span>
2. <span data-ttu-id="51889-145">Durante la riproduzione del video introduttivo, selezionare le due caselle di controllo nell'angolo inferiore sinistro della finestra di dialogo, quindi chiudere la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="51889-145">While the introductory walkthrough video is playing, select the two check boxes in the lower-left corner of the dialog box, and then close the dialog box.</span></span>
3. <span data-ttu-id="51889-146">Se non viene richiesto di chiudere il turno, scorrere verso destra nella pagina di **benvenuto**, selezionare **Chiudi turno**, quindi accedere nuovamente al POS.</span><span class="sxs-lookup"><span data-stu-id="51889-146">If you aren't prompted to close the shift, scroll to the right on the **Welcome** page, select **Close shift**, and then sign back in to the POS.</span></span>
4. <span data-ttu-id="51889-147">Dopo aver effettuato l'accesso, quando richiesto, selezionare **Eseguire un'operazione non relativa al cassetto**.</span><span class="sxs-lookup"><span data-stu-id="51889-147">After you're signed in, when you're prompted, select **Perform a non-drawer operation**.</span></span>
5. <span data-ttu-id="51889-148">Nella pagina di **benvenuto**, scorrere verso destra e selezionare l'operazione **Seleziona stazione hardware**.</span><span class="sxs-lookup"><span data-stu-id="51889-148">On the **Welcome** page, scroll to the right, and select the **Select hardware station** operation.</span></span>
6. <span data-ttu-id="51889-149">Selezionare **Gestione**, impostare l'opzione **Usa stazione hardware** su **Attivo**, quindi selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="51889-149">Select **Manage**, set the **Use hardware station** option to **On**, and then select **OK**.</span></span>
7. <span data-ttu-id="51889-150">Uscire dal POS, e quindi accedere di nuovo.</span><span class="sxs-lookup"><span data-stu-id="51889-150">Sign out of the POS, and then sign back in.</span></span>
8. <span data-ttu-id="51889-151">Dopo aver effettuato l'accesso, selezionare **Apri un nuovo turno**, quindi selezionare **Cassetto**.</span><span class="sxs-lookup"><span data-stu-id="51889-151">After you're signed in, select **Open a new shift**, and then select **Drawer**.</span></span>

## <a name="complete-a-bopis-scenario"></a><span data-ttu-id="51889-152">Completare uno scenario BOPIS</span><span class="sxs-lookup"><span data-stu-id="51889-152">Complete a BOPIS scenario</span></span>

### <a name="create-a-storefront-order-for-in-store-pickup"></a><span data-ttu-id="51889-153">Creare un ordine di vetrina virtuale per il ritiro in negozio</span><span class="sxs-lookup"><span data-stu-id="51889-153">Create a storefront order for in-store pickup</span></span>

1. <span data-ttu-id="51889-154">Andare all'URL specificato nel passaggio [Inizializzare e-Commerce](https://docs.microsoft.com/dynamics365/commerce/provisioning-guide#initialize-e-commerce) durante la configurazione dell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="51889-154">Go to the URL that you specified in the [Initialize e-Commerce](https://docs.microsoft.com/dynamics365/commerce/provisioning-guide#initialize-e-commerce) step during environment configuration.</span></span>
2. <span data-ttu-id="51889-155">Selezionare un articolo e selezionare **Aggiungi al carrello**.</span><span class="sxs-lookup"><span data-stu-id="51889-155">Select an item, and select **Add to cart**.</span></span>
3. <span data-ttu-id="51889-156">Nella pagina del carrello, selezionare **Ritira** per la riga dell'ordine appena aggiunto.</span><span class="sxs-lookup"><span data-stu-id="51889-156">On the shopping bag page, select **Pick this up** for the order line that you just added.</span></span>
4. <span data-ttu-id="51889-157">Nella finestra di dialogo **Seleziona un negozio**, immettere **San Francisco**, quindi selezionare il pulsante **Ricerca**.</span><span class="sxs-lookup"><span data-stu-id="51889-157">In the **Select a store** dialog box, enter **San Francisco**, and then select the **Search** button.</span></span>
5. <span data-ttu-id="51889-158">Nell'elenco dei risultati, trovare il negozio San Francisco e selezionare **Preleva qui**.</span><span class="sxs-lookup"><span data-stu-id="51889-158">In the list of results, find the San Francisco store, and select **Pick up here**.</span></span>
6. <span data-ttu-id="51889-159">Nella pagina del carrello, selezionare **Checkout come ospite**.</span><span class="sxs-lookup"><span data-stu-id="51889-159">On the shopping bag page, select **Checkout as Guest**.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="51889-160">Per continuare con il checkout, è necessario accettare l'informativa sui cookie.</span><span class="sxs-lookup"><span data-stu-id="51889-160">To continue with checkout, you must accept the cookie notice.</span></span> <span data-ttu-id="51889-161">Questo avviso appare come un banner nella parte superiore della pagina di checkout.</span><span class="sxs-lookup"><span data-stu-id="51889-161">This notice appears as a banner at the top of the checkout page.</span></span>

7. <span data-ttu-id="51889-162">Per il metodo di pagamento con carta di credito, immettere i seguenti dettagli:</span><span class="sxs-lookup"><span data-stu-id="51889-162">For the credit card payment method, enter the following details:</span></span>

    - <span data-ttu-id="51889-163">**Nome del titolare:** immettere un nome.</span><span class="sxs-lookup"><span data-stu-id="51889-163">**Cardholder name:** Enter any name.</span></span>
    - <span data-ttu-id="51889-164">**Numero carta:** immettere **4111-1111-1111-1111**.</span><span class="sxs-lookup"><span data-stu-id="51889-164">**Card number:** Enter **4111-1111-1111-1111**.</span></span>
    - <span data-ttu-id="51889-165">**Data di scadenza:** immettere **10/20**.</span><span class="sxs-lookup"><span data-stu-id="51889-165">**Expiration date:** Enter **10/20**.</span></span>
    - <span data-ttu-id="51889-166">**Codice valore di verifica carta (CVV):** immettere **737**.</span><span class="sxs-lookup"><span data-stu-id="51889-166">**Card verification value (CVV) code:** Enter **737**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="51889-167">Non utilizzare mai le informazioni di una carta di credito reale nel sito di prova.</span><span class="sxs-lookup"><span data-stu-id="51889-167">Never, under any circumstances, try to use actual credit card information on the test site.</span></span>

8. <span data-ttu-id="51889-168">Continuare il checkout inserendo i dettagli dell'indirizzo di fatturazione, quindi selezionare **Salva e continua**.</span><span class="sxs-lookup"><span data-stu-id="51889-168">Continue with checkout by entering details of the billing address, and then select **Save and continue**.</span></span>
9. <span data-ttu-id="51889-169">Quando l'ordine è pronto per essere effettuato, selezionare **Checkout**.</span><span class="sxs-lookup"><span data-stu-id="51889-169">When the order is ready to be placed, select **Checkout**.</span></span>

### <a name="synchronize-online-orders-to-the-back-office"></a><span data-ttu-id="51889-170">Sincronizzare gli ordini online con il back office</span><span class="sxs-lookup"><span data-stu-id="51889-170">Synchronize online orders to the back office</span></span>

<span data-ttu-id="51889-171">Per informazioni su come sincronizzare gli ordini online, vedere [Registrazione di vendite e pagamenti online](https://docs.microsoft.com/dynamics365/commerce/tasks/posting-online-sales-payments).</span><span class="sxs-lookup"><span data-stu-id="51889-171">For information about how to synchronize online orders, see [Posting of online sales and payments](https://docs.microsoft.com/dynamics365/commerce/tasks/posting-online-sales-payments).</span></span>

### <a name="pick-up-an-order-in-the-store"></a><span data-ttu-id="51889-172">Prelevare un ordine nel punto vendita</span><span class="sxs-lookup"><span data-stu-id="51889-172">Pick up an order in the store</span></span>

1. <span data-ttu-id="51889-173">Accedere al POS.</span><span class="sxs-lookup"><span data-stu-id="51889-173">Sign in to the POS.</span></span>
2. <span data-ttu-id="51889-174">Nella schermata di **benvenuto**, selezionare **Evasione ordine**</span><span class="sxs-lookup"><span data-stu-id="51889-174">On the **Welcome** screen, select **Order fulfillment**</span></span>
3. <span data-ttu-id="51889-175">Nell'elenco degli articoli per il ritiro, selezionare la riga dell'ordine effettuato online.</span><span class="sxs-lookup"><span data-stu-id="51889-175">In the list of items for pickup, select the line from the order that was placed online.</span></span>
4. <span data-ttu-id="51889-176">Mentre la riga ordine è selezionata, selezionare **Preleva**.</span><span class="sxs-lookup"><span data-stu-id="51889-176">While the order line is selected, select **Pick up**.</span></span>

    <span data-ttu-id="51889-177">L'articolo della riga viene aggiunto alla schermata della transazione e **$ 0,00** viene visualizzato come saldo dovuto.</span><span class="sxs-lookup"><span data-stu-id="51889-177">The line item is added to the transaction screen, and **$0.00** is shown as the balance that is due.</span></span>

5. <span data-ttu-id="51889-178">Selezionare il saldo dovuto di **$ 0,00** oppure selezionare un metodo di pagamento per concludere la transazione.</span><span class="sxs-lookup"><span data-stu-id="51889-178">Select the balance due of **$0.00**, or select any payment method to conclude the transaction.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="51889-179">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="51889-179">Troubleshooting</span></span>

### <a name="online-orders-that-are-retrieved-in-the-pos-have-a-non-zero-balance-due"></a><span data-ttu-id="51889-180">Gli ordini online recuperati nel POS hanno un saldo dovuto diverso da zero</span><span class="sxs-lookup"><span data-stu-id="51889-180">Online orders that are retrieved in the POS have a non-zero balance due</span></span>

<span data-ttu-id="51889-181">Quando viene recuperato un ordine per il ritiro in negozio, se il saldo dovuto non è 0 (zero), assicurarsi che venga utilizzato Modern POS e che la stazione hardware sia attiva.</span><span class="sxs-lookup"><span data-stu-id="51889-181">When an order is retrieved for in-store pickup, if the balance due isn't 0 (zero), make sure that Modern POS is being used, and that the hardware station is active.</span></span> <span data-ttu-id="51889-182">Se si utilizza Cloud POS o Modern POS per iOS, assicurarsi che sia attiva una stazione hardware condivisa.</span><span class="sxs-lookup"><span data-stu-id="51889-182">If Cloud POS or Modern POS for iOS is being used, make sure that a shared hardware station is active.</span></span> <span data-ttu-id="51889-183">Per recuperare i pagamenti effettuati online è necessaria una forma di stazione hardware attiva.</span><span class="sxs-lookup"><span data-stu-id="51889-183">Some form of active hardware station is required to retrieve payments that were made online.</span></span>

### <a name="general-issues-with-payment-capture"></a><span data-ttu-id="51889-184">Problemi generali con l'acquisizione dei pagamenti</span><span class="sxs-lookup"><span data-stu-id="51889-184">General issues with payment capture</span></span>

<span data-ttu-id="51889-185">Per tutti i problemi generali, consultare sempre i log degli eventi Modern POS o Internet Information Services (IIS) Hardware Station come primo passo.</span><span class="sxs-lookup"><span data-stu-id="51889-185">For all general issues, you should always consult the Modern POS or Internet Information Services (IIS) Hardware Station event logs as a first step.</span></span> <span data-ttu-id="51889-186">È possibile trovare questi log nei seguenti nodi del registro eventi di Windows:</span><span class="sxs-lookup"><span data-stu-id="51889-186">You can find these logs under the following nodes in the Windows event log:</span></span>

- <span data-ttu-id="51889-187">Log dei servizi e dell'applicazione \> Microsoft \> Dynamics \> Commerce-ModernPOS</span><span class="sxs-lookup"><span data-stu-id="51889-187">Application and Services Logs \> Microsoft \> Dynamics \> Commerce-ModernPOS</span></span>
- <span data-ttu-id="51889-188">Log dei servizi e dell'applicazione \> Microsoft \> Dynamics \> Commerce-Hardware Station</span><span class="sxs-lookup"><span data-stu-id="51889-188">Application and Services Logs \> Microsoft \> Dynamics \> Commerce-Hardware Station</span></span>

## <a name="additional-resources"></a><span data-ttu-id="51889-189">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="51889-189">Additional resources</span></span>

[<span data-ttu-id="51889-190">Panoramica dell'ambiente di valutazione Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="51889-190">Dynamics 365 Commerce evaluation environment overview</span></span>](cpe-overview.md)

[<span data-ttu-id="51889-191">Provisioning di un ambiente di valutazione Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="51889-191">Provision a Dynamics 365 Commerce evaluation environment</span></span>](provisioning-guide.md)

[<span data-ttu-id="51889-192">Configurare le funzioni facoltative per un ambiente di valutazione Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="51889-192">Configure optional features for a Dynamics 365 Commerce evaluation environment</span></span>](cpe-optional-features.md)

[<span data-ttu-id="51889-193">Domande frequenti sull'ambiente di valutazione Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="51889-193">Dynamics 365 Commerce evaluation environment FAQ</span></span>](cpe-faq.md)

[<span data-ttu-id="51889-194">Microsoft Lifecycle Services (LCS)</span><span class="sxs-lookup"><span data-stu-id="51889-194">Microsoft Lifecycle Services (LCS)</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide)

[<span data-ttu-id="51889-195">Retail Cloud Scale Unit (RCSU)</span><span class="sxs-lookup"><span data-stu-id="51889-195">Retail Cloud Scale Unit (RCSU)</span></span>](https://docs.microsoft.com/business-applications-release-notes/october18/dynamics365-retail/retail-cloud-scale-unit)

[<span data-ttu-id="51889-196">Portale di Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="51889-196">Microsoft Azure portal</span></span>](https://azure.microsoft.com/features/azure-portal)

[<span data-ttu-id="51889-197">Sito Web di Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="51889-197">Dynamics 365 Commerce website</span></span>](https://aka.ms/Dynamics365CommerceWebsite)

[<span data-ttu-id="51889-198">Connettore pagamenti Adyen</span><span class="sxs-lookup"><span data-stu-id="51889-198">Adyen payment connector</span></span>](https://docs.microsoft.com/dynamics365/commerce/dev-itpro/adyen-connector?tabs=8-1-3)

[<span data-ttu-id="51889-199">Salvare gli strumenti di pagamento online con il connettore Adyen</span><span class="sxs-lookup"><span data-stu-id="51889-199">Saving online payment instruments with the Adyen connector</span></span>](https://docs.microsoft.com/dynamics365/commerce/dev-itpro/adyen-connector-listpi)

[<span data-ttu-id="51889-200">Panoramica dei pagamenti omnicanale</span><span class="sxs-lookup"><span data-stu-id="51889-200">Omni-channel payments overview</span></span>](https://docs.microsoft.com/dynamics365/commerce/omni-channel-payments)
