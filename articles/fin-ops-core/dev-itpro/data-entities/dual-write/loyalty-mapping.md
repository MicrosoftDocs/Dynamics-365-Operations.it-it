---
title: Carte fedeltà dei clienti e punti premio
description: Questo argomento descrive l'integrazione dei dati relativi alle carte fedeltà dei clienti e ai punti premio in doppia scrittura.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 03/10/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-10
ms.openlocfilehash: 28872e9510394cf3d5cee151798d4130b8b6fe27
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/05/2020
ms.locfileid: "4683500"
---
# <a name="customer-loyalty-cards-and-reward-points"></a><span data-ttu-id="c3a31-103">Carte fedeltà e punti premio fedeltà dei clienti</span><span class="sxs-lookup"><span data-stu-id="c3a31-103">Customer loyalty cards and reward points</span></span>

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="c3a31-104">Le aziende classificano i clienti e forniscono servizi sofisticati, basati sui modelli di acquisto e di spesa dei clienti.</span><span class="sxs-lookup"><span data-stu-id="c3a31-104">Businesses classify customers and provide sophisticated services, based on customer shopping and spending patterns.</span></span> <span data-ttu-id="c3a31-105">Per esempio, Dynamics 365 Commerce dispone dell'infrastruttura e delle funzioni per facilitare e gestire le carte fedeltà dei clienti, i punti premio, i prezzi basati sulla fedeltà e le esperienze di acquisto basate sui premi.</span><span class="sxs-lookup"><span data-stu-id="c3a31-105">For example, Dynamics 365 Commerce has the infrastructure and functions to facilitate and handle customer loyalty cards, reward points, loyalty-based pricing, and rewards-based shopping experiences.</span></span> <span data-ttu-id="c3a31-106">Quando i dati relativi alle carte fedeltà dei clienti e ai punti premio in Commerce vengono sincronizzati con Dataverse, le app Customer Engagement possono utilizzare tali dati.</span><span class="sxs-lookup"><span data-stu-id="c3a31-106">When data about customer loyalty cards and reward points in Commerce is synced to Dataverse, customer engagement apps can use that data.</span></span> <span data-ttu-id="c3a31-107">Ad esempio, gli utenti Dynamics 365 Customer Service possono utilizzare i dati per fornire gli stessi servizi sofisticati tramite l'help desk.</span><span class="sxs-lookup"><span data-stu-id="c3a31-107">For example, Dynamics 365 Customer Service users can use the data to provide the same sophisticated services through the help desk.</span></span>

## <a name="templates"></a><span data-ttu-id="c3a31-108">Modelli</span><span class="sxs-lookup"><span data-stu-id="c3a31-108">Templates</span></span>

| <span data-ttu-id="c3a31-109">App di Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="c3a31-109">Finance and Operations apps</span></span> | <span data-ttu-id="c3a31-110">App basate su modello in Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="c3a31-110">Model-driven apps in Dynamics 365</span></span> | <span data-ttu-id="c3a31-111">descrizione</span><span class="sxs-lookup"><span data-stu-id="c3a31-111">Description</span></span> |
|-----------------------------|-----------------------------------|-------------|
| <span data-ttu-id="c3a31-112">Carta fedeltà</span><span class="sxs-lookup"><span data-stu-id="c3a31-112">Loyalty card</span></span>                | <span data-ttu-id="c3a31-113">msdyn\_loyaltycards</span><span class="sxs-lookup"><span data-stu-id="c3a31-113">msdyn\_loyaltycards</span></span>               | <span data-ttu-id="c3a31-114">Questo modello sincronizza le informazioni delle carte fedeltà dei clienti.</span><span class="sxs-lookup"><span data-stu-id="c3a31-114">This template syncs information about customer loyalty cards.</span></span> |
| <span data-ttu-id="c3a31-115">Punti premio fedeltà</span><span class="sxs-lookup"><span data-stu-id="c3a31-115">Loyalty reward points</span></span>       | <span data-ttu-id="c3a31-116">msdyn\_loyaltyrewardpoints</span><span class="sxs-lookup"><span data-stu-id="c3a31-116">msdyn\_loyaltyrewardpoints</span></span>        | <span data-ttu-id="c3a31-117">Questo modello sincronizza le informazioni dei punti premio dei clienti.</span><span class="sxs-lookup"><span data-stu-id="c3a31-117">This template syncs information about customer reward points.</span></span> |

[!include [banner](../../includes/dual-write-symbols.md)]

[!include [mapping loyalty card](includes/LoyaltyCard-msdyn-loyaltycards.md)]

[!include [mapping reward points](includes/LoyaltyRewardPoints-msdyn-loyaltyrewardpoints.md)]
