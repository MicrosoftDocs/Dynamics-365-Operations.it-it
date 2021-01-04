---
title: Stati della gestione trasporto
description: Questo argomento spiega come creare uno stato di trasporto e mappare tale stato a uno stato di vettore.
author: Henrikan
manager: tfehr
ms.date: 10/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2020-09-08
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: 3f7d471771ec2b4703d878fbf395cd90902b6669
ms.sourcegitcommit: fe7ac653efcb1ac6318083f482394b96ed82b4c7
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/29/2020
ms.locfileid: "4431611"
---
# <a name="transportation-management-statuses"></a><span data-ttu-id="37d32-103">Stati della gestione trasporto</span><span class="sxs-lookup"><span data-stu-id="37d32-103">Transportation management statuses</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="37d32-104">Impostare codici principali per gli stati di trasporto per interpretare i codici che sono forniti dai vettori di spedizione.</span><span class="sxs-lookup"><span data-stu-id="37d32-104">Set up master codes for transportation statuses to interpret codes that are provided by your shipping carriers.</span></span> <span data-ttu-id="37d32-105">Ciò consente l'integrazione con i vettori di spedizione per fornire uno stato.</span><span class="sxs-lookup"><span data-stu-id="37d32-105">This lets you integrate with shipping carriers to provide a status.</span></span> <span data-ttu-id="37d32-106">Lo stato del trasporto che si fornisce per un codice dello stato di trasporto principale consente di tenere traccia dello stato di un carico, una spedizione o un contenitore.</span><span class="sxs-lookup"><span data-stu-id="37d32-106">The transportation status that you provide for a transportation master status code can help you track the status of a load, shipment, or container.</span></span> <span data-ttu-id="37d32-107">Lo stato di trasporto specifico per un carico, una spedizione o un container può essere aggiornato solo tramite l'integrazione dei dati e non manualmente tramite l'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="37d32-107">The specific transportation status for a load, shipment, or container can only be updated through data integration and not manually through the user interface.</span></span>

## <a name="create-a-transportation-status"></a><span data-ttu-id="37d32-108">Creare uno stato di trasporto</span><span class="sxs-lookup"><span data-stu-id="37d32-108">Create a transportation status</span></span>

<span data-ttu-id="37d32-109">Per creare uno stato di trasporto, effettuare le seguenti operazioni:</span><span class="sxs-lookup"><span data-stu-id="37d32-109">To create a transportation status, follow these steps:</span></span>

1. <span data-ttu-id="37d32-110">Andare a **Gestione trasporto \> Impostazione \> Stato trasporto principale**.</span><span class="sxs-lookup"><span data-stu-id="37d32-110">Go to **Transportation management \> Setup \> Transportation status masters**.</span></span>
1. <span data-ttu-id="37d32-111">Selezionare **Nuovo** per creare uno stato di trasporto principale.</span><span class="sxs-lookup"><span data-stu-id="37d32-111">Select **New** to create a transportation status master.</span></span>
1. <span data-ttu-id="37d32-112">Nel campo **Stato trasporto principale** immettere un codice univoco per lo stato del trasporto.</span><span class="sxs-lookup"><span data-stu-id="37d32-112">In the **Transportation status master** field, enter a unique code for the transportation status.</span></span>
1. <span data-ttu-id="37d32-113">Nel campo **Tipo di trasporto** selezionare *Vettore di spedizione* o *Hub* come il tipo di trasporto.</span><span class="sxs-lookup"><span data-stu-id="37d32-113">In the **Transportation type** field, select either *Shipping carrier* or *Hub* as the type of transportation.</span></span>
1. <span data-ttu-id="37d32-114">Immettere un nome e lo stato del trasporto.</span><span class="sxs-lookup"><span data-stu-id="37d32-114">Enter a name and transportation status.</span></span>
1. <span data-ttu-id="37d32-115">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="37d32-115">Close the page.</span></span>

## <a name="map-a-transportation-status-to-a-carrier-status"></a><span data-ttu-id="37d32-116">Associare uno stato di trasporto a uno stato di vettore</span><span class="sxs-lookup"><span data-stu-id="37d32-116">Map a transportation status to a carrier status</span></span>

<span data-ttu-id="37d32-117">Per associare uno stato di trasporto a uno stato di vettore, effettuare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="37d32-117">To map a transportation status to a carrier status, follow these steps:</span></span>

1. <span data-ttu-id="37d32-118">Andare a **Gestione trasporto \> Impostazione \> Vettori \> Stato trasporto vettore**.</span><span class="sxs-lookup"><span data-stu-id="37d32-118">Go to **Transportation management \> Setup \> Carriers \> Carrier transportation status**.</span></span>
1. <span data-ttu-id="37d32-119">Selezionare **Nuovo** per mappare un vettore di spedizione a un codice dello stato di trasporto principale.</span><span class="sxs-lookup"><span data-stu-id="37d32-119">Select **New** to map a code from a shipping carrier to a transportation status master code.</span></span>
1. <span data-ttu-id="37d32-120">Selezionare l'ID univoco del vettore di spedizione e il servizio di trasporto.</span><span class="sxs-lookup"><span data-stu-id="37d32-120">Select the unique ID for the shipping carrier and the carrier service.</span></span>
1. <span data-ttu-id="37d32-121">Selezionare il codice dello stato di trasporto che si desidera mappare al codice del vettore di spedizione selezionato.</span><span class="sxs-lookup"><span data-stu-id="37d32-121">Select the transportation status code that you want to map to the selected shipping carrier's code.</span></span>
1. <span data-ttu-id="37d32-122">Immettere il codice esterno utilizzato dal vettore di spedizione.</span><span class="sxs-lookup"><span data-stu-id="37d32-122">Enter the external code that is used by the shipping carrier.</span></span>
1. <span data-ttu-id="37d32-123">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="37d32-123">Close the page.</span></span>
