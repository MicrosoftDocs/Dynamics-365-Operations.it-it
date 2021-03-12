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
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8220bacc8d683163e97956ec59a5af929b04319c
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4994417"
---
# <a name="settle-transactions-between-ledger-accounts"></a><span data-ttu-id="b01f0-103">Liquidare le transazioni tra conti CoGe</span><span class="sxs-lookup"><span data-stu-id="b01f0-103">Settle transactions between ledger accounts</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="b01f0-104">Questa procedura mostra come compensare le transazioni tra diversi conti CoGe e come annullare una compensazione dei saldi contabili.</span><span class="sxs-lookup"><span data-stu-id="b01f0-104">This procedure shows how to settle transactions between ledger accounts and cancel a ledger settlement.</span></span> <span data-ttu-id="b01f0-105">Questa procedura utilizza la società di dati dimostrativi USMF.</span><span class="sxs-lookup"><span data-stu-id="b01f0-105">This procedure uses the USMF demo data company.</span></span>


## <a name="settle-transaction-between-ledger-accounts"></a><span data-ttu-id="b01f0-106">Compensare una transazione tra conti CoGe</span><span class="sxs-lookup"><span data-stu-id="b01f0-106">Settle transaction between ledger accounts</span></span>
1. <span data-ttu-id="b01f0-107">Andare a Contabilità generale > Attività periodiche > Compensazioni dei saldi contabili.</span><span class="sxs-lookup"><span data-stu-id="b01f0-107">Go to General ledger > Periodic tasks > Ledger settlements.</span></span>
2. <span data-ttu-id="b01f0-108">Nell'elenco trovare la transazione da compensare.</span><span class="sxs-lookup"><span data-stu-id="b01f0-108">In the list, find the transaction that you want to settle.</span></span>
   > [!NOTE]
   > <span data-ttu-id="b01f0-109">Il saldo dell'importo deve essere pari a zero.</span><span class="sxs-lookup"><span data-stu-id="b01f0-109">The amount balance must be zero.</span></span>  
3. <span data-ttu-id="b01f0-110">Fare clic su Includi.</span><span class="sxs-lookup"><span data-stu-id="b01f0-110">Click Include.</span></span>
4. <span data-ttu-id="b01f0-111">Fare clic su Accetta.</span><span class="sxs-lookup"><span data-stu-id="b01f0-111">Click Accept.</span></span>

## <a name="cancel-a-ledger-settlement"></a><span data-ttu-id="b01f0-112">Annullare una compensazione dei saldi contabili</span><span class="sxs-lookup"><span data-stu-id="b01f0-112">Cancel a ledger settlement</span></span>

1. <span data-ttu-id="b01f0-113">Andare a Contabilità generale > Richieste di informazioni e report > Bilancio di verifica.</span><span class="sxs-lookup"><span data-stu-id="b01f0-113">Go to General ledger > Inquiries and reports > Trial balance.</span></span>
2. <span data-ttu-id="b01f0-114">Fare clic su Parametri per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="b01f0-114">Click Parameters to open the drop dialog.</span></span>
3. <span data-ttu-id="b01f0-115">Fare clic su Aggiorna.</span><span class="sxs-lookup"><span data-stu-id="b01f0-115">Click Update.</span></span>
4. <span data-ttu-id="b01f0-116">Nell'elenco trovare il conto che ha la transazione compensata.</span><span class="sxs-lookup"><span data-stu-id="b01f0-116">In the list, find the account that has the settled transaction.</span></span>
5. <span data-ttu-id="b01f0-117">Fare clic su Tutte le transazioni.</span><span class="sxs-lookup"><span data-stu-id="b01f0-117">Click All transactions.</span></span>
6. <span data-ttu-id="b01f0-118">Utilizzare un filtro per trovare facilmente la transazione nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="b01f0-118">Use a filter to easily find the transaction in the list.</span></span>
7. <span data-ttu-id="b01f0-119">Fare clic su Compensazioni dei saldi contabili.</span><span class="sxs-lookup"><span data-stu-id="b01f0-119">Click Ledger settlements.</span></span>
8. <span data-ttu-id="b01f0-120">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="b01f0-120">In the list, mark the selected row.</span></span>

