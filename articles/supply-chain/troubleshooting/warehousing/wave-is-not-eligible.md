---
title: Ciclo non è idoneo per la pulizia
description: Ciclo non è idoneo per la pulizia
author: perlynne
ms.date: 04/15/2021
ms.topic: troubleshooting
ms.search.form: WHSWaveTable_WHSWaveProcessingDataCleanup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-05-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 3e5142cf40a6c0d308e8e952bbe17e85b498826d
ms.sourcegitcommit: 5f5afb46431e1abd8fb6e92e0189914b598dc7fd
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2021
ms.locfileid: "5924329"
---
# <a name="wave-isnt-eligible-for-cleanup"></a><span data-ttu-id="537d3-103">Ciclo non è idoneo per la pulizia</span><span class="sxs-lookup"><span data-stu-id="537d3-103">Wave isn't eligible for cleanup</span></span>

<span data-ttu-id="537d3-104">Codice di errore: WaveNotEligibleForCleanup</span><span class="sxs-lookup"><span data-stu-id="537d3-104">Error code: WaveNotEligibleForCleanup</span></span>

## <a name="symptoms"></a><span data-ttu-id="537d3-105">Sintomi</span><span class="sxs-lookup"><span data-stu-id="537d3-105">Symptoms</span></span>

<span data-ttu-id="537d3-106">Il sistema mostra il seguente messaggio di errore:</span><span class="sxs-lookup"><span data-stu-id="537d3-106">The system shows the following error message:</span></span>

> <span data-ttu-id="537d3-107">L'ondata %1 non è idonea per la pulizia.</span><span class="sxs-lookup"><span data-stu-id="537d3-107">Wave %1 is not eligible for cleanup.</span></span>

<span data-ttu-id="537d3-108">I dati del ciclo non possono essere puliti.</span><span class="sxs-lookup"><span data-stu-id="537d3-108">The wave data can't be cleaned up.</span></span>  

## <a name="cause"></a><span data-ttu-id="537d3-109">Causa</span><span class="sxs-lookup"><span data-stu-id="537d3-109">Cause</span></span>

<span data-ttu-id="537d3-110">Il ciclo è attualmente in fase di elaborazione, come indicato da una delle seguenti condizioni:</span><span class="sxs-lookup"><span data-stu-id="537d3-110">The wave is currently being processed, as indicated by one of the following conditions:</span></span>

- <span data-ttu-id="537d3-111">Il campo **Stato ciclo** è impostato su *Esecuzione*.</span><span class="sxs-lookup"><span data-stu-id="537d3-111">The **Wave status** field is set to *Executing*.</span></span>
- <span data-ttu-id="537d3-112">Quando selezioni **Processo batch** nel gruppo **Ciclo** della scheda **Ciclo** nel riquadro azioni, il campo **Stato** non è impostato su *Finito*, *Errore*, o *Annullato*.</span><span class="sxs-lookup"><span data-stu-id="537d3-112">When you select **Batch job** in the **Wave** group on the **Wave** tab of the Action Pane, the **Status** field isn't set to *Ended*, *Error*, or *Canceled*.</span></span> <span data-ttu-id="537d3-113">Pertanto, un processo batch è attualmente in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="537d3-113">Therefore, a batch job is currently running.</span></span>

## <a name="resolution"></a><span data-ttu-id="537d3-114">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="537d3-114">Resolution</span></span>

<span data-ttu-id="537d3-115">Nel riquadro azioni, nella scheda **Ciclo**, nel gruppo **Ciclo**, selezionare **Processo batch**, quindi seguire uno di questi passaggi:</span><span class="sxs-lookup"><span data-stu-id="537d3-115">On the Action Pane, on the **Wave** tab, in the **Wave** group, select **Batch job**, and then follow one of these steps:</span></span>

- <span data-ttu-id="537d3-116">Se il campo **Stato** è impostato su *Esecuzione*: Nel riquadro azioni, nella scheda **Processo batch** nel gruppo **Processo batch**, seleziona **Visualizza attività**.</span><span class="sxs-lookup"><span data-stu-id="537d3-116">If the **Status** field is set to *Executing*: On the Action Pane, on the **Batch job** tab, in the **Batch job** group, select **View tasks**.</span></span> <span data-ttu-id="537d3-117">È possibile monitorare lo stato aggiornano la pagina **Attività batch**.</span><span class="sxs-lookup"><span data-stu-id="537d3-117">You can follow the progress by refreshing the **Batch tasks** page.</span></span>
- <span data-ttu-id="537d3-118">Se il campo **Stato** non è impostato su *Esecuzione*: Nel riquadro azioni, nella scheda **Processo batch** nel gruppo **Funzioni**, seleziona **Cambia stato**.</span><span class="sxs-lookup"><span data-stu-id="537d3-118">If the **Status** field isn't set to *Executing*: On the Action Pane, on the **Batch job** tab, in the **Functions** group, select **Change status**.</span></span> <span data-ttu-id="537d3-119">Nel campo **Seleziona nuovo stato** selezionare *In attesa*.</span><span class="sxs-lookup"><span data-stu-id="537d3-119">In the **Select new status** field, select *Waiting*.</span></span> <span data-ttu-id="537d3-120">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="537d3-120">Then select **OK**.</span></span>
