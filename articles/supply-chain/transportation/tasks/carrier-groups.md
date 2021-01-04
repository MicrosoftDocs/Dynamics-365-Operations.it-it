---
title: Gruppi vettore
description: In questo argomento viene descritto come impostare i dati per i gruppi vettore.
author: Henrikan
manager: ''
ms.date: 10/30/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TMSCarrierGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: henrikan
ms.search.validFrom: 2020-10-30
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 2570479edac9bc8cc7aa998a8b69f54ffc10cd61
ms.sourcegitcommit: deb711c92251ed48cdf20ea514d03461c26a2262
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/25/2020
ms.locfileid: "4646406"
---
# <a name="carrier-groups"></a><span data-ttu-id="c1d58-103">Gruppi vettore</span><span class="sxs-lookup"><span data-stu-id="c1d58-103">Carrier groups</span></span>

<span data-ttu-id="c1d58-104">Un gruppo vettore è una raccolta di vettori di spedizione e servizi di trasporto.</span><span class="sxs-lookup"><span data-stu-id="c1d58-104">A carrier group is a collection of shipping carriers and carrier services.</span></span> <span data-ttu-id="c1d58-105">Ciascun gruppo vettore specifica la sequenza preferita per i vettori di spedizione e i servizi di trasporto che gli appartengono.</span><span class="sxs-lookup"><span data-stu-id="c1d58-105">Each carrier group specifies the preferred sequence for the shipping carriers and carrier services that belong to it.</span></span>

<span data-ttu-id="c1d58-106">Quando esistono più vettori di spedizione e servizi di trasporto per lo stesso segmento di percorso, è possibile specificare un gruppo vettore anziché un vettore di spedizione e un servizio di trasporto nel piano e nella guida di percorso.</span><span class="sxs-lookup"><span data-stu-id="c1d58-106">When multiple shipping carriers and carrier services exist for the same route segment, you can specify a carrier group instead of a specific shipping carrier and carrier service in the route plan or route guide.</span></span>

## <a name="create-a-carrier-group"></a><span data-ttu-id="c1d58-107">Creare un gruppo vettore</span><span class="sxs-lookup"><span data-stu-id="c1d58-107">Create a carrier group</span></span>

1. <span data-ttu-id="c1d58-108">Andare a **Gestione trasporto &gt; Impostazioni &gt; Vettori &gt; Gruppo vettore**.</span><span class="sxs-lookup"><span data-stu-id="c1d58-108">Go to **Transportation management &gt; Setup &gt; Carriers &gt; Carrier group**.</span></span>
1. <span data-ttu-id="c1d58-109">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="c1d58-109">Select **New**.</span></span>
1. <span data-ttu-id="c1d58-110">Nel campo **Gruppo vettore** immettere un identificatore univoco (ID) per il gruppo.</span><span class="sxs-lookup"><span data-stu-id="c1d58-110">In the **Carrier group** field, enter a unique identifier (ID) for the group.</span></span>
1. <span data-ttu-id="c1d58-111">Nel campo **Nome** immettere un nome descrittivo per il gruppo.</span><span class="sxs-lookup"><span data-stu-id="c1d58-111">In the **Name** field, enter a descriptive name for the group.</span></span>
1. <span data-ttu-id="c1d58-112">Nella Scheda dettaglio **Dettagli**, aggiungere una riga e selezionare un vettore di spedizione e un servizio di trasporto per la riga stessa.</span><span class="sxs-lookup"><span data-stu-id="c1d58-112">On the **Details** FastTab, add a row, and select a shipping carrier and a carrier service for it.</span></span> <span data-ttu-id="c1d58-113">Ripetere questo passaggio fino a quando non sono stati aggiunti tutti i vettori per il gruppo.</span><span class="sxs-lookup"><span data-stu-id="c1d58-113">Repeat this step until you've added as many carriers as you require for the group.</span></span>
1. <span data-ttu-id="c1d58-114">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="c1d58-114">Close the page.</span></span>
