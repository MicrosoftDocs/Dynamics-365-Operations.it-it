---
title: Funzionalità rimosse o deprecate in Dynamics 365 Supply Chain Management
description: In questo argomento vengono descritte le funzionalità rimosse, o di cui è stata progettata la rimozione in Dynamics 365 Supply Chain Management.
author: kamaybac
manager: tfehr
ms.date: 04/30/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2020-03-03
ms.dyn365.ops.version: Platform update 33
ms.openlocfilehash: 07f37488747766dcca96884e204339b425bbd201
ms.sourcegitcommit: f64fce03ec52f844b05a9e8cac286cb201385002
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/16/2020
ms.locfileid: "3597118"
---
# <a name="removed-or-deprecated-features-in-dynamics-365-supply-chain-management"></a><span data-ttu-id="3db11-103">Funzionalità rimosse o deprecate in Dynamics 365 Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="3db11-103">Removed or deprecated features in Dynamics 365 Supply Chain Management</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="3db11-104">Questo argomento verrà aggiornato man mano che vengono documentate le nuove funzionalità rimosse o deprecate in Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="3db11-104">This topic will be updated as new removed or deprecated features are documented for Dynamics 365 Supply Chain Management.</span></span>

- <span data-ttu-id="3db11-105">Una funzionalità *rimossa* non è più disponibile nel prodotto.</span><span class="sxs-lookup"><span data-stu-id="3db11-105">A *removed* feature is no longer available in the product.</span></span>
- <span data-ttu-id="3db11-106">Una funzionalità *deprecata* non si trova nella fase attiva di sviluppo e potrebbe essere rimossa in un aggiornamento futuro.</span><span class="sxs-lookup"><span data-stu-id="3db11-106">A *deprecated* feature is not in active development and may be removed in a future update.</span></span>

<span data-ttu-id="3db11-107">Questo elenco ha lo scopo di aiutare a tenere in considerazione queste rimozioni e deprecazioni per la pianificazione.</span><span class="sxs-lookup"><span data-stu-id="3db11-107">This list is intended to help you consider these removals and deprecations for your own planning.</span></span>

> [!NOTE]
> <span data-ttu-id="3db11-108">Informazioni dettagliate sugli oggetti nella app Finance and Operations sono disponibili nei [Report tecnici di riferimento](https://mbs.microsoft.com/customersource/northamerica/AX/downloads/reports/axtechrefrep).</span><span class="sxs-lookup"><span data-stu-id="3db11-108">Detailed information about objects in Finance and Operations apps can be found in the [Technical reference reports](https://mbs.microsoft.com/customersource/northamerica/AX/downloads/reports/axtechrefrep).</span></span> <span data-ttu-id="3db11-109">È possibile confrontare le diverse versioni dei report per ottenere informazioni sugli oggetti che sono stati modificati o rimossi in ogni versione delle app Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="3db11-109">You can compare the different versions of these reports to learn about objects that have changed or been removed in each version of Finance and Operations apps.</span></span>

## <a name="features-removed-or-deprecated-in-the-supply-chain-management-10011-release"></a><span data-ttu-id="3db11-110">Funzionalità rimosse o deprecate nella versione Supply Chain Management 10.0.11</span><span class="sxs-lookup"><span data-stu-id="3db11-110">Features removed or deprecated in the Supply Chain Management 10.0.11 release</span></span>

### <a name="use-of-built-in-supply-chain-management-master-planning-engine-for-distribution-scenarios"></a><span data-ttu-id="3db11-111">Utilizzare il motore di pianificazione generale di Supply Chain Management incorporato per gli scenari di distribuzione</span><span class="sxs-lookup"><span data-stu-id="3db11-111">Use of built-in Supply Chain Management master planning engine for distribution scenarios</span></span>

|   |  |
|------------|--------------------|
| <span data-ttu-id="3db11-112">**Motivo del deprecamento/rimozione**</span><span class="sxs-lookup"><span data-stu-id="3db11-112">**Reason for deprecation/removal**</span></span> | <span data-ttu-id="3db11-113">Per migliorare le prestazioni e ridurre al minimo il carico del database SQL durante le esecuzioni di pianificazione generale, il motore di pianificazione generale di Supply Chain Management incorporato viene sostituito dall'ottimizzazione pianificazione.</span><span class="sxs-lookup"><span data-stu-id="3db11-113">To enhance performance and minimize the SQL database load during master planning runs, the built-in Supply Chain Management master planning engine is being replaced by Planning Optimization.</span></span> <span data-ttu-id="3db11-114">L'ottimizzazione di pianificazione consente le esecuzioni di pianificazione rapide anche durante l'orario di ufficio.</span><span class="sxs-lookup"><span data-stu-id="3db11-114">Planning Optimization allows for fast planning runs that can be performed even during office hours.</span></span> <span data-ttu-id="3db11-115">I pianificatori possono in questo modo rispondere immediatamente ai cambiamenti nella domanda e nei parametri di pianificazione.</span><span class="sxs-lookup"><span data-stu-id="3db11-115">This enables planners to react immediately to changes in demand or planning parameters.</span></span> |
| <span data-ttu-id="3db11-116">**Sostituita da un'altra funzionalità?**</span><span class="sxs-lookup"><span data-stu-id="3db11-116">**Replaced by another feature?**</span></span>   | <span data-ttu-id="3db11-117">Sì, l'ottimizzazione di pianificazione sostituirà l'attuale motore di pianificazione generale di Supply Chain Management incorporato.</span><span class="sxs-lookup"><span data-stu-id="3db11-117">Yes, Planning Optimization will replace the existing built-in Supply Chain Management master planning engine.</span></span> |
| <span data-ttu-id="3db11-118">**Aree del prodotto interessate**</span><span class="sxs-lookup"><span data-stu-id="3db11-118">**Product areas affected**</span></span>         | <span data-ttu-id="3db11-119">Supply Chain Management - Pianificazione master</span><span class="sxs-lookup"><span data-stu-id="3db11-119">Supply Chain Management - Master planning</span></span> |
| <span data-ttu-id="3db11-120">**Opzione di distribuzione**</span><span class="sxs-lookup"><span data-stu-id="3db11-120">**Deployment option**</span></span>              | <span data-ttu-id="3db11-121">Solo cloud.</span><span class="sxs-lookup"><span data-stu-id="3db11-121">Cloud only.</span></span> <span data-ttu-id="3db11-122">L'ottimizzazione di pianificazione non è supportata con le distribuzioni locali.</span><span class="sxs-lookup"><span data-stu-id="3db11-122">Planning Optimization is not supported with on-premises deployments.</span></span> |
| <span data-ttu-id="3db11-123">**Stato**</span><span class="sxs-lookup"><span data-stu-id="3db11-123">**Status**</span></span>                         | <span data-ttu-id="3db11-124">Deprecato.</span><span class="sxs-lookup"><span data-stu-id="3db11-124">Deprecated.</span></span> <span data-ttu-id="3db11-125">Nell'aprile 2021 gli scenari di distribuzione non saranno più supportati con il motore di pianificazione generale Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="3db11-125">On April 2021, distribution scenarios will no longer be supported with the built-in Dynamics 365 Supply Chain Management master planning engine.</span></span> <span data-ttu-id="3db11-126">Per gli scenari di distribuzione, i clienti devono utilizzare l'ottimizzazione di pianificazione per i calcoli della pianificazione generale.</span><span class="sxs-lookup"><span data-stu-id="3db11-126">For distribution scenarios, customers must use Planning Optimization for master planning calculations.</span></span> <span data-ttu-id="3db11-127">Per ulteriori informazioni, vedere [Panoramica dell'ottimizzazione di pianificazione](https://go.microsoft.com/fwlink/?linkid=2105830).</span><span class="sxs-lookup"><span data-stu-id="3db11-127">For more information, see [Planning Optimization documentation](https://go.microsoft.com/fwlink/?linkid=2105830).</span></span> <span data-ttu-id="3db11-128">I clienti con implementazioni locali di Dynamics 365 Supply Chain Management possono continuare a utilizzare il motore di pianificazione generale di Supply Chain Management per gli scenari di distribuzione dopo il mese di aprile 2021.</span><span class="sxs-lookup"><span data-stu-id="3db11-128">Customers with on-premises deployments of Dynamics 365 Supply Chain Management may continue to use the Supply Chain Management master planning engine for distribution scenarios after April 2021.</span></span> <span data-ttu-id="3db11-129">Non verranno tuttavia forniti ulteriori miglioramenti delle funzionalità.</span><span class="sxs-lookup"><span data-stu-id="3db11-129">However, no more feature enhancements will be provided.</span></span> |

## <a name="previous-announcements-about-removed-or-deprecated-features"></a><span data-ttu-id="3db11-130">Annunci precedenti sulle funzionalità rimosse o deprecate</span><span class="sxs-lookup"><span data-stu-id="3db11-130">Previous announcements about removed or deprecated features</span></span>

<span data-ttu-id="3db11-131">Per ulteriori informazioni sulle funzionalità che sono state rimosse o deprecate nelle versioni precedenti, vedere [Funzionalità rimosse o deprecate nelle versioni precedenti](../../fin-ops-core/dev-itpro/migration-upgrade/deprecated-features.md).</span><span class="sxs-lookup"><span data-stu-id="3db11-131">To learn more about features that have been removed or deprecated in previous releases, see [Removed or deprecated features in previous releases](../../fin-ops-core/dev-itpro/migration-upgrade/deprecated-features.md).</span></span>
