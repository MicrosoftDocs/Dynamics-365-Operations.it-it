---
title: Configurare e gestire la registrazione del database
description: Puoi tenere traccia delle modifiche a tabelle e campi in Dynamics 365 Human Resources con la registrazione del database.
author: andreabichsel
ms.date: 06/10/2020
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: d22ff9f3ce68c81f37840342c795d7d162eb027b
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5801337"
---
# <a name="configure-and-manage-database-logging"></a><span data-ttu-id="2899a-103">Configurare e gestire la registrazione del database</span><span class="sxs-lookup"><span data-stu-id="2899a-103">Configure and manage database logging</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="2899a-104">Puoi tenere traccia delle modifiche a tabelle e campi in Dynamics 365 Human Resources con la registrazione del database.</span><span class="sxs-lookup"><span data-stu-id="2899a-104">You can track changes to tables and fields in Dynamics 365 Human Resources with database logging.</span></span> <span data-ttu-id="2899a-105">In questo argomento viene descritto come:</span><span class="sxs-lookup"><span data-stu-id="2899a-105">This topic describes how to:</span></span>

- <span data-ttu-id="2899a-106">Gestire la sicurezza e le prestazioni per la registrazione del database</span><span class="sxs-lookup"><span data-stu-id="2899a-106">Manage security and performance for database logging</span></span>
- <span data-ttu-id="2899a-107">Imposta la registrazione del database</span><span class="sxs-lookup"><span data-stu-id="2899a-107">Set up database logging</span></span>
- <span data-ttu-id="2899a-108">Pulisci i log del database</span><span class="sxs-lookup"><span data-stu-id="2899a-108">Clean up database logs</span></span>

## <a name="overview-of-database-logging"></a><span data-ttu-id="2899a-109">Panoramica della registrazione del database</span><span class="sxs-lookup"><span data-stu-id="2899a-109">Overview of database logging</span></span>

<span data-ttu-id="2899a-110">La registrazione del database tiene traccia di modifiche specifiche a tabelle e campi in Microsoft Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="2899a-110">Database logging tracks specific changes to Microsoft Dynamics 365 Human Resources tables and fields.</span></span> <span data-ttu-id="2899a-111">Queste modifiche includono l'inserimento, l'aggiornamento o l'eliminazione.</span><span class="sxs-lookup"><span data-stu-id="2899a-111">These changes include inserting, updating, or deleting.</span></span> <span data-ttu-id="2899a-112">La registrazione del database memorizza un record di modifiche a tabelle o campi nella tabella di registro del database.</span><span class="sxs-lookup"><span data-stu-id="2899a-112">Database logging stores a record of changes to tables or fields in the database log table.</span></span>

<span data-ttu-id="2899a-113">Gli usi aziendali della registrazione del database includono:</span><span class="sxs-lookup"><span data-stu-id="2899a-113">The business uses of database logging include:</span></span>

- <span data-ttu-id="2899a-114">Creazione di un record di controllo delle modifiche a tabelle specifiche che contengono informazioni riservate.</span><span class="sxs-lookup"><span data-stu-id="2899a-114">Creating an audit record of changes to specific tables that contain sensitive information.</span></span>
- <span data-ttu-id="2899a-115">Tracciamento di singole transazioni.</span><span class="sxs-lookup"><span data-stu-id="2899a-115">Tracking single transactions.</span></span> <span data-ttu-id="2899a-116">La registrazione del database non è intesa per tenere traccia delle transazioni automatizzate eseguite in processi batch.</span><span class="sxs-lookup"><span data-stu-id="2899a-116">Database logging isn't intended for tracking automated transactions that run in batch jobs.</span></span>

## <a name="security-for-database-logging"></a><span data-ttu-id="2899a-117">Sicurezza per la registrazione del database</span><span class="sxs-lookup"><span data-stu-id="2899a-117">Security for database logging</span></span>

<span data-ttu-id="2899a-118">I registri del database possono contenere dati sensibili.</span><span class="sxs-lookup"><span data-stu-id="2899a-118">Database logs can contain sensitive data.</span></span> <span data-ttu-id="2899a-119">Limita l'accesso per includere solo i ruoli di sicurezza che richiedono l'accesso ai dati del registro.</span><span class="sxs-lookup"><span data-stu-id="2899a-119">Limit access to include only security roles that need access to the log data.</span></span>

## <a name="database-logging-and-performance"></a><span data-ttu-id="2899a-120">Registrazione e prestazioni del database</span><span class="sxs-lookup"><span data-stu-id="2899a-120">Database logging and performance</span></span>

<span data-ttu-id="2899a-121">Sebbene la registrazione nel database possa risultare utile da un punto di vista commerciale, può risultare costosa in termini di utilizzo e gestione delle risorse.</span><span class="sxs-lookup"><span data-stu-id="2899a-121">While valuable from a business perspective, database logging can be expensive in resource use and management.</span></span> <span data-ttu-id="2899a-122">Le implicazioni sulle prestazioni della registrazione del database includono:</span><span class="sxs-lookup"><span data-stu-id="2899a-122">The performance implications of database logging include:</span></span>

- <span data-ttu-id="2899a-123">La tabella dei registri del database può crescere rapidamente e causare un aumento delle dimensioni del database.</span><span class="sxs-lookup"><span data-stu-id="2899a-123">The database log table can grow quickly and cause an increase in the size of the database.</span></span> <span data-ttu-id="2899a-124">La crescita dipende dalla quantità di dati registrati che decidi di conservare.</span><span class="sxs-lookup"><span data-stu-id="2899a-124">Growth depends on the amount of logged data that you decide to keep.</span></span> <span data-ttu-id="2899a-125">Per impostazione predefinita, la tabella di registro del database conserva solo 30 giorni di dati di registro.</span><span class="sxs-lookup"><span data-stu-id="2899a-125">By default, the database log table maintains only 30 days of log data.</span></span> 

- <span data-ttu-id="2899a-126">La registrazione del database può influire negativamente sui processi automatizzati di lunga durata, come le importazioni di dati di lunga durata.</span><span class="sxs-lookup"><span data-stu-id="2899a-126">Database logging can adversely affect long-running automated processes, such as long-running data imports.</span></span>

### <a name="best-practices"></a><span data-ttu-id="2899a-127">Procedure consigliate</span><span class="sxs-lookup"><span data-stu-id="2899a-127">Best practices</span></span>

<span data-ttu-id="2899a-128">Per migliorare le prestazioni, limitare le voci del registro selezionando campi specifici e non intere tabelle.</span><span class="sxs-lookup"><span data-stu-id="2899a-128">To improve performance, limit log entries by selecting specific fields to log instead of whole tables.</span></span> <span data-ttu-id="2899a-129">Per aiutare a mantenere le prestazioni generali, la registrazione del database è limitata a 20 tabelle.</span><span class="sxs-lookup"><span data-stu-id="2899a-129">To help maintain overall performance, database logging is limited to 20 tables.</span></span>

> [!NOTE]
> <span data-ttu-id="2899a-130">In caso di campi singoli, puoi registrare solo gli aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="2899a-130">Only updates can be logged for individual fields.</span></span>

## <a name="set-up-database-logging"></a><span data-ttu-id="2899a-131">Imposta la registrazione del database</span><span class="sxs-lookup"><span data-stu-id="2899a-131">Set up database logging</span></span>

<span data-ttu-id="2899a-132">Puoi anche usare la procedura guidata **Registrazione modifiche database** per impostare la registrazione del database.</span><span class="sxs-lookup"><span data-stu-id="2899a-132">You can use the **Logging database changes** wizard to set up database logging.</span></span> <span data-ttu-id="2899a-133">La procedura guidata fornisce un modo flessibile per impostare la registrazione per tabelle o campi.</span><span class="sxs-lookup"><span data-stu-id="2899a-133">The wizard provides a flexible way to set up logging for tables or fields.</span></span>

1. <span data-ttu-id="2899a-134">Vai ad **Amministrazione sistema> Collegamenti> Database > Impostazione registro database**.</span><span class="sxs-lookup"><span data-stu-id="2899a-134">Go to **System administration > Links > Database > Database log setup**.</span></span> <span data-ttu-id="2899a-135">Seleziona **Nuovo** per avviare la procedura guidata **Registrazione modifiche database**.</span><span class="sxs-lookup"><span data-stu-id="2899a-135">Select **New** to start the **Logging database changes** wizard.</span></span>
2. <span data-ttu-id="2899a-136">Selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="2899a-136">Select **Next**.</span></span> 
3. <span data-ttu-id="2899a-137">Nella pagina **Tabelle e campi** della procedura guidata, seleziona le tabelle e i campi in cui vuoi abilitare la registrazione del database e seleziona **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="2899a-137">On the **Tables and fields** page of the wizard, select the the tables and fields on which you want to enable database logging, and select **Next**.</span></span>

   > [!Note]
   > <span data-ttu-id="2899a-138">La registrazione del database non è disponibile su tutte le tabelle nel database Human Resources</span><span class="sxs-lookup"><span data-stu-id="2899a-138">Database logging is not available on all tables in the Human Resources database.</span></span> <span data-ttu-id="2899a-139">La selezione di **Mostra tutte le tabelle** sotto l'elenco espande l'elenco di tabelle e campi per mostrare tutte le tabelle di database per le quali è disponibile la registrazione del database, ma questo sarà un sottoinsieme dell'elenco completo delle tabelle di database.</span><span class="sxs-lookup"><span data-stu-id="2899a-139">Selecting **Show all tables** below the list expands the list of tables and fields to show all database tables for which database logging is available, but this will be a subset of the full list of database tables.</span></span>

4. <span data-ttu-id="2899a-140">Nella pagina **Tipi di modifica** della procedura guidata, seleziona le operazioni sui dati per le quali vuoi tenere traccia delle modifiche per ciascuna delle tabelle e dei campi, quindi seleziona **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="2899a-140">On the **Types of change** page of the wizard, select the data operations for which you want to track changes for each of the tables and fields, and select **Next**.</span></span> <span data-ttu-id="2899a-141">Vedere la tabella seguente per una descrizione delle operazioni sui dati disponibili per la registrazione.</span><span class="sxs-lookup"><span data-stu-id="2899a-141">See the table below for a description of the data operations that are available for logging.</span></span>
5. <span data-ttu-id="2899a-142">Nella pagina **Fine** rivedi le modifiche che verranno apportate e seleziona **Fine**.</span><span class="sxs-lookup"><span data-stu-id="2899a-142">On the **Finish** page, review the changes that will be made, and select **Finish**.</span></span>

| <span data-ttu-id="2899a-143">Operazione</span><span class="sxs-lookup"><span data-stu-id="2899a-143">Operation</span></span> | <span data-ttu-id="2899a-144">descrizione</span><span class="sxs-lookup"><span data-stu-id="2899a-144">Description</span></span> |
| -- | -- |
| <span data-ttu-id="2899a-145">Tieni traccia delle nuove transazioni</span><span class="sxs-lookup"><span data-stu-id="2899a-145">Track new transactions</span></span> | <span data-ttu-id="2899a-146">Crea un registro per i nuovi record che vengono creati nella tabella.</span><span class="sxs-lookup"><span data-stu-id="2899a-146">Create a log for new records that are created in the table.</span></span> |
| <span data-ttu-id="2899a-147">Aggiornamento</span><span class="sxs-lookup"><span data-stu-id="2899a-147">Update</span></span> | <span data-ttu-id="2899a-148">Creare un registro per gli aggiornamenti ai record della tabella o per gli aggiornamenti ai campi selezionati individualmente nella tabella.</span><span class="sxs-lookup"><span data-stu-id="2899a-148">Create a log for updates to table records, or updates to individually selected fields in the table.</span></span> <span data-ttu-id="2899a-149">Se selezioni di registrare gli aggiornamenti per la tabella, viene creato un record di registro ogni volta che viene effettuato un aggiornamento a qualsiasi campo di qualsiasi record nella tabella.</span><span class="sxs-lookup"><span data-stu-id="2899a-149">If you select to log updates for the table, then a log record is created each time an update is made to any field of any record on the table.</span></span> <span data-ttu-id="2899a-150">Se selezioni di registrare gli aggiornamenti per campi specifici, viene creato un record di registro solo quando vengono effettuati aggiornamenti a quei campi dei record di tabella.</span><span class="sxs-lookup"><span data-stu-id="2899a-150">If you select to log updates for specific fields, then a log record is created only when updates are made to those fields of table records.</span></span> |
| <span data-ttu-id="2899a-151">CANC</span><span class="sxs-lookup"><span data-stu-id="2899a-151">Delete</span></span> | <span data-ttu-id="2899a-152">Crea un registro per i record eliminati dalla tabella.</span><span class="sxs-lookup"><span data-stu-id="2899a-152">Create a log for records deleted from the table.</span></span> |
| <span data-ttu-id="2899a-153">Rinomina chiave</span><span class="sxs-lookup"><span data-stu-id="2899a-153">Rename key</span></span> | <span data-ttu-id="2899a-154">Crea un record di registro quando una chiave di tabella viene rinominata.</span><span class="sxs-lookup"><span data-stu-id="2899a-154">Create a log record when a table key is renamed.</span></span> |


## <a name="clean-up-database-logs"></a><span data-ttu-id="2899a-155">Pulisci i log del database</span><span class="sxs-lookup"><span data-stu-id="2899a-155">Clean up database logs</span></span>

<span data-ttu-id="2899a-156">Puoi eliminare tutti o parte dei registri del database, utilizzando le seguenti opzioni:</span><span class="sxs-lookup"><span data-stu-id="2899a-156">You can delete all or part of the database logs, using the following options:</span></span>

- <span data-ttu-id="2899a-157">Seleziona tutti i registri per una determinata tabella.</span><span class="sxs-lookup"><span data-stu-id="2899a-157">Select all logs for a particular table.</span></span>
- <span data-ttu-id="2899a-158">Seleziona tipi specifici di registro del database.</span><span class="sxs-lookup"><span data-stu-id="2899a-158">Select specific types of database log.</span></span>
- <span data-ttu-id="2899a-159">Seleziona la data e l'ora in cui è stato creato un registro.</span><span class="sxs-lookup"><span data-stu-id="2899a-159">Select a date and time that a log was created.</span></span>

<span data-ttu-id="2899a-160">Per configurare la pulitura del registro del database, effettua le seguenti operazioni:</span><span class="sxs-lookup"><span data-stu-id="2899a-160">To set up database log cleanup, follow these steps:</span></span> 

1. <span data-ttu-id="2899a-161">Vai ad **Amministrazione sistema> Collegamenti> Database > Registro database**.</span><span class="sxs-lookup"><span data-stu-id="2899a-161">Go to **System administration > Links > Database > Database log**.</span></span> <span data-ttu-id="2899a-162">Seleziona **Pulisci registro**.</span><span class="sxs-lookup"><span data-stu-id="2899a-162">Select **Clean up log**.</span></span>

2. <span data-ttu-id="2899a-163">Scegli un metodo di selezione dei registri da eliminare inserendo una delle seguenti opzioni:</span><span class="sxs-lookup"><span data-stu-id="2899a-163">Choose a method of selecting logs to delete by entering one of the following options:</span></span>

   - <span data-ttu-id="2899a-164">ID tabella</span><span class="sxs-lookup"><span data-stu-id="2899a-164">Table ID</span></span>
   - <span data-ttu-id="2899a-165">Tipo di registro</span><span class="sxs-lookup"><span data-stu-id="2899a-165">Type of log</span></span>
   - <span data-ttu-id="2899a-166">Data e ora creazione</span><span class="sxs-lookup"><span data-stu-id="2899a-166">Created date and time</span></span>

3. <span data-ttu-id="2899a-167">Usa la scheda **Pulitura registro database** per determinare quando eseguire l'attività di pulizia del registro.</span><span class="sxs-lookup"><span data-stu-id="2899a-167">Use the **Database log cleanup** tab to determine when to run the log cleanup task.</span></span> <span data-ttu-id="2899a-168">Per impostazione predefinita, i registri del database sono disponibili per 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="2899a-168">By default, database logs are available for 30 days.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
