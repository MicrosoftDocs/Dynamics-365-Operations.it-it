---
title: Gestione delle informazioni del cliente per l'Italia
description: In questo argomento viene descritto come gestire le informazioni relative al cliente in Retail POS per l'Italia.
author: ''
manager: annbe
ms.date: 10/08/2019
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
ms.openlocfilehash: 443e513fe1ece8d4740406de861a2b759a9d4351
ms.sourcegitcommit: 0262a19e32b2c0c84c731d9f4fbe8ba91822afa3
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/15/2019
ms.locfileid: "2622702"
---
# <a name="customer-information-management-for-italy"></a><span data-ttu-id="b127c-103">Gestione delle informazioni del cliente per l'Italia</span><span class="sxs-lookup"><span data-stu-id="b127c-103">Customer information management for Italy</span></span>

[!include [banner](../includes/banner.md)]

## <a name="introduction"></a><span data-ttu-id="b127c-104">Introduzione</span><span class="sxs-lookup"><span data-stu-id="b127c-104">Introduction</span></span>

<span data-ttu-id="b127c-105">In questo argomento viene descritto come è possibile gestire le informazioni del cliente, ad esempio il codice fiscale del cliente, in Retail POS per l'Italia.</span><span class="sxs-lookup"><span data-stu-id="b127c-105">This topic describes how you can handle customer information, such as the customer's fiscal code, in Retail point of sale (POS) for Italy.</span></span>

<span data-ttu-id="b127c-106">È possibile specificare il codice fiscale del cliente quando si crea o si modifica un record di dati master del cliente in POS.</span><span class="sxs-lookup"><span data-stu-id="b127c-106">You can specify the customer's fiscal code when you create or edit a customer master record in POS.</span></span> <span data-ttu-id="b127c-107">È inoltre possibile specificare il codice fiscale per una transazione di vendita copiandolo dal cliente della transazione o immettendolo manualmente.</span><span class="sxs-lookup"><span data-stu-id="b127c-107">You can also specify the fiscal code for a sales transaction by copying it from the transaction customer or entering it manually.</span></span> <span data-ttu-id="b127c-108">Le informazioni del cliente possono quindi essere stampate sia sulle ricevute fiscali e normali e possono essere utilizzate per la lotteria nazionale.</span><span class="sxs-lookup"><span data-stu-id="b127c-108">The customer information can then be printed on both regular and fiscal receipts, and can be used for the National lottery.</span></span> <span data-ttu-id="b127c-109">I codici fiscali personali possono inoltre essere utilizzati per individuare un cliente in POS.</span><span class="sxs-lookup"><span data-stu-id="b127c-109">Personal fiscal codes can also be used to search for a customer in POS.</span></span>

> [!NOTE]
> <span data-ttu-id="b127c-110">Questa funzionalità è disponibile nella versione 10.0.7 e successive delle app Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="b127c-110">This functionality is available in version 10.0.7 and later of the Finance and Operations apps.</span></span>

## <a name="setup"></a><span data-ttu-id="b127c-111">Impostazione</span><span class="sxs-lookup"><span data-stu-id="b127c-111">Setup</span></span>

<span data-ttu-id="b127c-112">È necessario completare la seguente configurazione per utilizzare questa funzionalità:</span><span class="sxs-lookup"><span data-stu-id="b127c-112">You must complete the following configuration to use this functionality:</span></span>

- <span data-ttu-id="b127c-113">Aggiungere l'operazione "Aggiungi informazioni cliente" ai layout dello schermo.</span><span class="sxs-lookup"><span data-stu-id="b127c-113">Add the "Add customer information" operation to screen layouts.</span></span>
- <span data-ttu-id="b127c-114">Attivare la richiesta di informazioni del cliente.</span><span class="sxs-lookup"><span data-stu-id="b127c-114">Activate the inquiry for customer information.</span></span>
- <span data-ttu-id="b127c-115">Impostare i formati di ricevuta.</span><span class="sxs-lookup"><span data-stu-id="b127c-115">Set up receipt formats.</span></span>
- <span data-ttu-id="b127c-116">Aggiungere i criteri di ricerca cliente.</span><span class="sxs-lookup"><span data-stu-id="b127c-116">Add a customer search criterion.</span></span>
- <span data-ttu-id="b127c-117">Configurare i componenti del canale vendita al dettaglio.</span><span class="sxs-lookup"><span data-stu-id="b127c-117">Configure retail channel components.</span></span>

### <a name="add-the-add-customer-information-operation-to-screen-layouts"></a><span data-ttu-id="b127c-118">Aggiungere l'operazione "Aggiungi informazioni cliente" ai layout dello schermo</span><span class="sxs-lookup"><span data-stu-id="b127c-118">Add the "Add customer information" operation to screen layouts</span></span>

<span data-ttu-id="b127c-119">L'operazione "Aggiungi informazioni cliente" può essere utilizzata per aggiungere le informazioni del cliente, come il codice fiscale, a una transazione di vendita.</span><span class="sxs-lookup"><span data-stu-id="b127c-119">The "Add customer information" operation can be used to add customer information, such as the fiscal code, to a sales transaction.</span></span> <span data-ttu-id="b127c-120">Queste informazioni possono essere copiate dal cliente specificato per la transazione oppure possono essere inserite manualmente.</span><span class="sxs-lookup"><span data-stu-id="b127c-120">This information can be copied from the customer that is specified for the transaction, or it can be manually entered.</span></span>

<span data-ttu-id="b127c-121">Nella pagina **Griglie dei pulsanti**, selezionare la griglia dei pulsanti in cui dovrebbe apparire l'operazione e aprire la finestra Progettazione griglia dei pulsanti.</span><span class="sxs-lookup"><span data-stu-id="b127c-121">On the **Button grids** page, select the button grid where the operation should appear, and open the Button grid designer.</span></span> <span data-ttu-id="b127c-122">Aggiungere un nuovo pulsante, quindi nel campo **Azione** selezionare **Aggiungi informazioni cliente**.</span><span class="sxs-lookup"><span data-stu-id="b127c-122">Add a new button, and then, in the **Action** field, select **Add customer information**.</span></span> <span data-ttu-id="b127c-123">Per ulteriori informazioni sull'utilizzo dei layout dello schermo e delle griglie dei pulsanti, vedere [Layout delle schermate per il POS](../pos-screen-layouts.md).</span><span class="sxs-lookup"><span data-stu-id="b127c-123">For more information about how to work with screen layouts and button grids, see [Screen layouts for the point of sale (POS)](../pos-screen-layouts.md).</span></span>

### <a name="activate-the-inquiry-for-customer-information"></a><span data-ttu-id="b127c-124">Attivare la richiesta di informazioni del cliente</span><span class="sxs-lookup"><span data-stu-id="b127c-124">Activate the inquiry for customer information</span></span>

<span data-ttu-id="b127c-125">Se le informazioni del cliente non sono specificate per una transazione di vendita, una richiesta per tali informazioni può essere attivata automaticamente dopo la finalizzazione della transazione.</span><span class="sxs-lookup"><span data-stu-id="b127c-125">If the customer information isn't specified for a sales transaction, an inquiry for that information can be triggered automatically after the transaction is finalized.</span></span> <span data-ttu-id="b127c-126">Questo approccio è un'alternativa all'operazione "Aggiungi informazioni cliente".</span><span class="sxs-lookup"><span data-stu-id="b127c-126">This approach is an alternative to the "Add customer information" operation.</span></span>

<span data-ttu-id="b127c-127">Per attivare la richiesta di informazioni cliente, impostare l'opzione **Abilita richiesta informazioni sul cliente nelle transazioni di vendita** su **Sì** nella sezione **Parametri imposte** della Scheda dettaglio **Funzioni** della pagina **Profili funzionalità POS**.</span><span class="sxs-lookup"><span data-stu-id="b127c-127">To activate the inquiry for customer information, set the **Enable inquiry of customer information in sales transactions** option to **Yes** in the **Tax parameters** section on the **Functions** FastTab of the **POS functionality profiles** page.</span></span>

### <a name="set-up-receipt-formats"></a><span data-ttu-id="b127c-128">Impostare formati di ricevuta</span><span class="sxs-lookup"><span data-stu-id="b127c-128">Set up receipt formats</span></span>

<span data-ttu-id="b127c-129">È possibile configurare i formati di ricevuta in modo che il codice fiscale del cliente venga stampato sulle ricevute.</span><span class="sxs-lookup"><span data-stu-id="b127c-129">You can configure receipt formats so that the customer's fiscal code is printed on receipts.</span></span>

> [!NOTE]
> <span data-ttu-id="b127c-130">La società predefinita dell'utente che crea l'impostazione della ricevuta deve essere la stessa persona giuridica in cui viene creata l'impostazione del testo della lingua.</span><span class="sxs-lookup"><span data-stu-id="b127c-130">The default company of the user who creates the receipt setup should be the same legal entity where the language text setup is created.</span></span> <span data-ttu-id="b127c-131">In alternativa, i testi nella stessa lingua devono essere creati sia nella società predefinita dell'utente sia nella persona giuridica del negozio per cui è stata creata l'impostazione.</span><span class="sxs-lookup"><span data-stu-id="b127c-131">Alternatively, the same language texts should be created in both the user's default company and the legal entity of the store that the setup is created for.</span></span>

<span data-ttu-id="b127c-132">Nella pagina **Testo lingua**, nella scheda **POS**, aggiungere i record seguenti per le etichette dei campi personalizzati per i formati di ricevuta.</span><span class="sxs-lookup"><span data-stu-id="b127c-132">On the **Language text** page, on the **POS** tab, add the following records for the labels of the custom fields for receipt formats.</span></span> <span data-ttu-id="b127c-133">Tenere presente che i valori di **ID lingua**, **ID testo** e **Testo** visualizzati nella seguente tabella sono solo esempi.</span><span class="sxs-lookup"><span data-stu-id="b127c-133">Note that the **Language ID**, **Text ID**, and **Text** values that are shown in the following table are just examples.</span></span> <span data-ttu-id="b127c-134">È possibile modificarli in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="b127c-134">You can change them to meet your requirements.</span></span> <span data-ttu-id="b127c-135">Tuttavia, i valori **ID testo** utilizzati devono essere univoci e devono essere uguali o maggiori di 900001.</span><span class="sxs-lookup"><span data-stu-id="b127c-135">However, the **Text ID** values that you use must be unique, and they must be equal to or more than 900001.</span></span>

| <span data-ttu-id="b127c-136">ID lingua</span><span class="sxs-lookup"><span data-stu-id="b127c-136">Language ID</span></span> | <span data-ttu-id="b127c-137">ID testo</span><span class="sxs-lookup"><span data-stu-id="b127c-137">Text ID</span></span> | <span data-ttu-id="b127c-138">Testo</span><span class="sxs-lookup"><span data-stu-id="b127c-138">Text</span></span>                |
|-------------|---------|---------------------|
| <span data-ttu-id="b127c-139">en-US</span><span class="sxs-lookup"><span data-stu-id="b127c-139">en-US</span></span>       | <span data-ttu-id="b127c-140">900001</span><span class="sxs-lookup"><span data-stu-id="b127c-140">900001</span></span>  | <span data-ttu-id="b127c-141">Codice fiscale</span><span class="sxs-lookup"><span data-stu-id="b127c-141">Fiscal code</span></span>         |

<span data-ttu-id="b127c-142">Nella pagina **Campi personalizzati**, aggiungere i record seguenti per i campi personalizzati per i formati di ricevuta.</span><span class="sxs-lookup"><span data-stu-id="b127c-142">On the **Custom fields** page, add the following records for the custom fields for receipt formats.</span></span> <span data-ttu-id="b127c-143">Si noti che i valori **ID testo didascalia** devono corrispondere ai valori **ID testo** specificati nella pagina **Testo lingua**.</span><span class="sxs-lookup"><span data-stu-id="b127c-143">Note that the **Caption text ID** values must correspond to the **Text ID** values that you specified on the **Language text** page.</span></span>

| <span data-ttu-id="b127c-144">Nome</span><span class="sxs-lookup"><span data-stu-id="b127c-144">Name</span></span>                           | <span data-ttu-id="b127c-145">Tipo</span><span class="sxs-lookup"><span data-stu-id="b127c-145">Type</span></span>    | <span data-ttu-id="b127c-146">ID testo didascalia</span><span class="sxs-lookup"><span data-stu-id="b127c-146">Caption text ID</span></span> |
|--------------------------------|---------|-----------------|
| <span data-ttu-id="b127c-147">FISCALCUSTOMER\_FISCALCODE\_IT</span><span class="sxs-lookup"><span data-stu-id="b127c-147">FISCALCUSTOMER\_FISCALCODE\_IT</span></span> | <span data-ttu-id="b127c-148">Ricevimento</span><span class="sxs-lookup"><span data-stu-id="b127c-148">Receipt</span></span> | <span data-ttu-id="b127c-149">900001</span><span class="sxs-lookup"><span data-stu-id="b127c-149">900001</span></span>          |

<span data-ttu-id="b127c-150">In Progettazione formato ricevuta, aggiungere i campi personalizzati alla sezione appropriata della ricevuta per ogni formato di ricevuta necessario.</span><span class="sxs-lookup"><span data-stu-id="b127c-150">In the Receipt format designer, add the custom fields to the appropriate receipt section for every receipt format that is required.</span></span> <span data-ttu-id="b127c-151">Per ulteriori informazioni sulle modalità di utilizzo dei formati di ricevute, vedere [Modelli e stampa di ricevute](../receipt-templates-printing.md)</span><span class="sxs-lookup"><span data-stu-id="b127c-151">For more information about how to work with receipt formats, see [Receipt templates and printing](../receipt-templates-printing.md).</span></span>

### <a name="add-a-customer-search-criterion"></a><span data-ttu-id="b127c-152">Aggiungere i criteri di ricerca cliente</span><span class="sxs-lookup"><span data-stu-id="b127c-152">Add a customer search criterion</span></span>

<span data-ttu-id="b127c-153">È possibile aggiungere i criteri di ricerca cliente in modo che sia possibile cercare i clienti nel POS in base al codice fiscale.</span><span class="sxs-lookup"><span data-stu-id="b127c-153">You can add a customer search criterion so that customers can be searched for in POS by their fiscal codes.</span></span>

<span data-ttu-id="b127c-154">Nella pagina **Parametri di vendita al dettaglio**, nella scheda **Criteri di ricerca POS**, aggiungere un nuovo criterio di ricerca del cliente.</span><span class="sxs-lookup"><span data-stu-id="b127c-154">On the **Retail parameters** page, on the **POS search criteria** tab, add a new customer search criterion.</span></span> <span data-ttu-id="b127c-155">Nel campo **Criteri di ricerca cliente**, selezionare **Partita IVA**.</span><span class="sxs-lookup"><span data-stu-id="b127c-155">In the **Customer search criteria** field, select **Tax registration number**.</span></span> <span data-ttu-id="b127c-156">Selezionare la casella di controllo **Visualizza come collegamento**, ma lasciare deselezionata la casella di controllo **Ridefinizione possibile**.</span><span class="sxs-lookup"><span data-stu-id="b127c-156">Select the **Display as shortcut** check box, but leave the **Can be refined** check box cleared.</span></span> <span data-ttu-id="b127c-157">Nella pagina **Programmazioni della distribuzione**, eseguire il processo **1110**.</span><span class="sxs-lookup"><span data-stu-id="b127c-157">Then, on the **Distribution schedules** page, run the **1110** job.</span></span>

### <a name="configure-retail-channel-components"></a><span data-ttu-id="b127c-158">Configurare i componenti del canale vendita al dettaglio</span><span class="sxs-lookup"><span data-stu-id="b127c-158">Configure retail channel components</span></span>

<span data-ttu-id="b127c-159">Per rendere disponibile la funzionalità specifica dell'Italia, è necessario configurare le estensioni per i componenti del canale di vendita al dettaglio.</span><span class="sxs-lookup"><span data-stu-id="b127c-159">To make the functionality that is specific to Italy available, you must configure extensions for retail channel components.</span></span> <span data-ttu-id="b127c-160">Per ulteriori informazioni, vedere la sezione [Linee guida per la distribuzione](#deployment-guidelines) più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="b127c-160">For more information, see the [Deployment guidelines](#deployment-guidelines) section later in this topic.</span></span>

## <a name="example-scenarios"></a><span data-ttu-id="b127c-161">Scenari di esempio</span><span class="sxs-lookup"><span data-stu-id="b127c-161">Example scenarios</span></span>

<span data-ttu-id="b127c-162">I seguenti esempi mostrano come utilizzare le informazioni dei clienti in POS per l'Italia.</span><span class="sxs-lookup"><span data-stu-id="b127c-162">The following examples show how to work with customer information in POS for Italy.</span></span>

### <a name="scenario-1-make-a-sale-to-an-anonymous-customer"></a><span data-ttu-id="b127c-163">Scenario 1: Effettuare una vendita a un cliente anonimo</span><span class="sxs-lookup"><span data-stu-id="b127c-163">Scenario 1: Make a sale to an anonymous customer</span></span>

1. <span data-ttu-id="b127c-164">Accedere a POS.</span><span class="sxs-lookup"><span data-stu-id="b127c-164">Sign in to POS.</span></span>
1. <span data-ttu-id="b127c-165">Aggiunge articoli al carrello.</span><span class="sxs-lookup"><span data-stu-id="b127c-165">Add items to the cart.</span></span>
1. <span data-ttu-id="b127c-166">Selezionare **Aggiungi informazioni cliente** e quindi selezionare **Immetti manualmente**.</span><span class="sxs-lookup"><span data-stu-id="b127c-166">Select **Add customer information**, and then select **Enter manually**.</span></span>
1. <span data-ttu-id="b127c-167">Immettere il codice fiscale del cliente e quindi selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="b127c-167">Enter the customer's fiscal code, and then select **OK**.</span></span>
1. <span data-ttu-id="b127c-168">Registrare i pagamenti per la transazione e quindi completare la transazione.</span><span class="sxs-lookup"><span data-stu-id="b127c-168">Register payments for the transaction, and then finalize the transaction.</span></span>
1. <span data-ttu-id="b127c-169">Verificare che la ricevuta stampata contenga il codice fiscale del cliente.</span><span class="sxs-lookup"><span data-stu-id="b127c-169">Verify that the printed receipt contains the customer's fiscal code.</span></span>

### <a name="scenario-2-make-a-sale-to-a-new-named-customer"></a><span data-ttu-id="b127c-170">Scenario 2: Effettuare una vendita a un nuovo cliente denominato</span><span class="sxs-lookup"><span data-stu-id="b127c-170">Scenario 2: Make a sale to a new named customer</span></span>

1. <span data-ttu-id="b127c-171">Accedere a POS.</span><span class="sxs-lookup"><span data-stu-id="b127c-171">Sign in to POS.</span></span>
1. <span data-ttu-id="b127c-172">Aggiunge articoli al carrello.</span><span class="sxs-lookup"><span data-stu-id="b127c-172">Add items to the cart.</span></span>
1. <span data-ttu-id="b127c-173">Selezionare **Aggiungi cliente** e quindi selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="b127c-173">Select **Add customer**, and then select **New**.</span></span>
1. <span data-ttu-id="b127c-174">Specificare gli attributi del nuovo cliente.</span><span class="sxs-lookup"><span data-stu-id="b127c-174">Specify the new customer's attributes.</span></span> <span data-ttu-id="b127c-175">Nel campo **Codice fiscale**, immettere il codice fiscale del cliente.</span><span class="sxs-lookup"><span data-stu-id="b127c-175">In the **Fiscal code** field, enter the customer's fiscal code.</span></span>
1. <span data-ttu-id="b127c-176">Salvare il record cliente e aggiungere il cliente alla transazione.</span><span class="sxs-lookup"><span data-stu-id="b127c-176">Save the customer record, and add the customer to the transaction.</span></span>
1. <span data-ttu-id="b127c-177">Registrare i pagamenti per la transazione e quindi completare la transazione.</span><span class="sxs-lookup"><span data-stu-id="b127c-177">Register payments for the transaction, and then finalize the transaction.</span></span>
1. <span data-ttu-id="b127c-178">Nella finestra di dialogo **Immettere informazioni cliente** selezionare **Sì**, quindi scegliere **Copia dal cliente della transazione**.</span><span class="sxs-lookup"><span data-stu-id="b127c-178">In the **Enter customer information** dialog box, select **Yes**, and then select **Copy from transaction customer**.</span></span>
1. <span data-ttu-id="b127c-179">Verificare il codice fiscale del cliente e quindi selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="b127c-179">Verify the customer's fiscal code, and then select **OK**.</span></span>
1. <span data-ttu-id="b127c-180">Verificare che la ricevuta stampata contenga il codice fiscale del cliente.</span><span class="sxs-lookup"><span data-stu-id="b127c-180">Verify that the printed receipt contains the customer's fiscal code.</span></span>

> [!NOTE]
> <span data-ttu-id="b127c-181">Se è necessario specificare un cliente diverso per la transazione, è necessario cancellare le informazioni sul cliente e copiarle nuovamente dopo aver aggiunto il nuovo cliente.</span><span class="sxs-lookup"><span data-stu-id="b127c-181">If you have to specify a different customer for the transaction, you must clear the customer information and then copy it again after the new customer is added.</span></span>

### <a name="scenario-3-change-the-customer-information-for-a-sale-to-a-named-customer"></a><span data-ttu-id="b127c-182">Scenario 3: Modificare le informazioni relative al cliente per una vendita su un cliente specifico</span><span class="sxs-lookup"><span data-stu-id="b127c-182">Scenario 3: Change the customer information for a sale to a named customer</span></span>

1. <span data-ttu-id="b127c-183">Accedere a POS.</span><span class="sxs-lookup"><span data-stu-id="b127c-183">Sign in to POS.</span></span>
1. <span data-ttu-id="b127c-184">Aggiunge articoli al carrello.</span><span class="sxs-lookup"><span data-stu-id="b127c-184">Add items to the cart.</span></span>
1. <span data-ttu-id="b127c-185">Selezionare **Aggiungi cliente** e quindi selezionare un account cliente per aggiungerlo alla transazione.</span><span class="sxs-lookup"><span data-stu-id="b127c-185">Select **Add customer**, and then select a customer account to add it to the transaction.</span></span>
1. <span data-ttu-id="b127c-186">Selezionare **Aggiungi informazioni cliente**, quindi selezionare **Copia dal cliente della transazione**.</span><span class="sxs-lookup"><span data-stu-id="b127c-186">Select **Add customer information**, and then select **Copy from transaction customer**.</span></span>
1. <span data-ttu-id="b127c-187">Verificare il codice fiscale del cliente e quindi selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="b127c-187">Verify the customer's fiscal code, and then select **OK**.</span></span>
1. <span data-ttu-id="b127c-188">Selezionare **Aggiungi informazioni cliente** e quindi selezionare **Cancella** per cancellare le informazioni relative al cliente dalla transazione.</span><span class="sxs-lookup"><span data-stu-id="b127c-188">Select **Add customer information**, and then select **Clear** to clear the customer information from the transaction.</span></span>
1. <span data-ttu-id="b127c-189">Selezionare **Aggiungi informazioni cliente** e quindi selezionare **Immetti manualmente**.</span><span class="sxs-lookup"><span data-stu-id="b127c-189">Select **Add customer information**, and then select **Enter Manually**.</span></span>
1. <span data-ttu-id="b127c-190">Specificare il codice fiscale del cliente e quindi selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="b127c-190">Specify the customer's fiscal code, and then select **OK**.</span></span>
1. <span data-ttu-id="b127c-191">Registrare i pagamenti per la transazione e quindi completare la transazione.</span><span class="sxs-lookup"><span data-stu-id="b127c-191">Register payments for the transaction, and then finalize the transaction.</span></span>
1. <span data-ttu-id="b127c-192">Verificare che la ricevuta stampata contenga il codice fiscale del cliente.</span><span class="sxs-lookup"><span data-stu-id="b127c-192">Verify that the printed receipt contains the customer's fiscal code.</span></span>

## <a name="deployment-guidelines"></a><span data-ttu-id="b127c-193">Linee guida per la distribuzione</span><span class="sxs-lookup"><span data-stu-id="b127c-193">Deployment guidelines</span></span>

<span data-ttu-id="b127c-194">In questa sezione vengono fornite le linee guida per la distribuzione per consentire la gestione delle informazioni sui clienti nella localizzazione di Dynamics 365 Retail per l'Italia.</span><span class="sxs-lookup"><span data-stu-id="b127c-194">This section provides deployment guidance for enabling customer information management in the localization of Dynamics 365 Retail for Italy.</span></span>

> [!NOTE]
> <span data-ttu-id="b127c-195">Alcuni passaggi in queste procedure variano in base alla versione di Retail in uso.</span><span class="sxs-lookup"><span data-stu-id="b127c-195">Some steps in these procedures vary, depending on the version of Retail that you're using.</span></span> <span data-ttu-id="b127c-196">Per ulteriori informazioni, vedere [Novità o modifiche in Dynamics 365 for Retail](../get-started/whats-new.md).</span><span class="sxs-lookup"><span data-stu-id="b127c-196">For more information, see [What's new or changed in Dynamics 365 for Retail](../get-started/whats-new.md).</span></span>
>
> <span data-ttu-id="b127c-197">Se si desidera abilitare l'integrazione del POS con le stampanti fiscali per l'Italia, e in particolare se si desidera stampare i codici fiscali dei clienti sulle ricevute fiscali, è necessario distribuire [l'esempio di integrazione di stampante fiscale per l'Italia](emea-ita-fpi-sample.md).</span><span class="sxs-lookup"><span data-stu-id="b127c-197">If you want to enable the integration of POS with fiscal printers for Italy, and specifically if you want to print customer fiscal codes on fiscal receipts, you must deploy the [fiscal printer integration sample for Italy](emea-ita-fpi-sample.md).</span></span>

### <a name="update-customizations"></a><span data-ttu-id="b127c-198">Aggiornare le personalizzazioni</span><span class="sxs-lookup"><span data-stu-id="b127c-198">Update customizations</span></span>

<span data-ttu-id="b127c-199">Seguire questi passaggi se una qualsiasi delle personalizzazioni include gestori di richieste per la richiesta SaveCartRequest o CreateSalesOrderServiceRequest.</span><span class="sxs-lookup"><span data-stu-id="b127c-199">Follow these steps if any of your customizations include request handlers for the SaveCartRequest or CreateSalesOrderServiceRequest request.</span></span>

1. <span data-ttu-id="b127c-200">Individuare il gestore per la richiesta **SaveCartRequest**.</span><span class="sxs-lookup"><span data-stu-id="b127c-200">Find the request handler for the **SaveCartRequest** request.</span></span>
1. <span data-ttu-id="b127c-201">Individuare la riga di codice che esegue il gestore originale.</span><span class="sxs-lookup"><span data-stu-id="b127c-201">Find the line of code that runs the original handler.</span></span>
1. <span data-ttu-id="b127c-202">Sostituire la classe del gestore originale con **TaxRegistrationIdFiscalCustomerService**.</span><span class="sxs-lookup"><span data-stu-id="b127c-202">Replace the original handler class with **TaxRegistrationIdFiscalCustomerService**.</span></span>

    ```cs
    using Microsoft.Dynamics.Commerce.Runtime.TaxRegistrationIdItaly.Services;

    ...

    var requestHandler = new TaxRegistrationIdFiscalCustomerService();
    var response = request.RequestContext.Runtime.Execute<SaveCartResponse>(request, request.RequestContext, requestHandler, skipRequestTriggers: false);
    ```

1. <span data-ttu-id="b127c-203">Ripetere i passaggi da 1 a 3 per la richiesta **CreateSalesOrderServiceRequest**.</span><span class="sxs-lookup"><span data-stu-id="b127c-203">Repeat steps 1 through 3 for the **CreateSalesOrderServiceRequest** request.</span></span>

### <a name="update-development-environment"></a><span data-ttu-id="b127c-204">Aggiornare l'ambiente di sviluppo</span><span class="sxs-lookup"><span data-stu-id="b127c-204">Update development environment</span></span>

<span data-ttu-id="b127c-205">Seguire questi passaggi per aggiornare un ambiente di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="b127c-205">Follow these steps to update a development environment.</span></span>

#### <a name="crt-extension-components"></a><span data-ttu-id="b127c-206">Componenti dell'estensione CRT</span><span class="sxs-lookup"><span data-stu-id="b127c-206">CRT extension components</span></span>

1. <span data-ttu-id="b127c-207">Individuare il file di configurazione dell'estensione per Commerce Runtime (CRT):</span><span class="sxs-lookup"><span data-stu-id="b127c-207">Find the extension configuration file for the Commerce runtime (CRT):</span></span>

    - <span data-ttu-id="b127c-208">**Server Retail:** Individuare il file **CommerceRuntime.Ext.config** nella cartella **bin\\ext** nella posizione del sito del server Microsoft Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="b127c-208">**Retail Server:** Find the **CommerceRuntime.Ext.config** file in the **bin\\ext** folder under the Microsoft Internet Information Services (IIS) Retail server site location.</span></span>
    - <span data-ttu-id="b127c-209">**CRT locale sul POS moderno:** Trovare il file **CommerceRuntime.MPOSOffline.Ext.config** nella posizione del broker client CRT locale.</span><span class="sxs-lookup"><span data-stu-id="b127c-209">**Local CRT on Modern POS:** Find the **CommerceRuntime.MPOSOffline.Ext.config** file under the local CRT client broker location.</span></span>

1. <span data-ttu-id="b127c-210">Registrare l'estensione CRT nel file di configurazione dell'estensione.</span><span class="sxs-lookup"><span data-stu-id="b127c-210">Register the CRT extension in the extension configuration file.</span></span>

    ``` xml
    <add source="assembly" value="Microsoft.Dynamics.Commerce.Runtime.TaxRegistrationIdItaly" />
    ```

    > [!WARNING]
    > <span data-ttu-id="b127c-211">**Non** modificare i file CommerceRuntime.MPOSOffline.config e CommerceRuntime.config.</span><span class="sxs-lookup"><span data-stu-id="b127c-211">Do **not** edit the CommerceRuntime.config and CommerceRuntime.MPOSOffline.config files.</span></span> <span data-ttu-id="b127c-212">Questi file non sono progettati per essere personalizzati.</span><span class="sxs-lookup"><span data-stu-id="b127c-212">These files aren't intended for any customizations.</span></span>

#### <a name="modern-pos-extension-components"></a><span data-ttu-id="b127c-213">Componenti dell'estensione POS moderno</span><span class="sxs-lookup"><span data-stu-id="b127c-213">Modern POS extension components</span></span>

<span data-ttu-id="b127c-214">Seguire questi passaggi per rendere disponibile l'estensione TaxRegistrationId.IT.</span><span class="sxs-lookup"><span data-stu-id="b127c-214">Follow these steps to make the TaxRegistrationId.IT extension available.</span></span>

1. <span data-ttu-id="b127c-215">Aprire la soluzione in **RetailSdk\\POS\\ModernPOS.sln**.</span><span class="sxs-lookup"><span data-stu-id="b127c-215">Open the solution at **RetailSdk\\POS\\ModernPOS.sln**.</span></span>
1. <span data-ttu-id="b127c-216">In **POS.Extensions\\extensions.json**, attivare l'estensione.</span><span class="sxs-lookup"><span data-stu-id="b127c-216">In **POS.Extensions\\extensions.json**, turn on the extension.</span></span>

    ``` json
    {
        "extensionPackages": [
            {
               "baseUrl": "Microsoft/TaxRegistrationId.IT"
            }
        ]
    }
    ```

1. <span data-ttu-id="b127c-217">Compilare la soluzione.</span><span class="sxs-lookup"><span data-stu-id="b127c-217">Build the solution.</span></span>
1. <span data-ttu-id="b127c-218">Aprire POS moderno e verificare la funzionalità.</span><span class="sxs-lookup"><span data-stu-id="b127c-218">Open Modern POS, and test the functionality.</span></span>

#### <a name="cloud-pos-extension-components"></a><span data-ttu-id="b127c-219">Componenti dell'estensione POS cloud</span><span class="sxs-lookup"><span data-stu-id="b127c-219">Cloud POS extension components</span></span>

<span data-ttu-id="b127c-220">Seguire questi passaggi per rendere disponibile l'estensione TaxRegistrationId.IT.</span><span class="sxs-lookup"><span data-stu-id="b127c-220">Follow these steps to make the TaxRegistrationId.IT extension available.</span></span>

1. <span data-ttu-id="b127c-221">Aprire la soluzione in **RetailSdk\\POS\\CloudPOS.sln**.</span><span class="sxs-lookup"><span data-stu-id="b127c-221">Open the solution at **RetailSdk\\POS\\CloudPOS.sln**.</span></span>
1. <span data-ttu-id="b127c-222">In **POS.Extensions\\extensions.json**, attivare l'estensione.</span><span class="sxs-lookup"><span data-stu-id="b127c-222">In **POS.Extensions\\extensions.json**, turn on the extension.</span></span>

    ``` json
    {
        "extensionPackages": [
            {
               "baseUrl": "Microsoft/TaxRegistrationId.IT"
            }
        ]
    }
    ```

1. <span data-ttu-id="b127c-223">Compilare la soluzione.</span><span class="sxs-lookup"><span data-stu-id="b127c-223">Build the solution.</span></span>
1. <span data-ttu-id="b127c-224">Aprire POS cloud e verificare la funzionalità.</span><span class="sxs-lookup"><span data-stu-id="b127c-224">Open Cloud POS, and test the functionality.</span></span>

### <a name="update-a-production-environment"></a><span data-ttu-id="b127c-225">Aggiornare un ambiente di produzione</span><span class="sxs-lookup"><span data-stu-id="b127c-225">Update a production environment</span></span>

<span data-ttu-id="b127c-226">Attenersi alla procedura seguente per creare pacchetti distribuibili contenenti componenti Retail e per applicare i pacchetti a un ambiente di produzione.</span><span class="sxs-lookup"><span data-stu-id="b127c-226">Follow these steps to create deployable packages that contain Retail components, and to apply the packages in a production environment.</span></span>

1. <span data-ttu-id="b127c-227">Nei file di configurazione **CommerceRuntime.Ext.config** e **CommerceRuntime.MPOSOffline.Ext.config** nella cartella **RetailSdk\\Assets**, aggiungere le seguenti righe alla sezione **composition**.</span><span class="sxs-lookup"><span data-stu-id="b127c-227">In the **CommerceRuntime.Ext.config** and **CommerceRuntime.MPOSOffline.Ext.config** configuration files under the **RetailSdk\\Assets** folder, add the following lines to the **composition** section.</span></span>

    ``` xml
    <add source="assembly" value="Microsoft.Dynamics.Commerce.Runtime.TaxRegistrationIdItaly" />
    ```

1. <span data-ttu-id="b127c-228">Attivare l'estensione POS **TaxRegistrationId.IT**.</span><span class="sxs-lookup"><span data-stu-id="b127c-228">Turn on the **TaxRegistrationId.IT** POS extension.</span></span>

    ``` json
    {
        "extensionPackages": [
            {
                "baseUrl": "Microsoft/TaxRegistrationId.IT"
            }
        ]
    }
    ```

1. <span data-ttu-id="b127c-229">Eseguire **msbuild** per l'intero Retail SDK per creare i pacchetti distribuibili.</span><span class="sxs-lookup"><span data-stu-id="b127c-229">Run **msbuild** for the whole Retail software development kit (SDK) to create deployable packages.</span></span>
1. <span data-ttu-id="b127c-230">Applicare i pacchetti via Microsoft Dynamics Lifecycle Services (LCS) o manualmente.</span><span class="sxs-lookup"><span data-stu-id="b127c-230">Apply the packages via Microsoft Dynamics Lifecycle Services (LCS) or manually.</span></span> <span data-ttu-id="b127c-231">Per ulteriori informazioni, vedere [Confezione di Retail SDK](../dev-itpro/retail-sdk/retail-sdk-packaging.md).</span><span class="sxs-lookup"><span data-stu-id="b127c-231">For more information, see [Retail SDK packaging](../dev-itpro/retail-sdk/retail-sdk-packaging.md).</span></span>
