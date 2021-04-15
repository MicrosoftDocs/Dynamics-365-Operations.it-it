---
title: Utilizzare il Dynamics 365 Commerce motore di determinazione dei prezzi con Dynamics 365 Sales
description: Questo argomento descrive come utilizzare il motore di determinazione dei prezzi Microsoft Dynamics 365 Commerce per creare le offerte di vendita in Dynamics 365 Sales.
author: ShalabhjainMSFT
ms.date: 11/19/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: shajain
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-11-03
ms.openlocfilehash: 364cc5adf0358ffa952750149ad31d62cbd35e87
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5751436"
---
# <a name="use-the-dynamics-365-commerce-pricing-engine-with-dynamics-365-sales"></a><span data-ttu-id="308cf-103">Utilizzare il Dynamics 365 Commerce motore di determinazione dei prezzi con Dynamics 365 Sales</span><span class="sxs-lookup"><span data-stu-id="308cf-103">Use the Dynamics 365 Commerce pricing engine with Dynamics 365 Sales</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="308cf-104">Questo argomento descrive come utilizzare il motore di determinazione dei prezzi Microsoft Dynamics 365 Commerce per creare le offerte di vendita in Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="308cf-104">This topic describes how to use the Microsoft Dynamics 365 Commerce pricing engine to create sales quotations in Dynamics 365 Sales.</span></span>

<span data-ttu-id="308cf-105">Il Dynamics 365 Commerce Il motore di determinazione dei prezzi supporta la maggior parte degli scenari di prezzo business-to-consumer (B2C), come i prezzi a livello di negozio, i prezzi basati sull'affiliazione e sulla fedeltà, gli sconti combinati, gli sconti sulla quantità e gli sconti soglia.</span><span class="sxs-lookup"><span data-stu-id="308cf-105">The Dynamics 365 Commerce pricing engine supports most business-to-consumer (B2C) pricing scenarios, such as store-level pricing, affiliation-based and loyalty-based pricing, mix-and-match discounts, quantity discounts, and threshold discounts.</span></span> <span data-ttu-id="308cf-106">Il motore di determinazione del prezzo utilizza regole complesse per determinare il prezzo migliore per un determinato preventivo od ordine.</span><span class="sxs-lookup"><span data-stu-id="308cf-106">The pricing engine uses complex rules to determine the best price for a given quotation or order.</span></span>

<span data-ttu-id="308cf-107">Quando usi la [doppia scrittura](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-overview), hai tre opzioni per le tue esigenze di prezzo.</span><span class="sxs-lookup"><span data-stu-id="308cf-107">When you use [dual-write](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-overview), you have three options for your pricing needs.</span></span> <span data-ttu-id="308cf-108">Puoi utilizzare il prezzo statico che proviene dal listino prezzi in Dynamics 365 Sales, il motore dei prezzi in Dynamics 365 Supply Chain Management o il motore di determinazione dei prezzi in Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="308cf-108">You can use the static pricing that comes from the price list in Dynamics 365 Sales, the pricing engine in Dynamics 365 Supply Chain Management, or the pricing engine in Dynamics 365 Commerce.</span></span> <span data-ttu-id="308cf-109">Tra queste opzioni, il motore di determinazione dei prezzi di Commerce è più adatto agli scenari B2C.</span><span class="sxs-lookup"><span data-stu-id="308cf-109">Among these options, the Commerce pricing engine is best suited to B2C scenarios.</span></span>

## <a name="use-the-commerce-pricing-engine-in-sales"></a><span data-ttu-id="308cf-110">Utilizza il motore di determinazione dei prezzi di Commerce in Sales</span><span class="sxs-lookup"><span data-stu-id="308cf-110">Use the Commerce pricing engine in Sales</span></span>

> [!NOTE]
> <span data-ttu-id="308cf-111">Attualmente, il motore di determinazione dei prezzi di Commerce può essere utilizzato solo per la creazione delle offerte in Sales.</span><span class="sxs-lookup"><span data-stu-id="308cf-111">Currently, the Commerce pricing engine can be used only for quotation creation in the Sales.</span></span> <span data-ttu-id="308cf-112">L'integrazione dell'ordine del cliente con il motore di determinazione dei prezzi di Commerce non è ancora disponibile.</span><span class="sxs-lookup"><span data-stu-id="308cf-112">Sales order integration with the Commerce pricing engine isn't yet available.</span></span>

<span data-ttu-id="308cf-113">Quando gli utenti avviano un'offerta in Sales, il framework a doppia scrittura copia i dettagli dell'offerta in Commerce.</span><span class="sxs-lookup"><span data-stu-id="308cf-113">When users initiate a quotation in Sales, the dual-write framework copies the quotation details to Commerce.</span></span> <span data-ttu-id="308cf-114">Eventuali modifiche alle righe di offerta esistenti o alle righe di offerta appena aggiunte in Sales vengono copiate in Commerce.</span><span class="sxs-lookup"><span data-stu-id="308cf-114">Any changes to existing quotation lines or any newly added quotation lines in Sales are copied to Commerce.</span></span> <span data-ttu-id="308cf-115">Quando gli utenti desiderano utilizzare il motore di determinazione dei prezzi di Commerce per quotare l'offerta, possono selezionare **Preventivo** per aggiornare i prezzi dell'offerta, in base al motore di determinazione dei prezzi di Commerce.</span><span class="sxs-lookup"><span data-stu-id="308cf-115">When users want to use the Commerce pricing engine to price the quotation, they can select **Price quote** to update the prices of the quotation, based on the Commerce pricing engine.</span></span> <span data-ttu-id="308cf-116">I prezzi vengono quindi aggiornati automaticamente sia in Sales che in Commerce.</span><span class="sxs-lookup"><span data-stu-id="308cf-116">Prices are then automatically updated in both Sales and Commerce.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="308cf-117">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="308cf-117">Prerequisites</span></span>

- <span data-ttu-id="308cf-118">Prima di poter utilizzare il motore di determinazione dei prezzi di Commerce in Sales, è necessario seguire i passaggi in [Prospetto per uno scenario di liquidazione in doppia scrittura](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-prospect-to-cash/).</span><span class="sxs-lookup"><span data-stu-id="308cf-118">Before you can use the Commerce pricing engine in Sales, you must follow the steps in [Prospect-to-cash in dual-write](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-prospect-to-cash/).</span></span>
- <span data-ttu-id="308cf-119">È necessario disattivare la valutazione dell'accordo commerciale per l'inserimento manuale seguendo questi passaggi:</span><span class="sxs-lookup"><span data-stu-id="308cf-119">You must turn off trade agreement evaluation for manual entry by following these steps:</span></span>

    1. <span data-ttu-id="308cf-120">Nell'ambiente Commerce, andare a **Contabilità clienti \> Impostazioni \> Parametri contabilità clienti**.</span><span class="sxs-lookup"><span data-stu-id="308cf-120">In your Commerce environment, go to **Accounts receivable \> Setup \> Accounts receivable parameters**.</span></span>
    1. <span data-ttu-id="308cf-121">Nella scheda **Prezzi**, nella scheda dettaglio **Valutazione accordi commerciali**, deselezionare la casella di controllo **Inserimento manuale**.</span><span class="sxs-lookup"><span data-stu-id="308cf-121">On the **Prices** tab, on the **Trade agreement evaluation** FastTab, clear the **Manual entry** check box.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="308cf-122">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="308cf-122">Additional resources</span></span>

[<span data-ttu-id="308cf-123">Prospect to cash in doppia scrittura</span><span class="sxs-lookup"><span data-stu-id="308cf-123">Prospect-to-cash in dual-write</span></span>](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-prospect-to-cash/)


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]