---
title: Zone ubicazione aggiuntive
description: Questo argomento offre una panoramica delle nuove zone di ubicazione aggiunte a Microsoft Dynamics 365 Supply Chain Management.
author: Mirzaab
manager: tfehr
ms.date: 07/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSLocationBuild, WHSZone
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: 10.0.8
ms.openlocfilehash: 662725edf5bf8d95be038f7c989b73d8d05fa0df
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4996428"
---
# <a name="additional-location-zones"></a><span data-ttu-id="8f140-103">Zone ubicazione aggiuntive</span><span class="sxs-lookup"><span data-stu-id="8f140-103">Additional location zones</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="8f140-104">Tre nuovi campi di zona sono disponibili in Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="8f140-104">Three new zone fields are available in Microsoft Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="8f140-105">I responsabili del magazzino possono usarli per definire ulteriori layout o organizzazioni di magazzino.</span><span class="sxs-lookup"><span data-stu-id="8f140-105">Warehouse managers can use them to define additional warehouse organizations or layouts.</span></span> <span data-ttu-id="8f140-106">I nuovi campi di zona possono essere impostati manualmente o utilizzando la procedura guidata **Impostazione ubicazione**.</span><span class="sxs-lookup"><span data-stu-id="8f140-106">The new zone fields can be set either manually or by using the **Location setup** wizard.</span></span> <span data-ttu-id="8f140-107">Possono essere utilizzati in qualsiasi query o filtro che utilizza la tabella Ubicazioni.</span><span class="sxs-lookup"><span data-stu-id="8f140-107">They can be used in any query or filtering that uses the Locations table.</span></span>

<span data-ttu-id="8f140-108">Non è richiesta alcuna configurazione aggiuntiva per utilizzare i campi della zona.</span><span class="sxs-lookup"><span data-stu-id="8f140-108">No additional setup is required to use the zone fields.</span></span>

## <a name="turn-on-the-additional-location-zone-feature"></a><span data-ttu-id="8f140-109">Attivare la funzionalità della zona di ubicazione aggiuntiva</span><span class="sxs-lookup"><span data-stu-id="8f140-109">Turn on the Additional location zone feature</span></span>

<span data-ttu-id="8f140-110">Prima di poter utilizzare la funzionalità *Zona ubicazione aggiuntiva*, tale funzionalità deve essere attivata nel sistema.</span><span class="sxs-lookup"><span data-stu-id="8f140-110">Before you can use the *Additional location zone* feature, it must be turned on in your system.</span></span> <span data-ttu-id="8f140-111">Gli amministratori possono utilizzare le impostazioni della [gestione delle funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) per controllare lo stato della funzione e se necessario abilitarla.</span><span class="sxs-lookup"><span data-stu-id="8f140-111">Admins can use the [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="8f140-112">Nell'area di lavoro **Gestione funzionalità**, la funzione è elencata nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="8f140-112">In the **Feature management** workspace, the feature is listed in the following way:</span></span>

- <span data-ttu-id="8f140-113">**Modulo:** *Gestione Magazzino*</span><span class="sxs-lookup"><span data-stu-id="8f140-113">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="8f140-114">**Nome funzionalità:** *Zona di ubicazione aggiuntiva*</span><span class="sxs-lookup"><span data-stu-id="8f140-114">**Feature name:** *Additional location zone*</span></span>

## <a name="use-location-zones"></a><span data-ttu-id="8f140-115">Utilizzare le zone di ubicazione</span><span class="sxs-lookup"><span data-stu-id="8f140-115">Use location zones</span></span>

1. <span data-ttu-id="8f140-116">Vai a **Gestione magazzino \> Impostazioni \> Magazzino \> Impostazione guidata ubicazione**.</span><span class="sxs-lookup"><span data-stu-id="8f140-116">Go to **Warehouse management \> Setup \> Warehouse \> Location setup wizard**.</span></span>
2. <span data-ttu-id="8f140-117">Imposta i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="8f140-117">Set the following values:</span></span>

    - <span data-ttu-id="8f140-118">Nel campo **Magazzino** selezionare _62_.</span><span class="sxs-lookup"><span data-stu-id="8f140-118">In the **Warehouse** field, select _62_.</span></span>
    - <span data-ttu-id="8f140-119">Nel campo **ID zona**, seleziona _FLOOR_.</span><span class="sxs-lookup"><span data-stu-id="8f140-119">In the **Zone ID** field, select _FLOOR_.</span></span>
    - <span data-ttu-id="8f140-120">Nel campo **Zona aggiuntiva 1**, seleziona _PICKZONE1_.</span><span class="sxs-lookup"><span data-stu-id="8f140-120">In the **Additional Zone 1** field, select _PICKZONE1_.</span></span>
    - <span data-ttu-id="8f140-121">Nel campo **Zona aggiuntiva 2**, seleziona _WEBSHOP1_.</span><span class="sxs-lookup"><span data-stu-id="8f140-121">In the **Additional Zone 2** field, select _WEBSHOP1_.</span></span>
    - <span data-ttu-id="8f140-122">Nel campo **ID profilo di ubicazione**, seleziona _FLOOR_.</span><span class="sxs-lookup"><span data-stu-id="8f140-122">In the **Location profile ID** field, select _FLOOR_.</span></span>

3. <span data-ttu-id="8f140-123">Seleziona la riga **Piano**.</span><span class="sxs-lookup"><span data-stu-id="8f140-123">Select the **Floor** line.</span></span>
4. <span data-ttu-id="8f140-124">Nel campo **Numero di origine**, immetti _1_.</span><span class="sxs-lookup"><span data-stu-id="8f140-124">In the **From number** field, enter _1_.</span></span> <span data-ttu-id="8f140-125">Nel campo **Numero di destinazione**, immetti _3_.</span><span class="sxs-lookup"><span data-stu-id="8f140-125">In the **To number** field, enter _3_.</span></span>
5. <span data-ttu-id="8f140-126">Seleziona la riga **Sezione**.</span><span class="sxs-lookup"><span data-stu-id="8f140-126">Select the **Aisle** line.</span></span>
6. <span data-ttu-id="8f140-127">Nel campo **Numero di origine**, immetti _1_.</span><span class="sxs-lookup"><span data-stu-id="8f140-127">In the **From number** field, enter _1_.</span></span> <span data-ttu-id="8f140-128">Nel campo **Numero di destinazione**, immetti _5_.</span><span class="sxs-lookup"><span data-stu-id="8f140-128">In the **To number** field, enter _5_.</span></span>
7. <span data-ttu-id="8f140-129">Selezionare **Crea**.</span><span class="sxs-lookup"><span data-stu-id="8f140-129">Select **Create**.</span></span>
8. <span data-ttu-id="8f140-130">Ricevi messaggi che indicano che sono state aggiunte nuove ubicazioni.</span><span class="sxs-lookup"><span data-stu-id="8f140-130">You receive messages that state that new locations have been added.</span></span> <span data-ttu-id="8f140-131">Seleziona il pulsante **Mostra messaggi** per visualizzare i messaggi.</span><span class="sxs-lookup"><span data-stu-id="8f140-131">Select the **Show messages** button to view the messages.</span></span>
9. <span data-ttu-id="8f140-132">Vai a **Gestione magazzino \> Impostazione \> Magazzino \> Ubicazioni**.</span><span class="sxs-lookup"><span data-stu-id="8f140-132">Go to **Warehouse management \> Setup \> Warehouse \> Locations**.</span></span> <span data-ttu-id="8f140-133">Le nuove ubicazioni vengono visualizzate nell'elenco e tutti i campi della zona sono disponibili (ovvero, il campo della zona esistente e i nuovi campi della zona aggiuntivi).</span><span class="sxs-lookup"><span data-stu-id="8f140-133">The new locations appear in the list, and all zone fields are available (that is, the existing zone field and the new additional zone fields).</span></span>
