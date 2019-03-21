---
title: Domande frequenti sui flussi di lavoro
description: In questo argomento vengono fornite le risposte alle domande frequenti relative al sistema del flusso di lavoro di Microsoft Dynamics 365 for Finance and Operations.
author: ChrisGarty
manager: AnnBe
ms.date: 02/28/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f058a450eb18e688efbc5306a42b4efef6aa91e7
ms.sourcegitcommit: 9a723737565ac78c884e40f7129d0f5aad747524
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/01/2019
ms.locfileid: "773217"
---
# <a name="workflow-system"></a><span data-ttu-id="73a73-103">Sistema del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="73a73-103">Workflow system</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="73a73-104">In questo argomento vengono fornite le risposte alle domande frequenti relative al sistema del flusso di lavoro di Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="73a73-104">This topic answers frequently asked questions about the workflow system in Microsoft Dynamics 365 for Finance and Operations.</span></span>

## <a name="notifications"></a><span data-ttu-id="73a73-105">Notifiche</span><span class="sxs-lookup"><span data-stu-id="73a73-105">Notifications</span></span>

### <a name="why-are-multiple-notifications-received-when-a-work-item-is-rejected"></a><span data-ttu-id="73a73-106">Perché si ricevono molteplici notifiche quando un elemento di lavoro viene rifiutato?</span><span class="sxs-lookup"><span data-stu-id="73a73-106">Why are multiple notifications received when a work item is rejected?</span></span>
<span data-ttu-id="73a73-107">Quando un elemento di lavoro viene rifiutato, questo viene completato come rifiutato.</span><span class="sxs-lookup"><span data-stu-id="73a73-107">When a work item is rejected, that work item is completed as rejected.</span></span> <span data-ttu-id="73a73-108">Un altro elemento di lavoro viene creato e assegnato all'iniziatore.</span><span class="sxs-lookup"><span data-stu-id="73a73-108">Another work item is created and assigned to the originator.</span></span> <span data-ttu-id="73a73-109">Ciò significa che non si ha una notifica all'iniziatore per l'elemento di lavoro rifiutato e una notifica distinta all'utente assegnato al nuovo elemento di lavoro "modifica richiesta".</span><span class="sxs-lookup"><span data-stu-id="73a73-109">This means that there is a notification to the originator for the rejected work item, and a separate notification to the user assigned to the new "change requested" work item.</span></span> 

<span data-ttu-id="73a73-110">Ogni notifica è per un articolo di lavoro differente, ma le analogie possono creare confusione.</span><span class="sxs-lookup"><span data-stu-id="73a73-110">Each notification is for a different work item, but the similarity can cause confusion.</span></span> <span data-ttu-id="73a73-111">Questo inconveniente verrà migliorato in una versione successiva.</span><span class="sxs-lookup"><span data-stu-id="73a73-111">We are looking at ways to improve this in a future release.</span></span>
