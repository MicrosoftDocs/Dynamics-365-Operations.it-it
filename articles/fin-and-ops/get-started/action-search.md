---
title: Ricerca di azioni
description: "In questo articolo viene descritta la funzionalità di ricerca di azioni in Microsoft Dynamics 365 for Finance and Operations. La ricerca di azioni consente di individuare ed eseguire azioni in una pagina."
author: jasongre
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 62303
ms.assetid: 62c70de0-fdde-4417-8e08-0583fb095a40
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 20d28e22e4e89d0d864a0cbeaadeb568e73e223e
ms.openlocfilehash: 9b9bb0acc6f0dc1722c916f133eed766ffdd4cc8
ms.contentlocale: it-it
ms.lasthandoff: 06/29/2017


---

# <a name="action-search"></a><span data-ttu-id="44d99-104">Ricerca di azioni</span><span class="sxs-lookup"><span data-stu-id="44d99-104">Action search</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="44d99-105">In questo articolo viene descritta la funzionalità di ricerca di azioni in Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="44d99-105">This article describes the action search functionality in Microsoft Dynamics 365 for Finance and Operations.</span></span> <span data-ttu-id="44d99-106">La ricerca di azioni consente di individuare ed eseguire azioni in una pagina.</span><span class="sxs-lookup"><span data-stu-id="44d99-106">Action search will help you find and run actions on a page.</span></span>

<a name="introduction"></a><span data-ttu-id="44d99-107">Introduzione</span><span class="sxs-lookup"><span data-stu-id="44d99-107">Introduction</span></span>
------------

<span data-ttu-id="44d99-108">Le pagine in Microsoft Dynamics 365 for Finance and Operations espongono principalmente i controlli presenti nei riquadri azioni, sia il riquadro azioni standard visualizzato nella parte superiore di una pagina sia le barre degli strumenti visualizzate in diverse aree della pagina.</span><span class="sxs-lookup"><span data-stu-id="44d99-108">Pages in Microsoft Dynamics 365 for Finance and Operations primarily expose commands on Action Panes, both the standard Action Pane that appears at the top of a page and the toolbars that appear in various sections of the page.</span></span> <span data-ttu-id="44d99-109">Nelle versioni precedenti, una funzionalità Descrizione dei tasti consente di accedere rapidamente a qualsiasi pulsante in un riquadro azioni premendo il tasto ALT e una serie di lettere.</span><span class="sxs-lookup"><span data-stu-id="44d99-109">In previous versions, a Key Tips feature let you quickly access any button on an Action Pane by pressing the Alt key and then a series of letters.</span></span> 

<span data-ttu-id="44d99-110">[![keyTipsAX6](./media/keytipsax6.png)](./media/keytipsax6.png) Tuttavia, nella versione corrente di Finance and Operations, le descrizioni dei tasti non sono più disponibili ma sono state sostituite dalla funzionalità di ricerca di azioni.</span><span class="sxs-lookup"><span data-stu-id="44d99-110">[![keyTipsAX6](./media/keytipsax6.png)](./media/keytipsax6.png) However, in the current version of Finance and Operations, Key Tips are no longer available but have been replaced by the action search feature.</span></span> <span data-ttu-id="44d99-111">La nuova funzionalità consente di trovare rapidamente ed eseguire un pulsante da qualsiasi riquadro azioni visibile.</span><span class="sxs-lookup"><span data-stu-id="44d99-111">This new feature lets you quickly search for and run a button from any visible Action Pane.</span></span>

## <a name="using-action-search"></a><span data-ttu-id="44d99-112">Utilizzo della ricerca azioni</span><span class="sxs-lookup"><span data-stu-id="44d99-112">Using action search</span></span>
<span data-ttu-id="44d99-113">Per utilizzare la funzionalità di ricerca azioni, effettuare le operazioni indicate di seguito.</span><span class="sxs-lookup"><span data-stu-id="44d99-113">To use the action search feature, follow these steps.</span></span>

1.  <span data-ttu-id="44d99-114">Nel riquadro azioni fare clic nel campo di **ricerca azioni**.</span><span class="sxs-lookup"><span data-stu-id="44d99-114">On the Action Pane, click in the **action search** field.</span></span> <span data-ttu-id="44d99-115">(Il campo di **ricerca azioni** contiene un'icona a forma di lente d'ingrandimento).</span><span class="sxs-lookup"><span data-stu-id="44d99-115">(The **action search** field contains a magnifying glass icon.)</span></span>
2.  <span data-ttu-id="44d99-116">Digitare integralmente o parzialmente il nome del pulsante che si desidera eseguire.</span><span class="sxs-lookup"><span data-stu-id="44d99-116">Type all or part of the name of the button that you want to run.</span></span> <span data-ttu-id="44d99-117">È inoltre possibile eseguire la ricerca utilizzando le parole dal "percorso" del pulsante.</span><span class="sxs-lookup"><span data-stu-id="44d99-117">You can also search by using words from the button's "path."</span></span> <span data-ttu-id="44d99-118">(Per ulteriori informazioni, vedere la sezione successiva dell'articolo). In genere, un pulsante verrà visualizzato vicino alla parte superiore dell'elenco dei risultati dopo aver digitato da due a quattro caratteri.</span><span class="sxs-lookup"><span data-stu-id="44d99-118">(For more information, see the next section of this article.) Typically, a button will appear near the top of the results list after you've typed two to four characters.</span></span>
3.  <span data-ttu-id="44d99-119">Individuare ed eseguire il pulsante nell'elenco risultati (mediante il mouse o tastiera).</span><span class="sxs-lookup"><span data-stu-id="44d99-119">Find and run the button in the results list (by using your mouse or keyboard).</span></span>

<span data-ttu-id="44d99-120">Dopo che il pulsante viene eseguito, lo stato attivo torna all'ultima posizione nella pagina, in modo che sia possibile continuare a lavorare.</span><span class="sxs-lookup"><span data-stu-id="44d99-120">After the button is run, the focus is returned to your last position on the page, so that you can continue to work.</span></span> 

<span data-ttu-id="44d99-121">[![campo-di-ricerca-azioni](./media/action-search-field.png)](./media/action-search-field.png)</span><span class="sxs-lookup"><span data-stu-id="44d99-121">[![action-search-field](./media/action-search-field.png)](./media/action-search-field.png)</span></span>

<span data-ttu-id="44d99-122">È inoltre possibile avviare la ricerca azioni premendo i tasti CTRL+/ o ALT+Q.</span><span class="sxs-lookup"><span data-stu-id="44d99-122">You can also start action search by pressing Ctrl+/ or Alt+Q.</span></span> <span data-ttu-id="44d99-123">Premere di nuovo i tasti di scelta rapida per riportare lo stato attivo all'ultima posizione nella pagina.</span><span class="sxs-lookup"><span data-stu-id="44d99-123">Press the keyboard shortcut again to return the focus to your last position on the page.</span></span>

## <a name="understanding-the-results-list"></a><span data-ttu-id="44d99-124">Interpretazione dell'elenco dei risultati</span><span class="sxs-lookup"><span data-stu-id="44d99-124">Understanding the results list</span></span>
<span data-ttu-id="44d99-125">Spesso, in Finance and Operations, è necessario conoscere l'ubicazione e il contesto di un pulsante per comprendere completamente lo scopo di tale pulsante.</span><span class="sxs-lookup"><span data-stu-id="44d99-125">Often, in Finance and Operations, you must know both the location and the context of a button to fully understand the purpose of that button.</span></span> <span data-ttu-id="44d99-126">Di conseguenza, nell'elenco dei risultati vengono mostrate informazioni aggiuntive per ciascun articolo, al fine di aiutare a comprendere esattamente quali pulsanti vengono visualizzati nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="44d99-126">Therefore, additional information is shown for each item in the results list, to help you understand exactly which buttons appear in the list.</span></span> <span data-ttu-id="44d99-127">In particolare, verrà visualizzato "il percorso" del pulsante.</span><span class="sxs-lookup"><span data-stu-id="44d99-127">In particular, the "path" of the button is shown.</span></span> <span data-ttu-id="44d99-128">Questo percorso può includere le etichette dei seguenti elementi di interfaccia utente, a seconda dei casi:</span><span class="sxs-lookup"><span data-stu-id="44d99-128">This path might include the labels of the following UI elements, as relevant:</span></span>

-   <span data-ttu-id="44d99-129">Scheda del riquadro azioni</span><span class="sxs-lookup"><span data-stu-id="44d99-129">Action Pane tab</span></span>
-   <span data-ttu-id="44d99-130">Gruppo pulsanti</span><span class="sxs-lookup"><span data-stu-id="44d99-130">Button group</span></span>
-   <span data-ttu-id="44d99-131">Pulsante di menu (se il pulsante è all'interno di un pulsante di menu)</span><span class="sxs-lookup"><span data-stu-id="44d99-131">Menu button (if the button is inside a menu button)</span></span>
-   <span data-ttu-id="44d99-132">Separatore di menu (se il pulsante è interno un gruppo denominato all'interno di un pulsante di menu)</span><span class="sxs-lookup"><span data-stu-id="44d99-132">Menu separator (if the button is inside a named group inside a menu button)</span></span>
-   <span data-ttu-id="44d99-133">Gruppo o scheda nella pagina (ad esempio, il nome di una scheda dettaglio)</span><span class="sxs-lookup"><span data-stu-id="44d99-133">Group or tab on the page (for example, the name of a FastTab)</span></span>

<span data-ttu-id="44d99-134">Ad esempio, l'utente digita **tot** nel campo di **ricerca azioni** ed esamina l'elenco risultati.</span><span class="sxs-lookup"><span data-stu-id="44d99-134">For example, you typed **tot** in the **action search** field and are now examining the results list.</span></span> <span data-ttu-id="44d99-135">La prima voce, per un pulsante denominato **Totali**, viene evidenziata.</span><span class="sxs-lookup"><span data-stu-id="44d99-135">The first entry, for a button that is named **Totals**, is highlighted.</span></span> <span data-ttu-id="44d99-136">Viene inoltre visualizzato un percorso di pulsante di **Ordine cliente** &gt; **Visualizza**.</span><span class="sxs-lookup"><span data-stu-id="44d99-136">A button path of **Sales order** &gt; **View** is also shown.</span></span> <span data-ttu-id="44d99-137">La parte **Ordine cliente** del percorso corrisponde alla scheda **Ordine cliente** nel riquadro azioni e la parte **Visualizza** del percorso corrisponde al gruppo **Visualizza** nella relativa scheda.</span><span class="sxs-lookup"><span data-stu-id="44d99-137">The **Sales order** part of the path corresponds to the **Sales order** tab on the Action Pane, and the **View** part of the path corresponds to the **View** group on that tab.</span></span> <span data-ttu-id="44d99-138">Analogamente, il percorso del pulsante **Sconto totale** (**Vendi** &gt; **Calcola**) indica che questo pulsante è situato nel gruppo **Calcola** nella scheda **Vendi** del riquadro azioni.</span><span class="sxs-lookup"><span data-stu-id="44d99-138">Similarly, the path of the **Total discount** button (**Sell** &gt; **Calculate**) informs you that this button is located in the **Calculate** group on the **Sell** tab of the Action Pane.</span></span> <span data-ttu-id="44d99-139">Di conseguenza, queste informazioni aiutano a comprendere esattamente quale pulsante verrà attivato dalla ricerca di azioni (se si seleziona tale pulsante nell'elenco dei risultati).</span><span class="sxs-lookup"><span data-stu-id="44d99-139">Therefore, this information helps you understand exactly which button will be triggered by action search (if you select that button in the results list).</span></span> 

<span data-ttu-id="44d99-140">[![campo-di-ricerca-azioni-con-dati](./media/action-search-field-with-data.png)](./media/action-search-field-with-data.png)</span><span class="sxs-lookup"><span data-stu-id="44d99-140">[![action-search-field-with-data](./media/action-search-field-with-data.png)](./media/action-search-field-with-data.png)</span></span> 

<span data-ttu-id="44d99-141">Nell'esempio precedente, la ricerca azioni ha mostrato i risultati dal riquadro azioni standard nella parte superiore della pagina.</span><span class="sxs-lookup"><span data-stu-id="44d99-141">In the previous example, action search showed results from the standard Action Pane at the top of a page.</span></span> <span data-ttu-id="44d99-142">Tuttavia, la ricerca azioni mostra anche i risultati delle barre degli strumenti visibili situate in altri punti della pagina.</span><span class="sxs-lookup"><span data-stu-id="44d99-142">However, action search also shows results from visible toolbars that are located in other places on the page.</span></span> <span data-ttu-id="44d99-143">Ad esempio, se si cerca il pulsante **Scorte disponibili** situato nella scheda dettaglio **Righe ordine cliente**.</span><span class="sxs-lookup"><span data-stu-id="44d99-143">For example, you're searching for the **On-hand inventory** button that is located on the **Sales order lines** FastTab.</span></span> <span data-ttu-id="44d99-144">In questo caso, il percorso del pulsante nell'elenco dei risultati (**Righe ordine cliente** &gt; **Scorte** &gt; **Visualizza**) indica che questo pulsante è situato sotto l'intestazione **Visualizza** nel pulsante di menu **Scorte** nella scheda dettaglio **Righe ordine cliente**.</span><span class="sxs-lookup"><span data-stu-id="44d99-144">In this case, the button path in the results list (**Sales order lines** &gt; **Inventory** &gt; **View**) informs you that this button is located under the **View** heading on the **Inventory** menu button on the **Sales order lines** FastTab.</span></span> 

<span data-ttu-id="44d99-145">[![scorte-disponibili](./media/on-hand-inventory.png)](./media/on-hand-inventory.png)</span><span class="sxs-lookup"><span data-stu-id="44d99-145">[![on-hand-inventory](./media/on-hand-inventory.png)](./media/on-hand-inventory.png)</span></span>

## <a name="action-search-vs-navigation-search"></a><span data-ttu-id="44d99-146">Confronto tra ricerca di azioni e ricerca di navigazione</span><span class="sxs-lookup"><span data-stu-id="44d99-146">Action search vs. Navigation search</span></span>
<span data-ttu-id="44d99-147">La ricerca di azioni è destinata alla ricerca e all'esecuzione di azioni in una pagina, ma è disponibile un meccanismo di ricerca distinto che consente di cercare e passare alle pagine di Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="44d99-147">Whereas action search is intended to find and run actions on a page, there is a separate search mechanism for finding and navigating to pages in Finance and Operations.</span></span> <span data-ttu-id="44d99-148">Per ulteriori informazioni su tale funzionalità, vedere l'articolo [Ricerca per navigazione](navigation-search.md).</span><span class="sxs-lookup"><span data-stu-id="44d99-148">For more information about that feature, see the [Navigation search](navigation-search.md) article.</span></span>




