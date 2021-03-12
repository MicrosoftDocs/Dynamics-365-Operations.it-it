---
title: Esportare i dati delle filiali in file
description: Questo argomento spiega come prepararsi all'esportazione di dati da Microsoft Dynamics 365 Finance e quindi importarli in una persona giuridica consolidata.
author: jinniew
manager: AnnBe
ms.date: 10/09/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: jiwo
ms.search.validFrom: 2018-5-31
ms.dyn365.ops.version: 8.0.1
ms.openlocfilehash: 179a401178935b8a76d6718a7fb1f63e08344f50
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4968681"
---
# <a name="export-subsidiary-data-to-files"></a><span data-ttu-id="d3a13-103">Esportare i dati delle filiali in file</span><span class="sxs-lookup"><span data-stu-id="d3a13-103">Export subsidiary data to files</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d3a13-104">Usi la pagina **Esporta** (**Amministrazione di sistema \> Aree di lavoro \> Importa/Esporta**) per prepararsi a esportare i dati delle filiali in file che possono poi essere importati in una persona giuridica consolidata.</span><span class="sxs-lookup"><span data-stu-id="d3a13-104">You use the **Export** page (**System administration \> Workspaces \> Import/Export**) to prepare to export subsidiary data to files that can then be imported into a consolidated legal entity.</span></span> <span data-ttu-id="d3a13-105">Per ulteriori informazioni sui processi di importazione ed esportazione vedi [Panoramica dei processi di importazione ed esportazione dei dati](../../fin-ops-core/dev-itpro/data-entities/data-import-export-job.md).</span><span class="sxs-lookup"><span data-stu-id="d3a13-105">For more information about the import and export processes, see [Data import and export jobs overview](../../fin-ops-core/dev-itpro/data-entities/data-import-export-job.md).</span></span>

1. <span data-ttu-id="d3a13-106">Crea una persona giuridica per il processo di consolidamento.</span><span class="sxs-lookup"><span data-stu-id="d3a13-106">Create a legal entity for the consolidation process.</span></span> <span data-ttu-id="d3a13-107">Per ulteriori informazioni su come creare persone giuridiche, vedi [Creare una persona giuridica](../../fin-ops-core/fin-ops/organization-administration/tasks/create-legal-entity.md).</span><span class="sxs-lookup"><span data-stu-id="d3a13-107">For information about how to create legal entities, see [Create a legal entity](../../fin-ops-core/fin-ops/organization-administration/tasks/create-legal-entity.md).</span></span> <span data-ttu-id="d3a13-108">Per ulteriori informazioni, vedi [Preparare una persona giuridica da utilizzare nel processo di consolidamento](prepare-company-for-consolidation.md) e [Impostare una persona giuridica affiliata per il consolidamento](set-up-subsidiary-company-for-consolidation.md).</span><span class="sxs-lookup"><span data-stu-id="d3a13-108">For more information, see [Prepare a legal entity for use in the consolidation process](prepare-company-for-consolidation.md) and [Set up a subsidiary legal entity for consolidation](set-up-subsidiary-company-for-consolidation.md).</span></span> 

2. <span data-ttu-id="d3a13-109">Vai a **Consolidamenti \> Esporta saldi aziendali**.</span><span class="sxs-lookup"><span data-stu-id="d3a13-109">Go to **Consolidations \> Export company balances**.</span></span> <span data-ttu-id="d3a13-110">Nella pagina **Esporta saldi aziendali** nella scheda **Criteri** specifica i dettagli del consolidamento impostando i seguenti campi.</span><span class="sxs-lookup"><span data-stu-id="d3a13-110">On the **Export company balances** page, on the **Criteria** tab, specify the details of the consolidation by setting the following fields.</span></span>

    | <span data-ttu-id="d3a13-111">Campo</span><span class="sxs-lookup"><span data-stu-id="d3a13-111">Field</span></span>                             | <span data-ttu-id="d3a13-112">descrizione</span><span class="sxs-lookup"><span data-stu-id="d3a13-112">Description</span></span> |
    |-----------------------------------|-------|
    | <span data-ttu-id="d3a13-113">Conto principale</span><span class="sxs-lookup"><span data-stu-id="d3a13-113">Main account</span></span>                      | <span data-ttu-id="d3a13-114">Specifica i conti da consolidare.</span><span class="sxs-lookup"><span data-stu-id="d3a13-114">Specify the accounts to consolidate.</span></span> <span data-ttu-id="d3a13-115">Per includere tutti i conti lascia vuoto questo campo.</span><span class="sxs-lookup"><span data-stu-id="d3a13-115">To include all accounts, leave this field blank.</span></span> |
    | <span data-ttu-id="d3a13-116">Utilizza conto di consolidamento</span><span class="sxs-lookup"><span data-stu-id="d3a13-116">Use consolidation account</span></span>         | <span data-ttu-id="d3a13-117">Se hai specificato conti di consolidamento, imposta questa opzione su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="d3a13-117">If you've specified consolidation accounts, set this option to **Yes**.</span></span> |
    | <span data-ttu-id="d3a13-118">Selezionare il conto di consolidamento di origine</span><span class="sxs-lookup"><span data-stu-id="d3a13-118">Select consolidation account from</span></span> | <span data-ttu-id="d3a13-119">Seleziona **Conto principale** o **Gruppo di conti di consolidamento**.</span><span class="sxs-lookup"><span data-stu-id="d3a13-119">Select either **Main account** or **Consolidation account group**.</span></span> |
    | <span data-ttu-id="d3a13-120">Gruppo di conti di consolidamento</span><span class="sxs-lookup"><span data-stu-id="d3a13-120">Consolidation account group</span></span>       | <span data-ttu-id="d3a13-121">Selezionare un gruppo di conti di consolidamento per il conto di consolidamento selezionato.</span><span class="sxs-lookup"><span data-stu-id="d3a13-121">Select a consolidation account group for the consolidation account that you selected.</span></span> |
    | <span data-ttu-id="d3a13-122">Periodo di consolidamento</span><span class="sxs-lookup"><span data-stu-id="d3a13-122">Consolidation period</span></span>              | <span data-ttu-id="d3a13-123">Specifica le date "da" e "a" per il consolidamento.</span><span class="sxs-lookup"><span data-stu-id="d3a13-123">Specify "from" and "to" dates for the consolidation.</span></span> |
    | <span data-ttu-id="d3a13-124">Includi importi effettivi</span><span class="sxs-lookup"><span data-stu-id="d3a13-124">Include actual amounts</span></span>            | <span data-ttu-id="d3a13-125">Imposta questa opzione su **Sì** per includere gli importi effettivi.</span><span class="sxs-lookup"><span data-stu-id="d3a13-125">Set this option to **Yes** to include actual amounts.</span></span> |
    | <span data-ttu-id="d3a13-126">Includi importi di budget</span><span class="sxs-lookup"><span data-stu-id="d3a13-126">Include budget amounts</span></span>            | <span data-ttu-id="d3a13-127">Imposta questa opzione su **Sì** per includere gli importi di budget in consolidamento.</span><span class="sxs-lookup"><span data-stu-id="d3a13-127">Set this option to **Yes** to include budget amounts in consolidations.</span></span> |
    | <span data-ttu-id="d3a13-128">Modelli di budget</span><span class="sxs-lookup"><span data-stu-id="d3a13-128">Budget models</span></span>                     | <span data-ttu-id="d3a13-129">Specifica il modello di budget da includere.</span><span class="sxs-lookup"><span data-stu-id="d3a13-129">Specify the budget model to include.</span></span> |

3. <span data-ttu-id="d3a13-130">Nella scheda **Dimensioni finanziarie** specifica i dettagli del consolidamento:</span><span class="sxs-lookup"><span data-stu-id="d3a13-130">On the **Financial dimensions** tab, specify the details of the consolidation:</span></span>

    - <span data-ttu-id="d3a13-131">Specifica le informazioni sulle dimensioni finanziarie che devono essere trasferite dalle transazioni nei conti delle società affiliate alle transazioni della persona giuridica consolidata.</span><span class="sxs-lookup"><span data-stu-id="d3a13-131">Specify the financial dimension information that should be transferred from the transactions in the subsidiary accounts to the transactions in the consolidated legal entity.</span></span>
    - <span data-ttu-id="d3a13-132">Seleziona le dimensioni finanziarie nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="d3a13-132">Select financial dimensions in the list.</span></span>
    - <span data-ttu-id="d3a13-133">Identifica la specifica corretta per ciascuna dimensione finanziaria consolidata.</span><span class="sxs-lookup"><span data-stu-id="d3a13-133">Identify the correct specification for each financial dimension that is consolidated.</span></span> <span data-ttu-id="d3a13-134">Le opzioni disponibili includono **Dimensione**, **Dimensione gruppo**, **Conti aziendali** e **Conto**.</span><span class="sxs-lookup"><span data-stu-id="d3a13-134">The available options include **Dimension**, **Group dimension**, **Company accounts**, and **Account**.</span></span>

        > [!NOTE]
        > <span data-ttu-id="d3a13-135">L'opzione **Dimensione gruppo** consente di definire il valore della dimensione utilizzato dal gruppo di società che si sta consolidando.</span><span class="sxs-lookup"><span data-stu-id="d3a13-135">The **Group dimension** option lets you define the dimension value that is used by the group of companies that is being consolidated.</span></span>

    - <span data-ttu-id="d3a13-136">Specifica l'ordine dei segmenti da consolidare.</span><span class="sxs-lookup"><span data-stu-id="d3a13-136">Specify the segment order to consolidate in.</span></span>

4. <span data-ttu-id="d3a13-137">Nella scheda **Persone giuridiche** segui questi passaggi per specificare la persona giuridica che stai esportando:</span><span class="sxs-lookup"><span data-stu-id="d3a13-137">On the **Legal entities** tab, follow these steps to specify the legal entity that you're exporting:</span></span>

    1. <span data-ttu-id="d3a13-138">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="d3a13-138">Select **New**.</span></span>
    2. <span data-ttu-id="d3a13-139">Nel campo **Persona giuridica di origine** immetti la persona giuridica.</span><span class="sxs-lookup"><span data-stu-id="d3a13-139">In the **Source legal entity** field, enter the legal entity.</span></span>

        <span data-ttu-id="d3a13-140">Se gli stessi criteri sono applicabili a più affiliate nello stesso database, sarà possibile trasferire i dati di queste ultime dallo stesso database a file di esportazione distinti in un'unica operazione:</span><span class="sxs-lookup"><span data-stu-id="d3a13-140">If the same criteria apply to several subsidiaries that are in the same database, you can transfer data from those subsidiaries to separate export files in a single operation:</span></span>

        1. <span data-ttu-id="d3a13-141">Crea una riga per ogni persona giuridica affiliata i cui conti devono essere esportati in file.</span><span class="sxs-lookup"><span data-stu-id="d3a13-141">Create a line for each subsidiary legal entity for which accounts should be exported to files.</span></span> <span data-ttu-id="d3a13-142">Questi ultimi verranno in seguito importati nella persona giuridica consolidata.</span><span class="sxs-lookup"><span data-stu-id="d3a13-142">These files will be imported into the consolidated legal entity later.</span></span>
        2. <span data-ttu-id="d3a13-143">Per ogni società affiliata, immettere il nome della società stessa e il nome del file di esportazione che verrà creato durante il processo di esportazione.</span><span class="sxs-lookup"><span data-stu-id="d3a13-143">For each subsidiary, enter the subsidiary name and the name of the export file that will be created during the export job.</span></span>

    3. <span data-ttu-id="d3a13-144">Nel campo **Tipo di conto di differenze di conversione** seleziona **Profitti e perdite** o **Stato patrimoniale**.</span><span class="sxs-lookup"><span data-stu-id="d3a13-144">In **Account type of conversion differences** field, Select **Profit and loss** or **Balance sheet**.</span></span>
    4. <span data-ttu-id="d3a13-145">Immetti un nome file per il file di esportazione che verrà creato.</span><span class="sxs-lookup"><span data-stu-id="d3a13-145">Enter a file name for the export file that will be created.</span></span>

5. <span data-ttu-id="d3a13-146">Seleziona **OK** per eseguire l'esportazione.</span><span class="sxs-lookup"><span data-stu-id="d3a13-146">Select **OK** to run the export.</span></span>

<span data-ttu-id="d3a13-147">Al termine dell'esportazione, verrà visualizzato un messaggio con il numero di record salvati in ogni file.</span><span class="sxs-lookup"><span data-stu-id="d3a13-147">When the export is completed, you receive a message that shows the number of records that were saved in each file.</span></span> <span data-ttu-id="d3a13-148">È quindi possibile importare i file nella persona giuridica consolidata.</span><span class="sxs-lookup"><span data-stu-id="d3a13-148">You can then import the files into the consolidated legal entity.</span></span>
