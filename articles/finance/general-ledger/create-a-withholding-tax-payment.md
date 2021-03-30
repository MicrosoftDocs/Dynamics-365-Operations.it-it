---
title: Creare un pagamento ritenuta d'acconto
description: La procedura di pagamento della ritenuta d'acconto liquida i saldi delle ritenute d'acconto dalla contabilità fornitori nei conti ritenute d'acconto e li compensa sul conto di liquidazione della ritenuta d'acconto per un determinato periodo. Questo argomento elenca i passaggi per impostare un pagamento della ritenuta d'acconto.
author: roschlom
manager: AnnBe
ms.date: 01/12/2021
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
ms.search.validFrom: 2020-01-12
ms.dyn365.ops.version: AX 10.0.16
ms.openlocfilehash: eae914ccafad12426cadd91c0950bada23548005
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5212279"
---
# <a name="create-a-withholding-tax-payment"></a><span data-ttu-id="b8ee3-104">Creare un pagamento ritenuta d'acconto</span><span class="sxs-lookup"><span data-stu-id="b8ee3-104">Create a withholding tax payment</span></span>

<span data-ttu-id="b8ee3-105">La procedura di pagamento della ritenuta d'acconto liquida i saldi delle ritenute d'acconto dalla contabilità fornitori nei conti ritenute d'acconto e li compensa sul conto di liquidazione della ritenuta d'acconto per un determinato periodo.</span><span class="sxs-lookup"><span data-stu-id="b8ee3-105">The Withholding tax payment job procedure settles withholding tax balances from Accounts payable on withholding tax accounts, and offsets them to the withholding tax settlement account for a given period.</span></span> <span data-ttu-id="b8ee3-106">Questo argomento elenca i passaggi per impostare un pagamento della ritenuta d'acconto.</span><span class="sxs-lookup"><span data-stu-id="b8ee3-106">This topic lists the steps for setting up a withholding tax payment.</span></span>

> [!NOTE] 
> <span data-ttu-id="b8ee3-107">La compensazione della ritenuta d'acconto (dalla contabilità fornitori) non viene presa in considerazione quando viene calcolato il pagamento di una ritenuta d'acconto.</span><span class="sxs-lookup"><span data-stu-id="b8ee3-107">Withholding tax offset (from accounts receivable) is not taken into account when a withholding tax payment is calculated.</span></span>

1. <span data-ttu-id="b8ee3-108">Vai a **Pannello di navigazione > Moduli > Imposta > Dichiarazioni > Ritenuta d'acconto > Pagamento ritenuta d'acconto**.</span><span class="sxs-lookup"><span data-stu-id="b8ee3-108">Go to **Navigation pane > Modules > Tax > Declarations > Withholding tax > Withholding tax payment**.</span></span>
2. <span data-ttu-id="b8ee3-109">Nel campo **Periodo di liquidazione** fai clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="b8ee3-109">In the **Settlement period** field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="b8ee3-110">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="b8ee3-110">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="b8ee3-111">Immettere una data nel campo **Dal**.</span><span class="sxs-lookup"><span data-stu-id="b8ee3-111">In the **From date** field, enter a date.</span></span>
5. <span data-ttu-id="b8ee3-112">Nel campo **Data della transazione** immettere una data.</span><span class="sxs-lookup"><span data-stu-id="b8ee3-112">In the **Transaction date** field, enter a date.</span></span>
6. <span data-ttu-id="b8ee3-113">Seleziona **Aggiorna** per registrare il giustificativo di pagamento della ritenuta d'acconto sul conto di liquidazione della ritenuta d'acconto.</span><span class="sxs-lookup"><span data-stu-id="b8ee3-113">Select **Update** to post withholding tax payment voucher to the withholding tax settlement account.</span></span>
7. <span data-ttu-id="b8ee3-114">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="b8ee3-114">Click **OK**.</span></span>

![Parametri per il pagamento della ritenuta d'acconto](media/withholding-tax-payment.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]