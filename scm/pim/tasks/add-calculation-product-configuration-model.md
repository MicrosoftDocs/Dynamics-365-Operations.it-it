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
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 2db8fb922b085a7f118822ef4fd974ac338f4d99
ms.contentlocale: it-it
ms.lasthandoff: 08/29/2017

---
# <a name="add-a-calculation-to-a-product-configuration-model"></a><span data-ttu-id="12d1e-103">Aggiungere un calcolo a un modello di configurazione dei prodotti</span><span class="sxs-lookup"><span data-stu-id="12d1e-103">Add a calculation to a product configuration model</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="12d1e-104">In questa procedura vengono descritti i passaggi per aggiungere un nuovo calcolo a un modello di configurazione prodotto.</span><span class="sxs-lookup"><span data-stu-id="12d1e-104">This procedure shows how to add a new calculation to a product configuration model.</span></span> <span data-ttu-id="12d1e-105">Indica come è possibile creare un'espressione logica utilizzando l'operatore "If" per impostare l'altezza dell'altoparlante a 10 per gli altoparlanti bianchi e a 15 per tutti gli altri colori.</span><span class="sxs-lookup"><span data-stu-id="12d1e-105">It shows how you can create a logical expression using the "If" operator to set a speaker height to 10 for white speakers and 15 for all other cabinet finishes.</span></span> <span data-ttu-id="12d1e-106">La procedura utilizza il componente High end speaker nella società di dati dimostrativi USMF.</span><span class="sxs-lookup"><span data-stu-id="12d1e-106">The procedure uses the High end speaker component in the demo company USMF.</span></span>


## <a name="add-a-calculation"></a><span data-ttu-id="12d1e-107">Aggiungere un calcolo</span><span class="sxs-lookup"><span data-stu-id="12d1e-107">Add a calculation</span></span>

## <a name="create-calculation-expression"></a><span data-ttu-id="12d1e-108">Creare un'espressione di calcolo</span><span class="sxs-lookup"><span data-stu-id="12d1e-108">Create calculation expression</span></span>
1. <span data-ttu-id="12d1e-109">Fare clic su Modifica espressione.</span><span class="sxs-lookup"><span data-stu-id="12d1e-109">Click Edit expression.</span></span>
2. <span data-ttu-id="12d1e-110">Nel campo ConstraintBody, immettere 'If[CabinetFinish=="White", 10, 15]'.</span><span class="sxs-lookup"><span data-stu-id="12d1e-110">In the ConstraintBody field, enter 'If[CabinetFinish=="White", 10, 15]'.</span></span>
3. <span data-ttu-id="12d1e-111">Fare clic su Convalida.</span><span class="sxs-lookup"><span data-stu-id="12d1e-111">Click Validate.</span></span>
4. <span data-ttu-id="12d1e-112">Fare clic su Chiudi.</span><span class="sxs-lookup"><span data-stu-id="12d1e-112">Click Close.</span></span>
5. <span data-ttu-id="12d1e-113">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="12d1e-113">Click OK.</span></span>

