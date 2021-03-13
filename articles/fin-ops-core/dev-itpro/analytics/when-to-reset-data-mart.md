---
title: Quando reimpostare un data mart
description: Questo argomento elenca le circostanze che potrebbero essere migliorate reimpostando un data mart e le circostanze in cui è improbabile che la reimpostazione del data mart sia di aiuto.
author: jinniew
manager: AnnBe
ms.date: 12/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: jiwo
ms.search.validFrom: 2020-12-15
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 1c1524c7a1a3fbe71c51b23571996d87641cdf7e
ms.sourcegitcommit: 5192cfaedfd861faea63d8954d7bcc500608a225
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2021
ms.locfileid: "5093214"
---
# <a name="when-to-reset-a-data-mart"></a><span data-ttu-id="7a376-103">Quando reimpostare un data mart</span><span class="sxs-lookup"><span data-stu-id="7a376-103">When to reset a data mart</span></span>

<span data-ttu-id="7a376-104">La reimpostazione di un data mart può richiedere molto tempo.</span><span class="sxs-lookup"><span data-stu-id="7a376-104">Resetting a data mart can be time consuming.</span></span> <span data-ttu-id="7a376-105">A seconda delle circostanze, questa azione potrebbe non essere la soluzione necessaria.</span><span class="sxs-lookup"><span data-stu-id="7a376-105">Depending on the circumstances, this action may not be the solution that's needed.</span></span> <span data-ttu-id="7a376-106">Questo argomento elenca le circostanze che potrebbero essere migliorate reimpostando un data mart, nonché le circostanze in cui è improbabile che la reimpostazione del data mart sia di aiuto.</span><span class="sxs-lookup"><span data-stu-id="7a376-106">This topic lists the circumstances that might be improved by resetting a data mart, as well as circumstances in which resetting your data mart is unlikely to help.</span></span>  

## <a name="when-do-you-need-to-do-a-data-mart-reset"></a><span data-ttu-id="7a376-107">Quando è necessario eseguire un ripristino del data mart?</span><span class="sxs-lookup"><span data-stu-id="7a376-107">When do you need to do a data mart reset?</span></span>
<span data-ttu-id="7a376-108">Considera le seguenti domande prima di reimpostare un data mart.</span><span class="sxs-lookup"><span data-stu-id="7a376-108">Consider the following questions before resetting a data mart.</span></span> <span data-ttu-id="7a376-109">La risposta affermativa a una o più domande potrebbe indicare che l'organizzazione può trarre vantaggio dalla reimpostazione del data mart.</span><span class="sxs-lookup"><span data-stu-id="7a376-109">Answering yes to one or more questions might indicate that your organization can benefit by resetting the data mart.</span></span>

- <span data-ttu-id="7a376-110">Il database dell'applicazione è stato ripristinato, ma non è stato ripristinato il database data mart.</span><span class="sxs-lookup"><span data-stu-id="7a376-110">The application database was restored, but the data mart database was not restored.</span></span>
- <span data-ttu-id="7a376-111">Vengono visualizzati dati errati per un periodo contabile, che non sono il risultato di un problema con la progettazione del report.</span><span class="sxs-lookup"><span data-stu-id="7a376-111">You see incorrect data for an accounting period, which isn't the result of an issue with the report design.</span></span>
- <span data-ttu-id="7a376-112">Vengono visualizzati dati errati per un periodo contabile e i record sono elencati in Tentativi di integrazione nella pagina **Stato integrazione** in Progettazione report (avvia Progettazione report e seleziona **Strumenti> Stato integrazione**).</span><span class="sxs-lookup"><span data-stu-id="7a376-112">You see incorrect data for an accounting period, and records are listed under Integration attempts on the **Integration status** page in Report Designer (start the Report Designer and select **Tools > Integration status**).</span></span>
- <span data-ttu-id="7a376-113">Hai aperto un incidente di supporto e un tecnico del supporto ti ha chiesto di reimpostare il data mart come parte di un passaggio di risoluzione dei problemi.</span><span class="sxs-lookup"><span data-stu-id="7a376-113">You've opened a support incident and a support engineer has instructed you to reset the data mart as part of a troubleshooting step.</span></span>
 
## <a name="when-its-not-appropriate-to-reset-a-data-mart"></a><span data-ttu-id="7a376-114">Quando non è opportuno reimpostare un data mart?</span><span class="sxs-lookup"><span data-stu-id="7a376-114">When it's not appropriate to reset a data mart?</span></span>
<span data-ttu-id="7a376-115">In alcune circostanze non è consigliabile reimpostare un data mart,</span><span class="sxs-lookup"><span data-stu-id="7a376-115">There are some circumstances when we don't recommend resetting a data mart.</span></span> <span data-ttu-id="7a376-116">tra cui le seguenti.</span><span class="sxs-lookup"><span data-stu-id="7a376-116">These include the following.</span></span> 

- <span data-ttu-id="7a376-117">Ogni volta che il motivo non è elencato in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="7a376-117">Anytime the reason isn’t listed in this topic.</span></span>
- <span data-ttu-id="7a376-118">Stai riscontrando problemi di prestazioni associati a una sincronizzazione dei dati. In questa circostanza, la reimpostazione del data mart probabilmente non è di aiuto.</span><span class="sxs-lookup"><span data-stu-id="7a376-118">You're experiencing performance issues that are associated with a data sync. In this circumstance, resetting the data mart probably won't help.</span></span>
- <span data-ttu-id="7a376-119">Se si dispone di uno schema di ripristino ricorrente dovuto a uno dei seguenti motivi:</span><span class="sxs-lookup"><span data-stu-id="7a376-119">If you have a recurring reset pattern due to any of the following reasons:</span></span> 
  - <span data-ttu-id="7a376-120">**Dati mancanti** - In primo luogo, elimina i problemi di progettazione dei report e i problemi di sincronizzazione dei dati, ad esempio, osservi che la mappa dei fatti non è stata eseguita da quando sono stati pubblicati i dati mancanti.</span><span class="sxs-lookup"><span data-stu-id="7a376-120">**Missing data** - First, eliminate report design issues and data sync timing issues, for example, you observe that the fact map hasn’t run since missing data was posted.</span></span>
  - <span data-ttu-id="7a376-121">**Stato di integrazione bloccato** - Se l'integrazione è lenta o sembra bloccata, è improbabile che il ripristino del data mart risolva il problema.</span><span class="sxs-lookup"><span data-stu-id="7a376-121">**Stuck integration state** - If the integration is slow or seems stuck, resetting the data mart is unlikely to resolve the issue.</span></span>
  - <span data-ttu-id="7a376-122">**I tentativi di ripristino non hanno avuto successo** - Se sono stati effettuati diversi tentativi per completare un ripristino e non hanno avuto successo a causa della mancanza di dati, si consiglia di aprire un incidente di supporto e di collaborare con un tecnico dell'assistenza per analizzare la situazione prima di tentare di ripristinare nuovamente il data mart.</span><span class="sxs-lookup"><span data-stu-id="7a376-122">**Attempts to reset have been unsuccessful** - If a number of attempts to complete a reset have been made, and have been unsuccessful because of missing data, we recommend opening a support incident and working with a support engineer to analyze your situation before attempting to reset the data mart again.</span></span>
  - <span data-ttu-id="7a376-123">**Record obsoleti** - I record obsoleti da soli non giustificano necessariamente il ripristino del data mart.</span><span class="sxs-lookup"><span data-stu-id="7a376-123">**Stale records** - Stale records by themselves don't necessarily justify resetting the data mart.</span></span> <span data-ttu-id="7a376-124">Se si dispone di un set di dati di grandi dimensioni, l'esecuzione del processo di ripristino richiederà un po' di tempo, ma è improbabile che si verifichi un miglioramento.</span><span class="sxs-lookup"><span data-stu-id="7a376-124">If you have a large data set, the reset process will take some time to run, but is unlikely to result in improvement.</span></span>
 
## <a name="what-a-data-mart-reset-does-not-do"></a><span data-ttu-id="7a376-125">Cosa non fa un ripristino del data mart</span><span class="sxs-lookup"><span data-stu-id="7a376-125">What a data mart reset does not do</span></span>  
- <span data-ttu-id="7a376-126">Un ripristino inizierà solo al termine delle attività esistenti.</span><span class="sxs-lookup"><span data-stu-id="7a376-126">A reset will only start when existing tasks are complete.</span></span> <span data-ttu-id="7a376-127">Ciò garantisce che i vecchi dati non vengano inseriti.</span><span class="sxs-lookup"><span data-stu-id="7a376-127">This ensures that old data is not inserted.</span></span> <span data-ttu-id="7a376-128">A questo punto potrebbe essere visualizzato un messaggio del tipo "Impossibile elaborare il ripristino del data mart a causa di un'attività attiva.</span><span class="sxs-lookup"><span data-stu-id="7a376-128">At this point you may see a message such as, “The data mart reset was unable to be processed because of an active task.</span></span> <span data-ttu-id="7a376-129">Riprova più tardi."</span><span class="sxs-lookup"><span data-stu-id="7a376-129">Please try again later.”</span></span>
- <span data-ttu-id="7a376-130">Il ripristino disabiliterà le attività di integrazione ed eliminerà tutti i dati del data mart.</span><span class="sxs-lookup"><span data-stu-id="7a376-130">The reset will disable the integration tasks and delete all the data mart data.</span></span> <span data-ttu-id="7a376-131">L'integrazione viene nuovamente abilitata.</span><span class="sxs-lookup"><span data-stu-id="7a376-131">The integration is re-enabled.</span></span>

> [!NOTE]
> <span data-ttu-id="7a376-132">I seguenti punti specificano due cose che il ripristino di un data mart *non* fa.</span><span class="sxs-lookup"><span data-stu-id="7a376-132">The following points specify two things that resetting a data mart will *not* do.</span></span> <br>
> - <span data-ttu-id="7a376-133">I ripristini non cancellano le progettazioni di report.</span><span class="sxs-lookup"><span data-stu-id="7a376-133">Resets do not clear report designs.</span></span> <br>
> - <span data-ttu-id="7a376-134">I ripristini non cancellano i dati della società o dei dati dell'utente a meno che non siano selezionati.</span><span class="sxs-lookup"><span data-stu-id="7a376-134">Resets do not clear company data or user data unless selected.</span></span>
