---
title: Nuova interfaccia utente per documenti in Gestione documenti aziendali
description: Questo argomento fornisce informazioni su come utilizzare la nuova interfaccia utente per documenti nella funzionalità Gestione documenti aziendali del framework di creazione di report elettronici (ER).
author: v-anamir
manager: AnnBe
ms.date: 05/12/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERBDWorkspace, ERBDParameters
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: v-anamir
ms.search.validFrom: 2019-08-01
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 015b595f85397fc1cf2c0368814ddc0369176f82
ms.sourcegitcommit: 71ec2f48185b8104ca52ff70df52263ce5f87f26
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/25/2020
ms.locfileid: "3893197"
---
# <a name="new-document-user-interface-in-business-document-management"></a><span data-ttu-id="2b794-103">Nuova interfaccia utente per documenti in Gestione documenti aziendali</span><span class="sxs-lookup"><span data-stu-id="2b794-103">New document user interface in Business document management</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="2b794-104">La funzionalità Gestione documenti aziendali consente agli utenti aziendali di modificare i modelli di documenti aziendali tramite un servizio Microsoft 365 o l'applicazione desktop Microsoft Office appropriata.</span><span class="sxs-lookup"><span data-stu-id="2b794-104">Business document management lets business users edit business document templates by using a Microsoft 365 service or the appropriate Microsoft Office desktop application.</span></span> <span data-ttu-id="2b794-105">Le modifiche potrebbero includere modifiche alla progettazione o nuove distribuzioni oppure gli utenti potrebbero aggiungere segnaposto per includere dati aggiuntivi senza dover modificare il codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="2b794-105">Edits might include design changes or new deployments, or users might add placeholders to include additional data without having to change the source code.</span></span> <span data-ttu-id="2b794-106">Per ulteriori informazioni su come utilizzare Gestione documenti aziendali, vedere [Panoramica di Gestione documenti aziendali](er-business-document-management.md).</span><span class="sxs-lookup"><span data-stu-id="2b794-106">For more information about how to work with Business document management, see [Business document management overview](er-business-document-management.md).</span></span>

<span data-ttu-id="2b794-107">La nuova interfaccia utente per documenti è più chiara e più facile da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="2b794-107">The new document user interface (UI) is clearer and more comfortable to use.</span></span> <span data-ttu-id="2b794-108">L'area **Documento aziendale** mostra solo i modelli disponibili per il provider corrente.</span><span class="sxs-lookup"><span data-stu-id="2b794-108">The **Business document** area shows only the templates that are available for the current provider.</span></span>

<span data-ttu-id="2b794-109">Il pulsante **Nuovo documento** consente agli utenti di creare e modificare un modello in una configurazione in formato ER fornita da un altro provider.</span><span class="sxs-lookup"><span data-stu-id="2b794-109">The **New document** button lets users create and edit a template in an Electronic reporting (ER) format configuration that is provided by another provider.</span></span> <span data-ttu-id="2b794-110">Nell'esempio in questo argomento, il provider è Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2b794-110">In the example in this topic, the provider is Microsoft.</span></span>

## <a name="make-the-new-document-ui-in-business-document-management-available"></a><span data-ttu-id="2b794-111">Rendere disponibile la nuova interfaccia utente per documenti in Gestione documenti aziendali</span><span class="sxs-lookup"><span data-stu-id="2b794-111">Make the new document UI in Business document management available</span></span>

<span data-ttu-id="2b794-112">Per iniziare a utilizzare la nuova interfaccia utente per documenti in Gestione documenti aziendali, è necessario attivare la funzionalità **Esperienza di interfaccia utente simile a Office per Gestione documenti aziendali** nell'area di lavoro **Gestione funzionalità**.</span><span class="sxs-lookup"><span data-stu-id="2b794-112">To start to use the new document UI in Business document management, you must turn on the **Office-like UI experience for Business document management** feature in the **Feature management** workspace.</span></span>

<span data-ttu-id="2b794-113">Seguire questi passaggi per attivare questa funzione per tutte le persone giuridiche.</span><span class="sxs-lookup"><span data-stu-id="2b794-113">Follow these steps to turn on this feature for all legal entities.</span></span>

1. <span data-ttu-id="2b794-114">Nell'area di lavoro **Gestione funzionalità**, nella scheda **Nuovo**, selezionare la funzionalità **Esperienza di interfaccia utente simile a Office per Gestione documenti aziendali** nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="2b794-114">In the **Feature management** workspace, on the **New** tab, select the **Office-like UI experience for Business document management** feature in the list.</span></span>
2. <span data-ttu-id="2b794-115">Selezionare **Abilita ora** per attivare la funzionalità selezionata.</span><span class="sxs-lookup"><span data-stu-id="2b794-115">Select **Enable now** to turn on the selected feature.</span></span>
3. <span data-ttu-id="2b794-116">Aggiorna la pagina per accedere alla nuova funzionalità.</span><span class="sxs-lookup"><span data-stu-id="2b794-116">Refresh the page to access the new feature.</span></span>

### <a name="edit-templates-that-are-owned-by-other-providers"></a><span data-ttu-id="2b794-117">Modificare i modelli di proprietà di altri provider</span><span class="sxs-lookup"><span data-stu-id="2b794-117">Edit templates that are owned by other providers</span></span>

1. <span data-ttu-id="2b794-118">Nell'area di lavoro **Gestione documenti aziendali**, selezionare **Nuovo documento**.</span><span class="sxs-lookup"><span data-stu-id="2b794-118">In the **Business document management** workspace, select **New document**.</span></span>

    ![Area di lavoro di Gestione documenti aziendali](./media/BDM_overview_new_template1.png)

2. <span data-ttu-id="2b794-120">Nella finestra di dialogo selezionare il documento da utilizzare come modello e quindi selezionare **Crea documento**.</span><span class="sxs-lookup"><span data-stu-id="2b794-120">In the dialog box, select the document to use as a template, and then select **Create document**.</span></span>

    ![Finestra di dialogo Documenti aziendali](./media/BDM_overview_new_template2.png)

3. <span data-ttu-id="2b794-122">Nella nuova finestra di dialogo, nel campo **Titolo**, cambiare il titolo come richiesto.</span><span class="sxs-lookup"><span data-stu-id="2b794-122">In the new dialog box, in the **Title** field, change the title as you require.</span></span> <span data-ttu-id="2b794-123">Il testo del titolo verrà utilizzato per assegnare un nome alla nuova configurazione in formato ER creata automaticamente.</span><span class="sxs-lookup"><span data-stu-id="2b794-123">The title text is used to name the new ER format configuration that is automatically created.</span></span> <span data-ttu-id="2b794-124">La versione bozza di questa configurazione (**Copia report FTl cliente (GER)**) conterrà il modello modificato e verrà automaticamente utilizzata per eseguire questo formato ER per l'utente corrente.</span><span class="sxs-lookup"><span data-stu-id="2b794-124">The draft version of this configuration (**Customer FTI report (GER) Copy**) will contain the edited template and will be used to run this ER format for the current user.</span></span> <span data-ttu-id="2b794-125">Il modello originale della configurazione in formato ER di base sarà utilizzato per eseguire questo formato ER per qualsiasi altro utente.</span><span class="sxs-lookup"><span data-stu-id="2b794-125">The original template from the base ER format configuration will be used to run this ER format for every other user.</span></span>
4. <span data-ttu-id="2b794-126">Nel campo **Nome**, modificare il nome della prima revisione del modello modificabile che verrà creato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="2b794-126">In the **Name** field, change the name of the first revision of the editable template that will be automatically created.</span></span>
5. <span data-ttu-id="2b794-127">Nel campo **Commento**, aggiornare i commenti per la revisione del modello modificabile che verrà creata automaticamente.</span><span class="sxs-lookup"><span data-stu-id="2b794-127">In the **Comment** field, update the remarks for the revision of the editable template that will be automatically created.</span></span>
6. <span data-ttu-id="2b794-128">Selezionare **OK** per confermare l'avvio del processo di modifica.</span><span class="sxs-lookup"><span data-stu-id="2b794-128">Select **OK** to confirm the start of the editing process.</span></span>

    ![Finestra di dialogo per la creazione di documenti](./media/BDM_overview_new_template3.png)

<span data-ttu-id="2b794-130">Il pulsante **Nuovo documento** è utilizzato per creare e modificare un modello in una configurazione in formato ER fornita da un altro provider.</span><span class="sxs-lookup"><span data-stu-id="2b794-130">The **New document** button is used to create and edit a template in an ER format configuration that is provided by another provider.</span></span> <span data-ttu-id="2b794-131">In questo esempio, il provider è Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2b794-131">In this example, the provider is Microsoft.</span></span> <span data-ttu-id="2b794-132">Quando si seleziona **Nuovo documento**, è possibile visualizzare tutti i modelli di proprietà del provider corrente e di altri provider.</span><span class="sxs-lookup"><span data-stu-id="2b794-132">When you select **New document**, you can view all the templates that are owned by current and other providers.</span></span> <span data-ttu-id="2b794-133">Dopo aver selezionato il modello, questo viene aperto per la modifica.</span><span class="sxs-lookup"><span data-stu-id="2b794-133">After you select the template, it's opened for editing.</span></span> <span data-ttu-id="2b794-134">Il modello modificato verrà archiviato in una nuova configurazione in formato ER generato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="2b794-134">The edited template will then be stored in a new ER format configuration that is automatically generated.</span></span>

<span data-ttu-id="2b794-135">Per ulteriori informazioni, vedere [Panoramica di Gestione documenti aziendali](er-business-document-management.md).</span><span class="sxs-lookup"><span data-stu-id="2b794-135">For more information, see [Business document management overview](er-business-document-management.md).</span></span>
