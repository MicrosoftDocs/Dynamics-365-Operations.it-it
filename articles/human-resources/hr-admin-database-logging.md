---
title: Configurare e gestire la registrazione del database
description: Puoi tenere traccia delle modifiche a tabelle e campi in Dynamics 365 Human Resources con la registrazione del database.
author: andreabichsel
manager: tfehr
ms.date: 06/10/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2020-06-10
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 8057ebd0bc061c6bf78d8674c45e0885ffce681c
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/17/2021
ms.locfileid: "5467651"
---
# <a name="configure-and-manage-database-logging"></a><span data-ttu-id="e4918-103">Configurare e gestire la registrazione del database</span><span class="sxs-lookup"><span data-stu-id="e4918-103">Configure and manage database logging</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="e4918-104">Puoi tenere traccia delle modifiche a tabelle e campi in Dynamics 365 Human Resources con la registrazione del database.</span><span class="sxs-lookup"><span data-stu-id="e4918-104">You can track changes to tables and fields in Dynamics 365 Human Resources with database logging.</span></span> <span data-ttu-id="e4918-105">In questo argomento viene descritto come:</span><span class="sxs-lookup"><span data-stu-id="e4918-105">This topic describes how to:</span></span>

- <span data-ttu-id="e4918-106">Gestire la sicurezza e le prestazioni per la registrazione del database</span><span class="sxs-lookup"><span data-stu-id="e4918-106">Manage security and performance for database logging</span></span>
- <span data-ttu-id="e4918-107">Imposta la registrazione del database</span><span class="sxs-lookup"><span data-stu-id="e4918-107">Set up database logging</span></span>
- <span data-ttu-id="e4918-108">Pulisci i log del database</span><span class="sxs-lookup"><span data-stu-id="e4918-108">Clean up database logs</span></span>

## <a name="overview-of-database-logging"></a><span data-ttu-id="e4918-109">Panoramica della registrazione del database</span><span class="sxs-lookup"><span data-stu-id="e4918-109">Overview of database logging</span></span>

<span data-ttu-id="e4918-110">La registrazione del database tiene traccia di modifiche specifiche a tabelle e campi in Microsoft Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="e4918-110">Database logging tracks specific changes to Microsoft Dynamics 365 Human Resources tables and fields.</span></span> <span data-ttu-id="e4918-111">Queste modifiche includono l'inserimento, l'aggiornamento o l'eliminazione.</span><span class="sxs-lookup"><span data-stu-id="e4918-111">These changes include inserting, updating, or deleting.</span></span> <span data-ttu-id="e4918-112">La registrazione del database memorizza un record di modifiche a tabelle o campi nella tabella di registro del database.</span><span class="sxs-lookup"><span data-stu-id="e4918-112">Database logging stores a record of changes to tables or fields in the database log table.</span></span>

<span data-ttu-id="e4918-113">Gli usi aziendali della registrazione del database includono:</span><span class="sxs-lookup"><span data-stu-id="e4918-113">The business uses of database logging include:</span></span>

- <span data-ttu-id="e4918-114">Creazione di un record di controllo delle modifiche a tabelle specifiche che contengono informazioni riservate.</span><span class="sxs-lookup"><span data-stu-id="e4918-114">Creating an audit record of changes to specific tables that contain sensitive information.</span></span>
- <span data-ttu-id="e4918-115">Tracciamento di singole transazioni.</span><span class="sxs-lookup"><span data-stu-id="e4918-115">Tracking single transactions.</span></span> <span data-ttu-id="e4918-116">La registrazione del database non è intesa per tenere traccia delle transazioni automatizzate eseguite in processi batch.</span><span class="sxs-lookup"><span data-stu-id="e4918-116">Database logging isn't intended for tracking automated transactions that run in batch jobs.</span></span>

## <a name="security-for-database-logging"></a><span data-ttu-id="e4918-117">Sicurezza per la registrazione del database</span><span class="sxs-lookup"><span data-stu-id="e4918-117">Security for database logging</span></span>

<span data-ttu-id="e4918-118">I registri del database possono contenere dati sensibili.</span><span class="sxs-lookup"><span data-stu-id="e4918-118">Database logs can contain sensitive data.</span></span> <span data-ttu-id="e4918-119">Limita l'accesso per includere solo i ruoli di sicurezza che richiedono l'accesso ai dati del registro.</span><span class="sxs-lookup"><span data-stu-id="e4918-119">Limit access to include only security roles that need access to the log data.</span></span>

## <a name="database-logging-and-performance"></a><span data-ttu-id="e4918-120">Registrazione e prestazioni del database</span><span class="sxs-lookup"><span data-stu-id="e4918-120">Database logging and performance</span></span>

<span data-ttu-id="e4918-121">Sebbene la registrazione nel database possa risultare utile da un punto di vista commerciale, può risultare costosa in termini di utilizzo e gestione delle risorse.</span><span class="sxs-lookup"><span data-stu-id="e4918-121">While valuable from a business perspective, database logging can be expensive in resource use and management.</span></span> <span data-ttu-id="e4918-122">Le implicazioni sulle prestazioni della registrazione del database includono:</span><span class="sxs-lookup"><span data-stu-id="e4918-122">The performance implications of database logging include:</span></span>

- <span data-ttu-id="e4918-123">La tabella dei registri del database può crescere rapidamente e causare un aumento delle dimensioni del database.</span><span class="sxs-lookup"><span data-stu-id="e4918-123">The database log table can grow quickly and cause an increase in the size of the database.</span></span> <span data-ttu-id="e4918-124">La crescita dipende dalla quantità di dati registrati che decidi di conservare.</span><span class="sxs-lookup"><span data-stu-id="e4918-124">Growth depends on the amount of logged data that you decide to keep.</span></span> <span data-ttu-id="e4918-125">Per impostazione predefinita, la tabella di registro del database conserva solo 30 giorni di dati di registro.</span><span class="sxs-lookup"><span data-stu-id="e4918-125">By default, the database log table maintains only 30 days of log data.</span></span> 

- <span data-ttu-id="e4918-126">La registrazione del database può influire negativamente sui processi automatizzati di lunga durata, come le importazioni di dati di lunga durata.</span><span class="sxs-lookup"><span data-stu-id="e4918-126">Database logging can adversely affect long-running automated processes, such as long-running data imports.</span></span>

### <a name="best-practices"></a><span data-ttu-id="e4918-127">Procedure consigliate</span><span class="sxs-lookup"><span data-stu-id="e4918-127">Best practices</span></span>

<span data-ttu-id="e4918-128">Per migliorare le prestazioni, limitare le voci del registro selezionando campi specifici e non intere tabelle.</span><span class="sxs-lookup"><span data-stu-id="e4918-128">To improve performance, limit log entries by selecting specific fields to log instead of whole tables.</span></span> <span data-ttu-id="e4918-129">Per aiutare a mantenere le prestazioni generali, la registrazione del database è limitata a 20 tabelle.</span><span class="sxs-lookup"><span data-stu-id="e4918-129">To help maintain overall performance, database logging is limited to 20 tables.</span></span>

> [!NOTE]
> <span data-ttu-id="e4918-130">In caso di campi singoli, puoi registrare solo gli aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="e4918-130">Only updates can be logged for individual fields.</span></span>

## <a name="set-up-database-logging"></a><span data-ttu-id="e4918-131">Imposta la registrazione del database</span><span class="sxs-lookup"><span data-stu-id="e4918-131">Set up database logging</span></span>

<span data-ttu-id="e4918-132">Puoi anche usare la procedura guidata **Registrazione modifiche database** per impostare la registrazione del database.</span><span class="sxs-lookup"><span data-stu-id="e4918-132">You can use the **Logging database changes** wizard to set up database logging.</span></span> <span data-ttu-id="e4918-133">La procedura guidata fornisce un modo flessibile per impostare la registrazione per tabelle o campi.</span><span class="sxs-lookup"><span data-stu-id="e4918-133">The wizard provides a flexible way to set up logging for tables or fields.</span></span>

1. <span data-ttu-id="e4918-134">Vai ad **Amministrazione sistema> Collegamenti> Database > Impostazione registro database**.</span><span class="sxs-lookup"><span data-stu-id="e4918-134">Go to **System administration > Links > Database > Database log setup**.</span></span> <span data-ttu-id="e4918-135">Seleziona **Nuovo** per avviare la procedura guidata **Registrazione modifiche database**.</span><span class="sxs-lookup"><span data-stu-id="e4918-135">Select **New** to start the **Logging database changes** wizard.</span></span>
2. <span data-ttu-id="e4918-136">Completare la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="e4918-136">Complete the wizard.</span></span>

## <a name="clean-up-database-logs"></a><span data-ttu-id="e4918-137">Pulisci i log del database</span><span class="sxs-lookup"><span data-stu-id="e4918-137">Clean up database logs</span></span>

<span data-ttu-id="e4918-138">Puoi eliminare tutti o parte dei registri del database, utilizzando le seguenti opzioni:</span><span class="sxs-lookup"><span data-stu-id="e4918-138">You can delete all or part of the database logs, using the following options:</span></span>

- <span data-ttu-id="e4918-139">Seleziona tutti i registri per una determinata tabella.</span><span class="sxs-lookup"><span data-stu-id="e4918-139">Select all logs for a particular table.</span></span>
- <span data-ttu-id="e4918-140">Seleziona tipi specifici di registro del database.</span><span class="sxs-lookup"><span data-stu-id="e4918-140">Select specific types of database log.</span></span>
- <span data-ttu-id="e4918-141">Seleziona la data e l'ora in cui è stato creato un registro.</span><span class="sxs-lookup"><span data-stu-id="e4918-141">Select a date and time that a log was created.</span></span>

<span data-ttu-id="e4918-142">Per configurare la pulitura del registro del database, effettua le seguenti operazioni:</span><span class="sxs-lookup"><span data-stu-id="e4918-142">To set up database log cleanup, follow these steps:</span></span> 

1. <span data-ttu-id="e4918-143">Vai ad **Amministrazione sistema> Collegamenti> Database > Registro database**.</span><span class="sxs-lookup"><span data-stu-id="e4918-143">Go to **System administration > Links > Database > Database log**.</span></span> <span data-ttu-id="e4918-144">Seleziona **Pulisci registro**.</span><span class="sxs-lookup"><span data-stu-id="e4918-144">Select **Clean up log**.</span></span>

2. <span data-ttu-id="e4918-145">Scegli un metodo di selezione dei registri da eliminare inserendo una delle seguenti opzioni:</span><span class="sxs-lookup"><span data-stu-id="e4918-145">Choose a method of selecting logs to delete by entering one of the following options:</span></span>

   - <span data-ttu-id="e4918-146">ID tabella</span><span class="sxs-lookup"><span data-stu-id="e4918-146">Table ID</span></span>
   - <span data-ttu-id="e4918-147">Tipo di registro</span><span class="sxs-lookup"><span data-stu-id="e4918-147">Type of log</span></span>
   - <span data-ttu-id="e4918-148">Data e ora creazione</span><span class="sxs-lookup"><span data-stu-id="e4918-148">Created date and time</span></span>

3. <span data-ttu-id="e4918-149">Usa la scheda **Pulitura registro database** per determinare quando eseguire l'attività di pulizia del registro.</span><span class="sxs-lookup"><span data-stu-id="e4918-149">Use the **Database log cleanup** tab to determine when to run the log cleanup task.</span></span> <span data-ttu-id="e4918-150">Per impostazione predefinita, i registri del database sono disponibili per 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="e4918-150">By default, database logs are available for 30 days.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]