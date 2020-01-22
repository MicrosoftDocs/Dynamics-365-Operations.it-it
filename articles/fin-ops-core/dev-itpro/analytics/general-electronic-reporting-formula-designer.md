---
title: Designer formula nella creazione di report elettronici (ER)
description: In questo argomento sono riportate le informazioni sull'utilizzo di designer formula nella creazione di report elettronici (ER).
author: NickSelin
manager: kfend
ms.date: 12/05/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0028d1f64aced1bbff91b18456c81adbb95bce30
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/20/2019
ms.locfileid: "2914820"
---
# <a name="formula-designer-in-electronic-reporting-er"></a>Designer formula nella creazione di report elettronici (ER)

[!include [banner](../includes/banner.md)]

In questo argomento viene illustrato come utilizzare designer formula nei report elettronici (ER). Quando si progetta un formato di un documento elettronico specifico in ER, è possibile utilizzare le formule per la trasformazione dei dati in modo da soddisfare i requisiti per la compilazione e la formattazione del documento. Le formule somigliano alle formule in Microsoft Excel. Nelle formule sono supportate funzioni di diverso tipo: funzioni di testo, data e ora, logica matematica, informazioni e conversione del tipo di dati, oltre ad altre funzioni specifiche del dominio aziendale.

## <a name="formula-designer-overview"></a>Panoramica su Designer formula

ER supporta il Designer formula. Di conseguenza, in fase di progettazione, è possibile configurare le espressioni che possono essere utilizzate per le seguenti attività in fase di esecuzione:

- Trasformazione dei dati ricevuti da un database dell'applicazione e che devono essere inseriti in un modello dati ER progettato per fungere da origine dati per i formati ER. Se ad esempio, le trasformazioni possono includere il filtro, raggruppamento e conversione del tipo di dati.
- Formattare i dati che devono essere inviati a un documento elettronico di generazione in conformità al layout e agli stati di un formato specifico di ER. Se ad esempio, la formattazione deve essere eseguita in conformità alla lingua o cultura richiesta o alla codifica.
- Controllare il processo di creazione di documenti elettronici. Se ad esempio, le eventuali espressioni possono abilitare o disabilitare l'output di elementi specifici del formato, in base all'elaborazione dei dati. Possono inoltre interrompere il processo di creazione del documento o inviare messaggi agli utenti.

La pagina **Designer formula** può essere aperta quando si esegue una delle seguenti azioni:

- Associazione di articoli di origini dati a componenti del modello dati.
- Associazione di articoli di origini dati a componenti del formato.
- Gestione completa dei campi calcolati che sono parte delle origini dati.
- Definizione delle condizioni di visibilità per i parametri di input utente.
- Progettazione delle trasformazioni di un formato.
- Definizione delle condizioni di abilitazione per i componenti del formato.
- Definizione dei nomi di file per i componenti FILE del formato.
- Definizione delle condizioni per le convalide di controllo dei processi.
- Definizione del testo del messaggio per le convalide di controllo dei processi.

## <a name="Binding">Associazione dati</a>

Il Designer formula ER può essere utilizzato per definire un'espressione che trasforma i dati ricevuti da origini dati, in modo che i dati possono essere inseriti nel consumer di dati nei seguenti modi in fase di runtime:

- Da origini dati dell'applicazione e dai parametri di runtime a un modello dati ER
- Da un modello dati ER a un formato ER
- Da origini dati dell'applicazione e dai parametri di runtime a un formato ER

La figura seguente mostra la progettazione di un'espressione di questo tipo. In questo esempio, l'espressione arrotonda a due posizioni decimali il valore del campo **Intrastat.AmountMST** nella tabella Intrastat e quindi restituisce il valore arrotondato.

[![Espressione di associazione dati](./media/picture-expression-binding.jpg)](./media/picture-expression-binding.jpg)

La figura seguente mostra come è possibile utilizzare un'espressione di questo tipo. In questo esempio, il risultato dell'espressione pianificata è immesso nel componente **Transaction.InvoicedAmount** del modello dati **Modello di dichiarazione imposte**.

[![Espressione di associazione dati utilizzata](./media/picture-expression-binding2.jpg)](./media/picture-expression-binding2.jpg)

In fase di esecuzione, la formula progettata, `ROUND (Intrastat.AmountMST, 2)`, arrotonda a due posizioni decimali il valore del campo **AmountMST** per ogni record della tabella Intrastat. Quindi immette il valore arrotondato nel componente **Transaction.InvoicedAmount** del modello dati **Dichiarazione imposte**.

## <a name="Transformation">Formattazione di dati</a>

Il Designer formula ER può essere utilizzato per definire un'espressione che formatta i dati ricevuti da origini dati, in modo che i dati possono essere inviati come parte del documento elettronico generato. Potrebbe essere presente una formattazione che deve essere applicata come regola standard da riutilizzare per un formato. In questo caso, è possibile introdurla una volta nella configurazione del formato come trasformazione denominata con espressione di formattazione. Successivamente questa trasformazione denominata può essere collegata a molti componenti di formato in cui l'output deve essere formattato in base all'espressione di formattazione creata.

La figura seguente mostra la progettazione di una trasformazione di questo tipo. In questo esempio, la trasformazione **TrimmedString** tronca i dati in ingresso del tipo di dati *String* rimuovendo spazi iniziali e finali. Restituisce quindi il valore stringa troncato.

[![Trasformazione](./media/picture-transformation-design.jpg)](./media/picture-transformation-design.jpg)

La figura seguente mostra come è possibile utilizzare una trasformazione di questo tipo. In questo esempio, più componenti di formato inviano testo come output per la generazione del documento elettronico in fase di runtime. Tutti questi componenti del formato fanno riferimento alla trasformazione **TrimmedString** per nome.

[![Trasformazione utilizzata](./media/picture-transformation-usage.jpg)](./media/picture-transformation-usage.jpg)

Quando i componenti del formato fanno riferimento alla trasformazione **TrimmedString** (ad esempio, il componente **partyName** della precedente figura), la trasformazione invia il testo come output alla generazione del documento elettronico. Questo testo non include gli spazi iniziali e finali.

Se una formattazione deve essere applicata singolarmente, può essere introdotta come singola espressione di associazione di un determinato componente di formato. La figura seguente mostra un'espressione di questo tipo. In questo esempio, il componente di formato **partyType** è associato all'origine dati mediante un'espressione che converte i dati in ingresso dal campo **Model.Company.RegistrationType** nell'origine dati in testo maiuscolo. L'espressione invia quindi il testo come output al documento elettronico.

[![Applicazione della formattazione a un singolo componente](./media/picture-binding-with-formula.jpg)](./media/picture-binding-with-formula.jpg)

## <a name="Validation">Controllo del flusso del processo</a>

Designer formula ER può essere utilizzato per definire le espressioni che controllano il flusso del processo di generazione dei documenti elettronici. È possibile effettuare le attività seguenti:

- Definire le condizioni che determinano quando il processo di creazione di un documento deve essere arrestato.
- Specificare le espressioni che creano messaggi per l'utente sui processi arrestati o che generano i messaggi del registro di esecuzione sul proseguimento del processo di creazione del report.
- Specificare i nomi file dei documenti elettronici generati e controllare le condizioni della relativa creazione.

Ogni regola del controllo del flusso del processo è progettata come singola convalida. La figura seguente mostra una convalida di questo tipo. Ecco una spiegazione della configurazione in questo esempio:

- La convalida viene valutata quando il nodo **INSTAT** viene creato durante la generazione del file XML.
- Se l'elenco delle transazioni è vuoto, la convalida interrompe il processo di esecuzione restituisce **FALSE**.
- La convalida restituisce un messaggio di errore che include il testo dell'etichetta SYS70894 nella lingua preferita dell'utente.

[![Convalida](./media/picture-validation.jpg)](./media/picture-validation.jpg)

Designer formula ER può essere utilizzato anche per generare un nome file per la generazione di un documento elettronico e per controllare il processo di creazione del file. La figura seguente mostra la progettazione di un controllo del flusso di processo di questo tipo. Ecco una spiegazione della configurazione in questo esempio:

- L'elenco dei record dell'origine dati **model.Intrastat** è suddiviso in batch. Ogni batch contiene un massimo di 1.000 record.
- L'output crea un file ZIP contenente un file in formato XML per ogni batch creato.
- Un'espressione restituisce un nome file per la generazione dei documenti elettronici concatenando il nome file e l'estensione del nome file. Per il secondo batch e tutti i batch successivi, il nome file contiene l'ID batch come suffisso.
- Un'espressione abilita (restituendo **TRUE**) il processo di creazione file solo per i batch che contengono almeno un record.

[![Controllo del flusso del processo](./media/picture-file-control.jpg)](./media/picture-file-control.jpg)

## <a name="Enabled">Controllo del contenuto dei documenti</a>

Il designer formula ER può essere utilizzato per configurare espressioni che determinano i dati che verranno inseriti nei documenti elettronici generati in fase di esecuzione. Le espressioni possono abilitare o disabilitare l'output di elementi specifici del formato, in base ai dati di elaborazione e alla logica configurata. Queste espressioni possono essere immesse per un singolo elemento di formato nel campo **Abilitato** della scheda **Mapping** della pagina **Designer operazioni**. È possibile inserire le espressioni come condizione logica che restituisce un valore *Booleano*:

- Se la condizione restituisce **True**, viene eseguito l'elemento di formato corrente.
- Se la condizione restituisce **False**, viene ignorato l'elemento di formato corrente.

La figura seguente mostra espressioni di questo tipo. (La versione 11.12.11 della configurazione formato **Bonifico ISO20022 (NO)** fornita da Microsoft è usata come esempio.) Il componente formato **XMLHeader** è configurato per descrivere la struttura del messaggio di bonifico, in base agli standard di messaggio XML ISO 20022. Il componente formato **XMLHeader/Document/CstmrCdtTrfInitn/PmtInf/CdtTrfTxInf/RmtInf/Ustrd** è configurato per aggiungere l'elemento XML **Ustrd** al messaggio generato e inserire le informazioni sulla rimessa in un formato non strutturato come testo dei seguenti elementi XML:

- Il componente **PaymentNotes** viene utilizzato per generare il testo delle note di pagamento.
- Il componente **DelimitedSequence** genera numeri di fattura separati con virgole utilizzati per liquidare il bonifico corrente.

[![Componenti PaymentNotes e DelimitedSequence](./media/GER-FormulaEditor-ControlContent-1.png)](./media/GER-FormulaEditor-ControlContent-1.png)

> [!NOTE]
> I componenti **DelimitedSequence** e **PaymentNotes** sono etichettati utilizzando un punto interrogativo. Un punto interrogativo indica che l'uso di un componente è condizionale. In questo caso, l'uso dei componenti si basa sui seguenti criteri:
>
> - L'espressione `@.PaymentsNotes <> ""` definita per il componente **PaymentNotes** consente (restituendo **TRUE**) che l'elemento XML **Ustrd** venga riempito con il testo delle note di pagamento, se questo testo per il bonifico corrente non è vuoto.
>
>    [![Espressione per il componente PaymentNotes](./media/GER-FormulaEditor-ControlContent-2.png)](./media/GER-FormulaEditor-ControlContent-2.png)
>
> - L'espressione `@.PaymentsNotes = ""` definita per il componente **DelimitedSequence** consente (restituendo **TRUE**) che l'elemento XML **Ustrd** venga riempito con un elenco separato con virgole dei numeri di fattura utilizzati per liquidare il bonifico corrente, se il testo delle note di pagamento per tale bonifico è vuoto.
>
>    [![Espressione per il componente DelimitedSequence](./media/GER-FormulaEditor-ControlContent-3.png)](./media/GER-FormulaEditor-ControlContent-3.png)
> 
> In base a questa impostazione, il messaggio che viene generato per ogni pagamento debitore, l'elemento XML **Ustrd**, conterrà il testo delle note di pagamento o, quando questo testo è vuoto, l'elenco separato con virgole dei numeri di fattura utilizzati per liquidare il pagamento.

## <a name="TestFormula">Convalida delle formule configurate</a>

Nella pagina **Designer formula**, selezionare **Test** per convalidare il funzionamento della formula configurata.

[![Selezione di Test per convalidare una formula](./media/ER-FormulaTest-Start.png)](./media/ER-FormulaTest-Start.png)

Quando sono richiesti i valori degli argomenti della formula, è possibile aprire la finestra di dialogo **Espressione test** dalla pagina **Designer formula**. Nella maggior parte dei casi, questi argomenti devono essere definiti manualmente poiché le associazioni configurate non vengono eseguite in fase di progettazione. La scheda **Risultato test** nella pagina **Designer formula** mostra il risultato dell'esecuzione della formula configurata.

L'esempio seguente mostra come testare la formula configurata per il dominio del commercio estero per assicurarsi che il codice voce doganale Intrastat contenga solo cifre.

Quando si testa questa formula, è possibile utilizzare la finestra di dialogo **Espressione test** per specificare il valore del codice voce doganale Intrastat per il test.

[![Specifica del codice voce doganale Intrastat per il test](./media/ER-FormulaTest-Start-EnterArguments.png)](./media/ER-FormulaTest-Start-EnterArguments.png)

Dopo aver specificato il codice voce doganale Intrastat e selezionato **OK**, la scheda **Risultato test** nella pagina **Designer formula** mostra il risultato dell'esecuzione della formula configurata. È quindi possibile valutare se il risultato è accettabile. Se il risultato non è accettabile, è possibile aggiornare la formula e testarla di nuovo.

[![Risultato test](./media/ER-FormulaTest-Result.png)](./media/ER-FormulaTest-Result.png)

Alcune formule non possono essere testate in fase di progettazione. Ad esempio, una formula potrebbe restituire un risultato di un tipo di dati che non può essere mostrato nella scheda **Risultato test**. In questo caso, viene visualizzato un messaggio di errore che indica che la formula non può essere testata.

[![Messaggio di errore](./media/ER-FormulaTest-Error.png)](./media/ER-FormulaTest-Error.png)

## <a name="additional-resources"></a>Risorse aggiuntive

- [Panoramica sui report elettronici](general-electronic-reporting.md)
- [Linguaggio della formula nella creazione di report elettronici](er-formula-language.md)
