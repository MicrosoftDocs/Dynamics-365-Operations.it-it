---
title: Generare documenti che contengono dati dell'applicazione
description: "Per completare i passaggi di questa procedura, è necessario completare la procedura \"ER Generare documenti con l'aggiornamento dei dati dell'applicazione (Parte 4: Modificare il formato)\"."
author: NickSelin
manager: AnnBe
ms.date: 06/19/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 759869577ef30cd3f81eb74103a93cc5d1a3d608
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/12/2020
ms.locfileid: "3042852"
---
# <a name="generate-documents-that-have-application-data"></a><span data-ttu-id="8eb2c-103">Generare documenti che contengono dati dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="8eb2c-103">Generate documents that have application data</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="8eb2c-104">Per completare i passaggi di questa procedura, è necessario completare la procedura "ER Generare documenti con l'aggiornamento dei dati dell'applicazione (Parte 4: Modificare il formato)".</span><span class="sxs-lookup"><span data-stu-id="8eb2c-104">To complete the steps in this procedure, you must first complete the procedure, “ER Generate documents with application data update (Part 4: Modify format)”.</span></span>



<span data-ttu-id="8eb2c-105">I passaggi di questa procedura descrivono come progettare le configurazioni ER per generare un documento elettronico e aggiornare i dati dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="8eb2c-105">The steps in this procedure explain how to design Electronic reporting (ER) configurations to generate an electronic document and update application data.</span></span> <span data-ttu-id="8eb2c-106">In questa procedura si esegue la configurazione dei formati ER per generare la dichiarazione Intrastat e aggiornare i dati dell'applicazione per archiviare i dettagli del processo di dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="8eb2c-106">In this procedure, you execute the ER format configuration to generate the Intrastat report and update application data for archiving details of the reporting process.</span></span>



<span data-ttu-id="8eb2c-107">Questa procedura viene creata per utenti con il ruolo di amministratore di sistema o di sviluppatore di report elettronici.</span><span class="sxs-lookup"><span data-stu-id="8eb2c-107">This procedure is created for users with the assigned role of system administrator or electronic reporting developer.</span></span> <span data-ttu-id="8eb2c-108">Tali passaggi possono essere completati mediante il set di dati DEMF.</span><span class="sxs-lookup"><span data-stu-id="8eb2c-108">These steps can be completed using the DEMF dataset.</span></span> <span data-ttu-id="8eb2c-109">Prima di iniziare, assicurarsi che il contesto del paese per la società DEMF sia BEL (Belgio).</span><span class="sxs-lookup"><span data-stu-id="8eb2c-109">Before you begin, make sure that the country context for the DEMF company is BEL (Belgium).</span></span>


## <a name="set-up-foreign-trade-parameters"></a><span data-ttu-id="8eb2c-110">Imposta parametri per il commercio estero</span><span class="sxs-lookup"><span data-stu-id="8eb2c-110">Set up foreign trade parameters</span></span>
1. <span data-ttu-id="8eb2c-111">Passare a Imposta > Impostazione > Commercio estero > Parametri per il commercio estero.</span><span class="sxs-lookup"><span data-stu-id="8eb2c-111">Go to Tax > Setup > Foreign trade > Foreign trade parameters.</span></span>
2. <span data-ttu-id="8eb2c-112">Fare clic sulla scheda Sequenze numeriche.</span><span class="sxs-lookup"><span data-stu-id="8eb2c-112">Click the Number sequences tab.</span></span>

    <span data-ttu-id="8eb2c-113">Archiviando i dettagli del processo di dichiarazione Intrastat, dobbiamo identificare i record di ogni archivio creato.</span><span class="sxs-lookup"><span data-stu-id="8eb2c-113">Archiving details of Intrastat reporting process, we need to identify records of each archive we created.</span></span> <span data-ttu-id="8eb2c-114">A tale scopo è necessario configurare una sequenza numerica speciale.</span><span class="sxs-lookup"><span data-stu-id="8eb2c-114">A special number sequence must be configured for that.</span></span>  

3. <span data-ttu-id="8eb2c-115">Selezionare il riferimento 'ID archivio Intrastat'.</span><span class="sxs-lookup"><span data-stu-id="8eb2c-115">Select the ‘Intrastat archive ID’ reference.</span></span>
4. <span data-ttu-id="8eb2c-116">Nel campo Codice sequenza numerica selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="8eb2c-116">In the Number sequence code field, type a value.</span></span>

    <span data-ttu-id="8eb2c-117">Nel campo 'Codice sequenza numerica' immettere o selezionare il valore 'Fore_2'.</span><span class="sxs-lookup"><span data-stu-id="8eb2c-117">In the ‘Number sequence code’ field, enter or select the value ‘Fore_2’.</span></span>  

5. <span data-ttu-id="8eb2c-118">Risolvere le modifiche al codice della sequenza numerica.</span><span class="sxs-lookup"><span data-stu-id="8eb2c-118">ResolveChanges the Number sequence code.</span></span>
6. <span data-ttu-id="8eb2c-119">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="8eb2c-119">Click Save.</span></span>
7. <span data-ttu-id="8eb2c-120">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="8eb2c-120">Close the page.</span></span>

## <a name="run-modified-er-format"></a><span data-ttu-id="8eb2c-121">Eseguire il formato ER modificato</span><span class="sxs-lookup"><span data-stu-id="8eb2c-121">Run modified ER format</span></span>
1. <span data-ttu-id="8eb2c-122">Passare a Amministrazione organizzazione > Reporting elettronico > Configurazioni.</span><span class="sxs-lookup"><span data-stu-id="8eb2c-122">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="8eb2c-123">Nella struttura espandere "Intrastat (model)".</span><span class="sxs-lookup"><span data-stu-id="8eb2c-123">In the tree, expand 'Intrastat (model)'.</span></span>
3. <span data-ttu-id="8eb2c-124">Nella struttura selezionare "Intrastat (model)\Intrastat (format)".</span><span class="sxs-lookup"><span data-stu-id="8eb2c-124">In the tree, select 'Intrastat (model)\Intrastat (format)'.</span></span>
4. <span data-ttu-id="8eb2c-125">Fare clic su Esegui.</span><span class="sxs-lookup"><span data-stu-id="8eb2c-125">Click Run.</span></span>
5. <span data-ttu-id="8eb2c-126">Nel campo per immettere il nome del file digitare "intrastat2.xml".</span><span class="sxs-lookup"><span data-stu-id="8eb2c-126">In the Enter file name field, type 'intrastat2.xml'.</span></span>
6. <span data-ttu-id="8eb2c-127">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="8eb2c-127">Click OK.</span></span>

## <a name="review-er-format-executions-results"></a><span data-ttu-id="8eb2c-128">Esaminare i risultati dell'esecuzione del formato ER</span><span class="sxs-lookup"><span data-stu-id="8eb2c-128">Review ER format execution’s results</span></span>
<span data-ttu-id="8eb2c-129">Esaminare il file XML generato.</span><span class="sxs-lookup"><span data-stu-id="8eb2c-129">Review the generated XML file.</span></span>  
1. <span data-ttu-id="8eb2c-130">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="8eb2c-130">Close the page.</span></span>
2. <span data-ttu-id="8eb2c-131">Passare a Imposta > Dichiarazioni > Commercio estero > Intrastat.</span><span class="sxs-lookup"><span data-stu-id="8eb2c-131">Go to Tax > Declarations > Foreign trade > Intrastat.</span></span>

    <span data-ttu-id="8eb2c-132">Aprire il modulo contenente le transazioni Intrastat incluse nel documento elettronico generato.</span><span class="sxs-lookup"><span data-stu-id="8eb2c-132">Open this form containing Intrastat transactions that have been included to the generated electronic document.</span></span>  

3. <span data-ttu-id="8eb2c-133">Fare clic su archivio Intrastat.</span><span class="sxs-lookup"><span data-stu-id="8eb2c-133">Click Intrastat archive.</span></span>

    <span data-ttu-id="8eb2c-134">Poiché il formato ER eseguito contiene ora impostazioni per l'aggiornamento dei dati dell'applicazione, i dettagli della dichiarazione Intrastat completata sono stati archiviati.</span><span class="sxs-lookup"><span data-stu-id="8eb2c-134">Since the executed ER format contains now settings for application data update, the details of the completed Intrastat reporting have been archived.</span></span> <span data-ttu-id="8eb2c-135">In questo modulo, è possibile visualizzare il record di intestazione dell'archivio creato.</span><span class="sxs-lookup"><span data-stu-id="8eb2c-135">In this form, you can see the header record of the created archive.</span></span>  

4. <span data-ttu-id="8eb2c-136">Fare clic su Dettagli.</span><span class="sxs-lookup"><span data-stu-id="8eb2c-136">Click Details.</span></span>

    <span data-ttu-id="8eb2c-137">In questo modulo, è possibile visualizzare i dettagli dell'archivio creato.</span><span class="sxs-lookup"><span data-stu-id="8eb2c-137">In this form, you can see the details for the created archive.</span></span>  

5. <span data-ttu-id="8eb2c-138">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="8eb2c-138">Close the page.</span></span>
6. <span data-ttu-id="8eb2c-139">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="8eb2c-139">Close the page.</span></span>
7. <span data-ttu-id="8eb2c-140">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="8eb2c-140">Close the page.</span></span>

