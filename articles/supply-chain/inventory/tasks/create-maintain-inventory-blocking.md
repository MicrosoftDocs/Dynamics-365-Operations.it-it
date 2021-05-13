---
title: Creare e gestire un blocco scorte
description: Questo argomento descrive come usare un blocco scorte per impedire che scorte fisiche disponibili vengano prenotate da altri documenti di origine in uscita.
author: perlynne
ms.date: 03/23/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: InventBlocking, InventItemIdLookupSimple, InventLocationIdLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e9aa38ca52da577fff258bb330922ad7f4044330
ms.sourcegitcommit: 8362f3bd32ce8b9a5af93c8e57daef732a93b19e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2021
ms.locfileid: "5956160"
---
# <a name="create-and-maintain-an-inventory-blocking"></a><span data-ttu-id="42cdc-103">Creare e gestire un blocco scorte</span><span class="sxs-lookup"><span data-stu-id="42cdc-103">Create and maintain an inventory blocking</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="42cdc-104">Questo argomento descrive come usare un blocco scorte per impedire che scorte fisiche disponibili vengano prenotate da altri documenti di origine in uscita.</span><span class="sxs-lookup"><span data-stu-id="42cdc-104">This topic describes how to use an inventory blocking to prevent physical on-hand inventory from being reserved by other outbound source documents.</span></span> <span data-ttu-id="42cdc-105">Prima di iniziare le procedure in questo argomento, è necessario disporre di un articolo con scorte fisiche disponibili.</span><span class="sxs-lookup"><span data-stu-id="42cdc-105">Before you start the procedures in this topic, you must have an item that physical on-hand inventory is available for.</span></span>

## <a name="block-inventory"></a><span data-ttu-id="42cdc-106">Blocca scorte</span><span class="sxs-lookup"><span data-stu-id="42cdc-106">Block inventory</span></span>

<span data-ttu-id="42cdc-107">Per creare un record di blocco scorte in modo che le scorte siano bloccate, segui questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="42cdc-107">To create an inventory blocking record so that inventory is blocked, follow these steps.</span></span>

1. <span data-ttu-id="42cdc-108">Andare a **Gestione articoli \> Attività periodiche \> Blocco scorte**.</span><span class="sxs-lookup"><span data-stu-id="42cdc-108">Go to **Inventory management \> Periodic tasks \> Inventory blocking**.</span></span>
1. <span data-ttu-id="42cdc-109">Nel Riquadro azioni selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="42cdc-109">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="42cdc-110">Nell'intestazione del nuovo record di blocco, impostare il campo **Numero articolo** sull'articolo che si desidera bloccare e immettere una descrizione.</span><span class="sxs-lookup"><span data-stu-id="42cdc-110">On the header of the new blocking record, set the **Item number** field to the item that you want to block, and enter a description.</span></span>
1. <span data-ttu-id="42cdc-111">Nella scheda dettaglio **Generale**, nel campo **Quantità** immettere il numero di articoli da bloccare.</span><span class="sxs-lookup"><span data-stu-id="42cdc-111">On the **General** FastTab, in the **Quantity** field, enter the number of items to block.</span></span>
1. <span data-ttu-id="42cdc-112">Nella scheda dettaglio **Dimensioni inventariali**, specificare il sito e il magazzino in cui si trovano attualmente gli articoli che si desidera bloccare.</span><span class="sxs-lookup"><span data-stu-id="42cdc-112">On the **Inventory dimensions** FastTab, specify the site and warehouse where the items that you want to block are currently located.</span></span>
1. <span data-ttu-id="42cdc-113">Nel riquadro azioni selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="42cdc-113">On the Action Pane, select **Save**.</span></span>

## <a name="update-the-conditions-of-the-inventory-blocking"></a><span data-ttu-id="42cdc-114">Aggiornare le condizioni del blocco scorte</span><span class="sxs-lookup"><span data-stu-id="42cdc-114">Update the conditions of the inventory blocking</span></span>

<span data-ttu-id="42cdc-115">Per aggiornare un record di blocco scorte, segui questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="42cdc-115">To update an inventory blocking record, follow these steps.</span></span>

1. <span data-ttu-id="42cdc-116">Andare a **Gestione articoli \> Attività periodiche \> Blocco scorte**.</span><span class="sxs-lookup"><span data-stu-id="42cdc-116">Go to **Inventory management \> Periodic tasks \> Inventory blocking**.</span></span>
1. <span data-ttu-id="42cdc-117">Nel riquadro elenco, selezionare il record di blocco pertinente.</span><span class="sxs-lookup"><span data-stu-id="42cdc-117">In the list pane, select the relevant blocking record.</span></span>
1. <span data-ttu-id="42cdc-118">Modifica il record in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="42cdc-118">Edit the record as required.</span></span> <span data-ttu-id="42cdc-119">Ad esempio, potresti modificare il valore del campo **Data prevista** per indicare il momento in cui si prevede che le scorte bloccate diventino disponibili per la prenotazione.</span><span class="sxs-lookup"><span data-stu-id="42cdc-119">For example, you might change the value of the **Expected date** field to indicate when the blocked inventory is expected to become available for reservation.</span></span> <span data-ttu-id="42cdc-120">Se l'opzione **Entrate previste** è selezionata, la data apparirà sulla transazione prevista.</span><span class="sxs-lookup"><span data-stu-id="42cdc-120">If the **Expected receipts** option is selected, the date will appear on the expected transaction.</span></span> <span data-ttu-id="42cdc-121">(L'opzione **Entrate previste** è selezionata per impostazione predefinita quando si crea manualmente un record di blocco.)</span><span class="sxs-lookup"><span data-stu-id="42cdc-121">(The **Expected receipts** option is selected by default when you manually create a blocking record.)</span></span>
1. <span data-ttu-id="42cdc-122">Nel riquadro azioni selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="42cdc-122">On the Action Pane, select **Save**.</span></span>

## <a name="unblock-inventory"></a><span data-ttu-id="42cdc-123">Sloccare le scorte</span><span class="sxs-lookup"><span data-stu-id="42cdc-123">Unblock inventory</span></span>

<span data-ttu-id="42cdc-124">Per rimuovere un record di blocco scorte in modo che le scorte siano sbloccate, segui questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="42cdc-124">To remove an inventory blocking record so that inventory is unblocked, follow these steps.</span></span>

1. <span data-ttu-id="42cdc-125">Andare a **Gestione articoli \> Attività periodiche \> Blocco scorte**.</span><span class="sxs-lookup"><span data-stu-id="42cdc-125">Go to **Inventory management \> Periodic tasks \> Inventory blocking**.</span></span>
1. <span data-ttu-id="42cdc-126">Nel riquadro elenco, selezionare il record di blocco pertinente.</span><span class="sxs-lookup"><span data-stu-id="42cdc-126">In the list pane, select the relevant blocking record.</span></span>
1. <span data-ttu-id="42cdc-127">Nel riquadro azioni selezionare **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="42cdc-127">On the Action Pane, select **Delete**.</span></span>
1. <span data-ttu-id="42cdc-128">Ti viene chiesto di confermare l'operazione.</span><span class="sxs-lookup"><span data-stu-id="42cdc-128">You're prompted to confirm the operation.</span></span> <span data-ttu-id="42cdc-129">Selezionare **Sì** per continuare.</span><span class="sxs-lookup"><span data-stu-id="42cdc-129">Select **Yes** to continue.</span></span>
1. <span data-ttu-id="42cdc-130">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="42cdc-130">Close the page.</span></span>

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
