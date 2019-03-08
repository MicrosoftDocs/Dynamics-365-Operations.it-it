---
title: Aggiornare costi standard in un ambiente non di produzione
description: Questo articolo fornisce indicazioni per aggiornare i costi standard in un ambiente non di produzione.
author: AndersGirke
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CostingVersion, InventItemPrice
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 79723
ms.assetid: 7ba0c408-2450-4042-9542-6fdf83c12e6c
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4fa545aa6903bd6f789dda20ab5755ffe9a12b88
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2019
ms.locfileid: "323021"
---
# <a name="update-standard-costs-in-a-non-manufacturing-environment"></a><span data-ttu-id="081fe-103">Aggiornare costi standard in un ambiente non di produzione</span><span class="sxs-lookup"><span data-stu-id="081fe-103">Update standard costs in a non-manufacturing environment</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="081fe-104">Questo articolo fornisce indicazioni per aggiornare i costi standard in un ambiente non di produzione.</span><span class="sxs-lookup"><span data-stu-id="081fe-104">This article provides guidance for updating standard costs in a non-manufacturing environment.</span></span>

<span data-ttu-id="081fe-105">Nelle seguenti indicazioni si presuppone che venga utilizzato per l'aggiornamento dei costi standard un approccio basato su due versioni.</span><span class="sxs-lookup"><span data-stu-id="081fe-105">The following guidelines assume that you use a two-version approach to update standard cost.</span></span> <span data-ttu-id="081fe-106">Secondo questo approccio, una versione di determinazione costi contiene i costi standard inizialmente definiti per il periodo bloccato e la seconda versione di determinazione costi contiene gli aggiornamenti incrementali.</span><span class="sxs-lookup"><span data-stu-id="081fe-106">In this approach, one costing version contains the standard costs that were originally defined for the frozen period, and the second costing version contains the incremental updates.</span></span> <span data-ttu-id="081fe-107">Ogni aggiornamento viene immesso come record dei costi all'interno della seconda versione di determinazione costi e infine attivato.</span><span class="sxs-lookup"><span data-stu-id="081fe-107">Each update is entered as a cost record that is enclosed in the second costing version, and eventually it's enabled.</span></span> <span data-ttu-id="081fe-108">In alternativa, è possibile adottare un approccio basato su una sola versione, in cui si utilizza il set di costi standard definiti inizialmente.</span><span class="sxs-lookup"><span data-stu-id="081fe-108">An alternative, one-version approach uses the set of standard costs that was originally defined.</span></span> <span data-ttu-id="081fe-109">L'approccio basato su due versioni richiede la definizione di una seconda versione di determinazione costi.</span><span class="sxs-lookup"><span data-stu-id="081fe-109">The two-version approach requires that you define a second costing version.</span></span> <span data-ttu-id="081fe-110">Di seguito sono riportate le indicazioni per la definizione di tale versione.</span><span class="sxs-lookup"><span data-stu-id="081fe-110">Here are the guidelines for defining this costing version:</span></span>

-   <span data-ttu-id="081fe-111">Assegnare un tipo di determinazione costi per **Costi standard**.</span><span class="sxs-lookup"><span data-stu-id="081fe-111">Assign a costing type of **Standard costs**.</span></span>
-   <span data-ttu-id="081fe-112">Assegnare un identificatore significativo che indichi il contenuto della versione di determinazione costi, ad esempio **AGGIORNAMENTI-2016**.</span><span class="sxs-lookup"><span data-stu-id="081fe-112">Assign a meaningful identifier that indicates the contents of the costing version, such as **2016-UPDATES**.</span></span>
-   <span data-ttu-id="081fe-113">Assicurarsi che nel contenuto siano inclusi i record dei costi.</span><span class="sxs-lookup"><span data-stu-id="081fe-113">Make sure that the content includes cost records.</span></span>
-   <span data-ttu-id="081fe-114">Consentire l'immissione dei record dei costi per tutti i siti.</span><span class="sxs-lookup"><span data-stu-id="081fe-114">Allow cost records to be entered for all sites.</span></span> <span data-ttu-id="081fe-115">Se si specifica un sito, è possibile immettere i record dei costi solo per tale sito.</span><span class="sxs-lookup"><span data-stu-id="081fe-115">If you specify a site, cost records can be entered only for that site.</span></span>
-   <span data-ttu-id="081fe-116">Impostare il principio di fallback su **Nessuno**.</span><span class="sxs-lookup"><span data-stu-id="081fe-116">Indicate a fallback principle of **None**.</span></span> <span data-ttu-id="081fe-117">Tale principio si applica infatti solo al calcolo dei costi degli articoli prodotti.</span><span class="sxs-lookup"><span data-stu-id="081fe-117">The fallback principle applies only to cost calculations for manufactured items.</span></span>

<span data-ttu-id="081fe-118">Per correggere, rettificare o aggiornare i costi standard dei nuovi articoli, effettuare i passaggi riportati di seguito.</span><span class="sxs-lookup"><span data-stu-id="081fe-118">To correct, adjust, or update standard costs for new items, follow these steps.</span></span>

1.  <span data-ttu-id="081fe-119">Utilizzare la pagina **Impostazione versione di determinazione** **costi** per attivare i dati sui costi da inserire nella seconda versione di determinazione costi.</span><span class="sxs-lookup"><span data-stu-id="081fe-119">Use the **Costing version** **setup** page to enable cost data to be entered into the second costing version.</span></span> <span data-ttu-id="081fe-120">Impedire eventualmente l'attivazione dei costi in sospeso, con la possibilità di consentire l'attivazione dopo che i costi in sospeso siano stati definiti in modo completo e accurato.</span><span class="sxs-lookup"><span data-stu-id="081fe-120">Optionally, prevent the activation of pending costs, so that activation will be allowed after pending costs have been completely and accurately defined.</span></span> <span data-ttu-id="081fe-121">È inoltre possibile immettere facoltativamente una data nel campo **Dal**.</span><span class="sxs-lookup"><span data-stu-id="081fe-121">You can also optionally enter a date in the **From date** field.</span></span> <span data-ttu-id="081fe-122">In generale, utilizzare la data in cui si intende attivare gli aggiornamenti incrementali.</span><span class="sxs-lookup"><span data-stu-id="081fe-122">As a general guideline, use the date when you intend to enable the incremental updates.</span></span> <span data-ttu-id="081fe-123">In alternativa, lasciare vuoto il campo **Dal** per la versione di determinazione costi, quindi immettere una data nel campo **Dal** per ciascun record costi.</span><span class="sxs-lookup"><span data-stu-id="081fe-123">Alternatively, leave the **From date** field blank for the costing version, and then enter a date in the **From date** field for each cost record.</span></span>
2.  <span data-ttu-id="081fe-124">Utilizzare la pagina **Prezzo articolo** per immettere gli aggiornamenti come record costi articoli all'interno della seconda versione di determinazione costi.</span><span class="sxs-lookup"><span data-stu-id="081fe-124">Use the **Item price** page to enter updates as item cost records that are enclosed in the second costing version.</span></span>
3.  <span data-ttu-id="081fe-125">Utilizzare il report **Prezzi articoli** per verificare la completezza e l'accuratezza dei record costi articoli all'interno della seconda versione di determinazione costi.</span><span class="sxs-lookup"><span data-stu-id="081fe-125">Use the **Item prices** report to verify the completeness and accuracy of the item cost records that are enclosed in the second costing version.</span></span>
4.  <span data-ttu-id="081fe-126">Utilizzare la pagina **Gestione versione di determinazione costi** per modificare il flag di blocco per consentire l'attivazione dei record costi in sospeso all'interno della seconda versione di determinazione costi.</span><span class="sxs-lookup"><span data-stu-id="081fe-126">Use the **Costing version maintenance** page to change the blocking flag to allow activation of the pending cost records that are enclosed in the second costing version.</span></span>
5.  <span data-ttu-id="081fe-127">Utilizzare la pagina **Attiva prezzi** (accessibile dalla pagina **Gestione versione di determinazione costi**) per attivare tutti i record di costo articolo in sospeso all'interno della seconda versione di determinazione costi.</span><span class="sxs-lookup"><span data-stu-id="081fe-127">Use the **Activate prices** page (which you open from the **Costing version maintenance** page) to activate all pending item cost records that are enclosed in the second costing version.</span></span> <span data-ttu-id="081fe-128">È inoltre possibile attivare i record costi in sospeso per i singoli articoli facendo clic sul pulsante **Attiva prezzo in sospeso** nella pagina **Prezzo articolo**.</span><span class="sxs-lookup"><span data-stu-id="081fe-128">You can also activate the pending cost records for individual items by clicking the **Activate pending price** button on the **Item price** page.</span></span>
6.  <span data-ttu-id="081fe-129">Per evitare ulteriori operazioni di manutenzione dati, utilizzare la pagina **Impostazione versione di determinazione costi** per modificare i flag di blocco all'interno della seconda versione di determinazione costi.</span><span class="sxs-lookup"><span data-stu-id="081fe-129">To prevent additional data maintenance, use the **Costing version setup** page to change the blocking flags that are enclosed in the second costing version.</span></span> <span data-ttu-id="081fe-130">I criteri di blocco impediranno l'immissione di nuovi costi in sospeso e l'attivazione dei costi in sospeso.</span><span class="sxs-lookup"><span data-stu-id="081fe-130">The blocking policies will prevent the entry of new pending costs and the activation of pending costs.</span></span>




