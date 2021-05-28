---
title: È possibile aggiungere solo il conto principale come conto in Avere per motivi di riconciliazione
description: Quando imposti un motivo di riconciliazione in Gestione trasporto, puoi aggiungere solo il conto principale come conto in Avere.
author: Henrikan
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: TMSFBDetailReconcile
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 708081370b27fd51ef9a2329d8392f4515353dcb
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026629"
---
# <a name="you-can-add-only-the-main-account-as-the-credit-account-for-reconciliation-reasons"></a><span data-ttu-id="11f03-103">È possibile aggiungere solo il conto principale come conto in Avere per motivi di riconciliazione</span><span class="sxs-lookup"><span data-stu-id="11f03-103">You can add only the main account as the credit account for reconciliation reasons</span></span>

<span data-ttu-id="11f03-104">Numero KB: 4603538</span><span class="sxs-lookup"><span data-stu-id="11f03-104">KB number: 4603538</span></span>

## <a name="symptoms"></a><span data-ttu-id="11f03-105">Sintomi</span><span class="sxs-lookup"><span data-stu-id="11f03-105">Symptoms</span></span>

<span data-ttu-id="11f03-106">Quando imposti un motivo di riconciliazione in Gestione trasporto, puoi aggiungere solo il conto principale come conto in Avere.</span><span class="sxs-lookup"><span data-stu-id="11f03-106">When you set up a reconciliation reason in Transportation management, you can add only the main account as the credit account.</span></span> <span data-ttu-id="11f03-107">Non è possibile aggiungere un centro di costo o qualsiasi altra dimensione come conto in Avere.</span><span class="sxs-lookup"><span data-stu-id="11f03-107">You can't add a cost center or any other dimension as the credit account.</span></span> <span data-ttu-id="11f03-108">Tuttavia, il conto in Dare ti consente di selezionare altre dimensioni.</span><span class="sxs-lookup"><span data-stu-id="11f03-108">However, the debit account lets you select other dimensions.</span></span>

## <a name="resolution"></a><span data-ttu-id="11f03-109">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="11f03-109">Resolution</span></span>

<span data-ttu-id="11f03-110">Se la riconciliazione non viene eseguita per pagare il fornitore ma per accreditare uno specifico conto principale, il sistema non ti consente di selezionare una dimensione finanziaria per il conto in Avere quando imposti il motivo della riconciliazione.</span><span class="sxs-lookup"><span data-stu-id="11f03-110">If the reconciliation isn't done to pay the vendor but to credit a specific main account, the system doesn't allow you to select a financial dimension for the credit account when you set up the reconciliation reason.</span></span>

<span data-ttu-id="11f03-111">Se la struttura dei conti richiede uno specifico valore di dimensione finanziaria per il conto principale in Avere, il giornale di registrazione fornitore risultante non può essere registrato automaticamente perché manca il valore della dimensione finanziaria.</span><span class="sxs-lookup"><span data-stu-id="11f03-111">If the account structure requires a specific financial dimension value for the credit main account, the resulting vendor journal can't be posted automatically, because the financial dimension value is missing.</span></span> <span data-ttu-id="11f03-112">Pertanto, devi prima specificare manualmente il conto in Avere utilizzando la pagina **Giornale di registrazione fatture**.</span><span class="sxs-lookup"><span data-stu-id="11f03-112">Therefore, you must first manually specify the credit account by using the **Invoice journal** page.</span></span>

<span data-ttu-id="11f03-113">Poiché un valore di dimensione è richiesto per il conto in Avere, il giornale di registrazione fatture fornitore non può essere registrato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="11f03-113">Because a dimension value is required for the credit account, the vendor invoice journal can't be automatically posted.</span></span> <span data-ttu-id="11f03-114">Devi registrarlo manualmente dopo aver aggiunto manualmente il valore della dimensione al conto principale per la riga Avere.</span><span class="sxs-lookup"><span data-stu-id="11f03-114">You must manually post it after you manually add the dimension value to the main account for the credit line.</span></span>
