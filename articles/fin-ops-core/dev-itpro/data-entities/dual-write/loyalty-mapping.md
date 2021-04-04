---
title: Carte fedeltà dei clienti e punti premio
description: Questo argomento descrive l'integrazione dei dati relativi alle carte fedeltà dei clienti e ai punti premio in doppia scrittura.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 03/10/2019
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 39e1d5b0a73b198b164e51a18222dbd985192070
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2021
ms.locfileid: "5568030"
---
# <a name="customer-loyalty-cards-and-reward-points"></a><span data-ttu-id="42137-103">Carte fedeltà e punti premio fedeltà dei clienti</span><span class="sxs-lookup"><span data-stu-id="42137-103">Customer loyalty cards and reward points</span></span>

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="42137-104">Le aziende classificano i clienti e forniscono servizi sofisticati, basati sui modelli di acquisto e di spesa dei clienti.</span><span class="sxs-lookup"><span data-stu-id="42137-104">Businesses classify customers and provide sophisticated services, based on customer shopping and spending patterns.</span></span> <span data-ttu-id="42137-105">Per esempio, Dynamics 365 Commerce dispone dell'infrastruttura e delle funzioni per facilitare e gestire le carte fedeltà dei clienti, i punti premio, i prezzi basati sulla fedeltà e le esperienze di acquisto basate sui premi.</span><span class="sxs-lookup"><span data-stu-id="42137-105">For example, Dynamics 365 Commerce has the infrastructure and functions to facilitate and handle customer loyalty cards, reward points, loyalty-based pricing, and rewards-based shopping experiences.</span></span> <span data-ttu-id="42137-106">Quando i dati relativi alle carte fedeltà dei clienti e ai punti premio in Commerce vengono sincronizzati con Dataverse, le app Customer Engagement possono utilizzare tali dati.</span><span class="sxs-lookup"><span data-stu-id="42137-106">When data about customer loyalty cards and reward points in Commerce is synced to Dataverse, customer engagement apps can use that data.</span></span> <span data-ttu-id="42137-107">Ad esempio, gli utenti Dynamics 365 Customer Service possono utilizzare i dati per fornire gli stessi servizi sofisticati tramite l'help desk.</span><span class="sxs-lookup"><span data-stu-id="42137-107">For example, Dynamics 365 Customer Service users can use the data to provide the same sophisticated services through the help desk.</span></span>

## <a name="templates"></a><span data-ttu-id="42137-108">Modelli</span><span class="sxs-lookup"><span data-stu-id="42137-108">Templates</span></span>

| <span data-ttu-id="42137-109">App di Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="42137-109">Finance and Operations apps</span></span> | <span data-ttu-id="42137-110">App basate su modello in Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="42137-110">Model-driven apps in Dynamics 365</span></span> | <span data-ttu-id="42137-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="42137-111">Description</span></span> |
|-----------------------------|-----------------------------------|-------------|
| <span data-ttu-id="42137-112">Carta fedeltà</span><span class="sxs-lookup"><span data-stu-id="42137-112">Loyalty card</span></span>                | <span data-ttu-id="42137-113">msdyn\_loyaltycards</span><span class="sxs-lookup"><span data-stu-id="42137-113">msdyn\_loyaltycards</span></span>               | <span data-ttu-id="42137-114">Questo modello sincronizza le informazioni delle carte fedeltà dei clienti.</span><span class="sxs-lookup"><span data-stu-id="42137-114">This template syncs information about customer loyalty cards.</span></span> |
| <span data-ttu-id="42137-115">Punti premio fedeltà</span><span class="sxs-lookup"><span data-stu-id="42137-115">Loyalty reward points</span></span>       | <span data-ttu-id="42137-116">msdyn\_loyaltyrewardpoints</span><span class="sxs-lookup"><span data-stu-id="42137-116">msdyn\_loyaltyrewardpoints</span></span>        | <span data-ttu-id="42137-117">Questo modello sincronizza le informazioni dei punti premio dei clienti.</span><span class="sxs-lookup"><span data-stu-id="42137-117">This template syncs information about customer reward points.</span></span> |

[!include [banner](../../includes/dual-write-symbols.md)]

[!include [mapping loyalty card](includes/LoyaltyCard-msdyn-loyaltycards.md)]

[!include [mapping reward points](includes/LoyaltyRewardPoints-msdyn-loyaltyrewardpoints.md)]


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]