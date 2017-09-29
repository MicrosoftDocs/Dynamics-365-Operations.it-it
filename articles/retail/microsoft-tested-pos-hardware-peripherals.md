---
title: Periferiche hardware POS
description: "Retail Modern POS e POS cloud possono utilizzare una vasta gamma di periferiche hardware POS, con più opzioni di interfacce e distribuzione per soddisfare vari scenari aziendali di un rivenditore."
author: jblucher
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: josaw
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations, Retail
ms.custom: 215234
ms.assetid: 1893d4b3-e1b7-4b66-be58-0102addd5b36
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 97d374230cc6e833b9f585de000e1252f2a78b9d
ms.openlocfilehash: 17738e794f18fddc7320b1b40ef55376fba0de24
ms.contentlocale: it-it
ms.lasthandoff: 08/30/2017

---

# <a name="pos-hardware-peripherals"></a><span data-ttu-id="1b18f-103">Periferiche hardware POS</span><span class="sxs-lookup"><span data-stu-id="1b18f-103">POS hardware peripherals</span></span>

[!include[banner](includes/banner.md)]


<span data-ttu-id="1b18f-104">Retail Modern POS e POS cloud possono utilizzare una vasta gamma di periferiche hardware POS, con più opzioni di interfacce e distribuzione per soddisfare vari scenari aziendali di un rivenditore.</span><span class="sxs-lookup"><span data-stu-id="1b18f-104">Retail Modern point of sale (POS) and Cloud POS can utilize a wide range of POS hardware peripherals, with multiple interfaces and deployment options to achieve a retailer’s various business scenarios.</span></span> 

<span data-ttu-id="1b18f-105">Per supportare la più ampia gamma di dispositivi in termini di produttori e modelli, POS utilizza interfacce standard come OLE for Retail POS (OPOS), driver di dispositivo Windows e interfacce API punto di servizio Windows.</span><span class="sxs-lookup"><span data-stu-id="1b18f-105">To support the widest selection of devices across manufactures and models, POS utilizes standard interfaces such as OLE for Retail POS (OPOS), Windows device drivers, and Windows point of service application program interfaces (APIs).</span></span> <span data-ttu-id="1b18f-106">In genere, POS funzionerà con questi dispositivi a condizione che il driver appropriato viene fornito.</span><span class="sxs-lookup"><span data-stu-id="1b18f-106">Generally, POS will work on these devices provided that the appropriate driver is supplied.</span></span> <span data-ttu-id="1b18f-107">Tuttavia, poiché l'implementazione di questi standard da parte di ogni produttore e sviluppatori software può variare, esistono spesso differenze nelle funzionalità o i comportamenti supportati.</span><span class="sxs-lookup"><span data-stu-id="1b18f-107">However, because each manufacturer and software developer’s implementation of these standards can vary, there are often differences in supported capabilities or behaviors.</span></span>

<span data-ttu-id="1b18f-108">Nel seguente elenco sono inclusi modelli di dispositivi, in ciascuna classe, che sono stati testati internamente da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1b18f-108">The following list includes device models, in each class, that have been tested internally by Microsoft.</span></span>

<span data-ttu-id="1b18f-109">**dispositivi OPOS**</span><span class="sxs-lookup"><span data-stu-id="1b18f-109">**OPOS devices**</span></span>

-   <span data-ttu-id="1b18f-110">Codice a barre - Motorola DS9208</span><span class="sxs-lookup"><span data-stu-id="1b18f-110">Barcode – Motorola DS9208</span></span>
-   <span data-ttu-id="1b18f-111">MSR - HP IDRA-334133, Magtek PN - 21073062</span><span class="sxs-lookup"><span data-stu-id="1b18f-111">MSR – HP IDRA-334133, Magtek PN - 21073062</span></span>
-   <span data-ttu-id="1b18f-112">LineDisplay - Epson M58DC</span><span class="sxs-lookup"><span data-stu-id="1b18f-112">LineDisplay – Epson M58DC</span></span>
-   <span data-ttu-id="1b18f-113">Tastierino PIN - Verifone 1000SE</span><span class="sxs-lookup"><span data-stu-id="1b18f-113">Pinpad – Verifone 1000SE</span></span>
-   <span data-ttu-id="1b18f-114">Tastierino di firma - Scriptel ST1550</span><span class="sxs-lookup"><span data-stu-id="1b18f-114">Signature pad – Scriptel ST1550</span></span>
-   <span data-ttu-id="1b18f-115">Stampante - EPSON TM-T88IV, TMT88V</span><span class="sxs-lookup"><span data-stu-id="1b18f-115">Printer – EPSON TM-T88IV, TMT88V</span></span>
-   <span data-ttu-id="1b18f-116">Cassetto della cassa - Star SMD2-1317BK44</span><span class="sxs-lookup"><span data-stu-id="1b18f-116">Cash drawer – Star SMD2-1317BK44</span></span>
-   <span data-ttu-id="1b18f-117">Bilancia - Datalogic Magellan 8400</span><span class="sxs-lookup"><span data-stu-id="1b18f-117">Scale – Datalogic Magellan 8400</span></span>

<span data-ttu-id="1b18f-118">**MSR collegato alla tastiera**</span><span class="sxs-lookup"><span data-stu-id="1b18f-118">**Keyboard wedge MSR**</span></span>

-   <span data-ttu-id="1b18f-119">Magtek USB</span><span class="sxs-lookup"><span data-stu-id="1b18f-119">Magtek USB</span></span>

<span data-ttu-id="1b18f-120">**Terminale di pagamento**</span><span class="sxs-lookup"><span data-stu-id="1b18f-120">**Payment terminal**</span></span>

-   <span data-ttu-id="1b18f-121">Equinox L3500</span><span class="sxs-lookup"><span data-stu-id="1b18f-121">Equinox L3500</span></span>
-   <span data-ttu-id="1b18f-122">Verifone MX925</span><span class="sxs-lookup"><span data-stu-id="1b18f-122">Verifone MX925</span></span>

<span data-ttu-id="1b18f-123">**Dispositivi di rete**</span><span class="sxs-lookup"><span data-stu-id="1b18f-123">**Network devices**</span></span>

-   <span data-ttu-id="1b18f-124">Stampante – Star TSP650II</span><span class="sxs-lookup"><span data-stu-id="1b18f-124">Printer – Star TSP650II</span></span>
-   <span data-ttu-id="1b18f-125">Cassetto della cassa - APG Atwood</span><span class="sxs-lookup"><span data-stu-id="1b18f-125">Cash drawer – APG Atwood</span></span>
-   <span data-ttu-id="1b18f-126">Terminale di pagamento – MX915, MX925</span><span class="sxs-lookup"><span data-stu-id="1b18f-126">Payment terminal – MX915, MX925</span></span>

<span data-ttu-id="1b18f-127">**MPOS solo IPC diretto**</span><span class="sxs-lookup"><span data-stu-id="1b18f-127">**MPOS direct IPC only**</span></span>

-   <span data-ttu-id="1b18f-128">Codice a barre – Honeywell 1900, HP LS2208</span><span class="sxs-lookup"><span data-stu-id="1b18f-128">Barcode – Honeywell 1900, HP LS2208</span></span>
-   <span data-ttu-id="1b18f-129">MSR - Magtek PN - 21073075</span><span class="sxs-lookup"><span data-stu-id="1b18f-129">MSR – Magtek PN - 21073075</span></span>





