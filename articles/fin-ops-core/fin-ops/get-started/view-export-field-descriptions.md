---
title: Visualizzare ed esportare le descrizioni campi
description: In questo articolo viene descritto come visualizzare le descrizioni dei campi e come utilizzare la pagina Descrizioni campi per esportare le descrizioni.
author: rschloma
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: FieldDescriptions
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.custom: 11534
ms.assetid: e2795f51-a8a7-4c74-bdb9-b1be93bdd358
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 39dd9a86ffb04d18f61c75fb2c9634e441dc823b
ms.sourcegitcommit: b112925c389a460a98c3401cc2c67df7091b066f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/19/2020
ms.locfileid: "4797901"
---
# <a name="view-and-export-field-descriptions"></a><span data-ttu-id="a8cab-103">Visualizzare ed esportare le descrizioni campi</span><span class="sxs-lookup"><span data-stu-id="a8cab-103">View and export field descriptions</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a8cab-104">In questo articolo viene descritto come visualizzare le descrizioni dei campi e come utilizzare la pagina Descrizioni campi per esportare le descrizioni.</span><span class="sxs-lookup"><span data-stu-id="a8cab-104">This article describes how to view field descriptions and how to use the Field descriptions page to export descriptions.</span></span>

<span data-ttu-id="a8cab-105">Alcuni dei campi più complessi hanno le descrizioni.</span><span class="sxs-lookup"><span data-stu-id="a8cab-105">Some of the more complex fields have field descriptions.</span></span> <span data-ttu-id="a8cab-106">Queste descrizioni vengono visualizzate quando si passa su un campo con il mouse.</span><span class="sxs-lookup"><span data-stu-id="a8cab-106">These descriptions appear when you hover over a field.</span></span> <span data-ttu-id="a8cab-107">È anche possibile visualizzare ed esportare le descrizioni dalla pagina **Descrizioni campi**.</span><span class="sxs-lookup"><span data-stu-id="a8cab-107">You can also view and export descriptions on the **Field descriptions** page.</span></span>

<span data-ttu-id="a8cab-108">Non tutte le pagine presentano descrizioni dei campi.</span><span class="sxs-lookup"><span data-stu-id="a8cab-108">Not all pages have field descriptions.</span></span> <span data-ttu-id="a8cab-109">Sono riportate solo le descrizioni dei campi più complessi, non di quelli il cui uso è ovvio.</span><span class="sxs-lookup"><span data-stu-id="a8cab-109">We want to provide descriptions only for the more complex fields, not where the use of the field is obvious.</span></span> <span data-ttu-id="a8cab-110">Pertanto, le descrizioni dei campi non sono presenti in alcune pagine, alcune pagine hanno alcune descrizioni e alcune delle pagine più complesse, ad esempio molte delle pagine di parametri, includono molte descrizioni.</span><span class="sxs-lookup"><span data-stu-id="a8cab-110">Therefore, some pages don't have any field descriptions, some pages have a few descriptions, and some of the more complex pages, such as many of the parameters pages, have many descriptions.</span></span>

<span data-ttu-id="a8cab-111">Se si ha accesso all'ambiente di sviluppo è possibile aggiungere nuove descrizioni dei campi e personalizzare quelle esistenti.</span><span class="sxs-lookup"><span data-stu-id="a8cab-111">If you have access to the development environment, you can add new field descriptions and customize existing descriptions.</span></span> <span data-ttu-id="a8cab-112">Ad esempio, è possibile aggiungere informazioni specifiche della società per la descrizione di un campo.</span><span class="sxs-lookup"><span data-stu-id="a8cab-112">For example, you can add company-specific information to a field description.</span></span> <span data-ttu-id="a8cab-113">Per ulteriori informazioni, vedere [Personalizzare le descrizioni dei campi](../../dev-itpro/user-interface/customize-field-help.md).</span><span class="sxs-lookup"><span data-stu-id="a8cab-113">For more information, see [Customize field descriptions](../../dev-itpro/user-interface/customize-field-help.md).</span></span>

## <a name="see-field-descriptions-in-the-user-interface"></a><span data-ttu-id="a8cab-114">Vedere le descrizioni dei campi nell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="a8cab-114">See field descriptions in the user interface</span></span>

<span data-ttu-id="a8cab-115">È possibile visualizzare le descrizioni dei campi passando con il mouse su un campo.</span><span class="sxs-lookup"><span data-stu-id="a8cab-115">You can view field descriptions by hovering over a field.</span></span> <span data-ttu-id="a8cab-116">Se non è disponibile alcuna descrizione, verrà visualizzato il nome del campo al passaggio del mouse sul campo.</span><span class="sxs-lookup"><span data-stu-id="a8cab-116">If no description is available, you see the field name when you hover over the field.</span></span>

> [!NOTE]
> <span data-ttu-id="a8cab-117">In Dynamics AX 7.0 (Febbraio 2016), le descrizioni dei campi possono essere visualizzate solo nella pagina **Descrizioni campi**.</span><span class="sxs-lookup"><span data-stu-id="a8cab-117">In Dynamics AX 7.0 (February 2016), field descriptions can be viewed only on the **Field descriptions** page.</span></span>

<span data-ttu-id="a8cab-118">La seguente illustrazione mostra la descrizione che viene visualizzata quando si passa con il mouse sul campo **Blocca articoli durante il conteggio**.</span><span class="sxs-lookup"><span data-stu-id="a8cab-118">The following illustration shows the field description that appears when you hover over the **Lock items during count** field.</span></span>

<span data-ttu-id="a8cab-119">[![Esempio di una descrizione di campo](./media/field-description.png)](./media/field-description.png)</span><span class="sxs-lookup"><span data-stu-id="a8cab-119">[![Example of a field description](./media/field-description.png)](./media/field-description.png)</span></span>

## <a name="use-the-field-descriptions-page-to-view-and-export-field-help"></a><span data-ttu-id="a8cab-120">Utilizzare la pagina Descrizioni campi per visualizzare ed esportare la Guida sui campi</span><span class="sxs-lookup"><span data-stu-id="a8cab-120">Use the Field descriptions page to view and export field help</span></span>

<span data-ttu-id="a8cab-121">La pagina **Descrizioni campi** consente di visualizzare ed esportare le descrizioni dei campi.</span><span class="sxs-lookup"><span data-stu-id="a8cab-121">The **Field descriptions** page lets you view and export field descriptions.</span></span> <span data-ttu-id="a8cab-122">È possibile visualizzare le descrizioni disponibili per una pagina alla volta.</span><span class="sxs-lookup"><span data-stu-id="a8cab-122">You can see the descriptions that are available for one page at a time.</span></span>

### <a name="view-the-descriptions-for-a-page"></a><span data-ttu-id="a8cab-123">Visualizzare le descrizioni per una pagina</span><span class="sxs-lookup"><span data-stu-id="a8cab-123">View the descriptions for a page</span></span>

<span data-ttu-id="a8cab-124">Per visualizzare le descrizioni di una pagina, seguire questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="a8cab-124">To view the descriptions for a page, follow this step.</span></span>

- <span data-ttu-id="a8cab-125">Nel campo **Seleziona pagina** digitare il nome della pagina.</span><span class="sxs-lookup"><span data-stu-id="a8cab-125">In the **Select a page** field, type the name of the page.</span></span> <span data-ttu-id="a8cab-126">In alternativa, fare clic sulla freccia per aprire un elenco di tutte le pagine e quindi cercare o filtrare l'elenco.</span><span class="sxs-lookup"><span data-stu-id="a8cab-126">Alternatively, click the arrow to open a list of all the pages, and then browse or filter the list.</span></span>

<span data-ttu-id="a8cab-127">È possibile utilizzare il nome della pagina visualizzato nell'interfaccia utente, ad esempio **Clienti**, o il nome in codice (nome AOT) disponibile facendo clic con il pulsante destro del mouse su una pagina, ad esempio **CustTable**.</span><span class="sxs-lookup"><span data-stu-id="a8cab-127">You can use either the name of the page that is shown in the user interface (UI) (for example, **Customers**) or the code name (AOT name) that's available when you right-click a page (for example, **CustTable**).</span></span>

<span data-ttu-id="a8cab-128">Per informazioni sui vari modi per filtrare l'elenco delle pagine, vedere la sezione "Ricerca di una pagina" più avanti in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="a8cab-128">For information about the various ways to filter the list of pages, see the "Searching for a page" section later in this article.</span></span>

<span data-ttu-id="a8cab-129">Se si imposta l'opzione **Includi campi senza descrizione** su **Sì**, vengono visualizzati tutti i campi della pagina, anche se non hanno una descrizione.</span><span class="sxs-lookup"><span data-stu-id="a8cab-129">If you set the **Include fields without a description** option to **Yes**, all the fields on the page are shown, even if they don't have a field description.</span></span>

### <a name="export-the-descriptions-for-a-page"></a><span data-ttu-id="a8cab-130">Esportare le descrizioni di una pagina</span><span class="sxs-lookup"><span data-stu-id="a8cab-130">Export the descriptions for a page</span></span>

<span data-ttu-id="a8cab-131">Per esportare le descrizioni di una pagina, seguire questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="a8cab-131">To export the descriptions for a page, follow these steps.</span></span>

1. <span data-ttu-id="a8cab-132">Nel campo **Seleziona pagina** selezionare una pagina.</span><span class="sxs-lookup"><span data-stu-id="a8cab-132">In the **Select a page** field, select a page.</span></span>
2. <span data-ttu-id="a8cab-133">Fare clic sul pulsante **Apri in Microsoft Office** nell'angolo superiore destro, quindi selezionare **FieldDescriptionTmp**.</span><span class="sxs-lookup"><span data-stu-id="a8cab-133">Click the **Open in Microsoft Office** button in the upper-right corner, and then click **FieldDescriptionTmp**.</span></span>

### <a name="searching-for-a-page"></a><span data-ttu-id="a8cab-134">Ricerca di una pagina</span><span class="sxs-lookup"><span data-stu-id="a8cab-134">Searching for a page</span></span>

<span data-ttu-id="a8cab-135">Vi sono diversi modi per cercare una pagina nel campo **Seleziona pagina**.</span><span class="sxs-lookup"><span data-stu-id="a8cab-135">There are several ways to search for a page in the **Select a page** field.</span></span> <span data-ttu-id="a8cab-136">In molti casi è necessario fare clic sulla freccia nel campo **Seleziona pagina** per aprire l'elenco a discesa e selezionare da un elenco filtrato di pagine.</span><span class="sxs-lookup"><span data-stu-id="a8cab-136">In many cases, you must click the arrow in the **Select a page** field to open the drop-down list, and then select from a filtered list of pages.</span></span>

- <span data-ttu-id="a8cab-137">Digitare parte del nome, quindi aprire l'elenco a discesa per selezionare da un elenco filtrato di pagine.</span><span class="sxs-lookup"><span data-stu-id="a8cab-137">Type part of the name, and then open the drop-down list to select from a filtered list of pages.</span></span>
- <span data-ttu-id="a8cab-138">Aprire l'elenco a discesa e fare clic sull'intestazione **Nome pagina** nella parte superiore dell'elenco o sull'intestazione **Nome AOT pagina**.</span><span class="sxs-lookup"><span data-stu-id="a8cab-138">Open the drop-down list, and then click either the **Page name** heading at the top of the list or the **Page AOT name** heading.</span></span> <span data-ttu-id="a8cab-139">Verrà visualizzata una finestra di dialogo in cui è possibile utilizzare opzioni di filtro avanzate, ad esempio **Il nome della pagina inizia con**.</span><span class="sxs-lookup"><span data-stu-id="a8cab-139">A dialog box appears, where you can use advanced filtering options, such as **Page name begins with**.</span></span>
- <span data-ttu-id="a8cab-140">Digitare il nome completo della pagina.</span><span class="sxs-lookup"><span data-stu-id="a8cab-140">Type the full name of the page.</span></span> <span data-ttu-id="a8cab-141">Quando si utilizza questa opzione, è consigliabile aprire l'elenco a discesa e verificare gli altri elementi presenti nell'elenco anche se sono riportate descrizioni dei campi.</span><span class="sxs-lookup"><span data-stu-id="a8cab-141">When you use this option, it's best to open the drop-down list and see what else is in the list, even if field descriptions are shown.</span></span>

    - <span data-ttu-id="a8cab-142">Se è presente una sola corrispondenza esatta del nome, vengono riportate le descrizioni dei campi per la pagina.</span><span class="sxs-lookup"><span data-stu-id="a8cab-142">If there is a single exact match to the name, the field descriptions for that page are shown.</span></span>
    - <span data-ttu-id="a8cab-143">Se esiste più di una corrispondenza esatta, nessuna descrizione viene visualizzata.</span><span class="sxs-lookup"><span data-stu-id="a8cab-143">If there is more than one exact match, no descriptions are shown.</span></span> <span data-ttu-id="a8cab-144">È necessario aprire l'elenco a discesa e selezionare la pagina desiderata.</span><span class="sxs-lookup"><span data-stu-id="a8cab-144">You must open the drop-down list and select the page that you want.</span></span>
    - <span data-ttu-id="a8cab-145">Se il nome digitato è parte del nome di un'altra pagina, sarà possibile visualizzare le descrizioni della pagina.</span><span class="sxs-lookup"><span data-stu-id="a8cab-145">If the name that you typed is part of the name of another page, you see the descriptions for your page.</span></span> <span data-ttu-id="a8cab-146">Tuttavia, se si apre l'elenco a discesa, vengono visualizzate altre pagine che contengono il nome.</span><span class="sxs-lookup"><span data-stu-id="a8cab-146">However, if you open the drop-down list, you see additional pages that contain that name.</span></span>

<span data-ttu-id="a8cab-147">Ad esempio, nessuna descrizione viene visualizzata quando si digita **Conteggio** nel campo **Seleziona pagina**.</span><span class="sxs-lookup"><span data-stu-id="a8cab-147">For example, no descriptions are shown when you type **Counting** in the **Select a page** field.</span></span> <span data-ttu-id="a8cab-148">Si apre l'elenco a discesa e si nota che ci sono due pagine con il nome **Conteggio**, nonché varie pagine il cui nome contiene la parola "Conteggio".</span><span class="sxs-lookup"><span data-stu-id="a8cab-148">You open the drop-down list, and see that there are two pages that have the name **Counting** and several pages that contain the word "Counting" in the name.</span></span> <span data-ttu-id="a8cab-149">Se si seleziona la pagina che presenta il nome AOT **InventJournalCount**, vengono visualizzate le descrizioni dei campi per tale pagina.</span><span class="sxs-lookup"><span data-stu-id="a8cab-149">If you select the page that has the AOT name **InventJournalCount**, the field descriptions are shown for that page.</span></span> <span data-ttu-id="a8cab-150">Tuttavia, se si apre nuovamente l'elenco a discesa, si noterà che l'elenco ora contiene tutte le pagine che presentano come parte del loro nome AOT "InventJournalCount".</span><span class="sxs-lookup"><span data-stu-id="a8cab-150">However, if you open the drop-down list again, you will see that the list now contains all pages that have "InventJournalCount" as part of their AOT name.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="a8cab-151">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="a8cab-151">Troubleshooting</span></span>

<span data-ttu-id="a8cab-152">In questa sezione vengono fornite informazioni per consentire la risoluzione dei problemi che si possono riscontrare utilizzando le descrizioni campi.</span><span class="sxs-lookup"><span data-stu-id="a8cab-152">This section provides information to help you troubleshoot issues that you might encounter when you use field descriptions.</span></span>

### <a name="i-cant-find-a-field-description"></a><span data-ttu-id="a8cab-153">Impossibile trovare la descrizione di un campo</span><span class="sxs-lookup"><span data-stu-id="a8cab-153">I can't find a field description</span></span>

<span data-ttu-id="a8cab-154">È in corso l'aggiunta di descrizioni per i campi più complessi.</span><span class="sxs-lookup"><span data-stu-id="a8cab-154">We're in the process of adding descriptions for the more complex fields.</span></span> <span data-ttu-id="a8cab-155">Se sono necessarie informazioni per un campo specifico, è possibile comunicarlo aggiungendo un commento a questo articolo.</span><span class="sxs-lookup"><span data-stu-id="a8cab-155">If you require help for a particular field, let us know by adding a comment for this topic.</span></span>

### <a name="the-field-description-isnt-helpful"></a><span data-ttu-id="a8cab-156">La descrizione di un campo non è utile</span><span class="sxs-lookup"><span data-stu-id="a8cab-156">The field description isn't helpful</span></span>

<span data-ttu-id="a8cab-157">Comunicarlo aggiungendo un commento a questo articolo.</span><span class="sxs-lookup"><span data-stu-id="a8cab-157">Let us know by adding a comment for this topic.</span></span> <span data-ttu-id="a8cab-158">Se possibile, descrivere le informazioni aggiuntive necessarie.</span><span class="sxs-lookup"><span data-stu-id="a8cab-158">If you can, describe the additional information that you require.</span></span>

### <a name="i-cant-find-a-field-on-the-field-descriptions-page"></a><span data-ttu-id="a8cab-159">Impossibile trovare un campo della pagina Descrizioni campi</span><span class="sxs-lookup"><span data-stu-id="a8cab-159">I can't find a field on the Field descriptions page</span></span>

<span data-ttu-id="a8cab-160">Per visualizzare tutti i campi in una pagina, impostare l'opzione **Includi campi senza descrizione** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="a8cab-160">To show all the fields on a page, set the **Include fields without a description** option to **Yes**.</span></span> <span data-ttu-id="a8cab-161">Fare clic sul campo **Seleziona pagina** per verificare di aver selezionato la pagina corretta.</span><span class="sxs-lookup"><span data-stu-id="a8cab-161">Click the **Select a page** field to verify that you've selected the correct page.</span></span> <span data-ttu-id="a8cab-162">Se il nome digitato è parte di un altro nome di campo, potrebbe essere stata selezionata la pagina con il nome più lungo.</span><span class="sxs-lookup"><span data-stu-id="a8cab-162">If the name that you typed is part of another field name, you might have selected the page that has the longer name.</span></span>

### <a name="i-cant-find-a-page-on-the-field-descriptions-page"></a><span data-ttu-id="a8cab-163">Impossibile trovare una pagina nella pagina Descrizioni campi</span><span class="sxs-lookup"><span data-stu-id="a8cab-163">I can't find a page on the Field descriptions page</span></span>

<span data-ttu-id="a8cab-164">Per informazioni sui vari modi per trovare le pagine, vedere la sezione "Ricerca di una pagina" in precedenza in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="a8cab-164">For information about the various way to find pages, see the "Searching for pages" section earlier in this article.</span></span> <span data-ttu-id="a8cab-165">Se si è immesso il nome esatto della pagina, le descrizioni dei campi possono non essere riportate in caso siano presenti più pagine con lo stesso nome.</span><span class="sxs-lookup"><span data-stu-id="a8cab-165">If you've typed the exact name of the page, the field descriptions might not be shown if more than one page has the same name.</span></span> <span data-ttu-id="a8cab-166">Fare clic sul campo **Seleziona pagina** per aprire un elenco filtrato delle pagine disponibili.</span><span class="sxs-lookup"><span data-stu-id="a8cab-166">Click the arrow in the **Select a page** field to open a filtered list of the pages that are available.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="a8cab-167">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="a8cab-167">Additional resources</span></span>

[<span data-ttu-id="a8cab-168">Personalizzare le descrizioni dei campi</span><span class="sxs-lookup"><span data-stu-id="a8cab-168">Customize field descriptions</span></span>](../../dev-itpro/user-interface/customize-field-help.md)
