---
title: Codici NMFC (National Motor Freight Classification)
description: Questo argomento descrive come lavorare con i codici NMFC (National Motor Freight Classification) in Microsoft Dynamics 365 Supply Chain Management
author: Henrikan
ms.date: 04/22/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2021-04-22
ms.dyn365.ops.version: 10.0.8
ms.openlocfilehash: 0307437d3868f7ac34fa16a0913907a046ac14d4
ms.sourcegitcommit: 636c1bf096a8666a551b67e898da1f48feb9a187
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2021
ms.locfileid: "5941884"
---
# <a name="national-motor-freight-classification-nmfc-codes"></a><span data-ttu-id="f864a-103">Codici NMFC (National Motor Freight Classification)</span><span class="sxs-lookup"><span data-stu-id="f864a-103">National Motor Freight Classification (NMFC) codes</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f864a-104">I codici NMFC (National Motor Freight Classification) aiutano a classificare gli articoli che possono essere spediti.</span><span class="sxs-lookup"><span data-stu-id="f864a-104">National Motor Freight Classification (NMFC) codes help you classify items that can be shipped.</span></span> <span data-ttu-id="f864a-105">Il codice NMFC è una designazione utilizzata per raggruppare le merci.</span><span class="sxs-lookup"><span data-stu-id="f864a-105">The NMFC code is a designation that is used to group commodities.</span></span> <span data-ttu-id="f864a-106">Consente alle aziende di trasporto di valutare le merci per la spedizione classificando gli articoli in base a considerazioni come capacità di entrare in un camion, problemi di carico, problemi di movimentazione e deperibilità.</span><span class="sxs-lookup"><span data-stu-id="f864a-106">It enables transport companies to evaluate goods for shipment by classifying items based on considerations such as truck fit, loading issues, handling issues, and perishability.</span></span> <span data-ttu-id="f864a-107">Le merci sono raggruppate in una di 18 classi di trasporto utilizzando una gamma di numeri da 50 a 500.</span><span class="sxs-lookup"><span data-stu-id="f864a-107">Commodities are grouped into one of 18 freight classes by using a range of numbers from 50 to 500.</span></span> <span data-ttu-id="f864a-108">La classe in cui è raggruppata una merce si basa su una valutazione di quattro caratteristiche di trasporto: densità, stivabilità, movimentazione e responsabilità.</span><span class="sxs-lookup"><span data-stu-id="f864a-108">The class that a commodity is grouped into is based on an evaluation of four transportation characteristics: density, stowability, handling, and liability.</span></span> <span data-ttu-id="f864a-109">Insieme, queste caratteristiche stabiliscono la trasportabilità della merce.</span><span class="sxs-lookup"><span data-stu-id="f864a-109">Together, these characteristics establish the commodity's transportability.</span></span>

<span data-ttu-id="f864a-110">Un codice NMFC è associato a ogni articolo di spedizione inferiore al carico camion (LTL).</span><span class="sxs-lookup"><span data-stu-id="f864a-110">An NMFC code is associated with every less than truckload (LTL) shipping item.</span></span> <span data-ttu-id="f864a-111">Ad esempio, a un laptop potrebbe essere assegnato un NMFC di classe 2.5, mentre ai cavi elettrici potrebbe essere assegnato un NMFC di classe 65.</span><span class="sxs-lookup"><span data-stu-id="f864a-111">For example, a laptop might be assigned an NMFC that is classed at 2.5, whereas electrical cords might be assigned an NMFC that is classed at 65.</span></span>

<span data-ttu-id="f864a-112">Questa funzionalità può aiutare i lavoratori a utilizzare i codici NMFC per classificare gli articoli con spedizione LTL.</span><span class="sxs-lookup"><span data-stu-id="f864a-112">This feature can help workers use NMFC codes to classify LTL shipping items.</span></span> <span data-ttu-id="f864a-113">Di seguito sono riportati alcuni esempi.</span><span class="sxs-lookup"><span data-stu-id="f864a-113">Here are some examples:</span></span>

- <span data-ttu-id="f864a-114">Se la tua azienda include una descrizione del trasporto sulla polizza di carico (BOL), il vettore avrà un'idea di cosa sia il trasporto.</span><span class="sxs-lookup"><span data-stu-id="f864a-114">If your company includes a freight description on the bill of lading (BOL), the carrier will have some idea what the freight is.</span></span> <span data-ttu-id="f864a-115">Il trasporto è una classificazione importante perché molte società di trasporto basano il loro intero modello di business sui tipi di merci che spediscono.</span><span class="sxs-lookup"><span data-stu-id="f864a-115">Freight is an important classification because many transportation companies base their whole business model on the types of freight that they ship.</span></span>
- <span data-ttu-id="f864a-116">Questa classificazione potrebbe essere essenziale per la tua azienda perché viene utilizzata per determinare il costo di un determinato carico.</span><span class="sxs-lookup"><span data-stu-id="f864a-116">This classification might be essential to your company because it's used to determine the cost of a given load.</span></span>
- <span data-ttu-id="f864a-117">La tua azienda può identificare la redditività di una società di logistica e trasporto LTL.</span><span class="sxs-lookup"><span data-stu-id="f864a-117">Your company can identify the profitability of an LTL logistics and transportation company.</span></span>

<span data-ttu-id="f864a-118">In questo argomento viene descritto come utilizzare i codici NMFC in Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="f864a-118">This topic describes how to work with NMFC codes in Microsoft Dynamics 365 Supply Chain Management.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f864a-119">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="f864a-119">Prerequisites</span></span>

<span data-ttu-id="f864a-120">Prima di poter creare codici NMFC, è necessario impostare tutte le classi di trasporto LTL che devono essere mappate ad essi.</span><span class="sxs-lookup"><span data-stu-id="f864a-120">Before you can create NMFC codes, you must set up all the LTL freight classes that must be mapped to them.</span></span> <span data-ttu-id="f864a-121">Le classi di trasporto LTL rappresentano categorie di articoli, mentre i codici NMFC sono correlati a merci specifiche in ciascuna delle 18 classi di trasporto.</span><span class="sxs-lookup"><span data-stu-id="f864a-121">LTL freight classes represent categories of items, whereas NMFC codes are related to specific commodities in each of the 18 freight classes.</span></span> <span data-ttu-id="f864a-122">Per ulteriori informazioni su come lavorare con le classi LTL, vedere [Classi di carico inferiore a quello del camion (LTL)](ltl-class.md).</span><span class="sxs-lookup"><span data-stu-id="f864a-122">For more information about how to work with LTL classes, see [Less than truckload (LTL) classes](ltl-class.md).</span></span>

## <a name="create-an-nmfc-code"></a><span data-ttu-id="f864a-123">Creare un codice NMFC</span><span class="sxs-lookup"><span data-stu-id="f864a-123">Create an NMFC code</span></span>

<span data-ttu-id="f864a-124">Per creare un codice NMFC, attenersi alla procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="f864a-124">To create an NMFC code, follow these steps.</span></span>

1. <span data-ttu-id="f864a-125">Eseguire uno dei passaggi riportati di seguito.</span><span class="sxs-lookup"><span data-stu-id="f864a-125">Follow one of these steps:</span></span>

    - <span data-ttu-id="f864a-126">Vai a **Gestione magazzino \> Impostazioni \> Scorte \> Codici NMFC**.</span><span class="sxs-lookup"><span data-stu-id="f864a-126">Go to **Warehouse management \> Setup \> Inventory \> NMFC codes**.</span></span>
    - <span data-ttu-id="f864a-127">Andare a **Gestione trasporto \> Impostazioni \> Standard di trasporto \> Codici NMFC**.</span><span class="sxs-lookup"><span data-stu-id="f864a-127">Go to **Transportation management \> Setup \> Transportation standards \> NMFC codes**.</span></span>

1. <span data-ttu-id="f864a-128">Seleziona **Nuovo** per creare un codice NMFC.</span><span class="sxs-lookup"><span data-stu-id="f864a-128">Select **New** to create an NMFC code.</span></span> <span data-ttu-id="f864a-129">Quindi impostare i seguenti campi:</span><span class="sxs-lookup"><span data-stu-id="f864a-129">Then set the following fields:</span></span>

    - <span data-ttu-id="f864a-130">**Codice NMFC** – Immettere il codice NMFC per il tipo di merce.</span><span class="sxs-lookup"><span data-stu-id="f864a-130">**NMFC code** – Enter the NMFC code for the commodity type.</span></span>
    - <span data-ttu-id="f864a-131">**Nome**: immetti un nome per il codice NMFC.</span><span class="sxs-lookup"><span data-stu-id="f864a-131">**Name** – Enter a name for the NMFC code.</span></span>
    - <span data-ttu-id="f864a-132">**Classe LTL** - Seleziona la classe LTL associata al codice NMFC.</span><span class="sxs-lookup"><span data-stu-id="f864a-132">**LTL class** – Select the LTL class that is associated with the NMFC code.</span></span>
    - <span data-ttu-id="f864a-133">**Unità di movimentazione BOL** - Definire il tipo di movimentazione predefinito per la spedizione.</span><span class="sxs-lookup"><span data-stu-id="f864a-133">**BOL handling unit** – Define the default handling type for the shipment.</span></span>

## <a name="example-set-up-nmfc-codes"></a><span data-ttu-id="f864a-134">Esempio: Impostare i codici NMFC</span><span class="sxs-lookup"><span data-stu-id="f864a-134">Example: Set up NMFC codes</span></span>

<span data-ttu-id="f864a-135">L'esempio seguente mostra come impostare due diversi codici NMFC che possono essere utilizzati con prodotti diversi.</span><span class="sxs-lookup"><span data-stu-id="f864a-135">The following example shows how to set up two different NMFC codes that can be used with different products.</span></span>

1. <span data-ttu-id="f864a-136">Vai a **Gestione magazzino \> Impostazioni \> Scorte \> Codici NMFC**.</span><span class="sxs-lookup"><span data-stu-id="f864a-136">Go to **Warehouse management \> Setup \> Inventory \> NMFC codes**.</span></span>
1. <span data-ttu-id="f864a-137">Nel Riquadro azioni selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="f864a-137">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="f864a-138">Nella nuova riga, imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="f864a-138">On the new line, set the following values:</span></span>

    - <span data-ttu-id="f864a-139">**Codice NMFC:** *92.5*</span><span class="sxs-lookup"><span data-stu-id="f864a-139">**NMFC code:** *92.5*</span></span>
    - <span data-ttu-id="f864a-140">**Nome:** *Computer*</span><span class="sxs-lookup"><span data-stu-id="f864a-140">**Name:** *Computers*</span></span>
    - <span data-ttu-id="f864a-141">**Classe LTL:** *92.5*</span><span class="sxs-lookup"><span data-stu-id="f864a-141">**LTL class:** *92.5*</span></span>
    - <span data-ttu-id="f864a-142">**Unità di movimentazione BOL:** *Unità*</span><span class="sxs-lookup"><span data-stu-id="f864a-142">**BOL handling unit:** *Unit*</span></span>

1. <span data-ttu-id="f864a-143">Nel riquadro azioni selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="f864a-143">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="f864a-144">Nel Riquadro azioni selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="f864a-144">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="f864a-145">Nella nuova riga, imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="f864a-145">On the new line, set the following values:</span></span>

    - <span data-ttu-id="f864a-146">**Codice NMFC:** *125*</span><span class="sxs-lookup"><span data-stu-id="f864a-146">**NMFC code:** *125*</span></span>
    - <span data-ttu-id="f864a-147">**Nome:** *Telefoni*</span><span class="sxs-lookup"><span data-stu-id="f864a-147">**Name:** *Phones*</span></span>
    - <span data-ttu-id="f864a-148">**Classe LTL:** *125*</span><span class="sxs-lookup"><span data-stu-id="f864a-148">**LTL class:** *125*</span></span>
    - <span data-ttu-id="f864a-149">**Unità di movimentazione BOL:** *Unità*</span><span class="sxs-lookup"><span data-stu-id="f864a-149">**BOL handling unit:** *Unit*</span></span>

1. <span data-ttu-id="f864a-150">Nel riquadro azioni selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="f864a-150">On the Action Pane, select **Save**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="f864a-151">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="f864a-151">Additional resources</span></span>

- [<span data-ttu-id="f864a-152">Classi di carico inferiore a quello del camion (LTL)</span><span class="sxs-lookup"><span data-stu-id="f864a-152">Less than truckload (LTL) classes</span></span>](ltl-class.md)
- [<span data-ttu-id="f864a-153">Creare una polizza di carico</span><span class="sxs-lookup"><span data-stu-id="f864a-153">Create a bill of landing</span></span>](create-bill-of-lading.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
