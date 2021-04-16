---
title: Ridurre i giorni delle commissioni di sottoscrizione
description: Per ridurre il numero di giorni di commissione di una sottoscrizione presente, è possibile creare una nuova transazione in cui rimuovere il periodo che non deve più far parte dell'intervallo relativo alle commissioni della sottoscrizione.
author: ShylaThompson
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMASubscriptionTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5e8158c99d2447835f3656027fd73d7c22121536
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5836088"
---
# <a name="reduce-the-days-on-subscription-fees"></a><span data-ttu-id="30b77-103">Ridurre i giorni delle commissioni di sottoscrizione</span><span class="sxs-lookup"><span data-stu-id="30b77-103">Reduce the days on subscription fees</span></span> 

[!include [banner](../includes/banner.md)]


<span data-ttu-id="30b77-104">Per ridurre il numero di giorni di commissione di una sottoscrizione presente, è possibile creare una nuova transazione in cui rimuovere il periodo che non deve più far parte dell'intervallo relativo alle commissioni della sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="30b77-104">To reduce the number of days of an existing subscription fee, you can create a new transaction in which you remove the period of time that should no longer be part of the subscription fee interval.</span></span>

## <a name="reduce-the-days-on-a-subscription-fee"></a><span data-ttu-id="30b77-105">Ridurre i giorni di commissione di una sottoscrizione</span><span class="sxs-lookup"><span data-stu-id="30b77-105">Reduce the days on a subscription fee</span></span>

1.  <span data-ttu-id="30b77-106">Fare clic su **Gestione assistenza** \> **Comune** \> **Sottoscrizioni assistenza** \> **Tutte le sottoscrizioni assistenza**.</span><span class="sxs-lookup"><span data-stu-id="30b77-106">Click **Service management** \> **Common** \> **Service subscriptions** \> **All service subscriptions**.</span></span> <span data-ttu-id="30b77-107">Selezionare la sottoscrizione di assistenza e nel riquadro azioni fare clic su **Commissioni sottoscrizione**.</span><span class="sxs-lookup"><span data-stu-id="30b77-107">Select the service subscription, and on the Action Pane, click **Subscription fees**</span></span>

2.  <span data-ttu-id="30b77-108">Nel campo **Tipo di sottoscrizione**, selezionare **Giorni riduzione**.</span><span class="sxs-lookup"><span data-stu-id="30b77-108">In the **Subscription type** field, select **Reduction days**.</span></span>

3.  <span data-ttu-id="30b77-109">Utilizzare i campi **Dal** e **Al** per definire l'intervallo di date della commissione di sottoscrizione che si desidera rimuovere dal periodo di commissione, quindi scegliere **OK**.</span><span class="sxs-lookup"><span data-stu-id="30b77-109">Use the **From date** field and the **To date** fields to define the date interval of the subscription fee that you want to remove from the subscription fee period, and then click **OK**.</span></span>

<span data-ttu-id="30b77-110">Per visualizzare la transazione creata, nel modulo **Sottoscrizione** fare clic su , quindi su **Transazioni sbilanciate**.</span><span class="sxs-lookup"><span data-stu-id="30b77-110">To view the transaction that was created, in the **Subscription** form, click **Fee transactions**.</span></span>

## <a name="example"></a><span data-ttu-id="30b77-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="30b77-111">Example</span></span>

<span data-ttu-id="30b77-112">Se il periodo di una transazione di sottoscrizione va dal primo al 31 gennaio e si desidera ridurre il periodo di 10 giorni, creare una nuova transazione in cui il periodo di riduzione corrisponde ai giorni dal primo al 10 gennaio</span><span class="sxs-lookup"><span data-stu-id="30b77-112">If a subscription transaction period runs from January 1 to January 31, and you want to reduce the period by 10 days, create a new transaction in which the reduction period is January 1 to January 10.</span></span> <span data-ttu-id="30b77-113">o dal 5 al 15 gennaio oppure un altro periodo di dieci giorni.</span><span class="sxs-lookup"><span data-stu-id="30b77-113">(The reduction period could also be January 5 to January 15, or any other ten day period).</span></span>

<span data-ttu-id="30b77-114">Se inoltre la data impostata nel campo **Dal** del periodo di riduzione corrisponde al 21 gennaio (31 meno 10), nel campo **Al** è possibile impostare una qualsiasi data successiva al 31 gennaio. I 10 giorni verranno comunque rimossi dal periodo della transazione di commissione.</span><span class="sxs-lookup"><span data-stu-id="30b77-114">Also, if the **From date** on the reduction period is January 21 (31 minus 10), you could set the **To date** to any date after January 31, and 10 days will still be removed from the fee transaction period.</span></span>

## <a name="see-also"></a><span data-ttu-id="30b77-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="30b77-115">See also</span></span>

[<span data-ttu-id="30b77-116">Esempio di giorni di riduzione</span><span class="sxs-lookup"><span data-stu-id="30b77-116">Reduction days example</span></span>](reduction-days-example.md)

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]