--- 
title: Creare una voce di menu del dispositivo mobile per il consolidamento delle targhe
description: In questa procedura viene illustrato come creare una voce di menu del dispositivo mobile per il lavoro di consolidamento targhe.
author: YuyuScheller
manager: AnnBe
ms.date: 10/13/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mirzaab
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 7b8d20561ff092bd64c17c5d9335e9f54a1d191b
ms.contentlocale: it-it
ms.lasthandoff: 08/29/2017

---
# <a name="create-a-mobile-device-menu-item-for-license-plate-consolidation"></a><span data-ttu-id="47fe5-103">Creare una voce di menu del dispositivo mobile per il consolidamento delle targhe</span><span class="sxs-lookup"><span data-stu-id="47fe5-103">Create a mobile device menu item for license plate consolidation</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="47fe5-104">In questa procedura viene illustrato come creare una voce di menu del dispositivo mobile per il lavoro di consolidamento targhe.</span><span class="sxs-lookup"><span data-stu-id="47fe5-104">This procedure shows you how to create a mobile device menu item for license plate consolidation work.</span></span> <span data-ttu-id="47fe5-105">Questo consente agli addetti del magazzino di consolidare articoli in una targa con articoli in un'altra targa nella stessa ubicazione.</span><span class="sxs-lookup"><span data-stu-id="47fe5-105">This enables warehouse workers to consolidate items on one license plate with items on another license place within the same location.</span></span> <span data-ttu-id="47fe5-106">Ad esempio, potrebbero utilizzare questa funzione se i passaggi di gestione temporanea successivi fossero gli stessi su entrambi gli ordini di lavoro, in modo che il lavoro deve essere eseguito una sola volta per gli articoli uniti.</span><span class="sxs-lookup"><span data-stu-id="47fe5-106">For example, they might use this if subsequent staging steps were the same on both work orders, so that the work only needs to be performed once for the merged items.</span></span> <span data-ttu-id="47fe5-107">È possibile utilizzare questa procedura nella società di dati dimostrativi USMF.</span><span class="sxs-lookup"><span data-stu-id="47fe5-107">You can use this procedure in demo data company USMF.</span></span> <span data-ttu-id="47fe5-108">Questa attività viene in genere svolta da un responsabile del magazzino.</span><span class="sxs-lookup"><span data-stu-id="47fe5-108">The task would typically be carried out by a warehouse manager.</span></span> <span data-ttu-id="47fe5-109">Questa procedura è per una funzionalità che è stata aggiunta in Dynamics 365 for Operations, versione 1611.</span><span class="sxs-lookup"><span data-stu-id="47fe5-109">This procedure is for a feature that was added in Dynamics 365 for Operations, version 1611.</span></span>

1. <span data-ttu-id="47fe5-110">Andare a Gestione magazzino > Impostazioni > Dispositivo mobile > Voci di menu del dispositivo mobile.</span><span class="sxs-lookup"><span data-stu-id="47fe5-110">Go to Warehouse management > Setup > Mobile device > Mobile device menu items.</span></span>
2. <span data-ttu-id="47fe5-111">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="47fe5-111">Click New.</span></span>
3. <span data-ttu-id="47fe5-112">Digitare un valore nel campo Nome voce di menu.</span><span class="sxs-lookup"><span data-stu-id="47fe5-112">In the Menu item name field, type a value.</span></span>
4. <span data-ttu-id="47fe5-113">Digitare un valore nel campo Titolo.</span><span class="sxs-lookup"><span data-stu-id="47fe5-113">In the Title field, type a value.</span></span>
5. <span data-ttu-id="47fe5-114">Selezionare 'Indiretto' nel campo Modo.</span><span class="sxs-lookup"><span data-stu-id="47fe5-114">In the Mode field, select 'Indirect'.</span></span>
6. <span data-ttu-id="47fe5-115">Nel campo Codice attività, selezionare 'Consolida targhe'.</span><span class="sxs-lookup"><span data-stu-id="47fe5-115">In the Activity code field, select 'Consolidate license plates'.</span></span>

