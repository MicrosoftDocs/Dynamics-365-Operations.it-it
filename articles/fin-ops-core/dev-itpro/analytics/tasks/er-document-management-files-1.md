---
title: 'ER Usare file di gestione documenti in output di formato (Parte 1: Preparare il modello dati)'
description: In questo argomento viene descritto come configurare un formato di reporting elettronico (ER) per utilizzare i file di gestione dei documenti (allegati) nell'output ER. (Parte 1)
author: NickSelin
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERVendorPart, ERSolutionRepositoryTable, ERSolutionRepositoryCreateDropDialog, ERSolutionImport,  ERSolutionTable, ERSolutionCreateDropDialog
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 6b265c9af0635e6c9fb6295f7e8e4e353b2a5ba5
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5754940"
---
# <a name="er-use-document-management-files-in-format-outputs-part-1---prepare-data-model"></a><span data-ttu-id="c66d2-104">ER Usare file di gestione documenti in output di formato (Parte 1: Preparare il modello dati)</span><span class="sxs-lookup"><span data-stu-id="c66d2-104">ER Use Document Management files in format outputs (Part 1 - Prepare data model)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="c66d2-105">I passaggi seguenti descrivono come un utente con ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può configurare un formato per la creazione di report elettronici in modo che utilizzi i file (allegati) di gestione documenti nell'output della creazione di report elettronici.</span><span class="sxs-lookup"><span data-stu-id="c66d2-105">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) format to use Document Management files (attachments) in ER output.</span></span> <span data-ttu-id="c66d2-106">Questi passaggi possono essere eseguiti in qualsiasi società.</span><span class="sxs-lookup"><span data-stu-id="c66d2-106">These steps can be performed in any company.</span></span>

<span data-ttu-id="c66d2-107">Per completare questi passaggi, è necessario completare i passaggi della procedura "Creare un provider di configurazione e contrassegnarlo come attivo".</span><span class="sxs-lookup"><span data-stu-id="c66d2-107">To complete these steps, you must first complete the steps in the "Create a configuration provider and mark it as active" procedure.</span></span>

<span data-ttu-id="c66d2-108">Questa procedura è per una funzionalità che è stata aggiunta in Dynamics 365 for Operations versione 1611.</span><span class="sxs-lookup"><span data-stu-id="c66d2-108">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="get-access-to-the-list-of-configurations-provided-by-microsoft"></a><span data-ttu-id="c66d2-109">Ottenere l'accesso all'elenco delle configurazioni fornite da Microsoft</span><span class="sxs-lookup"><span data-stu-id="c66d2-109">Get access to the list of configurations provided by Microsoft</span></span>
1. <span data-ttu-id="c66d2-110">Andare ad Amministrazione organizzazione > Aree di lavoro > Creazione di report elettronici.</span><span class="sxs-lookup"><span data-stu-id="c66d2-110">Go to Organization administration > Workspaces > Electronic reporting.</span></span>

    <span data-ttu-id="c66d2-111">Assicurarsi che il provider Litware, Inc.</span><span class="sxs-lookup"><span data-stu-id="c66d2-111">Make sure that the 'Litware, Inc.'</span></span> <span data-ttu-id="c66d2-112">sia disponibile e contrassegnato come attivo.</span><span class="sxs-lookup"><span data-stu-id="c66d2-112">provider is available and marked as active.</span></span>  

2. <span data-ttu-id="c66d2-113">Selezionare il provider Litware, Inc</span><span class="sxs-lookup"><span data-stu-id="c66d2-113">Select the 'Litware, Inc.'</span></span> <span data-ttu-id="c66d2-114">.</span><span class="sxs-lookup"><span data-stu-id="c66d2-114">provider.</span></span>
3. <span data-ttu-id="c66d2-115">Fare clic su Archivi.</span><span class="sxs-lookup"><span data-stu-id="c66d2-115">Click Repositories.</span></span>

    <span data-ttu-id="c66d2-116">Se un archivio di tipo 'Risorse operative' esiste già, ignorare i passaggi restanti della sottoattività corrente.</span><span class="sxs-lookup"><span data-stu-id="c66d2-116">If a repository of the 'Operations resources' type already exists, skip the remaining steps of the current sub-task.</span></span>  

4. <span data-ttu-id="c66d2-117">Fare clic su Aggiungi per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="c66d2-117">Click Add to open the drop dialog.</span></span>
5. <span data-ttu-id="c66d2-118">Nel campo Tipo di archivio di configurazioni immettere 'Risorse operative'.</span><span class="sxs-lookup"><span data-stu-id="c66d2-118">In the Configuration repository type field, enter 'Operations resources'.</span></span>
6. <span data-ttu-id="c66d2-119">Fare clic su Crea archivio.</span><span class="sxs-lookup"><span data-stu-id="c66d2-119">Click Create repository.</span></span>
7. <span data-ttu-id="c66d2-120">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="c66d2-120">Click OK.</span></span>

## <a name="get-the-customer-invoice-model-configurations-provided-by-microsoft"></a><span data-ttu-id="c66d2-121">Ottenere le configurazioni del modello fattura cliente fornite da Microsoft</span><span class="sxs-lookup"><span data-stu-id="c66d2-121">Get the Customer invoice model configurations provided by Microsoft</span></span>
1. <span data-ttu-id="c66d2-122">Fare clic su Mostra filtri.</span><span class="sxs-lookup"><span data-stu-id="c66d2-122">Click Show filters.</span></span>
2. <span data-ttu-id="c66d2-123">Applicare filtri i seguenti: Immettere un valore di filtro "Risorse operative" nel campo "Nome" utilizzando l'operatore di filtro "inizia con"; Immettere un valore di filtro di "" nel campo "Descrizione" utilizzando l'operatore di filtro "inizia con"</span><span class="sxs-lookup"><span data-stu-id="c66d2-123">Apply the following filters: Enter a filter value of "Operations resources" on the "Name" field using the "begins with" filter operator; Enter a filter value of "" on the "Description" field using the "begins with" filter operator</span></span>
3. <span data-ttu-id="c66d2-124">Fare clic su Mostra filtri.</span><span class="sxs-lookup"><span data-stu-id="c66d2-124">Click Show filters.</span></span>
4. <span data-ttu-id="c66d2-125">Fare clic su Apri.</span><span class="sxs-lookup"><span data-stu-id="c66d2-125">Click Open.</span></span>
5. <span data-ttu-id="c66d2-126">Nella struttura selezionare 'Modello fattura cliente'.</span><span class="sxs-lookup"><span data-stu-id="c66d2-126">In the tree, select 'Customer invoice model'.</span></span>

    <span data-ttu-id="c66d2-127">Selezionare la configurazione modello 'Modello fattura cliente' per importarla.</span><span class="sxs-lookup"><span data-stu-id="c66d2-127">Select the model configuration 'Customer invoice model' to import it.</span></span>  

6. <span data-ttu-id="c66d2-128">Fare clic su Importa.</span><span class="sxs-lookup"><span data-stu-id="c66d2-128">Click Import.</span></span>

    <span data-ttu-id="c66d2-129">Fare clic su Importa per la versione 1 della configurazione selezionata.</span><span class="sxs-lookup"><span data-stu-id="c66d2-129">Click Import for version 1 of the selected configuration.</span></span>  

7. <span data-ttu-id="c66d2-130">Fare clic su Sì.</span><span class="sxs-lookup"><span data-stu-id="c66d2-130">Click Yes.</span></span>
8. <span data-ttu-id="c66d2-131">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="c66d2-131">Close the page.</span></span>
9. <span data-ttu-id="c66d2-132">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="c66d2-132">Close the page.</span></span>
10. <span data-ttu-id="c66d2-133">Fare clic su Configurazioni report.</span><span class="sxs-lookup"><span data-stu-id="c66d2-133">Click Reporting configurations.</span></span>
11. <span data-ttu-id="c66d2-134">Nella struttura selezionare 'Modello fattura cliente'.</span><span class="sxs-lookup"><span data-stu-id="c66d2-134">In the tree, select 'Customer invoice model'.</span></span>

## <a name="create-the-derived-model-to-support-access-to-the-document-management-files"></a><span data-ttu-id="c66d2-135">Creare il modello derivato per supportare l'accesso ai file di gestione documenti.</span><span class="sxs-lookup"><span data-stu-id="c66d2-135">Create the derived model to support access to the Document Management files.</span></span>
<span data-ttu-id="c66d2-136">Si creerà una propria configurazione del modello fattura cliente derivandola dalla configurazione fornita da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c66d2-136">You will create our own configuration of the Customer invoice model deriving it from the configuration provided by Microsoft.</span></span> <span data-ttu-id="c66d2-137">Si userà questa configurazione per implementare l'accesso ai file di gestione documenti e renderli disponibili per i documenti elettronici che verranno creati in base a tale modello.</span><span class="sxs-lookup"><span data-stu-id="c66d2-137">You will use this configuration to implement access to the Document Management files and make them available for electronic documents that you will create based on this model.</span></span>  
1. <span data-ttu-id="c66d2-138">Fare clic su Crea configurazione per aprire la finestra di dialogo a discesa .</span><span class="sxs-lookup"><span data-stu-id="c66d2-138">Click Create configuration to open the drop dialog.</span></span>
2. <span data-ttu-id="c66d2-139">Nel campo Nuovo, immettere 'Deriva da nome: Modello fattura cliente, Microsoft'.</span><span class="sxs-lookup"><span data-stu-id="c66d2-139">In the New field, enter 'Derive from Name: Customer invoice model, Microsoft'.</span></span>
3. <span data-ttu-id="c66d2-140">Nel campo Nome digitare 'Modello fattura cliente (personalizzato)'.</span><span class="sxs-lookup"><span data-stu-id="c66d2-140">In the Name field, type 'Customer invoice model (custom)'.</span></span>
4. <span data-ttu-id="c66d2-141">Fare clic su Crea configurazione.</span><span class="sxs-lookup"><span data-stu-id="c66d2-141">Click Create configuration.</span></span>



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]