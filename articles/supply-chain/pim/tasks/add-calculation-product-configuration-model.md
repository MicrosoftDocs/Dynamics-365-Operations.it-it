--- 
title: Aggiungere un calcolo a un modello di configurazione dei prodotti
description: In questa procedura vengono descritti i passaggi per aggiungere un nuovo calcolo a un modello di configurazione prodotto.
author: YuyuScheller
manager: AnnBe
ms.date: 03/02/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 01434e8dbd1e66ae04d0b7910ef2be582297ac84
ms.contentlocale: it-it
ms.lasthandoff: 04/13/2018

---
# <a name="add-a-calculation-to-a-product-configuration-model"></a><span data-ttu-id="5e10a-103">Aggiungere un calcolo a un modello di configurazione dei prodotti</span><span class="sxs-lookup"><span data-stu-id="5e10a-103">Add a calculation to a product configuration model</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="5e10a-104">In questa procedura vengono descritti i passaggi per aggiungere un nuovo calcolo a un modello di configurazione prodotto.</span><span class="sxs-lookup"><span data-stu-id="5e10a-104">This procedure shows how to add a new calculation to a product configuration model.</span></span> <span data-ttu-id="5e10a-105">Indica come è possibile creare un'espressione logica utilizzando l'operatore "If" per impostare l'altezza dell'altoparlante a 10 per gli altoparlanti bianchi e a 15 per tutti gli altri colori.</span><span class="sxs-lookup"><span data-stu-id="5e10a-105">It shows how you can create a logical expression using the "If" operator to set a speaker height to 10 for white speakers and 15 for all other cabinet finishes.</span></span> <span data-ttu-id="5e10a-106">La procedura utilizza il componente High end speaker nella società di dati dimostrativi USMF.</span><span class="sxs-lookup"><span data-stu-id="5e10a-106">The procedure uses the High end speaker component in the demo company USMF.</span></span>


## <a name="add-a-calculation"></a><span data-ttu-id="5e10a-107">Aggiungere un calcolo</span><span class="sxs-lookup"><span data-stu-id="5e10a-107">Add a calculation</span></span>

## <a name="create-calculation-expression"></a><span data-ttu-id="5e10a-108">Creare un'espressione di calcolo</span><span class="sxs-lookup"><span data-stu-id="5e10a-108">Create calculation expression</span></span>
1. <span data-ttu-id="5e10a-109">Fare clic su Modifica espressione.</span><span class="sxs-lookup"><span data-stu-id="5e10a-109">Click Edit expression.</span></span>
2. <span data-ttu-id="5e10a-110">Nel campo ConstraintBody, immettere 'If[CabinetFinish=="White", 10, 15]'.</span><span class="sxs-lookup"><span data-stu-id="5e10a-110">In the ConstraintBody field, enter 'If[CabinetFinish=="White", 10, 15]'.</span></span>
3. <span data-ttu-id="5e10a-111">Fare clic su Convalida.</span><span class="sxs-lookup"><span data-stu-id="5e10a-111">Click Validate.</span></span>
4. <span data-ttu-id="5e10a-112">Fare clic su Chiudi.</span><span class="sxs-lookup"><span data-stu-id="5e10a-112">Click Close.</span></span>
5. <span data-ttu-id="5e10a-113">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="5e10a-113">Click OK.</span></span>


