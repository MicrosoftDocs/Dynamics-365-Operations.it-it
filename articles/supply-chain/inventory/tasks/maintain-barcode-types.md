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
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 02b2e1eabd6336acc86a080e309c8c7e758fc8dd
ms.contentlocale: it-it
ms.lasthandoff: 05/08/2018

---
# <a name="maintain-bar-code-types"></a><span data-ttu-id="338f8-103">Gestire i tipi di codice a barre</span><span class="sxs-lookup"><span data-stu-id="338f8-103">Maintain bar code types</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="338f8-104">Questa procedura mostra come impostare una nuova definizione di codice a barre che potrà quindi essere utilizzata come parte del report distinta di prelievo.</span><span class="sxs-lookup"><span data-stu-id="338f8-104">This procedure shows you how to set up a new barcode definition which can then be used as part of the picking list report.</span></span> <span data-ttu-id="338f8-105">È possibile eseguire questa procedura nella società di dati dimostrativi USMF oppure utilizzando i propri dati.</span><span class="sxs-lookup"><span data-stu-id="338f8-105">You can walk through this procedure in demo data company USMF, or using your own data.</span></span> <span data-ttu-id="338f8-106">Se si utilizza USMF è possibile utilizzare i valori di esempio visualizzati.</span><span class="sxs-lookup"><span data-stu-id="338f8-106">If you are using USMF you can use the example values that are shown.</span></span> <span data-ttu-id="338f8-107">Queste attività verranno in genere svolte da un responsabile del magazzino.</span><span class="sxs-lookup"><span data-stu-id="338f8-107">These tasks would typically be carried out by a warehouse manager.</span></span>

1. <span data-ttu-id="338f8-108">Passare ai codici a barre.</span><span class="sxs-lookup"><span data-stu-id="338f8-108">Go to Bar codes.</span></span>
2. <span data-ttu-id="338f8-109">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="338f8-109">Click New.</span></span>
3. <span data-ttu-id="338f8-110">Digitare un valore nel campo Impostazione codice a barre.</span><span class="sxs-lookup"><span data-stu-id="338f8-110">In the Barcode setup field, type a value.</span></span>
4. <span data-ttu-id="338f8-111">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="338f8-111">In the Description field, type a value.</span></span>
5. <span data-ttu-id="338f8-112">Nel campo Tipo di codice a barre selezionare un'opzione.</span><span class="sxs-lookup"><span data-stu-id="338f8-112">In the Bar code type field, select an option.</span></span>
    * <span data-ttu-id="338f8-113">Se si utilizza USMF, è possibile selezionare 'Code 39'.</span><span class="sxs-lookup"><span data-stu-id="338f8-113">If you're using USMF, you can select 'Code 39'.</span></span>  
6. <span data-ttu-id="338f8-114">Nel campo Dimensioni immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="338f8-114">In the Size field, enter a number.</span></span>
7. <span data-ttu-id="338f8-115">Nel campo Lunghezza massima immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="338f8-115">In the Maximum length field, enter a number.</span></span>
8. <span data-ttu-id="338f8-116">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="338f8-116">Click Save.</span></span>
9. <span data-ttu-id="338f8-117">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="338f8-117">Close the page.</span></span>
10. <span data-ttu-id="338f8-118">Passare a Parametri di gestione articoli e magazzino.</span><span class="sxs-lookup"><span data-stu-id="338f8-118">Go to Inventory and warehouse management parameters.</span></span>
11. <span data-ttu-id="338f8-119">Nel campo Impostazione codice a barre immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="338f8-119">In the Barcode setup field, enter or select a value.</span></span>
    * <span data-ttu-id="338f8-120">Selezionare l'impostazione codice a barre creata prima, ma tenere presente che il formato di codice a barre deve corrispondere al formato dell'identificatore univoco per il tipo di record utilizzato nel processo.</span><span class="sxs-lookup"><span data-stu-id="338f8-120">Select the barcode setup that you created before, but be aware that the bar code format must match the format of the unique identifier for the record type used in the process.</span></span> <span data-ttu-id="338f8-121">Ad esempio, per i cicli di prelievo, il formato di codice a barre deve corrispondere al formato di riferimento del ciclo di prelievo, che è in genere una sequenza numerica.</span><span class="sxs-lookup"><span data-stu-id="338f8-121">For example, for picking routes, the bar code format should match the format of the picking route reference, which is typically a number sequence.</span></span>  
12. <span data-ttu-id="338f8-122">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="338f8-122">Click Save.</span></span>
13. <span data-ttu-id="338f8-123">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="338f8-123">Close the page.</span></span>

