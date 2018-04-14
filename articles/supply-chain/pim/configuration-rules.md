---
title: Regole di configurazione
description: Questo articolo fornisce informazioni generali sulle regole di configurazione. Le regole di configurazione definiscono le relazioni tra gli articoli in una distinta base (DBA) per i prodotti che utilizzano la tecnologia di configurazione in base alle dimensioni.
author: cvocph
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BOMConfigRule
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 19761
ms.assetid: e4c6622d-1e2d-4a4d-8047-c553a25d4f87
ms.search.region: Global
ms.author: conradv
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 87927f5bddbf11c224c77cff7c5355f2cd1317a6
ms.contentlocale: it-it
ms.lasthandoff: 04/13/2018

---

# <a name="configuration-rules"></a><span data-ttu-id="db521-104">Regole di configurazione</span><span class="sxs-lookup"><span data-stu-id="db521-104">Configuration rules</span></span>

[!INCLUDE [banner](../includes/banner.md)]

<span data-ttu-id="db521-105">Questo articolo fornisce informazioni generali sulle regole di configurazione.</span><span class="sxs-lookup"><span data-stu-id="db521-105">This article provides general information about configuration rules.</span></span> <span data-ttu-id="db521-106">Le regole di configurazione definiscono le relazioni tra gli articoli in una distinta base (DBA) per i prodotti che utilizzano la tecnologia di configurazione in base alle dimensioni.</span><span class="sxs-lookup"><span data-stu-id="db521-106">Configuration rules define relationships between items in a bill of materials (BOM) for products that use the dimension-based configuration technology.</span></span>

<span data-ttu-id="db521-107">Le regole di configurazione sono disponibili quando si definiscono i modelli di configurazione basata su dimensioni.</span><span class="sxs-lookup"><span data-stu-id="db521-107">Configuration rules are available when you define dimension-based configuration models.</span></span> <span data-ttu-id="db521-108">Le regole di configurazione vengono utilizzate per applicare o proibire combinazioni di articoli specifici in una distinta base (DBA).</span><span class="sxs-lookup"><span data-stu-id="db521-108">Configuration rules are used to either enforce or prohibit specific item combinations in a bill of materials (BOM).</span></span> <span data-ttu-id="db521-109">Dopo che una DBA è stata creata e gli articoli rilevanti sono stati assegnati ai rispettivi gruppi di configurazioni, una o più regole di configurazione possono essere definite.</span><span class="sxs-lookup"><span data-stu-id="db521-109">After a BOM has been created and the relevant items have been assigned to their respective configuration groups, one or more configuration rules can be defined.</span></span> <span data-ttu-id="db521-110">Se due articoli appartengono l'uno all'altro, l'operatore **Seleziona** viene utilizzato per garantire l'inclusione.</span><span class="sxs-lookup"><span data-stu-id="db521-110">If two items belong together, the **Select** operator is used to ensure inclusion.</span></span> <span data-ttu-id="db521-111">Se due articoli si escludono reciprocamente, l'operatore **Deseleziona** viene utilizzato per garantire l'esclusione.</span><span class="sxs-lookup"><span data-stu-id="db521-111">If two items are mutually exclusive, the **Deselect** operator is used to ensure exclusion.</span></span>  

<span data-ttu-id="db521-112">**Nota:** queste informazioni si applicano solo a rappresentazioni generali prodotto che utilizzano la tecnologia di configurazione basata su dimensioni.</span><span class="sxs-lookup"><span data-stu-id="db521-112">**Note:** This information applies only to product masters that use the dimension-based configuration technology.</span></span>  

<span data-ttu-id="db521-113">Le modifiche apportate successivamente alle regole di configurazione non interessano le configurazioni esistenti.</span><span class="sxs-lookup"><span data-stu-id="db521-113">Existing configurations aren't affected by subsequent changes to the configuration rules.</span></span> <span data-ttu-id="db521-114">È pertanto importante impostare le regole prima di definire una nuova configurazione e verificarle se si ritiene che siano state modificate.</span><span class="sxs-lookup"><span data-stu-id="db521-114">However, it's important that you set the rules before you define a new configuration, and that you check the rules if you think they have been changed.</span></span>  

<span data-ttu-id="db521-115">**Nota:** il metodo **Seleziona** determina la selezione automatica del gruppo di configurazione derivato, del numero di articolo e della configurazione,</span><span class="sxs-lookup"><span data-stu-id="db521-115">**Note:** For the **Select** method, the derived configuration group, item number, and configuration are automatically selected.</span></span> <span data-ttu-id="db521-116">mentre se si utilizza il metodo **Deseleziona** il gruppo di configurazione derivato, il numero di articolo e la configurazione non possono essere selezionati.</span><span class="sxs-lookup"><span data-stu-id="db521-116">For the **Deselect** method, the derived configuration group, item number, and configuration can't be selected.</span></span>

<a name="see-also"></a><span data-ttu-id="db521-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="db521-117">See also</span></span>
--------

[<span data-ttu-id="db521-118">Configurazione prodotto basata su dimensioni</span><span class="sxs-lookup"><span data-stu-id="db521-118">Dimension-based product configuration</span></span>](dimension-based-product-configuration.md)




