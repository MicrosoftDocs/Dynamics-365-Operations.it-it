---
title: Prestazioni di programmazione risorse di progetto
description: Questo argomento fornisce informazioni su come migliorare le prestazioni della programmazione delle risorse per un numero elevato di progetti.
author: Yowelle
manager: AnnBe
ms.date: 08/31/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Service industries
ms.author: v-radsh
ms.dyn365.ops.version: 10.0.14
ms.search.validFrom: 2020-09-01
ms.openlocfilehash: 988fc83230f08a6534caa7c37784757d73c1cc12
ms.sourcegitcommit: 241ada0945c72d769eaa70ae35aedbb6a3233fdf
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/02/2020
ms.locfileid: "3760589"
---
# <a name="project-resource-scheduling-performance"></a><span data-ttu-id="5c9a7-103">Prestazioni di programmazione risorse di progetto</span><span class="sxs-lookup"><span data-stu-id="5c9a7-103">Project resource scheduling performance</span></span>

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]


<span data-ttu-id="5c9a7-104">I problemi di prestazioni relativi alla programmazione delle risorse possono verificarsi quando il numero di progetti raggiunge le migliaia.</span><span class="sxs-lookup"><span data-stu-id="5c9a7-104">Performance issues related to resource scheduling can occur when the number of projects reaches into the thousands.</span></span> <span data-ttu-id="5c9a7-105">Per migliorare le prestazioni della programmazione delle risorse, è disponibile una funzione che consente agli utenti di ridurre il tempo necessario per avviare il modulo di disponibilità delle risorse.</span><span class="sxs-lookup"><span data-stu-id="5c9a7-105">To improve resource scheduling performance, a feature is available that allows users to reduce the time that it takes to launch the resource availability form.</span></span> <span data-ttu-id="5c9a7-106">In particolare, viene rimosso il processo di sincronizzazione di roll-up della capacità delle risorse e utilizzata la tabella **ResProjectResource** per velocizzare la ricerca delle risorse.</span><span class="sxs-lookup"><span data-stu-id="5c9a7-106">Specifically, this removes the resource capacity roll-up synchronization process and uses the **ResProjectResource** table to speed up the resource lookup.</span></span> <span data-ttu-id="5c9a7-107">Notare che la tabella **ResRollup** non verrà più utilizzata.</span><span class="sxs-lookup"><span data-stu-id="5c9a7-107">Note that the **ResRollup** table will no longer be used.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5c9a7-108">Se esiste una dipendenza dal processo di sincronizzazione di roll-up della capacità delle risorse o dalla tabella **ResProjectResource**, non utilizzare questa funzione.</span><span class="sxs-lookup"><span data-stu-id="5c9a7-108">If there is a dependency on either the resource capacity roll-up synchronization process or the **ResProjectResource** table, do not use this feature.</span></span>

## <a name="enable-resource-scheduling-performance-enhancement"></a><span data-ttu-id="5c9a7-109">Abilitare il miglioramento delle prestazioni della programmazione delle risorse</span><span class="sxs-lookup"><span data-stu-id="5c9a7-109">Enable resource scheduling performance enhancement</span></span>
<span data-ttu-id="5c9a7-110">Per abilitare il miglioramento delle prestazioni della programmazione delle risorse, completare i seguenti passaggi.</span><span class="sxs-lookup"><span data-stu-id="5c9a7-110">To enable resource scheduling performance enhancement, complete the following steps.</span></span>

1. <span data-ttu-id="5c9a7-111">Andare a **Gestione funzionalità** > **Tutto** e nell'elenco delle funzionalità individuare **Abilita il miglioramento delle prestazioni della programmazione delle risorse di progetto**.</span><span class="sxs-lookup"><span data-stu-id="5c9a7-111">Go to **Feature management** > **All**, and in the feature list, locate **Enable project resource scheduling performance enhancement feature**.</span></span>
2. <span data-ttu-id="5c9a7-112">Selezionare **Abilita ora**.</span><span class="sxs-lookup"><span data-stu-id="5c9a7-112">Select **Enable now**.</span></span>

> [!NOTE]
> <span data-ttu-id="5c9a7-113">Se non si riesce a trovare la funzione nell'elenco, selezionare **Controlla aggiornamenti** per aggiornare l'elenco.</span><span class="sxs-lookup"><span data-stu-id="5c9a7-113">If you can't find the feature in the list, select **Check for updates** to refresh the list.</span></span>

3. <span data-ttu-id="5c9a7-114">Aggiornare il browser, quindi andare a **Gestione progetti e contabilità** > **Periodico** > **Risorse di progetto** > **Sincronizza capacità dei calendari delle risorse per tutte le società**.</span><span class="sxs-lookup"><span data-stu-id="5c9a7-114">Refresh your browser, and then go to **Project management and accounting** > **Periodic** > **Project resources** > **Synchronize resource calendars capacity across all companies**.</span></span>
4. <span data-ttu-id="5c9a7-115">Impostare **Rimuovi record di capacità esistenti** su **Sì** per rimuovere i dati precedenti.</span><span class="sxs-lookup"><span data-stu-id="5c9a7-115">Set **Remove existing capacity records** to **Yes** to remove previous data.</span></span> <span data-ttu-id="5c9a7-116">Se si desidera generare dati incrementali, impostare su **No**.</span><span class="sxs-lookup"><span data-stu-id="5c9a7-116">If you want generate incremental data, set it to **No**.</span></span>
5. <span data-ttu-id="5c9a7-117">Nel campo **Codice periodo** selezionare il periodo in cui generare i dati.</span><span class="sxs-lookup"><span data-stu-id="5c9a7-117">In the **Period code** field, select the period in which data should be generated.</span></span> <span data-ttu-id="5c9a7-118">Se si seleziona un codice periodo, non è necessario definire una data di inizio e di fine.</span><span class="sxs-lookup"><span data-stu-id="5c9a7-118">If you select a period code, a start and end date do not need to be defined.</span></span>
6. <span data-ttu-id="5c9a7-119">Se si lascia il campo **Codice periodo** vuoto, selezionare date di inizio e fine specifiche per generare i dati.</span><span class="sxs-lookup"><span data-stu-id="5c9a7-119">If you leave the **Period code** field blank, select specific start and end dates to generate data.</span></span>
7. <span data-ttu-id="5c9a7-120">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="5c9a7-120">Select **OK**.</span></span>

 > [!NOTE]
 > <span data-ttu-id="5c9a7-121">Questo distribuirà i dati generali alla tabella **ResCalendarCapacity** per tutte le società dell'ambiente, quindi il processo batch deve essere eseguito solo in una persona giuridica.</span><span class="sxs-lookup"><span data-stu-id="5c9a7-121">This will distribute general data to the **ResCalendarCapacity** table across all companies in your environment, so the batch job only needs to be run in one legal entity.</span></span> <span data-ttu-id="5c9a7-122">I dati in questo processo batch sono necessari per calcolare la capacità delle risorse tramite il calendario associato.</span><span class="sxs-lookup"><span data-stu-id="5c9a7-122">The data in this batch job is needed to calculate resource capacity through the associated calendar.</span></span>

8. <span data-ttu-id="5c9a7-123">Andare a **Gestione progetti e contabilità** > **Periodico** > **Risorse di progetto** > **Popola risorse del progetto per tutte le società** e selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="5c9a7-123">Go to **Project management and accounting** > **Periodic** > **Project resources** > **Populate project resources across all companies** and then select **OK**.</span></span> <span data-ttu-id="5c9a7-124">Questo è lo script di aggiornamento per i dati generali nelle tabelle **ResProjectResource**, **ResCalendarDateTimeRange** e **ResEffectiveDateTimeRange**.</span><span class="sxs-lookup"><span data-stu-id="5c9a7-124">This is the data upgrade script for general data in the **ResProjectResource**, **ResCalendarDateTimeRange**, and **ResEffectiveDateTimeRange** tables.</span></span> <span data-ttu-id="5c9a7-125">I valori per il campo **PSAPRojSchedRole.RootActivity** vengono aggiornati.</span><span class="sxs-lookup"><span data-stu-id="5c9a7-125">Values for the **PSAPRojSchedRole.RootActivity** field are also updated.</span></span> <span data-ttu-id="5c9a7-126">Se non viene eseguito, viene visualizzato un avviso quando si prova a eseguire le operazioni di pianificazione delle risorse.</span><span class="sxs-lookup"><span data-stu-id="5c9a7-126">If this is not run, you will receive a warning when you try to execute resource scheduling operations.</span></span>
 
## <a name="turn-off-resource-scheduling-performance-enhancement"></a><span data-ttu-id="5c9a7-127">Disattivare il miglioramento delle prestazioni della programmazione delle risorse</span><span class="sxs-lookup"><span data-stu-id="5c9a7-127">Turn off resource scheduling performance enhancement</span></span>

1. <span data-ttu-id="5c9a7-128">Andare a **Gestione funzionalità** > **Tutto** e individuare **Abilita il miglioramento delle prestazioni della programmazione delle risorse di progetto**.</span><span class="sxs-lookup"><span data-stu-id="5c9a7-128">Go to **Feature management** > **All**  and search for **Enable project resource scheduling performance enhancement feature**.</span></span>
2. <span data-ttu-id="5c9a7-129">Selezionare la funzione, quindi selezionare il pulsante **Disabilita**.</span><span class="sxs-lookup"><span data-stu-id="5c9a7-129">Select the feature, and then select the **Disable** button.</span></span>
3. <span data-ttu-id="5c9a7-130">Aggiornare il browser.</span><span class="sxs-lookup"><span data-stu-id="5c9a7-130">Refresh your browser.</span></span>
4. <span data-ttu-id="5c9a7-131">Andare a **Gestione progetti e contabilità** > **Periodico** > **Sincronizzazione capacità** > **Sincronizza rollup capacità risorse**.</span><span class="sxs-lookup"><span data-stu-id="5c9a7-131">Go to **Project management and accounting** > **Periodic** > **Capacity synchronization** > **Synchronize resource capacity roll-ups**.</span></span>
5. <span data-ttu-id="5c9a7-132">Nella pagina **Sincronizza rollup capacità** impostare **Rimuovi record di capacità esistenti** su **Sì** per rimuovere i dati precedenti.</span><span class="sxs-lookup"><span data-stu-id="5c9a7-132">On the **Capacity roll-up synchronization** page, set **Remove existing capacity records** to **Yes** to remove previous data.</span></span> <span data-ttu-id="5c9a7-133">Se si desidera generare dati incrementali, impostare su **No**.</span><span class="sxs-lookup"><span data-stu-id="5c9a7-133">If you want to generate incremental data, set it to **No**.</span></span>
6. <span data-ttu-id="5c9a7-134">Nel campo **Codice periodo** selezionare il periodo in cui generare i dati.</span><span class="sxs-lookup"><span data-stu-id="5c9a7-134">In the **Period code** field, select the period in which data should be generated.</span></span> <span data-ttu-id="5c9a7-135">Se si seleziona un codice periodo, non è necessario definire una data di inizio e di fine.</span><span class="sxs-lookup"><span data-stu-id="5c9a7-135">If you select a period code, a start and end date do not need to be defined.</span></span>
7. <span data-ttu-id="5c9a7-136">Se si lascia il campo **Codice periodo** vuoto, selezionare date di inizio e fine specifiche per generare i dati.</span><span class="sxs-lookup"><span data-stu-id="5c9a7-136">If you leave the **Period code** field blank, select specific start and end dates to generate data.</span></span>
8. <span data-ttu-id="5c9a7-137">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="5c9a7-137">Select **OK**.</span></span>

> [!NOTE]
> <span data-ttu-id="5c9a7-138">Questo distribuirà i dati generali alla tabella **ResRollup** per tutte le società dell'ambiente, quindi il processo batch deve essere eseguito solo in una persona giuridica.</span><span class="sxs-lookup"><span data-stu-id="5c9a7-138">This will distribute general data to the **ResRollup** table across all companies in your environment, so the batch job only needs to be run in one legal entity.</span></span> <span data-ttu-id="5c9a7-139">Questo processo batch è necessario per tutte le visualizzazioni **Disponibilità risorse**.</span><span class="sxs-lookup"><span data-stu-id="5c9a7-139">This batch job is needed for all **Resource Availability** views.</span></span> <span data-ttu-id="5c9a7-140">Se questo processo batch non viene eseguito, i dati **ResRollup** verranno generati immediatamente, il che può richiedere tempo.</span><span class="sxs-lookup"><span data-stu-id="5c9a7-140">If this batch job is not run, the **ResRollup** data will be generated on the fly, which can take time.</span></span>
