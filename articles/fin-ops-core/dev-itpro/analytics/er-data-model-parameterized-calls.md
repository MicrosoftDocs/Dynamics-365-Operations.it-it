---
title: Supportare le chiamate con parametri di modelli dati di tipo Report elettronici
description: Questo articolo spiega come implementare le chiamate parametrizzate di modelli di dati di reporting elettronico (ER).
author: NickSelin
ms.date: 03/14/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERModelMappingDesigner, EROperationDesigner, ERExpressionDesignerFormula, ERDataModelDesigner
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-10-01
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 65ac81e9aa25b286640fd526e71b55de3b0695ca
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8884259"
---
# <a name="support-parameterized-calls-of-er-data-models"></a>Supportare le chiamate con parametri di modelli dati di tipo Report elettronici

[!include [banner](../includes/banner.md)]

Per generare documenti aziendali, configurare una soluzione di [Creazione di report elettronici (ER)](general-electronic-reporting.md) che contiene i seguenti componenti ER:

- **[Formato](er-overview-components.md#format-component)**: questo componente specifica la struttura di un documento commerciale.
- **Mappatura del formato**: questo componente controlla il modo in cui un documento commerciale viene compilato in fase di esecuzione.
- **[Mappatura del modello](er-overview-components.md#model-mapping-component)**: questo componente specifica ciò che i dati estraggono dall'applicazione in una mappatura del formato.
- **[Modello di dati](er-overview-components.md#data-model-component)**: questo componente trasmette le informazioni tra i singoli componenti.

Quando si esegue un formato ER, viene eseguito ogni elemento di formato, a partire dall'elemento di formato radice. Ogni volta che un elemento di formato eseguito contiene un'associazione a una [origine dati](general-electronic-reporting.md#configuring-data-model-mappings-for-outgoing-documents), l'origine dati viene eseguita per fornire i dati previsti e utilizzarli per compilare l'elemento di formato. Quando un'origine dati del tipo *Modello*, viene chiamata la mappatura del modello appropriata per estrarre i dati dall'applicazione, in base alle impostazioni della mappatura del modello.

In precedenza, queste chiamate di mappatura del modello non potevano essere parametrizzate per renderle dipendenti dalla logica del formato eseguito. È stato supportato solo il seguente flusso di dati.

<table>
<tbody>
<tr align="center">
<td>
<b>Formato</b><br>
Elemento&nbsp;formato<br>
&nbsp;
</td>
<td>
<i>Associazione</i><br>
&gt;&nbsp;richiesta&nbsp;&gt;<br>
&lt;&nbsp;valore&nbsp;&lt;
</td>
<td><b>Mappatura&nbsp;formato</b><br>
Origine dati<br>
&nbsp;
</td>
<td>
<i>Modello&nbsp;dati</i><br>
&gt;&nbsp;richiesta&nbsp;&gt;<br>
&lt;&nbsp;valore&nbsp;&lt;
</td>
<td>
<b>Mapping&nbsp;modello</b><br>
Origine&nbsp;dati<br>
&nbsp;
</td>
<td>
<i>Associazione</i><br>
&gt;&nbsp;richiesta&nbsp;&gt;<br>
&lt;&nbsp;valore&nbsp;&lt;
</td>
<td>
<b>Tabella</b><br>
Registra<br>
Campo
</td>
</tr>
</tbody>
</table>

Tuttavia, nella versione 10.0.15 e successive, è possibile configurare i campi del modello di dati che possono essere richiamati solo quando vengono forniti i valori dei parametri configurati. Quando tale campo viene configurato e chiamato da un componente di formato, i parametri richiesti devono essere forniti in un'associazione di formato come argomenti della chiamata. In questi casi, i valori degli argomenti possono essere specificati in base a valori specifici del formato. Pertanto, puoi usare **parametrizzazione runtime dinamico** per le chiamate al modello di dati per supportare il flusso di dati seguente.

<table>
<tbody>
<tr align="center">
<td>
<b>Formato</b><br>
Elemento&nbsp;formato&nbsp;1<br>
<br>
Elemento&nbsp;formato&nbsp;2<br>
&nbsp;<br>
&nbsp;
</td>
<td>
<i>Associazione</i><br>
&gt;&nbsp;richiesta&nbsp;1&nbsp;&gt;<br>
&lt;&nbsp;valore&nbsp;1&nbsp;&lt;<br>
&gt;&nbsp;richiesta&nbsp;2&nbsp;&gt;<br>
&lt;&nbsp;valore&nbsp;3&nbsp;&lt;<br>
&nbsp;
</td>
<td>
<b>Mappatura&nbsp;formato</b><br>
Origine&nbsp;dati&nbsp;1<br>
&nbsp;<br>
<b>value2=Func(value1)</b><br>
&nbsp;<br>
&nbsp;
</td>
<td>
<i>Modello&nbsp;dati</i><br>
&gt;&nbsp;campo1&nbsp;&gt;<br>
&lt;&nbsp;valore&nbsp;1&nbsp;&lt;<br>
<b>&gt;&nbsp;campo2(valore2)&nbsp;&gt;</b><br>
&lt;&nbsp;valore&nbsp;3&nbsp;&lt;<br>
&nbsp;
</td>
<td>
<b>Mapping&nbsp;modello</b><br>
Origine&nbsp;dati&nbsp;1<br>
<br>
Origine&nbsp;dati&nbsp;2<br>
&nbsp;<br>
&nbsp;
</td>
<td>
<i>Associazione</i><br>
&gt;&nbsp;richiesta&nbsp;1&nbsp;&gt;<br>
&lt;&nbsp;valore&nbsp;1&nbsp;&lt;<br>
&gt;&nbsp;richiesta&nbsp;2&nbsp;&gt;<br>
&lt;&nbsp;valore&nbsp;3&nbsp;&lt;<br>
&nbsp;
</td>
<td>
<b>Tabella&nbsp;1</b><br>
Record&nbsp;1<br>
Campo&nbsp;1<br>
<b>Tabella&nbsp;2</b><br>
Record&nbsp;2<br>
Campo&nbsp;2
</td>
</tr>
</tbody>
</table>

La nuova funzionalità consente di parametrizzare la chiamata a qualsiasi campo del modello di dati del tipo [*Record*](er-formula-supported-data-types-composite.md#record) o [*Elenco record*](er-formula-supported-data-types-composite.md#record-list). I seguenti tipi di dati sono supportati per i parametri di un campo del modello di dati:

- [Boolean](er-formula-supported-data-types-primitive.md#boolean)
- [Container](er-formula-supported-data-types-composite.md#container)
- [Data](er-formula-supported-data-types-primitive.md#date)
- [Data/Ora](er-formula-supported-data-types-primitive.md#datetime)
- [GUID](er-formula-supported-data-types-primitive.md#guid)
- [Int64](er-formula-supported-data-types-primitive.md#int64)
- [Integer](er-formula-supported-data-types-primitive.md#integer)
- [Reale](er-formula-supported-data-types-primitive.md#real)
- [String](er-formula-supported-data-types-primitive.md#string)

È possibile specificare ogni parametro di un campo del modello di dati per il quale l'argomento può essere fornito come valore singolo del tipo di dati definito e l'[*elenco*](er-formula-supported-data-types-composite.md#record-list) di tali valori.

> [!NOTE]
> Il valore predefinito per il parametro di un campo del modello di dati non è supportato. Se aggiungi un parametro a un campo in un modello dati e la versione di quel modello dati è già stata rilasciata e pubblicata, devi [riassegnare](general-electronic-reporting.md#upgrading-a-format-selecting-a-new-version-of-base-format-rebase) tutti i mapping e i formati del modello corrispondenti alla nuova versione di questo modello, perché questa modifica del modello di dati non è compatibile con le versioni precedenti.

È possibile configurare i campi del modello di dati parametrizzati per rendere le chiamate di mapping del modello specifiche per il formato. Questo approccio può aiutarti a ridurre il numero di mapping del modello che devono essere configurati per molti formati di un singolo modello di dati. Puoi anche utilizzare questo approccio per migliorare le prestazioni di esecuzione dei tuoi formati e ridurre il tempo necessario per generare documenti aziendali. Per ulteriori informazioni su questa funzionalità, completa l'esempio in questo articolo.

## <a name="example-use-parameterized-calls-of-er-data-models"></a>Esempio: usa le chiamate con parametri di modelli dati di tipo Report elettronici

I passaggi seguenti spiegano come un utente con il ruolo di amministratore di sistema o di sviluppatore di report elettronici può progettare una soluzione ER che contiene un modello di dati, una mappatura del modello e un componente ER dei formati che sono configurati per chiamare una mappatura del modello da un formato fornendo un argomento per la chiamata, il cui valore è stato calcolato in fase di esecuzione utilizzando la formula del formato in esecuzione. 

Queste operazioni possono essere completate nella società **DEMF**. Non sono necessarie modifiche al codice. 

In questo esempio verranno create le [configurazioni](general-electronic-reporting.md#Configuration) ER necessarie per la società di esempio **Litware, Inc**. Verifica che il provider di configurazione per la società di esempio **Litware, Inc.** (`http://www.litware.com`) sia elencato per il framework ER e sia contrassegnato come **Attivo**. Se questo provider di configurazione non è elencato o non è contrassegnato come **Attivo**, completare i passaggi in [Creare un provider di configurazione e contrassegnarlo come attivo](tasks/er-configuration-provider-mark-it-active-2016-11.md).

### <a name="business-scenario"></a>Scenario aziendale

Disponi di una soluzione ER che include un formato che puoi eseguire per generare un documento elettronico a scopo di controllo. Questo formato contiene le transazioni fiscali correlate agli ordini cliente e agli ordini fornitore e che hanno i dettagli richiesti, come la data della transazione e il valore fiscale. A partire dal nuovo anno fiscale, la struttura di questo documento è cambiata. È ora necessario inviare un documento esteso che includa dettagli aggiuntivi (nomi) di tutte le entità (clienti e fornitori) le cui transazioni sono presentate nei report generati. Pertanto, è necessario modificare la soluzione ER in modo che generi documenti conformi a questo nuovo requisito.

### <a name="configure-the-er-framework"></a>Configurare il framework ER

Segui i passaggi in [Configurare il framework ER](er-quick-start2-customize-report.md#ConfigureFramework) per impostare il set minimo di parametri ER. È necessario completare questa configurazione prima di iniziare a utilizzare il framework ER per progettare una nuova soluzione ER.

### <a name="design-a-domain-specific-data-model"></a>Progettare un modello di dati specifici di un dominio

È necessario creare una nuova configurazione ER che contenga il componente del modello di dati desiderato. Questo modello di dati verrà utilizzato come origine dati quando si progetta un formato ER per generare un report di controllo.

Segui questi passaggi per importare il modello di dati obbligatorio da un file XML fornito da Microsoft.

1. Scarica il file [Sample audit model.version.1.xml](https://download.microsoft.com/download/7/1/9/719b0132-fed7-4c73-8afa-90cac29c2fee/Sample-audit-model.version.1.xml) e salvalo sul computer locale.
2. Andare a **Amministrazione organizzazione** \> **Aree di lavoro** \> **Creazione di report elettronici**.
3. Nell'area di lavoro **Creazione di report elettronici**, selezionare **Configurazioni report**.
4. Nella pagina **Configurazioni**, nel riquadro Azioni, seleziona **Exchange** \> **Carica da file XML**.
5. Selezionare **Sfoglia**, quindi trovare e selezionare il file **Sample audit model.version.1.xml**.
6. Selezionare **OK** per importare la configurazione.

    ![Configurazione del modello di dati ER importata nella pagina Configurazioni.](./media/er-data-model-parameterized-calls-imported-model.png)

La figura seguente mostra la versione editabile del modello di dati configurato nella pagina **Progettazione del modello di dati**.

![Struttura del modello dati ER nella pagina Progettazione del modello di dati.](./media/er-data-model-parameterized-calls-model1.png)

Attualmente, il modello è progettato per esporre solo le transazioni fiscali che hanno i dettagli richiesti.

### <a name="design-a-model-mapping-for-the-configured-data-model"></a>Progettare un mapping del modello per il modello di dati configurato

In qualità di utente nel ruolo di sviluppatore per la creazione di report elettronici, è necessario creare una nuova configurazione ER che contenga un modello di dati di controllo di esempio. Questo componente implementa il modello di dati configurato per Microsoft Dynamics 365 Finance ed è specifico di tale app. È necessario configurare il componente di mapping del modello per specificare gli oggetti dell'applicazione che devono essere utilizzati per compilare il modello di dati configurato con i dati dell'applicazione in fase di runtime. Per completare questa attività, è necessario essere a conoscenza di come la struttura dati del dominio aziendale fiscale viene implementata in Finance.

Segui questi passaggi per importare il mapping del modello obbligatorio da un file XML fornito da Microsoft.

1. Scarica il file [Sample audit model mapping.version.1.1.xml](https://download.microsoft.com/download/c/0/3/c03a4673-b1b1-4ef8-96d0-bf96518be6e0/Sample-audit-model-mapping.version.1.1.xml) e salvalo sul computer locale.
2. Andare a **Amministrazione organizzazione** \> **Aree di lavoro** \> **Creazione di report elettronici**.
3. Nell'area di lavoro **Creazione di report elettronici**, selezionare **Configurazioni report**.
4. Nella pagina **Configurazioni**, nel riquadro Azioni, seleziona **Exchange** \> **Carica da file XML**.
5. Seleziona **Sfoglia**, quindi trova e seleziona il file **Sample audit model mapping.version.1.1.xml**.
6. Selezionare **OK** per importare la configurazione.

    ![Configurazione del mapping del modello ER importata nella pagina Configurazioni.](./media/er-data-model-parameterized-calls-imported-mapping.png)

La figura seguente mostra la versione editabile del mapping del modello configurato nella pagina **Progettazione mapping modello**.

![Struttura del mapping del modello ER nella pagina Progettazione mapping modello.](./media/er-data-model-parameterized-calls-mapping1.png)

Attualmente, il mapping del modello è progettato per visualizzare le transazioni fiscali che hanno i dettagli richiesti. Recupera queste informazioni dalla tabella dell'applicazione `TaxTrans` utilizzando le origini dati ER `TaxTrans` e `TaxTransFiltered` configurate.

### <a name="design-a-new-format"></a>Progetta un nuovo formato

In qualità di utente nel ruolo di consulente funzionale per la creazione di report elettronici, è necessario creare una nuova configurazione ER che contenga un componente di formato. Devi configurare il componente formato per compilare i report generati con le transazioni fiscali con tutti i dettagli richiesti.

Segui questi passaggi per importare il formato obbligatorio da un file XML fornito da Microsoft.

1. Scaricare il file [Sample audit format.version.1.1.xml](https://download.microsoft.com/download/e/b/7/eb7e126e-2bb3-4bbb-a735-ffd4c48920b1/Sample-audit-format.version.1.1.xml) e salvarlo sul computer locale.
2. Andare a **Amministrazione organizzazione** \> **Aree di lavoro** \> **Creazione di report elettronici**.
3. Nell'area di lavoro **Creazione di report elettronici**, selezionare **Configurazioni report**.
4. Nella pagina **Configurazioni**, nel riquadro Azioni, seleziona **Exchange** \> **Carica da file XML**.
5. Seleziona **Sfoglia**, quindi trovare e selezionare il file **Sample audit format.version.1.1.xml**.
6. Selezionare **OK** per importare la configurazione.

    ![Configurazione del formato ER importata nella pagina Configurazioni.](./media/er-data-model-parameterized-calls-imported-format.png)

La figura seguente mostra la versione editabile del formato configurato nella pagina **Progettazione formato**.

![Struttura del formato ER nella pagina Progettazione formato.](./media/er-data-model-parameterized-calls-format1.png)

Il formato ER è configurato per generare un report come file di testo in formato CSV (valori separati da virgola).

### <a name="run-the-imported-format"></a>Eseguire il formato importato

1. Nella pagina **Configurazioni**, seleziona la configurazione **Esempio di formato di controllo** e quindi, nel riquadro azioni, seleziona **Esegui**.
2. Nella finestra di dialogo **Parametri creazione di report elettronici**, nella scheda **Record da includere**, seleziona **Filtro**.
3. Specificare le condizioni per selezionare le transazioni fiscali dei buoni **PIV-110000004** e **INV-10000001**.
4. Seleziona **OK**.
5. Seleziona **OK**.
6. Rivedi il documento generato che contiene le transazioni fiscali dei giustificativi selezionati.

    ![Anteprima del documento generato con transazioni fiscali.](./media/er-data-model-parameterized-calls-output1.png)

### <a name="adjust-the-imported-er-solution"></a>Regola la soluzione ER importata

Secondo il nuovo requisito, il documento che devi presentare deve contenere i nomi dei clienti e dei fornitori le cui transazioni sono incluse. Pertanto, devi modificare la soluzione ER importata in modo che generi un documento conforme a questo nuovo requisito.

Decidi come implementare le modifiche richieste dei componenti ER importati.

L'approccio più ovvio è quello di implementare le seguenti modifiche:

- Nel tuo modello di dati, aggiungi il nuovo campo del modello di dati `Transaction.Party.Name` del tipo *Stringa*.
- Nel mapping del modello, configura l'associazione per il nuovo campo del modello di dati utilizzando le relazioni di tabella disponibili per accedere al relativo record della tabella delle applicazioni e recupera `DirPartyTable` il valore del campo `Name` da esso.

Sebbene questo approccio funzioni, potrebbe causare problemi di prestazioni nel database SQL, perché `TaxTrans` è la tabella delle transazioni e può quindi contenere un grande volume di record. In questo caso, il numero di chiamate a `DirPartyTable` deve essere uguale al numero di record nella tabella `TaxTrans` che può causare problemi di prestazioni.

In alternativa, potresti implementare le seguenti modifiche:

- Nel tuo modello di dati, aggiungi la nuova radice `Party` e il nuovo campo `Party.Name`.
- Nel mapping del modello, aggiungi una nuova origine dati che unirà tutti i record delle tabelle utilizzati nelle relazioni tra tabelle per accedere al relativo record della tabella delle applicazioni `DirPartyTable`, a partire dalla tabella `TaxTrans`.

Sebbene questo approccio funzioni, potrebbe causare alcuni problemi di consumo di memoria. Anche quando una nuova origine dati [JOIN](er-join-data-sources.md) viene eseguita come una singola richiesta SQL al database delle applicazioni per evitare problemi di prestazioni del database, il risultato deve essere recuperato nella memoria del server delle applicazioni. Poiché il numero di record e il numero di campi in tali record saranno piuttosto grandi, questo approccio potrebbe causare un consumo di memoria molto elevato. Potrebbe anche essere generata un'eccezione di runtime esaurito.

È possibile implementare le modifiche quando un formato in esecuzione raccoglie, in memoria, i codici identificativi univoci di clienti e fornitori per tutte le transazioni fiscali che verranno presentate su un report generato. Poiché devono essere mantenuti solo i codici univoci, il set finale di codici non sarà sufficientemente grande da influire sul consumo di memoria. L'insieme di codici verrà quindi passato al mapping del modello come argomento di un'altra chiamata dell'origine dati di tipo *Modello*. Sulla base di tale chiamata, il mapping del modello eseguirà una nuova origine dati ER che effettua una singola richiesta SQL al database dell'applicazione da recuperare, dalla tabella `DirPartyTable`, registra solo per quei soggetti i cui codici sono stati presentati nell'insieme di codici fornito.

### <a name="adjust-the-imported-data-model"></a>Regolare il modello dati importato

1. Andare a **Amministrazione organizzazione** \> **Creazione di report elettronici** \> **Configurazioni**.
2. Nella pagina **Configurazioni**, nella struttura delle configurazioni del riquadro sinistro, seleziona **Modello di controllo di esempio**.
3. Nella scheda **Versioni**, seleziona la versione **2** con stato **[Bozza](general-electronic-reporting.md#component-versioning)**.
4. Selezionare la Scheda dettaglio **Componenti di configurazione**.
5. Seleziona **Progettazione** per aprire il modello di dati per la modifica.
6. Nella pagina **Modello di dati**, assicurati che il campo `Root` sia selezionato, quindi seleziona **Nuovo**.
7. Nella finestra di dialogo a discesa, effettuare le seguenti operazioni:

    1. Nel gruppo di campi **Nuovo nodo come** seleziona l'opzione **Figlio di un nodo attivo**.
    2. Nel campo **Nome** immetti **Party**.
    3. Nel campo **Tipo di articolo** selezionare **Elenco di record**.
    4. Seleziona **Aggiungi** per completare l'aggiunta del nuovo campo.

8. Accertati di selezionare il campo `Root.Party`, e successivamente, nella scheda **Nodo**, seleziona **Parametri**.
9. Nella finestra di dialogo **Parametri** segui questi passaggi:

    1. Nella scheda **Parametri**, seleziona **Nuovo**.
    2. Nel campo **Nome** immettere **PartyRefRecId**.
    3. Nel campo **Tipo** seleziona **Int64**.
    4. Selezionare la casella di controllo **Elenco**.
    5. Seleziona **OK** per completare l'immissione dei parametri.

    > [!NOTE]
    > Hai appena configurato il campo del modello di dati `Root.Party` come un campo chiamato quando un valore viene fornito nel parametro **PartyRefRecId**. Questo valore deve essere presentato nell'elenco dei record che contiene un campo `Value` del tipo di dati *Int64*.

    ![Finestra di dialogo Parametri.](./media/er-data-model-parameterized-calls-model2a.png)

10. Accertarti che il campo `Root.Party` sia selezionato, quindi seleziona **Nuovo**.
11. Nella finestra di dialogo a discesa, effettuare le seguenti operazioni:

    1. Nel gruppo di campi **Nuovo nodo come** seleziona l'opzione **Figlio di un nodo attivo**.
    2. Nel campo **Nome** immettere **Nome**.
    3. Nel campo **Tipo di articolo** selezionare **Stringa**.
    4. Seleziona **Aggiungi** per completare l'aggiunta del nuovo campo.

12. Seleziona **Salva** e chiudi la pagina **Modelli di dati**.

    ![Struttura del modello di dati ER modificati nella pagina Progettazione del modello di dati.](./media/er-data-model-parameterized-calls-model2b.png)

13. Nella Scheda dettaglio **Versioni**, per la versione **2**, seleziona **Cambia stato** \> **Completa**. Selezionare **OK**.

    > [!NOTE]
    > Le modifiche al tuo modello di dati sono memorizzate nella seconda revisione del componente del modello di dati **Modello di controllo di esempio** ubicato nella seconda versione della configurazione ER **Modello di controllo di esempio**.

![Configurazione del modello di dati ER aggiornata nella pagina Configurazioni.](./media/er-data-model-parameterized-calls-updated-model.png)

### <a name="adjust-the-imported-model-mapping"></a>Regolare il mapping del modello importato

1. Nella pagina **Configurazioni**, nella struttura delle configurazioni del riquadro sinistro, espandi **Modello di controllo di esempio**.
2. Seleziona **Mapping del modello di controllo di esempio**, quindi nella scheda dettaglio **Versioni**, seleziona la seconda versione del mapping basata sulla prima versione del modello di dati (versione **1.2**) con stato **Bozza**.
3. Selezionare **Riassegna**.
4. Nel campo **Versione di destinazione**, lascia la versione **2** del modello di base **Modello di controllo di esempio**.
5. Seleziona **OK** per riassegnare e allineare il mapping dei modelli con modifiche al modello di dati recenti.

    Nota che il numero di versione del mapping del modello editabile è cambiata da **1.2** a **2.2** ad indicare che la seconda versione del modello è attualmente usata come base.

6. Selezionare **Progettazione**.
7. Seleziona **Progettazione** per il mapping del modello corrente nella pagina **Modello per mapping origine dati**.
8. Per aggiungere una nuova origine dati e accedere alla tabella delle applicazioni `DirPartyTable`, effettuare i seguenti passaggi:

    1. Nel riquadro **Tipo di origine dati**, seleziona **Dynamics 365 for Operations \> Tabella dei record**.
    2. Selezionare **Aggiungi radice** nel riquadro **Origini dati**.
    3. Nel campo **Nome** immettere **PartyTable**.
    4. Nel campo **ID tabella** specificare **DirPartyTable**.
    5. Seleziona **OK** per completare l'aggiunta della nuova origine dati.

9. Per aggiungere una nuova origine dati e richiedere record `DirPartyTable`, basati sull'elenco fornito di codici di identificazione record, effettuare i seguenti passaggi:

    1. Nel riquadro **Tipi di origine dati**, seleziona **Generale \> Contenitore vuoto**.
    2. Selezionare **Aggiungi radice** nel riquadro **Origini dati**.
    3. Nel campo **Nome** immetti **Dati**.
    4. Seleziona **OK** per completare l'aggiunta della nuova origine dati.
    5. Nel riquadro **Origini dati**, seleziona l'origine dati **Dati**.
    6. Nel riquadro **Tipo di origine dati**, seleziona **Funzioni \> Campo calcolato**.
    7. Seleziona **Aggiungi** nel riquadro **Origini dati**.
    8. Nel campo **Nome** immetti **DirParty**.
    9. Selezionare **Modifica formula**.
    10. Nella pagina **Designer formula** seleziona **Parametri**.
    11. Nella finestra di dialogo **Parametri** segui questi passaggi:

        1. Nella scheda **Parametri**, seleziona **Nuovo**.
        2. Nel campo **Nome** immetti **DirPartyId**.
        3. Nel campo **Tipo** seleziona **Int64**.
        4. Selezionare la casella di controllo **Elenco**.
        5. Seleziona **OK**.

        > [!NOTE]
        > Hai appena configurato questo campo calcolato in modo che accetti al runtime l'argomento di un singolo parametro configurato come elenco record che ha un singolo campo `Value` del tipo *Int64*.

    12. Nel campo **Formula**, immettere la seguente espressione:

        `FILTER(PartyTable, VALUEINLARGE(PartyTable.RecId, DirPartyId, DirPartyId.Value))`

        > [!NOTE]
        > Hai appena configurato il campo calcolato `DirParty` per recuperare solo i record `DirPartyTable` in cui i codici di identificazione dei record siano inclusi nell'elenco `DirPartyId` fornito come argomento quando viene richiamato il campo `DirParty`.

        ![Formula per recuperare i nomi delle entità dalla tabella delle applicazioni della pagina Designer formula.](./media/er-data-model-parameterized-calls-formula1.png)

    13. Selezionare **Salva** e chiudere la pagina **Designer formula**.
    14. Seleziona **Salva**, quindi **OK** per completare l'aggiunta della nuova origine dati.

10. Seguire questi passaggi per associare la nuova origine dati al nuovo campo del modello di dati in modo che questo venga usato per visualizzare i nomi delle entità:

    1. Nel riquadro **Modello di dati**, seleziona il campo del modello di dati `Root.Party`.
    2. Selezionare **Modifica** nel riquadro **Modello di dati**.
    3. Nella pagina **Designer formula** nel campo **Formula** immetti la seguente espressione `Data.DirParty(PartyRefRecId)`.
    4. Selezionare **Salva** e chiudere la pagina **Designer formula**.

        > [!NOTE]
        > Hai appena configurato l'associazione alla chiamata dell'origine dati `Data.DirParty` configurata e fornito l'elenco dei codici di identificazione che verranno specificati nel formato quando il campo del modello di dati `Root.Party` viene richiamato.

    5. Nel riquadro **Modello di dati**, seleziona il campo del modello di dati `Root.Party.Name`.
    6. Selezionare **Modifica** nel riquadro **Modello di dati**.
    7. Nella pagina **Designer formula**, nel riquadro **Origine dati**, espandi **Dati \> DirParty** e seleziona **Nome**.
    8. Selezionare **Aggiungi origine dati**.
    9. Selezionare **Salva** e chiudere la pagina **Designer formula**.

    ![Struttura del mapping del modello ER modificato nella pagina Progettazione del mapping del modello.](./media/er-data-model-parameterized-calls-mapping2.png)

11. Selezionare **Salva** chiudere la pagina **Progettazione mapping di modello**.
12. Chiudere la pagina **Modello per mapping origine dati**.
13. Nella Scheda dettaglio **Versioni**, per la versione **2.2**, seleziona **Cambia stato \> Completa**. Selezionare **OK**.

### <a name="adjust-the-imported-format"></a>Modifica il formato importato

1. Nella pagina **Configurazioni**, seleziona **Formato di controllo di esempio**.
2. Nella scheda dettaglio **Versioni**, seleziona la versione **1.2** con stato **Bozza**.
3. Selezionare **Riassegna**.
4. Nel campo **Versione di destinazione**, lascia la versione **2** del modello di base **Modello di controllo di esempio**.
5. Seleziona **OK** per riassegnare e allineare il formato alle modifiche al modello di dati recenti.
6. Selezionare **Progettazione**.
7. Nella pagina **Progettazione formato** nell'albero della struttura formati nel riquadro di sinistra, seleziona **Espandi/comprimi**.
8. Per aggiungere un nuovo elemento di formato per raccogliere codici di identificazione dei record di entità le cui transazioni sono presentate sui record generati, effettuare i seguenti passaggi:

    1. Nell'albero della struttura del formato, seleziona l'elemento della sequenza **Report.Row.Trans**.
    2. Seleziona **Aggiungi**.
    3. Nella finestra di dialogo **Aggiungi**, seleziona **Origine dati \> Articolo**.
    4. Nella finestra di dialogo **Proprietà componente**, nel campo **Nome**, immetti **ID**.
    5. Nel campo **Tipo di dati** seleziona **Int64**.
    6. Seleziona **OK**.

    > [!NOTE]
    > Un elemento **Origine dati \> Articolo** può essere utilizzata per eseguire calcoli interni e trasformazioni dei dati al solo scopo di eseguire il formato. Pertanto, aggiungendo questo elemento del formato, non modifichi il contenuto di un documento generato.

9. Effettuare questi passaggi per aggiungere nuovi elementi di formato per immettere i nomi delle entità o i report generati:

    1. Seleziona l'elemento della sequenza **Report.Row**.
    2. Seleziona **Aggiungi**.
    3. Nella finestra di dialogo **Aggiungi** seleziona **Testo \> Sequenza**.
    4. Nella finestra di dialogo **Proprietà componente**, nel campo **Nome**, immetti **Entità**.
    5. Seleziona **OK**.
    6. Seleziona l'elemento della sequenza **Report.Row.Party**.
    7. Seleziona **Aggiungi**.
    8. Nella finestra di dialogo **Aggiungi** seleziona **Testo \> Stringa**.
    9. Nella finestra di dialogo **Proprietà componente**, nel campo **Nome**, immetti **Nome**.
    10. Seleziona **OK**.

10. Per aggiungere una nuova origine dati per raccogliere codici di identificazione dei record di entità le cui transazioni sono presentate sui record generati, effettuare i seguenti passaggi:

    1. Nella scheda **Mapping**, selezionare **Aggiungi radice**.
    2. Nella finestra di dialogo **Aggiungi origine dati**, seleziona **Funzioni \> Raccolta dati**.
    3. Nella finestra di dialogo **Proprietà origine dati "Raccolta dati"** nel campo **Nome** immetti **PartyIds**.
    4. Nel campo **Tipo di articolo** seleziona **Int64**.
    5. Seleziona **OK**.

11. Per aggiungere una nuova associazione per raccogliere codici di identificazione dei record di entità le cui transazioni sono presentate sui record generati, effettuare i seguenti passaggi:

    1. Nell'albero della struttura del formato, seleziona l'elemento dell'articolo dei dati **Report.Row.Trans.Id**.
    2. Selezionare **Modifica formula**.
    3. Nella pagina **Designer formula**, immetti l'espressione `PartyIds.Collect(model.Transaction.Party.RecId)`.
    4. Selezionare **Salva** e chiudere la pagina **Designer formula**.

12. Effettuare questi passaggi per aggiungere nuove associazioni per immettere i nomi delle entità o i report generati:

    1. Nell'albero della struttura del formato, seleziona l'elemento della sequenza **Report.Party**.
    2. Selezionare **Modifica formula**.
    3. Nella pagina **Designer formula**, immetti l'espressione `model.Party(PartyIds.Result)`.
    4. Selezionare **Salva** e chiudere la pagina **Designer formula**.
    5. Nell'albero della struttura del formato, seleziona l'elemento della sequenza **Report.Party.Name**.
    6. Nella scheda **Mapping**, seleziona il campo del modello di dati `model.Party.Name`.
    7. Selezionare **Associa**.

    ![Struttura del formato ER modificato nella pagina Progettazione formato.](./media/er-data-model-parameterized-calls-format2.png)

13. Seleziona **Salva** e chiudi la pagina **Progettazione formato**.
14. Chiudere la pagina **Modello per mapping origine dati**.
15. Nella Scheda dettaglio **Versioni**, per la versione **2.2**, seleziona **Cambia stato** \> **Completa**. Selezionare **OK**.

### <a name="run-the-adjusted-format"></a>Eseguire il formato modificato

1. Nella pagina **Configurazioni**, seleziona **Formato di controllo di esempio**, quindi, nel riquadro Azioni, seleziona **Esegui**.
2. Nella finestra di dialogo **Parametri creazione di report elettronici**, nella scheda **Record da includere**, seleziona **Filtro**.
3. Specificare le condizioni per selezionare le transazioni iva dei giustificativi **PIV-110000004** e **INV-10000001**.
4. Seleziona **OK**.
5. Seleziona **OK**.
6. Rivedere il documento generato che contiene e transazioni iva dei giustificativi selezionati e i nomi dei relativi clienti e fornitori.

    ![Anteprima del documento generato con transazioni iva e nomi delle entità.](./media/er-data-model-parameterized-calls-output2.png)

7. Vai a **Contabilità fornitori** \> **Fornitori** \> **Tutti i fornitori** quindi rivedere i dettagli dei giustificativi selezionati **PIV-110000004**, incluso il nome del fornitore.

    ![Rivedere i dettagli dei giustificativi di acquisto sulle pagine Tutti i fornitori e Giornale di registrazione fatture.](./media/er-data-model-parameterized-calls-review1.gif)

8. Vai a **Contabilità clienti** \> **Clienti** \> **Tutti i clienti** quindi rivedere i dettagli dei giustificativi selezionati **INV-10000001**, incluso il nome del fornitore.

    ![Rivedere i dettagli dei giustificativi di vendita sulle pagine Tutti i clienti e IVA registrata.](./media/er-data-model-parameterized-calls-review2.gif)

Per ulteriori dettagli su questa esecuzione della soluzione ER, utilizzare il parser di [rilevamento delle prestazioni](trace-execution-er-troubleshoot-perf.md) ER integrato.

## <a name="additional-resources"></a>Risorse aggiuntive

- [Supporto per le chiamate parametrizzate delle origini dati ER di tipo Campo calcolato](er-calculated-field-type.md)
- [Tenere traccia dell'esecuzione dei formati di creazione di report elettronici per risolvere i problemi di prestazioni](trace-execution-er-troubleshoot-perf.md)
- [Utilizzare le origini dati RACCOLTA DATI nei formati per la creazione di report elettronici](er-data-collection-data-sources.md)
- [Funzione ER ValueInLarge](er-functions-logical-valueinlarge.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
