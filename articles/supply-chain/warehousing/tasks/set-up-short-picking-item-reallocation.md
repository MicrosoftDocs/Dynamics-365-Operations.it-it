---
title: Impostare la riallocazione articolo per prelievo breve
description: In questa procedura viene illustrato come consentire agli addetti al magazzino di individuare rapidamente le ubicazioni alternative se non è disponibile scorte sufficienti alla'ubicazione a cui sono stati indirizzati.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSWorkException, WHSWorker
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mirzaab
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: bf56a0811c4793ee2e3eaf78c8696c3c29e984c3
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "1560839"
---
# <a name="set-up-short-picking-item-reallocation"></a><span data-ttu-id="b16eb-103">Impostare la riallocazione articolo per prelievo breve</span><span class="sxs-lookup"><span data-stu-id="b16eb-103">Set up short picking item reallocation</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="b16eb-104">In questa procedura viene illustrato come consentire agli addetti al magazzino di individuare rapidamente le ubicazioni alternative se non è disponibile scorte sufficienti alla'ubicazione a cui sono stati indirizzati.</span><span class="sxs-lookup"><span data-stu-id="b16eb-104">This procedure shows you how to enable warehouse workers to quickly find alternative locations if there isn’t sufficient inventory at the location they’ve been directed to.</span></span> <span data-ttu-id="b16eb-105">È possibile utilizzare un processo di riallocazione automatica, in cui vengono utilizzate le direttive ubicazione per recuperare le merci se sono disponibili in un'altra ubicazione.</span><span class="sxs-lookup"><span data-stu-id="b16eb-105">It’s possible to use an automatic re-allocation process, which uses location directives to retrieve the goods if they’re available at another location.</span></span> <span data-ttu-id="b16eb-106">In alternativa, quando si usa la riallocazione manuale, viene visualizzato un elenco di ubicazioni con la quantità disponibile sul dispositivo mobile, in modo da consentire all'addetto al magazzino di selezionare l'ubicazione da cui utilizzare le scorte.</span><span class="sxs-lookup"><span data-stu-id="b16eb-106">Alternatively, when manual re-allocation is used, a list of the locations with the available quantity is shown on the mobile device, allowing the warehouse worker to choose which location to use inventory from.</span></span> <span data-ttu-id="b16eb-107">È possibile utilizzare questa procedura nella società di dati dimostrativi USMF.</span><span class="sxs-lookup"><span data-stu-id="b16eb-107">You can use this procedure in demo data company USMF.</span></span> <span data-ttu-id="b16eb-108">Questa procedura è per una funzionalità che è stata aggiunta in Dynamics 365 for Operations versione 1611.</span><span class="sxs-lookup"><span data-stu-id="b16eb-108">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="set-up-work-exceptions"></a><span data-ttu-id="b16eb-109">Imposta eccezioni lavoro</span><span class="sxs-lookup"><span data-stu-id="b16eb-109">Set up work exceptions</span></span>
1. <span data-ttu-id="b16eb-110">Passare a Gestione magazzino > Impostazione > Lavoro > Eccezioni lavoro.</span><span class="sxs-lookup"><span data-stu-id="b16eb-110">Go to Warehouse management > Setup > Work > Work exceptions.</span></span>
2. <span data-ttu-id="b16eb-111">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="b16eb-111">Click New.</span></span>
    * <span data-ttu-id="b16eb-112">È possibile definire più eccezioni lavoro con diversi criteri di riallocazione articolo per consentire all'addetto al magazzino di scegliere uno in base alle esigenze di spedizione in corso di elaborazione.</span><span class="sxs-lookup"><span data-stu-id="b16eb-112">It’s possible to define several work exceptions with different item reallocation policies to enable the warehouse worker to choose one based on the needs of the shipment that they are processing.</span></span>  
3. <span data-ttu-id="b16eb-113">Nel campo Codice di eccezione lavoro, immettere un valore.</span><span class="sxs-lookup"><span data-stu-id="b16eb-113">In the Work exception code field, type a value.</span></span>
    * <span data-ttu-id="b16eb-114">Dare all'eccezione lavoro un titolo per indicare per cosa è utilizzata.</span><span class="sxs-lookup"><span data-stu-id="b16eb-114">Give the work exception a title to indicate what it’s used for.</span></span> <span data-ttu-id="b16eb-115">Ad esempio, Prelievo manuale breve.</span><span class="sxs-lookup"><span data-stu-id="b16eb-115">For example, Short picking manual.</span></span>  
4. <span data-ttu-id="b16eb-116">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="b16eb-116">In the Description field, type a value.</span></span>
5. <span data-ttu-id="b16eb-117">Nel campo Tipo di eccezione selezionare 'Prelievo in difetto'.</span><span class="sxs-lookup"><span data-stu-id="b16eb-117">In the Exception type field, select 'Short pick'.</span></span>
6. <span data-ttu-id="b16eb-118">Selezionare la casella di controllo Correggi magazzino.</span><span class="sxs-lookup"><span data-stu-id="b16eb-118">Select the Adjust inventory check box.</span></span>
    * <span data-ttu-id="b16eb-119">Questa opzione indica che l'inventario verrà rettificato automaticamente su 0 all'ubicazione del prelievo breve.</span><span class="sxs-lookup"><span data-stu-id="b16eb-119">This option means that inventory will automatically be adjusted to 0 at the short picked location.</span></span>  
7. <span data-ttu-id="b16eb-120">Nel campo Codice tipo correzione predefinito, immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="b16eb-120">In the Default adjustment type code field, enter or select a value.</span></span>
    * <span data-ttu-id="b16eb-121">Ad esempio, in USMF è possibile selezionare 'Remove Res Adj Out'.</span><span class="sxs-lookup"><span data-stu-id="b16eb-121">For example, in USMF you can select 'Remove Res Adj Out'.</span></span>  
8. <span data-ttu-id="b16eb-122">Nel campo Riallocazione articolo selezionare 'Manuale'.</span><span class="sxs-lookup"><span data-stu-id="b16eb-122">In the Item reallocation field, select 'Manual'.</span></span>
    * <span data-ttu-id="b16eb-123">Se si seleziona Manuale o Automatico e manuale, l'addetto al magazzino deve essere abilitato per utilizzare la riallocazione manuale.</span><span class="sxs-lookup"><span data-stu-id="b16eb-123">If you select Manual, or Automatic and Manual, the warehouse worker needs to be enabled to use manual reallocation.</span></span>  

## <a name="set-up-a-worker-to-use-manual-item-reallocation"></a><span data-ttu-id="b16eb-124">Impostare un lavoratore per utilizzare la riallocazione manuale degli articoli</span><span class="sxs-lookup"><span data-stu-id="b16eb-124">Set up a worker to use manual item reallocation</span></span>
1. <span data-ttu-id="b16eb-125">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="b16eb-125">Close the page.</span></span>
2. <span data-ttu-id="b16eb-126">Andare a Gestione magazzino > Impostazioni > Lavoratore.</span><span class="sxs-lookup"><span data-stu-id="b16eb-126">Go to Warehouse management > Setup > Worker.</span></span>
3. <span data-ttu-id="b16eb-127">Fare clic su Modifica.</span><span class="sxs-lookup"><span data-stu-id="b16eb-127">Click Edit.</span></span>
4. <span data-ttu-id="b16eb-128">Nell'elenco selezionare il lavoratore 24.</span><span class="sxs-lookup"><span data-stu-id="b16eb-128">In the list, select worker 24.</span></span>
5. <span data-ttu-id="b16eb-129">Espandere la sezione Lavoro.</span><span class="sxs-lookup"><span data-stu-id="b16eb-129">Expand the Work section.</span></span>
6. <span data-ttu-id="b16eb-130">Selezionare Sì nel campo Consenti riallocazione manuale articolo.</span><span class="sxs-lookup"><span data-stu-id="b16eb-130">Select Yes in the Allow manual item reallocation field.</span></span>

