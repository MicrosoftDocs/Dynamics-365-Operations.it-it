---
title: Visualizzare ed esportare le descrizioni campi
description: In questo articolo viene descritto come visualizzare le descrizioni dei campi e come utilizzare la pagina Descrizioni campi per esportare le descrizioni.
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: FieldDescriptions
audience: Application User, Developer, IT Pro
ms.reviewer: rschloma
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 11534
ms.assetid: e2795f51-a8a7-4c74-bdb9-b1be93bdd358
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 08c38aada355583c5a6872f75b57db95d9b81786
ms.openlocfilehash: 1052338522ca1f2967f6a429f81a25493b89dee0
ms.contentlocale: it-it
ms.lasthandoff: 07/18/2017

---

# <a name="view-and-export-field-descriptions"></a><span data-ttu-id="6ea7c-103">Visualizzare ed esportare le descrizioni campi</span><span class="sxs-lookup"><span data-stu-id="6ea7c-103">View and export field descriptions</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="6ea7c-104">In questo articolo viene descritto come visualizzare le descrizioni dei campi e come utilizzare la pagina Descrizioni campi per esportare le descrizioni.</span><span class="sxs-lookup"><span data-stu-id="6ea7c-104">This article describes how to view field descriptions and how to use the Field descriptions page to export descriptions.</span></span>

<span data-ttu-id="6ea7c-105">Microsoft Dynamics 365 for Finance and Operations offre descrizioni per alcuni campi più complessi.</span><span class="sxs-lookup"><span data-stu-id="6ea7c-105">Microsoft Dynamics 365 for Finance and Operations has descriptions for some of the more complex fields.</span></span> <span data-ttu-id="6ea7c-106">Queste descrizioni vengono visualizzate quando si passa su un campo con il mouse.</span><span class="sxs-lookup"><span data-stu-id="6ea7c-106">These descriptions appear when you hover over a field.</span></span> <span data-ttu-id="6ea7c-107">È anche possibile visualizzare ed esportare le descrizioni dalla pagina **Descrizioni campi**.</span><span class="sxs-lookup"><span data-stu-id="6ea7c-107">You can also view and export descriptions on the **Field descriptions** page.</span></span> 

<span data-ttu-id="6ea7c-108">Non tutte le pagine presentano descrizioni dei campi.</span><span class="sxs-lookup"><span data-stu-id="6ea7c-108">Not all pages have field descriptions.</span></span> <span data-ttu-id="6ea7c-109">Sono riportate solo le descrizioni dei campi più complessi, non di quelli il cui uso è ovvio.</span><span class="sxs-lookup"><span data-stu-id="6ea7c-109">We want to provide descriptions only for the more complex fields, not where the use of the field is obvious.</span></span> <span data-ttu-id="6ea7c-110">Pertanto, le descrizioni dei campi non sono presenti in alcune pagine, alcune pagine hanno alcune descrizioni e alcune delle pagine più complesse, ad esempio molte delle pagine di parametri, includono molte descrizioni.</span><span class="sxs-lookup"><span data-stu-id="6ea7c-110">Therefore, some pages don't have any field descriptions, some pages have a few descriptions, and some of the more complex pages, such as many of the parameters pages, have many descriptions.</span></span> 

<span data-ttu-id="6ea7c-111">Se si ha accesso all'ambiente di sviluppo di Finance and Operations è possibile aggiungere nuove descrizioni dei campi e personalizzare quelle esistenti.</span><span class="sxs-lookup"><span data-stu-id="6ea7c-111">If you have access to the Finance and Operations development environment, you can add new field descriptions and customize existing descriptions.</span></span> <span data-ttu-id="6ea7c-112">Ad esempio, è possibile aggiungere informazioni specifiche della società per la descrizione di un campo.</span><span class="sxs-lookup"><span data-stu-id="6ea7c-112">For example, you can add company-specific information to a field description.</span></span> <span data-ttu-id="6ea7c-113">Per ulteriori informazioni, vedere [Personalizzare la Guida relativa ai campi](/dynamics365/unified-operations/dev-itpro/user-interface/customize-field-help).</span><span class="sxs-lookup"><span data-stu-id="6ea7c-113">For more information, see [Customize field help](/dynamics365/unified-operations/dev-itpro/user-interface/customize-field-help).</span></span>

## <a name="see-field-descriptions-in-the-user-interface"></a><span data-ttu-id="6ea7c-114">Vedere le descrizioni dei campi nell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="6ea7c-114">See field descriptions in the user interface</span></span>
<span data-ttu-id="6ea7c-115">È possibile visualizzare le descrizioni dei campi passando con il mouse su un campo.</span><span class="sxs-lookup"><span data-stu-id="6ea7c-115">You can view field descriptions by hovering over a field.</span></span> <span data-ttu-id="6ea7c-116">Se non è disponibile alcuna descrizione, verrà visualizzato il nome del campo al passaggio del mouse sul campo.</span><span class="sxs-lookup"><span data-stu-id="6ea7c-116">If no description is available, you see the field name when you hover over the field.</span></span> <span data-ttu-id="6ea7c-117">(Nota: in Dynamics AX 7.0 (febbraio 2016) le descrizioni dei campi possono essere visualizzate solo nella pagina **Descrizioni campi**). Nella seguente figura è illustrata la descrizione del campo visualizzato quando si passa con il mouse sul campo **Blocca articoli durante il conteggio**.</span><span class="sxs-lookup"><span data-stu-id="6ea7c-117">(Note: In Dynamics AX 7.0 (February 2016), field descriptions can be viewed only on the **Field descriptions** page.) The following illustration shows the field description that appears when you hover over the **Lock items during count** field.</span></span> 

<span data-ttu-id="6ea7c-118">[![Esempio di una descrizione di campo](./media/field-description.png)](./media/field-description.png)</span><span class="sxs-lookup"><span data-stu-id="6ea7c-118">[![Example of a field description](./media/field-description.png)](./media/field-description.png)</span></span>

## <a name="use-the-field-descriptions-page-to-view-and-export-field-help"></a><span data-ttu-id="6ea7c-119">Utilizzare la pagina Descrizioni campi per visualizzare ed esportare la Guida sui campi</span><span class="sxs-lookup"><span data-stu-id="6ea7c-119">Use the Field descriptions page to view and export field help</span></span>
<span data-ttu-id="6ea7c-120">La pagina **Descrizioni campi** consente di visualizzare ed esportare le descrizioni dei campi.</span><span class="sxs-lookup"><span data-stu-id="6ea7c-120">The **Field descriptions** page lets you view and export field descriptions.</span></span> <span data-ttu-id="6ea7c-121">È possibile visualizzare le descrizioni disponibili per una pagina alla volta.</span><span class="sxs-lookup"><span data-stu-id="6ea7c-121">You can see the descriptions that are available for one page at a time.</span></span>

### <a name="view-the-descriptions-for-a-page"></a><span data-ttu-id="6ea7c-122">Visualizzare le descrizioni per una pagina</span><span class="sxs-lookup"><span data-stu-id="6ea7c-122">View the descriptions for a page</span></span>

<span data-ttu-id="6ea7c-123">Per visualizzare le descrizioni di una pagina, seguire questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="6ea7c-123">To view the descriptions for a page, follow this step.</span></span>

-   <span data-ttu-id="6ea7c-124">Nel campo **Seleziona pagina** digitare il nome della pagina.</span><span class="sxs-lookup"><span data-stu-id="6ea7c-124">In the **Select a page** field, type the name of the page.</span></span> <span data-ttu-id="6ea7c-125">In alternativa, fare clic sulla freccia per aprire un elenco di tutte le pagine e quindi cercare o filtrare l'elenco.</span><span class="sxs-lookup"><span data-stu-id="6ea7c-125">Alternatively, click the arrow to open a list of all the pages, and then browse or filter the list.</span></span>

<span data-ttu-id="6ea7c-126">È possibile utilizzare il nome della pagina visualizzato nell'interfaccia utente, ad esempio **Clienti**, o il nome in codice (nome AOT) disponibile facendo clic con il pulsante destro del mouse su una pagina, ad esempio **CustTable**.</span><span class="sxs-lookup"><span data-stu-id="6ea7c-126">You can use either the name of the page that is shown in the user interface (UI) (for example, **Customers**) or the code name (AOT name) that's available when you right-click a page (for example, **CustTable**).</span></span> 

<span data-ttu-id="6ea7c-127">Per informazioni sui vari modi per filtrare l'elenco delle pagine, vedere la sezione "Ricerca di una pagina" più avanti in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="6ea7c-127">For information about the various ways to filter the list of pages, see the "Searching for a page" section later in this article.</span></span> 

<span data-ttu-id="6ea7c-128">Se si imposta l'opzione **Includi campi senza descrizione** su **Sì**, vengono visualizzati tutti i campi della pagina, anche se non hanno una descrizione.</span><span class="sxs-lookup"><span data-stu-id="6ea7c-128">If you set the **Include fields without a description** option to **Yes**, all the fields on the page are shown, even if they don't have a field description.</span></span>

### <a name="export-the-descriptions-for-a-page"></a><span data-ttu-id="6ea7c-129">Esportare le descrizioni di una pagina</span><span class="sxs-lookup"><span data-stu-id="6ea7c-129">Export the descriptions for a page</span></span>

<span data-ttu-id="6ea7c-130">Per esportare le descrizioni di una pagina, seguire questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="6ea7c-130">To export the descriptions for a page, follow these steps.</span></span>

1.  <span data-ttu-id="6ea7c-131">Nel campo **Seleziona pagina** selezionare una pagina.</span><span class="sxs-lookup"><span data-stu-id="6ea7c-131">In the **Select a page** field, select a page.</span></span>
2.  <span data-ttu-id="6ea7c-132">Fare clic sul pulsante **Apri in Microsoft Office** nell'angolo superiore destro, quindi selezionare **FieldDescriptionTmp**.</span><span class="sxs-lookup"><span data-stu-id="6ea7c-132">Click the **Open in Microsoft Office** button in the upper-right corner, and then click **FieldDescriptionTmp**.</span></span>

### <a name="searching-for-a-page"></a><span data-ttu-id="6ea7c-133">Ricerca di una pagina</span><span class="sxs-lookup"><span data-stu-id="6ea7c-133">Searching for a page</span></span>

<span data-ttu-id="6ea7c-134">Vi sono diversi modi per cercare una pagina nel campo **Seleziona pagina**.</span><span class="sxs-lookup"><span data-stu-id="6ea7c-134">There are several ways to search for a page in the **Select a page** field.</span></span> <span data-ttu-id="6ea7c-135">In molti casi è necessario fare clic sulla freccia nel campo **Seleziona pagina** per aprire l'elenco a discesa e selezionare da un elenco filtrato di pagine.</span><span class="sxs-lookup"><span data-stu-id="6ea7c-135">In many cases, you must click the arrow in the **Select a page** field to open the drop-down list, and then select from a filtered list of pages.</span></span>

-   <span data-ttu-id="6ea7c-136">Digitare parte del nome, quindi aprire l'elenco a discesa per selezionare da un elenco filtrato di pagine.</span><span class="sxs-lookup"><span data-stu-id="6ea7c-136">Type part of the name, and then open the drop-down list to select from a filtered list of pages.</span></span>
-   <span data-ttu-id="6ea7c-137">Aprire l'elenco a discesa e fare clic sull'intestazione **Nome pagina** nella parte superiore dell'elenco o sull'intestazione **Nome AOT pagina**.</span><span class="sxs-lookup"><span data-stu-id="6ea7c-137">Open the drop-down list, and then click either the **Page name** heading at the top of the list or the **Page AOT name** heading.</span></span> <span data-ttu-id="6ea7c-138">Verrà visualizzata una finestra di dialogo in cui è possibile utilizzare opzioni di filtro avanzate, ad esempio **Il nome della pagina inizia con**.</span><span class="sxs-lookup"><span data-stu-id="6ea7c-138">A dialog box appears, where you can use advanced filtering options, such as **Page name begins with**.</span></span>
-   <span data-ttu-id="6ea7c-139">Digitare il nome completo della pagina.</span><span class="sxs-lookup"><span data-stu-id="6ea7c-139">Type the full name of the page.</span></span> <span data-ttu-id="6ea7c-140">Quando si utilizza questa opzione, è consigliabile aprire l'elenco a discesa e verificare gli altri elementi presenti nell'elenco anche se sono riportate descrizioni dei campi.</span><span class="sxs-lookup"><span data-stu-id="6ea7c-140">When you use this option, it's best to open the drop-down list and see what else is in the list, even if field descriptions are shown.</span></span>
    -   <span data-ttu-id="6ea7c-141">Se è presente una sola corrispondenza esatta del nome, vengono riportate le descrizioni dei campi per la pagina.</span><span class="sxs-lookup"><span data-stu-id="6ea7c-141">If there is a single exact match to the name, the field descriptions for that page are shown.</span></span>
    -   <span data-ttu-id="6ea7c-142">Se esiste più di una corrispondenza esatta, nessuna descrizione viene visualizzata.</span><span class="sxs-lookup"><span data-stu-id="6ea7c-142">If there is more than one exact match, no descriptions are shown.</span></span> <span data-ttu-id="6ea7c-143">È necessario aprire l'elenco a discesa e selezionare la pagina desiderata.</span><span class="sxs-lookup"><span data-stu-id="6ea7c-143">You must open the drop-down list and select the page that you want.</span></span>
    -   <span data-ttu-id="6ea7c-144">Se il nome digitato è parte del nome di un'altra pagina, sarà possibile visualizzare le descrizioni della pagina.</span><span class="sxs-lookup"><span data-stu-id="6ea7c-144">If the name that you typed is part of the name of another page, you see the descriptions for your page.</span></span> <span data-ttu-id="6ea7c-145">Tuttavia, se si apre l'elenco a discesa, vengono visualizzate altre pagine che contengono il nome.</span><span class="sxs-lookup"><span data-stu-id="6ea7c-145">However, if you open the drop-down list, you see additional pages that contain that name.</span></span>

<span data-ttu-id="6ea7c-146">Ad esempio, nessuna descrizione viene visualizzata quando si digita **Conteggio** nel campo ****Seleziona pagina****.</span><span class="sxs-lookup"><span data-stu-id="6ea7c-146">For example, no descriptions are shown when you type **Counting** in the ****Select a page**** field.</span></span> <span data-ttu-id="6ea7c-147">Si apre l'elenco a discesa e si nota che ci sono due pagine con il nome **Conteggio**, nonché varie pagine il cui nome contiene la parola "Conteggio".</span><span class="sxs-lookup"><span data-stu-id="6ea7c-147">You open the drop-down list, and see that there are two pages that have the name **Counting** and several pages that contain the word "Counting" in the name.</span></span> <span data-ttu-id="6ea7c-148">Se si seleziona la pagina che presenta il nome AOT **InventJournalCount**, vengono visualizzate le descrizioni dei campi per tale pagina.</span><span class="sxs-lookup"><span data-stu-id="6ea7c-148">If you select the page that has the AOT name **InventJournalCount**, the field descriptions are shown for that page.</span></span> <span data-ttu-id="6ea7c-149">Tuttavia, se si apre nuovamente l'elenco a discesa, si noterà che l'elenco ora contiene tutte le pagine che presentano come parte del loro nome AOT "InventJournalCount".</span><span class="sxs-lookup"><span data-stu-id="6ea7c-149">However, if you open the drop-down list again, you will see that the list now contains all pages that have "InventJournalCount" as part of their AOT name.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="6ea7c-150">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="6ea7c-150">Troubleshooting</span></span>
<span data-ttu-id="6ea7c-151">In questa sezione vengono fornite informazioni per consentire la risoluzione dei problemi che si possono riscontrare utilizzando le descrizioni campi.</span><span class="sxs-lookup"><span data-stu-id="6ea7c-151">This section provides information to help you troubleshoot issues that you might encounter when you use field descriptions.</span></span>

### <a name="i-cant-find-a-field-description"></a><span data-ttu-id="6ea7c-152">Impossibile trovare la descrizione di un campo</span><span class="sxs-lookup"><span data-stu-id="6ea7c-152">I can't find a field description</span></span>

<span data-ttu-id="6ea7c-153">È in corso l'aggiunta di descrizioni per i campi più complessi.</span><span class="sxs-lookup"><span data-stu-id="6ea7c-153">We’re in the process of adding descriptions for the more complex fields.</span></span> <span data-ttu-id="6ea7c-154">Se sono necessarie informazioni per un campo specifico, è possibile comunicarlo aggiungendo un commento a questo articolo.</span><span class="sxs-lookup"><span data-stu-id="6ea7c-154">If you require help for a particular field, let us know by adding a comment for this topic.</span></span>

### <a name="the-field-description-isnt-helpful"></a><span data-ttu-id="6ea7c-155">La descrizione di un campo non è utile</span><span class="sxs-lookup"><span data-stu-id="6ea7c-155">The field description isn't helpful</span></span>

<span data-ttu-id="6ea7c-156">Comunicarlo aggiungendo un commento a questo articolo.</span><span class="sxs-lookup"><span data-stu-id="6ea7c-156">Let us know by adding a comment for this topic.</span></span> <span data-ttu-id="6ea7c-157">Se possibile, descrivere le informazioni aggiuntive necessarie.</span><span class="sxs-lookup"><span data-stu-id="6ea7c-157">If you can, describe the additional information that you require.</span></span>

### <a name="i-cant-find-a-field-on-the-field-descriptions-page"></a><span data-ttu-id="6ea7c-158">Impossibile trovare un campo della pagina Descrizioni campi</span><span class="sxs-lookup"><span data-stu-id="6ea7c-158">I can't find a field on the Field descriptions page</span></span>

<span data-ttu-id="6ea7c-159">Per visualizzare tutti i campi in una pagina, impostare l'opzione **Includi campi senza descrizione** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="6ea7c-159">To show all the fields on a page, set the **Include fields without a description** option to **Yes**.</span></span> <span data-ttu-id="6ea7c-160">Fare clic sul campo **Seleziona pagina** per verificare di aver selezionato la pagina corretta.</span><span class="sxs-lookup"><span data-stu-id="6ea7c-160">Click the **Select a page** field to verify that you've selected the correct page.</span></span> <span data-ttu-id="6ea7c-161">Se il nome digitato è parte di un altro nome di campo, potrebbe essere stata selezionata la pagina con il nome più lungo.</span><span class="sxs-lookup"><span data-stu-id="6ea7c-161">If the name that you typed is part of another field name, you might have selected the page that has the longer name.</span></span>

### <a name="i-cant-find-a-page-on-the-field-descriptions-page"></a><span data-ttu-id="6ea7c-162">Impossibile trovare una pagina nella pagina Descrizioni campi</span><span class="sxs-lookup"><span data-stu-id="6ea7c-162">I can't find a page on the Field descriptions page</span></span>

<span data-ttu-id="6ea7c-163">Per informazioni sui vari modi per trovare le pagine, vedere la sezione "Ricerca di una pagina" in precedenza in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="6ea7c-163">For information about the various way to find pages, see the "Searching for pages" section earlier in this article.</span></span> <span data-ttu-id="6ea7c-164">Se si è immesso il nome esatto della pagina, le descrizioni dei campi possono non essere riportate in caso siano presenti più pagine con lo stesso nome.</span><span class="sxs-lookup"><span data-stu-id="6ea7c-164">If you've typed the exact name of the page, the field descriptions might not be shown if more than one page has the same name.</span></span> <span data-ttu-id="6ea7c-165">Fare clic sul campo **Seleziona pagina** per aprire un elenco filtrato delle pagine disponibili.</span><span class="sxs-lookup"><span data-stu-id="6ea7c-165">Click the arrow in the **Select a page** field to open a filtered list of the pages that are available.</span></span>

<a name="see-also"></a><span data-ttu-id="6ea7c-166">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6ea7c-166">See also</span></span>
--------

[<span data-ttu-id="6ea7c-167">Personalizzare la Guida relativa ai campi</span><span class="sxs-lookup"><span data-stu-id="6ea7c-167">Customize field help</span></span>](/dynamics365/unified-operations/dev-itpro/user-interface/customize-field-help)





