---
title: Errore quando il giornale di registrazione Dichiarato finito viene registrato
description: Quando registri il giornale di registrazione Dichiarato finito, viene visualizzato un messaggio di errore che informa che la quantità ordinata non può essere ridotta.
author: johanhoffmann
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: ProdTableListPage, ProdParameters
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 55db7d0033dd66c1b973abf96671a20ab05d61d8
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026632"
---
# <a name="error-when-the-report-as-finished-journal-is-posted"></a><span data-ttu-id="0ca0f-103">Errore quando il giornale di registrazione Dichiarato finito viene registrato</span><span class="sxs-lookup"><span data-stu-id="0ca0f-103">Error when the Report as finished journal is posted</span></span>

<span data-ttu-id="0ca0f-104">Numero KB: 4612891</span><span class="sxs-lookup"><span data-stu-id="0ca0f-104">KB number: 4612891</span></span>

## <a name="symptoms"></a><span data-ttu-id="0ca0f-105">Sintomi</span><span class="sxs-lookup"><span data-stu-id="0ca0f-105">Symptoms</span></span>

<span data-ttu-id="0ca0f-106">Quando registri il giornale di registrazione **Dichiarato finito**, si verifica un errore e viene visualizzato il seguente messaggio di errore:</span><span class="sxs-lookup"><span data-stu-id="0ca0f-106">When you post the **Report as finished** journal, an error occurs, and you receive the following error message:</span></span>

> <span data-ttu-id="0ca0f-107">Impossibile ridurre la quantità ordinata perché non è presente un numero sufficiente di operazioni di magazzino aperte con stato Ordinato.</span><span class="sxs-lookup"><span data-stu-id="0ca0f-107">Quantity ordered cannot be reduced because there are not enough open inventory transactions with the ordered status.</span></span> <span data-ttu-id="0ca0f-108">Gli articoli sono acquistati, ricevuti o registrati.</span><span class="sxs-lookup"><span data-stu-id="0ca0f-108">The items are Purchased, Received or Registered.</span></span>

<span data-ttu-id="0ca0f-109">Questo errore si verifica solo quando il campo **Quantità difettosa** è impostato nella prima riga del giornale di registrazione **Dichiarato finito** e il campo **Quantità idonea** è impostato nell'ultima riga.</span><span class="sxs-lookup"><span data-stu-id="0ca0f-109">This error occurs only when the **Error quantity** field is set on the first line of the **Report as finished** journal, and the **Good quantity** field is set on the last line.</span></span> <span data-ttu-id="0ca0f-110">Se il campo **Quantità difettosa** è impostato nell'ultima riga, non si verificano errori.</span><span class="sxs-lookup"><span data-stu-id="0ca0f-110">If the **Error quantity** field is set on the last line, no error occurs.</span></span>

## <a name="resolution"></a><span data-ttu-id="0ca0f-111">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="0ca0f-111">Resolution</span></span>

<span data-ttu-id="0ca0f-112">Per evitare questo errore, apri la pagina **Parametri di controllo produzione**, quindi nella scheda **Generale**, imposta l'opzione **Aumenta quantità rimanente con quantità difettosa** su *Sì*.</span><span class="sxs-lookup"><span data-stu-id="0ca0f-112">To prevent this error, open the **Production control parameters** page, and then, on the **General** tab, set the **Increase remain qty with error qty** option to *Yes*.</span></span>
