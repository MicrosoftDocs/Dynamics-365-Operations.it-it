---
title: Novità o modifiche introdotte in Dynamics AX versione applicazione 7.0.1 (maggio 2016)
description: Questo articolo descrive le funzionalità nuove o modificate in Microsoft Dynamics AX versione applicazione 7.0.1. Questa versione è stata rilasciata nel maggio 2016 e ha numero di build 7.0.1265.23014.
author: sericks007
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ROBOTS: NOINDEX, NOFOLLOW
audience: Application User, Developer, IT Pro
ms.reviewer: josaw
ms.custom: 91213
ms.assetid: f0bbc78f-87fc-40e9-b46a-6655893f69be
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: c4d762a6750a295b91a1d146b7bf0ae750e2e9bd
ms.sourcegitcommit: 2f766e5bb8574d250f19180ff2e101e895097713
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2021
ms.locfileid: "5923191"
---
# <a name="whats-new-or-changed-in-dynamics-ax-application-version-701-may-2016"></a><span data-ttu-id="61fdd-104">Novità o modifiche introdotte in Dynamics AX versione applicazione 7.0.1 (maggio 2016)</span><span class="sxs-lookup"><span data-stu-id="61fdd-104">What's new or changed in Dynamics AX application version 7.0.1 (May 2016)</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="61fdd-105">Questo articolo descrive le funzionalità nuove o modificate in Microsoft Dynamics AX versione applicazione 7.0.1.</span><span class="sxs-lookup"><span data-stu-id="61fdd-105">This article describes features that are either new or changed in Microsoft Dynamics AX application version 7.0.1.</span></span> <span data-ttu-id="61fdd-106">Questa versione è stata rilasciata nel maggio 2016 e ha numero di build 7.0.1265.23014.</span><span class="sxs-lookup"><span data-stu-id="61fdd-106">This version was released in May 2016 and has a build number of 7.0.1265.23014.</span></span>

## <a name="electronic-reporting-er"></a><span data-ttu-id="61fdd-107">Creazione di report elettronici (ER)</span><span class="sxs-lookup"><span data-stu-id="61fdd-107">Electronic reporting (ER)</span></span>

| <span data-ttu-id="61fdd-108">Operazioni che è possibile effettuare</span><span class="sxs-lookup"><span data-stu-id="61fdd-108">What can you do?</span></span> | <span data-ttu-id="61fdd-109">Perché questo è importante?</span><span class="sxs-lookup"><span data-stu-id="61fdd-109">Why is this important?</span></span> |
|------------------|------------------------|
| <span data-ttu-id="61fdd-110">Configurare una finestra di dialogo in fase di esecuzione per la progettazione di report elettronici (ER), in modo che gli utenti possono selezionare le dimensioni finanziarie che desiderano.</span><span class="sxs-lookup"><span data-stu-id="61fdd-110">Configure a run-time dialog box for designing Electronic reporting (ER) reports, so that users can select the financial dimensions that they want.</span></span> | <span data-ttu-id="61fdd-111">In fase di esecuzione nella finestra di dialogo per l'esecuzione di un report ER, gli utenti possono selezionare più dimensioni finanziarie.</span><span class="sxs-lookup"><span data-stu-id="61fdd-111">At run time, in the dialog box for running an ER report, users can select multiple financial dimensions.</span></span> <span data-ttu-id="61fdd-112">I dettagli delle dimensioni finanziarie selezionate verranno visualizzati nel documento elettronico generato.</span><span class="sxs-lookup"><span data-stu-id="61fdd-112">The details of the selected financial dimensions will be displayed in the electronic document that is generated.</span></span> |
| <span data-ttu-id="61fdd-113">Configurare l'accesso a più dimensioni finanziarie durante la progettazione di un report ER, tramite un solo mapping all'origine dati desiderata.</span><span class="sxs-lookup"><span data-stu-id="61fdd-113">Configure access to multiple financial dimensions during the design of an ER report, via a single mapping to the desired data source.</span></span> | <span data-ttu-id="61fdd-114">La stessa configurazione di report ER può essere utilizzata per generare documenti elettronici che presentano i dati transazionali con i dettagli delle dimensioni finanziarie, indipendentemente dal numero di dimensioni finanziarie che sono selezionate dall'utente o configurate per la persona giuridica o l'istanza corrente.</span><span class="sxs-lookup"><span data-stu-id="61fdd-114">The same ER report configuration can be used to generate electronic documents that present transactional data together with details of financial dimensions, regardless of the number of financial dimensions that are either selected by the user or configured for the current legal entity or instance.</span></span> |
| <span data-ttu-id="61fdd-115">Configurare un report ER per immettere dati in colonne generate in modo dinamico di un documento elettronico che viene creato in formato foglio di lavoro OPENXML.</span><span class="sxs-lookup"><span data-stu-id="61fdd-115">Configure an ER report to enter data in dynamically generated columns of an electronic document that is created in OPENXML worksheet format.</span></span> | <span data-ttu-id="61fdd-116">Un report ER può immettere dati in un foglio di lavoro OPENXML che viene generato, tramite colonne che si replicano in senso orizzontale.</span><span class="sxs-lookup"><span data-stu-id="61fdd-116">An ER report can enter data in an OPENXML worksheet that is generated, via horizontally replicating columns.</span></span> <span data-ttu-id="61fdd-117">Pertanto, la stessa configurazione di report ER può essere riutilizzata per generare documenti elettronici che hanno un diverso numero di colonne generate dinamicamente.</span><span class="sxs-lookup"><span data-stu-id="61fdd-117">Therefore, the same ER report configuration can be reused to generate electronic documents that have a different number of dynamically generated columns.</span></span> |
| <span data-ttu-id="61fdd-118">Configurare le destinazioni di ER in modo che il risultato di output di un formato sia diretto alla destinazione specifica: file, posta elettronica o archivio (cartella di Microsoft SharePoint o Archiviazione di Microsoft Azure).</span><span class="sxs-lookup"><span data-stu-id="61fdd-118">Configure ER destinations so that the output result of a format is directed to specific destination: file, email, or archive (Microsoft SharePoint folder or Microsoft Azure Storage).</span></span> | <span data-ttu-id="61fdd-119">In precedenza, quando si eseguiva una configurazione ER, una finestra di messaggio compariva richiedendo l'azione dell'utente di salvare o aprire un file.</span><span class="sxs-lookup"><span data-stu-id="61fdd-119">Previously, when you ran an ER configuration, a message box appeared that required user action to save or open a file.</span></span> <span data-ttu-id="61fdd-120">È possibile ora preconfigurare una destinazione per ciascuna configurazione di formato e per ogni componente di output (una cartella o un file) separatamente.</span><span class="sxs-lookup"><span data-stu-id="61fdd-120">You can now pre-configure a destination for each format configuration and for each output component (a folder or a file) separately.</span></span> <span data-ttu-id="61fdd-121">Gli utenti che dispongono di diritti di accesso appropriati anche possono modificare le impostazioni di destinazione in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="61fdd-121">Users who have appropriate access rights can also modify destination settings at run time.</span></span> |

## <a name="pos--microsoft-dynamics-ax-retail"></a><span data-ttu-id="61fdd-122">POS – Microsoft Dynamics AX Retail</span><span class="sxs-lookup"><span data-stu-id="61fdd-122">POS – Microsoft Dynamics AX Retail</span></span>

| <span data-ttu-id="61fdd-123">Operazioni che è possibile effettuare</span><span class="sxs-lookup"><span data-stu-id="61fdd-123">What can you do?</span></span> | <span data-ttu-id="61fdd-124">Perché questo è importante?</span><span class="sxs-lookup"><span data-stu-id="61fdd-124">Why is this important?</span></span> |
|------------------|------------------------|
| <span data-ttu-id="61fdd-125">Utilizzare il browser Google Chrome.</span><span class="sxs-lookup"><span data-stu-id="61fdd-125">Use the Google Chrome browser.</span></span> | <span data-ttu-id="61fdd-126">I rivenditori possono ora avviare il POS cloud dal browser Chrome e possono utilizzare tutte le funzionalità disponibili nella versione Microsoft Edge e Internet Explorer di POS cloud.</span><span class="sxs-lookup"><span data-stu-id="61fdd-126">Retailers can now start Cloud POS from the Chrome browser, and can experience all the functionality that is available in the Microsoft Edge and Internet Explorer version of Cloud POS.</span></span> |

## <a name="financial-reporting"></a><span data-ttu-id="61fdd-127">Creazione di report finanziari</span><span class="sxs-lookup"><span data-stu-id="61fdd-127">Financial reporting</span></span>

| <span data-ttu-id="61fdd-128">Operazioni che è possibile effettuare</span><span class="sxs-lookup"><span data-stu-id="61fdd-128">What can you do?</span></span> | <span data-ttu-id="61fdd-129">Perché questo è importante?</span><span class="sxs-lookup"><span data-stu-id="61fdd-129">Why is this important?</span></span> |
|------------------|------------------------|
| <span data-ttu-id="61fdd-130">Ricompilare il data mart dei report finanziari.</span><span class="sxs-lookup"><span data-stu-id="61fdd-130">Rebuild the Financial reporting data mart.</span></span> | <span data-ttu-id="61fdd-131">Quando si spostano i database di Dynamics AX tra ambienti o si apportano altre modifiche invasive all'ambiente, può essere necessario ricompilare il database dei report finanziari.</span><span class="sxs-lookup"><span data-stu-id="61fdd-131">When you move Dynamics AX databases between environments or make other invasive changes to the environment, the Financial reporting database might have to be rebuilt.</span></span> <span data-ttu-id="61fdd-132">Uno script Windows PowerShell è ora disponibile per la ricompilazione automatica del database.</span><span class="sxs-lookup"><span data-stu-id="61fdd-132">A Windows PowerShell script is now provided to rebuild the database for you.</span></span> |
| <span data-ttu-id="61fdd-133">Non è più possibile selezionare opzioni di progettazione di report che non sono valide.</span><span class="sxs-lookup"><span data-stu-id="61fdd-133">You can no longer select report designer options that aren't valid.</span></span> | <span data-ttu-id="61fdd-134">Diverse opzioni della finestra di progettazione di report che erano utilizzate nelle versioni commercializzate di Management Reporter non si applicano a questa versione di Dynamics AX.</span><span class="sxs-lookup"><span data-stu-id="61fdd-134">Several report designer options that were used in the in-market versions of Management reporter don't apply to this version of Dynamics AX.</span></span> <span data-ttu-id="61fdd-135">Queste opzioni erano correlate a progettazione, output e collegamento di report finanziari.</span><span class="sxs-lookup"><span data-stu-id="61fdd-135">These options were related to financial report design, output, and linking.</span></span> <span data-ttu-id="61fdd-136">Queste opzioni sono state rimosse dalla finestra di progettazione di report finanziari per evitare errori dell'utente.</span><span class="sxs-lookup"><span data-stu-id="61fdd-136">These options have been removed from the financial report designer to prevent user errors.</span></span> |

## <a name="financial-management"></a><span data-ttu-id="61fdd-137">Gestione finanziaria</span><span class="sxs-lookup"><span data-stu-id="61fdd-137">Financial management</span></span>

| <span data-ttu-id="61fdd-138">Operazioni che è possibile effettuare</span><span class="sxs-lookup"><span data-stu-id="61fdd-138">What can you do?</span></span> | <span data-ttu-id="61fdd-139">Perché questo è importante?</span><span class="sxs-lookup"><span data-stu-id="61fdd-139">Why is this important?</span></span> |
|------------------|------------------------|
| <span data-ttu-id="61fdd-140">Generare file pagamenti sicuri per i pagamenti della contabilità fornitori</span><span class="sxs-lookup"><span data-stu-id="61fdd-140">Generate positive pay files for accounts payable payments.</span></span> | <span data-ttu-id="61fdd-141">È possibile generare i file pagamenti sicuri per impedire la frode di assegni.</span><span class="sxs-lookup"><span data-stu-id="61fdd-141">Positive pay files can be generated to help prevent check fraud.</span></span> |

## <a name="warehouse-and-production"></a><span data-ttu-id="61fdd-142">Magazzino e produzione</span><span class="sxs-lookup"><span data-stu-id="61fdd-142">Warehouse and production</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="61fdd-143">Operazioni che è possibile effettuare</span><span class="sxs-lookup"><span data-stu-id="61fdd-143">What can you do?</span></span></th>
<th><span data-ttu-id="61fdd-144">Perché questo è importante?</span><span class="sxs-lookup"><span data-stu-id="61fdd-144">Why is this important?</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="61fdd-145">Definire un criterio di lavoro di magazzino che controlla la creazione di lavoro per una serie di prodotti in ubicazioni specifiche.</span><span class="sxs-lookup"><span data-stu-id="61fdd-145">Define a warehouse work policy that controls the creation of work for a set of products at specific locations.</span></span></td>
<td><span data-ttu-id="61fdd-146">I processi del magazzino non includono sempre del lavoro.</span><span class="sxs-lookup"><span data-stu-id="61fdd-146">Warehouse processes don't always include work.</span></span> <span data-ttu-id="61fdd-147">Utilizzando i nuovi criteri di lavoro del magazzino, è possibile impedire la creazione di lavoro per il prelievo delle materie prime e lo stoccaggio di prodotti finiti per un set di prodotti in ubicazioni specifiche.</span><span class="sxs-lookup"><span data-stu-id="61fdd-147">By using the new warehouse work policy, you can prevent work from being created for raw material picking and put-away of finished goods for a set of products at specific locations.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="61fdd-148">Specificare un'ubicazione di uscita di produzione non è controllata da targa.</span><span class="sxs-lookup"><span data-stu-id="61fdd-148">Specify that a production output location isn't license plate–controlled.</span></span></td>
<td><span data-ttu-id="61fdd-149">È ora possibile specificare che un'ubicazione di uscita di produzione non è controllata da targa.</span><span class="sxs-lookup"><span data-stu-id="61fdd-149">You can now specify that a product output location isn't license plate–controlled.</span></span> <span data-ttu-id="61fdd-150">Ad esempio, questa funzionalità è utile quando un ordine di produzione a monte segnala articoli come finiti direttamente in una ubicazione che funge da ubicazione di entrata produzione per un ordine di produzione a valle.</span><span class="sxs-lookup"><span data-stu-id="61fdd-150">For example, this feature is useful when an upstream production order reports items as finished directly to a location that acts as production input location for a downstream production order.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="61fdd-151">Supportare BDA che comprendono articoli con dimensioni prodotto diverse dello stesso articolo.</span><span class="sxs-lookup"><span data-stu-id="61fdd-151">Support BOMs that include items with different product dimensions of the same item.</span></span></td>
<td><span data-ttu-id="61fdd-152">Quando si utilizza uno o più delle dimensioni del prodotto in produzione, è possibile avere situazioni in cui si desidera produrre un articolo, basato su una diversa variante dello stesso articolo.</span><span class="sxs-lookup"><span data-stu-id="61fdd-152">When using one or multiple of the product dimensions in production, you can have situations where you would like to produce an item, based on a different variant of the same item.</span></span> <span data-ttu-id="61fdd-153">Per ulteriori informazioni, vedere <a href="/archive/blogs/axmfg/support-for-boms-that-includes-items-with-different-product-dimensions-of-the-same-item">questo blog</a>.</span><span class="sxs-lookup"><span data-stu-id="61fdd-153">For more information, see <a href="/archive/blogs/axmfg/support-for-boms-that-includes-items-with-different-product-dimensions-of-the-same-item">this blog</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="61fdd-154">Ordini di produzione con strutture circolari al primo livello delle loro DBA vengono esclusi dal calcolo livello DBA per la pianificazione delle risorse materiali.</span><span class="sxs-lookup"><span data-stu-id="61fdd-154">Production orders with circular structures at the first level of their BOMs are excluded from BOM level calculation for material resource planning.</span></span></td>
<td><span data-ttu-id="61fdd-155">Non è possibile assegnare livelli di DBA corretti a varianti prodotto per gli ordini di produzione che provocano la circolarità della gerarchia DBA.</span><span class="sxs-lookup"><span data-stu-id="61fdd-155">It is not possible to assign correct BOM levels to product variants for production orders that cause circularity in the BOM hierarchy.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="61fdd-156">Calcolare livelli DBA separati per la pianificazione delle risorse materiali e il calcolo dei costi:</span><span class="sxs-lookup"><span data-stu-id="61fdd-156">Calculate separate BOM levels for material resource planning and cost calculation:</span></span>
<ul>
<li><span data-ttu-id="61fdd-157">Per la pianificazione delle risorse materiali, i livelli DBA vengono calcolati nella nuova tabella <strong>ReqItemLevel</strong>.</span><span class="sxs-lookup"><span data-stu-id="61fdd-157">For material resource planning, BOM levels are calculated in the new <strong>ReqItemLevel</strong> table.</span></span> <span data-ttu-id="61fdd-158">Ordini di produzione finiti vengono ignorati nel calcolo.</span><span class="sxs-lookup"><span data-stu-id="61fdd-158">Ended production orders are ignored in the calculation.</span></span></li>
<li><span data-ttu-id="61fdd-159">Per il calcolo di costi di produzione, livelli DBA vengono calcolati in <strong>InventTable</strong>.</span><span class="sxs-lookup"><span data-stu-id="61fdd-159">For production cost calculation, BOM levels are calculated in the <strong>InventTable</strong>.</span></span> <span data-ttu-id="61fdd-160">Ordini di produzione finiti vengono inclusi nel calcolo.</span><span class="sxs-lookup"><span data-stu-id="61fdd-160">Ended production orders are included in the calculation.</span></span></li>
</ul>
</td>
<td>
<ul>
<li><span data-ttu-id="61fdd-161">Durante l'esecuzione di pianificazione delle risorse materiali, ad esempio, programmazione ed esplosione pianificazione principale, devono essere ricalcolati solo i livelli DBA utilizzati per la pianificazione delle risorse materiali.</span><span class="sxs-lookup"><span data-stu-id="61fdd-161">When running material resource planning, for example, master planning plan scheduling and explosion, only BOM levels used for material resource planning need to be recalculated.</span></span> <span data-ttu-id="61fdd-162">In altre parole, non è necessario calcolare i livelli DBA utilizzati per il calcolo dei costi di produzione.</span><span class="sxs-lookup"><span data-stu-id="61fdd-162">In other words, there is no need to calculate BOM levels used for production costing calculation.</span></span></li>
<li><span data-ttu-id="61fdd-163">Durante l'esecuzione di operazioni determinazione costi, ad esempio la chiusura inventario, è necessario ricalcolare solo i livelli DBA utilizzati per il calcolo di determinazione costi di produzione.</span><span class="sxs-lookup"><span data-stu-id="61fdd-163">When running costing operations, for example, inventory closing, only BOM levels used for production costing calculation need to be recalculated.</span></span></li>
</ul>
</td>
</tr>
</tbody>
</table>

## <a name="additional-resources"></a><span data-ttu-id="61fdd-164">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="61fdd-164">Additional resources</span></span>

[<span data-ttu-id="61fdd-165">Novità o modifiche nella Finance and Operations home page</span><span class="sxs-lookup"><span data-stu-id="61fdd-165">What's new or changed in Finance and Operations home page</span></span>](whats-new-changed.md)

[<span data-ttu-id="61fdd-166">Guide attività nuove o aggiornate (maggio 2016)</span><span class="sxs-lookup"><span data-stu-id="61fdd-166">New or updated task guides (May 2016)</span></span>](new-updated-task-guides-available-may-2016.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]