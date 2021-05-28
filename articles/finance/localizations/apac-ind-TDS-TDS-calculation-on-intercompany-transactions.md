---
title: Calcolo della TDS sulle transazioni interaziendali
description: In questo argomento viene descritto il processo utilizzato per calcolare l'imposta dedotta all'origine (TDS) sulle transazioni interaziendali in fasi.
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: 0e304747cc93bfe0a39beababc3182ca14664b11
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023361"
---
# <a name="tds-calculation-on-intercompany-transactions"></a><span data-ttu-id="f2a62-103">Calcolo della TDS sulle transazioni interaziendali</span><span class="sxs-lookup"><span data-stu-id="f2a62-103">TDS calculation on intercompany transactions</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f2a62-104">In questo argomento viene descritto il processo utilizzato per calcolare l'imposta dedotta all'origine (TDS) sulle transazioni interaziendali in fasi.</span><span class="sxs-lookup"><span data-stu-id="f2a62-104">This topic describes the process that is used to calculate Tax Deducted at Source (TDS) on intercompany transactions in phases.</span></span>

<span data-ttu-id="f2a62-105">Quando viene creato un ordine fornitore o un ordine cliente interaziendale, il gruppo TDS predefinito definito per il cliente o il fornitore viene utilizzato per calcolare l'importo TDS.</span><span class="sxs-lookup"><span data-stu-id="f2a62-105">When an intercompany purchase order or sales order is created, the default TDS group that is defined for the customer or vendor is used to calculate the TDS amount.</span></span> <span data-ttu-id="f2a62-106">L'importo TDS viene registrato nei conti fornitori o clienti dopo la registrazione della fattura.</span><span class="sxs-lookup"><span data-stu-id="f2a62-106">The TDS amount is posted to the recoverable or payable accounts after the invoice is posted.</span></span>

<span data-ttu-id="f2a62-107">Un ordine cliente o un ordine fornitore interaziendale viene creato automaticamente per l'ordine fornitore o l'ordine cliente originale.</span><span class="sxs-lookup"><span data-stu-id="f2a62-107">An intercompany sales order or purchase order is automatically created for the original purchase order or sales order.</span></span> <span data-ttu-id="f2a62-108">Il gruppo TDS predefinito viene visualizzato nell'ordine interaziendale, in modo che sia possibile calcolare la TDS.</span><span class="sxs-lookup"><span data-stu-id="f2a62-108">The default TDS group is shown on the intercompany order, so that TDS can be calculated.</span></span> <span data-ttu-id="f2a62-109">Puoi modificare il gruppo TDS.</span><span class="sxs-lookup"><span data-stu-id="f2a62-109">You can change the TDS group.</span></span> <span data-ttu-id="f2a62-110">La fattura può essere registrata solo se l'importo netto della fattura nell'ordine interaziendale creato automaticamente corrisponde all'importo netto della fattura nell'ordine originale</span><span class="sxs-lookup"><span data-stu-id="f2a62-110">The invoice can be posted only if the net invoice amount on the intercompany order that is automatically created matches the net invoice amount on the original order.</span></span> <span data-ttu-id="f2a62-111">(l'importo netto è l'importo della fattura al netto della TDS).</span><span class="sxs-lookup"><span data-stu-id="f2a62-111">(The net amount is the invoice amount after TDS is deducted.)</span></span>

<span data-ttu-id="f2a62-112">Ad esempio, viene creata una fattura di vendita per 50.000 a cui viene associato il gruppo TDS del **10%**.</span><span class="sxs-lookup"><span data-stu-id="f2a62-112">For example, a sales invoice is created for 50,000, and the **10%** TDS group is attached to it.</span></span> <span data-ttu-id="f2a62-113">L'importo della fattura registrato è 45.000 e l'importo TDS registrato per la fattura di vendita è 5.000.</span><span class="sxs-lookup"><span data-stu-id="f2a62-113">The posted invoice amount is 45,000, and the posted TDS amount for the sales invoice is 5,000.</span></span> <span data-ttu-id="f2a62-114">Viene creato automaticamente un ordine di acquisto per l'ordine di vendita interaziendale a cui viene associato il gruppo TDS del **10%**.</span><span class="sxs-lookup"><span data-stu-id="f2a62-114">A purchase order is automatically created for the intercompany sales order, and the  **10%** TDS group is attached to it.</span></span> <span data-ttu-id="f2a62-115">Se selezioni il gruppo TDS del **15%**, non puoi registrare la fattura, poiché l'importo netto della fattura dell'ordine cliente interaziendale creato automaticamente non corrisponde all'importo netto della fattura dell'ordine cliente originale.</span><span class="sxs-lookup"><span data-stu-id="f2a62-115">If you change the TDS group to **15%**, you can't post the invoice, because the net invoice amount of the intercompany sales order that was automatically created doesn't match the net invoice amount of the original sales order.</span></span>

<span data-ttu-id="f2a62-116">Un giornale di registrazione pagamenti creato per una fattura interaziendale viene registrato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="f2a62-116">A payment journal that is created for an intercompany invoice is automatically posted.</span></span> <span data-ttu-id="f2a62-117">Il giornale di registrazione pagamenti può essere registrato solo se il relativo importo del pagamento netto corrisponde all'importo del pagamento netto nel giornale di registrazione pagamenti originale.</span><span class="sxs-lookup"><span data-stu-id="f2a62-117">That payment journal can be posted only if the net payment amount on it matches the net payment amount on the original payment journal.</span></span>
