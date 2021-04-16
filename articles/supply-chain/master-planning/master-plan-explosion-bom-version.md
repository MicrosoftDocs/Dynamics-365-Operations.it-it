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
ms.openlocfilehash: 367b662a43b3c3255632f20aeb821b973b04d890
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5833595"
---
# <a name="explosion-of-a-bom-version"></a><span data-ttu-id="9220a-103">Esplosione di una versione DBA</span><span class="sxs-lookup"><span data-stu-id="9220a-103">Explosion of a BOM version</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9220a-104">Questo articolo descrive uno scenario di pianificazione generale che include l'esplosione di una versione di distinta base (DBA).</span><span class="sxs-lookup"><span data-stu-id="9220a-104">This article explains a master planning scenario that involves explosion of a bill of materials (BOM) version.</span></span>

<span data-ttu-id="9220a-105">Un'esplosione della domanda di una versione DBA (distinta base) crea una domanda per ciascun articolo della riga DBA in un sito specifico e, probabilmente, in un magazzino specifico.</span><span class="sxs-lookup"><span data-stu-id="9220a-105">A demand explosion of a bill of materials (BOM) version creates a demand for each BOM line item at a specific site and, possibly, at a specific warehouse.</span></span> <span data-ttu-id="9220a-106">In una DBA specifica del sito può essere definito un magazzino specifico per ogni riga DBA.</span><span class="sxs-lookup"><span data-stu-id="9220a-106">In a site-specific BOM, a specific warehouse can be defined for each BOM line.</span></span> <span data-ttu-id="9220a-107">Inoltre, per ogni riga DBA, le impostazioni delle dimensioni dell'articolo determinano la necessità o meno del magazzino.</span><span class="sxs-lookup"><span data-stu-id="9220a-107">Additionally, for each BOM line, the item's dimension settings determine whether the warehouse is required.</span></span> <span data-ttu-id="9220a-108">La domanda risultante per ciascun elemento della riga DBA diventa, quindi, il punto di inizio per un'ulteriore esplosione della domanda.</span><span class="sxs-lookup"><span data-stu-id="9220a-108">The resulting demand for each BOM line item then becomes the starting point for additional demand explosion.</span></span> <span data-ttu-id="9220a-109">In questo scenario di pianificazione generale sono previste le seguenti condizioni:</span><span class="sxs-lookup"><span data-stu-id="9220a-109">This master planning scenario involves the following conditions:</span></span>

-   <span data-ttu-id="9220a-110">La dimensione sito è obbligatoria e deve essere immessa nella transazione relativa alla domanda.</span><span class="sxs-lookup"><span data-stu-id="9220a-110">The site dimension is mandatory and must be entered on the demand transaction.</span></span>
-   <span data-ttu-id="9220a-111">La dimensione sito è coerente.</span><span class="sxs-lookup"><span data-stu-id="9220a-111">The site dimension is consistent.</span></span> <span data-ttu-id="9220a-112">Di conseguenza, il sito relativo alla domanda di livello inferiore corrisponde a quello riportato nella transazione della domanda iniziale.</span><span class="sxs-lookup"><span data-stu-id="9220a-112">Therefore, the site for lower-level demand is the same as the site on the initial demand transaction.</span></span>

<span data-ttu-id="9220a-113">Nella figura riportata di seguito è illustrato il processo di esplosione della domanda nella pianificazione generale.</span><span class="sxs-lookup"><span data-stu-id="9220a-113">The following illustration shows how the process for master planning demand explosion.</span></span> ![Esplosione della domanda mediante una versione DBA](./media/multisitedemandexplosionscenariousingbomversion.gif)

<a name="additional-resources"></a><span data-ttu-id="9220a-115">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="9220a-115">Additional resources</span></span>
--------

[<span data-ttu-id="9220a-116">Determinare la versione DBA</span><span class="sxs-lookup"><span data-stu-id="9220a-116">Determine the BOM version</span></span>](master-plan-bom-version-determined.md)

[<span data-ttu-id="9220a-117">Panoramica pianificazione generale e funzionalità multisito</span><span class="sxs-lookup"><span data-stu-id="9220a-117">Master planning and multisite functionality overview</span></span>](master-plan-multisite-functionality.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]