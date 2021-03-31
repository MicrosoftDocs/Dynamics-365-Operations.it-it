---
title: Creare regole avanzate per giornali di registrazione
description: Questa procedura descrive come creare regole avanzate per i giornali di registrazione.
author: aprilolson
manager: AnnBe
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalSetup, LedgerJournalControl, CompanyLookup, LedgerJournalPostControl
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e61ed731c4040e7351e20421f6cf217ae9a4641d
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5222361"
---
# <a name="create-advanced-rules-for-journals"></a><span data-ttu-id="51953-103">Creare regole avanzate per giornali di registrazione</span><span class="sxs-lookup"><span data-stu-id="51953-103">Create advanced rules for journals</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="51953-104">Questa procedura descrive come creare regole avanzate per i giornali di registrazione.</span><span class="sxs-lookup"><span data-stu-id="51953-104">This procedure steps through creating advanced rules for journals.</span></span> <span data-ttu-id="51953-105">Sono incluse le impostazioni del controllo del giornale di registrazione e delle restrizioni della registrazione per utente.</span><span class="sxs-lookup"><span data-stu-id="51953-105">This includes setting up journal control and user posting restrictions.</span></span> <span data-ttu-id="51953-106">Questa procedura utilizza la società di dati dimostrativi USMF.</span><span class="sxs-lookup"><span data-stu-id="51953-106">This procedure uses the USMF demo data company.</span></span>


## <a name="set-up-journal-control"></a><span data-ttu-id="51953-107">Impostare il controllo del giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="51953-107">Set up journal control</span></span>
1. <span data-ttu-id="51953-108">Nel **pannello di navigazione**, andare a **Moduli > Contabilità generale > Impostazione giornale di registrazione > Nomi giornale di registrazione**.</span><span class="sxs-lookup"><span data-stu-id="51953-108">In the **Navigation pane**, go to **Modules > General ledger > Journal setup > Journal names**.</span></span>
2. <span data-ttu-id="51953-109">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="51953-109">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="51953-110">Fare clic su **Riquadro azioni** nel **Controllo giornale di registrazione**.</span><span class="sxs-lookup"><span data-stu-id="51953-110">On the **Action pane**, click **Journal control**.</span></span>
4. <span data-ttu-id="51953-111">Nella Scheda dettaglio **Quali tipi di conto è possibile registrare?**, fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="51953-111">In the **Which account types can be posted** fastTab, click **Add**.</span></span>
5. <span data-ttu-id="51953-112">Nel campo **Account società** fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="51953-112">In the **Company accounts** field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="51953-113">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="51953-113">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="51953-114">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="51953-114">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="51953-115">Nella Scheda dettaglio **Quali sono i valori segmento validi per questo giornale di registrazione?**, fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="51953-115">In the **Which segment values are valid for this journal** fastTab, click **Add**.</span></span>
9. <span data-ttu-id="51953-116">Nel campo **Struttura dei conti** fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="51953-116">In the **Account structure** field, click the drop-down button to open the lookup.</span></span>
10. <span data-ttu-id="51953-117">Trovare e selezionare il record desiderato nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="51953-117">In the list, find and select the desired record.</span></span>
11. <span data-ttu-id="51953-118">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="51953-118">In the list, click the link in the selected row.</span></span>
12. <span data-ttu-id="51953-119">Nel campo **Segmento** fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="51953-119">In the **Segment** field, click the drop-down button to open the lookup.</span></span>
13. <span data-ttu-id="51953-120">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="51953-120">In the list, click the link in the selected row.</span></span>
14. <span data-ttu-id="51953-121">Nel campo **Dal valore** fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="51953-121">In the **From value** field, click the drop-down button to open the lookup.</span></span>
15. <span data-ttu-id="51953-122">Trovare e selezionare il record desiderato nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="51953-122">In the list, find and select the desired record.</span></span>
16. <span data-ttu-id="51953-123">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="51953-123">In the list, click the link in the selected row.</span></span>
17. <span data-ttu-id="51953-124">Nel campo **Al valore** fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="51953-124">In the **To value** field, click the drop-down button to open the lookup.</span></span>
18. <span data-ttu-id="51953-125">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="51953-125">In the list, find and select the desired record.</span></span>
19. <span data-ttu-id="51953-126">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="51953-126">In the list, click the link in the selected row.</span></span>

## <a name="set-up-posting-restrictions"></a><span data-ttu-id="51953-127">Impostare le restrizioni di registrazione</span><span class="sxs-lookup"><span data-stu-id="51953-127">Set up posting restrictions</span></span>
1. <span data-ttu-id="51953-128">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="51953-128">Close the page.</span></span>
2. <span data-ttu-id="51953-129">Fare clic su **Restrizioni registrazione**.</span><span class="sxs-lookup"><span data-stu-id="51953-129">Click **Posting restrictions**.</span></span>
3. <span data-ttu-id="51953-130">In **Come si desidera impostare le restrizioni di registrazione**, selezionare "Per gruppo utenti".</span><span class="sxs-lookup"><span data-stu-id="51953-130">In the **How do you want to set up posting restrictions** field, select 'By user group'.</span></span>
4. <span data-ttu-id="51953-131">Nella struttura, selezionare 'il gruppo a cui è consentita la registrazione per questo nome di giornale di registrazione'.</span><span class="sxs-lookup"><span data-stu-id="51953-131">In the tree, check 'the group that you want to allow posting for this journal name.'.</span></span>
5. <span data-ttu-id="51953-132">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="51953-132">Click **OK**.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]