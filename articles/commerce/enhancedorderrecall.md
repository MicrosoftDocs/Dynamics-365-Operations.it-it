---
title: Operazione Richiama ordine nel POS
description: In questo argomento vengono descritte le funzionalità disponibili per le pagine Richiama ordine nel POS.
author: hhainesms
manager: annbe
ms.date: 10/09/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.search.region: global
ms.author: hhaines
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 41944fb7819b5527f6bc023a60acd9450d9e43c2
ms.sourcegitcommit: 25909c6ad3616e4f75a2fe006057dda18d7cc856
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/09/2020
ms.locfileid: "3974840"
---
# <a name="recall-order-operation-in-pos"></a><span data-ttu-id="02d86-103">Operazione Richiama ordine nel POS</span><span class="sxs-lookup"><span data-stu-id="02d86-103">Recall order operation in POS</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="02d86-104">L'operazione Richiama ordine nel POS fornisce funzionalità di ricerca e filtro degli ordini aggiornate e informazioni specifiche dell'ordine.</span><span class="sxs-lookup"><span data-stu-id="02d86-104">The Recall order operation in the Commerce point of sale (POS) provides updated order search and filtering features and order-specific information.</span></span> <span data-ttu-id="02d86-105">Questa funzionalità è disponibile in Commerce versione 10.0.15 e successive.</span><span class="sxs-lookup"><span data-stu-id="02d86-105">This feature is available in Commerce versions 10.0.15 and later.</span></span>

<span data-ttu-id="02d86-106">Per abilitare questa funzionalità, attiva la funzionalità **Operazione Richiama ordine migliorata nel POS** nell'area di lavoro **Gestione funzionalità** in Commerce Headquarters.</span><span class="sxs-lookup"><span data-stu-id="02d86-106">To enable this functionality, turn the **Improved Recall order operation in POS** feature on in **Feature management** workspace in Commerce headquarters.</span></span> <span data-ttu-id="02d86-107">Dopo aver abilitato la funzionalità, valuta la possibilità di aggiornare i [layout dello schermo](pos-screen-layouts.md) nel POS per utilizzare alcune delle funzionalità modificate.</span><span class="sxs-lookup"><span data-stu-id="02d86-107">After you enable the feature, consider updating your [screen layouts](pos-screen-layouts.md) in POS to take advantage of some of the changed  capabilities.</span></span>

<span data-ttu-id="02d86-108">La configurazione del pulsante dell'operazione **Richiama ordine** consente alle organizzazioni di distribuire l'operazione con una visualizzazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="02d86-108">The configuration of the **Recall order** operation button allows organizations to deploy the operation with a pre-defined display.</span></span>

![Configurazione della griglia dei pulsanti](media/recallorderbuttongrid.png)

<span data-ttu-id="02d86-110">Le opzioni di visualizzazione sono riportate di seguito.</span><span class="sxs-lookup"><span data-stu-id="02d86-110">The display options are as follows.</span></span>
- <span data-ttu-id="02d86-111">**Nessuna** - Questa opzione distribuisce l'operazione senza una visualizzazione specifica.</span><span class="sxs-lookup"><span data-stu-id="02d86-111">**None** – This option deploys the operation with no specific display.</span></span> <span data-ttu-id="02d86-112">Quando un utente apre l'operazione con questa configurazione, gli viene richiesto di cercare e trovare ordini o di scegliere da un filtro di ordini predefinito.</span><span class="sxs-lookup"><span data-stu-id="02d86-112">When a user opens the operation with this configuration, they will be prompted to search and find orders or choose from a pre-defined order filter.</span></span>
- <span data-ttu-id="02d86-113">**Ordini da evadere** - Quando un utente avvia l'operazione, viene eseguita automaticamente una query per cercare e visualizzare un elenco di ordini che devono essere evasi dal punto vendita.</span><span class="sxs-lookup"><span data-stu-id="02d86-113">**Orders to fulfill** – When a user launches the operation, a query will run automatically to search and display a list of orders that are to be fulfilled by the store.</span></span> <span data-ttu-id="02d86-114">Questi ordini sono configurati per il prelievo presso il punto vendita o la spedizione dal punto vendita e le righe di questi ordini non sono ancora state prelevate o imballate.</span><span class="sxs-lookup"><span data-stu-id="02d86-114">These orders are configured for in-store pickup or store shipment and the lines of these orders have not yet been picked or packed.</span></span>
- <span data-ttu-id="02d86-115">**Ordini da prelevare** - Quando un utente avvia l'operazione, viene eseguita automaticamente una query per cercare e visualizzare un elenco di ordini configurati per il prelievo presso il punto vendita corrente dell'utente.</span><span class="sxs-lookup"><span data-stu-id="02d86-115">**Orders to pick up** – When a user launches the operation, a query will run automatically to search and display a list of orders that are configured for in-store pickup at the user's current store.</span></span>
- <span data-ttu-id="02d86-116">**Ordini da spedire** - Quando un utente avvia l'operazione, viene eseguita automaticamente una query per cercare e visualizzare un elenco di ordini configurati per la spedizione dal punto vendita corrente dell'utente.</span><span class="sxs-lookup"><span data-stu-id="02d86-116">**Orders to ship** - When a user launches the operation, a query will run automatically to search and display a list of orders that are configured for shipment from the user's current store.</span></span>

<span data-ttu-id="02d86-117">Quando si avvia l'operazione **Richiama ordine** dal POS, se il display è impostato su **Nessuna**, un utente sarà in grado di cercare e recuperare ordini in uno dei seguenti modi.</span><span class="sxs-lookup"><span data-stu-id="02d86-117">When launching the **Recall order** operation from POS, if the display is configured to **None**, a user will be able to search and retrieve orders in one of the following ways.</span></span>
- <span data-ttu-id="02d86-118">Scansione di codici a barre di ordini.</span><span class="sxs-lookup"><span data-stu-id="02d86-118">Scan order barcodes.</span></span> <span data-ttu-id="02d86-119">In questo modo, vengono cercate le corrispondenze ai campi di numero ordine, riferimento canale e ID ricevuta.</span><span class="sxs-lookup"><span data-stu-id="02d86-119">This will search order number, channel reference, and receipt ID fields for matches.</span></span>
- <span data-ttu-id="02d86-120">Selezione dell'icona **Cerca ordini** o **Cerca e filtra** nella barra dell'applicazione per utilizzare il meccanismo di filtro con cui individuare gli ordini che soddisfano i criteri di filtro.</span><span class="sxs-lookup"><span data-stu-id="02d86-120">Select **Search orders** or **Search and filter** icon on the AppBar to use the filtering mechanism to locate orders that meet the filter criteria.</span></span>
- <span data-ttu-id="02d86-121">Scelta di un filtro predefinito nel menu a discesa **Mostra ordini** (ordini da evadere, ordini da prelevare o ordini da spedire).</span><span class="sxs-lookup"><span data-stu-id="02d86-121">Choose from a pre-defined filter from the **Show Orders** drop-down menu (orders to fulfill, orders to pick up, or orders to ship).</span></span>

![RecallOrderMainMenu](media/recallordermain.png)

<span data-ttu-id="02d86-123">Dopo aver applicato i criteri di ricerca, l'applicazione visualizzerà un elenco di ordini di vendita corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="02d86-123">After search criteria are applied, the application will display a list of matching sales orders.</span></span>

![RecallOrderDetail](media/orderrecalldetail.png)

<span data-ttu-id="02d86-125">Un utente può selezionare un ordine nell'elenco per visualizzare ulteriori dettagli.</span><span class="sxs-lookup"><span data-stu-id="02d86-125">A user can select an order on the list to view additional details.</span></span> <span data-ttu-id="02d86-126">Il pannello delle informazioni sul lato destro della schermata visualizza le specifiche sull'ordine selezionato, inclusi i dettagli su riga dell'ordine, consegna e evasione.</span><span class="sxs-lookup"><span data-stu-id="02d86-126">The information panel on the right side of the screen displays specifics on the selected order, including order line details, delivery details, and fulfillment details.</span></span>

<span data-ttu-id="02d86-127">Un utente può selezionare un'operazione nella barra dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="02d86-127">From the AppBar, a user can select an operation.</span></span> <span data-ttu-id="02d86-128">A seconda dello stato dell'ordine, è possibile che alcune operazioni non siano disponibili.</span><span class="sxs-lookup"><span data-stu-id="02d86-128">Depending on the status of the order, certain operations may not be enabled.</span></span>

- <span data-ttu-id="02d86-129">**Reso** - Esegue un reso per una o più fatture relative all'ordine cliente selezionato.</span><span class="sxs-lookup"><span data-stu-id="02d86-129">**Return** – Executes a return for one or more invoices related to the selected customer order.</span></span>

- <span data-ttu-id="02d86-130">**Annulla** - Emette un annullamento completo dell'ordine cliente selezionato.</span><span class="sxs-lookup"><span data-stu-id="02d86-130">**Cancel** – Issue a full cancellation of the selected sales order.</span></span>

- <span data-ttu-id="02d86-131">**Evadi** - Trasferisce l'utente alla pagina di evasione dell'ordine, che verrà pre-filtrata per l'ordine selezionato.</span><span class="sxs-lookup"><span data-stu-id="02d86-131">**Fulfill** – Transfers the user to the order fulfillment page, which will be pre-filtered for the selected order.</span></span> <span data-ttu-id="02d86-132">Vengono visualizzate solo le righe dell'ordine aperte per l'evasione dal punto vendita dell'utente per l'ordine selezionato.</span><span class="sxs-lookup"><span data-stu-id="02d86-132">Only order lines that are open for fulfillment by the user's store for the selected order will be displayed.</span></span>

- <span data-ttu-id="02d86-133">**Modifica** - Consente agli utenti di apportare modifiche all'ordine cliente selezionato.</span><span class="sxs-lookup"><span data-stu-id="02d86-133">**Edit** – Allows users to make changes to the selected customer order.</span></span>

- <span data-ttu-id="02d86-134">**Preleva** - Avvia il flusso di prelievo, che consente all'utente di scegliere i prodotti da prelevare e crea la transazione di prelievo delle vendite.</span><span class="sxs-lookup"><span data-stu-id="02d86-134">**Pick up** – Launches the pickup flow, which allows the user to choose the products to be picked up and creates the pickup sales transaction.</span></span>
