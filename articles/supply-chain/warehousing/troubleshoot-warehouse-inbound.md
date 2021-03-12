---
title: Risolvere i problemi relativi alle operazioni di magazzino in entrata
description: Questo argomento descrive come risolvere i problemi comuni che si possono verificare quando si utilizzano le operazioni di magazzino in entrata in Microsoft Dynamics 365 Supply Chain Management.
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
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-19
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 71f590ec01b757de298bd2692fdbdb0324843376
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4970252"
---
# <a name="troubleshoot-inbound-warehouse-operations"></a><span data-ttu-id="3bd7b-103">Risolvere i problemi relativi alle operazioni di magazzino in entrata</span><span class="sxs-lookup"><span data-stu-id="3bd7b-103">Troubleshoot inbound warehouse operations</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="3bd7b-104">Questo argomento descrive come risolvere i problemi comuni che si possono verificare quando si utilizzano le operazioni di magazzino in entrata in Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="3bd7b-104">This topic describes how to fix common issues that you might encounter while you work with inbound warehouse operations in Microsoft Dynamics 365 Supply Chain Management.</span></span>

## <a name="i-receive-the-following-error-message-quality-order-1-has-been-generated-cluster-profile-could-not-be-found-please-check-your-configuration"></a><span data-ttu-id="3bd7b-105">Viene visualizzato il seguente messaggio di errore: "Ordine di controllo qualità %1 è stato generato.</span><span class="sxs-lookup"><span data-stu-id="3bd7b-105">I receive the following error message: "Quality order %1 has been generated.</span></span> <span data-ttu-id="3bd7b-106">Impossibile trovare il profilo cluster per verificare la configurazione."</span><span class="sxs-lookup"><span data-stu-id="3bd7b-106">Cluster profile could not be found please check your configuration."</span></span>

### <a name="issue-description"></a><span data-ttu-id="3bd7b-107">Descrizione del problema</span><span class="sxs-lookup"><span data-stu-id="3bd7b-107">Issue description</span></span>

<span data-ttu-id="3bd7b-108">Questo messaggio di errore è correlato a un processo di ricezione in cui è attivata la gestione della qualità (QMS).</span><span class="sxs-lookup"><span data-stu-id="3bd7b-108">This error message is related to a receiving process where quality management (QMS) is turned on.</span></span> <span data-ttu-id="3bd7b-109">A seconda delle configurazioni nel proprio ambiente, ulteriori dettagli sulla transazione che sta generando il messaggio di errore potrebbero aiutare a risolvere il problema.</span><span class="sxs-lookup"><span data-stu-id="3bd7b-109">Depending on the configurations in your environment, additional details about the transaction that is generating the error message might help fix the issue.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="3bd7b-110">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="3bd7b-110">Issue resolution</span></span>

<span data-ttu-id="3bd7b-111">Innanzitutto, esaminare l'impostazione di [prelievo cluster](set-up-cluster-picking.md) e assicurarsi che i profili del cluster siano impostati correttamente.</span><span class="sxs-lookup"><span data-stu-id="3bd7b-111">First, review the [cluster picking](set-up-cluster-picking.md) setup, and make sure that your cluster profiles are set up correctly.</span></span> <span data-ttu-id="3bd7b-112">Non è possibile utilizzare una voce di menu del dispositivo mobile per la selezione del cluster a meno che non siano stati configurati i profili del cluster.</span><span class="sxs-lookup"><span data-stu-id="3bd7b-112">You can't use a mobile device menu item for cluster picking unless cluster profiles are set up.</span></span> <span data-ttu-id="3bd7b-113">A seconda del proprio ambiente, potrebbe essere necessario rivedere anche altre configurazioni correlate.</span><span class="sxs-lookup"><span data-stu-id="3bd7b-113">Depending on your environment, you might also have to review other related configurations.</span></span>

## <a name="mixed-license-plate-receiving-doesnt-work-for-any-disposition-code-except-credit"></a><span data-ttu-id="3bd7b-114">La ricezione di targhe miste non funziona per nessun codice smaltimento eccetto il credito.</span><span class="sxs-lookup"><span data-stu-id="3bd7b-114">Mixed license plate receiving doesn't work for any disposition code except Credit.</span></span>

### <a name="issue-description"></a><span data-ttu-id="3bd7b-115">Descrizione del problema</span><span class="sxs-lookup"><span data-stu-id="3bd7b-115">Issue description</span></span>

<span data-ttu-id="3bd7b-116">Quando il campo **Azione** per un codice smaltimento è impostato su *Credito* o *Scarti*, è possibile usare solo la voce di menu [Ricevimento targa mista](mixed-license-plate-receiving.md) per elaborare gli articoli restituiti.</span><span class="sxs-lookup"><span data-stu-id="3bd7b-116">When the **Action** field for a disposition code is set to *Credit* or *Scrap*, you can use only the [Mixed license plate receiving](mixed-license-plate-receiving.md) menu item to process returned items.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="3bd7b-117">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="3bd7b-117">Issue resolution</span></span>

<span data-ttu-id="3bd7b-118">Microsoft ha valutato questo problema e ha stabilito che si tratta di una limitazione delle funzionalità.</span><span class="sxs-lookup"><span data-stu-id="3bd7b-118">Microsoft has evaluated this issue and has determined that it's a feature limitation.</span></span> <span data-ttu-id="3bd7b-119">Attualmente solo i [codici smaltimento](../service-management/set-up-disposition-codes.md) dove il campo **Azione** è impostato su *Credito* o *Scarti* sono supportati per la ricezione di targhe miste.</span><span class="sxs-lookup"><span data-stu-id="3bd7b-119">Currently, only [disposition codes](../service-management/set-up-disposition-codes.md) where the **Action** field is set to *Credit* or *Scrap* are supported for mixed license plate receiving.</span></span>

## <a name="when-i-run-the-update-product-receipts-periodic-task-unconfirmed-purchase-orders-are-confirmed"></a><span data-ttu-id="3bd7b-120">Quando si esegue l'attività periodica Aggiorna entrate prodotti, vengono confermati gli ordini fornitore non confermati.</span><span class="sxs-lookup"><span data-stu-id="3bd7b-120">When I run the Update product receipts periodic task, unconfirmed purchase orders are confirmed.</span></span>

### <a name="issue-description"></a><span data-ttu-id="3bd7b-121">Descrizione del problema</span><span class="sxs-lookup"><span data-stu-id="3bd7b-121">Issue description</span></span>

<span data-ttu-id="3bd7b-122">Dopo aver eseguito l'attività periodica *Aggiorna entrate prodotti*, il sistema conferma automaticamente gli ordini fornitore non confermati con stato di transazione di magazzino *Registrato*.</span><span class="sxs-lookup"><span data-stu-id="3bd7b-122">After you run the *Update product receipts* periodic task, the system automatically confirms unconfirmed purchase orders that have an inventory transaction status of *Registered*.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="3bd7b-123">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="3bd7b-123">Issue resolution</span></span>

<span data-ttu-id="3bd7b-124">Una nuova funzione di gestione del carico in entrata, *Entrata in eccesso di quantità di carico*, risolve questo problema.</span><span class="sxs-lookup"><span data-stu-id="3bd7b-124">A new inbound load handling feature, *Over receipt of load quantities*, fixes this issue.</span></span> <span data-ttu-id="3bd7b-125">Per attivare questa funzionalità andare in [Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) per attivare le seguenti funzionalità (in questo ordine):</span><span class="sxs-lookup"><span data-stu-id="3bd7b-125">To turn on this feature, go to [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), and turn on the following features (in the order that they are listed in):</span></span>

1. <span data-ttu-id="3bd7b-126">Associa operazioni di magazzino ordine fornitore con carico</span><span class="sxs-lookup"><span data-stu-id="3bd7b-126">Associate purchase order inventory transactions with load</span></span>
1. <span data-ttu-id="3bd7b-127">Entrata in eccesso di quantità di carico</span><span class="sxs-lookup"><span data-stu-id="3bd7b-127">Over receipt of load quantities</span></span>

<span data-ttu-id="3bd7b-128">Per ulteriori informazioni, vedere [Registrare le quantità di prodotto registrate rispetto a ordini fornitore](inbound-load-handling.md#post-registered-quantities).</span><span class="sxs-lookup"><span data-stu-id="3bd7b-128">For more information, see [Post registered product quantities against purchase orders](inbound-load-handling.md#post-registered-quantities).</span></span>
