---
title: Creare un pagamento IVA
description: La procedura di liquidazione e registrazione liquida i saldi IVA nei conti IVA e li registra in contropartita nel conto di liquidazione IVA per un periodo specifico.
author: twheeloc
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: Dialog
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5066689fb85dd176da1ca1561614e443cb87d816
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5832756"
---
# <a name="create-a-sales-tax-payment"></a><span data-ttu-id="f8f9a-103">Creare un pagamento IVA</span><span class="sxs-lookup"><span data-stu-id="f8f9a-103">Create a sales tax payment</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="f8f9a-104">La procedura di liquidazione e registrazione liquida i saldi IVA nei conti IVA e li registra in contropartita nel conto di liquidazione IVA per un periodo specifico.</span><span class="sxs-lookup"><span data-stu-id="f8f9a-104">The settle and post sales tax job procedure settles sales tax balances on the sales tax accounts, and offsets them to the sales tax settlement account for a given period.</span></span>

1. <span data-ttu-id="f8f9a-105">Vaia a **Imposta > Dichiarazioni > IVA > Liquida e registra IVA**.</span><span class="sxs-lookup"><span data-stu-id="f8f9a-105">Go to **Tax > Declarations > Sales tax > Settle and post sales tax**.</span></span>
2. <span data-ttu-id="f8f9a-106">Nel campo **Periodo di liquidazione** fai clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="f8f9a-106">In the **Settlement period** field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="f8f9a-107">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="f8f9a-107">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="f8f9a-108">Immettere una data nel campo **Dal**.</span><span class="sxs-lookup"><span data-stu-id="f8f9a-108">In the **From date** field, enter a date.</span></span>
    * <span data-ttu-id="f8f9a-109">Se non selezioni l'opzione **Includi correzioni** nella pagina **Parametri di contabilità generale**, la liquidazione può essere elaborata per versioni diverse.</span><span class="sxs-lookup"><span data-stu-id="f8f9a-109">If you don't select the **Include corrections** option on the **General ledger parameters** page, the settlement can be processed for different versions.</span></span> <span data-ttu-id="f8f9a-110">Originale è la prima liquidazione per un intervallo periodico e può essere elaborata una sola volta per un intervallo periodico.</span><span class="sxs-lookup"><span data-stu-id="f8f9a-110">Original is the first settlement for a period interval and can be processed only once for a period interval.</span></span> <span data-ttu-id="f8f9a-111">Le ultime correzioni sistemeranno le transazioni IVA registrate dopo che la versione originale è stata creata.</span><span class="sxs-lookup"><span data-stu-id="f8f9a-111">The latest corrections will settle sales tax transactions which have been posted after the original version has been created.</span></span>   
5. <span data-ttu-id="f8f9a-112">Nel campo **Data della transazione** immettere una data.</span><span class="sxs-lookup"><span data-stu-id="f8f9a-112">In the **Transaction date** field, enter a date.</span></span>
6. <span data-ttu-id="f8f9a-113">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="f8f9a-113">Click **OK**.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]