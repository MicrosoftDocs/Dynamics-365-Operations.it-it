---
title: Panoramica sulla riconciliazione bancaria avanzata
description: Questo articolo descrive il flusso del processo di riconciliazione estratti conto avanzato. La funzionalità avanzata di riconciliazione estratti conto consente di importare rendiconti bancari che possono essere riconciliati automaticamente nelle transazioni bancarie.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BankReconciliationMatchRule
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 22104
ms.assetid: b0705653-1fa6-4d94-9728-bcf9fb387ad1
ms.search.region: Global
ms.author: leguo
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5c76b38e957c1c76a80c76782f45405573b7f191
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/01/2019
ms.locfileid: "1842616"
---
# <a name="advanced-bank-reconciliation-overview"></a><span data-ttu-id="71b76-104">Panoramica sulla riconciliazione bancaria avanzata</span><span class="sxs-lookup"><span data-stu-id="71b76-104">Advanced bank reconciliation overview</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="71b76-105">Questo articolo descrive il flusso del processo di riconciliazione estratti conto avanzato.</span><span class="sxs-lookup"><span data-stu-id="71b76-105">This article describes the flow for the advanced bank reconciliation process.</span></span> <span data-ttu-id="71b76-106">La funzionalità avanzata di riconciliazione estratti conto consente di importare rendiconti bancari che possono essere riconciliati automaticamente nelle transazioni bancarie.</span><span class="sxs-lookup"><span data-stu-id="71b76-106">The advanced bank reconciliation feature lets you import bank statements that can be automatically reconciled from within bank transactions.</span></span>

<span data-ttu-id="71b76-107">La funzionalità di riconciliazione bancaria avanzata consente di includere i rendiconti bancari.</span><span class="sxs-lookup"><span data-stu-id="71b76-107">The advanced bank reconciliation feature lets you import bank statements.</span></span> <span data-ttu-id="71b76-108">Il rendiconto bancario importato può automaticamente essere riconciliato dalle transazioni bancarie.</span><span class="sxs-lookup"><span data-stu-id="71b76-108">The imported bank statement can then be automatically reconciled from within bank transactions.</span></span> <span data-ttu-id="71b76-109">Di seguito sono riportati i passaggi del flusso di riconciliazione bancaria avanzata.</span><span class="sxs-lookup"><span data-stu-id="71b76-109">Here are the steps in the advanced bank reconciliation flow.</span></span>

1.  <span data-ttu-id="71b76-110">Impostare un'importazione dell'estratto conto bancario.</span><span class="sxs-lookup"><span data-stu-id="71b76-110">Set up a bank statement import.</span></span>
    -   <span data-ttu-id="71b76-111">Importare i rendiconti bancari tramite il framework dell'entità di dati.</span><span class="sxs-lookup"><span data-stu-id="71b76-111">Import bank statements through the data entity framework.</span></span>
    -   <span data-ttu-id="71b76-112">I formati tipici di rendiconto bancario sono incorporati: ISO20022, BAI2 e MT940.</span><span class="sxs-lookup"><span data-stu-id="71b76-112">Three typical bank statement formats are built in: ISO20022, BAI2, and MT940.</span></span>
    -   <span data-ttu-id="71b76-113">La funzionalità può essere estesa a qualsiasi formato.</span><span class="sxs-lookup"><span data-stu-id="71b76-113">The functionality can be extended to any format.</span></span>

2.  <span data-ttu-id="71b76-114">Impostare una sequenza numerica da utilizzare per la riconciliazione bancaria avanzata e definire le regole di abbinamento della riconciliazione estratti conto.</span><span class="sxs-lookup"><span data-stu-id="71b76-114">Set up a number sequence to use for advanced bank reconciliation, and define the bank reconciliation matching rules.</span></span>
    -   <span data-ttu-id="71b76-115">Una regola di abbinamento della riconciliazione è un set di criteri utilizzati per filtrare le righe del rendiconto bancario e le righe di transazione bancaria di Microsoft Dynamics 365 for Finance and Operations durante il processo di riconciliazione.</span><span class="sxs-lookup"><span data-stu-id="71b76-115">A reconciliation matching rule is a set of criteria that are used to filter bank statement lines and Microsoft Dynamics 365 for Finance and Operations bank transaction lines during the reconciliation process.</span></span> <span data-ttu-id="71b76-116">A seconda della procedura aziendale, è possibile impostare più regole di abbinamento per automatizzare e ottimizzare il processo di riconciliazione.</span><span class="sxs-lookup"><span data-stu-id="71b76-116">Depending on your business practice, you can set up more than one matching rule to automate and optimize your reconciliation process.</span></span>

3.  <span data-ttu-id="71b76-117">Riconciliare i rendiconti bancari con le transazioni bancarie di Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="71b76-117">Reconcile bank statements with Finance and Operations bank transactions.</span></span>
    -   <span data-ttu-id="71b76-118">Eseguire la corrispondenza automatica e la creazione dei giornali di registrazione riconciliazione.</span><span class="sxs-lookup"><span data-stu-id="71b76-118">Perform automatic matching and creation of reconciliation journals.</span></span>
    -   <span data-ttu-id="71b76-119">Visualizzare i rendiconti bancari e le transazioni bancarie di Finance and Operations in modalità affiancata.</span><span class="sxs-lookup"><span data-stu-id="71b76-119">View bank statements and Finance and Operations bank transactions side by side.</span></span>
    -   <span data-ttu-id="71b76-120">Registrare automaticamente le transazioni bancarie di Finance and Operations se vengono visualizzate in un rendiconto bancario ma non in Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="71b76-120">Automatically post Finance and Operations bank transactions if they appear on a bank statement but don't appear in Finance and Operations.</span></span>
    -   <span data-ttu-id="71b76-121">Generare un rendiconto riconciliazione.</span><span class="sxs-lookup"><span data-stu-id="71b76-121">Generate a reconciliation statement.</span></span>





