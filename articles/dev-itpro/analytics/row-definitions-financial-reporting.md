---
title: Definizioni di riga in Progettazione report finanziari
description: Una definizione di riga è un componente di report, o blocco predefinito, che specifica il contenuto di ciascuna riga in un report finanziario. Una definizione di riga può combinarsi con le definizioni di colonna, le definizioni di albero gerarchico e le definizioni di report per creare un gruppo di blocchi predefiniti che può essere utilizzato da più società.
author: aprilolson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 68873
ms.assetid: 2fd7b5da-700f-48cb-9003-90c0d82f818f
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: c829af1da1b3109f4687c9a2536dd156339d5c76
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "1551603"
---
# <a name="row-definitions-in-financial-report-designer"></a>Definizioni di riga in Progettazione report finanziari

[!include [banner](../includes/banner.md)]

Una definizione di riga è un componente di report, o blocco predefinito, che specifica il contenuto di ciascuna riga in un report finanziario. Una definizione di riga può combinarsi con le definizioni di colonna, le definizioni di albero gerarchico e le definizioni di report per creare un gruppo di blocchi predefiniti che può essere utilizzato da più società.

## <a name="create-a-row-definition"></a>Crea nuova definizione di riga

1. In Progettazione report, nel pannello di navigazione, fare clic su **Definizioni di riga**.
2. Scegliere **Nuovo**, quindi **Definizione riga** dal menu **File**. Per ulteriori informazioni sul contenuto di ogni cella, vedere [Modificare le celle di definizione di riga](modify-row-definition-cells-financial-reporting.md).

## <a name="open-a-row-definition"></a>Aprire una definizione di riga
1. In Progettazione report, nel pannello di navigazione, fare clic su **Definizioni di riga**.
2. Fare doppio clic sul nome della definizione di riga da aprire.
3. Per visualizzare tutti i blocchi predefiniti associati alla definizione di riga, fare clic con il pulsante destro del mouse sulla definizione di riga e selezionare **Associazioni**.

## <a name="contents-of-a-row-definition"></a> Contenuto di una definizione di riga
Una definizione di riga può contenere fino a 20.000 righe di dimensione finanziaria e includere le seguenti informazioni:

- Testo descrittivo che aggiunge significato al report creando intestazioni di sezione, righe e spazi, ad esempio **Contante** o **Totale ricavi**.
- Collegamenti ai dati finanziari che possono includere valori di dimensione del sistema Microsoft Dynamics 365 for Finance and Operations

    > [!NOTE]
    > È possibile impostare una definizione di riga per il recupero dei dati dal sistema di dimensioni finanziarie ogni volta che viene generato il report.

- Totali e formule di riga basati sui dati finanziari collegati

In genere, ogni riga in una definizione contiene uno dei seguenti tipi di informazioni:

- Riferimenti al sistema di dimensioni finanziarie
- Totali o calcoli basati sui dati
- Formattazione

Esistono due metodi per l'immissione dei dati in una definizione di riga:

- Immettere le informazioni sulla riga manualmente in una nuova definizione di riga. Per ulteriori informazioni, vedere [Modificare le celle di definizione di riga](modify-row-definition-cells-financial-reporting.md).
- Utilizzare Progettazione report per estrarre informazioni di riga direttamente dalle dimensioni finanziarie. Per ulteriori informazioni, vedere la sezione "Unità/righe/formule correlate" in [Modificare le celle di definizione riga](modify-row-definition-cells-financial-reporting.md).

## <a name="add-dimensions-in-a-row-definition"></a> Aggiungere dimensioni in una definizione di riga
Una dimensione è un'intersezione di dati e valori. È possibile raggruppare dati e valori in Progettazione report. È quindi possibile classificare e analizzare le transazioni in modo più dettagliato. È possibile utilizzare la finestra di dialogo **Inserire le righe delle dimensioni** per aggiungere contemporaneamente più righe in una definizione di riga. La finestra di dialogo visualizza una colonna per ogni dimensione. Nella seguente tabella vengono descritte le informazioni che è possibile specificare per ogni dimensione.

| Opzione                | Descrizione |
|-----------------------|-------------|
| Dimensione             | Il modello che identifica la dimensione da aggiungere alla definizione di riga. Questo modello contiene una e commerciale (&) o un cancelletto  (\#) per ogni posizione nelle dimensioni. In genere, utilizzare la e commerciale per la dimensione del conto principale e il cancelletto per le altre dimensioni. |
| Inizio intervallo dimensioni | Primo valore di questa dimensione da aggiungere alla definizione di riga. |
| Fine intervallo dimensioni   | L'ultimo valore della dimensione da aggiungere alla definizione di riga. |

Per aggiungere le dimensioni a una definizione di riga, effettuare i passaggi seguenti.

1. In Progettazione report, fare clic su **Definizioni di riga** quindi aprire la definizione di riga da modificare.
2. Nel menu **Modifica** fare clic su **Inserire le righe delle dimensioni**.
3. Nella finestra di dialogo **Inserisci righe da dimensioni**, nella riga **Dimensioni**, selezionare la cella per la dimensione da trasferire alla definizione di riga e fare clic su **Tutti &&&**.
4. Per limitare la definizione di riga a un intervallo specifico di valori di dimensione, immettere il valore di dimensione iniziale nella cella **Inizio intervallo dimensioni** e specificare il valore finale della dimensione nella cella **Fine intervallo dimensioni**. Per includere tutti i valori per la dimensione selezionata, lasciare vuote tali celle.

    > [!NOTE]
    > I caratteri jolly (\* o ?) negli intervalli di dimensioni potrebbero non restituire tutti i risultati desiderati, a seconda delle regole di confronto applicate ai dati nel database ERP.

5. Nel campo **Codice di riga iniziale** specificare il codice della riga per il primo valore di dimensione da aggiungere alla definizione di riga.
6. Nel campo **Incremento per ogni riga di** specificare la distanza tra codici di riga consecutivi. Ad esempio, se il primo codice di riga è 100 e il valore di incremento è 30, le prime nuove righe hanno i codici 100, 130, 160, 190 e 220. Utilizzare un valore di incremento che offra lo spazio sufficiente per inserire nuove righe di formula e di formato.
7. Scegliere **OK**. Per ogni valore di dimensione selezionato viene aggiunta una riga alla definizione di riga.

## <a name="adjust-rounding-in-a-row-definition"></a> Regolare l'arrotondamento in una definizione riga
In uno stato patrimoniale in cui gli importi sono arrotondati, è possibile che i totali siano sbilanciati. Questo problema può verificarsi se, ad esempio, si utilizza l'opzione di arrotondamento in un report dello stato patrimoniale e anche la definizione di report specifica l'arrotondamento. È possibile utilizzare l'opzione **Rettifica arrotondamento** nella definizione di riga per bilanciare gli importi nei conti patrimoniali. È possibile disattivare o modificare l'arrotondamento nella scheda **Impostazioni** della definizione di report. Nella tabella che segue è illustrato il modo in cui vengono arrotondati gli importi. Nella tabella, i totali delle righe 100 e 200 sono diversi quando l'arrotondamento è abilitato.

| Codice di riga | Importi senza arrotondamento | Importo con arrotondamento in migliaia |
|----------|--------------------------|-----------------------------------------|
| 100      | 3,600                    | 4                                       |
| 200      | 3,700                    | 4                                       |
| Totale    | 7,300                    | 8                                       |

Per rettificare l'arrotondamento nello stato patrimoniale, completare i passaggi seguenti.

1. In Progettazione report, fare clic su **Definizioni di riga** quindi aprire la definizione di riga da modificare.
2. Scegliere **Rettifica per arrotondamento** dal menu **Modifica**.
3. Nella finestra di dialogo **Rettifiche arrotondamento**, immettere i valori seguenti:

    - **Riga rettifica arrotondamento**: il codice della riga che deve essere rettificata per bilanciare lo stato patrimoniale.
    - **Riga totale cespiti**: il codice della riga nello stato patrimoniale contenente i cespiti totali.
    - **Riga totale passività e capitale netto**: il codice della riga nello stato patrimoniale contenente le passività e il capitale netto totali.
    - **Limiti importo di rettifica**: il limite, espresso come numero intero positivo, per le rettifiche automatiche. Questo importo viene confrontato con il valore assoluto della differenza da arrotondamento effettiva.

    > [!NOTE]
    > Questi codici di riga devono essere collegati ai dati finanziari. In altri termini, la riga deve presentare un valore di dimensione nella cella **Collega a Dimensioni finanziarie** **Non** fare riferimento a una riga di descrizione (**DESC**), calcolata (**CALC**) e totalizzata (**TOT**).

Gli importi nello stato patrimoniale vengono ora bilanciati uniformemente quando l'arrotondamento è abilitato.

> [!NOTE]
> Il limite di rettifica è applicato in base all'opzione **Approssimazione di arrotondamento** specificata per la definizione del report. Ad esempio, se si seleziona di arrotondare il report alle migliaia e si immette **2** nel campo **Limiti importo di rettifica**, viene visualizzato un messaggio di avviso quando il valore identificato nel campo **Riga rettifica arrotondamento** aumenta o diminuisce di più di 2.000.

## <a name="format-row-and-column-text"></a>Riga di formato e testo di colonna
È possibile personalizzare l'aspetto dei report modificando i tipi di carattere e formattando il testo. Nelle sezioni seguenti viene descritto come formattare l'aspetto delle righe e delle colonne nei report.

### <a name="manage-font-styles"></a>Gestire gli stili di carattere

È possibile creare e modificare gli stili dei caratteri per il report. È quindi possibile applicare tali stili al documento o a una specifica riga o colonna in un report.

<table>
<tbody>
<tr>
<td><strong>Creare uno stile di carattere</strong></td>
<td>
<ol>
<li>In Progettazione report, nel menu <strong>Formato</strong>, fare clic su <strong>Stili e formattazione</strong>.</li>
<li>Nella finestra di dialogo <strong>Stili e formattazione</strong> fare clic su <strong>Nuovo</strong>, quindi immettere un nome univoco per il nuovo stile.</li>
<li>Selezionare le opzioni desiderate per il carattere e quindi fare clic su <strong>OK</strong>.</li>
</ol>
</td>
</tr>
<tr>
<td><strong>Modificare uno stile di carattere</strong></td>
<td>
<ol>
<li>In Progettazione report, nel menu <strong>Formato</strong>, fare clic su <strong>Stili e formattazione</strong>.</li>
<li>Nella finestra di dialogo <strong>Stili e formattazione</strong> selezionare lo stile a modificare, quindi fare clic su <strong>Modifica</strong>.</li>
<li>Selezionare le opzioni desiderate per il carattere e quindi fare clic su <strong>OK</strong>.</li>
</ol>
</td>
</tr>
<tr>
<td><strong>Applicare lo stile di carattere</strong></td>
<td>
<ol>
<li>In Progettazione report, in una definizione o in una definizione di colonna oppure nelle intestazioni e nei piè di pagina, selezionare una o più celle.</li>
<li>Nell'elenco <strong>Stile</strong> sulla barra degli strumenti selezionare uno stile di carattere.</li>
</ol>
</td>
</tr>
</tbody>
</table>

### <a name="format-row-text"></a>Testo riga formato

La formattazione specificata nella definizione di riga sostituisce la formattazione specificata nella definizione di colonna e nella definizione di report. È possibile modificare il formato di testo utilizzando i controlli sulla barra degli strumenti formattazione. Tali controlli corrispondono ai controlli standard di Microsoft Windows.

1. In Progettazione report aprire la definizione di riga da modificare.
2. Selezionare le celle da formattare. Per selezionare più celle, tenere premuto CTRL mentre si seleziona la cella.
3. Fare clic sul pulsante del formato da applicare nella barra degli strumenti. Ad esempio, per impostare il rientro di una riga, selezionare la riga e fare clic su **Aumenta rientro** ![Aumenta rientro](https://i-technet.sec.s-msft.com/dynimg/IC679497.gif "Aumenta rientro") sulla barra degli strumenti.

### <a name="adjust-columns-while-you-design-reports"></a>Rettificare le colonne durante la progettazione dei report

Per semplificare la visualizzazione delle colonne su cui si lavora nella definizione di riga, è possibile rettificare la larghezza di una colonna e anche nascondere (ridurre) o visualizzare le colonne nel riquadro di visualizzazione. Le modifiche apportate influenzano solo l'aspetto delle colonne sullo schermo. Non influiscono sulla formattazione delle colonne nei report.

### <a name="change-the-width-of-a-column-in-the-view-pane"></a>Modificare la larghezza di una colonna del riquadro di visualizzazione

1. In Progettazione report, aprire la definizione di riga da modificare.
2. Nel menu **Formato**, selezionare **Larghezza colonna**.
3. Nella finestra di dialogo **Larghezza colonna** immettere un valore e quindi fare clic su **OK**. In alternativa, è possibile trascinare il limite destro di una cella di intestazione della colonna per modificare la larghezza della colonna.

### <a name="hide-columns-in-the-view-pane"></a>Nascondere le colonne nel riquadro di visualizzazione

1. In Progettazione report, aprire la definizione di riga da modificare.
2. Selezionare la colonna o le colonne che si intende ridurre a icona.
3. Fare clic con il pulsante destro del mouse e scegliere **Nascondi**.

### <a name="show-all-hidden-columns-in-the-view-pane"></a>Visualizzare tutte le colonne nascoste nel riquadro di visualizzazione

1. In Progettazione report, aprire la definizione di riga da modificare.
2. Fare clic con il pulsante destro del mouse sulla colonna ridotta che si desidera visualizzare, quindi scegliere **Scopri**.


## <a name="additional-resources"></a>Risorse aggiuntive

[Creazione di report finanziari](financial-reporting-intro.md)
