---
title: Creazione di ordini di lavoro
description: Nell'argomento viene descritto come creare ordini di lavoro in Gestione cespiti.
author: josaw1
manager: AnnBe
ms.date: 08/27/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 6e910b2400106baf9f9dc06f6bc0d3daee8e4a43
ms.sourcegitcommit: d37fb09101c30858bcb975931b3d8f947d72017b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/10/2019
ms.locfileid: "2570078"
---
# <a name="creating-work-orders"></a><span data-ttu-id="93cf9-103">Creazione di ordini di lavoro</span><span class="sxs-lookup"><span data-stu-id="93cf9-103">Creating work orders</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="93cf9-104">Dopo aver programmato processi di manutenzione preventiva, necessario creare ordini di lavoro per i processi.</span><span class="sxs-lookup"><span data-stu-id="93cf9-104">When you have scheduled preventive maintenance jobs, next step is to create work orders for the jobs.</span></span> <span data-ttu-id="93cf9-105">Questa operazione viene eseguita in una dei programmi di manutenzione.</span><span class="sxs-lookup"><span data-stu-id="93cf9-105">This is done in one of the maintenance schedules.</span></span> <span data-ttu-id="93cf9-106">I processi programmati in un programma di manutenzione possono avere diversi tipi di riferimenti:</span><span class="sxs-lookup"><span data-stu-id="93cf9-106">The scheduled jobs in a maintenance schedule can have different reference types:</span></span>

| <span data-ttu-id="93cf9-107">Tipo di riferimento</span><span class="sxs-lookup"><span data-stu-id="93cf9-107">Reference type</span></span> | <span data-ttu-id="93cf9-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="93cf9-108">Description</span></span>                    |
|-----------------------|------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="93cf9-109">Piani di manutenzione</span><span class="sxs-lookup"><span data-stu-id="93cf9-109">Maintenance plans</span></span>     | <span data-ttu-id="93cf9-110">Processi di manutenzione preventiva basati su tipi di piani di manutenzione "Tempo" o "Contatore".</span><span class="sxs-lookup"><span data-stu-id="93cf9-110">Preventive maintenance jobs based on maintenance plan types "Time" or "Counter".</span></span>                       |
| <span data-ttu-id="93cf9-111">Cicli di manutenzione</span><span class="sxs-lookup"><span data-stu-id="93cf9-111">Maintenance rounds</span></span>    | <span data-ttu-id="93cf9-112">Processi di manutenzione preventiva contenenti vari cespiti che richiedono un tipo di manutenzione simile.</span><span class="sxs-lookup"><span data-stu-id="93cf9-112">Preventive maintenance jobs containing several assets that require a similar type of maintenance.</span></span>           |
| <span data-ttu-id="93cf9-113">Richiesta di intervento di manutenzione</span><span class="sxs-lookup"><span data-stu-id="93cf9-113">Maintenance request</span></span>   | <span data-ttu-id="93cf9-114">Richiesta creata manualmente di manutenzione o riparazione di un cespite, che può essere convertita in un ordine di lavoro.</span><span class="sxs-lookup"><span data-stu-id="93cf9-114">Manually created request for maintenance or repair of an asset, which can be converted into a work order.</span></span> |


1. <span data-ttu-id="93cf9-115">Fare clic su **Gestione cespiti** > **Comune** > **Tutti i programmi di manutenzione** o **Apri righe di programma di manutenzione** o **Apri pool di programmi di manutenzione**.</span><span class="sxs-lookup"><span data-stu-id="93cf9-115">Click **Asset management** > **Common** > **All maintenance schedule** or **Open maintenance schedule lines** or **Open maintenance schedule pools**.</span></span>

2. <span data-ttu-id="93cf9-116">Selezionare processi di manutenzione programmati per i quali si desidera creare un ordine di lavoro e fare clic su **Ordine di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="93cf9-116">Select the scheduled maintenance jobs for which you want to create a work order and click **Work order**.</span></span> <span data-ttu-id="93cf9-117">Nella finestra di dialogo **Creare ordini di lavoro**, il numero totale di ore previste per le righe selezionate viene visualizzato nel campo **Ore previste manutenzione**.</span><span class="sxs-lookup"><span data-stu-id="93cf9-117">In the **Create work orders** dialog, the total number of forecast hours for the selected lines is shown in the **Maintenance forecast hours** field.</span></span>

3. <span data-ttu-id="93cf9-118">Nella sezione **Parametri**, selezionare il numero di ordini di lavoro che devono essere creati.</span><span class="sxs-lookup"><span data-stu-id="93cf9-118">In the **Parameters** section, select how many work orders should be created.</span></span> <span data-ttu-id="93cf9-119">È possibile creare un ordine di lavoro per riga di programma di manutenzione, o un numero di ordini di lavoro in base alle selezioni nella sezione **Un ordine di lavoro per**.</span><span class="sxs-lookup"><span data-stu-id="93cf9-119">You can create one work order per maintenance schedule line, or a number of work orders based on your selections in the **One work order per** section.</span></span>

4. <span data-ttu-id="93cf9-120">Selezionare un **tipo di ordine di lavoro** che verrà utilizzato negli ordini di lavoro creati.</span><span class="sxs-lookup"><span data-stu-id="93cf9-120">Select a **Work order type** that will be used on all the work orders you create.</span></span> <span data-ttu-id="93cf9-121">Nella figura seguente è illustrato un esempio della finestra di dialogo **Creare ordini di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="93cf9-121">The illustration below shows an example of the **Create work orders** dialog.</span></span>

![Figura 1](media/18-preventive-maintenance.png)

5. <span data-ttu-id="93cf9-123">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="93cf9-123">Click **OK**.</span></span> <span data-ttu-id="93cf9-124">Vengono creati uno o più ordini di lavoro.</span><span class="sxs-lookup"><span data-stu-id="93cf9-124">One or more work orders are created.</span></span>

