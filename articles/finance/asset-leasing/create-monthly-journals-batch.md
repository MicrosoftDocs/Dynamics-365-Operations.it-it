---
title: Creare registrazioni prima nota mensili in un batch
description: Questo argomento spiega come creare registrazioni prima nota in un batch per aumentare l'efficienza quando vengono registrate le spese di leasing mensili.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 7f46f289c58c32c535dd20fb510cf2812625c49c
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4971330"
---
# <a name="create-monthly-journal-entries-in-a-batch"></a><span data-ttu-id="5af3b-103">Creare registrazioni prima nota mensili in un batch</span><span class="sxs-lookup"><span data-stu-id="5af3b-103">Create monthly journal entries in a batch</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5af3b-104">Questo argomento spiega come creare registrazioni prima nota in un batch per aumentare l'efficienza quando vengono registrate le spese di leasing mensili.</span><span class="sxs-lookup"><span data-stu-id="5af3b-104">This topic explains how to create journal entries in a batch to help increase efficiency when monthly lease expenses are recorded.</span></span> <span data-ttu-id="5af3b-105">L'elaborazione batch può essere utilizzata per creare registrazioni prima nota da più scadenziari.</span><span class="sxs-lookup"><span data-stu-id="5af3b-105">Batch processing can be used to create journal entries from multiple schedules.</span></span> <span data-ttu-id="5af3b-106">Queste registrazioni prima nota possono includere canoni di leasing, ammortamento delle passività, ammortamento degli Asset ROU e spese per i costi esecutivi.</span><span class="sxs-lookup"><span data-stu-id="5af3b-106">These journal entries can include lease payments, liability amortization, right-of-use (ROU) asset amortization, and executory cost expenses.</span></span> <span data-ttu-id="5af3b-107">È inoltre possibile utilizzare l'elaborazione batch per eseguire il riconoscimento iniziale di più leasing contemporaneamente o per creare rettifiche di transizione per più leasing contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="5af3b-107">You can also use batch processing to do the initial recognition of multiple leases at the same time, or to create transition adjustments for multiple leases at the same time.</span></span>

<span data-ttu-id="5af3b-108">Per configurare un processo batch o per elaborare fatture di pagamento, ammortamenti o interessi per più leasing, vai a **Leasing cespite \> Periodico \> Creazione di un giornale in batch**.</span><span class="sxs-lookup"><span data-stu-id="5af3b-108">To set up a batch job, or to process payment invoices, depreciation, or interest for multiple leases, go to **Asset leasing \> Periodic \> Batch journal creation**.</span></span> <span data-ttu-id="5af3b-109">Nella finestra di dialogo visualizzata, puoi selezionare lo scadenziario da cui creare le scritture contabili.</span><span class="sxs-lookup"><span data-stu-id="5af3b-109">In the dialog box that appears, you can select the schedule that the journal entries should be created from.</span></span> <span data-ttu-id="5af3b-110">Puoi inoltre specificare se il processo batch deve essere eseguito per entità, gruppi di leasing o libri di leasing specifici.</span><span class="sxs-lookup"><span data-stu-id="5af3b-110">You can also specify whether the batch process should be run for specific entities, lease groups, or lease books.</span></span>

> [!NOTE]
> <span data-ttu-id="5af3b-111">Le transazioni successive, come piani di ammortamento delle passività, pagamenti, ammortamenti e spese, verranno contabilizzati solo dopo la registrazione iniziale per i leasing corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="5af3b-111">Subsequent transactions, such as liability amortization schedules, payments, depreciation, and expenses, will be posted only after the initial recognition for corresponding leases is posted.</span></span>
>
> <span data-ttu-id="5af3b-112">Le scritture contabili vengono create, ma non verranno registrate finché non selezioni il comando **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="5af3b-112">The journal entries are created, but they won't be posted until you select the **Run** command.</span></span>
