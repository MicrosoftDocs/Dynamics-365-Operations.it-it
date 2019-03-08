---
title: Creare un profilo di ubicazione
description: Ogni ubicazione del magazzino deve disporre di un profilo che descrive le proprietà dell'ubicazione, ad esempio, se l'ubicazione consente articoli combinati.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSLocationProfile
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mirzaab
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8bc7705b7db46af8fbe8bf9e78a878a53249b452
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2019
ms.locfileid: "361385"
---
# <a name="create-a-location-profile"></a><span data-ttu-id="552db-103">Creare un profilo di ubicazione</span><span class="sxs-lookup"><span data-stu-id="552db-103">Create a location profile</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="552db-104">Ogni ubicazione del magazzino deve disporre di un profilo che descrive le proprietà dell'ubicazione, ad esempio, se l'ubicazione consente articoli combinati.</span><span class="sxs-lookup"><span data-stu-id="552db-104">Every location in the warehouse needs to have a location profile associated with it that describes the properties of the location, for example, whether the location allows mixed items.</span></span> <span data-ttu-id="552db-105">In questa procedura creeremo il profilo per una ubicazione non richiede il controllo targa.</span><span class="sxs-lookup"><span data-stu-id="552db-105">In this procedure we’ll create a profile for a location that doesn’t require license plate control.</span></span> <span data-ttu-id="552db-106">Permetteremo articoli misti e stati inventario combinati e permettiamo il conteggio ciclo.</span><span class="sxs-lookup"><span data-stu-id="552db-106">We’ll enable mixed items, and mixed inventory statuses, and allow cycle counting.</span></span> <span data-ttu-id="552db-107">È possibile utilizzare questa procedura nella società di dati dimostrativi USMF.</span><span class="sxs-lookup"><span data-stu-id="552db-107">You can use this procedure in the USMF demo data company.</span></span>

1. <span data-ttu-id="552db-108">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="552db-108">Click New.</span></span>
2. <span data-ttu-id="552db-109">Nel campo ID profilo ubicazione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="552db-109">In the Location profile ID field, type a value.</span></span>
3. <span data-ttu-id="552db-110">Digitare un valore nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="552db-110">In the Name field, type a value.</span></span>
4. <span data-ttu-id="552db-111">Nel campo Formato ubicazione immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="552db-111">In the Location format field, enter or select a value.</span></span>
5. <span data-ttu-id="552db-112">Nel campo Tipo di ubicazione immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="552db-112">In the Location type field, enter or select a value.</span></span>
6. <span data-ttu-id="552db-113">Nel campo ID profilo gestione banchine, immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="552db-113">In the Dock management profile ID field, enter or select a value.</span></span>
7. <span data-ttu-id="552db-114">Selezionare Sì nel campo Consenti articoli combinati.</span><span class="sxs-lookup"><span data-stu-id="552db-114">Select Yes in the Allow mixed items field.</span></span>
8. <span data-ttu-id="552db-115">Selezionare Sì nel campo Consenti stati inventario combinati.</span><span class="sxs-lookup"><span data-stu-id="552db-115">Select Yes in the Allow mixed  inventory statuses field.</span></span>
9. <span data-ttu-id="552db-116">Selezionare Sì nel campo Consenti conteggio ciclo.</span><span class="sxs-lookup"><span data-stu-id="552db-116">Select Yes in the Allow cycle counting field.</span></span>
10. <span data-ttu-id="552db-117">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="552db-117">Click Save.</span></span>
11. <span data-ttu-id="552db-118">Andare a Gestione magazzino > Impostazioni > Magazzino > Profili ubicazione.</span><span class="sxs-lookup"><span data-stu-id="552db-118">Go to Warehouse management > Setup > Warehouse > Location profiles.</span></span>

