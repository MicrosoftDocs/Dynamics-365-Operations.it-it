---
title: Editor di formule avanzato per report elettronici
description: In questo argomento viene descritto come utilizzare l'editor di formule avanzato per configurare espressioni nei componenti di formato e nel mapping di modelli per report elettronici (ER).
author: NickSelin
ms.date: 04/10/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, ERExpressionDesignerFormula
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-04-01
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: d18aeedb2f21176ffe964b926168d4bf088a093b
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5751210"
---
# <a name="electronic-reporting-advanced-formula-editor"></a><span data-ttu-id="b6241-103">Editor di formule avanzato per report elettronici</span><span class="sxs-lookup"><span data-stu-id="b6241-103">Electronic reporting advanced formula editor</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b6241-104">Oltre all'[editor di formule](general-electronic-reporting-formula-designer.md) per [report elettronici](general-electronic-reporting.md) è possibile utilizzare l'editor di formule per report elettronici avanzato per migliorare l'esperienza di configurazione delle espressioni ER.</span><span class="sxs-lookup"><span data-stu-id="b6241-104">In addition to the [Electronic reporting](general-electronic-reporting.md) [formula editor](general-electronic-reporting-formula-designer.md), you can use the advanced Electronic reporting formula editor to improve the experience of configuring Electronic reporting (ER) expressions.</span></span> <span data-ttu-id="b6241-105">L'editor avanzato è basato su browser e utilizza l'[editor Monaco](https://microsoft.github.io/monaco-editor).</span><span class="sxs-lookup"><span data-stu-id="b6241-105">The advanced editor is browser-based and powered by the [Monaco editor](https://microsoft.github.io/monaco-editor).</span></span> <span data-ttu-id="b6241-106">Le funzionalità dell'editor avanzato più comunemente utilizzate sono descritte in questo argomento:</span><span class="sxs-lookup"><span data-stu-id="b6241-106">The most commonly used advanced editor features are described in this topic:</span></span>

- [<span data-ttu-id="b6241-107">Formattazione automatica del codice</span><span class="sxs-lookup"><span data-stu-id="b6241-107">Code autoformatting</span></span>](#Autoformatting)
- [<span data-ttu-id="b6241-108">IntelliSense</span><span class="sxs-lookup"><span data-stu-id="b6241-108">IntelliSense</span></span>](#IntelliSense)
- [<span data-ttu-id="b6241-109">Completamento del codice</span><span class="sxs-lookup"><span data-stu-id="b6241-109">Code completion</span></span>](#CodeCompletion)
- [<span data-ttu-id="b6241-110">Navigazione nel codice</span><span class="sxs-lookup"><span data-stu-id="b6241-110">Code navigation</span></span>](#CodeNavigation)
- [<span data-ttu-id="b6241-111">Strutturazione del codice</span><span class="sxs-lookup"><span data-stu-id="b6241-111">Code structuring</span></span>](#CodeStructuring)
- [<span data-ttu-id="b6241-112">Trova e sostituisci</span><span class="sxs-lookup"><span data-stu-id="b6241-112">Find and replace</span></span>](#FindAndReplace)
- [<span data-ttu-id="b6241-113">Incollare dati</span><span class="sxs-lookup"><span data-stu-id="b6241-113">Data pasting</span></span>](#DataPasting)
- [<span data-ttu-id="b6241-114">Colorazione della sintassi</span><span class="sxs-lookup"><span data-stu-id="b6241-114">Syntax colorization</span></span>](#SyntaxColorization)

## <a name=""></a><span data-ttu-id="b6241-115"><a name="ActivateAdvEditor">Attivare l'editor di formule avanzato</a></span><span class="sxs-lookup"><span data-stu-id="b6241-115"><a name="ActivateAdvEditor">Activate the advanced formula editor</a></span></span>

<span data-ttu-id="b6241-116">Completare i seguenti passaggi per iniziare a utilizzare l'editor di formule avanzato nell'istanza di Microsoft Dynamics 365 Finance.</span><span class="sxs-lookup"><span data-stu-id="b6241-116">Complete the following steps to start using the advanced formula editor in your instance of Microsoft Dynamics 365 Finance.</span></span>

1.  <span data-ttu-id="b6241-117">Andare a **Amministrazione organizzazione** \> **Creazione di report elettronici** \> **Configurazioni**.</span><span class="sxs-lookup"><span data-stu-id="b6241-117">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2.  <span data-ttu-id="b6241-118">Nella pagina **Configurazioni**, nel Riquadro azioni, nella scheda **Configurazioni**, nel gruppo **Impostazioni avanzate**, selezionare **Parametri utente**.</span><span class="sxs-lookup"><span data-stu-id="b6241-118">On the **Configurations** page, on the Action Pane, on the **Configurations** tab, in the **Advanced settings** group, select **User parameters**.</span></span>
3.  <span data-ttu-id="b6241-119">Nella finestra di dialogo **Parametri utente**, nella sezione **Traccia esecuzione**, impostare il parametro **Abilita editor di formule avanzato** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="b6241-119">In the **User parameters** dialog box, in the **Execution tracing** section, set the **Enable advanced formula editor** parameter to **Yes**.</span></span>

<span data-ttu-id="b6241-120">[![Pagina delle configurazioni ER](./media/ER-AdvEditor-Activate.png)](./media/ER-AdvEditor-Activate.png)</span><span class="sxs-lookup"><span data-stu-id="b6241-120">[![ER configurations page](./media/ER-AdvEditor-Activate.png)](./media/ER-AdvEditor-Activate.png)</span></span>

> [!NOTE]
> <span data-ttu-id="b6241-121">Tenere presente che questo parametro è specifico dell'utente e dell'azienda.</span><span class="sxs-lookup"><span data-stu-id="b6241-121">Be aware that this parameter is user specific and company specific.</span></span>

## <a name=""></a><span data-ttu-id="b6241-122"><a name="Autoformatting">Formattazione automatica del codice</a></span><span class="sxs-lookup"><span data-stu-id="b6241-122"><a name="Autoformatting">Code autoformatting</a></span></span>

<span data-ttu-id="b6241-123">Quando si scrive un'espressione complessa composta da più righe di codice, il rientro di una nuova riga immessa sarà automatico in base al rientro della riga precedente.</span><span class="sxs-lookup"><span data-stu-id="b6241-123">When you write a complex expression that consists of multiple rows of code, the indentation of a new entered line will be automatic based on the indentation of the previous row.</span></span> <span data-ttu-id="b6241-124">È possibile selezionare le righe e modificarne il rientro digitando **TAB** o **MAIUSC + TAB**.</span><span class="sxs-lookup"><span data-stu-id="b6241-124">You can select lines and change their indentation by typing **Tab** or **Shift+Tab**.</span></span>

<span data-ttu-id="b6241-125">[![Editor di formule ER](./media/ER-AdvEditor-Indentation.gif)](./media/ER-AdvEditor-Indentation.gif)</span><span class="sxs-lookup"><span data-stu-id="b6241-125">[![ER formula editor](./media/ER-AdvEditor-Indentation.gif)](./media/ER-AdvEditor-Indentation.gif)</span></span>

<span data-ttu-id="b6241-126">La formattazione automatica consente di mantenere l'intera espressione ben formattata per facilitare ulteriormente la manutenzione e semplificare la comprensione della logica configurata.</span><span class="sxs-lookup"><span data-stu-id="b6241-126">Autoformatting allows you to keep the entire expression well formatted to make further maintenance easier and to simplify understanding of the configured logic.</span></span>

## <a name=""></a><span data-ttu-id="b6241-127"><a name="IntelliSense">IntelliSense</a></span><span class="sxs-lookup"><span data-stu-id="b6241-127"><a name="IntelliSense">IntelliSense</a></span></span>

<span data-ttu-id="b6241-128">L'editor fornisce il completamento delle parole per consentire una scrittura più veloce delle espressioni ed evitare errori di battitura.</span><span class="sxs-lookup"><span data-stu-id="b6241-128">The editor provides word completion to help you write expression faster and avoid typos.</span></span> <span data-ttu-id="b6241-129">Quando si comincia a aggiungere testo, l'editor offre automaticamente un elenco di funzioni supportate nelle funzioni ER che contengono i caratteri immessi.</span><span class="sxs-lookup"><span data-stu-id="b6241-129">When you start adding new text, the editor automatically offers a list of functions supported in ER functions that contain the characters you have entered.</span></span> <span data-ttu-id="b6241-130">È inoltre possibile attivare IntelliSense ovunque in un'espressione configurata digitando **CTRL + BARRA SPAZIATRICE**.</span><span class="sxs-lookup"><span data-stu-id="b6241-130">You can also trigger IntelliSense in any place of a configured expression by typing **Ctrl+Space**.</span></span>

<span data-ttu-id="b6241-131">[![Editor di formule ER](./media/ER-AdvEditor-Intelisense.gif)](./media/ER-AdvEditor-Intelisense.gif)</span><span class="sxs-lookup"><span data-stu-id="b6241-131">[![ER formula editor](./media/ER-AdvEditor-Intelisense.gif)](./media/ER-AdvEditor-Intelisense.gif)</span></span>

## <a name=""></a><span data-ttu-id="b6241-132"><a name="CodeCompletion">Completamento del codice</a></span><span class="sxs-lookup"><span data-stu-id="b6241-132"><a name="CodeCompletion">Code completion</a></span></span>

<span data-ttu-id="b6241-133">L'editor fornisce automaticamente il completamento del codice tramite:</span><span class="sxs-lookup"><span data-stu-id="b6241-133">The editor automatically provides code completion by:</span></span>

- <span data-ttu-id="b6241-134">Inserimento di una parentesi quadra chiusa quando si inserisce una parentesi quadra aperta, mantenendo il cursore all'interno delle parentesi quadre.</span><span class="sxs-lookup"><span data-stu-id="b6241-134">Inserting a closing bracket when an opening  bracket is entered, keeping the cursor inside the brackets.</span></span>
- <span data-ttu-id="b6241-135">Inserimento della seconda virgoletta quando viene inserita la prima, mantenendo il cursore all'interno delle virgolette.</span><span class="sxs-lookup"><span data-stu-id="b6241-135">Inserting the second quotation symbol when the first one is entered, keeping the cursor inside the quotations.</span></span>
- <span data-ttu-id="b6241-136">Inserimento delle seconde virgolette doppie quando vengono inserite le prime, mantenendo il cursore all'interno delle virgolette.</span><span class="sxs-lookup"><span data-stu-id="b6241-136">Inserting the second double quotation symbol when the first one is entered, keeping the cursor inside the quotations.</span></span>

<span data-ttu-id="b6241-137">[![Editor di formule ER](./media/ER-AdvEditor-CodeCompletion.gif)](./media/ER-AdvEditor-CodeCompletion.gif)</span><span class="sxs-lookup"><span data-stu-id="b6241-137">[![ER formula editor](./media/ER-AdvEditor-CodeCompletion.gif)](./media/ER-AdvEditor-CodeCompletion.gif)</span></span>

<span data-ttu-id="b6241-138">Quando si punta alla parentesi tipizzata, la seconda parentesi di questa coppia viene automaticamente evidenziata per mostrare il costrutto che supportano.</span><span class="sxs-lookup"><span data-stu-id="b6241-138">When you point to the typed bracket, the second bracket of this pair is automatically highlighted to show the construct that they support.</span></span>

## <a name=""></a><span data-ttu-id="b6241-139"><a name="CodeNavigation">Navigazione nel codice</a></span><span class="sxs-lookup"><span data-stu-id="b6241-139"><a name="CodeNavigation">Code navigation</a></span></span>

<span data-ttu-id="b6241-140">È possibile individuare i simboli o le righe richiesti nell'espressione digitando il comando **Vai a** utilizzando il riquadro comandi o il menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="b6241-140">You can locate required symbols or lines in your expression by typing the **Go to** command using the command palette or the context menu.</span></span>

<span data-ttu-id="b6241-141">Ad esempio, per passare alla riga **8** procedere come segue:</span><span class="sxs-lookup"><span data-stu-id="b6241-141">For example, to jump to line **8**, do the following:</span></span>

- <span data-ttu-id="b6241-142">Premere **CTRL + G**, immettere il valore **8**, quindi premere **INVIO**.</span><span class="sxs-lookup"><span data-stu-id="b6241-142">Press **Ctrl+G**, enter the value **8**, and then press **Enter**.</span></span>

  <span data-ttu-id="b6241-143">oppure</span><span class="sxs-lookup"><span data-stu-id="b6241-143">-or-</span></span>

- <span data-ttu-id="b6241-144">Premere **F1**, digitare **G**, selezionare **Vai a riga**, immettere il valore **8** e premere **INVIO**.</span><span class="sxs-lookup"><span data-stu-id="b6241-144">Press **F1**, type **G**, select **Go to line**, enter the value **8**, and the press **Enter**.</span></span>

<span data-ttu-id="b6241-145">[![Editor di formule ER](./media/ER-AdvEditor-Goto.gif)](./media/ER-AdvEditor-Goto.gif)</span><span class="sxs-lookup"><span data-stu-id="b6241-145">[![ER formula editor](./media/ER-AdvEditor-Goto.gif)](./media/ER-AdvEditor-Goto.gif)</span></span>

## <a name=""></a><span data-ttu-id="b6241-146"><a name="CodeStructuring">Strutturazione del codice</a></span><span class="sxs-lookup"><span data-stu-id="b6241-146"><a name="CodeStructuring">Code structuring</a></span></span>

<span data-ttu-id="b6241-147">Il codice per alcune funzioni, come ad esempio [IF](er-functions-logical-if.md)o [CASE](er-functions-logical-case.md), viene automaticamente strutturato.</span><span class="sxs-lookup"><span data-stu-id="b6241-147">The code for some functions, such as [IF](er-functions-logical-if.md) or [CASE](er-functions-logical-case.md), is automatically structured.</span></span> <span data-ttu-id="b6241-148">È possibile espandere e comprimere una o tutte le aree di riduzione di questo codice per ridurre la parte modificabile di un'espressione al fine di concentrarsi solo sulla parte di codice che richiede attenzione.</span><span class="sxs-lookup"><span data-stu-id="b6241-148">You can expand and collapse any or all of the folding regions of this code to reduce the editable part of an expression in order to focus on only  thepiece of code that requires your attention.</span></span> <span data-ttu-id="b6241-149">I comandi di attivazione/disattivazione Riduci/Espandi possono essere usati a questo scopo.</span><span class="sxs-lookup"><span data-stu-id="b6241-149">The toggle fold/unfold commands can be used for that.</span></span>

<span data-ttu-id="b6241-150">Ad esempio, per ridurre tutte le aree, procedere come segue:</span><span class="sxs-lookup"><span data-stu-id="b6241-150">For example, to fold all regions, do the following:</span></span>

- <span data-ttu-id="b6241-151">Premere **CTRL + K**</span><span class="sxs-lookup"><span data-stu-id="b6241-151">Press **Ctrl+K**</span></span>

  <span data-ttu-id="b6241-152">oppure</span><span class="sxs-lookup"><span data-stu-id="b6241-152">-or-</span></span>

- <span data-ttu-id="b6241-153">Premere **F1** e quindi **FO**, selezionare **Riduci tutto**, quindi premere **INVIO**</span><span class="sxs-lookup"><span data-stu-id="b6241-153">Press **F1**, press **FO**, select **Fold all**, and then press **Enter**</span></span>

<span data-ttu-id="b6241-154">Per espandere tutte le aree, procedere come segue:</span><span class="sxs-lookup"><span data-stu-id="b6241-154">To unfold all regions, do the following:</span></span>

- <span data-ttu-id="b6241-155">Premere **CTRL + J**</span><span class="sxs-lookup"><span data-stu-id="b6241-155">Press **Ctrl+J**</span></span>

  <span data-ttu-id="b6241-156">oppure</span><span class="sxs-lookup"><span data-stu-id="b6241-156">-or-</span></span>
  
- <span data-ttu-id="b6241-157">Premere **F1** digitare **UN**, selezionare **Espandi tutto**, quindi premere **INVIO**</span><span class="sxs-lookup"><span data-stu-id="b6241-157">Press **F1**, type **UN**, select **Unfold all**, and then press **Enter**</span></span>

<span data-ttu-id="b6241-158">[![Editor di formule ER](./media/ER-AdvEditor-ToggleFold.gif)](./media/ER-AdvEditor-ToggleFold.gif)</span><span class="sxs-lookup"><span data-stu-id="b6241-158">[![ER formula editor](./media/ER-AdvEditor-ToggleFold.gif)](./media/ER-AdvEditor-ToggleFold.gif)</span></span>

## <a name=""></a><span data-ttu-id="b6241-159"><a name="FindAndReplace">Trova e sostituisci</a></span><span class="sxs-lookup"><span data-stu-id="b6241-159"><a name="FindAndReplace">Find and replace</a></span></span>

<span data-ttu-id="b6241-160">Per trovare occorrenze di un determinato testo, selezionare il testo nell'espressione ed eseguire le seguenti operazioni:</span><span class="sxs-lookup"><span data-stu-id="b6241-160">To find occurrences of certain text, select the text in your expression, and do the following:</span></span>

- <span data-ttu-id="b6241-161">Premere **CTRL + F** e quindi premere **F3** per trovare la ricorrenza successiva del testo selezionato oppure premere **MAIUSC + F3** per trovare l'occorrenza precedente.</span><span class="sxs-lookup"><span data-stu-id="b6241-161">Press **Ctrl+F** and then press **F3** to find the next occurrence of the selected text, or press **Shift+F3** to find the previous occurrence.</span></span>

  <span data-ttu-id="b6241-162">oppure</span><span class="sxs-lookup"><span data-stu-id="b6241-162">-or-</span></span>
  
- <span data-ttu-id="b6241-163">Premere **F1**, digitare **F**, quindi selezionare l'opzione necessaria per trovare il testo selezionato.</span><span class="sxs-lookup"><span data-stu-id="b6241-163">Press **F1**, type **F**, and then select the required option to find the selected text.</span></span>

<span data-ttu-id="b6241-164">Per sostituire occorrenze di un determinato testo, selezionare il testo nell'espressione ed eseguire le seguenti operazioni:</span><span class="sxs-lookup"><span data-stu-id="b6241-164">To replace occurrences of a certain text, select the text in your expression, and do the following:</span></span>

- <span data-ttu-id="b6241-165">Premere **CTRL + H**.</span><span class="sxs-lookup"><span data-stu-id="b6241-165">Press **Ctrl+H**.</span></span> <span data-ttu-id="b6241-166">Immettere il testo alternativo e selezionare l'opzione di sostituzione per sostituire il testo selezionato o tutte le occorrenze di tale testo nell'espressione corrente.</span><span class="sxs-lookup"><span data-stu-id="b6241-166">Enter the alternative text and select the replacement option to replace either the selected text or all occurrences of this text in the current expression.</span></span>

  <span data-ttu-id="b6241-167">oppure</span><span class="sxs-lookup"><span data-stu-id="b6241-167">-or-</span></span>
  
- <span data-ttu-id="b6241-168">Premere **F1**, digitare **R**, quindi selezionare l'opzione necessaria per sostituire il testo selezionato.</span><span class="sxs-lookup"><span data-stu-id="b6241-168">Press **F1**, type **R**, and then select the required option to replace the selected text.</span></span> <span data-ttu-id="b6241-169">Immettere il testo alternativo e selezionare l'opzione di sostituzione per sostituire il testo selezionato o tutte le occorrenze di tale testo nell'espressione corrente.</span><span class="sxs-lookup"><span data-stu-id="b6241-169">Enter the alternative text and select the replacement option to replace either the selected text or all occurrences of this text in the current expression.</span></span>

<span data-ttu-id="b6241-170">Per cambiare tutte occorrenze di un determinato testo, selezionare il testo nell'espressione ed eseguire le seguenti operazioni:</span><span class="sxs-lookup"><span data-stu-id="b6241-170">To change all occurrences of a certain text, select the text in your expression, and do the following:</span></span>

- <span data-ttu-id="b6241-171">Premere **CTRL + F2** e quindi inserire il testo alternativo.</span><span class="sxs-lookup"><span data-stu-id="b6241-171">Press **Ctrl+F2** and then enter the alternative text.</span></span>

  <span data-ttu-id="b6241-172">oppure</span><span class="sxs-lookup"><span data-stu-id="b6241-172">-or-</span></span>
  
- <span data-ttu-id="b6241-173">Premere **F1**, digitare **C**, quindi selezionare l'opzione necessaria per cambiare il testo selezionato.</span><span class="sxs-lookup"><span data-stu-id="b6241-173">Press **F1**, type **C**, and then select the required option to change the selected text.</span></span> <span data-ttu-id="b6241-174">Immettere il testo alternativo.</span><span class="sxs-lookup"><span data-stu-id="b6241-174">Enter the alternative text.</span></span>

<span data-ttu-id="b6241-175">[![Editor di formule ER](./media/ER-AdvEditor-Find.gif)](./media/ER-AdvEditor-Find.gif)</span><span class="sxs-lookup"><span data-stu-id="b6241-175">[![ER formula editor](./media/ER-AdvEditor-Find.gif)](./media/ER-AdvEditor-Find.gif)</span></span>

## <a name=""></a><span data-ttu-id="b6241-176"><a name="DataPasting">Incollare origini dati e funzioni</a></span><span class="sxs-lookup"><span data-stu-id="b6241-176"><a name="DataPasting">Data sources and functions pasting</a></span></span>

<span data-ttu-id="b6241-177">È possibile selezionare **Aggiungi origine dati**, che consente di incollare nell'espressione corrente un'origine dati correntemente selezionata nel riquadro sinistro **Origine dati**.</span><span class="sxs-lookup"><span data-stu-id="b6241-177">You can select **Add data source**, which pastes to the current expression a data source that is currently selected on the **Data source** left panel.</span></span> <span data-ttu-id="b6241-178">Analogamente, è possibile selezionare **Aggiungi funzione**, che consente di incollare nell'espressione corrente la funzione correntemente selezionata nel riquadro destro **Funzioni**.</span><span class="sxs-lookup"><span data-stu-id="b6241-178">Simlilarly, you can select **Add function**, which pastes to the current expression a function that is currently selected on the **Functions** right panel.</span></span> <span data-ttu-id="b6241-179">Se si utilizza l'editor di formule ER, una funzione o un'origine dati selezionata verrà sempre incollata alla fine dell'espressione configurata.</span><span class="sxs-lookup"><span data-stu-id="b6241-179">If you use the ER formula editor, a selected function or a selected data source will always be pasted to the end of the configured expression.</span></span> <span data-ttu-id="b6241-180">Quando si utilizza l'editor di formule ER avanzato, una funzione o un'origine dati selezionata può essere incollata ovunque nell'espressione configurata.</span><span class="sxs-lookup"><span data-stu-id="b6241-180">When you use the advanced ER formula editor, a selected function or a selected data source can be pasted to any part of the configured expression.</span></span> <span data-ttu-id="b6241-181">Sarà necessario utilizzare il cursore per specificare dove si desidera incollare i dati.</span><span class="sxs-lookup"><span data-stu-id="b6241-181">You will need to use the cursor to specify where you want to paste the data.</span></span>

<span data-ttu-id="b6241-182">[![Editor di formule ER](./media/ER-AdvEditor-PasteValue.gif)](./media/ER-AdvEditor-PasteValue.gif)</span><span class="sxs-lookup"><span data-stu-id="b6241-182">[![ER formula editor](./media/ER-AdvEditor-PasteValue.gif)](./media/ER-AdvEditor-PasteValue.gif)</span></span>

## <a name=""></a><span data-ttu-id="b6241-183"><a name="SyntaxColorization">Colorazione della sintassi</a></span><span class="sxs-lookup"><span data-stu-id="b6241-183"><a name="SyntaxColorization">Syntax colorization</a></span></span>

<span data-ttu-id="b6241-184">Attualmente, vengono utilizzati differenti colori per evidenziare le seguenti parti di espressioni:</span><span class="sxs-lookup"><span data-stu-id="b6241-184">Currently, different colors are used to highlight the following parts of expressions:</span></span>

- <span data-ttu-id="b6241-185">Il testo tra parentesi quadre doppie che può rappresentare un ID etichetta di una costante di testo.</span><span class="sxs-lookup"><span data-stu-id="b6241-185">The text in double brackets that can represent a label ID of a text constant.</span></span>

<span data-ttu-id="b6241-186">[![Editor di formule ER](./media/ER-AdvEditor-SyntaxColorization.png)](./media/ER-AdvEditor-SyntaxColorization.png)</span><span class="sxs-lookup"><span data-stu-id="b6241-186">[![ER formula editor](./media/ER-AdvEditor-SyntaxColorization.png)](./media/ER-AdvEditor-SyntaxColorization.png)</span></span>

## <a name="limitations"></a><span data-ttu-id="b6241-187">Limiti</span><span class="sxs-lookup"><span data-stu-id="b6241-187">Limitations</span></span>

<span data-ttu-id="b6241-188">L'editor è attualmente supportato nei seguenti browser Web:</span><span class="sxs-lookup"><span data-stu-id="b6241-188">The editor is currently supported in the following web browsers:</span></span>

- <span data-ttu-id="b6241-189">Chrome</span><span class="sxs-lookup"><span data-stu-id="b6241-189">Chrome</span></span>
- <span data-ttu-id="b6241-190">Bordo</span><span class="sxs-lookup"><span data-stu-id="b6241-190">Edge</span></span>
- <span data-ttu-id="b6241-191">Firefox</span><span class="sxs-lookup"><span data-stu-id="b6241-191">Firefox</span></span>
- <span data-ttu-id="b6241-192">Opera</span><span class="sxs-lookup"><span data-stu-id="b6241-192">Opera</span></span>
- <span data-ttu-id="b6241-193">Safari</span><span class="sxs-lookup"><span data-stu-id="b6241-193">Safari</span></span>

## <a name="additional-resources"></a><span data-ttu-id="b6241-194">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="b6241-194">Additional resources</span></span>

- [<span data-ttu-id="b6241-195">Panoramica dei report elettronici</span><span class="sxs-lookup"><span data-stu-id="b6241-195">Electronic reporting (ER) overview</span></span>](general-electronic-reporting.md)
- [<span data-ttu-id="b6241-196">Designer formula nella creazione di report elettronici</span><span class="sxs-lookup"><span data-stu-id="b6241-196">Formula designer in Electronic reporting</span></span>](general-electronic-reporting-formula-designer.md)
- [<span data-ttu-id="b6241-197">Editor Monaco</span><span class="sxs-lookup"><span data-stu-id="b6241-197">Monaco editor</span></span>](https://microsoft.github.io/monaco-editor)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]