---
title: Organizzare i componenti del report in Progettazione report
description: In questo argomento viene spiegato come organizzare i report, i blocchi predefiniti e gli oggetti esistenti in Progettazione report.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: kfend
ms.custom: 59161
ms.assetid: 32e728c5-3b06-4049-8070-ade01e951d49
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 0b55dcee00f571228ec1e933306d77d9edc12866
ms.sourcegitcommit: 5192cfaedfd861faea63d8954d7bcc500608a225
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2021
ms.locfileid: "5092425"
---
# <a name="organize-report-components-in-report-designer"></a><span data-ttu-id="14f63-103">Organizzare i componenti del report in Progettazione report</span><span class="sxs-lookup"><span data-stu-id="14f63-103">Organize report components in report designer</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="14f63-104">Dopo aver progettato i blocchi predefiniti e generato i report, è utile organizzare questi oggetti in modo che gli utenti possano individuarli più facilmente.</span><span class="sxs-lookup"><span data-stu-id="14f63-104">After you've designed building blocks and generated reports, it's helpful to organize these objects so that they are easier for users to locate.</span></span> <span data-ttu-id="14f63-105">In questo articolo viene spiegato come organizzare i report, i blocchi predefiniti e gli oggetti esistenti in Progettazione report.</span><span class="sxs-lookup"><span data-stu-id="14f63-105">This article explains how to organize existing reports, building blocks, and objects in report designer.</span></span>

<span data-ttu-id="14f63-106">È possibile rinominare le cartelle, i report, i blocchi predefiniti e altri oggetti in Progettazione report per migliorare l'organizzazione dei file.</span><span class="sxs-lookup"><span data-stu-id="14f63-106">You can rename folders, reports, building blocks, and other objects in report designer to help organize your files.</span></span> <span data-ttu-id="14f63-107">A seconda del tipo di oggetto che rinominate, potrebbe essere necessario aggiornare le associazioni a tale oggetto.</span><span class="sxs-lookup"><span data-stu-id="14f63-107">Depending on the type of object that you rename, you might have to update associations with that object.</span></span>

## <a name="rename-a-folder-or-building-block-in-report-designer"></a><span data-ttu-id="14f63-108">Rinominare una cartella o un blocco predefinito in Progettazione report</span><span class="sxs-lookup"><span data-stu-id="14f63-108">Rename a folder or building block in Report Designer</span></span>
<span data-ttu-id="14f63-109">In Progettazione report è possibile rinominare cartelle, definizioni di report, di riga di colonna e di albero gerarchico.</span><span class="sxs-lookup"><span data-stu-id="14f63-109">In Report Designer, you can rename folders, report definitions, row definitions, column definitions, and reporting tree definitions.</span></span>

### <a name="rename-a-folder-or-building-block-in-report-designer"></a><span data-ttu-id="14f63-110">Rinominare una cartella o un blocco predefinito in Progettazione report</span><span class="sxs-lookup"><span data-stu-id="14f63-110">Rename a folder or building block in Report Designer</span></span>

1. <span data-ttu-id="14f63-111">In Progettazione report utilizzare il riquadro di spostamento per individuare la cartella o l'oggetto da rinominare.</span><span class="sxs-lookup"><span data-stu-id="14f63-111">In Report Designer, use the navigation pane to locate the folder or object to rename.</span></span>
2. <span data-ttu-id="14f63-112">Fare clic con il pulsante destro del mouse sulla cartella o sull'oggetto, quindi scegliere **Rinomina**.</span><span class="sxs-lookup"><span data-stu-id="14f63-112">Right-click the folder or object, and then click **Rename**.</span></span> <span data-ttu-id="14f63-113">Il campo **Nome** nel pannello di navigazione diventa disponibile.</span><span class="sxs-lookup"><span data-stu-id="14f63-113">The **Name** field in the navigation pane becomes available.</span></span>
3. <span data-ttu-id="14f63-114">Immettere un nuovo nome e premere Invio.</span><span class="sxs-lookup"><span data-stu-id="14f63-114">Type a new name, and then press Enter.</span></span>
4. <span data-ttu-id="14f63-115">Se il blocco predefinito è una definizione di riga, una definizione di colonna o una definizione di albero gerarchico, è necessario aggiornare altri blocchi predefiniti associati a esso.</span><span class="sxs-lookup"><span data-stu-id="14f63-115">If the building block is a row definition, column definition, or reporting tree definition, you must update other building blocks that are associated with it.</span></span> <span data-ttu-id="14f63-116">Fare clic con il pulsante destro del mouse sul blocco prefedinito rinominato al passaggio 3, selezionare **Associazioni** quindi selezionare un elemento nell'elenco per aggiornarlo.</span><span class="sxs-lookup"><span data-stu-id="14f63-116">Right-click the building block that you renamed in step 3, select **Associations**, and then select an item in the list to update it.</span></span>
5. <span data-ttu-id="14f63-117">Ripetere il passaggio 4 fino a che tutti gli elementi associati sono aggiornati.</span><span class="sxs-lookup"><span data-stu-id="14f63-117">Repeat step 4 until all associated items are updated.</span></span>

## <a name="create-and-manage-report-groups"></a><span data-ttu-id="14f63-118">Creare e gestire gruppi di report</span><span class="sxs-lookup"><span data-stu-id="14f63-118">Create and manage report groups</span></span>
<span data-ttu-id="14f63-119">È possibile raggruppare le definizioni di report per generare più report contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="14f63-119">You can group report definitions to generate multiple reports at the same time.</span></span> <span data-ttu-id="14f63-120">Per creare, modificare, eliminare e generare gruppi di report, è necessario disporre del ruolo di designer o amministratore.</span><span class="sxs-lookup"><span data-stu-id="14f63-120">To create, modify, delete, and generate report groups, you must have the designer or administrator role.</span></span> <span data-ttu-id="14f63-121">Gli utenti con il ruolo di generatore possono generare gruppi di report e possono inoltre modificare l'impostazione delle definizioni di report dell'utente per i gruppi di report.</span><span class="sxs-lookup"><span data-stu-id="14f63-121">Users who have the generator role can generate report groups and can also modify the user report definitions setting for report groups.</span></span>

### <a name="create-a-report-group"></a><span data-ttu-id="14f63-122">Creare un gruppo di report.</span><span class="sxs-lookup"><span data-stu-id="14f63-122">Create a report group</span></span>

1. <span data-ttu-id="14f63-123">In Progettazione report, nel pannello di navigazione, fare clic su **Gruppi di report**.</span><span class="sxs-lookup"><span data-stu-id="14f63-123">In Report Designer, in the navigation pane, click **Report Groups**.</span></span>
2. <span data-ttu-id="14f63-124">Nel menu **File**, fare clic su **Nuovo** &gt; **Definizione gruppo di report** per aprire un nuovo gruppo di report nella finestra del visualizzatore.</span><span class="sxs-lookup"><span data-stu-id="14f63-124">On the **File** menu, click **New** &gt; **Report Group Definition** to open a new report group in the viewer window.</span></span> <span data-ttu-id="14f63-125">In alternativa, fare clic sul pulsante **Gruppo di report** ![Gruppo di report](media/report-group.gif "Gruppo di report") sulla barra degli strumenti.</span><span class="sxs-lookup"><span data-stu-id="14f63-125">Alternatively, click the **Report Group** button ![Report Group](media/report-group.gif "Report Group") on the toolbar.</span></span>
3. <span data-ttu-id="14f63-126">Fare clic sulla scheda **Gruppo di report**. Per ignorare le informazioni sulle singole definizioni di report per la generazione di questo report, selezionare la casella di controllo **Ignora impostazioni società, dettagli e data dalle singole definizioni di report**.</span><span class="sxs-lookup"><span data-stu-id="14f63-126">Click the **Report Group** tab. To override the information on the individual report definitions for the generation of this report, select the **Override company, detail, and date settings from individual report definitions** check box.</span></span> <span data-ttu-id="14f63-127">Il nome della società, il livello di dettaglio, l'impostazione provvisoria e le informazioni sulla data vengono immessi automaticamente ma è comunque possibile effettuare aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="14f63-127">The company name, detail level, provisional setting, and date information are entered automatically, but you can make updates.</span></span>
4. <span data-ttu-id="14f63-128">Selezionare la casella di controllo **Includi tutte le valute di dichiarazione** per generare più report che mostrano tali valute.</span><span class="sxs-lookup"><span data-stu-id="14f63-128">To generate multiple reports that show the reporting currencies, select the **Include all reporting currencies** check box.</span></span> <span data-ttu-id="14f63-129">È quindi possibile accedere a più visualizzazioni facendo clic sul pulsante **Valuta** nel Visualizzatore Web quando si visualizza il report.</span><span class="sxs-lookup"><span data-stu-id="14f63-129">You can then access multiple views by clicking the **Currency** button in the Web Viewer when you view the report.</span></span>
5. <span data-ttu-id="14f63-130">Nel campo **Report nel gruppo**, fare clic su **Aggiungi** per selezionare i report da includere nel gruppo di report.</span><span class="sxs-lookup"><span data-stu-id="14f63-130">In the **Reports in group** field, click **Add** to select the reports to include in the report group.</span></span> <span data-ttu-id="14f63-131">Per selezionare più report nella finestra di dialogo **Aggiungi**, tenere premuto il tasto Ctrl mentre si seleziono i report.</span><span class="sxs-lookup"><span data-stu-id="14f63-131">To select multiple reports in the **Add** dialog box, hold down the Ctrl key while you select reports.</span></span> <span data-ttu-id="14f63-132">Una volta terminata la selezione dei report, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="14f63-132">When you've finished selecting reports, click **OK**.</span></span>
6. <span data-ttu-id="14f63-133">Fare clic su **File** &gt; **Salva** per salvare il nuovo gruppo di report.</span><span class="sxs-lookup"><span data-stu-id="14f63-133">Click **File** &gt; **Save** to save the new report group.</span></span>

### <a name="modify-a-report-group"></a><span data-ttu-id="14f63-134">Modificare un gruppo di report</span><span class="sxs-lookup"><span data-stu-id="14f63-134">Modify a report group</span></span>

1. <span data-ttu-id="14f63-135">In Progettazione report, nel pannello di navigazione, fare clic su **Gruppi di report**.</span><span class="sxs-lookup"><span data-stu-id="14f63-135">In Report Designer, in the navigation pane, click **Report Groups**.</span></span>
2. <span data-ttu-id="14f63-136">Fare doppio clic sul gruppo di report da modificare.</span><span class="sxs-lookup"><span data-stu-id="14f63-136">Double-click the report group to modify.</span></span>
3. <span data-ttu-id="14f63-137">Nella scheda **Gruppo di report** apportare le modifiche desiderate.</span><span class="sxs-lookup"><span data-stu-id="14f63-137">On the **Report Group** tab, make the changes that you want.</span></span>
4. <span data-ttu-id="14f63-138">Nel menu **File** fare clic su **Salva** per salvare il gruppo di report modificato. In alternativa, fare clic sul pulsante **Salva** ![Salva](media/save.gif "Salva") sulla barra degli strumenti.</span><span class="sxs-lookup"><span data-stu-id="14f63-138">On the **File** menu, click **Save** to save the modified report group, Alternatively, click the **Save** button ![Save](media/save.gif "Save") on the toolbar.</span></span>

> <span data-ttu-id="14f63-139">[NOTA] Se è stata pianificata la generazione di report a intervalli stabiliti, è possibile ignorare tali impostazioni e generare un report immediatamente.</span><span class="sxs-lookup"><span data-stu-id="14f63-139">[NOTE] If you've scheduled reports so that they are generated at set intervals, you can override those settings and generate a report immediately.</span></span>

### <a name="generate-a-report-group-report"></a><span data-ttu-id="14f63-140">Generare un gruppo di report</span><span class="sxs-lookup"><span data-stu-id="14f63-140">Generate a report group report</span></span>

1. <span data-ttu-id="14f63-141">In Progettazione report, nel pannello di navigazione, fare clic su **Gruppi di report**.</span><span class="sxs-lookup"><span data-stu-id="14f63-141">In Report Designer, in the navigation pane, click **Report Groups**.</span></span>
2. <span data-ttu-id="14f63-142">Aprire il gruppo di report da generare.</span><span class="sxs-lookup"><span data-stu-id="14f63-142">Open the report group to generate.</span></span>
3. <span data-ttu-id="14f63-143">Fare clic sul pulsante **Genera report** ![Genera report](media/generate-report.gif "Genera report") per generare i report.</span><span class="sxs-lookup"><span data-stu-id="14f63-143">Click the **Generate Report** button ![Generate Report](media/generate-report.gif "Generate Report") to generate reports.</span></span>

### <a name="delete-a-report-group"></a><span data-ttu-id="14f63-144">Eliminare un gruppo di report</span><span class="sxs-lookup"><span data-stu-id="14f63-144">Delete a report group</span></span>

1. <span data-ttu-id="14f63-145">In Progettazione report, nel pannello di navigazione, fare clic su **Gruppi di report**.</span><span class="sxs-lookup"><span data-stu-id="14f63-145">In Report Designer, in the navigation pane, click **Report Groups**.</span></span>
2. <span data-ttu-id="14f63-146">Fare clic con il pulsante destro del mouse sul gruppo di report da eliminare e selezionare **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="14f63-146">Right-click the report group to delete, and then select **Delete**.</span></span>
3. <span data-ttu-id="14f63-147">Quando viene visualizzato un messaggio di conferma, fare clic su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="14f63-147">When a confirmation message appears, click **Yes**.</span></span>

## <a name="report-group-tab-controls"></a><span data-ttu-id="14f63-148">Controlli della scheda Gruppo di report</span><span class="sxs-lookup"><span data-stu-id="14f63-148">Report Group tab controls</span></span>
<span data-ttu-id="14f63-149">Nella tabella riportata di seguito viene fornita una descrizione dei controlli presenti nella scheda **Gruppo di report**.</span><span class="sxs-lookup"><span data-stu-id="14f63-149">The following table describes the controls on the **Report Group** tab.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="14f63-150">Controlla</span><span class="sxs-lookup"><span data-stu-id="14f63-150">Control</span></span></th>
<th><span data-ttu-id="14f63-151">Descrizione</span><span class="sxs-lookup"><span data-stu-id="14f63-151">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="14f63-152">Ignora impostazioni società, dettagli e data dalle singole definizioni di report</span><span class="sxs-lookup"><span data-stu-id="14f63-152">Override company, detail, and date settings from individual report definitions</span></span></td>
<td><span data-ttu-id="14f63-153">Selezionare questa casella di controllo per ignorare le singole definizioni di report nel gruppo di report solo per la generazione di questi report.</span><span class="sxs-lookup"><span data-stu-id="14f63-153">Select this check box to override individual report definitions of the reports in this report group for the generation of these reports only.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="14f63-154">Nome società</span><span class="sxs-lookup"><span data-stu-id="14f63-154">Company name</span></span></td>
<td><span data-ttu-id="14f63-155">Selezionare la società da utilizzare per i report.</span><span class="sxs-lookup"><span data-stu-id="14f63-155">Select the company to use for the reports.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="14f63-156">Livello dettagli</span><span class="sxs-lookup"><span data-stu-id="14f63-156">Detail level</span></span></td>
<td><span data-ttu-id="14f63-157">Specificare il livello di dettaglio da includere nei report.</span><span class="sxs-lookup"><span data-stu-id="14f63-157">Specify the level of detail that the reports include.</span></span>
<ul>
<li><span data-ttu-id="14f63-158"><strong>Riepilogo finanziario</strong>: report di riepilogo generale.</span><span class="sxs-lookup"><span data-stu-id="14f63-158"><strong>Financial</strong> − A high-level summary report.</span></span> <span data-ttu-id="14f63-159">Non è possibile eseguire il drill-down nei conti e dimensioni, ad eccezione di quelli aggiunti tramite un albero gerarchico.</span><span class="sxs-lookup"><span data-stu-id="14f63-159">You can&#39;t drill down to accounts and dimensions, except for those accounts and dimensions that have been added through a reporting tree.</span></span></li>
<li><span data-ttu-id="14f63-160"><strong>Finanziario e conto</strong>- Un report contenente un riepilogo di alto livello e i dettagli del conto.</span><span class="sxs-lookup"><span data-stu-id="14f63-160"><strong>Financial &amp; Account</strong> − A report that contains a high-level summary and account details.</span></span></li>
<li><span data-ttu-id="14f63-161"><strong>Finanziario, conto e transazione</strong>- Un report contenente un riepilogo di alto livello e i dettagli delle transazioni.</span><span class="sxs-lookup"><span data-stu-id="14f63-161"><strong>Financial, Account, &amp; Transaction</strong> − A report that contains a high-level summary and transaction details.</span></span></li>
</ul></td>
</tr>
<tr>
<td><span data-ttu-id="14f63-162">Dati provvisori</span><span class="sxs-lookup"><span data-stu-id="14f63-162">Provisional</span></span></td>
<td><span data-ttu-id="14f63-163">Specificare i tipi di attività da includere nei report.</span><span class="sxs-lookup"><span data-stu-id="14f63-163">Specify the types of activity that the reports include.</span></span>
<ul>
<li><span data-ttu-id="14f63-164"><strong>Solo attività registrata</strong>: includere solo le transazioni e i saldi registrati nei dati finanziari.</span><span class="sxs-lookup"><span data-stu-id="14f63-164"><strong>Posted activity only</strong> − Include only the transactions and balances that are posted in your financial data.</span></span></li>
<li><span data-ttu-id="14f63-165"><strong>Attività registrata e non registrata</strong>: includere tutte le transazioni e i saldi immessi e registrati nei dati finanziari.</span><span class="sxs-lookup"><span data-stu-id="14f63-165"><strong>Posted and unposted activity</strong> − Include all the transactions and balances that are entered and posted in your financial data.</span></span></li>
<li><span data-ttu-id="14f63-166"><strong>Solo attività non registrata</strong>: includere solo le transazioni immesse nei dati finanziari ma non ancora registrate.</span><span class="sxs-lookup"><span data-stu-id="14f63-166"><strong>Unposted activity only</strong> − Include only the transactions that are entered, but not yet posted, in your financial data.</span></span></li>
</ul></td>
</tr>
<tr>
<td><span data-ttu-id="14f63-167">Includi tutte le valute di dichiarazione</span><span class="sxs-lookup"><span data-stu-id="14f63-167">Include all reporting currencies</span></span></td>
<td><span data-ttu-id="14f63-168">Le valute di dichiarazione aggiuntive configurate nel sistema Microsoft Dynamics ERP vengono elencate qui.</span><span class="sxs-lookup"><span data-stu-id="14f63-168">Any additional reporting currencies that are configured in your Microsoft Dynamics ERP system are listed here.</span></span> <span data-ttu-id="14f63-169">Selezionare questa casella di controllo per generare report aggiuntivi nelle valute indicate.</span><span class="sxs-lookup"><span data-stu-id="14f63-169">Select this check box to generate additional reports in the currencies that are indicated.</span></span> <span data-ttu-id="14f63-170">Per visualizzare questi report, in Visualizzatore Web fare clic sul pulsante <strong>Valuta</strong>, quindi selezionare una valuta.</span><span class="sxs-lookup"><span data-stu-id="14f63-170">To view these reports in the Web Viewer, click the <strong>Currency</strong> button, and then select a currency.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="14f63-171">Informazioni data non salvate con la definizione di report</span><span class="sxs-lookup"><span data-stu-id="14f63-171">Date information not saved with report definition</span></span></td>
<td><ul>
<li><span data-ttu-id="14f63-172">Periodo di base</span><span class="sxs-lookup"><span data-stu-id="14f63-172">Base period</span></span></li>
<li><span data-ttu-id="14f63-173">Anno di base</span><span class="sxs-lookup"><span data-stu-id="14f63-173">Base year</span></span></li>
<li><span data-ttu-id="14f63-174">Periodo coperto</span><span class="sxs-lookup"><span data-stu-id="14f63-174">Period covered</span></span></li>
</ul>
<span data-ttu-id="14f63-175">Solo le impostazioni del periodo di base predefinito vengono salvate con la definizione di report.</span><span class="sxs-lookup"><span data-stu-id="14f63-175">Only default base period settings are saved with the report definition.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="14f63-176">Informazioni data salvate con la definizione di report</span><span class="sxs-lookup"><span data-stu-id="14f63-176">Date information saved with report definition</span></span></td>
<td><ul>
<li><span data-ttu-id="14f63-177">Data report</span><span class="sxs-lookup"><span data-stu-id="14f63-177">Report date</span></span></li>
<li><span data-ttu-id="14f63-178">Periodo di base predefinito</span><span class="sxs-lookup"><span data-stu-id="14f63-178">Default base period</span></span></li>
</ul></td>
</tr>
<tr>
<td><span data-ttu-id="14f63-179">Report nel gruppo</span><span class="sxs-lookup"><span data-stu-id="14f63-179">Reports in group</span></span></td>
<td><span data-ttu-id="14f63-180">Aggiungere, rimuovere e riordinare i report nel gruppo di report.</span><span class="sxs-lookup"><span data-stu-id="14f63-180">Add, remove, and re-order reports in the report group.</span></span>
<ul>
<li><span data-ttu-id="14f63-181">Per aggiungere definizioni di report al gruppo di report, fare doppio clic sul gruppo di report per aprirlo, quindi fare clic su <strong>Aggiungi</strong>.</span><span class="sxs-lookup"><span data-stu-id="14f63-181">To add report definitions to the report group, double-click the report group to open it, and then click <strong>Add</strong>.</span></span> <span data-ttu-id="14f63-182">Selezionare i report da includere nel gruppo di report, quindi fare clic su <strong>OK</strong>.</span><span class="sxs-lookup"><span data-stu-id="14f63-182">Select the reports to include in the report group, and then click <strong>OK</strong>.</span></span></li>
<li><span data-ttu-id="14f63-183">Per rimuovere un report dal gruppo di report, selezionarlo, quindi fare clic su <strong>Rimuovi</strong>.</span><span class="sxs-lookup"><span data-stu-id="14f63-183">To remove a report from the report group, select it, and then click <strong>Remove</strong>.</span></span></li>
<li><span data-ttu-id="14f63-184">Per modificare l'ordine in cui i report vengono generati, selezionare un report nell'elenco e quindi fare clic su <strong>Sposta su</strong> o <strong>Sposta giù</strong>.</span><span class="sxs-lookup"><span data-stu-id="14f63-184">To modify the order that the reports are generated in, select a report in the list, and then click <strong>Move up</strong> or <strong>Move down</strong>.</span></span></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="additional-resources"></a><span data-ttu-id="14f63-185">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="14f63-185">Additional resources</span></span>

[<span data-ttu-id="14f63-186">Creazione di report finanziari</span><span class="sxs-lookup"><span data-stu-id="14f63-186">Financial reporting</span></span>](financial-reporting-intro.md)
