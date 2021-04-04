---
title: 'ER Configurare il formato per eseguire il conteggio e la sommatoria (Parte 1: creare il formato)'
description: Questo argomento descrive come configurare un formato di report elettronico per eseguire il conteggio e la somma in base ai dati dell'output di testo già generato. (Parte 1)
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERVendorPart, ERSolutionRepositoryTable, ERSolutionRepositoryCreateDropDialog, ERSolutionImport,  ERSolutionTable
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 64bf9f48319029e835f9e3fe2b888625100cc408
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2021
ms.locfileid: "5565144"
---
# <a name="er-configure-format-to-do-counting-and-summing-part-1---create-format"></a><span data-ttu-id="2e23d-104">ER Configurare il formato per eseguire il conteggio e la sommatoria (Parte 1: creare il formato)</span><span class="sxs-lookup"><span data-stu-id="2e23d-104">ER Configure format to do counting and summing (Part 1 - Create format)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="2e23d-105">I passaggi seguenti descrivono come un utente con ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può configurare un formato per la creazione di report elettronici in modo che esegua calcoli e somme in base ai dati dell'output di testo già generato.</span><span class="sxs-lookup"><span data-stu-id="2e23d-105">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) format to do counting and summing based on data of the already generated text output.</span></span> <span data-ttu-id="2e23d-106">Questi passaggi possono essere eseguiti in qualsiasi società.</span><span class="sxs-lookup"><span data-stu-id="2e23d-106">These steps can be performed in any company.</span></span>

<span data-ttu-id="2e23d-107">Per completare questi passaggi, è necessario completare i passaggi della procedura "Creare un provider di configurazione e contrassegnarlo come attivo".</span><span class="sxs-lookup"><span data-stu-id="2e23d-107">To complete these steps, you must first complete the steps in the "Create a configuration provider and mark it as active" procedure.</span></span>

<span data-ttu-id="2e23d-108">Questa procedura è per una funzionalità che è stata aggiunta in Dynamics 365 for Operations versione 1611.</span><span class="sxs-lookup"><span data-stu-id="2e23d-108">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="get-access-to-the-list-of-configurations-provided-by-microsoft"></a><span data-ttu-id="2e23d-109">Ottenere l'accesso all'elenco delle configurazioni fornite da Microsoft</span><span class="sxs-lookup"><span data-stu-id="2e23d-109">Get access to the list of configurations provided by Microsoft</span></span>
1. <span data-ttu-id="2e23d-110">Andare ad Amministrazione organizzazione > Aree di lavoro > Creazione di report elettronici.</span><span class="sxs-lookup"><span data-stu-id="2e23d-110">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
    * <span data-ttu-id="2e23d-111">Assicurarsi che il provider "Litware, Inc."</span><span class="sxs-lookup"><span data-stu-id="2e23d-111">Make sure that the "Litware, Inc."</span></span> <span data-ttu-id="2e23d-112">sia disponibile e contrassegnato come attivo.</span><span class="sxs-lookup"><span data-stu-id="2e23d-112">provider is available and marked as active.</span></span>  
2. <span data-ttu-id="2e23d-113">Selezionare il provider "Litware, Inc."</span><span class="sxs-lookup"><span data-stu-id="2e23d-113">Select the "Litware, Inc."</span></span> <span data-ttu-id="2e23d-114">.</span><span class="sxs-lookup"><span data-stu-id="2e23d-114">provider.</span></span>
3. <span data-ttu-id="2e23d-115">Fare clic su Archivi.</span><span class="sxs-lookup"><span data-stu-id="2e23d-115">Click Repositories.</span></span>
    * <span data-ttu-id="2e23d-116">Se un archivio di tipo 'Risorse operative' esiste già, ignorare i passaggi restanti della sottoattività corrente.</span><span class="sxs-lookup"><span data-stu-id="2e23d-116">If a repository of the "Operations resources" type already exists, skip the remaining steps of the current sub-task.</span></span>  
4. <span data-ttu-id="2e23d-117">Fare clic su Aggiungi per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="2e23d-117">Click Add to open the drop dialog.</span></span>
5. <span data-ttu-id="2e23d-118">Nel campo Tipo di archivio di configurazioni immettere 'Risorse operative'.</span><span class="sxs-lookup"><span data-stu-id="2e23d-118">In the Configuration repository type field, enter 'Operations resources'.</span></span>
6. <span data-ttu-id="2e23d-119">Fare clic su Crea archivio.</span><span class="sxs-lookup"><span data-stu-id="2e23d-119">Click Create repository.</span></span>
7. <span data-ttu-id="2e23d-120">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="2e23d-120">Click OK.</span></span>

## <a name="get-the-intrastat-configurations-provided-by-microsoft"></a><span data-ttu-id="2e23d-121">Ottenere le configurazioni Intrastat fornite da Microsoft</span><span class="sxs-lookup"><span data-stu-id="2e23d-121">Get the Intrastat configurations provided by Microsoft</span></span>
1. <span data-ttu-id="2e23d-122">Fare clic su Apri.</span><span class="sxs-lookup"><span data-stu-id="2e23d-122">Click Open.</span></span>
2. <span data-ttu-id="2e23d-123">Nella struttura, selezionare 'Modello Intrastat\Intrastat (DE)'.</span><span class="sxs-lookup"><span data-stu-id="2e23d-123">In the tree, select 'Intrastat model\Intrastat (DE)'.</span></span>
3. <span data-ttu-id="2e23d-124">Fare clic su Importa.</span><span class="sxs-lookup"><span data-stu-id="2e23d-124">Click Import.</span></span>
    * <span data-ttu-id="2e23d-125">Fare clic su Importa per la versione 1.1 della configurazione selezionata.</span><span class="sxs-lookup"><span data-stu-id="2e23d-125">Click Import for version 1.1 of the selected configuration.</span></span>  
4. <span data-ttu-id="2e23d-126">Fare clic su Sì.</span><span class="sxs-lookup"><span data-stu-id="2e23d-126">Click Yes.</span></span>
5. <span data-ttu-id="2e23d-127">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="2e23d-127">Close the page.</span></span>
6. <span data-ttu-id="2e23d-128">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="2e23d-128">Close the page.</span></span>
7. <span data-ttu-id="2e23d-129">Fare clic su Configurazioni report.</span><span class="sxs-lookup"><span data-stu-id="2e23d-129">Click Reporting configurations.</span></span>
8. <span data-ttu-id="2e23d-130">Nella struttura espandere 'Modello Intrastat'.</span><span class="sxs-lookup"><span data-stu-id="2e23d-130">In the tree, expand 'Intrastat model'.</span></span>
9. <span data-ttu-id="2e23d-131">Nella struttura, selezionare 'Modello Intrastat\Intrastat (DE)'.</span><span class="sxs-lookup"><span data-stu-id="2e23d-131">In the tree, select 'Intrastat model\Intrastat (DE)'.</span></span>



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]