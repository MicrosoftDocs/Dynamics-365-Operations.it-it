---
title: 'ER Usare file di gestione documenti in output di formato (Parte 2: Estendere il modello dati)'
description: I passaggi seguenti descrivono come un utente con ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può configurare un formato per la creazione di report elettronici in modo che utilizzi i file (allegati) di gestione documenti nell'output della creazione di report elettronici.
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERDataModelDesigner, ERDataModelContentsItemCreationDialog, ERModelMappingTable, ERModelMappingDesigner, ERExpressionDesignerFormula
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 24eba0402caefb611a212db19cdb8feafa7c1fee
ms.sourcegitcommit: 75db3b75d35d27034f9b56e7119c9d0cb7666830
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/03/2019
ms.locfileid: "2550742"
---
# <a name="er-use-document-management-files-in-format-outputs-part-2---extend-data-model"></a><span data-ttu-id="8a348-103">ER Usare file di gestione documenti in output di formato (Parte 2: Estendere il modello dati)</span><span class="sxs-lookup"><span data-stu-id="8a348-103">ER Use Document Management files in format outputs (Part 2 - Extend data model)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="8a348-104">I passaggi seguenti descrivono come un utente con ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può configurare un formato per la creazione di report elettronici in modo che utilizzi i file (allegati) di gestione documenti nell'output della creazione di report elettronici.</span><span class="sxs-lookup"><span data-stu-id="8a348-104">The following steps explain how a user assigned to the System Administrator or Electronic Reporting Developer role can configure an Electronic reporting (ER) format to use Document Management files (attachments) in ER output.</span></span> <span data-ttu-id="8a348-105">Questi passaggi possono essere eseguiti in qualsiasi società.</span><span class="sxs-lookup"><span data-stu-id="8a348-105">These steps can be performed in any company.</span></span>

<span data-ttu-id="8a348-106">Per effettuare queste operazioni, è innanzitutto necessario completare i passaggi della guida attività 'ER Usare i file di gestione documenti negli output di formato (parte 1: preparare il modello dati)'.</span><span class="sxs-lookup"><span data-stu-id="8a348-106">To complete these steps, you must first complete the steps in the “ER Use Document Management files in format outputs (Part 1: Prepare data model)” task guide.</span></span>

<span data-ttu-id="8a348-107">Questa procedura è per una funzionalità che è stata aggiunta in Dynamics 365 for Operations versione 1611.</span><span class="sxs-lookup"><span data-stu-id="8a348-107">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="extend-data-model-to-present-the-document-management-files-in-it"></a><span data-ttu-id="8a348-108">Estendere il modello dati per presentare i file di gestione documenti al suo interno</span><span class="sxs-lookup"><span data-stu-id="8a348-108">Extend data model to present the Document Management files in it</span></span>
1. <span data-ttu-id="8a348-109">Andare ad Amministrazione organizzazione > Aree di lavoro > Creazione di report elettronici.</span><span class="sxs-lookup"><span data-stu-id="8a348-109">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="8a348-110">Fare clic su Configurazioni report.</span><span class="sxs-lookup"><span data-stu-id="8a348-110">Click Reporting configurations.</span></span>
3. <span data-ttu-id="8a348-111">Nella struttura espandere 'Modello fattura cliente'.</span><span class="sxs-lookup"><span data-stu-id="8a348-111">In the tree, expand 'Customer invoice model'.</span></span>
4. <span data-ttu-id="8a348-112">Nella struttura selezionare 'Modello fattura cliente\Modello fattura cliente (personalizzato)'.</span><span class="sxs-lookup"><span data-stu-id="8a348-112">In the tree, select 'Customer invoice model\Customer invoice model (custom)'.</span></span>
5. <span data-ttu-id="8a348-113">Fare clic su Progettazione.</span><span class="sxs-lookup"><span data-stu-id="8a348-113">Click Designer.</span></span>
6. <span data-ttu-id="8a348-114">Nella struttura selezionare 'Fattura cliente(InvoiceCustomer)'.</span><span class="sxs-lookup"><span data-stu-id="8a348-114">In the tree, select 'Customer invoice(InvoiceCustomer)'.</span></span>
    * <span data-ttu-id="8a348-115">Estenderemo questo modello dati per esporvi qualsiasi file allegato a un ordine cliente correlato a una fattura elaborata elettronicamente.</span><span class="sxs-lookup"><span data-stu-id="8a348-115">We will extend this data model to expose in it any files that have been attached to a sales order that is related to an electronically processing invoice.</span></span>  
7. <span data-ttu-id="8a348-116">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="8a348-116">Click New to open the drop dialog.</span></span>
8. <span data-ttu-id="8a348-117">Nel campo Nome digitare 'Allegati fattura'.</span><span class="sxs-lookup"><span data-stu-id="8a348-117">In the Name field, type 'Invoice attachments'.</span></span>
    * <span data-ttu-id="8a348-118">Allegati fattura</span><span class="sxs-lookup"><span data-stu-id="8a348-118">Invoice attachments</span></span>  
9. <span data-ttu-id="8a348-119">Nel campo Tipo di articolo selezionare "Elenco di record".</span><span class="sxs-lookup"><span data-stu-id="8a348-119">In the Item type field, select 'Record list'.</span></span>
10. <span data-ttu-id="8a348-120">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="8a348-120">Click Add.</span></span>
11. <span data-ttu-id="8a348-121">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="8a348-121">Click New to open the drop dialog.</span></span>
12. <span data-ttu-id="8a348-122">Digitare 'Contenuto file' nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="8a348-122">In the Name field, type 'File content'.</span></span>
    * <span data-ttu-id="8a348-123">Contenuto file</span><span class="sxs-lookup"><span data-stu-id="8a348-123">File content</span></span>  
13. <span data-ttu-id="8a348-124">Nel campo Tipo di articolo selezionare 'Contenitore'.</span><span class="sxs-lookup"><span data-stu-id="8a348-124">In the Item type field, select 'Container'.</span></span>
14. <span data-ttu-id="8a348-125">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="8a348-125">Click Add.</span></span>
15. <span data-ttu-id="8a348-126">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="8a348-126">Click New to open the drop dialog.</span></span>
16. <span data-ttu-id="8a348-127">Nel campo Nome digitare 'Nome file'.</span><span class="sxs-lookup"><span data-stu-id="8a348-127">In the Name field, type 'File name'.</span></span>
    * <span data-ttu-id="8a348-128">Nome file</span><span class="sxs-lookup"><span data-stu-id="8a348-128">File name</span></span>  
17. <span data-ttu-id="8a348-129">Nel campo Tipo di articolo selezionare "Stringa".</span><span class="sxs-lookup"><span data-stu-id="8a348-129">In the Item type field, select 'String'.</span></span>
18. <span data-ttu-id="8a348-130">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="8a348-130">Click Add.</span></span>

## <a name="map-new-data-model-elements-to-data-sources"></a><span data-ttu-id="8a348-131">Mappare gli elementi del nuovo modello dati alle origini dati</span><span class="sxs-lookup"><span data-stu-id="8a348-131">Map new data model elements to data sources</span></span>
1. <span data-ttu-id="8a348-132">Fare clic su Mappa modello a origine dati.</span><span class="sxs-lookup"><span data-stu-id="8a348-132">Click Map model to datasource.</span></span>
2. <span data-ttu-id="8a348-133">Utilizzare il filtro rapido per filtrare in base al campo Definizione con un valore di 'InvoiceCustomer'.</span><span class="sxs-lookup"><span data-stu-id="8a348-133">Use the Quick Filter to filter on the Definition field with a value of 'InvoiceCustomer'.</span></span>
    * <span data-ttu-id="8a348-134">InvoiceCustomer</span><span class="sxs-lookup"><span data-stu-id="8a348-134">InvoiceCustomer</span></span>  
    * <span data-ttu-id="8a348-135">Mapperemo gli elementi del nuovo modello alle origini dati appropriate.</span><span class="sxs-lookup"><span data-stu-id="8a348-135">We will map new model elements to appropriate data sources.</span></span>  
3. <span data-ttu-id="8a348-136">Fare clic su Progettazione.</span><span class="sxs-lookup"><span data-stu-id="8a348-136">Click Designer.</span></span>
4. <span data-ttu-id="8a348-137">Nella struttura selezionare 'Allegati fattura'.</span><span class="sxs-lookup"><span data-stu-id="8a348-137">In the tree, select 'Invoice attachments'.</span></span>
5. <span data-ttu-id="8a348-138">Nella struttura espandere 'Allegati fattura'.</span><span class="sxs-lookup"><span data-stu-id="8a348-138">In the tree, expand 'Invoice attachments'.</span></span>
6. <span data-ttu-id="8a348-139">Nella struttura selezionare 'Allegati fattura\Nome file'.</span><span class="sxs-lookup"><span data-stu-id="8a348-139">In the tree, select 'Invoice attachments\File name'.</span></span>
7. <span data-ttu-id="8a348-140">Fare clic su Modifica.</span><span class="sxs-lookup"><span data-stu-id="8a348-140">Click Edit.</span></span>
8. <span data-ttu-id="8a348-141">Nel campo Formula immettere 'CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'originalFileName()''.</span><span class="sxs-lookup"><span data-stu-id="8a348-141">In the Formula field, enter 'CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'originalFileName()''.</span></span>
    * <span data-ttu-id="8a348-142">CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'originalFileName()'</span><span class="sxs-lookup"><span data-stu-id="8a348-142">CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'originalFileName()'</span></span>  
9. <span data-ttu-id="8a348-143">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="8a348-143">Click Save.</span></span>
10. <span data-ttu-id="8a348-144">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="8a348-144">Close the page.</span></span>
11. <span data-ttu-id="8a348-145">Nella struttura selezionare 'Allegati fattura\Contenuto file'.</span><span class="sxs-lookup"><span data-stu-id="8a348-145">In the tree, select 'Invoice attachments\File content'.</span></span>
12. <span data-ttu-id="8a348-146">Fare clic su Modifica.</span><span class="sxs-lookup"><span data-stu-id="8a348-146">Click Edit.</span></span>
13. <span data-ttu-id="8a348-147">Nel campo Formula immettere 'CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'getFileContentAsContainer()''.</span><span class="sxs-lookup"><span data-stu-id="8a348-147">In the Formula field, enter 'CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'getFileContentAsContainer()''.</span></span>
    * <span data-ttu-id="8a348-148">CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'getFileContentAsContainer()'</span><span class="sxs-lookup"><span data-stu-id="8a348-148">CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'getFileContentAsContainer()'</span></span>  
14. <span data-ttu-id="8a348-149">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="8a348-149">Click Save.</span></span>
15. <span data-ttu-id="8a348-150">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="8a348-150">Close the page.</span></span>
16. <span data-ttu-id="8a348-151">Nella struttura selezionare 'Allegati fattura'.</span><span class="sxs-lookup"><span data-stu-id="8a348-151">In the tree, select 'Invoice attachments'.</span></span>
17. <span data-ttu-id="8a348-152">Fare clic su Modifica.</span><span class="sxs-lookup"><span data-stu-id="8a348-152">Click Edit.</span></span>
18. <span data-ttu-id="8a348-153">Nel campo Formula immettere 'CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents''.</span><span class="sxs-lookup"><span data-stu-id="8a348-153">In the Formula field, enter 'CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents''.</span></span>
    * <span data-ttu-id="8a348-154">CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'</span><span class="sxs-lookup"><span data-stu-id="8a348-154">CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'</span></span>  
19. <span data-ttu-id="8a348-155">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="8a348-155">Click Save.</span></span>
20. <span data-ttu-id="8a348-156">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="8a348-156">Close the page.</span></span>
21. <span data-ttu-id="8a348-157">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="8a348-157">Click Save.</span></span>
22. <span data-ttu-id="8a348-158">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="8a348-158">Close the page.</span></span>
23. <span data-ttu-id="8a348-159">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="8a348-159">Close the page.</span></span>
24. <span data-ttu-id="8a348-160">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="8a348-160">Close the page.</span></span>
25. <span data-ttu-id="8a348-161">Fare clic su Cambia stato.</span><span class="sxs-lookup"><span data-stu-id="8a348-161">Click Change status.</span></span>
26. <span data-ttu-id="8a348-162">Fare clic su Completa.</span><span class="sxs-lookup"><span data-stu-id="8a348-162">Click Complete.</span></span>
27. <span data-ttu-id="8a348-163">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="8a348-163">Click OK.</span></span>

