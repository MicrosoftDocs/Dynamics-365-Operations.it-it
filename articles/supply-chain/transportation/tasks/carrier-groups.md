---
title: Gruppi vettore
description: In questo argomento viene descritto come impostare i dati per i gruppi vettore.
author: Henrikan
ms.date: 10/30/2020
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TMSCarrierGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: henrikan
ms.search.validFrom: 2020-10-30
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 9fe95ee9a0b6d69544f35ac6bc9cdf3dd00db291
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5809064"
---
# <a name="carrier-groups"></a><span data-ttu-id="39a03-103">Gruppi vettore</span><span class="sxs-lookup"><span data-stu-id="39a03-103">Carrier groups</span></span>

<span data-ttu-id="39a03-104">Un gruppo vettore è una raccolta di vettori di spedizione e servizi di trasporto.</span><span class="sxs-lookup"><span data-stu-id="39a03-104">A carrier group is a collection of shipping carriers and carrier services.</span></span> <span data-ttu-id="39a03-105">Ciascun gruppo vettore specifica la sequenza preferita per i vettori di spedizione e i servizi di trasporto che gli appartengono.</span><span class="sxs-lookup"><span data-stu-id="39a03-105">Each carrier group specifies the preferred sequence for the shipping carriers and carrier services that belong to it.</span></span>

<span data-ttu-id="39a03-106">Quando esistono più vettori di spedizione e servizi di trasporto per lo stesso segmento di percorso, è possibile specificare un gruppo vettore anziché un vettore di spedizione e un servizio di trasporto nel piano e nella guida di percorso.</span><span class="sxs-lookup"><span data-stu-id="39a03-106">When multiple shipping carriers and carrier services exist for the same route segment, you can specify a carrier group instead of a specific shipping carrier and carrier service in the route plan or route guide.</span></span>

## <a name="create-a-carrier-group"></a><span data-ttu-id="39a03-107">Creare un gruppo vettore</span><span class="sxs-lookup"><span data-stu-id="39a03-107">Create a carrier group</span></span>

1. <span data-ttu-id="39a03-108">Andare a **Gestione trasporto &gt; Impostazioni &gt; Vettori &gt; Gruppo vettore**.</span><span class="sxs-lookup"><span data-stu-id="39a03-108">Go to **Transportation management &gt; Setup &gt; Carriers &gt; Carrier group**.</span></span>
1. <span data-ttu-id="39a03-109">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="39a03-109">Select **New**.</span></span>
1. <span data-ttu-id="39a03-110">Nel campo **Gruppo vettore** immettere un identificatore univoco (ID) per il gruppo.</span><span class="sxs-lookup"><span data-stu-id="39a03-110">In the **Carrier group** field, enter a unique identifier (ID) for the group.</span></span>
1. <span data-ttu-id="39a03-111">Nel campo **Nome** immettere un nome descrittivo per il gruppo.</span><span class="sxs-lookup"><span data-stu-id="39a03-111">In the **Name** field, enter a descriptive name for the group.</span></span>
1. <span data-ttu-id="39a03-112">Nella Scheda dettaglio **Dettagli**, aggiungere una riga e selezionare un vettore di spedizione e un servizio di trasporto per la riga stessa.</span><span class="sxs-lookup"><span data-stu-id="39a03-112">On the **Details** FastTab, add a row, and select a shipping carrier and a carrier service for it.</span></span> <span data-ttu-id="39a03-113">Ripetere questo passaggio fino a quando non sono stati aggiunti tutti i vettori per il gruppo.</span><span class="sxs-lookup"><span data-stu-id="39a03-113">Repeat this step until you've added as many carriers as you require for the group.</span></span>
1. <span data-ttu-id="39a03-114">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="39a03-114">Close the page.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]