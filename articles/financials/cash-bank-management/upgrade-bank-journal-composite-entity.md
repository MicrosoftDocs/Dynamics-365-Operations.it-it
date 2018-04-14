---
title: "Aggiornare l'entità composta giornale di registrazione bancario"
description: I passaggi seguenti sono necessari per aggiungere il campo BankTransactionType aggiuntivo a BankJournalEntity composta.
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User, Developer
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 221654
ms.assetid: adb8146b-eb21-4be2-a338-a5b299fcc9a0
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 6378e5f960c651e51ccbe696d14530e9e22e783a
ms.contentlocale: it-it
ms.lasthandoff: 04/13/2018

---

# <a name="update-the-bank-journal-composite-entity"></a><span data-ttu-id="cc339-103">Aggiornare l'entità composta giornale di registrazione bancario</span><span class="sxs-lookup"><span data-stu-id="cc339-103">Update the bank journal composite entity</span></span>

[!INCLUDE [banner](../includes/banner.md)]

<span data-ttu-id="cc339-104">I passaggi seguenti sono necessari per aggiungere il campo BankTransactionType aggiuntivo a BankJournalEntity composta.</span><span class="sxs-lookup"><span data-stu-id="cc339-104">The following steps are needed in order to add the additional BankTransactionType field to the composite BankJournalEntity.</span></span>

<span data-ttu-id="cc339-105">Effettuare le seguenti operazioni per aggiungere il campo BankTransactionType aggiuntivo a BankJournalEntity composta.</span><span class="sxs-lookup"><span data-stu-id="cc339-105">Use the following steps to add the additional BankTransactionType field to the composite BankJournalEntity.</span></span>

1.  <span data-ttu-id="cc339-106">Compilare e sincronizzare le entità composte, entità e tabelle di gestione temporanea del giornale di registrazione bancario seguenti:</span><span class="sxs-lookup"><span data-stu-id="cc339-106">Compile and synchronize the following bank journal composite entities, entities, and staging tables:</span></span>
    -   <span data-ttu-id="cc339-107">Entità composta\\BankJournalEntity</span><span class="sxs-lookup"><span data-stu-id="cc339-107">Composite Entity\\BankJournalEntity</span></span>
    -   <span data-ttu-id="cc339-108">Entità\\BankJournalHeaderEntity</span><span class="sxs-lookup"><span data-stu-id="cc339-108">Entity\\BankJournalHeaderEntity</span></span>
    -   <span data-ttu-id="cc339-109">Entità\\BankJournalLineEntity</span><span class="sxs-lookup"><span data-stu-id="cc339-109">Entity\\BankJournalLineEntity</span></span>
    -   <span data-ttu-id="cc339-110">Tabella\\BankJournalHeaderStaging</span><span class="sxs-lookup"><span data-stu-id="cc339-110">Table\\BankJournalHeaderStaging</span></span>
    -   <span data-ttu-id="cc339-111">Tabella\\BankJournalLineStaging</span><span class="sxs-lookup"><span data-stu-id="cc339-111">Table\\BankJournalLineStaging</span></span>

2.  <span data-ttu-id="cc339-112">Gestione dati\\Progetti dati</span><span class="sxs-lookup"><span data-stu-id="cc339-112">Data management\\data projects</span></span>
    -   <span data-ttu-id="cc339-113">Esporre il tipo **Transazione bancaria**sul layout **Dati di origine**.</span><span class="sxs-lookup"><span data-stu-id="cc339-113">Expose the **Bank Transaction** type on **Source Data** layout.</span></span>
        -   <span data-ttu-id="cc339-114">Formato dati di origine = Elemento XML</span><span class="sxs-lookup"><span data-stu-id="cc339-114">Source data format = XML-Element</span></span>
        -   <span data-ttu-id="cc339-115">Nome entità = Giornale di registrazione bancario</span><span class="sxs-lookup"><span data-stu-id="cc339-115">Entity name = Bank Journal</span></span>
        -   <span data-ttu-id="cc339-116">Caricare il file di dati = nuova versione SampleBankJournalCompositeEntity.xml</span><span class="sxs-lookup"><span data-stu-id="cc339-116">Upload data file = new version SampleBankJournalCompositeEntity.xml</span></span>
        -   <span data-ttu-id="cc339-117">Fare clic su **Sì** per sovrascrivere il file esistente.</span><span class="sxs-lookup"><span data-stu-id="cc339-117">Click **Yes** to overwrite the existing file.</span></span>
        -   <span data-ttu-id="cc339-118">Fare clic su **Sì** per generare un mapping completamente nuovo.</span><span class="sxs-lookup"><span data-stu-id="cc339-118">Click **Yes** to generate mapping from scratch.</span></span>
        -   <span data-ttu-id="cc339-119">Verificare che Tipo di transazione bancaria sia mappato.</span><span class="sxs-lookup"><span data-stu-id="cc339-119">Verify that the Bank Transaction Type is mapped.</span></span>
            -   <span data-ttu-id="cc339-120">Fare clic su **Visualizza mapping** sull'entità Riga.</span><span class="sxs-lookup"><span data-stu-id="cc339-120">Click **View map** on Line entity.</span></span>
            -   <span data-ttu-id="cc339-121">Verificare che Tipo di transazione bancaria sia mappato da Origine a Gestione temporanea.</span><span class="sxs-lookup"><span data-stu-id="cc339-121">Verify that Bank Transaction type is mapped from Source to Staging.</span></span>

3.  <span data-ttu-id="cc339-122">Importare il nuovo rendiconto.</span><span class="sxs-lookup"><span data-stu-id="cc339-122">Import the new statement.</span></span>





