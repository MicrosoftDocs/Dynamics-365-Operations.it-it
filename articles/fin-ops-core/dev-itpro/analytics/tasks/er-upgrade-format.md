---
title: ER Aggiornare il formato adottandone una nuova versione di base
description: In questo argomento viene illustrato come mantenere una configurazione di formato per la creazione di report elettronici (ER).
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERVendorPart, ERSolutionTable, ERSolutionCreateDropDialog, EROperationDesigner, ERComponentTypeDropDialog
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b76fb09ff961a3100b6a4bf890c1b12e6a0a2771
ms.sourcegitcommit: 5192cfaedfd861faea63d8954d7bcc500608a225
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2021
ms.locfileid: "5092568"
---
# <a name="er-upgrade-your-format-by-adopting-a-new-base-version-of-that-format"></a><span data-ttu-id="c8b06-103">ER Aggiornare il formato adottandone una nuova versione di base</span><span class="sxs-lookup"><span data-stu-id="c8b06-103">ER Upgrade your format by adopting a new, base version of that format</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="c8b06-104">I passaggi seguenti illustrano come un utente assegnato al ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può gestire una configurazione di formato per la creazione di report elettronici (ER).</span><span class="sxs-lookup"><span data-stu-id="c8b06-104">The following steps explain how a user in the System Administrator or Electronic Reporting Developer role can maintain an Electronic reporting (ER) format configuration.</span></span> <span data-ttu-id="c8b06-105">Questa procedura illustra come sia possibile creare una versione personalizzata di un formato in base al formato ricevuto da un provider di configurazione (CP).</span><span class="sxs-lookup"><span data-stu-id="c8b06-105">This procedure explains how a custom version of a format can be created based on the format received from a configuration provider (CP).</span></span> <span data-ttu-id="c8b06-106">Illustra anche come adottare una nuova versione di base di quel formato.</span><span class="sxs-lookup"><span data-stu-id="c8b06-106">It also explains how to adopt a new, base version of that format.</span></span>

<span data-ttu-id="c8b06-107">Per completare questi passaggi, è necessario completare i passaggi delle procedure "Creare un provider di configurazione e contrassegnarlo come attivo" e "Utilizzare il formato creato per generare documenti elettronici per i pagamenti".</span><span class="sxs-lookup"><span data-stu-id="c8b06-107">To complete these steps, you must first complete the steps in the "Create a configuration provider and mark it as active" and "Use created format to generate electronic documents for payments" procedures.</span></span> <span data-ttu-id="c8b06-108">Queste operazioni possono essere eseguite nella società GBSI.</span><span class="sxs-lookup"><span data-stu-id="c8b06-108">These steps can be performed in the GBSI company.</span></span>

## <a name="select-format-configuration-for-customization"></a><span data-ttu-id="c8b06-109">Selezionare la configurazione del formato per la personalizzazione</span><span class="sxs-lookup"><span data-stu-id="c8b06-109">Select format configuration for customization</span></span>
1. <span data-ttu-id="c8b06-110">Andare ad Amministrazione organizzazione > Aree di lavoro > Creazione di report elettronici.</span><span class="sxs-lookup"><span data-stu-id="c8b06-110">Go to Organization administration > Workspaces > Electronic reporting.</span></span>

    <span data-ttu-id="c8b06-111">In questo esempio, la società campione Litware, Inc. (https://www.litware.com) fungerà da provider di configurazione che supporta le configurazioni dei formati per i pagamenti elettronici di un paese specifico.</span><span class="sxs-lookup"><span data-stu-id="c8b06-111">In this example, sample company Litware, Inc. (https://www.litware.com) will act as a configuration provider that supports format configurations for electronic payments for a particular country.</span></span>    <span data-ttu-id="c8b06-112">La società campione Proseware, Inc. (http://www.proseware.com) fungerà da utente della configurazione del formato che Litware, Inc. ha fornito.</span><span class="sxs-lookup"><span data-stu-id="c8b06-112">Sample company Proseware, Inc. (http://www.proseware.com) will act as a consumer of the format configuration that Litware, Inc. provided.</span></span> <span data-ttu-id="c8b06-113">Proseware, Inc. utilizza formati in determinate aree del paese.</span><span class="sxs-lookup"><span data-stu-id="c8b06-113">Proseware, Inc. uses formats in certain regions of that country.</span></span>  
2. <span data-ttu-id="c8b06-114">Fare clic su Configurazioni report.</span><span class="sxs-lookup"><span data-stu-id="c8b06-114">Click Reporting configurations.</span></span>
3. <span data-ttu-id="c8b06-115">Fare clic su Mostra filtri.</span><span class="sxs-lookup"><span data-stu-id="c8b06-115">Click Show filters.</span></span>
4. <span data-ttu-id="c8b06-116">Applicare i filtri seguenti: immettere un valore di filtro "BACS (fittizio per il Regno Unito)" nel campo "Nome" utilizzando l'operatore di filtro "inizia con".</span><span class="sxs-lookup"><span data-stu-id="c8b06-116">Apply the following filters: Enter a filter value of "BACS (UK fictitious)" on the "Name" field using the "begins with" filter operator.</span></span>
  
    <span data-ttu-id="c8b06-117">La configurazione selezionata del formato BACS (fittizia per il Regno Unito) è posseduta dal provider Litware, Inc.</span><span class="sxs-lookup"><span data-stu-id="c8b06-117">The selected format configuration BACS (UK fictitious) is owned by provider Litware, Inc.</span></span>  

5. <span data-ttu-id="c8b06-118">Fare clic su Mostra filtri.</span><span class="sxs-lookup"><span data-stu-id="c8b06-118">Click Show filters.</span></span>
6. <span data-ttu-id="c8b06-119">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="c8b06-119">In the list, find and select the desired record.</span></span>

    <span data-ttu-id="c8b06-120">La versione del formato con stato Completato verrà utilizzata da Proseware, Inc. per la personalizzazione.</span><span class="sxs-lookup"><span data-stu-id="c8b06-120">The version of the format with the status of Completed will be used by Proseware, Inc. for customization.</span></span>  

## <a name="create-a-new-configuration-for-your-custom-format-of-electronic-document"></a><span data-ttu-id="c8b06-121">Creare una nuova configurazione per il formato personalizzato del documento elettronico</span><span class="sxs-lookup"><span data-stu-id="c8b06-121">Create a new configuration for your custom format of electronic document</span></span>
<span data-ttu-id="c8b06-122">Proseware, Inc. ha ricevuto la versione 1.1 della configurazione BACS (fittizia per il Regno Unito) contenente il formato iniziale per generare i documenti di pagamento elettronico da Litware, Inc. in conformità alla sottoscrizione del servizio effettuata.</span><span class="sxs-lookup"><span data-stu-id="c8b06-122">Proseware, Inc. received version 1.1 of BACS (UK fictitious) configuration that contains the initial format to generate electronic payment documents from Litware, Inc. in accordance to their service subscription.</span></span> <span data-ttu-id="c8b06-123">Proseware, Inc. desidera iniziare a usare questa come standard per il paese, ma è necessaria una certa personalizzazione per supportare i requisiti regionali specifici.</span><span class="sxs-lookup"><span data-stu-id="c8b06-123">Proseware, Inc. wants to start using this as a standard for their country but some customization is required to support specific regional requirements.</span></span> <span data-ttu-id="c8b06-124">Proseware, Inc. desidera anche mantenere la possibilità di aggiornare un formato personalizzato non appena viene fornito da Litware, Inc. e desidera eseguire questo aggiornamento al costo più basso.</span><span class="sxs-lookup"><span data-stu-id="c8b06-124">Proseware, Inc. also wants to keep the ability to upgrade a custom format as soon as a new version of it (with changes to support new country-specific requirements) comes from Litware, Inc. and they want to perform this upgrade with the lowest cost.</span></span>  

<span data-ttu-id="c8b06-125">A tale scopo, Proseware, Inc. deve creare una configurazione tramite la configurazione BACS (fittizia per il Regni Unito) di Litware, Inc.</span><span class="sxs-lookup"><span data-stu-id="c8b06-125">To do this, Proseware, Inc. needs to create a configuration using the Litware, Inc. configuration BACS (UK fictitious) as a base.</span></span>  

1. <span data-ttu-id="c8b06-126">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="c8b06-126">Close the page.</span></span>
2. <span data-ttu-id="c8b06-127">Selezionare Proseware, Inc. per renderlo un provider attivo.</span><span class="sxs-lookup"><span data-stu-id="c8b06-127">Select Proseware, Inc. to make it an active provider.</span></span>
3. <span data-ttu-id="c8b06-128">Fare clic su Imposta attivo.</span><span class="sxs-lookup"><span data-stu-id="c8b06-128">Click Set active.</span></span>
4. <span data-ttu-id="c8b06-129">Fare clic su Configurazioni report.</span><span class="sxs-lookup"><span data-stu-id="c8b06-129">Click Reporting configurations.</span></span>
5. <span data-ttu-id="c8b06-130">Nella struttura espandere "Pagamenti (modello semplificato)".</span><span class="sxs-lookup"><span data-stu-id="c8b06-130">In the tree, expand 'Payments (simplified model)'.</span></span>
6. <span data-ttu-id="c8b06-131">Nella struttura selezionare "Pagamenti (modello semplificato)\BACS (fittizia per Regno Unito)".</span><span class="sxs-lookup"><span data-stu-id="c8b06-131">In the tree, select 'Payments (simplified model)\BACS (UK fictitious)'.</span></span>

    <span data-ttu-id="c8b06-132">Selezionare la configurazione BACS (fittizia per il Regno Unito) da Litware, Inc. Proseware, inc utilizzerà la versione 1.1 come base per la versione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="c8b06-132">Select the BACS (UK fictitious) configuration from Litware, Inc. Proseware, Inc. will use version 1.1 as a base for the custom version.</span></span>  

7. <span data-ttu-id="c8b06-133">Fare clic su Crea configurazione per aprire la finestra di dialogo a discesa .</span><span class="sxs-lookup"><span data-stu-id="c8b06-133">Click Create configuration to open the drop dialog.</span></span>

    <span data-ttu-id="c8b06-134">Ciò consente di creare una nuova configurazione per un formato di pagamento personalizzato.</span><span class="sxs-lookup"><span data-stu-id="c8b06-134">This lets you create a new configuration for a custom payment format.</span></span>  

8. <span data-ttu-id="c8b06-135">Nel campo Nuovo immettere "Derivare da nome: BACS (fittizia per regno Unito), Litware, Inc.".</span><span class="sxs-lookup"><span data-stu-id="c8b06-135">In the New field, enter 'Derive from Name: BACS (UK fictitious), Litware, Inc.'.</span></span>

    <span data-ttu-id="c8b06-136">Selezionare l'opzione Deriva per confermare l'utilizzo di BACS (fittizia per il Regno Unito) come base per creare la versione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="c8b06-136">Select the Derive option to confirm the usage of BACS (UK fictitious) as the base for creating the custom version.</span></span>  

9. <span data-ttu-id="c8b06-137">Nel campo Nome digitare "BACS (personalizzata, fittizia per il Regno Unito)".</span><span class="sxs-lookup"><span data-stu-id="c8b06-137">In the Name field, type 'BACS (UK fictitious custom)'.</span></span>
10. <span data-ttu-id="c8b06-138">Nel campo Descrizione digitare 'Pagamento fornitore BACS (personalizzata, fittizia per il Regno Unito)'.</span><span class="sxs-lookup"><span data-stu-id="c8b06-138">In the Description field, type 'BACS vendor payment (UK fictitious custom)'.</span></span>

    <span data-ttu-id="c8b06-139">Il provider di configurazione attivo (Proseware, Inc.) viene inserito automaticamente in questo punto.</span><span class="sxs-lookup"><span data-stu-id="c8b06-139">The active configuration provider (Proseware, Inc.) is automatically entered here.</span></span> <span data-ttu-id="c8b06-140">Tale provider potrà gestire la configurazione.</span><span class="sxs-lookup"><span data-stu-id="c8b06-140">This provider will be able to maintain this configuration.</span></span> <span data-ttu-id="c8b06-141">Altri provider possono utilizzare la configurazione, ma non potranno gestirla.</span><span class="sxs-lookup"><span data-stu-id="c8b06-141">Other providers can use this configuration, but will not be able to maintain it.</span></span>  

11. <span data-ttu-id="c8b06-142">Fare clic su Crea configurazione.</span><span class="sxs-lookup"><span data-stu-id="c8b06-142">Click Create configuration.</span></span>

## <a name="customize-your-format-for-the-electronic-document"></a><span data-ttu-id="c8b06-143">Personalizzare il formato per il documento elettronico</span><span class="sxs-lookup"><span data-stu-id="c8b06-143">Customize your format for the electronic document</span></span>
1. <span data-ttu-id="c8b06-144">Fare clic su Progettazione.</span><span class="sxs-lookup"><span data-stu-id="c8b06-144">Click Designer.</span></span>
2. <span data-ttu-id="c8b06-145">Fare clic su Espandi/Comprimi.</span><span class="sxs-lookup"><span data-stu-id="c8b06-145">Click Expand/collapse.</span></span>
3. <span data-ttu-id="c8b06-146">Fare clic su Espandi/Comprimi.</span><span class="sxs-lookup"><span data-stu-id="c8b06-146">Click Expand/collapse.</span></span>
4. <span data-ttu-id="c8b06-147">Nella struttura selezionare 'Xml\Messaggio\Pagamenti\Articolo\Fornitore\Banca'.</span><span class="sxs-lookup"><span data-stu-id="c8b06-147">In the tree, select 'Xml\Message\Payments\Item\Vendor\Bank'.</span></span>
5. <span data-ttu-id="c8b06-148">Fare clic su Aggiungi per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="c8b06-148">Click Add to open the drop dialog.</span></span>
6. <span data-ttu-id="c8b06-149">Nella struttura selezionare "XML\Elemento".</span><span class="sxs-lookup"><span data-stu-id="c8b06-149">In the tree, select 'XML\Element'.</span></span>
7. <span data-ttu-id="c8b06-150">Nel campo nome digitare "IBAN".</span><span class="sxs-lookup"><span data-stu-id="c8b06-150">In the Name field, type 'IBAN'.</span></span>
8. <span data-ttu-id="c8b06-151">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="c8b06-151">Click OK.</span></span>
9. <span data-ttu-id="c8b06-152">Nella struttura selezionare 'Xml\Messaggio\Pagamenti\Articolo\Fornitore\Banca\IBAN'.</span><span class="sxs-lookup"><span data-stu-id="c8b06-152">In the tree, select 'Xml\Message\Payments\Item\Vendor\Bank\IBAN'.</span></span>
10. <span data-ttu-id="c8b06-153">Fare clic su Aggiungi per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="c8b06-153">Click Add to open the drop dialog.</span></span>
11. <span data-ttu-id="c8b06-154">Nella struttura selezionare "Testo\Stringa".</span><span class="sxs-lookup"><span data-stu-id="c8b06-154">In the tree, select 'Text\String'.</span></span>
12. <span data-ttu-id="c8b06-155">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="c8b06-155">Click OK.</span></span>
13. <span data-ttu-id="c8b06-156">Nella struttura selezionare 'Xml\Messaggio\Pagamenti\Articolo\Fornitore\Nome\Stringa'.</span><span class="sxs-lookup"><span data-stu-id="c8b06-156">In the tree, select 'Xml\Message\Payments\Item\Vendor\Name\String'.</span></span>
14. <span data-ttu-id="c8b06-157">Nel campo Lunghezza massima immettere "60".</span><span class="sxs-lookup"><span data-stu-id="c8b06-157">In the Maximum length field, enter '60'.</span></span>
15. <span data-ttu-id="c8b06-158">Fare clic sulla scheda Mapping.</span><span class="sxs-lookup"><span data-stu-id="c8b06-158">Click the Mapping tab.</span></span>
16. <span data-ttu-id="c8b06-159">Nella struttura , espandere il "modello".</span><span class="sxs-lookup"><span data-stu-id="c8b06-159">In the tree, expand 'model'.</span></span>
17. <span data-ttu-id="c8b06-160">Nella struttura espandere "modello\Pagamenti".</span><span class="sxs-lookup"><span data-stu-id="c8b06-160">In the tree, expand 'model\Payments'.</span></span>
18. <span data-ttu-id="c8b06-161">Nella struttura espandere "modello\Pagamenti\Creditore".</span><span class="sxs-lookup"><span data-stu-id="c8b06-161">In the tree, expand 'model\Payments\Creditor'.</span></span>
19. <span data-ttu-id="c8b06-162">Nella struttura espandere "modello\Pagamenti\Creditore\Conto".</span><span class="sxs-lookup"><span data-stu-id="c8b06-162">In the tree, expand 'model\Payments\Creditor\Account'.</span></span>
20. <span data-ttu-id="c8b06-163">Nella struttura selezionare 'modello\Pagamenti\Creditore\Conto\IBAN'.</span><span class="sxs-lookup"><span data-stu-id="c8b06-163">In the tree, select 'model\Payments\Creditor\Account\IBAN'.</span></span>
21. <span data-ttu-id="c8b06-164">Nella struttura selezionare 'Xml\Messaggio\Pagamenti\Articolo = model.Payments\Fornitore\Banca\IBAN\Stringa'.</span><span class="sxs-lookup"><span data-stu-id="c8b06-164">In the tree, select 'Xml\Message\Payments\Item =  model.Payments\Vendor\Bank\IBAN\String'.</span></span>
22. <span data-ttu-id="c8b06-165">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="c8b06-165">Click Bind.</span></span>
23. <span data-ttu-id="c8b06-166">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="c8b06-166">Click Save.</span></span>

## <a name="validate-the-customized-format"></a><span data-ttu-id="c8b06-167">Convalidare il formato personalizzato</span><span class="sxs-lookup"><span data-stu-id="c8b06-167">Validate the customized format</span></span>
1. <span data-ttu-id="c8b06-168">Fare clic su Convalida.</span><span class="sxs-lookup"><span data-stu-id="c8b06-168">Click Validate.</span></span>

    <span data-ttu-id="c8b06-169">Convalidare le modifiche personalizzate del layout del formato e del mapping dei dati per assicurarsi che tutte le associazioni siano giuste.</span><span class="sxs-lookup"><span data-stu-id="c8b06-169">Validate the customized format layout and data mapping changes to make sure that all bindings are okay.</span></span>  

2. <span data-ttu-id="c8b06-170">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="c8b06-170">Close the page.</span></span>

## <a name="change-the-status-of-the-current-version-of-the-custom-format-configuration"></a><span data-ttu-id="c8b06-171">Modificare lo stato della versione corrente della configurazione del formato personalizzato</span><span class="sxs-lookup"><span data-stu-id="c8b06-171">Change the status of the current version of the custom format configuration</span></span>
<span data-ttu-id="c8b06-172">Modificare lo stato della configurazione designata del formato da Bozza a Completato per renderla disponibile per la generazione del documento di pagamento.</span><span class="sxs-lookup"><span data-stu-id="c8b06-172">Change the status of the designed format configuration from Draft to Completed to make it available for payment document generation.</span></span>  

1. <span data-ttu-id="c8b06-173">Fare clic su Cambia stato.</span><span class="sxs-lookup"><span data-stu-id="c8b06-173">Click Change status.</span></span>

    <span data-ttu-id="c8b06-174">La versione corrente della configurazione selezionata è nello stato Bozza.</span><span class="sxs-lookup"><span data-stu-id="c8b06-174">Note that the current version of the selected configuration is in Draft status.</span></span>  

2. <span data-ttu-id="c8b06-175">Fare clic su Completa.</span><span class="sxs-lookup"><span data-stu-id="c8b06-175">Click Complete.</span></span>
3. <span data-ttu-id="c8b06-176">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="c8b06-176">In the Description field, type a value.</span></span>
4. <span data-ttu-id="c8b06-177">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="c8b06-177">Click OK.</span></span>
5. <span data-ttu-id="c8b06-178">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="c8b06-178">In the list, find and select the desired record.</span></span>

    <span data-ttu-id="c8b06-179">Si noti che la configurazione creata viene salvata come versione completata 1.1.1.</span><span class="sxs-lookup"><span data-stu-id="c8b06-179">Note that the created configuration is saved as completed version 1.1.1.</span></span> <span data-ttu-id="c8b06-180">Ciò significa che è la versione 1 del formato BACS personalizzato (personalizzata, fittizia per il Regno Unito), basato sulla versione 1 del formato BACS (fittizia per il Regno Unito), che si basa sulla versione 1 del modello dati Pagamenti (modello semplificato).</span><span class="sxs-lookup"><span data-stu-id="c8b06-180">This means it is version 1 of the custom BACS (UK fictitious custom) format, which is based on version 1 of the BACS (UK fictitious) format, which is based on version 1 of the Payments (simplified model) data model.</span></span>  

## <a name="test-the-customized-format-to-generate-payment-files"></a><span data-ttu-id="c8b06-181">Testare il formato personalizzato per generare file di pagamento</span><span class="sxs-lookup"><span data-stu-id="c8b06-181">Test the customized format to generate payment files</span></span>
<span data-ttu-id="c8b06-182">Completare i passaggi della procedura "Utilizzare il formato creato per generare documenti elettronici per i pagamenti" in una sessione parallela di Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="c8b06-182">Complete the steps in the "Use created format to generate electronic documents for payments" procedure in a parallel Finance and Operations session.</span></span> <span data-ttu-id="c8b06-183">Selezionare il formato BACS (personalizzata, fittizia per il Regno Unito) nei parametri del metodo di pagamento elettronico.</span><span class="sxs-lookup"><span data-stu-id="c8b06-183">Select the BACS (UK fictitious custom) format in electronic payment method parameters.</span></span> <span data-ttu-id="c8b06-184">Verificare che il file di pagamento creato contenga il nodo XML introdotto di recente che presenta il codice di IBAN in conformità ai requisiti regionali.</span><span class="sxs-lookup"><span data-stu-id="c8b06-184">Make sure that the created payment file contains the recently introduced XML node presenting IBAN code in accordance to regional requirements.</span></span>  

## <a name="update-the-existing-country-specific-configuration"></a><span data-ttu-id="c8b06-185">Aggiornare la configurazione specifica di ciascun paese esistente</span><span class="sxs-lookup"><span data-stu-id="c8b06-185">Update the existing country-specific configuration</span></span>
<span data-ttu-id="c8b06-186">Litware, Inc. deve aggiornare la configurazione BACS (fittizia per il Regno Unito) e adottare nuovi requisiti per il paese per gestire il formato del documento elettronico.</span><span class="sxs-lookup"><span data-stu-id="c8b06-186">Litware, Inc. needs to update the BACS (UK fictitious) configuration and adopt new country requirements for managing the format of the electronic document.</span></span> <span data-ttu-id="c8b06-187">Successivamente, questo verrà accluso in una nuova versione della configurazione che verrà offerta per gli iscritti al servizio, inclusa Proseware, Inc.</span><span class="sxs-lookup"><span data-stu-id="c8b06-187">Later, this will be enclosed in a new version of this configuration that will be offered for service subscribers, including Proseware, Inc.</span></span>  

<span data-ttu-id="c8b06-188">Nei processi reali correlati all'erogazione del servizio ogni nuova versione di BACS (fittizia per il Regno Unito) può essere importata da Proseware, Inc. dall'archivio LCS delle configurazioni di Litware, Inc.</span><span class="sxs-lookup"><span data-stu-id="c8b06-188">In real service provision related processes, each new version of BACS (UK fictitious) can be imported by Proseware, Inc. from Litware, Inc. configurations' LCS repository.</span></span> <span data-ttu-id="c8b06-189">In questa procedura simuleremo questo processo aggiornando BACS (fittizia per il Regno Unito) per conto di un provider di servizi.</span><span class="sxs-lookup"><span data-stu-id="c8b06-189">In this procedure we will simulate this by updating BACS (UK fictitious) on behalf of a service provider.</span></span>  

1. <span data-ttu-id="c8b06-190">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="c8b06-190">Close the page.</span></span>
2. <span data-ttu-id="c8b06-191">Selezionare Litware, Inc. .</span><span class="sxs-lookup"><span data-stu-id="c8b06-191">Select Litware, inc. provider.</span></span>
3. <span data-ttu-id="c8b06-192">Fare clic su Imposta attivo.</span><span class="sxs-lookup"><span data-stu-id="c8b06-192">Click Set active.</span></span>
4. <span data-ttu-id="c8b06-193">Fare clic su Configurazioni report.</span><span class="sxs-lookup"><span data-stu-id="c8b06-193">Click Reporting configurations.</span></span>
5. <span data-ttu-id="c8b06-194">Nella struttura espandere "Pagamenti (modello semplificato)".</span><span class="sxs-lookup"><span data-stu-id="c8b06-194">In the tree, expand 'Payments (simplified model)'.</span></span>
6. <span data-ttu-id="c8b06-195">Nella struttura selezionare "Pagamenti (modello semplificato)\BACS (fittizia per Regno Unito)".</span><span class="sxs-lookup"><span data-stu-id="c8b06-195">In the tree, select 'Payments (simplified model)\BACS (UK fictitious)'.</span></span>

    <span data-ttu-id="c8b06-196">La versione bozza di proprietà del BACS (fittizia per il Regno Unito) del provider Litware, Inc. viene selezionata per apportare modifiche per supportare i nuovi requisiti specifici di ciascun paese.</span><span class="sxs-lookup"><span data-stu-id="c8b06-196">The draft version owned by Litware, Inc. provider BACS (UK fictitious) is selected to bring in changes to support new country-specific requirements.</span></span>  

## <a name="localize-the-base-format-of-the-electronic-document"></a><span data-ttu-id="c8b06-197">Localizzare il formato di base del documento elettronico</span><span class="sxs-lookup"><span data-stu-id="c8b06-197">Localize the base format of the electronic document</span></span>
<span data-ttu-id="c8b06-198">Si supponga che siano presenti nuovi requisiti specifici del paese che Litware, Inc. deve supportare:</span><span class="sxs-lookup"><span data-stu-id="c8b06-198">Assume that there are new country-specific requirements to be supported by Litware, Inc.:</span></span>  

- <span data-ttu-id="c8b06-199">Un valore per il codice SWIFT della banca del creditore in ogni transazione di pagamento.</span><span class="sxs-lookup"><span data-stu-id="c8b06-199">A value for the creditor's bank SWIFT code in each payment transaction.</span></span>
- <span data-ttu-id="c8b06-200">Un limite di 100 caratteri per la lunghezza del testo per il nome del fornitore in un file di creazione.</span><span class="sxs-lookup"><span data-stu-id="c8b06-200">A limit of 100 characters for the length of text for the vendor's name in a generating file.</span></span>  
- <span data-ttu-id="c8b06-201">Nuovi requisiti specifici del paese</span><span class="sxs-lookup"><span data-stu-id="c8b06-201">New country-specific requirements</span></span>  
- <span data-ttu-id="c8b06-202">Selezionare la versione bozza della configurazione desiderata per introdurre le modifiche necessarie.</span><span class="sxs-lookup"><span data-stu-id="c8b06-202">Select the draft version of the desired configuration to introduce required changes.</span></span>  


1. <span data-ttu-id="c8b06-203">Fare clic su Progettazione.</span><span class="sxs-lookup"><span data-stu-id="c8b06-203">Click Designer.</span></span>
2. <span data-ttu-id="c8b06-204">Fare clic su Espandi/Comprimi.</span><span class="sxs-lookup"><span data-stu-id="c8b06-204">Click Expand/collapse.</span></span>
3. <span data-ttu-id="c8b06-205">Fare clic su Espandi/Comprimi.</span><span class="sxs-lookup"><span data-stu-id="c8b06-205">Click Expand/collapse.</span></span>
4. <span data-ttu-id="c8b06-206">Nella struttura selezionare 'Xml\Messaggio\Pagamenti\Articolo\Fornitore\Banca'.</span><span class="sxs-lookup"><span data-stu-id="c8b06-206">In the tree, select 'Xml\Message\Payments\Item\Vendor\Bank'.</span></span>
5. <span data-ttu-id="c8b06-207">Fare clic su Aggiungi per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="c8b06-207">Click Add to open the drop dialog.</span></span>
6. <span data-ttu-id="c8b06-208">Nella struttura selezionare "XML\Elemento".</span><span class="sxs-lookup"><span data-stu-id="c8b06-208">In the tree, select 'XML\Element'.</span></span>
7. <span data-ttu-id="c8b06-209">Nel campo Nome digitare "SWIFT".</span><span class="sxs-lookup"><span data-stu-id="c8b06-209">In the Name field, type 'SWIFT'.</span></span>
8. <span data-ttu-id="c8b06-210">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="c8b06-210">Click OK.</span></span>
9. <span data-ttu-id="c8b06-211">Nella struttura selezionare 'Xml\Messaggio\Pagamenti\Articolo\Fornitore\Banca\SWIFT'.</span><span class="sxs-lookup"><span data-stu-id="c8b06-211">In the tree, select 'Xml\Message\Payments\Item\Vendor\Bank\SWIFT'.</span></span>
10. <span data-ttu-id="c8b06-212">Fare clic su Aggiungi per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="c8b06-212">Click Add to open the drop dialog.</span></span>
11. <span data-ttu-id="c8b06-213">Nella struttura selezionare "Testo\Stringa".</span><span class="sxs-lookup"><span data-stu-id="c8b06-213">In the tree, select 'Text\String'.</span></span>
12. <span data-ttu-id="c8b06-214">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="c8b06-214">Click OK.</span></span>
13. <span data-ttu-id="c8b06-215">Nella struttura selezionare 'Xml\Messaggio\Pagamenti\Articolo\Fornitore\Nome\Stringa'.</span><span class="sxs-lookup"><span data-stu-id="c8b06-215">In the tree, select 'Xml\Message\Payments\Item\Vendor\Name\String'.</span></span>
14. <span data-ttu-id="c8b06-216">Nel campo Lunghezza massima immettere "100".</span><span class="sxs-lookup"><span data-stu-id="c8b06-216">In the Maximum length field, enter '100'.</span></span>
15. <span data-ttu-id="c8b06-217">Fare clic sulla scheda Mapping.</span><span class="sxs-lookup"><span data-stu-id="c8b06-217">Click the Mapping tab.</span></span>
16. <span data-ttu-id="c8b06-218">Nella struttura , espandere il "modello".</span><span class="sxs-lookup"><span data-stu-id="c8b06-218">In the tree, expand 'model'.</span></span>
17. <span data-ttu-id="c8b06-219">Nella struttura espandere "modello\Pagamenti".</span><span class="sxs-lookup"><span data-stu-id="c8b06-219">In the tree, expand 'model\Payments'.</span></span>
18. <span data-ttu-id="c8b06-220">Nella struttura espandere "modello\Pagamenti\Creditore".</span><span class="sxs-lookup"><span data-stu-id="c8b06-220">In the tree, expand 'model\Payments\Creditor'.</span></span>
19. <span data-ttu-id="c8b06-221">Nella struttura espandere "modello\Pagamenti\Creditore\Agente".</span><span class="sxs-lookup"><span data-stu-id="c8b06-221">In the tree, expand 'model\Payments\Creditor\Agent'.</span></span>
20. <span data-ttu-id="c8b06-222">Nella struttura selezionare 'modello\Pagamenti\Creditore\Agente\SWIFT'.</span><span class="sxs-lookup"><span data-stu-id="c8b06-222">In the tree, select 'model\Payments\Creditor\Agent\SWIFT'.</span></span>
21. <span data-ttu-id="c8b06-223">Nella struttura selezionare 'Xml\Messaggio\Pagamenti\Articolo = model.Payments\Fornitore\Banca\SWIFT\Stringa'.</span><span class="sxs-lookup"><span data-stu-id="c8b06-223">In the tree, select 'Xml\Message\Payments\Item =  model.Payments\Vendor\Bank\SWIFT\String'.</span></span>
22. <span data-ttu-id="c8b06-224">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="c8b06-224">Click Bind.</span></span>
23. <span data-ttu-id="c8b06-225">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="c8b06-225">Click Save.</span></span>

## <a name="validate-the-localized-format"></a><span data-ttu-id="c8b06-226">Convalidare il formato localizzato</span><span class="sxs-lookup"><span data-stu-id="c8b06-226">Validate the localized format</span></span>
1. <span data-ttu-id="c8b06-227">Fare clic su Convalida.</span><span class="sxs-lookup"><span data-stu-id="c8b06-227">Click Validate.</span></span>
2. <span data-ttu-id="c8b06-228">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="c8b06-228">Close the page.</span></span>

## <a name="change-the-status-of-the-current-version-of-the-base-format-configuration"></a><span data-ttu-id="c8b06-229">Modificare lo stato della versione corrente della configurazione del formato di base</span><span class="sxs-lookup"><span data-stu-id="c8b06-229">Change the status of the current version of the base format configuration</span></span>
<span data-ttu-id="c8b06-230">Modificare lo stato della configurazione aggiornata del formato di base da Bozza a Completato per renderla disponibile per la creazione di documenti di pagamento e di aggiornamenti delle configurazioni del formato che ne derivano.</span><span class="sxs-lookup"><span data-stu-id="c8b06-230">Change the status of the updated base format configuration from Draft to Completed to make it available for generation of payment documents and updates of format configurations derived from it.</span></span>  

1. <span data-ttu-id="c8b06-231">Fare clic su Cambia stato.</span><span class="sxs-lookup"><span data-stu-id="c8b06-231">Click Change status.</span></span>

    <span data-ttu-id="c8b06-232">La versione corrente della configurazione selezionata è nello stato Bozza.</span><span class="sxs-lookup"><span data-stu-id="c8b06-232">Note that the current version of the selected configuration is in Draft status.</span></span>  

2. <span data-ttu-id="c8b06-233">Fare clic su Completa.</span><span class="sxs-lookup"><span data-stu-id="c8b06-233">Click Complete.</span></span>
3. <span data-ttu-id="c8b06-234">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="c8b06-234">In the Description field, type a value.</span></span>
4. <span data-ttu-id="c8b06-235">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="c8b06-235">Click OK.</span></span>
5. <span data-ttu-id="c8b06-236">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="c8b06-236">In the list, find and select the desired record.</span></span>

## <a name="change-the-base-version-for-the-custom-format-configuration"></a><span data-ttu-id="c8b06-237">Cambiare la versione di base per la configurazione del formato personalizzato</span><span class="sxs-lookup"><span data-stu-id="c8b06-237">Change the base version for the custom format configuration</span></span>

<span data-ttu-id="c8b06-238">Proseware, Inc. è informata che una nuova versione 1.2 della configurazione BACS (fittizia per il Regno Unito) è disponibile per generare documenti di pagamento elettronici in conformità ai requisiti specifici del paese annunciati di recente.</span><span class="sxs-lookup"><span data-stu-id="c8b06-238">Proseware, Inc. is informed that a new version 1.2 of BACS (UK fictitious) configuration is available to generate electronic payment documents in accordance to recently announced country-specific requirements.</span></span> <span data-ttu-id="c8b06-239">Proseware, Inc. desidera iniziare a usarla come standard per il paese.</span><span class="sxs-lookup"><span data-stu-id="c8b06-239">Proseware, Inc. wants to start using it as a standard for the country.</span></span>  

<span data-ttu-id="c8b06-240">A questo scopo, Proseware, Inc. deve modificare la versione della configurazione di base con la configurazione personalizzata BACS (personalizzata fittizia per il Regno Unito).</span><span class="sxs-lookup"><span data-stu-id="c8b06-240">To do this, Proseware, Inc. needs to change the base configuration version for the custom configuration BACS (UK fictitious custom).</span></span> <span data-ttu-id="c8b06-241">Anziché la versione 1.1 della BACS (fittizia per il Regno Unito), usare la nuova versione 1.2.</span><span class="sxs-lookup"><span data-stu-id="c8b06-241">Instead of version 1.1 of BACS (UK fictitious) use new version 1.2.</span></span>  

1. <span data-ttu-id="c8b06-242">Andare ad Amministrazione organizzazione > Aree di lavoro > Creazione di report elettronici.</span><span class="sxs-lookup"><span data-stu-id="c8b06-242">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="c8b06-243">Selezionare il provider Proseware, Inc. per renderlo un provider attivo.</span><span class="sxs-lookup"><span data-stu-id="c8b06-243">Select the Proseware, Inc. provider to mark it as active.</span></span>
3. <span data-ttu-id="c8b06-244">Fare clic su Imposta attivo.</span><span class="sxs-lookup"><span data-stu-id="c8b06-244">Click Set active.</span></span>
4. <span data-ttu-id="c8b06-245">Fare clic su Configurazioni report.</span><span class="sxs-lookup"><span data-stu-id="c8b06-245">Click Reporting configurations.</span></span>
5. <span data-ttu-id="c8b06-246">Nella struttura espandere "Pagamenti (modello semplificato)".</span><span class="sxs-lookup"><span data-stu-id="c8b06-246">In the tree, expand 'Payments (simplified model)'.</span></span>
6. <span data-ttu-id="c8b06-247">Nella struttura espandere "Pagamenti (modello semplificato)\BACS (fittizia per Regno Unito)".</span><span class="sxs-lookup"><span data-stu-id="c8b06-247">In the tree, expand 'Payments (simplified model)\BACS (UK fictitious)'.</span></span>
7. <span data-ttu-id="c8b06-248">Nella struttura selezionare "Pagamenti (modello semplificato)\BACS (fittizia per Regno Unito)\BACS (personalizzata, fittizia per Regno Unito)".</span><span class="sxs-lookup"><span data-stu-id="c8b06-248">In the tree, select 'Payments (simplified model)\BACS (UK fictitious)\BACS (UK fictitious custom)'.</span></span>

    <span data-ttu-id="c8b06-249">Selezionare la configurazione BACS (personalizzata, fittizia per il Regno Unito), posseduta da Proseware, Inc.</span><span class="sxs-lookup"><span data-stu-id="c8b06-249">Select the BACS (UK fictitious custom) configuration, which is owned by Proseware, Inc.</span></span>  

    <span data-ttu-id="c8b06-250">Utilizzare la versione bozza della configurazione selezionata per introdurre le modifiche necessarie.</span><span class="sxs-lookup"><span data-stu-id="c8b06-250">Use the draft version of the selected configuration to introduce required changes.</span></span>  

8. <span data-ttu-id="c8b06-251">Fare clic su Riassegna.</span><span class="sxs-lookup"><span data-stu-id="c8b06-251">Click Rebase.</span></span>

    <span data-ttu-id="c8b06-252">Selezionare la nuova versione 1.2 della configurazione di base che dovrà essere applicata come nuova base per aggiornare la configurazione.</span><span class="sxs-lookup"><span data-stu-id="c8b06-252">Select the new version 1.2 of the base configuration to be applied as a new base for updating the configuration.</span></span>  

9. <span data-ttu-id="c8b06-253">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="c8b06-253">Click OK.</span></span>

    <span data-ttu-id="c8b06-254">Alcuni conflitti sono stati individuati nella fusione della versione personalizzata e della nuova versione di base che rappresentano modifiche di formato che non possono essere unite automaticamente.</span><span class="sxs-lookup"><span data-stu-id="c8b06-254">Note that some conflicts have been discovered between merging the custom version and a new base version representing some format changes that can't be merged automatically.</span></span>  

## <a name="resolve-rebase-conflicts"></a><span data-ttu-id="c8b06-255">Risolvere conflitti di riassegnazione</span><span class="sxs-lookup"><span data-stu-id="c8b06-255">Resolve rebase conflicts</span></span>
1. <span data-ttu-id="c8b06-256">Fare clic su Progettazione.</span><span class="sxs-lookup"><span data-stu-id="c8b06-256">Click Designer.</span></span>
    
    <span data-ttu-id="c8b06-257">Le modifiche al limite di lunghezza del testo del nome del fornitore non possono essere risolte automaticamente.</span><span class="sxs-lookup"><span data-stu-id="c8b06-257">Note that changes to the vendor's name text length limit couldn't be resolved automatically.</span></span> <span data-ttu-id="c8b06-258">Di conseguenza, questo viene presentato in un elenco di conflitti.</span><span class="sxs-lookup"><span data-stu-id="c8b06-258">Therefore, this is presented in a conflicts list.</span></span> <span data-ttu-id="c8b06-259">Per ogni conflitto di tipo aggiornamento sono disponibili le seguenti opzioni: Applica valori di base precedenti (pulsante in alto nella griglia) per introdurre il valore di base della versione precedente (0 nel nostro caso).</span><span class="sxs-lookup"><span data-stu-id="c8b06-259">For each conflict of type Update, the following options are available:  - Apply a prior base value (button on top of the grid) to bring in the previous base version value (0 in our case).</span></span>  <span data-ttu-id="c8b06-260">- Applica un valore di base (pulsante in alto nella griglia) per introdurre il nuovo valore di base della versione (100 nel nostro caso).</span><span class="sxs-lookup"><span data-stu-id="c8b06-260">- Apply a base value (button on top of the grid) to bring in the new base version value (100 in our case).</span></span>  <span data-ttu-id="c8b06-261">- Mantiene il proprio valore personalizzato (60 nel nostro caso).</span><span class="sxs-lookup"><span data-stu-id="c8b06-261">- Keep your own (custom) value (60 in our case).</span></span>  <span data-ttu-id="c8b06-262">Fare clic su Applica valori di base per applicare un limite specifico per paese di 100 caratteri per la lunghezza del testo del nome del fornitore.</span><span class="sxs-lookup"><span data-stu-id="c8b06-262">Click Apply base value to apply a country-specific limit of 100 characters for vendor's name text length.</span></span>  

    <span data-ttu-id="c8b06-263">Proseware, Inc. e Litware, Inc. hanno versioni locali e personalizzate di questo formato utilizzando i codici SWIFT e IBAN con i relativi componenti che vengono automaticamente unite nel formato di gestione.</span><span class="sxs-lookup"><span data-stu-id="c8b06-263">Note that Proseware, Inc. and Litware, Inc. have custom and local versions of this format using IBAN and SWIFT codes with related components that are automatically merged in the managing format.</span></span>  

2. <span data-ttu-id="c8b06-264">Fare clic su Applica valori di base.</span><span class="sxs-lookup"><span data-stu-id="c8b06-264">Click Apply base value.</span></span>

    <span data-ttu-id="c8b06-265">Fare clic su Applica valori di base per applicare il limite specifico per paese di 100 caratteri per i nomi dei fornitori.</span><span class="sxs-lookup"><span data-stu-id="c8b06-265">Click Apply base value to apply the country-specific limit of 100 characters for vendor names.</span></span>  

3. <span data-ttu-id="c8b06-266">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="c8b06-266">Click Save.</span></span>

    <span data-ttu-id="c8b06-267">Il salvataggio del formato rimuoverà i conflitti risolti dall'elenco dei conflitti.</span><span class="sxs-lookup"><span data-stu-id="c8b06-267">Saving the format will remove resolved conflicts from the conflicts list.</span></span>  

4. <span data-ttu-id="c8b06-268">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="c8b06-268">Close the page.</span></span>

## <a name="change-the-status-of-the-new-version-of-the-custom-format-configuration"></a><span data-ttu-id="c8b06-269">Modificare lo stato della versione nuova della configurazione del formato personalizzato</span><span class="sxs-lookup"><span data-stu-id="c8b06-269">Change the status of the new version of the custom format configuration</span></span>
1. <span data-ttu-id="c8b06-270">Fare clic su Cambia stato.</span><span class="sxs-lookup"><span data-stu-id="c8b06-270">Click Change status.</span></span>

    <span data-ttu-id="c8b06-271">Modificare lo stato della configurazione aggiornata e personalizzata del formato da Bozza a Completato.</span><span class="sxs-lookup"><span data-stu-id="c8b06-271">Change the status of the updated, custom format configuration from Draft to Completed.</span></span> <span data-ttu-id="c8b06-272">Questo renderà disponibile la configurazione del formato per la generazione dei documenti di pagamento.</span><span class="sxs-lookup"><span data-stu-id="c8b06-272">This will make the format configuration available for generating payment documents.</span></span> <span data-ttu-id="c8b06-273">La versione corrente della configurazione selezionata è nello stato Bozza.</span><span class="sxs-lookup"><span data-stu-id="c8b06-273">Note that the current version of the selected configuration is in Draft status.</span></span>  

2. <span data-ttu-id="c8b06-274">Fare clic su Completa.</span><span class="sxs-lookup"><span data-stu-id="c8b06-274">Click Complete.</span></span>
3. <span data-ttu-id="c8b06-275">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="c8b06-275">In the Description field, type a value.</span></span>
4. <span data-ttu-id="c8b06-276">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="c8b06-276">Click OK.</span></span>

    <span data-ttu-id="c8b06-277">La configurazione creata viene salvata come versione 1.2.2 completata: versione 2 del formato di base BACS (personalizzata, fittizia per il Regno Unito), basata sulla versione 2 del formato di base BACS (fittizia per il Regno Unito), basato sulla versione 1 del modello dati Pagamenti (modello semplificato).</span><span class="sxs-lookup"><span data-stu-id="c8b06-277">Note that the created configuration is saved as completed version 1.2.2: version 2 of base BACS (UK fictitious custom) format, which is based on version 2 of base BACS (UK fictitious) format, which is based on version 1 of Payments (simplified model) data model.</span></span>  

## <a name="test-the-customized-format-for-payment-files-generation"></a><span data-ttu-id="c8b06-278">Testare il formato personalizzato per la generazione di file di pagamento</span><span class="sxs-lookup"><span data-stu-id="c8b06-278">Test the customized format for payment files generation</span></span>
<span data-ttu-id="c8b06-279">Completare i passaggi della procedura "Utilizzare il formato creato per generare documenti elettronici per i pagamenti" in una sessione parallela di Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="c8b06-279">Complete the steps in the "Use created format to generate electronic documents for payments" procedure in parallel Finance and Operations session.</span></span> <span data-ttu-id="c8b06-280">Selezionare il formato "BACS (personalizzata, fittizia per il Regno Unito)" creato nei parametri del metodo di pagamento elettronico.</span><span class="sxs-lookup"><span data-stu-id="c8b06-280">Select the created 'BACS (UK fictitious custom)' format in electronic payment method parameters.</span></span> <span data-ttu-id="c8b06-281">Verificare che il file di pagamento creato contenga il nodo XML introdotto di recente da Proseware, Inc. che presenta il codice conto IBAN in conformità ai requisiti regionali.</span><span class="sxs-lookup"><span data-stu-id="c8b06-281">Make sure that the created payment file contains recently introduced by Proseware, Inc. XML node presenting IBAN account code in accordance to regional requirements.</span></span> <span data-ttu-id="c8b06-282">Il file deve inoltre contenere il nodo XML introdotto di recente da Litware, Inc. che presenta il codice bancario SWIFT in conformità ai requisiti del paese.</span><span class="sxs-lookup"><span data-stu-id="c8b06-282">The file also should contain the recently introduced by Litware, Inc. XML node presenting SWIFT bank code in accordance to country requirements.</span></span>  

