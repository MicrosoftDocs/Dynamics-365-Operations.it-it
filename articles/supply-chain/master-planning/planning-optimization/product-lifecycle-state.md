---
title: Escludere i prodotti con specifici stati del ciclo di vita del prodotto
description: Questo argomento spiega come escludere i prodotti in base al loro stato del ciclo di vita quando viene utilizzata la funzionalità Ottimizzazione pianificazione.
author: ChristianRytt
manager: tfehr
ms.date: 11/13/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2019-11-13
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 371d98eefa482fc3e430f2f0977ddffb9dd0d30e
ms.sourcegitcommit: deb711c92251ed48cdf20ea514d03461c26a2262
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/25/2020
ms.locfileid: "4645094"
---
# <a name="exclude-products-that-have-specific-product-lifecycle-states"></a><span data-ttu-id="b5214-103">Escludere i prodotti con specifici stati del ciclo di vita del prodotto</span><span class="sxs-lookup"><span data-stu-id="b5214-103">Exclude products that have specific product lifecycle states</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="b5214-104">I prodotti rilasciati e le versioni del prodotto rilasciate includono un campo **Stato del ciclo di vita del prodotto**.</span><span class="sxs-lookup"><span data-stu-id="b5214-104">Released products and released product versions include a **Product lifecycle state** field.</span></span> <span data-ttu-id="b5214-105">Questo campo consente di controllare, tra le altre cose, quali prodotti sono inclusi durante la pianificazione generale.</span><span class="sxs-lookup"><span data-stu-id="b5214-105">This field lets you control, among other things, which products are included during master planning.</span></span> <span data-ttu-id="b5214-106">È possibile aggiungere, rimuovere e modificare gli stati del ciclo di vita come richiesto andando a **Gestione informazioni sul prodotto \> Impostazione \> Stato del ciclo di vita del prodotto**.</span><span class="sxs-lookup"><span data-stu-id="b5214-106">You can add, remove, and edit lifecycle states as required by going to **Product information management \> Setup \> Product lifecycle state**.</span></span> <span data-ttu-id="b5214-107">Per ogni stato del ciclo di vita del prodotto, impostare l'opzione **Attivo per la pianificazione** su *Sì* se i prodotti con tale stato devono essere inclusi durante la pianificazione generale.</span><span class="sxs-lookup"><span data-stu-id="b5214-107">For each product lifecycle state, set the **Is active for planning** option to *Yes* if products that have that state should be included during master planning.</span></span> <span data-ttu-id="b5214-108">Quando l'opzione è impostata su *No*, i prodotti e le varianti associati verranno esclusi da tutta la pianificazione generale e da tutti i calcoli a livello di distinta base (DBA).</span><span class="sxs-lookup"><span data-stu-id="b5214-108">When the option is set to *No*, the associated products and variants will be excluded from all master planning and all calculations at the bill of materials (BOM) level.</span></span>

<span data-ttu-id="b5214-109">I prodotti e le varianti rilasciati in cui il campo **Stato del ciclo di vita del prodotto** viene lasciato vuoto vengono trattati come se avessero uno stato del ciclo di vita del prodotto in cui l'opzione **Attivo per la pianificazione** è impostata su *Sì*.</span><span class="sxs-lookup"><span data-stu-id="b5214-109">Released products and variants where the **Product lifecycle state** field is left blank are treated as though they have a product lifecycle state where the **Is active for planning** option is set to *Yes*.</span></span> <span data-ttu-id="b5214-110">In altre parole, saranno inclusi durante la pianificazione generale.</span><span class="sxs-lookup"><span data-stu-id="b5214-110">In other words, they will be included during master planning.</span></span>

> [!NOTE]
> <span data-ttu-id="b5214-111">Per evitare suggerimenti di offerta non necessari, si consiglia vivamente di associare tutti i prodotti e le varianti rilasciati obsoleti a uno stato del ciclo di vita del prodotto in cui l'opzione **Attivo per la pianificazione** è impostata su *No*.</span><span class="sxs-lookup"><span data-stu-id="b5214-111">To help avoid unnecessary supply suggestions, we strongly recommend that you associate all obsolete released products and variants with a product lifecycle state where the **Is active for planning** option is set to *No*.</span></span> <span data-ttu-id="b5214-112">Questo approccio è particolarmente importante quando si lavora con varianti di configurazione del prodotto che non sono riutilizzabili, perché aiuterà a prevenire gli sprechi.</span><span class="sxs-lookup"><span data-stu-id="b5214-112">This approach is especially important when you work with product configuration variants that aren't reusable, because it will help prevent waste.</span></span>

## <a name="related-resources"></a><span data-ttu-id="b5214-113">Risorse correlate</span><span class="sxs-lookup"><span data-stu-id="b5214-113">Related resources</span></span>

<span data-ttu-id="b5214-114">Per ulteriori informazioni relative agli stati del ciclo di vita del prodotto, vedere [Panoramica dello stato del ciclo di vita del prodotto](../../pim/product-lifecycle.md).</span><span class="sxs-lookup"><span data-stu-id="b5214-114">For more information about product lifecycle states, see [Product lifecycle state overview](../../pim/product-lifecycle.md).</span></span>

<span data-ttu-id="b5214-115">Per informazioni dettagliate che includono i passaggi per utilizzare gli stati del ciclo di vita del prodotto per escludere i prodotti dalla pianificazione generale e dal calcolo a livello di DBA, vedere [Creare uno stato del ciclo di vita del prodotto per escludere i prodotti dalla pianificazione generale](../../pim/tasks/exclude-products-master-planning.md).</span><span class="sxs-lookup"><span data-stu-id="b5214-115">For detailed information that includes steps for using product lifecycle states to exclude products from master planning and BOM-level calculations, see [Create a product lifecycle state to exclude products from Master planning](../../pim/tasks/exclude-products-master-planning.md).</span></span>
