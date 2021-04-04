---
title: Impostazione delle informazioni di spedizione
description: In questo argomento viene descritto come impostare le informazioni di spedizione per il modulo Costo sbarcato.
author: sherry-zheng
manager: tfehr
ms.date: 12/04/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ITMGoodsDescriptionTable, ITMVesselTable, ITMExporterTable, ITMCommodityCodeTable, ITMCustomsDescription
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-12-04
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: 90794a154eb2a63f33277383cda80323dafd77b0
ms.sourcegitcommit: 2b4809e60974e72df9476ffd62706b1bfc8da4a7
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/04/2021
ms.locfileid: "5500936"
---
# <a name="shipping-information-setup"></a><span data-ttu-id="b6b0b-103">Impostazione delle informazioni di spedizione</span><span class="sxs-lookup"><span data-stu-id="b6b0b-103">Shipping information setup</span></span>

[!include [banner](../../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="b6b0b-104">In questo argomento viene descritto come impostare le informazioni di spedizione per il modulo **Costo sbarcato**.</span><span class="sxs-lookup"><span data-stu-id="b6b0b-104">This topic describes how to set up shipping information for the **Landed cost** module.</span></span>

## <a name="description-of-goods"></a><a name="description-of-goods"></a><span data-ttu-id="b6b0b-105">Descrizione delle merci</span><span class="sxs-lookup"><span data-stu-id="b6b0b-105">Description of goods</span></span>

<span data-ttu-id="b6b0b-106">Le descrizioni delle merci aiutano a identificare un viaggio, un contenitore di spedizione o una registrazione di merci e le merci in esso contenute.</span><span class="sxs-lookup"><span data-stu-id="b6b0b-106">Descriptions of goods help identify a voyage, shipping container, or folio of goods, and the goods in it.</span></span> <span data-ttu-id="b6b0b-107">È possibile selezionare una descrizione delle merci nell'intestazione del contenitore di spedizione o della registrazione.</span><span class="sxs-lookup"><span data-stu-id="b6b0b-107">You can select a description of goods on the shipping container header or the folio header.</span></span>

<span data-ttu-id="b6b0b-108">Selezionare **Costo sbarcato \> Impostazione informazioni di spedizione \> Descrizione delle merci**</span><span class="sxs-lookup"><span data-stu-id="b6b0b-108">To work with descriptions of goods, go to **Landed cost \> Shipping information setup \> Description of goods**.</span></span> <span data-ttu-id="b6b0b-109">per visualizzare, aprire, creare ed eliminare record per le descrizioni delle merci.</span><span class="sxs-lookup"><span data-stu-id="b6b0b-109">There, you can view, open, create, and delete records for descriptions of goods.</span></span> <span data-ttu-id="b6b0b-110">Nella seguente tabella sono descritti i campi disponibili per ogni record.</span><span class="sxs-lookup"><span data-stu-id="b6b0b-110">The following table describes the fields that are available for each record.</span></span>

| <span data-ttu-id="b6b0b-111">Campo</span><span class="sxs-lookup"><span data-stu-id="b6b0b-111">Field</span></span> | <span data-ttu-id="b6b0b-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b6b0b-112">Description</span></span> |
|---|---|
| <span data-ttu-id="b6b0b-113">Descrizione delle merci</span><span class="sxs-lookup"><span data-stu-id="b6b0b-113">Description of goods</span></span> | <span data-ttu-id="b6b0b-114">Immettere un nome/numero di identificazione univoco per il tipo di merce che utilizzerà questa descrizione.</span><span class="sxs-lookup"><span data-stu-id="b6b0b-114">Enter a unique identification name/number for the type of goods that will use this description.</span></span> |
| <span data-ttu-id="b6b0b-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b6b0b-115">Description</span></span> | <span data-ttu-id="b6b0b-116">Immettere una descrizione del tipo di merce in questa categoria.</span><span class="sxs-lookup"><span data-stu-id="b6b0b-116">Enter a description of the type of goods in this category.</span></span> |

## <a name="vessels"></a><a name="vessels"></a><span data-ttu-id="b6b0b-117">Imbarcazioni</span><span class="sxs-lookup"><span data-stu-id="b6b0b-117">Vessels</span></span>

<span data-ttu-id="b6b0b-118">Un'imbarcazione è il nome univoco di una nave o di un'imbarcazione utilizzata da una società o un'agenzia di spedizione.</span><span class="sxs-lookup"><span data-stu-id="b6b0b-118">A vessel is the unique name of a ship or vessel that a shipping company or agency uses.</span></span> <span data-ttu-id="b6b0b-119">Quando si crea un viaggio, si deve sempre selezionare o immettere un'imbarcazione.</span><span class="sxs-lookup"><span data-stu-id="b6b0b-119">When you create a voyage, you must always either select or enter a vessel for it.</span></span> <span data-ttu-id="b6b0b-120">Se si utilizzano spesso le stesse imbarcazioni, è possibile semplificare e rendere più veloce la creazione di un nuovo viaggio creando un record per ogni imbarcazione, consentendo così agli utenti di selezionare l'imbarcazione da un elenco piuttosto che inserire manualmente il nome o il numero ogni volta.</span><span class="sxs-lookup"><span data-stu-id="b6b0b-120">If you often use the same vessels, then you can make it faster and easier to create a new voyage by creating a vessel record for each of them, thereby allowing users to select the vessel from a list rather then enter the name or number manually each time.</span></span>

<span data-ttu-id="b6b0b-121">Selezionare **Costo sbarcato \> Impostazione informazioni di spedizione \> Imbarcazioni**</span><span class="sxs-lookup"><span data-stu-id="b6b0b-121">To work with vessels, go to **Landed cost \> Shipping information setup \> Vessels**.</span></span> <span data-ttu-id="b6b0b-122">per visualizzare, aprire, creare ed eliminare record per le imbarcazioni.</span><span class="sxs-lookup"><span data-stu-id="b6b0b-122">There, you can view, open, create, and delete records for vessels.</span></span> <span data-ttu-id="b6b0b-123">Nella seguente tabella sono descritti i campi disponibili per ogni record.</span><span class="sxs-lookup"><span data-stu-id="b6b0b-123">The following table describes the fields that are available for each record.</span></span>

| <span data-ttu-id="b6b0b-124">Campo</span><span class="sxs-lookup"><span data-stu-id="b6b0b-124">Field</span></span> | <span data-ttu-id="b6b0b-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b6b0b-125">Description</span></span> |
|---|---|
| <span data-ttu-id="b6b0b-126">Imbarcazione</span><span class="sxs-lookup"><span data-stu-id="b6b0b-126">Vessel</span></span> | <span data-ttu-id="b6b0b-127">Immettere un nome/numero di identificazione univoco per la nave che verrà utilizzata per il trasporto delle merci in un viaggio.</span><span class="sxs-lookup"><span data-stu-id="b6b0b-127">Enter a unique identification name/number for the ship that will be used to transport goods on a voyage.</span></span> |
| <span data-ttu-id="b6b0b-128">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b6b0b-128">Description</span></span> | <span data-ttu-id="b6b0b-129">Immettere una descrizione dell'imbarcazione.</span><span class="sxs-lookup"><span data-stu-id="b6b0b-129">Enter a description of the vessel.</span></span> <span data-ttu-id="b6b0b-130">In genere, questa descrizione identifica il nome della nave e la società e l'agenzia di spedizione.</span><span class="sxs-lookup"><span data-stu-id="b6b0b-130">Typically, this description identifies the name of the ship and the shipping company/agent.</span></span> |
| <span data-ttu-id="b6b0b-131">Modalità di consegna</span><span class="sxs-lookup"><span data-stu-id="b6b0b-131">Mode of delivery</span></span> | <span data-ttu-id="b6b0b-132">Selezionare la modalità di consegna dell'imbarcazione (come _Via aerea_, _Via mare_ o _Treno_).</span><span class="sxs-lookup"><span data-stu-id="b6b0b-132">Select the mode of delivery that the vessel uses (such as _Air_, _Ocean_, or _Train_).</span></span> |

## <a name="exporters"></a><span data-ttu-id="b6b0b-133">Esportatori</span><span class="sxs-lookup"><span data-stu-id="b6b0b-133">Exporters</span></span>

<span data-ttu-id="b6b0b-134">Ogni record di esportatore identifica un fornitore o un esportatore che può essere definito come fornitore di un viaggio.</span><span class="sxs-lookup"><span data-stu-id="b6b0b-134">Each exporter record identifies a vendor or exporter that can be defined as the vendor for a voyage.</span></span> <span data-ttu-id="b6b0b-135">L'esportatore può essere associato a un viaggio e utilizzato per i report.</span><span class="sxs-lookup"><span data-stu-id="b6b0b-135">The exporter can be associated with a voyage and used for reporting.</span></span>

<span data-ttu-id="b6b0b-136">Selezionare **Costo sbarcato \> Impostazione informazioni di spedizione \> Esportatori**</span><span class="sxs-lookup"><span data-stu-id="b6b0b-136">To work with exporters, go to **Landed cost \> Shipping information setup \> Exporters**.</span></span> <span data-ttu-id="b6b0b-137">per visualizzare, aprire, creare ed eliminare record per gli esportatori.</span><span class="sxs-lookup"><span data-stu-id="b6b0b-137">There, you can view, open, create, and delete records for exporters.</span></span> <span data-ttu-id="b6b0b-138">Nella seguente tabella sono descritti i campi disponibili per ogni record.</span><span class="sxs-lookup"><span data-stu-id="b6b0b-138">The following table describes the fields that are available for each record.</span></span>

| <span data-ttu-id="b6b0b-139">Campo</span><span class="sxs-lookup"><span data-stu-id="b6b0b-139">Field</span></span> | <span data-ttu-id="b6b0b-140">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b6b0b-140">Description</span></span> |
|---|---|
| <span data-ttu-id="b6b0b-141">Esportatore</span><span class="sxs-lookup"><span data-stu-id="b6b0b-141">Exporter</span></span> | <span data-ttu-id="b6b0b-142">Immettere un nome/numero di identificazione univoco per gli esportatori delle merci che vengono trasportate in un viaggio.</span><span class="sxs-lookup"><span data-stu-id="b6b0b-142">Enter a unique identification name/number for the exporter of goods that are transported on a voyage.</span></span> |
| <span data-ttu-id="b6b0b-143">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b6b0b-143">Description</span></span> | <span data-ttu-id="b6b0b-144">Immettere una descrizione dell'esportatore.</span><span class="sxs-lookup"><span data-stu-id="b6b0b-144">Enter a description of the exporter.</span></span> <span data-ttu-id="b6b0b-145">In genere, questa descrizione identifica il nome completo della società/agenzia di spedizione.</span><span class="sxs-lookup"><span data-stu-id="b6b0b-145">Typically, this description identifies the full name of the shipping company/agent.</span></span> |

## <a name="commodity-codes"></a><span data-ttu-id="b6b0b-146">Codici voce doganale</span><span class="sxs-lookup"><span data-stu-id="b6b0b-146">Commodity codes</span></span>

<span data-ttu-id="b6b0b-147">I codici voce doganale facilitano l'identificazione doganale e il calcolo delle aliquote dei dazi per le merci in un viaggio.</span><span class="sxs-lookup"><span data-stu-id="b6b0b-147">You use commodity codes to help with customs identification and the calculation of duty rates for goods on a voyage.</span></span> <span data-ttu-id="b6b0b-148">È possibile selezionare codici voce doganale nella pagina **Prodotti rilasciati**.</span><span class="sxs-lookup"><span data-stu-id="b6b0b-148">You can select commodity codes on the **Released products** page.</span></span>

<span data-ttu-id="b6b0b-149">Selezionare **Costo sbarcato \> Impostazione informazioni di spedizione \> Codici voce doganale**</span><span class="sxs-lookup"><span data-stu-id="b6b0b-149">To work with commodity codes, go to **Landed cost \> Shipping information setup \> Commodity codes**.</span></span> <span data-ttu-id="b6b0b-150">per visualizzare, aprire, creare ed eliminare record per i codici voce doganale.</span><span class="sxs-lookup"><span data-stu-id="b6b0b-150">There, you can view, open, create, and delete records for commodity codes.</span></span> <span data-ttu-id="b6b0b-151">Nella seguente tabella sono descritti i campi disponibili per ogni record.</span><span class="sxs-lookup"><span data-stu-id="b6b0b-151">The following table describes the fields that are available for each record.</span></span>

| <span data-ttu-id="b6b0b-152">Campo</span><span class="sxs-lookup"><span data-stu-id="b6b0b-152">Field</span></span> | <span data-ttu-id="b6b0b-153">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b6b0b-153">Description</span></span> |
|---|---|
| <span data-ttu-id="b6b0b-154">Codice voce doganale</span><span class="sxs-lookup"><span data-stu-id="b6b0b-154">Commodity code</span></span> | <span data-ttu-id="b6b0b-155">Immettere un codice univoco per questo tipo di voce doganale.</span><span class="sxs-lookup"><span data-stu-id="b6b0b-155">Enter a unique code for this type of commodity.</span></span> |
| <span data-ttu-id="b6b0b-156">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b6b0b-156">Description</span></span> | <span data-ttu-id="b6b0b-157">Immettere una descrizione per il tipo di voce doganale.</span><span class="sxs-lookup"><span data-stu-id="b6b0b-157">Enter a description of the commodity type.</span></span> |

## <a name="customs-description"></a><span data-ttu-id="b6b0b-158">Descrizione doganale</span><span class="sxs-lookup"><span data-stu-id="b6b0b-158">Customs description</span></span>

<span data-ttu-id="b6b0b-159">Le descrizioni doganali aiutano a identificare le merci a fini doganali.</span><span class="sxs-lookup"><span data-stu-id="b6b0b-159">Customs descriptions help identify goods for customs purposes.</span></span> <span data-ttu-id="b6b0b-160">È possibile selezionare una descrizione doganale nella pagina **Prodotti rilasciati** o nelle righe di ordine fornitore.</span><span class="sxs-lookup"><span data-stu-id="b6b0b-160">You can select a customs description on the **Released products** page or on purchase order lines.</span></span>

<span data-ttu-id="b6b0b-161">Selezionare **Costo sbarcato \> Impostazione informazioni di spedizione \> Descrizione doganale**</span><span class="sxs-lookup"><span data-stu-id="b6b0b-161">To work with customs descriptions, go to **Landed cost \> Shipping information setup \> Customs description**.</span></span> <span data-ttu-id="b6b0b-162">per visualizzare, aprire, creare ed eliminare record per le descrizioni doganali.</span><span class="sxs-lookup"><span data-stu-id="b6b0b-162">There, you can view, open, create, and delete records for custom descriptions.</span></span> <span data-ttu-id="b6b0b-163">Nella seguente tabella sono descritti i campi disponibili per ogni record.</span><span class="sxs-lookup"><span data-stu-id="b6b0b-163">The following table describes the fields that are available for each record.</span></span>

| <span data-ttu-id="b6b0b-164">Campo</span><span class="sxs-lookup"><span data-stu-id="b6b0b-164">Field</span></span> | <span data-ttu-id="b6b0b-165">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b6b0b-165">Description</span></span> |
|---|---|
| <span data-ttu-id="b6b0b-166">Descrizione doganale</span><span class="sxs-lookup"><span data-stu-id="b6b0b-166">Customs description</span></span> | <span data-ttu-id="b6b0b-167">Immettere un codice univoco per questo tipo di classificazione doganale.</span><span class="sxs-lookup"><span data-stu-id="b6b0b-167">Enter a unique code for this type of customs classification.</span></span> <span data-ttu-id="b6b0b-168">Spesso, questo codice sarà la descrizione ufficiale fornita da un'autorità doganale per la descrizione e il valore qualitativo delle merci.</span><span class="sxs-lookup"><span data-stu-id="b6b0b-168">Often, this code will be the official description that is provided by a customs authority for the description and qualitative value of the goods.</span></span> |
| <span data-ttu-id="b6b0b-169">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b6b0b-169">Description</span></span> | <span data-ttu-id="b6b0b-170">Immettere una descrizione della classificazione doganale.</span><span class="sxs-lookup"><span data-stu-id="b6b0b-170">Enter a description of the customs classification.</span></span> |
