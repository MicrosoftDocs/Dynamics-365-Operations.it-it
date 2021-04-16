---
title: ER Usare file di gestione documenti in output di formato (parte 4 - eseguire il formato)
description: In questo argomento viene descritto come configurare un formato di reporting elettronico per utilizzare i file di gestione dei documenti nell'output ER. (Parte 4)
author: NickSelin
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: CustOpenInvoicesListPage, CustInvoiceJournal, SalesTable, ERSolutionTable
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f7a7c9705d8b53ef13cd3faf13290f3f1b1d1c43
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5749119"
---
# <a name="er-use-document-management-files-in-format-outputs-part-4---run-format"></a><span data-ttu-id="8da1d-104">ER Usare file di gestione documenti in output di formato (parte 4 - eseguire il formato)</span><span class="sxs-lookup"><span data-stu-id="8da1d-104">ER Use Document Management files in format outputs (Part 4 - Run format)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="8da1d-105">I passaggi seguenti descrivono come un utente con ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può configurare un formato per la creazione di report elettronici in modo che utilizzi i file (allegati) di gestione documenti nell'output della creazione di report elettronici.</span><span class="sxs-lookup"><span data-stu-id="8da1d-105">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) format to use Document Management files (attachments) in ER output.</span></span> <span data-ttu-id="8da1d-106">Queste operazioni possono essere eseguite nella società DEMF.</span><span class="sxs-lookup"><span data-stu-id="8da1d-106">These steps can be performed in the DEMF company.</span></span>

<span data-ttu-id="8da1d-107">Per effettuare queste operazioni, è innanzitutto necessario completare i passaggi della procedura "ER Usare i file di gestione documenti negli output di formato (parte 3: creare il formato)".</span><span class="sxs-lookup"><span data-stu-id="8da1d-107">To complete these steps, you must first complete the steps in the "ER Use Document Management files in format outputs (Part 3: Create format)" procedure.</span></span>

<span data-ttu-id="8da1d-108">Questa procedura è per una funzionalità che è stata aggiunta in Dynamics 365 for Operations versione 1611.</span><span class="sxs-lookup"><span data-stu-id="8da1d-108">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="add-necessary-attachments-for-sales-order-of-a-single-invoice"></a><span data-ttu-id="8da1d-109">Aggiungere gli allegati necessari per l'ordine cliente di una singola fattura</span><span class="sxs-lookup"><span data-stu-id="8da1d-109">Add necessary attachments for sales order of a single invoice</span></span>
1. <span data-ttu-id="8da1d-110">Andare a Contabilità clienti > Fatture > Fatture cliente aperte.</span><span class="sxs-lookup"><span data-stu-id="8da1d-110">Go to Accounts receivable > Invoices > Open customer invoices.</span></span>
2. <span data-ttu-id="8da1d-111">Utilizzare il filtro rapido per trovare i record.</span><span class="sxs-lookup"><span data-stu-id="8da1d-111">Use the Quick Filter to find records.</span></span> <span data-ttu-id="8da1d-112">Ad esempio, filtrare in base al campo Fattura con un valore 'CIV-000148'.</span><span class="sxs-lookup"><span data-stu-id="8da1d-112">For example, filter on the Invoice field with a value of 'CIV-000148'.</span></span>
    * <span data-ttu-id="8da1d-113">CIV-000148</span><span class="sxs-lookup"><span data-stu-id="8da1d-113">CIV-000148</span></span>  
3. <span data-ttu-id="8da1d-114">Fare clic su per seguire il collegamento della fattura selezionata.</span><span class="sxs-lookup"><span data-stu-id="8da1d-114">Click to follow the selected invoice's link.</span></span>
    * <span data-ttu-id="8da1d-115">CIV-000148</span><span class="sxs-lookup"><span data-stu-id="8da1d-115">CIV-000148</span></span>  
4. <span data-ttu-id="8da1d-116">Fare clic per seguire il collegamento nel campo Ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="8da1d-116">Click to follow the link in the Sales order field.</span></span>
    * <span data-ttu-id="8da1d-117">000148</span><span class="sxs-lookup"><span data-stu-id="8da1d-117">000148</span></span>  
5. <span data-ttu-id="8da1d-118">Selezionare l'opzione Intestazione nel campo Righe o intestazione.</span><span class="sxs-lookup"><span data-stu-id="8da1d-118">In the Lines or header field, select the option of Header.</span></span>
    * <span data-ttu-id="8da1d-119">Selezionare l'intestazione per indicare che sarà la destinazione per l'aggiunta degli allegati.</span><span class="sxs-lookup"><span data-stu-id="8da1d-119">Select Header to indicate that this will be the target for adding attachments.</span></span>  
6. <span data-ttu-id="8da1d-120">Fare clic su Allega.</span><span class="sxs-lookup"><span data-stu-id="8da1d-120">Click Attach.</span></span>
    * <span data-ttu-id="8da1d-121">Aggiungere alcuni file come allegati per l'ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="8da1d-121">Add a few files as attachments for this sales order.</span></span> <span data-ttu-id="8da1d-122">Utilizzare i file dei tipi di documento che sono supportati dalla gestione documenti (con le estensioni di file DOCX, DPF XML, JPG ecc.).</span><span class="sxs-lookup"><span data-stu-id="8da1d-122">Use the files of the document types that are supported by the Document Management (with file extensions DOCX, DPF, XML, JPG, etc.).</span></span> <span data-ttu-id="8da1d-123">Individuare e selezionare i file da allegare e elaborare ulteriormente con la fattura correlata nel messaggio elettronico della creazione di report elettronici.</span><span class="sxs-lookup"><span data-stu-id="8da1d-123">Browse and select files to be attached and further processed with the related invoice in the ER electronic message.</span></span>  
7. <span data-ttu-id="8da1d-124">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="8da1d-124">Click New.</span></span>
8. <span data-ttu-id="8da1d-125">Fare clic su File.</span><span class="sxs-lookup"><span data-stu-id="8da1d-125">Click File.</span></span>
9. <span data-ttu-id="8da1d-126">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="8da1d-126">Click New.</span></span>
10. <span data-ttu-id="8da1d-127">Fare clic su File.</span><span class="sxs-lookup"><span data-stu-id="8da1d-127">Click File.</span></span>
11. <span data-ttu-id="8da1d-128">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="8da1d-128">Close the page.</span></span>
12. <span data-ttu-id="8da1d-129">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="8da1d-129">Close the page.</span></span>
13. <span data-ttu-id="8da1d-130">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="8da1d-130">Close the page.</span></span>
14. <span data-ttu-id="8da1d-131">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="8da1d-131">Close the page.</span></span>

## <a name="run-the-designed-report-for-the-selected-invoice"></a><span data-ttu-id="8da1d-132">Eseguire il report progettato per la fattura selezionata</span><span class="sxs-lookup"><span data-stu-id="8da1d-132">Run the designed report for the selected invoice</span></span>
1. <span data-ttu-id="8da1d-133">Passare a Amministrazione organizzazione > Reporting elettronico > Configurazioni.</span><span class="sxs-lookup"><span data-stu-id="8da1d-133">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="8da1d-134">Nella struttura espandere 'Modello fattura cliente'.</span><span class="sxs-lookup"><span data-stu-id="8da1d-134">In the tree, expand 'Customer invoice model'.</span></span>
3. <span data-ttu-id="8da1d-135">Nella struttura espandere 'Modello fattura cliente\Modello fattura cliente (personalizzato)'.</span><span class="sxs-lookup"><span data-stu-id="8da1d-135">In the tree, expand 'Customer invoice model\Customer invoice model (custom)'.</span></span>
4. <span data-ttu-id="8da1d-136">Nella struttura selezionare 'Modello fattura cliente\Modello fattura cliente (personalizzato)\Messaggio di esempio fattura elettronica'.</span><span class="sxs-lookup"><span data-stu-id="8da1d-136">In the tree, select 'Customer invoice model\Customer invoice model (custom)\Electronic invoice sample message'.</span></span>
5. <span data-ttu-id="8da1d-137">Fare clic su Esegui.</span><span class="sxs-lookup"><span data-stu-id="8da1d-137">Click Run.</span></span>
6. <span data-ttu-id="8da1d-138">Espandere la sezione Record da includere ().</span><span class="sxs-lookup"><span data-stu-id="8da1d-138">Expand the Records to include () section.</span></span>
7. <span data-ttu-id="8da1d-139">Fare clic su Filtro.</span><span class="sxs-lookup"><span data-stu-id="8da1d-139">Click Filter.</span></span>
8. <span data-ttu-id="8da1d-140">Selezionare la riga del giornale di registrazione fatture cliente e il campo Ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="8da1d-140">Select the row of the Customer invoice journal and the Sales order field.</span></span>
9. <span data-ttu-id="8da1d-141">Nel campo Criteri digitare '000148'.</span><span class="sxs-lookup"><span data-stu-id="8da1d-141">In the Criteria field, type '000148'.</span></span>
    * <span data-ttu-id="8da1d-142">Nel campo "Ordine cliente" di criteri, digitare il numero di ordine 000148.</span><span class="sxs-lookup"><span data-stu-id="8da1d-142">In the criteria "Sales order" field, type the order number 000148.</span></span>  
10. <span data-ttu-id="8da1d-143">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="8da1d-143">Click OK.</span></span>
11. <span data-ttu-id="8da1d-144">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="8da1d-144">Click OK.</span></span>
    * <span data-ttu-id="8da1d-145">Esaminare l'output generato.</span><span class="sxs-lookup"><span data-stu-id="8da1d-145">Review the generated output.</span></span> <span data-ttu-id="8da1d-146">Tenere presente che per ogni collegato un singolo nodo XML è stato creato.</span><span class="sxs-lookup"><span data-stu-id="8da1d-146">Note that for each attachment a single XML node has been created.</span></span> <span data-ttu-id="8da1d-147">Il contenuto dell'allegato viene popolato nell'output XML in formato testo MIME (base64).</span><span class="sxs-lookup"><span data-stu-id="8da1d-147">The attachment's content is populated to the XML output in MIME (base64) text format.</span></span>  



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]