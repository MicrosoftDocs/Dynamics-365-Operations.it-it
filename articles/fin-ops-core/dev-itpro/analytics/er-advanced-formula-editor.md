---
title: Editor di formule avanzato per report elettronici
description: In questo argomento viene descritto come utilizzare l'editor di formule avanzato per configurare espressioni nei componenti di formato e nel mapping di modelli per report elettronici (ER).
author: NickSelin
manager: AnnBe
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
ms.openlocfilehash: 8746340eb886ec797afdd58797a4c5e41f93022f
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2021
ms.locfileid: "5560143"
---
# <a name="electronic-reporting-advanced-formula-editor"></a>Editor di formule avanzato per report elettronici

[!include [banner](../includes/banner.md)]

Oltre all'[editor di formule](general-electronic-reporting-formula-designer.md) per [report elettronici](general-electronic-reporting.md) è possibile utilizzare l'editor di formule per report elettronici avanzato per migliorare l'esperienza di configurazione delle espressioni ER. L'editor avanzato è basato su browser e utilizza l'[editor Monaco](https://microsoft.github.io/monaco-editor). Le funzionalità dell'editor avanzato più comunemente utilizzate sono descritte in questo argomento:

- [Formattazione automatica del codice](#Autoformatting)
- [IntelliSense](#IntelliSense)
- [Completamento del codice](#CodeCompletion)
- [Navigazione nel codice](#CodeNavigation)
- [Strutturazione del codice](#CodeStructuring)
- [Trova e sostituisci](#FindAndReplace)
- [Incollare dati](#DataPasting)
- [Colorazione della sintassi](#SyntaxColorization)

## <a name=""></a><a name="ActivateAdvEditor">Attivare l'editor di formule avanzato</a>

Completare i seguenti passaggi per iniziare a utilizzare l'editor di formule avanzato nell'istanza di Microsoft Dynamics 365 Finance.

1.  Andare a **Amministrazione organizzazione** \> **Creazione di report elettronici** \> **Configurazioni**.
2.  Nella pagina **Configurazioni**, nel Riquadro azioni, nella scheda **Configurazioni**, nel gruppo **Impostazioni avanzate**, selezionare **Parametri utente**.
3.  Nella finestra di dialogo **Parametri utente**, nella sezione **Traccia esecuzione**, impostare il parametro **Abilita editor di formule avanzato** su **Sì**.

[![Pagina delle configurazioni ER](./media/ER-AdvEditor-Activate.png)](./media/ER-AdvEditor-Activate.png)

> [!NOTE]
> Tenere presente che questo parametro è specifico dell'utente e dell'azienda.

## <a name=""></a><a name="Autoformatting">Formattazione automatica del codice</a>

Quando si scrive un'espressione complessa composta da più righe di codice, il rientro di una nuova riga immessa sarà automatico in base al rientro della riga precedente. È possibile selezionare le righe e modificarne il rientro digitando **TAB** o **MAIUSC + TAB**.

[![Editor di formule ER](./media/ER-AdvEditor-Indentation.gif)](./media/ER-AdvEditor-Indentation.gif)

La formattazione automatica consente di mantenere l'intera espressione ben formattata per facilitare ulteriormente la manutenzione e semplificare la comprensione della logica configurata.

## <a name=""></a><a name="IntelliSense">IntelliSense</a>

L'editor fornisce il completamento delle parole per consentire una scrittura più veloce delle espressioni ed evitare errori di battitura. Quando si comincia a aggiungere testo, l'editor offre automaticamente un elenco di funzioni supportate nelle funzioni ER che contengono i caratteri immessi. È inoltre possibile attivare IntelliSense ovunque in un'espressione configurata digitando **CTRL + BARRA SPAZIATRICE**.

[![Editor di formule ER](./media/ER-AdvEditor-Intelisense.gif)](./media/ER-AdvEditor-Intelisense.gif)

## <a name=""></a><a name="CodeCompletion">Completamento del codice</a>

L'editor fornisce automaticamente il completamento del codice tramite:

- Inserimento di una parentesi quadra chiusa quando si inserisce una parentesi quadra aperta, mantenendo il cursore all'interno delle parentesi quadre.
- Inserimento della seconda virgoletta quando viene inserita la prima, mantenendo il cursore all'interno delle virgolette.
- Inserimento delle seconde virgolette doppie quando vengono inserite le prime, mantenendo il cursore all'interno delle virgolette.

[![Editor di formule ER](./media/ER-AdvEditor-CodeCompletion.gif)](./media/ER-AdvEditor-CodeCompletion.gif)

Quando si punta alla parentesi tipizzata, la seconda parentesi di questa coppia viene automaticamente evidenziata per mostrare il costrutto che supportano.

## <a name=""></a><a name="CodeNavigation">Navigazione nel codice</a>

È possibile individuare i simboli o le righe richiesti nell'espressione digitando il comando **Vai a** utilizzando il riquadro comandi o il menu di scelta rapida.

Ad esempio, per passare alla riga **8** procedere come segue:

- Premere **CTRL + G**, immettere il valore **8**, quindi premere **INVIO**.

  oppure

- Premere **F1**, digitare **G**, selezionare **Vai a riga**, immettere il valore **8** e premere **INVIO**.

[![Editor di formule ER](./media/ER-AdvEditor-Goto.gif)](./media/ER-AdvEditor-Goto.gif)

## <a name=""></a><a name="CodeStructuring">Strutturazione del codice</a>

Il codice per alcune funzioni, come ad esempio [IF](er-functions-logical-if.md)o [CASE](er-functions-logical-case.md), viene automaticamente strutturato. È possibile espandere e comprimere una o tutte le aree di riduzione di questo codice per ridurre la parte modificabile di un'espressione al fine di concentrarsi solo sulla parte di codice che richiede attenzione. I comandi di attivazione/disattivazione Riduci/Espandi possono essere usati a questo scopo.

Ad esempio, per ridurre tutte le aree, procedere come segue:

- Premere **CTRL + K**

  oppure

- Premere **F1** e quindi **FO**, selezionare **Riduci tutto**, quindi premere **INVIO**

Per espandere tutte le aree, procedere come segue:

- Premere **CTRL + J**

  oppure
  
- Premere **F1** digitare **UN**, selezionare **Espandi tutto**, quindi premere **INVIO**

[![Editor di formule ER](./media/ER-AdvEditor-ToggleFold.gif)](./media/ER-AdvEditor-ToggleFold.gif)

## <a name=""></a><a name="FindAndReplace">Trova e sostituisci</a>

Per trovare occorrenze di un determinato testo, selezionare il testo nell'espressione ed eseguire le seguenti operazioni:

- Premere **CTRL + F** e quindi premere **F3** per trovare la ricorrenza successiva del testo selezionato oppure premere **MAIUSC + F3** per trovare l'occorrenza precedente.

  oppure
  
- Premere **F1**, digitare **F**, quindi selezionare l'opzione necessaria per trovare il testo selezionato.

Per sostituire occorrenze di un determinato testo, selezionare il testo nell'espressione ed eseguire le seguenti operazioni:

- Premere **CTRL + H**. Immettere il testo alternativo e selezionare l'opzione di sostituzione per sostituire il testo selezionato o tutte le occorrenze di tale testo nell'espressione corrente.

  oppure
  
- Premere **F1**, digitare **R**, quindi selezionare l'opzione necessaria per sostituire il testo selezionato. Immettere il testo alternativo e selezionare l'opzione di sostituzione per sostituire il testo selezionato o tutte le occorrenze di tale testo nell'espressione corrente.

Per cambiare tutte occorrenze di un determinato testo, selezionare il testo nell'espressione ed eseguire le seguenti operazioni:

- Premere **CTRL + F2** e quindi inserire il testo alternativo.

  oppure
  
- Premere **F1**, digitare **C**, quindi selezionare l'opzione necessaria per cambiare il testo selezionato. Immettere il testo alternativo.

[![Editor di formule ER](./media/ER-AdvEditor-Find.gif)](./media/ER-AdvEditor-Find.gif)

## <a name=""></a><a name="DataPasting">Incollare origini dati e funzioni</a>

È possibile selezionare **Aggiungi origine dati**, che consente di incollare nell'espressione corrente un'origine dati correntemente selezionata nel riquadro sinistro **Origine dati**. Analogamente, è possibile selezionare **Aggiungi funzione**, che consente di incollare nell'espressione corrente la funzione correntemente selezionata nel riquadro destro **Funzioni**. Se si utilizza l'editor di formule ER, una funzione o un'origine dati selezionata verrà sempre incollata alla fine dell'espressione configurata. Quando si utilizza l'editor di formule ER avanzato, una funzione o un'origine dati selezionata può essere incollata ovunque nell'espressione configurata. Sarà necessario utilizzare il cursore per specificare dove si desidera incollare i dati.

[![Editor di formule ER](./media/ER-AdvEditor-PasteValue.gif)](./media/ER-AdvEditor-PasteValue.gif)

## <a name=""></a><a name="SyntaxColorization">Colorazione della sintassi</a>

Attualmente, vengono utilizzati differenti colori per evidenziare le seguenti parti di espressioni:

- Il testo tra parentesi quadre doppie che può rappresentare un ID etichetta di una costante di testo.

[![Editor di formule ER](./media/ER-AdvEditor-SyntaxColorization.png)](./media/ER-AdvEditor-SyntaxColorization.png)

## <a name="limitations"></a>Limiti

L'editor è attualmente supportato nei seguenti browser Web:

- Chrome
- Bordo
- Firefox
- Opera
- Safari

## <a name="additional-resources"></a>Risorse aggiuntive

- [Panoramica dei report elettronici](general-electronic-reporting.md)
- [Designer formula nella creazione di report elettronici](general-electronic-reporting-formula-designer.md)
- [Editor Monaco](https://microsoft.github.io/monaco-editor)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]