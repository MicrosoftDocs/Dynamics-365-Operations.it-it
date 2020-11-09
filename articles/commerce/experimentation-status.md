---
title: Esaminare lo stato di un esperimento
description: In questo argomento viene descritto lo stato di un esperimento nel ciclo di vita della sperimentazione in Dynamics 365 Commerce.
author: sushma-rao
manager: AnnBe
ms.date: 10/21/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: sushmar
ms.search.validFrom: 2020-09-30
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: eea67ddc1718902198b74614ee1a910fc6e29c1d
ms.sourcegitcommit: 7592c2dec0428d56843ab395d2a52c89f77f99b5
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2020
ms.locfileid: "4097072"
---
# <a name="review-the-status-of-an-experiment"></a><span data-ttu-id="c4efc-103">Esaminare lo stato di un esperimento</span><span class="sxs-lookup"><span data-stu-id="c4efc-103">Review the status of an experiment</span></span>
<span data-ttu-id="c4efc-104">La configurazione e l'esecuzione di un esperimento in Dynamics 365 Commerce comportano molti passaggi.</span><span class="sxs-lookup"><span data-stu-id="c4efc-104">There are many steps involved in setting up and running an experiment in Dynamics 365 Commerce.</span></span> <span data-ttu-id="c4efc-105">Per informazioni sul ciclo di vita della sperimentazione, vedi [Sperimentazione in Dynamics 365 Commerce](experimentation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="c4efc-105">For information about the experimentation lifecycle, see [Experimentation in Dynamics 365 Commerce](experimentation-overview.md).</span></span>

<span data-ttu-id="c4efc-106">Per sapere dove si trova un esperimento nel ciclo di vita, in Creazione di siti Web di Commerce selezionare **Esperimenti** nel riquadro di spostamento a sinistra.</span><span class="sxs-lookup"><span data-stu-id="c4efc-106">To learn where an experiment is in the lifecycle, in Commerce site builder select **Experiments** in the left navigation pane.</span></span> <span data-ttu-id="c4efc-107">Viene visualizzato un elenco di esperimenti con lo stato di ogni esperimento sia in Commerce che nel servizio di terze parti utilizzato per consentire la creazione di esperimenti, assegnare varianti e analizzare dati.</span><span class="sxs-lookup"><span data-stu-id="c4efc-107">A list of experiments is displayed with the status of each experiment in both Commerce and the third-party service that is being used to enable the creation of experiments, assign variations, and analyze data.</span></span>

<span data-ttu-id="c4efc-108">Nella colonna **Stato Commerce** , possono essere visualizzati i seguenti valori.</span><span class="sxs-lookup"><span data-stu-id="c4efc-108">In the **Commerce status** column, the following values may be displayed.</span></span> 
- <span data-ttu-id="c4efc-109">**Bozza** - L'esperimento è collegato a una pagina o a un frammento in Commerce ed è in fase di modifica.</span><span class="sxs-lookup"><span data-stu-id="c4efc-109">**Draft** - The experiment is connected to a page or fragment in Commerce and is being edited.</span></span>
- <span data-ttu-id="c4efc-110">**Pubblicato** - Le varianti dell'esperimento sono pronte per essere visualizzate sul sito web.</span><span class="sxs-lookup"><span data-stu-id="c4efc-110">**Published** - The experiment variations are ready to be displayed on your website.</span></span> <span data-ttu-id="c4efc-111">Se l'esperimento è in esecuzione nel servizio di terze parti, gli utenti del sito web vedranno una variante della pagina o del frammento come selezionato dal servizio di terze parti.</span><span class="sxs-lookup"><span data-stu-id="c4efc-111">If the experiment is running in the third-party service, website users will see a variation of the page or fragment as selected by the third-party service.</span></span>
- <span data-ttu-id="c4efc-112">**Non pubblicato** - L'esperimento non è più disponibile sul sito web.</span><span class="sxs-lookup"><span data-stu-id="c4efc-112">**Unpublished** - The experiment is no longer available on your website.</span></span> <span data-ttu-id="c4efc-113">Se l'esperimento è in esecuzione nel servizio di terze parti, gli utenti del sito web vedranno una variante predefinita della pagina o del frammento.</span><span class="sxs-lookup"><span data-stu-id="c4efc-113">Website users will only see the default version of the page or fragment even if the experiment is running in the third-party service.</span></span>
- <span data-ttu-id="c4efc-114">**Completato** - L'esperimento è stato completato e la variante è ora live per tutti gli utenti del sito web.</span><span class="sxs-lookup"><span data-stu-id="c4efc-114">**Completed** - The experiment has run its course and a variation was promoted to live for all website users.</span></span>

<span data-ttu-id="c4efc-115">Allo stesso modo, nella colonna **Stato terze parti** , i seguenti valori potrebbero essere visualizzati per indicare lo stato degli esperimenti nel servizio di terze parti.</span><span class="sxs-lookup"><span data-stu-id="c4efc-115">Similarly, in the **third-party status** column, the following values may be displayed to indicate what status the experiments are in the third-party service.</span></span>
- <span data-ttu-id="c4efc-116">**Bozza** - L'esperimento è configurato nel servizio di terze parti ma non è stato avviato.</span><span class="sxs-lookup"><span data-stu-id="c4efc-116">**Draft** - The experiment is set up in the third-party service but hasn't been started.</span></span>
- <span data-ttu-id="c4efc-117">**In esecuzione** - L'esperimento è stato avviato nel servizio di terze parti e sta raccogliendo dati.</span><span class="sxs-lookup"><span data-stu-id="c4efc-117">**Running** - The experiment was started in the third-party service and is collecting data.</span></span>
- <span data-ttu-id="c4efc-118">**In sospeso** - L'esperimento è sospeso e non raccoglie dati.</span><span class="sxs-lookup"><span data-stu-id="c4efc-118">**Paused** - The experiment is paused and not collecting data.</span></span> <span data-ttu-id="c4efc-119">Devi riprendere l'esperimento affinché raccolga nuovamente i dati.</span><span class="sxs-lookup"><span data-stu-id="c4efc-119">You must resume the experiment for it to collect data again.</span></span>
- <span data-ttu-id="c4efc-120">**Archiviato** - L'esperimento è stato completato ed è stato catalogato nel servizio di terze parti per riferimento futuro.</span><span class="sxs-lookup"><span data-stu-id="c4efc-120">**Archived** - The experiment has run its course and has been cataloged in the third-party service for future reference.</span></span>

<span data-ttu-id="c4efc-121">Il diagramma seguente mostra entrambi i gruppi di stati e il modo in cui si relazionano tra loro.</span><span class="sxs-lookup"><span data-stu-id="c4efc-121">The diagram below shows both sets of statuses and how they relate to each other.</span></span>

<span data-ttu-id="c4efc-122">[ ![Stati della sperimentazione](./media/experimentation_statuses.svg) ](./media/experimentation_statuses.svg#lightbox)</span><span class="sxs-lookup"><span data-stu-id="c4efc-122">[ ![Experimentation statuses](./media/experimentation_statuses.svg) ](./media/experimentation_statuses.svg#lightbox)</span></span>
