---
title: Quando reimpostare un data mart
description: Questo argomento elenca le circostanze che potrebbero essere migliorate reimpostando un data mart e le circostanze in cui è improbabile che la reimpostazione del data mart sia di aiuto.
author: jinniew
ms.date: 05/06/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: jiwo
ms.search.validFrom: 2021-05-06
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: bc2c4ee490f3bebd6e7c91609a06f8dfedfcb628
ms.sourcegitcommit: 5916ea2a94ab9af7aac21f0fc44e194d5ce82917
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2021
ms.locfileid: "5988994"
---
# <a name="when-to-reset-a-data-mart"></a><span data-ttu-id="5d18a-103">Quando reimpostare un data mart</span><span class="sxs-lookup"><span data-stu-id="5d18a-103">When to reset a data mart</span></span>

<span data-ttu-id="5d18a-104">La reimpostazione di un data mart può richiedere molto tempo.</span><span class="sxs-lookup"><span data-stu-id="5d18a-104">Resetting a data mart can be time consuming.</span></span> <span data-ttu-id="5d18a-105">A seconda delle circostanze, questa azione potrebbe non essere la soluzione necessaria.</span><span class="sxs-lookup"><span data-stu-id="5d18a-105">Depending on the circumstances, this action may not be the solution that's needed.</span></span> <span data-ttu-id="5d18a-106">Questo argomento elenca le circostanze che potrebbero essere migliorate reimpostando un data mart, nonché le circostanze in cui è improbabile che la reimpostazione del data mart sia di aiuto.</span><span class="sxs-lookup"><span data-stu-id="5d18a-106">This topic lists the circumstances that might be improved by resetting a data mart, as well as circumstances in which resetting your data mart is unlikely to help.</span></span>  

## <a name="when-do-i-need-to-do-a-data-mart-reset"></a><span data-ttu-id="5d18a-107">Quando devo eseguire la reimpostazione del data mart?</span><span class="sxs-lookup"><span data-stu-id="5d18a-107">When do I need to do a data mart reset?</span></span>
<span data-ttu-id="5d18a-108">Considera le seguenti domande prima di reimpostare un data mart.</span><span class="sxs-lookup"><span data-stu-id="5d18a-108">Consider the following questions before resetting a data mart.</span></span> <span data-ttu-id="5d18a-109">La risposta affermativa a una o più domande potrebbe indicare che l'organizzazione può trarre vantaggio dalla reimpostazione del data mart.</span><span class="sxs-lookup"><span data-stu-id="5d18a-109">Answering yes to one or more questions might indicate that your organization can benefit by resetting the data mart.</span></span>

- <span data-ttu-id="5d18a-110">Il database dell'applicazione è stato ripristinato?</span><span class="sxs-lookup"><span data-stu-id="5d18a-110">Was the application database restored?</span></span>
- <span data-ttu-id="5d18a-111">Se hai aperto un incidente di supporto e un tecnico del supporto ti ha chiesto di reimpostare il data mart come parte di un passaggio di risoluzione dei problemi.</span><span class="sxs-lookup"><span data-stu-id="5d18a-111">If you've opened a support incident that and a support engineer has instructed you to reset the data mart as part of a troubleshooting step?</span></span>
 
## <a name="when-is-it-not-appropriate-to-reset-a-data-mart"></a><span data-ttu-id="5d18a-112">Quando non è opportuno reimpostare un data mart?</span><span class="sxs-lookup"><span data-stu-id="5d18a-112">When is it not appropriate to reset a data mart?</span></span>
<span data-ttu-id="5d18a-113">In alcune circostanze non è consigliabile reimpostare un data mart,</span><span class="sxs-lookup"><span data-stu-id="5d18a-113">There are some circumstances when we don't recommend resetting a data mart.</span></span> <span data-ttu-id="5d18a-114">tra cui le seguenti.</span><span class="sxs-lookup"><span data-stu-id="5d18a-114">These include the following.</span></span> 

- <span data-ttu-id="5d18a-115">Stai riscontrando problemi di prestazioni associati a una sincronizzazione dei dati.</span><span class="sxs-lookup"><span data-stu-id="5d18a-115">You're experiencing performance issues that are associated with a data sync.</span></span> 
- <span data-ttu-id="5d18a-116">Se si dispone di uno schema di ripristino ricorrente dovuto a uno dei seguenti motivi:</span><span class="sxs-lookup"><span data-stu-id="5d18a-116">If you have a recurring reset pattern due to any of the following reasons:</span></span> 
  - <span data-ttu-id="5d18a-117">**Dati mancanti**</span><span class="sxs-lookup"><span data-stu-id="5d18a-117">**Missing data**</span></span> 
  - <span data-ttu-id="5d18a-118">**Stato di integrazione bloccato**</span><span class="sxs-lookup"><span data-stu-id="5d18a-118">**Stuck integration state**</span></span> 
  - <span data-ttu-id="5d18a-119">**Record obsoleti** - I record obsoleti da soli non giustificano necessariamente la reimpostazione del data mart.</span><span class="sxs-lookup"><span data-stu-id="5d18a-119">**Stale records** - Stale records by themselves don't necessarily justify resetting the data mart.</span></span> <span data-ttu-id="5d18a-120">Se si dispone di un set di dati di grandi dimensioni, l'esecuzione del processo di reimpostazione richiederà un po' di tempo, ma è improbabile che si verifichi un miglioramento.</span><span class="sxs-lookup"><span data-stu-id="5d18a-120">If you have a large data set, the reset process will take some time to run, but is unlikely to result in improvement.</span></span>
 
## <a name="what-is-a-data-mart-reset"></a><span data-ttu-id="5d18a-121">Cos'è una reimpostazione di un data mart?</span><span class="sxs-lookup"><span data-stu-id="5d18a-121">What is a data mart reset?</span></span>
- <span data-ttu-id="5d18a-122">Una reimpostazione inizierà solo al termine delle attività esistenti.</span><span class="sxs-lookup"><span data-stu-id="5d18a-122">A reset will only start when existing tasks are complete.</span></span> <span data-ttu-id="5d18a-123">Ciò garantisce che i vecchi dati non vengano inseriti.</span><span class="sxs-lookup"><span data-stu-id="5d18a-123">This ensures that old data is not inserted.</span></span> <span data-ttu-id="5d18a-124">A questo punto potrebbe essere visualizzato un messaggio del tipo "Impossibile elaborare la reimpostazione del data mart a causa di un'attività attiva.</span><span class="sxs-lookup"><span data-stu-id="5d18a-124">At this point you may see a message such as, “The data mart reset was unable to be processed because of an active task.</span></span> <span data-ttu-id="5d18a-125">Riprova più tardi."</span><span class="sxs-lookup"><span data-stu-id="5d18a-125">Please try again later.”</span></span>
- <span data-ttu-id="5d18a-126">La reimpostazione disabiliterà le attività di integrazione ed eliminerà tutti i dati del data mart.</span><span class="sxs-lookup"><span data-stu-id="5d18a-126">The reset will disable the integration tasks and delete all the data mart data.</span></span> <span data-ttu-id="5d18a-127">L'integrazione viene nuovamente abilitata.</span><span class="sxs-lookup"><span data-stu-id="5d18a-127">The integration is re-enabled.</span></span>

## <a name="if-i-reset-the-data-mart-will-i-lose-reports-that-ive-already-designed"></a><span data-ttu-id="5d18a-128">Se reimposto il data mart, perderò i report che ho già progettato?</span><span class="sxs-lookup"><span data-stu-id="5d18a-128">If I reset the data mart, will I lose reports that I've already designed?</span></span> 
<span data-ttu-id="5d18a-129">No, i report vengono archiviati in tabelle SQL che non sono influenzate da una reimpostazione del data mart.</span><span class="sxs-lookup"><span data-stu-id="5d18a-129">No, your reports are stored in SQL tables that are not impacted by a reset of the data mart.</span></span> <span data-ttu-id="5d18a-130">Se sei preoccupato di perdere i report che hai progettato, puoi eseguire il backup dei dati che non vuoi rischiare di perdere.</span><span class="sxs-lookup"><span data-stu-id="5d18a-130">If you are concerned about losing any reports you've designed, you can back up the designs that you don't want to lose.</span></span> <span data-ttu-id="5d18a-131">Per eseguire il backup, apri Report Designer e vai a **Società > Società > Blocchi predefinit > Esporta**.</span><span class="sxs-lookup"><span data-stu-id="5d18a-131">To back them up, open Report Designer and go to **Company > Companies > Building Blocks > Export**.</span></span>
 
## <a name="is-it-necessary-for-all-users-to-exit-the-system-to-reset-the-data-mart"></a><span data-ttu-id="5d18a-132">È necessario che tutti gli utenti escano dal sistema per reimpostare il data mart?</span><span class="sxs-lookup"><span data-stu-id="5d18a-132">Is it necessary for all users to exit the system to reset the data mart?</span></span>
<span data-ttu-id="5d18a-133">No, gli utenti possono continuare a lavorare nel sistema durante la reimpostazione del data mart.</span><span class="sxs-lookup"><span data-stu-id="5d18a-133">No, users can continue working in the system during the data mart reset.</span></span> <span data-ttu-id="5d18a-134">Tuttavia, non potranno accedere ai report creati con Financial Reporter fino al termine della reimpostazione.</span><span class="sxs-lookup"><span data-stu-id="5d18a-134">However, they won’t be able to access any reports that were created with Financial Reporter until the reset is finished.</span></span> 

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
