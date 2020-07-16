---
title: Automazione del processo
description: Questo argomento fornisce dettagli su come l'automazione dei processi consente una semplice pianificazione dei processi che verranno eseguiti dal server batch.
author: RyanCCarlson2
manager: tonyafehr
ms.date: 06/24/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProcessScheduleSeries
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.scope: Operations, Core
ms.search.region: Global
ms.author: rcarlson
ms.search.validFrom: 2020-06-30
ms.dyn365.ops.version: AX 10.0.11
ms.openlocfilehash: 2ab4e7510ff98b9fbf0223096b905e9de47f52e1
ms.sourcegitcommit: 1833c1e07a32c8ad41e4a1516e78100ae04a2156
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/26/2020
ms.locfileid: "3508187"
---
# <a name="process-automation"></a><span data-ttu-id="af2c2-103">Automazione del processo</span><span class="sxs-lookup"><span data-stu-id="af2c2-103">Process automation</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="af2c2-104">L'automazione dei processi consente una semplice pianificazione dei processi che verranno eseguiti dal server batch.</span><span class="sxs-lookup"><span data-stu-id="af2c2-104">Process automation allows simple scheduling of processes that will be run by the batch server.</span></span> <span data-ttu-id="af2c2-105">La visualizzazione calendario aggiornata del lavoro pianificato consente agli utenti finali di visualizzare e agire sul lavoro programmato e completato.</span><span class="sxs-lookup"><span data-stu-id="af2c2-105">The updated calendar view of the scheduled work allows end users to view and take action on scheduled and completed work.</span></span>

## <a name="administration"></a><span data-ttu-id="af2c2-106">Amministrazione sistema</span><span class="sxs-lookup"><span data-stu-id="af2c2-106">Administration</span></span>

<span data-ttu-id="af2c2-107">La pagina di amministrazione centrale per tutte le automazioni di processo si trova nel modulo Amministrazione di sistema nel menu **Impostazione**.</span><span class="sxs-lookup"><span data-stu-id="af2c2-107">The central administration page for all process automations is found in the System Administration module under the **Setup** menu.</span></span> <span data-ttu-id="af2c2-108">Questa pagina elencherà tutti i processi automatizzati (serie) impostati nel sistema.</span><span class="sxs-lookup"><span data-stu-id="af2c2-108">This page will list all automated processes (series) that are set up in the system.</span></span> <span data-ttu-id="af2c2-109">Consentirà anche di aggiungere nuove automazioni di processo direttamente da questa pagina.</span><span class="sxs-lookup"><span data-stu-id="af2c2-109">It will also allow you to add new process automations directly from this page.</span></span> <span data-ttu-id="af2c2-110">Dopo aver impostato una serie, è possibile gestire ogni serie da questo elenco.</span><span class="sxs-lookup"><span data-stu-id="af2c2-110">After a series is set up, you can manage each series from this list.</span></span> <span data-ttu-id="af2c2-111">È possibile scegliere di modificare l'intera serie, eliminarla, visualizzare tutte le occorrenze in una vista elenco o disabilitare la serie se si desidera sospendere il lavoro pianificato per un periodo di tempo.</span><span class="sxs-lookup"><span data-stu-id="af2c2-111">You can chose to edit the entire series, delete it, view all occurrences in a list view, or disable the series if you would like to pause the scheduled work for a period of time.</span></span> 

## <a name="calendar-view"></a><span data-ttu-id="af2c2-112">Visualizzazione calendario</span><span class="sxs-lookup"><span data-stu-id="af2c2-112">Calendar view</span></span> 
<span data-ttu-id="af2c2-113">Uno dei principali vantaggi dell'automazione di processo è la capacità di vedere il lavoro pianificato in una semplice vista del calendario.</span><span class="sxs-lookup"><span data-stu-id="af2c2-113">One of the key benefits of process automation is the ability to see the scheduled work in a simple calendar view.</span></span>  <span data-ttu-id="af2c2-114">Questa vista ti consente di vedere il lavoro per una settimana alla volta.</span><span class="sxs-lookup"><span data-stu-id="af2c2-114">This view allows you to see work for a week at a time.</span></span> <span data-ttu-id="af2c2-115">Vedrai questa vista sul lato destro della pagina **Automazione processo**.</span><span class="sxs-lookup"><span data-stu-id="af2c2-115">You will see this view on the right side of the **Process automation** page.</span></span> <span data-ttu-id="af2c2-116">Verrà popolata con il lavoro pianificato per le serie selezionate.</span><span class="sxs-lookup"><span data-stu-id="af2c2-116">It will be populated with the scheduled work for the selected series.</span></span> 

<span data-ttu-id="af2c2-117">[![Calendario di automazione del processo](./media/CalendarView2.png)](./media/CalendarView2.png)</span><span class="sxs-lookup"><span data-stu-id="af2c2-117">[![Process automation calendar](./media/CalendarView2.png)](./media/CalendarView2.png)</span></span>

## <a name="occurrence-changes"></a><span data-ttu-id="af2c2-118">Modifiche alle occorrenze</span><span class="sxs-lookup"><span data-stu-id="af2c2-118">Occurrence changes</span></span>
<span data-ttu-id="af2c2-119">Ogni occorrenza può essere modificata senza influire su altre occorrenze definite dalle serie che le hanno originate.</span><span class="sxs-lookup"><span data-stu-id="af2c2-119">Each occurrence can be modified without impacting other occurrences defined by the series that originated them.</span></span> <span data-ttu-id="af2c2-120">Le occorrenze di lavoro pianificato possono essere modificate dalla vista del calendario selezionando il pulsante **Visualizza/Modifica** e selezionando **Occorrenza**.</span><span class="sxs-lookup"><span data-stu-id="af2c2-120">Occurrences of scheduled work can be edited from the calendar view by selecting the **View/Edit** button and selecting **Occurrence**.</span></span> <span data-ttu-id="af2c2-121">Ciò consente di accedere a tutte le impostazioni originariamente mostrate nella procedura guidata di configurazione della serie e offre la possibilità di apportare una modifica una tantum per l'occorrenza selezionata.</span><span class="sxs-lookup"><span data-stu-id="af2c2-121">This allows you access to all the settings originally shown in the series setup wizard and provides the ability to make a one-off change for the selected occurrence.</span></span> <span data-ttu-id="af2c2-122">Un'occorrenza di lavoro pianificato può anche essere disattivata selezionando il pulsante **Disabilita** dalla vista del calendario.</span><span class="sxs-lookup"><span data-stu-id="af2c2-122">An occurrence of scheduled work can also be turned off by selecting the **Disable** button from the calendar view.</span></span> 

## <a name="developer-documentation"></a><span data-ttu-id="af2c2-123">Documentazione sviluppatori</span><span class="sxs-lookup"><span data-stu-id="af2c2-123">Developer documentation</span></span> 
<span data-ttu-id="af2c2-124">La documentazione per gli sviluppatori è attualmente in fase di scrittura per consentire agli sviluppatori di estendere il framework di automazione dei processi.</span><span class="sxs-lookup"><span data-stu-id="af2c2-124">Developer documentation is currently being written to allow developers to extend the process automation framework.</span></span> <span data-ttu-id="af2c2-125">Questa documentazione fornirà informazioni su come è possibile creare processi personalizzati che devono essere eseguiti dal server batch pianificato con la procedura guidata di automazione dei processi e visualizzati automaticamente nella vista del calendario.</span><span class="sxs-lookup"><span data-stu-id="af2c2-125">This documentation will provide information about how you can create custom processes that you require to be run by the batch server scheduled with the process automation wizard and appear in the calendar view automatically.</span></span>
