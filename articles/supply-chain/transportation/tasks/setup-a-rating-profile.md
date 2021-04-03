---
title: Profili valutazione
description: In questo argomento viene descritto come impostare i profili valutazione.
author: Henrikan
manager: ''
ms.date: 10/30/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TMSRatingProfile
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: henrikan
ms.search.validFrom: 2020-10-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5f754a8b86b0d369af03812a831d77a8a6fa8154
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5233513"
---
# <a name="rating-profiles"></a><span data-ttu-id="a55cf-103">Profili valutazione</span><span class="sxs-lookup"><span data-stu-id="a55cf-103">Rating profiles</span></span>

<span data-ttu-id="a55cf-104">Un profilo di valutazione è simile a un contratto di logistica (ma non a un contratto legale).</span><span class="sxs-lookup"><span data-stu-id="a55cf-104">A rating profile resembles a logistics contract (but not a legal contract).</span></span> <span data-ttu-id="a55cf-105">Viene utilizzato per determinare le tariffe di trasporto per i carichi.</span><span class="sxs-lookup"><span data-stu-id="a55cf-105">It's used to determine transportation tariffs for loads.</span></span> 

<span data-ttu-id="a55cf-106">Ogni profilo di valutazione è univoco per il vettore di spedizione.</span><span class="sxs-lookup"><span data-stu-id="a55cf-106">Each rating profile is unique to a shipping carrier.</span></span> <span data-ttu-id="a55cf-107">Nel profilo si associa il vettore di spedizione ai dati master tariffe.</span><span class="sxs-lookup"><span data-stu-id="a55cf-107">In the profile, you associate the shipping carrier with a rate master.</span></span> <span data-ttu-id="a55cf-108">I dati master tariffe definiscono l'assegnazione di base delle tariffe e la base tariffaria.</span><span class="sxs-lookup"><span data-stu-id="a55cf-108">The rate master defines the rate base assignment and the rate base.</span></span> <span data-ttu-id="a55cf-109">La base tariffaria determina la tariffa del vettore.</span><span class="sxs-lookup"><span data-stu-id="a55cf-109">The rate base determines the rate of the carrier.</span></span>

<span data-ttu-id="a55cf-110">È possibile impostare un profilo di valutazione utilizzando una pagina generica contenente una panoramica di tutti i profili di valutazione esistenti.</span><span class="sxs-lookup"><span data-stu-id="a55cf-110">You can set up a rating profile by using a generic page that shows an overview of all existing rating profiles.</span></span> <span data-ttu-id="a55cf-111">In alternativa è possibile impostare un profilo di valutazione direttamente dal vettore di spedizione.</span><span class="sxs-lookup"><span data-stu-id="a55cf-111">Alternatively, you can set up a rating profile directly from the shipping carrier.</span></span> <span data-ttu-id="a55cf-112">In entrambi i casi, le informazioni impostate per il profilo di valutazione sono le stesse.</span><span class="sxs-lookup"><span data-stu-id="a55cf-112">In both cases, the information that you set up for the rating profile is the same.</span></span>

## <a name="create-or-edit-a-rating-profile-on-the-rating-profiles-page"></a><span data-ttu-id="a55cf-113">Creare o modificare un profilo di valutazione nella pagina Profili valutazione</span><span class="sxs-lookup"><span data-stu-id="a55cf-113">Create or edit a rating profile on the Rating profiles page</span></span>

<span data-ttu-id="a55cf-114">Nella pagina **Profili valutazione** è possibile rivedere tutti i profili di valutazione disponibili.</span><span class="sxs-lookup"><span data-stu-id="a55cf-114">On the **Rating profiles** page, you can review all available rating profiles.</span></span> <span data-ttu-id="a55cf-115">Inoltre, è possibile modificare i profili esistenti e creare nuovi profili.</span><span class="sxs-lookup"><span data-stu-id="a55cf-115">You can also edit existing profiles and create new profiles.</span></span>

1. <span data-ttu-id="a55cf-116">Passare a **Gestione trasporto \> Impostazioni \> Valutazione \> Profilo valutazione**.</span><span class="sxs-lookup"><span data-stu-id="a55cf-116">Go to **Transportation management \> Setup \> Rating \> Rating profile**.</span></span>
1. <span data-ttu-id="a55cf-117">Nel riquadro azioni selezionare **Nuovo** per aggiungere un nuovo profilo di valutazione alla griglia oppure selezionare **Modifica** per modificare un profilo esistente.</span><span class="sxs-lookup"><span data-stu-id="a55cf-117">On the Action Pane, select **New** to add a new rating profile to the grid, or select **Edit** to edit an existing profile.</span></span>
1. <span data-ttu-id="a55cf-118">Nella riga del profilo di valutazione nuovo o esistente, impostare i seguenti campi:</span><span class="sxs-lookup"><span data-stu-id="a55cf-118">In the row for the new or existing rating profile, set the following fields:</span></span>

    - <span data-ttu-id="a55cf-119">**Profilo valutazione** – Immettere un identificatore univoco (ID) per il profilo di valutazione.</span><span class="sxs-lookup"><span data-stu-id="a55cf-119">**Rating profile** – Enter a unique identifier (ID) for the rating profile.</span></span>
    - <span data-ttu-id="a55cf-120">**Nome** – Immettere un nome descrittivo per il profilo di valutazione.</span><span class="sxs-lookup"><span data-stu-id="a55cf-120">**Name** – Enter a descriptive name for the rating profile.</span></span>
    - <span data-ttu-id="a55cf-121">**Vettore di spedizione** – Selezionare un corriere.</span><span class="sxs-lookup"><span data-stu-id="a55cf-121">**Shipping carrier** – Select a shipping carrier.</span></span> <span data-ttu-id="a55cf-122">Il profilo di valutazione che si sta impostando verrà mostrato anche nella pagina **Vettori di spedizione** per il vettore selezionato.</span><span class="sxs-lookup"><span data-stu-id="a55cf-122">The rating profile that you're setting up will also be shown on the **Shipping carriers** page for the selected carrier.</span></span>
    - <span data-ttu-id="a55cf-123">**Sito** e **Magazzino** - Selezionare un sito e un magazzino.</span><span class="sxs-lookup"><span data-stu-id="a55cf-123">**Site** and **Warehouse** – Select a site and warehouse.</span></span>
    - <span data-ttu-id="a55cf-124">**Motore tariffe** - Selezionare il motore delle tariffe per il profilo di valutazione.</span><span class="sxs-lookup"><span data-stu-id="a55cf-124">**Rate engine** – Select the rate engine for the rating profile.</span></span>
    - <span data-ttu-id="a55cf-125">**Tariffa principale** - Selezionare la tariffa principale per il profilo di valutazione.</span><span class="sxs-lookup"><span data-stu-id="a55cf-125">**Rate master** – Select the rate master for the rating profile.</span></span> <span data-ttu-id="a55cf-126">I dati master tariffe possono essere utilizzati per definire il tipo di base tariffaria e una base tariffaria.</span><span class="sxs-lookup"><span data-stu-id="a55cf-126">You can use the rate master to define a rate base type and a rate base.</span></span> <span data-ttu-id="a55cf-127">Per ulteriori informazioni, vedere [Impostare i dati master tariffe](set-up-rate-masters.md).</span><span class="sxs-lookup"><span data-stu-id="a55cf-127">For more information, see [Set up rate masters](set-up-rate-masters.md).</span></span>
    - <span data-ttu-id="a55cf-128">**Motore tempo di transito** - Selezionare il motore del tempo di transito per il profilo di valutazione.</span><span class="sxs-lookup"><span data-stu-id="a55cf-128">**Transit time engine** – Select the transit time engine for the rating profile.</span></span>
    - <span data-ttu-id="a55cf-129">**Indice carburante vettore** – Selezionare il motore transito e l'indice carburante del vettore per il profilo di valutazione.</span><span class="sxs-lookup"><span data-stu-id="a55cf-129">**Carrier fuel index** – Select the carrier fuel index for the rating profile.</span></span>
    - <span data-ttu-id="a55cf-130">**Data e ora di inizio validità** e **Data e ora di fine validità** - Definire il periodo in cui il profilo di valutazione deve essere attivo.</span><span class="sxs-lookup"><span data-stu-id="a55cf-130">**Effect start date and time** and **Effective end date and time** – Define the period when the rating profile should be active.</span></span>

1. <span data-ttu-id="a55cf-131">Nel riquadro azioni selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="a55cf-131">On the Action Pane, select **Save**.</span></span>

## <a name="create-a-rating-profile-directly-on-the-shipping-carriers-page"></a><span data-ttu-id="a55cf-132">Creare un profilo di valutazione direttamente nella pagina Vettori spedizione</span><span class="sxs-lookup"><span data-stu-id="a55cf-132">Create a rating profile directly on the Shipping carriers page</span></span>

1. <span data-ttu-id="a55cf-133">Vai a **Gestione trasporto \> Impostazioni \> Vettori \> Vettori spedizione**.</span><span class="sxs-lookup"><span data-stu-id="a55cf-133">Go to **Transportation management \> Setup \> Carriers \> Shipping carriers**.</span></span>
1. <span data-ttu-id="a55cf-134">Selezionare un vettore di spedizione nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="a55cf-134">Select a shipping carrier in the list.</span></span>
1. <span data-ttu-id="a55cf-135">Nella Scheda dettaglio **Profili valutazione** selezionare **Nuovo** per creare un profilo di valutazione.</span><span class="sxs-lookup"><span data-stu-id="a55cf-135">On the **Rating profiles** FastTab, select **New** to create a rating profile.</span></span>
1. <span data-ttu-id="a55cf-136">Impostare i campi per il nuovo profilo di valutazione.</span><span class="sxs-lookup"><span data-stu-id="a55cf-136">Set the fields for the new rating profile.</span></span> <span data-ttu-id="a55cf-137">Questi campi corrispondono ai campi nella pagina **Profili di valutazione**, come descritto nella sezione precedente di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="a55cf-137">These fields correspond to the fields on the **Rating profiles** page, as described in previous section of this topic.</span></span>

> [!NOTE]
> <span data-ttu-id="a55cf-138">I profili creati nella pagina **Vettori di spedizione** vengono visualizzati anche nella pagina **Profili di valutazione**.</span><span class="sxs-lookup"><span data-stu-id="a55cf-138">Profiles that are created on the **Shipping carriers** page are also shown on the **Rating profiles** page.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]