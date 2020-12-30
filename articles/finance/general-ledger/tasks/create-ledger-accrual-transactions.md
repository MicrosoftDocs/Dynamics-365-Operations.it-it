---
title: Creare transazioni di attribuzione per competenza in contabilità generale
description: Questa guida di attività descrive la generazione di transazioni di attribuzione per competenza in contabilità generale basate su schemi di attribuzione per competenza.
author: aprilolson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransDaily, LedgerJournalTransAccrual, LedgerJournalTransAccrualTrans
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2112336045086d0eb3b2fb0018f33631528a05ec
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4444688"
---
# <a name="create-ledger-accrual-transactions"></a><span data-ttu-id="8c1c9-103">Creare transazioni di attribuzione per competenza in contabilità generale</span><span class="sxs-lookup"><span data-stu-id="8c1c9-103">Create ledger accrual transactions</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="8c1c9-104">Questa guida di attività descrive la generazione di transazioni di attribuzione per competenza in contabilità generale basate su schemi di attribuzione per competenza.</span><span class="sxs-lookup"><span data-stu-id="8c1c9-104">This task guide steps through generating ledger accrual transactions that are based on accrual schemes</span></span>

1. <span data-ttu-id="8c1c9-105">Fare clic su Contabilità generale > Scritture contabili > Giornali di registrazione generali.</span><span class="sxs-lookup"><span data-stu-id="8c1c9-105">Go to General ledger > Journal entries > General journals.</span></span>
2. <span data-ttu-id="8c1c9-106">Nell'elenco, trovare e selezionare il giornale di registrazione desiderato o crearne uno nuovo.</span><span class="sxs-lookup"><span data-stu-id="8c1c9-106">In the list, find and select the desired journal or create a new one.</span></span>
3. <span data-ttu-id="8c1c9-107">Fare clic per seguire il collegamento nel campo Numero batch giornale di registrazione.</span><span class="sxs-lookup"><span data-stu-id="8c1c9-107">Click to follow the link in the Journal batch number field.</span></span>
4. <span data-ttu-id="8c1c9-108">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="8c1c9-108">In the list, mark the selected row.</span></span>
5. <span data-ttu-id="8c1c9-109">Nel campo Conto, specificare i valori desiderati.</span><span class="sxs-lookup"><span data-stu-id="8c1c9-109">In the Account field, specify the desired values.</span></span>
    * <span data-ttu-id="8c1c9-110">In questo esempio viene definita la spesa dell'assicurazione.</span><span class="sxs-lookup"><span data-stu-id="8c1c9-110">In this example, we are defining the expense for the insurance.</span></span> <span data-ttu-id="8c1c9-111">Verrà impostata come importo di spesa periodico.</span><span class="sxs-lookup"><span data-stu-id="8c1c9-111">It will be come periodic expense amount.</span></span>  
6. <span data-ttu-id="8c1c9-112">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="8c1c9-112">In the Description field, type a value.</span></span>
7. <span data-ttu-id="8c1c9-113">Nel campo Dare immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="8c1c9-113">In the Debit field, enter a number.</span></span>
8. <span data-ttu-id="8c1c9-114">Nel campo Conto di contropartita, specificare i valori desiderati.</span><span class="sxs-lookup"><span data-stu-id="8c1c9-114">In the Offset account field, specify the desired values.</span></span>
9. <span data-ttu-id="8c1c9-115">Fare clic su Funzioni.</span><span class="sxs-lookup"><span data-stu-id="8c1c9-115">Click Functions.</span></span>
10. <span data-ttu-id="8c1c9-116">Fare clic su Ratei in contabilità generale.</span><span class="sxs-lookup"><span data-stu-id="8c1c9-116">Click Ledger accruals.</span></span>
11. <span data-ttu-id="8c1c9-117">Nel campo Identificazione attribuzione per competenza fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="8c1c9-117">In the Accrual identification field, click the drop-down button to open the lookup.</span></span>
12. <span data-ttu-id="8c1c9-118">Nell'elenco, trovare e selezionare lo schema di attribuzione per competenza che si desidera applicare.</span><span class="sxs-lookup"><span data-stu-id="8c1c9-118">In the list, find and select the accural scheme you want to apply.</span></span>
13. <span data-ttu-id="8c1c9-119">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="8c1c9-119">In the list, click the link in the selected row.</span></span>
14. <span data-ttu-id="8c1c9-120">Nel campo Data di inizio, immettere una data.</span><span class="sxs-lookup"><span data-stu-id="8c1c9-120">In the Start date field, enter a date.</span></span>
15. <span data-ttu-id="8c1c9-121">Fare clic su Transazioni.</span><span class="sxs-lookup"><span data-stu-id="8c1c9-121">Click Transactions.</span></span>
16. <span data-ttu-id="8c1c9-122">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="8c1c9-122">Close the page.</span></span>
17. <span data-ttu-id="8c1c9-123">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="8c1c9-123">Click OK.</span></span>
18. <span data-ttu-id="8c1c9-124">Fare clic su Registra.</span><span class="sxs-lookup"><span data-stu-id="8c1c9-124">Click Post.</span></span>

