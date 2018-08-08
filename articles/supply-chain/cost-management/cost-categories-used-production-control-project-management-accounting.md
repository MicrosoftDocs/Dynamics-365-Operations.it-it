---
title: "Categorie costi utilizzate in Controllo produzione e Gestione progetti e contabilità"
description: "Alcuni tipi di lavori di produzione possono essere utilizzati per le stime del tempo di progetto e per la relativa dichiarazione. Questo articolo fornisce informazioni sulle categorie di costi che è necessario definire per questi tipi di lavoro di produzione ai fini della produzione e del progetto."
author: AndersGirke
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ProjCategory
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 78253
ms.assetid: cfdd58a0-8afa-4a6f-a208-a76e2c162429
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: cab4629740e92f9075b7afc7a5d228b2e01c4664
ms.contentlocale: it-it
ms.lasthandoff: 08/07/2018

---

# <a name="cost-categories-used-in-production-control-and-project-management-accounting"></a><span data-ttu-id="618c2-104">Categorie costi utilizzate in Controllo produzione e Gestione progetti e contabilità</span><span class="sxs-lookup"><span data-stu-id="618c2-104">Cost categories used in Production control and Project management accounting</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="618c2-105">Alcuni tipi di lavori di produzione possono essere utilizzati per le stime del tempo di progetto e per la relativa dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="618c2-105">Some types of production work can apply to project time estimates and reporting.</span></span> <span data-ttu-id="618c2-106">Questo articolo fornisce informazioni sulle categorie di costi che è necessario definire per questi tipi di lavoro di produzione ai fini della produzione e del progetto.</span><span class="sxs-lookup"><span data-stu-id="618c2-106">This article provides information about the cost categories that you must define for these types of production work for production and project purposes.</span></span>

<span data-ttu-id="618c2-107">Alcuni tipi di lavori di produzione possono essere utilizzati per le stime del tempo di progetto e per la relativa dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="618c2-107">Some types of production work can apply to project time estimates and reporting.</span></span> <span data-ttu-id="618c2-108">In questo caso è necessaria una categoria di costi per gli scopi di produzione e progetto.</span><span class="sxs-lookup"><span data-stu-id="618c2-108">In this case, a cost category is required for production and project purposes.</span></span> <span data-ttu-id="618c2-109">Quando una categoria costi viene utilizzata nella produzione e nei progetti, è necessario definire ulteriori informazioni correlate al progetto.</span><span class="sxs-lookup"><span data-stu-id="618c2-109">When a cost category is used in production and projects, additional project-related information must be defined.</span></span> <span data-ttu-id="618c2-110">I costi orario associati ai progetti, ad esempio, possono differire dai costi orario associati alla produzione.</span><span class="sxs-lookup"><span data-stu-id="618c2-110">For example, the hourly costs that are associated with projects can differ from the hourly costs that are associated with production.</span></span> <span data-ttu-id="618c2-111">È possibile utilizzare la pagina **Categorie costi** per definire una categoria di costi utilizzata nella contabilità di controllo produzione e gestione progetti.</span><span class="sxs-lookup"><span data-stu-id="618c2-111">You can use the **Cost categories** page to define a cost category that is used in Production control and Project management accounting.</span></span> 

<span data-ttu-id="618c2-112">**Nota:** la contabilità industriale contiene una pagina **Categorie di progetto**, ma questa pagina non ha alcuna relazione con la funzionalità descritta in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="618c2-112">**Note:** Cost accounting has a **Project categories** page, but this page has no relationship to the functionality that is described in this topic.</span></span> <span data-ttu-id="618c2-113">Quando si utilizza una categoria di costi nei progetti, la pagina **Categorie costi** contiene schede aggiuntive che indicano le informazioni aggiuntive correlate al progetto.</span><span class="sxs-lookup"><span data-stu-id="618c2-113">When you use a cost category in projects, the **Cost categories** page has additional tabs that show additional project-related information.</span></span> <span data-ttu-id="618c2-114">Tali informazioni includono il gruppo di categorie, una proprietà riga e i conti CoGe assegnati alla categoria di costi.</span><span class="sxs-lookup"><span data-stu-id="618c2-114">This information includes the category group, a line property, and ledger accounts that are assigned to the cost category.</span></span>

-   <span data-ttu-id="618c2-115">La categoria di costi deve essere assegnata a un gruppo di categorie che supporta un tipo di transazione **Ore**.</span><span class="sxs-lookup"><span data-stu-id="618c2-115">The cost category must be assigned to a category group that supports a transaction type of **Hours**.</span></span>
-   <span data-ttu-id="618c2-116">La proprietà di riga indica informazioni predefinite su come l'ora dichiarata possa essere addebitata a un progetto.</span><span class="sxs-lookup"><span data-stu-id="618c2-116">The line property indicates default information about how reported time can be charged to a project.</span></span>
-   <span data-ttu-id="618c2-117">In genere, i conti CoGe correlati ai costi e alle vendite vengono definiti per il gruppo di categorie assegnato alla categoria costi, tuttavia è possibile definire conti specifici anche per una singola categoria costi.</span><span class="sxs-lookup"><span data-stu-id="618c2-117">Typically, the ledger accounts that are related to costs and sales are defined for the category group that is assigned to the cost category.</span></span> <span data-ttu-id="618c2-118">È possibile, tuttavia, definire conti specifici per una singola categoria costi.</span><span class="sxs-lookup"><span data-stu-id="618c2-118">However, specific accounts can be defined for an individual cost category.</span></span>

<span data-ttu-id="618c2-119">I pulsanti aggiuntivi nella pagina **Categorie costi** consentono di accedere alle informazioni correlate al progetto relative a una categoria costi selezionata.</span><span class="sxs-lookup"><span data-stu-id="618c2-119">Additional buttons on the **Cost categories** page let you access project-related information about a selected cost category.</span></span> <span data-ttu-id="618c2-120">Ad esempio, è possibile visualizzare le transazioni correlate al progetto, definire dipendenti o progetti, definire costi orari e prezzi di vendita e visualizzare report.</span><span class="sxs-lookup"><span data-stu-id="618c2-120">For example, you can view project-related transactions, define employees or projects, define hourly costs and sales prices, and view reports.</span></span>




