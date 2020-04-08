---
title: Ricevere articoli in un ordine fornitore da una richiesta articolo
description: In questo argomento viene illustrato come ricevere gli articoli in un ordine fornitore da una richiesta articolo.
author: KimANelson
manager: AnnBe
ms.date: 08/06/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjProjectsListPage, ProjTable, ProjSalesItemReq, InventItemIdLookupSimple, PurchCreateFromSalesOrder, VendAccountItemLookup, PurchTable, PurchEditLines
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1f288a47f952a30d98a4a5b96409dc53f880d41d
ms.sourcegitcommit: b92c3e1b3403d0455fc4e0bf9132d6bc0d7aba5e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/18/2020
ms.locfileid: "3139061"
---
# <a name="receive-items-on-purchase-order-from-item-requirement"></a><span data-ttu-id="438c6-103">Ricevere articoli in un ordine fornitore da una richiesta articolo</span><span class="sxs-lookup"><span data-stu-id="438c6-103">Receive items on purchase order from item requirement</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="438c6-104">In questo argomento viene illustrato come ricevere gli articoli in un ordine fornitore da una richiesta articolo.</span><span class="sxs-lookup"><span data-stu-id="438c6-104">This topic explains how to receive items on a purchase order from an item requirement.</span></span>

<span data-ttu-id="438c6-105">Le richieste articoli consentono, rispetto alle transazioni articolo, di pianificare la consegna per il momento immediatamente precedente l'utilizzo effettivo dell'articolo, di creare un ordine fornitore, di includere l'articolo all'interno di un accordo commerciale e di includere la richiesta articolo nella pianificazione della produzione.</span><span class="sxs-lookup"><span data-stu-id="438c6-105">By using an item requirement instead of an item transaction, you can plan for delivery just before the item is actually used, create a purchase order, include the item in the trade-agreement framework, and include the item requirement in production planning.</span></span> 

<span data-ttu-id="438c6-106">Questa attività utilizza il set di dati dimostrativi USSI.</span><span class="sxs-lookup"><span data-stu-id="438c6-106">This task uses the USSI data set.</span></span>

1. <span data-ttu-id="438c6-107">Nel pannello di navigazione, andare a **Moduli > Gestione progetti e contabilità > Progetti > Tutti i progetti**.</span><span class="sxs-lookup"><span data-stu-id="438c6-107">In the navigation pane, go to **Modules > Project management and accounting > Projects > All projects**.</span></span>
2. <span data-ttu-id="438c6-108">Nell'elenco fare clic sul collegamento nella riga desiderata.</span><span class="sxs-lookup"><span data-stu-id="438c6-108">In the list, select the link in the desired row.</span></span>
3. <span data-ttu-id="438c6-109">Nel Riquadro azioni selezionare **Pianifica**.</span><span class="sxs-lookup"><span data-stu-id="438c6-109">On the Action Pane, select **Plan**.</span></span>
4. <span data-ttu-id="438c6-110">Selezionare **Richieste articoli**.</span><span class="sxs-lookup"><span data-stu-id="438c6-110">Select **Item requirements**.</span></span>
5. <span data-ttu-id="438c6-111">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="438c6-111">Select **New**.</span></span>
6. <span data-ttu-id="438c6-112">Nella nuova riga, immettere o selezionare un valore nel campo **Numero articolo**.</span><span class="sxs-lookup"><span data-stu-id="438c6-112">In the new row, enter or select a value in the **Item number** field.</span></span>
7. <span data-ttu-id="438c6-113">Nel campo **Quantità** immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="438c6-113">In the **Quantity** field, enter a number.</span></span>
8. <span data-ttu-id="438c6-114">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="438c6-114">Select **Save**.</span></span>
9. <span data-ttu-id="438c6-115">Nel riquadro azioni, fare clic su **Gestisci**.</span><span class="sxs-lookup"><span data-stu-id="438c6-115">On the Action Pane, select **Manage**.</span></span>
10. <span data-ttu-id="438c6-116">Selezionare **Funzioni**.</span><span class="sxs-lookup"><span data-stu-id="438c6-116">Select **Functions**.</span></span>
11. <span data-ttu-id="438c6-117">Selezionare **Crea ordine fornitore**.</span><span class="sxs-lookup"><span data-stu-id="438c6-117">Select **Create purchase order**.</span></span>
12. <span data-ttu-id="438c6-118">Selezionare la casella di controllo **Includi tutto**.</span><span class="sxs-lookup"><span data-stu-id="438c6-118">Select the **Include all** check box.</span></span>
13. <span data-ttu-id="438c6-119">Nel campo **Conto fornitore**, immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="438c6-119">In the **Vendor account** field, enter or select a value.</span></span>
14. <span data-ttu-id="438c6-120">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="438c6-120">Select **OK**.</span></span>
15. <span data-ttu-id="438c6-121">Nel pannello di navigazione, andare a **Moduli > Contabilità fornitori > Ordini fornitore > Tutti gli ordini fornitore**.</span><span class="sxs-lookup"><span data-stu-id="438c6-121">In the navigation pane, go to **Modules > Accounts payable > Purchase orders > All purchase orders**.</span></span>
16. <span data-ttu-id="438c6-122">Nell'elenco fare clic sul collegamento nella riga desiderata.</span><span class="sxs-lookup"><span data-stu-id="438c6-122">In the list, select the link in the desired row.</span></span>
17. <span data-ttu-id="438c6-123">Nel riquadro azioni fare clic su **Acquisto**.</span><span class="sxs-lookup"><span data-stu-id="438c6-123">On the Action Pane, select **Purchase**.</span></span>
18. <span data-ttu-id="438c6-124">Selezionare **Conferma**.</span><span class="sxs-lookup"><span data-stu-id="438c6-124">Select **Confirm**.</span></span>
19. <span data-ttu-id="438c6-125">Nel riquadro azioni fare clic su **Ricevimento**.</span><span class="sxs-lookup"><span data-stu-id="438c6-125">On the Action Pane, select **Receive**.</span></span>
20. <span data-ttu-id="438c6-126">Selezionare **Entrata prodotti**.</span><span class="sxs-lookup"><span data-stu-id="438c6-126">Select **Product receipt**.</span></span>
21. <span data-ttu-id="438c6-127">Nel campo **Entrata prodotti**, digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="438c6-127">In the **Product receipt** field, type a value.</span></span>
22. <span data-ttu-id="438c6-128">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="438c6-128">Select **OK**.</span></span>

