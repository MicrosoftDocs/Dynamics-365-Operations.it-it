---
title: Estendere Talent con Power Apps e Power Automate
description: In questo articolo vengono descritti alcuni esempi di scenari di estendibilità per Microsoft Dynamics 365 Human Resources che utilizzano Microsoft Power Apps e Microsoft Power Automate.
author: negudava
manager: Annbe
ms.date: 02/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: Dynamics 365 Human Resources;PowerApps;Flow;Common Data Service
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core;Experience Apps;Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: negudava
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 8d4185b958ed35e9d2bc764db8ea77b3a2f53c37
ms.sourcegitcommit: 13c4a6f98ccce243d6befde90992aefcf562bdab
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "3029867"
---
# <a name="extend-with-power-apps-and-power-automate"></a><span data-ttu-id="998a3-103">Estendere con Power Apps e Power Automate</span><span class="sxs-lookup"><span data-stu-id="998a3-103">Extend with Power Apps and Power Automate</span></span>

<span data-ttu-id="998a3-104">In questo articolo vengono descritti alcuni esempi di scenari di estendibilità per Microsoft Dynamics 365 Human Resources che utilizzano Microsoft Power Apps e Microsoft Power Automate.</span><span class="sxs-lookup"><span data-stu-id="998a3-104">This article describes some examples of extensibility scenarios for Microsoft Dynamics 365 Human Resources that use Microsoft Power Apps and Microsoft Power Automate.</span></span> <span data-ttu-id="998a3-105">È possibile importare il pacchetto di soluzioni associato a ogni esempio nell'ambiente di Power Apps.</span><span class="sxs-lookup"><span data-stu-id="998a3-105">You can import the solution package that is associated with each example into your Power Apps environment.</span></span> <span data-ttu-id="998a3-106">È quindi possibile utilizzare i pacchetti come riferimento o punto di partenza per implementare scenari applicabili all'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="998a3-106">You can then use the packages either as guidance or as starting points to implement scenarios that are applicable to your organization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="998a3-107">Se si desidera utilizzare i modelli e le app descritti in questo argomento "così come sono", testarli per assicurarsi che coprano tutti gli scenari specifici dell'implementazione.</span><span class="sxs-lookup"><span data-stu-id="998a3-107">If you want to use the templates and apps that are described in this topic "as is," be sure to test them to make sure that they cover all the scenarios that are specific to your implementation.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="998a3-108">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="998a3-108">Prerequisites</span></span>

- <span data-ttu-id="998a3-109">Per importare pacchetti, gli utenti devono disporre dell'autorizzazione **Creazione ambiente**.</span><span class="sxs-lookup"><span data-stu-id="998a3-109">To import packages, users must have the **Environment Maker** permission.</span></span>
- <span data-ttu-id="998a3-110">Per esportare o importare app, gli utenti devono disporre di una licenza di Power Apps Piano 2 o una licenza di valutazione di Power Apps Piano 2.</span><span class="sxs-lookup"><span data-stu-id="998a3-110">To export or import apps, users must have a Power Apps Plan 2 license or a Power Apps Plan 2 trial license.</span></span>

## <a name="integration-with-office-365-power-automate"></a><span data-ttu-id="998a3-111">Integrazione con Office 365, Power Automate</span><span class="sxs-lookup"><span data-stu-id="998a3-111">Integration with Office 365, Power Automate</span></span>

<span data-ttu-id="998a3-112">L'app **Integration with Office 365** può essere utilizzata per estrarre informazioni sui team per gli utenti registrati da Microsoft Office 365.</span><span class="sxs-lookup"><span data-stu-id="998a3-112">The **Integration with Office 365** app can be used to extract team information for signed-in users from Microsoft Office 365.</span></span> <span data-ttu-id="998a3-113">Fa riferimento ai lavoratori in Human Resources per estrarre i tipi di identificazione dei dipendenti.</span><span class="sxs-lookup"><span data-stu-id="998a3-113">It references workers in Human Resources to extract employee identification types.</span></span> <span data-ttu-id="998a3-114">I manager possono controllare le date di scadenza dei tipi di ID dipendente.</span><span class="sxs-lookup"><span data-stu-id="998a3-114">Managers can check expiration dates of employee ID types.</span></span> <span data-ttu-id="998a3-115">Possono anche inviare un promemoria via e-mail se il tipo di ID dipendente è in scadenza.</span><span class="sxs-lookup"><span data-stu-id="998a3-115">They can also send an email reminder if the employee ID type is expiring.</span></span> <span data-ttu-id="998a3-116">Power Automate si integra con Power Apps per inviare questo promemoria.</span><span class="sxs-lookup"><span data-stu-id="998a3-116">Power Automate integrates with Power Apps to send this reminder.</span></span> <span data-ttu-id="998a3-117">La conferma verrà rispedita a Power Apps da Power Automate quando viene inviato il promemoria.</span><span class="sxs-lookup"><span data-stu-id="998a3-117">Confirmation will be sent back to Power Apps from Power Automate when the reminder is sent.</span></span> <span data-ttu-id="998a3-118">I tipi di identificazione includono la patente di guida, il passaporto e altre forme di identità accettabili.</span><span class="sxs-lookup"><span data-stu-id="998a3-118">Identification types include driver's license, passport, and other acceptable forms of ID.</span></span>

<span data-ttu-id="998a3-119">È possibile estendere questa app per altri scenari.</span><span class="sxs-lookup"><span data-stu-id="998a3-119">You can extend this app for other scenarios.</span></span> <span data-ttu-id="998a3-120">Ad esempio, è possibile utilizzarla per visualizzare informazioni sulle ferie del team, eventi di calendario e qualsiasi evento specifico del team.</span><span class="sxs-lookup"><span data-stu-id="998a3-120">For example, you can use it to show team vacation information, calendar events, and any team-specific events.</span></span>

<span data-ttu-id="998a3-121">Per scaricare l'app **Integrazione con Office 365, Power Automate**, andare a [Integrazione con Office 365](https://go.microsoft.com/fwlink/?linkid=2081787) nell'Area download Microsoft.</span><span class="sxs-lookup"><span data-stu-id="998a3-121">To download the **Integration with Office 365, Power Automate** app, go to [Integration with Office 365](https://go.microsoft.com/fwlink/?linkid=2081787) on the Microsoft Download Center.</span></span>

## <a name="power-automate--sql-connect-and-execute"></a><span data-ttu-id="998a3-122">Power Automate – Connessione a SQL ed esecuzione</span><span class="sxs-lookup"><span data-stu-id="998a3-122">Power Automate – SQL Connect and execute</span></span>

<span data-ttu-id="998a3-123">Il modello **Power Automate – Connessione a SQL ed esecuzione** esegue la connessione a Microsoft SQL Server e consente l'esecuzione delle query SQL.</span><span class="sxs-lookup"><span data-stu-id="998a3-123">The **Power Automate – SQL Connect and execute** template connects to Microsoft SQL Server and enables SQL queries to be run.</span></span>

<span data-ttu-id="998a3-124">Sebbene questo modello legga e aggiorni le tabelle SQL, è possibile estenderlo e utilizzarlo per altri scenari.</span><span class="sxs-lookup"><span data-stu-id="998a3-124">Although this template reads and updates SQL tables, you can extend it and use it for other scenarios.</span></span> <span data-ttu-id="998a3-125">Ad esempio, per compilare una tabella di gestione temporanea in Common Data Service con record di SQL Server e per sincronizzarla periodicamente utilizzando un push incrementale di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="998a3-125">For example, you can use it to fill a staging table in Common Data Service with records from SQL Server, and to periodically synchronize the staging table by using an incremental push from SQL Server.</span></span>

<span data-ttu-id="998a3-126">Query avanzata è integrata con Flow per abilitare la trasformazione dei dati e il push incrementale.</span><span class="sxs-lookup"><span data-stu-id="998a3-126">Advanced Query is integrated with Flow to enable Data transformation and incremental push.</span></span>

<span data-ttu-id="998a3-127">Per scaricare il modello **Power Automate – Connessione a SQL ed esecuzione**, andare a [Power Automate – Connessione a SQL ed esecuzione](https://go.microsoft.com/fwlink/?linkid=2081789) nell'Area download Microsoft.</span><span class="sxs-lookup"><span data-stu-id="998a3-127">To download the **Power Automate – SQL Connect and execute** template, go to [Power Automate – SQL Connect and execute](https://go.microsoft.com/fwlink/?linkid=2081789) on the Microsoft Download Center.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="998a3-128">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="998a3-128">Additional resources</span></span>

[<span data-ttu-id="998a3-129">Microsoft Power Platform</span><span class="sxs-lookup"><span data-stu-id="998a3-129">The Microsoft Power Platform</span></span>](https://docs.microsoft.com/power-platform/admin/admin-documentation)</br>
[<span data-ttu-id="998a3-130">Migrare app tra tenant e ambienti</span><span class="sxs-lookup"><span data-stu-id="998a3-130">Migrate app between tenants and environments</span></span>](https://docs.microsoft.com/power-platform/admin/environment-and-tenant-migration)