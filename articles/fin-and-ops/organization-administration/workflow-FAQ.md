---
title: Domande frequenti sui flussi di lavoro
description: In questo argomento vengono fornite le risposte alle domande frequenti relative al sistema del flusso di lavoro di Microsoft Dynamics 365 for Finance and Operations.
author: ChrisGarty
manager: AnnBe
ms.date: 05/07/2019
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
ms.openlocfilehash: f6240b1b5136937aa47f455547fed6f0c7c08e2c
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2019
ms.locfileid: "1509293"
---
# <a name="workflow-system"></a><span data-ttu-id="f1b6c-103">Sistema del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="f1b6c-103">Workflow system</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f1b6c-104">In questo argomento vengono fornite le risposte alle domande frequenti relative al sistema del flusso di lavoro di Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="f1b6c-104">This topic answers frequently asked questions about the workflow system in Microsoft Dynamics 365 for Finance and Operations.</span></span>

## <a name="notifications"></a><span data-ttu-id="f1b6c-105">Notifiche</span><span class="sxs-lookup"><span data-stu-id="f1b6c-105">Notifications</span></span>

### <a name="why-are-multiple-notifications-received-when-a-work-item-is-rejected"></a><span data-ttu-id="f1b6c-106">Perché si ricevono molteplici notifiche quando un elemento di lavoro viene rifiutato?</span><span class="sxs-lookup"><span data-stu-id="f1b6c-106">Why are multiple notifications received when a work item is rejected?</span></span>
<span data-ttu-id="f1b6c-107">Quando un elemento di lavoro viene rifiutato, questo viene completato come rifiutato.</span><span class="sxs-lookup"><span data-stu-id="f1b6c-107">When a work item is rejected, that work item is completed as rejected.</span></span> <span data-ttu-id="f1b6c-108">Un altro elemento di lavoro viene creato e assegnato all'iniziatore.</span><span class="sxs-lookup"><span data-stu-id="f1b6c-108">Another work item is created and assigned to the originator.</span></span> <span data-ttu-id="f1b6c-109">Ciò significa che non si ha una notifica all'iniziatore per l'elemento di lavoro rifiutato e una notifica distinta all'utente assegnato al nuovo elemento di lavoro "modifica richiesta".</span><span class="sxs-lookup"><span data-stu-id="f1b6c-109">This means that there is a notification to the originator for the rejected work item, and a separate notification to the user assigned to the new "change requested" work item.</span></span> 

<span data-ttu-id="f1b6c-110">Ogni notifica è per un articolo di lavoro differente, ma le analogie possono creare confusione.</span><span class="sxs-lookup"><span data-stu-id="f1b6c-110">Each notification is for a different work item, but the similarity can cause confusion.</span></span> <span data-ttu-id="f1b6c-111">Questo inconveniente verrà migliorato in una versione successiva.</span><span class="sxs-lookup"><span data-stu-id="f1b6c-111">We are looking at ways to improve this in a future release.</span></span>

### <a name="why-are-my-workflow-exports-failing"></a><span data-ttu-id="f1b6c-112">Perché le esportazioni del flusso di lavoro non funzionano?</span><span class="sxs-lookup"><span data-stu-id="f1b6c-112">Why are my workflow exports failing?</span></span>
<span data-ttu-id="f1b6c-113">Attualmente, esiste una limitazione nella funzionalità di esportazione del flusso di lavoro che impedisce ai nomi del flusso di lavoro di superare i 48 caratteri.</span><span class="sxs-lookup"><span data-stu-id="f1b6c-113">There is currently a limitation in the workflow export feature that prevents workflow names from exceeding 48 characters.</span></span> <span data-ttu-id="f1b6c-114">L'utilizzo di un nome superiore ai 48 caratteri può comportare l'errore di autenticazione del server e/o impedire l'esportazione di un file senza un tipo di file.</span><span class="sxs-lookup"><span data-stu-id="f1b6c-114">Using a name that is longer than 48 characters can result in a "Server failed to authenticate the request" error and/or prevent a file to be exported  without a file type.</span></span> <span data-ttu-id="f1b6c-115">Il seguente post di blog sulla [risoluzione dei problemi di esportazione del flusso di lavoro](https://community.dynamics.com/ax/b/elandaxdynamicsaxupgradesanddevelopment/archive/2019/04/10/workflow-export-troubleshooting) fornisce ulteriori dettagli.</span><span class="sxs-lookup"><span data-stu-id="f1b6c-115">The following blog post provides more details [Workflow Export Troubleshooting](https://community.dynamics.com/ax/b/elandaxdynamicsaxupgradesanddevelopment/archive/2019/04/10/workflow-export-troubleshooting).</span></span>
