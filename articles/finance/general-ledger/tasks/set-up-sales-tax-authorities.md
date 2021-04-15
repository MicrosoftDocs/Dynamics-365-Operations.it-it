---
title: Impostazione degli uffici IVA
description: Gli uffici IVA sono entità in cui l'IVA deve essere dichiarata e pagata.
author: twheeloc
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TaxAuthority
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 160b2507b7ca14ebab54b4775f29615c4aa5f8e0
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5815094"
---
# <a name="set-up-sales-tax-authorities"></a><span data-ttu-id="9ea93-103">Impostazione degli uffici IVA</span><span class="sxs-lookup"><span data-stu-id="9ea93-103">Set up sales tax authorities</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="9ea93-104">Gli uffici IVA sono entità in cui l'IVA deve essere dichiarata e pagata.</span><span class="sxs-lookup"><span data-stu-id="9ea93-104">Sales tax authorities are entities to which collected sales tax needs to be reported and paid.</span></span> <span data-ttu-id="9ea93-105">È possibile pagare l'IVA all'ufficio direttamente o tramite un conto fornitore creato per l'ufficio IVA.</span><span class="sxs-lookup"><span data-stu-id="9ea93-105">You can pay sales taxes to the authority directly or through a vendor account that you create for the sales tax authority.</span></span> <span data-ttu-id="9ea93-106">In questo caso la società potrà utilizzare la routine di pagamento abituale per effettuare il pagamento all'ufficio IVA entro i termini previsti.</span><span class="sxs-lookup"><span data-stu-id="9ea93-106">If you do this, the company can use its usual payment routines to pay the sales tax authority on time.</span></span> <span data-ttu-id="9ea93-107">Se non si imposta l'ufficio IVA come fornitore, sarà necessario preparare un pagamento manuale per l'ufficio IVA nella data di scadenza appropriata.</span><span class="sxs-lookup"><span data-stu-id="9ea93-107">If you do not set up the tax authority as a vendor, someone must prepare a manual payment to the tax authority on the appropriate due date.</span></span> <span data-ttu-id="9ea93-108">In questa attività viene utilizzata la società dimostrativa USMF.</span><span class="sxs-lookup"><span data-stu-id="9ea93-108">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="9ea93-109">Andare a Imposta > Imposte indirette > IVA > Uffici IVA.</span><span class="sxs-lookup"><span data-stu-id="9ea93-109">Go to Tax > Indirect taxes > Sales tax > Sales tax authorities.</span></span>
2. <span data-ttu-id="9ea93-110">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="9ea93-110">Click New.</span></span>
3. <span data-ttu-id="9ea93-111">Digitare un valore nel campo Ufficio.</span><span class="sxs-lookup"><span data-stu-id="9ea93-111">In the Authority field, type a value.</span></span>
4. <span data-ttu-id="9ea93-112">Digitare un valore nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="9ea93-112">In the Name field, type a value.</span></span>
5. <span data-ttu-id="9ea93-113">Nel campo Conto fornitore fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="9ea93-113">In the Vendor account field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="9ea93-114">Trovare e selezionare il record desiderato nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="9ea93-114">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="9ea93-115">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="9ea93-115">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="9ea93-116">Selezionare il layout del report per il paese, se disponibile.</span><span class="sxs-lookup"><span data-stu-id="9ea93-116">Select the report layout for your country/region, if one is available.</span></span> <span data-ttu-id="9ea93-117">Se i layout del report non corrispondono ai requisiti dell'ufficio IVA, utilizzare il layout predefinito.</span><span class="sxs-lookup"><span data-stu-id="9ea93-117">If the report layouts do not correspond to the requirements of the sales tax authority, use default layout.</span></span>
9. <span data-ttu-id="9ea93-118">Immettere i valori nei campi Tipo di arrotondamento e Arrotondamento per specificare come l'importo totale IVA da pagare deve essere arrotondato.</span><span class="sxs-lookup"><span data-stu-id="9ea93-118">Enter values in the Rounding form and the Round-off fields to specify how the tax total amount to be paid should be rounded.</span></span> <span data-ttu-id="9ea93-119">Tutte le differenze di arrotondamento verranno registrate nei conti per l'impostazione di transazioni automatiche nella contabilità generale.</span><span class="sxs-lookup"><span data-stu-id="9ea93-119">Any rounding differences will be posted to Accounts for automatic transactions set up in General ledger.</span></span>
10. <span data-ttu-id="9ea93-120">Immettere un numero nel campo Arrotondamento.</span><span class="sxs-lookup"><span data-stu-id="9ea93-120">In the Round-off field, enter a number.</span></span>
11. <span data-ttu-id="9ea93-121">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="9ea93-121">Click Save.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]