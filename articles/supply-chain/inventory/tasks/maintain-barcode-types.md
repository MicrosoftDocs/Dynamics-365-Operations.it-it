---
title: Gestisci tipi di codici a barre
description: Questa procedura mostra come impostare una nuova definizione di codice a barre che potrà quindi essere utilizzata come parte del report distinta di prelievo.
author: perlynne
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BarcodeSetup, InventParameters
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7834745923bf5ec05018ff5829ddaa0b75df5db7
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/18/2020
ms.locfileid: "3145580"
---
# <a name="maintain-barcode-types"></a><span data-ttu-id="3694c-103">Gestisci tipi di codici a barre</span><span class="sxs-lookup"><span data-stu-id="3694c-103">Maintain barcode types</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="3694c-104">Questa procedura mostra come impostare una nuova definizione di codice a barre che potrà quindi essere utilizzata come parte del report distinta di prelievo.</span><span class="sxs-lookup"><span data-stu-id="3694c-104">This procedure shows you how to set up a new barcode definition which can then be used as part of the picking list report.</span></span> <span data-ttu-id="3694c-105">È possibile eseguire questa procedura nella società di dati dimostrativi USMF oppure utilizzando i propri dati.</span><span class="sxs-lookup"><span data-stu-id="3694c-105">You can walk through this procedure in demo data company USMF, or using your own data.</span></span> <span data-ttu-id="3694c-106">Se si utilizza USMF è possibile utilizzare i valori di esempio visualizzati.</span><span class="sxs-lookup"><span data-stu-id="3694c-106">If you are using USMF you can use the example values that are shown.</span></span> <span data-ttu-id="3694c-107">Queste attività verranno in genere svolte da un responsabile del magazzino.</span><span class="sxs-lookup"><span data-stu-id="3694c-107">These tasks would typically be carried out by a warehouse manager.</span></span>

1. <span data-ttu-id="3694c-108">Passare ai codici a barre.</span><span class="sxs-lookup"><span data-stu-id="3694c-108">Go to Bar codes.</span></span>
2. <span data-ttu-id="3694c-109">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="3694c-109">Click New.</span></span>
3. <span data-ttu-id="3694c-110">Digitare un valore nel campo Impostazione codice a barre.</span><span class="sxs-lookup"><span data-stu-id="3694c-110">In the Barcode setup field, type a value.</span></span>
4. <span data-ttu-id="3694c-111">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="3694c-111">In the Description field, type a value.</span></span>
5. <span data-ttu-id="3694c-112">Nel campo Tipo di codice a barre selezionare un'opzione.</span><span class="sxs-lookup"><span data-stu-id="3694c-112">In the Bar code type field, select an option.</span></span>
    * <span data-ttu-id="3694c-113">Se si utilizza USMF, è possibile selezionare 'Code 39'.</span><span class="sxs-lookup"><span data-stu-id="3694c-113">If you're using USMF, you can select 'Code 39'.</span></span>  
6. <span data-ttu-id="3694c-114">Nel campo Dimensioni immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="3694c-114">In the Size field, enter a number.</span></span>
7. <span data-ttu-id="3694c-115">Nel campo Lunghezza massima immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="3694c-115">In the Maximum length field, enter a number.</span></span>
8. <span data-ttu-id="3694c-116">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="3694c-116">Click Save.</span></span>
9. <span data-ttu-id="3694c-117">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="3694c-117">Close the page.</span></span>
10. <span data-ttu-id="3694c-118">Passare a Parametri di gestione articoli e magazzino.</span><span class="sxs-lookup"><span data-stu-id="3694c-118">Go to Inventory and warehouse management parameters.</span></span>
11. <span data-ttu-id="3694c-119">Nel campo Impostazione codice a barre immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="3694c-119">In the Barcode setup field, enter or select a value.</span></span>
    * <span data-ttu-id="3694c-120">Selezionare l'impostazione codice a barre creata prima, ma tenere presente che il formato di codice a barre deve corrispondere al formato dell'identificatore univoco per il tipo di record utilizzato nel processo.</span><span class="sxs-lookup"><span data-stu-id="3694c-120">Select the barcode setup that you created before, but be aware that the bar code format must match the format of the unique identifier for the record type used in the process.</span></span> <span data-ttu-id="3694c-121">Ad esempio, per i cicli di prelievo, il formato di codice a barre deve corrispondere al formato di riferimento del ciclo di prelievo, che è in genere una sequenza numerica.</span><span class="sxs-lookup"><span data-stu-id="3694c-121">For example, for picking routes, the bar code format should match the format of the picking route reference, which is typically a number sequence.</span></span>  
12. <span data-ttu-id="3694c-122">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="3694c-122">Click Save.</span></span>
13. <span data-ttu-id="3694c-123">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="3694c-123">Close the page.</span></span>

