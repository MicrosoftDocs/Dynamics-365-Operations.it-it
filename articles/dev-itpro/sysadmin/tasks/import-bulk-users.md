--- 
title: Importare utenti in blocco
description: "Questa procedura può essere utilizzata dagli amministratori di sistema per importare un numero elevato di utenti da Active Directory Azure."
author: maertenm
manager: AnnBe
ms.date: 07/07/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: sericks
ms.search.scope: Operations
ms.search.region: Global
ms.author: maertenm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 339cc1d3bcdc1dc93b796c385d2165f45f8f7ecf
ms.contentlocale: it-it
ms.lasthandoff: 05/08/2018

---
# <a name="import-users-in-bulk"></a><span data-ttu-id="cdb5d-103">Importare utenti in blocco</span><span class="sxs-lookup"><span data-stu-id="cdb5d-103">Import users in bulk</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="cdb5d-104">Questa procedura può essere utilizzata dagli amministratori di sistema per importare un numero elevato di utenti da Active Directory Azure.</span><span class="sxs-lookup"><span data-stu-id="cdb5d-104">This procedure can be used by system administrators to import a large number of users from Azure Active Directory.</span></span>


## <a name="run-as-a-batch-job"></a><span data-ttu-id="cdb5d-105">Esegui come processo batch</span><span class="sxs-lookup"><span data-stu-id="cdb5d-105">Run as a batch job</span></span>
1. <span data-ttu-id="cdb5d-106">Andare a Amministrazione sistema > Utenti > Utenti.</span><span class="sxs-lookup"><span data-stu-id="cdb5d-106">Go to System administration > Users > Users.</span></span>
2. <span data-ttu-id="cdb5d-107">Fare clic su Importazione batch.</span><span class="sxs-lookup"><span data-stu-id="cdb5d-107">Click Batch import.</span></span>
3. <span data-ttu-id="cdb5d-108">Espandere la sezione Esecuzione in background.</span><span class="sxs-lookup"><span data-stu-id="cdb5d-108">Expand the Run in the background section.</span></span>
4. <span data-ttu-id="cdb5d-109">Selezionare Sì nel campo Elaborazione batch.</span><span class="sxs-lookup"><span data-stu-id="cdb5d-109">Select Yes in the Batch processing field.</span></span>
5. <span data-ttu-id="cdb5d-110">Nel campo Descrizione attività immettere un valore.</span><span class="sxs-lookup"><span data-stu-id="cdb5d-110">In the Task description field, type a value.</span></span>
6. <span data-ttu-id="cdb5d-111">Nel campo Gruppo batch immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="cdb5d-111">In the Batch group field, enter or select a value.</span></span>
    * <span data-ttu-id="cdb5d-112">Questo passaggio è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="cdb5d-112">This is an optional step.</span></span>  
7. <span data-ttu-id="cdb5d-113">Selezionare Sì nel campo Privato.</span><span class="sxs-lookup"><span data-stu-id="cdb5d-113">Select Yes in the Private field.</span></span>
    * <span data-ttu-id="cdb5d-114">Questo passaggio è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="cdb5d-114">This is an optional step.</span></span>  
8. <span data-ttu-id="cdb5d-115">Selezionare Sì nel campo Processo critico.</span><span class="sxs-lookup"><span data-stu-id="cdb5d-115">Select Yes in the Critical Job field.</span></span>
    * <span data-ttu-id="cdb5d-116">Questo passaggio è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="cdb5d-116">This is an optional step.</span></span>  
9. <span data-ttu-id="cdb5d-117">Selezionare un'opzione nel campo Categoria di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="cdb5d-117">In the Monitoring category field, select an option.</span></span>
10. <span data-ttu-id="cdb5d-118">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="cdb5d-118">Click OK.</span></span>

## <a name="run-in-a-sandbox-environment"></a><span data-ttu-id="cdb5d-119">Eseguire l'operazione in un ambiente sandbox</span><span class="sxs-lookup"><span data-stu-id="cdb5d-119">Run in a sandbox environment</span></span>
1. <span data-ttu-id="cdb5d-120">Fare clic su Importazione batch.</span><span class="sxs-lookup"><span data-stu-id="cdb5d-120">Click Batch import.</span></span>
2. <span data-ttu-id="cdb5d-121">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="cdb5d-121">Click OK.</span></span>


