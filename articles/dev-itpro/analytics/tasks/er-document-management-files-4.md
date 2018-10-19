--- 
title: Eseguire i formati per utilizzare i file di gestione documenti nell'output di ER
description: "I passaggi seguenti descrivono come un utente con ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può configurare un formato per la creazione di report elettronici in modo che utilizzi i file (allegati) di gestione documenti nell'output della creazione di report elettronici."
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CustOpenInvoicesListPage, CustInvoiceJournal, SalesTable, ERSolutionTable
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: e87dbb0fa890f4d554c3e2ff09566fb2b1f3206b
ms.contentlocale: it-it
ms.lasthandoff: 10/16/2018

---
# <a name="run-formats-to-use-document-management-files-in-er-output"></a><span data-ttu-id="0ff22-103">Eseguire i formati per utilizzare i file di gestione documenti nell'output di ER</span><span class="sxs-lookup"><span data-stu-id="0ff22-103">Run formats to use Document Management files in ER output</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="0ff22-104">I passaggi seguenti descrivono come un utente con ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può configurare un formato per la creazione di report elettronici in modo che utilizzi i file (allegati) di gestione documenti nell'output della creazione di report elettronici.</span><span class="sxs-lookup"><span data-stu-id="0ff22-104">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) format to use Document Management files (attachments) in ER output.</span></span> <span data-ttu-id="0ff22-105">Queste operazioni possono essere eseguite nella società DEMF.</span><span class="sxs-lookup"><span data-stu-id="0ff22-105">These steps can be performed in the DEMF company.</span></span>

<span data-ttu-id="0ff22-106">Per effettuare queste operazioni, è innanzitutto necessario completare i passaggi della procedura 'ER Usare i file di gestione documenti negli output di formato (parte 3: creare il formato)'.</span><span class="sxs-lookup"><span data-stu-id="0ff22-106">To complete these steps, you must first complete the steps in the “ER Use Document Management files in format outputs (Part 3: Create format)” procedure.</span></span>

<span data-ttu-id="0ff22-107">Questa procedura è per una funzionalità che è stata aggiunta in Dynamics 365 for Operations versione 1611.</span><span class="sxs-lookup"><span data-stu-id="0ff22-107">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="add-necessary-attachments-for-sales-order-of-a-single-invoice"></a><span data-ttu-id="0ff22-108">Aggiungere gli allegati necessari per l'ordine cliente di una singola fattura</span><span class="sxs-lookup"><span data-stu-id="0ff22-108">Add necessary attachments for sales order of a single invoice</span></span>
1. <span data-ttu-id="0ff22-109">Andare a Contabilità clienti > Fatture > Fatture cliente aperte.</span><span class="sxs-lookup"><span data-stu-id="0ff22-109">Go to Accounts receivable > Invoices > Open customer invoices.</span></span>
2. <span data-ttu-id="0ff22-110">Utilizzare il filtro rapido per trovare i record.</span><span class="sxs-lookup"><span data-stu-id="0ff22-110">Use the Quick Filter to find records.</span></span> <span data-ttu-id="0ff22-111">Ad esempio, filtrare in base al campo Fattura con un valore 'CIV-000148'.</span><span class="sxs-lookup"><span data-stu-id="0ff22-111">For example, filter on the Invoice field with a value of 'CIV-000148'.</span></span>
    * <span data-ttu-id="0ff22-112">CIV-000148</span><span class="sxs-lookup"><span data-stu-id="0ff22-112">CIV-000148</span></span>  
3. <span data-ttu-id="0ff22-113">Fare clic su per seguire il collegamento della fattura selezionata.</span><span class="sxs-lookup"><span data-stu-id="0ff22-113">Click to follow the selected invoice’s link.</span></span>
    * <span data-ttu-id="0ff22-114">CIV-000148</span><span class="sxs-lookup"><span data-stu-id="0ff22-114">CIV-000148</span></span>  
4. <span data-ttu-id="0ff22-115">Fare clic per seguire il collegamento nel campo Ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="0ff22-115">Click to follow the link in the Sales order field.</span></span>
    * <span data-ttu-id="0ff22-116">000148</span><span class="sxs-lookup"><span data-stu-id="0ff22-116">000148</span></span>  
5. <span data-ttu-id="0ff22-117">Selezionare l'opzione Intestazione nel campo Righe o intestazione.</span><span class="sxs-lookup"><span data-stu-id="0ff22-117">In the Lines or header field, select the option of Header.</span></span>
    * <span data-ttu-id="0ff22-118">Selezionare l'intestazione per indicare che sarà la destinazione per l'aggiunta degli allegati.</span><span class="sxs-lookup"><span data-stu-id="0ff22-118">Select Header to indicate that this will be the target for adding attachments.</span></span>  
6. <span data-ttu-id="0ff22-119">Fare clic su Allega.</span><span class="sxs-lookup"><span data-stu-id="0ff22-119">Click Attach.</span></span>
    * <span data-ttu-id="0ff22-120">Aggiungere alcuni file come allegati per l'ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="0ff22-120">Add a few files as attachments for this sales order.</span></span> <span data-ttu-id="0ff22-121">Utilizzare i file dei tipi di documento che sono supportati dalla gestione documenti (con le estensioni di file DOCX, DPF XML, JPG ecc.).</span><span class="sxs-lookup"><span data-stu-id="0ff22-121">Use the files of the document types that are supported by the Document Management (with file extensions DOCX, DPF, XML, JPG, etc.).</span></span> <span data-ttu-id="0ff22-122">Individuare e selezionare i file da allegare e elaborare ulteriormente con la fattura correlata nel messaggio elettronico della creazione di report elettronici.</span><span class="sxs-lookup"><span data-stu-id="0ff22-122">Browse and select files to be attached and further processed with the related invoice in the ER electronic message.</span></span>  
7. <span data-ttu-id="0ff22-123">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="0ff22-123">Click New.</span></span>
8. <span data-ttu-id="0ff22-124">Fare clic su File.</span><span class="sxs-lookup"><span data-stu-id="0ff22-124">Click File.</span></span>
9. <span data-ttu-id="0ff22-125">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="0ff22-125">Click New.</span></span>
10. <span data-ttu-id="0ff22-126">Fare clic su File.</span><span class="sxs-lookup"><span data-stu-id="0ff22-126">Click File.</span></span>
11. <span data-ttu-id="0ff22-127">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="0ff22-127">Close the page.</span></span>
12. <span data-ttu-id="0ff22-128">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="0ff22-128">Close the page.</span></span>
13. <span data-ttu-id="0ff22-129">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="0ff22-129">Close the page.</span></span>
14. <span data-ttu-id="0ff22-130">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="0ff22-130">Close the page.</span></span>

## <a name="run-the-designed-report-for-the-selected-invoice"></a><span data-ttu-id="0ff22-131">Eseguire il report progettato per la fattura selezionata</span><span class="sxs-lookup"><span data-stu-id="0ff22-131">Run the designed report for the selected invoice</span></span>
1. <span data-ttu-id="0ff22-132">Passare a Amministrazione organizzazione > Reporting elettronico > Configurazioni.</span><span class="sxs-lookup"><span data-stu-id="0ff22-132">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="0ff22-133">Nella struttura espandere 'Modello fattura cliente'.</span><span class="sxs-lookup"><span data-stu-id="0ff22-133">In the tree, expand 'Customer invoice model'.</span></span>
3. <span data-ttu-id="0ff22-134">Nella struttura espandere 'Modello fattura cliente\Modello fattura cliente (personalizzato)'.</span><span class="sxs-lookup"><span data-stu-id="0ff22-134">In the tree, expand 'Customer invoice model\Customer invoice model (custom)'.</span></span>
4. <span data-ttu-id="0ff22-135">Nella struttura selezionare 'Modello fattura cliente\Modello fattura cliente (personalizzato)\Messaggio di esempio fattura elettronica'.</span><span class="sxs-lookup"><span data-stu-id="0ff22-135">In the tree, select 'Customer invoice model\Customer invoice model (custom)\Electronic invoice sample message'.</span></span>
5. <span data-ttu-id="0ff22-136">Fare clic su Esegui.</span><span class="sxs-lookup"><span data-stu-id="0ff22-136">Click Run.</span></span>
6. <span data-ttu-id="0ff22-137">Espandere la sezione Record da includere ().</span><span class="sxs-lookup"><span data-stu-id="0ff22-137">Expand the Records to include () section.</span></span>
7. <span data-ttu-id="0ff22-138">Fare clic su Filtro.</span><span class="sxs-lookup"><span data-stu-id="0ff22-138">Click Filter.</span></span>
8. <span data-ttu-id="0ff22-139">Selezionare la riga del giornale di registrazione fatture cliente e il campo Ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="0ff22-139">Select the row of the Customer invoice journal and the Sales order field.</span></span>
9. <span data-ttu-id="0ff22-140">Nel campo Criteri digitare '000148'.</span><span class="sxs-lookup"><span data-stu-id="0ff22-140">In the Criteria field, type '000148'.</span></span>
    * <span data-ttu-id="0ff22-141">Nel campo "Ordine cliente" di criteri, digitare il numero di ordine 000148.</span><span class="sxs-lookup"><span data-stu-id="0ff22-141">In the criteria “Sales order” field, type the order number 000148.</span></span>  
10. <span data-ttu-id="0ff22-142">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="0ff22-142">Click OK.</span></span>
11. <span data-ttu-id="0ff22-143">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="0ff22-143">Click OK.</span></span>
    * <span data-ttu-id="0ff22-144">Esaminare l'output generato.</span><span class="sxs-lookup"><span data-stu-id="0ff22-144">Review the generated output.</span></span> <span data-ttu-id="0ff22-145">Tenere presente che per ogni collegato un singolo nodo XML è stato creato.</span><span class="sxs-lookup"><span data-stu-id="0ff22-145">Note that for each attachment a single XML node has been created.</span></span> <span data-ttu-id="0ff22-146">Il contenuto dell'allegato viene popolato nell'output XML in formato testo MIME (base64).</span><span class="sxs-lookup"><span data-stu-id="0ff22-146">The attachment’s content is populated to the XML output in MIME (base64) text format.</span></span>  


