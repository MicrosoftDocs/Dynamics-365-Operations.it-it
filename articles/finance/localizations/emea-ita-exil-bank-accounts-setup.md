---
title: Miglioramento dell'usabilità dei dati bancari
description: Questo argomento spiega come risparmiare tempo e semplificare la registrazione dei dati bancari per clienti e fornitori.
author: ilkond
manager: AnnBe
ms.date: 11/12/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Italy
ms.author: ilyako
ms.search.validFrom: 2019-11-29
ms.dyn365.ops.version: 10.0.7
ms.openlocfilehash: 06a445dbe1d7e4046c0f6ae4564ec4254e339f26
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4962635"
---
# <a name="bank-data-usability-enhancement"></a><span data-ttu-id="9bab9-103">Miglioramento dell'usabilità dei dati bancari</span><span class="sxs-lookup"><span data-stu-id="9bab9-103">Bank data usability enhancement</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9bab9-104">Le aziende spesso devono inserire e conservare una grande quantità di informazioni bancarie.</span><span class="sxs-lookup"><span data-stu-id="9bab9-104">Companies often have to enter and maintain a large amount of banking information.</span></span> <span data-ttu-id="9bab9-105">Il costo dell'inserimento di informazioni bancarie errate può essere molto elevato.</span><span class="sxs-lookup"><span data-stu-id="9bab9-105">The cost of entering incorrect bank information can be very high.</span></span> <span data-ttu-id="9bab9-106">Per risparmiare tempo e semplificare la registrazione dei dati bancari, è possibile importare informazioni bancarie italiane da fonti affidabili.</span><span class="sxs-lookup"><span data-stu-id="9bab9-106">To help save time and simplify bank data registration, you can import Italian bank information from reliable sources.</span></span> <span data-ttu-id="9bab9-107">In questo modo, contribuisci a ridurre il rischio di errori quando vengono utilizzati i dati bancari per clienti e fornitori.</span><span class="sxs-lookup"><span data-stu-id="9bab9-107">In this way, you help reduce the risk of errors when bank data for customers and vendors is used.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="9bab9-108">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="9bab9-108">Prerequisites</span></span>

<span data-ttu-id="9bab9-109">Prima di iniziare, è necessario soddisfare i seguenti prerequisiti:</span><span class="sxs-lookup"><span data-stu-id="9bab9-109">Before you begin, the following prerequisites must be met:</span></span>

- <span data-ttu-id="9bab9-110">L'indirizzo principale della persona giuridica deve essere in Italia.</span><span class="sxs-lookup"><span data-stu-id="9bab9-110">The primary address of the legal entity must be in Italy.</span></span>
- <span data-ttu-id="9bab9-111">La funzionalità **Miglioramento della configurazione del conto bancario** deve essere attivata nell'area di lavoro **Gestione delle funzionalità**.</span><span class="sxs-lookup"><span data-stu-id="9bab9-111">The **Bank account setup enhancement** feature must be turned on in the **Feature management** workspace.</span></span> <span data-ttu-id="9bab9-112">Per ulteriori informazioni, vedere [Panoramica della gestione funzionalità](../../fin-and-ops/get-started/feature-management/feature-management-overview.md).</span><span class="sxs-lookup"><span data-stu-id="9bab9-112">For more information, see [Feature management overview](../../fin-and-ops/get-started/feature-management/feature-management-overview.md).</span></span>

## <a name="import-bank-groups"></a><span data-ttu-id="9bab9-113">Importare gruppi bancari</span><span class="sxs-lookup"><span data-stu-id="9bab9-113">Import bank groups</span></span>

<span data-ttu-id="9bab9-114">È possibile importare l'elenco delle banche utilizzando l'entità **Gruppi bancari** e il framework Gestione dati.</span><span class="sxs-lookup"><span data-stu-id="9bab9-114">You can import the list of banks by using the **Bank groups** entity and the Data management framework.</span></span> <span data-ttu-id="9bab9-115">Per ulteriori informazioni, vedere [Panoramica dei processi di importazione ed esportazione dei dati](../../dev-itpro/data-entities/data-import-export-job.md).</span><span class="sxs-lookup"><span data-stu-id="9bab9-115">For more information, see [Data import and export jobs overview](../../dev-itpro/data-entities/data-import-export-job.md).</span></span>

<span data-ttu-id="9bab9-116">I dati di origine utilizzati per importare i gruppi bancari possono essere presentati come un file di Microsoft Excel con i seguenti nomi di colonna:</span><span class="sxs-lookup"><span data-stu-id="9bab9-116">The source data that is used to import bank groups can be presented as a Microsoft Excel file that has the following column names:</span></span>

- <span data-ttu-id="9bab9-117">BANKGROUPID</span><span class="sxs-lookup"><span data-stu-id="9bab9-117">BANKGROUPID</span></span>
- <span data-ttu-id="9bab9-118">ADDRESSCITY</span><span class="sxs-lookup"><span data-stu-id="9bab9-118">ADDRESSCITY</span></span>
- <span data-ttu-id="9bab9-119">ADDRESSCOUNTRY</span><span class="sxs-lookup"><span data-stu-id="9bab9-119">ADDRESSCOUNTRY</span></span>
- <span data-ttu-id="9bab9-120">ADDRESSCOUNTY</span><span class="sxs-lookup"><span data-stu-id="9bab9-120">ADDRESSCOUNTY</span></span>
- <span data-ttu-id="9bab9-121">ADDRESSDESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9bab9-121">ADDRESSDESCRIPTION</span></span>
- <span data-ttu-id="9bab9-122">ADDRESSDISTRICTNAME</span><span class="sxs-lookup"><span data-stu-id="9bab9-122">ADDRESSDISTRICTNAME</span></span>
- <span data-ttu-id="9bab9-123">ADDRESSLATITUDE</span><span class="sxs-lookup"><span data-stu-id="9bab9-123">ADDRESSLATITUDE</span></span>
- <span data-ttu-id="9bab9-124">ADDRESSLOCATIONID</span><span class="sxs-lookup"><span data-stu-id="9bab9-124">ADDRESSLOCATIONID</span></span>
- <span data-ttu-id="9bab9-125">ADDRESSLONGITUDE</span><span class="sxs-lookup"><span data-stu-id="9bab9-125">ADDRESSLONGITUDE</span></span>
- <span data-ttu-id="9bab9-126">ADDRESSSTATE</span><span class="sxs-lookup"><span data-stu-id="9bab9-126">ADDRESSSTATE</span></span>
- <span data-ttu-id="9bab9-127">ADDRESSSTREET</span><span class="sxs-lookup"><span data-stu-id="9bab9-127">ADDRESSSTREET</span></span>
- <span data-ttu-id="9bab9-128">ADDRESSTIMEZONE</span><span class="sxs-lookup"><span data-stu-id="9bab9-128">ADDRESSTIMEZONE</span></span>
- <span data-ttu-id="9bab9-129">ADDRESSVALIDFROM</span><span class="sxs-lookup"><span data-stu-id="9bab9-129">ADDRESSVALIDFROM</span></span>
- <span data-ttu-id="9bab9-130">ADDRESSVALIDTO</span><span class="sxs-lookup"><span data-stu-id="9bab9-130">ADDRESSVALIDTO</span></span>
- <span data-ttu-id="9bab9-131">ADDRESSZIPCODE</span><span class="sxs-lookup"><span data-stu-id="9bab9-131">ADDRESSZIPCODE</span></span>
- <span data-ttu-id="9bab9-132">NOME</span><span class="sxs-lookup"><span data-stu-id="9bab9-132">NAME</span></span>
- <span data-ttu-id="9bab9-133">ROUTINGNUMBER</span><span class="sxs-lookup"><span data-stu-id="9bab9-133">ROUTINGNUMBER</span></span>
- <span data-ttu-id="9bab9-134">ROUTINGNUMBERTYPE</span><span class="sxs-lookup"><span data-stu-id="9bab9-134">ROUTINGNUMBERTYPE</span></span>
- <span data-ttu-id="9bab9-135">STATEMENTFORMATID</span><span class="sxs-lookup"><span data-stu-id="9bab9-135">STATEMENTFORMATID</span></span>
- <span data-ttu-id="9bab9-136">SUFFIX</span><span class="sxs-lookup"><span data-stu-id="9bab9-136">SUFFIX</span></span>
- <span data-ttu-id="9bab9-137">BRANCHNAME\_IT</span><span class="sxs-lookup"><span data-stu-id="9bab9-137">BRANCHNAME\_IT</span></span>

> [!NOTE]
> <span data-ttu-id="9bab9-138">Il valore **BANKGROUPID** deve corrispondere al valore **ROUTINGNUMBER**.</span><span class="sxs-lookup"><span data-stu-id="9bab9-138">The **BANKGROUPID** value must match the **ROUTINGNUMBER** value.</span></span>

## <a name="use-the-enhanced-list-of-bank-groups"></a><span data-ttu-id="9bab9-139">Utilizzare l'elenco avanzato dei gruppi bancari</span><span class="sxs-lookup"><span data-stu-id="9bab9-139">Use the enhanced list of bank groups</span></span>

<span data-ttu-id="9bab9-140">Quando la funzione di miglioramento della configurazione del conto bancario è attivata, due campi descrittivi aggiuntivi, **Nome filiale** e **Città**, diventano disponibili per gruppi bancari.</span><span class="sxs-lookup"><span data-stu-id="9bab9-140">When the Bank account setup enhancement feature is turned on, two additional descriptive fields, **Branch name** and **City**, become available for bank groups.</span></span>

![Campi Nome filiale e Città](media/emea-ita-exil-bank-pic.jpg)

<span data-ttu-id="9bab9-142">Durante la configurazione di un conto bancario, sono disponibili campi descrittivi aggiuntivi per i gruppi bancari che consentono una selezione più precisa di una banca.</span><span class="sxs-lookup"><span data-stu-id="9bab9-142">During the setup of a bank account, the additional descriptive fields for bank groups are available and allow for more precise selection of a bank.</span></span>

![Campi descrittivi aggiuntivi in una configurazione del conto bancario](media/emea-ita-exil-bank-pic2.jpg)
