--- 
title: Estendere il modello dati per utilizzare i file di gestione documenti nel formato di output per la creazione di report elettronici (ER)
description: "I passaggi seguenti descrivono come un utente con ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può configurare un formato per la creazione di report elettronici in modo che utilizzi i file (allegati) di gestione documenti nell'output della creazione di report elettronici."
author: NickSelin
manager: AnnBe
ms.date: 10/28/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 1a5325dc3a97b9e205b41fe8dae18f43e430daeb
ms.contentlocale: it-it
ms.lasthandoff: 08/29/2017

---
# <a name="extend-data-model-to-use-document-management-files-in-format-outputs-for-electronic-reporting-er"></a><span data-ttu-id="9f323-103">Estendere il modello dati per utilizzare i file di gestione documenti nel formato di output per la creazione di report elettronici (ER)</span><span class="sxs-lookup"><span data-stu-id="9f323-103">Extend data model to use Document Management files in format outputs for electronic reporting (ER)</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="9f323-104">I passaggi seguenti descrivono come un utente con ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può configurare un formato per la creazione di report elettronici in modo che utilizzi i file (allegati) di gestione documenti nell'output della creazione di report elettronici.</span><span class="sxs-lookup"><span data-stu-id="9f323-104">The following steps explain how a user assigned to the System Administrator or Electronic Reporting Developer role can configure an Electronic reporting (ER) format to use Document Management files (attachments) in ER output.</span></span> <span data-ttu-id="9f323-105">Questi passaggi possono essere eseguiti in qualsiasi società.</span><span class="sxs-lookup"><span data-stu-id="9f323-105">These steps can be performed in any company.</span></span>

<span data-ttu-id="9f323-106">Per effettuare queste operazioni, è innanzitutto necessario completare i passaggi della guida attività 'ER Usare i file di gestione documenti negli output di formato (parte 1: preparare il modello dati)'.</span><span class="sxs-lookup"><span data-stu-id="9f323-106">To complete these steps, you must first complete the steps in the “ER Use Document Management files in format outputs (Part 1: Prepare data model)” task guide.</span></span>

<span data-ttu-id="9f323-107">Questa procedura è per una funzionalità che è stata aggiunta in Dynamics 365 for Operations versione 1611.</span><span class="sxs-lookup"><span data-stu-id="9f323-107">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="extend-data-model-to-present-the-document-management-files-in-it"></a><span data-ttu-id="9f323-108">Estendere il modello dati per presentare i file di gestione documenti al suo interno</span><span class="sxs-lookup"><span data-stu-id="9f323-108">Extend data model to present the Document Management files in it</span></span>
1. <span data-ttu-id="9f323-109">Andare ad Amministrazione organizzazione > Aree di lavoro > Creazione di report elettronici.</span><span class="sxs-lookup"><span data-stu-id="9f323-109">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="9f323-110">Fare clic su Configurazioni report.</span><span class="sxs-lookup"><span data-stu-id="9f323-110">Click Reporting configurations.</span></span>
3. <span data-ttu-id="9f323-111">Nella struttura espandere 'Modello fattura cliente'.</span><span class="sxs-lookup"><span data-stu-id="9f323-111">In the tree, expand 'Customer invoice model'.</span></span>
4. <span data-ttu-id="9f323-112">Nella struttura selezionare 'Modello fattura cliente\Modello fattura cliente (personalizzato)'.</span><span class="sxs-lookup"><span data-stu-id="9f323-112">In the tree, select 'Customer invoice model\Customer invoice model (custom)'.</span></span>
5. <span data-ttu-id="9f323-113">Fare clic su Progettazione.</span><span class="sxs-lookup"><span data-stu-id="9f323-113">Click Designer.</span></span>
6. <span data-ttu-id="9f323-114">Nella struttura selezionare 'Fattura cliente(InvoiceCustomer)'.</span><span class="sxs-lookup"><span data-stu-id="9f323-114">In the tree, select 'Customer invoice(InvoiceCustomer)'.</span></span>
    * <span data-ttu-id="9f323-115">Estenderemo questo modello dati per esporvi qualsiasi file allegato a un ordine cliente correlato a una fattura elaborata elettronicamente.</span><span class="sxs-lookup"><span data-stu-id="9f323-115">We will extend this data model to expose in it any files that have been attached to a sales order that is related to an electronically processing invoice.</span></span>  
7. <span data-ttu-id="9f323-116">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="9f323-116">Click New to open the drop dialog.</span></span>
8. <span data-ttu-id="9f323-117">Nel campo Nome digitare 'Allegati fattura'.</span><span class="sxs-lookup"><span data-stu-id="9f323-117">In the Name field, type 'Invoice attachments'.</span></span>
    * <span data-ttu-id="9f323-118">Allegati fattura</span><span class="sxs-lookup"><span data-stu-id="9f323-118">Invoice attachments</span></span>  
9. <span data-ttu-id="9f323-119">Nel campo Tipo di articolo selezionare "Elenco di record".</span><span class="sxs-lookup"><span data-stu-id="9f323-119">In the Item type field, select 'Record list'.</span></span>
10. <span data-ttu-id="9f323-120">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="9f323-120">Click Add.</span></span>
11. <span data-ttu-id="9f323-121">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="9f323-121">Click New to open the drop dialog.</span></span>
12. <span data-ttu-id="9f323-122">Digitare 'Contenuto file' nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="9f323-122">In the Name field, type 'File content'.</span></span>
    * <span data-ttu-id="9f323-123">Contenuto file</span><span class="sxs-lookup"><span data-stu-id="9f323-123">File content</span></span>  
13. <span data-ttu-id="9f323-124">Nel campo Tipo di articolo selezionare 'Contenitore'.</span><span class="sxs-lookup"><span data-stu-id="9f323-124">In the Item type field, select 'Container'.</span></span>
14. <span data-ttu-id="9f323-125">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="9f323-125">Click Add.</span></span>
15. <span data-ttu-id="9f323-126">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="9f323-126">Click New to open the drop dialog.</span></span>
16. <span data-ttu-id="9f323-127">Nel campo Nome digitare 'Nome file'.</span><span class="sxs-lookup"><span data-stu-id="9f323-127">In the Name field, type 'File name'.</span></span>
    * <span data-ttu-id="9f323-128">Nome file</span><span class="sxs-lookup"><span data-stu-id="9f323-128">File name</span></span>  
17. <span data-ttu-id="9f323-129">Nel campo Tipo di articolo selezionare "Stringa".</span><span class="sxs-lookup"><span data-stu-id="9f323-129">In the Item type field, select 'String'.</span></span>
18. <span data-ttu-id="9f323-130">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="9f323-130">Click Add.</span></span>

## <a name="map-new-data-model-elements-to-dynamics-365-for-finance-and-operations-enterprise-edition-data-sources"></a><span data-ttu-id="9f323-131">Mappare gli elementi del nuovo modello dati alle origini dati di Dynamics 365 for Finance and Operations, Enterprise edition</span><span class="sxs-lookup"><span data-stu-id="9f323-131">Map new data model elements to Dynamics 365 for Finance and Operations, Enterprise edition data sources</span></span>
1. <span data-ttu-id="9f323-132">Fare clic su Mappa modello a origine dati.</span><span class="sxs-lookup"><span data-stu-id="9f323-132">Click Map model to datasource.</span></span>
2. <span data-ttu-id="9f323-133">Utilizzare il filtro rapido per filtrare in base al campo Definizione con un valore di 'InvoiceCustomer'.</span><span class="sxs-lookup"><span data-stu-id="9f323-133">Use the Quick Filter to filter on the Definition field with a value of 'InvoiceCustomer'.</span></span>
    * <span data-ttu-id="9f323-134">InvoiceCustomer</span><span class="sxs-lookup"><span data-stu-id="9f323-134">InvoiceCustomer</span></span>  
    * <span data-ttu-id="9f323-135">Mapperemo gli elementi del nuovo modello alle origini dati appropriate.</span><span class="sxs-lookup"><span data-stu-id="9f323-135">We will map new model elements to appropriate data sources.</span></span>  
3. <span data-ttu-id="9f323-136">Fare clic su Progettazione.</span><span class="sxs-lookup"><span data-stu-id="9f323-136">Click Designer.</span></span>
4. <span data-ttu-id="9f323-137">Nella struttura selezionare 'Allegati fattura'.</span><span class="sxs-lookup"><span data-stu-id="9f323-137">In the tree, select 'Invoice attachments'.</span></span>
5. <span data-ttu-id="9f323-138">Nella struttura espandere 'Allegati fattura'.</span><span class="sxs-lookup"><span data-stu-id="9f323-138">In the tree, expand 'Invoice attachments'.</span></span>
6. <span data-ttu-id="9f323-139">Nella struttura selezionare 'Allegati fattura\Nome file'.</span><span class="sxs-lookup"><span data-stu-id="9f323-139">In the tree, select 'Invoice attachments\File name'.</span></span>
7. <span data-ttu-id="9f323-140">Fare clic su Modifica.</span><span class="sxs-lookup"><span data-stu-id="9f323-140">Click Edit.</span></span>
8. <span data-ttu-id="9f323-141">Nel campo Formula immettere 'CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'originalFileName()''.</span><span class="sxs-lookup"><span data-stu-id="9f323-141">In the Formula field, enter 'CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'originalFileName()''.</span></span>
    * <span data-ttu-id="9f323-142">CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'originalFileName()'</span><span class="sxs-lookup"><span data-stu-id="9f323-142">CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'originalFileName()'</span></span>  
9. <span data-ttu-id="9f323-143">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="9f323-143">Click Save.</span></span>
10. <span data-ttu-id="9f323-144">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="9f323-144">Close the page.</span></span>
11. <span data-ttu-id="9f323-145">Nella struttura selezionare 'Allegati fattura\Contenuto file'.</span><span class="sxs-lookup"><span data-stu-id="9f323-145">In the tree, select 'Invoice attachments\File content'.</span></span>
12. <span data-ttu-id="9f323-146">Fare clic su Modifica.</span><span class="sxs-lookup"><span data-stu-id="9f323-146">Click Edit.</span></span>
13. <span data-ttu-id="9f323-147">Nel campo Formula immettere 'CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'getFileContentAsContainer()''.</span><span class="sxs-lookup"><span data-stu-id="9f323-147">In the Formula field, enter 'CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'getFileContentAsContainer()''.</span></span>
    * <span data-ttu-id="9f323-148">CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'getFileContentAsContainer()'</span><span class="sxs-lookup"><span data-stu-id="9f323-148">CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'getFileContentAsContainer()'</span></span>  
14. <span data-ttu-id="9f323-149">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="9f323-149">Click Save.</span></span>
15. <span data-ttu-id="9f323-150">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="9f323-150">Close the page.</span></span>
16. <span data-ttu-id="9f323-151">Nella struttura selezionare 'Allegati fattura'.</span><span class="sxs-lookup"><span data-stu-id="9f323-151">In the tree, select 'Invoice attachments'.</span></span>
17. <span data-ttu-id="9f323-152">Fare clic su Modifica.</span><span class="sxs-lookup"><span data-stu-id="9f323-152">Click Edit.</span></span>
18. <span data-ttu-id="9f323-153">Nel campo Formula immettere 'CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents''.</span><span class="sxs-lookup"><span data-stu-id="9f323-153">In the Formula field, enter 'CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents''.</span></span>
    * <span data-ttu-id="9f323-154">CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'</span><span class="sxs-lookup"><span data-stu-id="9f323-154">CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'</span></span>  
19. <span data-ttu-id="9f323-155">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="9f323-155">Click Save.</span></span>
20. <span data-ttu-id="9f323-156">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="9f323-156">Close the page.</span></span>
21. <span data-ttu-id="9f323-157">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="9f323-157">Click Save.</span></span>
22. <span data-ttu-id="9f323-158">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="9f323-158">Close the page.</span></span>
23. <span data-ttu-id="9f323-159">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="9f323-159">Close the page.</span></span>
24. <span data-ttu-id="9f323-160">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="9f323-160">Close the page.</span></span>
25. <span data-ttu-id="9f323-161">Fare clic su Cambia stato.</span><span class="sxs-lookup"><span data-stu-id="9f323-161">Click Change status.</span></span>
26. <span data-ttu-id="9f323-162">Fare clic su Completa.</span><span class="sxs-lookup"><span data-stu-id="9f323-162">Click Complete.</span></span>
27. <span data-ttu-id="9f323-163">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="9f323-163">Click OK.</span></span>


