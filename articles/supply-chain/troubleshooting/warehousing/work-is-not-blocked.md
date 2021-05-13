---
title: Il lavoro non è bloccato
description: Il lavoro non è bloccato
author: perlynne
ms.date: 04/15/2021
ms.topic: troubleshooting
ms.search.form: WHSWorkTable_WHSWorkUnblocking
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-05-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: d64ab282972e46e8857581b59e5705dd15667328
ms.sourcegitcommit: 5f5afb46431e1abd8fb6e92e0189914b598dc7fd
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2021
ms.locfileid: "5924206"
---
# <a name="work-isnt-blocked"></a><span data-ttu-id="16269-103">Il lavoro non è bloccato</span><span class="sxs-lookup"><span data-stu-id="16269-103">Work isn't blocked</span></span>

<span data-ttu-id="16269-104">Codice di errore: WHSUnblockNotBlockedWorkErrorMessage</span><span class="sxs-lookup"><span data-stu-id="16269-104">Error code: WHSUnblockNotBlockedWorkErrorMessage</span></span>

## <a name="symptoms"></a><span data-ttu-id="16269-105">Sintomi</span><span class="sxs-lookup"><span data-stu-id="16269-105">Symptoms</span></span>

<span data-ttu-id="16269-106">Il sistema mostra il seguente messaggio di errore:</span><span class="sxs-lookup"><span data-stu-id="16269-106">The system shows the following error message:</span></span>

> <span data-ttu-id="16269-107">Lavoro con ID %1 non bloccato.</span><span class="sxs-lookup"><span data-stu-id="16269-107">Work with Id %1 is not blocked.</span></span>

## <a name="cause"></a><span data-ttu-id="16269-108">Causa</span><span class="sxs-lookup"><span data-stu-id="16269-108">Cause</span></span>

<span data-ttu-id="16269-109">L'opzione **Ciclo bloccato** nel ciclo è impostata su *No*.</span><span class="sxs-lookup"><span data-stu-id="16269-109">The **Blocked wave** option on the wave is set to *No*.</span></span> <span data-ttu-id="16269-110">Il lavoro non può essere sbloccato perché al momento non è bloccato.</span><span class="sxs-lookup"><span data-stu-id="16269-110">The work can't be unblocked because it isn't currently blocked.</span></span>

## <a name="resolution"></a><span data-ttu-id="16269-111">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="16269-111">Resolution</span></span>

 <span data-ttu-id="16269-112">Solo il lavoro dove l'opzione **Ciclo bloccato** è impostata su *Sì* può essere sbloccato.</span><span class="sxs-lookup"><span data-stu-id="16269-112">Only work where the **Blocked wave** option is set to *Yes* can be unblocked.</span></span>
