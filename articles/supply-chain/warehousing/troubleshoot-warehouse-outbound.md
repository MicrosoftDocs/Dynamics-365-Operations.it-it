---
title: Risolvere i problemi relativi alle operazioni di magazzino in uscita
description: Questo argomento descrive come risolvere i problemi comuni che si possono verificare quando si utilizzano le operazioni di magazzino in uscita in Microsoft Dynamics 365 Supply Chain Management.
author: perlynne
manager: tfehr
ms.date: 10/19/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-19
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 56bd91d8a6fe895317021d806e180df3a2db302b
ms.sourcegitcommit: deb711c92251ed48cdf20ea514d03461c26a2262
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/25/2020
ms.locfileid: "4645454"
---
# <a name="troubleshoot-outbound-warehouse-operations"></a><span data-ttu-id="9ff19-103">Risolvere i problemi relativi alle operazioni di magazzino in uscita</span><span class="sxs-lookup"><span data-stu-id="9ff19-103">Troubleshoot outbound warehouse operations</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9ff19-104">Questo argomento descrive come risolvere i problemi comuni che si possono verificare quando si utilizzano le operazioni di magazzino in uscita in Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="9ff19-104">This topic describes how to fix common issues that you might encounter while you work with outbound warehouse operations in Microsoft Dynamics 365 Supply Chain Management.</span></span>

## <a name="i-receive-the-following-error-message-sales-order-could-not-be-released"></a><span data-ttu-id="9ff19-105">Viene visualizzato il seguente messaggio di errore: "Impossibile rilasciare l'ordine cliente".</span><span class="sxs-lookup"><span data-stu-id="9ff19-105">I receive the following error message: "Sales order could not be released."</span></span>

### <a name="issue-description"></a><span data-ttu-id="9ff19-106">Descrizione del problema</span><span class="sxs-lookup"><span data-stu-id="9ff19-106">Issue description</span></span>

<span data-ttu-id="9ff19-107">Questo problema può verificarsi per diversi motivi.</span><span class="sxs-lookup"><span data-stu-id="9ff19-107">This issue can occur for several reasons.</span></span> <span data-ttu-id="9ff19-108">Ad esempio, l'ordine è in attesa della gestione del credito e non è possibile creare spedizioni finché non viene immesso un indirizzo postale valido per tutte le righe di vendita associate all'ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="9ff19-108">For example, the order is on credit management hold, and no shipments can be created until a valid postal address is entered for all sales lines that are associated with a sales order.</span></span> <span data-ttu-id="9ff19-109">In alternativa, esiste una sospensione dell'ordine che deve essere risolta prima che l'ordine possa essere rilasciato al magazzino.</span><span class="sxs-lookup"><span data-stu-id="9ff19-109">Alternatively, there is an order hold that must be addressed before the order can be released to the warehouse.</span></span> <span data-ttu-id="9ff19-110">Questa sospensione potrebbe essere specifica dell'ordine o potrebbe essere sull'account del cliente.</span><span class="sxs-lookup"><span data-stu-id="9ff19-110">This hold might be order-specific, or it might be on the customer account.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="9ff19-111">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="9ff19-111">Issue resolution</span></span>

<span data-ttu-id="9ff19-112">Aggiungere o aggiornare l'indirizzo nell'ordine cliente e nelle righe ordine, quindi rilasciare l'ordine al magazzino.</span><span class="sxs-lookup"><span data-stu-id="9ff19-112">Add or update the address on the sales order and order lines, and then release the order to the warehouse.</span></span> <span data-ttu-id="9ff19-113">Gli ordini possono essere rilasciati al magazzino solo se hanno un indirizzo di consegna valido (in base all'impostazione del formato dell'indirizzo nel modulo **Amministrazione organizzazione**).</span><span class="sxs-lookup"><span data-stu-id="9ff19-113">Orders can be released to the warehouse only if they have a valid delivery address (per the address format setup in the **Organization administration** module).</span></span>

<span data-ttu-id="9ff19-114">Esaminare la sospensione dell'ordine e risolvere i problemi.</span><span class="sxs-lookup"><span data-stu-id="9ff19-114">Investigate the order hold, and address the issues.</span></span> <span data-ttu-id="9ff19-115">Quindi rimuovere la sospensione dall'ordine o dal cliente e rilasciare l'ordine al magazzino.</span><span class="sxs-lookup"><span data-stu-id="9ff19-115">Then remove the hold from the order or customer, and release the order to the warehouse.</span></span>

## <a name="i-receive-the-following-message-the-shipment-for-load-1-has-been-confirmed-however-no-lines-are-posted"></a><span data-ttu-id="9ff19-116">Viene visualizzato il seguente messaggio: "La spedizione per il carico 1% è stata confermata."</span><span class="sxs-lookup"><span data-stu-id="9ff19-116">I receive the following message: "The shipment for load 1% has been confirmed."</span></span> <span data-ttu-id="9ff19-117">Tuttavia, non vengono registrate le righe.</span><span class="sxs-lookup"><span data-stu-id="9ff19-117">However, no lines are posted.</span></span>

### <a name="issue-description"></a><span data-ttu-id="9ff19-118">Descrizione del problema</span><span class="sxs-lookup"><span data-stu-id="9ff19-118">Issue description</span></span>

<span data-ttu-id="9ff19-119">È stata confermata una spedizione di un carico, ma non sono state effettuate ulteriori registrazioni.</span><span class="sxs-lookup"><span data-stu-id="9ff19-119">A shipment on a load was confirmed, but no further posting occurred.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="9ff19-120">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="9ff19-120">Issue resolution</span></span>

<span data-ttu-id="9ff19-121">La conferma della spedizione non influisce sulla registrazione.</span><span class="sxs-lookup"><span data-stu-id="9ff19-121">Shipment confirmation doesn't affect posting.</span></span> <span data-ttu-id="9ff19-122">Aggiorna solo lo stato della spedizione e del carico.</span><span class="sxs-lookup"><span data-stu-id="9ff19-122">It just updates the shipment and load status.</span></span> <span data-ttu-id="9ff19-123">La registrazione deve avvenire in un processo separato.</span><span class="sxs-lookup"><span data-stu-id="9ff19-123">Posting must occur in a separate process.</span></span>

## <a name="i-receive-the-following-error-message-direct-delivery-is-not-able-to-process-for-warehouse-1-as-it-has-warehouse-management-enabled-please-specify-another-warehouse-that-is-not-enabled-for-warehouse-management"></a><span data-ttu-id="9ff19-124">Viene visualizzato il seguente messaggio di errore: "La consegna diretta non è in grado di elaborare per il magazzino 1% poiché la gestione magazzino è abilitata.</span><span class="sxs-lookup"><span data-stu-id="9ff19-124">I receive the following error message: "Direct delivery is not able to process for warehouse 1% as it has warehouse management enabled.</span></span> <span data-ttu-id="9ff19-125">Specificare un altro magazzino non abilitato per la gestione del magazzino."</span><span class="sxs-lookup"><span data-stu-id="9ff19-125">Please specify another warehouse that is not enabled for warehouse management."</span></span>

### <a name="issue-description"></a><span data-ttu-id="9ff19-126">Descrizione del problema</span><span class="sxs-lookup"><span data-stu-id="9ff19-126">Issue description</span></span>

<span data-ttu-id="9ff19-127">Un articolo viene aggiunto a una riga di vendita per la consegna diretta da un magazzino abilitato per la gestione del magazzino (WMS).</span><span class="sxs-lookup"><span data-stu-id="9ff19-127">An item is added to a sales line for direct delivery from a warehouse that is enabled for warehouse management (WMS).</span></span> <span data-ttu-id="9ff19-128">Viene visualizzato questo messaggio di errore quando viene aggiornata la riga di vendita.</span><span class="sxs-lookup"><span data-stu-id="9ff19-128">You receive this error message when the sales line is updated.</span></span> 

### <a name="issue-resolution"></a><span data-ttu-id="9ff19-129">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="9ff19-129">Issue resolution</span></span>

<span data-ttu-id="9ff19-130">Microsoft ha valutato questo problema e ha stabilito che si tratta di una limitazione delle funzionalità.</span><span class="sxs-lookup"><span data-stu-id="9ff19-130">Microsoft has evaluated this issue and has determined that it's a feature limitation.</span></span> <span data-ttu-id="9ff19-131">Attualmente, WMS non supporta la consegna diretta.</span><span class="sxs-lookup"><span data-stu-id="9ff19-131">Currently, WMS doesn't support direct delivery.</span></span> <span data-ttu-id="9ff19-132">Pertanto, per utilizzare la consegna diretta, è necessario selezionare un articolo e un magazzino non WMS.</span><span class="sxs-lookup"><span data-stu-id="9ff19-132">Therefore, to use direct delivery, you must select a non-WMS item and warehouse.</span></span>
