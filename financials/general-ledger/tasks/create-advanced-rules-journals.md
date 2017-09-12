--- 
title: Creare regole avanzate per giornali di registrazione
description: Questa procedura descrive come creare regole avanzate per i giornali di registrazione.
author: aprilolson
manager: AnnBe
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 1bb1663b0f5d7e6a550e1ffd2ee2edf3771a13b3
ms.contentlocale: it-it
ms.lasthandoff: 08/29/2017

---
# <a name="create-advanced-rules-for-journals"></a><span data-ttu-id="f6ce5-103">Creare regole avanzate per giornali di registrazione</span><span class="sxs-lookup"><span data-stu-id="f6ce5-103">Create advanced rules for journals</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="f6ce5-104">Questa procedura descrive come creare regole avanzate per i giornali di registrazione.</span><span class="sxs-lookup"><span data-stu-id="f6ce5-104">This procedure steps through creating advanced rules for journals.</span></span> <span data-ttu-id="f6ce5-105">Sono incluse le impostazioni del controllo del giornale di registrazione e delle restrizioni della registrazione per utente.</span><span class="sxs-lookup"><span data-stu-id="f6ce5-105">This includes setting up journal control and user posting restrictions.</span></span> <span data-ttu-id="f6ce5-106">Questa procedura utilizza la società di dati dimostrativi USMF.</span><span class="sxs-lookup"><span data-stu-id="f6ce5-106">This procedure uses the USMF demo data company.</span></span>


## <a name="set-up-journal-control"></a><span data-ttu-id="f6ce5-107">Impostare il controllo del giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="f6ce5-107">Set up journal control</span></span>
1. <span data-ttu-id="f6ce5-108">Andare a Contabilità generale > Impostazione giornale di registrazione > Nomi giornale di registrazione.</span><span class="sxs-lookup"><span data-stu-id="f6ce5-108">Go to General ledger > Journal setup > Journal names.</span></span>
2. <span data-ttu-id="f6ce5-109">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="f6ce5-109">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="f6ce5-110">Fare clic su Controllo giornale di registrazione.</span><span class="sxs-lookup"><span data-stu-id="f6ce5-110">Click Journal control.</span></span>
4. <span data-ttu-id="f6ce5-111">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="f6ce5-111">Click Add.</span></span>
5. <span data-ttu-id="f6ce5-112">Nel campo Account società fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="f6ce5-112">In the Company accounts field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="f6ce5-113">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="f6ce5-113">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="f6ce5-114">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="f6ce5-114">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="f6ce5-115">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="f6ce5-115">Click Add.</span></span>
9. <span data-ttu-id="f6ce5-116">Nel campo Struttura dei conti fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="f6ce5-116">In the Account structure field, click the drop-down button to open the lookup.</span></span>
10. <span data-ttu-id="f6ce5-117">Trovare e selezionare il record desiderato nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="f6ce5-117">In the list, find and select the desired record.</span></span>
11. <span data-ttu-id="f6ce5-118">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="f6ce5-118">In the list, click the link in the selected row.</span></span>
12. <span data-ttu-id="f6ce5-119">Nel campo Segmento fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="f6ce5-119">In the Segment field, click the drop-down button to open the lookup.</span></span>
13. <span data-ttu-id="f6ce5-120">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="f6ce5-120">In the list, click the link in the selected row.</span></span>
14. <span data-ttu-id="f6ce5-121">Nel campo Dal valore fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="f6ce5-121">In the From value field, click the drop-down button to open the lookup.</span></span>
15. <span data-ttu-id="f6ce5-122">Trovare e selezionare il record desiderato nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="f6ce5-122">In the list, find and select the desired record.</span></span>
16. <span data-ttu-id="f6ce5-123">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="f6ce5-123">In the list, click the link in the selected row.</span></span>
17. <span data-ttu-id="f6ce5-124">Nel campo Al valore fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="f6ce5-124">In the To value field, click the drop-down button to open the lookup.</span></span>
18. <span data-ttu-id="f6ce5-125">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="f6ce5-125">In the list, find and select the desired record.</span></span>
19. <span data-ttu-id="f6ce5-126">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="f6ce5-126">In the list, click the link in the selected row.</span></span>

## <a name="set-up-posting-restrictions"></a><span data-ttu-id="f6ce5-127">Impostare le restrizioni di registrazione</span><span class="sxs-lookup"><span data-stu-id="f6ce5-127">Set up posting restrictions</span></span>
1. <span data-ttu-id="f6ce5-128">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="f6ce5-128">Close the page.</span></span>
2. <span data-ttu-id="f6ce5-129">Fare clic su Restrizioni registrazione.</span><span class="sxs-lookup"><span data-stu-id="f6ce5-129">Click Posting restrictions.</span></span>
3. <span data-ttu-id="f6ce5-130">In Come si desidera impostare le restrizioni di registrazione, selezionare Per gruppo utenti.</span><span class="sxs-lookup"><span data-stu-id="f6ce5-130">In the How do you want to set up posting restrictions, select By user group.</span></span>
4. <span data-ttu-id="f6ce5-131">Nella struttura, selezionare 'il gruppo a cui è consentita la registrazione per questo nome di giornale di registrazione'.</span><span class="sxs-lookup"><span data-stu-id="f6ce5-131">In the tree, check 'the group that you want to allow posting for this journal name.'.</span></span>
5. <span data-ttu-id="f6ce5-132">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="f6ce5-132">Click OK.</span></span>


