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
ms.author: conradv
ms.search.validFrom: 2019-10-14
ms.dyn365.ops.version: ''
ms.openlocfilehash: 5006f06d90ddcc314a51878e9e21337de7d493e7
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2020
ms.locfileid: "3208466"
---
# <a name="hazardous-materials"></a><span data-ttu-id="f4869-103">Materiali pericolosi</span><span class="sxs-lookup"><span data-stu-id="f4869-103">Hazardous materials</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f4869-104">Le informazioni sui materiali pericolosi sono incluse in Gestione informazioni sul prodotto.</span><span class="sxs-lookup"><span data-stu-id="f4869-104">Information about hazardous materials is set up in Product information management.</span></span> <span data-ttu-id="f4869-105">Questo modulo fornisce anche documenti che possono essere stampati mediante Gestione magazzino.</span><span class="sxs-lookup"><span data-stu-id="f4869-105">This module also provides documents that can be printed through warehouse management.</span></span>

<span data-ttu-id="f4869-106">Quando si spediscono materiali classificati come merci pericolose, è necessario includere ulteriori documenti con le spedizioni.</span><span class="sxs-lookup"><span data-stu-id="f4869-106">When you ship materials that are classified as dangerous goods, additional paperwork must be included with the shipments.</span></span> <span data-ttu-id="f4869-107">La funzionalità Materiale pericoloso consente ai clienti di archiviare informazioni di classificazione e applicarle agli articoli rilasciati.</span><span class="sxs-lookup"><span data-stu-id="f4869-107">The hazardous materials functionality lets customers store classification information and relate it to release items.</span></span> <span data-ttu-id="f4869-108">Queste informazioni possono quindi essere utilizzate per preparare la documentazione di spedizione.</span><span class="sxs-lookup"><span data-stu-id="f4869-108">This information can then be used to help prepare shipping documentation.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f4869-109">Per facilitare la gestione delle spedizioni di merci pericolose, Microsoft Dynamics 365 Supply Chain Management consente di impostare ulteriori informazioni di riferimento relative ai prodotti.</span><span class="sxs-lookup"><span data-stu-id="f4869-109">To help manage shipments of dangerous goods, Microsoft Dynamics 365 Supply Chain Management lets you set up additional reference information that is related to products.</span></span> <span data-ttu-id="f4869-110">È inoltre possibile impostare documenti di spedizione aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="f4869-110">You can also set up additional shipment documents.</span></span> <span data-ttu-id="f4869-111">Tuttavia, il sistema non è automaticamente conforme alle normative del proprio paese o area geografica.</span><span class="sxs-lookup"><span data-stu-id="f4869-111">However, the system isn't automatically compliant with your country's or region's regulations.</span></span> <span data-ttu-id="f4869-112">È comunque uno strumento che può rivelarsi utile per il programma globale.</span><span class="sxs-lookup"><span data-stu-id="f4869-112">Instead, it's a tool that can help your overall program.</span></span>

<span data-ttu-id="f4869-113">Per poter utilizzare questa funzionalità è necessario eseguire la configurazione seguente:</span><span class="sxs-lookup"><span data-stu-id="f4869-113">Before you can use this functionality, the following setup is required:</span></span>

- <span data-ttu-id="f4869-114">**Gestione informazioni sul prodotto:** impostare codici che possono essere applicati ai prodotti rilasciati.</span><span class="sxs-lookup"><span data-stu-id="f4869-114">**Product information management:** Set up codes that can be applied to released products.</span></span>
- <span data-ttu-id="f4869-115">**Gestione magazzino:** utilizzare documenti di spedizione aggiuntivi per stampare informazioni sulla spedizione.</span><span class="sxs-lookup"><span data-stu-id="f4869-115">**Warehouse management:** Use additional shipping documents to print shipment information.</span></span>

## <a name="product-information-management"></a><span data-ttu-id="f4869-116">Gestione informazioni sul prodotto</span><span class="sxs-lookup"><span data-stu-id="f4869-116">Product information management</span></span>

<span data-ttu-id="f4869-117">Gestione informazioni sul prodotto include una serie di tabelle di configurazione in cui è possibile aggiungere le informazioni di riferimento fornite negli elenchi di merci pericolose per trasporto via terra, aereo e marittimo.</span><span class="sxs-lookup"><span data-stu-id="f4869-117">In Product information management, there is a range of setup tables where you can add the reference information that is provided in the dangerous goods lists for road, air, and sea freight.</span></span>

<span data-ttu-id="f4869-118">Di seguito sono riportate alcune normative a cui si fa spesso riferimento:</span><span class="sxs-lookup"><span data-stu-id="f4869-118">Here are some of the regulations that are often referenced:</span></span>

- <span data-ttu-id="f4869-119">**ADR** - Normative relative al trasporto internazionale di merci pericolose via terra</span><span class="sxs-lookup"><span data-stu-id="f4869-119">**ADR** – Regulations that are related to the international carriage of dangerous goods by road</span></span>
- <span data-ttu-id="f4869-120">**CFR 49** - Normative negli Stati Uniti per il trasporto di merci pericolose</span><span class="sxs-lookup"><span data-stu-id="f4869-120">**CFR 49** – Regulations in the United Sates for the carriage of dangerous goods</span></span>
- <span data-ttu-id="f4869-121">**IMDG** – Il codice International Marine Dangerous Goods (IMDG)</span><span class="sxs-lookup"><span data-stu-id="f4869-121">**IMDG** – The International Marine Dangerous Goods (IMDG) code</span></span>
- <span data-ttu-id="f4869-122">**IATA** - Le normative sulle merci pericolose della International Air Transport Association (IATA)</span><span class="sxs-lookup"><span data-stu-id="f4869-122">**IATA** – The International Air Transport Association (IATA) dangerous goods regulations</span></span>

<span data-ttu-id="f4869-123">Ognuna di queste normative presenta un elenco di merci pericolose che include codici di riferimento.</span><span class="sxs-lookup"><span data-stu-id="f4869-123">Each of these regulations has a dangerous goods list that includes reference codes.</span></span> <span data-ttu-id="f4869-124">Gli elenchi per ciascun tipo di trasporto sono combinati in classificazioni internazionali condivise.</span><span class="sxs-lookup"><span data-stu-id="f4869-124">The lists for each type of transport are combined on shared international classifications.</span></span> <span data-ttu-id="f4869-125">Supply Chain Management fornisce una tabella di riferimento per i codici condivisi in tali elenchi.</span><span class="sxs-lookup"><span data-stu-id="f4869-125">Supply Chain Management provides a reference table for the shared codes in those lists.</span></span> <span data-ttu-id="f4869-126">Ogni elenco include inoltre alcuni codici univoci che possono essere definiti.</span><span class="sxs-lookup"><span data-stu-id="f4869-126">Each list also has some unique codes that can be defined.</span></span>

<span data-ttu-id="f4869-127">Per iniziare a configurare queste informazioni, creare una normativa che è possibile utilizzare per configurare i parametri iniziali.</span><span class="sxs-lookup"><span data-stu-id="f4869-127">To start to configure this information, create a regulation that you can use to configure the initial parameters.</span></span>

## <a name="warehouse-management"></a><span data-ttu-id="f4869-128">Gestione magazzino</span><span class="sxs-lookup"><span data-stu-id="f4869-128">Warehouse management</span></span>

<span data-ttu-id="f4869-129">Quando si prepara una spedizione, è possibile stampare vari nuovi report.</span><span class="sxs-lookup"><span data-stu-id="f4869-129">When a shipment is prepared, several new reports can be printed.</span></span> <span data-ttu-id="f4869-130">Questi report utilizzano le informazioni impostate in Gestione informazioni sul prodotto.</span><span class="sxs-lookup"><span data-stu-id="f4869-130">These reports use the information that you set up in Product information management.</span></span>
