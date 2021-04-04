---
title: Funzionalità rimosse o deprecate in Lifecycle Services (LCS)
description: In questo argomento vengono descritte le funzionalità rimosse, o di cui è stata progettata la rimozione da Microsoft Dynamics Lifecycle Services (LCS).
author: AngelMarshall
manager: AnnBe
ms.date: 06/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: tsmarsha
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 6b49a6f26b4c2fa895fe0e49f716ce423c3c0057
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2021
ms.locfileid: "5559087"
---
# <a name="removed-or-deprecated-features-in-lifecycle-services-lcs"></a><span data-ttu-id="77b19-103">Funzionalità rimosse o deprecate in Lifecycle Services (LCS)</span><span class="sxs-lookup"><span data-stu-id="77b19-103">Removed or deprecated features in Lifecycle Services (LCS)</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="77b19-104">In questo argomento vengono descritte le funzionalità che sono state rimosse o deprecate in Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="77b19-104">This topic describes features that have been removed or deprecated for Microsoft Dynamics Lifecycle Services (LCS).</span></span>

- <span data-ttu-id="77b19-105">Una funzionalità *rimossa* non è più disponibile nel servizio.</span><span class="sxs-lookup"><span data-stu-id="77b19-105">A *removed* feature is no longer available in the service.</span></span>
- <span data-ttu-id="77b19-106">Una funzionalità *deprecata* non si trova nella fase attiva di sviluppo e potrebbe essere rimossa in un aggiornamento futuro.</span><span class="sxs-lookup"><span data-stu-id="77b19-106">A *deprecated* feature isn't in active development and might be removed in a future update.</span></span>

<span data-ttu-id="77b19-107">Questo elenco viene fornito per aiutare a tenere in considerazione queste rimozioni e deprecazioni per la pianificazione.</span><span class="sxs-lookup"><span data-stu-id="77b19-107">This list is provided so that you can consider these removals and deprecations as you do your own planning.</span></span>

## <a name="october-2019-announcements"></a><span data-ttu-id="77b19-108">Annunci di ottobre 2019</span><span class="sxs-lookup"><span data-stu-id="77b19-108">October 2019 announcements</span></span>

### <a name="flowchart-diagrams-in-business-process-modeler"></a><span data-ttu-id="77b19-109">Diagrammi di flusso in Modellatore di processi aziendali</span><span class="sxs-lookup"><span data-stu-id="77b19-109">Flowchart diagrams in Business process modeler</span></span>

<table>
<tbody>
<tr>
<td><span data-ttu-id="77b19-110"><strong>Motivo del deprecamento/rimozione</strong></span><span class="sxs-lookup"><span data-stu-id="77b19-110"><strong>Reason for deprecation/removal</strong></span></span></td>
<td><span data-ttu-id="77b19-111">Il componente diagramma di flusso in Business process modeler (BPM) viene deprecato in ragione dello scarso utilizzo della progettazione legacy.</span><span class="sxs-lookup"><span data-stu-id="77b19-111">We are deprecating the flowchart diagrams component in Business process modeler (BPM), because the legacy design caused low usage.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="77b19-112"><strong>Sostituita da un'altra funzionalità?</strong></span><span class="sxs-lookup"><span data-stu-id="77b19-112"><strong>Replaced by another feature?</strong></span></span></td>
<td><span data-ttu-id="77b19-113">Nessuno</span><span class="sxs-lookup"><span data-stu-id="77b19-113">No</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="77b19-114"><strong>Aree interessate</strong></span><span class="sxs-lookup"><span data-stu-id="77b19-114"><strong>Areas affected</strong></span></span></td>
<td><span data-ttu-id="77b19-115">Modellatore di processi aziendali</span><span class="sxs-lookup"><span data-stu-id="77b19-115">Business process modeler</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="77b19-116"><strong>Stato</strong></span><span class="sxs-lookup"><span data-stu-id="77b19-116"><strong>Status</strong></span></span></td>
<td><span data-ttu-id="77b19-117">Deprecato: il componente diagrammi di flusso in BPM dovrebbe essere rimosso nel 2020.</span><span class="sxs-lookup"><span data-stu-id="77b19-117">Deprecated: The flowchart diagrams component in BPM is expected to be removed in 2020.</span></span> <span data-ttu-id="77b19-118">La seguente funzionalità diventerà non disponibile:</span><span class="sxs-lookup"><span data-stu-id="77b19-118">The following functionality will be unavailable:</span></span>
<ul>
<li><span data-ttu-id="77b19-119">Tutti i diagrammi di flusso saranno di sola lettura e non disponibili per la modifica.</span><span class="sxs-lookup"><span data-stu-id="77b19-119">All flowcharts will be read-only and unavailable for editing.</span></span> <span data-ttu-id="77b19-120">Anche le proprietà della forma associate alle attività del diagramma di flusso non saranno disponibili.</span><span class="sxs-lookup"><span data-stu-id="77b19-120">The shape properties that are associated with flowchart activities will also be unavailable.</span></span> <span data-ttu-id="77b19-121">Questi diagrammi di flusso includono sia diagrammi di flusso predefiniti che vengono generati automaticamente sia diagrammi di flusso personalizzati che vengono modificati in base a tali diagrammi di flusso predefiniti.</span><span class="sxs-lookup"><span data-stu-id="77b19-121">These flowcharts include both the default flowcharts that are automatically generated and customized flowcharts that are modified based on those default flowcharts.</span></span></li>
<li><span data-ttu-id="77b19-122">I passaggi della procedura saranno di sola lettura e non disponibili per la modifica.</span><span class="sxs-lookup"><span data-stu-id="77b19-122">The process steps will be read-only and unavailable for editing.</span></span></li>     
<li><span data-ttu-id="77b19-123">La funzionalità di analisi degli scostamenti/adeguatezza non sarà disponibile.</span><span class="sxs-lookup"><span data-stu-id="77b19-123">The legacy fit/gap analysis feature will be unavailable.</span></span> <span data-ttu-id="77b19-124">Pertanto, nessun elenco di scostamenti verrà automaticamente creato o sarà disponibile per l'esportazione.</span><span class="sxs-lookup"><span data-stu-id="77b19-124">Therefore, no gap list will be automatically created or available for export.</span></span>
<p><span data-ttu-id="77b19-125"><strong>Nota:</strong> questa funzionalità era stata precedentemente deprecata e sostituita dalle integrazioni di  Microsoft Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="77b19-125"><strong>Note:</strong> This feature had previously been deprecated and replaced by Microsoft Azure DevOps integrations.</span></span></p>
</li>
<li><span data-ttu-id="77b19-126">La cronologia delle versioni del diagramma di flusso non sarà disponibile.</span><span class="sxs-lookup"><span data-stu-id="77b19-126">The version history of the flowchart will be unavailable.</span></span></li>
</ul>
</td>
</tr>
</tbody>
</table>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]