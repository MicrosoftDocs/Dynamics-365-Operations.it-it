---
title: Specifica IVA per report transazione contabile
description: In questo argomento viene spiegato come utilizzare il report Specifica IVA per transazione contabile per visualizzare e stampare informazioni sulle transazioni contabili per le quali viene calcolata l'IVA.
author: ericwang
ms.date: 08/19/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TaxTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2019-08-19
ms.dyn365.ops.version: 10.0.6
ms.openlocfilehash: 75913edcbac0151d5d27d866ff5430b194c62738
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5815262"
---
# <a name="sales-tax-specification-by-ledger-transaction-report"></a><span data-ttu-id="4511b-103">Specifica IVA per report transazione contabile</span><span class="sxs-lookup"><span data-stu-id="4511b-103">Sales tax specification by ledger transaction report</span></span>
[!include [banner](../includes/banner.md)]

<span data-ttu-id="4511b-104">In questo argomento viene spiegato come utilizzare il report **Specifica IVA per transazione contabile** per visualizzare e stampare informazioni sulle transazioni contabili per le quali viene calcolata l'IVA.</span><span class="sxs-lookup"><span data-stu-id="4511b-104">This topic explains how to use the **Sales tax specification by ledger transaction** report to view and print information about ledger transactions that sales tax is calculated for.</span></span>

## <a name="tax-accounts-vs-non-tax-accounts"></a><span data-ttu-id="4511b-105">Conti fiscali e conti non fiscali</span><span class="sxs-lookup"><span data-stu-id="4511b-105">Tax accounts vs. non-tax accounts</span></span>

<span data-ttu-id="4511b-106">Nel report **Specifica IVA per transazione contabile** sono presenti le transazioni IVA per i conti fiscali e conti non fiscali.</span><span class="sxs-lookup"><span data-stu-id="4511b-106">The **Sales tax specification by ledger transaction** report shows tax transactions for both tax accounts and non-tax accounts.</span></span> <span data-ttu-id="4511b-107">Questi conti vengono classificati nel seguente modo:</span><span class="sxs-lookup"><span data-stu-id="4511b-107">These accounts are categorized in the following way:</span></span>

- <span data-ttu-id="4511b-108">**Conto fiscale** - Un conto viene considerato conto fiscale quando viene registrata una transazione IVA e il conto principale nella riga giornale di registrazione **IVA** è un conto fiscale, ad esempio un conto IVA a debito o un conto IVA a credito.</span><span class="sxs-lookup"><span data-stu-id="4511b-108">**Tax account** – An account is considered a tax account when a tax transaction is posted, and the main account on the **Sales Tax** journal line is a tax account, such as a sales tax payable account or a sales tax receivable account.</span></span>
- <span data-ttu-id="4511b-109">**Conto non fiscale** - Un conto viene considerato conto non fiscale quando viene registrata una transazione IVA e il conto principale nella transazione originale è un conto non fiscale, ad esempio un conto ricavi o un conto spese.</span><span class="sxs-lookup"><span data-stu-id="4511b-109">**Non-tax account** – An account is considered a non-tax account when a tax transaction is posted, and the main account on the original transaction is a non-tax account, such as a revenue account or an expense account.</span></span>

<span data-ttu-id="4511b-110">Per i conti IVA, le colonne **Origine**, **IVA a credito** e **IVA a debito** del report mostrano **0** (zero).</span><span class="sxs-lookup"><span data-stu-id="4511b-110">For tax accounts, the **Origin**, **Sales tax receivable**, and **Sales tax payable** columns on the report show **0** (zero).</span></span> <span data-ttu-id="4511b-111">Per i conti non fiscali, in queste colonne sono riportati gli importi.</span><span class="sxs-lookup"><span data-stu-id="4511b-111">For non-tax accounts, those columns show amounts.</span></span>

## <a name="filtering-the-data-on-the-report"></a><span data-ttu-id="4511b-112">Filtrare i dati nel report</span><span class="sxs-lookup"><span data-stu-id="4511b-112">Filtering the data on the report</span></span>

<span data-ttu-id="4511b-113">Quando si genera il report, sono disponibili i seguenti campi predefiniti.</span><span class="sxs-lookup"><span data-stu-id="4511b-113">When you generate the report, the following default fields are available.</span></span> <span data-ttu-id="4511b-114">È possibile utilizzare questi campi per filtrare i dati visualizzati nel report.</span><span class="sxs-lookup"><span data-stu-id="4511b-114">You can use these fields to filter the data that is shown on the report.</span></span>

| <span data-ttu-id="4511b-115">Campo</span><span class="sxs-lookup"><span data-stu-id="4511b-115">Field</span></span>                      | <span data-ttu-id="4511b-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4511b-116">Description</span></span> |
|----------------------------|-------------|
| <span data-ttu-id="4511b-117">Data</span><span class="sxs-lookup"><span data-stu-id="4511b-117">Date</span></span>                       | <span data-ttu-id="4511b-118">Utilizzare i campi nelle sezioni **A** e **Da** per definire un intervallo di date per le transazioni IVA.</span><span class="sxs-lookup"><span data-stu-id="4511b-118">Use the fields in the **From** and **To** sections to define a date range for the tax transactions.</span></span> |
| <span data-ttu-id="4511b-119">Conto principale</span><span class="sxs-lookup"><span data-stu-id="4511b-119">Main account</span></span>               | <span data-ttu-id="4511b-120">Utilizzare i campi nelle sezioni **A** e **Da** per definire un intervallo di conti principali.</span><span class="sxs-lookup"><span data-stu-id="4511b-120">Use the fields in the **From** and **To** sections to define a range of main accounts.</span></span> |
| <span data-ttu-id="4511b-121">Codice IVA</span><span class="sxs-lookup"><span data-stu-id="4511b-121">Sales tax code</span></span>             | <span data-ttu-id="4511b-122">Utilizzare i campi nelle sezioni **A** e **Da** per definire un intervallo di codici IVA.</span><span class="sxs-lookup"><span data-stu-id="4511b-122">Use the fields in the **From** and **To** sections to define a range of sales tax codes.</span></span> |
| <span data-ttu-id="4511b-123">Raggruppamento</span><span class="sxs-lookup"><span data-stu-id="4511b-123">Grouping</span></span>                   | <span data-ttu-id="4511b-124">Specificare se il report deve essere raggruppato per conto CoGe o codice IVA.</span><span class="sxs-lookup"><span data-stu-id="4511b-124">Select whether the report should be grouped by ledger account or sales tax code.</span></span> |
| <span data-ttu-id="4511b-125">Subtotale per codice IVA</span><span class="sxs-lookup"><span data-stu-id="4511b-125">Subtotal by sales tax code</span></span> | <span data-ttu-id="4511b-126">Impostare questa opzione su **Sì** per visualizzare i subtotali per codice IVA.</span><span class="sxs-lookup"><span data-stu-id="4511b-126">Set this option to **Yes** to show subtotals by sales tax code.</span></span> |
| <span data-ttu-id="4511b-127">Solo totali</span><span class="sxs-lookup"><span data-stu-id="4511b-127">Totals only</span></span>                | <span data-ttu-id="4511b-128">Impostare questa opzione su **Sì** per visualizzare solo i totali.</span><span class="sxs-lookup"><span data-stu-id="4511b-128">Set this option to **Yes** to show only totals.</span></span> |
| <span data-ttu-id="4511b-129">Solo conti principali</span><span class="sxs-lookup"><span data-stu-id="4511b-129">Main accounts only</span></span>         | <span data-ttu-id="4511b-130">Impostare questa opzione su **Sì** per includere nel report solo i conti principali.</span><span class="sxs-lookup"><span data-stu-id="4511b-130">Set this option to **Yes** to include only main accounts on the report.</span></span> |

## <a name="showing-only-non-tax-accounts-on-the-report"></a><span data-ttu-id="4511b-131">Mostrare nel report solo i conti non fiscali</span><span class="sxs-lookup"><span data-stu-id="4511b-131">Showing only non-tax accounts on the report</span></span>

<span data-ttu-id="4511b-132">Per visualizzare solo i conti non fiscali nel report, impostare una condizione di filtro, ad esempio un asterisco (\*), come illustrato nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="4511b-132">To show only non-tax accounts on the report, set up a filter condition, such as an asterisk (\*), as shown in the following illustration.</span></span>

![Report con i conti non fiscali](media/taxspecperledgertrans.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]