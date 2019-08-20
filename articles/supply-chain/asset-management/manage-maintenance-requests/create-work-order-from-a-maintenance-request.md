---
title: Creare ordini di lavoro delle richieste di intervento di manutenzione
description: In questo argomento viene illustrato come creare un ordine di lavoro da una richiesta di intervento di manutenzione in Gestione cespiti.
author: josaw1
manager: AnnBe
ms.date: 10/01/2019
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
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 3f7af87f359cfe3a606c8be857dd905bfef75e97
ms.sourcegitcommit: 871b76f8808a48d282f151144829323258ffc912
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/02/2019
ms.locfileid: "1847461"
---
# <a name="create-work-orders-from-maintenance-requests"></a><span data-ttu-id="88e5f-103">Creare ordini di lavoro delle richieste di intervento di manutenzione</span><span class="sxs-lookup"><span data-stu-id="88e5f-103">Create work orders from maintenance requests</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]


<span data-ttu-id="88e5f-104">Dopo aver creato le richieste di intervento di manutenzione, è possibile convertirli facilmente in ordini di lavoro.</span><span class="sxs-lookup"><span data-stu-id="88e5f-104">After you've created maintenance requests, you can easily convert them to work orders.</span></span> <span data-ttu-id="88e5f-105">In questo argomento viene descritto il modo più veloce di lavorare con le richieste di intervento di manutenzione, aggiornare più richieste di intervento di manutenzione contemporaneamente e creare un ordine di lavoro per più richieste di intervento di manutenzione contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="88e5f-105">This topic describes the quickest way to work with maintenance requests, update several maintenance requests at the same time, and then create a work order for several maintenance requests at the same time.</span></span> <span data-ttu-id="88e5f-106">Nella pagina **Richieste di intervento di manutenzione attive** o **Richieste di intervento di manutenzione delle unità funzionali personali**, è possibile anche utilizzare una richiesta di intervento di manutenzione alla volta e convertire una richiesta di intervento di manutenzione in un ordine di lavoro.</span><span class="sxs-lookup"><span data-stu-id="88e5f-106">On the **Active maintenance requests** or **My functional location maintenance requests** page, you can also work with one maintenance request at a time and convert one maintenance request to a work order.</span></span>

> [!NOTE]
> <span data-ttu-id="88e5f-107">Ogni richiesta di intervento di manutenzione può essere correlata a un solo ordine di lavoro.</span><span class="sxs-lookup"><span data-stu-id="88e5f-107">Every maintenance request can be related to only one work order.</span></span> <span data-ttu-id="88e5f-108">Tuttavia, più richieste di intervento di manutenzione possono essere incluse in un ordine di lavoro, anche se le richieste di intervento di manutenzione hanno cespiti diversi.</span><span class="sxs-lookup"><span data-stu-id="88e5f-108">However, multiple maintenance requests can be included in one work order, even if the maintenance requests have different assets.</span></span>

1. <span data-ttu-id="88e5f-109">Selezionare **Gestione cespiti** \> **Comune** \> **Richieste di intervento di manutenzione** \> **Tutte le richieste di intervento di manutenzione**.</span><span class="sxs-lookup"><span data-stu-id="88e5f-109">Select **Asset management** \> **Common** \> **maintenance requests** \> **All maintenance requests**.</span></span>
2. <span data-ttu-id="88e5f-110">Prima di creare un ordine di lavoro delle richieste di intervento di manutenzione, è necessario selezionare, al minimo, il tipo di processo di manutenzione per le richieste di intervento di manutenzione nonché una variante e una mansione qualificata per il tipo di processo di manutenzione, se queste informazioni sono rilevanti.</span><span class="sxs-lookup"><span data-stu-id="88e5f-110">Before you can create a work order from maintenance requests, you must select, at a minimum, a maintenance job type for the maintenance requests, and also a maintenance job type variant and trade, if this information is relevant.</span></span> <span data-ttu-id="88e5f-111">Nella visualizzazione griglia, è possibile aggiornare facilmente le informazioni relative a una richiesta di intervento di manutenzione.</span><span class="sxs-lookup"><span data-stu-id="88e5f-111">In the grid view, you can easily update information for a maintenance request.</span></span>
3. <span data-ttu-id="88e5f-112">Quando si è pronti a creare un ordine di lavoro, selezionare le richieste intervento di manutenzione da includere.</span><span class="sxs-lookup"><span data-stu-id="88e5f-112">When you're ready to create a work order, select the maintenance requests to include in it.</span></span>

    - <span data-ttu-id="88e5f-113">Se si selezionano più richieste di intervento di manutenzione da convertire in ordine di lavoro, il campo **Cespite** e il campo **Tipo di processo di manutenzione** devono essere impostati prima di creare l'ordine di lavoro.</span><span class="sxs-lookup"><span data-stu-id="88e5f-113">If you select several maintenance requests to convert to a work order, both the **Asset** field and the **Maintenance job type** field must be set before you create the work order.</span></span>
    - <span data-ttu-id="88e5f-114">Se si seleziona una sola richiesta di intervento di manutenzione da convertire in ordine di lavoro, solo il campo **Cespite** deve essere impostato prima di creare l'ordine di lavoro.</span><span class="sxs-lookup"><span data-stu-id="88e5f-114">If you select one maintenance request to convert to a work order, only the **Asset** field must be set before you create the work order.</span></span> <span data-ttu-id="88e5f-115">Tuttavia, quando si crea l'ordine di lavoro, è possibile selezionare un tipo di processo di manutenzione (e una variante e una mansione qualificata per il tipo di processo di manutenzione correlati, se queste informazioni sono pertinenti) nella finestra di dialogo **Crea ordine di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="88e5f-115">However, when you create the work order, you can select a maintenance job type (and a related maintenance job type variant and trade, if this information is relevant) in the **Create work order** dialog box.</span></span>

4. <span data-ttu-id="88e5f-116">Selezionare **Ordine di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="88e5f-116">Select **Work order**.</span></span>
5. <span data-ttu-id="88e5f-117">Nella finestra  dialogo **Crea ordine di lavoro**, impostare i campi e quindi selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="88e5f-117">In the **Create work order** dialog box, set the fields, and then select **OK**.</span></span>

    <span data-ttu-id="88e5f-118">La barra dei messaggi può indicare che un nuovo ordine di lavoro è stato creato.</span><span class="sxs-lookup"><span data-stu-id="88e5f-118">A message bar might notify you that a new work order has been created.</span></span>

    <span data-ttu-id="88e5f-119">Inoltre, quando si crea un ordine di lavoro basato su una richiesta di intervento di manutenzione, se il cespite correlato alla richiesta di intervento di manutenzione è incluso in un contratto di garanzia, una barra dei messaggi informa del contratto di garanzia.</span><span class="sxs-lookup"><span data-stu-id="88e5f-119">Additionally, when you create a work order that is based on a maintenance request, if the asset that is related to the maintenance request is included in a warranty agreement, a message bar notifies you about the warranty agreement.</span></span>

6. <span data-ttu-id="88e5f-120">Selezionare **Gestione cespiti** \> **Comune** \> **Ordini di lavoro** \> **Tutti gli ordini di lavoro** e aprire il nuovo ordine di lavoro.</span><span class="sxs-lookup"><span data-stu-id="88e5f-120">Select **Asset management** \> **Common** \> **Work orders** \> **All work orders**, and open the new work order.</span></span>

    ![Figura 1](media/05-manage-maintenance-requests.png)
