---
title: Includere peso e volume del contenitore nel carico
description: In questo argomento viene descritto come impostare e utilizzare la funzionalità che consente di includere peso e volume dei contenitori nei carichi.
author: pjacobse
manager: AnnBe
ms.date: 05/26/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TMSRateRouteWorkbench, TMSDriverLogListPage, TMSTransportationTender
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 269384
ms.search.region: Global
ms.author: pjacobse
ms.search.validFrom: 2017-09-20
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: adbaa379889d373d597b2f6882b78f82bd71ae57
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "1549223"
---
# <a name="include-container-weight-and-volume-on-load"></a><span data-ttu-id="576bb-103">Includere peso e volume del contenitore nel carico</span><span class="sxs-lookup"><span data-stu-id="576bb-103">Include container weight and volume on load</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="576bb-104">La funzionalità che consente di includere peso e volume dei contenitori in un carico fornisce una chiara rappresentazione del peso e del volume totali dei contenitori e degli articoli in un carico.</span><span class="sxs-lookup"><span data-stu-id="576bb-104">The functionality for including the container weight and volume on a load gives a clear representation of the total weight and volume of containers and items that are going on a load.</span></span>

<span data-ttu-id="576bb-105">Un carico contiene una o più spedizioni e tali spedizioni includono articoli distinti che appartengono a uno o più ordini cliente.</span><span class="sxs-lookup"><span data-stu-id="576bb-105">A load contains a single shipment or multiple shipments, and these shipments contain distinct items that belong to a single sales order or multiple sales orders.</span></span> <span data-ttu-id="576bb-106">Gli articoli sono immagazzinati in un contenitore e i contenitori vengono caricati in un carico.</span><span class="sxs-lookup"><span data-stu-id="576bb-106">The items are stored inside a container, and containers are loaded on a load.</span></span> <span data-ttu-id="576bb-107">Anche gli articoli al di fuori di un contenitore possono far parte di un carico.</span><span class="sxs-lookup"><span data-stu-id="576bb-107">Items that are outside a container can also be part of a load.</span></span> <span data-ttu-id="576bb-108">In base a queste condizioni, il sistema calcola i valori relativi a peso e volume del carico prendendo in considerazione peso e volume dei contenitori e degli articoli.</span><span class="sxs-lookup"><span data-stu-id="576bb-108">Based on these conditions, the system calculates values for the weight and volume on the load by considering the weight and volume of both containers and items.</span></span>

<span data-ttu-id="576bb-109">Se i valori calcolati non sono precisi, è possibile rettificarli immettendo i valori effettivi del peso e del volume del carico.</span><span class="sxs-lookup"><span data-stu-id="576bb-109">If the calculated values aren’t precise, you can adjust them by entering the actual values for the weight and volume on the load.</span></span> <span data-ttu-id="576bb-110">I valori per il peso e il volume sono utilizzati nei processi di gestione trasporto.</span><span class="sxs-lookup"><span data-stu-id="576bb-110">The values for the weight and volume are used in transportation management processes.</span></span> <span data-ttu-id="576bb-111">Ad esempio, i valori sono utilizzati nella tariffa workbench del ciclo di lavorazione, in quanto consentono di definire la tariffa e il ciclo di lavorazione per i carichi, nonché per i metodi di pagamento del trasporto e per il check-in del conducente.</span><span class="sxs-lookup"><span data-stu-id="576bb-111">For example, the values are used in the rate route workbench, where they help define the rate and route for loads, and they are also used for transportation tenders and driver check-in.</span></span>

## <a name="where-it-applies"></a><span data-ttu-id="576bb-112">Dove si applica</span><span class="sxs-lookup"><span data-stu-id="576bb-112">Where it applies</span></span>

<span data-ttu-id="576bb-113">La funzionalità per l'importazione di peso e volume dei contenitori in un carico viene applicata ai processi di gestione trasporto, ad esempio la tariffa workbench del ciclo di lavorazione, i metodi di pagamento del trasporto e il check-in del conducente.</span><span class="sxs-lookup"><span data-stu-id="576bb-113">The functionality for including the container weight and volume on a load applies in transportation management processes, such as the rate route workbench, transportation tenders, and driver check-in.</span></span>

## <a name="how-it-is-set-up"></a><span data-ttu-id="576bb-114">Come si imposta</span><span class="sxs-lookup"><span data-stu-id="576bb-114">How it is set up</span></span>

<span data-ttu-id="576bb-115">Il numero di contenitori da prendere in considerazione per un carico viene calcolato in base al peso e al volume del contenitore e alla percentuale di utilizzo del contenitore.</span><span class="sxs-lookup"><span data-stu-id="576bb-115">The number of containers that should be considered for a load is calculated based on the weight and volume of the container, and on the percentage of the container is used.</span></span>

-   <span data-ttu-id="576bb-116">Per impostare peso e volume di un contenitore, fare clic su **Gestione magazzino** \> **Impostazione** \> **Contenitori** \> **Tipi di contenitore**.</span><span class="sxs-lookup"><span data-stu-id="576bb-116">To set the weight and volume for a container, click **Warehouse management** \> **Setup** \> **Containers** \> **Container types**.</span></span>

-   <span data-ttu-id="576bb-117">Per impostare la percentuale di utilizzo del contenitore, fare clic su **Gestione magazzino** \> **Impostazione** \> **Contenitori** \> **Gruppo di contenitori** e immettere un valore nel campo **Percentuale di utilizzo contenitore**.</span><span class="sxs-lookup"><span data-stu-id="576bb-117">To set the container utilization percentage, click **Warehouse management** \> **Setup** \> **Containers** \> **Container groups**, and then enter a value in the **Container utilization percentage** field.</span></span>
