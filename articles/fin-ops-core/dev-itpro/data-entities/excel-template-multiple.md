---
title: Modelli di dati con più fogli di lavoro
description: In questo argomento viene descritto come importare i dati mediante modelli di entità di dati Excel in Finance and Operations.
author: Sunil-Garg
manager: AnnBe
ms.date: 01/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: sericks
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: sunilg
ms.search.validFrom: 2018-01-01
ms.dyn365.ops.version: Platform update 13
ms.openlocfilehash: 64515ff74c0ca2b01bb9dac06331ba0424811411
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2021
ms.locfileid: "5565573"
---
# <a name="data-templates-with-multiple-worksheets"></a><span data-ttu-id="40ca3-103">Modelli di dati con più fogli di lavoro</span><span class="sxs-lookup"><span data-stu-id="40ca3-103">Data templates with multiple worksheets</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="40ca3-104">La gestione dei dati nell'applicazione supporta modelli basati su Microsoft Excel per le entità di dati.</span><span class="sxs-lookup"><span data-stu-id="40ca3-104">Data management in the application supports Microsoft Excel-based templates for data entities.</span></span> <span data-ttu-id="40ca3-105">Questi modelli possono contenere uno o più fogli di lavoro.</span><span class="sxs-lookup"><span data-stu-id="40ca3-105">These templates can contain one or more worksheets.</span></span> <span data-ttu-id="40ca3-106">I modelli con più fogli di lavoro vengono spesso utilizzati quando è conveniente gestire i dati in un singolo file e importarli in più entità di dati.</span><span class="sxs-lookup"><span data-stu-id="40ca3-106">Templates with multiple worksheets are often used when it is convenient to manage data in a single file and import it to multiple data entities.</span></span> <span data-ttu-id="40ca3-107">Un esempio potrebbe essere il caso di siti e magazzini.</span><span class="sxs-lookup"><span data-stu-id="40ca3-107">An example would be sites and warehouses.</span></span>

## <a name="upload-a-file-once-and-map-it-to-all-entities"></a><span data-ttu-id="40ca3-108">Caricare una volta un file e mapparlo a tutte le entità</span><span class="sxs-lookup"><span data-stu-id="40ca3-108">Upload a file once and map it to all entities</span></span>
<span data-ttu-id="40ca3-109">Si veda un esempio in cui esiste un file Excel con i fogli di lavoro chiamati **Siti** e **Magazzini**.</span><span class="sxs-lookup"><span data-stu-id="40ca3-109">Let's take an example where there is one Excel file with worksheets called **Sites** and **Warehouses**.</span></span> <span data-ttu-id="40ca3-110">Per impostare il progetto di importazione di dati, aggiungere la prima entità di dati **Siti**, quindi caricare il file.</span><span class="sxs-lookup"><span data-stu-id="40ca3-110">To set up the data import project, you would add the first data entity, **Sites** and then upload the file.</span></span> <span data-ttu-id="40ca3-111">Sarà possibile selezionare **Siti** come foglio di lavoro da utilizzare per questa entità.</span><span class="sxs-lookup"><span data-stu-id="40ca3-111">You will be able to select **Sites** as the worksheet to be used for this entity.</span></span>

<span data-ttu-id="40ca3-112">Se si aggiunge la seconda entità **Magazzini** senza chiudere il modulo **Aggiungi file**, la ricerca del foglio di lavoro consente di selezionare il foglio di lavoro **Magazzini** senza dover caricare di nuovo il file.</span><span class="sxs-lookup"><span data-stu-id="40ca3-112">If you add the second entity **Warehouses** without leaving the **Add file** form, the worksheet lookup will let you select the **Warehouses** worksheet without having to upload the file again.</span></span> <span data-ttu-id="40ca3-113">Il solo motivo per caricare un nuovo file sarebbe se i dati di **Magazzini** si trovassero in un altro file.</span><span class="sxs-lookup"><span data-stu-id="40ca3-113">The only reason to upload a new file would be if the **Warehouses** data was in a different file.</span></span>

![Fogli di lavoro multipli](./media/AddFileMultipleWorkSheets.png)

## <a name="fix-worksheet-to-entity-mapping"></a><span data-ttu-id="40ca3-115">Fissare il foglio di lavoro al mapping di entità</span><span class="sxs-lookup"><span data-stu-id="40ca3-115">Fix worksheet to entity mapping</span></span>

<span data-ttu-id="40ca3-116">Il mapping del foglio di lavoro a un'entità di dati nel processo di importazione può essere fissato dalla griglia.</span><span class="sxs-lookup"><span data-stu-id="40ca3-116">The mapping of the worksheet to a data entity in the import job can be fixed from the grid.</span></span> <span data-ttu-id="40ca3-117">La colonna **Foglio di lavoro** nella griglia mostra i fogli di lavoro del file che è stato mappato.</span><span class="sxs-lookup"><span data-stu-id="40ca3-117">The **Worksheet** column in the grid shows the worksheets from the file that was mapped.</span></span> <span data-ttu-id="40ca3-118">È possibile scegliere un foglio di lavoro diverso dal menu a discesa.</span><span class="sxs-lookup"><span data-stu-id="40ca3-118">You can choose a different worksheet from the drop-down menu.</span></span> <span data-ttu-id="40ca3-119">Se il foglio di lavoro è già stato mappato a un'entità nel progetto di dati, il sistema chiede di confermare la modifica.</span><span class="sxs-lookup"><span data-stu-id="40ca3-119">If the chosen worksheet is already mapped to an entity in the data project, the system asks you to confirm the change.</span></span> <span data-ttu-id="40ca3-120">Si consiglia di fissare tutti i mapping nella griglia.</span><span class="sxs-lookup"><span data-stu-id="40ca3-120">We recommend that you fix all mappings in the grid.</span></span>

![Aggiornare il mapping del foglio di lavoro](./media/UpdateMappings.png)

## <a name="re-map-to-a-new-file"></a><span data-ttu-id="40ca3-122">Ripetere il mapping in un nuovo file</span><span class="sxs-lookup"><span data-stu-id="40ca3-122">Re-map to a new file</span></span>

<span data-ttu-id="40ca3-123">Nei casi in cui una nuova versione dello stesso file o un file completamente nuovo viene caricata per le entità esistenti in un progetto di dati, è necessario utilizzare l'esperienza **Aggiungi file** e aggiungere di nuovo le entità come se si stessero aggiungendo per la prima volta.</span><span class="sxs-lookup"><span data-stu-id="40ca3-123">In cases where a new version of the same file or a completely new file must be uploaded for existing entities in a data project, you must use the **Add file** experience, and add the entities again as if they were being added for the first time.</span></span> <span data-ttu-id="40ca3-124">Il sistema confermerà che si desidera sovrascrivere le entità esistenti nel progetto di dati prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="40ca3-124">The system will confirm that you want to overwrite the existing entities in the data project before proceeding.</span></span> <span data-ttu-id="40ca3-125">Le entità che non vengono aggiunte (o sovrascritte) continueranno a mantenere i mapping precedenti del file precedente.</span><span class="sxs-lookup"><span data-stu-id="40ca3-125">Entities that are not added again (or overwritten) will continue to hold the previous mappings from the previous file.</span></span>

## <a name="upload-a-file-using-run-project"></a><span data-ttu-id="40ca3-126">Caricare un file tramite Esegui progetto</span><span class="sxs-lookup"><span data-stu-id="40ca3-126">Upload a file using Run project</span></span>

<span data-ttu-id="40ca3-127">È possibile caricare un file di Excel quando si utilizza l'opzione **Esegui progetto** per eseguire un progetto di importazione.</span><span class="sxs-lookup"><span data-stu-id="40ca3-127">You can upload an Excel file while using the **Run project** option to execute an import project.</span></span> <span data-ttu-id="40ca3-128">Prestare attenzione a caricare solo i file con gli stessi fogli di lavoro dei mapping esistenti nelle entità di dati nel progetto dati.</span><span class="sxs-lookup"><span data-stu-id="40ca3-128">You must be careful to upload only files that have the same worksheets as the existing mappings on the data entities in the data project.</span></span> <span data-ttu-id="40ca3-129">Se non è possibile trovare un foglio di lavoro nel nuovo file caricato, il sistema visualizza un errore e interrompe l'importazione.</span><span class="sxs-lookup"><span data-stu-id="40ca3-129">If a worksheet is not found in the newly uploaded file, the system displays an error and will stop the import.</span></span> <span data-ttu-id="40ca3-130">Se il mapping al foglio di lavoro deve essere modificato per un'entità, i mapping nel progetto di dati devono essere aggiornati nel progetto dati prima di utilizzare il file nell'esperienza **Esegui progetto**.</span><span class="sxs-lookup"><span data-stu-id="40ca3-130">If the mapping to the worksheet must be changed for an entity, then the mappings in the data project must be first updated from within the data project before using the file in the **Run project** experience.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]