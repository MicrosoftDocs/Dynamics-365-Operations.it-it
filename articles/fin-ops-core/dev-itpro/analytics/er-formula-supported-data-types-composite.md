---
title: Tipi di dati compositi supportati per le formule di creazione di report elettronici
description: Questo articolo fornisce informazioni sui tipi di dati compositi supportati nelle formule di creazione di report elettronici (ER).
author: kfend
ms.date: 06/02/2021
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
ms.openlocfilehash: ea6f8ab1f0cd26fd2414a17be559aa60fc52e7d3
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9272714"
---
# <a name="supported-composite-data-types-for-electronic-reporting-formulas"></a>Tipi di dati compositi supportati per le formule di creazione di report elettronici

[!include [banner](../includes/banner.md)]

Questo articolo fornisce informazioni sui tipi di dati compositi supportati nelle espressioni di [generazione di report elettronici (ER)](general-electronic-reporting.md). I tipi di dati compositi sono [classe](#class), [contenitore](#container), [record](#record), [elenco di record](#record-list) e [oggetto](#object).

## <a name="class"></a><a name="class"></a>Classe

Il tipo di dati *classe* fa riferimento a una classe di applicazioni pubbliche. In ER, è rappresentato come un [*record*](#record) che contiene un campo separato per ogni metodo pubblico della classe di riferimento. Quando la chiamata del metodo è parametrizzata, è necessario specificare anche gli argomenti obbligatori dei tipi appropriati in un'espressione ER configurata per chiamare il metodo.

Nei componenti di mapping e formattazione di ER, è possibile aggiungere l'origine dati **Classe** presentata come origine dati e che restituisce un valore di tipo *classe*. Questa origine dati espone i metodi pubblici della classe che possono essere chiamati in runtime.

> [!NOTE]
> Solo i metodi che restituiscono un valore possono essere chiamati dalle espressioni ER.
>
> Solo i metodi che hanno un intervallo da zero a otto argomenti possono essere chiamati dalle espressioni ER.

Il valore predefinito di una *classe* è **null**.

L'immagine seguente mostra come l'origine dati **System information(xInfo)** del tipo **Classe** viene aggiunto all'istanza della classe dell'applicazione **xInfo** e chiama il relativo metodo **productName()** per ricevere il nome dell'applicazione corrente. Il nome dell'applicazione corrente viene recuperato in runtime mediante l'esecuzione del binding `xInfo.productName` configurato per il campo **Nome del software(SoftwareName)** del modello dati ER. Questo binding chiama il metodo `productName()` della classe dell'applicazione **xInfo** rappresentata nel mapping del modello corrente come origine dati **Informazioni di sistema(xInfo)**.

[![Configurazione di un'origine dati Classe nella finestra di progettazione mapping modello ER.](./media/er-formula-supported-data-types-composite-class1.gif)](./media/er-formula-supported-data-types-composite-class1.gif)

L'illustrazione seguente mostra come il formato ER sia configurato per inserire il nome dell'applicazione specificato nei documenti generati. Il campo **Nome software(SoftwareName)** del modello dati usato è stato associato al componente **Stringa** nidificato nell'elemento XML **softwareUsed** del formato ER. Quindi, il nome dell'applicazione corrente viene inserito in runtime nell'elemento XML **softwareUsed** di un documento generato in formato XML.

[![Configurazione della struttura di un documento elettronico in uscita nella finestra di progettazione formato ER.](./media/er-formula-supported-data-types-composite-class2.png)](./media/er-formula-supported-data-types-composite-class2.png)

## <a name="container"></a><a name="container"></a>Contenitore

Il tipo di dati *contenitore* include contenuto binario. Un valore *contenitore* può essere utilizzato per passare informazioni specifiche dall'archiviazione a un documento generato. Nel framework ER, questo tipo di dati viene spesso utilizzato per inserire contenuti multimediali quali il logo di un'azienda nei documenti generati.

> [!NOTE]
> Sebbene ogni elemento multimediale possa essere rappresentato come valore *contenitore*, non tutti i valori *contenitore* rappresentano un elemento multimediale. Pertanto, se si configura un formato ER in modo che utilizzi un *contenitore* per inserire un'immagine nei documenti generati, ma il *contenitore* di riferimento non restituisce il contenuto multimediale, potrebbe essere generata un'eccezione simile all'esempio seguente: "Errore durante l'esecuzione del codice: binario (oggetto), metodo constructFromContainer chiamato con parametri non validi".

Il valore predefinito di un *contenitore* è **null**.

L'illustrazione seguente mostra come il campo **Bitmap(Image)** del tipo *Contenitore* sia associato al campo **Logo** del modello dati del tipo **Contenitore** nel mapping del modello **Sales invoice**. Il binding rende disponibile il logo aziendale in qualsiasi formato ER progettato per la definizione radice **SalesInvoice** e che usa questo mapping di modello in runtime.

[![Binding di un campo di tipo Contenitore nella soluzione di progettazione del mapping del modello ER.](./media/er-formula-supported-data-types-composite-container.png)](./media/er-formula-supported-data-types-composite-container.png)

## <a name="record"></a><a name="record"></a>Registra

Un *record* è una raccolta di campi denominati, ognuno dei quali è associato a un valore di un tipo di dati [primitivo](er-formula-supported-data-types-primitive.md) o composito. In genere, un *record* viene utilizzato per rappresentare un singolo record di un elenco di record. In questo caso, ogni elemento rappresenta singoli campi, metodi e relazioni.

Il valore predefinito di un *record* è **vuoto**.

> [!NOTE]
> Quando ottieni il valore di un campo di un *record* vuoto, viene restituito il valore predefinito del tipo di dati appropriato.

Un *record* può essere ottenuto utilizzando le seguenti funzioni:

- [FIRST](er-functions-list-first.md)
- [FIRSTORNULL](er-functions-list-firstornull.md)
- [EMPTYRECORD](er-functions-record-emptyrecord.md)
- [NULLCONTAINER](er-functions-record-nullcontainer.md)

Per maggiori informazioni sulla trasformazione dei valori dei *record*, vedere [Elenco delle funzioni ER nella categoria dell'elenco](er-functions-category-list.md).

## <a name="record-list"></a><a name="record-list"></a>Elenco di record

Un *elenco di record* è un elenco di elementi di tipo *record*. In genere, un *elenco di record* viene utilizzato per rappresentare l'elenco dei record recuperato da una tabella di database.

Per impostazione predefinita, l'accesso ai record di un *elenco di record* avviene in modo sequenziale. Per accedere a un record specifico, è possibile utilizzare la funzione [INDEX](er-functions-list-index.md) e specificare l'indice sotto forma di *numero intero*.

Il valore predefinito di un *elenco di record* è **vuoto**. È possibile usare la funzione [ISEMPTY](er-functions-list-isempty.md) per valutare se un *elenco di record* è vuoto.

> [!NOTE]
> Se un *elenco di record* è vuoto, qualsiasi tentativo di ottenere un valore di campo per un *record* all'interno dello stesso determina la generazione di un'eccezione in runtime. Per sapere come prevenire eccezioni di runtime di questo tipo, vedere [Considerazione dei casi di elenco vuoto](er-components-inspections.md#i9).

Un *elenco di record* può essere inizializzato utilizzando le seguenti funzioni:

- [ALLITEMS](er-functions-list-allitems.md)
- [ALLITEMSQUERY](er-functions-list-allitemsquery.md)
- [EMPTYLIST](er-functions-list-emptylist.md)
- [LIST](er-functions-list-list.md)
- [LISTDISTINCT](er-functions-list-listdistinct.md)

Per maggiori informazioni sulla trasformazione dei valori dei *record*, vedere [Elenco delle funzioni ER nella categoria dell'elenco](er-functions-category-list.md). Per sapere come inserire degli elementi in un *elenco di record*, compilarli con i dati dell'applicazione e quindi utilizzare i dati per generare documenti aziendali, vedere [Progettare una nuova soluzione ER per stampare un report personalizzato](er-quick-start1-new-solution.md).

## <a name="object"></a><a name="object"></a>Oggetto

Un *oggetto* fa riferimento a un'istanza stateful di una *classe*. Di solito, un *oggetto* viene inizializzato nel codice sorgente. Viene quindi passato a un mapping del modello ER e fornisce i dettagli del contesto di esecuzione.

Il valore predefinito di un *oggetto* è **null**.

La seguente illustrazione mostra come è stata aggiunta l'origine dati **ReportDataContract** del tipo *Oggetto* per passare le informazioni su una fattura generata dal codice sorgente al mapping del modello **Fattura del progetto**. Ad esempio, il testo dell'istanza della fattura viene passato come parte del contesto di esecuzione. Questo testo viene acquisito dal codice sorgente in runtime mediante l'esecuzione del binding `ReportDataContract.parmInvoiceInstanceText` configurato per il campo **Nota** del modello dati ER. Questo binding chiama il metodo `parmInvoiceInstanceText()` della classe dell'applicazione **PSAProjInvoiceContract** rappresentata nel mapping del modello corrente come origine dati **ReportDataContract**.

[![Configurazione di un'origine dati Oggetto nella finestra di progettazione mapping modello ER.](./media/er-formula-supported-data-types-composite-object.gif)](./media/er-formula-supported-data-types-composite-object.gif)

Per sapere come passare i dettagli del contesto di esecuzione dal codice sorgente alla soluzione ER in esecuzione, vedere [Sviluppare artefatti di applicazioni per chiamare il report progettato](er-quick-start1-new-solution.md#DevelopCustomCode).

## <a name="additional-resources"></a>Risorse aggiuntive

- [Panoramica sui report elettronici](general-electronic-reporting.md)
- [Linguaggio della formula nella creazione di report elettronici](er-formula-language.md)
- [Tipi di dati primitivi supportati](er-formula-supported-data-types-primitive.md)
