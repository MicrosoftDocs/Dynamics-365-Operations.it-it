---
title: Creare un pagamento IVA
description: Il processo di liquidazione e registrazione liquida i saldi IVA nei conti IVA e li registra in contropartita nel conto di liquidazione IVA per un periodo specifico.
author: twheeloc
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: Dialog
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 99059a8e5d6f4bf125266ad2a98cb73751529e6b
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/18/2020
ms.locfileid: "3139925"
---
# <a name="create-a-sales-tax-payment"></a><span data-ttu-id="28c23-103">Creare un pagamento IVA</span><span class="sxs-lookup"><span data-stu-id="28c23-103">Create a sales tax payment</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="28c23-104">Il processo di liquidazione e registrazione liquida i saldi IVA nei conti IVA e li registra in contropartita nel conto di liquidazione IVA per un periodo specifico.</span><span class="sxs-lookup"><span data-stu-id="28c23-104">The settle and post sales tax job settles sales tax balances on the sales tax accounts and offsets them to the sales tax settlement account for a given period.</span></span>

1. <span data-ttu-id="28c23-105">Passare a Imposta > Dichiarazioni > IVA > Liquida e registra IVA.</span><span class="sxs-lookup"><span data-stu-id="28c23-105">Go to Tax > Declarations > Sales tax > Settle and post sales tax.</span></span>
2. <span data-ttu-id="28c23-106">Nel campo Periodo di liquidazione fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="28c23-106">In the Settlement period field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="28c23-107">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="28c23-107">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="28c23-108">Immettere una data nel campo Dal.</span><span class="sxs-lookup"><span data-stu-id="28c23-108">In the From date field, enter a date.</span></span>
    * <span data-ttu-id="28c23-109">Se l'opzione Includi correzioni non è selezionata nella pagina Parametri di contabilità generale, la liquidazione può essere elaborata per versioni diverse.</span><span class="sxs-lookup"><span data-stu-id="28c23-109">If the Include corrections option is not selected on the General ledger parameters page, the settlement can be processed for different versions.</span></span> <span data-ttu-id="28c23-110">Originale è la prima liquidazione per un intervallo periodico e può essere elaborata una sola volta per un intervallo periodico.</span><span class="sxs-lookup"><span data-stu-id="28c23-110">Original is the first settlement for a period interval and can only processed once for a period interval.</span></span> <span data-ttu-id="28c23-111">Le ultime correzioni sistemeranno le transazioni IVA registrate dopo che la versione originale è stata creata.</span><span class="sxs-lookup"><span data-stu-id="28c23-111">Latest corrections will settle sales tax transactions which have been posted after the original version has been created.</span></span>   
5. <span data-ttu-id="28c23-112">Nel campo Data della transazione immettere una data.</span><span class="sxs-lookup"><span data-stu-id="28c23-112">In the Transaction date field, enter a date.</span></span>
6. <span data-ttu-id="28c23-113">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="28c23-113">Click OK.</span></span>

