---
title: Panoramica dei materiali pericolosi
description: Questo argomento fornisce una panoramica delle funzionalità correlate alla gestione e alla documentazione dei materiali pericolosi per la gestione delle informazioni sul prodotto e la gestione del magazzino.
author: dasani-madipalli
manager: tfehr
ms.date: 06/10/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: damadipa
ms.search.validFrom: 2020-06-10
ms.dyn365.ops.version: Release 10.0.11
ms.openlocfilehash: 4ff997214f80d97f6e558d32fbf66663cbc84143
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5231890"
---
# <a name="hazardous-materials-overview"></a><span data-ttu-id="cf85a-103">Panoramica dei materiali pericolosi</span><span class="sxs-lookup"><span data-stu-id="cf85a-103">Hazardous materials overview</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="cf85a-104">Per rimanere conformi alle normative sulla spedizione e sul trasporto, le organizzazioni che spediscono materiali classificati come merci pericolose devono includere documenti aggiuntivi con le loro spedizioni.</span><span class="sxs-lookup"><span data-stu-id="cf85a-104">To remain compliant with shipping and transport regulations, organizations that ship materials that are classified as dangerous goods must include additional paperwork with their shipments.</span></span> <span data-ttu-id="cf85a-105">La funzione dei materiali pericolosi consente ai clienti di memorizzare le informazioni relative agli articoli rilasciati.</span><span class="sxs-lookup"><span data-stu-id="cf85a-105">The hazardous materials feature lets customers store information that is related to released items.</span></span> <span data-ttu-id="cf85a-106">Queste informazioni possono quindi essere utilizzate per preparare la documentazione di spedizione.</span><span class="sxs-lookup"><span data-stu-id="cf85a-106">This information can then be used to help prepare shipping documentation.</span></span> <span data-ttu-id="cf85a-107">Un'organizzazione che spedisce merci pericolose deve avere propri processi e procedure per la gestione del processo di spedizione.</span><span class="sxs-lookup"><span data-stu-id="cf85a-107">An organization that ships dangerous goods must have its own processes and procedures for managing the shipping process.</span></span> <span data-ttu-id="cf85a-108">Microsoft Dynamics 365 Supply Chain Management è solo uno strumento che può aiutare a generare i documenti richiesti.</span><span class="sxs-lookup"><span data-stu-id="cf85a-108">Microsoft Dynamics 365 Supply Chain Management is just a tool that can help generate the required documents.</span></span>

<span data-ttu-id="cf85a-109">Il diagramma seguente illustra i passaggi necessari per impostare e utilizzare la funzione dei materiali pericolosi.</span><span class="sxs-lookup"><span data-stu-id="cf85a-109">The following diagram illustrates the steps needed to set up and use the hazardous materials feature.</span></span>

<span data-ttu-id="cf85a-110">![Impostazione e utilizzo della funzione dei materiali pericolosi](media/hazmat-overview.png "Impostazione e utilizzo della funzione dei materiali pericolosi")</span><span class="sxs-lookup"><span data-stu-id="cf85a-110">![Setup and use of the hazardous materials feature](media/hazmat-overview.png "Setup and use of the hazardous materials feature")</span></span>

<span data-ttu-id="cf85a-111">La funzione dei materiali pericolosi viene impostata nella gestione delle informazioni sul prodotto e fornisce i documenti che possono essere stampati tramite la gestione del magazzino.</span><span class="sxs-lookup"><span data-stu-id="cf85a-111">The hazardous materials feature is set up in Product information management and provides documents that can be printed through Warehouse management.</span></span> <span data-ttu-id="cf85a-112">Pertanto, in linea di massima, queste sono le due aree principali in cui è possibile rivedere, impostare e utilizzare la funzionalità di questa funzione:</span><span class="sxs-lookup"><span data-stu-id="cf85a-112">Therefore, broadly speaking, those areas are the two main areas where you will review, set up, and use this feature's functionality:</span></span>

- <span data-ttu-id="cf85a-113">**Gestione informazioni sul prodotto:** impostare codici che possono essere applicati a un prodotto rilasciato.</span><span class="sxs-lookup"><span data-stu-id="cf85a-113">**Product information management** – Set up the codes that will be applied to a released product.</span></span>
- <span data-ttu-id="cf85a-114">**Gestione magazzino**: utilizzare i documenti di spedizione aggiuntivi che verranno stampati per le spedizioni.</span><span class="sxs-lookup"><span data-stu-id="cf85a-114">**Warehouse management** – Work with additional shipping documents that will be printed for shipments.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cf85a-115">Le funzioni relative ai materiali pericolosi in Supply Chain Management forniscono una raccolta di campi di informazioni sul prodotto utili e funzionalità correlate che possono aiutare a registrare e consultare le informazioni relative ai prodotti pericolosi.</span><span class="sxs-lookup"><span data-stu-id="cf85a-115">The hazardous materials features in Supply Chain Management provide a collection of useful product information fields and related functionality that can help you record and reference information that is related to your hazardous products.</span></span> <span data-ttu-id="cf85a-116">Queste funzionalità possono anche aiutarti a progettare e stampare documenti di spedizione che includono le stesse informazioni sui materiali pericolosi che stai spedendo.</span><span class="sxs-lookup"><span data-stu-id="cf85a-116">These features can also help you design and print shipment documents that include some of the same information about any hazardous materials that you're shipping.</span></span> <span data-ttu-id="cf85a-117">Tuttavia, il sistema non è automaticamente conforme alle normative applicabili del proprio paese o area geografica.</span><span class="sxs-lookup"><span data-stu-id="cf85a-117">However, the system won't automatically make you compliant with all applicable regulations in your country or region.</span></span> <span data-ttu-id="cf85a-118">Sebbene questi strumenti abbiano lo scopo di aiutarti a rispettare le normative comuni, non sono sufficienti di per sé né sono garantiti a esserlo.</span><span class="sxs-lookup"><span data-stu-id="cf85a-118">Although these tools are intended to help you comply with common regulations, they are neither sufficient in themselves nor guaranteed to be so.</span></span> <span data-ttu-id="cf85a-119">La tua organizzazione è responsabile di conoscere tutte le normative applicabili e di adottare tutte le misure necessarie per rispettarle.</span><span class="sxs-lookup"><span data-stu-id="cf85a-119">Your organization is responsible for being aware of all applicable regulations and for taking all necessary steps to comply with them.</span></span>

## <a name="product-information-management"></a><span data-ttu-id="cf85a-120">Gestione informazioni sul prodotto</span><span class="sxs-lookup"><span data-stu-id="cf85a-120">Product information management</span></span>

<span data-ttu-id="cf85a-121">Gestione informazioni sul prodotto fornisce una serie di tabelle di configurazione in cui è possibile immettere le informazioni di riferimento per i diversi elenchi di merci pericolose per trasporto via terra, aereo e marittimo.</span><span class="sxs-lookup"><span data-stu-id="cf85a-121">Product information management provides a range of setup tables where you can enter reference information for the various dangerous goods lists for road, air, and sea freight.</span></span>

<span data-ttu-id="cf85a-122">Quando questa funzionalità è stata sviluppata, sono state considerate le seguenti normative comuni:</span><span class="sxs-lookup"><span data-stu-id="cf85a-122">The following common regulations were referenced when this functionality was developed:</span></span>

- <span data-ttu-id="cf85a-123">**ADR** - Normative relative al trasporto internazionale di merci pericolose via terra</span><span class="sxs-lookup"><span data-stu-id="cf85a-123">**ADR** – Regulations that are related to the international carriage of dangerous goods by road</span></span>
- <span data-ttu-id="cf85a-124">**CFR 49** - Normative negli Stati Uniti per il trasporto di merci pericolose</span><span class="sxs-lookup"><span data-stu-id="cf85a-124">**CFR 49** – Regulations in the United Sates for the carriage of dangerous goods</span></span>
- <span data-ttu-id="cf85a-125">**IMDG** – Il codice International Marine Dangerous Goods (IMDG)</span><span class="sxs-lookup"><span data-stu-id="cf85a-125">**IMDG** – The International Marine Dangerous Goods (IMDG) code</span></span>
- <span data-ttu-id="cf85a-126">**IATA** - Le normative sulle merci pericolose della International Air Transport Association (IATA)</span><span class="sxs-lookup"><span data-stu-id="cf85a-126">**IATA** – The International Air Transport Association (IATA) dangerous goods regulations</span></span>

<span data-ttu-id="cf85a-127">Ogni serie di normative fornisce elenchi standard di merci pericolose e codici di riferimento.</span><span class="sxs-lookup"><span data-stu-id="cf85a-127">Each set of regulations provides standardized lists of dangerous goods and reference codes.</span></span> <span data-ttu-id="cf85a-128">Pertanto Supply Chain Management fornisce una tabella di riferimento per i codici comuni in tali elenchi.</span><span class="sxs-lookup"><span data-stu-id="cf85a-128">Therefore, Supply Chain Management provides a reference table for the common codes on those lists.</span></span> <span data-ttu-id="cf85a-129">Ogni elenco include inoltre alcuni codici univoci che possono essere definiti.</span><span class="sxs-lookup"><span data-stu-id="cf85a-129">Each list also has some unique codes that you can define.</span></span>

<span data-ttu-id="cf85a-130">Per ulteriori informazioni su come impostare normative e valori per i materiali pericolosi e su come assegnare i valori ai prodotti pertinenti, vedere i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="cf85a-130">For more information about how to set up regulations and values for hazardous materials, and how to assign the values to relevant products, see the following topics:</span></span>

- [<span data-ttu-id="cf85a-131">Impostare i materiali pericolosi</span><span class="sxs-lookup"><span data-stu-id="cf85a-131">Set up hazardous materials</span></span>](hazmat-setup.md)
- [<span data-ttu-id="cf85a-132">Materiali pericolosi in prodotti, ordini, spedizioni e carichi</span><span class="sxs-lookup"><span data-stu-id="cf85a-132">Hazardous materials in products, orders, shipments, and loads</span></span>](hazmat-items.md)

## <a name="warehouse-management"></a><span data-ttu-id="cf85a-133">Gestione magazzino</span><span class="sxs-lookup"><span data-stu-id="cf85a-133">Warehouse management</span></span>

<span data-ttu-id="cf85a-134">Quando si prepara una spedizione in Gestione magazzino, è possibile stampare diversi nuovi report che utilizzano le informazioni impostate in Gestione informazioni sul prodotto.</span><span class="sxs-lookup"><span data-stu-id="cf85a-134">When you prepare a shipment in Warehouse management, you will be able to print several new reports that use the information that you set up in Product information management.</span></span> <span data-ttu-id="cf85a-135">Per ulteriori informazioni sui report disponibili e su come utilizzarli, vedere [Richieste di informazioni e report sui materiali pericolosi](hazmat-reports.md).</span><span class="sxs-lookup"><span data-stu-id="cf85a-135">For more information about the available reports and how to use them, see [Hazardous materials inquiries and reports](hazmat-reports.md).</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]