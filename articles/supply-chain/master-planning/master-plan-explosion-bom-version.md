---
title: Esplosione di una versione DBA
description: Questo articolo descrive uno scenario di pianificazione generale che include l'esplosione di una versione di distinta base (DBA).
author: roxanadiaconu
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqTransExplosion
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19211
ms.assetid: fe08c2e6-9cc5-4e34-bbb2-cd07843403b5
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 17e5d8638dc02d92a0c67364790353833551250f
ms.sourcegitcommit: ff09736563d3cd2bc74c7664edd1767b218401cb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2021
ms.locfileid: "6187412"
---
# <a name="explosion-of-a-bom-version"></a><span data-ttu-id="85e66-103">Esplosione di una versione DBA</span><span class="sxs-lookup"><span data-stu-id="85e66-103">Explosion of a BOM version</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="85e66-104">Questo articolo descrive uno scenario di pianificazione generale che include l'esplosione di una versione di distinta base (DBA).</span><span class="sxs-lookup"><span data-stu-id="85e66-104">This article explains a master planning scenario that involves explosion of a bill of materials (BOM) version.</span></span>

<span data-ttu-id="85e66-105">Un'esplosione della domanda di una versione DBA (distinta base) crea una domanda per ciascun articolo della riga DBA in un sito specifico e, probabilmente, in un magazzino specifico.</span><span class="sxs-lookup"><span data-stu-id="85e66-105">A demand explosion of a bill of materials (BOM) version creates a demand for each BOM line item at a specific site and, possibly, at a specific warehouse.</span></span> <span data-ttu-id="85e66-106">In una DBA specifica del sito può essere definito un magazzino specifico per ogni riga DBA.</span><span class="sxs-lookup"><span data-stu-id="85e66-106">In a site-specific BOM, a specific warehouse can be defined for each BOM line.</span></span> <span data-ttu-id="85e66-107">Inoltre, per ogni riga DBA, le impostazioni delle dimensioni dell'articolo determinano la necessità o meno del magazzino.</span><span class="sxs-lookup"><span data-stu-id="85e66-107">Additionally, for each BOM line, the item's dimension settings determine whether the warehouse is required.</span></span> <span data-ttu-id="85e66-108">La domanda risultante per ciascun elemento della riga DBA diventa, quindi, il punto di inizio per un'ulteriore esplosione della domanda.</span><span class="sxs-lookup"><span data-stu-id="85e66-108">The resulting demand for each BOM line item then becomes the starting point for additional demand explosion.</span></span> <span data-ttu-id="85e66-109">In questo scenario di pianificazione generale sono previste le seguenti condizioni:</span><span class="sxs-lookup"><span data-stu-id="85e66-109">This master planning scenario involves the following conditions:</span></span>

-   <span data-ttu-id="85e66-110">La dimensione sito è obbligatoria e deve essere immessa nella transazione relativa alla domanda.</span><span class="sxs-lookup"><span data-stu-id="85e66-110">The site dimension is mandatory and must be entered on the demand transaction.</span></span>
-   <span data-ttu-id="85e66-111">La dimensione sito è coerente.</span><span class="sxs-lookup"><span data-stu-id="85e66-111">The site dimension is consistent.</span></span> <span data-ttu-id="85e66-112">Di conseguenza, il sito relativo alla domanda di livello inferiore corrisponde a quello riportato nella transazione della domanda iniziale.</span><span class="sxs-lookup"><span data-stu-id="85e66-112">Therefore, the site for lower-level demand is the same as the site on the initial demand transaction.</span></span>

<span data-ttu-id="85e66-113">Nella figura riportata di seguito è illustrato il processo di esplosione della domanda nella pianificazione generale.</span><span class="sxs-lookup"><span data-stu-id="85e66-113">The following illustration shows how the process for master planning demand explosion.</span></span> ![Esplosione della domanda mediante una versione DBA](./media/multisitedemandexplosionscenariousingbomversion.gif)

## <a name="additional-resources"></a><span data-ttu-id="85e66-115">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="85e66-115">Additional resources</span></span>

[<span data-ttu-id="85e66-116">Determinare la versione DBA</span><span class="sxs-lookup"><span data-stu-id="85e66-116">Determine the BOM version</span></span>](master-plan-bom-version-determined.md)

[<span data-ttu-id="85e66-117">Panoramica pianificazione generale e funzionalità multisito</span><span class="sxs-lookup"><span data-stu-id="85e66-117">Master planning and multisite functionality overview</span></span>](master-plan-multisite-functionality.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]