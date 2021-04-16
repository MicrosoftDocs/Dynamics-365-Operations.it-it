---
title: Configurare le denominazioni del contante per il POS
description: Le denominazioni del contante per banconote e monete possono essere definite nel back office per l'uso da parte di cassieri, assistenti alle vendite e responsabili nel punto vendita dal POS.
author: jblucher
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailStoreTable, RetailStoreCashDeclarationTable
audience: Application User
ms.reviewer: josaw
ms.custom: 16231
ms.assetid: f28a827c-3a50-4d5e-83eb-e5a768db70a1
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 5dbef67728e86259ee48b51c48921f6e44a61015
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5793059"
---
# <a name="configure-cash-denominations-for-the-point-of-sale-pos"></a><span data-ttu-id="2ae5f-103">Configurare le denominazioni del contante per il POS</span><span class="sxs-lookup"><span data-stu-id="2ae5f-103">Configure cash denominations for the point of sale (POS)</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="2ae5f-104">Le denominazioni del contante per banconote e monete possono essere definite nel back office per l'uso da parte di cassieri, assistenti alle vendite e responsabili nel punto vendita dal POS.</span><span class="sxs-lookup"><span data-stu-id="2ae5f-104">Cash denominations for notes and coins can be defined in the back office to be used by cashiers, sales associates, and managers at the store from within the POS.</span></span> <span data-ttu-id="2ae5f-105">Queste denominazioni possono essere utilizzate per agevolare il conteggio del contante per i riepiloghi incassi alla fine della giornata o per incassare rapidamente una vendita.</span><span class="sxs-lookup"><span data-stu-id="2ae5f-105">These denominations can be used to aid in counting cash for end of day tender declarations or for quickly tendering a sale.</span></span>

## <a name="define-denominations"></a><span data-ttu-id="2ae5f-106">Definire le denominazioni</span><span class="sxs-lookup"><span data-stu-id="2ae5f-106">Define denominations</span></span>

<span data-ttu-id="2ae5f-107">È possibile impostare le denominazioni per punto vendita selezionando **Imposta** \> **Riepilogo di cassa** nella pagina delle proprietà dei punti vendita.</span><span class="sxs-lookup"><span data-stu-id="2ae5f-107">The denominations are set up per store on the **Set up** \> **Cash declaration** option from the store property page.</span></span>

![Opzione Riepilogo di cassa](./media/image1-denomination.png)

<span data-ttu-id="2ae5f-109">Per definire una denominazione:</span><span class="sxs-lookup"><span data-stu-id="2ae5f-109">To define a denomination:</span></span>

1. <span data-ttu-id="2ae5f-110">Fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="2ae5f-110">Click **New**.</span></span>
1. <span data-ttu-id="2ae5f-111">Specificare il tipo (moneta o banconota).</span><span class="sxs-lookup"><span data-stu-id="2ae5f-111">Specify the type (coin or note).</span></span>
1. <span data-ttu-id="2ae5f-112">Specificare l'importo (valore).</span><span class="sxs-lookup"><span data-stu-id="2ae5f-112">Specify the amount (value).</span></span>

![Pagina Denominazioni riepilogo di cassa](./media/image2-denomination.png)

## <a name="configure-the-functionality-profile"></a><span data-ttu-id="2ae5f-114">Configurare il profilo funzionalità</span><span class="sxs-lookup"><span data-stu-id="2ae5f-114">Configure the functionality profile</span></span>

<span data-ttu-id="2ae5f-115">In caso di pagamento in contanti nel POS, l'utente può utilizzare le denominazioni delle banconote per immettere rapidamente l'importo pagato dal cliente.</span><span class="sxs-lookup"><span data-stu-id="2ae5f-115">When paying by cash in POS, the user can use the note denominations to quickly enter the amount paid by the customer.</span></span> <span data-ttu-id="2ae5f-116">Nel profilo funzionalità, è possibile configurare le due opzioni per la visualizzazione della denominazione nel POS.</span><span class="sxs-lookup"><span data-stu-id="2ae5f-116">In the functionality profile, you can configure the two options for showing the denomination in POS.</span></span>

- <span data-ttu-id="2ae5f-117">**Maggiore o uguale all'importo dovuto**: per impostazione predefinita, il POS visualizzerà solo le denominazioni delle banconote superiori all'importo dovuto. Ciò consente di effettuare il pagamento con un singolo tocco.</span><span class="sxs-lookup"><span data-stu-id="2ae5f-117">**Greater or equal to amount due** – By default, POS will only show the note denominations that are greater than the amount due, which allows for one-touch tendering.</span></span> <span data-ttu-id="2ae5f-118">Ad esempio, se l'importo dovuto è 7,50 USD, il POS visualizza le denominazioni 10, 20, 50 e 100 USD.</span><span class="sxs-lookup"><span data-stu-id="2ae5f-118">For example, if the amount due is $7.50, POS would show the following denominations: $10, $20, $50, and $100.</span></span> <span data-ttu-id="2ae5f-119">Toccando una di quelle denominazioni, si incassa automaticamente l'importo della vendita.</span><span class="sxs-lookup"><span data-stu-id="2ae5f-119">Touching any of these amounts will automatically tender the sale for that amount.</span></span> <span data-ttu-id="2ae5f-120">Le banconote da 1 e 5 USD non sono visualizzate in quanto inferiori all'importo dovuto.</span><span class="sxs-lookup"><span data-stu-id="2ae5f-120">The $1 and $5 notes are not shown since these amounts are less than the amount due.</span></span>
- <span data-ttu-id="2ae5f-121">**Tutte le denominazioni**: selezionare questa opzione per visualizzare sempre tutte le denominazioni delle banconote nel POS, indipendentemente dall'importo dovuto.</span><span class="sxs-lookup"><span data-stu-id="2ae5f-121">**All denominations** – Select this option to always show all note denominations in POS, regardless of the amount due.</span></span> <span data-ttu-id="2ae5f-122">In tal modo, l'utente può utilizzare una combinazione di banconote per ottenere l'importo dovuto.</span><span class="sxs-lookup"><span data-stu-id="2ae5f-122">This means that the user can use a combination of notes to reach the amount due.</span></span> <span data-ttu-id="2ae5f-123">Ad esempio, se l'importo dovuto è 25 USD, l'utente può scegliere 20 USD e 5 USD per completare la vendita.</span><span class="sxs-lookup"><span data-stu-id="2ae5f-123">For example, if the amount due is $25.00, the user can choose $20 and $5 to complete the sale.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]