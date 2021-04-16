---
title: Creare regole avanzate per giornali di registrazione
description: Questa procedura descrive come creare regole avanzate per i giornali di registrazione.
author: aprilolson
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalSetup, LedgerJournalControl, CompanyLookup, LedgerJournalPostControl
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: cd753d521dc4ad4c1e46bf51d9c1e4aa0ba02721
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5832804"
---
# <a name="create-advanced-rules-for-journals"></a><span data-ttu-id="5ecb9-103">Creare regole avanzate per giornali di registrazione</span><span class="sxs-lookup"><span data-stu-id="5ecb9-103">Create advanced rules for journals</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="5ecb9-104">Questa procedura descrive come creare regole avanzate per i giornali di registrazione.</span><span class="sxs-lookup"><span data-stu-id="5ecb9-104">This procedure steps through creating advanced rules for journals.</span></span> <span data-ttu-id="5ecb9-105">Sono incluse le impostazioni del controllo del giornale di registrazione e delle restrizioni della registrazione per utente.</span><span class="sxs-lookup"><span data-stu-id="5ecb9-105">This includes setting up journal control and user posting restrictions.</span></span> <span data-ttu-id="5ecb9-106">Questa procedura utilizza la società di dati dimostrativi USMF.</span><span class="sxs-lookup"><span data-stu-id="5ecb9-106">This procedure uses the USMF demo data company.</span></span>


## <a name="set-up-journal-control"></a><span data-ttu-id="5ecb9-107">Impostare il controllo del giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="5ecb9-107">Set up journal control</span></span>
1. <span data-ttu-id="5ecb9-108">Nel **pannello di navigazione**, andare a **Moduli > Contabilità generale > Impostazione giornale di registrazione > Nomi giornale di registrazione**.</span><span class="sxs-lookup"><span data-stu-id="5ecb9-108">In the **Navigation pane**, go to **Modules > General ledger > Journal setup > Journal names**.</span></span>
2. <span data-ttu-id="5ecb9-109">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="5ecb9-109">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="5ecb9-110">Fare clic su **Riquadro azioni** nel **Controllo giornale di registrazione**.</span><span class="sxs-lookup"><span data-stu-id="5ecb9-110">On the **Action pane**, click **Journal control**.</span></span>
4. <span data-ttu-id="5ecb9-111">Nella Scheda dettaglio **Quali tipi di conto è possibile registrare?**, fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="5ecb9-111">In the **Which account types can be posted** fastTab, click **Add**.</span></span>
5. <span data-ttu-id="5ecb9-112">Nel campo **Account società** fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="5ecb9-112">In the **Company accounts** field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="5ecb9-113">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="5ecb9-113">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="5ecb9-114">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="5ecb9-114">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="5ecb9-115">Nella Scheda dettaglio **Quali sono i valori segmento validi per questo giornale di registrazione?**, fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="5ecb9-115">In the **Which segment values are valid for this journal** fastTab, click **Add**.</span></span>
9. <span data-ttu-id="5ecb9-116">Nel campo **Struttura dei conti** fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="5ecb9-116">In the **Account structure** field, click the drop-down button to open the lookup.</span></span>
10. <span data-ttu-id="5ecb9-117">Trovare e selezionare il record desiderato nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="5ecb9-117">In the list, find and select the desired record.</span></span>
11. <span data-ttu-id="5ecb9-118">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="5ecb9-118">In the list, click the link in the selected row.</span></span>
12. <span data-ttu-id="5ecb9-119">Nel campo **Segmento** fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="5ecb9-119">In the **Segment** field, click the drop-down button to open the lookup.</span></span>
13. <span data-ttu-id="5ecb9-120">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="5ecb9-120">In the list, click the link in the selected row.</span></span>
14. <span data-ttu-id="5ecb9-121">Nel campo **Dal valore** fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="5ecb9-121">In the **From value** field, click the drop-down button to open the lookup.</span></span>
15. <span data-ttu-id="5ecb9-122">Trovare e selezionare il record desiderato nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="5ecb9-122">In the list, find and select the desired record.</span></span>
16. <span data-ttu-id="5ecb9-123">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="5ecb9-123">In the list, click the link in the selected row.</span></span>
17. <span data-ttu-id="5ecb9-124">Nel campo **Al valore** fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="5ecb9-124">In the **To value** field, click the drop-down button to open the lookup.</span></span>
18. <span data-ttu-id="5ecb9-125">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="5ecb9-125">In the list, find and select the desired record.</span></span>
19. <span data-ttu-id="5ecb9-126">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="5ecb9-126">In the list, click the link in the selected row.</span></span>

## <a name="set-up-posting-restrictions"></a><span data-ttu-id="5ecb9-127">Impostare le restrizioni di registrazione</span><span class="sxs-lookup"><span data-stu-id="5ecb9-127">Set up posting restrictions</span></span>
1. <span data-ttu-id="5ecb9-128">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="5ecb9-128">Close the page.</span></span>
2. <span data-ttu-id="5ecb9-129">Fare clic su **Restrizioni registrazione**.</span><span class="sxs-lookup"><span data-stu-id="5ecb9-129">Click **Posting restrictions**.</span></span>
3. <span data-ttu-id="5ecb9-130">In **Come si desidera impostare le restrizioni di registrazione**, selezionare "Per gruppo utenti".</span><span class="sxs-lookup"><span data-stu-id="5ecb9-130">In the **How do you want to set up posting restrictions** field, select 'By user group'.</span></span>
4. <span data-ttu-id="5ecb9-131">Nella struttura, selezionare 'il gruppo a cui è consentita la registrazione per questo nome di giornale di registrazione'.</span><span class="sxs-lookup"><span data-stu-id="5ecb9-131">In the tree, check 'the group that you want to allow posting for this journal name.'.</span></span>
5. <span data-ttu-id="5ecb9-132">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="5ecb9-132">Click **OK**.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]