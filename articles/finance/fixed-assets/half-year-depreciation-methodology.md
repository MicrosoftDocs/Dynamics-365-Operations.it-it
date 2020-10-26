---
title: Metodologia della convenzione di ammortamento semestrale
description: In questo argomento viene descritto il metodo utilizzato dai cespiti per calcolare l'ammortamento utilizzando la convenzione semestrale, che calcola sei mesi di ammortamento durante il primo e l'ultimo anno di utilizzo di un cespite.
author: moaamer
manager: Ann Beebe
ms.date: 08/17/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxTable
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations, Retail
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2019-08-17
ms.dyn365.ops.version: 10.0.12
ms.openlocfilehash: 55fb03cf08d8ec042aa8fb37fd1fb858d98279b1
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/10/2020
ms.locfileid: "3977241"
---
# <a name="half-year-depreciation-convention-methodology"></a><span data-ttu-id="38da6-103">Metodologia della convenzione di ammortamento semestrale</span><span class="sxs-lookup"><span data-stu-id="38da6-103">Half-year depreciation convention methodology</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="38da6-104">In questo argomento viene descritto il metodo utilizzato nei cespiti per calcolare l'ammortamento utilizzando la convenzione semestrale.</span><span class="sxs-lookup"><span data-stu-id="38da6-104">This topic describes the method that is used in fixed assets to calculate depreciation using the half-year convention.</span></span> <span data-ttu-id="38da6-105">La convenzione semestrale calcola sei mesi di ammortamento durante il primo e l'ultimo anno di utilizzo di un cespite.</span><span class="sxs-lookup"><span data-stu-id="38da6-105">The half-year convention calculates six months of depreciation during an asset’s first and last year of service.</span></span> <span data-ttu-id="38da6-106">Per ulteriori informazioni sulle convenzioni di ammortamento, vedere [Metodi e convenzioni di ammortamento](Fixed-asset-depreciation-conventions.md).</span><span class="sxs-lookup"><span data-stu-id="38da6-106">For more information about depreciation conventions, see [Depreciation methods and conventions](Fixed-asset-depreciation-conventions.md).</span></span> 

<span data-ttu-id="38da6-107">Quando si utilizza la convenzione di ammortamento semestrale, il sistema utilizza l'anno di acquisizione o l'anno in cui il cespite è stato messo in uso, quindi calcola cinque anni di ammortamento da quell'anno e aggiunge sei mesi.</span><span class="sxs-lookup"><span data-stu-id="38da6-107">When you use the six-month depreciation convention, the system uses the acquisition year or the year that the asset was placed in service, then calculates five years of depreciation from that year, and then adds six months.</span></span> <span data-ttu-id="38da6-108">Per illustrare questo processo, si consideri un cespite che è stato acquistato al prezzo di 50.000 e messo in uso nell'aprile 2020.</span><span class="sxs-lookup"><span data-stu-id="38da6-108">To illustrate this process, consider an asset that was acquired for the price of 50,000, and placed in service in April 2020.</span></span> <span data-ttu-id="38da6-109">Si supponga inoltre che il cespite abbia una durata di utilizzo di cinque anni.</span><span class="sxs-lookup"><span data-stu-id="38da6-109">Also assume that the asset has a five-year service life.</span></span>

<span data-ttu-id="38da6-110">Il primo anno di utilizzo si concluderà a dicembre 2020, il che significa che la fine della vita utile di cinque anni del cespite sarà dicembre 2024.</span><span class="sxs-lookup"><span data-stu-id="38da6-110">The first year of service will conclude in December 2020, which means the end of the asset’s five-year service life will be December 2024.</span></span> <span data-ttu-id="38da6-111">La convenzione sull'ammortamento semestrale aggiungerà sei mesi alla vita del cespite, il che significa che la sua vita utile terminerà nel giugno 2025.</span><span class="sxs-lookup"><span data-stu-id="38da6-111">The half-year depreciation convention will add six months to the asset’s life, which means its service life will end in June 2025.</span></span> 

> <span data-ttu-id="38da6-112">Ammortamento annuale 50.000/5 = 10.000 ammortamento mensile 10.000/12 = 833,33</span><span class="sxs-lookup"><span data-stu-id="38da6-112">Yearly depreciation 50,000/5 = 10,000 monthly depreciation 10,000/12 = 833.33</span></span> <br>
> <span data-ttu-id="38da6-113">Ammortamento primo anno 10.000/2 = 5.000 e successivo ammortamento mensile 5.000/9 = 555,56</span><span class="sxs-lookup"><span data-stu-id="38da6-113">First year depreciation 10,000/2 = 5,000  and the subsequent monthly depreciation 5,000/9 = 555.56</span></span>

   <span data-ttu-id="38da6-114">[![Piano di ammortamento per convenzione di ammortamento semestrale](./media/half-yr-dprectn-cnvntn.png)](./media/half-yr-dprectn-cnvntn.png)</span><span class="sxs-lookup"><span data-stu-id="38da6-114">[![Depreciation schedule for half-year depreciation convention](./media/half-yr-dprectn-cnvntn.png)](./media/half-yr-dprectn-cnvntn.png)</span></span>

<span data-ttu-id="38da6-115">I periodi di ammortamento estesi aggiunti dalla convenzione semestrale forniscono un'allocazione più accurata dell'ammortamento.</span><span class="sxs-lookup"><span data-stu-id="38da6-115">The extended depreciation periods that are added by the half-year convention provide more accurate allocation of depreciation.</span></span> <span data-ttu-id="38da6-116">La convenzione semestrale rappresenta le spese di ammortamento in modo più equo, utile per la rendicontazione del conto economico.</span><span class="sxs-lookup"><span data-stu-id="38da6-116">The six-month convention represents depreciation expenses more equally, which is useful for reporting on the profit and loss statement.</span></span>
