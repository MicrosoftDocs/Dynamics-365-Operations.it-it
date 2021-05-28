---
title: Supporto della funzione fiscale per ordini di trasferimento
description: In questo argomento viene illustrato il nuovo supporto della funzione fiscale per gli ordini di trasferimento utilizzando il servizio di calcolo delle imposte.
author: kailiang
ms.date: 04/20/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 3a5c2b6fb48d98ba045c77ed034d976f7d89af98
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2021
ms.locfileid: "6021371"
---
# <a name="tax-feature-support-for-transfer-orders"></a><span data-ttu-id="70b15-103">Supporto della funzione fiscale per ordini di trasferimento</span><span class="sxs-lookup"><span data-stu-id="70b15-103">Tax feature support for transfer orders</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="70b15-104">In questo argomento vengono fornite informazioni sul calcolo delle imposte e sull'integrazione della registrazione negli ordini di trasferimento.</span><span class="sxs-lookup"><span data-stu-id="70b15-104">This topic provides information about tax calculation and posting integration in transfer orders.</span></span> <span data-ttu-id="70b15-105">Questa funzionalità consente di impostare il calcolo delle imposte e la registrazione negli ordini di trasferimento per i trasferimenti di scorte.</span><span class="sxs-lookup"><span data-stu-id="70b15-105">This functionality lets you set up tax calculation and posting in transfer orders for stock transfers.</span></span> <span data-ttu-id="70b15-106">Ai sensi della normativa sull'imposta sul valore aggiunto (IVA) dell'Unione europea (UE), i trasferimenti di scorte sono considerati fornitura intracomunitaria e acquisizioni intracomunitarie.</span><span class="sxs-lookup"><span data-stu-id="70b15-106">Under European Union (EU) value-added tax (VAT) regulations, stock transfers are considered intra-community supply and intra-community acquisitions.</span></span>

<span data-ttu-id="70b15-107">Per configurare e utilizzare questa funzionalità, è necessario completare tre passaggi principali:</span><span class="sxs-lookup"><span data-stu-id="70b15-107">To configure and use this functionality, you must complete three main steps:</span></span>

1. <span data-ttu-id="70b15-108">**Configurazione RCS:** In Regulatory Configuration Service, imposta la funzione fiscale, i codici imposta e l'applicabilità dei codici imposta per la determinazione del codice imposta negli ordini di trasferimento.</span><span class="sxs-lookup"><span data-stu-id="70b15-108">**RCS setup:** In Regulatory Configuration Service, set up the tax feature, tax codes, and tax codes applicability for tax code determination in transfer orders.</span></span>
2. <span data-ttu-id="70b15-109">**Configurazione Finance:** In Microsoft Dynamics 365 Finance, attiva la funzionalità **Imposta in ordine di trasferimento**, imposta i parametri del servizio fiscale per l'inventario e imposta i parametri fiscali di base.</span><span class="sxs-lookup"><span data-stu-id="70b15-109">**Finance setup:** In Microsoft Dynamics 365 Finance, turn on the **Tax in transfer order** feature, set up the tax service parameters for inventory, and set up core tax parameters.</span></span>
3. <span data-ttu-id="70b15-110">**Configurazione inventario:** Imposta la configurazione dell'inventario per le transazioni degli ordini di trasferimento.</span><span class="sxs-lookup"><span data-stu-id="70b15-110">**Inventory setup:** Set up the inventory configuration for transfer order transactions.</span></span>

## <a name="set-up-rcs-for-tax-and-transfer-order-transactions"></a><span data-ttu-id="70b15-111">Impostare RCS per le transazioni di imposte e ordini di trasferimento</span><span class="sxs-lookup"><span data-stu-id="70b15-111">Set up RCS for tax and transfer order transactions</span></span>

<span data-ttu-id="70b15-112">Segui questi passaggi per configurare l'imposta applicata in un ordine di trasferimento.</span><span class="sxs-lookup"><span data-stu-id="70b15-112">Follow these steps to set up the tax that is involved in a transfer order.</span></span> <span data-ttu-id="70b15-113">Nell'esempio mostrato qui, l'ordine di trasferimento è dai Paesi Bassi al Belgio.</span><span class="sxs-lookup"><span data-stu-id="70b15-113">In the example that is shown here, the transfer order is from the Netherlands to Belgium.</span></span>

1. <span data-ttu-id="70b15-114">Nella pagina **Funzionalità fiscali**, nella scheda **Versioni** seleziona la versione bozza della funzionalità, quindi selezionare **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="70b15-114">On the **Tax features** page, on the **Versions** tab, select the draft feature version, and then select **Edit**.</span></span>

    ![Selezione di Modifica](../media/tax-feature-support-01.png)

2. <span data-ttu-id="70b15-116">Nella pagina **Configurazione funzioni fiscali** nella scheda **Codici imposta** seleziona **Aggiungi** per creare nuovi codici imposta.</span><span class="sxs-lookup"><span data-stu-id="70b15-116">On the **Tax features setup** page, on the **Tax codes** tab, select **Add** to create new tax codes.</span></span> <span data-ttu-id="70b15-117">Per questo esempio, vengono creati tre codici imposta: **NL-Exempt**, **BE-RC-21**, e **BE-RC+21**.</span><span class="sxs-lookup"><span data-stu-id="70b15-117">For this example, three tax codes are created: **NL-Exempt**, **BE-RC-21**, and **BE-RC+21**.</span></span>

    - <span data-ttu-id="70b15-118">Quando un ordine di trasferimento viene spedito da un magazzino nei Paesi Bassi, il codice imposta olandese esente da IVA (**NL-Exempt**) viene applicato.</span><span class="sxs-lookup"><span data-stu-id="70b15-118">When a transfer order is shipped from a warehouse in the Netherlands, the Netherlands VAT exempted tax code (**NL-Exempt**) is applied.</span></span>
      
        <span data-ttu-id="70b15-119">Crea il codice imposta **NL-Exempt**.</span><span class="sxs-lookup"><span data-stu-id="70b15-119">Create the tax code **NL-Exempt**.</span></span>
        1. <span data-ttu-id="70b15-120">Seleziona **Aggiungi**, immetti **NL-Exempt** nel campo **Codice imposta**.</span><span class="sxs-lookup"><span data-stu-id="70b15-120">Select **Add**, enter **NL-Exempt** in the **Tax code** field.</span></span>
        2. <span data-ttu-id="70b15-121">Seleziona **Per importo netto** nel campo **Componente fiscale**.</span><span class="sxs-lookup"><span data-stu-id="70b15-121">Select **By Net Amount** in the **Tax component** field.</span></span>
        3. <span data-ttu-id="70b15-122">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="70b15-122">Select **Save**.</span></span>
        4. <span data-ttu-id="70b15-123">Nella tabella **Tasso** seleziona **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="70b15-123">Select **Add** in the **Rate** table.</span></span>
        5. <span data-ttu-id="70b15-124">Imposta **Esente** su **Sì** nella sezione **Generale**.</span><span class="sxs-lookup"><span data-stu-id="70b15-124">Swtich **Is Exempt** to **Yes** in the **General** section.</span></span>

        ![Codice imposta NL-Exempt](../media/tax-feature-support-02.png)

    - <span data-ttu-id="70b15-126">Quando un ordine di trasferimento viene ricevuto in un magazzino in Belgio, il meccanismo di reverse charge viene applicato utilizzando i codici imposta **BE-RC-21** e **BE-RC+21**.</span><span class="sxs-lookup"><span data-stu-id="70b15-126">When a transfer order is received at a Belgium warehouse, the reverse charge mechanism is applied by using the **BE-RC-21** and **BE-RC+21** tax codes.</span></span>
        
        <span data-ttu-id="70b15-127">Crea il codice imposta **BE-RC-21**.</span><span class="sxs-lookup"><span data-stu-id="70b15-127">Create the tax code **BE-RC-21**.</span></span>      
        1. <span data-ttu-id="70b15-128">Seleziona **Aggiungi**, immetti **BE-RC-21** nel campo **Codice imposta**.</span><span class="sxs-lookup"><span data-stu-id="70b15-128">Select **Add**, enter **BE-RC-21** in the **Tax code** field.</span></span>
        2. <span data-ttu-id="70b15-129">Seleziona **Per importo netto** nel campo **Componente fiscale**.</span><span class="sxs-lookup"><span data-stu-id="70b15-129">Select **By Net Amount** in the **Tax component** field.</span></span>
        3. <span data-ttu-id="70b15-130">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="70b15-130">Select **Save**.</span></span>
        4. <span data-ttu-id="70b15-131">Nella tabella **Tasso** seleziona **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="70b15-131">Select **Add** in the **Rate** table.</span></span>
        5. <span data-ttu-id="70b15-132">Immetti **-21** nel campo **Aliquota imposta**.</span><span class="sxs-lookup"><span data-stu-id="70b15-132">Enter **-21** in the **Tax Rate** field.</span></span>
        6. <span data-ttu-id="70b15-133">Imposta **Reverse Charge** su **Sì** nella sezione **Generale**.</span><span class="sxs-lookup"><span data-stu-id="70b15-133">Swtich **Is Reverse Charge** to **Yes** in the **General** section.</span></span>
        7. <span data-ttu-id="70b15-134">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="70b15-134">Select **Save**.</span></span>

        ![Codice imposta BE-RC-21 per reverse charge](../media/tax-feature-support-03.png)
        
        <span data-ttu-id="70b15-136">Crea il codice imposta **BE-RC+21**.</span><span class="sxs-lookup"><span data-stu-id="70b15-136">Create the tax code **BE-RC+21**.</span></span>
        1. <span data-ttu-id="70b15-137">Seleziona **Aggiungi**, immetti **BE-RC-21** nel campo **Codice imposta**.</span><span class="sxs-lookup"><span data-stu-id="70b15-137">Select **Add**, enter **BE-RC-21** in the **Tax code** field.</span></span>
        2. <span data-ttu-id="70b15-138">Seleziona **Per importo netto** nel campo **Componente fiscale**.</span><span class="sxs-lookup"><span data-stu-id="70b15-138">Select **By Net Amount** in the **Tax component** field.</span></span>
        3. <span data-ttu-id="70b15-139">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="70b15-139">Select **Save**.</span></span>
        4. <span data-ttu-id="70b15-140">Nella tabella **Tasso** seleziona **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="70b15-140">Select **Add** in the **Rate** table.</span></span>
        5. <span data-ttu-id="70b15-141">Immetti **21** nel campo **Aliquota imposta**.</span><span class="sxs-lookup"><span data-stu-id="70b15-141">Enter **21** in the **Tax Rate** field.</span></span>
        6. <span data-ttu-id="70b15-142">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="70b15-142">Select **Save**.</span></span>

        ![Codice imposta BE-RC+21 per reverse charge](../media/tax-feature-support-04.png)

3. <span data-ttu-id="70b15-144">Definisci l'applicabilità dei codici imposta.</span><span class="sxs-lookup"><span data-stu-id="70b15-144">Define the applicability of the tax codes.</span></span>

    1. <span data-ttu-id="70b15-145">Seleziona **Gestisci colonne** e quindi seleziona le colonne da utilizzare per creare la tabella di applicabilità.</span><span class="sxs-lookup"><span data-stu-id="70b15-145">Select **Manage columns**, and then select columns that should be used to build the applicability table.</span></span>

        > [!NOTE]
        > <span data-ttu-id="70b15-146">Assicurati di aggiungere le colonne **Processo aziendale** e **Indicazioni fiscali** alla tabella.</span><span class="sxs-lookup"><span data-stu-id="70b15-146">Be sure to add the **Business process** and **Tax directions** columns to the table.</span></span> <span data-ttu-id="70b15-147">Entrambe le colonne sono essenziali per la funzionalità dell'imposta negli ordini di trasferimento.</span><span class="sxs-lookup"><span data-stu-id="70b15-147">Both columns are essential to the functionality for tax in transfer orders.</span></span>

    2. <span data-ttu-id="70b15-148">Aggiungi le regole di applicabilità.</span><span class="sxs-lookup"><span data-stu-id="70b15-148">Add applicability rules.</span></span> <span data-ttu-id="70b15-149">Non lasciare i campi **Codici imposta**, **Gruppo di imposte**, e **Gruppo di imposte articolo** vuoti.</span><span class="sxs-lookup"><span data-stu-id="70b15-149">Don't leave the **Tax codes**, **Tax group**, and **Item tax group** fields blank.</span></span>
        
        <span data-ttu-id="70b15-150">Aggiungi una nuova regola per la spedizione dell'ordine di trasferimento.</span><span class="sxs-lookup"><span data-stu-id="70b15-150">Add a new rule for transfer order shipment.</span></span>
        1. <span data-ttu-id="70b15-151">Nella tabella **Regole di applicabilità** seleziona **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="70b15-151">Select **Add** in the **Applicability rules** table.</span></span>
        2. <span data-ttu-id="70b15-152">Nel campo **Processo aziendale** seleziona **Inventario** per rendere la regola applicabile a un ordine di trasferimento.</span><span class="sxs-lookup"><span data-stu-id="70b15-152">In the **Business process** field, select **Inventory** to make the rule applicable for a transfer order.</span></span>
        3. <span data-ttu-id="70b15-153">Nel campo **Spedisci da Paese/Regione** inserisci **NLD**.</span><span class="sxs-lookup"><span data-stu-id="70b15-153">In the **Ship From Country/Region** field, enter **NLD**.</span></span>
        4. <span data-ttu-id="70b15-154">Nel campo **Spedisci a Paese/Regione** inserisci **BEL**.</span><span class="sxs-lookup"><span data-stu-id="70b15-154">In the **Ship To Country/Region** field, enter **BEL**.</span></span>
        5. <span data-ttu-id="70b15-155">Nel campo **Direzione fiscale** seleziona **Output** per rendere la regola applicabile alla spedizione dell'ordine di trasferimento.</span><span class="sxs-lookup"><span data-stu-id="70b15-155">In the **Tax direction** field, select **Output** to make the rule applicable to transfer order shipment.</span></span>
        6. <span data-ttu-id="70b15-156">Nel campo **Codici imposta** seleziona **NL-Exempt**.</span><span class="sxs-lookup"><span data-stu-id="70b15-156">In the **Tax codes** field, select **NL-Exempt**.</span></span>
        7. <span data-ttu-id="70b15-157">Nel campo **Gruppo di imposte** e **Gruppo di imposte articolo**, immetti la fascia IVA correlata e la fascia IVA articolo definite nel sistema Finance.</span><span class="sxs-lookup"><span data-stu-id="70b15-157">In the **Tax Group** field and the **Item Tax Group**, enter the related sales tax group and item sales tax group which are defined in your Finance system.</span></span>
        
        <span data-ttu-id="70b15-158">Aggiungi un'altra regola per la ricezione dell'ordine di trasferimento.</span><span class="sxs-lookup"><span data-stu-id="70b15-158">Add another rule for transfer order receipt.</span></span>
        1. <span data-ttu-id="70b15-159">Nella tabella **Regole di applicabilità** seleziona **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="70b15-159">Select **Add** in the **Applicability rules** table.</span></span>
        2. <span data-ttu-id="70b15-160">Nel campo **Processo aziendale** seleziona **Inventario** per rendere la regola applicabile a un ordine di trasferimento.</span><span class="sxs-lookup"><span data-stu-id="70b15-160">In the **Business process** field, select **Inventory** to make the rule applicable for a transfer order.</span></span>
        3. <span data-ttu-id="70b15-161">Nel campo **Spedisci da Paese/Regione** inserisci **NLD**.</span><span class="sxs-lookup"><span data-stu-id="70b15-161">In the **Ship From Country/Region** field, enter **NLD**.</span></span>
        4. <span data-ttu-id="70b15-162">Nel campo **Spedisci a Paese/Regione** inserisci **BEL**.</span><span class="sxs-lookup"><span data-stu-id="70b15-162">In the **Ship To Country/Region** field, enter **BEL**.</span></span>
        5. <span data-ttu-id="70b15-163">Nel campo **Direzione fiscale** seleziona **Input** per rendere la regola applicabile alla ricezione dell'ordine di trasferimento.</span><span class="sxs-lookup"><span data-stu-id="70b15-163">In the **Tax direction** field, select **Input** to make the rule applicable to transfer order receipt.</span></span>
        6. <span data-ttu-id="70b15-164">Nel campo **Codici imposta** seleziona **BE-RC+21** e **BE-RC-21**.</span><span class="sxs-lookup"><span data-stu-id="70b15-164">In the **Tax codes** field, select **BE-RC+21** and **BE-RC-21**.</span></span>
        7. <span data-ttu-id="70b15-165">Nel campo **Gruppo di imposte** e **Gruppo di imposte articolo**, immetti la fascia IVA correlata e la fascia IVA articolo definite nel sistema Finance.</span><span class="sxs-lookup"><span data-stu-id="70b15-165">In the **Tax Group** field and the **Item Tax Group**, enter the related sales tax group and item sales tax group which are defined in your Finance system.</span></span>

        ![Regole di applicabilità](../media/image5.png)

4. <span data-ttu-id="70b15-167">Completa e pubblica la nuova versione della funzione fiscale.</span><span class="sxs-lookup"><span data-stu-id="70b15-167">Complete and publish the new tax feature version.</span></span>

    <span data-ttu-id="70b15-168">[![Modifica dello stato della nuova versione](../media/image6.png)](../media/image6.png)</span><span class="sxs-lookup"><span data-stu-id="70b15-168">[![Changing the status of the new version](../media/image6.png)](../media/image6.png)</span></span>

## <a name="set-up-finance-for-transfer-order-transactions"></a><span data-ttu-id="70b15-169">Impostare Finance per le transazioni di ordini di trasferimento</span><span class="sxs-lookup"><span data-stu-id="70b15-169">Set up Finance for transfer order transactions</span></span>

<span data-ttu-id="70b15-170">Per impostare le imposte per gli ordini di trasferimento, effettua i passaggi descritti di seguito.</span><span class="sxs-lookup"><span data-stu-id="70b15-170">Follow these steps to enable and set up taxes for transfer orders.</span></span>

1. <span data-ttu-id="70b15-171">In Finance, via a **Aree di lavoro** \> **Gestione funzionalità**.</span><span class="sxs-lookup"><span data-stu-id="70b15-171">In Finance, go to **Workspaces** \> **Feature management**.</span></span>
2. <span data-ttu-id="70b15-172">Nell'elenco, trova e seleziona la funzionalità **Imposta in ordine di trasferimento**, quindi seleziona **Abilita ora** per attivarla.</span><span class="sxs-lookup"><span data-stu-id="70b15-172">In the list, find and select the **Tax in transfer order** feature, and then select **Enable now** to turn it on.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="70b15-173">La funzionalità **Imposta in ordine di trasferimento** è completamente dipendente dal servizio fiscale.</span><span class="sxs-lookup"><span data-stu-id="70b15-173">The **Tax in transfer order** feature is fully dependent on the tax service.</span></span> <span data-ttu-id="70b15-174">Pertanto, può essere attivata solo dopo aver installato il servizio fiscale.</span><span class="sxs-lookup"><span data-stu-id="70b15-174">Therefore, it can be turned on only after you've installed the tax service.</span></span>

    ![Funzionalità imposta in ordine di trasferimento](../media/image7.png)

3. <span data-ttu-id="70b15-176">Abilita il servizio fiscale e seleziona il processo aziendale **Inventario**.</span><span class="sxs-lookup"><span data-stu-id="70b15-176">Enable the tax service, and select the **Inventory** business process.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="70b15-177">È necessario completare questo passaggio per ogni persona giuridica in Finance in cui si desidera rendere disponibili il servizio fiscale e la funzionalità per le imposte negli ordini di trasferimento.</span><span class="sxs-lookup"><span data-stu-id="70b15-177">You must complete this step for each legal entity in Finance where you want the tax service and the functionality for tax in transfer orders to be available.</span></span>

    1. <span data-ttu-id="70b15-178">Vai a **Imposte** \> **Impostazioni** \> **Configurazione fiscale** \> **Configurazione del servizio fiscale**.</span><span class="sxs-lookup"><span data-stu-id="70b15-178">Go to **Tax** \> **Setup** \> **Tax configuration** \> **Tax service setup**.</span></span>
    2. <span data-ttu-id="70b15-179">Nel campo **Processo aziendale** seleziona **Inventario**.</span><span class="sxs-lookup"><span data-stu-id="70b15-179">In the **Business process** field, select **Inventory**.</span></span>

    ![Impostazione del campo Processo aziendale](../media/image8.png)

4. <span data-ttu-id="70b15-181">Verificare che il meccanismo di reverse charge sia impostato.</span><span class="sxs-lookup"><span data-stu-id="70b15-181">Verify that the reverse charge mechanism is set up.</span></span> <span data-ttu-id="70b15-182">Vai a **Contabilità generale** \> **Impostazioni** \> **Parametri** e poi nella scheda **Reverse charge** verifica che l'opzione **Abilita reverse charge** sia impostata su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="70b15-182">Go to **General ledger** \> **Setup** \> **Parameters**, and then, on the **Reverse charge** tab, verify that the **Enable reverse charge** option is set to **Yes**.</span></span>

    ![Abilitare l'opzione di inversione contabile](../media/image9.png)

5. <span data-ttu-id="70b15-184">Verifica che i codici imposta, i gruppi di imposte, i gruppi di imposte articoli e i numeri di registrazione IVA correlati siano stati impostati in Finance in base alle indicazioni del servizio fiscale.</span><span class="sxs-lookup"><span data-stu-id="70b15-184">Verify that the related tax codes, tax groups, item tax groups, and VAT registration numbers have been set up in Finance according to the tax service guidance.</span></span>
6. <span data-ttu-id="70b15-185">Crea un conto di transito provvisorio.</span><span class="sxs-lookup"><span data-stu-id="70b15-185">Set up an interim transit account.</span></span> <span data-ttu-id="70b15-186">Questo passaggio è necessario solo quando l'imposta applicata a un ordine di trasferimento non è applicabile a un meccanismo di esenzione fiscale o di reverse charge.</span><span class="sxs-lookup"><span data-stu-id="70b15-186">This step is required only when the tax that is applied to a transfer order isn't applicable to a tax exempted or reverse charge mechanism.</span></span>

    1. <span data-ttu-id="70b15-187">Vai a **Imposta** \> **Impostazioni** \> **IVA** \> **Gruppi registrazione contabile**.</span><span class="sxs-lookup"><span data-stu-id="70b15-187">Go to **Tax** \> **Setup** \> **Sales tax** \> **Ledger posting groups**.</span></span>
    2. <span data-ttu-id="70b15-188">Nel campo **Transito provvisorio** seleziona un conto CoGe.</span><span class="sxs-lookup"><span data-stu-id="70b15-188">In the **Interim transit** field, select a ledger account.</span></span>

    ![Selezione di un conto di transito provvisorio](../media/image10.png)

## <a name="set-up-basic-inventory-for-transfer-order-transactions"></a><span data-ttu-id="70b15-190">Impostare l'inventario di base per le transazioni di ordini di trasferimento</span><span class="sxs-lookup"><span data-stu-id="70b15-190">Set up basic inventory for transfer order transactions</span></span>

<span data-ttu-id="70b15-191">Segui questi passaggi per impostare l'inventario di base per abilitare le transazioni degli ordini di trasferimento.</span><span class="sxs-lookup"><span data-stu-id="70b15-191">Follow these steps to set up basic inventory to enable transfer order transactions.</span></span>

1. <span data-ttu-id="70b15-192">Crea siti di partenza e destinazione della spedizione per i tuoi magazzini in diversi paesi o regioni e aggiungi l'indirizzo principale per ogni sito.</span><span class="sxs-lookup"><span data-stu-id="70b15-192">Create ship-from and ship-to sites for your warehouses in different countries or regions, and add the primary address for each site.</span></span>

    1. <span data-ttu-id="70b15-193">Vai a **Gestione magazzino** \> **Impostazione** \> **Magazzino** \> **Siti**.</span><span class="sxs-lookup"><span data-stu-id="70b15-193">Go to **Warehouse management** \> **Setup** \> **Warehouse** \> **Sites**.</span></span>
    2. <span data-ttu-id="70b15-194">Seleziona **Nuovo** per creare il sito che in seguito assegnerai a un magazzino.</span><span class="sxs-lookup"><span data-stu-id="70b15-194">Select **New** to create the site that you will assign to a warehouse later.</span></span>
    3. <span data-ttu-id="70b15-195">Ripeti il passaggio 2 per tutti gli altri siti che è necessario creare.</span><span class="sxs-lookup"><span data-stu-id="70b15-195">Repeat step 2 for all the other sites that you must create.</span></span>

    > [!NOTE]
    > <span data-ttu-id="70b15-196">Uno dei siti che crei deve essere denominato **Transito**.</span><span class="sxs-lookup"><span data-stu-id="70b15-196">One of the sites that you create should be named **Transit**.</span></span> <span data-ttu-id="70b15-197">Nelle fasi successive di questa procedura, assegnerai questo sito al magazzino di transito, in modo che i giustificativi di inventario relativi alle imposte possano essere registrati nelle transazioni di "spedizione" e "ricezione" per gli ordini di trasferimento.</span><span class="sxs-lookup"><span data-stu-id="70b15-197">In later steps of this procedure, you will assign this site to the transit warehouse, so that tax-related inventory vouchers can be posted in "ship" and "receive" transactions for transfer orders.</span></span> <span data-ttu-id="70b15-198">L'indirizzo del sito di transito è irrilevante per il calcolo delle imposte.</span><span class="sxs-lookup"><span data-stu-id="70b15-198">The address of the transit site is irrelevant to tax calculation.</span></span> <span data-ttu-id="70b15-199">Pertanto, non è possibile non specificare tale valore.</span><span class="sxs-lookup"><span data-stu-id="70b15-199">Therefore, you can leave it blank.</span></span>

    ![Impostazione dei siti](../media/image11.png)

2. <span data-ttu-id="70b15-201">Crea magazzini di partenza, transito e consegna.</span><span class="sxs-lookup"><span data-stu-id="70b15-201">Create ship-from, transit, and ship-to warehouses.</span></span> <span data-ttu-id="70b15-202">Qualsiasi informazione sull'indirizzo conservata in un magazzino sovrascriverà l'indirizzo del sito durante il calcolo delle imposte.</span><span class="sxs-lookup"><span data-stu-id="70b15-202">Any address information that is maintained in a warehouse will override the site address during tax calculation.</span></span>

    1. <span data-ttu-id="70b15-203">Vai a **Gestione magazzino** \> **Impostazioni** \> **Magazzino** \> **Magazzini**.</span><span class="sxs-lookup"><span data-stu-id="70b15-203">Go to **Warehouse management** \> **Setup** \> **Warehouse** \> **Warehouses**.</span></span>
    2. <span data-ttu-id="70b15-204">Seleziona **Nuovo** per creare il magazzino e assegnarlo al sito corrispondente.</span><span class="sxs-lookup"><span data-stu-id="70b15-204">Select **New** to create a warehouse, and assign it to the corresponding site.</span></span>
    3. <span data-ttu-id="70b15-205">Ripeti il passaggio 2 per creare un magazzino per ogni sito come richiesto.</span><span class="sxs-lookup"><span data-stu-id="70b15-205">Repeat step 2 to create a warehouse for each site as required.</span></span>

    ![Impostazione dei magazzini](../media/image12.png)

    > [!NOTE]
    > <span data-ttu-id="70b15-207">Per un magazzino di partenza, è necessario selezionare un magazzino di transito nel campo **Magazzino di transito** per le transazioni dell'ordine di trasferimento.</span><span class="sxs-lookup"><span data-stu-id="70b15-207">For a ship-from warehouse, a transit warehouse must be selected in the **Transit warehouse** field for transfer order transactions.</span></span>
    >
    > ![Selezione di un magazzino di transito](../media/image13.png)

3. <span data-ttu-id="70b15-209">Verifica che la configurazione di registrazione inventario sia configurata per le transazioni degli ordini di trasferimento.</span><span class="sxs-lookup"><span data-stu-id="70b15-209">Verify that the inventory posting configuration is set up for transfer order transactions.</span></span>

    1. <span data-ttu-id="70b15-210">Andare a **Gestione scorte**\>**Impostazioni**\>**Registrazione**\>**Registrazione**.</span><span class="sxs-lookup"><span data-stu-id="70b15-210">Go to **Inventory management** \> **Setup** \> **Posting** \> **Posting**.</span></span>
    2. <span data-ttu-id="70b15-211">Nella scheda **Inventario** verifica che sia impostato un conto contabile per le registrazioni **Uscita inventario** e **Entrata inventario**.</span><span class="sxs-lookup"><span data-stu-id="70b15-211">On the **Inventory** tab, verify that a ledger account is set up for both **Inventory issue** and **Inventory receipt** posting.</span></span>

        ![Impostazione dell'uscita di scorte e della registrazione delle entrate scorte](../media/image14.png)

    3. <span data-ttu-id="70b15-213">Verifica che sia impostato un conto contabile per la registrazione **Contabilità fornitori tra unità**.</span><span class="sxs-lookup"><span data-stu-id="70b15-213">Verify that a ledger account is set up for **Inter-unit payable** posting.</span></span>

        ![Impostazione della registrazione contabilità fornitori tra unità](../media/image15.png)

    4. <span data-ttu-id="70b15-215">Verifica che sia impostato un conto contabile per la registrazione **Contabilità clienti tra unità**.</span><span class="sxs-lookup"><span data-stu-id="70b15-215">Verify that a ledger account is set up for **Inter-unit receivable** posting.</span></span>

        ![Impostazione della registrazione contabilità clienti tra unità](../media/image16.png)
