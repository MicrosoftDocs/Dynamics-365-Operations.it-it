---
title: Creare una classe di lavoro
description: Questa procedura mostra come impostare una classe di lavoro.
author: ShylaThompson
manager: tfehr
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSWorkClass
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 49b110b93e6f0f886d180f9f2725245faad7afab
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5239040"
---
# <a name="create-a-work-class"></a><span data-ttu-id="d8a15-103">Creare una classe di lavoro</span><span class="sxs-lookup"><span data-stu-id="d8a15-103">Create a work class</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="d8a15-104">Questa procedura mostra come impostare una classe di lavoro.</span><span class="sxs-lookup"><span data-stu-id="d8a15-104">This procedure shows you how to set up a work class.</span></span> <span data-ttu-id="d8a15-105">Le classi di lavoro vengono utilizzate per indirizzare e/o limitare il tipo di righe ordine di lavoro che un addetto al magazzino può elaborare in un dispositivo mobile.</span><span class="sxs-lookup"><span data-stu-id="d8a15-105">Work classes are used to direct and/or limit the type of work order lines that a warehouse worker can process on a mobile device.</span></span> <span data-ttu-id="d8a15-106">Le righe che un lavoratore può elaborare vengono determinate dalle classi di lavoro sulle voci di menu del dispositivo mobile a cui l'addetto al magazzino può accedere e dalla classe di lavoro specificata nelle righe di lavoro.</span><span class="sxs-lookup"><span data-stu-id="d8a15-106">The lines that a worker can process are determined from the work classes on the mobile device menu items that the warehouse worker has access to and the work class that's specified on the work lines.</span></span> <span data-ttu-id="d8a15-107">Le classi di lavoro possono essere utilizzate per convalidare l'ubicazione di stoccaggio per una riga ordine di lavoro.</span><span class="sxs-lookup"><span data-stu-id="d8a15-107">Work classes can also be used to validate the put location for a work order line.</span></span> <span data-ttu-id="d8a15-108">È possibile eseguire questa procedura nella società di dati dimostrativi USMF oppure nei propri dati.</span><span class="sxs-lookup"><span data-stu-id="d8a15-108">You can run this procedure in demo data company USMF or on your own data.</span></span> <span data-ttu-id="d8a15-109">Questa procedura è destinata al responsabile del magazzino.</span><span class="sxs-lookup"><span data-stu-id="d8a15-109">This procedure is intended for the warehouse manager.</span></span>

1. <span data-ttu-id="d8a15-110">Andare a Gestione magazzino > Impostazioni > Lavoro > Classi di lavoro.</span><span class="sxs-lookup"><span data-stu-id="d8a15-110">Go to Warehouse management > Setup > Work > Work classes.</span></span>
2. <span data-ttu-id="d8a15-111">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="d8a15-111">Click New.</span></span>
3. <span data-ttu-id="d8a15-112">Nel campo ID classe, digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="d8a15-112">In the Work class ID field, type a value.</span></span>
4. <span data-ttu-id="d8a15-113">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="d8a15-113">In the Description field, type a value.</span></span>
5. <span data-ttu-id="d8a15-114">Nel campo Tipo ordine di lavoro selezionare un'opzione.</span><span class="sxs-lookup"><span data-stu-id="d8a15-114">In the Work order type field, select an option.</span></span>
6. <span data-ttu-id="d8a15-115">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="d8a15-115">Click New.</span></span>
7. <span data-ttu-id="d8a15-116">Digitare un valore nel campo Tipo di ubicazione.</span><span class="sxs-lookup"><span data-stu-id="d8a15-116">In the Location type field, type a value.</span></span>
    * <span data-ttu-id="d8a15-117">Se si seleziona un tipo di ubicazione, viene impostata una restrizione in cui gli articoli possono essere inseriti dopo che sono stati prelevati.</span><span class="sxs-lookup"><span data-stu-id="d8a15-117">If you select a location type, this sets a restriction on where items can be put after they've been picked.</span></span> <span data-ttu-id="d8a15-118">Questa impostazione viene utilizzata quando una direttiva ubicazione prova a risolvere l'ubicazione o se un addetto al magazzino fornisce manualmente l'ubicazione per la voce di menu del dispositivo mobile.</span><span class="sxs-lookup"><span data-stu-id="d8a15-118">This setting is used when a location directive tries to resolve the location, or if a warehouse worker manually provides the location for the mobile device menu item.</span></span>  
8. <span data-ttu-id="d8a15-119">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="d8a15-119">Close the page.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]