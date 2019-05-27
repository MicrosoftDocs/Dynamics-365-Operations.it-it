---
title: Impostare programmi di continuità per i servizi clienti
description: In questo articolo viene descritto come impostare un programma di continuità per il servizio clienti.
author: josaw1
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: MCROrderParameters
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 16081
ms.assetid: 426a9be7-a931-4780-b372-e06f6083dd60
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 369856f33c6da49b6c6b3f51f42c99a8f07fe777
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "1555446"
---
# <a name="set-up-continuity-programs-for-call-centers"></a><span data-ttu-id="ac0a9-103">Impostare programmi di continuità per i servizi clienti</span><span class="sxs-lookup"><span data-stu-id="ac0a9-103">Set up continuity programs for call centers</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="ac0a9-104">In questo articolo viene descritto come impostare un programma di continuità per il servizio clienti.</span><span class="sxs-lookup"><span data-stu-id="ac0a9-104">This article describes how to set up a continuity program for a call center.</span></span>

<span data-ttu-id="ac0a9-105">In un programma di continuità, noto anche come programma ordine ricorrente, i clienti ricevono le spedizioni prodotto normali in base a una programmazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="ac0a9-105">In a continuity program, which is also known as a recurring order program, customers receive regular product shipments according to a predefined schedule.</span></span> <span data-ttu-id="ac0a9-106">Ogni spedizione può contenere un prodotto diverso, come nel caso di un club libro del mese oppure lo stesso prodotto può essere inviato più volte.</span><span class="sxs-lookup"><span data-stu-id="ac0a9-106">Each shipment can contain a different product, as in the case of a book-of-the-month club, or the same product can be sent repeatedly.</span></span> <span data-ttu-id="ac0a9-107">Per impostare un gruppo di continuità, è necessario completare le seguenti attività.</span><span class="sxs-lookup"><span data-stu-id="ac0a9-107">To set up a continuity program, you must complete the following tasks.</span></span>

1. <span data-ttu-id="ac0a9-108">Impostare i parametri di continuità nella pagina **Parametri servizio clienti**.</span><span class="sxs-lookup"><span data-stu-id="ac0a9-108">Set the continuity parameters on the **Call center parameters** page.</span></span>
2. <span data-ttu-id="ac0a9-109">Creare un programma di continuità che specifica dettagli quali lo scadenzario pagamenti, i tempi di spedizione e se la fatturazione è con costi preliminari fatturabili.</span><span class="sxs-lookup"><span data-stu-id="ac0a9-109">Create a continuity program that specifies details such as the payment schedule, the timing of the shipments, and whether billing is up front.</span></span> <span data-ttu-id="ac0a9-110">È inoltre necessario aggiungere un elenco di prodotti inclusi nel programma di continuità.</span><span class="sxs-lookup"><span data-stu-id="ac0a9-110">You must also add a list of products that are included in the continuity program.</span></span> <span data-ttu-id="ac0a9-111">Ciascun prodotto riceve un numero ID evento allocato in sequenza, a partire da 1.</span><span class="sxs-lookup"><span data-stu-id="ac0a9-111">Each product receives an event ID number that is assigned sequentially, beginning with 1.</span></span> <span data-ttu-id="ac0a9-112">Gli ID evento determinano l'ordine in cui i prodotti sono inviati.</span><span class="sxs-lookup"><span data-stu-id="ac0a9-112">The event IDs determine the order that products are sent in.</span></span>

    - <span data-ttu-id="ac0a9-113">Se i clienti ricevono un prodotto diverso in ogni spedizione, i prodotti vengono introdotti in ordine sequenziale in base ai relativi ID evento e a partire dall'evento corrente.</span><span class="sxs-lookup"><span data-stu-id="ac0a9-113">If customers receive a different product in each shipment, the products are sent in sequential order, based on their event IDs and beginning with the current event.</span></span>
    - <span data-ttu-id="ac0a9-114">Se i clienti ricevono lo stesso prodotto in ogni spedizione, l'elenco conterrà solo un prodotto con un ID evento.</span><span class="sxs-lookup"><span data-stu-id="ac0a9-114">If customers receive the same product in each shipment, the list contains only one product that has one event ID.</span></span> <span data-ttu-id="ac0a9-115">Lo stesso evento si verifica più volte.</span><span class="sxs-lookup"><span data-stu-id="ac0a9-115">The same event occurs repeatedly.</span></span> <span data-ttu-id="ac0a9-116">È possibile specificare quante volte ciascun evento viene ripetuto.</span><span class="sxs-lookup"><span data-stu-id="ac0a9-116">You can specify how many times each event is repeated.</span></span>

3. <span data-ttu-id="ac0a9-117">Creare un prodotto padre che rappresenta il programma continuità creato nell'attività 2.</span><span class="sxs-lookup"><span data-stu-id="ac0a9-117">Create a parent product that represents the continuity program that you created in task 2.</span></span> <span data-ttu-id="ac0a9-118">Se si aggiunge il prodotto in un ordine cliente, la pagina **Continuità** verrà aperta.</span><span class="sxs-lookup"><span data-stu-id="ac0a9-118">If you add this product to a sales order, the **Continuity** page opens.</span></span> <span data-ttu-id="ac0a9-119">È quindi possibile utilizzare tale pagina per creare l'ordine di continuità effettivo.</span><span class="sxs-lookup"><span data-stu-id="ac0a9-119">You can then use that page to create the actual continuity order.</span></span> <span data-ttu-id="ac0a9-120">Il prodotto padre non specifica i singoli prodotti che il cliente riceve in ogni spedizione.</span><span class="sxs-lookup"><span data-stu-id="ac0a9-120">The parent product doesn't specify the individual products that the customer receives in each shipment.</span></span>

<span data-ttu-id="ac0a9-121">Dopo aver impostato un programma di continuità come descritto in precedenza, è possibile creare un ordine di continuità per un cliente.</span><span class="sxs-lookup"><span data-stu-id="ac0a9-121">After you've set up a continuity program as described above, you can create a continuity order for a customer.</span></span> <span data-ttu-id="ac0a9-122">Potrebbe inoltre essere necessario eseguire le seguenti attività di manutenzione aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="ac0a9-122">You might also have to perform the following additional maintenance tasks.</span></span>

- <span data-ttu-id="ac0a9-123">**Aggiornare il periodo evento corrente di continuità**: impostare un processo batch che indica al sistema il periodo evento corrente.</span><span class="sxs-lookup"><span data-stu-id="ac0a9-123">**Update the current continuity event period** – Set up a batch job that tells the system what the current event period is.</span></span>
- <span data-ttu-id="ac0a9-124">**Crea ordini di continuità figlio**: creare ordini figlio dall'ordine di continuità padre.</span><span class="sxs-lookup"><span data-stu-id="ac0a9-124">**Create continuity child orders** – Create child orders from the parent continuity order.</span></span>
- <span data-ttu-id="ac0a9-125">**Elabora pagamenti di continuità**: elaborare la fatturazione e le notifiche per pagamenti associati agli ordini cliente di continuità.</span><span class="sxs-lookup"><span data-stu-id="ac0a9-125">**Process continuity payments** – Process billing and notifications for payments that are associated with continuity sales orders.</span></span>
- <span data-ttu-id="ac0a9-126">**Estendi righe continuità** (se necessario): estendere il numero di volte che un evento di continuità può essere ripetuto.</span><span class="sxs-lookup"><span data-stu-id="ac0a9-126">**Extend continuity lines** (if required) – Extend the number of times that a continuity event can be repeated.</span></span> <span data-ttu-id="ac0a9-127">La ripetizione delle spedizioni può quindi estendersi oltre il limite impostato nel campo **Soglia ripetizione continuità** dei parametri del servizio clienti.</span><span class="sxs-lookup"><span data-stu-id="ac0a9-127">The repetition of shipments can then extend beyond the limit that was set in the **Continuity repeat threshold** field in the call center parameters.</span></span>
- <span data-ttu-id="ac0a9-128">**Eseguire un aggiornamento di continuità** (se necessario): sincronizzare le modifiche tra il programma di continuità e gli ordini cliente padre di continuità.</span><span class="sxs-lookup"><span data-stu-id="ac0a9-128">**Perform a continuity update** (if required) – Synchronize changes between the continuity program and the continuity parent sales orders.</span></span>
- <span data-ttu-id="ac0a9-129">**Chiudi righe e ordini di continuità**: chiudere gli ordini di continuità.</span><span class="sxs-lookup"><span data-stu-id="ac0a9-129">**Close continuity parent lines and orders** – Close continuity orders.</span></span>
