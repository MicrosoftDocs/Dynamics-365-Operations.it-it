---
title: Ricerca di azioni
description: In questo articolo viene descritta la funzionalità di ricerca di azioni. La ricerca di azioni consente di individuare ed eseguire azioni in una pagina.
author: jasongre
manager: AnnBe
ms.date: 03/09/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.custom: 62303
ms.assetid: 62c70de0-fdde-4417-8e08-0583fb095a40
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: dd9962451e8b72677e1a006dd9c1b8b8b268c93e
ms.sourcegitcommit: b112925c389a460a98c3401cc2c67df7091b066f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/19/2020
ms.locfileid: "4798649"
---
# <a name="action-search"></a><span data-ttu-id="a5c22-104">Ricerca di azioni</span><span class="sxs-lookup"><span data-stu-id="a5c22-104">Action search</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a5c22-105">In questo articolo viene descritta la funzionalità di ricerca di azioni.</span><span class="sxs-lookup"><span data-stu-id="a5c22-105">This article describes the action search functionality.</span></span> <span data-ttu-id="a5c22-106">La ricerca di azioni consente di individuare ed eseguire azioni in una pagina.</span><span class="sxs-lookup"><span data-stu-id="a5c22-106">Action search will help you find and run actions on a page.</span></span>

## <a name="introduction"></a><span data-ttu-id="a5c22-107">Introduzione</span><span class="sxs-lookup"><span data-stu-id="a5c22-107">Introduction</span></span>

<span data-ttu-id="a5c22-108">Le pagine espongono principalmente i controlli presenti nei riquadri azioni, sia il riquadro azioni standard visualizzato nella parte superiore di una pagina sia le barre degli strumenti visualizzate in diverse aree della pagina.</span><span class="sxs-lookup"><span data-stu-id="a5c22-108">Pages primarily expose commands on Action Panes, both the standard Action Pane that appears at the top of a page and the toolbars that appear in various sections of the page.</span></span> <span data-ttu-id="a5c22-109">Nelle versioni precedenti, una funzionalità Descrizione dei tasti consente di accedere rapidamente a qualsiasi pulsante in un riquadro azioni premendo il tasto ALT e una serie di lettere.</span><span class="sxs-lookup"><span data-stu-id="a5c22-109">In previous versions, a Key Tips feature let you quickly access any button on an Action Pane by pressing the Alt key and then a series of letters.</span></span>

<span data-ttu-id="a5c22-110">[![keyTipsAX6](./media/keytipsax6.png)](./media/keytipsax6.png)</span><span class="sxs-lookup"><span data-stu-id="a5c22-110">[![keyTipsAX6](./media/keytipsax6.png)](./media/keytipsax6.png)</span></span>

<span data-ttu-id="a5c22-111">La funzionalità di ricerca delle azioni sostituisce le descrizioni dei tasti che non sono più disponibili.</span><span class="sxs-lookup"><span data-stu-id="a5c22-111">The action search feature replaces Key Tips, which are no longer available.</span></span> <span data-ttu-id="a5c22-112">La nuova funzionalità consente di trovare rapidamente ed eseguire un pulsante da qualsiasi riquadro azioni visibile.</span><span class="sxs-lookup"><span data-stu-id="a5c22-112">This new feature lets you quickly search for and run a button from any visible Action Pane.</span></span>

## <a name="using-action-search"></a><span data-ttu-id="a5c22-113">Utilizzo della ricerca azioni</span><span class="sxs-lookup"><span data-stu-id="a5c22-113">Using action search</span></span>

<span data-ttu-id="a5c22-114">Per utilizzare la funzionalità di ricerca azioni, effettuare le operazioni indicate di seguito.</span><span class="sxs-lookup"><span data-stu-id="a5c22-114">To use the action search feature, follow these steps.</span></span>

1. <span data-ttu-id="a5c22-115">Nel riquadro azioni fare clic nel campo di **ricerca azioni**.</span><span class="sxs-lookup"><span data-stu-id="a5c22-115">On the Action Pane, click in the **action search** field.</span></span> <span data-ttu-id="a5c22-116">(Il campo di **ricerca azioni** contiene un'icona a forma di lente d'ingrandimento).</span><span class="sxs-lookup"><span data-stu-id="a5c22-116">(The **action search** field contains a magnifying glass icon.)</span></span>
2. <span data-ttu-id="a5c22-117">Digitare integralmente o parzialmente il nome del pulsante che si desidera eseguire.</span><span class="sxs-lookup"><span data-stu-id="a5c22-117">Type all or part of the name of the button that you want to run.</span></span> <span data-ttu-id="a5c22-118">È inoltre possibile eseguire la ricerca utilizzando le parole dal "percorso" del pulsante.</span><span class="sxs-lookup"><span data-stu-id="a5c22-118">You can also search by using words from the button's "path."</span></span> <span data-ttu-id="a5c22-119">(Per ulteriori informazioni, vedere la sezione successiva dell'articolo). In genere, un pulsante verrà visualizzato vicino alla parte superiore dell'elenco dei risultati dopo aver digitato da due a quattro caratteri.</span><span class="sxs-lookup"><span data-stu-id="a5c22-119">(For more information, see the next section of this article.) Typically, a button will appear near the top of the results list after you've typed two to four characters.</span></span>
3. <span data-ttu-id="a5c22-120">Individuare ed eseguire il pulsante nell'elenco risultati (mediante il mouse o tastiera).</span><span class="sxs-lookup"><span data-stu-id="a5c22-120">Find and run the button in the results list (by using your mouse or keyboard).</span></span>

<span data-ttu-id="a5c22-121">Dopo che il pulsante viene eseguito, lo stato attivo torna all'ultima posizione nella pagina, in modo che sia possibile continuare a lavorare.</span><span class="sxs-lookup"><span data-stu-id="a5c22-121">After the button is run, the focus is returned to your last position on the page, so that you can continue to work.</span></span>

<span data-ttu-id="a5c22-122">[![campo-di-ricerca-azioni](./media/action-search-field.png)](./media/action-search-field.png)</span><span class="sxs-lookup"><span data-stu-id="a5c22-122">[![action-search-field](./media/action-search-field.png)](./media/action-search-field.png)</span></span>

<span data-ttu-id="a5c22-123">È inoltre possibile avviare la ricerca azioni premendo i tasti CTRL+/ o ALT+Q.</span><span class="sxs-lookup"><span data-stu-id="a5c22-123">You can also start action search by pressing Ctrl+/ or Alt+Q.</span></span> <span data-ttu-id="a5c22-124">Premere di nuovo i tasti di scelta rapida per riportare lo stato attivo all'ultima posizione nella pagina.</span><span class="sxs-lookup"><span data-stu-id="a5c22-124">Press the keyboard shortcut again to return the focus to your last position on the page.</span></span>

## <a name="understanding-the-results-list"></a><span data-ttu-id="a5c22-125">Interpretazione dell'elenco dei risultati</span><span class="sxs-lookup"><span data-stu-id="a5c22-125">Understanding the results list</span></span>

<span data-ttu-id="a5c22-126">Spesso, è necessario conoscere l'ubicazione e il contesto di un pulsante per comprendere completamente lo scopo di tale pulsante.</span><span class="sxs-lookup"><span data-stu-id="a5c22-126">Often, you must know both the location and the context of a button to fully understand the purpose of that button.</span></span> <span data-ttu-id="a5c22-127">Di conseguenza, nell'elenco dei risultati vengono mostrate informazioni aggiuntive per ciascun articolo, al fine di aiutare a comprendere esattamente quali pulsanti vengono visualizzati nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="a5c22-127">Therefore, the results list shows additional information to help you understand exactly which buttons appear in the list.</span></span> <span data-ttu-id="a5c22-128">In particolare, verrà visualizzato "il percorso" del pulsante.</span><span class="sxs-lookup"><span data-stu-id="a5c22-128">In particular, the "path" of the button is shown.</span></span> <span data-ttu-id="a5c22-129">Questo percorso può includere le etichette dei seguenti elementi di interfaccia utente, a seconda dei casi:</span><span class="sxs-lookup"><span data-stu-id="a5c22-129">This path might include the labels of the following UI elements, as relevant:</span></span>

- <span data-ttu-id="a5c22-130">Scheda del riquadro azioni</span><span class="sxs-lookup"><span data-stu-id="a5c22-130">Action Pane tab</span></span>
- <span data-ttu-id="a5c22-131">Gruppo pulsanti</span><span class="sxs-lookup"><span data-stu-id="a5c22-131">Button group</span></span>
- <span data-ttu-id="a5c22-132">Pulsante di menu (se il pulsante è all'interno di un pulsante di menu)</span><span class="sxs-lookup"><span data-stu-id="a5c22-132">Menu button (if the button is inside a menu button)</span></span>
- <span data-ttu-id="a5c22-133">Separatore di menu (se il pulsante è interno un gruppo denominato all'interno di un pulsante di menu)</span><span class="sxs-lookup"><span data-stu-id="a5c22-133">Menu separator (if the button is inside a named group inside a menu button)</span></span>
- <span data-ttu-id="a5c22-134">Gruppo o scheda nella pagina (ad esempio, il nome di una scheda dettaglio)</span><span class="sxs-lookup"><span data-stu-id="a5c22-134">Group or tab on the page (for example, the name of a FastTab)</span></span>

<span data-ttu-id="a5c22-135">Ad esempio, l'utente digita **tot** nel campo di **ricerca azioni** ed esamina l'elenco risultati.</span><span class="sxs-lookup"><span data-stu-id="a5c22-135">For example, you typed **tot** in the **action search** field and are now examining the results list.</span></span> <span data-ttu-id="a5c22-136">La prima voce, per un pulsante denominato **Totali**, viene evidenziata.</span><span class="sxs-lookup"><span data-stu-id="a5c22-136">The first entry, for a button that is named **Totals**, is highlighted.</span></span> <span data-ttu-id="a5c22-137">Viene inoltre visualizzato un percorso di pulsante di **Ordine cliente** &gt; **Visualizza**.</span><span class="sxs-lookup"><span data-stu-id="a5c22-137">A button path of **Sales order** &gt; **View** is also shown.</span></span> <span data-ttu-id="a5c22-138">La parte **Ordine cliente** del percorso corrisponde alla scheda **Ordine cliente** nel riquadro azioni e la parte **Visualizza** del percorso corrisponde al gruppo **Visualizza** in quella scheda. Analogamente, il percorso del pulsante **Sconto totale** (**Vendi** &gt; **Calcola**) indica che questo pulsante si trova nel gruppo **Calcola** nella scheda **Vendi** del riquadro azioni.</span><span class="sxs-lookup"><span data-stu-id="a5c22-138">The **Sales order** part of the path corresponds to the **Sales order** tab on the Action Pane, and the **View** part of the path corresponds to the **View** group on that tab. Similarly, the path of the **Total discount** button (**Sell** &gt; **Calculate**) informs you that this button is located in the **Calculate** group on the **Sell** tab of the Action Pane.</span></span> <span data-ttu-id="a5c22-139">Di conseguenza, queste informazioni aiutano a comprendere esattamente quale pulsante verrà attivato dalla ricerca di azioni (se si seleziona tale pulsante nell'elenco dei risultati).</span><span class="sxs-lookup"><span data-stu-id="a5c22-139">Therefore, this information helps you understand exactly which button will be triggered by action search (if you select that button in the results list).</span></span>

<span data-ttu-id="a5c22-140">[![campo-di-ricerca-azioni-con-dati](./media/action-search-field-with-data.png)](./media/action-search-field-with-data.png)</span><span class="sxs-lookup"><span data-stu-id="a5c22-140">[![action-search-field-with-data](./media/action-search-field-with-data.png)](./media/action-search-field-with-data.png)</span></span>

<span data-ttu-id="a5c22-141">Nell'esempio precedente, la ricerca azioni ha mostrato i risultati dal riquadro azioni standard nella parte superiore della pagina.</span><span class="sxs-lookup"><span data-stu-id="a5c22-141">In the previous example, action search showed results from the standard Action Pane at the top of a page.</span></span> <span data-ttu-id="a5c22-142">Tuttavia, la ricerca azioni mostra anche i risultati delle barre degli strumenti visibili situate in altri punti della pagina.</span><span class="sxs-lookup"><span data-stu-id="a5c22-142">However, action search also shows results from visible toolbars that are in other places on the page.</span></span> <span data-ttu-id="a5c22-143">Ad esempio, se si cerca il pulsante **Scorte disponibili** situato nella scheda dettaglio **Righe ordine cliente**.</span><span class="sxs-lookup"><span data-stu-id="a5c22-143">For example, you're searching for the **On-hand inventory** button that is on the **Sales order lines** FastTab.</span></span> <span data-ttu-id="a5c22-144">In questo caso, il percorso del pulsante nell'elenco dei risultati (**Righe ordine cliente** &gt; **Scorte** &gt; **Visualizza**) indica che questo pulsante è situato sotto l'intestazione **Visualizza** nel pulsante di menu **Scorte** nella scheda dettaglio **Righe ordine cliente**.</span><span class="sxs-lookup"><span data-stu-id="a5c22-144">In this case, the button path in the results list (**Sales order lines** &gt; **Inventory** &gt; **View**) informs you that this button is under the **View** heading on the **Inventory** menu button on the **Sales order lines** FastTab.</span></span>

<span data-ttu-id="a5c22-145">[![scorte-disponibili](./media/on-hand-inventory.png)](./media/on-hand-inventory.png)</span><span class="sxs-lookup"><span data-stu-id="a5c22-145">[![on-hand-inventory](./media/on-hand-inventory.png)](./media/on-hand-inventory.png)</span></span>

> [!NOTE]
> <span data-ttu-id="a5c22-146">Esistono alcuni pulsanti che non vengono visualizzati nella ricerca di azioni.</span><span class="sxs-lookup"><span data-stu-id="a5c22-146">There are some buttons that do not show up in Action search.</span></span> <span data-ttu-id="a5c22-147">Sono inclusi i pulsanti di dialogo a discesa e i pulsanti di moduli secondari.</span><span class="sxs-lookup"><span data-stu-id="a5c22-147">These include drop dialog buttons and buttons from subforms.</span></span> 

## <a name="action-search-vs-navigation-search"></a><span data-ttu-id="a5c22-148">Confronto tra ricerca di azioni e ricerca di navigazione</span><span class="sxs-lookup"><span data-stu-id="a5c22-148">Action search vs. Navigation search</span></span>

<span data-ttu-id="a5c22-149">La ricerca di azioni è destinata alla ricerca e all'esecuzione di azioni in una pagina, ma è disponibile un meccanismo di ricerca distinto che consente di cercare e passare alle pagine.</span><span class="sxs-lookup"><span data-stu-id="a5c22-149">Whereas action search is intended to find and run actions on a page, there is a separate search mechanism for finding and navigating to pages.</span></span> <span data-ttu-id="a5c22-150">Per ulteriori informazioni su tale funzionalità, vedere l'articolo [Ricerca per navigazione](navigation-search.md).</span><span class="sxs-lookup"><span data-stu-id="a5c22-150">For more information about that feature, see the [Navigation search](navigation-search.md) article.</span></span>
