---
title: Materiali pericolosi
description: Questo argomento fornisce informazioni su documenti relativi a materiali pericolosi immagazzinati nel proprio ambiente.
author: lachlancashMS
manager: tfehr
ms.date: 01/10/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations, Retail
ms.custom: 19171
ms.assetid: 81fa3709-4ab8-4fbf-9806-359892a05985
ms.search.region: Global
ms.search.industry: Retail
ms.author: kamaybac
ms.search.validFrom: 2019-10-14
ms.dyn365.ops.version: ''
ms.openlocfilehash: feee6b348ac1870295a894ad988278b23a3f30a3
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/10/2020
ms.locfileid: "3979042"
---
# <a name="hazardous-materials"></a><span data-ttu-id="911e1-103">Materiali pericolosi</span><span class="sxs-lookup"><span data-stu-id="911e1-103">Hazardous materials</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="911e1-104">Le informazioni sui materiali pericolosi sono incluse in Gestione informazioni sul prodotto.</span><span class="sxs-lookup"><span data-stu-id="911e1-104">Information about hazardous materials is set up in Product information management.</span></span> <span data-ttu-id="911e1-105">Questo modulo fornisce anche documenti che possono essere stampati mediante Gestione magazzino.</span><span class="sxs-lookup"><span data-stu-id="911e1-105">This module also provides documents that can be printed through warehouse management.</span></span>

<span data-ttu-id="911e1-106">Quando si spediscono materiali classificati come merci pericolose, è necessario includere ulteriori documenti con le spedizioni.</span><span class="sxs-lookup"><span data-stu-id="911e1-106">When you ship materials that are classified as dangerous goods, additional paperwork must be included with the shipments.</span></span> <span data-ttu-id="911e1-107">La funzionalità Materiale pericoloso consente ai clienti di archiviare informazioni di classificazione e applicarle agli articoli rilasciati.</span><span class="sxs-lookup"><span data-stu-id="911e1-107">The hazardous materials functionality lets customers store classification information and relate it to release items.</span></span> <span data-ttu-id="911e1-108">Queste informazioni possono quindi essere utilizzate per preparare la documentazione di spedizione.</span><span class="sxs-lookup"><span data-stu-id="911e1-108">This information can then be used to help prepare shipping documentation.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="911e1-109">Le funzioni relative ai materiali pericolosi in Microsoft Dynamics 365 Supply Chain Management forniscono una raccolta di campi di informazioni sul prodotto utili e funzionalità correlate che possono aiutare a registrare e consultare le informazioni relative ai prodotti pericolosi.</span><span class="sxs-lookup"><span data-stu-id="911e1-109">The hazardous materials features in Microsoft Dynamics 365 Supply Chain Management provide a collection of useful product information fields and related functionality that can help you record and reference information that is related to your hazardous products.</span></span> <span data-ttu-id="911e1-110">Queste funzionalità possono anche aiutarti a progettare e stampare documenti di spedizione che includono le stesse informazioni sui materiali pericolosi che stai spedendo.</span><span class="sxs-lookup"><span data-stu-id="911e1-110">These features can also help you design and print shipment documents that include some of the same information about any hazardous materials that you're shipping.</span></span> <span data-ttu-id="911e1-111">Tuttavia, il sistema non è automaticamente conforme alle normative applicabili del proprio paese o area geografica.</span><span class="sxs-lookup"><span data-stu-id="911e1-111">However, the system won't automatically make you compliant with all applicable regulations in your country or region.</span></span> <span data-ttu-id="911e1-112">Sebbene questi strumenti abbiano lo scopo di aiutarti a rispettare le normative comuni, non sono sufficienti di per sé né sono garantiti a esserlo.</span><span class="sxs-lookup"><span data-stu-id="911e1-112">Although these tools are intended to help you comply with common regulations, they are neither sufficient in themselves nor guaranteed to be so.</span></span> <span data-ttu-id="911e1-113">La tua organizzazione è responsabile di conoscere tutte le normative applicabili e di adottare tutte le misure necessarie per rispettarle.</span><span class="sxs-lookup"><span data-stu-id="911e1-113">Your organization is responsible for being aware of all applicable regulations and for taking all necessary steps to comply with them.</span></span>

<span data-ttu-id="911e1-114">Per poter utilizzare questa funzionalità è necessario eseguire la configurazione seguente:</span><span class="sxs-lookup"><span data-stu-id="911e1-114">Before you can use this functionality, the following setup is required:</span></span>

- <span data-ttu-id="911e1-115">**Gestione informazioni sul prodotto:** impostare codici che possono essere applicati ai prodotti rilasciati.</span><span class="sxs-lookup"><span data-stu-id="911e1-115">**Product information management:** Set up codes that can be applied to released products.</span></span>
- <span data-ttu-id="911e1-116">**Gestione magazzino:** utilizzare documenti di spedizione aggiuntivi per stampare informazioni sulla spedizione.</span><span class="sxs-lookup"><span data-stu-id="911e1-116">**Warehouse management:** Use additional shipping documents to print shipment information.</span></span>

## <a name="product-information-management"></a><span data-ttu-id="911e1-117">Gestione informazioni sul prodotto</span><span class="sxs-lookup"><span data-stu-id="911e1-117">Product information management</span></span>

<span data-ttu-id="911e1-118">Gestione informazioni sul prodotto include una serie di tabelle di configurazione in cui è possibile aggiungere le informazioni di riferimento fornite negli elenchi di merci pericolose per trasporto via terra, aereo e marittimo.</span><span class="sxs-lookup"><span data-stu-id="911e1-118">In Product information management, there is a range of setup tables where you can add the reference information that is provided in the dangerous goods lists for road, air, and sea freight.</span></span>

<span data-ttu-id="911e1-119">Di seguito sono riportate alcune normative a cui si fa spesso riferimento:</span><span class="sxs-lookup"><span data-stu-id="911e1-119">Here are some of the regulations that are often referenced:</span></span>

- <span data-ttu-id="911e1-120">**ADR** - Normative relative al trasporto internazionale di merci pericolose via terra</span><span class="sxs-lookup"><span data-stu-id="911e1-120">**ADR** – Regulations that are related to the international carriage of dangerous goods by road</span></span>
- <span data-ttu-id="911e1-121">**CFR 49** - Normative negli Stati Uniti per il trasporto di merci pericolose</span><span class="sxs-lookup"><span data-stu-id="911e1-121">**CFR 49** – Regulations in the United Sates for the carriage of dangerous goods</span></span>
- <span data-ttu-id="911e1-122">**IMDG** – Il codice International Marine Dangerous Goods (IMDG)</span><span class="sxs-lookup"><span data-stu-id="911e1-122">**IMDG** – The International Marine Dangerous Goods (IMDG) code</span></span>
- <span data-ttu-id="911e1-123">**IATA** - Le normative sulle merci pericolose della International Air Transport Association (IATA)</span><span class="sxs-lookup"><span data-stu-id="911e1-123">**IATA** – The International Air Transport Association (IATA) dangerous goods regulations</span></span>

<span data-ttu-id="911e1-124">Ognuna di queste normative presenta un elenco di merci pericolose che include codici di riferimento.</span><span class="sxs-lookup"><span data-stu-id="911e1-124">Each of these regulations has a dangerous goods list that includes reference codes.</span></span> <span data-ttu-id="911e1-125">Gli elenchi per ciascun tipo di trasporto sono combinati in classificazioni internazionali condivise.</span><span class="sxs-lookup"><span data-stu-id="911e1-125">The lists for each type of transport are combined on shared international classifications.</span></span> <span data-ttu-id="911e1-126">Supply Chain Management fornisce una tabella di riferimento per i codici condivisi in tali elenchi.</span><span class="sxs-lookup"><span data-stu-id="911e1-126">Supply Chain Management provides a reference table for the shared codes in those lists.</span></span> <span data-ttu-id="911e1-127">Ogni elenco include inoltre alcuni codici univoci che possono essere definiti.</span><span class="sxs-lookup"><span data-stu-id="911e1-127">Each list also has some unique codes that can be defined.</span></span>

<span data-ttu-id="911e1-128">Per iniziare a configurare queste informazioni, creare una normativa che è possibile utilizzare per configurare i parametri iniziali.</span><span class="sxs-lookup"><span data-stu-id="911e1-128">To start to configure this information, create a regulation that you can use to configure the initial parameters.</span></span>

## <a name="warehouse-management"></a><span data-ttu-id="911e1-129">Gestione magazzino</span><span class="sxs-lookup"><span data-stu-id="911e1-129">Warehouse management</span></span>

<span data-ttu-id="911e1-130">Quando si prepara una spedizione, è possibile stampare vari nuovi report.</span><span class="sxs-lookup"><span data-stu-id="911e1-130">When a shipment is prepared, several new reports can be printed.</span></span> <span data-ttu-id="911e1-131">Questi report utilizzano le informazioni impostate in Gestione informazioni sul prodotto.</span><span class="sxs-lookup"><span data-stu-id="911e1-131">These reports use the information that you set up in Product information management.</span></span>
