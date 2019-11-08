---
title: Unità funzionali e cespiti
description: Questo argomento illustra unità funzionali e cespiti in Gestione cespiti. Gestione cespiti è un modulo avanzato per gestire i cespiti e processi di manutenzione in Dynamics 365 Supply Chain Management.
author: josaw1
manager: AnnBe
ms.date: 06/24/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e3a42d36fd137aa780886276a4235f1b8f3a3680
ms.sourcegitcommit: 0099fb24f5f40ff442020b488ef4171836c35c48
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/23/2019
ms.locfileid: "2653349"
---
# <a name="functional-locations-and-assets"></a><span data-ttu-id="77010-104">Unità funzionali e cespiti</span><span class="sxs-lookup"><span data-stu-id="77010-104">Functional locations and assets</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="77010-105">Questo argomento illustra unità funzionali e cespiti in Gestione cespiti.</span><span class="sxs-lookup"><span data-stu-id="77010-105">This topic describes functional locations and assets in Asset Management.</span></span> <span data-ttu-id="77010-106">Gestione cespiti è un modulo avanzato per gestire i cespiti e processi di manutenzione in Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="77010-106">Asset Management is an advanced module for managing assets and maintenance jobs in Dynamics 365 Supply Chain Management.</span></span>

## <a name="overview"></a><span data-ttu-id="77010-107">Panoramica</span><span class="sxs-lookup"><span data-stu-id="77010-107">Overview</span></span>

<span data-ttu-id="77010-108">Gestione cespiti è integrato con diversi moduli in altre app Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="77010-108">Asset Management is integrated seamlessly with several modules with other Finance and Operations apps.</span></span> <span data-ttu-id="77010-109">La figura di seguito mostra le interfacce con altri moduli.</span><span class="sxs-lookup"><span data-stu-id="77010-109">The following illustration shows the interfaces with other modules.</span></span>

![Diagramma che mostra come Gestione cespiti si interfaccia con altri moduli](media/01-overview-image.png)

<span data-ttu-id="77010-111">Gestione cespiti consente di gestire e eseguire in modo efficiente tutte le attività correlate alla gestione e alla manutenzione di molti tipi di attrezzature della società.</span><span class="sxs-lookup"><span data-stu-id="77010-111">Asset Management lets you efficiently manage and perform all tasks that are related to managing and servicing many types of equipment in your company.</span></span> <span data-ttu-id="77010-112">Queste attrezzatture includono macchine, impianti di produzione e veicoli.</span><span class="sxs-lookup"><span data-stu-id="77010-112">This equipment includes machines, production equipment, and vehicles.</span></span> <span data-ttu-id="77010-113">Gestione cespiti supporta anche soluzioni per numerosi settori.</span><span class="sxs-lookup"><span data-stu-id="77010-113">Asset Management also supports solutions across numerous industries.</span></span>

<span data-ttu-id="77010-114">Nella seguente figura è illustrata una panoramica delle funzionalità principali di Gestione cespiti.</span><span class="sxs-lookup"><span data-stu-id="77010-114">The following illustration shows an overview of the main functionality that is covered by Asset Management.</span></span>

![Diagramma che mostra le funzionalità principali in Gestione cespiti](media/02-overview-image.png)

## <a name="functional-locations-and-assets"></a><span data-ttu-id="77010-116">Unità funzionali e cespiti</span><span class="sxs-lookup"><span data-stu-id="77010-116">Functional locations and assets</span></span>

<span data-ttu-id="77010-117">Le unità funzionali vengono utilizzate per gestire i cespiti nelle ubicazioni.</span><span class="sxs-lookup"><span data-stu-id="77010-117">Functional locations are used to manage assets on locations.</span></span> <span data-ttu-id="77010-118">La gestione comprende la tracciabilità dei costi dei cespiti nelle unità funzionali.</span><span class="sxs-lookup"><span data-stu-id="77010-118">This management includes tracking of asset costs on functional locations.</span></span> <span data-ttu-id="77010-119">Le unità funzionali sono strutturate in modo gerarchico e le ubicazioni possono avere ubicazioni secondarie.</span><span class="sxs-lookup"><span data-stu-id="77010-119">Functional locations are structured hierarchically, and locations can have sub-locations.</span></span> <span data-ttu-id="77010-120">La struttura delle unità funzionali è statica.</span><span class="sxs-lookup"><span data-stu-id="77010-120">The structure of functional locations is static.</span></span> <span data-ttu-id="77010-121">Ovvero le ubicazioni non possono cambiare posto.</span><span class="sxs-lookup"><span data-stu-id="77010-121">In other words, locations can't change place.</span></span> <span data-ttu-id="77010-122">I cespiti possono essere installati nelle unità funzionali e, secondo le esigenze, è possibile installarli più avanti in altre unità funzionali.</span><span class="sxs-lookup"><span data-stu-id="77010-122">Assets can be installed on functional locations and, as required, can be installed on other functional locations later.</span></span>

<span data-ttu-id="77010-123">I costi dei cespiti seguono sempre l'ubicazione del cespite.</span><span class="sxs-lookup"><span data-stu-id="77010-123">Asset costs always follow the location of the asset.</span></span> <span data-ttu-id="77010-124">Ovvero se si installa un cespite in una nuova unità funzionale, il cespite utilizza automaticamente le dimensioni finanziarie correlate alla nuova unità funzionale.</span><span class="sxs-lookup"><span data-stu-id="77010-124">In other words, if you install an asset on a new functional location, the asset automatically uses the financial dimensions that are related to the new functional location.</span></span> <span data-ttu-id="77010-125">Di conseguenza, i costi dei cespiti sono sempre correlati all'unità funzionale in cui il cespite è attualmente installato.</span><span class="sxs-lookup"><span data-stu-id="77010-125">Therefore, asset costs are always related to the functional location that the asset is  currently installed on.</span></span> <span data-ttu-id="77010-126">Questa gestione automatica delle dimensioni finanziarie facilita la tracciabilità completa dei costi quando la società effettua il controllo dei progetti e il reporting sulle unità funzionali.</span><span class="sxs-lookup"><span data-stu-id="77010-126">This automatic handling of financial dimensions helps guarantee complete tracking of costs when your company does project controlling and reporting on functional locations.</span></span>

<span data-ttu-id="77010-127">Il modo in cui sviluppare la gerarchia delle unità funzionali dipende dai requisiti della società per la manutenzione delle attrezzature interne o dei clienti.</span><span class="sxs-lookup"><span data-stu-id="77010-127">The way that you build your hierarchy of functional locations depends on your company's requirements for maintaining internal equipment or servicing customer equipment.</span></span> <span data-ttu-id="77010-128">Nella figura seguente viene illustrato un esempio di unità funzionali basate sulle ubicazioni geografiche.</span><span class="sxs-lookup"><span data-stu-id="77010-128">The following figure shows an example of functional locations that are based on geographical locations.</span></span>

![Diagramma che mostra le unità funzionali in base alle ubicazioni geografiche](media/03-overview-image.png)

<span data-ttu-id="77010-130">Nella figura seguente viene illustrato un esempio di unità funzionali basate sui clienti.</span><span class="sxs-lookup"><span data-stu-id="77010-130">The following figure shows an example of functional locations that are based on customers.</span></span>

![Diagramma che mostra le unità funzionali in base ai clienti](media/04-overview-image.png)
