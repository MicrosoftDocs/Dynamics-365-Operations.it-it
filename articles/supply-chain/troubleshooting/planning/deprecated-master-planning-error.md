---
title: Viene visualizzato un errore durante l'esecuzione del motore di pianificazione generale integrato
description: Quando si esegue il motore di pianificazione generale integrato viene visualizzato un messaggio di errore.
author: ankubik
ms.date: 06/10/2021
ms.topic: troubleshooting
ms.search.form: Dialog_ReqCalcScheduleItemTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ankubik
ms.search.validFrom: 2021-06-10
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 9c950292a4f43319d21a7deafdfb341b7bef15d8
ms.sourcegitcommit: 18ca2df785e9656fdd4e8c0734eca2b2624fda10
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/22/2021
ms.locfileid: "6294111"
---
# <a name="you-receive-an-error-when-running-the-built-in-master-planning-engine"></a><span data-ttu-id="1fd71-103">Viene visualizzato un errore durante l'esecuzione del motore di pianificazione generale integrato</span><span class="sxs-lookup"><span data-stu-id="1fd71-103">You receive an error when running the built-in master planning engine</span></span>

<span data-ttu-id="1fd71-104">Codice di errore: ReqCalcScheduleItemTablePlanningOptimizationFitError</span><span class="sxs-lookup"><span data-stu-id="1fd71-104">Error code: ReqCalcScheduleItemTablePlanningOptimizationFitError</span></span>

## <a name="symptoms"></a><span data-ttu-id="1fd71-105">Sintomi</span><span class="sxs-lookup"><span data-stu-id="1fd71-105">Symptoms</span></span>

<span data-ttu-id="1fd71-106">Quando si esegue la pianificazione generale viene visualizzato il seguente messaggio di errore:</span><span class="sxs-lookup"><span data-stu-id="1fd71-106">When you run master planning by using the deprecated built-in master planning engine, you receive the following error message:</span></span>

> <span data-ttu-id="1fd71-107">Viene visualizzato questo messaggio di errore perché il motore di pianificazione generale incorporato è stato utilizzato per gli scenari supportati da Ottimizzazione pianificazione.</span><span class="sxs-lookup"><span data-stu-id="1fd71-107">You receive this error message because the built-in master planning engine was used for scenarios supported by Planning Optimization.</span></span> <span data-ttu-id="1fd71-108">È necessario eseguire la migrazione a Ottimizzazione pianificazione ora, poiché l'attuale pianificazione generale incorporata sarà deprecata.</span><span class="sxs-lookup"><span data-stu-id="1fd71-108">You should migrate to Planning Optimization now, as the current built-in master planning will be deprecated.</span></span> <span data-ttu-id="1fd71-109">Notare che l'esecuzione della pianificazione generale viene completata correttamente.</span><span class="sxs-lookup"><span data-stu-id="1fd71-109">Note that this master planning run did complete successfully.</span></span> <span data-ttu-id="1fd71-110">Nel caso in cui la migrazione abbia forti dipendenze da funzionalità in sospeso, è possibile richiedere un'eccezione per l'utilizzo continuato del motore di pianificazione generale integrato.</span><span class="sxs-lookup"><span data-stu-id="1fd71-110">In case your migration has strong dependencies on pending features, an exception to continued usage of the built-in master planning engine can be requested.</span></span> <span data-ttu-id="1fd71-111">Completare il seguente questionario per iniziare e, se pertinente, richiedere l'eccezione dalla migrazione a Ottimizzazione pianificazione.</span><span class="sxs-lookup"><span data-stu-id="1fd71-111">Please complete the following questionnaire to get started and, if relevant, request an exception from migration to Planning Optimization.</span></span> [<span data-ttu-id="1fd71-112">Questionario sulla migrazione e sulle eccezioni di Ottimizzazione pianificazione</span><span class="sxs-lookup"><span data-stu-id="1fd71-112">Planning Optimization migration and exception questionnaire</span></span>](https://go.microsoft.com/fwlink/?linkid=2144962)

## <a name="cause"></a><span data-ttu-id="1fd71-113">Causa</span><span class="sxs-lookup"><span data-stu-id="1fd71-113">Cause</span></span>

<span data-ttu-id="1fd71-114">Se si esegue la pianificazione e non si utilizzano le funzionalità di controllo della produzione, è consigliabile eseguire la migrazione a Ottimizzazione pianificazione.</span><span class="sxs-lookup"><span data-stu-id="1fd71-114">If you run planning and don't use production control features, you should consider migrating to Planning Optimization.</span></span> <span data-ttu-id="1fd71-115">Il motore di pianificazione generale integrato è stato deprecato.</span><span class="sxs-lookup"><span data-stu-id="1fd71-115">The built-in master planning engine is being deprecated.</span></span> <span data-ttu-id="1fd71-116">Pertanto, per continuare a utilizzarlo senza ricevere il messaggio di errore, è necessario richiedere un'eccezione a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1fd71-116">Therefore, if you want to continue to use it without receiving the error message, you must apply for an exception from Microsoft.</span></span>

## <a name="resolution"></a><span data-ttu-id="1fd71-117">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="1fd71-117">Resolution</span></span>

<span data-ttu-id="1fd71-118">Per ulteriori informazioni su come eseguire la migrazione a Ottimizzazione pianificazione o su come richiedere un'eccezione in modo da poter continuare a utilizzare il motore di pianificazione integrato deprecato, vedi [Migrazione a Ottimizzazione pianificazione per la pianificazione generale](/dynamics365/supply-chain/master-planning/new-master-planning-engine).</span><span class="sxs-lookup"><span data-stu-id="1fd71-118">For more information about how to migrate to Planning Optimization, or how to apply for an exception so that you can continue to use the deprecated built-in planning engine instead, see [Migration to Planning Optimization for master planning](/dynamics365/supply-chain/master-planning/new-master-planning-engine).</span></span>
