---
title: Creare una classe di lavoro
description: Questa procedura mostra come impostare una classe di lavoro.
author: ShylaThompson
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5def9be0966d65728ffb0897229c0d749e7e13a0
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "1571795"
---
# <a name="create-a-work-class"></a><span data-ttu-id="56d85-103">Creare una classe di lavoro</span><span class="sxs-lookup"><span data-stu-id="56d85-103">Create a work class</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="56d85-104">Questa procedura mostra come impostare una classe di lavoro.</span><span class="sxs-lookup"><span data-stu-id="56d85-104">This procedure shows you how to set up a work class.</span></span> <span data-ttu-id="56d85-105">Le classi di lavoro vengono utilizzate per indirizzare e/o limitare il tipo di righe ordine di lavoro che un addetto al magazzino può elaborare in un dispositivo mobile.</span><span class="sxs-lookup"><span data-stu-id="56d85-105">Work classes are used to direct and/or limit the type of work order lines that a warehouse worker can process on a mobile device.</span></span> <span data-ttu-id="56d85-106">Le righe che un lavoratore può elaborare vengono determinate dalle classi di lavoro sulle voci di menu del dispositivo mobile a cui l'addetto al magazzino può accedere e dalla classe di lavoro specificata nelle righe di lavoro.</span><span class="sxs-lookup"><span data-stu-id="56d85-106">The lines that a worker can process are determined from the work classes on the mobile device menu items that the warehouse worker has access to and the work class that’s specified on the work lines.</span></span> <span data-ttu-id="56d85-107">Le classi di lavoro possono essere utilizzate per convalidare l'ubicazione di stoccaggio per una riga ordine di lavoro.</span><span class="sxs-lookup"><span data-stu-id="56d85-107">Work classes can also be used to validate the put location for a work order line.</span></span> <span data-ttu-id="56d85-108">È possibile eseguire questa procedura nella società di dati dimostrativi USMF oppure nei propri dati.</span><span class="sxs-lookup"><span data-stu-id="56d85-108">You can run this procedure in demo data company USMF or on your own data.</span></span> <span data-ttu-id="56d85-109">Questa procedura è destinata al responsabile del magazzino.</span><span class="sxs-lookup"><span data-stu-id="56d85-109">This procedure is intended for the warehouse manager.</span></span>

1. <span data-ttu-id="56d85-110">Andare a Gestione magazzino > Impostazioni > Lavoro > Classi di lavoro.</span><span class="sxs-lookup"><span data-stu-id="56d85-110">Go to Warehouse management > Setup > Work > Work classes.</span></span>
2. <span data-ttu-id="56d85-111">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="56d85-111">Click New.</span></span>
3. <span data-ttu-id="56d85-112">Nel campo ID classe, digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="56d85-112">In the Work class ID field, type a value.</span></span>
4. <span data-ttu-id="56d85-113">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="56d85-113">In the Description field, type a value.</span></span>
5. <span data-ttu-id="56d85-114">Nel campo Tipo ordine di lavoro selezionare un'opzione.</span><span class="sxs-lookup"><span data-stu-id="56d85-114">In the Work order type field, select an option.</span></span>
6. <span data-ttu-id="56d85-115">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="56d85-115">Click New.</span></span>
7. <span data-ttu-id="56d85-116">Digitare un valore nel campo Tipo di ubicazione.</span><span class="sxs-lookup"><span data-stu-id="56d85-116">In the Location type field, type a value.</span></span>
    * <span data-ttu-id="56d85-117">Se si seleziona un tipo di ubicazione, viene impostata una restrizione in cui gli articoli possono essere inseriti dopo che sono stati prelevati.</span><span class="sxs-lookup"><span data-stu-id="56d85-117">If you select a location type, this sets a restriction on where items can be put after they’ve been picked.</span></span> <span data-ttu-id="56d85-118">Questa impostazione viene utilizzata quando una direttiva ubicazione prova a risolvere l'ubicazione o se un addetto al magazzino fornisce manualmente l'ubicazione per la voce di menu del dispositivo mobile.</span><span class="sxs-lookup"><span data-stu-id="56d85-118">This setting is used when a location directive tries to resolve the location, or if a warehouse worker manually provides the location for the mobile device menu item.</span></span>  
8. <span data-ttu-id="56d85-119">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="56d85-119">Close the page.</span></span>

