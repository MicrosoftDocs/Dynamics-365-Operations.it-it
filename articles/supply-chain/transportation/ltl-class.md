---
title: Classi di carico inferiore a quello del camion (LTL)
description: Questo argomento spiega cosa sono le classi di carico inferiori a quello del camion (LTL) e descrive come configurarle in Microsoft Dynamics 365 Supply Chain Management.
author: Henrikan
ms.date: 04/05/2021
ms.topic: article
ms.search.form: WHSLTLClass
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2021-04-05
ms.dyn365.ops.version: 10.0.8
ms.openlocfilehash: 295006cac0a67cd577809a1b62566de043ea55fb
ms.sourcegitcommit: 636c1bf096a8666a551b67e898da1f48feb9a187
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2021
ms.locfileid: "5941812"
---
# <a name="less-than-truckload-ltl-classes"></a><span data-ttu-id="87693-103">Classi di carico inferiore a quello del camion (LTL)</span><span class="sxs-lookup"><span data-stu-id="87693-103">Less than truckload (LTL) classes</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="87693-104">Una classe LTL è una classe di spedizione merci utilizzata per classificare gli articoli che possono essere spediti.</span><span class="sxs-lookup"><span data-stu-id="87693-104">A less than truckload (LTL) class is a freight shipping class that is used to classify items that can be shipped.</span></span> <span data-ttu-id="87693-105">In generale, ogni tipo di prodotto o merce ha un codice NMFC (National Motor Freight Classification) che corrisponde a un numero di classe di trasporto specifico per le spedizioni LTL.</span><span class="sxs-lookup"><span data-stu-id="87693-105">Generally, every type of product or commodity has a National Motor Freight Classification (NMFC) code that corresponds to a specific freight class number for LTL shipments.</span></span> <span data-ttu-id="87693-106">Le classi di trasporto LTL rappresentano categorie di articoli, mentre i codici NMFC sono correlati a merci specifiche in ciascuna delle 18 classi di trasporto.</span><span class="sxs-lookup"><span data-stu-id="87693-106">LTL freight classes represent categories of items, whereas NMFC codes are related to specific commodities in each of the 18 freight classes.</span></span>

<span data-ttu-id="87693-107">Questa funzionalità consente di usare il sistema per svolgere le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="87693-107">This feature lets you use your system to perform the following tasks:</span></span>

- <span data-ttu-id="87693-108">Definire le classi di trasporto LTL utilizzate nella tua azienda.</span><span class="sxs-lookup"><span data-stu-id="87693-108">Define the LTL freight classes that are used at your company.</span></span>
- <span data-ttu-id="87693-109">Assegnare ogni classe LTL a un codice NMFC nella pagina **Codici NMFC**.</span><span class="sxs-lookup"><span data-stu-id="87693-109">Assign each LTL class to an NMFC code on the **NMFC Codes** page.</span></span> <span data-ttu-id="87693-110">Per ulteriori informazioni, vedere [Codici NMFC (National Motor Freight Classification)](nmfc-codes.md).</span><span class="sxs-lookup"><span data-stu-id="87693-110">For more information, see [National Motor Freight Classification (NMFC) codes](nmfc-codes.md).</span></span>
- <span data-ttu-id="87693-111">Assegna un codice NMFC (e quindi il codice LTL associato) a ciascun prodotto nella pagina **Prodotti**.</span><span class="sxs-lookup"><span data-stu-id="87693-111">Assign an NMFC code (and therefore its associated LTL code) to each product on the **Products** page.</span></span>
- <span data-ttu-id="87693-112">Valutare accuratamente la classe LTL di ciascun prodotto a cui è assegnato un codice NMFC.</span><span class="sxs-lookup"><span data-stu-id="87693-112">Accurately assess the LTL class of each product that an NMFC code is assigned to.</span></span>
- <span data-ttu-id="87693-113">Determinare i requisiti di imballaggio per ciascuna classe LTL controllando gli standard internazionali LTL.</span><span class="sxs-lookup"><span data-stu-id="87693-113">Determine packing requirements for each LTL class by checking the international LTL standards.</span></span> <span data-ttu-id="87693-114">In questo modo, ti assicuri che i tuoi prodotti saranno ben protetti e spediti in sicurezza.</span><span class="sxs-lookup"><span data-stu-id="87693-114">In this way, you ensure that your products will be well protected and safely shipped.</span></span>
- <span data-ttu-id="87693-115">Ottieni stime di spedizione accurate, in base alla classe di trasporto LTL per ogni prodotto.</span><span class="sxs-lookup"><span data-stu-id="87693-115">Get accurate shipping estimates, based on the LTL freight class for each product.</span></span>

<span data-ttu-id="87693-116">In questo argomento viene descritto come creare classi LTL in Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="87693-116">This topic describes how to create LTL classes in Microsoft Dynamics 365 Supply Chain Management.</span></span>

## <a name="create-an-ltl-class"></a><span data-ttu-id="87693-117">Creare una classe LTL</span><span class="sxs-lookup"><span data-stu-id="87693-117">Create an LTL class</span></span>

<span data-ttu-id="87693-118">Per creare una classe LTL, attenersi alla procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="87693-118">To create an LTL class, follow these steps.</span></span>

1. <span data-ttu-id="87693-119">Eseguire uno dei passaggi riportati di seguito.</span><span class="sxs-lookup"><span data-stu-id="87693-119">Follow one of these steps:</span></span>

    - <span data-ttu-id="87693-120">Vai a **Gestione magazzino \> Impostazioni \> Scorte \> Classi LTL**.</span><span class="sxs-lookup"><span data-stu-id="87693-120">Go to **Warehouse management \> Setup \> Inventory \> LTL classes**.</span></span>
    - <span data-ttu-id="87693-121">Andare a **Gestione trasporto \> Impostazioni \> Standard di trasporto \> Classi LTL**.</span><span class="sxs-lookup"><span data-stu-id="87693-121">Go to **Transportation management \> Setup \> Transportation standards \> LTL classes**.</span></span>

2. <span data-ttu-id="87693-122">Nel riquadro azioni seleziona **Nuovo** per creare una classe LTL.</span><span class="sxs-lookup"><span data-stu-id="87693-122">On the Action Pane, select **New** to create an LTL class.</span></span> <span data-ttu-id="87693-123">Quindi impostare i seguenti campi:</span><span class="sxs-lookup"><span data-stu-id="87693-123">Then set the following fields:</span></span>

    - <span data-ttu-id="87693-124">**Classe LTL** - Immettere l'identificatore (ID) della classe LTL interna della propria azienda per il tipo di merce.</span><span class="sxs-lookup"><span data-stu-id="87693-124">**LTL class** – Enter your company's internal LTL class identifier (ID) for the commodity type.</span></span> <span data-ttu-id="87693-125">La maggior parte delle aziende utilizza lo standard internazionale.</span><span class="sxs-lookup"><span data-stu-id="87693-125">Most companies use the international standard.</span></span> <span data-ttu-id="87693-126">In tal caso, il valore di questo campo corrisponderà al valore del campo **Classe**.</span><span class="sxs-lookup"><span data-stu-id="87693-126">In that case, the value of this field will match the value of the **Class** field.</span></span> <span data-ttu-id="87693-127">Tuttavia, se la tua azienda utilizza il proprio standard, inserisci un codice conforme a quello standard.</span><span class="sxs-lookup"><span data-stu-id="87693-127">However, if your company uses its own standard, enter a code that conforms to that standard.</span></span>
    - <span data-ttu-id="87693-128">**Nome** - Immettere un nome descrittivo che aiuterà te e gli altri utenti a selezionare la classe LTL corretta per ogni codice NMFC.</span><span class="sxs-lookup"><span data-stu-id="87693-128">**Name** – Enter a descriptive name that will help you and other users select the correct LTL class for each NMFC code.</span></span>
    - <span data-ttu-id="87693-129">**Classe** - Immettere l'ID classe LTL standard internazionale per il tipo di merce.</span><span class="sxs-lookup"><span data-stu-id="87693-129">**Class** – Enter the international standard LTL class ID for the commodity type.</span></span> <span data-ttu-id="87693-130">Il codice che inserisci qui deve essere conforme allo standard ufficiale.</span><span class="sxs-lookup"><span data-stu-id="87693-130">The code that you enter here must conform to the official standard.</span></span>

## <a name="example-set-up-ltl-classes"></a><span data-ttu-id="87693-131">Esempio: Impostare le classi LTL</span><span class="sxs-lookup"><span data-stu-id="87693-131">Example: Set up LTL classes</span></span>

<span data-ttu-id="87693-132">L'esempio seguente mostra come impostare due diversi classi LTL che possono essere utilizzati con tipi di prodotti diversi.</span><span class="sxs-lookup"><span data-stu-id="87693-132">The following example shows how to set up two different LTL classes that you can use with different types of products.</span></span>

1. <span data-ttu-id="87693-133">Vai a **Gestione magazzino \> Impostazioni \> Scorte \> Classi LTL**.</span><span class="sxs-lookup"><span data-stu-id="87693-133">Go to **Warehouse management \> Setup \> Inventory \> LTL classes**.</span></span>
1. <span data-ttu-id="87693-134">Nel Riquadro azioni selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="87693-134">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="87693-135">Nella nuova riga, imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="87693-135">On the new line, set the following values:</span></span>

    - <span data-ttu-id="87693-136">**Classe LTL:** *92.5*</span><span class="sxs-lookup"><span data-stu-id="87693-136">**LTL class:** *92.5*</span></span>
    - <span data-ttu-id="87693-137">**Nome:** *Computer, monitor, frigoriferi*</span><span class="sxs-lookup"><span data-stu-id="87693-137">**Name:** *Computers, monitors, refrigerators*</span></span>
    - <span data-ttu-id="87693-138">**Classe:** *92.5*</span><span class="sxs-lookup"><span data-stu-id="87693-138">**Class:** *92.5*</span></span>

1. <span data-ttu-id="87693-139">Nel riquadro azioni selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="87693-139">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="87693-140">Nel Riquadro azioni selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="87693-140">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="87693-141">Nella nuova riga, imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="87693-141">On the new line, set the following values:</span></span>

    - <span data-ttu-id="87693-142">**Classe LTL:** *125*</span><span class="sxs-lookup"><span data-stu-id="87693-142">**LTL class:** *125*</span></span>
    - <span data-ttu-id="87693-143">**Nome:** *Piccoli elettrodomestici*</span><span class="sxs-lookup"><span data-stu-id="87693-143">**Name:** *Small household appliances*</span></span>
    - <span data-ttu-id="87693-144">**Classe:** *125*</span><span class="sxs-lookup"><span data-stu-id="87693-144">**Class:** *125*</span></span>

1. <span data-ttu-id="87693-145">Nel riquadro azioni selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="87693-145">On the Action Pane, select **Save**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="87693-146">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="87693-146">Additional resources</span></span>

- [<span data-ttu-id="87693-147">Codici NMFC (National Motor Freight Classification)</span><span class="sxs-lookup"><span data-stu-id="87693-147">National Motor Freight Classification (NMFC) codes</span></span>](nmfc-codes.md)
- [<span data-ttu-id="87693-148">Creare una polizza di carico</span><span class="sxs-lookup"><span data-stu-id="87693-148">Create a bill of lading</span></span>](create-bill-of-lading.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
