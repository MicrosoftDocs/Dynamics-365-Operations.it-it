---
title: Impostare fasce IVA e fasce IVA articoli
description: In questa registrazione attività verrà illustrata l'impostazione dell'IVA e delle fasce IVA articoli.
author: twheeloc
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TaxGroup,  TaxItemGroup
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 844eee7f81c64eb50ada44cbc151c8aa00c5ae98
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5815070"
---
# <a name="set-up-sales-tax-groups-and-item-sales-tax-groups"></a><span data-ttu-id="f40c2-103">Impostare fasce IVA e fasce IVA articoli</span><span class="sxs-lookup"><span data-stu-id="f40c2-103">Set up sales tax groups and item sales tax groups</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="f40c2-104">In questa registrazione attività verrà illustrata l'impostazione dell'IVA e delle fasce IVA articoli.</span><span class="sxs-lookup"><span data-stu-id="f40c2-104">This task recording walks you through the setup of Sales tax and Item sales tax groups.</span></span> <span data-ttu-id="f40c2-105">Le fasce IVA sono gruppi di codici IVA allegati a clienti e fornitori.</span><span class="sxs-lookup"><span data-stu-id="f40c2-105">Sales tax groups are groups of sales tax codes that are attached to customers and vendors.</span></span> <span data-ttu-id="f40c2-106">Vengono anche allegati ai conti CoGe per le transazioni che non vengono registrate per uno specifico fornitore o cliente.</span><span class="sxs-lookup"><span data-stu-id="f40c2-106">They are also attached to ledger accounts for transactions that are not posted to a particular vendor or customer.</span></span>  <span data-ttu-id="f40c2-107">Le fasce IVA articoli sono gruppi di codici IVA collegati alle risorse come i prodotti.</span><span class="sxs-lookup"><span data-stu-id="f40c2-107">Item sales tax groups are groups of sales tax codes that are attached to resources like products.</span></span>  <span data-ttu-id="f40c2-108">Le fasce IVA applicabili a una transazione specifica sono determinate dai codici IVA inclusi nella fascia IVA e nella fascia IVA articoli della transazione.</span><span class="sxs-lookup"><span data-stu-id="f40c2-108">The sales taxes that apply to a particular transaction are determined by the sales tax codes that are included both in the sales tax group and in the item sales tax group of the transaction.</span></span>  <span data-ttu-id="f40c2-109">L'IVA può essere calcolata solo se vengono selezionate una fascia IVA e una fascia IVA articoli per ciascuna transazione per la quale è necessario calcolare o registrare l'IVA.</span><span class="sxs-lookup"><span data-stu-id="f40c2-109">Sales tax can be calculated only if a sales tax group and an item sales tax group are selected for each transaction for which sales tax must be calculated or recorded.</span></span>  

1. <span data-ttu-id="f40c2-110">Andare a **Pannello di navigazione > Moduli > Imposta > Imposte indirette > IVA > Fasce IVA**.</span><span class="sxs-lookup"><span data-stu-id="f40c2-110">Go to **Navigation pane > Modules > Tax > Indirect taxes > Sales tax > Sales tax groups**.</span></span>
2. <span data-ttu-id="f40c2-111">Fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="f40c2-111">Click **New**.</span></span>
3. <span data-ttu-id="f40c2-112">Nel campo **Fascia IVA** digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="f40c2-112">In the **Sales tax group** field, type a value.</span></span>
4. <span data-ttu-id="f40c2-113">Digitare un valore nel campo **Descrizione**</span><span class="sxs-lookup"><span data-stu-id="f40c2-113">In the **Description** field, type a value.</span></span>
5. <span data-ttu-id="f40c2-114">Attiva/disattiva l'espansione della sezione **Impostazione**.</span><span class="sxs-lookup"><span data-stu-id="f40c2-114">Toggle the expansion of the **Setup** section.</span></span>
6. <span data-ttu-id="f40c2-115">Scegliere **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="f40c2-115">Click **Add**.</span></span>
7. <span data-ttu-id="f40c2-116">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="f40c2-116">In the list, mark the selected row.</span></span>
8. <span data-ttu-id="f40c2-117">Nel campo **Codice IVA** fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="f40c2-117">In the **Sales tax code** field, click the drop-down button to open the lookup.</span></span>
9. <span data-ttu-id="f40c2-118">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="f40c2-118">In the list, click the link in the selected row.</span></span>
10. <span data-ttu-id="f40c2-119">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="f40c2-119">Click **Save**.</span></span>
11. <span data-ttu-id="f40c2-120">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="f40c2-120">Close the page.</span></span>
12. <span data-ttu-id="f40c2-121">Passare a **Imposta > Imposte indirette > IVA > Fasce IVA articoli**.</span><span class="sxs-lookup"><span data-stu-id="f40c2-121">Go to **Tax > Indirect taxes > Sales tax > Item sales tax groups**.</span></span>
13. <span data-ttu-id="f40c2-122">Fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="f40c2-122">Click **New**.</span></span>
14. <span data-ttu-id="f40c2-123">Nel campo **Fascia IVA articoli** digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="f40c2-123">In the **Item sales tax group** field, type a value.</span></span>
15. <span data-ttu-id="f40c2-124">Digitare un valore nel campo **Descrizione**</span><span class="sxs-lookup"><span data-stu-id="f40c2-124">In the **Description** field, type a value.</span></span>
16. <span data-ttu-id="f40c2-125">Scegliere **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="f40c2-125">Click **Add**.</span></span>
17. <span data-ttu-id="f40c2-126">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="f40c2-126">In the list, mark the selected row.</span></span>
18. <span data-ttu-id="f40c2-127">Nel campo **Codice IVA** fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="f40c2-127">In the **Sales tax code** field, click the drop-down button to open the lookup.</span></span>
19. <span data-ttu-id="f40c2-128">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="f40c2-128">In the list, click the link in the selected row.</span></span>
20. <span data-ttu-id="f40c2-129">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="f40c2-129">Click **Save**.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]