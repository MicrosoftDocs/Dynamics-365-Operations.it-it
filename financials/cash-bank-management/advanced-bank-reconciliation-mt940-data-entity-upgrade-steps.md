---
title: "Importazione MT940 riconciliazione estratti conto avanzata - Aggiornamento entità di dati compositi"
description: "Un numero progressivo deve essere aggiunto all'entità importazione rendiconto bancario per supportare il formato MT940."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User, Developer
ms.reviewer: twheeloc
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 221594
ms.assetid: dddc99ae-56ae-48df-856a-131079c17dcb
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: 08c38aada355583c5a6872f75b57db95d9b81786
ms.openlocfilehash: 0fb86cd4264d5420c479e14f7eed41e480c88b63
ms.contentlocale: it-it
ms.lasthandoff: 07/18/2017

---

# <a name="advanced-bank-reconciliation-mt940-import--composite-data-entity-upgrade"></a><span data-ttu-id="a770f-103">Importazione MT940 riconciliazione estratti conto avanzata - Aggiornamento entità di dati compositi</span><span class="sxs-lookup"><span data-stu-id="a770f-103">Advanced bank reconciliation MT940 Import – Composite data entity upgrade</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="a770f-104">Un numero progressivo deve essere aggiunto all'entità importazione rendiconto bancario per supportare il formato MT940.</span><span class="sxs-lookup"><span data-stu-id="a770f-104">A sequence number needs to be added to the bank statement import entity to support the MT940 format.</span></span> 

<span data-ttu-id="a770f-105">Effettuare le seguenti operazioni per aggiungere l'entità importazione rendiconto bancario per supportare il formato MT940.</span><span class="sxs-lookup"><span data-stu-id="a770f-105">Use the following steps to add the bank statement import entity to support the MT940 format.</span></span>

1.  <span data-ttu-id="a770f-106">Compilare e sincronizzare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="a770f-106">Compile and synchronize the following:</span></span>
    -   <span data-ttu-id="a770f-107">Entità composta\\BankStatementImportEntity</span><span class="sxs-lookup"><span data-stu-id="a770f-107">Composite Entity\\BankStatementImportEntity</span></span>
    -   <span data-ttu-id="a770f-108">Entità\\BankStatementBalanceEntity</span><span class="sxs-lookup"><span data-stu-id="a770f-108">Entity\\BankStatementBalanceEntity</span></span>
    -   <span data-ttu-id="a770f-109">Entità\\BankStatementDocumentEntity</span><span class="sxs-lookup"><span data-stu-id="a770f-109">Entity\\BankStatementDocumentEntity</span></span>
    -   <span data-ttu-id="a770f-110">Entità\\BankStatementEntity</span><span class="sxs-lookup"><span data-stu-id="a770f-110">Entity\\BankStatementEntity</span></span>
    -   <span data-ttu-id="a770f-111">Entità\\BankStatementLineEntity</span><span class="sxs-lookup"><span data-stu-id="a770f-111">Entity\\BankStatementLineEntity</span></span>
    -   <span data-ttu-id="a770f-112">Tabelle\\BankStatementStaging</span><span class="sxs-lookup"><span data-stu-id="a770f-112">Tables\\BankStatementStaging</span></span>

2.  <span data-ttu-id="a770f-113">Gestione dati\\Progetti dati.</span><span class="sxs-lookup"><span data-stu-id="a770f-113">Data management\\data projects.</span></span>
    1.  <span data-ttu-id="a770f-114">Caricare i progetti di importazione MT940</span><span class="sxs-lookup"><span data-stu-id="a770f-114">Load MT940 import project(s)</span></span>
        1.  <span data-ttu-id="a770f-115">Modificare XSLT.</span><span class="sxs-lookup"><span data-stu-id="a770f-115">Change XSLT.</span></span>
            -   <span data-ttu-id="a770f-116">Fare clic su **Visualizza mapping**.</span><span class="sxs-lookup"><span data-stu-id="a770f-116">Click **View map**.</span></span>
            -   <span data-ttu-id="a770f-117">Fare clic su **Visualizza mapping** sul documento di rendiconto bancario.</span><span class="sxs-lookup"><span data-stu-id="a770f-117">Click **View map** on the bank statement document.</span></span>
            -   <span data-ttu-id="a770f-118">Fare clic su **Trasformazioni**</span><span class="sxs-lookup"><span data-stu-id="a770f-118">Click **Transformations**</span></span>
            -   <span data-ttu-id="a770f-119">Eliminare il file BankReconiliation-to-Composite.xslt.</span><span class="sxs-lookup"><span data-stu-id="a770f-119">Delete the BankReconiliation-to-Composite.xslt file.</span></span>
            -   <span data-ttu-id="a770f-120">Aggiungere la nuova versione di BankReconiliation-to-Composite.xsl.</span><span class="sxs-lookup"><span data-stu-id="a770f-120">Add the new version of BankReconiliation-to-Composite.xsl.</span></span>

        2.  <span data-ttu-id="a770f-121">Esporre **Numero progressivo** sul layout **Dati di origine**.</span><span class="sxs-lookup"><span data-stu-id="a770f-121">Expose the **Sequence Number** on **Source Data** layout.</span></span>
            1.  <span data-ttu-id="a770f-122">Formato dati di origine = Elemento XML.</span><span class="sxs-lookup"><span data-stu-id="a770f-122">Source data format = XML-Element.</span></span>
            2.  <span data-ttu-id="a770f-123">Nome entità = Rendiconti bancari.</span><span class="sxs-lookup"><span data-stu-id="a770f-123">Entity name = Bank statements.</span></span>
            3.  <span data-ttu-id="a770f-124">Caricare il file di dati = nuova versione SampleBankCompositeEntity.xml.</span><span class="sxs-lookup"><span data-stu-id="a770f-124">Upload data file = new version SampleBankCompositeEntity.xml.</span></span>
            4.  <span data-ttu-id="a770f-125">Fare clic su **Sì** per sovrascrivere il file esistente.</span><span class="sxs-lookup"><span data-stu-id="a770f-125">Click **Yes** to overwrite the existing file.</span></span>
            5.  <span data-ttu-id="a770f-126">Fare clic su **Sì** per generare un nuovo mapping.</span><span class="sxs-lookup"><span data-stu-id="a770f-126">Click **Yes** to generate a new mapping.</span></span>
            6.  <span data-ttu-id="a770f-127">Verificare che S**equenceNumber** sia stato mappato.</span><span class="sxs-lookup"><span data-stu-id="a770f-127">Verify that S**equenceNumber** is mapped.</span></span>
                -   <span data-ttu-id="a770f-128">Fare clic su **Visualizza mapping** sull'entità rendiconto.</span><span class="sxs-lookup"><span data-stu-id="a770f-128">Click **View Map** on the statement entity.</span></span>
                -   <span data-ttu-id="a770f-129">Verificare che **SequenceNumber** sia mappato da Origine a Gestione temporanea.</span><span class="sxs-lookup"><span data-stu-id="a770f-129">Verify that **SequenceNumber** is mapped from Source to Staging.</span></span>

3.  <span data-ttu-id="a770f-130">Importare il nuovo rendiconto.</span><span class="sxs-lookup"><span data-stu-id="a770f-130">Import the new statement.</span></span>





