---
title: L'ordine di produzione pianificato deve essere programmato prima di poter essere stabilizzato
description: Quando si tenta di stabilizzare un ordine pianificato, viene visualizzato un messaggio di errore che indica che l'ordine deve essere pianificato prima di poter essere stabilizzato.
author: ankubik
ms.date: 06/10/2021
ms.topic: troubleshooting
ms.search.form: ReqTransPo
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ankubik
ms.search.validFrom: 2021-06-10
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: a360cb3cbd26e1bc1ebb1baf1a6a4d8282c28c5c
ms.sourcegitcommit: 18ca2df785e9656fdd4e8c0734eca2b2624fda10
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/22/2021
ms.locfileid: "6294114"
---
# <a name="planned-production-order-must-be-scheduled-before-it-can-be-firmed"></a><span data-ttu-id="a792e-103">L'ordine di produzione pianificato deve essere programmato prima di poter essere stabilizzato</span><span class="sxs-lookup"><span data-stu-id="a792e-103">Planned production order must be scheduled before it can be firmed</span></span>

<span data-ttu-id="a792e-104">Codice errore: SYS309802</span><span class="sxs-lookup"><span data-stu-id="a792e-104">Error code: SYS309802</span></span>

## <a name="symptoms"></a><span data-ttu-id="a792e-105">Sintomi</span><span class="sxs-lookup"><span data-stu-id="a792e-105">Symptoms</span></span>

<span data-ttu-id="a792e-106">Quando tenti di stabilizzare un ordine pianificato viene visualizzato il seguente messaggio di errore:</span><span class="sxs-lookup"><span data-stu-id="a792e-106">When you try to firm a planned order, you receive the following error message:</span></span>

> <span data-ttu-id="a792e-107">Per stabilizzare un ordine di produzione pianificato, è innanzitutto necessario programmarlo.</span><span class="sxs-lookup"><span data-stu-id="a792e-107">The planned production order must be scheduled before it can be firmed.</span></span>

## <a name="cause"></a><span data-ttu-id="a792e-108">Causa</span><span class="sxs-lookup"><span data-stu-id="a792e-108">Cause</span></span>

<span data-ttu-id="a792e-109">Le date di inizio e fine pianificate non possono essere vuote.</span><span class="sxs-lookup"><span data-stu-id="a792e-109">The scheduled start and end dates can't be blank.</span></span>

## <a name="resolution"></a><span data-ttu-id="a792e-110">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="a792e-110">Resolution</span></span>

<span data-ttu-id="a792e-111">Per specificare le date di inizio e di fine per l'ordine pianificato, segui questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="a792e-111">To specify start and end dates for the planned order, follow these steps.</span></span>

1. <span data-ttu-id="a792e-112">Andare a **Pianificazione generale \> Pianificazione generale \> Ordini pianificati**.</span><span class="sxs-lookup"><span data-stu-id="a792e-112">Go to **Master planning \> Master planning \> Planned orders**.</span></span>
1. <span data-ttu-id="a792e-113">Apri l'ordine pianificato rilevante.</span><span class="sxs-lookup"><span data-stu-id="a792e-113">Open the relevant planned order.</span></span>
1. <span data-ttu-id="a792e-114">Nella scheda dettaglio **Generale** nella sezione **Programmato** specifica le date nei campi **Data di inizio** e **Data di fine**.</span><span class="sxs-lookup"><span data-stu-id="a792e-114">On the **General** FastTab, in the **Scheduled** section, specify dates in the **Start date** and **End date** fields.</span></span>
