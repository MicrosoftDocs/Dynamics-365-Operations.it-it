---
title: Esempio di elaborazione di lettere di sollecito
description: Questo argomento illustra un esempio che mostra il processo di creazione, stampa e registrazione di lettere di sollecito.
author: JodiChristiansen
manager: AnnBe
ms.date: 02/03/2021
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustPosting, CustCollectionLetterNote
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2021-02-03
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: df4252513f9e3a02632561b4e465c98edc888ea7
ms.sourcegitcommit: 4ecc1bf82fbb04882d7ef5e1994ef3c07ef953dc
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/08/2021
ms.locfileid: "5558313"
---
# <a name="process-collection-letters-example"></a><span data-ttu-id="886be-103">Esempio di elaborazione di lettere di sollecito</span><span class="sxs-lookup"><span data-stu-id="886be-103">Process collection letters example</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="886be-104">Questo argomento illustra un esempio che mostra il processo di creazione, stampa e registrazione di lettere di sollecito.</span><span class="sxs-lookup"><span data-stu-id="886be-104">This topic goes through an example that shows the process of creating, printing, and posting collection letters.</span></span> <span data-ttu-id="886be-105">L'esempio è basato sull'opzione **Ignora pagamenti e note di credito durante il calcolo del codice di lettera di sollecito** in Credito e riscossioni.</span><span class="sxs-lookup"><span data-stu-id="886be-105">The example is based on the **Ignore payments and credit memos when calculating collection letter code** option in Credit and collections.</span></span> <span data-ttu-id="886be-106">Utilizza i dati della società dimostrativa USMF e di un nuovo cliente, US-045.</span><span class="sxs-lookup"><span data-stu-id="886be-106">It uses data in the USMF demo company and a new customer, US-045.</span></span>

<span data-ttu-id="886be-107">Per iniziare, selezionare **Contabilità clienti \> Clienti \> Tutti i clienti**, selezionare **Nuovo** e quindi immettere le informazioni necessarie per creare il cliente US-045.</span><span class="sxs-lookup"><span data-stu-id="886be-107">To begin, go to **Accounts receivable \> Customers \> All customers**, select **New**, and then enter the required information to create customer US-045.</span></span>

<span data-ttu-id="886be-108">Al termine, procedere come segue.</span><span class="sxs-lookup"><span data-stu-id="886be-108">When you've finished, follow these steps.</span></span>

1. <span data-ttu-id="886be-109">Selezionare **Crediti e riscossioni \> Lettera di sollecito \> Imposta la sequenza lettere di sollecito** e impostare la sequenza delle lettere di sollecito come mostrato nella seguente tabella assegnata al profilo di registrazione cliente.</span><span class="sxs-lookup"><span data-stu-id="886be-109">Go to **Credit and collections \> Collection letter \> Setup collection letter sequence**, and set up the collection letter sequence as shown in the following table that is assigned to the customer posting profile.</span></span>

|     <span data-ttu-id="886be-110">Codice lettera di sollecito</span><span class="sxs-lookup"><span data-stu-id="886be-110">Collection   letter code</span></span>      |     <span data-ttu-id="886be-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="886be-111">Description</span></span>                           |     <span data-ttu-id="886be-112">Valuta</span><span class="sxs-lookup"><span data-stu-id="886be-112">Currency</span></span>      |     <span data-ttu-id="886be-113">Conto   principale</span><span class="sxs-lookup"><span data-stu-id="886be-113">Main   account</span></span>        |     <span data-ttu-id="886be-114">Addebito   in valuta</span><span class="sxs-lookup"><span data-stu-id="886be-114">Fee   in currency</span></span>     |     <span data-ttu-id="886be-115">Minimo   oltre</span><span class="sxs-lookup"><span data-stu-id="886be-115">Minimum   over</span></span>        |     <span data-ttu-id="886be-116">Blocco   giorni</span><span class="sxs-lookup"><span data-stu-id="886be-116">Days   Block</span></span>      |
|---------------------------------  |---------------------------------------    |-----------------  |-----------------------    |-------------------------- |-----------------------    |---------------------  |
|     <span data-ttu-id="886be-117">Lettera di   sollecito 1</span><span class="sxs-lookup"><span data-stu-id="886be-117">Collection   letter 1</span></span>         |     <span data-ttu-id="886be-118">Seconda   notifica a pagamento</span><span class="sxs-lookup"><span data-stu-id="886be-118">Second   notification with fee</span></span>        |     <span data-ttu-id="886be-119">USD</span><span class="sxs-lookup"><span data-stu-id="886be-119">USD</span></span>           |                           |     <span data-ttu-id="886be-120">0,00</span><span class="sxs-lookup"><span data-stu-id="886be-120">0.00</span></span>                  |     <span data-ttu-id="886be-121">0,00</span><span class="sxs-lookup"><span data-stu-id="886be-121">0.00</span></span>                  |     <span data-ttu-id="886be-122">2</span><span class="sxs-lookup"><span data-stu-id="886be-122">2</span></span>                 |
|     <span data-ttu-id="886be-123">Lettera di   sollecito 2</span><span class="sxs-lookup"><span data-stu-id="886be-123">Collection   letter 2</span></span>         |     <span data-ttu-id="886be-124">Seconda   notifica a pagamento</span><span class="sxs-lookup"><span data-stu-id="886be-124">Second   notification with fee</span></span>        |     <span data-ttu-id="886be-125">USC</span><span class="sxs-lookup"><span data-stu-id="886be-125">USC</span></span>           |     <span data-ttu-id="886be-126">403150</span><span class="sxs-lookup"><span data-stu-id="886be-126">403150</span></span>                |     <span data-ttu-id="886be-127">20.00</span><span class="sxs-lookup"><span data-stu-id="886be-127">20.00</span></span>                 |     <span data-ttu-id="886be-128">10.00</span><span class="sxs-lookup"><span data-stu-id="886be-128">10.00</span></span>                 |     <span data-ttu-id="886be-129">3</span><span class="sxs-lookup"><span data-stu-id="886be-129">3</span></span>                 |
|     <span data-ttu-id="886be-130">Incasso</span><span class="sxs-lookup"><span data-stu-id="886be-130">Collection</span></span>                    |     <span data-ttu-id="886be-131">Notifica   finale a pagamento</span><span class="sxs-lookup"><span data-stu-id="886be-131">Final   notification with fee</span></span>         |     <span data-ttu-id="886be-132">USD</span><span class="sxs-lookup"><span data-stu-id="886be-132">USD</span></span>           |     <span data-ttu-id="886be-133">403150</span><span class="sxs-lookup"><span data-stu-id="886be-133">403150</span></span>                |     <span data-ttu-id="886be-134">50.00</span><span class="sxs-lookup"><span data-stu-id="886be-134">50.00</span></span>                 |     <span data-ttu-id="886be-135">100.00</span><span class="sxs-lookup"><span data-stu-id="886be-135">100.00</span></span>                |     <span data-ttu-id="886be-136">15</span><span class="sxs-lookup"><span data-stu-id="886be-136">15</span></span>                |

<span data-ttu-id="886be-137">La figura seguente mostra come le informazioni presenti nella tabella apparirebbero nella pagina **Lettere di sollecito**.</span><span class="sxs-lookup"><span data-stu-id="886be-137">The following illustration shows the information that's in the table as it would appear on the **Collection letters** page.</span></span> 

<span data-ttu-id="886be-138">[![Impostare una sequenza di lettere di sollecito](./media/Ignore-payments-creditmemos-1.PNG)](./media/Ignore-payments-creditmemos-1.PNG)</span><span class="sxs-lookup"><span data-stu-id="886be-138">[![Setting up a collection letter sequence](./media/Ignore-payments-creditmemos-1.PNG)](./media/Ignore-payments-creditmemos-1.PNG)</span></span>

 <span data-ttu-id="886be-139">È ora necessario impostare i due parametri richiesti per questo esempio.</span><span class="sxs-lookup"><span data-stu-id="886be-139">You must now set the two parameters that are required for this example.</span></span>

2. <span data-ttu-id="886be-140">Selezionare **Crediti e riscossioni \> Impostazioni \> Parametri contabilità clienti** e procedere come segue:</span><span class="sxs-lookup"><span data-stu-id="886be-140">Go to **Credit and collections \> Setup \> Accounts receivable parameters**, and follow these steps:</span></span>

    1. <span data-ttu-id="886be-141">Nella scheda **Riscossioni**, impostare l'opzione **Ignora pagamenti e note di credito durante il calcolo del codice di lettera di sollecito** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="886be-141">On the **Collections** tab, set the **Ignore payments and credit memos when calculating collection letter code** option to **Yes**.</span></span>
    2. <span data-ttu-id="886be-142">Assicurarsi che il campo **Crea lettera di sollecito per** sia impostato su **Cliente**.</span><span class="sxs-lookup"><span data-stu-id="886be-142">Make sure that the **Create collection letter per** field is set to **Customer**.</span></span>

    <span data-ttu-id="886be-143">[![Impostare parametri di contabilità clienti per crediti e riscossioni](./media/Ignore-payments-creditmemos-2.PNG)](./media/Ignore-payments-creditmemos-2.PNG)</span><span class="sxs-lookup"><span data-stu-id="886be-143">[![Setting Accounts receivable parameters for Credit collections](./media/Ignore-payments-creditmemos-2.PNG)](./media/Ignore-payments-creditmemos-2.PNG)</span></span>

3. <span data-ttu-id="886be-144">Selezionare **Contabilità clienti \> Fatture \> Tutte le fatture a testo libero**, selezionare **Nuovo** e quindi procedere come segue:</span><span class="sxs-lookup"><span data-stu-id="886be-144">Go to **Accounts receivable \> Invoices \> All free text invoices**, select **New**, and then follow these steps:</span></span>

    1. <span data-ttu-id="886be-145">Nel campo **Conto cliente** selezionare **US-045**.</span><span class="sxs-lookup"><span data-stu-id="886be-145">In the **Customer account** field select **US-045**.</span></span>
    2. <span data-ttu-id="886be-146">Nel campo **Data fattura** immettere **15/1/2021**.</span><span class="sxs-lookup"><span data-stu-id="886be-146">In the **Invoice date** field, enter **1/15/2021**.</span></span>
    3. <span data-ttu-id="886be-147">Nel campo **Data di scadenza** immettere **16/1/2021**.</span><span class="sxs-lookup"><span data-stu-id="886be-147">In the **Due date** field, enter **1/16/2021**.</span></span>
    4. <span data-ttu-id="886be-148">Nella Scheda dettaglio **Righe fattura** nel campo **Account principale**, immettere **401100**.</span><span class="sxs-lookup"><span data-stu-id="886be-148">On the **Invoice lines** FastTab, in the **Main account** field, enter **401100**.</span></span>
    5. <span data-ttu-id="886be-149">Nel campo **Prezzo unitario** immettere **500.00**.</span><span class="sxs-lookup"><span data-stu-id="886be-149">In the **Unit price** field, enter **500.00**.</span></span>
    6. <span data-ttu-id="886be-150">Selezionare **Registra**.</span><span class="sxs-lookup"><span data-stu-id="886be-150">Select **Post**.</span></span>

    <span data-ttu-id="886be-151">È ora necessario immettere due note di credito per il cliente.</span><span class="sxs-lookup"><span data-stu-id="886be-151">You must now enter two credit notes for the customer.</span></span>

4. <span data-ttu-id="886be-152">Selezionare **Nuovo** e procedere come segue:</span><span class="sxs-lookup"><span data-stu-id="886be-152">Select **New**, and then follow these steps:</span></span>

    1. <span data-ttu-id="886be-153">Nel campo **Conto cliente** selezionare **US-045**.</span><span class="sxs-lookup"><span data-stu-id="886be-153">In the **Customer account** field, select **US-045**.</span></span>
    2. <span data-ttu-id="886be-154">Nel campo **Data fattura** immettere **15/1/2021**.</span><span class="sxs-lookup"><span data-stu-id="886be-154">In the **Invoice date** field, enter **1/15/2021**.</span></span>
    3. <span data-ttu-id="886be-155">Nel campo **Data di scadenza** immettere **16/1/2021**.</span><span class="sxs-lookup"><span data-stu-id="886be-155">In the **Due date** field, enter **1/16/2021**.</span></span>
    4. <span data-ttu-id="886be-156">Nella Scheda dettaglio **Righe fattura** nel campo **Account principale**, immettere **401100**.</span><span class="sxs-lookup"><span data-stu-id="886be-156">On the **Invoice lines** FastTab, in the **Main account** field, enter **401100**.</span></span>
    5. <span data-ttu-id="886be-157">Nel campo **Prezzo unitario** immettere **-100,00**.</span><span class="sxs-lookup"><span data-stu-id="886be-157">In the **Unit price** field, enter **-100.00**.</span></span>
    6. <span data-ttu-id="886be-158">Selezionare **Registra**.</span><span class="sxs-lookup"><span data-stu-id="886be-158">Select **Post**.</span></span>

5. <span data-ttu-id="886be-159">Ripetere il passaggio 4, ma immettere **-200,00** nel campo **Prezzo unitario**.</span><span class="sxs-lookup"><span data-stu-id="886be-159">Repeat step 4, but enter **-200.00** in the **Unit price** field.</span></span>
6. <span data-ttu-id="886be-160">Selezionare **Contabilità clienti \> Clienti \> Tutti i clienti** e selezionare il cliente **US-045**.</span><span class="sxs-lookup"><span data-stu-id="886be-160">Go to **Accounts receivable \> Customers \> All customers**, and select customer **US-045**.</span></span> <span data-ttu-id="886be-161">Quindi, nel riquadro Azioni, selezionare **Transazioni \> Transazioni** per esaminare le transazioni dei clienti registrate in precedenza.</span><span class="sxs-lookup"><span data-stu-id="886be-161">Then, on the Action Pane, select **Transactions \> Transactions** to review the customer transactions that you posted earlier.</span></span>

    <span data-ttu-id="886be-162">[![Revisione delle transazioni cliente registrate](./media/Ignore-payments-creditmemos-3.PNG)](./media/Ignore-payments-creditmemos-3.PNG)</span><span class="sxs-lookup"><span data-stu-id="886be-162">[![Reviewing the posted customer transactions](./media/Ignore-payments-creditmemos-3.PNG)](./media/Ignore-payments-creditmemos-3.PNG)</span></span>

    <span data-ttu-id="886be-163">È ora necessario creare lettere di sollecito per il cliente US-045.</span><span class="sxs-lookup"><span data-stu-id="886be-163">You must now create collection letters for customer US-045.</span></span>

7. <span data-ttu-id="886be-164">Selezionare **Crediti e riscossioni \> Lettera di sollecito \> Crea lettere di sollecito** e procedere come segue.</span><span class="sxs-lookup"><span data-stu-id="886be-164">Go to **Credit and collections \> Collection letter \> Create collection letters**, and follow these steps:</span></span>

    1. <span data-ttu-id="886be-165">Impostare le opzioni **Fattura** e **Nota di credito** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="886be-165">Set the **Invoice** and **Credit note** options to **Yes**.</span></span>

        <span data-ttu-id="886be-166">Per impostazione predefinita, il campo **Lettera di sollecito** deve essere impostato su **Sollecito per cliente**.</span><span class="sxs-lookup"><span data-stu-id="886be-166">By default, the **Collection letter** field should be set to **Collection per customer**.</span></span>

    2. <span data-ttu-id="886be-167">Nel campo **Data della lettera di sollecito** immettere **19/1/2021**.</span><span class="sxs-lookup"><span data-stu-id="886be-167">In the **Collection letter date** field, enter **1/19/2021**.</span></span>
    3. <span data-ttu-id="886be-168">Nella Scheda dettaglio **Record da includere**, selezionare **Filtro** e nel campo **Account cliente** aggiungere il cliente **US-045**.</span><span class="sxs-lookup"><span data-stu-id="886be-168">On the **Records to include** FastTab, select **Filter**, and then, in the **Customer account** field, add customer **US-045**.</span></span>
    4. <span data-ttu-id="886be-169">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="886be-169">Select **OK**.</span></span>
    5. <span data-ttu-id="886be-170">Selezionare **OK** per creare lettere di sollecito.</span><span class="sxs-lookup"><span data-stu-id="886be-170">Select **OK** to create collection letters.</span></span>

8. <span data-ttu-id="886be-171">Selezionare **Crediti e riscossioni \> Lettera di sollecito \> Esamina ed elabora lettere di sollecito** e procedere come segue.</span><span class="sxs-lookup"><span data-stu-id="886be-171">Go to **Credit and collections \> Collection letter \> Review and process collection letters**, and follow these steps:</span></span>

    1. <span data-ttu-id="886be-172">Da notare che il codice di lettera di sollecito nell'intestazione e nelle righe della transazione è **Lettera di sollecito 1**, poiché questa lettera di sollecito è la prima lettera di sollecito nella sequenza</span><span class="sxs-lookup"><span data-stu-id="886be-172">Notice that the collection letter code on both the header and the transaction lines is **Collection letter 1**, because this collection letter is the first collection letter in the sequence.</span></span> <span data-ttu-id="886be-173">(per visualizzare le righe della transazione, potrebbe essere necessario selezionare la Scheda dettaglio **Transazioni**).</span><span class="sxs-lookup"><span data-stu-id="886be-173">(To view the transaction lines, you might have to select the **Transactions** FastTab.)</span></span>

   <span data-ttu-id="886be-174">[![Verificare che lo stesso codice di lettera di sollecito sia visualizzato nell'intestazione e nelle righe](./media/Ignore-payments-creditmemos-4.PNG)](./media/Ignore-payments-creditmemos-4.PNG)</span><span class="sxs-lookup"><span data-stu-id="886be-174">[![Verifying that the same collection letter code appears on the header and the lines](./media/Ignore-payments-creditmemos-4.PNG)](./media/Ignore-payments-creditmemos-4.PNG)</span></span>

    2. <span data-ttu-id="886be-175">Nel riquadro Azioni selezionare **Registra**.</span><span class="sxs-lookup"><span data-stu-id="886be-175">On the Action Pane, select **Post**.</span></span>
    3. <span data-ttu-id="886be-176">Nel campo **Data di registrazione** immettere **19/1/2021**.</span><span class="sxs-lookup"><span data-stu-id="886be-176">In the **Posting date** field, enter **1/19/2021**.</span></span>

    <span data-ttu-id="886be-177">È ora necessario creare di nuovo lettere di sollecito per il cliente US-045.</span><span class="sxs-lookup"><span data-stu-id="886be-177">You must now create collection letters again for customer US-045.</span></span>

9. <span data-ttu-id="886be-178">Selezionare **Crediti e riscossioni \> Lettera di sollecito \> Crea lettere di sollecito** e procedere come segue.</span><span class="sxs-lookup"><span data-stu-id="886be-178">Go to **Credit and collections \> Collection letter \> Create collection letters**, and follow these steps:</span></span>

    1. <span data-ttu-id="886be-179">Impostare le opzioni **Fattura** e **Nota di credito** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="886be-179">Set the **Invoice** and **Credit note** options to **Yes**.</span></span>

        <span data-ttu-id="886be-180">Per impostazione predefinita, il campo **Lettera di sollecito** deve essere impostato su **Sollecito per cliente**.</span><span class="sxs-lookup"><span data-stu-id="886be-180">By default, the **Collection letter** field should be set to **Collection per customer**.</span></span>

    2. <span data-ttu-id="886be-181">Nel campo **Data della lettera di sollecito** immettere **23/1/2021**.</span><span class="sxs-lookup"><span data-stu-id="886be-181">In the **Collection letter date** field, enter **1/23/2021**.</span></span>
    3. <span data-ttu-id="886be-182">Nella Scheda dettaglio **Record da includere**, selezionare **Filtro** e nel campo **Account cliente** aggiungere il cliente **US-045**.</span><span class="sxs-lookup"><span data-stu-id="886be-182">On the **Records to include** FastTab, select **Filter**, and then, in the **Customer account** field, add customer **US-045**.</span></span>
    4. <span data-ttu-id="886be-183">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="886be-183">Select **OK**.</span></span>
    5. <span data-ttu-id="886be-184">Selezionare **OK** per creare lettere di sollecito.</span><span class="sxs-lookup"><span data-stu-id="886be-184">Select **OK** to create collection letters.</span></span>

10. <span data-ttu-id="886be-185">Selezionare **Crediti e riscossioni \> Lettera di sollecito \> Esamina ed elabora lettere di sollecito** e procedere come segue.</span><span class="sxs-lookup"><span data-stu-id="886be-185">Go to **Credit and collections \> Collection letter \> Review and process collection letters**, and follow these steps:</span></span>

    1. <span data-ttu-id="886be-186">Da notare che il codice di lettera di sollecito nell'intestazione è **Lettera di sollecito 1**.</span><span class="sxs-lookup"><span data-stu-id="886be-186">Notice that the collection letter code on the header is **Collection letter 1**.</span></span> <span data-ttu-id="886be-187">Tuttavia, il codice nelle righe della transazione è **Lettera di sollecito 2**.</span><span class="sxs-lookup"><span data-stu-id="886be-187">However, the code on the transaction lines is **Collection letter 2**.</span></span>

   <span data-ttu-id="886be-188">[![Verificare che codici di lettera di sollecito differenti siano visualizzati nell'intestazione e nelle righe](./media/Ignore-payments-creditmemos-5.PNG)](./media/Ignore-payments-creditmemos-5.PNG)</span><span class="sxs-lookup"><span data-stu-id="886be-188">[![Verifies that different collection letter codes appear on the header and the lines](./media/Ignore-payments-creditmemos-5.PNG)](./media/Ignore-payments-creditmemos-5.PNG)</span></span>

  <span data-ttu-id="886be-189">I codici differiscono poiché l'opzione **Ignora pagamenti e note di credito durante il calcolo del codice di lettera di sollecito** è impostata su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="886be-189">The codes differ because the **Ignore payments and credit memos when calculating collection letter code** option is to **Yes**.</span></span>

  2. <span data-ttu-id="886be-190">Non registrare questa lettera di sollecito.</span><span class="sxs-lookup"><span data-stu-id="886be-190">Don't post this collection letter.</span></span>

11. <span data-ttu-id="886be-191">Selezionare **Crediti e le riscossioni \> Impostazioni \> Parametri contabilità clienti** e nella scheda **Solleciti**, impostare l'opzione **Ignora pagamenti e note di credito durante il calcolo del codice di lettera di sollecito** su **No**.</span><span class="sxs-lookup"><span data-stu-id="886be-191">Go to **Credit and collections \> Setup \> Accounts receivable parameters**, and then, on the **Collections** tab, set the **Ignore payments and credit memos when calculating collection letter code** option to **No**.</span></span>

    <span data-ttu-id="886be-192">[![Impostare l'opzione Ignora pagamenti e note di credito durante il calcolo del codice di lettera di sollecito su No](./media/Ignore-payments-creditmemos-6.PNG)](./media/Ignore-payments-creditmemos-6.PNG)</span><span class="sxs-lookup"><span data-stu-id="886be-192">[![Setting the Ignore payments and credit memos when calculating collection letter code option to No](./media/Ignore-payments-creditmemos-6.PNG)](./media/Ignore-payments-creditmemos-6.PNG)</span></span>

    <span data-ttu-id="886be-193">È ora necessario creare di nuovo lettere di sollecito per il cliente US-045.</span><span class="sxs-lookup"><span data-stu-id="886be-193">You must now create collection letters again for customer US-045.</span></span>

12. <span data-ttu-id="886be-194">Selezionare **Crediti e riscossioni \> Lettera di sollecito \> Crea lettere di sollecito** e procedere come segue.</span><span class="sxs-lookup"><span data-stu-id="886be-194">Go to **Credit and collections \> Collection letter \> Create collection letters**, and follow these steps:</span></span>

    1. <span data-ttu-id="886be-195">Impostare le opzioni **Fattura** e **Nota di credito** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="886be-195">Set the **Invoice** and **Credit note** options to **Yes**.</span></span>

        <span data-ttu-id="886be-196">Per impostazione predefinita, il campo **Lettera di sollecito** deve essere impostato su **Sollecito per cliente**.</span><span class="sxs-lookup"><span data-stu-id="886be-196">By default, the **Collection letter** field should be set to **Collection per customer**.</span></span>

    2. <span data-ttu-id="886be-197">Nel campo **Data della lettera di sollecito** immettere **23/1/2021**.</span><span class="sxs-lookup"><span data-stu-id="886be-197">In the **Collection letter date** field, enter **1/23/2021**.</span></span>
    3. <span data-ttu-id="886be-198">Nella Scheda dettaglio **Record da includere**, selezionare **Filtro** e nel campo **Account cliente** aggiungere il cliente **US-045**.</span><span class="sxs-lookup"><span data-stu-id="886be-198">On the **Records to include** FastTab, select **Filter**, and then, in the **Customer account** field, add customer **US-045**.</span></span>
    4. <span data-ttu-id="886be-199">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="886be-199">Select **OK**.</span></span>
    5. <span data-ttu-id="886be-200">Selezionare **OK** per creare lettere di sollecito.</span><span class="sxs-lookup"><span data-stu-id="886be-200">Select **OK** to create collection letters.</span></span>

13. <span data-ttu-id="886be-201">Selezionare **Crediti e riscossioni \> Lettera di sollecito \> Esamina ed elabora lettere di sollecito**. Da notare che il codice di lettera di sollecito nell'intestazione e nelle righe della transazione è **Lettera di sollecito 2**.</span><span class="sxs-lookup"><span data-stu-id="886be-201">Go to **Credit and collections \> Collection letter \> Review and process collection letters**, and notice that the collection letter code on both the header and the transaction lines is **Collection letter 2**.</span></span>

    <span data-ttu-id="886be-202">[![Visualizzare di nuovo lo stesso codice di lettera di sollecito nell'intestazione e nelle righe](./media/Ignore-payments-creditmemos-7.PNG)](./media/Ignore-payments-creditmemos-7.PNG)</span><span class="sxs-lookup"><span data-stu-id="886be-202">[![Showing again that the same collection letter code appears on the header and the lines](./media/Ignore-payments-creditmemos-7.PNG)](./media/Ignore-payments-creditmemos-7.PNG)</span></span>

    <span data-ttu-id="886be-203">Lo stesso codice appare in entrambe le posizioni poiché l'opzione **Ignora pagamenti e note di credito durante il calcolo del codice di lettera di sollecito** è ora impostata su **No**.</span><span class="sxs-lookup"><span data-stu-id="886be-203">The same code appears in both places because the **Ignore payments and credit memos when calculating collection letter code** option is now set to **No**.</span></span>
