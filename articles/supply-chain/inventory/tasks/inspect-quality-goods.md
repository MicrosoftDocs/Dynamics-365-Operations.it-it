---
title: Verificare la qualità delle merci
description: In questo argomento viene descritto come elaborare un ordine di controllo qualità.
author: perlynne
manager: AnnBe
ms.date: 08/01/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventQualityOrderTable, InventQualityOrderLineResults, HcmWorkerLookUp
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 10acb9aadfeb11ede1d66dd525ace7b70db3bd1c
ms.sourcegitcommit: fbaccf72df82e6b6927f0c9f0d35af0ca3ecbc2d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/02/2019
ms.locfileid: "1855688"
---
# <a name="inspect-the-quality-of-goods"></a><span data-ttu-id="29587-103">Verificare la qualità delle merci</span><span class="sxs-lookup"><span data-stu-id="29587-103">Inspect the quality of goods</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="29587-104">In questo argomento viene descritto come elaborare un ordine di controllo qualità.</span><span class="sxs-lookup"><span data-stu-id="29587-104">This topic explains how to process a quality order.</span></span> <span data-ttu-id="29587-105">È possibile eseguire questa guida nella società di dati dimostrativi USMF.</span><span class="sxs-lookup"><span data-stu-id="29587-105">You can run this guide in demo data company USMF.</span></span> <span data-ttu-id="29587-106">Prima di iniziare questa procedura di esempio, è necessario confermare l'ordine fornitore "000016" e registrare un'entrata prodotti.</span><span class="sxs-lookup"><span data-stu-id="29587-106">Before you start this example procedure, you need to confirm purchase order “000016” and post a product receipt.</span></span> <span data-ttu-id="29587-107">In questo modo verrà automaticamente creato un ordine di controllo qualità.</span><span class="sxs-lookup"><span data-stu-id="29587-107">This will automatically create a quality order.</span></span> <span data-ttu-id="29587-108">Le ispezioni di controllo qualità sono in genere effettuati da un addetto al controllo qualità.</span><span class="sxs-lookup"><span data-stu-id="29587-108">Quality inspections are typically carried out by a quality clerk.</span></span>


## <a name="select-a-quality-order"></a><span data-ttu-id="29587-109">Selezionare un ordine di controllo qualità.</span><span class="sxs-lookup"><span data-stu-id="29587-109">Select a quality order</span></span>
1. <span data-ttu-id="29587-110">Nel pannello di navigazione andare a **Moduli > Gestione articoli > Attività periodiche > Gestione qualità > Ordini di controllo qualità**.</span><span class="sxs-lookup"><span data-stu-id="29587-110">In the navigation pane, go to **Modules > Inventory management > Periodic tasks > Quality management > Quality orders**.</span></span>
2. <span data-ttu-id="29587-111">Selezionare l'ordine di controllo qualità creato prima di aver avviato questa procedura.</span><span class="sxs-lookup"><span data-stu-id="29587-111">Select the quality order that was created before you started this procedure.</span></span>  

## <a name="record-test-results"></a><span data-ttu-id="29587-112">Registrazione dei risultati dei test</span><span class="sxs-lookup"><span data-stu-id="29587-112">Record test results</span></span>
1. <span data-ttu-id="29587-113">Selezionare **Risultati**.</span><span class="sxs-lookup"><span data-stu-id="29587-113">Select **Results**.</span></span>
2. <span data-ttu-id="29587-114">Selezionare **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="29587-114">Select **Edit**.</span></span>
3. <span data-ttu-id="29587-115">Nel campo **Quantità risultante** immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="29587-115">In the **Result quantity** field, enter a number.</span></span>
4. <span data-ttu-id="29587-116">Nel campo **Risultato** fare clic sul record desiderato del menu a discesa.</span><span class="sxs-lookup"><span data-stu-id="29587-116">In the **Outcome** field, select the desired record in the drop-down menu.</span></span>  
- <span data-ttu-id="29587-117">In questo esempio il risultato è basato su un risultato predefinito.</span><span class="sxs-lookup"><span data-stu-id="29587-117">In this example the result is based on a pre-defined outcome.</span></span> <span data-ttu-id="29587-118">In genere viene registrato un risultato del test più specifico, ad esempio una dimensione o un altro valore simile.</span><span class="sxs-lookup"><span data-stu-id="29587-118">Normally you would record a more specific test result, for example a size or other dimension.</span></span>  
5. <span data-ttu-id="29587-119">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="29587-119">Select **Save**.</span></span>
6. <span data-ttu-id="29587-120">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="29587-120">Close the page.</span></span>

## <a name="validate-the-quality-order"></a><span data-ttu-id="29587-121">Convalida l'ordine di controllo qualità</span><span class="sxs-lookup"><span data-stu-id="29587-121">Validate the quality order</span></span>
1. <span data-ttu-id="29587-122">Selezionare **Convalida**.</span><span class="sxs-lookup"><span data-stu-id="29587-122">Select **Validate**.</span></span>
2. <span data-ttu-id="29587-123">Nel campo **Convalidato da**, selezionare l'utente che esegue l'ispezione dal menu a discesa.</span><span class="sxs-lookup"><span data-stu-id="29587-123">In the **Validated by** field, select the user performing the inspection from the drop-down menu.</span></span>  
3. <span data-ttu-id="29587-124">Fare clic su **Seleziona**.</span><span class="sxs-lookup"><span data-stu-id="29587-124">Click **Select**.</span></span>
4. <span data-ttu-id="29587-125">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="29587-125">Select **OK**.</span></span>
5. <span data-ttu-id="29587-126">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="29587-126">Close the page.</span></span>

