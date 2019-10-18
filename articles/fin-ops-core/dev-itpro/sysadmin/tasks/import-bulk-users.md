---
title: Importare utenti in blocco
description: Questa procedura può essere utilizzata dagli amministratori di sistema per importare un numero elevato di utenti da Azure Active Directory.
author: maertenm
manager: AnnBe
ms.date: 07/07/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.search.scope: Operations
ms.search.region: Global
ms.author: maertenm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: cb2c316465f8c6964a562e92ce0a2233b37d38fe
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/27/2019
ms.locfileid: "2180900"
---
# <a name="import-users-in-bulk"></a><span data-ttu-id="906a1-103">Importare utenti in blocco</span><span class="sxs-lookup"><span data-stu-id="906a1-103">Import users in bulk</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="906a1-104">Questa procedura può essere utilizzata dagli amministratori di sistema per importare un numero elevato di utenti da Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="906a1-104">This procedure can be used by system administrators to import a large number of users from Azure Active Directory.</span></span>


## <a name="run-as-a-batch-job"></a><span data-ttu-id="906a1-105">Esegui come processo batch</span><span class="sxs-lookup"><span data-stu-id="906a1-105">Run as a batch job</span></span>
1. <span data-ttu-id="906a1-106">Andare a Amministrazione sistema > Utenti > Utenti.</span><span class="sxs-lookup"><span data-stu-id="906a1-106">Go to System administration > Users > Users.</span></span>
2. <span data-ttu-id="906a1-107">Fare clic su Importazione batch.</span><span class="sxs-lookup"><span data-stu-id="906a1-107">Click Batch import.</span></span>
3. <span data-ttu-id="906a1-108">Espandere la sezione Esecuzione in background.</span><span class="sxs-lookup"><span data-stu-id="906a1-108">Expand the Run in the background section.</span></span>
4. <span data-ttu-id="906a1-109">Selezionare Sì nel campo Elaborazione batch.</span><span class="sxs-lookup"><span data-stu-id="906a1-109">Select Yes in the Batch processing field.</span></span>
5. <span data-ttu-id="906a1-110">Nel campo Descrizione attività immettere un valore.</span><span class="sxs-lookup"><span data-stu-id="906a1-110">In the Task description field, type a value.</span></span>
6. <span data-ttu-id="906a1-111">Nel campo Gruppo batch immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="906a1-111">In the Batch group field, enter or select a value.</span></span>
    * <span data-ttu-id="906a1-112">Questo passaggio è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="906a1-112">This is an optional step.</span></span>  
7. <span data-ttu-id="906a1-113">Selezionare Sì nel campo Privato.</span><span class="sxs-lookup"><span data-stu-id="906a1-113">Select Yes in the Private field.</span></span>
    * <span data-ttu-id="906a1-114">Questo passaggio è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="906a1-114">This is an optional step.</span></span>  
8. <span data-ttu-id="906a1-115">Selezionare Sì nel campo Processo critico.</span><span class="sxs-lookup"><span data-stu-id="906a1-115">Select Yes in the Critical Job field.</span></span>
    * <span data-ttu-id="906a1-116">Questo passaggio è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="906a1-116">This is an optional step.</span></span>  
9. <span data-ttu-id="906a1-117">Selezionare un'opzione nel campo Categoria di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="906a1-117">In the Monitoring category field, select an option.</span></span>
10. <span data-ttu-id="906a1-118">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="906a1-118">Click OK.</span></span>

## <a name="run-in-a-sandbox-environment"></a><span data-ttu-id="906a1-119">Eseguire l'operazione in un ambiente sandbox</span><span class="sxs-lookup"><span data-stu-id="906a1-119">Run in a sandbox environment</span></span>
1. <span data-ttu-id="906a1-120">Fare clic su Importazione batch.</span><span class="sxs-lookup"><span data-stu-id="906a1-120">Click Batch import.</span></span>
2. <span data-ttu-id="906a1-121">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="906a1-121">Click OK.</span></span>

