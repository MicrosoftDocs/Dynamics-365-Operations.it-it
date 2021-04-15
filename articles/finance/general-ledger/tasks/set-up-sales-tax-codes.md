---
title: Impostare i codici IVA
description: In questo argomento viene illustrato come impostare i codici IVA in Dynamics 365 Finance.
author: twheeloc
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TaxTable, TaxData
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 6c7208fa65905fcc902d9c08b5b90178745e76d4
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5815046"
---
# <a name="set-up-sales-tax-codes"></a><span data-ttu-id="5adc7-103">Impostare i codici IVA</span><span class="sxs-lookup"><span data-stu-id="5adc7-103">Set up sales tax codes</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="5adc7-104">In questo argomento viene illustrato come impostare i codici IVA.</span><span class="sxs-lookup"><span data-stu-id="5adc7-104">This topic explains how to set up sales tax codes.</span></span> <span data-ttu-id="5adc7-105">I codici IVA vengono creati per ogni imposta indiretta che la persona giuridica è obbligata a calcolare, riscuotere e pagare agli uffici IVA.</span><span class="sxs-lookup"><span data-stu-id="5adc7-105">Sales tax codes are created for every indirect tax or duty that the legal entity is obligated to calculate, collect, and pay to sales tax authorities.</span></span>

<span data-ttu-id="5adc7-106">In questa attività viene utilizzata la società dimostrativa USMF.</span><span class="sxs-lookup"><span data-stu-id="5adc7-106">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="5adc7-107">Andare a **Pannello di navigazione > Imposta > Imposte indirette > IVA > Codici IVA**.</span><span class="sxs-lookup"><span data-stu-id="5adc7-107">Go to **Navigation pane > Tax > Indirect taxes > Sales tax > Sales tax codes**.</span></span>
2. <span data-ttu-id="5adc7-108">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="5adc7-108">Select **New**.</span></span>
3. <span data-ttu-id="5adc7-109">Nel campo **Codice IVA** digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="5adc7-109">In the **Sales tax code** field, type a value.</span></span>
4. <span data-ttu-id="5adc7-110">Digitare un valore nel campo **Nome**.</span><span class="sxs-lookup"><span data-stu-id="5adc7-110">In the **Name** field, type a value.</span></span>
5. <span data-ttu-id="5adc7-111">Selezionare un **periodo di liquidazione** aprendo l'elenco a discesa per specificare in che ufficio IVA e in quali intervalli l'IVA deve essere dichiarata e pagata.</span><span class="sxs-lookup"><span data-stu-id="5adc7-111">Select a **Settlement period** by opening the pull-down list to specify which Sales tax authority and in which intervals this sales tax needs to be reported and paid.</span></span>
6. <span data-ttu-id="5adc7-112">Selezionare un **gruppo di registrazione contabile** per specificare i conti principali per registrare l'IVA nella contabilità generale.</span><span class="sxs-lookup"><span data-stu-id="5adc7-112">Select a **Ledger posting group** to specify the main accounts to post sales tax to the general ledger.</span></span>
7. <span data-ttu-id="5adc7-113">Espandere la Scheda dettaglio **Calcolo**.</span><span class="sxs-lookup"><span data-stu-id="5adc7-113">Expand the **Calculation** FastTab.</span></span> <span data-ttu-id="5adc7-114">Sono inclusi più campi che controllano la modalità di calcolo degli importi IVA.</span><span class="sxs-lookup"><span data-stu-id="5adc7-114">This includes multiple fields that control how sales tax amounts will be calculated.</span></span> <span data-ttu-id="5adc7-115">Completare questi campi in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="5adc7-115">Fill these fields out as needed.</span></span>  
8. <span data-ttu-id="5adc7-116">Nel **Riquadro azioni** nella parte superiore dell'interfaccia, selezionare **Codice IVA**.</span><span class="sxs-lookup"><span data-stu-id="5adc7-116">On the **Action Pane** at the top of the interface, select **Sales tax code**.</span></span>
9. <span data-ttu-id="5adc7-117">Selezionare **Valori**.</span><span class="sxs-lookup"><span data-stu-id="5adc7-117">Select **Values**.</span></span>
10. <span data-ttu-id="5adc7-118">Immettere il valore per questo codice IVA nella colonna **valore**.</span><span class="sxs-lookup"><span data-stu-id="5adc7-118">Enter the value for this tax code in the **value** column.</span></span>
    - <span data-ttu-id="5adc7-119">Nella Scheda dettaglio **Calcolo**, nel campo Origine, se Importo unitario è selezionato, il valore verrà moltiplicato per la quantità della transazione per calcolare l'importo IVA.</span><span class="sxs-lookup"><span data-stu-id="5adc7-119">On the **Calculation** FastTab, in the Origin field, if Amount per unit is selected, the value will be multiplied by the quantity on the transaction to calculate the sales tax amount.</span></span>  <span data-ttu-id="5adc7-120">Se il codice IVA non è un'imposta basata sull'unità, il valore è una percentuale applicata all'origine per il codice IVA per calcolare l'importo IVA.</span><span class="sxs-lookup"><span data-stu-id="5adc7-120">If the tax code is not a unit based tax, the value is a percentage that is applied on the Origin for this tax code to calculate the sales tax amount.</span></span>     
11. <span data-ttu-id="5adc7-121">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="5adc7-121">Select **Save**.</span></span>
12. <span data-ttu-id="5adc7-122">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="5adc7-122">Close the page.</span></span>
13. <span data-ttu-id="5adc7-123">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="5adc7-123">Select **Save**.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]