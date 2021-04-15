---
title: Gestione delle attività in POS
description: Questo argomento descrive la gestione delle attività nelle applicazioni POS di Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 02/10/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: gmohanv
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Release 10.0.9
ms.openlocfilehash: 38ee9db94b3b222e8c0ce5d0883f47bd5d3e7d22
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5796924"
---
# <a name="task-management-in-pos"></a><span data-ttu-id="bf3a9-103">Gestione delle attività in POS</span><span class="sxs-lookup"><span data-stu-id="bf3a9-103">Task management in POS</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="bf3a9-104">Questo argomento descrive la gestione delle attività nelle applicazioni POS di Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="bf3a9-104">This topic describes task management in the Microsoft Dynamics 365 Commerce point of sale (POS) application.</span></span>

<span data-ttu-id="bf3a9-105">L'applicazione POS di Dynamics 365 Commerce ha funzionalità di gestione delle attività che consente ai responsabili e ai dipendenti del negozio di gestire le attività e aggiornarne lo stato.</span><span class="sxs-lookup"><span data-stu-id="bf3a9-105">The Dynamics 365 Commerce POS application has task management features that let store managers and workers manage tasks and update task status.</span></span> <span data-ttu-id="bf3a9-106">Gli addetti al negozio possono accedere alle attività selezionando il riquadro **Attività** sulla home page del POS o selezionando le notifiche delle attività.</span><span class="sxs-lookup"><span data-stu-id="bf3a9-106">Store workers can access tasks either by selecting the **Tasks** tile on the POS home page or by selecting task notifications.</span></span> <span data-ttu-id="bf3a9-107">Per impostazione predefinita, gli addetti al negozio vengono indirizzati alla scheda **Attività personali** dove possono visualizzare le attività loro assegnate.</span><span class="sxs-lookup"><span data-stu-id="bf3a9-107">By default, store workers are taken to the **My tasks** tab, where they can view the tasks that are assigned to them.</span></span> <span data-ttu-id="bf3a9-108">Tuttavia, possono facilmente passare alle schede **Attività scadute**, **Attività aperte** e **Elenchi di attività**.</span><span class="sxs-lookup"><span data-stu-id="bf3a9-108">However, they can easily switch to the **Overdue tasks**, **Open tasks**, and **Task lists** tabs.</span></span>

## <a name="task-operations-for-store-managers"></a><span data-ttu-id="bf3a9-109">Operazioni di attività per i responsabili punto vendita</span><span class="sxs-lookup"><span data-stu-id="bf3a9-109">Task operations for store managers</span></span>

<span data-ttu-id="bf3a9-110">I responsabili punto vendita possono eseguire le seguenti operazioni di attività nell'applicazione POS utilizzando i pulsanti sulla barra dei comandi:</span><span class="sxs-lookup"><span data-stu-id="bf3a9-110">Store managers can perform the following task operations in the POS application by using the buttons on the command bar:</span></span>

- <span data-ttu-id="bf3a9-111">**Assegna** - Assegnare le attività selezionate a un addetto del negozio.</span><span class="sxs-lookup"><span data-stu-id="bf3a9-111">**Assign** – Assign selected tasks to a store worker.</span></span>
- <span data-ttu-id="bf3a9-112">**Stato attività** - Modifica lo stato delle attività selezionate.</span><span class="sxs-lookup"><span data-stu-id="bf3a9-112">**Task status** – Change the status of selected tasks.</span></span>
- <span data-ttu-id="bf3a9-113">**Filtro** - Per impostazione predefinita vengono visualizzate solo le attività attive.</span><span class="sxs-lookup"><span data-stu-id="bf3a9-113">**Filter** – By default, only active tasks are shown.</span></span> <span data-ttu-id="bf3a9-114">Tuttavia, applicando i filtri, i responsabili possono visualizzare tutte le attività, anche quelle che sono state completate o annullate.</span><span class="sxs-lookup"><span data-stu-id="bf3a9-114">However, by applying filters, managers can view all tasks, even tasks that have been completed or canceled.</span></span>
- <span data-ttu-id="bf3a9-115">**Nuova attività** - Creare un'attività in un elenco di attività esistenti o creare un'attività con unico scopo.</span><span class="sxs-lookup"><span data-stu-id="bf3a9-115">**New task** – Create a task under an existing task list, or create an single-purpose task.</span></span>

<span data-ttu-id="bf3a9-116">Gli addetti al negozio possono eseguire le seguenti operazioni di attività nell'applicazione POS utilizzando i pulsanti sulla barra dei comandi:</span><span class="sxs-lookup"><span data-stu-id="bf3a9-116">Store workers can perform the following task operations in the POS application by using the buttons on the command bar:</span></span>

- <span data-ttu-id="bf3a9-117">**Stato attività** - Modifica lo stato delle attività selezionate.</span><span class="sxs-lookup"><span data-stu-id="bf3a9-117">**Task status** – Change the status of selected tasks.</span></span>
- <span data-ttu-id="bf3a9-118">**Filtro** - Per impostazione predefinita vengono visualizzate solo le attività attive.</span><span class="sxs-lookup"><span data-stu-id="bf3a9-118">**Filter** – By default, only active tasks are shown.</span></span> <span data-ttu-id="bf3a9-119">Tuttavia, applicando i filtri, gli addetti possono visualizzare tutte le attività, anche quelle che sono state completate o annullate.</span><span class="sxs-lookup"><span data-stu-id="bf3a9-119">However, by applying filters, workers can view all tasks, even tasks that have been completed or canceled.</span></span>

<span data-ttu-id="bf3a9-120">La seguente illustrazione mostra la scheda **Attività personali** nell'applicazione POS di Commerce.</span><span class="sxs-lookup"><span data-stu-id="bf3a9-120">The following illustration shows the **My tasks** tab in the Commerce POS application.</span></span>

![Scheda Attività personali nell'applicazione POS di Commerce](media/POS-task-management.png)

<span data-ttu-id="bf3a9-122">La figura di seguito mostra la scheda **Elenchi di attività**.</span><span class="sxs-lookup"><span data-stu-id="bf3a9-122">The following illustration shows the **Task lists** tab.</span></span>

![Scheda elenchi di attività nell'applicazione POS di Commerce](media/POS-task-lists-management.png)

## <a name="additional-resources"></a><span data-ttu-id="bf3a9-124">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="bf3a9-124">Additional resources</span></span>

[<span data-ttu-id="bf3a9-125">Panoramica della gestione attività</span><span class="sxs-lookup"><span data-stu-id="bf3a9-125">Task management overview</span></span>](task-mgmt-overview.md)

[<span data-ttu-id="bf3a9-126">Configurare la gestione delle attività</span><span class="sxs-lookup"><span data-stu-id="bf3a9-126">Configure task management</span></span>](task-mgmt-configure.md)

[<span data-ttu-id="bf3a9-127">Creare elenchi di attività e aggiungere attività</span><span class="sxs-lookup"><span data-stu-id="bf3a9-127">Create task lists and add tasks</span></span>](task-mgmt-create-lists.md)

[<span data-ttu-id="bf3a9-128">Assegnare elenchi di attività a punti vendita o dipendenti</span><span class="sxs-lookup"><span data-stu-id="bf3a9-128">Assign task lists to stores or employees</span></span>](task-mgmt-assign-lists.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
