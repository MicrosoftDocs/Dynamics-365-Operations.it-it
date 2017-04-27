---
title: Definizioni di riga in Progettazione report finanziari
description: "Una definizione di riga è un componente di report, o blocco predefinito, che specifica il contenuto di ciascuna riga in un report finanziario. Una definizione di riga può combinarsi con le definizioni di colonna, le definizioni di albero gerarchico e le definizioni di report per creare un gruppo di blocchi predefiniti che può essere utilizzato da più società."
author: RobinARH
manager: AnnBe
ms.date: 2016-03-18 15 - 42 - 39
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: RobinARH
ms.search.scope: Management Reporter, Core
ms.custom: 68873
ms.assetid: 2fd7b5da-700f-48cb-9003-90c0d82f818f
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 
ms.dyn365.ops.version: 
translationtype: Human Translation
ms.sourcegitcommit: 4d6cf88788dcc5e982e509137aa444a020137a5e
ms.openlocfilehash: a2f92effd1cfdc1d5da2c5ec895c0487a6fc82a4
ms.lasthandoff: 03/29/2017


---

# <a name="row-definitions-in-financial-report-designer"></a>Definizioni di riga in Progettazione report finanziari

Una definizione di riga è un componente di report, o blocco predefinito, che specifica il contenuto di ciascuna riga in un report finanziario. Una definizione di riga può combinarsi con le definizioni di colonna, le definizioni di albero gerarchico e le definizioni di report per creare un gruppo di blocchi predefiniti che può essere utilizzato da più società.

<a name="create-a-row-definition"></a>Creazione di una definizione di riga
-----------------------

1.  In Progettazione report, nel pannello di navigazione, fare clic su **Definizioni di riga**.
2.  Scegliere **Nuovo**, quindi **Definizione riga** dal menu **File**. Per ulteriori informazioni sul contenuto di ogni cella, vedere [Modificare le celle di definizione di riga](modify-row-definition-cells-financial-reporting.md).

## <a name="open-a-row-definition"></a>Aprire una definizione di riga
1.  In Progettazione report, nel pannello di navigazione, fare clic su **Definizioni di riga**.
2.  Fare doppio clic sul nome della definizione di riga da aprire.
3.  Per visualizzare tutti i blocchi predefiniti associati alla definizione di riga, fare clic con il pulsante destro del mouse sulla definizione di riga e selezionare **Associazioni**.

## <a name="contents-of-a-row-definition"></a> Contenuto di una definizione di riga
Una definizione di riga può contenere fino a 20.000 righe di dimensione finanziaria e includere le seguenti informazioni:

-   Testo descrittivo che aggiunge significato al report creando intestazioni di sezione, righe e spazi, ad esempio **Contante** o **Totale ricavi**.
-   Collegamenti ai dati finanziari, che possono includere valori di dimensione in Microsoft Dynamics 365 for Operations **Nota:** È possibile impostare una definizione di riga per il pull dei dati dal sistema di dimensioni finanziarie ogni volta che viene generato il report.
-   Totali e formule di riga basati sui dati finanziari collegati

In genere, ogni riga in una definizione contiene uno dei seguenti tipi di informazioni:

-   Riferimenti al sistema di dimensioni finanziarie
-   Totali o calcoli basati sui dati
-   Formattazione

Esistono due metodi per l'immissione dei dati in una definizione di riga:

-   Immettere le informazioni sulla riga manualmente in una nuova definizione di riga. Per ulteriori informazioni, vedere [Modificare le celle di definizione di riga](modify-row-definition-cells-financial-reporting.md).
-   Utilizzare Progettazione report per estrarre informazioni di riga direttamente dalle dimensioni finanziarie. Per ulteriori informazioni, vedere la sezione "Unità/righe/formule correlate" in [Modificare le celle di definizione riga](modify-row-definition-cells-financial-reporting.md).

## <a name="add-dimensions-in-a-row-definition"></a> Aggiungere dimensioni in una definizione di riga
Una dimensione è un'intersezione di dati e valori. È possibile raggruppare dati e valori in Progettazione report. È quindi possibile classificare e analizzare le transazioni in modo più dettagliato. È possibile utilizzare la finestra di dialogo **Inserire le righe delle dimensioni** per aggiungere contemporaneamente più righe in una definizione di riga. La finestra di dialogo visualizza una colonna per ogni dimensione. Nella seguente tabella vengono descritte le informazioni che è possibile specificare per ogni dimensione.

| Opzione                | Descrizione                                                                                                                                                                                                                                                                      |
|-----------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Dimensione             | Il modello che identifica la dimensione da aggiungere alla definizione di riga. Questo modello contiene una e commerciale (&) o un cancelletto  (\#) per ogni posizione nelle dimensioni. In genere, utilizzare la e commerciale per la dimensione del conto principale e il cancelletto per le altre dimensioni. |
| Inizio intervallo dimensioni | Il primo valore della dimensione da aggiungere alla definizione di riga.                                                                                                                                                                                                                 |
| Fine intervallo dimensioni   | L'ultimo valore della dimensione da aggiungere alla definizione di riga.                                                                                                                                                                                                                  |

Per aggiungere le dimensioni a una definizione di riga, effettuare i passaggi seguenti.

1.  In Progettazione report, fare clic su **Definizioni di riga** quindi aprire la definizione di riga da modificare.
2.  Nel menu **Modifica** fare clic su **Inserire le righe delle dimensioni**.
3.  Nella finestra di dialogo **Inserisci righe da dimensioni **, nella riga **Dimensioni**, selezionare la cella per la dimensione da trasferire alla definizione di riga e fare clic su **Tutti &&&**.
4.  Per limitare la definizione di riga a un intervallo specifico di valori di dimensione, immettere il valore di dimensione iniziale nella cella **Inizio intervallo dimensioni** e specificare il valore finale della dimensione nella cella **Fine intervallo dimensioni**. Per includere tutti i valori della dimensione selezionata, lasciare vuote le celle. **Nota**: i caratteri jolly s (\* or ?) negli intervalli di dimensione possono non restituire tutti risultati desiderati, a seconda della modalità di raccolta dei dati del database ERP.
5.  Nel campo **Codice di riga iniziale** specificare il codice della riga per il primo valore di dimensione da aggiungere alla definizione di riga.
6.  Nel campo **Incremento per ogni riga di** specificare la distanza tra codici di riga consecutivi. Ad esempio, se il primo codice di riga è 100 e il valore di incremento è 30, le prime nuove righe hanno i codici 100, 130, 160, 190 e 220. Utilizzare un valore di incremento che offra lo spazio sufficiente per inserire nuove righe di formula e di formato.
7.  Scegliere **OK**. Per ogni valore di dimensione selezionato viene aggiunta una riga alla definizione di riga.

## <a name="adjust-rounding-in-a-row-definition"></a> Regolare l'arrotondamento in una definizione riga
In uno stato patrimoniale in cui gli importi sono arrotondati, è possibile che i totali siano sbilanciati. Questo problema può verificarsi se, ad esempio, si utilizza l'opzione di arrotondamento in un report dello stato patrimoniale e anche la definizione di report specifica l'arrotondamento. È possibile utilizzare l'opzione **Rettifica arrotondamento** nella definizione di riga per bilanciare gli importi nei conti patrimoniali. È possibile disattivare o modificare l'arrotondamento nella scheda **Impostazioni** della definizione di report. Nella tabella che segue è illustrato il modo in cui vengono arrotondati gli importi. Nella tabella, i totali delle righe 100 e 200 sono diversi quando l'arrotondamento è abilitato.

| Codice di riga | Importi senza arrotondamento | Importo con arrotondamento in migliaia |
|----------|--------------------------|-----------------------------------------|
| 100      | 3,600                    | 4                                       |
| 200      | 3,700                    | 4                                       |
| Totale    | 7,300                    | 8                                       |

Per rettificare l'arrotondamento nello stato patrimoniale, completare i passaggi seguenti.

1.  In Progettazione report, fare clic su **Definizioni di riga** quindi aprire la definizione di riga da modificare.
2.  Nel menu **Modifica** fare clic su **Rettifica arrotondamento**.
3.  Nella finestra di dialogo **Rettifiche arrotondamento**, immettere i valori seguenti:
    -   **Riga rettifica arrotondamento**: il codice della riga che deve essere rettificata per bilanciare lo stato patrimoniale.
    -   **Riga totale cespiti**: il codice della riga nello stato patrimoniale contenente i cespiti totali.
    -   **Riga totale passività e capitale netto**: il codice della riga nello stato patrimoniale contenente le passività e il capitale netto totali.
    -   **Limiti importo di rettifica**: il limite, espresso come numero intero positivo, per le rettifiche automatiche. Questo importo viene confrontato con il valore assoluto della differenza di arrotondamento effettiva.

    **Nota: **questi codici di riga devono essere collegati ai dati finanziari. In altre parole, la riga deve avere un valore di dimensione nella cella **Collegamento a dimensioni finanziarie**. **Non** fare riferimento a una riga di descrizione (**DESC**), calcolata (**CALC**) e totalizzata (**TOT**).

Gli importi nello stato patrimoniale vengono ora bilanciati uniformemente quando l'arrotondamento è abilitato. **Nota: **il limite di rettifica si applica in base all'opzione **Precisione di arrotondamento** specificata per la definizione di report. Ad esempio, se si seleziona di arrotondare il report alle migliaia e si immette **2** nel campo **Limiti importo di rettifica**, viene visualizzato un messaggio di avviso quando il valore identificato nel campo **Riga rettifica arrotondamento** aumenta o diminuisce di più di 2.000.

## <a name="format-row-and-column-text"></a>Riga di formato e testo di colonna
È possibile personalizzare l'aspetto dei report modificando i tipi di carattere e formattando il testo. Nelle sezioni seguenti viene descritto come formattare l'aspetto delle righe e delle colonne nei report.

### <a name="manage-font-styles"></a>Gestire gli stili di carattere

È possibile creare e modificare gli stili dei caratteri per il report. È quindi possibile applicare tali stili al documento o a una specifica riga o colonna in un report.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td>Creare uno stile di carattere</td>
<td><ol>
<li>In Progettazione report, nel menu <strong>Formato</strong>, fare clic su <strong>Stili e formattazione</strong>.</li>
<li>Fare clic su <strong>Nuovo</strong> nella finestra di dialogo <strong>Stili e formattazione</strong> quindi immettere un nome univoco per il nuovo stile.</li>
<li>Selezionare i tipi di carattere desiderati e scegliere <strong>OK</strong>.</li>
</ol></td>
</tr>
<tr class="even">
<td>Modificare lo stile di carattere</td>
<td><ol>
<li>In Progettazione report, nel menu <strong>Formato</strong>, fare clic su <strong>Stili e formattazione</strong>.</li>
<li>Selezionare lo stile da modificare nella finestra di dialogo <strong>Stili e formattazione</strong> quindi fare clic su <strong>Modifica</strong>.</li>
<li>Selezionare i tipi di carattere desiderati e scegliere <strong>OK</strong>.</li>
</ol></td>
</tr>
<tr class="odd">
<td>Applicare lo stile di carattere</td>
<td><ol>
<li>In Progettazione report, in una definizione o in una definizione di colonna oppure nelle intestazioni e nei piè di pagina, selezionare una o più celle.</li>
<li>Nell'elenco <strong>Stile</strong> della barra degli strumenti, selezionare uno stile di carattere.</li>
</ol></td>
</tr>
</tbody>
</table>

### <a name="format-row-text"></a>Testo riga formato

La formattazione specificata nella definizione di riga sostituisce la formattazione specificata nella definizione di colonna e nella definizione di report. È possibile modificare il formato di testo utilizzando i controlli sulla barra degli strumenti formattazione. Questi controlli sono i controlli standard di Microsoft Windows.

1.  In Progettazione report, aprire la definizione di riga da modificare.
2.  Selezionare le celle da formattare. Per selezionare più celle, tenere premuto CTRL mentre si seleziona la cella.
3.  Fare clic sul pulsante del formato da applicare nella barra degli strumenti. Ad esempio, per impostare il rientro di una riga, selezionare la riga e fare clic su **Aumenta rientro** ![Aumenta rientro](https://i-technet.sec.s-msft.com/dynimg/IC679497.gif "Aumenta rientro") sulla barra degli strumenti.

### <a name="adjust-columns-while-you-design-reports"></a>Rettificare le colonne durante la progettazione dei report

Per semplificare la visualizzazione delle colonne su cui si lavora nella definizione di riga, è possibile rettificare la larghezza di una colonna e anche nascondere (ridurre) o visualizzare le colonne nel riquadro di visualizzazione. Le modifiche apportate influenzano solo l'aspetto delle colonne sullo schermo. Non influiscono sulla formattazione delle colonne nei report.

### <a name="change-the-width-of-a-column-in-the-view-pane"></a>Modificare la larghezza di una colonna del riquadro di visualizzazione

1.  In Progettazione report, aprire la definizione di riga da modificare.
2.  Nel menu **Formato**, selezionare **Larghezza colonna**.
3.  Nella finestra di dialogo **Larghezza colonna** immettere un valore e quindi fare clic su **OK**. In alternativa, è possibile trascinare il limite destro di una cella di intestazione della colonna per modificare la larghezza della colonna.

### <a name="hide-columns-in-the-view-pane"></a>Nascondere le colonne nel riquadro di visualizzazione

1.  In Progettazione report, aprire la definizione di riga da modificare.
2.  Selezionare la colonna o le colonne da nascondere.
3.  Fare clic con il pulsante destro del mouse e scegliere **Nascondi**.

### <a name="show-all-hidden-columns-in-the-view-pane"></a>Visualizzare tutte le colonne nascoste nel riquadro di visualizzazione

1.  In Progettazione report, aprire la definizione di riga da modificare.
2.  Fare clic con il pulsante destro del mouse sulla colonna ridotta che si desidera visualizzare, quindi scegliere **Scopri**.


<a name="see-also"></a>Vedere anche
--------

[Report finanziari per Microsoft Dynamics 365 for Operations](financial-reporting-intro.md)


