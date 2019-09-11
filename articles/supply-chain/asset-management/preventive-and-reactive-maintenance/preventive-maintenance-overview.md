---
title: Panoramica della manutenzione preventiva
description: In questo argomento viene descritta la manutenzione preventiva in Gestione cespiti.
author: josaw1
manager: AnnBe
ms.date: 08/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-15
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 3b43c795426f40cb43962976824c44a7702d91b7
ms.sourcegitcommit: f5bfa3212bc3ef7d944a358ef08fe8863fd93b91
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/16/2019
ms.locfileid: "1875724"
---
# <a name="preventive-maintenance-overview"></a><span data-ttu-id="c502e-103">Panoramica della manutenzione preventiva</span><span class="sxs-lookup"><span data-stu-id="c502e-103">Preventive maintenance overview</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

<span data-ttu-id="c502e-104">In questo argomento viene descritta la manutenzione preventiva in Gestione cespiti.</span><span class="sxs-lookup"><span data-stu-id="c502e-104">This topic explains preventive maintenance in Asset Management.</span></span> <span data-ttu-id="c502e-105">La manutenzione preventiva è una disciplina che comporta processi di manutenzione pianificati, ad esempio, assistenza, calibrazione e ispezioni regolari.</span><span class="sxs-lookup"><span data-stu-id="c502e-105">Preventive maintenance is a discipline involving planned maintenance jobs, for example, regular service, calibration, and inspections.</span></span> <span data-ttu-id="c502e-106">In **Gestione cespiti**, è possibile creare piani di manutenzione e impostarli nei cespiti e nelle unità funzionali.</span><span class="sxs-lookup"><span data-stu-id="c502e-106">In **Asset Management**, you can create maintenance plans and set them up on assets and functional locations.</span></span> <span data-ttu-id="c502e-107">È anche possibile impostare cicli di manutenzione in unità funzionali.</span><span class="sxs-lookup"><span data-stu-id="c502e-107">You can also set up maintenance rounds on functional locations.</span></span> <span data-ttu-id="c502e-108">I piani di manutenzione nei cespiti sono attivi indipendentemente da dove il cespite è installato.</span><span class="sxs-lookup"><span data-stu-id="c502e-108">Maintenance plans on assets are active regardless of where the asset is installed.</span></span> <span data-ttu-id="c502e-109">I piani di manutenzione e i cicli di manutenzione nell'unità funzionale sono attivi per i cespiti attualmente installati nell'unità.</span><span class="sxs-lookup"><span data-stu-id="c502e-109">Maintenance plans and maintenance rounds on functional location are active for the assets currently installed at the location.</span></span> <span data-ttu-id="c502e-110">Anziché installare piani di manutenzione nei cespiti o cicli di manutenzione nelle unità funzionali, è possibile creare cicli di manutenzione che includono più cespiti in cui è necessario eseguire tipi di processo di manutenzione correlati nella stessa routine di lavoro.</span><span class="sxs-lookup"><span data-stu-id="c502e-110">Instead of setting up maintenance plans on assets, or setting up maintenance rounds on functional locations, you can create maintenance rounds that include multiple assets on which you need to perform related types of maintenance jobs in the same work routine.</span></span> <span data-ttu-id="c502e-111">Creare cicli di manutenzione a partire da cespiti - anziché nelle unità funzionali - significa che è possibile selezionare una serie di cespiti per un ciclo di manutenzione, che non sono installati nella stessa unità funzionale.</span><span class="sxs-lookup"><span data-stu-id="c502e-111">Maintenance rounds created from assets - instead of created on functional locations - means that you can select a number of assets for one maintenance round, which are not installed on the same functional location.</span></span>

<span data-ttu-id="c502e-112">I piani di manutenzione sono utilizzati per la manutenzione preventiva e reattiva in singoli cespiti.</span><span class="sxs-lookup"><span data-stu-id="c502e-112">Maintenance plans are used for preventive and reactive maintenance on individual assets.</span></span> <span data-ttu-id="c502e-113">I cicli di manutenzione sono utilizzati per la manutenzione preventiva in un gruppo o un set di cespiti.</span><span class="sxs-lookup"><span data-stu-id="c502e-113">Maintenance rounds are used for preventive maintenance on a group or a set of assets.</span></span> <span data-ttu-id="c502e-114">I piani e i cicli di manutenzione sono utilizzati per generare proposte di ordini di lavoro.</span><span class="sxs-lookup"><span data-stu-id="c502e-114">Maintenance plans and maintenance rounds are used for generating work order proposals.</span></span> <span data-ttu-id="c502e-115">Le proposte di ordine di lavoro vengono salvate come righe di programma di manutenzione, che possono essere aggregate e convertite in ordini di lavoro.</span><span class="sxs-lookup"><span data-stu-id="c502e-115">The work order proposals are saved as maintenance schedule lines, which can be bundled and converted into work orders.</span></span>

<span data-ttu-id="c502e-116">Nella figura seguente viene fornita una panoramica del flusso di lavoro dalla creazione di piani di manutenzione e cicli di manutenzione alla creazione di ordini di lavoro per cespiti, in base a questi piani e cicli di manutenzione.</span><span class="sxs-lookup"><span data-stu-id="c502e-116">The figure below provides an overview of the work flow from creating maintenance plans and maintenance rounds to creating work orders for assets, based on those maintenance plans and maintenance rounds.</span></span>

![Figura 1](media/01-preventive-maintenance.png)

