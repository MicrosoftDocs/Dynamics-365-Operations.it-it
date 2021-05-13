---
title: Verificare la qualità delle merci
description: In questo argomento viene descritto come elaborare ordini di controllo qualità.
author: perlynne
ms.date: 03/23/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: InventQualityOrderTable, InventQualityOrderLineResults, HcmWorkerLookUp
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ec67e7864db12178c0f3cfe8b93d510a46e8a0d4
ms.sourcegitcommit: 8362f3bd32ce8b9a5af93c8e57daef732a93b19e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2021
ms.locfileid: "5956136"
---
# <a name="inspect-the-quality-of-goods"></a><span data-ttu-id="31d9c-103">Verificare la qualità delle merci</span><span class="sxs-lookup"><span data-stu-id="31d9c-103">Inspect the quality of goods</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="31d9c-104">In questo argomento viene descritto come elaborare ordini di controllo qualità.</span><span class="sxs-lookup"><span data-stu-id="31d9c-104">This topic describes how to process quality orders.</span></span> <span data-ttu-id="31d9c-105">Le ispezioni di controllo qualità sono in genere effettuati da un addetto al controllo qualità.</span><span class="sxs-lookup"><span data-stu-id="31d9c-105">Quality inspections are typically done by a quality clerk.</span></span>

<span data-ttu-id="31d9c-106">Se sono installati i dati demo standard, è possibile utilizzarli per completare le procedure in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="31d9c-106">If the standard demo data is installed, you can use it to complete the procedures in this topic.</span></span> <span data-ttu-id="31d9c-107">Per usare i dati demo, selezionare la persona giuridica *USMF* prima di iniziare.</span><span class="sxs-lookup"><span data-stu-id="31d9c-107">To use the demo data, select the *USMF* legal entity before you begin.</span></span> <span data-ttu-id="31d9c-108">È quindi necessario confermare l'ordine fornitore *000016* e registrare una entrata prodotti.</span><span class="sxs-lookup"><span data-stu-id="31d9c-108">You must then confirm purchase order *000016* and post a product receipt.</span></span> <span data-ttu-id="31d9c-109">Viene generato automaticamente un ordine di controllo qualità.</span><span class="sxs-lookup"><span data-stu-id="31d9c-109">A quality order is automatically generated.</span></span>

## <a name="step-1-select-a-quality-order"></a><span data-ttu-id="31d9c-110">Passaggio 1: Selezionare un ordine di controllo qualità.</span><span class="sxs-lookup"><span data-stu-id="31d9c-110">Step 1: Select a quality order</span></span>

<span data-ttu-id="31d9c-111">Per selezionare un ordine di controllo qualità, attieniti alla procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="31d9c-111">To select a quality order, follow these steps.</span></span>

1. <span data-ttu-id="31d9c-112">Andare a **Gestione inventario \> Attività periodiche \> Gestione qualità \> Ordini di controllo qualità**.</span><span class="sxs-lookup"><span data-stu-id="31d9c-112">Go to **Inventory management \> Periodic tasks \> Quality management \> Quality orders**.</span></span>
1. <span data-ttu-id="31d9c-113">Selezionare l'ordine di controllo qualità generato prima di aver avviato questa procedura.</span><span class="sxs-lookup"><span data-stu-id="31d9c-113">Select the quality order that was generated before you started this procedure.</span></span>

## <a name="step-2-record-test-results"></a><span data-ttu-id="31d9c-114">Passaggio 2: Registrazione dei risultati dei test</span><span class="sxs-lookup"><span data-stu-id="31d9c-114">Step 2: Record test results</span></span>

<span data-ttu-id="31d9c-115">Per registrare i risultati dei test, eseguire i passaggi indicati di seguito:</span><span class="sxs-lookup"><span data-stu-id="31d9c-115">To record test results, follow these steps.</span></span>

1. <span data-ttu-id="31d9c-116">Seleziona **Risultati**.</span><span class="sxs-lookup"><span data-stu-id="31d9c-116">Select **Results**.</span></span>
1. <span data-ttu-id="31d9c-117">Seleziona **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="31d9c-117">Select **Edit**.</span></span>
1. <span data-ttu-id="31d9c-118">Nel campo **Quantità risultante** immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="31d9c-118">In the **Result quantity** field, enter a number.</span></span>
1. <span data-ttu-id="31d9c-119">Nel campo **Risultato**, selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="31d9c-119">In the **Outcome** field, select the desired record.</span></span> <span data-ttu-id="31d9c-120">In questo esempio il risultato è basato su un risultato predefinito.</span><span class="sxs-lookup"><span data-stu-id="31d9c-120">In this example, the result is based on a predefined outcome.</span></span> <span data-ttu-id="31d9c-121">In genere viene registrato un risultato del test più specifico, ad esempio una dimensione o un altro valore simile.</span><span class="sxs-lookup"><span data-stu-id="31d9c-121">Usually, you will record a more specific test result, such as a size or other dimension.</span></span>
1. <span data-ttu-id="31d9c-122">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="31d9c-122">Select **Save**.</span></span>
1. <span data-ttu-id="31d9c-123">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="31d9c-123">Close the page.</span></span>

## <a name="step-3-validate-the-quality-order"></a><span data-ttu-id="31d9c-124">Passaggio 3: Convalida l'ordine di controllo qualità</span><span class="sxs-lookup"><span data-stu-id="31d9c-124">Step 3: Validate the quality order</span></span>

<span data-ttu-id="31d9c-125">Per convalidare l'ordine di controllo qualità, attieniti alla procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="31d9c-125">To validate the quality order, follow these steps.</span></span>

1. <span data-ttu-id="31d9c-126">Selezionare **Convalida**.</span><span class="sxs-lookup"><span data-stu-id="31d9c-126">Select **Validate**.</span></span>
1. <span data-ttu-id="31d9c-127">Nel campo **Convalidato da** selezionare l'utente che sta effettuando l'ispezione.</span><span class="sxs-lookup"><span data-stu-id="31d9c-127">In the **Validated by** field, select the user who is doing the inspection.</span></span>
1. <span data-ttu-id="31d9c-128">Selezionare **Select**.</span><span class="sxs-lookup"><span data-stu-id="31d9c-128">Select **Select**.</span></span>
1. <span data-ttu-id="31d9c-129">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="31d9c-129">Select **OK**.</span></span>
1. <span data-ttu-id="31d9c-130">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="31d9c-130">Close the page.</span></span>

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
