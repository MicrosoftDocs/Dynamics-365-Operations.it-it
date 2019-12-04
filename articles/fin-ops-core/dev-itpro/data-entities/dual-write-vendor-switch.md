---
title: Passare da una struttura fornitori all'altra
description: ''
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 09/20/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-09-20
ms.openlocfilehash: 4e97ff0b0e6195b5e3703e15a0bb0de7644ef8d1
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/06/2019
ms.locfileid: "2772366"
---
# <a name="switch-between-vendor-designs"></a><span data-ttu-id="e4336-102">Passare da una struttura fornitori all'altra</span><span class="sxs-lookup"><span data-stu-id="e4336-102">Switch between vendor designs</span></span>

[!include [banner](../includes/banner.md)]

## <a name="vendor-data-flow"></a><span data-ttu-id="e4336-103">Flusso di dati fornitore</span><span class="sxs-lookup"><span data-stu-id="e4336-103">Vendor data flow</span></span> 

<span data-ttu-id="e4336-104">Se si utilizzano altre app di Dynamics 365 per la gestione dei fornitori e si desidera isolare le informazioni sui fornitore quelle sui clienti, utilizzare questa struttura fornitori di base.</span><span class="sxs-lookup"><span data-stu-id="e4336-104">If you use other Dynamics 365 apps for vendor mastering and you want to isolate vendor information from customers, use this basic vendor design.</span></span>  

![Flusso di base del fornitore](media/dual-write-switch-1.png)
 
<span data-ttu-id="e4336-106">Se si utilizzano altre app Dynamics 365 per la gestione dei fornitori e si desidera continuare a usare l'entità **Conto** per archiviare le informazioni sui fornitori, utilizzare la nuova struttura fornitori estesa.</span><span class="sxs-lookup"><span data-stu-id="e4336-106">If you use other Dynamics 365 apps for vendor mastering and you want to continue to use the **Account** entity for storing vendor information, use this extended vendor design.</span></span> <span data-ttu-id="e4336-107">In questa struttura, le informazioni estese dei fornitori come lo stato in sospeso e il profilo fornitore vengono archiviate nell'entità **fornitori** in Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="e4336-107">In this design, extended vendor information like vendor on-hold status and vendor profile is stored in the **vendors** entity in Common Data Service.</span></span> 

![Flusso esteso fornitore](media/dual-write-switch-2.png)
 
<span data-ttu-id="e4336-109">Completare i passaggi di seguito per utilizzare la struttura estesa fornitore:</span><span class="sxs-lookup"><span data-stu-id="e4336-109">Follow the below steps to use the extended vendor design:</span></span> 
 
1. <span data-ttu-id="e4336-110">Il pacchetto della soluzione **SupplyChainCommon** contiene i modelli di processo del flusso di lavoro come illustrato nella seguente immagine.</span><span class="sxs-lookup"><span data-stu-id="e4336-110">The **SupplyChainCommon** solution package contains the workflow process templates as shown in the following image.</span></span>
    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="e4336-111">![Modelli del processo del flusso di lavoro](media/dual-write-switch-3.png)</span><span class="sxs-lookup"><span data-stu-id="e4336-111">![Workflow process templates](media/dual-write-switch-3.png)</span></span>
2. <span data-ttu-id="e4336-112">Creare nuovi processi del flusso di lavoro utilizzando i modelli del processo del flusso di lavoro:</span><span class="sxs-lookup"><span data-stu-id="e4336-112">Create new workflow processes using the workflow process templates:</span></span> 
    1. <span data-ttu-id="e4336-113">Creare un nuovo processo del flusso di lavoro per l'entità **Fornitore** utilizzando il modello di processo del flusso di lavoro **Creare fornitori nell'entità conto** e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="e4336-113">Create a new workflow process for the **Vendor** entity using the **Create Vendors in Account Entity** workflow process template and click **OK**.</span></span> <span data-ttu-id="e4336-114">Questo flusso di lavoro gestisce lo scenario di creazione del fornitore per l'entità **Conto**.</span><span class="sxs-lookup"><span data-stu-id="e4336-114">This workflow handles the vendor creation scenario for the **Account** entity.</span></span>
        > [!div class="mx-imgBorder"]
        > <span data-ttu-id="e4336-115">![Creare fornitori nell'entità conto](media/dual-write-switch-4.png)</span><span class="sxs-lookup"><span data-stu-id="e4336-115">![Create Vendors in Account Entity](media/dual-write-switch-4.png)</span></span>
    2. <span data-ttu-id="e4336-116">Creare un nuovo processo del flusso di lavoro per l'entità **Fornitore** utilizzando il modello di processo del flusso di lavoro **Aggiornare entità conto** e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="e4336-116">Create a new workflow process for the **Vendor** entity using the **Update Accounts Entity** workflow process template and click **OK**.</span></span> <span data-ttu-id="e4336-117">Questo flusso di lavoro gestisce lo scenario di aggiornamento del fornitore per l'entità **Conto**.</span><span class="sxs-lookup"><span data-stu-id="e4336-117">This workflow handles the vendor update scenario for the **Account** entity.</span></span> 
        > [!div class="mx-imgBorder"]
        > <span data-ttu-id="e4336-118">![Aggiornare entità conto](media/dual-write-switch-5.png)</span><span class="sxs-lookup"><span data-stu-id="e4336-118">![Update Accounts Entity](media/dual-write-switch-5.png)</span></span>
    3. <span data-ttu-id="e4336-119">Creare nuovi processi del flusso di lavoro dai modelli creati sull'entità **Conti**.</span><span class="sxs-lookup"><span data-stu-id="e4336-119">Create new workflow processes from the templates created on the **Accounts** entity.</span></span> 
        > [!div class="mx-imgBorder"]
        > <span data-ttu-id="e4336-120">![Creare fornitori nell'entità fornitori](media/dual-write-switch-6.png)
        > </span><span class="sxs-lookup"><span data-stu-id="e4336-120">![Create vendors in vendors entity](media/dual-write-switch-6.png)
        > </span></span>[!div class="mx-imgBorder"]
<span data-ttu-id="e4336-121">![Aggiornare entità fornitori](media/dual-write-switch-7.png)</span><span class="sxs-lookup"><span data-stu-id="e4336-121">![Update vendors entity](media/dual-write-switch-7.png)</span></span>
    4. <span data-ttu-id="e4336-122">È possibile configurare i flussi di lavoro come flussi di lavoro in tempo reale o in background in base ai requisiti.</span><span class="sxs-lookup"><span data-stu-id="e4336-122">You can configure the workflows as real-time or background workflows based on your requirements.</span></span> 
        > [!div class="mx-imgBorder"]
        > <span data-ttu-id="e4336-123">![Conversione a un flusso di lavoro in background](media/dual-write-switch-8.png)</span><span class="sxs-lookup"><span data-stu-id="e4336-123">![Convert to a background workflow](media/dual-write-switch-8.png)</span></span>
    5. <span data-ttu-id="e4336-124">Attivare i flussi di lavoro creati sulle entità **Fornitore** e **Conto** per iniziare a utilizzare l'entità **Conto** di Customer Engagement per archiviare le informazioni sul fornitore.</span><span class="sxs-lookup"><span data-stu-id="e4336-124">Activate the workflows that you created on the **Account** and **Vendor** entities to start using the Customer Engagement **Account** entity for storing vendor information.</span></span> 
 
