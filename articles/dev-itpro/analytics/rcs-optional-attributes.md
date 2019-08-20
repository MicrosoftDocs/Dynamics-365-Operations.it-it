---
title: Importare file in formato XML con attributi facoltativi
description: In questo argomento vengono fornite informazioni sulla progettazione di formati ER che specificano attributi XML per analizzare i documenti elettronici in entrata in formato XML.
author: NickSelin
manager: AnnBe
ms.date: 07/03/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: EROperationDesigner
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: global
ms.author: nselin
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: eb5d721784f45097ab466f75d43256495aac36ca
ms.sourcegitcommit: 16bfa0fd08feec1647829630401ce62ce2ffa1a4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/02/2019
ms.locfileid: "1849997"
---
# <a name="import-files-in-xml-format-with-optional-attributes"></a><span data-ttu-id="84e88-103">Importare file in formato XML con attributi facoltativi</span><span class="sxs-lookup"><span data-stu-id="84e88-103">Import files in XML format with optional attributes</span></span>

<span data-ttu-id="84e88-104">È possibile progettare formati di report elettronici (ER) per analizzare documenti elettronici in entrata in formato XML.</span><span class="sxs-lookup"><span data-stu-id="84e88-104">You can design Electronic reporting (ER) formats to parse incoming electronic documents in XML format.</span></span> <span data-ttu-id="84e88-105">Determinati attributi di elementi XML possono essere specificati nel formato ER progettato come facoltativi.</span><span class="sxs-lookup"><span data-stu-id="84e88-105">Certain attributes of XML elements can be specified in designed ER format as optional.</span></span> <span data-ttu-id="84e88-106">Ciò consentirà di gestire correttamente i file in entrata con e senza tali attributi XML.</span><span class="sxs-lookup"><span data-stu-id="84e88-106">It will allow you to handle incoming files with and without such XML attributes properly.</span></span> <span data-ttu-id="84e88-107">È quindi possibile utilizzare il contenuto di tali file per aggiornare i dati dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="84e88-107">You can then use the content from these files to update application data.</span></span>

<span data-ttu-id="84e88-108">Per ulteriori informazioni su questa funzionalità, completare i passaggi nell'argomento [(RCS) Importare file in formato XML con attributi facoltativi](tasks/import-files-xml-format-optional-attributes.md), che fa parte del processo aziendale 7.5.4.3 Acquisire/sviluppare componenti di soluzioni/servizi IT (10677).</span><span class="sxs-lookup"><span data-stu-id="84e88-108">To learn more about this feature, complete the steps in the topic, [RCS Import files in XML format with optional attributes](tasks/import-files-xml-format-optional-attributes.md), which is part of the 7.5.4.3 Acquire/Develop IT service/solution components (10677) business process.</span></span> <span data-ttu-id="84e88-109">È possibile scaricare questa guida attività e i file di esempio associati dall'[Area download Microsoft](https://go.microsoft.com/fwlink/?linkid=874684).</span><span class="sxs-lookup"><span data-stu-id="84e88-109">You can download this task guide and associated sample files from the [Microsoft Download Center](https://go.microsoft.com/fwlink/?linkid=874684).</span></span>


| <span data-ttu-id="84e88-110">Descrizione contenuto</span><span class="sxs-lookup"><span data-stu-id="84e88-110">Content description</span></span>       | <span data-ttu-id="84e88-111">File</span><span class="sxs-lookup"><span data-stu-id="84e88-111">File</span></span>                                                         |
|---------------------------|--------------------------------------------------------------|
| <span data-ttu-id="84e88-112">File di esempio in formato XML</span><span class="sxs-lookup"><span data-stu-id="84e88-112">Sample file in XML format</span></span> | <span data-ttu-id="84e88-113">IncomingDocumentToLearnHowToHandleOptionalAttributes.xml</span><span class="sxs-lookup"><span data-stu-id="84e88-113">IncomingDocumentToLearnHowToHandleOptionalAttributes.xml</span></span>     |
| <span data-ttu-id="84e88-114">Guida attività</span><span class="sxs-lookup"><span data-stu-id="84e88-114">Task guide</span></span>                | <span data-ttu-id="84e88-115">(RCS) Importare file in formato XML con attributi facoltativi.axtr</span><span class="sxs-lookup"><span data-stu-id="84e88-115">RCS Import files in XML format with optional attributes.axtr</span></span> |


<span data-ttu-id="84e88-116">I passaggi seguenti illustrano come un utente con ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può progettare una configurazione di formato ER per importare file in formato XML contenente attributi facoltativi.</span><span class="sxs-lookup"><span data-stu-id="84e88-116">The following steps explain how a user in the System Administrator or Electronic Reporting Developer role can design ER format configuration to import files in XML format containing optional attributes.</span></span> <span data-ttu-id="84e88-117">Per completare questi passaggi, è necessario dapprima completare i passaggi della procedura [Creare un provider di configurazione e contrassegnarlo come attivo](tasks/er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="84e88-117">To complete these steps, you must first complete the steps in the procedure, [Create a configuration provider and mark it as active](tasks/er-configuration-provider-mark-it-active-2016-11.md).</span></span> <span data-ttu-id="84e88-118">Prima di iniziare, scaricare e salvare localmente il file IncomingDocumentToLearnHowToHandleOptionalAttributes.xml dall'Area download Microsoft (https://go.microsoft.com/fwlink/?linkid=874684).</span><span class="sxs-lookup"><span data-stu-id="84e88-118">Before you begin, download and save locally the IncomingDocumentToLearnHowToHandleOptionalAttributes.xml file from Microsoft Download Center (https://go.microsoft.com/fwlink/?linkid=874684 ).</span></span>

1. <span data-ttu-id="84e88-119">Andare a **Amministrazione organizzazione** > **Aree di lavoro** > **Creazione di report elettronici**.</span><span class="sxs-lookup"><span data-stu-id="84e88-119">Go to **Organization administration** > **Workspaces** > **Electronic reporting**.</span></span>
2. <span data-ttu-id="84e88-120">Verificare che il provider di configurazione per la società di esempio Litware, Inc. sia disponibile e contrassegnato come **attivo**.</span><span class="sxs-lookup"><span data-stu-id="84e88-120">Make sure that the configuration provider for the sample company, Litware, Inc., is available and marked as **Active**.</span></span> <span data-ttu-id="84e88-121">Se questo provider di configurazione non è visualizzato, completare i passaggi dell'argomento [Creare un provider di configurazione e contrassegnarlo come attivo](tasks/er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="84e88-121">If you don’t see this configuration provider, complete the steps in the topic, [Create a configuration provider and mark it as active](tasks/er-configuration-provider-mark-it-active-2016-11.md).</span></span>
3. <span data-ttu-id="84e88-122">Fare clic su **Configurazioni report**.</span><span class="sxs-lookup"><span data-stu-id="84e88-122">Click **Reporting configurations**.</span></span>

## <a name="create-a-new-data-model-configuration"></a><span data-ttu-id="84e88-123">Creare una nuova configurazione del modello di dati</span><span class="sxs-lookup"><span data-stu-id="84e88-123">Create a new data model configuration</span></span>
1. <span data-ttu-id="84e88-124">Fare clic su **Crea configurazione** per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="84e88-124">Click **Create configuration** to open the drop dialog.</span></span>
2. <span data-ttu-id="84e88-125">Nel campo **Nome**, digitare "Modello per importare il file XML".</span><span class="sxs-lookup"><span data-stu-id="84e88-125">In the **Name** field, type 'Model to import xml file'.</span></span>
3. <span data-ttu-id="84e88-126">Fare clic su **Crea configurazione**.</span><span class="sxs-lookup"><span data-stu-id="84e88-126">Click **Create configuration**.</span></span>
4. <span data-ttu-id="84e88-127">Fare clic su **Progettazione**.</span><span class="sxs-lookup"><span data-stu-id="84e88-127">Click **Designer**.</span></span>
5. <span data-ttu-id="84e88-128">Fare clic su **Nuovo** per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="84e88-128">Click **New** to open the drop dialog.</span></span>
6. <span data-ttu-id="84e88-129">Digitare "Radice" nel campo **Nome**.</span><span class="sxs-lookup"><span data-stu-id="84e88-129">In the **Name** field, type 'Root'.</span></span>
7. <span data-ttu-id="84e88-130">Scegliere **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="84e88-130">Click **Add**.</span></span>
8. <span data-ttu-id="84e88-131">Fare clic su **Nuovo** per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="84e88-131">Click **New** to open the drop dialog.</span></span>
9. <span data-ttu-id="84e88-132">Digitare "Elenco" nel campo **Nome**.</span><span class="sxs-lookup"><span data-stu-id="84e88-132">In the **Name** field, type 'List'.</span></span>
10. <span data-ttu-id="84e88-133">Nel campo **Tipo di articolo** selezionare **Elenco di record**.</span><span class="sxs-lookup"><span data-stu-id="84e88-133">In the **Item type** field, select **Record list**.</span></span>
11. <span data-ttu-id="84e88-134">Scegliere **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="84e88-134">Click **Add**.</span></span>
12. <span data-ttu-id="84e88-135">Fare clic su **Nuovo** per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="84e88-135">Click **New** to open the drop dialog.</span></span>
13. <span data-ttu-id="84e88-136">Digitare "Codice" nel campo **Nome**.</span><span class="sxs-lookup"><span data-stu-id="84e88-136">In the **Name** field, type 'Code'.</span></span>
14. <span data-ttu-id="84e88-137">Nel campo **Tipo di articolo** selezionare **Stringa**.</span><span class="sxs-lookup"><span data-stu-id="84e88-137">In the **Item type** field, select **String**.</span></span>
15. <span data-ttu-id="84e88-138">Scegliere **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="84e88-138">Click **Add**.</span></span>
16. <span data-ttu-id="84e88-139">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="84e88-139">Click **Save**.</span></span>
17. <span data-ttu-id="84e88-140">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="84e88-140">Close the page.</span></span>
18. <span data-ttu-id="84e88-141">Fare clic su **Cambia stato**.</span><span class="sxs-lookup"><span data-stu-id="84e88-141">Click **Change status**.</span></span>
19. <span data-ttu-id="84e88-142">Fare clic su **Completa**.</span><span class="sxs-lookup"><span data-stu-id="84e88-142">Click **Complete**.</span></span>
20. <span data-ttu-id="84e88-143">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="84e88-143">Click **OK**.</span></span>

## <a name="create-a-format-for-data-import"></a><span data-ttu-id="84e88-144">Creare un formato per l'importazione di dati</span><span class="sxs-lookup"><span data-stu-id="84e88-144">Create a format for data import</span></span>
1. <span data-ttu-id="84e88-145">Fare clic su **Crea configurazione** per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="84e88-145">Click **Create configuration** to open the drop dialog.</span></span>
2. <span data-ttu-id="84e88-146">Nel campo **Nuovo** immettere "Formato basato sul modello di dati Modello per importare il file xml".</span><span class="sxs-lookup"><span data-stu-id="84e88-146">In the **New** field, enter 'Format based on data model Model to import xml file'.</span></span>
3. <span data-ttu-id="84e88-147">Nel campo **Nome**, digitare "Formato per importare il file XML".</span><span class="sxs-lookup"><span data-stu-id="84e88-147">In the **Nam**e field, type 'Format to import xml file'.</span></span> 
4. <span data-ttu-id="84e88-148">Selezionare **Sì** nel campo **Supporta importazione dati**.</span><span class="sxs-lookup"><span data-stu-id="84e88-148">Select **Yes** in the **Supports data import** field.</span></span>
5. <span data-ttu-id="84e88-149">Fare clic su **Crea configurazione**.</span><span class="sxs-lookup"><span data-stu-id="84e88-149">Click **Create configuration**.</span></span>

## <a name="design-a-format-to-parse-incoming-file-in-xml-format"></a><span data-ttu-id="84e88-150">Progettare un formato per analizzare il file in entrata in formato XML</span><span class="sxs-lookup"><span data-stu-id="84e88-150">Design a format to parse incoming file in xml format</span></span>
1. <span data-ttu-id="84e88-151">Fare clic su **Progettazione**.</span><span class="sxs-lookup"><span data-stu-id="84e88-151">Click **Designer**.</span></span>
2. <span data-ttu-id="84e88-152">Fare clic su **Aggiungi radice** per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="84e88-152">Click **Add root** to open the drop dialog.</span></span>
3. <span data-ttu-id="84e88-153">Nella struttura selezionare **XML\Elemento**.</span><span class="sxs-lookup"><span data-stu-id="84e88-153">In the tree, select **XML\Element**.</span></span>
4. <span data-ttu-id="84e88-154">Digitare "Radice" nel campo **Nome**.</span><span class="sxs-lookup"><span data-stu-id="84e88-154">In the **Name** field, type 'root'.</span></span>
5. <span data-ttu-id="84e88-155">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="84e88-155">Click **OK**.</span></span>
6. <span data-ttu-id="84e88-156">Fare clic su **Aggiungi** per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="84e88-156">Click **Add** to open the drop dialog.</span></span>
7. <span data-ttu-id="84e88-157">Nella struttura selezionare **XML\Elemento**.</span><span class="sxs-lookup"><span data-stu-id="84e88-157">In the tree, select **XML\Element**.</span></span>
8. <span data-ttu-id="84e88-158">Nel campo **Nome** digitare "Documento".</span><span class="sxs-lookup"><span data-stu-id="84e88-158">In the **Name** field, type 'document'.</span></span>
9. <span data-ttu-id="84e88-159">Nel campo **Molteplicità** selezionare **Uno molti**.</span><span class="sxs-lookup"><span data-stu-id="84e88-159">In the **Multiplicity** field, select **One many**.</span></span>
10. <span data-ttu-id="84e88-160">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="84e88-160">Click **OK**.</span></span>
11. <span data-ttu-id="84e88-161">Nella struttura selezionare **radice\documento**.</span><span class="sxs-lookup"><span data-stu-id="84e88-161">In the tree, select **root\document**.</span></span>
12. <span data-ttu-id="84e88-162">Fare clic su **Aggiungi** per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="84e88-162">Click **Add** to open the drop dialog.</span></span>
13. <span data-ttu-id="84e88-163">Nella struttura selezionare **XML\Attributo**.</span><span class="sxs-lookup"><span data-stu-id="84e88-163">In the tree, select **XML\Attribute**.</span></span>
14. <span data-ttu-id="84e88-164">Nel campo **Nome** digitare "id".</span><span class="sxs-lookup"><span data-stu-id="84e88-164">In the **Name** field, type 'id'.</span></span>
15. <span data-ttu-id="84e88-165">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="84e88-165">Click **OK**.</span></span>
16. <span data-ttu-id="84e88-166">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="84e88-166">Click **Save**.</span></span>

## <a name="design-a-format-mapping-to-save-parsed-information-to-data-model"></a><span data-ttu-id="84e88-167">Progettare un mapping di formato per salvare le informazioni analizzate nel modello di dati</span><span class="sxs-lookup"><span data-stu-id="84e88-167">Design a format mapping to save parsed information to data model</span></span>
1.  <span data-ttu-id="84e88-168">Fare clic su **Mapping formato a modello**.</span><span class="sxs-lookup"><span data-stu-id="84e88-168">Click **Map format to model**.</span></span>
2.  <span data-ttu-id="84e88-169">Fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="84e88-169">Click **New**.</span></span>
3.  <span data-ttu-id="84e88-170">Nel campo **Definizione** immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="84e88-170">In the **Definition** field, enter or select a value.</span></span>
4.  <span data-ttu-id="84e88-171">Nel campo **Nome** digitare "Mapping".</span><span class="sxs-lookup"><span data-stu-id="84e88-171">In the **Name** field, type 'Mapping'.</span></span>
5.  <span data-ttu-id="84e88-172">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="84e88-172">Click **Save**.</span></span>
6.  <span data-ttu-id="84e88-173">Fare clic su **Progettazione**.</span><span class="sxs-lookup"><span data-stu-id="84e88-173">Click **Designer**.</span></span>
7.  <span data-ttu-id="84e88-174">Nella struttura espandere **formato**.</span><span class="sxs-lookup"><span data-stu-id="84e88-174">In the tree, expand **format**.</span></span>
8.  <span data-ttu-id="84e88-175">Nella struttura espandere **format\root: XML Element(root)**.</span><span class="sxs-lookup"><span data-stu-id="84e88-175">In the tree, expand **format\root: XML Element(root)**.</span></span>
9.  <span data-ttu-id="84e88-176">Nella struttura selezionare \**format\root: XML Element(root)\document: XML Element 1..*</span><span class="sxs-lookup"><span data-stu-id="84e88-176">In the tree, select \**format\root: XML Element(root)\document: XML Element 1..*</span></span> <span data-ttu-id="84e88-177">(documento)\*\*.</span><span class="sxs-lookup"><span data-stu-id="84e88-177">(document)\*\*.</span></span>
10. <span data-ttu-id="84e88-178">Fare clic su **Associa**.</span><span class="sxs-lookup"><span data-stu-id="84e88-178">Click **Bind**.</span></span>
11. <span data-ttu-id="84e88-179">Nella struttura, espandere \**format\root: XML Element(root)\document: XML Element 1..*</span><span class="sxs-lookup"><span data-stu-id="84e88-179">In the tree, expand \**format\root: XML Element(root)\document: XML Element 1..*</span></span> <span data-ttu-id="84e88-180">(documento)\*\*.</span><span class="sxs-lookup"><span data-stu-id="84e88-180">(document)\*\*.</span></span>
12. <span data-ttu-id="84e88-181">Nella struttura selezionare \**format\root: XML Element(root)\document: XML Element 1..*</span><span class="sxs-lookup"><span data-stu-id="84e88-181">In the tree, select \**format\root: XML Element(root)\document: XML Element 1..*</span></span> <span data-ttu-id="84e88-182">(documento)\id\*\*.</span><span class="sxs-lookup"><span data-stu-id="84e88-182">(document)\id\*\*.</span></span>
13. <span data-ttu-id="84e88-183">Nella struttura espandere **Elenco = format.root.document**.</span><span class="sxs-lookup"><span data-stu-id="84e88-183">In the tree, expand **List = format.root.document**.</span></span>
14. <span data-ttu-id="84e88-184">Nella struttura selezionare **Elenco = format.root.document\Codice**.</span><span class="sxs-lookup"><span data-stu-id="84e88-184">In the tree, select **List = format.root.document\Code**.</span></span>
15. <span data-ttu-id="84e88-185">Fare clic su **Associa**.</span><span class="sxs-lookup"><span data-stu-id="84e88-185">Click **Bind**.</span></span>
16. <span data-ttu-id="84e88-186">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="84e88-186">Click **Save**.</span></span>
17. <span data-ttu-id="84e88-187">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="84e88-187">Close the page.</span></span>

## <a name="run-format-mapping"></a><span data-ttu-id="84e88-188">Eseguire il mapping del formato</span><span class="sxs-lookup"><span data-stu-id="84e88-188">Run format mapping</span></span>
1. <span data-ttu-id="84e88-189">Fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="84e88-189">Click **Run**.</span></span>
2. <span data-ttu-id="84e88-190">Fare clic su **Sfoglia** e selezionare il file **IncomingDocumentToLearnHowToHandleOptionalAttributes.xml**.</span><span class="sxs-lookup"><span data-stu-id="84e88-190">Click **Browse** and select the file, **IncomingDocumentToLearnHowToHandleOptionalAttributes.xml**.</span></span>
3. <span data-ttu-id="84e88-191">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="84e88-191">Click **OK**.</span></span>

> [!NOTE]
> <span data-ttu-id="84e88-192">Il file selezionato non è stato importato in quanto la progettazione del formato presuppone l'esistenza dell'attributo "id" per l'elemento "documento", ma il file importato non contiene tale attributo.</span><span class="sxs-lookup"><span data-stu-id="84e88-192">The selected file has not been imported as the format design assumes the existence of ‘id’ attribute for the ‘document’ element, but the imported file contains no such attribute.</span></span>

## <a name="modify-format-structure-to-handle-xml-attribute-as-optional"></a><span data-ttu-id="84e88-193">Modificare la struttura del formato per gestire l'attributo xml come facoltativo</span><span class="sxs-lookup"><span data-stu-id="84e88-193">Modify format structure to handle xml attribute as optional</span></span>
1. <span data-ttu-id="84e88-194">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="84e88-194">Close the page.</span></span>
2. <span data-ttu-id="84e88-195">Nella struttura espandere **radice\documento**.</span><span class="sxs-lookup"><span data-stu-id="84e88-195">In the tree, expand **root\document**.</span></span>
3. <span data-ttu-id="84e88-196">Nella struttura selezionare **radice\documento\id**.</span><span class="sxs-lookup"><span data-stu-id="84e88-196">In the tree, select **root\document\id**.</span></span>
4. <span data-ttu-id="84e88-197">Nel campo **Stringa vuota per attributo mancante**, selezionare **Sì**.</span><span class="sxs-lookup"><span data-stu-id="84e88-197">In the **Empty string for missing attribute** field, select **Yes**.</span></span>
5. <span data-ttu-id="84e88-198">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="84e88-198">Click **Save**.</span></span>

## <a name="run-format-mapping-to-test-changes"></a><span data-ttu-id="84e88-199">Eseguire il mapping di formato per testare le modifiche</span><span class="sxs-lookup"><span data-stu-id="84e88-199">Run format mapping to test changes</span></span>
1. <span data-ttu-id="84e88-200">Fare clic su **Mapping formato a modello**.</span><span class="sxs-lookup"><span data-stu-id="84e88-200">Click **Map format to model**.</span></span>
2. <span data-ttu-id="84e88-201">Fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="84e88-201">Click **Run**.</span></span>
3. <span data-ttu-id="84e88-202">Fare clic su **Sfoglia** e selezionare il file **IncomingDocumentToLearnHowToHandleOptionalAttributes.xml**.</span><span class="sxs-lookup"><span data-stu-id="84e88-202">Click **Browse** and select the file, **IncomingDocumentToLearnHowToHandleOptionalAttributes.xml**.</span></span>
4. <span data-ttu-id="84e88-203">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="84e88-203">Click **OK**.</span></span>
5. <span data-ttu-id="84e88-204">Esaminare il file generato.</span><span class="sxs-lookup"><span data-stu-id="84e88-204">Review the generated file.</span></span> <span data-ttu-id="84e88-205">Da notare che lo stesso file è stato importato in quanto la progettazione del formato ora considera l'attributo "id" per l'elemento "documento" come facoltativo.</span><span class="sxs-lookup"><span data-stu-id="84e88-205">Note that same file has been imported as the format design now consider the ‘id’ attribute for the ‘document’ element as optional.</span></span>