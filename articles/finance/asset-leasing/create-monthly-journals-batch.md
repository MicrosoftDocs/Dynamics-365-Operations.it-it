---
title: Creare registrazioni prima nota mensili in un batch
description: Questo argomento spiega come creare registrazioni prima nota in un batch per aumentare l'efficienza quando vengono registrate le spese di leasing mensili.
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: Dialog
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: ca84e56569ea5ddbb4d5335d0944a6bd8a50a1b1
ms.sourcegitcommit: d18d9cdb175c9d42eafbed66352c24b2aa94258b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2021
ms.locfileid: "5881206"
---
# <a name="create-monthly-journal-entries-in-a-batch"></a><span data-ttu-id="accbb-103">Creare registrazioni prima nota mensili in un batch</span><span class="sxs-lookup"><span data-stu-id="accbb-103">Create monthly journal entries in a batch</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="accbb-104">Questo argomento spiega come creare registrazioni prima nota in un batch per aumentare l'efficienza quando vengono registrate le spese di leasing mensili.</span><span class="sxs-lookup"><span data-stu-id="accbb-104">This topic explains how to create journal entries in a batch to help increase efficiency when monthly lease expenses are recorded.</span></span> <span data-ttu-id="accbb-105">L'elaborazione batch può essere utilizzata per creare registrazioni prima nota da più scadenziari.</span><span class="sxs-lookup"><span data-stu-id="accbb-105">Batch processing can be used to create journal entries from multiple schedules.</span></span> <span data-ttu-id="accbb-106">Queste registrazioni prima nota possono includere canoni di leasing, ammortamento delle passività, ammortamento degli Asset ROU e spese per i costi esecutivi.</span><span class="sxs-lookup"><span data-stu-id="accbb-106">These journal entries can include lease payments, liability amortization, right-of-use (ROU) asset amortization, and executory cost expenses.</span></span> <span data-ttu-id="accbb-107">È inoltre possibile utilizzare l'elaborazione batch per eseguire il riconoscimento iniziale di più leasing contemporaneamente o per creare rettifiche di transizione per più leasing contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="accbb-107">You can also use batch processing to do the initial recognition of multiple leases at the same time, or to create transition adjustments for multiple leases at the same time.</span></span>

<span data-ttu-id="accbb-108">Per configurare un processo batch o per elaborare fatture di pagamento, ammortamenti o interessi per più leasing, vai a **Leasing cespite \> Periodico \> Creazione di un giornale in batch**.</span><span class="sxs-lookup"><span data-stu-id="accbb-108">To set up a batch job, or to process payment invoices, depreciation, or interest for multiple leases, go to **Asset leasing \> Periodic \> Batch journal creation**.</span></span> <span data-ttu-id="accbb-109">Nella finestra di dialogo visualizzata, puoi selezionare lo scadenziario da cui creare le scritture contabili.</span><span class="sxs-lookup"><span data-stu-id="accbb-109">In the dialog box that appears, you can select the schedule that the journal entries should be created from.</span></span> <span data-ttu-id="accbb-110">Puoi inoltre specificare se il processo batch deve essere eseguito per entità, gruppi di leasing o libri di leasing specifici.</span><span class="sxs-lookup"><span data-stu-id="accbb-110">You can also specify whether the batch process should be run for specific entities, lease groups, or lease books.</span></span>

> [!NOTE]
> <span data-ttu-id="accbb-111">Le transazioni successive, come piani di ammortamento delle passività, pagamenti, ammortamenti e spese, verranno contabilizzati solo dopo la registrazione iniziale per i leasing corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="accbb-111">Subsequent transactions, such as liability amortization schedules, payments, depreciation, and expenses, will be posted only after the initial recognition for corresponding leases is posted.</span></span>
>
> <span data-ttu-id="accbb-112">Le scritture contabili vengono create, ma non verranno registrate finché non selezioni il comando **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="accbb-112">The journal entries are created, but they won't be posted until you select the **Run** command.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
