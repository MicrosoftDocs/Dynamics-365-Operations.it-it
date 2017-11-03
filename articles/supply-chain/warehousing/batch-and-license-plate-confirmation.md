---
title: Conferma batch e targa
description: In questo argomento viene descritto come impostare e applicare la conferma batch e targa da un dispositivo mobile.
author: Mirzaab
manager: AnnBe
ms.date: 05/26/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, Operations
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 0444caa0f1cc176153c322b8619db65bd377ddd0
ms.contentlocale: it-it
ms.lasthandoff: 11/03/2017

---

# <a name="batch-and-license-plate-confirmation"></a><span data-ttu-id="a3aa2-103">Conferma batch e targa</span><span class="sxs-lookup"><span data-stu-id="a3aa2-103">Batch and license plate confirmation</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="a3aa2-104">La conferma batch consente di verificare che il batch corretto viene selezionato nel dispositivo mobile.</span><span class="sxs-lookup"><span data-stu-id="a3aa2-104">Batch confirmation allows you to confirm that the correct batch is being picked from the mobile device.</span></span> <span data-ttu-id="a3aa2-105">Nel prelievo iniziale del lavoro solo per batch sopra gli articoli, dove batch sopra indica che il batch è sopra l'ubicazione nella gerarchia di ricerca, è necessario verificare che il batch selezionato corrisponda al batch della riga di lavoro.</span><span class="sxs-lookup"><span data-stu-id="a3aa2-105">On the initial pick of work for batch above-items only, where batch above indicates that batch ranges higher than location in the search hierarchy, you must verify that the batch that is picked matches the batch on the work line.</span></span> 

<span data-ttu-id="a3aa2-106">La conferma targa consente di verificare che la targa corretta viene selezionata nel dispositivo mobile.</span><span class="sxs-lookup"><span data-stu-id="a3aa2-106">License plate confirmation allows you to confirm that the correct license plate is being picked from the mobile device.</span></span> <span data-ttu-id="a3aa2-107">Quando si seleziona il lavoro da un'ubicazione della fase, è necessario verificare che la targa selezionata corrisponda alla targa associata al lavoro.</span><span class="sxs-lookup"><span data-stu-id="a3aa2-107">When picking work from a stage location, you must verify that the license plate that is picked matches the license plate that is associated with the work.</span></span> <span data-ttu-id="a3aa2-108">Se il lavoro viene avviato tramite la scansione della targa, questo passaggio di conferma verrà ignorato.</span><span class="sxs-lookup"><span data-stu-id="a3aa2-108">If the work is started by scanning a license plate, this confirmation step will be skipped.</span></span>

## <a name="where-it-applies"></a><span data-ttu-id="a3aa2-109">Dove si applica</span><span class="sxs-lookup"><span data-stu-id="a3aa2-109">Where it applies</span></span>
<span data-ttu-id="a3aa2-110">La conferma viene applicata nei seguenti scenari:</span><span class="sxs-lookup"><span data-stu-id="a3aa2-110">Confirmation applies in the following scenarios:</span></span>

- <span data-ttu-id="a3aa2-111">La conferma batch viene applicata ai prelievi iniziali del lavoro per batch sopra gli articoli.</span><span class="sxs-lookup"><span data-stu-id="a3aa2-111">Batch confirmation applies to the initial picks of work for batch above-items.</span></span>
- <span data-ttu-id="a3aa2-112">La conferma targa si applica ai prelievi dalle ubicazioni della fase.</span><span class="sxs-lookup"><span data-stu-id="a3aa2-112">License plate confirmation applies to picks from stage locations.</span></span>

## <a name="set-up-batch-and-license-plate-confirmation"></a><span data-ttu-id="a3aa2-113">Configurare la conferma batch e targa</span><span class="sxs-lookup"><span data-stu-id="a3aa2-113">Set up batch and license plate confirmation</span></span>
<span data-ttu-id="a3aa2-114">È possibile configurare la conferma batch e targa tramite le voci di menu del dispositivo mobile.</span><span class="sxs-lookup"><span data-stu-id="a3aa2-114">You can configure batch and license plate confirmation from the mobile device menu items.</span></span>  
1.  <span data-ttu-id="a3aa2-115">Dalle voci di menu del dispositivo mobile, aprire la configurazione della conferma del lavoro.</span><span class="sxs-lookup"><span data-stu-id="a3aa2-115">From the mobile device menu items, enter the work confirmation setup.</span></span>  
2.  <span data-ttu-id="a3aa2-116">Selezionare l'opzione per la conferma batch o targa.</span><span class="sxs-lookup"><span data-stu-id="a3aa2-116">Select the option for either batch or license plate confirmation.</span></span> <span data-ttu-id="a3aa2-117">Entrambe le opzioni sono disponibili per i prelievi di tipo lavoro senza la conferma automatica attivata.</span><span class="sxs-lookup"><span data-stu-id="a3aa2-117">Both options are available for work type picks that do not have automatic confirmation enabled.</span></span>  

