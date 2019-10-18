---
title: Creare un profilo di ubicazione
description: In questo argomento viene illustrato come creare un profilo di ubicazione in Dynamics 365 Supply Chain Management.
author: ShylaThompson
manager: AnnBe
ms.date: 07/29/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSLocationProfile
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mirzaab
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 36bad7424ac247b8fd9a819928837de619e9e258
ms.sourcegitcommit: f87de0f949b5d60993b19e0f61297f02d42b5bef
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/24/2019
ms.locfileid: "2026787"
---
# <a name="create-a-location-profile"></a><span data-ttu-id="c4def-103">Creare un profilo di ubicazione</span><span class="sxs-lookup"><span data-stu-id="c4def-103">Create a location profile</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="c4def-104">In questo argomento viene illustrato come creare un profilo di ubicazione in Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="c4def-104">This topic explains how to create a location profile in Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="c4def-105">Ogni ubicazione del magazzino deve disporre di un profilo che descrive le proprietà dell'ubicazione, ad esempio, se l'ubicazione consente articoli combinati.</span><span class="sxs-lookup"><span data-stu-id="c4def-105">Every location in the warehouse needs to have a location profile associated with it that describes the properties of the location, for example, whether the location allows mixed items.</span></span> <span data-ttu-id="c4def-106">In questa procedura creeremo il profilo per una ubicazione non richiede il controllo targa.</span><span class="sxs-lookup"><span data-stu-id="c4def-106">In this procedure we’ll create a profile for a location that doesn’t require license plate control.</span></span> <span data-ttu-id="c4def-107">Permetteremo articoli misti e stati inventario combinati e permettiamo il conteggio ciclo.</span><span class="sxs-lookup"><span data-stu-id="c4def-107">We’ll enable mixed items, and mixed inventory statuses, and allow cycle counting.</span></span> <span data-ttu-id="c4def-108">È possibile utilizzare questa procedura nella società di dati dimostrativi USMF.</span><span class="sxs-lookup"><span data-stu-id="c4def-108">You can use this procedure in the USMF demo data company.</span></span>


1. <span data-ttu-id="c4def-109">Nel pannello di navigazione andare a **Moduli > Gestione magazzino > Impostazioni > Magazzino > Profili ubicazione**.</span><span class="sxs-lookup"><span data-stu-id="c4def-109">In the navigation pane, go to **Modules > Warehouse management > Setup > Warehouse > Location profiles**.</span></span>
2. <span data-ttu-id="c4def-110">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="c4def-110">Select **New**.</span></span>
3. <span data-ttu-id="c4def-111">Nel campo **ID profilo ubicazione** digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="c4def-111">In the **Location profile ID** field, type a value.</span></span>
4. <span data-ttu-id="c4def-112">Digitare un valore nel campo **Nome**.</span><span class="sxs-lookup"><span data-stu-id="c4def-112">In the **Name** field, type a value.</span></span>
5. <span data-ttu-id="c4def-113">Nel campo **Formato ubicazione** immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="c4def-113">In the **Location format** field, enter or select a value.</span></span>
6. <span data-ttu-id="c4def-114">Nel campo **Tipo di ubicazione** immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="c4def-114">In the **Location type** field, enter or select a value.</span></span>
7. <span data-ttu-id="c4def-115">Nel campo **ID profilo gestione banchine**, immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="c4def-115">In the **Dock management profile ID** field, enter or select a value.</span></span>
8. <span data-ttu-id="c4def-116">Selezionare **Sì** nel campo **Consenti articoli combinati**.</span><span class="sxs-lookup"><span data-stu-id="c4def-116">Select **Yes** in the **Allow mixed items** field.</span></span>
9. <span data-ttu-id="c4def-117">Selezionare **Sì** nel campo **Consenti stati inventario combinati**.</span><span class="sxs-lookup"><span data-stu-id="c4def-117">Select **Yes** in the **Allow mixed inventory statuses** field.</span></span>
10. <span data-ttu-id="c4def-118">Selezionare **Sì** nel campo **Consenti conteggio ciclo**.</span><span class="sxs-lookup"><span data-stu-id="c4def-118">Select **Yes** in the **Allow cycle counting** field.</span></span>
11. <span data-ttu-id="c4def-119">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="c4def-119">Select **Save**.</span></span>

