---
title: Ti viene chiesto di salvare le impostazioni di copertura degli articoli anche se non hai apportato modifiche
description: Ti viene chiesto di salvare le impostazioni di copertura degli articoli anche se non hai apportato modifiche.
author: ChristianRytt
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: DataManagementWorkspace_
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: angarmas
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 3dfa974740420433af1e1b37630b22509510c91b
ms.sourcegitcommit: 3c15a26e9708adc9a75082dc551f0a3a0a7d89f4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/17/2021
ms.locfileid: "6049474"
---
# <a name="youre-prompted-to-save-item-coverage-settings-even-though-you-made-no-changes"></a><span data-ttu-id="f9626-103">Ti viene chiesto di salvare le impostazioni di copertura degli articoli anche se non hai apportato modifiche</span><span class="sxs-lookup"><span data-stu-id="f9626-103">You're prompted to save item coverage settings even though you made no changes</span></span>

<span data-ttu-id="f9626-104">Numero KB: 4615588</span><span class="sxs-lookup"><span data-stu-id="f9626-104">KB number: 4615588</span></span>

## <a name="symptoms"></a><span data-ttu-id="f9626-105">Sintomi</span><span class="sxs-lookup"><span data-stu-id="f9626-105">Symptoms</span></span>

<span data-ttu-id="f9626-106">In alcuni scenari, potresti ricevere il seguente messaggio quando apri la pagina **Copertura dell'articolo** dopo aver importato gli elementi tramite l'entità *Copertura articolo V2*:</span><span class="sxs-lookup"><span data-stu-id="f9626-106">In some scenarios, you might receive the following message when you open the **Item coverage** page after you import items through the *Item coverage V2* entity:</span></span>

> <span data-ttu-id="f9626-107">Salvare le modifiche apportate prima di chiudere?</span><span class="sxs-lookup"><span data-stu-id="f9626-107">Do you want to save your changes before closing?</span></span>

<span data-ttu-id="f9626-108">Riceverai questo messaggio anche se non hai apportato modifiche.</span><span class="sxs-lookup"><span data-stu-id="f9626-108">You receive this message even though you haven't made any changes.</span></span>

## <a name="resolution"></a><span data-ttu-id="f9626-109">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="f9626-109">Resolution</span></span>

<span data-ttu-id="f9626-110">La pagina **Copertura dell'articolo** include una logica di default complessa che potrebbe causare la visualizzazione del messaggio dopo che sono state apportate di recente modifiche dirette al database, ad esempio tramite l'importazione di entità.</span><span class="sxs-lookup"><span data-stu-id="f9626-110">The **Item coverage** page includes complex defaulting logic that might cause the message to be shown after direct changes have recently been made in the database, such as through entity import.</span></span> <span data-ttu-id="f9626-111">Ad esempio, il campo entità `AREGENERALSETTINGSOVERRIDDEN` è impostato su *No*, ma importi un file che fornisce valori nuovi o modificati per campi come `PRODUCTCOVERAGEGROUPID` e/o `VENDORACCOUNTNUMBER`.</span><span class="sxs-lookup"><span data-stu-id="f9626-111">For example, the `AREGENERALSETTINGSOVERRIDDEN` entity field is set to *No*, but you import a file that provides new or modified values for fields such as `PRODUCTCOVERAGEGROUPID` and/or `VENDORACCOUNTNUMBER`.</span></span> <span data-ttu-id="f9626-112">In questo caso, poiché il campo `AREGENERALSETTINGSOVERRIDDEN` è impostato su *No*, i valori vengono automaticamente cancellati dai campi quando si apre la pagina **Copertura dell'articolo** per la prima volta dopo l'importazione.</span><span class="sxs-lookup"><span data-stu-id="f9626-112">In this case, because the `AREGENERALSETTINGSOVERRIDDEN` field is set to *No*, the values are automatically cleared from the fields when you open the **Item coverage** page for the first time after the import.</span></span> <span data-ttu-id="f9626-113">Se si salvano le modifiche come richiesto dalla finestra di messaggio, vengono archiviate nel database.</span><span class="sxs-lookup"><span data-stu-id="f9626-113">If you save the changes as the message box prompts, they are stored in the database.</span></span> <span data-ttu-id="f9626-114">In caso contrario, riceverai lo stesso messaggio la prossima volta che aprirai la pagina.</span><span class="sxs-lookup"><span data-stu-id="f9626-114">Otherwise, you will receive the same message the next time that you open the page.</span></span>

<span data-ttu-id="f9626-115">Per evitare questo comportamento, ma includere anche valori per campi come `PRODUCTCOVERAGEGROUPID` tramite l'importazione di entità, imposta `AREGENERALSETTINGSOVERRIDDEN` su *Sì* quando importi.</span><span class="sxs-lookup"><span data-stu-id="f9626-115">To prevent this behavior but also include values for fields such as `PRODUCTCOVERAGEGROUPID` through entity import, set `AREGENERALSETTINGSOVERRIDDEN` to *Yes* when you import.</span></span>
