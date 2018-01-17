---
title: Conferma di prelievo pezzi
description: In questo argomento viene descritto come impostare e applicare la conferma di prelievo dei pezzi da un dispositivo mobile.
author: Mirzaab
manager: AnnBe
ms.date: 05/26/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WHSRFAutoConfirm, WHSRFMenuItem
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, Operations
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 029511634e56aec7fdd91bad9441cd12951fbd8d
ms.openlocfilehash: b1868851d22f41d3278cd9574a48bdf062185012
ms.contentlocale: it-it
ms.lasthandoff: 01/17/2018

---

# <a name="piece-picking-confirmation"></a><span data-ttu-id="fe71e-103">Conferma di prelievo pezzi</span><span class="sxs-lookup"><span data-stu-id="fe71e-103">Piece picking confirmation</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="fe71e-104">Il prelievo dei pezzi consente di confermare ogni pezzo di magazzino tramite lavoro di prelievo o conteggio su un dispositivo mobile.</span><span class="sxs-lookup"><span data-stu-id="fe71e-104">Piece picking allows you to confirm each piece of inventory through picking or counting work on a mobile device.</span></span> <span data-ttu-id="fe71e-105">Per i prelievi, è possibile confermare la quantità di lavoro da elaborare fino a quella specificata sul lavoro da prelevare.</span><span class="sxs-lookup"><span data-stu-id="fe71e-105">For picks, you can confirm the quantity of work to be processed up to the quantity that is specified on work to be picked.</span></span> <span data-ttu-id="fe71e-106">Per il lavoro di conteggio, è possibile analizzare le scorte in fase di conteggio e registrare l'importo totale.</span><span class="sxs-lookup"><span data-stu-id="fe71e-106">For counting work, you can scan the inventory that you are counting and track the total amount.</span></span>

<span data-ttu-id="fe71e-107">Quando si abilita il prelievo dei pezzi, la conferma del prodotto viene selezionata automaticamente.</span><span class="sxs-lookup"><span data-stu-id="fe71e-107">When you enable piece picking, product confirmation is automatically selected.</span></span> <span data-ttu-id="fe71e-108">Per i prelievi di tipo lavoro, il numero massimo di pezzi è abilitato.</span><span class="sxs-lookup"><span data-stu-id="fe71e-108">For work-type picks, a maximum number of pieces is enabled.</span></span> <span data-ttu-id="fe71e-109">Consente di impostare un valore massimo per il numero di pezzi che devono essere confermati durante il processo di lavoro.</span><span class="sxs-lookup"><span data-stu-id="fe71e-109">This allows you to set a maximum to the number of pieces that must be confirmed during the work process.</span></span> <span data-ttu-id="fe71e-110">La quantità massima è basata sull'unità di lavoro corrente in corso di elaborazione.</span><span class="sxs-lookup"><span data-stu-id="fe71e-110">The maximum quantity is based on the current work unit that is being processed.</span></span> <span data-ttu-id="fe71e-111">Il tipo di lavoro conteggio non consente un valore massimo.</span><span class="sxs-lookup"><span data-stu-id="fe71e-111">The counting work type does not allow a maximum.</span></span>

<span data-ttu-id="fe71e-112">È inoltre possibile utilizzare la quantità e l'unità di misura (UOM) associata a un codice a barre letto tramite scanner.</span><span class="sxs-lookup"><span data-stu-id="fe71e-112">You can also use the quantity and unit of measure (UOM) that is associated with a scanned bar code.</span></span> <span data-ttu-id="fe71e-113">Questo funzionerà per il ricevimento sui flussi in entrata incluso il ricevimento di numero di identificazione, articolo ordine fornitore, articolo ordine di trasferimento e articolo di carico.</span><span class="sxs-lookup"><span data-stu-id="fe71e-113">This will work for receiving on inbound flows including mixed license plate receiving, purchase order item, transfer order item, and load item.</span></span> <span data-ttu-id="fe71e-114">Funziona anche con il prelievo dei pezzi in cui scansione del codice a barre aggiunge la quantità al numero totale di pezzi confermati che eseguono la conversione tra l'unità di misura sul codice a barre e l'unità di lavoro.</span><span class="sxs-lookup"><span data-stu-id="fe71e-114">It also works for piece picking where scanning the bar code will add the quantity to the total number of confirmed pieces converting between the UOM on the bar code and the work unit.</span></span> <span data-ttu-id="fe71e-115">Se durante il conteggio dell'unità di misura sul codice a barre, viene confermato che la quantità è consentita per il conteggio per il gruppo di sequenze, la quantità verrà aggiunto al conto totale.</span><span class="sxs-lookup"><span data-stu-id="fe71e-115">If, when counting the UOM on the bar code, it is confirmed that the quantity is allowed for counting on the sequence group, the quantity will be added to the total count.</span></span>

## <a name="where-it-applies"></a><span data-ttu-id="fe71e-116">Dove si applica</span><span class="sxs-lookup"><span data-stu-id="fe71e-116">Where it applies</span></span>

<span data-ttu-id="fe71e-117">Il prelievo di pezzi funziona per tutto il lavoro di conteggio per il prelievo iniziale per qualsiasi tipo di lavoro.</span><span class="sxs-lookup"><span data-stu-id="fe71e-117">Piece picking works for all counting work and for the initial pick for any type of work.</span></span> <span data-ttu-id="fe71e-118">Il prelievo dei pezzi non è applicabile se l'articoloo è controllato dai numeri di serie o se si tratta di prelievo kanban o di produzione da un'ubicazione di della targa e l'articoloo è impostato sulla gestione temporanea.</span><span class="sxs-lookup"><span data-stu-id="fe71e-118">Piece picking does not apply if the item is controlled by serial numbers or if it is a production or kanban pick from a license plate (LP) location and the item is set to staging.</span></span>

## <a name="set-up-piece-picking"></a><span data-ttu-id="fe71e-119">Impostare il prelievo di pezzi</span><span class="sxs-lookup"><span data-stu-id="fe71e-119">Set up piece picking</span></span>

1.  <span data-ttu-id="fe71e-120">Su una voce di menu del dispositivo mobile, aprire il modulo di impostazione per la conferma di lavoro: Gestione magazzino > **Gestione magazzino** > **Impostazione** > **Dispositivo mobile** > **Voci di menu del dispositivo mobile**.</span><span class="sxs-lookup"><span data-stu-id="fe71e-120">On a mobile device menu item, open the setup form for work confirmation: Warehouse management > **Warehouse management** > **Setup** > **Mobile device** > **Mobile device menu items**.</span></span> 
2. <span data-ttu-id="fe71e-121">Dalle voci di menu del dispositivo mobile, aprire la configurazione della conferma del lavoro.</span><span class="sxs-lookup"><span data-stu-id="fe71e-121">From the mobile device menu item, open Work confirmation setup.</span></span>

<span data-ttu-id="fe71e-122">Le opzioni seguenti diventano disponibili per la selezione quando il tipo di lavoro è prelievo o conteggio.</span><span class="sxs-lookup"><span data-stu-id="fe71e-122">The following options become available for selection when the work type is pick or counting.</span></span>

| <span data-ttu-id="fe71e-123">Opzione</span><span class="sxs-lookup"><span data-stu-id="fe71e-123">Option</span></span>        | <span data-ttu-id="fe71e-124">descrizione</span><span class="sxs-lookup"><span data-stu-id="fe71e-124">Description</span></span>   | 
| ------------- | ------------- |
| <span data-ttu-id="fe71e-125">Conferma di prelievo pezzi</span><span class="sxs-lookup"><span data-stu-id="fe71e-125">Piece picking confirmation</span></span>   | <span data-ttu-id="fe71e-126">Disponibile per i tipi di lavoro prelievo e conteggio.</span><span class="sxs-lookup"><span data-stu-id="fe71e-126">Available for pick and counting work types.</span></span> <span data-ttu-id="fe71e-127">La conferma del prodotto viene selezionata automaticamente.</span><span class="sxs-lookup"><span data-stu-id="fe71e-127">Product confirmation is automatically selected.</span></span> <span data-ttu-id="fe71e-128">Consente di confermare ogni pezzo di magazzino dal dispositivo mobile.</span><span class="sxs-lookup"><span data-stu-id="fe71e-128">Allows you to confirm each piece of inventory from the mobile device.</span></span> | 
| <span data-ttu-id="fe71e-129">Numero massimo di pezzi</span><span class="sxs-lookup"><span data-stu-id="fe71e-129">Maximum number of pieces</span></span>     | <span data-ttu-id="fe71e-130">Disponibile per il lavoro di prelievo se la conferma di prelievo del pezzo è abilitata.</span><span class="sxs-lookup"><span data-stu-id="fe71e-130">Available for pick work if piece picking confirmation is enabled.</span></span> <span data-ttu-id="fe71e-131">Consente di impostare un limite al numero di pezzi che è necessario confermare.</span><span class="sxs-lookup"><span data-stu-id="fe71e-131">Sets a limit to the number of pieces that you must confirm.</span></span> |  

