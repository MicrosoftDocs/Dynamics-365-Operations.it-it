---
title: Tipi di diagnostica per non conformità
description: Questo argomento descrive come utilizzare e creare tipi di diagnostica che possono essere utilizzati con non conformità.
author: rachel-profitt
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventTestDiagnosticType, InventTestCorrection
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: raprofit
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b7a5c593f1d9e8f7a77f693f6e652e9355a985fb
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2021
ms.locfileid: "6022278"
---
# <a name="diagnostic-types-for-nonconformances"></a><span data-ttu-id="dbf83-103">Tipi di diagnostica per non conformità</span><span class="sxs-lookup"><span data-stu-id="dbf83-103">Diagnostic types for nonconformances</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="dbf83-104">Questo argomento descrive come utilizzare e creare tipi di diagnostica che possono essere utilizzati con non conformità.</span><span class="sxs-lookup"><span data-stu-id="dbf83-104">This topic describes how to use and create diagnostic types that can be used with nonconformances.</span></span>

<span data-ttu-id="dbf83-105">Utilizzare la pagina **Tipi di diagnostica** per definire una classificazione delle azioni di diagnostica.</span><span class="sxs-lookup"><span data-stu-id="dbf83-105">You use the **Diagnostic types** page to define a classification of diagnostic actions.</span></span> <span data-ttu-id="dbf83-106">Quindi, quando si crea una correzione per una non conformità, si seleziona una diagnostica.</span><span class="sxs-lookup"><span data-stu-id="dbf83-106">Then, when you create a correction for a nonconformance, you select a diagnostic.</span></span> <span data-ttu-id="dbf83-107">Una correzione specifica il tipo di azione di diagnostica da eseguire per una non conformità approvata e l'utente che deve eseguire l'azione.</span><span class="sxs-lookup"><span data-stu-id="dbf83-107">A correction specifies what type of diagnostic action should be taken for an approved nonconformance, and who should take that action.</span></span> <span data-ttu-id="dbf83-108">Specifica inoltre la data di completamento richiesta e la data di completamento pianificata.</span><span class="sxs-lookup"><span data-stu-id="dbf83-108">It also specifies the requested completion date and the planned completion date.</span></span>

## <a name="examples-of-diagnostic-types"></a><span data-ttu-id="dbf83-109">Esempi di tipi di diagnostica</span><span class="sxs-lookup"><span data-stu-id="dbf83-109">Examples of diagnostic types</span></span>

<span data-ttu-id="dbf83-110">Lavori per un'azienda di produzione e diversi articoli non hanno superato i test di controllo qualità.</span><span class="sxs-lookup"><span data-stu-id="dbf83-110">You work for a manufacturing company, and several items have failed quality tests.</span></span> <span data-ttu-id="dbf83-111">Tali articoli vengono spostati in un'area di quarantena e contrassegnati come prodotti non conformi.</span><span class="sxs-lookup"><span data-stu-id="dbf83-111">Those items are moved into a quarantine area and marked as nonconforming products.</span></span> <span data-ttu-id="dbf83-112">Un record di non conformità viene creato in Microsoft Dynamics 365 Supply Chain Management per tenere traccia dei dettagli attraverso la risoluzione dei problemi.</span><span class="sxs-lookup"><span data-stu-id="dbf83-112">A nonconformance record is created in Microsoft Dynamics 365 Supply Chain Management to track the details through issue resolution.</span></span>

<span data-ttu-id="dbf83-113">In questo caso, i problemi di qualità si verificano perché i cuscinetti della macchina che imballa gli articoli si sono deteriorati e si stanno surriscaldando.</span><span class="sxs-lookup"><span data-stu-id="dbf83-113">In this case, the quality issues are occurring because bearings in the machine that packages the items have gone bad and are overheating.</span></span> <span data-ttu-id="dbf83-114">La correzione per questo problema è sostituire le parti nella macchina.</span><span class="sxs-lookup"><span data-stu-id="dbf83-114">The correction for this problem is to replace the parts in the machine.</span></span>

<span data-ttu-id="dbf83-115">Quando si configurano i tipi di diagnostica, è possibile creare più record, ognuno dei quali rappresenta un diverso tipo di problema che la macchina potrebbe avere.</span><span class="sxs-lookup"><span data-stu-id="dbf83-115">When you configure the diagnostic types, you can create multiple records, each of which represents a different type of problem that the machine might have.</span></span> <span data-ttu-id="dbf83-116">In alternativa, è possibile creare un tipo di diagnostica generico che rappresenta la riparazione della macchina.</span><span class="sxs-lookup"><span data-stu-id="dbf83-116">Alternatively, you can create one generic diagnostic type that represents machine repair.</span></span>

## <a name="create-a-diagnostic-type"></a><span data-ttu-id="dbf83-117">Creare un tipo di diagnostica</span><span class="sxs-lookup"><span data-stu-id="dbf83-117">Create a diagnostic type</span></span>

1. <span data-ttu-id="dbf83-118">Andare a **Gestione articoli \> Impostazioni \> Gestione qualità \> Tipi di diagnostica**.</span><span class="sxs-lookup"><span data-stu-id="dbf83-118">Go to **Inventory management \> Setup \> Quality management \> Diagnostic types**.</span></span>
1. <span data-ttu-id="dbf83-119">Nel riquadro azioni seleziona **Nuova** per aggiungere una riga alla griglia.</span><span class="sxs-lookup"><span data-stu-id="dbf83-119">On the Action Pane, select **New** to add a row to the grid.</span></span> <span data-ttu-id="dbf83-120">Quindi imposta i seguenti campi per la nuova riga:</span><span class="sxs-lookup"><span data-stu-id="dbf83-120">Then set the following fields for the new row:</span></span>

    - <span data-ttu-id="dbf83-121">**Diagnostica** - Immettere un ID o un nome univoco per il tipo di diagnostica.</span><span class="sxs-lookup"><span data-stu-id="dbf83-121">**Diagnostic** – Enter a unique ID or name for the diagnostic type.</span></span>
    - <span data-ttu-id="dbf83-122">**Descrizione** - Immettere una descrizione dettagliata del tipo di diagnostica.</span><span class="sxs-lookup"><span data-stu-id="dbf83-122">**Description** – Enter a detailed description of the diagnostic type.</span></span>

1. <span data-ttu-id="dbf83-123">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="dbf83-123">Close the page.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="dbf83-124">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="dbf83-124">Additional resources</span></span>

- [<span data-ttu-id="dbf83-125">Panoramica gestione qualità</span><span class="sxs-lookup"><span data-stu-id="dbf83-125">Quality management overview</span></span>](quality-management-processes.md)
- [<span data-ttu-id="dbf83-126">Abilitare la gestione della qualità e della non conformità</span><span class="sxs-lookup"><span data-stu-id="dbf83-126">Enable quality and nonconformance management</span></span>](enable-quality-management.md)
- [<span data-ttu-id="dbf83-127">Lavoratori responsabili dell'approvazione delle non conformità</span><span class="sxs-lookup"><span data-stu-id="dbf83-127">Workers responsible for approving nonconformances</span></span>](quality-responsible-workers.md)
- [<span data-ttu-id="dbf83-128">Aree di quarantena per non conformità</span><span class="sxs-lookup"><span data-stu-id="dbf83-128">Quarantine zones for nonconformances</span></span>](quality-quarantine-zones.md)
- [<span data-ttu-id="dbf83-129">Tipi di problemi per non conformità</span><span class="sxs-lookup"><span data-stu-id="dbf83-129">Problem types for nonconformances</span></span>](quality-problem-types.md)
- [<span data-ttu-id="dbf83-130">Spese di gestione qualità per non conformità</span><span class="sxs-lookup"><span data-stu-id="dbf83-130">Quality charges for nonconformances</span></span>](quality-charges.md)
- [<span data-ttu-id="dbf83-131">Operazioni per non conformità</span><span class="sxs-lookup"><span data-stu-id="dbf83-131">Operations for nonconformances</span></span>](quality-operations.md)
- [<span data-ttu-id="dbf83-132">Gestione qualità per i processi di magazzino</span><span class="sxs-lookup"><span data-stu-id="dbf83-132">Quality management for warehouse processes</span></span>](quality-management-for-warehouses-processes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
