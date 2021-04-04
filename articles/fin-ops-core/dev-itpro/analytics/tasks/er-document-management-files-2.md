---
title: 'ER Usare file di gestione documenti in output di formato (Parte 2: Estendere il modello dati)'
description: In questo argomento viene descritto come configurare un formato di reporting elettronico (ER) per utilizzare i file di gestione dei documenti (allegati) nell'output ER. (Parte 2)
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERDataModelDesigner, ERDataModelContentsItemCreationDialog, ERModelMappingTable, ERModelMappingDesigner, ERExpressionDesignerFormula
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b47c35790ce04a494b6c58f6e04fa9b829d2ab93
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2021
ms.locfileid: "5559775"
---
# <a name="er-use-document-management-files-in-format-outputs-part-2---extend-data-model"></a><span data-ttu-id="094c0-104">ER Usare file di gestione documenti in output di formato (Parte 2: Estendere il modello dati)</span><span class="sxs-lookup"><span data-stu-id="094c0-104">ER Use Document Management files in format outputs (Part 2 - Extend data model)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="094c0-105">I passaggi seguenti descrivono come un utente con ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può configurare un formato per la creazione di report elettronici in modo che utilizzi i file (allegati) di gestione documenti nell'output della creazione di report elettronici.</span><span class="sxs-lookup"><span data-stu-id="094c0-105">The following steps explain how a user assigned to the System Administrator or Electronic Reporting Developer role can configure an Electronic reporting (ER) format to use Document Management files (attachments) in ER output.</span></span> <span data-ttu-id="094c0-106">Questi passaggi possono essere eseguiti in qualsiasi società.</span><span class="sxs-lookup"><span data-stu-id="094c0-106">These steps can be performed in any company.</span></span>

<span data-ttu-id="094c0-107">Per effettuare queste operazioni, è innanzitutto necessario completare i passaggi della guida attività "ER Usare i file di gestione documenti negli output di formato (parte 1: preparare il modello dati)".</span><span class="sxs-lookup"><span data-stu-id="094c0-107">To complete these steps, you must first complete the steps in the "ER Use Document Management files in format outputs (Part 1: Prepare data model)" task guide.</span></span>

<span data-ttu-id="094c0-108">Questa procedura è per una funzionalità che è stata aggiunta in Dynamics 365 for Operations versione 1611.</span><span class="sxs-lookup"><span data-stu-id="094c0-108">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="extend-data-model-to-present-the-document-management-files-in-it"></a><span data-ttu-id="094c0-109">Estendere il modello dati per presentare i file di gestione documenti al suo interno</span><span class="sxs-lookup"><span data-stu-id="094c0-109">Extend data model to present the Document Management files in it</span></span>
1. <span data-ttu-id="094c0-110">Andare ad Amministrazione organizzazione > Aree di lavoro > Creazione di report elettronici.</span><span class="sxs-lookup"><span data-stu-id="094c0-110">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="094c0-111">Fare clic su Configurazioni report.</span><span class="sxs-lookup"><span data-stu-id="094c0-111">Click Reporting configurations.</span></span>
3. <span data-ttu-id="094c0-112">Nella struttura espandere 'Modello fattura cliente'.</span><span class="sxs-lookup"><span data-stu-id="094c0-112">In the tree, expand 'Customer invoice model'.</span></span>
4. <span data-ttu-id="094c0-113">Nella struttura selezionare 'Modello fattura cliente\Modello fattura cliente (personalizzato)'.</span><span class="sxs-lookup"><span data-stu-id="094c0-113">In the tree, select 'Customer invoice model\Customer invoice model (custom)'.</span></span>
5. <span data-ttu-id="094c0-114">Fare clic su Progettazione.</span><span class="sxs-lookup"><span data-stu-id="094c0-114">Click Designer.</span></span>
6. <span data-ttu-id="094c0-115">Nella struttura selezionare 'Fattura cliente(InvoiceCustomer)'.</span><span class="sxs-lookup"><span data-stu-id="094c0-115">In the tree, select 'Customer invoice(InvoiceCustomer)'.</span></span>
    * <span data-ttu-id="094c0-116">Estenderemo questo modello dati per esporvi qualsiasi file allegato a un ordine cliente correlato a una fattura elaborata elettronicamente.</span><span class="sxs-lookup"><span data-stu-id="094c0-116">We will extend this data model to expose in it any files that have been attached to a sales order that is related to an electronically processing invoice.</span></span>  
7. <span data-ttu-id="094c0-117">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="094c0-117">Click New to open the drop dialog.</span></span>
8. <span data-ttu-id="094c0-118">Nel campo Nome digitare 'Allegati fattura'.</span><span class="sxs-lookup"><span data-stu-id="094c0-118">In the Name field, type 'Invoice attachments'.</span></span>
    * <span data-ttu-id="094c0-119">Allegati fattura</span><span class="sxs-lookup"><span data-stu-id="094c0-119">Invoice attachments</span></span>  
9. <span data-ttu-id="094c0-120">Nel campo Tipo di articolo selezionare "Elenco di record".</span><span class="sxs-lookup"><span data-stu-id="094c0-120">In the Item type field, select 'Record list'.</span></span>
10. <span data-ttu-id="094c0-121">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="094c0-121">Click Add.</span></span>
11. <span data-ttu-id="094c0-122">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="094c0-122">Click New to open the drop dialog.</span></span>
12. <span data-ttu-id="094c0-123">Digitare 'Contenuto file' nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="094c0-123">In the Name field, type 'File content'.</span></span>
    * <span data-ttu-id="094c0-124">Contenuto file</span><span class="sxs-lookup"><span data-stu-id="094c0-124">File content</span></span>  
13. <span data-ttu-id="094c0-125">Nel campo Tipo di articolo selezionare 'Contenitore'.</span><span class="sxs-lookup"><span data-stu-id="094c0-125">In the Item type field, select 'Container'.</span></span>
14. <span data-ttu-id="094c0-126">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="094c0-126">Click Add.</span></span>
15. <span data-ttu-id="094c0-127">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="094c0-127">Click New to open the drop dialog.</span></span>
16. <span data-ttu-id="094c0-128">Nel campo Nome digitare 'Nome file'.</span><span class="sxs-lookup"><span data-stu-id="094c0-128">In the Name field, type 'File name'.</span></span>
    * <span data-ttu-id="094c0-129">Nome file</span><span class="sxs-lookup"><span data-stu-id="094c0-129">File name</span></span>  
17. <span data-ttu-id="094c0-130">Nel campo Tipo di articolo selezionare "Stringa".</span><span class="sxs-lookup"><span data-stu-id="094c0-130">In the Item type field, select 'String'.</span></span>
18. <span data-ttu-id="094c0-131">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="094c0-131">Click Add.</span></span>

## <a name="map-new-data-model-elements-to-data-sources"></a><span data-ttu-id="094c0-132">Mappare gli elementi del nuovo modello dati alle origini dati</span><span class="sxs-lookup"><span data-stu-id="094c0-132">Map new data model elements to data sources</span></span>
1. <span data-ttu-id="094c0-133">Fare clic su Mappa modello a origine dati.</span><span class="sxs-lookup"><span data-stu-id="094c0-133">Click Map model to datasource.</span></span>
2. <span data-ttu-id="094c0-134">Utilizzare il filtro rapido per filtrare in base al campo Definizione con un valore di 'InvoiceCustomer'.</span><span class="sxs-lookup"><span data-stu-id="094c0-134">Use the Quick Filter to filter on the Definition field with a value of 'InvoiceCustomer'.</span></span>
    * <span data-ttu-id="094c0-135">InvoiceCustomer</span><span class="sxs-lookup"><span data-stu-id="094c0-135">InvoiceCustomer</span></span>  
    * <span data-ttu-id="094c0-136">Mapperemo gli elementi del nuovo modello alle origini dati appropriate.</span><span class="sxs-lookup"><span data-stu-id="094c0-136">We will map new model elements to appropriate data sources.</span></span>  
3. <span data-ttu-id="094c0-137">Fare clic su Progettazione.</span><span class="sxs-lookup"><span data-stu-id="094c0-137">Click Designer.</span></span>
4. <span data-ttu-id="094c0-138">Nella struttura selezionare 'Allegati fattura'.</span><span class="sxs-lookup"><span data-stu-id="094c0-138">In the tree, select 'Invoice attachments'.</span></span>
5. <span data-ttu-id="094c0-139">Nella struttura espandere 'Allegati fattura'.</span><span class="sxs-lookup"><span data-stu-id="094c0-139">In the tree, expand 'Invoice attachments'.</span></span>
6. <span data-ttu-id="094c0-140">Nella struttura selezionare 'Allegati fattura\Nome file'.</span><span class="sxs-lookup"><span data-stu-id="094c0-140">In the tree, select 'Invoice attachments\File name'.</span></span>
7. <span data-ttu-id="094c0-141">Fare clic su Modifica.</span><span class="sxs-lookup"><span data-stu-id="094c0-141">Click Edit.</span></span>
8. <span data-ttu-id="094c0-142">Nel campo Formula immettere 'CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'originalFileName()''.</span><span class="sxs-lookup"><span data-stu-id="094c0-142">In the Formula field, enter 'CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'originalFileName()''.</span></span>
    * <span data-ttu-id="094c0-143">CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'originalFileName()'</span><span class="sxs-lookup"><span data-stu-id="094c0-143">CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'originalFileName()'</span></span>  
9. <span data-ttu-id="094c0-144">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="094c0-144">Click Save.</span></span>
10. <span data-ttu-id="094c0-145">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="094c0-145">Close the page.</span></span>
11. <span data-ttu-id="094c0-146">Nella struttura selezionare 'Allegati fattura\Contenuto file'.</span><span class="sxs-lookup"><span data-stu-id="094c0-146">In the tree, select 'Invoice attachments\File content'.</span></span>
12. <span data-ttu-id="094c0-147">Fare clic su Modifica.</span><span class="sxs-lookup"><span data-stu-id="094c0-147">Click Edit.</span></span>
13. <span data-ttu-id="094c0-148">Nel campo Formula immettere 'CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'getFileContentAsContainer()''.</span><span class="sxs-lookup"><span data-stu-id="094c0-148">In the Formula field, enter 'CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'getFileContentAsContainer()''.</span></span>
    * <span data-ttu-id="094c0-149">CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'getFileContentAsContainer()'</span><span class="sxs-lookup"><span data-stu-id="094c0-149">CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'getFileContentAsContainer()'</span></span>  
14. <span data-ttu-id="094c0-150">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="094c0-150">Click Save.</span></span>
15. <span data-ttu-id="094c0-151">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="094c0-151">Close the page.</span></span>
16. <span data-ttu-id="094c0-152">Nella struttura selezionare 'Allegati fattura'.</span><span class="sxs-lookup"><span data-stu-id="094c0-152">In the tree, select 'Invoice attachments'.</span></span>
17. <span data-ttu-id="094c0-153">Fare clic su Modifica.</span><span class="sxs-lookup"><span data-stu-id="094c0-153">Click Edit.</span></span>
18. <span data-ttu-id="094c0-154">Nel campo Formula immettere 'CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents''.</span><span class="sxs-lookup"><span data-stu-id="094c0-154">In the Formula field, enter 'CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents''.</span></span>
    * <span data-ttu-id="094c0-155">CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'</span><span class="sxs-lookup"><span data-stu-id="094c0-155">CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'</span></span>  
19. <span data-ttu-id="094c0-156">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="094c0-156">Click Save.</span></span>
20. <span data-ttu-id="094c0-157">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="094c0-157">Close the page.</span></span>
21. <span data-ttu-id="094c0-158">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="094c0-158">Click Save.</span></span>
22. <span data-ttu-id="094c0-159">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="094c0-159">Close the page.</span></span>
23. <span data-ttu-id="094c0-160">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="094c0-160">Close the page.</span></span>
24. <span data-ttu-id="094c0-161">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="094c0-161">Close the page.</span></span>
25. <span data-ttu-id="094c0-162">Fare clic su Cambia stato.</span><span class="sxs-lookup"><span data-stu-id="094c0-162">Click Change status.</span></span>
26. <span data-ttu-id="094c0-163">Fare clic su Completa.</span><span class="sxs-lookup"><span data-stu-id="094c0-163">Click Complete.</span></span>
27. <span data-ttu-id="094c0-164">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="094c0-164">Click OK.</span></span>



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]