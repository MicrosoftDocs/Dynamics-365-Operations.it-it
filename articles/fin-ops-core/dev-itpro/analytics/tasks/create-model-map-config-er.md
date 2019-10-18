---
title: Creare configurazioni di mapping modello per la creazione di report elettronici
description: Utilizzare questa procedura per progettare una nuova configurazione di mapping di modello (ER) per la creazione di report elettronici e usare le funzioni ER incorporate per i calcoli aggregati efficienti.
author: NickSelin
manager: AnnBe
ms.date: 12/12/2017
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
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: bcfc258e7fe364779fd77cc79413e8d5e871e214
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/27/2019
ms.locfileid: "2182694"
---
# <a name="create-electronic-reporting-er-model-mapping-configurations"></a><span data-ttu-id="25a8a-103">Creare configurazioni di mapping modello per la creazione di report elettronici</span><span class="sxs-lookup"><span data-stu-id="25a8a-103">Create Electronic reporting (ER) model mapping configurations</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="25a8a-104">Utilizzare questa procedura per progettare una nuova configurazione di mapping di modello (ER) per la creazione di report elettronici e usare le funzioni ER incorporate per i calcoli aggregati efficienti.</span><span class="sxs-lookup"><span data-stu-id="25a8a-104">Use this procedure to design a new Electronic reporting (ER) model mapping configuration and use built-in ER functions for efficient aggregate calculations.</span></span> <span data-ttu-id="25a8a-105">In questa procedura verrà creata una configurazione per la società di esempio Litware, Inc.</span><span class="sxs-lookup"><span data-stu-id="25a8a-105">In this procedure, you will create a configuration for sample company, Litware, Inc.</span></span> 

<span data-ttu-id="25a8a-106">Questa procedura viene creata per utenti con il ruolo di amministratore di sistema o di sviluppatore di report elettronici.</span><span class="sxs-lookup"><span data-stu-id="25a8a-106">This procedure is created for uses with the assigned role of System administrator or Electronic reporting developer.</span></span>

<span data-ttu-id="25a8a-107">Tali passaggi possono essere completati mediante un set di dati.</span><span class="sxs-lookup"><span data-stu-id="25a8a-107">These steps can be completed using any dataset.</span></span> <span data-ttu-id="25a8a-108">Per completare questi passaggi, è necessario completare i passaggi della procedura "Creare un provider di configurazione e contrassegnarlo come attivo".</span><span class="sxs-lookup"><span data-stu-id="25a8a-108">To complete these steps, you must first complete the steps in the procedure, “Create a configuration provider and mark it as active.”</span></span>

1. <span data-ttu-id="25a8a-109">Andare ad Amministrazione organizzazione > Aree di lavoro > Creazione di report elettronici.</span><span class="sxs-lookup"><span data-stu-id="25a8a-109">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
    * <span data-ttu-id="25a8a-110">Verificare che il provider di configurazione per la società di esempio Litware, Inc. sia disponibile e contrassegnato come attivo.</span><span class="sxs-lookup"><span data-stu-id="25a8a-110">Make sure that the configuration provider for the sample company, Litware, Inc., is available and marked as Active.</span></span> <span data-ttu-id="25a8a-111">Se il provider di configurazione non è visualizzato, è necessario innanzitutto completare i passaggi della procedura "Creazione di report elettronici: creare e attivare un provider di configurazione".</span><span class="sxs-lookup"><span data-stu-id="25a8a-111">If you don’t see this configuration provider, complete the steps in the procedure, “Create a configuration provider and mark it as active”.</span></span>  
2. <span data-ttu-id="25a8a-112">Fare clic su Configurazioni report.</span><span class="sxs-lookup"><span data-stu-id="25a8a-112">Click Reporting configurations.</span></span>
3. <span data-ttu-id="25a8a-113">Fare clic su Mostra filtri.</span><span class="sxs-lookup"><span data-stu-id="25a8a-113">Click Show filters.</span></span>
4. <span data-ttu-id="25a8a-114">Immettere il valore di filtro "Intrastat" nel campo "Nome" e utilizzare l'operatore di filtro "inizia con".</span><span class="sxs-lookup"><span data-stu-id="25a8a-114">In the "Name" field, enter the filter value, "Intrastat" and use the filter operator "begins with".</span></span>
    * <span data-ttu-id="25a8a-115">Applicare questo filtro per individuare la configurazione del modello dati "Intrastat".</span><span class="sxs-lookup"><span data-stu-id="25a8a-115">Apply this filter to find the ‘Intrastat’ data model configuration.</span></span> <span data-ttu-id="25a8a-116">Questo modello potrebbe essere già presente nella struttura di configurazioni.</span><span class="sxs-lookup"><span data-stu-id="25a8a-116">This model may already exist in the configurations tree.</span></span> <span data-ttu-id="25a8a-117">In tal caso, ignorare la sottoattività successiva.</span><span class="sxs-lookup"><span data-stu-id="25a8a-117">If it does, skip the next sub-task.</span></span>   

## <a name="get-the-intrastat-model-configuration-provided-by-microsoft"></a><span data-ttu-id="25a8a-118">Ottenere la configurazione di modello Intrastat fornita da Microsoft</span><span class="sxs-lookup"><span data-stu-id="25a8a-118">Get the Intrastat model configuration provided by Microsoft</span></span>
1. <span data-ttu-id="25a8a-119">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="25a8a-119">Close the page.</span></span>
2. <span data-ttu-id="25a8a-120">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="25a8a-120">Close the page.</span></span>
3. <span data-ttu-id="25a8a-121">Andare ad Amministrazione organizzazione > Aree di lavoro > Creazione di report elettronici.</span><span class="sxs-lookup"><span data-stu-id="25a8a-121">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
4. <span data-ttu-id="25a8a-122">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="25a8a-122">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="25a8a-123">Selezionare il riquadro Provider Microsoft.</span><span class="sxs-lookup"><span data-stu-id="25a8a-123">Select the Microsoft provider tile.</span></span>  
5. <span data-ttu-id="25a8a-124">Fare clic su Archivi.</span><span class="sxs-lookup"><span data-stu-id="25a8a-124">Click Repositories.</span></span>
    * <span data-ttu-id="25a8a-125">Fare clic su Archivi nel riquadro Provider Microsoft.</span><span class="sxs-lookup"><span data-stu-id="25a8a-125">Click Repositories in the Microsoft provider tile.</span></span>  
6. <span data-ttu-id="25a8a-126">Fare clic su Mostra filtri.</span><span class="sxs-lookup"><span data-stu-id="25a8a-126">Click Show filters.</span></span>
7. <span data-ttu-id="25a8a-127">Immettere il valore di filtro "risorse" nel campo "Nome del tipo" e utilizzare l'operatore di filtro "contiene".</span><span class="sxs-lookup"><span data-stu-id="25a8a-127">In the "Type name" field, enter the filter value, “resources” and use the filter operator "contains".</span></span> 
8. <span data-ttu-id="25a8a-128">Fare clic su Apri.</span><span class="sxs-lookup"><span data-stu-id="25a8a-128">Click Open.</span></span>
9. <span data-ttu-id="25a8a-129">Nella struttura selezionare "Modello Intrastat".</span><span class="sxs-lookup"><span data-stu-id="25a8a-129">In the tree, select 'Intrastat model'.</span></span>
10. <span data-ttu-id="25a8a-130">Fare clic su Importa.</span><span class="sxs-lookup"><span data-stu-id="25a8a-130">Click Import.</span></span>
11. <span data-ttu-id="25a8a-131">Fare clic su Sì.</span><span class="sxs-lookup"><span data-stu-id="25a8a-131">Click Yes.</span></span>
    * <span data-ttu-id="25a8a-132">È stata importata la configurazione del modello ER contenente il modello dati che verrà utilizzato per esplorare come le nuove funzionalità ER possono essere utilizzate.</span><span class="sxs-lookup"><span data-stu-id="25a8a-132">You imported the ER model configuration that contains the data model that you will use to explore how the new ER functionality can be used.</span></span>  
12. <span data-ttu-id="25a8a-133">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="25a8a-133">Close the page.</span></span>
13. <span data-ttu-id="25a8a-134">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="25a8a-134">Close the page.</span></span>
14. <span data-ttu-id="25a8a-135">Fare clic su Configurazioni report.</span><span class="sxs-lookup"><span data-stu-id="25a8a-135">Click Reporting configurations.</span></span>

## <a name="add-a-new-model-mapping-configuration"></a><span data-ttu-id="25a8a-136">Aggiungere una nuova configurazione del mapping di modello</span><span class="sxs-lookup"><span data-stu-id="25a8a-136">Add a new model mapping configuration</span></span>
1. <span data-ttu-id="25a8a-137">Nella struttura selezionare "Modello Intrastat".</span><span class="sxs-lookup"><span data-stu-id="25a8a-137">In the tree, select 'Intrastat model'.</span></span>
2. <span data-ttu-id="25a8a-138">Fare clic su Crea configurazione per aprire la finestra di dialogo a discesa .</span><span class="sxs-lookup"><span data-stu-id="25a8a-138">Click Create configuration to open the drop dialog.</span></span>
3. <span data-ttu-id="25a8a-139">Nel campo Nuovo immettere 'Mapping di modello basato sul modello dati Intrastat'.</span><span class="sxs-lookup"><span data-stu-id="25a8a-139">In the New field, enter 'Model Mapping based on data model Intrastat'.</span></span>
4. <span data-ttu-id="25a8a-140">Nel campo Nome digitare "Mapping di esempio Intrastat".</span><span class="sxs-lookup"><span data-stu-id="25a8a-140">In the Name field, type 'Intrastat sample mapping'.</span></span>
    * <span data-ttu-id="25a8a-141">Mapping di esempio Intrastat</span><span class="sxs-lookup"><span data-stu-id="25a8a-141">Intrastat sample mapping</span></span>  
5. <span data-ttu-id="25a8a-142">Fare clic su Crea configurazione.</span><span class="sxs-lookup"><span data-stu-id="25a8a-142">Click Create configuration.</span></span>

