---
title: Configurare i nomi di campo app nell'app Magazzino
description: "In questo argomento viene descritto come definire e configurare i nomi e le priorità di campo app nell'app Magazzino in Finance and Operations."
author: MarkusFogelberg
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WHSMobileAppField, WHSMobileAppFieldPriority
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 269434
ms.assetid: 6cf3d7da-29bb-4d3d-aaf5-544ca9cc2980
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: mafoge
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 55c77c5c41b83c6b9d3e04e1e0c6382f23831502
ms.contentlocale: it-it
ms.lasthandoff: 08/29/2017

---

# <a name="configure-app-field-names-in-warehousing-app"></a><span data-ttu-id="1fe5c-103">Configurare i nomi di campo app nell'app Magazzino</span><span class="sxs-lookup"><span data-stu-id="1fe5c-103">Configure app field names in Warehousing app</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="1fe5c-104">In questo argomento viene descritto come definire e configurare i nomi e le priorità di campo app nell'app Magazzino in Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="1fe5c-104">This topic describes how to define and configure warehouse app field names and priorities in Finance and Operations.</span></span> 

<span data-ttu-id="1fe5c-105">**Nota:** questo argomento si applica alle funzionalità in Gestione magazzino.</span><span class="sxs-lookup"><span data-stu-id="1fe5c-105">**Note:** This topic applies to features in Warehouse management.</span></span> <span data-ttu-id="1fe5c-106">Non viene applicato alle funzionalità in Gestione inventario.</span><span class="sxs-lookup"><span data-stu-id="1fe5c-106">It doesn’t apply to features in Inventory management.</span></span> <span data-ttu-id="1fe5c-107">Finance and Operations - Magazzino è un'applicazione che consente di eseguire attività di magazzino.</span><span class="sxs-lookup"><span data-stu-id="1fe5c-107">Finance and Operations - Warehousing is an application that you can use to perform warehouse tasks.</span></span> <span data-ttu-id="1fe5c-108">È possibile definire e configurare i nomi di campo utilizzati nell'app, nonché configurare la priorità da assegnare ai nomi di campo.</span><span class="sxs-lookup"><span data-stu-id="1fe5c-108">You can define and configure the field names that are used in the app, as well as configure the priority to which the field names should be assigned.</span></span> <span data-ttu-id="1fe5c-109">In questo argomento viene illustrato come definire e configurare i nomi e le priorità di campo dell'app Magazzino e viene descritto come utilizzarli in Finance and Operations - Magazzino.</span><span class="sxs-lookup"><span data-stu-id="1fe5c-109">This topic explains how to define and configure these warehouse app field names and priorities, and how they are used in Finance and Operations - Warehousing.</span></span> <span data-ttu-id="1fe5c-110">Per informazioni dettagliate su come configurare la connessione in Finance and Operations - Magazzino, fare riferimento all'esercitazione [Installare e configurare Finance and Operations - Magazzino](install-configure-warehousing-app.md).</span><span class="sxs-lookup"><span data-stu-id="1fe5c-110">For detailed information about how to configure the connection to Finance and Operations  - Warehousing, refer to the tutorial [Install and configure Finance and Operations - Warehousing](install-configure-warehousing-app.md).</span></span>

<a name="configure-warehouse-app-field-names"></a><span data-ttu-id="1fe5c-111">Configurare i nomi di campo dell'app Magazzino</span><span class="sxs-lookup"><span data-stu-id="1fe5c-111">Configure warehouse app field names</span></span>
===================================

<span data-ttu-id="1fe5c-112">Quando si utilizza Finance and Operations - Magazzino sul dispositivo mobile, è possibile configurare la modalità con cui devono essere visualizzati i metadati sul dispositivo nella pagina **Nomi campo per app magazzino**.</span><span class="sxs-lookup"><span data-stu-id="1fe5c-112">When you use Finance and Operations - Warehousing on your mobile device, you can configure how metadata should be displayed on your device on the **Warehouse app field names** page.</span></span> <span data-ttu-id="1fe5c-113">In una nuova società in Finance and Operations, selezionare **Crea impostazione predefinita** per generare tutti i nomi di campo che verranno utilizzati nei flussi di lavoro del dispositivo mobile di magazzino, quindi assegnare loro una modalità e un tipo di input preferiti.</span><span class="sxs-lookup"><span data-stu-id="1fe5c-113">In a new company in Finance and Operations, select **Create default setup** to generate all field names that will be used in the warehouse mobile device workflows, and then assign a preferred input mode and input type to them.</span></span> <span data-ttu-id="1fe5c-114">Dopo aver generato tutti i nomi di campo, è possibile selezionare le seguenti opzioni di input.</span><span class="sxs-lookup"><span data-stu-id="1fe5c-114">After you have generated all field names, you can select the following input options.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1fe5c-115">Opzione</span><span class="sxs-lookup"><span data-stu-id="1fe5c-115">Option</span></span></th>
<th><span data-ttu-id="1fe5c-116">descrizione</span><span class="sxs-lookup"><span data-stu-id="1fe5c-116">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="1fe5c-117">Modalità di input preferita</span><span class="sxs-lookup"><span data-stu-id="1fe5c-117">Preferred input mode</span></span></td>
<td><span data-ttu-id="1fe5c-118">Questa opzione definisce se un campo di scansione o un campo di input di immissione manuale deve essere visualizzato per il nome di campo selezionato.</span><span class="sxs-lookup"><span data-stu-id="1fe5c-118">This option defines whether a scanning field or a manual entry input field should be shown for the selected field name.</span></span> <span data-ttu-id="1fe5c-119">Questa opzione è utile per distinguere i campi a seconda che vengano utilizzati o meno codici a barre per il campo.</span><span class="sxs-lookup"><span data-stu-id="1fe5c-119">This is useful to distinguish fields depending on if barcodes are used for the field.</span></span> <span data-ttu-id="1fe5c-120"><strong>Nota:</strong> per i nomi di campo con modalità di input preferita impostata su <strong>Scansione</strong>, è possibile immettere manualmente le informazioni se il codice a barre è illeggibile o danneggiato.</span><span class="sxs-lookup"><span data-stu-id="1fe5c-120"><strong>Note:</strong> For field names with preferred input mode set to <strong>Scanning</strong>, you can enter information manually if the barcode is unreadable or damaged.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="1fe5c-121">Tipo di input</span><span class="sxs-lookup"><span data-stu-id="1fe5c-121">Input type</span></span></td>
<td><span data-ttu-id="1fe5c-122">Questa opzione definisce il tipo di input da utilizzare per il nome di campo selezionato.</span><span class="sxs-lookup"><span data-stu-id="1fe5c-122">This option defines what input type should be used for the selected field name.</span></span> <span data-ttu-id="1fe5c-123">Sono disponibili quattro opzioni:</span><span class="sxs-lookup"><span data-stu-id="1fe5c-123">Four options are available:</span></span>
<ul>
<li><span data-ttu-id="1fe5c-124"><strong>Selezione</strong> - Contiene un elenco di opzioni tra cui scegliere.</span><span class="sxs-lookup"><span data-stu-id="1fe5c-124"><strong>Selection</strong> - Contains a list of options to choose from.</span></span> <span data-ttu-id="1fe5c-125">I nomi di campo con questa opzione non sono modificabili.</span><span class="sxs-lookup"><span data-stu-id="1fe5c-125">Field names with this option are not editable.</span></span></li>
<li><span data-ttu-id="1fe5c-126"><strong>Data</strong> - I nomi di campo specificati come data verranno visualizzati in un formato data con l'etichetta.</span><span class="sxs-lookup"><span data-stu-id="1fe5c-126"><strong>Date</strong> - Field names specified as date will show a date format with the label.</span></span> <span data-ttu-id="1fe5c-127">Ciò consente ai lavoratori di magazzino di individuare in quale formato immettere la data.</span><span class="sxs-lookup"><span data-stu-id="1fe5c-127">This helps warehouse workers see in which format to enter the date.</span></span> <span data-ttu-id="1fe5c-128">I nomi di campo con questa opzione non sono modificabili.</span><span class="sxs-lookup"><span data-stu-id="1fe5c-128">Field names with this option are not editable.</span></span></li>
<li><span data-ttu-id="1fe5c-129"><strong>Ordine alfabetico</strong> - Se l'opzione è selezionata, la tastiera del dispositivo verrà utilizzata quando si immettono le informazioni manualmente nell'app.</span><span class="sxs-lookup"><span data-stu-id="1fe5c-129"><strong>Alpha</strong> - If selected, the device keyboard will be used when entering information manually in the app.</span></span> <span data-ttu-id="1fe5c-130">L'esperienza della tastiera può essere modificata in base al dispositivo utilizzato.</span><span class="sxs-lookup"><span data-stu-id="1fe5c-130">The keyboard experience can be changed depending on which device is used.</span></span></li>
<li><span data-ttu-id="1fe5c-131"><strong>Numerico</strong> - Per i nomi di campo che utilizzano l'input solo numerico, è possibile selezionare questa opzione per visualizzare una tastiera numerica personalizzata con il campo di input anziché la tastiera del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="1fe5c-131"><strong>Numeric</strong> - For field names that use numeric input only, you can select this option to display a custom numeric keypad with the input field instead of the device keyboard.</span></span></li>
</ul></td>
</tr>
</tbody>
</table>

<a name="configure-warehouse-app-field-priority"></a><span data-ttu-id="1fe5c-132">Configurare la priorità di campo nell'app Magazzino</span><span class="sxs-lookup"><span data-stu-id="1fe5c-132">Configure warehouse app field priority</span></span>
======================================

<span data-ttu-id="1fe5c-133">Nella pagina **Priorità campo per app magazzino**, è possibile inserire i nomi di campo in gruppi di priorità diversi.</span><span class="sxs-lookup"><span data-stu-id="1fe5c-133">On the **Warehouse app field priority** page, you can put field names into different priority groups.</span></span> <span data-ttu-id="1fe5c-134">Ciò consente di scegliere le informazioni da visualizzare nella pagina dell'attività principale quando i lavoratori di magazzino eseguono attività mediante l'app.</span><span class="sxs-lookup"><span data-stu-id="1fe5c-134">This makes it possible to decide what information should be displayed on the main task page when warehouse workers perform tasks using the app.</span></span> <span data-ttu-id="1fe5c-135">Se si fa clic su **Crea impostazione predefinita**, verrà generato un set predefinito di gruppi di priorità.</span><span class="sxs-lookup"><span data-stu-id="1fe5c-135">If you click **Create default setup**, a default set of priority groups will be generated.</span></span> <span data-ttu-id="1fe5c-136">È possibile creare un numero illimitato di gruppi di priorità, se necessario, ma solo tre gruppi di priorità verranno visualizzati nella pagina dell'attività.</span><span class="sxs-lookup"><span data-stu-id="1fe5c-136">It is possible to create as many priority groups as needed, but only three priority groups will be shown on the task page.</span></span> <span data-ttu-id="1fe5c-137">Quando Finance and Operations invia i metadati all'app, a ogni campo verrà assegnata una priorità relativa a seconda del rispettivo gruppo di priorità e l'app visualizzerà i primi tre gruppi di priorità contenuti nei metadati nella pagina dell'attività.</span><span class="sxs-lookup"><span data-stu-id="1fe5c-137">When Finance and Operations sends metadata to the app, it will assign each field a relative priority depending on its priority group, and the app will display the first three priority groups contained in the metadata on the task page.</span></span> <span data-ttu-id="1fe5c-138">Il resto dei metadati aggiuntivi verranno visualizzati in una pagina dei dettagli secondaria.</span><span class="sxs-lookup"><span data-stu-id="1fe5c-138">The rest of the overflowing metadata will be displayed on a secondary details page.</span></span> <span data-ttu-id="1fe5c-139">Nella tabella seguente viene illustrato un esempio di cinque gruppi di priorità.</span><span class="sxs-lookup"><span data-stu-id="1fe5c-139">The following table shows an example of five priority groups.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1fe5c-140">Gruppo di priorità</span><span class="sxs-lookup"><span data-stu-id="1fe5c-140">Priority group</span></span></th>
<th><span data-ttu-id="1fe5c-141">Campi assegnati</span><span class="sxs-lookup"><span data-stu-id="1fe5c-141">Assigned fields</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td> <span data-ttu-id="1fe5c-142">Priorità 10</span><span class="sxs-lookup"><span data-stu-id="1fe5c-142">Priority 10</span></span></td>
<td><ul>
<li><span data-ttu-id="1fe5c-143">Articolo</span><span class="sxs-lookup"><span data-stu-id="1fe5c-143">Item</span></span></li>
<li><span data-ttu-id="1fe5c-144">Quantità</span><span class="sxs-lookup"><span data-stu-id="1fe5c-144">Quantity</span></span></li>
<li><span data-ttu-id="1fe5c-145">Unità di misura</span><span class="sxs-lookup"><span data-stu-id="1fe5c-145">Unit of measure</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td> <span data-ttu-id="1fe5c-146">Priorità 20</span><span class="sxs-lookup"><span data-stu-id="1fe5c-146">Priority 20</span></span></td>
<td><ul>
<li><span data-ttu-id="1fe5c-147">Posizione cluster</span><span class="sxs-lookup"><span data-stu-id="1fe5c-147">Cluster position</span></span></li>
<li><span data-ttu-id="1fe5c-148">Cluster</span><span class="sxs-lookup"><span data-stu-id="1fe5c-148">Cluster</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td> <span data-ttu-id="1fe5c-149">Priorità 30</span><span class="sxs-lookup"><span data-stu-id="1fe5c-149">Priority 30</span></span></td>
<td><ul>
<li><span data-ttu-id="1fe5c-150">Descrizione articolo</span><span class="sxs-lookup"><span data-stu-id="1fe5c-150">Item description</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td> <span data-ttu-id="1fe5c-151">Priorità 40</span><span class="sxs-lookup"><span data-stu-id="1fe5c-151">Priority 40</span></span></td>
<td><ul>
<li><span data-ttu-id="1fe5c-152">Configurazione</span><span class="sxs-lookup"><span data-stu-id="1fe5c-152">Configuration</span></span></li>
<li><span data-ttu-id="1fe5c-153">Colore</span><span class="sxs-lookup"><span data-stu-id="1fe5c-153">Color</span></span></li>
<li><span data-ttu-id="1fe5c-154">Dimensioni</span><span class="sxs-lookup"><span data-stu-id="1fe5c-154">Size</span></span></li>
<li><span data-ttu-id="1fe5c-155">Stile</span><span class="sxs-lookup"><span data-stu-id="1fe5c-155">Style</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td> <span data-ttu-id="1fe5c-156">Priorità 50</span><span class="sxs-lookup"><span data-stu-id="1fe5c-156">Priority 50</span></span></td>
<td><ul>
<li><span data-ttu-id="1fe5c-157">Posizione</span><span class="sxs-lookup"><span data-stu-id="1fe5c-157">Location</span></span></li>
<li><span data-ttu-id="1fe5c-158">Targa</span><span class="sxs-lookup"><span data-stu-id="1fe5c-158">License plate</span></span></li>
</ul></td>
</tr>
</tbody>
</table>

<span data-ttu-id="1fe5c-159">Ad esempio, quando un lavoratore di magazzino esegue un'attività su un dispositivo mobile, se i metadati visualizzati nell'app sono costituiti dai seguenti campi:</span><span class="sxs-lookup"><span data-stu-id="1fe5c-159">For example, when a warehouse worker is performing a task on a mobile device, if the metadata that will be displayed in the app consists of the following fields:</span></span>

-   <span data-ttu-id="1fe5c-160">Articolo</span><span class="sxs-lookup"><span data-stu-id="1fe5c-160">Item</span></span>
-   <span data-ttu-id="1fe5c-161">Quantità</span><span class="sxs-lookup"><span data-stu-id="1fe5c-161">Quantity</span></span>
-   <span data-ttu-id="1fe5c-162">Unità di misura</span><span class="sxs-lookup"><span data-stu-id="1fe5c-162">Unit of measure</span></span>
-   <span data-ttu-id="1fe5c-163">Descrizione articolo</span><span class="sxs-lookup"><span data-stu-id="1fe5c-163">Item description</span></span>
-   <span data-ttu-id="1fe5c-164">Dimensione e ubicazione</span><span class="sxs-lookup"><span data-stu-id="1fe5c-164">Size and Location</span></span>

<span data-ttu-id="1fe5c-165">In base alla priorità di campo dell'app Magazzino impostata nella tabella precedente, le seguenti 3 righe di informazioni verranno visualizzate nella pagina dell'attività:</span><span class="sxs-lookup"><span data-stu-id="1fe5c-165">Based on the warehouse app field priority set up in the table above, the following 3 rows of information will be displayed on the task page:</span></span>

-   <span data-ttu-id="1fe5c-166">Riga 1: Articolo, Quantità, Unità di misura</span><span class="sxs-lookup"><span data-stu-id="1fe5c-166">Row 1: Item, Quantity, Unit of measure</span></span>
-   <span data-ttu-id="1fe5c-167">Riga 2: Descrizione dell'articolo</span><span class="sxs-lookup"><span data-stu-id="1fe5c-167">Row 2: Item description</span></span>
-   <span data-ttu-id="1fe5c-168">Riga 3: Dimensione</span><span class="sxs-lookup"><span data-stu-id="1fe5c-168">Row 3: Size</span></span>

<span data-ttu-id="1fe5c-169">I metadati rimanenti, ad esempio l'ubicazione, non verranno visualizzati nella pagina dell'attività, ma verranno visualizzati in una pagina dei dettagli.</span><span class="sxs-lookup"><span data-stu-id="1fe5c-169">The remaining metadata, for example, Location, will not be displayed on the task page, but will be displayed on a details page.</span></span> <span data-ttu-id="1fe5c-170">Per ulteriori informazioni e per visualizzare esempi dell'interfaccia utente, fare riferimento al post di blog [Presentazione di Finance and Operations - Magazzino](https://blogs.msdn.microsoft.com/dynamicsaxscm/2017/01/20/announcing-dynamics-365-for-operations-warehousing/).</span><span class="sxs-lookup"><span data-stu-id="1fe5c-170">To learn more and see examples of the user interface, refer to the blog post [Announcing Finance and Operations - Warehousing](https://blogs.msdn.microsoft.com/dynamicsaxscm/2017/01/20/announcing-dynamics-365-for-operations-warehousing/).</span></span>

<a name="see-also"></a><span data-ttu-id="1fe5c-171">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1fe5c-171">See also</span></span>
--------

[<span data-ttu-id="1fe5c-172">Installare e configurare Microsoft Dynamics 365 for Finance and Operations - Magazzino</span><span class="sxs-lookup"><span data-stu-id="1fe5c-172">Install and configure Microsoft Dynamics 365 for Finance and Operations – Warehousing</span></span>](install-configure-warehousing-app.md)




