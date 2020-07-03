---
title: Funzionalità rimosse o deprecate in Lifecycle Services (LCS)
description: In questo argomento vengono descritte le funzionalità rimosse, o di cui è stata progettata la rimozione da Microsoft Dynamics Lifecycle Services (LCS).
author: AngelMarshall
manager: AnnBe
ms.date: 06/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.scope: Operations
ms.search.region: Global
ms.author: tsmarsha
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: e571cc26f55e0bd7a1eef301e193921e0b3f8e31
ms.sourcegitcommit: ac47e8679fb104515f7dcca509294264bd05d2b1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/15/2020
ms.locfileid: "3454697"
---
# <a name="removed-or-deprecated-features-in-lifecycle-services-lcs"></a><span data-ttu-id="5ba05-103">Funzionalità rimosse o deprecate in Lifecycle Services (LCS)</span><span class="sxs-lookup"><span data-stu-id="5ba05-103">Removed or deprecated features in Lifecycle Services (LCS)</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="5ba05-104">In questo argomento vengono descritte le funzionalità che sono state rimosse o deprecate in Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="5ba05-104">This topic describes features that have been removed or deprecated for Microsoft Dynamics Lifecycle Services (LCS).</span></span>

- <span data-ttu-id="5ba05-105">Una funzionalità *rimossa* non è più disponibile nel servizio.</span><span class="sxs-lookup"><span data-stu-id="5ba05-105">A *removed* feature is no longer available in the service.</span></span>
- <span data-ttu-id="5ba05-106">Una funzionalità *deprecata* non si trova nella fase attiva di sviluppo e potrebbe essere rimossa in un aggiornamento futuro.</span><span class="sxs-lookup"><span data-stu-id="5ba05-106">A *deprecated* feature isn't in active development and might be removed in a future update.</span></span>

<span data-ttu-id="5ba05-107">Questo elenco viene fornito per aiutare a tenere in considerazione queste rimozioni e deprecazioni per la pianificazione.</span><span class="sxs-lookup"><span data-stu-id="5ba05-107">This list is provided so that you can consider these removals and deprecations as you do your own planning.</span></span>

## <a name="october-2019-announcements"></a><span data-ttu-id="5ba05-108">Annunci di ottobre 2019</span><span class="sxs-lookup"><span data-stu-id="5ba05-108">October 2019 announcements</span></span>

### <a name="flowchart-diagrams-in-business-process-modeler"></a><span data-ttu-id="5ba05-109">Diagrammi di flusso in Modellatore di processi aziendali</span><span class="sxs-lookup"><span data-stu-id="5ba05-109">Flowchart diagrams in Business process modeler</span></span>

<table>
<tbody>
<tr>
<td><span data-ttu-id="5ba05-110"><strong>Motivo del deprecamento/rimozione</strong></span><span class="sxs-lookup"><span data-stu-id="5ba05-110"><strong>Reason for deprecation/removal</strong></span></span></td>
<td><span data-ttu-id="5ba05-111">Il componente diagramma di flusso in Business process modeler (BPM) viene deprecato in ragione dello scarso utilizzo della progettazione legacy.</span><span class="sxs-lookup"><span data-stu-id="5ba05-111">We are deprecating the flowchart diagrams component in Business process modeler (BPM), because the legacy design caused low usage.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5ba05-112"><strong>Sostituita da un'altra funzionalità?</strong></span><span class="sxs-lookup"><span data-stu-id="5ba05-112"><strong>Replaced by another feature?</strong></span></span></td>
<td><span data-ttu-id="5ba05-113">Nessuno</span><span class="sxs-lookup"><span data-stu-id="5ba05-113">No</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5ba05-114"><strong>Aree interessate</strong></span><span class="sxs-lookup"><span data-stu-id="5ba05-114"><strong>Areas affected</strong></span></span></td>
<td><span data-ttu-id="5ba05-115">Modellatore di processi aziendali</span><span class="sxs-lookup"><span data-stu-id="5ba05-115">Business process modeler</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5ba05-116"><strong>Stato</strong></span><span class="sxs-lookup"><span data-stu-id="5ba05-116"><strong>Status</strong></span></span></td>
<td><span data-ttu-id="5ba05-117">Deprecato: il componente diagrammi di flusso in BPM dovrebbe essere rimosso nel 2020.</span><span class="sxs-lookup"><span data-stu-id="5ba05-117">Deprecated: The flowchart diagrams component in BPM is expected to be removed in 2020.</span></span> <span data-ttu-id="5ba05-118">La seguente funzionalità diventerà non disponibile:</span><span class="sxs-lookup"><span data-stu-id="5ba05-118">The following functionality will be unavailable:</span></span>
<ul>
<li><span data-ttu-id="5ba05-119">Tutti i diagrammi di flusso saranno di sola lettura e non disponibili per la modifica.</span><span class="sxs-lookup"><span data-stu-id="5ba05-119">All flowcharts will be read-only and unavailable for editing.</span></span> <span data-ttu-id="5ba05-120">Anche le proprietà della forma associate alle attività del diagramma di flusso non saranno disponibili.</span><span class="sxs-lookup"><span data-stu-id="5ba05-120">The shape properties that are associated with flowchart activities will also be unavailable.</span></span> <span data-ttu-id="5ba05-121">Questi diagrammi di flusso includono sia diagrammi di flusso predefiniti che vengono generati automaticamente sia diagrammi di flusso personalizzati che vengono modificati in base a tali diagrammi di flusso predefiniti.</span><span class="sxs-lookup"><span data-stu-id="5ba05-121">These flowcharts include both the default flowcharts that are automatically generated and customized flowcharts that are modified based on those default flowcharts.</span></span></li>
<li><span data-ttu-id="5ba05-122">I passaggi della procedura saranno di sola lettura e non disponibili per la modifica.</span><span class="sxs-lookup"><span data-stu-id="5ba05-122">The process steps will be read-only and unavailable for editing.</span></span></li>     
<li><span data-ttu-id="5ba05-123">La funzionalità di analisi degli scostamenti/adeguatezza non sarà disponibile.</span><span class="sxs-lookup"><span data-stu-id="5ba05-123">The legacy fit/gap analysis feature will be unavailable.</span></span> <span data-ttu-id="5ba05-124">Pertanto, nessun elenco di scostamenti verrà automaticamente creato o sarà disponibile per l'esportazione.</span><span class="sxs-lookup"><span data-stu-id="5ba05-124">Therefore, no gap list will be automatically created or available for export.</span></span>
<p><span data-ttu-id="5ba05-125"><strong>Nota:</strong> questa funzionalità era stata precedentemente deprecata e sostituita dalle integrazioni di  Microsoft Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="5ba05-125"><strong>Note:</strong> This feature had previously been deprecated and replaced by Microsoft Azure DevOps integrations.</span></span></p>
</li>
<li><span data-ttu-id="5ba05-126">La cronologia delle versioni del diagramma di flusso non sarà disponibile.</span><span class="sxs-lookup"><span data-stu-id="5ba05-126">The version history of the flowchart will be unavailable.</span></span></li>
</ul>
</td>
</tr>
</tbody>
</table>
