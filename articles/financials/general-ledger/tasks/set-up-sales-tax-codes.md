--- 
title: Imposta i codici IVA
description: "I codici IVA vengono creati per ogni imposta indiretta che la persona giuridica è obbligata a calcolare, riscuotere e pagare agli uffici IVA."
author: twheeloc
manager: AnnBe
ms.date: 11/14/2016
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
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: 968f4bb9f7d54cdb4de4f7842ed1777c9a9acd64
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---
# <a name="set-up-sales-tax-codes"></a><span data-ttu-id="2e008-103">Imposta i codici IVA</span><span class="sxs-lookup"><span data-stu-id="2e008-103">Set up sales tax codes</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="2e008-104">I codici IVA vengono creati per ogni imposta indiretta che la persona giuridica è obbligata a calcolare, riscuotere e pagare agli uffici IVA.</span><span class="sxs-lookup"><span data-stu-id="2e008-104">Sales tax codes are created for every indirect tax or duty that the legal entity is obligated to calculate, collect, and pay to sales tax authorities.</span></span>

<span data-ttu-id="2e008-105">In questa attività viene utilizzata la società dimostrativa USMF.</span><span class="sxs-lookup"><span data-stu-id="2e008-105">This task uses the USMF demo company.</span></span>



1. <span data-ttu-id="2e008-106">Andare a Imposta > Imposte indirette > IVA > Codici IVA.</span><span class="sxs-lookup"><span data-stu-id="2e008-106">Go to Tax > Indirect taxes > Sales tax > Sales tax codes.</span></span>
2. <span data-ttu-id="2e008-107">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="2e008-107">Click New.</span></span>
3. <span data-ttu-id="2e008-108">Nel campo Codice IVA digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="2e008-108">In the Sales tax code field, type a value.</span></span>
4. <span data-ttu-id="2e008-109">Digitare un valore nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="2e008-109">In the Name field, type a value.</span></span>
5. <span data-ttu-id="2e008-110">Selezionare un periodo di liquidazione per specificare in che ufficio IVA e in quali intervalli l'IVA deve essere dichiarata e pagata.</span><span class="sxs-lookup"><span data-stu-id="2e008-110">Select a Settlement period to specify which Sales tax authority and in which intervals this sales tax needs to be reported and paid.</span></span>
6. <span data-ttu-id="2e008-111">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="2e008-111">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="2e008-112">Selezionare un gruppo di registrazione contabile per specificare i conti principali per registrare l'IVA nella contabilità generale.</span><span class="sxs-lookup"><span data-stu-id="2e008-112">Select a Ledger posting group to specify the main accounts to post sales tax to the general ledger.</span></span>
8. <span data-ttu-id="2e008-113">Trovare e selezionare il record desiderato nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="2e008-113">In the list, find and select the desired record.</span></span>
9. <span data-ttu-id="2e008-114">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="2e008-114">In the list, click the link in the selected row.</span></span>
10. <span data-ttu-id="2e008-115">Espandere la Scheda dettaglio Calcolo.</span><span class="sxs-lookup"><span data-stu-id="2e008-115">Expand the Calculation FastTab.</span></span>
    * <span data-ttu-id="2e008-116">La Scheda dettaglio Calcolo presenta più campi che controllano la modalità di calcolo degli importi VAT.</span><span class="sxs-lookup"><span data-stu-id="2e008-116">The Calculation FastTab has multiple fields that control how sales tax amounts will be calculated.</span></span>  
11. <span data-ttu-id="2e008-117">Nel riquadro azioni, fare clic su Codice IVA.</span><span class="sxs-lookup"><span data-stu-id="2e008-117">On the Action Pane, click Sales tax code.</span></span>
12. <span data-ttu-id="2e008-118">Fare clic su Valori.</span><span class="sxs-lookup"><span data-stu-id="2e008-118">Click Values.</span></span>
13. <span data-ttu-id="2e008-119">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="2e008-119">In the list, mark the selected row.</span></span>
14. <span data-ttu-id="2e008-120">Immettere il valore per il codice imposta.</span><span class="sxs-lookup"><span data-stu-id="2e008-120">Enter the value for this tax code.</span></span>
    * <span data-ttu-id="2e008-121">Nella Scheda dettaglio Calcolo, nel campo Origine, se Importo unitario è selezionato, il valore verrà moltiplicato per la quantità della transazione per calcolare l'importo IVA.</span><span class="sxs-lookup"><span data-stu-id="2e008-121">On the Calculation FastTab, in the Origin field, if Amount per unit is selected, the value will be multiplied by the quantity on the transaction to calculate the sales tax amount.</span></span>  <span data-ttu-id="2e008-122">Se il codice IVA non è un'imposta basata sull'unità, il valore è una percentuale applicata all'origine per il codice IVA per calcolare l'importo IVA.</span><span class="sxs-lookup"><span data-stu-id="2e008-122">If the tax code is not a unit based tax, the value is a percentage that is applied on the Origin for this tax code to calculate the sales tax amount.</span></span>     
15. <span data-ttu-id="2e008-123">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="2e008-123">Click Save.</span></span>
16. <span data-ttu-id="2e008-124">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="2e008-124">Close the page.</span></span>
17. <span data-ttu-id="2e008-125">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="2e008-125">Click Save.</span></span>


