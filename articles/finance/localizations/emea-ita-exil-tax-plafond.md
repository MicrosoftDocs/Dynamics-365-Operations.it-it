---
title: Plafond fiscale
description: Questo argomento spiega come impostare e lavorare con il plafond fiscale, un processo di esenzione fiscale.
author: ilkond
manager: AnnBe
ms.date: 04/20/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Italy
ms.author: ilyako
ms.search.validFrom: 2020-06-01
ms.dyn365.ops.version: 10.0.9
ms.openlocfilehash: accbb60094f433ba1cfb89230e75a83c35e09b4f
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4978242"
---
# <a name="tax-plafond"></a><span data-ttu-id="2d2c8-103">Plafond fiscale</span><span class="sxs-lookup"><span data-stu-id="2d2c8-103">Tax plafond</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="2d2c8-104">Il plafond fiscale è un processo di esenzione fiscale disponibile per le aziende, chiamato *esportatore abituale*, di acquistare e importare beni e servizi senza pagare l'IVA, entro un valore limitato delle loro vendite all'estero nel periodo precedente.</span><span class="sxs-lookup"><span data-stu-id="2d2c8-104">Tax plafond is a tax exemption process available for companies, called *usual exporter*, of purchasing and importing goods and services without paying sales tax, within a limited value of their sales to foreign countries in the previous period.</span></span> <span data-ttu-id="2d2c8-105">Una società è una *esportatore abituale* se, durante l'anno precedente, il 10 percento del suo valore dei ricavi proveniva dalla vendita in un paese straniero.</span><span class="sxs-lookup"><span data-stu-id="2d2c8-105">A company is a *usual exporter* if, during the previous year, 10 percent of its revenue value came from selling to a foreign country.</span></span> <span data-ttu-id="2d2c8-106">L'importo iniziale del plafond e le sue date di validità sono stabiliti all'inizio del periodo.</span><span class="sxs-lookup"><span data-stu-id="2d2c8-106">The initial plafond amount and its validity dates are established at the beginning of the period.</span></span> <span data-ttu-id="2d2c8-107">La società può acquistare senza pagare l'IVA purché il valore degli acquisti sia inferiore all'importo iniziale del plafond.</span><span class="sxs-lookup"><span data-stu-id="2d2c8-107">The company can buy without paying sales tax as long as the value of the purchases is less than the initial plafond amount.</span></span>

<span data-ttu-id="2d2c8-108">Questo argomento descrive come completare queste attività:</span><span class="sxs-lookup"><span data-stu-id="2d2c8-108">This topic describes how to complete these tasks:</span></span>

- <span data-ttu-id="2d2c8-109">Configurare il sistema affinché utilizzi la funzionalità **Plafond fiscale**.</span><span class="sxs-lookup"><span data-stu-id="2d2c8-109">Set up the system to use the **Tax plafond** feature.</span></span>
- <span data-ttu-id="2d2c8-110">Lavora con lettere di intenti e plafond fiscali.</span><span class="sxs-lookup"><span data-stu-id="2d2c8-110">Work with tax plafond and intent letters.</span></span>
- <span data-ttu-id="2d2c8-111">Segnala pagamenti fiscali che includono informazioni sul plafond fiscale.</span><span class="sxs-lookup"><span data-stu-id="2d2c8-111">Report tax payments that include tax plafond information.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="2d2c8-112">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="2d2c8-112">Prerequisites</span></span>

- <span data-ttu-id="2d2c8-113">L'indirizzo principale della persona giuridica deve essere in Italia.</span><span class="sxs-lookup"><span data-stu-id="2d2c8-113">The primary address of the legal entity must be in Italy.</span></span>
- <span data-ttu-id="2d2c8-114">Nell'area di lavoro **Gestione funzionalità**, abilita la funzionalità **Plafond fiscale**.</span><span class="sxs-lookup"><span data-stu-id="2d2c8-114">In the **Feature management** workspace, turn on the **Tax plafond** feature.</span></span> <span data-ttu-id="2d2c8-115">Per ulteriori informazioni, vedere [Panoramica della gestione funzionalità](../../fin-and-ops/get-started/feature-management/feature-management-overview.md).</span><span class="sxs-lookup"><span data-stu-id="2d2c8-115">For more information, see [Feature management overview](../../fin-and-ops/get-started/feature-management/feature-management-overview.md).</span></span>

## <a name="set-up-parameters"></a><span data-ttu-id="2d2c8-116">Impostare i parametri</span><span class="sxs-lookup"><span data-stu-id="2d2c8-116">Set up parameters</span></span>

### <a name="set-up-accounts-payable-parameters"></a><span data-ttu-id="2d2c8-117">Impostazione dei parametri di Contabilità fornitori</span><span class="sxs-lookup"><span data-stu-id="2d2c8-117">Set up Accounts payable parameters</span></span>

1. <span data-ttu-id="2d2c8-118">Vai a **Contabilità fornitori** \> **Impostazioni** \> **Parametri contabilità fornitori**.</span><span class="sxs-lookup"><span data-stu-id="2d2c8-118">Go to **Accounts payable** \> **Setup** \> **Accounts payable parameters**.</span></span>
2. <span data-ttu-id="2d2c8-119">Nella scheda **Sequenze numeriche**, specifica le sequenze numeriche per i seguenti riferimenti:</span><span class="sxs-lookup"><span data-stu-id="2d2c8-119">On the **Number sequences** tab, specify number sequences for the following references:</span></span>

    - <span data-ttu-id="2d2c8-120">Numero plafond</span><span class="sxs-lookup"><span data-stu-id="2d2c8-120">Plafond number</span></span>
    - <span data-ttu-id="2d2c8-121">Numero lettera d'intento</span><span class="sxs-lookup"><span data-stu-id="2d2c8-121">Intent letter number</span></span>

3. <span data-ttu-id="2d2c8-122">Nella scheda **Lettere di intenti - Modello telematico** nel campo **Mappatura del formato del modello di lettera di intenti**, specificare il riferimento alla configurazione **Modello telematico lettera di intenti**.</span><span class="sxs-lookup"><span data-stu-id="2d2c8-122">On the **Intent letters - Telematic model** tab, in the **Intent letter model format mapping** field, specify the reference to the **Intent letter telematic model** configuration.</span></span>

    ![Campo di mappatura del formato del modello di lettera di intenti](media/emea-ita-exil-plafond-model.jpg)

    > [!NOTE]
    > <span data-ttu-id="2d2c8-124">La configurazione deve essere importata utilizzando il report elettronico (ER).</span><span class="sxs-lookup"><span data-stu-id="2d2c8-124">The configuration must be imported by using Electronic reporting (ER).</span></span> <span data-ttu-id="2d2c8-125">Per ulteriori istruzioni su come scaricare le configurazioni dei report elettronici, vedi [Scarica le configurazioni per la creazione di report elettronici da Lifecycle Services](../../fin-ops-core/dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md).</span><span class="sxs-lookup"><span data-stu-id="2d2c8-125">For more information about how to download ER configurations, see [Download Electronic reporting configurations from Lifecycle Services](../../fin-ops-core/dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md).</span></span>

4. <span data-ttu-id="2d2c8-126">Nella scheda **Contabilità generale e IVA**, nella Scheda dettaglio **IVA**, sezione **Plafond**, imposta i campi **Gruppo plafond fiscale** e **Data plafond predefinita**.</span><span class="sxs-lookup"><span data-stu-id="2d2c8-126">On the **Ledger and sale tax** tab, on the **Sales tax** FastTab, in the **Plafond** section, set the **Plafond tax group** and **Default plafond date** fields.</span></span>

    ![Campi nella sezione Plafond](media/emea-ita-exil-plafond-group.jpg)

### <a name="set-up-general-ledger-parameters"></a><span data-ttu-id="2d2c8-128">Impostazione dei parametri di Contabilità generale</span><span class="sxs-lookup"><span data-stu-id="2d2c8-128">Set up General ledger parameters</span></span>

1. <span data-ttu-id="2d2c8-129">Selezionare **Contabilità generale** \> **Impostazione contabilità generale** \> **Parametri di contabilità generale**.</span><span class="sxs-lookup"><span data-stu-id="2d2c8-129">Go to **General ledger** \> **Ledger setup** \> **General ledger parameters**.</span></span>
2. <span data-ttu-id="2d2c8-130">Nella scheda **Sequenze numeriche**, specificare la sequenza numerica per il riferimento **ID modello telematico lettera di intenti**.</span><span class="sxs-lookup"><span data-stu-id="2d2c8-130">On the **Number sequences** tab, specify the number sequence for the **Intent letter telematic model ID** reference.</span></span>

### <a name="set-up-sales-tax-codes"></a><span data-ttu-id="2d2c8-131">Imposta i codici IVA</span><span class="sxs-lookup"><span data-stu-id="2d2c8-131">Set up sales tax codes</span></span>

1. <span data-ttu-id="2d2c8-132">Vai a **Imposta** \> **Imposte indirette** \> **IVA** \> **Codici IVA**.</span><span class="sxs-lookup"><span data-stu-id="2d2c8-132">Go to **Tax** \> **Indirect taxes** \> **Sales tax** \> **Sales tax codes**.</span></span>
2. <span data-ttu-id="2d2c8-133">Nela sezione Scheda dettaglio **Generale**, nella sezione **Fatturazione**, imposta l'opzione **Invia lettere di intento** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="2d2c8-133">On the **General** FastTab, in the **Invoicing** section, set the **Affect intent letters** option to **Yes**.</span></span>

    ![Influisce sull'opzione lettere di intenti](media/emea-ita-exil-intent-tax-setup.jpg)

## <a name="create-tax-plafond"></a><span data-ttu-id="2d2c8-135">Crea plafond fiscale</span><span class="sxs-lookup"><span data-stu-id="2d2c8-135">Create tax plafond</span></span>

<span data-ttu-id="2d2c8-136">Per registrare un nuovo plafond fiscale, attieniti alla seguente procedura.</span><span class="sxs-lookup"><span data-stu-id="2d2c8-136">To register a new tax plafond, follow these steps.</span></span>

1. <span data-ttu-id="2d2c8-137">Vai a **Imposta** \> **Imposte indirette** \> **IVA** \> **Plafond fiscale**.</span><span class="sxs-lookup"><span data-stu-id="2d2c8-137">Go to **Tax** \> **Indirect taxes** \> **Sales tax** \> **Tax plafond**.</span></span>
2. <span data-ttu-id="2d2c8-138">Nel riquadro azioni, seleziona **Funzioni** \> **Crea nuovo** e inserisci le informazioni sul plafond fiscale.</span><span class="sxs-lookup"><span data-stu-id="2d2c8-138">On the Action Pane, select **Functions** \> **Create new**, and enter information about the tax plafond.</span></span>

   <span data-ttu-id="2d2c8-139">Nella seguente tabella vengono descritti i vari campi.</span><span class="sxs-lookup"><span data-stu-id="2d2c8-139">The following table describes the various fields.</span></span>

    | <span data-ttu-id="2d2c8-140">Nome campo</span><span class="sxs-lookup"><span data-stu-id="2d2c8-140">Field name</span></span>                             | <span data-ttu-id="2d2c8-141">descrizione</span><span class="sxs-lookup"><span data-stu-id="2d2c8-141">Description</span></span> |
    |----------------------------------------|-------------|
    | <span data-ttu-id="2d2c8-142">Numero plafond</span><span class="sxs-lookup"><span data-stu-id="2d2c8-142">Plafond number</span></span>                         | <span data-ttu-id="2d2c8-143">Il numero del plafond fiscale.</span><span class="sxs-lookup"><span data-stu-id="2d2c8-143">The number of the tax plafond.</span></span> <span data-ttu-id="2d2c8-144">Questo valore viene inserito automaticamente in base alla sequenza numerica specificata per il riferimento **Numero plafond** nella pagina **Parametri contabilità fornitori**.</span><span class="sxs-lookup"><span data-stu-id="2d2c8-144">This value is automatically filled in according to the number sequence that is specified for the **Plafond number** reference on the **Accounts payable parameters** page.</span></span> |
    | <span data-ttu-id="2d2c8-145">descrizione</span><span class="sxs-lookup"><span data-stu-id="2d2c8-145">Description</span></span>                            | <span data-ttu-id="2d2c8-146">Immetti una descrizione del plafond fiscale.</span><span class="sxs-lookup"><span data-stu-id="2d2c8-146">Enter a description of the tax plafond.</span></span> |
    | <span data-ttu-id="2d2c8-147">Dal</span><span class="sxs-lookup"><span data-stu-id="2d2c8-147">From date</span></span>                              | <span data-ttu-id="2d2c8-148">La data di inizio del periodo durante il quale è effettivo il plafond fiscale.</span><span class="sxs-lookup"><span data-stu-id="2d2c8-148">The start date of the period that the tax plafond is effective during.</span></span> |
    | <span data-ttu-id="2d2c8-149">Al</span><span class="sxs-lookup"><span data-stu-id="2d2c8-149">To date</span></span>                                | <span data-ttu-id="2d2c8-150">La data di fine del periodo durante il quale è effettivo il plafond fiscale.</span><span class="sxs-lookup"><span data-stu-id="2d2c8-150">The end date of the period that the tax plafond is effective during.</span></span> |
    | <span data-ttu-id="2d2c8-151">Data di chiusura</span><span class="sxs-lookup"><span data-stu-id="2d2c8-151">Closed date</span></span>                            | <span data-ttu-id="2d2c8-152">La data calcolata in cui il plafond fiscale è chiuso.</span><span class="sxs-lookup"><span data-stu-id="2d2c8-152">The calculated date when the tax plafond is closed.</span></span> |
    | <span data-ttu-id="2d2c8-153">Importo del plafond iniziale</span><span class="sxs-lookup"><span data-stu-id="2d2c8-153">Initial plafond amount</span></span>                 | <span data-ttu-id="2d2c8-154">Immetti l'importo del plafond fiscale.</span><span class="sxs-lookup"><span data-stu-id="2d2c8-154">Enter the amount of the tax plafond.</span></span> |
    | <span data-ttu-id="2d2c8-155">Importo corrente iniziale</span><span class="sxs-lookup"><span data-stu-id="2d2c8-155">Initial current amount</span></span>                 | <span data-ttu-id="2d2c8-156">L'importo calcolato disponibile nel plafond fiscale.</span><span class="sxs-lookup"><span data-stu-id="2d2c8-156">The calculated amount that is available on the tax plafond.</span></span> |
    | <span data-ttu-id="2d2c8-157">Tipo di avviso del plafond, importo,%</span><span class="sxs-lookup"><span data-stu-id="2d2c8-157">Plafond warning type, amount, %</span></span>        | <span data-ttu-id="2d2c8-158">Il tipo di controllo che viene eseguito e l'importo o la percentuale correlati in corrispondenza dei quali gli utenti inizieranno a ricevere avvisi sull'importo rimanente del plafond fiscale.</span><span class="sxs-lookup"><span data-stu-id="2d2c8-158">The type of check that is done, and the related amount or percentage at which users will begin to receive warnings about the remaining amount of the tax plafond.</span></span> |
    | <span data-ttu-id="2d2c8-159">Periodo di liquidazione</span><span class="sxs-lookup"><span data-stu-id="2d2c8-159">Settlement period</span></span>                      | <span data-ttu-id="2d2c8-160">Specifica il periodo di liquidazione.</span><span class="sxs-lookup"><span data-stu-id="2d2c8-160">Specify the settlement period.</span></span> |
    | <span data-ttu-id="2d2c8-161">Operazioni che contribuiscono al plafond</span><span class="sxs-lookup"><span data-stu-id="2d2c8-161">Operations contributing to the plafond</span></span> | <span data-ttu-id="2d2c8-162">Attiva o disattiva le opzioni per l'inclusione nel report sulle lettere di intenti.</span><span class="sxs-lookup"><span data-stu-id="2d2c8-162">Turn the options for inclusion in the intent letters report on or off.</span></span> |

<span data-ttu-id="2d2c8-163">Per rivedere le transazioni fiscali registrate per un plafond fiscale esistente, nella pagina **Plafond fiscale**, nel riquadro azioni, seleziona **Transazioni plafond**.</span><span class="sxs-lookup"><span data-stu-id="2d2c8-163">To review posted tax transactions for an existing tax plafond, on the **Tax plafond** page, on the Action Pane, select **Plafond transactions**.</span></span>

## <a name="create-intent-letters"></a><span data-ttu-id="2d2c8-164">Crea una lettera di intenti</span><span class="sxs-lookup"><span data-stu-id="2d2c8-164">Create intent letters</span></span>

<span data-ttu-id="2d2c8-165">Per creare una nuova lettera di intenti per un fornitore, effettua le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="2d2c8-165">To create a new intent letter for a vendor, follow these steps.</span></span>

1. <span data-ttu-id="2d2c8-166">Vai a **Contabilità fornitori** \> **Lettere di intenti** \> **Lettere di intenti**.</span><span class="sxs-lookup"><span data-stu-id="2d2c8-166">Go to **Accounts payable** \> **Intent letters** \> **Intent letters**.</span></span>
2. <span data-ttu-id="2d2c8-167">Nel riquadro azioni, seleziona **Nuovo** e inserisci le seguenti informazioni relative alla lettera di intenti.</span><span class="sxs-lookup"><span data-stu-id="2d2c8-167">On the Action Pane, select **New**, and enter the following information about the intent letter.</span></span>

    | <span data-ttu-id="2d2c8-168">Nome campo</span><span class="sxs-lookup"><span data-stu-id="2d2c8-168">Field name</span></span>   | <span data-ttu-id="2d2c8-169">descrizione</span><span class="sxs-lookup"><span data-stu-id="2d2c8-169">Description</span></span>                                                                      |
    |--------------|----------------------------------------------------------------------------------|
    | <span data-ttu-id="2d2c8-170">Data di registrazione</span><span class="sxs-lookup"><span data-stu-id="2d2c8-170">Posting date</span></span> | <span data-ttu-id="2d2c8-171">Specifica la data di registrazione della lettera di intenti.</span><span class="sxs-lookup"><span data-stu-id="2d2c8-171">Specify the posting date for the intent letter.</span></span>                                  |
    | <span data-ttu-id="2d2c8-172">Tipo lettera</span><span class="sxs-lookup"><span data-stu-id="2d2c8-172">Letter type</span></span>  | <span data-ttu-id="2d2c8-173">Seleziona il tipo di lettera di intenti: **Quantità** oppure **Operazione specifica**.</span><span class="sxs-lookup"><span data-stu-id="2d2c8-173">Select the type of intent letter: **Amount** or **Specific operation**.</span></span>          |
    | <span data-ttu-id="2d2c8-174">Dal</span><span class="sxs-lookup"><span data-stu-id="2d2c8-174">From date</span></span>    | <span data-ttu-id="2d2c8-175">Specifica la data di inizio del periodo durante il quale è effettiva la lettera di intenti.</span><span class="sxs-lookup"><span data-stu-id="2d2c8-175">Specify the start date of the period that the intent letter is effective during.</span></span> |
    | <span data-ttu-id="2d2c8-176">Al</span><span class="sxs-lookup"><span data-stu-id="2d2c8-176">To date</span></span>      | <span data-ttu-id="2d2c8-177">Specifica la data di fine del periodo durante il quale è effettiva la lettera di intenti.</span><span class="sxs-lookup"><span data-stu-id="2d2c8-177">Specify the end date of the period that the intent letter is effective during.</span></span>   |
    | <span data-ttu-id="2d2c8-178">Quantità</span><span class="sxs-lookup"><span data-stu-id="2d2c8-178">Amount</span></span>       | <span data-ttu-id="2d2c8-179">Specifica l'importo della lettera di intenti.</span><span class="sxs-lookup"><span data-stu-id="2d2c8-179">Specify the amount for the intent letter.</span></span>                                        |

3. <span data-ttu-id="2d2c8-180">Nella Scheda dettaglio **Record da includere**, seleziona **Filtro** per selezionare i fornitori per i quali devono essere create le lettere di intenti.</span><span class="sxs-lookup"><span data-stu-id="2d2c8-180">On **Records to include** FastTab, select **Filter** to select the vendors that intent letters must be created for.</span></span>
4. <span data-ttu-id="2d2c8-181">Seleziona **OK** per finalizzare la selezione.</span><span class="sxs-lookup"><span data-stu-id="2d2c8-181">Select **OK** to finalize the selection.</span></span>
5. <span data-ttu-id="2d2c8-182">Nella pagina successiva, seleziona **Aggiorna gli ordini di acquisto esistenti**, applica nuove lettere di intenti agli ordini di acquisto esistenti che non sono stati ancora fatturati per i fornitori selezionati.</span><span class="sxs-lookup"><span data-stu-id="2d2c8-182">On the next page, select **Update existing purchase orders** to apply new intent letters to existing purchase orders that haven't yet been invoiced for the selected vendors.</span></span>
6. <span data-ttu-id="2d2c8-183">Seleziona **Conferma nuovamente ordini fornitore** per riconfermare gli ordini fornitore a cui vengono applicate le lettere di intenti, nel caso fossero confermate.</span><span class="sxs-lookup"><span data-stu-id="2d2c8-183">Select **Re-confirm purchase orders** to reconfirm the purchase orders that intent letters are applied to, in case they were confirmed.</span></span>
7. <span data-ttu-id="2d2c8-184">Seleziona **Escludi ordini fornitore consegnati o parzialmente consegnati** per escludere gli ordini fornitore che sono stati consegnati in tutto o in parte dall'elenco degli ordini fornitore che verranno aggiornati con lettere di intenti.</span><span class="sxs-lookup"><span data-stu-id="2d2c8-184">Select **Exclude delivered or partly delivered purchase orders** to exclude purchase orders that were fully or partially delivered from the list of purchase orders that will be updated with intent letters.</span></span>
8. <span data-ttu-id="2d2c8-185">Seleziona **OK** per creare lettere di intenti basate su parametri specificati.</span><span class="sxs-lookup"><span data-stu-id="2d2c8-185">Select **OK** to create intent letters that are based on the specified parameters.</span></span>

    > [!NOTE]
    > <span data-ttu-id="2d2c8-186">Quando vengono create lettere di intenti, il sistema le numera automaticamente in base alla sequenza numerica specificata per il riferimento **Numero lettera di intenti** nella pagina **Parametri contabilità fornitori**.</span><span class="sxs-lookup"><span data-stu-id="2d2c8-186">When intent letters are created, the system automatically numbers them according to the number sequence that is specified for the **Intent letter number** reference on the **Accounts payable parameters** page.</span></span>

9. <span data-ttu-id="2d2c8-187">Per le lettere di intenti che vengono create, nella scheda **Generale**, puoi inserire informazioni sul modello telematico generato.</span><span class="sxs-lookup"><span data-stu-id="2d2c8-187">For the intent letters that are created, on the **General** tab, you can enter information about the generated telematic model.</span></span>

    <span data-ttu-id="2d2c8-188">Nella seguente tabella vengono descritti i vari campi.</span><span class="sxs-lookup"><span data-stu-id="2d2c8-188">The following table describes the various fields.</span></span>

    | <span data-ttu-id="2d2c8-189">Nome campo</span><span class="sxs-lookup"><span data-stu-id="2d2c8-189">Field name</span></span>    | <span data-ttu-id="2d2c8-190">descrizione</span><span class="sxs-lookup"><span data-stu-id="2d2c8-190">Description</span></span> |
    |---------------|-------------|
    | <span data-ttu-id="2d2c8-191">ID modello</span><span class="sxs-lookup"><span data-stu-id="2d2c8-191">Model ID</span></span>      | <span data-ttu-id="2d2c8-192">L'identificatore del modello telematico in cui è stata inclusa la lettera di intenti.</span><span class="sxs-lookup"><span data-stu-id="2d2c8-192">The identifier of the telematic model that the intent letter was included in.</span></span> <span data-ttu-id="2d2c8-193">Questo valore viene inserito automaticamente in base alla sequenza numerica specificata per il riferimento **ID modello telematico lettera di intenti** nella pagina **Parametri di contabilità generale**.</span><span class="sxs-lookup"><span data-stu-id="2d2c8-193">This value is automatically filled in according to the number sequence that is specified for the **Intent letter telematic model ID** reference on the **General ledger parameters** page.</span></span> |
    | <span data-ttu-id="2d2c8-194">Tipo di acquisto</span><span class="sxs-lookup"><span data-stu-id="2d2c8-194">Purchase type</span></span> | <span data-ttu-id="2d2c8-195">Seleziona il tipo di acquisto: **Acquisti** o **Importo**.</span><span class="sxs-lookup"><span data-stu-id="2d2c8-195">Select the type of purchase: **Purchase** or **Import**.</span></span> |

> [!NOTE]
> <span data-ttu-id="2d2c8-196">Le lettere di intenti del tipo **Periodo** non sono supportate e non è possibile crearle.</span><span class="sxs-lookup"><span data-stu-id="2d2c8-196">Intent letters of the **Period** type aren't supported, and you can't create them.</span></span> <span data-ttu-id="2d2c8-197">Il tipo **Periodo** viene selezionato per i dati storici, per quegli utenti che hanno precedentemente utilizzato questo tipo e il parametro **Assegnazione automatica lettera di intento** nella scheda **Contabilità generale e IVA** della pagina **Parametri contabilità fornitori**.</span><span class="sxs-lookup"><span data-stu-id="2d2c8-197">The **Period** type is kept for historical data, for those users who previously used this type and the **Automatic intent letter assignment** parameter on the **Ledger and sales tax** tab of the **Accounts payable parameters** page.</span></span>

## <a name="work-with-intent-letters"></a><span data-ttu-id="2d2c8-198">Utilizza le lettere di intenti</span><span class="sxs-lookup"><span data-stu-id="2d2c8-198">Work with intent letters</span></span>

<span data-ttu-id="2d2c8-199">Le lettere di intenti create per i fornitori possono essere applicate agli ordini fornitore o alle fatture fornitore prima che le fatture vengano registrate.</span><span class="sxs-lookup"><span data-stu-id="2d2c8-199">Intent letters that are created for vendors can be applied to purchase orders or vendor invoice journals before invoices are posted.</span></span>

<span data-ttu-id="2d2c8-200">Per applicare una lettera di intenti a un ordine fornitore o a un giornale di registrazione delle fatture fornitore, selezionala nel campo **Numero lettera di intenti** del relativo ordine fornitore o giornale di fatture dei fornitori.</span><span class="sxs-lookup"><span data-stu-id="2d2c8-200">To apply an intent letter to a purchase order or vendor invoice journal, select it in the **Intent letter number** field of the related purchase order or vendor invoice journal.</span></span> <span data-ttu-id="2d2c8-201">Il gruppo IVA sulle vendite specificato nel campo **Gruppo plafond fiscale** nella pagina **Parametri contabilità fornitori** verrà compilata automaticamente per l'ordine fornitore o per il giornale di fatture dei fornitori.</span><span class="sxs-lookup"><span data-stu-id="2d2c8-201">The sales tax group that is specified in the **Plafond tax group** field on the **Accounts payable parameters** page will be automatically filled in for the purchase order or vendor invoice journal.</span></span>

![Campo del numero di lettera di intenti per un ordine fornitore](media/emea-ita-exil-plafond-PO.jpg)

<span data-ttu-id="2d2c8-203">Puoi inoltre rivedere le lettere di intenti per un fornitore specifico dai dati master del fornitore.</span><span class="sxs-lookup"><span data-stu-id="2d2c8-203">You can also review the intent letters for a specific vendor from vendor master data.</span></span>

1. <span data-ttu-id="2d2c8-204">Andare a **Contabilità fornitori** \> **Fornitori** \> **Tutti i fornitori**.</span><span class="sxs-lookup"><span data-stu-id="2d2c8-204">Go to **Accounts payable** \> **Vendors** \> **All vendors**.</span></span>
2. <span data-ttu-id="2d2c8-205">Nel riquadro azioni, nella scheda **Fornitore** del gruppo **Informazioni correlate**, seleziona **Lettere di intenti** per visualizzare le lettere di intenti correlate al fornitore selezionato.</span><span class="sxs-lookup"><span data-stu-id="2d2c8-205">On the Action Pane, on the **Vendor** tab, in the **Related information** group, select **Intent letters** to view the intent letters that are related to the selected vendor.</span></span>

## <a name="generate-the-telematic-model-for-intent-letters"></a><span data-ttu-id="2d2c8-206">Genera il modello telematico per le lettere di intenti</span><span class="sxs-lookup"><span data-stu-id="2d2c8-206">Generate the telematic model for intent letters</span></span>

<span data-ttu-id="2d2c8-207">Per generare il modello telematico per una lettera di intenti, attieniti alla seguente procedura.</span><span class="sxs-lookup"><span data-stu-id="2d2c8-207">To generate the telematic model for an intent letter, follow these steps.</span></span>

1. <span data-ttu-id="2d2c8-208">Vai a **Imposta** \> **Dichiarazioni** \> **IVA** \> **Lettere di intenti - Modello telematico**.</span><span class="sxs-lookup"><span data-stu-id="2d2c8-208">Go to **Tax** \> **Declarations** \> **Sales tax** \> **Intent letters – Telematic model**.</span></span>
2. <span data-ttu-id="2d2c8-209">Nel riquadro azioni, seleziona **Nuovo** per creare un nuovo record per il reporting di modelli telematici.</span><span class="sxs-lookup"><span data-stu-id="2d2c8-209">On the Action Pane, select **New** to create a new record for telematic model reporting.</span></span> <span data-ttu-id="2d2c8-210">L'ID del modello viene inserito automaticamente in base alla sequenza numerica specificata per il riferimento **ID modello telematico lettera di intenti** nella pagina **Parametri di contabilità generale**.</span><span class="sxs-lookup"><span data-stu-id="2d2c8-210">The model ID is automatically filled in according to the number sequence that is specified for the **Intent letter telematic model ID** reference on the **General ledger parameters** page.</span></span>
3. <span data-ttu-id="2d2c8-211">Nel campo **Descrizione interna**, specificare la descrizione interna per il nuovo modello telematico.</span><span class="sxs-lookup"><span data-stu-id="2d2c8-211">In the **Internal description** field, specify the internal description for the new telematic model.</span></span>
4. <span data-ttu-id="2d2c8-212">Nella scheda **Generale**, immetti tutte le informazioni correlate sul nuovo modello telematico: firmatario, autore, parametri integrativi e nome del file.</span><span class="sxs-lookup"><span data-stu-id="2d2c8-212">On the **General** tab, enter any related information about the new telematic model: the signatory, the writer, integrative parameters, and the file name.</span></span>
5. <span data-ttu-id="2d2c8-213">Nel riquadro azioni, seleziona **Trasferimento**, quindi seleziona le lettere di intenti da includere nel modello corrente.</span><span class="sxs-lookup"><span data-stu-id="2d2c8-213">On the Action Pane, select **Transfer**, and then select the intent letters to include in the current model.</span></span> <span data-ttu-id="2d2c8-214">Le lettere di intenti selezionate verranno visualizzate nella Scheda dettaglio **Lettere di intenti**.</span><span class="sxs-lookup"><span data-stu-id="2d2c8-214">The selected intent letters will be shown on the **Intent letters** FastTab.</span></span>

    > [!NOTE] 
    > <span data-ttu-id="2d2c8-215">Le lettere di intenti già incluse in altri modelli non possono essere selezionate.</span><span class="sxs-lookup"><span data-stu-id="2d2c8-215">Intent letters that are already included in other models can't be selected.</span></span>

6. <span data-ttu-id="2d2c8-216">Nel riquadro azioni, seleziona **Esporta** per generare il file di output **Modello telematico lettera di intenti**.</span><span class="sxs-lookup"><span data-stu-id="2d2c8-216">On the Action Pane, select **Export** to generate the **Intent letter telematic model** output file.</span></span>
