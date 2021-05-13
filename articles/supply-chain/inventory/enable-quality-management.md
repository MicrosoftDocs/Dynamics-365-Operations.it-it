---
title: Abilitare la gestione della qualità e della non conformità
description: Questo argomento fornisce una panoramica del processo per l'impostazione e la configurazione delle funzionalità di gestione della qualità e della non conformità in Microsoft Dynamics 365 Supply Chain Management.
author: perlynne
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventTestAssociationTable, InventTestGroup, InventTestItemQualityGroup, InventTestTable, InventTestVariable, InventTestVariableOutcome, InventParameters, InventProblemType, InventProblemTypeSetup, InventQuarantineZone, InventTestDiagnosticType, InventTestReportSetup, SysUserManagement, InventTestRelatedOperations
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 67d5da648e31d07d054246f5d308a6c6cdeb506c
ms.sourcegitcommit: 8362f3bd32ce8b9a5af93c8e57daef732a93b19e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2021
ms.locfileid: "5956256"
---
# <a name="enable-quality-and-nonconformance-management"></a><span data-ttu-id="b6183-103">Abilitare la gestione della qualità e della non conformità</span><span class="sxs-lookup"><span data-stu-id="b6183-103">Enable quality and nonconformance management</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b6183-104">Questo argomento fornisce una panoramica del processo per l'impostazione e la configurazione delle funzionalità di gestione della qualità e della non conformità in Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="b6183-104">This topic provides an overview of the process for setting up and configuring quality and nonconformance management features in Microsoft Dynamics 365 Supply Chain Management.</span></span>

## <a name="enable-quality-and-nonconformance-management"></a><a name="enable-qm"></a><span data-ttu-id="b6183-105">Abilitare la gestione della qualità e della non conformità</span><span class="sxs-lookup"><span data-stu-id="b6183-105">Enable quality and nonconformance management</span></span>

<span data-ttu-id="b6183-106">Segui questi passaggi per abilitare la gestione della qualità sul tuo sistema.</span><span class="sxs-lookup"><span data-stu-id="b6183-106">Follow these steps to enable quality management on your system.</span></span>

1. <span data-ttu-id="b6183-107">Fare clic su **Gestione magazzino \> Impostazione \> Parametri di gestione articoli e magazzino**.</span><span class="sxs-lookup"><span data-stu-id="b6183-107">Go to **Inventory management \> Setup \> Inventory and warehouse management parameters**.</span></span>
1. <span data-ttu-id="b6183-108">Nella scheda **Gestione qualità**, impostare l'opzione **Usa Gestione qualità** su *Sì*.</span><span class="sxs-lookup"><span data-stu-id="b6183-108">On the **Quality management** tab, set the **Use quality management** option to *Yes*.</span></span>
1. <span data-ttu-id="b6183-109">Nel campo **Tariffa oraria**, immettere una tariffa oraria per la manodopera nella valuta locale.</span><span class="sxs-lookup"><span data-stu-id="b6183-109">In the **Hourly rate** field, enter an hourly labor rate in the local currency.</span></span> <span data-ttu-id="b6183-110">La tariffa oraria viene utilizzata per calcolare i costi delle operazioni correlate a una non conformità.</span><span class="sxs-lookup"><span data-stu-id="b6183-110">The hourly rate is used to calculate costs for operations that are related to a nonconformance.</span></span> <span data-ttu-id="b6183-111">La tariffa oraria e i costi calcolati forniscono informazioni di riferimento per una non conformità.</span><span class="sxs-lookup"><span data-stu-id="b6183-111">The hourly rate and calculated costs provide reference information for a nonconformance.</span></span> <span data-ttu-id="b6183-112">Non interagiscono con altre funzionalità.</span><span class="sxs-lookup"><span data-stu-id="b6183-112">They don't interact with other functionality.</span></span>
1. <span data-ttu-id="b6183-113">Seleziona **Impostazione report**.</span><span class="sxs-lookup"><span data-stu-id="b6183-113">Select **Report setup**.</span></span>
1. <span data-ttu-id="b6183-114">Aggiungere nuove righe per i vari tipi di report e selezionare il tipo di documento da utilizzare per ogni report.</span><span class="sxs-lookup"><span data-stu-id="b6183-114">Add new lines for the various report types, and select the type of document to use for each report.</span></span>
1. <span data-ttu-id="b6183-115">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="b6183-115">Close the page.</span></span>
1. <span data-ttu-id="b6183-116">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="b6183-116">Close the page.</span></span>

## <a name="quality-management-configuration-process"></a><span data-ttu-id="b6183-117">Processo di configurazione della gestione qualità</span><span class="sxs-lookup"><span data-stu-id="b6183-117">Quality management configuration process</span></span>

<span data-ttu-id="b6183-118">Prima di poter iniziare a utilizzare le funzionalità di gestione della qualità e generare ordini di controllo qualità, è necessario configurare il sistema e i prerequisiti.</span><span class="sxs-lookup"><span data-stu-id="b6183-118">Before you can start to use the quality management features and generate quality orders, you must configure the system and prerequisites.</span></span> <span data-ttu-id="b6183-119">Di seguito è riportato un elenco dei passaggi necessari per configurare la gestione della qualità.</span><span class="sxs-lookup"><span data-stu-id="b6183-119">Here is a list of the steps that are required to configure quality management.</span></span>

1. <span data-ttu-id="b6183-120">[Abilitare la gestione della qualità e della non conformità](#enable-qm).</span><span class="sxs-lookup"><span data-stu-id="b6183-120">[Enable quality and nonconformance management](#enable-qm).</span></span>
1. <span data-ttu-id="b6183-121">Facoltativo: [Configurare gli strumenti di test](quality-test-instruments.md).</span><span class="sxs-lookup"><span data-stu-id="b6183-121">Optional: [Configure test instruments](quality-test-instruments.md).</span></span>
1. <span data-ttu-id="b6183-122">[Configurare i test](quality-tests.md).</span><span class="sxs-lookup"><span data-stu-id="b6183-122">[Configure tests](quality-tests.md).</span></span>
1. <span data-ttu-id="b6183-123">[Configurare le variabili e i risultati dei test](quality-test-variables.md).</span><span class="sxs-lookup"><span data-stu-id="b6183-123">[Configure test variables and outcomes](quality-test-variables.md).</span></span>
1. <span data-ttu-id="b6183-124">[Configurare i gruppi di test](quality-test-groups.md).</span><span class="sxs-lookup"><span data-stu-id="b6183-124">[Configure test groups](quality-test-groups.md).</span></span>
1. <span data-ttu-id="b6183-125">Facoltativo: [Configurare i gruppi di controllo qualità e collegarli ai prodotti](quality-groups.md).</span><span class="sxs-lookup"><span data-stu-id="b6183-125">Optional: [Configure quality groups, and link to products](quality-groups.md).</span></span>
1. <span data-ttu-id="b6183-126">Facoltativo: [Configurare le associazioni di controllo qualità](quality-associations.md).</span><span class="sxs-lookup"><span data-stu-id="b6183-126">Optional: [Configure quality associations](quality-associations.md).</span></span>

<span data-ttu-id="b6183-127">Una volta completata la configurazione, è possibile iniziare a creare ed elaborare gli ordini di controllo qualità.</span><span class="sxs-lookup"><span data-stu-id="b6183-127">After the configuration is completed, you can start to create and process quality orders.</span></span> <span data-ttu-id="b6183-128">Per ulteriori informazioni su come creare e utilizzare gli ordini di controllo qualità, vedere [Ordini di controllo qualità](quality-orders.md).</span><span class="sxs-lookup"><span data-stu-id="b6183-128">For more information about how to create and work with quality orders, see [Quality orders](quality-orders.md).</span></span>

## <a name="nonconformance-management-configuration-process"></a><span data-ttu-id="b6183-129">Processo di configurazione della gestione delle non conformità</span><span class="sxs-lookup"><span data-stu-id="b6183-129">Nonconformance management configuration process</span></span>

<span data-ttu-id="b6183-130">Prima di poter iniziare a utilizzare le funzionalità di gestione delle non conformità e generare non conformità, è necessario configurare il sistema e i prerequisiti.</span><span class="sxs-lookup"><span data-stu-id="b6183-130">Before you can start to use the nonconformance management features and generate nonconformances, you must configure the system and prerequisites.</span></span> <span data-ttu-id="b6183-131">Di seguito è riportato un elenco dei passaggi necessari per configurare la gestione della non conformità.</span><span class="sxs-lookup"><span data-stu-id="b6183-131">Here is a list of the steps that are required to configure nonconformance management.</span></span>

1. <span data-ttu-id="b6183-132">[Abilitare la gestione della qualità e della non conformità](#enable-qm).</span><span class="sxs-lookup"><span data-stu-id="b6183-132">[Enable quality and nonconformance management](#enable-qm).</span></span>
1. <span data-ttu-id="b6183-133">[Configurare i lavoratori responsabili dell'approvazione delle non conformità](quality-responsible-workers.md)</span><span class="sxs-lookup"><span data-stu-id="b6183-133">[Configure workers who are responsible for approving nonconformances](quality-responsible-workers.md).</span></span>
1. <span data-ttu-id="b6183-134">[Configurare i tipi di problemi](quality-problem-types.md).</span><span class="sxs-lookup"><span data-stu-id="b6183-134">[Configure problem types](quality-problem-types.md).</span></span>
1. <span data-ttu-id="b6183-135">[Configurare le aree di quarantena](quality-quarantine-zones.md).</span><span class="sxs-lookup"><span data-stu-id="b6183-135">[Configure quarantine zones](quality-quarantine-zones.md).</span></span>
1. <span data-ttu-id="b6183-136">[Configurare i tipi di diagnostica](quality-diagnostic-types.md).</span><span class="sxs-lookup"><span data-stu-id="b6183-136">[Configure diagnostic types](quality-diagnostic-types.md).</span></span>
1. <span data-ttu-id="b6183-137">[Configurare le operazioni](quality-operations.md).</span><span class="sxs-lookup"><span data-stu-id="b6183-137">[Configure operations](quality-operations.md).</span></span>
1. <span data-ttu-id="b6183-138">Facoltativo: [Configurare le spese di gestione qualità](quality-charges.md).</span><span class="sxs-lookup"><span data-stu-id="b6183-138">Optional: [Configure quality charges](quality-charges.md).</span></span>

<span data-ttu-id="b6183-139">Una volta completata la configurazione, è possibile iniziare a creare ed elaborare le non conformità.</span><span class="sxs-lookup"><span data-stu-id="b6183-139">After the configuration is completed, you can start to create and process nonconformances.</span></span> <span data-ttu-id="b6183-140">Per ulteriori informazioni su come creare e utilizzare le non conformità, vedere [Creare ed elaborare le non conformità](tasks/create-process-non-conformance.md).</span><span class="sxs-lookup"><span data-stu-id="b6183-140">For more information about how to create and work with nonconformances, see [Create and process nonconformances](tasks/create-process-non-conformance.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="b6183-141">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="b6183-141">Additional resources</span></span>

- [<span data-ttu-id="b6183-142">Panoramica gestione qualità</span><span class="sxs-lookup"><span data-stu-id="b6183-142">Quality management overview</span></span>](quality-management-processes.md)
- [<span data-ttu-id="b6183-143">Abilitare la gestione della qualità e della non conformità</span><span class="sxs-lookup"><span data-stu-id="b6183-143">Enable quality and nonconformance management</span></span>](enable-quality-management.md)
- [<span data-ttu-id="b6183-144">Gestione qualità per i processi di magazzino</span><span class="sxs-lookup"><span data-stu-id="b6183-144">Quality management for warehouse processes</span></span>](quality-management-for-warehouses-processes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
