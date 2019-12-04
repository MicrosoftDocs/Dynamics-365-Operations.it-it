---
title: (RCS) Importare file in formato XML con attributi facoltativi
description: In questo argomento vengono fornite informazioni su come un utente può progettare una configurazione di formato ER per importare file in formato XML con attributi facoltativi.
author: NickSelin
manager: AnnBe
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-07-28
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f34302a32b2e06f281dc93d6df160b88ffac7123
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/06/2019
ms.locfileid: "2769787"
---
# <a name="rcs-import-files-in-xml-format-with-optional-attributes"></a><span data-ttu-id="164a9-103">(RCS) Importare file in formato XML con attributi facoltativi</span><span class="sxs-lookup"><span data-stu-id="164a9-103">(RCS) Import files in XML format with optional attributes</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="164a9-104">I passaggi seguenti illustrano come un utente con ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può progettare una configurazione di formato ER per importare file in formato XML contenente attributi facoltativi.</span><span class="sxs-lookup"><span data-stu-id="164a9-104">The following steps explain how a user in the System Administrator or Electronic Reporting Developer role can design ER format configuration to import files in XML format containing optional attributes.</span></span> <span data-ttu-id="164a9-105">Per completare questi passaggi, è necessario completare i passaggi della procedura "Creare un provider di configurazione e contrassegnarlo come attivo".</span><span class="sxs-lookup"><span data-stu-id="164a9-105">To complete these steps, you must first complete the steps in the “Create a configuration provider and mark it as active” procedure.</span></span> <span data-ttu-id="164a9-106">Prima di iniziare, scaricare e salvare localmente il file IncomingDocumentToLearnHowToHandleOptionalAttributes.xml dall'[Area download Microsoft](https://go.microsoft.com/fwlink/?linkid=874684).</span><span class="sxs-lookup"><span data-stu-id="164a9-106">Before you begin, download and save locally the IncomingDocumentToLearnHowToHandleOptionalAttributes.xml file from [Microsoft Download Center](https://go.microsoft.com/fwlink/?linkid=874684).</span></span>

1.  <span data-ttu-id="164a9-107">Andare a **Tutte le aree di lavoro** > **Creazione di report elettronici**.</span><span class="sxs-lookup"><span data-stu-id="164a9-107">Go to **All workspaces** > **Electronic reporting**.</span></span>
2.  <span data-ttu-id="164a9-108">Verificare che il provider di configurazione per la società di esempio Litware, Inc. sia disponibile e contrassegnato come **attivo**.</span><span class="sxs-lookup"><span data-stu-id="164a9-108">Make sure that the configuration provider for the sample company, Litware, Inc., is available and marked as **Active**.</span></span> <span data-ttu-id="164a9-109">Se questo provider di configurazione non è visualizzato, completare i passaggi nella procedura [Creare provider di configurazioni e contrassegnarli come attivi](er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="164a9-109">If you don’t see this configuration provider, complete the steps in the procedure [Create configuration providers and mark them as active](er-configuration-provider-mark-it-active-2016-11.md).</span></span>
3.  <span data-ttu-id="164a9-110">Fare clic su **Configurazioni report**.</span><span class="sxs-lookup"><span data-stu-id="164a9-110">Click **Reporting configurations**.</span></span>

## <a name="create-a-new-data-model-configuration"></a><span data-ttu-id="164a9-111">Creare una nuova configurazione del modello di dati</span><span class="sxs-lookup"><span data-stu-id="164a9-111">Create a new data model configuration</span></span>
1.  <span data-ttu-id="164a9-112">Fare clic su **Crea configurazione** per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="164a9-112">Click **Create configuration** to open the drop dialog.</span></span>
2.  <span data-ttu-id="164a9-113">Nel campo **Nome**, digitare "Modello per importare il file XML".</span><span class="sxs-lookup"><span data-stu-id="164a9-113">In the **Name** field, type 'Model to import xml file'.</span></span>
3.  <span data-ttu-id="164a9-114">Fare clic su **Crea configurazione**.</span><span class="sxs-lookup"><span data-stu-id="164a9-114">Click **Create configuration**.</span></span>
4.  <span data-ttu-id="164a9-115">Fare clic su **Progettazione**.</span><span class="sxs-lookup"><span data-stu-id="164a9-115">Click **Designer**.</span></span>
5.  <span data-ttu-id="164a9-116">Fare clic su **Nuovo** per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="164a9-116">Click **New** to open the drop dialog.</span></span>
6.  <span data-ttu-id="164a9-117">Digitare "Radice" nel campo **Nome**.</span><span class="sxs-lookup"><span data-stu-id="164a9-117">In the **Name** field, type 'Root'.</span></span>
7.  <span data-ttu-id="164a9-118">Scegliere **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="164a9-118">Click **Add**.</span></span>
8.  <span data-ttu-id="164a9-119">Fare clic su **Nuovo** per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="164a9-119">Click **New** to open the drop dialog.</span></span>
9.  <span data-ttu-id="164a9-120">Digitare "Elenco" nel campo **Nome**.</span><span class="sxs-lookup"><span data-stu-id="164a9-120">In the **Name** field, type 'List'.</span></span>
10. <span data-ttu-id="164a9-121">Nel campo **Tipo di articolo** selezionare **Elenco di record**.</span><span class="sxs-lookup"><span data-stu-id="164a9-121">In the **Item type** field, select **Record list**.</span></span>
11. <span data-ttu-id="164a9-122">Scegliere **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="164a9-122">Click **Add**.</span></span>
12. <span data-ttu-id="164a9-123">Fare clic su **Nuovo** per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="164a9-123">Click **New** to open the drop dialog.</span></span>
13. <span data-ttu-id="164a9-124">Digitare "Codice" nel campo **Nome**.</span><span class="sxs-lookup"><span data-stu-id="164a9-124">In the **Name** field, type 'Code'.</span></span>
14. <span data-ttu-id="164a9-125">Nel campo **Tipo di articolo** selezionare **Stringa**.</span><span class="sxs-lookup"><span data-stu-id="164a9-125">In the **Item type** field, select **String**.</span></span>
15. <span data-ttu-id="164a9-126">Scegliere **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="164a9-126">Click **Add**.</span></span>
16. <span data-ttu-id="164a9-127">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="164a9-127">Click **Save**.</span></span>
17. <span data-ttu-id="164a9-128">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="164a9-128">Close the page.</span></span>
18. <span data-ttu-id="164a9-129">Fare clic su **Cambia stato**.</span><span class="sxs-lookup"><span data-stu-id="164a9-129">Click **Change status**.</span></span>
19. <span data-ttu-id="164a9-130">Fare clic su **Completa**.</span><span class="sxs-lookup"><span data-stu-id="164a9-130">Click **Complete**.</span></span>
20. <span data-ttu-id="164a9-131">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="164a9-131">Click **OK**.</span></span>

## <a name="create-a-format-for-data-import"></a><span data-ttu-id="164a9-132">Creare un formato per l'importazione di dati</span><span class="sxs-lookup"><span data-stu-id="164a9-132">Create a format for data import</span></span>
1.  <span data-ttu-id="164a9-133">Fare clic su **Crea configurazione** per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="164a9-133">Click **Create configuration** to open the drop dialog.</span></span>
2.  <span data-ttu-id="164a9-134">Nel campo **Nuovo** immettere "Formato basato sul modello di dati Modello per importare il file xml".</span><span class="sxs-lookup"><span data-stu-id="164a9-134">In the **New** field, enter 'Format based on data model Model to import xml file'.</span></span>
3.  <span data-ttu-id="164a9-135">Nel campo **Nome**, digitare "Formato per importare il file XML".</span><span class="sxs-lookup"><span data-stu-id="164a9-135">In the **Name** field, type 'Format to import xml file'.</span></span>
4.  <span data-ttu-id="164a9-136">Selezionare **Sì** nel campo **Supporta importazione dati**.</span><span class="sxs-lookup"><span data-stu-id="164a9-136">Select **Yes** in the **Supports data import** field.</span></span>
5.  <span data-ttu-id="164a9-137">Fare clic su **Crea configurazione**.</span><span class="sxs-lookup"><span data-stu-id="164a9-137">Click **Create configuration**.</span></span>

## <a name="design-a-format-to-parse-incoming-file-in-xml-format"></a><span data-ttu-id="164a9-138">Progettare un formato per analizzare il file in entrata in formato XML</span><span class="sxs-lookup"><span data-stu-id="164a9-138">Design a format to parse incoming file in xml format</span></span>
1.  <span data-ttu-id="164a9-139">Fare clic su **Progettazione**.</span><span class="sxs-lookup"><span data-stu-id="164a9-139">Click **Designer**.</span></span>
2.  <span data-ttu-id="164a9-140">Fare clic su **Aggiungi radice** per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="164a9-140">Click **Add root** to open the drop dialog.</span></span>
3.  <span data-ttu-id="164a9-141">Nella struttura selezionare **XML\Elemento**.</span><span class="sxs-lookup"><span data-stu-id="164a9-141">In the tree, select **XML\Element**.</span></span>
4.  <span data-ttu-id="164a9-142">Digitare "Radice" nel campo **Nome**.</span><span class="sxs-lookup"><span data-stu-id="164a9-142">In the **Name** field, type 'root'.</span></span>
5.  <span data-ttu-id="164a9-143">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="164a9-143">Click **OK**.</span></span>
6.  <span data-ttu-id="164a9-144">Fare clic su **Aggiungi** per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="164a9-144">Click **Add** to open the drop dialog.</span></span>
7.  <span data-ttu-id="164a9-145">Nella struttura selezionare **XML\Elemento**.</span><span class="sxs-lookup"><span data-stu-id="164a9-145">In the tree, select **XML\Element**.</span></span>
8.  <span data-ttu-id="164a9-146">Nel campo **Nome** digitare "Documento".</span><span class="sxs-lookup"><span data-stu-id="164a9-146">In the **Name** field, type 'document'.</span></span>
9.  <span data-ttu-id="164a9-147">Nel campo **Molteplicità** selezionare **Uno molti**.</span><span class="sxs-lookup"><span data-stu-id="164a9-147">In the **Multiplicity** field, select **One many**.</span></span>
10. <span data-ttu-id="164a9-148">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="164a9-148">Click **OK**.</span></span>
11. <span data-ttu-id="164a9-149">Nella struttura selezionare **radice\documento**.</span><span class="sxs-lookup"><span data-stu-id="164a9-149">In the tree, select **root\document**.</span></span>
12. <span data-ttu-id="164a9-150">Fare clic su **Aggiungi** per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="164a9-150">Click **Add** to open the drop dialog.</span></span>
13. <span data-ttu-id="164a9-151">Nella struttura selezionare **XML\Attributo**.</span><span class="sxs-lookup"><span data-stu-id="164a9-151">In the tree, select **XML\Attribute**.</span></span>
14. <span data-ttu-id="164a9-152">Nel campo **Nome** digitare "ID".</span><span class="sxs-lookup"><span data-stu-id="164a9-152">In the **Name** field, type 'ID'.</span></span>
15. <span data-ttu-id="164a9-153">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="164a9-153">Click **OK**.</span></span>
16. <span data-ttu-id="164a9-154">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="164a9-154">Click **Save**.</span></span>

## <a name="design-a-format-mapping-to-save-parsed-information-to-data-model"></a><span data-ttu-id="164a9-155">Progettare un mapping di formato per salvare le informazioni analizzate nel modello di dati</span><span class="sxs-lookup"><span data-stu-id="164a9-155">Design a format mapping to save parsed information to data model</span></span>
1. <span data-ttu-id="164a9-156">Fare clic su **Mapping formato a modello**.</span><span class="sxs-lookup"><span data-stu-id="164a9-156">Click **Map format to model**.</span></span>
2. <span data-ttu-id="164a9-157">Fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="164a9-157">Click **New**.</span></span>
3. <span data-ttu-id="164a9-158">Nel campo **Definizione** immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="164a9-158">In the **Definition** field, enter or select a value.</span></span>
4. <span data-ttu-id="164a9-159">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="164a9-159">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="164a9-160">Nel campo **Nome** digitare "Mapping".</span><span class="sxs-lookup"><span data-stu-id="164a9-160">In the **Name** field, type 'Mapping'.</span></span>
6. <span data-ttu-id="164a9-161">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="164a9-161">Click **Save**.</span></span>
7. <span data-ttu-id="164a9-162">Fare clic su **Progettazione**.</span><span class="sxs-lookup"><span data-stu-id="164a9-162">Click **Designer**.</span></span>
8. <span data-ttu-id="164a9-163">Nella struttura espandere **formato**.</span><span class="sxs-lookup"><span data-stu-id="164a9-163">In the tree, expand **format**.</span></span>
9. <span data-ttu-id="164a9-164">Nella struttura espandere **format\root: XML Element(root)**.</span><span class="sxs-lookup"><span data-stu-id="164a9-164">In the tree, expand **format\root: XML Element(root)**.</span></span>
10. <span data-ttu-id="164a9-165">Nella struttura selezionare \**format\root: XML Element(root)\document: XML Element 1..*</span><span class="sxs-lookup"><span data-stu-id="164a9-165">In the tree, select \**format\root: XML Element(root)\document: XML Element 1..*</span></span> <span data-ttu-id="164a9-166">(documento)\*\*.</span><span class="sxs-lookup"><span data-stu-id="164a9-166">(document)\*\*.</span></span>
11. <span data-ttu-id="164a9-167">Fare clic su **Associa**.</span><span class="sxs-lookup"><span data-stu-id="164a9-167">Click **Bind**.</span></span>
12. <span data-ttu-id="164a9-168">Nella struttura, espandere \**format\root: XML Element(root)\document: XML Element 1..*</span><span class="sxs-lookup"><span data-stu-id="164a9-168">In the tree, expand \**format\root: XML Element(root)\document: XML Element 1..*</span></span> <span data-ttu-id="164a9-169">(documento)\*\*.</span><span class="sxs-lookup"><span data-stu-id="164a9-169">(document)\*\*.</span></span>
13. <span data-ttu-id="164a9-170">Nella struttura selezionare \**format\root: XML Element(root)\document: XML Element 1..*</span><span class="sxs-lookup"><span data-stu-id="164a9-170">In the tree, select \**format\root: XML Element(root)\document: XML Element 1..*</span></span> <span data-ttu-id="164a9-171">(documento)\id\*\*.</span><span class="sxs-lookup"><span data-stu-id="164a9-171">(document)\id\*\*.</span></span>
14. <span data-ttu-id="164a9-172">Nella struttura espandere **Elenco = format.root.document**.</span><span class="sxs-lookup"><span data-stu-id="164a9-172">In the tree, expand **List = format.root.document**.</span></span>
15. <span data-ttu-id="164a9-173">Nella struttura selezionare **Elenco = format.root.document\Codice**.</span><span class="sxs-lookup"><span data-stu-id="164a9-173">In the tree, select **List = format.root.document\Code**.</span></span>
16. <span data-ttu-id="164a9-174">Fare clic su **Associa**.</span><span class="sxs-lookup"><span data-stu-id="164a9-174">Click **Bind**.</span></span>
17. <span data-ttu-id="164a9-175">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="164a9-175">Click **Save**.</span></span>
18. <span data-ttu-id="164a9-176">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="164a9-176">Close the page.</span></span>
 
## <a name="run-format-mapping"></a><span data-ttu-id="164a9-177">Eseguire il mapping di formato</span><span class="sxs-lookup"><span data-stu-id="164a9-177">Run format mapping</span></span>
1. <span data-ttu-id="164a9-178">Fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="164a9-178">Click **Run**.</span></span>
2. <span data-ttu-id="164a9-179">Fare clic su **Sfoglia** e selezionare **IncomingDocumentToLearnHowToHandleOptionalAttributes.xml**.</span><span class="sxs-lookup"><span data-stu-id="164a9-179">Click **Browse** and select **IncomingDocumentToLearnHowToHandleOptionalAttributes.xml**.</span></span>
3. <span data-ttu-id="164a9-180">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="164a9-180">Click **OK**.</span></span>

> [!NOTE]
> <span data-ttu-id="164a9-181">Il file selezionato non è stato importato in quanto la progettazione del formato presuppone l'esistenza dell'attributo "id" per l'elemento "documento", ma il file importato non contiene tale attributo.</span><span class="sxs-lookup"><span data-stu-id="164a9-181">The selected file has not been imported as the format design assumes the existence of ‘id’ attribute for the ‘document’ element, but the imported file contains no such attribute.</span></span>

## <a name="modify-format-structure-to-handle-xml-attribute-as-optional"></a><span data-ttu-id="164a9-182">Modificare la struttura del formato per gestire l'attributo xml come facoltativo</span><span class="sxs-lookup"><span data-stu-id="164a9-182">Modify format structure to handle xml attribute as optional</span></span>
1. <span data-ttu-id="164a9-183">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="164a9-183">Close the page.</span></span>
2. <span data-ttu-id="164a9-184">Nella struttura espandere **radice\documento**.</span><span class="sxs-lookup"><span data-stu-id="164a9-184">In the tree, expand **root\document**.</span></span>
3. <span data-ttu-id="164a9-185">Nella struttura selezionare **radice\documento\id**.</span><span class="sxs-lookup"><span data-stu-id="164a9-185">In the tree, select **root\document\id**.</span></span>
4. <span data-ttu-id="164a9-186">Selezionare **Sì** nel campo **Stringa vuota per attributo mancante**.</span><span class="sxs-lookup"><span data-stu-id="164a9-186">Select **Yes** in the **Empty string for missing attribute** field.</span></span>
5. <span data-ttu-id="164a9-187">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="164a9-187">Click **Save**.</span></span>
 
## <a name="run-format-mapping-to-test-changes"></a><span data-ttu-id="164a9-188">Eseguire il mapping di formato per testare le modifiche</span><span class="sxs-lookup"><span data-stu-id="164a9-188">Run format mapping to test changes</span></span>
1. <span data-ttu-id="164a9-189">Fare clic su **Mapping formato a modello**.</span><span class="sxs-lookup"><span data-stu-id="164a9-189">Click **Map format to model**.</span></span>
2. <span data-ttu-id="164a9-190">Fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="164a9-190">Click **Run**.</span></span>
3. <span data-ttu-id="164a9-191">Fare clic su **Sfoglia** e selezionare il file **IncomingDocumentToLearnHowToHandleOptionalAttributes.xml**.</span><span class="sxs-lookup"><span data-stu-id="164a9-191">Click **Browse** and select the **IncomingDocumentToLearnHowToHandleOptionalAttributes.xml** file.</span></span>
4. <span data-ttu-id="164a9-192">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="164a9-192">Click **OK**.</span></span>
5. <span data-ttu-id="164a9-193">Esaminare il file generato.</span><span class="sxs-lookup"><span data-stu-id="164a9-193">Review the generated file.</span></span> 

> [!NOTE]
> <span data-ttu-id="164a9-194">Lo stesso file è stato importato in quanto la progettazione del formato ora considera l'attributo "id" per l'elemento "documento" come facoltativo.</span><span class="sxs-lookup"><span data-stu-id="164a9-194">The same file has been imported as the format design now consider the ‘id’ attribute for the ‘document’ element as optional.</span></span>
