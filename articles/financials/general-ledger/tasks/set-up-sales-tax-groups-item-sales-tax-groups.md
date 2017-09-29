--- 
title: Impostare fasce IVA e fasce IVA articoli
description: "In questa registrazione attività verrà illustrata l'impostazione dell'IVA e delle fasce IVA articoli."
author: twheeloc
manager: AnnBe
ms.date: 11/10/2015
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 4d7f1093edcfff65fd466fa8138b1bb5203648b3
ms.contentlocale: it-it
ms.lasthandoff: 08/29/2017

---
# <a name="set-up-sales-tax-groups-and-item-sales-tax-groups"></a><span data-ttu-id="6f62b-103">Impostare fasce IVA e fasce IVA articoli</span><span class="sxs-lookup"><span data-stu-id="6f62b-103">Set up sales tax groups and item sales tax groups</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="6f62b-104">In questa registrazione attività verrà illustrata l'impostazione dell'IVA e delle fasce IVA articoli.</span><span class="sxs-lookup"><span data-stu-id="6f62b-104">This task recording walks you through the setup of Sales tax and Item sales tax groups.</span></span> <span data-ttu-id="6f62b-105">Le fasce IVA sono gruppi di codici IVA allegati a clienti e fornitori.</span><span class="sxs-lookup"><span data-stu-id="6f62b-105">Sales tax groups are groups of sales tax codes that are attached to customers and vendors.</span></span> <span data-ttu-id="6f62b-106">Vengono anche allegati ai conti CoGe per le transazioni che non vengono registrate per uno specifico fornitore o cliente.</span><span class="sxs-lookup"><span data-stu-id="6f62b-106">They are also attached to ledger accounts for transactions that are not posted to a particular vendor or customer.</span></span>  <span data-ttu-id="6f62b-107">Le fasce IVA articoli sono gruppi di codici IVA collegati alle risorse come i prodotti.</span><span class="sxs-lookup"><span data-stu-id="6f62b-107">Item sales tax groups are groups of sales tax codes that are attached to resources like products.</span></span>  <span data-ttu-id="6f62b-108">Le fasce IVA applicabili a una transazione specifica sono determinate dai codici IVA inclusi nella fascia IVA e nella fascia IVA articoli della transazione.</span><span class="sxs-lookup"><span data-stu-id="6f62b-108">The sales taxes that apply to a particular transaction are determined by the sales tax codes that are included both in the sales tax group and in the item sales tax group of the transaction.</span></span>  <span data-ttu-id="6f62b-109">L'IVA può essere calcolata solo se vengono selezionate una fascia IVA e una fascia IVA articoli per ciascuna transazione per la quale è necessario calcolare o registrare l'IVA.</span><span class="sxs-lookup"><span data-stu-id="6f62b-109">Sales tax can be calculated only if a sales tax group and an item sales tax group are selected for each transaction for which sales tax must be calculated or recorded.</span></span>  

1. <span data-ttu-id="6f62b-110">Passare a Imposta > Imposte indirette > IVA > Fasce IVA.</span><span class="sxs-lookup"><span data-stu-id="6f62b-110">Go to Tax > Indirect taxes > Sales tax > Sales tax groups.</span></span>
2. <span data-ttu-id="6f62b-111">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="6f62b-111">Click New.</span></span>
3. <span data-ttu-id="6f62b-112">Nel campo Fascia IVA digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="6f62b-112">In the Sales tax group field, type a value.</span></span>
4. <span data-ttu-id="6f62b-113">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="6f62b-113">In the Description field, type a value.</span></span>
5. <span data-ttu-id="6f62b-114">Attiva/disattiva l'espansione della sezione Impostazione.</span><span class="sxs-lookup"><span data-stu-id="6f62b-114">Toggle the expansion of the Setup section.</span></span>
6. <span data-ttu-id="6f62b-115">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="6f62b-115">Click Add.</span></span>
7. <span data-ttu-id="6f62b-116">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="6f62b-116">In the list, mark the selected row.</span></span>
8. <span data-ttu-id="6f62b-117">Nel campo Codice IVA fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="6f62b-117">In the Sales tax code field, click the drop-down button to open the lookup.</span></span>
9. <span data-ttu-id="6f62b-118">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="6f62b-118">In the list, click the link in the selected row.</span></span>
10. <span data-ttu-id="6f62b-119">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="6f62b-119">Click Save.</span></span>
11. <span data-ttu-id="6f62b-120">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="6f62b-120">Close the page.</span></span>
12. <span data-ttu-id="6f62b-121">Passare a Imposta > Imposte indirette > IVA > Fasce IVA.</span><span class="sxs-lookup"><span data-stu-id="6f62b-121">Go to Tax > Indirect taxes > Sales tax > Item sales tax groups.</span></span>
13. <span data-ttu-id="6f62b-122">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="6f62b-122">Click New.</span></span>
14. <span data-ttu-id="6f62b-123">Nel campo Fascia IVA articoli digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="6f62b-123">In the Item sales tax group field, type a value.</span></span>
15. <span data-ttu-id="6f62b-124">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="6f62b-124">In the Description field, type a value.</span></span>
16. <span data-ttu-id="6f62b-125">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="6f62b-125">Click Add.</span></span>
17. <span data-ttu-id="6f62b-126">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="6f62b-126">In the list, mark the selected row.</span></span>
18. <span data-ttu-id="6f62b-127">Nel campo Codice IVA fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="6f62b-127">In the Sales tax code field, click the drop-down button to open the lookup.</span></span>
19. <span data-ttu-id="6f62b-128">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="6f62b-128">In the list, click the link in the selected row.</span></span>
20. <span data-ttu-id="6f62b-129">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="6f62b-129">Click Save.</span></span>


