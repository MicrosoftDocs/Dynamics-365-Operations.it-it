---
title: Passa tra strutture fornitore
description: In questo argomento viene descritto come passare tra l'integrazione dei dati dei fornitori tra le app Finance and Operations e Common Data Service.
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
ms.openlocfilehash: 204d788e72e79e7acf744d24cbeacb0f9b47da7d
ms.sourcegitcommit: 3306e451f04df01c51d8d332306b135d8ae1e254
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2019
ms.locfileid: "2902727"
---
# <a name="switch-between-vendor-designs"></a><span data-ttu-id="188e2-103">Passa tra strutture fornitore</span><span class="sxs-lookup"><span data-stu-id="188e2-103">Switch between vendor designs</span></span>

[!include [banner](../includes/banner.md)]

## <a name="vendor-data-flow"></a><span data-ttu-id="188e2-104">Flusso di dati fornitore</span><span class="sxs-lookup"><span data-stu-id="188e2-104">Vendor data flow</span></span> 

<span data-ttu-id="188e2-105">Se si utilizzano altre app di Dynamics 365 per la gestione dei fornitori e si desidera isolare le informazioni sui fornitore quelle sui clienti, utilizzare questa struttura fornitori di base.</span><span class="sxs-lookup"><span data-stu-id="188e2-105">If you use other Dynamics 365 apps for vendor mastering and you want to isolate vendor information from customers, use this basic vendor design.</span></span>  

![Flusso di base del fornitore](media/dual-write-vendor-data-flow.png)
 
<span data-ttu-id="188e2-107">Se si utilizzano altre app Dynamics 365 per la gestione dei fornitori e si desidera continuare a usare l'entità **Conto** per archiviare le informazioni sui fornitori, utilizzare la nuova struttura fornitori estesa.</span><span class="sxs-lookup"><span data-stu-id="188e2-107">If you use other Dynamics 365 apps for vendor mastering and you want to continue to use the **Account** entity for storing vendor information, use this extended vendor design.</span></span> <span data-ttu-id="188e2-108">In questa struttura, le informazioni estese dei fornitori come lo stato in sospeso e il profilo fornitore vengono archiviate nell'entità **fornitori** in Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="188e2-108">In this design, extended vendor information like vendor on-hold status and vendor profile is stored in the **vendors** entity in Common Data Service.</span></span> 

![Flusso esteso fornitore](media/dual-write-vendor-detail.jpg)
 
<span data-ttu-id="188e2-110">Completare i passaggi di seguito per utilizzare la struttura estesa fornitore:</span><span class="sxs-lookup"><span data-stu-id="188e2-110">Follow the below steps to use the extended vendor design:</span></span> 
 
1. <span data-ttu-id="188e2-111">Il pacchetto della soluzione **SupplyChainCommon** contiene i modelli di processo del flusso di lavoro come illustrato nella seguente immagine.</span><span class="sxs-lookup"><span data-stu-id="188e2-111">The **SupplyChainCommon** solution package contains the workflow process templates as shown in the following image.</span></span>
    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="188e2-112">![Modelli del processo del flusso di lavoro](media/dual-write-switch-3.png)</span><span class="sxs-lookup"><span data-stu-id="188e2-112">![Workflow process templates](media/dual-write-switch-3.png)</span></span>
2. <span data-ttu-id="188e2-113">Creare nuovi processi del flusso di lavoro utilizzando i modelli del processo del flusso di lavoro:</span><span class="sxs-lookup"><span data-stu-id="188e2-113">Create new workflow processes using the workflow process templates:</span></span> 
    1. <span data-ttu-id="188e2-114">Creare un nuovo processo del flusso di lavoro per l'entità **Fornitore** utilizzando il modello di processo del flusso di lavoro **Creare fornitori nell'entità conto** e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="188e2-114">Create a new workflow process for the **Vendor** entity using the **Create Vendors in Account Entity** workflow process template and click **OK**.</span></span> <span data-ttu-id="188e2-115">Questo flusso di lavoro gestisce lo scenario di creazione del fornitore per l'entità **Conto**.</span><span class="sxs-lookup"><span data-stu-id="188e2-115">This workflow handles the vendor creation scenario for the **Account** entity.</span></span>
        > [!div class="mx-imgBorder"]
        > <span data-ttu-id="188e2-116">![Creare fornitori nell'entità conto](media/dual-write-switch-4.png)</span><span class="sxs-lookup"><span data-stu-id="188e2-116">![Create Vendors in Account Entity](media/dual-write-switch-4.png)</span></span>
    2. <span data-ttu-id="188e2-117">Creare un nuovo processo del flusso di lavoro per l'entità **Fornitore** utilizzando il modello di processo del flusso di lavoro **Aggiornare entità conto** e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="188e2-117">Create a new workflow process for the **Vendor** entity using the **Update Accounts Entity** workflow process template and click **OK**.</span></span> <span data-ttu-id="188e2-118">Questo flusso di lavoro gestisce lo scenario di aggiornamento del fornitore per l'entità **Conto**.</span><span class="sxs-lookup"><span data-stu-id="188e2-118">This workflow handles the vendor update scenario for the **Account** entity.</span></span> 
        > [!div class="mx-imgBorder"]
        > <span data-ttu-id="188e2-119">![Aggiornare entità conto](media/dual-write-switch-5.png)</span><span class="sxs-lookup"><span data-stu-id="188e2-119">![Update Accounts Entity](media/dual-write-switch-5.png)</span></span>
    3. <span data-ttu-id="188e2-120">Creare nuovi processi del flusso di lavoro dai modelli creati sull'entità **Conti**.</span><span class="sxs-lookup"><span data-stu-id="188e2-120">Create new workflow processes from the templates created on the **Accounts** entity.</span></span> 
        > [!div class="mx-imgBorder"]
        > <span data-ttu-id="188e2-121">![Creare fornitori nell'entità fornitori](media/dual-write-switch-6.png)
        > </span><span class="sxs-lookup"><span data-stu-id="188e2-121">![Create vendors in vendors entity](media/dual-write-switch-6.png)
        > </span></span>[!div class="mx-imgBorder"]
<span data-ttu-id="188e2-122">![Aggiornare entità fornitori](media/dual-write-switch-7.png)</span><span class="sxs-lookup"><span data-stu-id="188e2-122">![Update vendors entity](media/dual-write-switch-7.png)</span></span>
    4. <span data-ttu-id="188e2-123">È possibile configurare i flussi di lavoro come flussi di lavoro in tempo reale o in background in base ai requisiti.</span><span class="sxs-lookup"><span data-stu-id="188e2-123">You can configure the workflows as real-time or background workflows based on your requirements.</span></span> 
        > [!div class="mx-imgBorder"]
        > <span data-ttu-id="188e2-124">![Conversione a un flusso di lavoro in background](media/dual-write-switch-8.png)</span><span class="sxs-lookup"><span data-stu-id="188e2-124">![Convert to a background workflow](media/dual-write-switch-8.png)</span></span>
    5. <span data-ttu-id="188e2-125">Attivare i flussi di lavoro creati sulle entità **Fornitore** e **Account** per iniziare a utilizzare l'entità **Account** per archiviare le informazioni sul fornitore.</span><span class="sxs-lookup"><span data-stu-id="188e2-125">Activate the workflows that you created on the **Account** and **Vendor** entities to start using the **Account** entity for storing vendor information.</span></span> 
 
