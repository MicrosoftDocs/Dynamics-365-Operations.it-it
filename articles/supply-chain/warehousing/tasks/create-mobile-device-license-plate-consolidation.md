---
title: Creare una voce di menu del dispositivo mobile per il consolidamento delle targhe
description: In questa procedura viene illustrato come creare una voce di menu del dispositivo mobile per il lavoro di consolidamento targhe.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSRFMenuItem
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mirzaab
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7dc52284473f3e3275675b608386641c8570218b
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4431011"
---
# <a name="create-a-mobile-device-menu-item-for-license-plate-consolidation"></a><span data-ttu-id="ab71b-103">Creare una voce di menu del dispositivo mobile per il consolidamento delle targhe</span><span class="sxs-lookup"><span data-stu-id="ab71b-103">Create a mobile device menu item for license plate consolidation</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="ab71b-104">In questa procedura viene illustrato come creare una voce di menu del dispositivo mobile per il lavoro di consolidamento targhe.</span><span class="sxs-lookup"><span data-stu-id="ab71b-104">This procedure shows you how to create a mobile device menu item for license plate consolidation work.</span></span> <span data-ttu-id="ab71b-105">Questo consente agli addetti del magazzino di consolidare articoli in una targa con articoli in un'altra targa nella stessa ubicazione.</span><span class="sxs-lookup"><span data-stu-id="ab71b-105">This enables warehouse workers to consolidate items on one license plate with items on another license place within the same location.</span></span> <span data-ttu-id="ab71b-106">Ad esempio, potrebbero utilizzare questa funzione se i passaggi di gestione temporanea successivi fossero gli stessi su entrambi gli ordini di lavoro, in modo che il lavoro deve essere eseguito una sola volta per gli articoli uniti.</span><span class="sxs-lookup"><span data-stu-id="ab71b-106">For example, they might use this if subsequent staging steps were the same on both work orders, so that the work only needs to be performed once for the merged items.</span></span> <span data-ttu-id="ab71b-107">È possibile utilizzare questa procedura nella società di dati dimostrativi USMF.</span><span class="sxs-lookup"><span data-stu-id="ab71b-107">You can use this procedure in demo data company USMF.</span></span> <span data-ttu-id="ab71b-108">Questa attività viene in genere svolta da un responsabile del magazzino.</span><span class="sxs-lookup"><span data-stu-id="ab71b-108">The task would typically be carried out by a warehouse manager.</span></span> <span data-ttu-id="ab71b-109">Questa procedura è per una funzionalità che è stata aggiunta in Dynamics 365 for Operations versione 1611.</span><span class="sxs-lookup"><span data-stu-id="ab71b-109">This procedure is for a feature that was added in Dynamics 365 for Operations, version 1611.</span></span>

1. <span data-ttu-id="ab71b-110">Andare a Gestione magazzino > Impostazioni > Dispositivo mobile > Voci di menu del dispositivo mobile.</span><span class="sxs-lookup"><span data-stu-id="ab71b-110">Go to Warehouse management > Setup > Mobile device > Mobile device menu items.</span></span>
2. <span data-ttu-id="ab71b-111">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="ab71b-111">Click New.</span></span>
3. <span data-ttu-id="ab71b-112">Digitare un valore nel campo Nome voce di menu.</span><span class="sxs-lookup"><span data-stu-id="ab71b-112">In the Menu item name field, type a value.</span></span>
4. <span data-ttu-id="ab71b-113">Digitare un valore nel campo Titolo.</span><span class="sxs-lookup"><span data-stu-id="ab71b-113">In the Title field, type a value.</span></span>
5. <span data-ttu-id="ab71b-114">Selezionare 'Indiretto' nel campo Modo.</span><span class="sxs-lookup"><span data-stu-id="ab71b-114">In the Mode field, select 'Indirect'.</span></span>
6. <span data-ttu-id="ab71b-115">Nel campo Codice attività, selezionare 'Consolida targhe'.</span><span class="sxs-lookup"><span data-stu-id="ab71b-115">In the Activity code field, select 'Consolidate license plates'.</span></span>

