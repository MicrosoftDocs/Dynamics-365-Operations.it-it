---
title: Reimpostare i processi batch bloccati
description: Questo argomento spiega come risolvere i problemi con processi batch bloccati.
author: andreabichsel
ms.date: 03/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2021-03-19
ms.dyn365.ops.version: Platform update 42
ms.openlocfilehash: d0b12908993070a41d21ac57d6fb504fc6e3b06a
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/18/2021
ms.locfileid: "6053517"
---
# <a name="reset-stuck-batch-jobs"></a><span data-ttu-id="8ab91-103">Reimpostare i processi batch bloccati</span><span class="sxs-lookup"><span data-stu-id="8ab91-103">Reset stuck batch jobs</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

## <a name="issue"></a><span data-ttu-id="8ab91-104">Uscita</span><span class="sxs-lookup"><span data-stu-id="8ab91-104">Issue</span></span>

<span data-ttu-id="8ab91-105">In Microsoft Dynamics 365 Human Resources possono verificarsi problemi con i processi batch bloccati in uno stato **In esecuzione** o **Annullamento** che non vengono completati.</span><span class="sxs-lookup"><span data-stu-id="8ab91-105">Microsoft Dynamics 365 Human Resources can experience issues with batch jobs that are stuck in either an **Executing** or **Canceling** state and don't complete.</span></span>

## <a name="resolution"></a><span data-ttu-id="8ab91-106">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="8ab91-106">Resolution</span></span>

<span data-ttu-id="8ab91-107">Quando un processo batch è bloccato in uno stato **In esecuzione** o **Annullamento** puoi reimpostare lo stato forzando l'annullamento del processo.</span><span class="sxs-lookup"><span data-stu-id="8ab91-107">When a batch job is stuck in an **Executing** or **Canceling** state, you can reset the status by forcing the cancellation of the job.</span></span> <span data-ttu-id="8ab91-108">Dopo averlo annullato, è possibile ripristinare il processo batch impostandolo su uno stato **In attesa**.</span><span class="sxs-lookup"><span data-stu-id="8ab91-108">After you cancel it, you can reset the batch job by setting it to a **Waiting** status.</span></span> <span data-ttu-id="8ab91-109">Verrà quindi nuovamente prelevato per l'esecuzione nella successiva esecuzione batch pianificata.</span><span class="sxs-lookup"><span data-stu-id="8ab91-109">It will then be picked up again for execution in the next scheduled batch run.</span></span>

1. <span data-ttu-id="8ab91-110">Nell'area di lavoro **Amministrazione di sistema** seleziona la pagina **Collegamenti** e seleziona **Processi batch**.</span><span class="sxs-lookup"><span data-stu-id="8ab91-110">In the **System administration** workspace, select the **Links** page, and select **Batch jobs**.</span></span>

2. <span data-ttu-id="8ab91-111">Nella pagina elenco **Processo batch** seleziona il processo che deve essere ripristinato.</span><span class="sxs-lookup"><span data-stu-id="8ab91-111">On the **Batch job** list page, select the job that needs to be reset.</span></span>

3. <span data-ttu-id="8ab91-112">Sulla barra multifunzione seleziona **Forza annullamento** e conferma l'azione.</span><span class="sxs-lookup"><span data-stu-id="8ab91-112">On the action ribbon, select **Force cancel**, and confirm the action.</span></span>

   > [!NOTE]
   > <span data-ttu-id="8ab91-113">L'azione **Forza annullamento** è disponibile solo quando il processo batch selezionato ha lo stato **In esecuzione** o **Annullamento** e nessun processo di esecuzione o annullamento batch è in esecuzione per il processo.</span><span class="sxs-lookup"><span data-stu-id="8ab91-113">The **Force cancel** action is only available when the selected batch job has a status of either **Executing** or **Canceling**, and no batch execution or cancellation processes are running for the job.</span></span>

4. <span data-ttu-id="8ab91-114">Nella barra multifunzione seleziona **Cambia stato**.</span><span class="sxs-lookup"><span data-stu-id="8ab91-114">On the action ribbon, select **Change status**.</span></span>

5. <span data-ttu-id="8ab91-115">Nella pagina **Seleziona nuovo stato** seleziona **In attesa** e quindi seleziona **OK**.</span><span class="sxs-lookup"><span data-stu-id="8ab91-115">On the **Select new status** page, select **Waiting**, and then select **OK**.</span></span>

   ![Selezionare un nuovo stato del processo batch](./media/hr-admin-reset-batch-job-status.png)

## <a name="see-also"></a><span data-ttu-id="8ab91-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8ab91-117">See also</span></span>

[<span data-ttu-id="8ab91-118">Ottimizzare le prestazioni programmando i processi batch dopo ore</span><span class="sxs-lookup"><span data-stu-id="8ab91-118">Optimize performance by scheduling batch jobs after hours</span></span>](hr-admin-troubleshooting-batch-jobs.md)<br>
[<span data-ttu-id="8ab91-119">Ottimizzare le prestazioni con attività di pulizia automatica</span><span class="sxs-lookup"><span data-stu-id="8ab91-119">Optimize performance with auto cleanup tasks</span></span>](hr-admin-troubleshooting-batch-history.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
