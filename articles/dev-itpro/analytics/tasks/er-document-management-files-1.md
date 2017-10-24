--- 
title: Preparare il modello dati per utilizzare i file di gestione documenti nel formato di output per la creazione di report elettronici (ER)
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
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: 5d224afd799306828a59e97f7f3bcd4cb831537c
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---
# <a name="prepare-data-model-to-use-document-management-files-in-format-outputs-for-electronic-reporting-er"></a><span data-ttu-id="66852-103">Preparare il modello dati per utilizzare i file di gestione documenti nel formato di output per la creazione di report elettronici (ER)</span><span class="sxs-lookup"><span data-stu-id="66852-103">Prepare data model to use Document Management files in format outputs for electronic reporting (ER)</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="66852-104">I passaggi seguenti descrivono come un utente con ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può configurare un formato per la creazione di report elettronici in modo che utilizzi i file (allegati) di gestione documenti nell'output della creazione di report elettronici.</span><span class="sxs-lookup"><span data-stu-id="66852-104">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) format to use Document Management files (attachments) in ER output.</span></span> <span data-ttu-id="66852-105">Questi passaggi possono essere eseguiti in qualsiasi società.</span><span class="sxs-lookup"><span data-stu-id="66852-105">These steps can be performed in any company.</span></span>

<span data-ttu-id="66852-106">Per completare questi passaggi, è necessario completare i passaggi della procedura "Creare un provider di configurazione e contrassegnarlo come attivo".</span><span class="sxs-lookup"><span data-stu-id="66852-106">To complete these steps, you must first complete the steps in the “Create a configuration provider and mark it as active” procedure.</span></span>

<span data-ttu-id="66852-107">Questa procedura è per una funzionalità che è stata aggiunta in Dynamics 365 for Operations versione 1611.</span><span class="sxs-lookup"><span data-stu-id="66852-107">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="get-access-to-the-list-of-configurations-provided-by-microsoft"></a><span data-ttu-id="66852-108">Ottenere l'accesso all'elenco delle configurazioni fornite da Microsoft</span><span class="sxs-lookup"><span data-stu-id="66852-108">Get access to the list of configurations provided by Microsoft</span></span>
1. <span data-ttu-id="66852-109">Andare ad Amministrazione organizzazione > Aree di lavoro > Creazione di report elettronici.</span><span class="sxs-lookup"><span data-stu-id="66852-109">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
    * <span data-ttu-id="66852-110">Assicurarsi che il provider Litware, Inc.</span><span class="sxs-lookup"><span data-stu-id="66852-110">Make sure that the 'Litware, Inc.'</span></span> <span data-ttu-id="66852-111">sia disponibile e contrassegnato come attivo.</span><span class="sxs-lookup"><span data-stu-id="66852-111">provider is available and marked as active.</span></span>  
2. <span data-ttu-id="66852-112">Selezionare il provider Litware, Inc</span><span class="sxs-lookup"><span data-stu-id="66852-112">Select the 'Litware, Inc.'</span></span> <span data-ttu-id="66852-113">.</span><span class="sxs-lookup"><span data-stu-id="66852-113">provider.</span></span>
3. <span data-ttu-id="66852-114">Fare clic su Archivi.</span><span class="sxs-lookup"><span data-stu-id="66852-114">Click Repositories.</span></span>
    * <span data-ttu-id="66852-115">Se un archivio di tipo 'Risorse operative' esiste già, ignorare i passaggi restanti della sottoattività corrente.</span><span class="sxs-lookup"><span data-stu-id="66852-115">If a repository of the 'Operations resources' type already exists, skip the remaining steps of the current sub-task.</span></span>  
4. <span data-ttu-id="66852-116">Fare clic su Aggiungi per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="66852-116">Click Add to open the drop dialog.</span></span>
5. <span data-ttu-id="66852-117">Nel campo Tipo di archivio di configurazioni immettere 'Risorse operative'.</span><span class="sxs-lookup"><span data-stu-id="66852-117">In the Configuration repository type field, enter 'Operations resources'.</span></span>
6. <span data-ttu-id="66852-118">Fare clic su Crea archivio.</span><span class="sxs-lookup"><span data-stu-id="66852-118">Click Create repository.</span></span>
7. <span data-ttu-id="66852-119">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="66852-119">Click OK.</span></span>

## <a name="get-the-customer-invoice-model-configurations-provided-by-microsoft"></a><span data-ttu-id="66852-120">Ottenere le configurazioni del modello fattura cliente fornite da Microsoft</span><span class="sxs-lookup"><span data-stu-id="66852-120">Get the Customer invoice model configurations provided by Microsoft</span></span>
1. <span data-ttu-id="66852-121">Fare clic su Mostra filtri.</span><span class="sxs-lookup"><span data-stu-id="66852-121">Click Show filters.</span></span>
2. <span data-ttu-id="66852-122">Applicare filtri i seguenti: Immettere un valore di filtro "Risorse operative" nel campo "Nome" utilizzando l'operatore di filtro "inizia con"; Immettere un valore di filtro di "" nel campo "Descrizione" utilizzando l'operatore di filtro "inizia con"</span><span class="sxs-lookup"><span data-stu-id="66852-122">Apply the following filters: Enter a filter value of "Operations resources" on the "Name" field using the "begins with" filter operator; Enter a filter value of "" on the "Description" field using the "begins with" filter operator</span></span>
3. <span data-ttu-id="66852-123">Fare clic su Mostra filtri.</span><span class="sxs-lookup"><span data-stu-id="66852-123">Click Show filters.</span></span>
4. <span data-ttu-id="66852-124">Fare clic su Apri.</span><span class="sxs-lookup"><span data-stu-id="66852-124">Click Open.</span></span>
5. <span data-ttu-id="66852-125">Nella struttura selezionare 'Modello fattura cliente'.</span><span class="sxs-lookup"><span data-stu-id="66852-125">In the tree, select 'Customer invoice model'.</span></span>
    * <span data-ttu-id="66852-126">Selezionare la configurazione modello 'Modello fattura cliente' per importarla.</span><span class="sxs-lookup"><span data-stu-id="66852-126">Select the model configuration 'Customer invoice model' to import it.</span></span>  
6. <span data-ttu-id="66852-127">Fare clic su Importa.</span><span class="sxs-lookup"><span data-stu-id="66852-127">Click Import.</span></span>
    * <span data-ttu-id="66852-128">Fare clic su Importa per la versione 1 della configurazione selezionata.</span><span class="sxs-lookup"><span data-stu-id="66852-128">Click Import for version 1 of the selected configuration.</span></span>  
7. <span data-ttu-id="66852-129">Fare clic su Sì.</span><span class="sxs-lookup"><span data-stu-id="66852-129">Click Yes.</span></span>
8. <span data-ttu-id="66852-130">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="66852-130">Close the page.</span></span>
9. <span data-ttu-id="66852-131">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="66852-131">Close the page.</span></span>
10. <span data-ttu-id="66852-132">Fare clic su Configurazioni report.</span><span class="sxs-lookup"><span data-stu-id="66852-132">Click Reporting configurations.</span></span>
11. <span data-ttu-id="66852-133">Nella struttura selezionare 'Modello fattura cliente'.</span><span class="sxs-lookup"><span data-stu-id="66852-133">In the tree, select 'Customer invoice model'.</span></span>

## <a name="create-the-derived-model-to-support-access-to-the-document-management-files"></a><span data-ttu-id="66852-134">Creare il modello derivato per supportare l'accesso ai file di gestione documenti.</span><span class="sxs-lookup"><span data-stu-id="66852-134">Create the derived model to support access to the Document Management files.</span></span>
    * <span data-ttu-id="66852-135">Si creerà una propria configurazione del modello fattura cliente derivandola dalla configurazione fornita da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="66852-135">You will create our own configuration of the Customer invoice model deriving it from the configuration provided by Microsoft.</span></span> <span data-ttu-id="66852-136">Si userà questa configurazione per implementare l'accesso ai file di gestione documenti e renderli disponibili per i documenti elettronici che verranno creati in base a tale modello.</span><span class="sxs-lookup"><span data-stu-id="66852-136">You will use this configuration to implement access to the Document Management files and make them available for electronic documents that you will create based on this model.</span></span>  
1. <span data-ttu-id="66852-137">Fare clic su Crea configurazione per aprire la finestra di dialogo a discesa .</span><span class="sxs-lookup"><span data-stu-id="66852-137">Click Create configuration to open the drop dialog.</span></span>
2. <span data-ttu-id="66852-138">Nel campo Nuovo, immettere 'Deriva da nome: Modello fattura cliente, Microsoft'.</span><span class="sxs-lookup"><span data-stu-id="66852-138">In the New field, enter 'Derive from Name: Customer invoice model, Microsoft'.</span></span>
3. <span data-ttu-id="66852-139">Nel campo Nome digitare 'Modello fattura cliente (personalizzato)'.</span><span class="sxs-lookup"><span data-stu-id="66852-139">In the Name field, type 'Customer invoice model (custom)'.</span></span>
    * <span data-ttu-id="66852-140">Modello fattura cliente (personalizzato)</span><span class="sxs-lookup"><span data-stu-id="66852-140">Customer invoice model (custom)</span></span>  
4. <span data-ttu-id="66852-141">Fare clic su Crea configurazione.</span><span class="sxs-lookup"><span data-stu-id="66852-141">Click Create configuration.</span></span>


