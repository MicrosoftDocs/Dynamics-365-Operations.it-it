---
title: Configurare i nomi di campo app nell'app Magazzino
description: In questo argomento viene descritto come definire e configurare i nomi e le priorità di campo app in Dynamics 365 Supply Chain Management.
author: MarkusFogelberg
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSMobileAppField, WHSMobileAppFieldPriority
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 269434
ms.assetid: 6cf3d7da-29bb-4d3d-aaf5-544ca9cc2980
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: mafoge
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: f9b02b93895757580b323a4cd891909d5551ea55
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2020
ms.locfileid: "3205761"
---
# <a name="configure-app-field-names-in-warehousing-app"></a><span data-ttu-id="58263-103">Configurare i nomi di campo app nell'app Magazzino</span><span class="sxs-lookup"><span data-stu-id="58263-103">Configure app field names in Warehousing app</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="58263-104">In questo argomento viene descritto come definire e configurare i nomi e le priorità di campo app in Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="58263-104">This topic describes how to define and configure warehouse app field names and priorities in Dynamics 365 Supply Chain Management.</span></span> 

> [!NOTE]
> <span data-ttu-id="58263-105">Questo argomento si applica alle funzionalità in Gestione magazzino.</span><span class="sxs-lookup"><span data-stu-id="58263-105">This topic applies to features in Warehouse management.</span></span> <span data-ttu-id="58263-106">Non viene applicato alle funzionalità in Gestione inventario.</span><span class="sxs-lookup"><span data-stu-id="58263-106">It doesn’t apply to features in Inventory management.</span></span> <span data-ttu-id="58263-107">Magazzino è un'applicazione che consente di eseguire attività di magazzino.</span><span class="sxs-lookup"><span data-stu-id="58263-107">Warehousing is an application that you can use to perform warehouse tasks.</span></span> <span data-ttu-id="58263-108">È possibile definire e configurare i nomi di campo utilizzati nell'app, nonché configurare la priorità da assegnare ai nomi di campo.</span><span class="sxs-lookup"><span data-stu-id="58263-108">You can define and configure the field names that are used in the app, as well as configure the priority to which the field names should be assigned.</span></span> <span data-ttu-id="58263-109">In questo argomento viene illustrato come definire e configurare i nomi e le priorità di campo dell'app Magazzino e viene descritto come utilizzarli in Magazzino.</span><span class="sxs-lookup"><span data-stu-id="58263-109">This topic explains how to define and configure these warehouse app field names and priorities, and how they are used in Warehousing.</span></span> <span data-ttu-id="58263-110">Per informazioni dettagliate su come configurare la connessione in Magazzino, fare riferimento all'esercitazione [Panoramica sull'installazione e sulla configurazione dell'app del magazzino](install-configure-warehousing-app.md).</span><span class="sxs-lookup"><span data-stu-id="58263-110">For detailed information about how to configure the connection to FWarehousing, refer to the tutorial [Install and configure the Warehousing app overview](install-configure-warehousing-app.md).</span></span>

## <a name="configure-warehouse-app-field-names"></a><span data-ttu-id="58263-111">Configurare i nomi di campo dell'app Magazzino</span><span class="sxs-lookup"><span data-stu-id="58263-111">Configure warehouse app field names</span></span>

<span data-ttu-id="58263-112">Quando si utilizza Magazzino sul dispositivo mobile, è possibile configurare la modalità di visualizzazione dei metadati sul dispositivo nella pagina **Nomi campo per app magazzino**.</span><span class="sxs-lookup"><span data-stu-id="58263-112">When you use Warehousing on your mobile device, you can configure how metadata should be displayed on your device on the **Warehouse app field names** page.</span></span> <span data-ttu-id="58263-113">In una nuova società, selezionare **Crea impostazione predefinita** per generare tutti i nomi di campo che verranno utilizzati nei flussi di lavoro del dispositivo mobile di magazzino, quindi assegnare loro una modalità e un tipo di input preferiti.</span><span class="sxs-lookup"><span data-stu-id="58263-113">In a new company, select **Create default setup** to generate all field names that will be used in the warehouse mobile device workflows, and then assign a preferred input mode and input type to them.</span></span> <span data-ttu-id="58263-114">Dopo aver generato tutti i nomi di campo, è possibile selezionare le seguenti opzioni di input.</span><span class="sxs-lookup"><span data-stu-id="58263-114">After you have generated all field names, you can select the following input options.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="58263-115">Opzione</span><span class="sxs-lookup"><span data-stu-id="58263-115">Option</span></span></th>
<th><span data-ttu-id="58263-116">descrizione</span><span class="sxs-lookup"><span data-stu-id="58263-116">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="58263-117">Modalità di input preferita</span><span class="sxs-lookup"><span data-stu-id="58263-117">Preferred input mode</span></span></td>
<td><span data-ttu-id="58263-118">Questa opzione definisce se un campo di scansione o un campo di input di immissione manuale deve essere visualizzato per il nome di campo selezionato.</span><span class="sxs-lookup"><span data-stu-id="58263-118">This option defines whether a scanning field or a manual entry input field should be shown for the selected field name.</span></span> <span data-ttu-id="58263-119">Questa opzione è utile per distinguere i campi a seconda che vengano utilizzati o meno codici a barre per il campo.</span><span class="sxs-lookup"><span data-stu-id="58263-119">This is useful to distinguish fields depending on if barcodes are used for the field.</span></span> <span data-ttu-id="58263-120"><strong>Nota:</strong> per i nomi di campo con modalità di input preferita impostata su <strong>Scansione</strong>, è possibile immettere manualmente le informazioni se il codice a barre è illeggibile o danneggiato.</span><span class="sxs-lookup"><span data-stu-id="58263-120"><strong>Note:</strong> For field names with preferred input mode set to <strong>Scanning</strong>, you can enter information manually if the barcode is unreadable or damaged.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="58263-121">Tipo di input</span><span class="sxs-lookup"><span data-stu-id="58263-121">Input type</span></span></td>
<td><span data-ttu-id="58263-122">Questa opzione definisce il tipo di input da utilizzare per il nome di campo selezionato.</span><span class="sxs-lookup"><span data-stu-id="58263-122">This option defines what input type should be used for the selected field name.</span></span> <span data-ttu-id="58263-123">Sono disponibili quattro opzioni:</span><span class="sxs-lookup"><span data-stu-id="58263-123">Four options are available:</span></span>
<ul>
<li><span data-ttu-id="58263-124"><strong>Selezione</strong> - Contiene un elenco di opzioni tra cui scegliere.</span><span class="sxs-lookup"><span data-stu-id="58263-124"><strong>Selection</strong> - Contains a list of options to choose from.</span></span> <span data-ttu-id="58263-125">I nomi di campo con questa opzione non sono modificabili.</span><span class="sxs-lookup"><span data-stu-id="58263-125">Field names with this option are not editable.</span></span></li>
<li><span data-ttu-id="58263-126"><strong>Data</strong> - I nomi di campo specificati come data verranno visualizzati in un formato data con l'etichetta.</span><span class="sxs-lookup"><span data-stu-id="58263-126"><strong>Date</strong> - Field names specified as date will show a date format with the label.</span></span> <span data-ttu-id="58263-127">Ciò consente ai lavoratori di magazzino di individuare in quale formato immettere la data.</span><span class="sxs-lookup"><span data-stu-id="58263-127">This helps warehouse workers see in which format to enter the date.</span></span> <span data-ttu-id="58263-128">I nomi di campo con questa opzione non sono modificabili.</span><span class="sxs-lookup"><span data-stu-id="58263-128">Field names with this option are not editable.</span></span></li>
<li><span data-ttu-id="58263-129"><strong>Ordine alfabetico</strong> - Se l'opzione è selezionata, la tastiera del dispositivo verrà utilizzata quando si immettono le informazioni manualmente nell'app.</span><span class="sxs-lookup"><span data-stu-id="58263-129"><strong>Alpha</strong> - If selected, the device keyboard will be used when entering information manually in the app.</span></span> <span data-ttu-id="58263-130">L'esperienza della tastiera può essere modificata in base al dispositivo utilizzato.</span><span class="sxs-lookup"><span data-stu-id="58263-130">The keyboard experience can be changed depending on which device is used.</span></span></li>
<li><span data-ttu-id="58263-131"><strong>Numerico</strong> - Per i nomi di campo che utilizzano l'input solo numerico, è possibile selezionare questa opzione per visualizzare una tastiera numerica personalizzata con il campo di input anziché la tastiera del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="58263-131"><strong>Numeric</strong> - For field names that use numeric input only, you can select this option to display a custom numeric keypad with the input field instead of the device keyboard.</span></span></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="configure-warehouse-app-field-priority"></a><span data-ttu-id="58263-132">Configurare la priorità di campo nell'app Magazzino</span><span class="sxs-lookup"><span data-stu-id="58263-132">Configure warehouse app field priority</span></span>

<span data-ttu-id="58263-133">Nella pagina **Priorità campo per app magazzino**, è possibile inserire i nomi di campo in gruppi di priorità diversi.</span><span class="sxs-lookup"><span data-stu-id="58263-133">On the **Warehouse app field priority** page, you can put field names into different priority groups.</span></span> <span data-ttu-id="58263-134">Ciò consente di scegliere le informazioni da visualizzare nella pagina dell'attività principale quando i lavoratori di magazzino eseguono attività mediante l'app.</span><span class="sxs-lookup"><span data-stu-id="58263-134">This makes it possible to decide what information should be displayed on the main task page when warehouse workers perform tasks using the app.</span></span> <span data-ttu-id="58263-135">Se si fa clic su **Crea impostazione predefinita**, verrà generato un set predefinito di gruppi di priorità.</span><span class="sxs-lookup"><span data-stu-id="58263-135">If you click **Create default setup**, a default set of priority groups will be generated.</span></span> <span data-ttu-id="58263-136">È possibile creare un numero illimitato di gruppi di priorità, se necessario, ma solo tre gruppi di priorità verranno visualizzati nella pagina dell'attività.</span><span class="sxs-lookup"><span data-stu-id="58263-136">It is possible to create as many priority groups as needed, but only three priority groups will be shown on the task page.</span></span> <span data-ttu-id="58263-137">Quando il sistema invia metadati all'app, a ogni campo verrà assegnata una priorità relativa a seconda del rispettivo gruppo di priorità e l'app visualizzerà i primi tre gruppi di priorità contenuti nei metadati nella pagina dell'attività.</span><span class="sxs-lookup"><span data-stu-id="58263-137">When the system sends metadata to the app, it will assign each field a relative priority depending on its priority group, and the app will display the first three priority groups contained in the metadata on the task page.</span></span> <span data-ttu-id="58263-138">Il resto dei metadati aggiuntivi verranno visualizzati in una pagina dei dettagli secondaria.</span><span class="sxs-lookup"><span data-stu-id="58263-138">The rest of the overflowing metadata will be displayed on a secondary details page.</span></span> <span data-ttu-id="58263-139">Nella tabella seguente viene illustrato un esempio di cinque gruppi di priorità.</span><span class="sxs-lookup"><span data-stu-id="58263-139">The following table shows an example of five priority groups.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="58263-140">Gruppo di priorità</span><span class="sxs-lookup"><span data-stu-id="58263-140">Priority group</span></span></th>
<th><span data-ttu-id="58263-141">Campi assegnati</span><span class="sxs-lookup"><span data-stu-id="58263-141">Assigned fields</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td> <span data-ttu-id="58263-142">Priorità 10</span><span class="sxs-lookup"><span data-stu-id="58263-142">Priority 10</span></span></td>
<td><ul>
<li><span data-ttu-id="58263-143">Articolo</span><span class="sxs-lookup"><span data-stu-id="58263-143">Item</span></span></li>
<li><span data-ttu-id="58263-144">Quantità</span><span class="sxs-lookup"><span data-stu-id="58263-144">Quantity</span></span></li>
<li><span data-ttu-id="58263-145">Unità di misura</span><span class="sxs-lookup"><span data-stu-id="58263-145">Unit of measure</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td> <span data-ttu-id="58263-146">Priorità 20</span><span class="sxs-lookup"><span data-stu-id="58263-146">Priority 20</span></span></td>
<td><ul>
<li><span data-ttu-id="58263-147">Posizione cluster</span><span class="sxs-lookup"><span data-stu-id="58263-147">Cluster position</span></span></li>
<li><span data-ttu-id="58263-148">Cluster</span><span class="sxs-lookup"><span data-stu-id="58263-148">Cluster</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td> <span data-ttu-id="58263-149">Priorità 30</span><span class="sxs-lookup"><span data-stu-id="58263-149">Priority 30</span></span></td>
<td><ul>
<li><span data-ttu-id="58263-150">Descrizione articolo</span><span class="sxs-lookup"><span data-stu-id="58263-150">Item description</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td> <span data-ttu-id="58263-151">Priorità 40</span><span class="sxs-lookup"><span data-stu-id="58263-151">Priority 40</span></span></td>
<td><ul>
<li><span data-ttu-id="58263-152">Configurazione</span><span class="sxs-lookup"><span data-stu-id="58263-152">Configuration</span></span></li>
<li><span data-ttu-id="58263-153">Colore</span><span class="sxs-lookup"><span data-stu-id="58263-153">Color</span></span></li>
<li><span data-ttu-id="58263-154">Dimensioni</span><span class="sxs-lookup"><span data-stu-id="58263-154">Size</span></span></li>
<li><span data-ttu-id="58263-155">Stile</span><span class="sxs-lookup"><span data-stu-id="58263-155">Style</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td> <span data-ttu-id="58263-156">Priorità 50</span><span class="sxs-lookup"><span data-stu-id="58263-156">Priority 50</span></span></td>
<td><ul>
<li><span data-ttu-id="58263-157">Posizione</span><span class="sxs-lookup"><span data-stu-id="58263-157">Location</span></span></li>
<li><span data-ttu-id="58263-158">Targa</span><span class="sxs-lookup"><span data-stu-id="58263-158">License plate</span></span></li>
</ul></td>
</tr>
</tbody>
</table>

<span data-ttu-id="58263-159">Ad esempio, quando un lavoratore di magazzino esegue un'attività su un dispositivo mobile, se i metadati visualizzati nell'app sono costituiti dai seguenti campi:</span><span class="sxs-lookup"><span data-stu-id="58263-159">For example, when a warehouse worker is performing a task on a mobile device, if the metadata that will be displayed in the app consists of the following fields:</span></span>

-   <span data-ttu-id="58263-160">Articolo</span><span class="sxs-lookup"><span data-stu-id="58263-160">Item</span></span>
-   <span data-ttu-id="58263-161">Quantità</span><span class="sxs-lookup"><span data-stu-id="58263-161">Quantity</span></span>
-   <span data-ttu-id="58263-162">Unità di misura</span><span class="sxs-lookup"><span data-stu-id="58263-162">Unit of measure</span></span>
-   <span data-ttu-id="58263-163">Descrizione articolo</span><span class="sxs-lookup"><span data-stu-id="58263-163">Item description</span></span>
-   <span data-ttu-id="58263-164">Dimensione e ubicazione</span><span class="sxs-lookup"><span data-stu-id="58263-164">Size and Location</span></span>

<span data-ttu-id="58263-165">In base alla priorità di campo dell'app Magazzino impostata nella tabella precedente, le seguenti 3 righe di informazioni verranno visualizzate nella pagina dell'attività:</span><span class="sxs-lookup"><span data-stu-id="58263-165">Based on the warehouse app field priority set up in the table above, the following 3 rows of information will be displayed on the task page:</span></span>

-   <span data-ttu-id="58263-166">Riga 1: Articolo, Quantità, Unità di misura</span><span class="sxs-lookup"><span data-stu-id="58263-166">Row 1: Item, Quantity, Unit of measure</span></span>
-   <span data-ttu-id="58263-167">Riga 2: Descrizione dell'articolo</span><span class="sxs-lookup"><span data-stu-id="58263-167">Row 2: Item description</span></span>
-   <span data-ttu-id="58263-168">Riga 3: Dimensione</span><span class="sxs-lookup"><span data-stu-id="58263-168">Row 3: Size</span></span>

<span data-ttu-id="58263-169">I metadati rimanenti, ad esempio l'ubicazione, non verranno visualizzati nella pagina dell'attività, ma verranno visualizzati in una pagina dei dettagli.</span><span class="sxs-lookup"><span data-stu-id="58263-169">The remaining metadata, for example, Location, will not be displayed on the task page, but will be displayed on a details page.</span></span> <span data-ttu-id="58263-170">Per ulteriori informazioni e per visualizzare esempi dell'interfaccia utente, fare riferimento al post di blog [Presentazione di Finance and Operations - Magazzino](https://blogs.msdn.microsoft.com/dynamicsaxscm/2017/01/20/announcing-dynamics-365-for-operations-warehousing/).</span><span class="sxs-lookup"><span data-stu-id="58263-170">To learn more and see examples of the user interface, refer to the blog post [Announcing Finance and Operations - Warehousing](https://blogs.msdn.microsoft.com/dynamicsaxscm/2017/01/20/announcing-dynamics-365-for-operations-warehousing/).</span></span>

<a name="additional-resources"></a><span data-ttu-id="58263-171">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="58263-171">Additional resources</span></span>
--------

[<span data-ttu-id="58263-172">Panoramica sull'installazione e sulla configurazione dell'app Magazzino</span><span class="sxs-lookup"><span data-stu-id="58263-172">Install and configure the Warehousing app overview</span></span>](install-configure-warehousing-app.md)
