---
title: Gestione delle attività in POS
description: Questo argomento descrive la gestione delle attività nelle applicazioni POS di Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
manager: annbe
ms.date: 02/10/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: gmohanv
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Release 10.0.9
ms.openlocfilehash: 889cc90b534de33ccd0e2bea367b2da42b5d72e0
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "5006187"
---
# <a name="task-management-in-pos"></a><span data-ttu-id="58169-103">Gestione delle attività in POS</span><span class="sxs-lookup"><span data-stu-id="58169-103">Task management in POS</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="58169-104">Questo argomento descrive la gestione delle attività nelle applicazioni POS di Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="58169-104">This topic describes task management in the Microsoft Dynamics 365 Commerce point of sale (POS) application.</span></span>

## <a name="overview"></a><span data-ttu-id="58169-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="58169-105">Overview</span></span>

<span data-ttu-id="58169-106">L'applicazione POS di Dynamics 365 Commerce ha funzionalità di gestione delle attività che consente ai responsabili e ai dipendenti del negozio di gestire le attività e aggiornarne lo stato.</span><span class="sxs-lookup"><span data-stu-id="58169-106">The Dynamics 365 Commerce POS application has task management features that let store managers and workers manage tasks and update task status.</span></span> <span data-ttu-id="58169-107">Gli addetti al negozio possono accedere alle attività selezionando il riquadro **Attività** sulla home page del POS o selezionando le notifiche delle attività.</span><span class="sxs-lookup"><span data-stu-id="58169-107">Store workers can access tasks either by selecting the **Tasks** tile on the POS home page or by selecting task notifications.</span></span> <span data-ttu-id="58169-108">Per impostazione predefinita, gli addetti al negozio vengono indirizzati alla scheda **Attività personali** dove possono visualizzare le attività loro assegnate.</span><span class="sxs-lookup"><span data-stu-id="58169-108">By default, store workers are taken to the **My tasks** tab, where they can view the tasks that are assigned to them.</span></span> <span data-ttu-id="58169-109">Tuttavia, possono facilmente passare alle schede **Attività scadute**, **Attività aperte** e **Elenchi di attività**.</span><span class="sxs-lookup"><span data-stu-id="58169-109">However, they can easily switch to the **Overdue tasks**, **Open tasks**, and **Task lists** tabs.</span></span>

## <a name="task-operations-for-store-managers"></a><span data-ttu-id="58169-110">Operazioni di attività per i responsabili punto vendita</span><span class="sxs-lookup"><span data-stu-id="58169-110">Task operations for store managers</span></span>

<span data-ttu-id="58169-111">I responsabili punto vendita possono eseguire le seguenti operazioni di attività nell'applicazione POS utilizzando i pulsanti sulla barra dei comandi:</span><span class="sxs-lookup"><span data-stu-id="58169-111">Store managers can perform the following task operations in the POS application by using the buttons on the command bar:</span></span>

- <span data-ttu-id="58169-112">**Assegna** - Assegnare le attività selezionate a un addetto del negozio.</span><span class="sxs-lookup"><span data-stu-id="58169-112">**Assign** – Assign selected tasks to a store worker.</span></span>
- <span data-ttu-id="58169-113">**Stato attività** - Modifica lo stato delle attività selezionate.</span><span class="sxs-lookup"><span data-stu-id="58169-113">**Task status** – Change the status of selected tasks.</span></span>
- <span data-ttu-id="58169-114">**Filtro** - Per impostazione predefinita vengono visualizzate solo le attività attive.</span><span class="sxs-lookup"><span data-stu-id="58169-114">**Filter** – By default, only active tasks are shown.</span></span> <span data-ttu-id="58169-115">Tuttavia, applicando i filtri, i responsabili possono visualizzare tutte le attività, anche quelle che sono state completate o annullate.</span><span class="sxs-lookup"><span data-stu-id="58169-115">However, by applying filters, managers can view all tasks, even tasks that have been completed or canceled.</span></span>
- <span data-ttu-id="58169-116">**Nuova attività** - Creare un'attività in un elenco di attività esistenti o creare un'attività con unico scopo.</span><span class="sxs-lookup"><span data-stu-id="58169-116">**New task** – Create a task under an existing task list, or create an single-purpose task.</span></span>

<span data-ttu-id="58169-117">Gli addetti al negozio possono eseguire le seguenti operazioni di attività nell'applicazione POS utilizzando i pulsanti sulla barra dei comandi:</span><span class="sxs-lookup"><span data-stu-id="58169-117">Store workers can perform the following task operations in the POS application by using the buttons on the command bar:</span></span>

- <span data-ttu-id="58169-118">**Stato attività** - Modifica lo stato delle attività selezionate.</span><span class="sxs-lookup"><span data-stu-id="58169-118">**Task status** – Change the status of selected tasks.</span></span>
- <span data-ttu-id="58169-119">**Filtro** - Per impostazione predefinita vengono visualizzate solo le attività attive.</span><span class="sxs-lookup"><span data-stu-id="58169-119">**Filter** – By default, only active tasks are shown.</span></span> <span data-ttu-id="58169-120">Tuttavia, applicando i filtri, gli addetti possono visualizzare tutte le attività, anche quelle che sono state completate o annullate.</span><span class="sxs-lookup"><span data-stu-id="58169-120">However, by applying filters, workers can view all tasks, even tasks that have been completed or canceled.</span></span>

<span data-ttu-id="58169-121">La seguente illustrazione mostra la scheda **Attività personali** nell'applicazione POS di Commerce.</span><span class="sxs-lookup"><span data-stu-id="58169-121">The following illustration shows the **My tasks** tab in the Commerce POS application.</span></span>

![Scheda Attività personali nell'applicazione POS di Commerce](media/POS-task-management.png)

<span data-ttu-id="58169-123">La figura di seguito mostra la scheda **Elenchi di attività**.</span><span class="sxs-lookup"><span data-stu-id="58169-123">The following illustration shows the **Task lists** tab.</span></span>

![Scheda elenchi di attività nell'applicazione POS di Commerce](media/POS-task-lists-management.png)

## <a name="additional-resources"></a><span data-ttu-id="58169-125">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="58169-125">Additional resources</span></span>

[<span data-ttu-id="58169-126">Panoramica della gestione attività</span><span class="sxs-lookup"><span data-stu-id="58169-126">Task management overview</span></span>](task-mgmt-overview.md)

[<span data-ttu-id="58169-127">Configurare la gestione delle attività</span><span class="sxs-lookup"><span data-stu-id="58169-127">Configure task management</span></span>](task-mgmt-configure.md)

[<span data-ttu-id="58169-128">Creare elenchi di attività e aggiungere attività</span><span class="sxs-lookup"><span data-stu-id="58169-128">Create task lists and add tasks</span></span>](task-mgmt-create-lists.md)

[<span data-ttu-id="58169-129">Assegnare elenchi di attività a punti vendita o dipendenti</span><span class="sxs-lookup"><span data-stu-id="58169-129">Assign task lists to stores or employees</span></span>](task-mgmt-assign-lists.md)
