---
title: 'ER Usare file di gestione documenti in output di formato (Parte 1: Preparare il modello dati)'
description: I passaggi seguenti descrivono come un utente con ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può configurare un formato per la creazione di report elettronici in modo che utilizzi i file (allegati) di gestione documenti nell'output della creazione di report elettronici.
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERVendorPart, ERSolutionRepositoryTable, ERSolutionRepositoryCreateDropDialog, ERSolutionImport,  ERSolutionTable, ERSolutionCreateDropDialog
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 800df13e1654bc01304411bfa52f4bbd04e6589a
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/18/2020
ms.locfileid: "3142065"
---
# <a name="er-use-document-management-files-in-format-outputs-part-1---prepare-data-model"></a><span data-ttu-id="5fc5a-103">ER Usare file di gestione documenti in output di formato (Parte 1: Preparare il modello dati)</span><span class="sxs-lookup"><span data-stu-id="5fc5a-103">ER Use Document Management files in format outputs (Part 1 - Prepare data model)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="5fc5a-104">I passaggi seguenti descrivono come un utente con ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può configurare un formato per la creazione di report elettronici in modo che utilizzi i file (allegati) di gestione documenti nell'output della creazione di report elettronici.</span><span class="sxs-lookup"><span data-stu-id="5fc5a-104">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) format to use Document Management files (attachments) in ER output.</span></span> <span data-ttu-id="5fc5a-105">Questi passaggi possono essere eseguiti in qualsiasi società.</span><span class="sxs-lookup"><span data-stu-id="5fc5a-105">These steps can be performed in any company.</span></span>

<span data-ttu-id="5fc5a-106">Per completare questi passaggi, è necessario completare i passaggi della procedura "Creare un provider di configurazione e contrassegnarlo come attivo".</span><span class="sxs-lookup"><span data-stu-id="5fc5a-106">To complete these steps, you must first complete the steps in the "Create a configuration provider and mark it as active" procedure.</span></span>

<span data-ttu-id="5fc5a-107">Questa procedura è per una funzionalità che è stata aggiunta in Dynamics 365 for Operations versione 1611.</span><span class="sxs-lookup"><span data-stu-id="5fc5a-107">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="get-access-to-the-list-of-configurations-provided-by-microsoft"></a><span data-ttu-id="5fc5a-108">Ottenere l'accesso all'elenco delle configurazioni fornite da Microsoft</span><span class="sxs-lookup"><span data-stu-id="5fc5a-108">Get access to the list of configurations provided by Microsoft</span></span>
1. <span data-ttu-id="5fc5a-109">Andare ad Amministrazione organizzazione > Aree di lavoro > Creazione di report elettronici.</span><span class="sxs-lookup"><span data-stu-id="5fc5a-109">Go to Organization administration > Workspaces > Electronic reporting.</span></span>

    <span data-ttu-id="5fc5a-110">Assicurarsi che il provider Litware, Inc.</span><span class="sxs-lookup"><span data-stu-id="5fc5a-110">Make sure that the 'Litware, Inc.'</span></span> <span data-ttu-id="5fc5a-111">sia disponibile e contrassegnato come attivo.</span><span class="sxs-lookup"><span data-stu-id="5fc5a-111">provider is available and marked as active.</span></span>  

2. <span data-ttu-id="5fc5a-112">Selezionare il provider Litware, Inc</span><span class="sxs-lookup"><span data-stu-id="5fc5a-112">Select the 'Litware, Inc.'</span></span> <span data-ttu-id="5fc5a-113">.</span><span class="sxs-lookup"><span data-stu-id="5fc5a-113">provider.</span></span>
3. <span data-ttu-id="5fc5a-114">Fare clic su Archivi.</span><span class="sxs-lookup"><span data-stu-id="5fc5a-114">Click Repositories.</span></span>

    <span data-ttu-id="5fc5a-115">Se un archivio di tipo 'Risorse operative' esiste già, ignorare i passaggi restanti della sottoattività corrente.</span><span class="sxs-lookup"><span data-stu-id="5fc5a-115">If a repository of the 'Operations resources' type already exists, skip the remaining steps of the current sub-task.</span></span>  

4. <span data-ttu-id="5fc5a-116">Fare clic su Aggiungi per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="5fc5a-116">Click Add to open the drop dialog.</span></span>
5. <span data-ttu-id="5fc5a-117">Nel campo Tipo di archivio di configurazioni immettere 'Risorse operative'.</span><span class="sxs-lookup"><span data-stu-id="5fc5a-117">In the Configuration repository type field, enter 'Operations resources'.</span></span>
6. <span data-ttu-id="5fc5a-118">Fare clic su Crea archivio.</span><span class="sxs-lookup"><span data-stu-id="5fc5a-118">Click Create repository.</span></span>
7. <span data-ttu-id="5fc5a-119">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="5fc5a-119">Click OK.</span></span>

## <a name="get-the-customer-invoice-model-configurations-provided-by-microsoft"></a><span data-ttu-id="5fc5a-120">Ottenere le configurazioni del modello fattura cliente fornite da Microsoft</span><span class="sxs-lookup"><span data-stu-id="5fc5a-120">Get the Customer invoice model configurations provided by Microsoft</span></span>
1. <span data-ttu-id="5fc5a-121">Fare clic su Mostra filtri.</span><span class="sxs-lookup"><span data-stu-id="5fc5a-121">Click Show filters.</span></span>
2. <span data-ttu-id="5fc5a-122">Applicare filtri i seguenti: Immettere un valore di filtro "Risorse operative" nel campo "Nome" utilizzando l'operatore di filtro "inizia con"; Immettere un valore di filtro di "" nel campo "Descrizione" utilizzando l'operatore di filtro "inizia con"</span><span class="sxs-lookup"><span data-stu-id="5fc5a-122">Apply the following filters: Enter a filter value of "Operations resources" on the "Name" field using the "begins with" filter operator; Enter a filter value of "" on the "Description" field using the "begins with" filter operator</span></span>
3. <span data-ttu-id="5fc5a-123">Fare clic su Mostra filtri.</span><span class="sxs-lookup"><span data-stu-id="5fc5a-123">Click Show filters.</span></span>
4. <span data-ttu-id="5fc5a-124">Fare clic su Apri.</span><span class="sxs-lookup"><span data-stu-id="5fc5a-124">Click Open.</span></span>
5. <span data-ttu-id="5fc5a-125">Nella struttura selezionare 'Modello fattura cliente'.</span><span class="sxs-lookup"><span data-stu-id="5fc5a-125">In the tree, select 'Customer invoice model'.</span></span>

    <span data-ttu-id="5fc5a-126">Selezionare la configurazione modello 'Modello fattura cliente' per importarla.</span><span class="sxs-lookup"><span data-stu-id="5fc5a-126">Select the model configuration 'Customer invoice model' to import it.</span></span>  

6. <span data-ttu-id="5fc5a-127">Fare clic su Importa.</span><span class="sxs-lookup"><span data-stu-id="5fc5a-127">Click Import.</span></span>

    <span data-ttu-id="5fc5a-128">Fare clic su Importa per la versione 1 della configurazione selezionata.</span><span class="sxs-lookup"><span data-stu-id="5fc5a-128">Click Import for version 1 of the selected configuration.</span></span>  

7. <span data-ttu-id="5fc5a-129">Fare clic su Sì.</span><span class="sxs-lookup"><span data-stu-id="5fc5a-129">Click Yes.</span></span>
8. <span data-ttu-id="5fc5a-130">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="5fc5a-130">Close the page.</span></span>
9. <span data-ttu-id="5fc5a-131">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="5fc5a-131">Close the page.</span></span>
10. <span data-ttu-id="5fc5a-132">Fare clic su Configurazioni report.</span><span class="sxs-lookup"><span data-stu-id="5fc5a-132">Click Reporting configurations.</span></span>
11. <span data-ttu-id="5fc5a-133">Nella struttura selezionare 'Modello fattura cliente'.</span><span class="sxs-lookup"><span data-stu-id="5fc5a-133">In the tree, select 'Customer invoice model'.</span></span>

## <a name="create-the-derived-model-to-support-access-to-the-document-management-files"></a><span data-ttu-id="5fc5a-134">Creare il modello derivato per supportare l'accesso ai file di gestione documenti.</span><span class="sxs-lookup"><span data-stu-id="5fc5a-134">Create the derived model to support access to the Document Management files.</span></span>
<span data-ttu-id="5fc5a-135">Si creerà una propria configurazione del modello fattura cliente derivandola dalla configurazione fornita da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="5fc5a-135">You will create our own configuration of the Customer invoice model deriving it from the configuration provided by Microsoft.</span></span> <span data-ttu-id="5fc5a-136">Si userà questa configurazione per implementare l'accesso ai file di gestione documenti e renderli disponibili per i documenti elettronici che verranno creati in base a tale modello.</span><span class="sxs-lookup"><span data-stu-id="5fc5a-136">You will use this configuration to implement access to the Document Management files and make them available for electronic documents that you will create based on this model.</span></span>  
1. <span data-ttu-id="5fc5a-137">Fare clic su Crea configurazione per aprire la finestra di dialogo a discesa .</span><span class="sxs-lookup"><span data-stu-id="5fc5a-137">Click Create configuration to open the drop dialog.</span></span>
2. <span data-ttu-id="5fc5a-138">Nel campo Nuovo, immettere 'Deriva da nome: Modello fattura cliente, Microsoft'.</span><span class="sxs-lookup"><span data-stu-id="5fc5a-138">In the New field, enter 'Derive from Name: Customer invoice model, Microsoft'.</span></span>
3. <span data-ttu-id="5fc5a-139">Nel campo Nome digitare 'Modello fattura cliente (personalizzato)'.</span><span class="sxs-lookup"><span data-stu-id="5fc5a-139">In the Name field, type 'Customer invoice model (custom)'.</span></span>
4. <span data-ttu-id="5fc5a-140">Fare clic su Crea configurazione.</span><span class="sxs-lookup"><span data-stu-id="5fc5a-140">Click Create configuration.</span></span>

