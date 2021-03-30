---
title: Dividere un cespite
description: In questo argomento viene descritto come suddividere una percentuale di un libro cespiti in un nuovo libro cespiti.
author: saraschi2
manager: AnnBe
ms.date: 08/06/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetTable, AssetBook, AssetSplit, AssetBookLookup, LedgerJournalTable, LedgerJournalTransAsset
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: db601be192b57fbec220193d3c9fde1a4f50c085
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5213510"
---
# <a name="split-a-fixed-asset"></a><span data-ttu-id="41b42-103">Dividere un cespite</span><span class="sxs-lookup"><span data-stu-id="41b42-103">Split a fixed asset</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="41b42-104">In questo argomento viene descritto come suddividere una percentuale di un libro cespiti in un nuovo libro cespiti.</span><span class="sxs-lookup"><span data-stu-id="41b42-104">This topic explains how to split a percentage of one asset book to a new asset book.</span></span> <span data-ttu-id="41b42-105">Utilizza il ruolo Ragioniere e i dati dimostrativi USMF.</span><span class="sxs-lookup"><span data-stu-id="41b42-105">It uses the Accountant role and USMF demo data.</span></span>

## <a name="create-a-new-fixed-asset"></a><span data-ttu-id="41b42-106">Crea un nuovo cespite</span><span class="sxs-lookup"><span data-stu-id="41b42-106">Create a new fixed asset</span></span>

1. <span data-ttu-id="41b42-107">Nel pannello di navigazione, passare a **Moduli \> Cespiti \> Cespiti \> Cespiti**.</span><span class="sxs-lookup"><span data-stu-id="41b42-107">In the navigation pane, go to **Modules \> Fixed assets \> Fixed assets \> Fixed assets**.</span></span>
2. <span data-ttu-id="41b42-108">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="41b42-108">Select **New**.</span></span>
3. <span data-ttu-id="41b42-109">Nel campo **Gruppo cespite** immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="41b42-109">In the **Fixed asset group** field, enter or select a value.</span></span> <span data-ttu-id="41b42-110">Si noti il numero cespite da utilizzare successivamente nel processo di divisione.</span><span class="sxs-lookup"><span data-stu-id="41b42-110">Note the fixed asset number to use in the split process later.</span></span>
4. <span data-ttu-id="41b42-111">Nel campo **Nome** immettere un valore.</span><span class="sxs-lookup"><span data-stu-id="41b42-111">In the **Name** field, enter a value.</span></span>
5. <span data-ttu-id="41b42-112">Chiudere il modulo.</span><span class="sxs-lookup"><span data-stu-id="41b42-112">Close the form.</span></span>

## <a name="split-a-fixed-asset"></a><span data-ttu-id="41b42-113">Dividere un cespite</span><span class="sxs-lookup"><span data-stu-id="41b42-113">Split a fixed asset</span></span>

<span data-ttu-id="41b42-114">Prima che un cespite completamente ammortizzato venga suddiviso, lo stato del libro cespiti deve essere modificato manualmente da **Chiuso** in **Aperto**.</span><span class="sxs-lookup"><span data-stu-id="41b42-114">Before a fully depreciated asset is split, the asset book status should be manually changed from **Closed** to **Open**.</span></span> <span data-ttu-id="41b42-115">Questo passaggio è necessario perché lo stato del libro deve essere **Aperto** per registrare le transazioni per l'attività (ad esempio, per una vendita di dismissione).</span><span class="sxs-lookup"><span data-stu-id="41b42-115">This step is required because the book status has to be **Open** if you must post transactions for the asset (for example, for a disposal sale).</span></span> <span data-ttu-id="41b42-116">È inoltre necessario attivare il parametro **Consenti più transazioni in un giustificativo** nella scheda **Generale** della pagina **Parametri di contabilità generale**.</span><span class="sxs-lookup"><span data-stu-id="41b42-116">You must also turn on the **Allow multiple transactions within one voucher** parameter on the **General** tab of the **General ledger parameters** page.</span></span> <span data-ttu-id="41b42-117">Dopo che lo stato del libro cespiti è stato modificato e sono state consentite più transazioni all'interno di un giustificativo, completa i seguenti passaggi per dividere il cespite.</span><span class="sxs-lookup"><span data-stu-id="41b42-117">After the asset book status is changed and multiple transactions within one voucher have been allowed, complete the following steps to split the asset.</span></span>

1. <span data-ttu-id="41b42-118">Nell'elenco, individuare e selezionare il collegamento del cespite da dividere.</span><span class="sxs-lookup"><span data-stu-id="41b42-118">In the list, find and select the link of the fixed asset to split.</span></span>
2. <span data-ttu-id="41b42-119">Selezionare **Libri**.</span><span class="sxs-lookup"><span data-stu-id="41b42-119">Select **Books**.</span></span> <span data-ttu-id="41b42-120">Selezionare il libro per la divisione in base al nuovo cespite.</span><span class="sxs-lookup"><span data-stu-id="41b42-120">Select the book to split to the new asset.</span></span>
3. <span data-ttu-id="41b42-121">Selezionare **Funzioni**.</span><span class="sxs-lookup"><span data-stu-id="41b42-121">Select **Functions**.</span></span>
4. <span data-ttu-id="41b42-122">Selezionare **Dividi cespite**.</span><span class="sxs-lookup"><span data-stu-id="41b42-122">Select **Split fixed asset**.</span></span>
5. <span data-ttu-id="41b42-123">Nel campo **A cespite** immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="41b42-123">In the **To fixed asset** field, enter or select a value.</span></span>
6. <span data-ttu-id="41b42-124">Nel campo **Al libro** selezionare il pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="41b42-124">In the **To book** field, select the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="41b42-125">Nel campo **Data della transazione** immettere una data.</span><span class="sxs-lookup"><span data-stu-id="41b42-125">In the **Transaction date** field, enter a date.</span></span>
8. <span data-ttu-id="41b42-126">Nel campo **Percentuale** immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="41b42-126">In the **Percent** field, enter a number.</span></span>
9. <span data-ttu-id="41b42-127">Nel campo **Nome giornale di registrazione** immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="41b42-127">In the **Journal name** field, enter or select a value.</span></span>
10. <span data-ttu-id="41b42-128">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="41b42-128">Select **OK**.</span></span>

## <a name="post-the-journal-transaction"></a><span data-ttu-id="41b42-129">Registrare la transazione del giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="41b42-129">Post the journal transaction</span></span>

1. <span data-ttu-id="41b42-130">Nel pannello di navigazione, andare a **Moduli \> Cespiti \> Inserimenti nel giornale di registrazione \> Giornale di registrazione cespiti**.</span><span class="sxs-lookup"><span data-stu-id="41b42-130">In the navigation pane, go to **Modules \> Fixed assets \> Journal entries \> Fixed assets journal**.</span></span>
2. <span data-ttu-id="41b42-131">Nell'elenco, selezionare il giornale di registrazione creato con il processo di divisione.</span><span class="sxs-lookup"><span data-stu-id="41b42-131">In the list, select the journal created with the split process.</span></span>
3. <span data-ttu-id="41b42-132">Selezionare **Righe**.</span><span class="sxs-lookup"><span data-stu-id="41b42-132">Select **Lines**.</span></span>

    - <span data-ttu-id="41b42-133">Verificare le righe del giornale di registrazione create.</span><span class="sxs-lookup"><span data-stu-id="41b42-133">Verify the journal lines created.</span></span>
    - <span data-ttu-id="41b42-134">Una transazione di rettifica acquisizione viene creata per il cespite originario per diminuire il valore della percentuale specificata durante il processo di divisione.</span><span class="sxs-lookup"><span data-stu-id="41b42-134">An Acquisition adjustment transaction is created for the original asset to decrease the value by the percentage specified during the split process.</span></span>
    - <span data-ttu-id="41b42-135">Una transazione di acquisizione viene creata per il nuovo cespite per lo stesso importo.</span><span class="sxs-lookup"><span data-stu-id="41b42-135">An Acquisition transaction is created for the new asset for the same amount.</span></span>

4. <span data-ttu-id="41b42-136">Selezionare **Registra**.</span><span class="sxs-lookup"><span data-stu-id="41b42-136">Select **Post**.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]