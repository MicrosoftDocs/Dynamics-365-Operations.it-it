---
title: Funzionalità rimosse o deprecate in Lifecycle Services (LCS)
description: In questo argomento vengono descritte le funzionalità rimosse, o di cui è stata progettata la rimozione da Microsoft Dynamics Lifecycle Services (LCS).
author: sericks007
manager: AnnBe
ms.date: 12/02/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.scope: Operations
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: c792d06e9b0aa42919de924bdcc9118358779b72
ms.sourcegitcommit: 75bbcff474cfb8d2f282be2b9d2d7984d1505fa3
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/03/2019
ms.locfileid: "2885457"
---
# <a name="removed-or-deprecated-features-in-lifecycle-services-lcs"></a><span data-ttu-id="cae02-103">Funzionalità rimosse o deprecate in Lifecycle Services (LCS)</span><span class="sxs-lookup"><span data-stu-id="cae02-103">Removed or deprecated features in Lifecycle Services (LCS)</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="cae02-104">In questo argomento vengono descritte le funzionalità che sono state rimosse o deprecate in Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="cae02-104">This topic describes features that have been removed or deprecated for Microsoft Dynamics Lifecycle Services (LCS).</span></span>

- <span data-ttu-id="cae02-105">Una funzionalità *rimossa* non è più disponibile nel servizio.</span><span class="sxs-lookup"><span data-stu-id="cae02-105">A *removed* feature is no longer available in the service.</span></span>
- <span data-ttu-id="cae02-106">Una funzionalità *deprecata* non si trova nella fase attiva di sviluppo e potrebbe essere rimossa in un aggiornamento futuro.</span><span class="sxs-lookup"><span data-stu-id="cae02-106">A *deprecated* feature isn't in active development and might be removed in a future update.</span></span>

<span data-ttu-id="cae02-107">Questo elenco viene fornito per aiutare a tenere in considerazione queste rimozioni e deprecazioni per la pianificazione.</span><span class="sxs-lookup"><span data-stu-id="cae02-107">This list is provided so that you can consider these removals and deprecations as you do your own planning.</span></span>

## <a name="october-2019-announcements"></a><span data-ttu-id="cae02-108">Annunci di ottobre 2019</span><span class="sxs-lookup"><span data-stu-id="cae02-108">October 2019 announcements</span></span>

### <a name="flowchart-diagrams-in-business-process-modeler"></a><span data-ttu-id="cae02-109">Diagrammi di flusso in Modellatore di processi aziendali</span><span class="sxs-lookup"><span data-stu-id="cae02-109">Flowchart diagrams in Business process modeler</span></span>

<table>
<tbody>
<tr>
<td><span data-ttu-id="cae02-110"><strong>Motivo del deprecamento/rimozione</strong></span><span class="sxs-lookup"><span data-stu-id="cae02-110"><strong>Reason for deprecation/removal</strong></span></span></td>
<td><span data-ttu-id="cae02-111">Il componente diagramma di flusso in Business process modeler (BPM) viene deprecato in ragione dello scarso utilizzo della progettazione legacy.</span><span class="sxs-lookup"><span data-stu-id="cae02-111">We are deprecating the flowchart diagrams component in Business process modeler (BPM), because the legacy design caused low usage.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="cae02-112"><strong>Sostituita da un'altra funzionalità?</strong></span><span class="sxs-lookup"><span data-stu-id="cae02-112"><strong>Replaced by another feature?</strong></span></span></td>
<td><span data-ttu-id="cae02-113">Nessuno</span><span class="sxs-lookup"><span data-stu-id="cae02-113">No</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="cae02-114"><strong>Aree interessate</strong></span><span class="sxs-lookup"><span data-stu-id="cae02-114"><strong>Areas affected</strong></span></span></td>
<td><span data-ttu-id="cae02-115">Modellatore di processi aziendali</span><span class="sxs-lookup"><span data-stu-id="cae02-115">Business process modeler</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="cae02-116"><strong>Stato</strong></span><span class="sxs-lookup"><span data-stu-id="cae02-116"><strong>Status</strong></span></span></td>
<td><span data-ttu-id="cae02-117">Deprecato: il componente diagrammi di flusso in BPM dovrebbe essere rimosso all'inizio di febbraio 2020.</span><span class="sxs-lookup"><span data-stu-id="cae02-117">Deprecated: The flowchart diagrams component in BPM is expected to be removed by early February 2020.</span></span> <span data-ttu-id="cae02-118">Le seguenti funzionalità verranno rimosse:</span><span class="sxs-lookup"><span data-stu-id="cae02-118">The following functionality will be removed:</span></span>
<ul>
<li><span data-ttu-id="cae02-119">I diagrammi di flusso esistenti non saranno disponibili per la visualizzazione o la modifica.</span><span class="sxs-lookup"><span data-stu-id="cae02-119">Existing flowcharts will be unavailable for viewing or editing.</span></span> <span data-ttu-id="cae02-120">Anche le proprietà della forma associate alle attività del diagramma di flusso non saranno disponibili, poiché l'intera scheda <strong>Diagramma di flusso</strong> verrà rimossa.</span><span class="sxs-lookup"><span data-stu-id="cae02-120">The shape properties that are associated with flowchart activities will also be unavailable, because the whole <strong>Flowchart</strong> tab will be removed.</span></span> <span data-ttu-id="cae02-121">Questi diagrammi di flusso includono sia diagrammi di flusso predefiniti che vengono generati automaticamente sia diagrammi di flusso personalizzati che vengono modificati in base a tali diagrammi di flusso predefiniti.</span><span class="sxs-lookup"><span data-stu-id="cae02-121">These flowcharts include both the default flowcharts that are automatically generated and customized flowcharts that are modified based on those default flowcharts.</span></span></li>
<li><span data-ttu-id="cae02-122">La funzionalità di analisi degli scostamenti/adeguatezza non sarà disponibile.</span><span class="sxs-lookup"><span data-stu-id="cae02-122">The legacy fit/gap analysis feature will be unavailable.</span></span> <span data-ttu-id="cae02-123">Pertanto, nessun elenco di scostamenti verrà automaticamente creato o sarà disponibile per l'esportazione.</span><span class="sxs-lookup"><span data-stu-id="cae02-123">Therefore, no gap list will be automatically created or available for export.</span></span>
<p><span data-ttu-id="cae02-124"><strong>Nota:</strong> questa funzionalità era stata precedentemente deprecata e sostituita dalle integrazioni di  Microsoft Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="cae02-124"><strong>Note:</strong> This feature had previously been deprecated and replaced by Microsoft Azure DevOps integrations.</span></span></p>
</li>
<li><span data-ttu-id="cae02-125">La cronologia delle versioni del diagramma di flusso non sarà disponibile.</span><span class="sxs-lookup"><span data-stu-id="cae02-125">The version history of the flowchart will be unavailable.</span></span></li>
</ul>
</td>
</tr>
</tbody>
</table>
