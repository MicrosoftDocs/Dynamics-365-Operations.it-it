---
title: Sincronizzare le capacità risorse
description: Questo argomento fornisce informazioni su come sincronizzare la capacità di una risorsa tra calendari e progetti.
author: Yowelle
manager: AnnBe
ms.date: 09/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjProjectsListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 82022
ms.assetid: bd2fb375-84c6-428a-8e54-f0f719045898
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 27b6fde91a72e37bb2712daba765032322cbd4e9
ms.sourcegitcommit: 241ada0945c72d769eaa70ae35aedbb6a3233fdf
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/02/2020
ms.locfileid: "3760582"
---
# <a name="synchronize-resource-capacity"></a><span data-ttu-id="679d8-103">Sincronizzare le capacità risorse</span><span class="sxs-lookup"><span data-stu-id="679d8-103">Synchronize resource capacity</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="679d8-104">I processi per la sincronizzazione delle risorse garantiscono l'inserimento delle informazioni per il calendario e il calendario di base nella pianificazione delle risorse del progetto.</span><span class="sxs-lookup"><span data-stu-id="679d8-104">The processes for resource synchronization help guarantee that information for the calendar and base calendar trickles down into project resource scheduling.</span></span> <span data-ttu-id="679d8-105">Se il calendario viene modificato, i processi eseguono gli aggiornamenti necessari alla pianificazione delle risorse di progetto.</span><span class="sxs-lookup"><span data-stu-id="679d8-105">If the calendar is changed, the processes make the required updates to the scheduling of project resources.</span></span> <span data-ttu-id="679d8-106">I processi consentono anche di migliorare le prestazioni, poiché le informazioni sulle risorse del calendario vengono sincronizzate in anticipo.</span><span class="sxs-lookup"><span data-stu-id="679d8-106">The processes also help improve performance, because the calendar's resource information is synchronized in advance.</span></span> <span data-ttu-id="679d8-107">Di conseguenza, gli aggiornamenti alle informazioni sulla pianificazione delle risorse si verificano più rapidamente..</span><span class="sxs-lookup"><span data-stu-id="679d8-107">Therefore, updates to resource scheduling information occur more quickly.</span></span> <span data-ttu-id="679d8-108">È consigliabile pianificare i processi come batch e non uno alla volta.</span><span class="sxs-lookup"><span data-stu-id="679d8-108">We recommend that you schedule the processes as a batch instead of one at a time.</span></span> <span data-ttu-id="679d8-109">In caso contrario, esiste il rischio che qualcuno dimentichi le date in cui le informazioni sono state sincronizzate l'ultima volta.</span><span class="sxs-lookup"><span data-stu-id="679d8-109">Otherwise, there is a risk that someone will forget the inclusive dates when the information was last synchronized.</span></span> <span data-ttu-id="679d8-110">Se le date incluse non vengono utilizzate, possono verificarsi dei vuoti durante la sincronizzazione delle date.</span><span class="sxs-lookup"><span data-stu-id="679d8-110">If inclusive dates aren't used, gaps can occur during date synchronization.</span></span>

![Sincronizzazione del calendario](./media/projectresourcing04-1024x471.jpg)

## <a name="synchronize-resource-capacity-roll-ups"></a><span data-ttu-id="679d8-112">Sincronizza rollup capacità risorse</span><span class="sxs-lookup"><span data-stu-id="679d8-112">Synchronize resource capacity roll-ups</span></span>

<span data-ttu-id="679d8-113">Il processo di sincronizzazione è progettato per sincronizzare tutte le informazioni sul calendario delle risorse.</span><span class="sxs-lookup"><span data-stu-id="679d8-113">The synchronization process is designed to synchronize all resource calendar information.</span></span> <span data-ttu-id="679d8-114">Queste informazioni includono le informazioni sul calendario di base su tutte le modifiche alla tabella della capacità del calendario risorse del progetto.</span><span class="sxs-lookup"><span data-stu-id="679d8-114">This information includes base calendar information about any changes to the project's Resource calendar capacity table.</span></span> <span data-ttu-id="679d8-115">Se nuove risorse vengono aggiunte nel progetto, la sincronizzazione garantisce che le informazioni del calendario aggiornate siano disponibili.</span><span class="sxs-lookup"><span data-stu-id="679d8-115">If new resources are added in the project, synchronization helps guarantee that the updated calendar information is available.</span></span> <span data-ttu-id="679d8-116">Questa sincronizzazione può essere eseguita in qualsiasi momento.</span><span class="sxs-lookup"><span data-stu-id="679d8-116">This synchronization can be done at any time.</span></span>

<span data-ttu-id="679d8-117">Si consiglia di utilizzare un batch.</span><span class="sxs-lookup"><span data-stu-id="679d8-117">We recommend that you use a batch.</span></span> <span data-ttu-id="679d8-118">Le opzioni sono disponibili durante la sincronizzazione delle prenotazioni della capacità.</span><span class="sxs-lookup"><span data-stu-id="679d8-118">The options are available during synchronization of capacity reservations.</span></span>

1. <span data-ttu-id="679d8-119">Selezionare **Gestione progetti e contabilità** &gt; **Periodico** &gt; **Sincronizzazione capacità** &gt; **Sincronizza rollup capacità risorse**.</span><span class="sxs-lookup"><span data-stu-id="679d8-119">Select **Project management and accounting** &gt; **Periodic** &gt; **Capacity synchronization** &gt; **Synchronize resources capacity roll-ups**.</span></span>
2. <span data-ttu-id="679d8-120">Impostare le opzioni nella seguente tabella.</span><span class="sxs-lookup"><span data-stu-id="679d8-120">Set the options in the following table.</span></span>

    | <span data-ttu-id="679d8-121">Opzione</span><span class="sxs-lookup"><span data-stu-id="679d8-121">Option</span></span>      | <span data-ttu-id="679d8-122">descrizione</span><span class="sxs-lookup"><span data-stu-id="679d8-122">Description</span></span> |
    |-------------|-------------|
    | <span data-ttu-id="679d8-123">Codice periodo</span><span class="sxs-lookup"><span data-stu-id="679d8-123">Period code</span></span> | <span data-ttu-id="679d8-124">È possibile selezionare il codice intervallo date della contabilità generale per impostare le date di inizio e fine per il processo di sincronizzazione dei roll-up delle capacità delle risorse.</span><span class="sxs-lookup"><span data-stu-id="679d8-124">Optionally select the General ledger date interval code to set the start and end dates for the synchronization process for resource capacity roll-ups.</span></span> |
    | <span data-ttu-id="679d8-125">Data di inizio</span><span class="sxs-lookup"><span data-stu-id="679d8-125">Start date</span></span>  | <span data-ttu-id="679d8-126">Immettere la data di inizio del processo di sincronizzazione per i roll-up delle capacità delle risorse.</span><span class="sxs-lookup"><span data-stu-id="679d8-126">Enter the start date for the synchronization process for resource capacity roll-ups.</span></span> |
    | <span data-ttu-id="679d8-127">Data di fine</span><span class="sxs-lookup"><span data-stu-id="679d8-127">End date</span></span>    | <span data-ttu-id="679d8-128">Immettere la data di fine del processo di sincronizzazione per i roll-up delle capacità delle risorse.</span><span class="sxs-lookup"><span data-stu-id="679d8-128">Enter the end date for the synchronization process for resource capacity roll-ups.</span></span> |

<span data-ttu-id="679d8-129">[![Processo di sincronizzazione](./media/projectresourcing09.jpg)](./media/projectresourcing09.jpg)</span><span class="sxs-lookup"><span data-stu-id="679d8-129">[![Synchronization process](./media/projectresourcing09.jpg)](./media/projectresourcing09.jpg)</span></span>
