---
title: Gestire i tipi di codice a barre
description: "Questa procedura mostra come impostare una nuova definizione di codice a barre che potrà quindi essere utilizzata come parte del report distinta di prelievo."
author: perlynne
manager: AnnBe
ms.date: 03/02/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0e7f66cccd76e5326fce75d1a13aff294c16fb9b
ms.openlocfilehash: 45323206550d1b0ed66d89f4be7b995c60af63fc
ms.contentlocale: it-it
ms.lasthandoff: 09/12/2017

---
# <a name="maintain-bar-code-types"></a><span data-ttu-id="cf5ab-103">Gestire i tipi di codice a barre</span><span class="sxs-lookup"><span data-stu-id="cf5ab-103">Maintain bar code types</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="cf5ab-104">Questa procedura mostra come impostare una nuova definizione di codice a barre che potrà quindi essere utilizzata come parte del report distinta di prelievo.</span><span class="sxs-lookup"><span data-stu-id="cf5ab-104">This procedure shows you how to set up a new barcode definition which can then be used as part of the picking list report.</span></span> <span data-ttu-id="cf5ab-105">È possibile eseguire questa procedura nella società di dati dimostrativi USMF oppure utilizzando i propri dati.</span><span class="sxs-lookup"><span data-stu-id="cf5ab-105">You can walk through this procedure in demo data company USMF, or using your own data.</span></span> <span data-ttu-id="cf5ab-106">Se si utilizza USMF è possibile utilizzare i valori di esempio visualizzati.</span><span class="sxs-lookup"><span data-stu-id="cf5ab-106">If you are using USMF you can use the example values that are shown.</span></span> <span data-ttu-id="cf5ab-107">Queste attività verranno in genere svolte da un responsabile del magazzino.</span><span class="sxs-lookup"><span data-stu-id="cf5ab-107">These tasks would typically be carried out by a warehouse manager.</span></span>

1. <span data-ttu-id="cf5ab-108">Passare ai codici a barre.</span><span class="sxs-lookup"><span data-stu-id="cf5ab-108">Go to Bar codes.</span></span>
2. <span data-ttu-id="cf5ab-109">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="cf5ab-109">Click New.</span></span>
3. <span data-ttu-id="cf5ab-110">Digitare un valore nel campo Impostazione codice a barre.</span><span class="sxs-lookup"><span data-stu-id="cf5ab-110">In the Barcode setup field, type a value.</span></span>
4. <span data-ttu-id="cf5ab-111">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="cf5ab-111">In the Description field, type a value.</span></span>
5. <span data-ttu-id="cf5ab-112">Nel campo Tipo di codice a barre selezionare un'opzione.</span><span class="sxs-lookup"><span data-stu-id="cf5ab-112">In the Bar code type field, select an option.</span></span>
    * <span data-ttu-id="cf5ab-113">Se si utilizza USMF, è possibile selezionare 'Code 39'.</span><span class="sxs-lookup"><span data-stu-id="cf5ab-113">If you're using USMF, you can select 'Code 39'.</span></span>  
6. <span data-ttu-id="cf5ab-114">Nel campo Dimensioni immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="cf5ab-114">In the Size field, enter a number.</span></span>
7. <span data-ttu-id="cf5ab-115">Nel campo Lunghezza massima immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="cf5ab-115">In the Maximum length field, enter a number.</span></span>
8. <span data-ttu-id="cf5ab-116">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="cf5ab-116">Click Save.</span></span>
9. <span data-ttu-id="cf5ab-117">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="cf5ab-117">Close the page.</span></span>
10. <span data-ttu-id="cf5ab-118">Passare a Parametri di gestione articoli e magazzino.</span><span class="sxs-lookup"><span data-stu-id="cf5ab-118">Go to Inventory and warehouse management parameters.</span></span>
11. <span data-ttu-id="cf5ab-119">Nel campo Impostazione codice a barre immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="cf5ab-119">In the Barcode setup field, enter or select a value.</span></span>
    * <span data-ttu-id="cf5ab-120">Selezionare l'impostazione codice a barre creata prima, ma tenere presente che il formato di codice a barre deve corrispondere al formato dell'identificatore univoco per il tipo di record utilizzato nel processo.</span><span class="sxs-lookup"><span data-stu-id="cf5ab-120">Select the barcode setup that you created before, but be aware that the bar code format must match the format of the unique identifier for the record type used in the process.</span></span> <span data-ttu-id="cf5ab-121">Ad esempio, per i cicli di prelievo, il formato di codice a barre deve corrispondere al formato di riferimento del ciclo di prelievo, che è in genere una sequenza numerica.</span><span class="sxs-lookup"><span data-stu-id="cf5ab-121">For example, for picking routes, the bar code format should match the format of the picking route reference, which is typically a number sequence.</span></span>  
12. <span data-ttu-id="cf5ab-122">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="cf5ab-122">Click Save.</span></span>
13. <span data-ttu-id="cf5ab-123">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="cf5ab-123">Close the page.</span></span>

