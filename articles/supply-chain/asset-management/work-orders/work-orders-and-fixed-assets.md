---
title: Cespiti e ordini di lavoro
description: In questo argomento vengono descritti gli ordini di lavoro e i cespiti in Gestione cespiti.
author: josaw1
manager: AnnBe
ms.date: 08/15/2019
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
ms.search.validFrom: 2019-08-15
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 95fe394d22f9fe81511c230a2cf7b8ddf00d896f
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/30/2019
ms.locfileid: "2250831"
---
# <a name="work-orders-and-fixed-assets"></a><span data-ttu-id="1dbed-103">Cespiti e ordini di lavoro</span><span class="sxs-lookup"><span data-stu-id="1dbed-103">Work orders and fixed assets</span></span>


[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]


<span data-ttu-id="1dbed-104">In Gestione cespiti, i cespiti possono essere associati a cespiti ed è possibile creare ordini di lavoro per tali cespiti.</span><span class="sxs-lookup"><span data-stu-id="1dbed-104">In Asset Management, assets can be related to fixed assets, and you can create work orders for those assets.</span></span> <span data-ttu-id="1dbed-105">Se si utilizza questa funzionalità, è possibile ottenere una panoramica completa dei cespiti, dei progetti di investimento correlati e dei costi registrati nei progetti di investimento nel modulo **Gestione progetti e contabilità** e nel modulo **Cespiti**.</span><span class="sxs-lookup"><span data-stu-id="1dbed-105">If you use this functionality, you can get a complete overview of fixed assets, related investment projects, and the costs registered on the investment projects in the **Project management and accounting** module and the **Fixed assets** module.</span></span>

>[!NOTE]
><span data-ttu-id="1dbed-106">Il campo **Numero cespite** viene compilato nel progetto di processo di ordine di lavoro solo se il tipo "Investimento" è selezionato come tipo di progetto nel progetto di processo di ordine di lavoro.</span><span class="sxs-lookup"><span data-stu-id="1dbed-106">The **Fixed asset number** field is only filled out on the work order job project if type "Investment" is selected as the project type on the work order job project.</span></span>

![Figura 1](media/24-work-orders.png)

<span data-ttu-id="1dbed-108">Nella seguente procedura viene descritta la relazione tra cespiti, ordini di lavoro, progetti di processo di ordine di lavoro e cespiti.</span><span class="sxs-lookup"><span data-stu-id="1dbed-108">The following procedure describes the relation between assets, work orders, work order job projects, and fixed assets.</span></span>

1. <span data-ttu-id="1dbed-109">Si crea un cespite e lo si associa a un cespite, come illustrato nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="1dbed-109">You create an asset that you relate to a fixed asset, as shown in the figure below.</span></span>

![Figura 2](media/25-work-orders.png)

2. <span data-ttu-id="1dbed-111">Quando si impostano tipi di ordine di lavoro (**Gestione risorse** > **Impostazione** > **Ordini di lavoro** > **Tipi di ordine di lavoro**), si crea un tipo di ordine di lavoro per la gestione degli investimenti.</span><span class="sxs-lookup"><span data-stu-id="1dbed-111">When you set up work order types (**Asset management** > **Setup** > **Work orders** > **Work order types**), you create a work order type for handling investments.</span></span> <span data-ttu-id="1dbed-112">Vedere anche [Tipi di ordine di lavoro](../setup-for-work-orders/work-order-types.md).</span><span class="sxs-lookup"><span data-stu-id="1dbed-112">See also [Work order types](../setup-for-work-orders/work-order-types.md).</span></span>

![Figura 3](media/26-work-orders.png)

3. <span data-ttu-id="1dbed-114">Quando si impostano gruppi di progetti di ordine di lavoro (collegamento **Gestione cespiti** > **Impostazione** > **Ordini di lavoro** > **Impostazione progetto** > **Gruppo di progetti** ), si crea una relazione tra il tipo di ordine di lavoro utilizzato per gli investimenti e il gruppo di progetti creato per gli investimenti nel modulo **Gestione progetti e contabilità** (**Gestione progetti e contabilità** > **Impostazione** > **Registrazione** > **Gruppi di progetti**).</span><span class="sxs-lookup"><span data-stu-id="1dbed-114">When you set up work order project groups (**Asset management** > **Setup** > **Work orders** > **Project setup** > **Project group** link), you create a relation between the work order type used for investments and the project group created for investments in the **Project management and accounting** module (**Project management and accounting** > **Setup** > **Posting** > **Project groups**).</span></span>

![Figura 4](media/27-work-orders.png)

4. <span data-ttu-id="1dbed-116">Quando si crea un ordine di lavoro associato a un oggetto cespiti, si seleziona il tipo di ordine di lavoro utilizzato per la gestione degli investimenti, ad esempio "Investimento".</span><span class="sxs-lookup"><span data-stu-id="1dbed-116">When you create a work order that relates to a fixed asset object, you select the work order type used for handling investments, for example, "Investment".</span></span>

5. <span data-ttu-id="1dbed-117">Quando viene creato l'ordine di lavoro, il tipo di ordine di lavoro associato viene visualizzato in **Tutti gli ordini di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="1dbed-117">When the work order is created, the related work order type is shown in **All work orders**.</span></span>

![Figura 5](media/28-work-orders.png)

6. <span data-ttu-id="1dbed-119">Quando l'ordine di lavoro viene creato, il progetto associato all'ordine di lavoro viene creato in **Gestione progetti e contabilità** > **Tutti i progetti**.</span><span class="sxs-lookup"><span data-stu-id="1dbed-119">When the work order is created, the project related to the work order is created in **Project management and accounting** > **All projects**.</span></span> <span data-ttu-id="1dbed-120">È possibile visualizzare le informazioni correlate al progetto facendo clic sul collegamento **ID progetto** (in **Gestione cespiti**, aprire l'ordine di lavoro nella visualizzazione Dettagli > Scheda dettaglio **Dettagli riga** > scheda **Generale** > campo **ID progetto**).</span><span class="sxs-lookup"><span data-stu-id="1dbed-120">You can see project-related information by clicking the **Project ID** link on the work order (in **Asset management**, open the work order in Details view > **Line details** FastTab > **General** tab > **Project ID** field).</span></span>

![Figura 6](media/29-work-orders.png)

7. <span data-ttu-id="1dbed-122">In **Cespiti**, è possibile visualizzare una panoramica dei progetti associati a un cespite (**Cespiti** > **Cespiti** > **Cespiti** > fare clic sul cespite nel campo **Numero cespite** > visualizzare i contenuti nel riquadro **Informazioni correlate** > sezione **Progetti associati**).</span><span class="sxs-lookup"><span data-stu-id="1dbed-122">In **Fixed assets**, you are able to see an overview of the projects associated with a fixed asset (**Fixed assets** > **Fixed assets** > **Fixed assets** > click on the fixed asset in the **Fixed asset number** field > view the contents in the **Related information** pane > **Associated projects** section).</span></span>

