---
title: Liquidare le transazioni tra conti CoGe
description: Questa procedura mostra come compensare le transazioni tra diversi conti CoGe e come annullare una compensazione dei saldi contabili.
author: aprilolson
manager: AnnBe
ms.date: 10/03/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerTransSettlement, LedgerTrialBalanceListPage, LedgerTrialBalanceListPageBalanceParms, LedgerTransAccount, LedgerTransSettled
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 6ed76f82532d43a3c05b60b12176fe851e327956
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/01/2019
ms.locfileid: "1846225"
---
# <a name="settle-transactions-between-ledger-accounts"></a><span data-ttu-id="55cfe-103">Liquidare le transazioni tra conti CoGe</span><span class="sxs-lookup"><span data-stu-id="55cfe-103">Settle transactions between ledger accounts</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="55cfe-104">Questa procedura mostra come compensare le transazioni tra diversi conti CoGe e come annullare una compensazione dei saldi contabili.</span><span class="sxs-lookup"><span data-stu-id="55cfe-104">This procedure shows how to settle transactions between ledger accounts and cancel a ledger settlement.</span></span> <span data-ttu-id="55cfe-105">Questa procedura utilizza la società di dati dimostrativi USMF.</span><span class="sxs-lookup"><span data-stu-id="55cfe-105">This procedure uses the USMF demo data company.</span></span>


## <a name="settle-transaction-between-ledger-accounts"></a><span data-ttu-id="55cfe-106">Compensare una transazione tra conti CoGe</span><span class="sxs-lookup"><span data-stu-id="55cfe-106">Settle transaction between ledger accounts</span></span>
1. <span data-ttu-id="55cfe-107">Andare a Contabilità generale > Attività periodiche > Compensazioni dei saldi contabili.</span><span class="sxs-lookup"><span data-stu-id="55cfe-107">Go to General ledger > Periodic tasks > Ledger settlements.</span></span>
2. <span data-ttu-id="55cfe-108">Nell'elenco trovare la transazione da compensare.</span><span class="sxs-lookup"><span data-stu-id="55cfe-108">In the list, find the transaction that you want to settle.</span></span>
   > [!NOTE]
   > <span data-ttu-id="55cfe-109">Il saldo dell'importo deve essere pari a zero.</span><span class="sxs-lookup"><span data-stu-id="55cfe-109">The amount balance must be zero.</span></span>  
3. <span data-ttu-id="55cfe-110">Fare clic su Includi.</span><span class="sxs-lookup"><span data-stu-id="55cfe-110">Click Include.</span></span>
4. <span data-ttu-id="55cfe-111">Fare clic su Accetta.</span><span class="sxs-lookup"><span data-stu-id="55cfe-111">Click Accept.</span></span>

## <a name="cancel-a-ledger-settlement"></a><span data-ttu-id="55cfe-112">Annullare una compensazione dei saldi contabili</span><span class="sxs-lookup"><span data-stu-id="55cfe-112">Cancel a ledger settlement</span></span>

1. <span data-ttu-id="55cfe-113">Andare a Contabilità generale > Richieste di informazioni e report > Bilancio di verifica.</span><span class="sxs-lookup"><span data-stu-id="55cfe-113">Go to General ledger > Inquiries and reports > Trial balance.</span></span>
2. <span data-ttu-id="55cfe-114">Fare clic su Parametri per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="55cfe-114">Click Parameters to open the drop dialog.</span></span>
3. <span data-ttu-id="55cfe-115">Fare clic su Aggiorna.</span><span class="sxs-lookup"><span data-stu-id="55cfe-115">Click Update.</span></span>
4. <span data-ttu-id="55cfe-116">Nell'elenco trovare il conto che ha la transazione compensata.</span><span class="sxs-lookup"><span data-stu-id="55cfe-116">In the list, find the account that has the settled transaction.</span></span>
5. <span data-ttu-id="55cfe-117">Fare clic su Tutte le transazioni.</span><span class="sxs-lookup"><span data-stu-id="55cfe-117">Click All transactions.</span></span>
6. <span data-ttu-id="55cfe-118">Utilizzare un filtro per trovare facilmente la transazione nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="55cfe-118">Use a filter to easily find the transaction in the list.</span></span>
7. <span data-ttu-id="55cfe-119">Fare clic su Compensazioni dei saldi contabili.</span><span class="sxs-lookup"><span data-stu-id="55cfe-119">Click Ledger settlements.</span></span>
8. <span data-ttu-id="55cfe-120">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="55cfe-120">In the list, mark the selected row.</span></span>

