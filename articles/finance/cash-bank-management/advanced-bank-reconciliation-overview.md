---
title: Panoramica sulla riconciliazione bancaria avanzata
description: Questo articolo descrive il flusso del processo di riconciliazione estratti conto avanzato. La funzionalità avanzata di riconciliazione estratti conto consente di importare rendiconti bancari che possono essere riconciliati automaticamente nelle transazioni bancarie.
author: panolte
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
ms.author: panolte
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b26b6e1e50e5a9b53ca6b5315de760f5bcec4769
ms.sourcegitcommit: 74b10104338222a945684d841d60ab4b8e570168
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/28/2020
ms.locfileid: "3899399"
---
# <a name="advanced-bank-reconciliation-overview"></a><span data-ttu-id="60d2e-104">Panoramica sulla riconciliazione bancaria avanzata</span><span class="sxs-lookup"><span data-stu-id="60d2e-104">Advanced bank reconciliation overview</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="60d2e-105">Questo articolo descrive il flusso del processo di riconciliazione estratti conto avanzato.</span><span class="sxs-lookup"><span data-stu-id="60d2e-105">This article describes the flow for the advanced bank reconciliation process.</span></span> <span data-ttu-id="60d2e-106">La funzionalità avanzata di riconciliazione estratti conto consente di importare rendiconti bancari che possono essere riconciliati automaticamente nelle transazioni bancarie.</span><span class="sxs-lookup"><span data-stu-id="60d2e-106">The advanced bank reconciliation feature lets you import bank statements that can be automatically reconciled from within bank transactions.</span></span>

<span data-ttu-id="60d2e-107">La funzionalità di riconciliazione bancaria avanzata consente di includere i rendiconti bancari.</span><span class="sxs-lookup"><span data-stu-id="60d2e-107">The advanced bank reconciliation feature lets you import bank statements.</span></span> <span data-ttu-id="60d2e-108">Il rendiconto bancario importato può automaticamente essere riconciliato dalle transazioni bancarie.</span><span class="sxs-lookup"><span data-stu-id="60d2e-108">The imported bank statement can then be automatically reconciled from within bank transactions.</span></span> <span data-ttu-id="60d2e-109">Di seguito sono riportati i passaggi del flusso di riconciliazione bancaria avanzata.</span><span class="sxs-lookup"><span data-stu-id="60d2e-109">Here are the steps in the advanced bank reconciliation flow.</span></span>

1.  <span data-ttu-id="60d2e-110">Impostare un'importazione dell'estratto conto bancario.</span><span class="sxs-lookup"><span data-stu-id="60d2e-110">Set up a bank statement import.</span></span>
    -   <span data-ttu-id="60d2e-111">Importare i rendiconti bancari tramite il framework dell'entità di dati.</span><span class="sxs-lookup"><span data-stu-id="60d2e-111">Import bank statements through the data entity framework.</span></span>
    -   <span data-ttu-id="60d2e-112">I formati tipici di rendiconto bancario sono incorporati: ISO20022, BAI2 e MT940.</span><span class="sxs-lookup"><span data-stu-id="60d2e-112">Three typical bank statement formats are built in: ISO20022, BAI2, and MT940.</span></span>
    -   <span data-ttu-id="60d2e-113">La funzionalità può essere estesa a qualsiasi formato.</span><span class="sxs-lookup"><span data-stu-id="60d2e-113">The functionality can be extended to any format.</span></span>

2.  <span data-ttu-id="60d2e-114">Impostare una sequenza numerica da utilizzare per la riconciliazione bancaria avanzata e definire le regole di abbinamento della riconciliazione estratti conto.</span><span class="sxs-lookup"><span data-stu-id="60d2e-114">Set up a number sequence to use for advanced bank reconciliation, and define the bank reconciliation matching rules.</span></span>
    -   <span data-ttu-id="60d2e-115">Una regola di abbinamento della riconciliazione è un set di criteri utilizzati per filtrare le righe del rendiconto bancario e le righe di transazione bancaria di Microsoft Dynamics 365 Finance durante il processo di riconciliazione.</span><span class="sxs-lookup"><span data-stu-id="60d2e-115">A reconciliation matching rule is a set of criteria that are used to filter bank statement lines and Microsoft Dynamics 365 Finance bank transaction lines during the reconciliation process.</span></span> <span data-ttu-id="60d2e-116">A seconda della procedura aziendale, è possibile impostare più regole di abbinamento per automatizzare e ottimizzare il processo di riconciliazione.</span><span class="sxs-lookup"><span data-stu-id="60d2e-116">Depending on your business practice, you can set up more than one matching rule to automate and optimize your reconciliation process.</span></span>

3.  <span data-ttu-id="60d2e-117">Riconciliare i rendiconti bancari con le transazioni bancarie di Finance.</span><span class="sxs-lookup"><span data-stu-id="60d2e-117">Reconcile bank statements with Finance bank transactions.</span></span>
    -   <span data-ttu-id="60d2e-118">Eseguire la corrispondenza automatica e la creazione dei giornali di registrazione riconciliazione.</span><span class="sxs-lookup"><span data-stu-id="60d2e-118">Perform automatic matching and creation of reconciliation journals.</span></span>
    -   <span data-ttu-id="60d2e-119">Visualizzare i rendiconti bancari e le transazioni bancarie di Finance in modalità affiancata.</span><span class="sxs-lookup"><span data-stu-id="60d2e-119">View bank statements and Finance bank transactions side by side.</span></span>
    -   <span data-ttu-id="60d2e-120">Registrare automaticamente le transazioni bancarie di Finance se vengono visualizzate in un rendiconto bancario ma non nell'app Finance.</span><span class="sxs-lookup"><span data-stu-id="60d2e-120">Automatically post Finance bank transactions if they appear on a bank statement but don't appear in the Finance app.</span></span>
    -   <span data-ttu-id="60d2e-121">Generare un rendiconto riconciliazione.</span><span class="sxs-lookup"><span data-stu-id="60d2e-121">Generate a reconciliation statement.</span></span>





