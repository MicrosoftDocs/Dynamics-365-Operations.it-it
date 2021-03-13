---
title: Progettare le configurazioni per generare documenti che contengono dati dell'applicazione
description: Questo argomento descrive come progettare le configurazioni ER per generare un documento elettronico. (Parte 1 - Importare configurazioni).
author: NickSelin
manager: AnnBe
ms.date: 06/19/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 417c419dc6925bac337fe74a2f057395316ec75d
ms.sourcegitcommit: 5192cfaedfd861faea63d8954d7bcc500608a225
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2021
ms.locfileid: "5092924"
---
# <a name="design-configurations-to-generate-documents-that-have-application-data"></a><span data-ttu-id="6af0d-104">Progettare le configurazioni per generare documenti che contengono dati dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="6af0d-104">Design configurations to generate documents that have application data</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="6af0d-105">Per completare i passaggi di questa procedura, è necessario completare la procedura "ER Generare documenti con l'aggiornamento dei dati dell'applicazione (Parte 1: Importare configurazioni).</span><span class="sxs-lookup"><span data-stu-id="6af0d-105">To complete the steps in this procedure, you must first complete the procedure, ER Generate documents with application data update (Part 1: Import configurations).</span></span>



<span data-ttu-id="6af0d-106">I passaggi di questa procedura descrivono come progettare le configurazioni ER per generare un documento elettronico.</span><span class="sxs-lookup"><span data-stu-id="6af0d-106">The steps in this procedure explain how to design Electronic reporting (ER) configurations to generate an electronic document.</span></span> <span data-ttu-id="6af0d-107">In questa procedura verranno eseguite le configurazioni di formati ER importate che sono state create per la società di esempio Litware, Inc. per generare documenti elettronici.</span><span class="sxs-lookup"><span data-stu-id="6af0d-107">In this procedure, you run the ER imported format configuration that has been created for the sample company, Litware, Inc. to generate electronic documents.</span></span>



<span data-ttu-id="6af0d-108">Questa procedura viene creata per utenti con il ruolo di amministratore di sistema o di sviluppatore di report elettronici.</span><span class="sxs-lookup"><span data-stu-id="6af0d-108">This procedure is created for users with the assigned role of system administrator or electronic reporting developer.</span></span> <span data-ttu-id="6af0d-109">Tali passaggi possono essere completati mediante il set di dati DEMF.</span><span class="sxs-lookup"><span data-stu-id="6af0d-109">These steps can be completed using the DEMF dataset.</span></span> 



<span data-ttu-id="6af0d-110">Prima di iniziare, modificare il contesto del paese per la società DEMF da DEU (Germania) a BEL (Belgio).</span><span class="sxs-lookup"><span data-stu-id="6af0d-110">Before you begin, change the country context for the DEMF company from DEU (Germany) to BEL (Belgium).</span></span> <span data-ttu-id="6af0d-111">Fare clic su Amministrazione organizzazione > Organizzazioni > Persone giuridiche per aggiornare il codice paese nell'indirizzo principale della persona giuridica DEMF.</span><span class="sxs-lookup"><span data-stu-id="6af0d-111">Click Organization administration > Organizations > Legal entities to update the country code in the primary address of the legal entity DEMF.</span></span> <span data-ttu-id="6af0d-112">Riavviare l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="6af0d-112">Restart your application.</span></span>


## <a name="run-imported-er-format"></a><span data-ttu-id="6af0d-113">Eseguire il formato ER importato.</span><span class="sxs-lookup"><span data-stu-id="6af0d-113">Run imported ER format</span></span>
1. <span data-ttu-id="6af0d-114">Passare a Amministrazione organizzazione > Reporting elettronico > Configurazioni.</span><span class="sxs-lookup"><span data-stu-id="6af0d-114">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="6af0d-115">Nella struttura espandere "Intrastat (model)".</span><span class="sxs-lookup"><span data-stu-id="6af0d-115">In the tree, expand 'Intrastat (model)'.</span></span>
3. <span data-ttu-id="6af0d-116">Nella struttura selezionare "Intrastat (model)\Intrastat (format)".</span><span class="sxs-lookup"><span data-stu-id="6af0d-116">In the tree, select 'Intrastat (model)\Intrastat (format)'.</span></span>
4. <span data-ttu-id="6af0d-117">Fare clic su Esegui.</span><span class="sxs-lookup"><span data-stu-id="6af0d-117">Click Run.</span></span>
    * <span data-ttu-id="6af0d-118">Eseguire la versione bozza della configurazione dei formati ER per generare il report Intrastat.</span><span class="sxs-lookup"><span data-stu-id="6af0d-118">Run the draft version of the ER format configuration to generate the Intrastat report.</span></span>  
5. <span data-ttu-id="6af0d-119">Nel campo per immettere il nome del file digitare "intrastat.xml".</span><span class="sxs-lookup"><span data-stu-id="6af0d-119">In the Enter file name field, type 'intrastat.xml'.</span></span>
    * <span data-ttu-id="6af0d-120">Specifica il nome del file.</span><span class="sxs-lookup"><span data-stu-id="6af0d-120">Specify the name of the file.</span></span>  
6. <span data-ttu-id="6af0d-121">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="6af0d-121">Click OK.</span></span>
    * <span data-ttu-id="6af0d-122">Esaminare il file XML generato.</span><span class="sxs-lookup"><span data-stu-id="6af0d-122">Review the generated XML file.</span></span>  
7. <span data-ttu-id="6af0d-123">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="6af0d-123">Close the page.</span></span>
8. <span data-ttu-id="6af0d-124">Passare a Imposta > Dichiarazioni > Commercio estero > Intrastat.</span><span class="sxs-lookup"><span data-stu-id="6af0d-124">Go to Tax > Declarations > Foreign trade > Intrastat.</span></span>
    * <span data-ttu-id="6af0d-125">Aprire il modulo per visualizzare le transazioni Intrastat incluse nel documento elettronico generato.</span><span class="sxs-lookup"><span data-stu-id="6af0d-125">Open this form to view the Intrastat transactions that are included in the generated electronic document.</span></span>  
9. <span data-ttu-id="6af0d-126">Fare clic su archivio Intrastat.</span><span class="sxs-lookup"><span data-stu-id="6af0d-126">Click Intrastat archive.</span></span>
    * <span data-ttu-id="6af0d-127">Poiché il formato ER eseguito non contiene impostazioni per l'aggiornamento dei dati dell'applicazione, i dettagli del report Intrastat completato non sono stati archiviati.</span><span class="sxs-lookup"><span data-stu-id="6af0d-127">Because the executed ER format does not contain any settings for application data update, the details of the completed Intrastat report have not been archived.</span></span>  
10. <span data-ttu-id="6af0d-128">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="6af0d-128">Close the page.</span></span>
11. <span data-ttu-id="6af0d-129">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="6af0d-129">Close the page.</span></span>

