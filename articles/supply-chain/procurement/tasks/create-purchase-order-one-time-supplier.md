---
title: Creare un ordine fornitore per un fornitore occasionale
description: Questa procedura indica come creare un ordine fornitore per un fornitore occasionale.
author: FrankDahl
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable, PurchCreateOrder
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: fdahl
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e2fa54ff598bb6a09bbcc483995a6e1a3f4286b3
ms.sourcegitcommit: 16612a632aad9d390f8d80d3fc1f766585b2911e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/04/2020
ms.locfileid: "3098078"
---
# <a name="create-a-purchase-order-for-a-one-time-supplier"></a><span data-ttu-id="0fe3d-103">Creare un ordine fornitore per un fornitore occasionale</span><span class="sxs-lookup"><span data-stu-id="0fe3d-103">Create a purchase order for a one-time supplier</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="0fe3d-104">Questa procedura indica come creare un ordine fornitore per un fornitore occasionale.</span><span class="sxs-lookup"><span data-stu-id="0fe3d-104">This procedure shows you how to create a purchase order for a one-time supplier.</span></span> <span data-ttu-id="0fe3d-105">Il fornitore è creato automaticamente con l'ordine fornitore, piuttosto che dover creare manualmente il conto fornitore.</span><span class="sxs-lookup"><span data-stu-id="0fe3d-105">The supplier is created automatically with the purchase order, rather than having to create the vendor account manually.</span></span> <span data-ttu-id="0fe3d-106">Gli ordini acquisti sono in genere creati da un addetto agli acquisti.</span><span class="sxs-lookup"><span data-stu-id="0fe3d-106">Purchase orders are typically created by a purchasing agent.</span></span> <span data-ttu-id="0fe3d-107">L'esempio indicato in questa guida può essere utilizzato nella società di dati dimostrativi USMF.</span><span class="sxs-lookup"><span data-stu-id="0fe3d-107">The example shown in this guide can be used in the USMF demo data company.</span></span> <span data-ttu-id="0fe3d-108">È un prerequisito che un conto fornitore occasionale sia stato impostato nella pagina Parametri contabilità fornitori.</span><span class="sxs-lookup"><span data-stu-id="0fe3d-108">It is a prerequisite that a one-time vendor account has been set up in the Account payable parameters page.</span></span>


## <a name="create-a-purchase-order-for-a-one-time-supplier"></a><span data-ttu-id="0fe3d-109">Creare un ordine fornitore per un fornitore occasionale</span><span class="sxs-lookup"><span data-stu-id="0fe3d-109">Create a purchase order for a one-time supplier</span></span>
1. <span data-ttu-id="0fe3d-110">Andare ad Approvvigionamento > Ordini fornitore> Tutti gli ordini fornitore.</span><span class="sxs-lookup"><span data-stu-id="0fe3d-110">Go to Procurement and sourcing > Purchase orders > All purchase orders.</span></span>
2. <span data-ttu-id="0fe3d-111">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="0fe3d-111">Click New.</span></span>
3. <span data-ttu-id="0fe3d-112">Selezionare Sì nel campo Fornitore occasionale.</span><span class="sxs-lookup"><span data-stu-id="0fe3d-112">Select Yes in the One-time supplier field.</span></span>
    * <span data-ttu-id="0fe3d-113">Un conto fornitore viene automaticamente creato ed assegnato all'ordine fornitore.</span><span class="sxs-lookup"><span data-stu-id="0fe3d-113">A vendor account is automatically created and assigned to the purchase order.</span></span> <span data-ttu-id="0fe3d-114">Il conto fornitore è creato in base al modello che è specificato nella scheda generale nella pagina Parametri contabilità fornitori.</span><span class="sxs-lookup"><span data-stu-id="0fe3d-114">The vendor account is created based on the template that is specified on the General tab in the Accounts payable parameters page.</span></span>  
4. <span data-ttu-id="0fe3d-115">Nel campo Nome digitare un nome univoco per il fornitore.</span><span class="sxs-lookup"><span data-stu-id="0fe3d-115">In the Name field, type a name for the supplier.</span></span>
5. <span data-ttu-id="0fe3d-116">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="0fe3d-116">Click OK.</span></span>
    * <span data-ttu-id="0fe3d-117">L'ordine fornitore può ora essere completato ed elaborato come qualunque altro ordine.</span><span class="sxs-lookup"><span data-stu-id="0fe3d-117">The purchase order can now be completed and processed like any other order.</span></span> <span data-ttu-id="0fe3d-118">Non ci sono caratteristiche speciali relative a come questo è fatto.</span><span class="sxs-lookup"><span data-stu-id="0fe3d-118">There are no special characteristics related to how this is done.</span></span> <span data-ttu-id="0fe3d-119">La fattura contabilizzerà una transazione dovuta sul conto fornitore che è stato creato con l'ordine ed il pagamento poi sarà elaborato.</span><span class="sxs-lookup"><span data-stu-id="0fe3d-119">The invoice will account a due transaction on the vendor account that was created with the order, and payment will then be processed.</span></span>

