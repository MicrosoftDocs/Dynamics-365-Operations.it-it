---
title: Gestione delle informazioni del cliente per l'Italia
description: In questo argomento viene descritto come gestire le informazioni relative al cliente nel POS per l'Italia.
author: sepism
manager: annbe
ms.date: 01/14/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailFunctionalityProfile, RetailParameters
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.search.region: Italy
ms.search.industry: Retail
ms.author: sepism
ms.search.validFrom: 2019-10-08
ms.dyn365.ops.version: 10.0.7
ms.openlocfilehash: b6ddd2177c46dcf19bf42eeadf3c7f835fa3e72f
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4408078"
---
# <a name="customer-information-management-for-italy"></a><span data-ttu-id="d5801-103">Gestione delle informazioni cliente per l'Italia</span><span class="sxs-lookup"><span data-stu-id="d5801-103">Customer information management for Italy</span></span>

[!include [banner](../includes/banner.md)]


## <a name="introduction"></a><span data-ttu-id="d5801-104">Introduzione</span><span class="sxs-lookup"><span data-stu-id="d5801-104">Introduction</span></span>

<span data-ttu-id="d5801-105">In questo argomento viene descritto come è possibile gestire le informazioni relative al cliente, ad esempio il codice lotteria del cliente, nel POS di Commerce per l'Italia.</span><span class="sxs-lookup"><span data-stu-id="d5801-105">This topic describes how you can handle customer information, such as the customer's lottery code, in the Commerce point of sale (POS) for Italy.</span></span>

<span data-ttu-id="d5801-106">È possibile specificare informazioni sul cliente, come il codice fiscale o il codice lotteria, quando si crea o si modifica un record di dati master del cliente nel POS.</span><span class="sxs-lookup"><span data-stu-id="d5801-106">You can specify the customer information, such as the fiscal code or lottery code, when you create or edit a customer master record in POS.</span></span> <span data-ttu-id="d5801-107">È inoltre possibile specificare il codice lotteria per una transazione di vendita copiandolo dal cliente della transazione o immettendolo manualmente.</span><span class="sxs-lookup"><span data-stu-id="d5801-107">You can also specify the lottery code for a sales transaction by copying it from the transaction customer or entering it manually.</span></span> <span data-ttu-id="d5801-108">Il codice lotteria può quindi essere stampato sia sulle ricevute fiscali e su quelle normali ed essere utilizzato per la lotteria nazionale.</span><span class="sxs-lookup"><span data-stu-id="d5801-108">The lottery code can then be printed on both regular and fiscal receipts, and it can be used for the national lottery.</span></span> <span data-ttu-id="d5801-109">I codici fiscali personali possono inoltre essere utilizzati per individuare un cliente in POS.</span><span class="sxs-lookup"><span data-stu-id="d5801-109">Personal fiscal codes can also be used to search for a customer in POS.</span></span>

> [!NOTE]
> <span data-ttu-id="d5801-110">Questa funzionalità è disponibile nella versione 10.0.7 e successive.</span><span class="sxs-lookup"><span data-stu-id="d5801-110">This functionality is available in version 10.0.7 and later.</span></span>

## <a name="setup"></a><span data-ttu-id="d5801-111">Attrezzaggio</span><span class="sxs-lookup"><span data-stu-id="d5801-111">Setup</span></span>

<span data-ttu-id="d5801-112">È necessario completare la seguente configurazione per utilizzare questa funzionalità:</span><span class="sxs-lookup"><span data-stu-id="d5801-112">You must complete the following configuration to use this functionality:</span></span>

- <span data-ttu-id="d5801-113">Impostare un tipo di registrazione per il codice lotteria.</span><span class="sxs-lookup"><span data-stu-id="d5801-113">Set up a registration type for the lottery code.</span></span>
- <span data-ttu-id="d5801-114">Aggiungere l'operazione **Aggiungi informazioni cliente** ai layout dello schermo.</span><span class="sxs-lookup"><span data-stu-id="d5801-114">Add the **Add customer information** operation to screen layouts.</span></span>
- <span data-ttu-id="d5801-115">Attivare la richiesta di informazioni del cliente.</span><span class="sxs-lookup"><span data-stu-id="d5801-115">Activate the inquiry for customer information.</span></span>
- <span data-ttu-id="d5801-116">Impostare i formati di ricevuta.</span><span class="sxs-lookup"><span data-stu-id="d5801-116">Set up receipt formats.</span></span>
- <span data-ttu-id="d5801-117">Aggiungere i criteri di ricerca cliente.</span><span class="sxs-lookup"><span data-stu-id="d5801-117">Add a customer search criterion.</span></span>
- <span data-ttu-id="d5801-118">Configurare i componenti del canale.</span><span class="sxs-lookup"><span data-stu-id="d5801-118">Configure channel components.</span></span>

### <a name="set-up-a-registration-type-for-the-lottery-code"></a><span data-ttu-id="d5801-119">Impostare un tipo di registrazione per il codice lotteria</span><span class="sxs-lookup"><span data-stu-id="d5801-119">Set up a registration type for the lottery code</span></span>

<span data-ttu-id="d5801-120">Prima di poter specificare i codici lotteria nel POS, è necessario creare un tipo di registrazione appropriato per il codice lotteria e collegarlo alla categoria di registrazione **Codice lotteria**.</span><span class="sxs-lookup"><span data-stu-id="d5801-120">Before lottery codes can be specified in POS, you must create an appropriate registration type for the lottery code and link it to the **Lottery code** registration category.</span></span> <span data-ttu-id="d5801-121">Per ulteriori informazioni su come utilizzare i tipi di registrazione e gli ID registrazione, vedere [ID registrazione](../../finance/localizations/emea-registration-ids.md).</span><span class="sxs-lookup"><span data-stu-id="d5801-121">For more information about how to work with registration types and registration IDs, see [Registration IDs](../../finance/localizations/emea-registration-ids.md).</span></span>

> [!WARNING]
> <span data-ttu-id="d5801-122">Se un tipo di registrazione non viene creato o non è collegato alla categoria di registrazione **Codice lotteria**, viene generato un errore nel POS quando il codice lotteria viene immesso per un indirizzo cliente.</span><span class="sxs-lookup"><span data-stu-id="d5801-122">If a registration type isn't created or isn't linked to the **Lottery code** registration category, an error will be generated in POS when the lottery code is filled in for a customer address.</span></span>

### <a name="add-the-add-customer-information-operation-to-screen-layouts"></a><span data-ttu-id="d5801-123">Aggiungere l'operazione Aggiungi informazioni cliente ai layout dello schermo</span><span class="sxs-lookup"><span data-stu-id="d5801-123">Add the Add customer information operation to screen layouts</span></span>

<span data-ttu-id="d5801-124">L'operazione **Aggiungi informazioni cliente** può essere utilizzata per aggiungere informazioni sul cliente, come il codice lotteria, a una transazione di vendita.</span><span class="sxs-lookup"><span data-stu-id="d5801-124">The **Add customer information** operation can be used to add customer information, such as the lottery code, to a sales transaction.</span></span> <span data-ttu-id="d5801-125">Queste informazioni possono essere copiate dal cliente specificato per la transazione oppure possono essere inserite manualmente.</span><span class="sxs-lookup"><span data-stu-id="d5801-125">This information can be copied from the customer that is specified for the transaction, or it can be manually entered.</span></span>

<span data-ttu-id="d5801-126">Nella pagina **Griglie dei pulsanti**, selezionare la griglia dei pulsanti in cui dovrebbe apparire l'operazione e aprire la finestra Progettazione griglia dei pulsanti.</span><span class="sxs-lookup"><span data-stu-id="d5801-126">On the **Button grids** page, select the button grid where the operation should appear, and open the Button grid designer.</span></span> <span data-ttu-id="d5801-127">Aggiungere un nuovo pulsante, quindi nel campo **Azione** selezionare **Aggiungi informazioni cliente**.</span><span class="sxs-lookup"><span data-stu-id="d5801-127">Add a new button, and then, in the **Action** field, select **Add customer information**.</span></span> <span data-ttu-id="d5801-128">Per ulteriori informazioni sull'utilizzo dei layout dello schermo e delle griglie dei pulsanti, vedere [Layout delle schermate per il POS](../pos-screen-layouts.md).</span><span class="sxs-lookup"><span data-stu-id="d5801-128">For more information about how to work with screen layouts and button grids, see [Screen layouts for the point of sale (POS)](../pos-screen-layouts.md).</span></span>

### <a name="activate-the-inquiry-for-customer-information"></a><span data-ttu-id="d5801-129">Attivare la richiesta di informazioni del cliente</span><span class="sxs-lookup"><span data-stu-id="d5801-129">Activate the inquiry for customer information</span></span>

<span data-ttu-id="d5801-130">Se le informazioni del cliente non sono specificate per una transazione di vendita, una richiesta per tali informazioni può essere attivata automaticamente dopo la finalizzazione della transazione.</span><span class="sxs-lookup"><span data-stu-id="d5801-130">If the customer information isn't specified for a sales transaction, an inquiry for that information can be triggered automatically after the transaction is finalized.</span></span> <span data-ttu-id="d5801-131">Questo approccio è un'alternativa all'operazione **Aggiungi informazioni cliente**.</span><span class="sxs-lookup"><span data-stu-id="d5801-131">This approach is an alternative to the **Add customer information** operation.</span></span>

<span data-ttu-id="d5801-132">Per attivare la richiesta di informazioni cliente, impostare l'opzione **Abilita richiesta informazioni sul cliente nelle transazioni di vendita** su **Sì** nella sezione **Parametri imposte** della Scheda dettaglio **Funzioni** della pagina **Profili funzionalità POS**.</span><span class="sxs-lookup"><span data-stu-id="d5801-132">To activate the inquiry for customer information, set the **Enable inquiry of customer information in sales transactions** option to **Yes** in the **Tax parameters** section on the **Functions** FastTab of the **POS functionality profiles** page.</span></span>

### <a name="set-up-receipt-formats"></a><span data-ttu-id="d5801-133">Impostare formati di ricevuta</span><span class="sxs-lookup"><span data-stu-id="d5801-133">Set up receipt formats</span></span>

<span data-ttu-id="d5801-134">È possibile configurare i formati di ricevuta in modo che il codice fiscale e il codice lotteria del cliente siano stampati sulle ricevute.</span><span class="sxs-lookup"><span data-stu-id="d5801-134">You can configure receipt formats so that the customer's fiscal code and lottery code are printed on receipts.</span></span>

> [!NOTE]
> <span data-ttu-id="d5801-135">La società predefinita dell'utente che crea l'impostazione della ricevuta deve essere la stessa persona giuridica in cui viene creata l'impostazione del testo della lingua.</span><span class="sxs-lookup"><span data-stu-id="d5801-135">The default company of the user who creates the receipt setup should be the same legal entity where the language text setup is created.</span></span> <span data-ttu-id="d5801-136">In alternativa, i testi nella stessa lingua devono essere creati sia nella società predefinita dell'utente sia nella persona giuridica del negozio per cui è stata creata l'impostazione.</span><span class="sxs-lookup"><span data-stu-id="d5801-136">Alternatively, the same language texts should be created in both the user's default company and the legal entity of the store that the setup is created for.</span></span>

<span data-ttu-id="d5801-137">Nella pagina **Testo lingua**, nella scheda **POS**, aggiungere i record seguenti per le etichette dei campi personalizzati per i formati di ricevuta.</span><span class="sxs-lookup"><span data-stu-id="d5801-137">On the **Language text** page, on the **POS** tab, add the following records for the labels of the custom fields for receipt formats.</span></span> <span data-ttu-id="d5801-138">Tenere presente che i valori di **ID lingua**, **ID testo** e **Testo** visualizzati nella seguente tabella sono solo esempi.</span><span class="sxs-lookup"><span data-stu-id="d5801-138">Note that the **Language ID**, **Text ID**, and **Text** values that are shown in the following table are just examples.</span></span> <span data-ttu-id="d5801-139">È possibile modificarli in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="d5801-139">You can change them to meet your requirements.</span></span> <span data-ttu-id="d5801-140">Tuttavia, i valori **ID testo** utilizzati devono essere univoci e devono essere uguali o maggiori di 900001.</span><span class="sxs-lookup"><span data-stu-id="d5801-140">However, the **Text ID** values that you use must be unique, and they must be equal to or more than 900001.</span></span>

| <span data-ttu-id="d5801-141">ID lingua</span><span class="sxs-lookup"><span data-stu-id="d5801-141">Language ID</span></span> | <span data-ttu-id="d5801-142">ID testo</span><span class="sxs-lookup"><span data-stu-id="d5801-142">Text ID</span></span> | <span data-ttu-id="d5801-143">Text</span><span class="sxs-lookup"><span data-stu-id="d5801-143">Text</span></span>                |
|-------------|---------|---------------------|
| <span data-ttu-id="d5801-144">en-US</span><span class="sxs-lookup"><span data-stu-id="d5801-144">en-US</span></span>       | <span data-ttu-id="d5801-145">900001</span><span class="sxs-lookup"><span data-stu-id="d5801-145">900001</span></span>  | <span data-ttu-id="d5801-146">Codice lotteria</span><span class="sxs-lookup"><span data-stu-id="d5801-146">Lottery code</span></span>        |
| <span data-ttu-id="d5801-147">en-US</span><span class="sxs-lookup"><span data-stu-id="d5801-147">en-US</span></span>       | <span data-ttu-id="d5801-148">900002</span><span class="sxs-lookup"><span data-stu-id="d5801-148">900002</span></span>  | <span data-ttu-id="d5801-149">Codice fiscale</span><span class="sxs-lookup"><span data-stu-id="d5801-149">Fiscal code</span></span>         |

<span data-ttu-id="d5801-150">Nella pagina **Campi personalizzati**, aggiungere i record seguenti per i campi personalizzati per i formati di ricevuta.</span><span class="sxs-lookup"><span data-stu-id="d5801-150">On the **Custom fields** page, add the following records for the custom fields for receipt formats.</span></span> <span data-ttu-id="d5801-151">Si noti che i valori **ID testo didascalia** devono corrispondere ai valori **ID testo** specificati nella pagina **Testo lingua**.</span><span class="sxs-lookup"><span data-stu-id="d5801-151">Note that the **Caption text ID** values must correspond to the **Text ID** values that you specified on the **Language text** page.</span></span>

| <span data-ttu-id="d5801-152">Nome</span><span class="sxs-lookup"><span data-stu-id="d5801-152">Name</span></span>                           | <span data-ttu-id="d5801-153">Tipo</span><span class="sxs-lookup"><span data-stu-id="d5801-153">Type</span></span>    | <span data-ttu-id="d5801-154">ID testo didascalia</span><span class="sxs-lookup"><span data-stu-id="d5801-154">Caption text ID</span></span> |
|--------------------------------|---------|-----------------|
| <span data-ttu-id="d5801-155">FISCALCUSTOMER\_LOTTERYCODE\_IT</span><span class="sxs-lookup"><span data-stu-id="d5801-155">FISCALCUSTOMER\_LOTTERYCODE\_IT</span></span>| <span data-ttu-id="d5801-156">Ricevimento</span><span class="sxs-lookup"><span data-stu-id="d5801-156">Receipt</span></span> | <span data-ttu-id="d5801-157">900001</span><span class="sxs-lookup"><span data-stu-id="d5801-157">900001</span></span>          |
| <span data-ttu-id="d5801-158">CUSTOMER\_FISCALCODE\_IT</span><span class="sxs-lookup"><span data-stu-id="d5801-158">CUSTOMER\_FISCALCODE\_IT</span></span>       | <span data-ttu-id="d5801-159">Ricevimento</span><span class="sxs-lookup"><span data-stu-id="d5801-159">Receipt</span></span> | <span data-ttu-id="d5801-160">900002</span><span class="sxs-lookup"><span data-stu-id="d5801-160">900002</span></span>          |

<span data-ttu-id="d5801-161">In Progettazione formato ricevuta, aggiungere i campi personalizzati alla sezione appropriata della ricevuta per ogni formato di ricevuta necessario.</span><span class="sxs-lookup"><span data-stu-id="d5801-161">In the Receipt format designer, add the custom fields to the appropriate receipt section for every receipt format that is required.</span></span> <span data-ttu-id="d5801-162">Per ulteriori informazioni sulle modalità di utilizzo dei formati di ricevute, vedere [Modelli e stampa di ricevute](../receipt-templates-printing.md)</span><span class="sxs-lookup"><span data-stu-id="d5801-162">For more information about how to work with receipt formats, see [Receipt templates and printing](../receipt-templates-printing.md).</span></span>

### <a name="add-a-customer-search-criterion"></a><span data-ttu-id="d5801-163">Aggiungere i criteri di ricerca cliente</span><span class="sxs-lookup"><span data-stu-id="d5801-163">Add a customer search criterion</span></span>

<span data-ttu-id="d5801-164">È possibile aggiungere i criteri di ricerca cliente in modo che sia possibile cercare i clienti nel POS in base al codice fiscale.</span><span class="sxs-lookup"><span data-stu-id="d5801-164">You can add a customer search criterion so that customers can be searched for in POS by their fiscal codes.</span></span>

<span data-ttu-id="d5801-165">Nella pagina **Parametri di commercio**, nella scheda **Criteri di ricerca POS**, aggiungere un nuovo criterio di ricerca del cliente.</span><span class="sxs-lookup"><span data-stu-id="d5801-165">On the **Commerce parameters** page, on the **POS search criteria** tab, add a new customer search criterion.</span></span> <span data-ttu-id="d5801-166">Nel campo **Criteri di ricerca cliente**, selezionare **Partita IVA**.</span><span class="sxs-lookup"><span data-stu-id="d5801-166">In the **Customer search criteria** field, select **Tax registration number**.</span></span> <span data-ttu-id="d5801-167">Selezionare la casella di controllo **Visualizza come collegamento**, ma lasciare deselezionata la casella di controllo **Ridefinizione possibile**.</span><span class="sxs-lookup"><span data-stu-id="d5801-167">Select the **Display as shortcut** check box, but leave the **Can be refined** check box cleared.</span></span> <span data-ttu-id="d5801-168">Nella pagina **Programmazioni della distribuzione**, eseguire il processo **1110**.</span><span class="sxs-lookup"><span data-stu-id="d5801-168">Then, on the **Distribution schedules** page, run the **1110** job.</span></span>

### <a name="configure-channel-components"></a><span data-ttu-id="d5801-169">Configurare i componenti del canale</span><span class="sxs-lookup"><span data-stu-id="d5801-169">Configure channel components</span></span>

<span data-ttu-id="d5801-170">Per rendere disponibile la funzionalità specifica dell'Italia, è necessario configurare le estensioni per i componenti del canale di commercio.</span><span class="sxs-lookup"><span data-stu-id="d5801-170">To make the functionality that is specific to Italy available, you must configure extensions for commerce channel components.</span></span> <span data-ttu-id="d5801-171">Per ulteriori informazioni, vedere la sezione [Linee guida per la distribuzione](#deployment-guidelines) più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="d5801-171">For more information, see the [Deployment guidelines](#deployment-guidelines) section later in this topic.</span></span>

## <a name="example-scenarios"></a><span data-ttu-id="d5801-172">Scenari di esempio</span><span class="sxs-lookup"><span data-stu-id="d5801-172">Example scenarios</span></span>

<span data-ttu-id="d5801-173">I seguenti scenari di esempio mostrano come utilizzare le informazioni sui clienti nel POS per l'Italia.</span><span class="sxs-lookup"><span data-stu-id="d5801-173">The following example scenarios show how to work with customer information in POS for Italy.</span></span>

### <a name="scenario-1-make-a-sale-to-an-anonymous-customer"></a><span data-ttu-id="d5801-174">Scenario 1: Effettuare una vendita a un cliente anonimo</span><span class="sxs-lookup"><span data-stu-id="d5801-174">Scenario 1: Make a sale to an anonymous customer</span></span>

1. <span data-ttu-id="d5801-175">Accedere a POS.</span><span class="sxs-lookup"><span data-stu-id="d5801-175">Sign in to POS.</span></span>
1. <span data-ttu-id="d5801-176">Aggiunge articoli al carrello.</span><span class="sxs-lookup"><span data-stu-id="d5801-176">Add items to the cart.</span></span>
1. <span data-ttu-id="d5801-177">Selezionare **Aggiungi informazioni cliente** e quindi selezionare **Immetti manualmente**.</span><span class="sxs-lookup"><span data-stu-id="d5801-177">Select **Add customer information**, and then select **Enter manually**.</span></span>
1. <span data-ttu-id="d5801-178">Immettere il codice lotteria del cliente e quindi selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="d5801-178">Enter the customer's lottery code, and then select **OK**.</span></span>
1. <span data-ttu-id="d5801-179">Registrare i pagamenti per la transazione e quindi completare la transazione.</span><span class="sxs-lookup"><span data-stu-id="d5801-179">Register payments for the transaction, and then finalize the transaction.</span></span>
1. <span data-ttu-id="d5801-180">Verificare che la ricevuta stampata contenga il codice lotteria del cliente.</span><span class="sxs-lookup"><span data-stu-id="d5801-180">Verify that the printed receipt contains the customer's lottery code.</span></span>

### <a name="scenario-2-make-a-sale-to-a-new-named-customer"></a><span data-ttu-id="d5801-181">Scenario 2: Effettuare una vendita a un nuovo cliente denominato</span><span class="sxs-lookup"><span data-stu-id="d5801-181">Scenario 2: Make a sale to a new named customer</span></span>

1. <span data-ttu-id="d5801-182">Accedere a POS.</span><span class="sxs-lookup"><span data-stu-id="d5801-182">Sign in to POS.</span></span>
1. <span data-ttu-id="d5801-183">Aggiunge articoli al carrello.</span><span class="sxs-lookup"><span data-stu-id="d5801-183">Add items to the cart.</span></span>
1. <span data-ttu-id="d5801-184">Selezionare **Aggiungi cliente** e quindi selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="d5801-184">Select **Add customer**, and then select **New**.</span></span>
1. <span data-ttu-id="d5801-185">Specificare gli attributi del nuovo cliente.</span><span class="sxs-lookup"><span data-stu-id="d5801-185">Specify the new customer's attributes.</span></span> <span data-ttu-id="d5801-186">Nel campo **Codice fiscale**, immettere il codice fiscale del cliente.</span><span class="sxs-lookup"><span data-stu-id="d5801-186">In the **Fiscal code** field, enter the customer's fiscal code.</span></span>
1. <span data-ttu-id="d5801-187">Selezionare **Crea una nuova rubrica**.</span><span class="sxs-lookup"><span data-stu-id="d5801-187">Select **Create a new address**.</span></span> <span data-ttu-id="d5801-188">Quindi specificare le informazioni di contatto del nuovo cliente e un indirizzo.</span><span class="sxs-lookup"><span data-stu-id="d5801-188">Then specify the new customer's contact information and an address.</span></span>
1. <span data-ttu-id="d5801-189">Nel campo **Codice lotteria**, immettere il codice lotteria del cliente.</span><span class="sxs-lookup"><span data-stu-id="d5801-189">In the **Lottery code** field, enter the customer's lottery code.</span></span>
1. <span data-ttu-id="d5801-190">Salvare il record cliente e il record indirizzo cliente e aggiungere il cliente alla transazione.</span><span class="sxs-lookup"><span data-stu-id="d5801-190">Save the customer record and the customer address record, and add the customer to the transaction.</span></span>
1. <span data-ttu-id="d5801-191">Registrare i pagamenti per la transazione e quindi completare la transazione.</span><span class="sxs-lookup"><span data-stu-id="d5801-191">Register payments for the transaction, and then finalize the transaction.</span></span>
1. <span data-ttu-id="d5801-192">Poiché la richiesta di informazioni relative al cliente è stata attivata, ma tali informazioni non sono state aggiunte alla transazione, il viene visualizzata la finestra di dialogo **Immettere informazioni cliente**.</span><span class="sxs-lookup"><span data-stu-id="d5801-192">Because the inquiry for customer information has been activated, but customer information hasn't been added to the transaction, the **Enter customer information** dialog box is opened.</span></span> <span data-ttu-id="d5801-193">Selezionare **Sì**, quindi selezionare **Copia dal cliente della transazione**.</span><span class="sxs-lookup"><span data-stu-id="d5801-193">Select **Yes**, and then select **Copy from transaction customer**.</span></span>
1. <span data-ttu-id="d5801-194">Verificare il codice lotteria del cliente e quindi selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="d5801-194">Verify the customer's lottery code, and then select **OK**.</span></span>
1. <span data-ttu-id="d5801-195">Verificare che la ricevuta stampata contenga il codice lotteria del cliente.</span><span class="sxs-lookup"><span data-stu-id="d5801-195">Verify that the printed receipt contains the customer's lottery code.</span></span>

> [!NOTE]
> <span data-ttu-id="d5801-196">Se è necessario specificare un cliente diverso per la transazione, è necessario cancellare le informazioni sul cliente e copiarle nuovamente dopo aver aggiunto il nuovo cliente.</span><span class="sxs-lookup"><span data-stu-id="d5801-196">If you must specify a different customer for the transaction, you must clear the customer information and then copy it again after the new customer is added.</span></span>

### <a name="scenario-3-change-the-customer-information-for-a-sale-to-a-named-customer"></a><span data-ttu-id="d5801-197">Scenario 3: Modificare le informazioni relative al cliente per una vendita su un cliente specifico</span><span class="sxs-lookup"><span data-stu-id="d5801-197">Scenario 3: Change the customer information for a sale to a named customer</span></span>

1. <span data-ttu-id="d5801-198">Accedere a POS.</span><span class="sxs-lookup"><span data-stu-id="d5801-198">Sign in to POS.</span></span>
1. <span data-ttu-id="d5801-199">Aggiunge articoli al carrello.</span><span class="sxs-lookup"><span data-stu-id="d5801-199">Add items to the cart.</span></span>
1. <span data-ttu-id="d5801-200">Selezionare **Aggiungi cliente** e quindi selezionare un account cliente per aggiungerlo alla transazione.</span><span class="sxs-lookup"><span data-stu-id="d5801-200">Select **Add customer**, and then select a customer account to add it to the transaction.</span></span>
1. <span data-ttu-id="d5801-201">Selezionare **Aggiungi informazioni cliente**, quindi selezionare **Copia dal cliente della transazione**.</span><span class="sxs-lookup"><span data-stu-id="d5801-201">Select **Add customer information**, and then select **Copy from transaction customer**.</span></span>
1. <span data-ttu-id="d5801-202">Verificare il codice lotteria del cliente e quindi selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="d5801-202">Verify the customer's lottery code, and then select **OK**.</span></span>
1. <span data-ttu-id="d5801-203">Selezionare **Aggiungi informazioni cliente** e quindi selezionare **Cancella** per cancellare le informazioni relative al cliente dalla transazione.</span><span class="sxs-lookup"><span data-stu-id="d5801-203">Select **Add customer information**, and then select **Clear** to clear the customer information from the transaction.</span></span>
1. <span data-ttu-id="d5801-204">Selezionare **Aggiungi informazioni cliente** e quindi selezionare **Immetti manualmente**.</span><span class="sxs-lookup"><span data-stu-id="d5801-204">Select **Add customer information**, and then select **Enter manually**.</span></span>
1. <span data-ttu-id="d5801-205">Specificare il codice lotteria del cliente e quindi selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="d5801-205">Specify the customer's lottery code, and then select **OK**.</span></span>
1. <span data-ttu-id="d5801-206">Registrare i pagamenti per la transazione e quindi completare la transazione.</span><span class="sxs-lookup"><span data-stu-id="d5801-206">Register payments for the transaction, and then finalize the transaction.</span></span>
1. <span data-ttu-id="d5801-207">Verificare che la ricevuta stampata contenga il codice lotteria del cliente.</span><span class="sxs-lookup"><span data-stu-id="d5801-207">Verify that the printed receipt contains the customer's lottery code.</span></span>

## <a name="deployment-guidelines"></a><span data-ttu-id="d5801-208">Linee guida per la distribuzione</span><span class="sxs-lookup"><span data-stu-id="d5801-208">Deployment guidelines</span></span>

<span data-ttu-id="d5801-209">In questa sezione vengono fornite le linee guida per la distribuzione per consentire la gestione delle informazioni sui clienti nella localizzazione di Commerce per l'Italia.</span><span class="sxs-lookup"><span data-stu-id="d5801-209">This section provides deployment guidance for enabling customer information management in the localization of Commerce for Italy.</span></span>

> [!NOTE]
> <span data-ttu-id="d5801-210">Alcuni passaggi in queste procedure variano in base alla versione di Commerce in uso.</span><span class="sxs-lookup"><span data-stu-id="d5801-210">Some steps in these procedures vary, depending on the version of Commerce that you're using.</span></span> <span data-ttu-id="d5801-211">Per ulteriori informazioni, vedere [Novità o modifiche in Dynamics 365 for Retail](../get-started/whats-new.md).</span><span class="sxs-lookup"><span data-stu-id="d5801-211">For more information, see [What's new or changed in Dynamics 365 for Retail](../get-started/whats-new.md).</span></span>
>
> <span data-ttu-id="d5801-212">Se si desidera abilitare l'integrazione del POS con le stampanti fiscali per l'Italia, e in particolare se si desidera stampare i codici lotteria dei clienti sulle ricevute fiscali, è necessario distribuire [l'esempio di integrazione di stampante fiscale per l'Italia](emea-ita-fpi-sample.md).</span><span class="sxs-lookup"><span data-stu-id="d5801-212">If you want to enable the integration of POS with fiscal printers for Italy, and specifically if you want to print customer lottery codes on fiscal receipts, you must deploy the [fiscal printer integration sample for Italy](emea-ita-fpi-sample.md).</span></span>

### <a name="update-customizations"></a><span data-ttu-id="d5801-213">Aggiornare le personalizzazioni</span><span class="sxs-lookup"><span data-stu-id="d5801-213">Update customizations</span></span>

<span data-ttu-id="d5801-214">Seguire i passaggi seguenti per aggiornare le personalizzazioni.</span><span class="sxs-lookup"><span data-stu-id="d5801-214">Follow these steps to update customizations.</span></span>

# <a name="retail-1007-and-later"></a>[<span data-ttu-id="d5801-215">Retail 10.0.7 e versioni successive</span><span class="sxs-lookup"><span data-stu-id="d5801-215">Retail 10.0.7 and later</span></span>](#tab/retail-10-0-7)

<span data-ttu-id="d5801-216">Se una qualsiasi delle personalizzazioni include gestori di richieste per le richieste `SaveCartRequest` o `CreateSalesOrderServiceRequest`:</span><span class="sxs-lookup"><span data-stu-id="d5801-216">If any of your customizations include request handlers for the `SaveCartRequest` or `CreateSalesOrderServiceRequest` requests:</span></span>

1. <span data-ttu-id="d5801-217">Trovare il gestore delle richieste per `SaveCartRequest`.</span><span class="sxs-lookup"><span data-stu-id="d5801-217">Find the request handler for `SaveCartRequest`.</span></span>
1. <span data-ttu-id="d5801-218">Individuare la riga di codice che esegue il gestore delle richieste originale.</span><span class="sxs-lookup"><span data-stu-id="d5801-218">Find the line of code that runs the original request handler.</span></span>
1. <span data-ttu-id="d5801-219">Aggiungere le seguenti righe prima di chiamare il gestore delle richieste originale:</span><span class="sxs-lookup"><span data-stu-id="d5801-219">Add the following lines before calling the original request handler:</span></span>

    ```cs
    using Microsoft.Dynamics.Commerce.Runtime.TaxRegistrationIdItaly.Services;

    ...

    new TaxRegistrationIdFiscalCustomerService().Execute(request);
    ```

1. <span data-ttu-id="d5801-220">Trovare il gestore delle richieste per `CreateSalesOrderServiceRequest`.</span><span class="sxs-lookup"><span data-stu-id="d5801-220">Find the request handler for `CreateSalesOrderServiceRequest`.</span></span>
1. <span data-ttu-id="d5801-221">Individuare la riga di codice che esegue il gestore delle richieste originale.</span><span class="sxs-lookup"><span data-stu-id="d5801-221">Find the line of code that runs the original request handler.</span></span>
1. <span data-ttu-id="d5801-222">Sostituirlo con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="d5801-222">Replace it with the following code:</span></span>

    ```cs
    using Microsoft.Dynamics.Commerce.Runtime.TaxRegistrationIdItaly.Services;

    ...

    return new TaxRegistrationIdFiscalCustomerService().Execute(request);
    ```

# <a name="retail-10012-and-later"></a>[<span data-ttu-id="d5801-223">Retail 10.0.12 e versioni successive</span><span class="sxs-lookup"><span data-stu-id="d5801-223">Retail 10.0.12 and later</span></span>](#tab/retail-10-0-12)

<span data-ttu-id="d5801-224">Se le personalizzazioni includono riferimenti al servizio `TaxRegistrationIdFiscalCustomerService`, questi devono essere rimossi.</span><span class="sxs-lookup"><span data-stu-id="d5801-224">If customizations have references to the `TaxRegistrationIdFiscalCustomerService` service, they must be removed.</span></span>

---

### <a name="update-a-development-environment"></a><span data-ttu-id="d5801-225">Aggiornare un ambiente di sviluppo</span><span class="sxs-lookup"><span data-stu-id="d5801-225">Update a development environment</span></span>

<span data-ttu-id="d5801-226">Seguire questi passaggi per aggiornare un ambiente di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="d5801-226">Follow these steps to update a development environment.</span></span>

#### <a name="crt-extension-components"></a><span data-ttu-id="d5801-227">Componenti dell'estensione CRT</span><span class="sxs-lookup"><span data-stu-id="d5801-227">CRT extension components</span></span>

1. <span data-ttu-id="d5801-228">Individuare il file di configurazione dell'estensione per Commerce Runtime (CRT):</span><span class="sxs-lookup"><span data-stu-id="d5801-228">Find the extension configuration file for the Commerce runtime (CRT):</span></span>

    - <span data-ttu-id="d5801-229">**Commerce Scale Unit:** individuare il file **CommerceRuntime.Ext.config** nella cartella **bin\\ext** nella posizione del sito Commerce Scale Unit di Microsoft Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="d5801-229">**Commerce Scale Unit:** Find the **CommerceRuntime.Ext.config** file in the **bin\\ext** folder under the Microsoft Internet Information Services (IIS) Commerce Scale Unit site location.</span></span>
    - <span data-ttu-id="d5801-230">**CRT locale sul POS moderno:** Trovare il file **CommerceRuntime.MPOSOffline.Ext.config** nella posizione del broker client CRT locale.</span><span class="sxs-lookup"><span data-stu-id="d5801-230">**Local CRT on Modern POS:** Find the **CommerceRuntime.MPOSOffline.Ext.config** file under the local CRT client broker location.</span></span>

1. <span data-ttu-id="d5801-231">Registrare l'estensione CRT nel file di configurazione dell'estensione.</span><span class="sxs-lookup"><span data-stu-id="d5801-231">Register the CRT extension in the extension configuration file.</span></span>

    ``` xml
    <add source="assembly" value="Microsoft.Dynamics.Commerce.Runtime.TaxRegistrationIdItaly" />
    ```

    > [!WARNING]
    > <span data-ttu-id="d5801-232">**Non** modificare i file CommerceRuntime.MPOSOffline.config e CommerceRuntime.config.</span><span class="sxs-lookup"><span data-stu-id="d5801-232">Do **not** edit the CommerceRuntime.config and CommerceRuntime.MPOSOffline.config files.</span></span> <span data-ttu-id="d5801-233">Questi file non sono progettati per essere personalizzati.</span><span class="sxs-lookup"><span data-stu-id="d5801-233">These files aren't intended for any customizations.</span></span>

#### <a name="modern-pos-extension-components"></a><span data-ttu-id="d5801-234">Componenti dell'estensione POS moderno</span><span class="sxs-lookup"><span data-stu-id="d5801-234">Modern POS extension components</span></span>

<span data-ttu-id="d5801-235">Seguire questi passaggi per rendere disponibile l'estensione TaxRegistrationId.IT.</span><span class="sxs-lookup"><span data-stu-id="d5801-235">Follow these steps to make the TaxRegistrationId.IT extension available.</span></span>

1. <span data-ttu-id="d5801-236">Aprire la soluzione in **RetailSdk\\POS\\ModernPOS.sln**.</span><span class="sxs-lookup"><span data-stu-id="d5801-236">Open the solution at **RetailSdk\\POS\\ModernPOS.sln**.</span></span>
1. <span data-ttu-id="d5801-237">In **POS.Extensions\\extensions.json**, attivare l'estensione.</span><span class="sxs-lookup"><span data-stu-id="d5801-237">In **POS.Extensions\\extensions.json**, turn on the extension.</span></span>

    ``` json
    {
        "extensionPackages": [
            {
                "baseUrl": "Microsoft/TaxRegistrationId.IT"
            }
        ]
    }
    ```

1. <span data-ttu-id="d5801-238">Compilare la soluzione.</span><span class="sxs-lookup"><span data-stu-id="d5801-238">Build the solution.</span></span>
1. <span data-ttu-id="d5801-239">Aprire POS moderno e verificare la funzionalità.</span><span class="sxs-lookup"><span data-stu-id="d5801-239">Open Modern POS, and test the functionality.</span></span>

#### <a name="cloud-pos-extension-components"></a><span data-ttu-id="d5801-240">Componenti dell'estensione POS cloud</span><span class="sxs-lookup"><span data-stu-id="d5801-240">Cloud POS extension components</span></span>

<span data-ttu-id="d5801-241">Seguire questi passaggi per rendere disponibile l'estensione TaxRegistrationId.IT.</span><span class="sxs-lookup"><span data-stu-id="d5801-241">Follow these steps to make the TaxRegistrationId.IT extension available.</span></span>

1. <span data-ttu-id="d5801-242">Aprire la soluzione in **RetailSdk\\POS\\CloudPOS.sln**.</span><span class="sxs-lookup"><span data-stu-id="d5801-242">Open the solution at **RetailSdk\\POS\\CloudPOS.sln**.</span></span>
1. <span data-ttu-id="d5801-243">In **POS.Extensions\\extensions.json**, attivare l'estensione.</span><span class="sxs-lookup"><span data-stu-id="d5801-243">In **POS.Extensions\\extensions.json**, turn on the extension.</span></span>

    ``` json
    {
        "extensionPackages": [
            {
                "baseUrl": "Microsoft/TaxRegistrationId.IT"
            }
        ]
    }
    ```

1. <span data-ttu-id="d5801-244">Compilare la soluzione.</span><span class="sxs-lookup"><span data-stu-id="d5801-244">Build the solution.</span></span>
1. <span data-ttu-id="d5801-245">Aprire POS cloud e verificare la funzionalità.</span><span class="sxs-lookup"><span data-stu-id="d5801-245">Open Cloud POS, and test the functionality.</span></span>

### <a name="update-a-production-environment"></a><span data-ttu-id="d5801-246">Aggiornare un ambiente di produzione</span><span class="sxs-lookup"><span data-stu-id="d5801-246">Update a production environment</span></span>

<span data-ttu-id="d5801-247">Attenersi alla procedura seguente per creare pacchetti distribuibili contenenti componenti Commerce e per applicare i pacchetti a un ambiente di produzione.</span><span class="sxs-lookup"><span data-stu-id="d5801-247">Follow these steps to create deployable packages that contain Commerce components, and to apply the packages in a production environment.</span></span>

1. <span data-ttu-id="d5801-248">Nei file di configurazione **CommerceRuntime.Ext.config** e **CommerceRuntime.MPOSOffline.Ext.config** nella cartella **RetailSdk\\Assets**, aggiungere le seguenti righe alla sezione **composition**.</span><span class="sxs-lookup"><span data-stu-id="d5801-248">In the **CommerceRuntime.Ext.config** and **CommerceRuntime.MPOSOffline.Ext.config** configuration files under the **RetailSdk\\Assets** folder, add the following lines to the **composition** section.</span></span>

    ``` xml
    <add source="assembly" value="Microsoft.Dynamics.Commerce.Runtime.TaxRegistrationIdItaly" />
    ```

1. <span data-ttu-id="d5801-249">Attivare l'estensione POS **TaxRegistrationId.IT**.</span><span class="sxs-lookup"><span data-stu-id="d5801-249">Turn on the **TaxRegistrationId.IT** POS extension.</span></span>

    ``` json
    {
        "extensionPackages": [
            {
                "baseUrl": "Microsoft/TaxRegistrationId.IT"
            }
        ]
    }
    ```

1. <span data-ttu-id="d5801-250">Eseguire **msbuild** per l'intero Retail SDK per creare i pacchetti distribuibili.</span><span class="sxs-lookup"><span data-stu-id="d5801-250">Run **msbuild** for the whole Retail software development kit (SDK) to create deployable packages.</span></span>
1. <span data-ttu-id="d5801-251">Applicare i pacchetti via Microsoft Dynamics Lifecycle Services (LCS) o manualmente.</span><span class="sxs-lookup"><span data-stu-id="d5801-251">Apply the packages via Microsoft Dynamics Lifecycle Services (LCS) or manually.</span></span> <span data-ttu-id="d5801-252">Per ulteriori informazioni, vedere [Confezione di Retail SDK](../dev-itpro/retail-sdk/retail-sdk-packaging.md).</span><span class="sxs-lookup"><span data-stu-id="d5801-252">For more information, see [Retail SDK packaging](../dev-itpro/retail-sdk/retail-sdk-packaging.md).</span></span>
