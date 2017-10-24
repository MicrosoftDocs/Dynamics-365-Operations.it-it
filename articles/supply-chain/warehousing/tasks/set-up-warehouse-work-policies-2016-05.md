--- 
title: 'Impostare i criteri di lavoro magazzino '
description: I processi del magazzino non includono sempre il lavoro in magazzino.
author: johanhoffmann
manager: AnnBe
ms.date: 06/23/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: b7d579ca7e2b9ca8cbead74b2c2ababfd142f171
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---
# <a name="set-up-warehouse-work-policies"></a><span data-ttu-id="a08a5-103">Impostare i criteri di lavoro magazzino </span><span class="sxs-lookup"><span data-stu-id="a08a5-103">Set up warehouse work policies</span></span> 

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="a08a5-104">I processi del magazzino non includono sempre il lavoro in magazzino.</span><span class="sxs-lookup"><span data-stu-id="a08a5-104">Warehouse processes don’t always include warehouse work.</span></span> <span data-ttu-id="a08a5-105">Definendo i criteri di lavoro, è possibile impedire la creazione di lavoro per il prelievo delle materie prime e lo stoccaggio di prodotti finiti per un set di prodotti in ubicazioni specifiche.</span><span class="sxs-lookup"><span data-stu-id="a08a5-105">By defining a work policy, you can prevent the creation of work for raw material picking and put-away of finished goods for a set of products at specific locations.</span></span> <span data-ttu-id="a08a5-106">La società di dati dimostrativi USMF è stata utilizzata per creare questa registrazione.</span><span class="sxs-lookup"><span data-stu-id="a08a5-106">The USMF demo data company was used to create this recording.</span></span> <span data-ttu-id="a08a5-107">Questa guida attività richiede l'applicazione Dynamics AX 7.0.1 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="a08a5-107">This task guide requires Dynamics AX application 7.0.1 or later.</span></span>

1. <span data-ttu-id="a08a5-108">Andare a Gestione magazzino > Impostazioni > Lavoro > Criteri di lavoro.</span><span class="sxs-lookup"><span data-stu-id="a08a5-108">Go to Warehouse management > Setup > Work > Work policies.</span></span>
2. <span data-ttu-id="a08a5-109">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="a08a5-109">Click New.</span></span>
3. <span data-ttu-id="a08a5-110">Nel campo Nome criteri di lavoro digitare “No lavoro di stoccaggio".</span><span class="sxs-lookup"><span data-stu-id="a08a5-110">In the Work policy name field, type 'No put-away work'.</span></span>
4. <span data-ttu-id="a08a5-111">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="a08a5-111">Click Save.</span></span>
5. <span data-ttu-id="a08a5-112">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="a08a5-112">Click Add.</span></span>
6. <span data-ttu-id="a08a5-113">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="a08a5-113">In the list, mark the selected row.</span></span>
7. <span data-ttu-id="a08a5-114">Nel campo Tipo ordine di lavoro selezionare "Stoccaggio prodotti finiti".</span><span class="sxs-lookup"><span data-stu-id="a08a5-114">In the Work order type field, select 'Finished goods put away'.</span></span>
8. <span data-ttu-id="a08a5-115">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="a08a5-115">Click Add.</span></span>
9. <span data-ttu-id="a08a5-116">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="a08a5-116">In the list, mark the selected row.</span></span>
10. <span data-ttu-id="a08a5-117">Nel campo Tipo ordine di lavoro selezionare "Stoccaggio co-prodotti e sottoprodotti".</span><span class="sxs-lookup"><span data-stu-id="a08a5-117">In the Work order type field, select 'Co-product and by-product put away'.</span></span>
11. <span data-ttu-id="a08a5-118">Espandere la sezione Ubicazioni di magazzino.</span><span class="sxs-lookup"><span data-stu-id="a08a5-118">Expand the Inventory locations section.</span></span>
12. <span data-ttu-id="a08a5-119">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="a08a5-119">Click Add.</span></span>
13. <span data-ttu-id="a08a5-120">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="a08a5-120">In the list, mark the selected row.</span></span>
14. <span data-ttu-id="a08a5-121">Nell'elenco di magazzino immettere "51".</span><span class="sxs-lookup"><span data-stu-id="a08a5-121">In the Warehouse list, enter '51'.</span></span>
15. <span data-ttu-id="a08a5-122">Nel campo Ubicazione immettere o selezionare "001".</span><span class="sxs-lookup"><span data-stu-id="a08a5-122">In the Location field, enter or select '001'.</span></span>
16. <span data-ttu-id="a08a5-123">Espandere la sezione Prodotti.</span><span class="sxs-lookup"><span data-stu-id="a08a5-123">Expand the Products section.</span></span>
17. <span data-ttu-id="a08a5-124">Nel campo Selezione prodotto selezionare "Selezionato".</span><span class="sxs-lookup"><span data-stu-id="a08a5-124">In the Product selection field, select 'Selected'.</span></span>
18. <span data-ttu-id="a08a5-125">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="a08a5-125">Click Add.</span></span>
19. <span data-ttu-id="a08a5-126">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="a08a5-126">In the list, mark the selected row.</span></span>
20. <span data-ttu-id="a08a5-127">Nel campo Numero articolo immettere o selezionare "L0101".</span><span class="sxs-lookup"><span data-stu-id="a08a5-127">In the Item number field, enter or select 'L0101'.</span></span>
21. <span data-ttu-id="a08a5-128">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="a08a5-128">Click Save.</span></span>


