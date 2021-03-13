---
title: Tipi di ordine di lavoro
description: In questo argomento vengono descritti i tipi di ordine di lavoro in Gestione cespiti.
author: josaw1
manager: tfehr
ms.date: 08/13/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetWorkOrderType
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 9111ffa552059883696cf8248a02dfe70bc12ee7
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/16/2021
ms.locfileid: "5021531"
---
# <a name="work-order-types"></a><span data-ttu-id="2a9a9-103">Tipi di ordine di lavoro</span><span class="sxs-lookup"><span data-stu-id="2a9a9-103">Work order types</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="2a9a9-104">I tipi di ordine di lavoro sono utilizzati per classificare gli ordini di lavoro.</span><span class="sxs-lookup"><span data-stu-id="2a9a9-104">Work order types are used to categorize work orders.</span></span> <span data-ttu-id="2a9a9-105">Ad esempio, potrebbero esserci ordini di lavoro correlati alla manutenzione preventiva o alla manutenzione correttiva.</span><span class="sxs-lookup"><span data-stu-id="2a9a9-105">For example, you might have work orders that are related to preventive maintenance or corrective maintenance.</span></span>

<span data-ttu-id="2a9a9-106">Un tipo di ordine di lavoro definisce un rapporto con un modello del ciclo di vita di ordine di lavoro.</span><span class="sxs-lookup"><span data-stu-id="2a9a9-106">A work order type defines an affiliation with a work order lifecycle model.</span></span> <span data-ttu-id="2a9a9-107">Un modello del ciclo di vita di ordine di lavoro definisce gli stati del ciclo di vita di ordine di lavoro che possono essere configurati in un ordine di lavoro</span><span class="sxs-lookup"><span data-stu-id="2a9a9-107">A work order lifecycle model defines the work order lifecycle states that can be set on a work order.</span></span> <span data-ttu-id="2a9a9-108">(esempi di stati del ciclo di vita di ordine di lavoro includono **Creato**, **In corso** e **Completato**).</span><span class="sxs-lookup"><span data-stu-id="2a9a9-108">(Examples of work order lifecycle states include **Created**, **In Process**, and **Finished**.)</span></span>

<span data-ttu-id="2a9a9-109">Per ulteriori informazioni sugli stati del ciclo di vita di ordine di lavoro e sulle fasi di progetto, vedere [Stati del ciclo di vita ordine di lavoro](work-order-lifecycle-states.md).</span><span class="sxs-lookup"><span data-stu-id="2a9a9-109">For more information about work order lifecycle states and project stages, see [Work order lifecycle states](work-order-lifecycle-states.md).</span></span>

1. <span data-ttu-id="2a9a9-110">Selezionare **Gestione cespiti** \> **Impostazione** \> **Ordini di lavoro** \> **Tipi di ordine di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="2a9a9-110">Select **Asset management** \> **Setup** \> **Work orders** \> **Work order types**.</span></span>
2. <span data-ttu-id="2a9a9-111">Selezionare **Nuovo** per creare un tipo di ordine di lavoro.</span><span class="sxs-lookup"><span data-stu-id="2a9a9-111">Select **New** to create a work order type.</span></span>
3. <span data-ttu-id="2a9a9-112">Nel campo **Tipo di ordine di lavoro**, immettere un ID per il tipo di ordine di lavoro.</span><span class="sxs-lookup"><span data-stu-id="2a9a9-112">In the **Work order type** field, enter an ID for the work order type.</span></span>
4. <span data-ttu-id="2a9a9-113">Nel campo **Nome** immettere un nome.</span><span class="sxs-lookup"><span data-stu-id="2a9a9-113">In the **Name** field, enter a name.</span></span>
5. <span data-ttu-id="2a9a9-114">Nel campo **Modello del ciclo di vita ordine di lavoro**, selezionare un modello del ciclo di vita.</span><span class="sxs-lookup"><span data-stu-id="2a9a9-114">In the **Work order lifecycle model** field, select a lifecycle model.</span></span>
5. <span data-ttu-id="2a9a9-115">Impostare l'opzione **Un addetto alla manutenzione** su **Sì** se tutti i processi di ordine di lavoro correlati a un ordine di lavoro di questo tipo devono essere programmati per lo stesso addetto alla manutenzione.</span><span class="sxs-lookup"><span data-stu-id="2a9a9-115">Set the **One maintenance worker** option to **Yes** if all work order jobs that are related to a work order of this type should be scheduled to the same maintenance worker.</span></span>
6. <span data-ttu-id="2a9a9-116">Nel campo **Tipo di costo**, selezionare **Correttivo**, **Preventivo** o **Investimento**, a seconda delle esigenze.</span><span class="sxs-lookup"><span data-stu-id="2a9a9-116">In the **Cost type** field, select **Corrective**, **Preventive**, or **Investment**, as appropriate.</span></span> <span data-ttu-id="2a9a9-117">Tutti i processi di ordine di lavoro in un ordine di lavoro devono avere lo stesso tipo di costo.</span><span class="sxs-lookup"><span data-stu-id="2a9a9-117">All work order jobs on a work order must have the same cost type.</span></span>
7. <span data-ttu-id="2a9a9-118">Nella sezione **Obbligatorio**, impostare le opzioni pertinenti su **Sì** per specificare quali informazioni correlate agli errori o ai tempi di fermo per la manutenzione sono aggiunte a un ordine di lavoro di questo tipo.</span><span class="sxs-lookup"><span data-stu-id="2a9a9-118">In the **Mandatory** section, set the relevant options to **Yes** to specify which fault-related or maintenance downtime–related information is added to a work order of this type.</span></span>

    > [!NOTE]
    > <span data-ttu-id="2a9a9-119">Le opzioni nella sezione **Obbligatorio** sono correlate alle opzioni nella Scheda dettaglio **Convalida** della pagina **Stati del ciclo di vita ordine di lavoro** (**Gestione cespiti** \> **Impostazione** \> **Ordini di lavoro** \> **Stati del ciclo di vita**).</span><span class="sxs-lookup"><span data-stu-id="2a9a9-119">The options in the **Mandatory** section are related to the options on the **Validate** FastTab of the **Work order lifecycle states** page (**Asset management** \> **Setup** \> **Work orders** \> **Lifecycle states**).</span></span>

8. <span data-ttu-id="2a9a9-120">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="2a9a9-120">Select **Save**.</span></span>

![Tipi di ordine di lavoro](media/16-setup-for-work-orders.png)
