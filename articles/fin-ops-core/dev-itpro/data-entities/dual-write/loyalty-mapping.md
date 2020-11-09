---
title: Carte fedeltà dei clienti e punti premio
description: Questo argomento descrive l'integrazione dei dati relativi alle carte fedeltà dei clienti e ai punti premio tra le app Finance and Operations e Common Data Service.
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
ms.openlocfilehash: 24ce08bb6cba9c74075151bafe0b07509fbdf73d
ms.sourcegitcommit: 0a741b131ed71f6345d4219a47cf5f71fec6744b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "3998016"
---
# <a name="customer-loyalty-cards-and-reward-points"></a><span data-ttu-id="33c90-103">Carte fedeltà dei clienti e punti premio</span><span class="sxs-lookup"><span data-stu-id="33c90-103">Customer loyalty cards and reward points</span></span>

[!include [banner](../../includes/banner.md)]



<span data-ttu-id="33c90-104">Le aziende classificano i clienti e forniscono servizi sofisticati, basati sui modelli di acquisto e di spesa dei clienti.</span><span class="sxs-lookup"><span data-stu-id="33c90-104">Businesses classify customers and provide sophisticated services, based on customer shopping and spending patterns.</span></span> <span data-ttu-id="33c90-105">Nella suite di applicazioni Microsoft Dynamics 365, Dynamics 365 Commerce dispone dell'infrastruttura e delle funzioni per facilitare e gestire le carte fedeltà dei clienti, i punti premio, i prezzi basati sulla fedeltà e le esperienze di acquisto basate sui premi.</span><span class="sxs-lookup"><span data-stu-id="33c90-105">In the Microsoft Dynamics 365 suite of applications, Dynamics 365 Commerce has the infrastructure and functions to facilitate and handle customer loyalty cards, reward points, loyalty-based pricing, and rewards-based shopping experiences.</span></span> <span data-ttu-id="33c90-106">Quando i dati relativi alle carte fedeltà dei clienti e ai punti premio in Commerce vengono sincronizzati con Common Data Service, le app basate su modello in Dynamics 365 possono utilizzare tali dati.</span><span class="sxs-lookup"><span data-stu-id="33c90-106">When data about customer loyalty cards and reward points in Commerce is synced to Common Data service, model-driven apps in Dynamics 365 can use that data.</span></span> <span data-ttu-id="33c90-107">Ad esempio, gli utenti Dynamics 365 Customer Service possono utilizzare i dati per fornire gli stessi servizi sofisticati tramite l'help desk.</span><span class="sxs-lookup"><span data-stu-id="33c90-107">For example, Dynamics 365 Customer Service users can use the data to provide the same sophisticated services through the help desk.</span></span>

## <a name="templates"></a><span data-ttu-id="33c90-108">Modelli</span><span class="sxs-lookup"><span data-stu-id="33c90-108">Templates</span></span>

| <span data-ttu-id="33c90-109">App di Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="33c90-109">Finance and Operations apps</span></span> | <span data-ttu-id="33c90-110">App basate su modello in Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="33c90-110">Model-driven apps in Dynamics 365</span></span> | <span data-ttu-id="33c90-111">descrizione</span><span class="sxs-lookup"><span data-stu-id="33c90-111">Description</span></span> |
|-----------------------------|-----------------------------------|-------------|
| <span data-ttu-id="33c90-112">Carta fedeltà</span><span class="sxs-lookup"><span data-stu-id="33c90-112">Loyalty card</span></span>                | <span data-ttu-id="33c90-113">msdyn\_loyaltycards</span><span class="sxs-lookup"><span data-stu-id="33c90-113">msdyn\_loyaltycards</span></span>               | <span data-ttu-id="33c90-114">Questo modello sincronizza le informazioni delle carte fedeltà dei clienti.</span><span class="sxs-lookup"><span data-stu-id="33c90-114">This template syncs information about customer loyalty cards.</span></span> |
| <span data-ttu-id="33c90-115">Punti premio fedeltà</span><span class="sxs-lookup"><span data-stu-id="33c90-115">Loyalty reward points</span></span>       | <span data-ttu-id="33c90-116">msdyn\_loyaltyrewardpoints</span><span class="sxs-lookup"><span data-stu-id="33c90-116">msdyn\_loyaltyrewardpoints</span></span>        | <span data-ttu-id="33c90-117">Questo modello sincronizza le informazioni dei punti premio dei clienti.</span><span class="sxs-lookup"><span data-stu-id="33c90-117">This template syncs information about customer reward points.</span></span> |

[!include [banner](../../includes/dual-write-symbols.md)]

[!include [mapping loyalty card](includes/LoyaltyCard-msdyn-loyaltycards.md)]

[!include [mapping reward points](includes/LoyaltyRewardPoints-msdyn-loyaltyrewardpoints.md)]
