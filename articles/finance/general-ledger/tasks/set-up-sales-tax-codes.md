---
title: Impostare i codici IVA
description: In questo argomento viene illustrato come impostare i codici IVA in Dynamics 365 Finance.
author: twheeloc
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxTable, TaxData
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 3dad006b486f7cd6714c713a3bd83a95fdf0d2b5
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4444690"
---
# <a name="set-up-sales-tax-codes"></a><span data-ttu-id="3c900-103">Impostare i codici IVA</span><span class="sxs-lookup"><span data-stu-id="3c900-103">Set up sales tax codes</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="3c900-104">In questo argomento viene illustrato come impostare i codici IVA.</span><span class="sxs-lookup"><span data-stu-id="3c900-104">This topic explains how to set up sales tax codes.</span></span> <span data-ttu-id="3c900-105">I codici IVA vengono creati per ogni imposta indiretta che la persona giuridica è obbligata a calcolare, riscuotere e pagare agli uffici IVA.</span><span class="sxs-lookup"><span data-stu-id="3c900-105">Sales tax codes are created for every indirect tax or duty that the legal entity is obligated to calculate, collect, and pay to sales tax authorities.</span></span>

<span data-ttu-id="3c900-106">In questa attività viene utilizzata la società dimostrativa USMF.</span><span class="sxs-lookup"><span data-stu-id="3c900-106">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="3c900-107">Andare a **Pannello di navigazione > Imposta > Imposte indirette > IVA > Codici IVA**.</span><span class="sxs-lookup"><span data-stu-id="3c900-107">Go to **Navigation pane > Tax > Indirect taxes > Sales tax > Sales tax codes**.</span></span>
2. <span data-ttu-id="3c900-108">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="3c900-108">Select **New**.</span></span>
3. <span data-ttu-id="3c900-109">Nel campo **Codice IVA** digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="3c900-109">In the **Sales tax code** field, type a value.</span></span>
4. <span data-ttu-id="3c900-110">Digitare un valore nel campo **Nome**.</span><span class="sxs-lookup"><span data-stu-id="3c900-110">In the **Name** field, type a value.</span></span>
5. <span data-ttu-id="3c900-111">Selezionare un **periodo di liquidazione** aprendo l'elenco a discesa per specificare in che ufficio IVA e in quali intervalli l'IVA deve essere dichiarata e pagata.</span><span class="sxs-lookup"><span data-stu-id="3c900-111">Select a **Settlement period** by opening the pull-down list to specify which Sales tax authority and in which intervals this sales tax needs to be reported and paid.</span></span>
6. <span data-ttu-id="3c900-112">Selezionare un **gruppo di registrazione contabile** per specificare i conti principali per registrare l'IVA nella contabilità generale.</span><span class="sxs-lookup"><span data-stu-id="3c900-112">Select a **Ledger posting group** to specify the main accounts to post sales tax to the general ledger.</span></span>
7. <span data-ttu-id="3c900-113">Espandere la Scheda dettaglio **Calcolo**.</span><span class="sxs-lookup"><span data-stu-id="3c900-113">Expand the **Calculation** FastTab.</span></span> <span data-ttu-id="3c900-114">Sono inclusi più campi che controllano la modalità di calcolo degli importi IVA.</span><span class="sxs-lookup"><span data-stu-id="3c900-114">This includes multiple fields that control how sales tax amounts will be calculated.</span></span> <span data-ttu-id="3c900-115">Completare questi campi in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="3c900-115">Fill these fields out as needed.</span></span>  
8. <span data-ttu-id="3c900-116">Nel **Riquadro azioni** nella parte superiore dell'interfaccia, selezionare **Codice IVA**.</span><span class="sxs-lookup"><span data-stu-id="3c900-116">On the **Action Pane** at the top of the interface, select **Sales tax code**.</span></span>
9. <span data-ttu-id="3c900-117">Selezionare **Valori**.</span><span class="sxs-lookup"><span data-stu-id="3c900-117">Select **Values**.</span></span>
10. <span data-ttu-id="3c900-118">Immettere il valore per questo codice IVA nella colonna **valore**.</span><span class="sxs-lookup"><span data-stu-id="3c900-118">Enter the value for this tax code in the **value** column.</span></span>
    - <span data-ttu-id="3c900-119">Nella Scheda dettaglio **Calcolo**, nel campo Origine, se Importo unitario è selezionato, il valore verrà moltiplicato per la quantità della transazione per calcolare l'importo IVA.</span><span class="sxs-lookup"><span data-stu-id="3c900-119">On the **Calculation** FastTab, in the Origin field, if Amount per unit is selected, the value will be multiplied by the quantity on the transaction to calculate the sales tax amount.</span></span>  <span data-ttu-id="3c900-120">Se il codice IVA non è un'imposta basata sull'unità, il valore è una percentuale applicata all'origine per il codice IVA per calcolare l'importo IVA.</span><span class="sxs-lookup"><span data-stu-id="3c900-120">If the tax code is not a unit based tax, the value is a percentage that is applied on the Origin for this tax code to calculate the sales tax amount.</span></span>     
11. <span data-ttu-id="3c900-121">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="3c900-121">Select **Save**.</span></span>
12. <span data-ttu-id="3c900-122">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="3c900-122">Close the page.</span></span>
13. <span data-ttu-id="3c900-123">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="3c900-123">Select **Save**.</span></span>

