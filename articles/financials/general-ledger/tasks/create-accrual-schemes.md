---
title: Creare schemi di attribuzione per competenza
description: Questa guida attività descrive la creazione di uno schema di attribuzione.
author: aprilolson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerAccrualTable
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e0ae55000a5cf1593d057d940dc3dbbf9e5cb3f3
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/01/2019
ms.locfileid: "1834889"
---
# <a name="create-accrual-schemes"></a><span data-ttu-id="36217-103">Creare schemi di attribuzione per competenza</span><span class="sxs-lookup"><span data-stu-id="36217-103">Create accrual schemes</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="36217-104">Questa guida attività descrive la creazione di uno schema di attribuzione.</span><span class="sxs-lookup"><span data-stu-id="36217-104">This task guide steps through creating an accrual scheme.</span></span> <span data-ttu-id="36217-105">In questa attività viene utilizzata la società dimostrativa USMF.</span><span class="sxs-lookup"><span data-stu-id="36217-105">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="36217-106">Andare a Contabilità generale > Impostazione giornale di registrazione > Schemi di attribuzione per competenza.</span><span class="sxs-lookup"><span data-stu-id="36217-106">Go to General ledger > Journal setup > Accrual schemes.</span></span>
2. <span data-ttu-id="36217-107">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="36217-107">Click New.</span></span>
3. <span data-ttu-id="36217-108">Digitare un valore nel campo Identificazione attribuzione per competenza.</span><span class="sxs-lookup"><span data-stu-id="36217-108">In the Accrual identification field, type a value.</span></span>
4. <span data-ttu-id="36217-109">Nel campo Descrizione dello schema di attribuzione per competenza digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="36217-109">In the Description of accrual scheme field, type a value.</span></span>
5. <span data-ttu-id="36217-110">Nel campo Dare, specificare i valori desiderati.</span><span class="sxs-lookup"><span data-stu-id="36217-110">In the Debit field, specify the desired values.</span></span>
    * <span data-ttu-id="36217-111">Il conto principale definito sostituirà il conto principale in Dare nella riga di giustificativo giornale di registrazione e verrà inoltre utilizzato per lo storno del differimento basato sulle transazioni di attribuzione per competenza in contabilità generale.</span><span class="sxs-lookup"><span data-stu-id="36217-111">The main account defined will replace the debit main account on the journal voucher line and it will also be used for the reversal of the deferral based on the ledger accrual transactions.</span></span>  
6. <span data-ttu-id="36217-112">Nel campo Avere, specificare i valori desiderati.</span><span class="sxs-lookup"><span data-stu-id="36217-112">In the Credit field, specify the desired values.</span></span>
    * <span data-ttu-id="36217-113">Il conto principale definito sostituirà il conto principale in Avere nella riga di giustificativo giornale di registrazione e verrà inoltre utilizzato per lo storno del differimento basato sulle transazioni di attribuzione per competenza in contabilità generale.</span><span class="sxs-lookup"><span data-stu-id="36217-113">The main account defined will replace the credit main account on the journal voucher line and it will also be used for the reversal of the deferral based on the ledger accrual transactions.</span></span>  
7. <span data-ttu-id="36217-114">Nel campo Giustificativo, selezionare la modalità di determinazione del giustificativo quando vengono registrate le transazioni.</span><span class="sxs-lookup"><span data-stu-id="36217-114">In the Voucher field, select how you want the voucher determined when the transactions are posted.</span></span>
8. <span data-ttu-id="36217-115">Nel campo Descrizione, immettere un valore per descrivere le transazioni che verranno registrate.</span><span class="sxs-lookup"><span data-stu-id="36217-115">In the Description field, type a value to describe the transactions that will be posted.</span></span>
9. <span data-ttu-id="36217-116">Nel campo Frequenza periodo, selezionare la frequenza delle transazioni.</span><span class="sxs-lookup"><span data-stu-id="36217-116">In the Period frequency field, select how often the transactions should occur.</span></span>
10. <span data-ttu-id="36217-117">Nel campo Numero di occorrenze per periodo, immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="36217-117">In the Number of occurrences by period field, enter a number.</span></span>
11. <span data-ttu-id="36217-118">Nel campo Registra transazioni specificare quando le transazioni devono essere registrate, ad esempio mensilmente.</span><span class="sxs-lookup"><span data-stu-id="36217-118">In the Post transactions field, select when the transactions should be posted, such as Monthly.</span></span>

