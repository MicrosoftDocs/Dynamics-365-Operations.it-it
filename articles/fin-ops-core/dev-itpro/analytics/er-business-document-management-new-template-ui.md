---
title: Interfaccia utente di tipo Microsoft Office in Gestione documenti aziendali
description: Questo argomento descrive come utilizzare la nuova interfaccia utente nella funzionalità Gestione documenti aziendali del framework Creazione di report elettronici.
author: v-anamir
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERBDWorkspace, ERBDParameters
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: v-anamir
ms.search.validFrom: 2019-08-01
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: e6c5081f71a18dfac83b7aea950395436b42f50e
ms.sourcegitcommit: d18d9cdb175c9d42eafbed66352c24b2aa94258b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2021
ms.locfileid: "5881038"
---
# <a name="microsoft-office-style-user-interface-in-business-document-management"></a><span data-ttu-id="a7173-103">Interfaccia utente di tipo Microsoft Office in Gestione documenti aziendali</span><span class="sxs-lookup"><span data-stu-id="a7173-103">Microsoft Office-style user interface in Business document management</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a7173-104">La funzionalità Gestione documenti aziendali consente agli utenti aziendali di modificare i modelli di documenti aziendali tramite un servizio Microsoft 365 o l'applicazione desktop Microsoft Office appropriata.</span><span class="sxs-lookup"><span data-stu-id="a7173-104">Business document management lets business users edit business document templates by using a Microsoft 365 service or the appropriate Microsoft Office desktop application.</span></span> <span data-ttu-id="a7173-105">Le modifiche potrebbero includere modifiche alla progettazione o nuove distribuzioni oppure gli utenti potrebbero aggiungere segnaposto per includere dati aggiuntivi senza dover modificare il codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="a7173-105">Edits might include design changes or new deployments, or users might add placeholders to include additional data without having to change the source code.</span></span> <span data-ttu-id="a7173-106">Per ulteriori informazioni su come utilizzare Gestione documenti aziendali, vedere [Panoramica di Gestione documenti aziendali](er-business-document-management.md).</span><span class="sxs-lookup"><span data-stu-id="a7173-106">For more information about how to work with Business document management, see [Business document management overview](er-business-document-management.md).</span></span>

<span data-ttu-id="a7173-107">La nuova interfaccia utente è più chiara e più facile da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="a7173-107">The new user interface (UI) is clearer and more comfortable to use.</span></span> <span data-ttu-id="a7173-108">L'area **Documento aziendale** mostra solo i modelli disponibili per il provider corrente.</span><span class="sxs-lookup"><span data-stu-id="a7173-108">The **Business document** area shows only the templates that are available for the current provider.</span></span> <span data-ttu-id="a7173-109">Nell'interfaccia utente precedente, la scheda **Modello** elencava tutti i modelli disponibili per qualsiasi provider.</span><span class="sxs-lookup"><span data-stu-id="a7173-109">In the previous UI, the **Template** tab listed all the templates that were available for any providers.</span></span> <span data-ttu-id="a7173-110">Mostrava anche tutti i modelli creati e modificati da qualsiasi utente con lo stesso ruolo.</span><span class="sxs-lookup"><span data-stu-id="a7173-110">It also showed all the templates that were created and edited by any user who had the same role.</span></span>

<span data-ttu-id="a7173-111">È possibile utilizzare il pulsante **Nuovo documento** per creare e modificare un modello in una configurazione in formato ER fornita da un altro provider.</span><span class="sxs-lookup"><span data-stu-id="a7173-111">You can use the **New document** button to create and edit a template in an Electronic reporting (ER) format configuration that is provided by another provider.</span></span> <span data-ttu-id="a7173-112">Nell'esempio in questo argomento, il provider è Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a7173-112">In the example in this topic, the provider is Microsoft.</span></span> <span data-ttu-id="a7173-113">In alternativa, è possibile creare un modello caricando il modello in formato Excel.</span><span class="sxs-lookup"><span data-stu-id="a7173-113">Alternatively, you can create a template by uploading your own template in Excel format.</span></span>


> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWAVQg]

<span data-ttu-id="a7173-114">Il video [Creare un nuovo documento aziendale utilizzando Gestione documenti aziendali](https://youtu.be/gAIYl-mM_pw) (mostrato sopra) è incluso nella [playlist Finance and Operations](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW) disponibile su YouTube.</span><span class="sxs-lookup"><span data-stu-id="a7173-114">The [Create a new business document using Business document management](https://youtu.be/gAIYl-mM_pw) video (shown above) is included in the [Finance and Operations playlist](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW) available on YouTube.</span></span>

## <a name="make-the-new-document-ui-in-business-document-management-available"></a><span data-ttu-id="a7173-115">Rendere disponibile la nuova interfaccia utente per documenti in Gestione documenti aziendali</span><span class="sxs-lookup"><span data-stu-id="a7173-115">Make the new document UI in Business document management available</span></span>

<span data-ttu-id="a7173-116">Per iniziare a utilizzare la nuova interfaccia utente per documenti in Gestione documenti aziendali, è necessario attivare la funzionalità **Esperienza di interfaccia utente simile a Office per Gestione documenti aziendali** nell'area di lavoro **Gestione funzionalità**.</span><span class="sxs-lookup"><span data-stu-id="a7173-116">To start to use the new document UI in Business document management, you must turn on the **Office-like UI experience for Business document management** feature in the **Feature management** workspace.</span></span>

<span data-ttu-id="a7173-117">Seguire questi passaggi per attivare questa funzione per tutte le persone giuridiche.</span><span class="sxs-lookup"><span data-stu-id="a7173-117">Follow these steps to turn on this feature for all legal entities.</span></span>

1. <span data-ttu-id="a7173-118">Nell'area di lavoro **Gestione funzionalità**, nella scheda **Tutto**, selezionare la funzionalità **Esperienza di interfaccia utente simile a Office per Gestione documenti aziendali** nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="a7173-118">In the **Feature management** workspace, on the **All** tab, select the **Office-like UI experience for Business document management** feature in the list.</span></span>
2. <span data-ttu-id="a7173-119">Selezionare **Abilita ora** per attivare la funzionalità selezionata.</span><span class="sxs-lookup"><span data-stu-id="a7173-119">Select **Enable now** to turn on the selected feature.</span></span>
3. <span data-ttu-id="a7173-120">Aggiorna la pagina per accedere alla nuova funzionalità.</span><span class="sxs-lookup"><span data-stu-id="a7173-120">Refresh the page to access the new feature.</span></span>

## <a name="edit-templates-that-are-owned-by-other-providers"></a><span data-ttu-id="a7173-121">Modificare i modelli di proprietà di altri provider</span><span class="sxs-lookup"><span data-stu-id="a7173-121">Edit templates that are owned by other providers</span></span>

1. <span data-ttu-id="a7173-122">Nell'area di lavoro **Gestione documenti aziendali**, selezionare **Nuovo documento**.</span><span class="sxs-lookup"><span data-stu-id="a7173-122">In the **Business document management** workspace, select **New document**.</span></span>

    ![Area di lavoro di Gestione documenti aziendali](./media/BDM_overview_new_template1.png)

2. <span data-ttu-id="a7173-124">Nella scheda **Seleziona**, selezionare il documento da utilizzare come modello e quindi selezionare **Crea documento**.</span><span class="sxs-lookup"><span data-stu-id="a7173-124">On the **Select** tab, select the document to use as a template, and then select **Create document**.</span></span>

    ![Finestra di dialogo Documenti aziendali](./media/BDM_overview_new_template2.png)

3. <span data-ttu-id="a7173-126">Nella nuova finestra di dialogo, nel campo **Titolo**, cambiare il titolo come richiesto.</span><span class="sxs-lookup"><span data-stu-id="a7173-126">In the new dialog box, in the **Title** field, change the title as you require.</span></span> <span data-ttu-id="a7173-127">Il testo del titolo verrà utilizzato per assegnare un nome alla nuova configurazione in formato ER creata automaticamente.</span><span class="sxs-lookup"><span data-stu-id="a7173-127">The title text is used to name the new ER format configuration that is automatically created.</span></span> <span data-ttu-id="a7173-128">La versione bozza di questa configurazione (**Copia report FTl cliente (GER)**) conterrà il modello modificato e verrà automaticamente utilizzata per eseguire questo formato ER per l'utente corrente.</span><span class="sxs-lookup"><span data-stu-id="a7173-128">The draft version of this configuration (**Customer FTI report (GER) Copy**) will contain the edited template and will be used to run this ER format for the current user.</span></span> <span data-ttu-id="a7173-129">Il modello originale della configurazione in formato ER di base sarà utilizzato per eseguire questo formato ER per qualsiasi altro utente.</span><span class="sxs-lookup"><span data-stu-id="a7173-129">The original template from the base ER format configuration will be used to run this ER format for every other user.</span></span>
4. <span data-ttu-id="a7173-130">Nel campo **Nome**, modificare il nome della prima revisione del modello modificabile che verrà creato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="a7173-130">In the **Name** field, change the name of the first revision of the editable template that will be automatically created.</span></span>
5. <span data-ttu-id="a7173-131">Nel campo **Commento**, aggiornare i commenti per la revisione del modello modificabile che verrà creata automaticamente.</span><span class="sxs-lookup"><span data-stu-id="a7173-131">In the **Comment** field, update the remarks for the revision of the editable template that will be automatically created.</span></span>
6. <span data-ttu-id="a7173-132">Selezionare **OK** per confermare l'avvio del processo di modifica.</span><span class="sxs-lookup"><span data-stu-id="a7173-132">Select **OK** to confirm the start of the editing process.</span></span>

    ![Finestra di dialogo per la creazione di documenti](./media/BDM_overview_new_template3.png)

<span data-ttu-id="a7173-134">Il pulsante **Nuovo documento** è utilizzato per creare e modificare un modello in una configurazione in formato ER fornita da un altro provider.</span><span class="sxs-lookup"><span data-stu-id="a7173-134">The **New document** button is used to create and edit a template in an ER format configuration that is provided by another provider.</span></span> <span data-ttu-id="a7173-135">In questo esempio, il provider è Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a7173-135">In this example, the provider is Microsoft.</span></span> <span data-ttu-id="a7173-136">Quando si seleziona **Nuovo documento**, è possibile visualizzare tutti i modelli di proprietà del provider corrente e di altri provider.</span><span class="sxs-lookup"><span data-stu-id="a7173-136">When you select **New document**, you can view all the templates that are owned by current and other providers.</span></span> <span data-ttu-id="a7173-137">Dopo aver selezionato il modello, questo viene aperto per la modifica.</span><span class="sxs-lookup"><span data-stu-id="a7173-137">After you select the template, it's opened for editing.</span></span> <span data-ttu-id="a7173-138">Il modello modificato verrà archiviato in una nuova configurazione in formato ER generato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="a7173-138">The edited template will then be stored in a new ER format configuration that is automatically generated.</span></span>

## <a name="upload-a-template-that-uses-an-existing-excel-format"></a><span data-ttu-id="a7173-139">Caricare un modello che utilizza un formato Excel esistente</span><span class="sxs-lookup"><span data-stu-id="a7173-139">Upload a template that uses an existing Excel format</span></span>
<span data-ttu-id="a7173-140">Seguire questi passaggi per fornire le informazioni necessarie prima di caricare un modello.</span><span class="sxs-lookup"><span data-stu-id="a7173-140">Follow these steps to provide required information before you upload a template.</span></span>

1. <span data-ttu-id="a7173-141">Nell'area di lavoro **Gestione documenti aziendali**, selezionare **Nuovo documento**.</span><span class="sxs-lookup"><span data-stu-id="a7173-141">In the **Business document management** workspace, select **New document**.</span></span>

    ![Area di lavoro di Gestione documenti aziendali](./media/BDM_overview_new_template1.png)
    
2. <span data-ttu-id="a7173-143">Nella pagina **Crea un nuovo modello**, nella scheda **Carica**, nella scheda **Modello**, selezionare **Sfoglia** per trovare e selezionare il file Excel che si desidera utilizzare come modello.</span><span class="sxs-lookup"><span data-stu-id="a7173-143">On the **Create a new template** page, on the **Upload** tab, on the **Template** tab, select **Browse** to find and select the Excel file that you want to use as a template.</span></span> <span data-ttu-id="a7173-144">Nella sezione **Modello**, i campi **Titolo** e **Descrizione** vengono compilati automaticamente.</span><span class="sxs-lookup"><span data-stu-id="a7173-144">In the **Template** section, the **Title** and **Description** fields are automatically filled in.</span></span> <span data-ttu-id="a7173-145">Questi specificano il nome e la descrizione della nuova configurazione in formato ER che viene creata automaticamente.</span><span class="sxs-lookup"><span data-stu-id="a7173-145">They specify the name and description of the new ER format configuration that is automatically created.</span></span> <span data-ttu-id="a7173-146">È possibile modificare questi campi secondo le necessità.</span><span class="sxs-lookup"><span data-stu-id="a7173-146">You can edit these fields as you require.</span></span>
3. <span data-ttu-id="a7173-147">Nella sezione **Tipo di documento**, nel campo **Nome**, specificare il tipo di documento aziendale.</span><span class="sxs-lookup"><span data-stu-id="a7173-147">In the **Document Type** section, in the **Name** field, specify the type of business document.</span></span> <span data-ttu-id="a7173-148">Questo valore verrà utilizzato per cercare l'origine dati corretta (ovvero la configurazione del modello ER).</span><span class="sxs-lookup"><span data-stu-id="a7173-148">This value will be used to search the correct data source (that is, the ER model configuration).</span></span>

    ![Scheda Modello](./media/BDM_overview_new_UI_import_21.jpg)

4. <span data-ttu-id="a7173-150">Nella scheda **Origine dati**, nella Scheda dettaglio **Filtro**, selezionare **Applica filtro**.</span><span class="sxs-lookup"><span data-stu-id="a7173-150">On the **Data source** tab, on the **Filter** FastTab, select **Apply filter**.</span></span> <span data-ttu-id="a7173-151">Nella sezione **Origine dati**, il campo **Nome** viene compilato automaticamente oppure è possibile selezionare manualmente un valore.</span><span class="sxs-lookup"><span data-stu-id="a7173-151">In the **Data source** section, the **Name** field is automatically filled in, or you can manually select a value.</span></span> <span data-ttu-id="a7173-152">È possibile utilizzare il filtro per cercare il nome dell'origine dati appropriata per nome, descrizione, codice paese/regione e tipo di documento aziendale.</span><span class="sxs-lookup"><span data-stu-id="a7173-152">You can use the filter to search for the appropriate data source name by name, description, country/region code, and business document type.</span></span>

    ![Scheda Origine dati](./media/BDM_overview_new_UI_import_31.jpg)
    
    > [!NOTE]
    > <span data-ttu-id="a7173-154">Questa Scheda dettaglio **Filtro** viene utilizzata per cercare nell'origine dati corretta (ovvero la configurazione del modello ER).</span><span class="sxs-lookup"><span data-stu-id="a7173-154">The **Filter** FastTab is used to search the correct data source (that is, the ER model configuration).</span></span> <span data-ttu-id="a7173-155">È possibile modificare tutti i campi del filtro per trovare l'origine dati più appropriata per il documento che si sta caricando.</span><span class="sxs-lookup"><span data-stu-id="a7173-155">You can edit all filter fields to find the most appropriate data source for the document that you're uploading.</span></span>
    > 
    > <span data-ttu-id="a7173-156">Le condizioni nella Scheda dettaglio **Filtro** sono usate come condizioni **OR**.</span><span class="sxs-lookup"><span data-stu-id="a7173-156">The conditions on the **Filter** FastTab are used as **OR** conditions.</span></span>
    
5. <span data-ttu-id="a7173-157">Nella scheda **Mapping**, selezionare **Rilevamento automatico**.</span><span class="sxs-lookup"><span data-stu-id="a7173-157">On the **Mapping** tab, select **Auto detect**.</span></span> <span data-ttu-id="a7173-158">Il campo **Definizione radice** viene automaticamente riempito oppure è possibile selezionare manualmente un valore.</span><span class="sxs-lookup"><span data-stu-id="a7173-158">The **Root definition** field is automatically filled in, or you can manually select a value.</span></span> <span data-ttu-id="a7173-159">Questa scheda mostra il mapping finale per gli elementi del modello.</span><span class="sxs-lookup"><span data-stu-id="a7173-159">This tab shows the end mapping for the elements from the template and the model.</span></span>

    ![Scheda Mapping](./media/BDM_overview_new_UI_import_41.jpg)
    
   > [!NOTE]
   > <span data-ttu-id="a7173-161">Il mapping nella sezione **Struttura del modello** utilizza la corrispondenza completa delle etichette o delle descrizioni nell'origine dati nella lingua dell'utente e nel nome di cella nel modello.</span><span class="sxs-lookup"><span data-stu-id="a7173-161">The mapping in the **Template structure** section uses the full match of the labels or descriptions in the data source in the user's language, and in the cell name in the template.</span></span>

6. <span data-ttu-id="a7173-162">Selezionare **Crea documento** per confermare che si desidera creare un modello e avviare il processo di modifica.</span><span class="sxs-lookup"><span data-stu-id="a7173-162">Select **Create document** to confirm that you want to create a template and start the editing process.</span></span>

<span data-ttu-id="a7173-163">Per ulteriori informazioni, vedere [Panoramica di Gestione documenti aziendali](er-business-document-management.md).</span><span class="sxs-lookup"><span data-stu-id="a7173-163">For more information, see [Business document management overview](er-business-document-management.md).</span></span>

<span data-ttu-id="a7173-164">Se non è presente un provider in Creazione di report elettronici, è possibile crearne uno.</span><span class="sxs-lookup"><span data-stu-id="a7173-164">If there isn't a provider in Electronic reporting, you can create one.</span></span> <span data-ttu-id="a7173-165">Se non c'è un provider attivo, è possibile scegliere di attivarne uno.</span><span class="sxs-lookup"><span data-stu-id="a7173-165">If there's no active provider, you can select to activate one.</span></span>

- <span data-ttu-id="a7173-166">Per creare un provider, modificare il nome del provider nel campo **Nome**, aggiornare l'indirizzo Internet del nuovo provider nel campo **Indirizzo Internet** e selezionare **OK** per confermare.</span><span class="sxs-lookup"><span data-stu-id="a7173-166">To create a provider, change the name of the provider in the **Name** field, update the internet address of the new provider in the **Internet address** field, and select **OK** to confirm.</span></span>

    ![Creare un nuovo provider in Gestione documenti aziendali](./media/bdm_create_provider.png)
    
- <span data-ttu-id="a7173-168">Per attivare il provider esistente, scegliere il nome del provider nel campo **Provider di configurazioni** e selezionare **OK** per impostare il provider come attivo.</span><span class="sxs-lookup"><span data-stu-id="a7173-168">To activate existing provider, choose the name of the provider in the **Configuration provider** field, and select **OK** to set provider as active.</span></span>

    ![Attivare il provider in Gestione documenti aziendali](./media/bdm_choose_provider.png)

> [!NOTE]
> <span data-ttu-id="a7173-170">Ogni modello di Gestione documenti aziendali fa riferimento al provider come autore della configurazione.</span><span class="sxs-lookup"><span data-stu-id="a7173-170">Each BDM template refers to the provider as the author of the configuration.</span></span> <span data-ttu-id="a7173-171">Questo è il motivo per cui un provider attivo è necessario per il modello.</span><span class="sxs-lookup"><span data-stu-id="a7173-171">This is why an active provider is required for the template.</span></span>

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
