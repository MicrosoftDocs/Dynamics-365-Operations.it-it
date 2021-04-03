---
title: Automazione del processo
description: Questo argomento fornisce dettagli su come l'automazione dei processi consente una semplice pianificazione dei processi che verranno eseguiti dal server batch.
author: RyanCCarlson2
manager: tonyafehr
ms.date: 08/12/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ProcessScheduleSeries
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: rcarlson
ms.search.validFrom: 2020-06-30
ms.dyn365.ops.version: AX 10.0.11
ms.openlocfilehash: e3babed18caefff16105f70a0b15b8b8cf0f08eb
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2021
ms.locfileid: "5568212"
---
# <a name="process-automation"></a><span data-ttu-id="41b1a-103">Automazione del processo</span><span class="sxs-lookup"><span data-stu-id="41b1a-103">Process automation</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="41b1a-104">L'automazione dei processi consente una semplice pianificazione dei processi che verranno eseguiti dal server batch.</span><span class="sxs-lookup"><span data-stu-id="41b1a-104">Process automation allows simple scheduling of processes that will be run by the batch server.</span></span> <span data-ttu-id="41b1a-105">La visualizzazione calendario aggiornata del lavoro pianificato consente agli utenti finali di visualizzare e agire sul lavoro programmato e completato.</span><span class="sxs-lookup"><span data-stu-id="41b1a-105">The updated calendar view of the scheduled work allows end users to view and take action on scheduled and completed work.</span></span>

## <a name="administration"></a><span data-ttu-id="41b1a-106">Amministrazione sistema</span><span class="sxs-lookup"><span data-stu-id="41b1a-106">Administration</span></span>

<span data-ttu-id="41b1a-107">La pagina di amministrazione centrale per tutte le automazioni di processo si trova nel modulo Amministrazione di sistema nel menu **Impostazione**.</span><span class="sxs-lookup"><span data-stu-id="41b1a-107">The central administration page for all process automations is found in the System Administration module under the **Setup** menu.</span></span> <span data-ttu-id="41b1a-108">Questa pagina elencherà tutti i processi automatizzati (serie) impostati nel sistema.</span><span class="sxs-lookup"><span data-stu-id="41b1a-108">This page will list all automated processes (series) that are set up in the system.</span></span> <span data-ttu-id="41b1a-109">Consentirà anche di aggiungere nuove automazioni di processo direttamente da questa pagina.</span><span class="sxs-lookup"><span data-stu-id="41b1a-109">It will also allow you to add new process automations directly from this page.</span></span> <span data-ttu-id="41b1a-110">Dopo aver impostato una serie, è possibile gestire ogni serie da questo elenco.</span><span class="sxs-lookup"><span data-stu-id="41b1a-110">After a series is set up, you can manage each series from this list.</span></span> <span data-ttu-id="41b1a-111">È possibile scegliere di modificare l'intera serie, eliminarla, visualizzare tutte le occorrenze in una vista elenco o disabilitare la serie se si desidera sospendere il lavoro pianificato per un periodo di tempo.</span><span class="sxs-lookup"><span data-stu-id="41b1a-111">You can choose to edit the entire series, delete it, view all occurrences in a list view, or disable the series if you would like to pause the scheduled work for a while.</span></span> 

<span data-ttu-id="41b1a-112">Tutti i processi disabilitati nella gestione delle funzionalità non verranno visualizzati quando la funzionalità è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="41b1a-112">Any processes that are disabled in feature management won't show when the feature is disabled.</span></span> <span data-ttu-id="41b1a-113">Inoltre, il motore di pianificazione dell'automazione dei processi non pianificherà alcuna occorrenza o processo in background per una funzione disabilitata.</span><span class="sxs-lookup"><span data-stu-id="41b1a-113">Additionally, the process automation scheduling engine won't schedule any occurrences or background processes for a disabled feature.</span></span> <span data-ttu-id="41b1a-114">La riattivazione della funzione provocherà l'esecuzione immediata di eventuali ricorrenze pianificate o processi in background precedenti.</span><span class="sxs-lookup"><span data-stu-id="41b1a-114">Re-enabling the feature will cause any scheduled occurrences or background processes in the past to run immediately.</span></span>

## <a name="calendar-view"></a><span data-ttu-id="41b1a-115">Visualizzazione calendario</span><span class="sxs-lookup"><span data-stu-id="41b1a-115">Calendar view</span></span>

<span data-ttu-id="41b1a-116">Uno dei principali vantaggi dell'automazione di processo è la capacità di vedere il lavoro pianificato in una semplice vista del calendario.</span><span class="sxs-lookup"><span data-stu-id="41b1a-116">One of the key benefits of process automation is the ability to see the scheduled work in a simple calendar view.</span></span>  <span data-ttu-id="41b1a-117">Questa vista ti consente di vedere il lavoro per una settimana alla volta.</span><span class="sxs-lookup"><span data-stu-id="41b1a-117">This view allows you to see work for a week at a time.</span></span> <span data-ttu-id="41b1a-118">Vedrai questa vista sul lato destro della pagina **Automazione processo**.</span><span class="sxs-lookup"><span data-stu-id="41b1a-118">You'll see this view on the right side of the **Process automation** page.</span></span> <span data-ttu-id="41b1a-119">Verrà popolata con il lavoro pianificato per le serie selezionate.</span><span class="sxs-lookup"><span data-stu-id="41b1a-119">It will be populated with the scheduled work for the selected series.</span></span> 

<span data-ttu-id="41b1a-120">[![Calendario di automazione del processo](./media/CalendarView2.png)](./media/CalendarView2.png)</span><span class="sxs-lookup"><span data-stu-id="41b1a-120">[![Process automation calendar](./media/CalendarView2.png)](./media/CalendarView2.png)</span></span>

## <a name="occurrence-changes"></a><span data-ttu-id="41b1a-121">Modifiche alle occorrenze</span><span class="sxs-lookup"><span data-stu-id="41b1a-121">Occurrence changes</span></span>

<span data-ttu-id="41b1a-122">Ogni occorrenza può essere modificata senza influire su altre occorrenze definite dalle serie che le hanno originate.</span><span class="sxs-lookup"><span data-stu-id="41b1a-122">Each occurrence can be modified without impacting other occurrences defined by the series that originated them.</span></span> <span data-ttu-id="41b1a-123">Le occorrenze di lavoro pianificato possono essere modificate dalla vista del calendario selezionando il pulsante **Visualizza/Modifica** e selezionando **Occorrenza**.</span><span class="sxs-lookup"><span data-stu-id="41b1a-123">Occurrences of scheduled work can be edited from the calendar view by selecting the **View/Edit** button and selecting **Occurrence**.</span></span> <span data-ttu-id="41b1a-124">Questa pagina consente di accedere a tutte le impostazioni originariamente mostrate nella procedura guidata di configurazione della serie e offre la possibilità di apportare una modifica una tantum per l'occorrenza selezionata.</span><span class="sxs-lookup"><span data-stu-id="41b1a-124">This page allows you access to all the settings originally shown in the series setup wizard and provides the ability to make a one-off change for the selected occurrence.</span></span> <span data-ttu-id="41b1a-125">Un'occorrenza di lavoro pianificato può anche essere disattivata selezionando il pulsante **Disabilita** dalla vista del calendario.</span><span class="sxs-lookup"><span data-stu-id="41b1a-125">An occurrence of scheduled work can also be turned off by selecting the **Disable** button from the calendar view.</span></span>

## <a name="developer-documentation"></a><span data-ttu-id="41b1a-126">Documentazione sviluppatori</span><span class="sxs-lookup"><span data-stu-id="41b1a-126">Developer documentation</span></span>

<span data-ttu-id="41b1a-127">Il framework di automazione dei processi consente agli sviluppatori di estendere il framework di automazione dei processi.</span><span class="sxs-lookup"><span data-stu-id="41b1a-127">The process automation framework allows developers to extend the process automation framework.</span></span> <span data-ttu-id="41b1a-128">La documentazione relativa al [framework di automazione dei processi](../process-automation/process-automation-framework.md) fornisce informazioni su come è possibile creare processi personalizzati che devono essere eseguiti dal server batch pianificato con la procedura guidata di automazione dei processi e visualizzati automaticamente nella vista del calendario.</span><span class="sxs-lookup"><span data-stu-id="41b1a-128">The [Process automation framework](../process-automation/process-automation-framework.md) documentation provides information about how you can create custom processes that you require to be run by the batch server scheduled with the process automation wizard and appear in the calendar view automatically.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]