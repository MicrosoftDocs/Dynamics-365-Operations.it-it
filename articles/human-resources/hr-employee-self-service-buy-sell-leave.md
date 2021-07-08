---
title: Acquista e vendi congedo
description: In Dynamics 365 Human Resources, è possibile inviare richieste di acquisto e vendita di congedi in base ai criteri di acquisto e vendita stabiliti dalla società.
author: andreabichsel
ms.date: 08/20/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ESSLeaveBuyRequestEntry, EssWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-06-01
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 6d32abacc1539cb930ad6f1ebcfe6fa9af4befcf
ms.sourcegitcommit: dc4898aa32f381620c517bf89c7856e693563ace
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/17/2021
ms.locfileid: "6271489"
---
# <a name="buy-and-sell-leave"></a><span data-ttu-id="9761d-103">Acquista e vendi congedo</span><span class="sxs-lookup"><span data-stu-id="9761d-103">Buy and sell leave</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="9761d-104">In Dynamics 365 Human Resources, è possibile inviare richieste di acquisto e vendita di congedi in base ai criteri di acquisto e vendita stabiliti dalla società.</span><span class="sxs-lookup"><span data-stu-id="9761d-104">In Dynamics 365 Human Resources, you can submit requests to buy and sell leave based on the buy and sell leave policies set up by your company.</span></span>  

## <a name="request-to-buy-leave"></a><span data-ttu-id="9761d-105">Richiesta di acquisto di congedi</span><span class="sxs-lookup"><span data-stu-id="9761d-105">Request to buy leave</span></span>

1. <span data-ttu-id="9761d-106">Nell'area di lavoro **Self-service dipendenti**, seleziona **Richiesta di acquisto di congedi** nel riquadro **Saldi permessi**.</span><span class="sxs-lookup"><span data-stu-id="9761d-106">In the **Employee self service** workspace, select **Buy leave request** in the **Time Off Balances** tile.</span></span> 

2. <span data-ttu-id="9761d-107">Aggiungere un **Tipo di congedo** e immettere una **Quantità** per la quantità di congedi che si desidera acquistare.</span><span class="sxs-lookup"><span data-stu-id="9761d-107">Add a **Leave type** and enter an **Amount** for the amount of leave you'd like to buy.</span></span> 

3. <span data-ttu-id="9761d-108">Selezionare **Invia** quando si è pronti per inviare la richiesta.</span><span class="sxs-lookup"><span data-stu-id="9761d-108">Select **Submit** when you're ready to submit your request.</span></span> 

<span data-ttu-id="9761d-109">I saldi verranno aggiornati automaticamente o verranno sottoposti a un processo di approvazione prima dell'aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="9761d-109">Your balances will either automatically update or go through an approval process before updating.</span></span> <span data-ttu-id="9761d-110">Dipende da come sono stati configurati i criteri di acquisto.</span><span class="sxs-lookup"><span data-stu-id="9761d-110">This depends on how the buy policy has been configured.</span></span>

## <a name="request-to-sell-leave"></a><span data-ttu-id="9761d-111">Richiesta di vendita di congedi</span><span class="sxs-lookup"><span data-stu-id="9761d-111">Request to sell leave</span></span>

1. <span data-ttu-id="9761d-112">Nell'area di lavoro **Self-service dipendenti**, selezionare **Richiesta di vendita di congedi** nel riquadro **Saldi permessi**.</span><span class="sxs-lookup"><span data-stu-id="9761d-112">In the **Employee self service** workspace, select **Sell leave request** in the **Time Off Balances** tile.</span></span> 

2. <span data-ttu-id="9761d-113">Aggiungere un **Tipo di congedo** e immettere una **Quantità** per la quantità di congedi che si desidera vendere.</span><span class="sxs-lookup"><span data-stu-id="9761d-113">Add a **Leave type** and enter an **Amount** for the amount of leave you'd like to sell.</span></span> 

3. <span data-ttu-id="9761d-114">Selezionare **Invia** quando si è pronti per inviare la richiesta.</span><span class="sxs-lookup"><span data-stu-id="9761d-114">Select **Submit** when you're ready to submit your request.</span></span>

<span data-ttu-id="9761d-115">I saldi verranno aggiornati automaticamente o verranno sottoposti a un processo di approvazione prima dell'aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="9761d-115">Your balances will either automatically update or go through an approval process before updating.</span></span> <span data-ttu-id="9761d-116">Dipende da come sono stati configurati i criteri di acquisto.</span><span class="sxs-lookup"><span data-stu-id="9761d-116">This depends on how the buy policy has been configured.</span></span>


## <a name="troubleshooting"></a><span data-ttu-id="9761d-117">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="9761d-117">Troubleshooting</span></span> 

<span data-ttu-id="9761d-118">Se un flusso di lavoro di richiesta per l'acquisto e la vendita di congedi non riesce, gli utenti con il privilegio **EssLeaveBuySellRequestApprover** possono rivedere il registro dei messaggi per tutte le richieste di acquisto e vendita di congedi.</span><span class="sxs-lookup"><span data-stu-id="9761d-118">If a buy or sell leave request workflow fails, users with the **EssLeaveBuySellRequestApprover** privilege can review the message log for all leave buy and sell requests.</span></span> <span data-ttu-id="9761d-119">Per farlo, vai su **Congedo e assenza > Collega > Acquista e vendi richieste di congedo > Registro messaggi** (in alto a sinistra).</span><span class="sxs-lookup"><span data-stu-id="9761d-119">To do this, go to **Leave and absence > Link > Buy and sell leave requests > Message log** (on the upper left).</span></span> <span data-ttu-id="9761d-120">Il **registro messaggi** mostra agli utenti come sono state elaborate le transazioni e la cronologia del flusso di lavoro associata.</span><span class="sxs-lookup"><span data-stu-id="9761d-120">The **Message log** shows users how the transactions were processed and the associated workflow history.</span></span>


## <a name="see-also"></a><span data-ttu-id="9761d-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9761d-121">See also</span></span>

[<span data-ttu-id="9761d-122">Panoramica di congedo e assenza</span><span class="sxs-lookup"><span data-stu-id="9761d-122">Leave and absence overview</span></span>](hr-leave-and-absence-overview.md)</br>
[<span data-ttu-id="9761d-123">Gestire i criteri di acquisto e vendita congedo</span><span class="sxs-lookup"><span data-stu-id="9761d-123">Manage buy and sell leave policies</span></span>](hr-leave-and-absence-manage-buy-and-sell-leave-policies.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
