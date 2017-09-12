--- 
title: Creare un pagamento IVA
description: Il processo di liquidazione e registrazione liquida i saldi IVA nei conti IVA e li registra in contropartita nel conto di liquidazione IVA per un periodo specifico.
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
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 6ee84da7fd055c8b0b50c43f134c0fc048ecfaeb
ms.contentlocale: it-it
ms.lasthandoff: 08/29/2017

---
# <a name="create-a-sales-tax-payment"></a><span data-ttu-id="0163a-103">Creare un pagamento IVA</span><span class="sxs-lookup"><span data-stu-id="0163a-103">Create a sales tax payment</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="0163a-104">Il processo di liquidazione e registrazione liquida i saldi IVA nei conti IVA e li registra in contropartita nel conto di liquidazione IVA per un periodo specifico.</span><span class="sxs-lookup"><span data-stu-id="0163a-104">The settle and post sales tax job settles sales tax balances on the sales tax accounts and offsets them to the sales tax settlement account for a given period.</span></span>

1. <span data-ttu-id="0163a-105">Passare a Imposta > Dichiarazioni > IVA > Liquida e registra IVA.</span><span class="sxs-lookup"><span data-stu-id="0163a-105">Go to Tax > Declarations > Sales tax > Settle and post sales tax.</span></span>
2. <span data-ttu-id="0163a-106">Nel campo Periodo di liquidazione fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="0163a-106">In the Settlement period field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="0163a-107">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="0163a-107">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="0163a-108">Immettere una data nel campo Dal.</span><span class="sxs-lookup"><span data-stu-id="0163a-108">In the From date field, enter a date.</span></span>
    * <span data-ttu-id="0163a-109">Se l'opzione Includi correzioni non è selezionata nella pagina Parametri di contabilità generale, la liquidazione può essere elaborata per versioni diverse.</span><span class="sxs-lookup"><span data-stu-id="0163a-109">If the Include corrections option is not selected on the General ledger parameters page, the settlement can be processed for different versions.</span></span> <span data-ttu-id="0163a-110">Originale è la prima liquidazione per un intervallo periodico e può essere elaborata una sola volta per un intervallo periodico.</span><span class="sxs-lookup"><span data-stu-id="0163a-110">Original is the first settlement for a period interval and can only processed once for a period interval.</span></span> <span data-ttu-id="0163a-111">Le ultime correzioni sistemeranno le transazioni IVA registrate dopo che la versione originale è stata creata.</span><span class="sxs-lookup"><span data-stu-id="0163a-111">Latest corrections will settle sales tax transactions which have been posted after the original version has been created.</span></span>   
5. <span data-ttu-id="0163a-112">Nel campo Data della transazione immettere una data.</span><span class="sxs-lookup"><span data-stu-id="0163a-112">In the Transaction date field, enter a date.</span></span>
6. <span data-ttu-id="0163a-113">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="0163a-113">Click OK.</span></span>


