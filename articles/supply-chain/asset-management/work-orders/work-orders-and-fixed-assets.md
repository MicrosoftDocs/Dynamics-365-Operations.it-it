---
title: Cespiti e ordini di lavoro
description: In questo argomento vengono descritti gli ordini di lavoro e i cespiti in Gestione cespiti.
author: johanhoffmann
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 65adcd07f1649b2e4eb2e2528507bb15631782ce
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5816726"
---
# <a name="work-orders-and-fixed-assets"></a><span data-ttu-id="e7249-103">Cespiti e ordini di lavoro</span><span class="sxs-lookup"><span data-stu-id="e7249-103">Work orders and fixed assets</span></span>

[!include [banner](../../includes/banner.md)]


<span data-ttu-id="e7249-104">In Gestione cespiti, i cespiti possono essere associati a cespiti ed è possibile creare ordini di lavoro per tali cespiti.</span><span class="sxs-lookup"><span data-stu-id="e7249-104">In Asset Management, assets can be related to fixed assets, and you can create work orders for those assets.</span></span> <span data-ttu-id="e7249-105">Se si utilizza questa funzionalità, è possibile ottenere una panoramica completa dei cespiti, dei progetti di investimento correlati e dei costi registrati nei progetti di investimento nei moduli **Gestione progetti e contabilità** e **Cespiti** in Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="e7249-105">If you use this functionality, you can get a complete overview of fixed assets, related investment projects, and the costs that are registered on the investment projects in the **Project management and accounting** and **Fixed assets** modules in Microsoft Dynamics 365 for Finance and Operations.</span></span>

>[!NOTE]
><span data-ttu-id="e7249-106">Il campo **Numero cespite** viene compilato nel progetto di processo di ordine di lavoro solo se il tipo **Investimento** è selezionato come tipo di progetto nel progetto di processo di ordine di lavoro.</span><span class="sxs-lookup"><span data-stu-id="e7249-106">The **Fixed asset number** field on the work order job project is set only if **Investment** is selected as the project type on the work order job project.</span></span>

<span data-ttu-id="e7249-107">L'illustrazione seguente mostra la relazione tra un progetto di investimento nel modulo **Gestione progetti e contabilità** e un progetto di processo ordine di lavoro.</span><span class="sxs-lookup"><span data-stu-id="e7249-107">The illustration below shows the relation between an investment project in the **Project management and accounting** module and a work order job project.</span></span>

![Figura 1](media/24-work-orders.png)

<span data-ttu-id="e7249-109">Nella seguente procedura viene descritta la relazione tra cespiti, ordini di lavoro, progetti di processo di ordine di lavoro e cespiti.</span><span class="sxs-lookup"><span data-stu-id="e7249-109">The following procedure describes the relation between assets, work orders, work order job projects, and fixed assets.</span></span>

1. <span data-ttu-id="e7249-110">Si crea un cespite che si collega a un cespite.</span><span class="sxs-lookup"><span data-stu-id="e7249-110">You create an asset that you relate to a fixed asset.</span></span>

![Figura 2](media/25-work-orders.png)

2. <span data-ttu-id="e7249-112">Quando si impostano tipi di ordine di lavoro nella pagina **Tipi di ordine di lavoro** (**Gestione risorse** > **Impostazione** > **Ordini di lavoro** > **Tipi di ordine di lavoro**), si crea un tipo di ordine di lavoro per la gestione degli investimenti.</span><span class="sxs-lookup"><span data-stu-id="e7249-112">When you set up work order types on the **Work order types** page (**Asset management** > **Setup** > **Work orders** > **Work order types**), you create a work order type for handling investments.</span></span> <span data-ttu-id="e7249-113">Vedere anche [Tipi di ordine di lavoro](../setup-for-work-orders/work-order-types.md).</span><span class="sxs-lookup"><span data-stu-id="e7249-113">See also [Work order types](../setup-for-work-orders/work-order-types.md).</span></span>

![Figura 3](media/26-work-orders.png)

3. <span data-ttu-id="e7249-115">Quando si impostano gruppi di progetti di ordine di lavoro nella scheda **Gruppo di progetti** della pagina **Impostazione del progetto dell'ordine di lavoro** (**Gestione cespiti** > **Impostazione** > **Ordini di lavoro** > **Impostazione progetto**), si crea una relazione tra il tipo di ordine di lavoro utilizzato per gli investimenti e il gruppo di progetti creato per gli investimenti nella pagina **Gruppi di progetti** page del modulo **Gestione progetti e contabilità** (**Gestione progetti e contabilità** > **Impostazione** > **Registrazione** > **Gruppi di progetti**).</span><span class="sxs-lookup"><span data-stu-id="e7249-115">When you set up work order project groups on the **Project group** tab of the **Work order project setup** page (**Asset management** > **Setup** > **Work orders** > **Project setup**), you create a relation between the work order type that is used for investments and the project group that was created for investments on the **Project groups** page in the **Project management and accounting** module (**Project management and accounting** > **Setup** > **Posting** > **Project groups**).</span></span>

![Figura 4](media/27-work-orders.png)

4. <span data-ttu-id="e7249-117">Quando si crea un ordine di lavoro associato a un oggetto cespiti, si seleziona il tipo di ordine di lavoro utilizzato per la gestione degli investimenti, ad esempio **Investimento**.</span><span class="sxs-lookup"><span data-stu-id="e7249-117">When you create a work order that is related to a fixed asset, you select the work order type that is used to handle investments, such as **Investment**.</span></span>

5. <span data-ttu-id="e7249-118">Quando viene creato l'ordine di lavoro, il tipo di ordine di lavoro associato viene visualizzato nella pagina **Tutti gli ordini di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="e7249-118">When the work order is created, the related work order type is shown on the **All work orders** page.</span></span>

![Figura 5](media/28-work-orders.png)

6. <span data-ttu-id="e7249-120">Quando viene creato l'ordine di lavoro, viene creato il progetto correlato all'ordine di lavoro nella pagina **Tutti i progetti** del modulo **Gestione progetti e contabilità** (**Gestione progetti e contabilità** > **Progetti** > **Tutti i progetti**).</span><span class="sxs-lookup"><span data-stu-id="e7249-120">When the work order is created, the project that is related to the work order is created on the **All projects** page in the **Project management and accounting** module (**Project management and accounting** > **Projects** > **All projects**).</span></span> <span data-ttu-id="e7249-121">Per visualizzare le informazioni correlate al progetto, selezionare il collegamento nel campo **ID progetto** della scheda **Generale** della scheda dettaglio **Dettagli riga** nella visualizzazione dei dettagli della pagina **Tutti gli ordini di lavoro** del modulo **Gestione cespiti** (**Gestione cespiti** > **Comune** > **Ordini di lavoro** > **Tutti gli ordini di lavoro**).</span><span class="sxs-lookup"><span data-stu-id="e7249-121">To view project-related information, select the link in the **Project ID** field on the **General** tab on the **Line details** FastTab in the details view of the **All work orders** page in the **Asset management** module (**Asset management** > **Commom** > **Work orders** > **All work orders**).</span></span>

![Figura 6](media/29-work-orders.png)

7. <span data-ttu-id="e7249-123">Per visualizzare una panoramica dei progetti associati a un cespite, selezionare **Cespiti** > **Cespiti** > **Cespiti**, quindi nel campo **Numero cespite**, selezionare il collegamento del cespite per aprire la visualizzazione dei dettagli.</span><span class="sxs-lookup"><span data-stu-id="e7249-123">To see an overview of the projects associated with a fixed asset, select **Fixed assets** > **Fixed assets** > **Fixed assets**, and then, in the **Fixed asset number** field, select the link for the fixed asset to open the details view.</span></span> <span data-ttu-id="e7249-124">Espandere il riquadro **Informazioni correlate** sul lato destro della pagina e selezionare la scheda dettaglio **Progetti associati**.</span><span class="sxs-lookup"><span data-stu-id="e7249-124">Expand the **Related information** pane on the right side of the page, and select the **Associated projects** FastTab.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]