---
title: Ispezionare il componente ER configurato per evitare problemi di runtime
description: Questo argomento spiega come ispezionare i componenti di creazione di report elettronici (ER) configurati per prevenire problemi di runtime che potrebbero verificarsi.
author: NickSelin
manager: AnnBe
ms.date: 03/04/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, ERDataModelDesigner, ERModelMappingTable, ERModelMappingDesigner, EROperationDesigner
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 86db6dc27a8a76e90494e3dc7a7cc9c828f9ec37
ms.sourcegitcommit: a3052f76ad71894dbef66566c07c6e2c31505870
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/10/2021
ms.locfileid: "5574127"
---
# <a name="inspect-the-configured-er-component-to-prevent-runtime-issues"></a>Ispezionare il componente ER configurato per evitare problemi di runtime

[!include[banner](../includes/banner.md)]

Ogni formato [Reporting elettronico (ER)](general-electronic-reporting.md) [configurato](general-electronic-reporting.md#FormatComponentOutbound) e [componente del mapping del modello](general-electronic-reporting.md#data-model-and-model-mapping-components) può essere [convalidato](er-fillable-excel.md#validate-an-er-format) in fase di progettazione. Durante questa convalida, viene eseguito un controllo di coerenza per aiutare a prevenire problemi di runtime che potrebbero verificarsi, come errori di esecuzione e riduzione delle prestazioni. Per ogni problema riscontrato, il controllo fornisce il percorso di un elemento problematico. Per alcuni problemi è disponibile una correzione automatica.

Per impostazione predefinita, la convalida viene applicata automaticamente nei seguenti casi per una configurazione ER che contiene i componenti ER precedentemente menzionati:

- [Importare](general-electronic-reporting.md#importing-an-er-component-from-lcs-to-use-it-internally) una nuova [versione](general-electronic-reporting.md#component-versioning) di una configurazione ER nell'istanza di Microsoft Dynamics 365 Finance.
- Modificare lo [stato](general-electronic-reporting.md#component-versioning) della configurazione modificabile e personalizzata da **Bozza** a **Completato**.
- [Risolvere](general-electronic-reporting.md#upgrading-a-format-selecting-a-new-version-of-base-format-rebase) una configurazione ER modificabile applicando una nuova versione di base.

È possibile eseguire esplicitamente questa convalida. Selezionare una delle tre opzioni seguenti e seguire i passaggi forniti:

- Opzione 1:

    1. Andare a **Amministrazione organizzazione\> Creazione di report elettronici \> Configurazioni**.
    2. Nella struttura ad albero delle configurazioni nel riquadro di sinistra, selezionare la configurazione ER desiderata che contiene il formato ER o il componente di mapping del modello ER.
    3. Nella scheda dettaglio **Versioni** selezionare la versione desiderata della configurazione ER.
    4. Nel riquadro azioni seleziona **Convalida**.

- Opzione 2, per un formato ER:

    1. Andare a **Amministrazione organizzazione\> Creazione di report elettronici \> Configurazioni**.
    2. Nella struttura ad albero delle configurazioni nel riquadro di sinistra, selezionare la configurazione ER desiderata che contiene il componente del formato ER.
    3. Nella scheda dettaglio **Versioni** selezionare la versione desiderata della configurazione ER.
    4. Nel riquadro azioni selezionare **Progettazione**.
    5. Nella pagina **Progettazione formati**, nel riquadro azioni, selezionare **Convalidare**.

- Opzione 3, per un mapping del modello ER:

    1. Andare a **Amministrazione organizzazione\> Creazione di report elettronici \> Configurazioni**.
    2. Nella struttura ad albero delle configurazioni nel riquadro di sinistra, selezionare la configurazione ER desiderata che contiene il componente di mapping del modello ER.
    3. Nella scheda dettaglio **Versioni** selezionare la versione desiderata della configurazione ER.
    4. Nel riquadro azioni selezionare **Progettazione**.
    5. Selezionare **Progettazione** nel riquadro azioni della pagina **Modello per mapping origine dati**.
    6. Selezionare **Convalida** nel riquadro azioni della pagina **Progettazione mapping modello**.

Per saltare la convalida quando la configurazione viene importata, attenersi alla seguente procedura.

1. Andare a **Amministrazione organizzazione\> Creazione di report elettronici \> Configurazioni**.
2. Nella pagina **Configurazioni**, nel Riquadro azioni, nella scheda **Configurazioni**, nel gruppo **Impostazioni avanzate**, selezionare **Parametri utente**.
3. Impostare l'opzione **Convalida la configurazione dopo l'importazione** su **No**.

Per saltare la convalida quando lo stato della versione viene modificato o riassegnato, seguire i seguenti passaggi.

1. Andare a **Amministrazione organizzazione\> Creazione di report elettronici \> Configurazioni**.
2. Nella pagina **Configurazioni**, nel Riquadro azioni, nella scheda **Configurazioni**, nel gruppo **Impostazioni avanzate**, selezionare **Parametri utente**.
3. Impostare l'opzione **Ignora convalida alla riassegnazione e alla modifica dello stato della configurazione** su **Sì**.

ER utilizza le seguenti categorie per raggruppare le ispezioni di controllo della coerenza:

- **Eseguibilità** - Ispezioni che rilevano problemi critici che potrebbero verificarsi in fase di esecuzione. Questi problemi sono per lo più in un livello **Errore**. 
- **Prestazione** - Ispezioni che rilevano problemi che potrebbero causare un'esecuzione inefficiente dei componenti ER configurati. Questi problemi sono per lo più a un livello **Avviso**.
- **Integrità dei dati** - Ispezioni che rilevano problemi che potrebbero causare perdita di dati o problemi di runtime. Questi problemi sono per lo più a un livello **Avviso**.

## <a name="list-of-inspections"></a>Elenco delle ispezioni

Nella seguente tabella viene fornita una panoramica delle ispezioni che ER offre. Per ulteriori informazioni su queste ispezioni, utilizzare i collegamenti nella prima colonna per accedere alle sezioni pertinenti di questo argomento. Queste sezioni spiegano i tipi di componenti per i quali ER fornisce ispezioni e come è possibile riconfigurare i componenti ER per aiutare a prevenire problemi.

<table>
<thead>
<tr>
<th>Nome</th>
<th>Categoria</th>
<th>Livello</th>
<th>Messaggio</th>
</tr>
</thead>
<tbody>
<tr>
<td><a href='#i1'>Conversione di tipo</a></td>
<td>Eseguibilità</td>
<td>Errore</td>
<td>
<p>Impossibile convertire l'espressione di tipo &lt;genere&gt; al campo di tipo &lt;genere&gt;.</p>
<p><b>Errore di runtime:</b> Eccezione di tipo</p>
</td>
</tr>
<tr>
<td><a href='#i2'>Compatibilità di genere</a></td>
<td>Eseguibilità</td>
<td>Errore</td>
<td>
<p>L'espressione configurata non può essere utilizzata come associazione dell'elemento di formato corrente a un'origine dati poiché questa espressione restituisce il valore del tipo di dati &lt;genere&gt; che va oltre l'ambito dei tipi di dati supportati dall'elemento di formato corrente di tipo &lt;genere&gt;.</p>
<p><b>Errore di runtime:</b> Eccezione di tipo</p>
</td>
</tr>
<tr>
<td><a href='#i3'>Elemento di configurazione mancante</a></td>
<td>Eseguibilità</td>
<td>Errore</td>
<td>
<p>Percorso non trovato &lt;percorso&gt;.</p>
<p><b>Errore di runtime:</b> Elemento della configurazione &lt;percorso&gt; non trovato</p>
</td>
</tr>
<tr>
<td><a href='#i4'>Eseguibilità di un'espressione con la funzione FILTER</a></td>
<td>Eseguibilità</td>
<td>Errore</td>
<td>
<p>L'espressione elenco della funzione di FILTRO non è disponibile per query.</p>
<p><b>Errore di runtime:</b> il filtro non è supportato. Convalidare la configurazione per ottenere maggiori dettagli su questo.</p>
</td>
</tr>
<tr>
<td rowspan='2'><a href='#i5'>Eseguibilità di un'origine dati GROUPBY</a></td>
<td>Eseguibilità</td>
<td>Errore</td>
<td>Percorso &lt;percorso&gt; non supporta le query.</td>
</tr>
<tr>
<td>Eseguibilità</td>
<td>Errore</td>
<td>
<p>Raggruppa per funzione non può essere eseguito con la query.</p>
<p><b>Errore di runtime:</b> Raggruppa per funzione non può essere eseguito con la query.</p>
</td>
</tr>
<tr>
<td><a href='#i6'>Eseguibilità di un'origine dati JOIN</a></td>
<td>Eseguibilità</td>
<td>Errore</td>
<td>
<p>Non è possibile entrare in un elenco &lt;percorso&gt; che non è un filtro nella query.</p>
<p><b>Errore di runtime:</b> l'origine dati unita alla funzione deve essere un'espressione di filtro che il campo calcolato è stato chiamato in modo errato.</p>
</td>
</tr>
<tr>
<td><a href='#i7'>Preferibilità della funzione FILTER rispetto a WHERE</a></td>
<td>Prestazioni</td>
<td>Avviso</td>
<td>L'uso della funzione FILTER per l'espressione è preferibile rispetto a WHERE dal punto di vista delle prestazioni. Selezionare Correggi per sostituirlo automaticamente.</td>
</tr>
<tr>
<td><a href='#i8'>Preferibilità della funzione ALLITEMSQUERY rispetto a ALLITEMS</a></td>
<td>Prestazioni</td>
<td>Avviso</td>
<td>L'uso della funzione ALLITEMSQUERY per l'espressione è preferibile rispetto a ALLITEMS dal punto di vista delle prestazioni. Selezionare Correggi per sostituirlo automaticamente.</td>
</tr>
<tr>
<td><a href='#i9'>Considerazione di casi di elenchi vuoti</a></td>
<td>Eseguibilità</td>
<td>Avviso</td>
<td>
<p>L'elenco &lt;percorso&gt; non ha alcun controllo per casi di elenco vuoto, ciò può causare un errore in fase di esecuzione. Aggiungere un segno di spunta per un caso elenco vuoto.</p>
<p><b>Errore di runtime:</b> l'elenco è vuoto in &lt;percorso&gt;</p>
<p><b><a href='#i9a'>Potenziale problema</a> :</b> la riga viene popolata una volta mentre un'origine dati da cui viene popolata contiene più record</p>
</td>
</tr>
<tr>
<td><a href='#i10'>Eseguibilità di un'espressione con la funzione FILTER (memorizzazione nella cache)</a></td>
<td>Eseguibilità</td>
<td>Errore</td>
<td>
<p>La funzione FILTER non può essere applicata al tipo selezionato di origine dati. Un'origine dati del genere Record di tabella è applicabile solo quando non è memorizzata nella cache e non dispone di origini dati nidificate aggiunte manualmente.</p>
<p><b>Errore di runtime:</b> il filtro non è supportato. Convalidare la configurazione per ottenere maggiori dettagli su questo.</p>
</td>
</tr>
<tr>
<td><a href='#i11'>Associazione mancante</a></td>
<td>Eseguibilità</td>
<td>Avviso</td>
<td>
<p>Percorso &lt;percorso&gt; non ha alcun legame con alcuna origine dati nell'utilizzo del mapping del modello.</p>
<p><b>Errore di runtime:</b> persorso &lt;percorso&gt; non è vincolato</p>
</td>
</tr>
<tr>
<td><a href='#i12'>Modello non collegato</a></td>
<td>Integrità dei dati</td>
<td>Avviso</td>
<td>Il &lt;nome&gt; del file non è collegato a nessun componente del file e verrà rimosso dopo aver modificato lo stato della versione di configurazione.</td>
</tr>
<tr>
<td><a href='#i13'>Formato non sincronizzato</a></td>
<td>Integrità dei dati</td>
<td>Avviso</td>
<td>Nome definito &lt;il nome del componente&gt; non esiste nel foglio Excel &lt;nome del foglio&gt;</td>
</tr>
<tr>
<td><a href='#i14'>Formato non sincronizzato</a></td>
<td>Integrità dei dati</td>
<td>Avviso</td>
<td>
<p>Il tag &lt;Controllo del contenuto di Word con tag&gt; non esiste nel file di modello di Word</p>
<p><b>Errore di runtime:</b> il tag &lt;Controllo del contenuto di Word con tag&gt; non esiste nel file di modello di Word.</p>
</td>
</tr>
<tr>
<td><a href='#i15'>Nessun mapping predefinito</a></td>
<td>Integrità dei dati</td>
<td>Errore</td>
<td>
<p>Esiste più di un mapping del modello per il modello di dati &lt;nome di modello (descrittore radice)&gt; nelle configurazioni &lt;nomi di configurazioni separati con virgole&gt;. Impostare una delle configurazioni come predefinita</p>
<p><b>Errore di runtime:</b> Esiste più di un mapping dei modelli per il modello di dati &lt;nome di modello (descrittore radice)&gt; nelle configurazioni &lt;nomi di configurazioni separati con virgole&gt;. Imposta una delle configurazioni come predefinita.</p>
</td>
</tr>
<tr>
<td><a href='#i16'>Impostazione incoerente dei componenti di intestazione o piè di pagina</a></td>
<td>Integrità dei dati</td>
<td>Errore</td>
<td>
<p>Le intestazioni/piè di pagina (&lt;tipo di componente: intestazione o piè di pagina&gt;) sono incoerenti</p>
<p><b>Runtime:</b> l'ultimo componente configurato viene utilizzato in fase di runtime se viene eseguita la versione bozza del formato ER configurato.</p>
</td>
</tr>
</tbody>
</table>

## <a name="type-conversion"></a><a id="i1"></a>Conversione di tipo

ER controlla se il tipo di dati di un campo del modello di dati è compatibile con il tipo di dati di un'espressione configurata come associazione di quel campo. Se i tipi di dati non sono compatibili, si verifica un errore di convalida nel designer di mapping del modello ER. Il messaggio che ricevi indica che ER non può convertire un'espressione di tipo A in un campo di tipo B.

I passaggi seguenti mostrano come potrebbe verificarsi questo problema.

1. Iniziare a configurare il modello di dati ER e i componenti di mapping del modello ER contemporaneamente.
2. Nell'albero del modello di dati, aggiungere un campo denominato **X** e selezionare **Numero intero** come tipo di dati.

    ![Campo X e tipo di dati Numero intero aggiunti all'albero della modalità dati nella pagina Modello dati](./media/er-components-inspections-01.png)

3. Nel riquadro **Origine dati** del mapping del modello, aggiungere un'origine dati di tipo **Campo calcolato**.
4. Assegnare un nome alla nuova origine dati **Y** e configurarlo in modo che contenga l'espressione `INTVALUE(100)`.
5. Associare **X** a **Y**.
6. Nella finestra di progettazione del modello di dati, modificare il tipo di dati del campo **X** da **Numero intero** a **Int64**.
7. Selezionare **Convalida** per ispezionare il componente di mapping del modello modificabile nella pagina **Designer del mapping del modello**.

    ![Convalida del componente di mapping del modello modificabile nella pagina Progettazione mapping modello](./media/er-components-inspections-01.gif)

8. Selezionare **Convalida** per ispezionare il componente di mapping del modello della configurazione ER selezionata nella pagina **Configurazioni**.

    ![Verificare il componente di mapping del modello nella pagina Configurazioni](./media/er-components-inspections-01a.png)

9. Notare che si verifica un errore di convalida. Il messaggio afferma che il valore del tipo **Numero intero** che l'origine dati dell'`INTVALUE(100)`espressione di **Y** restituisce non può essere archiviato nel campo del modello di dati **X** del tipo **Int64**.

La figura seguente mostra l'errore di runtime che si verifica se si ignora l'avviso e si seleziona **Esegui** per eseguire un formato configurato per utilizzare il mapping del modello.

![Errori di runtime nella pagina Progettazione formati](./media/er-components-inspections-01b.png)

### <a name="automatic-resolution"></a>Risoluzione automatica

Non è disponibile alcuna opzione per risolvere automaticamente questo problema.

### <a name="manual-resolution"></a>Risoluzione manuale

#### <a name="option-1"></a>Opzione 1

Aggiornare la struttura del modello dati modificando il tipo di dati del campo del modello dati in modo che corrisponda al tipo di dati dell'espressione configurata per l'associazione di quel campo. Nell'esempio precedente, il tipo di dati del campo **X** deve essere modificato di nuovo in **Numero intero**.

#### <a name="option-2"></a>Opzione 2

Aggiornare il mapping del modello modificando l'espressione dell'origine dati associata al campo del modello di dati. Nell'esempio precedente, l'espressione dell'origine dati **Y** deve essere modificata in `INT64VALUE(100)`.

## <a name="type-compatibility"></a><a id="i2"></a>Compatibilità di genere

ER controlla se il tipo di dati di un elemento di formato è compatibile con il tipo di dati di un'espressione configurata come associazione dell'elemento di formato. Se i tipi di dati non sono compatibili, si verifica un errore di convalida nella progettazione delle operazioni ER. Il messaggio che si riceve afferma che l'espressione configurata non può essere utilizzata come associazione dell'elemento di formato corrente a un'origine dati poiché questa espressione restituisce un valore del tipo di dati A che va oltre l'ambito dei tipi di dati supportati dall'elemento di formato corrente di tipo B.

I passaggi seguenti mostrano come potrebbe verificarsi questo problema.

1. Iniziare a configurare il modello di dati ER e i componenti di formato ER contemporaneamente.
2. Nell'albero del modello di dati, aggiungere un campo denominato **X** e selezionare **Numero intero** come tipo di dati.
3. Nell'albero della struttura del formato, aggiungere un elemento di formato del tipo **Numerico**.
4. Assegnare un nome al nuovo elemento di formato **Y**. Nel campo **Tipo numerico**, selezionare **Numero intero** come tipo di dati.
5. Associare **X** a **Y**.
6. Nell'albero della struttura del formato, modificare il tipo di dati dell'elemento di formato **Y** da **Numero intero** a **Int64**.
7. Selezionare **Convalida** per ispezionare il componente formato modificabile nella pagina **Progettazione formati**.

    ![Convalida della compatibilità del tipo nella pagina Progettazione formato](./media/er-components-inspections-02.gif)

8. Notare che si verifica un errore di convalida. Il messaggio indica che l'espressione configurata può solo accettare i valori **Int64**. Pertanto, il valore del campo del modello di dati **X** del genere **Numero intero** non può essere inserito nell'elemento di formato **Y**.

### <a name="automatic-resolution"></a>Risoluzione automatica

Non è disponibile alcuna opzione per risolvere automaticamente questo problema.

### <a name="manual-resolution"></a>Risoluzione manuale

#### <a name="option-1"></a>Opzione 1

Aggiornare la struttura del formato modificando il tipo di dati dell'elemento di formato **Numerico** in modo che corrisponda al tipo di dati dell'espressione configurata per l'associazione di quell'elemento. Nell'esempio precedente, il valore di **tipo Numerico** dell'elemento di formato **X** deve essere modificato di nuovo in **Intero**.

#### <a name="option-2"></a>Opzione 2

Aggiornare il mapping di formato dell'elemento di formato **X** modificando l'espressione da `model.X` a `INT64VALUE(model.X)`.

## <a name="missing-configuration-element"></a><a id="i3"></a>Elemento di configurazione mancante

ER controlla se le espressioni di associazione contengono solo origini dati configurate nel componente ER modificabile. Per ogni associazione che contiene un'origine dati mancante nel componente ER modificabile, si verifica un errore di convalida nella progettazione delle operazioni ER o nella progettazione mapping modello di ER.

I passaggi seguenti mostrano come potrebbe verificarsi questo problema.

1. Iniziare a configurare il modello di dati ER e i componenti di mapping del modello ER contemporaneamente.
2. Nell'albero del modello di dati, aggiungere un campo denominato **X** e selezionare **Numero intero** come tipo di dati.

    ![L'albero del modello di dati con campo X e tipo di dati Numero intero nella pagina Modello dati](./media/er-components-inspections-01.png)

3. Nel riquadro **Origine dati** del mapping del modello, aggiungere un'origine dati di tipo **Campo calcolato**.
4. Assegnare un nome alla nuova origine dati **Y** e configurarlo in modo che contenga l'espressione `INTVALUE(100)`.
5. Associare **X** a **Y**.
6. Nella progettazione mapping modello, nel riquadro **Origini dati**, eliminare l'origine dati **Y**.
7. Selezionare **Convalida** per ispezionare il componente di mapping del modello modificabile nella pagina **Designer del mapping del modello**.

    ![Verificare il componente di mapping del modello ER modificabile nella pagina Progettazione mapping modello](./media/er-components-inspections-03.gif)

8. Notare che si verifica un errore di convalida. Il messaggio afferma che l'associazione del campo del modello di dati **X** contiene il percorso che fa riferimento all'origine dati **Y**, ma questa origine dati non è stata trovata.

### <a name="automatic-resolution"></a>Risoluzione automatica

Selezionare **Separa** per risolvere automaticamente questo problema rimuovendo l'associazione dell'origine dati mancante.

### <a name="manual-resolution"></a>Risoluzione manuale

#### <a name="option-1"></a>Opzione 1

Separare il campo del modello di dati **X** per interrompere il riferimento all'origine dati **Y** inesistente.

#### <a name="option-2"></a>Opzione 2

Nel riquadro **Origini dati** della progettazione mapping modello, aggiungere nuovamente l'origine dati **Y**.

## <a name="executability-of-an-expression-with-filter-function"></a><a id="i4"></a>Eseguibilità di un'espressione con la funzione FILTER

La funzione ER [FILTER](er-functions-list-filter.md) incorporata viene utilizzata per accedere a tabelle, viste o entità di dati dell'applicazione inserendo una singola chiamata SQL per ottenere i dati richiesti come elenco di record. Un'origine dati del tipo **Elenco di record** viene utilizzata come argomento di questa funzione e specifica l'origine della domanda di lavoro per la chiamata. ER verifica se è possibile stabilire una query SQL diretta su un'origine dati a cui si fa riferimento nella funzione `FILTER`. Se non è possibile stabilire una query diretta, si verifica un errore di convalida nella finestra di progettazione del mapping del modello ER. Il messaggio ricevuto indica che l'espressione ER che include la funzione `FILTER` non può essere eseguita in fase di esecuzione.

I passaggi seguenti mostrano come potrebbe verificarsi questo problema.

1. Iniziare a configurare il componente di mapping del modello ER.
2. Aggiungere un'origine dati di tipo **Dynamics 365 for Operations \\ Record di tabella**.
3. Assegnare un nome alla nuova origine dati **Fornitore**. Nel campo **Tabella**, selezionare **VendTable** per specificare che questa origine dati richiederà la tabella VendTable.
4. Aggiungere un'origine dati del tipo **Campo calcolato**.
5. Assegnare un nome alla nuova origine dati **FornitoreFiltrato** e configurarla in modo che contenga l'espressione `FILTER(Vendor, Vendor.AccountNum="US-101")`.
6. Selezionare **Convalida** per ispezionare il componente di mapping del modello modificabile nella pagina **Progettazione mapping modello** e verificare che l'espressione `FILTER(Vendor, Vendor.AccountNum="US-101")` nell'origine dati **Fornitore** possa essere interrogata.
7. Modificare l'origine dati **Fornitore** aggiungendo un campo nidificato del tipo **Campo calcolato** per ottenere il numero di conto del fornitore ridotto.
8. Assegnare un nome al nuovo campo nidificato **$AccNumber** e configurarlo in modo che contenga l'espressione `TRIM(Vendor.AccountNum)`.
9. Selezionare **Convalida** per ispezionare il componente di mapping del modello modificabile nella pagina **Progettazione mapping modello** e verificare che l'espressione `FILTER(Vendor, Vendor.AccountNum="US-101")` nell'origine dati **Fornitore** possa essere interrogata.

    ![Verificare la possibilità di eseguire una query sull'espressione nella pagina Progettazione mapping modello](./media/er-components-inspections-04.gif)

10. Si noti che si verifica un errore di convalida, perché l'origine dati **Fornitore** contiene un campo nidificato del tipo **Campo calcolato** che non consente l'espressione dell'origine dati **FornitoreFiltrato** da tradurre nell'istruzione SQL diretta.

La figura seguente mostra l'errore di runtime che si verifica se si ignora l'avviso e si seleziona **Esegui** per eseguire un formato configurato per utilizzare il mapping del modello.

![Errori di runtime che si verificano quando si esegue il formato modificabile nella pagina Progettazione formati](./media/er-components-inspections-04a.png)

### <a name="automatic-resolution"></a>Risoluzione automatica

Non è disponibile alcuna opzione per risolvere automaticamente questo problema.

### <a name="manual-resolution"></a>Risoluzione manuale

#### <a name="option-1"></a>Opzione 1

Invece di aggiungere un campo nidificato del tipo **Campo calcolato** all'origine dati **Fornitore**, aggiungere il campo nidificato **$AccNumber** all'origine dati **FornitoreFiltrato** e configurarla in modo che contenga l'espressione `TRIM(FilteredVendor.AccountNum)`. In questo modo, l'espressione `FILTER(Vendor, Vendor.AccountNum="US-101")` può essere eseguita a livello SQL e calcolare il campo nidificato **$AccNumber** in seguito.

#### <a name="option-2"></a>Opzione 2

Cambiare l'espressione dell'origine dati **FornitoreFiltrato** da `FILTER(Vendor, Vendor.AccountNum="US-101")` a `WHERE(Vendor, Vendor.AccountNum="US-101")`. Non è consigliabile modificare l'espressione per una tabella che ha un grande volume di dati (tabella transazionale), perché tutti i record verranno recuperati e la selezione dei record richiesti verrà eseguita in memoria. Pertanto, questo approccio può causare prestazioni ridotte. Per ulteriori informazioni, vedere [Funzione ER WHERE](er-functions-list-where.md).

## <a name="executability-of-a-groupby-data-source"></a><a id="i5"></a>Eseguibilità di un'origine dati GROUPBY

L'origine dati **GROUPBY** divide il risultato della query in gruppi di record, in genere allo scopo di eseguire una o più aggregazioni su ciascun gruppo. Ogni origine dati **GROUPBY** può essere configurata in modo che venga eseguita a livello di database o in memoria. Quando un'origine dati **GROUPBY** è configurata in modo da essere eseguita a livello di database, ER verifica se è possibile stabilire una query SQL diretta su un'origine dati a cui si fa riferimento in tale origine dati. Se non è possibile stabilire una query diretta, si verifica un errore di convalida nella finestra di progettazione del mapping del modello ER. Il messaggio che si riceve indica che l'origine dati configurata **GROUPBY** non può essere eseguita in fase di esecuzione.

I passaggi seguenti mostrano come potrebbe verificarsi questo problema.

1. Iniziare a configurare il componente di mapping del modello ER.
2. Aggiungere un'origine dati del tipo **Dynamics 365 for Operations \\ Record di tabella**.
3. Assegnare un nome alla nuova origine dati **Trans**. Nel campo **Tabella**, selezionare **VendTrans** per specificare che questa origine dati richiederà la tabella VendTrans.
4. Aggiungere un'origine dati del tipo **Raggruppa per**.
5. Assegnare un nome alla nuova origine dati **GroupedTrans** e configurarla nel modo seguente:

    - Selezionare l'origine dati **Trans** come origine dei record che dovrebbero essere raggruppati.
    - Nel campo **Ubicazione dell'esecuzione**, selezionare **Query** per specificare che si desidera eseguire questa origine dati a livello di database.

    ![Configurazione dell'origine dati nella pagina dei parametri Modifica "Raggruppa per"](./media/er-components-inspections-05a.gif)

6. Selezionare **Convalida** per ispezionare il componente di mapping del modello modificabile nella pagina **Progettazione mapping modello** e verificare che l'origine dati configurata **GroupedTrans** possa essere interrogata.
7. Modificare l'origine dati **Trans** aggiungendo un campo nidificato del tipo **Campo calcolato** per ottenere il numero di conto del fornitore ridotto.
8. Assegnare un nome alla nuova origine dati **$AccNumber** e configurarla in modo che contenga l'espressione `TRIM(Trans.AccountNum)`.

    ![Configurazione dell'origine dati transazioni nella pagina di progettazione del mapping del modello](./media/er-components-inspections-05a.png)

9. Selezionare **Convalida** per ispezionare il componente di mapping del modello modificabile nella pagina **Progettazione mapping modello** e verificare che l'origine dati configurata **GroupedTrans** possa essere interrogata.

    ![Convalidare il componente di mapping del modello ER e verificare che sia possibile eseguire una query sull'origine dati GroupedTrans nella pagina Progettazione mapping modello](./media/er-components-inspections-05b.png)

10. Si noti che si verifica un errore di convalida, perché l'origine dati **Trans** contiene un campo nidificato del tipo **Campo calcolato** che non consente la chiamata per l'origine dati **GroupedTrans** da tradurre nell'istruzione SQL diretta.

La figura seguente mostra l'errore di runtime che si verifica se si ignora l'avviso e si seleziona **Esegui** per eseguire un formato configurato per utilizzare il mapping del modello.

![Errori di runtime che si verificano se si ignora l'avviso nella pagina Progettazione formati](./media/er-components-inspections-05c.png)

### <a name="automatic-resolution"></a>Risoluzione automatica

Non è disponibile alcuna opzione per risolvere automaticamente questo problema.

### <a name="manual-resolution"></a>Risoluzione manuale

#### <a name="option-1"></a>Opzione 1

Invece di aggiungere un campo nidificato del tipo **Campo calcolato** all'origine dati **Trans**, aggiungere il campo nidificato **$AccNumber** per l'elemento **GroupedTrans.lines** dell'origine dati **GroupedTrans** e configurarla in modo che contenga l'espressione `TRIM(GroupedTrans.lines.AccountNum)`. In questo modo, l'origine dati **GroupedTrans** può essere eseguita a livello SQL e calcolare il campo nidificato **$AccNumber** in seguito.

#### <a name="option-2"></a>Opzione 2

Modificare il valore del campo **Ubicazione di esecuzione** per l'origine dati **GroupedTrans** da **Query** a **In memoria**. Non è consigliabile modificare il valore per una tabella che ha un grande volume di dati (tabella transazionale), perché tutti i record verranno recuperati e il raggruppamento e l'aggregazione verranno eseguiti in memoria. Pertanto, questo approccio può causare prestazioni ridotte.

## <a name="executability-of-a-join-data-source"></a><a id="i6"></a>Eseguibilità di un'origine dati JOIN

L'origine dati [JOIN](er-join-data-sources.md) combina i record di due o più tabelle di database, in base ai campi correlati. Ogni origine dati **JOIN** può essere configurata in modo che venga eseguita a livello di database o in memoria. Quando un'origine dati **JOIN** è configurata in modo da essere eseguita a livello di database, ER verifica se è possibile stabilire una query SQL diretta su origini dati a cui si fa riferimento in tale origine dati. Se non è possibile stabilire una query SQL diretta con almento un'origine dati a cui si fa riferimento, si verifica un errore di convalida nella finestra di progettazione del mapping del modello ER. Il messaggio che si riceve indica che l'origine dati configurata **JOIN** non può essere eseguita in fase di esecuzione.

I passaggi seguenti mostrano come potrebbe verificarsi questo problema.

1. Iniziare a configurare il componente di mapping del modello ER.
2. Aggiungere un'origine dati del tipo **Dynamics 365 for Operations \\ Record di tabella**.
3. Assegnare un nome alla nuova origine dati **Fornitore**. Nel campo **Tabella**, selezionare **VendTable** per specificare che questa origine dati richiederà la tabella VendTable.
4. Aggiungere un'origine dati del tipo **Dynamics 365 for Operations \\ Record di tabella**.
5. Assegnare un nome alla nuova origine dati **Trans**. Nel campo **Tabella**, selezionare **VendTrans** per specificare che questa origine dati richiederà la tabella VendTrans.
6. Aggiungere un'origine dati del tipo **Campo calcolato** come campo nidificato dell'origine dati **Fornitore**.
7. Assegnare un nome alla nuova origine dati **FilteredTrans** e configurarla in modo che contenga l'espressione `FILTER(Trans, Trans.AccountNum=Vendor.AccountNum)`.
8. Aggiungere un'origine dati del tipo **Join**.
9. Assegnare un nome alla nuova origine dati **JoinedList** e configurarla nel modo seguente:

    1. Aggiungere l'origine dati **Fornitore** come primo set di record da unire.
    2. Aggiungere l'origine dati **Vendor.FilteredTrans** come secondo set di record da unire. Selezionare **INNER** come tipo.
    3. Nel campo **Esegui**, selezionare **Query** per specificare che si desidera eseguire questa origine dati a livello di database.

    ![Configurazione dell'origine dati nella pagina di progettazione Join](./media/er-components-inspections-06a.gif)

10. Selezionare **Convalida** per ispezionare il componente di mapping del modello modificabile nella pagina **Progettazione mapping modello** e verificare che l'origine dati configurata **JoinedList** possa essere interrogata.
11. Cambiare l'espressione dell'origine dati **Vendor.FilteredTrans** da `FILTER(Trans, Trans.AccountNum=Vendor.AccountNum)` a `WHERE(Trans, Trans.AccountNum=Vendor.AccountNum)`.
12. Selezionare **Convalida** per ispezionare il componente di mapping del modello modificabile nella pagina **Progettazione mapping modello** e verificare che l'origine dati configurata **JoinedList** possa essere interrogata.

    ![Convalidare il componente del mapping del modello modificabile e verificare che sia possibile eseguire una query sull'origine dati JoinedList nella pagina Progettazione mapping modello](./media/er-components-inspections-06b.png)

13. Si noti che si verifica un errore di convalida, poiché l'espressione dell'origine dati **Vendor.FilteredTrans** non può essere tradotta nella chiamata SQL diretta. Inoltre, la chiamata SQL diretta non consente la chiamata per l'origine dati **JoinedList** da tradurre nell'istruzione SQL diretta.

    ![Errori di runtime dovuti alla convalida non riuscita dell'origine dati JoinedList nella pagina Progettazione mapping modello](./media/er-components-inspections-06c.png)

La figura seguente mostra l'errore di runtime che si verifica se si ignora l'avviso e si seleziona **Esegui** per eseguire un formato configurato per utilizzare il mapping del modello.

![Eseguire il formato modificabile nella pagina Progettazione formati](./media/er-components-inspections-06e.png)

### <a name="automatic-resolution"></a>Risoluzione automatica

Non è disponibile alcuna opzione per risolvere automaticamente questo problema.

### <a name="manual-resolution"></a>Risoluzione manuale

#### <a name="option-1"></a>Opzione 1

Cambiare l'espressione dell'origine dati **Vendor.FilteredTrans** da `WHERE(Trans, Trans.AccountNum=Vendor.AccountNum)` indietro a `FILTER(Trans, Trans.AccountNum=Vendor.AccountNum)`, come consigliato dall'avviso.

![Espressione aggiornata dell'origine dati nella pagina di progettazione del mapping del modello](./media/er-components-inspections-06d.png)

#### <a name="option-2"></a>Opzione 2

Modificare il valore del campo **Esegui** per l'origine dati **JoinedList** da **Query** a **In memoria**. Non è consigliabile modificare il valore per una tabella che ha un grande volume di dati (tabella transazionale), perché tutti i record verranno recuperati e il join verrà eseguito in memoria. Pertanto, questo approccio può causare prestazioni ridotte. Viene visualizzato un avviso di convalida per informarti di questo rischio.

## <a name="preferability-of-filter-vs-where-function"></a><a id="i7"></a>Preferibilità della funzione FILTER rispetto a WHERE

La funzione ER [FILTER](er-functions-list-filter.md) incorporata viene utilizzata per accedere a tabelle, viste o entità di dati dell'applicazione inserendo una singola chiamata SQL per ottenere i dati richiesti come elenco di record. La funzione [WHERE](er-functions-list-where.md) preleva tutti i record dall'origine data ed esegue la selezione dei record in memoria. Un'origine dati del tipo **Elenco di record** viene utilizzato come argomento di entrambe le funzioni e specifica un'origine per ottenere i record. ER verifica se è possibile stabilire una chiamata SQL diretta su un'origine dati a cui si fa riferimento nella funzione **WHERE**. Se non è possibile stabilire una chiamata diretta, compare un avviso di convalida nella finestra di progettazione del mapping del modello ER. Il messaggio ricevuto consiglia di utilizzare la funzione **FILTER** invece della funzione **WHERE** per contribuire a migliorare l'efficienza.

I passaggi seguenti mostrano come potrebbe verificarsi questo problema.

1. Iniziare a configurare il componente di mapping del modello ER.
2. Aggiungere un'origine dati del tipo **Dynamics 365 for Operations \\ Record di tabella**.
3. Assegnare un nome alla nuova origine dati **Trans**. Nel campo **Tabella**, selezionare **VendTrans** per specificare che questa origine dati richiederà la tabella VendTrans.
4. Aggiungere un'origine dati del tipo **Campo calcolato** come campo nidificato dell'origine dati **Fornitore**.
5. Assegnare un nome alla nuova origine dati **FilteredTrans** e configurarla in modo che contenga l'espressione `WHERE(Trans, Trans.AccountNum="US-101")`.
6. Aggiungere un'origine dati del tipo **Dynamics 365 for Operations \\ Record di tabella**.
7. Assegnare un nome alla nuova origine dati **Fornitore**. Nel campo **Tabella**, selezionare **VendTable** per specificare che questa origine dati richiederà la tabella VendTable.
8. Aggiungere un'origine dati del tipo **Campo calcolato**.
9. Assegnare un nome alla nuova origine dati **FornitoreFiltrato** e configurarla in modo che contenga l'espressione `WHERE(Vendor, Vendor.AccountNum="US-101")`.
10. Selezionare **Convalida** per ispezionare il componente di mapping del modello modificabile nella pagina **Designer del mapping del modello**.

    ![Verificare il componente di mapping del modello modificabile nella pagina Progettazione mapping modello](./media/er-components-inspections-07a.png)

11. Si noti che gli avvisi di convalida consigliano di utilizzare la funzione **FILTER** invece della funzione **WHERE** per le origini dati **FilteredVendor** e **FilteredTrans**.

    ![Raccomandazione di utilizzare la funzione FILTER anziché la funzione WHERE nella pagina Progettazione mapping modello](./media/er-components-inspections-07b.png)

### <a name="automatic-resolution"></a>Risoluzione automatica

Selezionare **Correggi** per sostituire automaticamente la funzione **WHERE** con la funzione **FILTER** nell'espressione di tutte le origini dati che appaiono nella griglia nella scheda **Avvisi** per questo tipo di ispezione.

In alternativa, è possibile selezionare la riga per un singolo avviso nella griglia e quindi selezionare **Correzione selezionata**. In questo caso, l'espressione viene modificata automaticamente solo nell'origine dati menzionata nell'avviso selezionato.

![Selezionare Correggi per sostituire automaticamente la funzione WHERE con la funzione FILTER nella pagina Progettazione mapping modello](./media/er-components-inspections-07c.png)

### <a name="manual-resolution"></a>Risoluzione manuale

È possibile regolare manualmente le espressioni di tutte le origini dati nella griglia di convalida sostituendo la funzione **WHERE** con la funzione **FILTER**.

## <a name="preferability-of-allitemsquery-vs-allitems-function"></a><a id="i8"></a>Preferibilità della funzione ALLITEMSQUERY rispetto a ALLITEMS

Le funzioni ER incorporate [ALLITEMS](er-functions-list-allitems.md) e [ALLITEMSQUERY](er-functions-list-allitemsquery.md) vengono utilizzate per ottenere un valore bidimensionale **Elenco di record** che consiste in un elenco di record che rappresentano tutti gli elementi che corrispondono al percorso specificato. ER verifica se è possibile stabilire una chiamata SQL diretta su un'origine dati a cui si fa riferimento nella funzione **ALLITEMS**. Se non è possibile stabilire una chiamata diretta, compare un avviso di convalida nella finestra di progettazione del mapping del modello ER. Il messaggio ricevuto consiglia di utilizzare la funzione **ALLITEMSQUERY** invece della funzione **ALLITEMS** per contribuire a migliorare l'efficienza.

I passaggi seguenti mostrano come potrebbe verificarsi questo problema.

1. Iniziare a configurare il componente di mapping del modello ER.
2. Aggiungere un'origine dati del tipo **Dynamics 365 for Operations \\ Record di tabella**.
3. Assegnare un nome alla nuova origine dati **Fornitore**. Nel campo **Tabella**, selezionare **VendTable** per specificare che questa origine dati richiederà la tabella VendTable.
4. Aggiungere un'origine dati del tipo **Campo calcolato** per ottenere i record di vari fornitori.
5. Assegnare un nome alla nuova origine dati **FornitoreFiltrato** e configurarla in modo che contenga l'espressione `FILTER(Vendor, OR(Vendor.AccountNum="US-101",Vendor.AccountNum="US-102"))`.
6. Aggiungere un'origine dati di tipo **Campo calcolato** per ottenere le transazioni di tutti i fornitori filtrati.
7. Assegnare un nome alla nuova origine dati **FilteredVendorTrans** e configurarla in modo che contenga l'espressione `ALLITEMS(FilteredVendor.'<Relations'.'VendTrans.VendTable_AccountNum')`.
8. Selezionare **Convalida** per ispezionare il componente di mapping del modello modificabile nella pagina **Designer del mapping del modello**.

    ![Verificare il componente di mapping del modello modificabile nella pagina Progettazione mapping modello](./media/er-components-inspections-08a.png)

9. Notare che si verifica un avviso di convalida. Il messaggio consiglia di utilizzare la funzione **ALLITEMSQUERY** invece della funzione **ALLITEMS** per l'origine dati **FilteredVendorTrans**.

    ![Raccomandazione di utilizzare la funzione ALLITEMSQUERY anziché la funzione ALLITEMS nella pagina Progettazione mapping modello](./media/er-components-inspections-08b.png)

### <a name="automatic-resolution"></a>Risoluzione automatica

Selezionare **Correggi** per sostituire automaticamente la funzione **ALLITEMS** con la funzione **ALLITEMSQUERY** nell'espressione di tutte le origini dati che appaiono nella griglia nella scheda **Avvisi** per questo tipo di ispezione.

In alternativa, è possibile selezionare la riga per un singolo avviso nella griglia e quindi selezionare **Correzione selezionata**. In questo caso, l'espressione viene modificata automaticamente solo nell'origine dati menzionata nell'avviso selezionato.

![Selezionare Correggi nella pagina Progettazione mapping modello](./media/er-components-inspections-08c.png)

### <a name="manual-resolution"></a>Risoluzione manuale

È possibile regolare manualmente le espressioni di tutte le origini dati menzionate nella griglia di convalida sostituendo la funzione **ALLITEMS** con la funzione **ALLITEMSQUERY**.

## <a name="consideration-of-empty-list-cases"></a><a id="i9"></a>Considerazione di casi di elenchi vuoti

È possibile configurare il formato ER o il componente di mapping del modello per ottenere il valore del campo di un'origine dati di tipo **Elenco di record**. ER controlla se la progettazione prende in considerazione il caso in cui un'origine dati chiamata non contenga record (ovvero è vuota), per evitare errori di runtime quando un valore viene recuperato da un campo di un record inesistente.

I passaggi seguenti mostrano come potrebbe verificarsi questo problema.

1. Iniziare a configurare il modello di dati ER, il mapping di modello di ER e i componenti di formato ER contemporaneamente.
2. Nell'albero del modello di dati, aggiungere un elemento radice denominato **Root3**.
3. Modificare l'elemento **Root3** aggiungendo un elemento nidificato del tipo **Elenco di record**.
4. Assegnare un nome al nuovo elemento nidificato **Fornitore**.
5. Modificare l'elemento **Fornitore** nel modo seguente:

    - Aggiungere un campo nidificato del tipo **Stringa** e denominarlo **Nome**.
    - Aggiungere un campo nidificato del tipo **Stringa** e denominarlo **AccountNumber**.

    ![Aggiunta di campi nidificati nella pagina Modello dati](./media/er-components-inspections-09a.png)

6. Nel riquadro **Origine dati** del mapping del modello, aggiungere un'origine dati di tipo **Dynamics 365 for Operations \\ Record tabella**.
7. Assegnare un nome alla nuova origine dati **Fornitore**. Nel campo **Tabella**, selezionare **VendTable** per specificare che questa origine dati richiederà la tabella VendTable.
8. Aggiungere un'origine dati del tipo **Parametro di input dell'utente \\ Generale** per cercare un account fornitore nella finestra di dialogo runtime.
9. Assegnare un nome alla nuova origine dati **RequestedAccountNum**. Nel campo **Etichetta** immettere il **numero del conto del fornitore**. Nel campo **Nome del tipo di dati delle operazioni**, lasciare il valore predefinito, **Descrizione**.
10. Aggiungere un'origine dati del tipo **Campo calcolato** per filtrare un fornitore su cui si richiedono informazioni.
11. Assegnare un nome alla nuova origine dati **FornitoreFiltrato** e configurarla in modo che contenga l'espressione `FILTER(Vendor, Vendor.AccountNum=RequestedAccountNum)`.
12. Associare gli elementi del modello di dati alle origini dati configurate nel modo seguente:

    - Associare **FilteredVendor** a **Fornitore**.
    - Associare **FilteredVendor.AccountNum** a **Vendor.AccountNumber**.
    - Associare **FilteredVendor.'name()'** a **Vendor.Name**.

    ![Associazione degli elementi del modello di dati nella pagina di progettazione del mapping del modello](./media/er-components-inspections-09b.png)

13. Nell'albero della struttura del formato, aggiungere i seguenti elementi per generare un documento in uscita in formato XML che contiene i dettagli del fornitore:

    1. Aggiungere l'elemento XML radice **Rendiconto**.
    2. Per l'elemento XML **Rendiconto**, aggiungere l'elemento XML nidificato **Parte**.
    3. Per l'elemento XML **Parte**, aggiungere i seguenti attributi XML nidificati:

        - Nome
        - AccountNum

14. Associare gli elementi di formato alle origini dati fornite nel modo seguente:

    - Associare l'elemento di formato **Rendiconto\\Parte\\Nome** al campo origine dati **model.Vendor.Name**.
    - Associare l'elemento di formato **Rendiconto\\Parte\\AccountNum** al campo origine dati **model.Vendor.AccountNumber**.

15. Selezionare **Convalida** per ispezionare il componente formato modificabile nella pagina **Progettazione formati**.

    ![Convalidare gli elementi di formato associati alle origini dati nella pagina Progettazione formati](./media/er-components-inspections-09c.png)

16. Notare che si verifica un errore di convalida. Il messaggio indica che potrebbe essere generato un errore per i componenti formato configurati **Rendiconto\\Parte\\Nome** e **Rendiconto\\Parte\\AccountNum** in fase di esecuzione se l'elenco `model.Vendor` è vuoto.

    ![Errore di convalida su un potenziale errore per i componenti di formato configurati](./media/er-components-inspections-09d.png)

La figura seguente mostra l'errore di runtime che si verifica se si ignora l'avviso, selezionare **Esegui** per eseguire il formato e selezionare il numero di conto di un fornitore che non esiste. Poiché il fornitore richiesto non esiste, l'elenco `model.Vendor` sarà vuoto (ovvero, non conterrà record).

![Errori di runtime che si verificano durante l'esecuzione del mapping del formato](./media/er-components-inspections-09e.png)

### <a name="automatic-resolution"></a>Risoluzione automatica

Per la riga selezionata nella griglia nella scheda **Avvisi**, è possibile selezionare **Separa**. L'associazione indicata nella colonna **Percorso** viene automaticamente rimossa dagli elementi di formato.

### <a name="manual-resolution"></a>Risoluzione manuale

#### <a name="option-1"></a>Opzione 1

È possibile associare l'elemento di formato **Rendiconto\\Parte\\Nome** all'elemento origine dati `model.Vendor`. In fase di esecuzione, questa associazione chiama prima l'origine dati `model.Vendor`. Se `model.Vendor` restituisce un elenco di record vuoto, gli elementi di formato nidificati non vengono eseguiti. Pertanto, non si verificano avvisi di convalida per questa configurazione di formato.

![Associare l'elemento di formato all'elemento origini dati nella pagina Progettazione formati](./media/er-components-inspections-09e.gif)

#### <a name="option-2"></a>Opzione 2

Modificare l'associazione dell'elemento di formato **Rendiconto\\Parte\\Nome** da `model.Vendor.Name` a `FIRSTORNULL(model.Vendor).Name`. L'associazione aggiornata converte in modo condizionale il primo record dell'origine dati `model.Vendor` del tipo **Elenco di record** in una nuova origine dati del tipo **Record**. Questa nuova origine dati contiene lo stesso insieme di campi.

- Se almeno un record è disponibile nell'origine dati `model.Vendor`, i campi di quel record vengono riempiti con i valori dei campi del primo record dell'origine dati `model.Vendor`. In questo caso, l'associazione aggiornata restituisce il nome del fornitore.
- In caso contrario, ogni campo del record creato viene riempito con il valore predefinito per il tipo di dati di quel campo. In questo caso, la stringa vuota viene restituita come valore predefinito del tipo di dati **Stringa**.

Pertanto, non si verificano avvisi di convalida per l'elemento di formato **Rendiconto\\Parte\\Nome** quando è associato all'espressione `FIRSTORNULL(model.Vendor).Name`.

![L'associazione modificata risolve gli avvisi di convalida nella pagina Progettazione formati](./media/er-components-inspections-09f.gif)

#### <a name="option-3"></a>Opzione 3

Se si desidera specificare esplicitamente i dati inseriti in un documento generato quando l'origine dati `model.Vendor` del tipo **Elenco di record** non restituisce alcun record (il testo **Non disponibile** in questo esempio), modificare l'associazione dell'elemento di formato **Rendiconto\\Parte\\Nome** da `model.Vendor.Name` a `IF(NOT(ISEMPTY(model.Vendor)), model.Vendor.Name, "Not available")`. È possibile anche usare l'espressione `IF(COUNT(model.Vendor)=0, model.Vendor.Name, "Not available")`.

### <a name="additional-consideration"></a><a id="i9a"></a>Ulteriori considerazioni

L'ispezione avvisa anche di un altro potenziale problema. Per impostazione predefinita, quando si associano gli elementi di formato **Rendiconto\\Parte\\Nome** e **Rendiconto\\Parte\\AccountNum** ai campi appropriati dell'origine dati `model.Vendor` del tipo **Elenco di record**, quelle associazioni verranno eseguite e assumeranno i valori dei campi appropriati del primo record dell'origine dati `model.Vendor`, se l'elenco non è vuoto.

Perché l'elemento di formato **Rendiconto\\Parte** non è stato vincolato con l'origine dati `model.Vendor`, l'elemento **Rendiconto\\Parte** non verrà iterato per ogni record dell'origine dati `model.Vendor` durante l'esecuzione del formato. Al contrario, un documento generato verrà riempito con le informazioni solo dal primo record dell'elenco di record, se tale elenco contiene più record. Pertanto, potrebbe esserci un problema se il formato è inteso a riempire un documento generato con informazioni su tutti i fornitori dall'origine dati `model.Vendor`. Per risolvere questo problema, associare l'elemento **Rendiconto\\Parte** all'origine dati `model.Vendor`.

## <a name="executability-of-an-expression-with-filter-function-caching"></a><a id="i10"></a>Eseguibilità di un'espressione con la funzione FILTER (memorizzazione nella cache)

Diverse funzioni ER incorporate, incluse [FILTER](er-functions-list-filter.md) e [ALLITEMSQUERY](er-functions-list-allitemsquery.md), vengono utilizzate per accedere a tabelle, viste o entità di dati dell'applicazione inserendo una singola chiamata SQL per ottenere i dati richiesti come elenco di record. Un'origine dati del tipo **Elenco di record** viene utilizzata come argomento di ognuna di queste funzioni e specifica un'origine della domanda di lavoro per la chiamata. ER verifica se è possibile stabilire una chiamata SQL diretta su un'origine dati a cui si fa riferimento in una di queste funzioni. Se non è possibile stabilire una chiamata perchè l'origine dati è stata contrassegnata come [memorizzata nella cache](trace-execution-er-troubleshoot-perf.md#improve-the-model-mapping-based-on-information-from-the-execution-trace), si verifica un errore di convalida nella finestra di progettazione del mapping del modello ER. Il messaggio ricevuto indica che l'espressione ER che contiene una di queste funzioni non può essere eseguita in fase di esecuzione.

I passaggi seguenti mostrano come potrebbe verificarsi questo problema.

1. Iniziare a configurare il componente di mapping del modello ER.
2. Aggiungere un'origine dati del tipo **Dynamics 365 for Operations \\ Record di tabella**.
3. Assegnare un nome alla nuova origine dati **Fornitore**. Nel campo **Tabella**, selezionare **VendTable** per specificare che questa origine dati richiederà la tabella VendTable.
4. Aggiungere un'origine dati del tipo **Parametro di input dell'utente \\ Generale** per cercare un account fornitore nella finestra di dialogo runtime.
5. Assegnare un nome alla nuova origine dati **RequestedAccountNum**. Nel campo **Etichetta** immettere il **numero del conto del fornitore**. Nel campo **Nome del tipo di dati delle operazioni**, lasciare il valore predefinito, **Descrizione**.
6. Aggiungere un'origine dati del tipo **Campo calcolato** per filtrare un fornitore su cui si richiedono informazioni.
7. Assegnare un nome alla nuova origine dati **FornitoreFiltrato** e configurarla in modo che contenga l'espressione `FILTER(Vendor, Vendor.AccountNum=RequestedAccountNum)`.
8. Contrassegnare l'origine dati configurata **Fornitore** come memorizzata nella cache.

    ![Configurare il componente di mapping del modello nella pagina Progettazione mapping modello](./media/er-components-inspections-10a.gif)

9. Selezionare **Convalida** per ispezionare il componente di mapping del modello modificabile nella pagina **Designer del mapping del modello**.

    ![Convalidare la funzione FILTER applicata all'origine dati Fornitore memorizzata nella cache nella pagina Progettazione mapping modello](./media/er-components-inspections-10a.png)

10. Notare che si verifica un errore di convalida. Il messaggio afferma che la funzione **FILTER** non può essere applicata all'origine dati memorizzata nella cache **Fornitore**.

La figura seguente mostra l'errore di runtime che si verifica se si ignora l'avviso e si seleziona **Esegui** per eseguire il formato.

![Errore di runtime che si verifica durante l'esecuzione del mapping del formato nella pagina Progettazione formati](./media/er-components-inspections-10b.png)

### <a name="automatic-resolution"></a>Risoluzione automatica

Non è disponibile alcuna opzione per risolvere automaticamente questo problema.

### <a name="manual-resolution"></a>Risoluzione manuale

#### <a name="option-1"></a>Opzione 1

Rimuovere il flag **Cache** dall'origine dati **Fornitore**. L'origine dati **FilteredVendor** diventerà quindi eseguibile, ma l'origine dati **Fornitore** a cui si fa riferimento nella tabella VendTable sarà accessibile ogni volta che viene chiamata l'origine dati **FilteredVendor**.

#### <a name="option-2"></a>Opzione 2

Cambiare l'espressione dell'origine dati **FornitoreFiltrato** da `FILTER(Vendor, Vendor.AccountNum="US-101")` a `WHERE(Vendor, Vendor.AccountNum="US-101")`. In questo caso, l'origine dati **Fornitore** a cui si fa riferimento nella tabella VendTable sarà accessibile solo durante la prima chiamata dell'origine dati **Fornitore**. Tuttavia, la selezione dei record verrà eseguita in memoria. Pertanto, questo approccio può causare prestazioni ridotte.

## <a name="missing-binding"></a><a id="i11"></a>Associazione mancante

Quando si configura un componente del formato ER, il modello di dati ER di base viene offerto come origine dati predefinita per il formato ER. Quando viene eseguito il formato ER configurato, il [mapping di modello predefinito](er-country-dependent-model-mapping.md) per il modello di base viene utilizzato per riempire il modello di dati con i dati dell'applicazione. La progettazione del formato ER mostra un avviso se si associa un elemento di formato a un elemento del modello di dati che non è associato a nessuna origine dati mapping di modello che è attualmente selezionata come mapping di modello predefinito per il formato modificabile. Questo tipo di associazione non può essere eseguito in fase di esecuzione, perché il formato che viene eseguito non può riempire un elemento associato con i dati dell'applicazione. Pertanto, si verifica un errore in fase di esecuzione.

I passaggi seguenti mostrano come potrebbe verificarsi questo problema.

1. Iniziare a configurare il modello di dati ER, il mapping di modello di ER e i componenti di formato ER contemporaneamente.
2. Nell'albero del modello di dati, aggiungere un elemento radice denominato **Root3**.
3. Modificare l'elemento **Root3** aggiungendo un nuovo elemento nidificato del tipo **Elenco di record**.
4. Assegnare un nome al nuovo elemento nidificato **Fornitore**.
5. Modificare l'elemento **Fornitore** nel modo seguente:

    - Aggiungere un campo nidificato del tipo **Stringa** e denominarlo **Nome**.
    - Aggiungere un campo nidificato del tipo **Stringa** e denominarlo **AccountNumber**.

    ![Aggiungere campi nidificati all'elemento Fornitore nella pagina Modello dati](./media/er-components-inspections-11a.png)

6. Nel riquadro **Origine dati** del mapping del modello, aggiungere un'origine dati di tipo **Dynamics 365 for Operations \\ Record tabella**.
7. Assegnare un nome alla nuova origine dati **Fornitore**. Nel campo **Tabella**, selezionare **VendTable** per specificare che questa origine dati richiederà la tabella VendTable.
8. Aggiungere un'origine dati del tipo **Parametro di input dell'utente \\ Generale** per chiedere informazioni su un account fornitore nella finestra di dialogo runtime.
9. Assegnare un nome alla nuova origine dati **RequestedAccountNum**. Nel campo **Etichetta** immettere il **numero del conto del fornitore**. Nel campo **Nome del tipo di dati delle operazioni**, lasciare il valore predefinito, **Descrizione**.
10. Aggiungere un'origine dati del tipo **Campo calcolato** per filtrare un fornitore su cui si richiedono informazioni.
11. Assegnare un nome alla nuova origine dati **FornitoreFiltrato** e configurarla in modo che contenga l'espressione `FILTER(Vendor, Vendor.AccountNum=RequestedAccountNum)`.
12. Associare gli elementi del modello di dati alle origini dati configurate nel modo seguente:

    - Associare **FilteredVendor** a **Fornitore**.
    - Associare **FilteredVendor.AccountNum** a **Vendor.AccountNumber**.

    > [!NOTE]
    > Il campo del modello di dati **Vendor.Name** rimane non associato.

    ![Elementi del modello di dati associati a origini dati configurate e un elemento in modalità dati che rimane non associato nella pagina Progettazione mapping modello](./media/er-components-inspections-11b.png)

13. Nell'albero della struttura del formato, aggiungere i seguenti elementi per generare un documento in uscita in formato XML che contenga i dettagli dei fornitori di cui si cercano informazioni:

    1. Aggiungere l'elemento XML radice **Rendiconto**.
    2. Per l'elemento XML **Rendiconto**, aggiungere l'elemento XML nidificato **Parte**.
    3. Per l'elemento XML **Parte**, aggiungere i seguenti attributi XML nidificati:

        - Nome
        - AccountNum

14. Associare gli elementi di formato alle origini dati fornite nel modo seguente:

    - Associare l'elemento di formato **Rendiconto\\Parte** all'elemento origine dati `model.Vendor`.
    - Associare l'elemento di formato **Rendiconto\\Parte\\Nome** al campo origine dati **model.Vendor.Name**.
    - Associare l'elemento di formato **Rendiconto\\Parte\\AccountNum** al campo origine dati **model.Vendor.AccountNumber**.

15. Selezionare **Convalida** per ispezionare il componente formato modificabile nella pagina **Progettazione formati**.

    ![Convalidare il componente formato ER nella pagina Progettazione formati](./media/er-components-inspections-11c.png)

16. Notare che si verifica un avviso di convalida. Il messaggio afferma che l'origine dati **model.Vendor.Name** non è associato a nessuna origine dati nel mapping di modello configurato per essere utilizzato dal formato. Quindi, l'elemento formato **Rendiconto\\Parte\\Nome** potrebbe non essere compilato in fase di runtime e potrebbe verificarsi un'eccezione di runtime.

    ![Convalida del componente formato ER nella pagina Progettazione formati](./media/er-components-inspections-11d.png)

La figura seguente mostra l'errore di runtime che si verifica se si ignora l'avviso e si seleziona **Esegui** per eseguire il formato.

![Esecuzione del formato modificabile nella pagina Progettazione formati](./media/er-components-inspections-11e.png)

### <a name="automatic-resolution"></a>Risoluzione automatica

Non è disponibile alcuna opzione per risolvere automaticamente questo problema.

### <a name="manual-resolution"></a>Risoluzione manuale

#### <a name="option-1"></a>Opzione 1

Modificare la mappatura del modello configurato aggiungendo un'associazione per il campo origine dati **model.Vendor.Name**.

#### <a name="option-2"></a>Opzione 2

Modificare il formato configurato rimuovendo l'associazione per l'elemento di formato **Rendiconto\\Parte\\Nome**.

## <a name="not-linked-template"></a><a id="i12"></a>Modello non collegato

Quando si configura [manualmente](er-fillable-excel.md#manual-entry) un componente formato ER per utilizzare un modello per generare un documento in uscita, è necessario aggiungere manualmente l'elemento **Excel\\File**, aggiungere il modello richiesto come allegato del componente modificabile e selezionare tale allegato nell'elemento aggiunto **Excel\\File**. In questo modo, si indica che l'elemento aggiunto riempirà il modello selezionato in fase di runtime. Quando si configura una versione del componente di formato nello [stato](general-electronic-reporting.md#component-versioning) **Bozza**, si potrebbero aggiungere diversi modelli al componente modificabile e quindi selezionare ogni modello nell'elemento **Excel\\File** per eseguire il formato ER. In questo modo, è possibile vedere come i diversi modelli vengono riempiti in fase di esecuzione. Se disponi di modelli che non sono selezionati in alcun elemento **Excel\\File**, la progettazione del formato ER avvisa che quei modelli verranno eliminati dalla versione modificabile del componente del formato ER quando il suo stato viene modificato da **Bozza** a **Completato**.

I passaggi seguenti mostrano come potrebbe verificarsi questo problema.

1. Iniziare a configurare il componente formato ER.
2. Nell'albero della struttura del formato, aggiungere l'elemento **File\\Excel**.
3. Per l'elemento **File\\Excel** appena aggiunto, aggiungere un file di cartella di lavoro di Excel, **A.xlsx**, come un allegato. Utilizzare il tipo di documento configurato in [Parametri ER](electronic-reporting-er-configure-parameters.md#parameters-to-manage-documents) per specificare l'archiviazione dei modelli in formato ER.
4. Per l'elemento **File\\Excel**, aggiungere un altro file di cartella di lavoro di Excel, **B.xlsx**, come un allegato. Utilizzare lo stesso tipo di documento utilizzato per il file della cartella di lavoro A.
5. Nell'elemento **File\\Excel**, selezionare il file della cartella di lavoro A.
6. Selezionare **Convalida** per ispezionare il componente formato modificabile nella pagina **Progettazione formati**.

    ![Convalida del componente formato modificabile del file della cartella di lavoro nella pagina Progettazione formati](./media/er-components-inspections-12a.gif)

7. Notare che si verifica un avviso di convalida. Il messaggio indica il file della cartella di lavoro B.xlsx non è collegato ad alcun componente e che verrà rimosso dopo la modifica dello stato della versione della configurazione.

### <a name="automatic-resolution"></a>Risoluzione automatica

Non è disponibile alcuna opzione per risolvere automaticamente questo problema.

### <a name="manual-resolution"></a>Risoluzione manuale

Modificare il formato configurato rimuovendo tutti i modelli che non sono collegati ad alcun elemento **File\\Excel**.

## <a name="not-synced-format"></a><a id="i13"></a>Formato non sincronizzato

Quando si [configura](er-fillable-excel.md) un componente formato ER per utilizzare un modello Excel per generare un documento in uscita, è possibile aggiungere manualmente l'elemento **File\\Excel**, aggiungere il modello richiesto come allegato del componente modificabile e selezionare tale allegato nell'elemento aggiunto **File\\Excel**. In questo modo, si indica che l'elemento aggiunto riempirà il modello selezionato in fase di runtime. Poiché il modello Excel aggiunto è stato progettato esternamente, il formato ER modificabile potrebbe contenere nomi Excel mancanti dal modello aggiunto. La progettazione del formato ER ti avvisa di eventuali incongruenze tra le proprietà degli elementi del formato ER che fanno riferimento a nomi che non sono inclusi nel modello Excel aggiunto.

I passaggi seguenti mostrano come potrebbe verificarsi questo problema.

1. Iniziare a configurare il componente formato ER.
2. Nell'albero della struttura del formato, aggiungere l'elemento **File\\Excel** **Report**.
3. Per l'elemento **File\\Excel** appena aggiunto, aggiungere un file di cartella di lavoro di Excel, **A.xlsx**, come un allegato. Utilizzare il tipo di documento configurato in [Parametri ER](electronic-reporting-er-configure-parameters.md#parameters-to-manage-documents) per specificare l'archiviazione dei modelli in formato ER.

    > [!IMPORTANT]
    > Assicurarsi che la cartella di lavoro di Excel aggiunta non contenga il nome **ReportTitle**.

4. Aggiungere l'elemento **Excel\\Cella** **Titolo** come elemento nidificato dell'elemento **Report**. Nel campo **Intervallo Excel**, immettere **ReportTitle**.
5. Selezionare **Convalida** per ispezionare il componente formato modificabile nella pagina **Progettazione formati**.

    ![Convalidare gli elementi e i campi nidificati nella pagina Progettazione formati](./media/er-components-inspections-13a.png)

6. Notare che si verifica un avviso di convalida. Il messaggio afferma che il nome **ReportTitle** non esiste sul foglio **Foglio1** del modello di Excel che stai utilizzando.

    ![Avviso di convalida che indica che il nome ReportTitle non esiste nel Foglio1 del modello Excel](./media/er-components-inspections-13b.png)

### <a name="automatic-resolution"></a>Risoluzione automatica

Non è disponibile alcuna opzione per risolvere automaticamente questo problema.

### <a name="manual-resolution"></a>Risoluzione manuale

#### <a name="option-1"></a>Opzione 1

Modificare il formato configurato rimuovendo tutti gli elementi che fanno riferimento a nomi di Excel mancanti dal modello.

#### <a name="option-2"></a>Opzione 2

[Aggiornare](er-fillable-excel.md#template-import) il formato ER modificabile importando un modello Excel. La struttura del formato ER modificabile verrà [sincronizzato](modify-electronic-reporting-format-reapply-excel-template.md) con la struttura del modello Excel importato.

### <a name="additional-consideration"></a>Ulteriori considerazioni

Per sapere come sincronizzare la struttura del formato con un modello ER nell'editor modelli di [Gestione documenti aziendali](er-business-document-management.md), vedere [Aggiornare la struttura di un modello di documento aziendale](er-bdm-update-structure.md).

## <a name="not-synced-with-a-word-template-format"></a><a id="i14"></a>Non sincronizzato con un formato di modello di Word

Quando si [configura](er-fillable-excel.md) un componente formato ER per utilizzare un modello Word per generare un documento in uscita, è possibile aggiungere manualmente l'elemento **Excel\\File**, aggiungere il modello Word richiesto come allegato del componente modificabile e selezionare tale allegato nell'elemento aggiunto **Excel\\File**.

> [!NOTE]
> Quando il documento Word è associato, la progettazione del formato ER presenta l'elemento modificabile come **Word\\File**.

In questo modo, si indica che l'elemento aggiunto riempirà il modello selezionato in fase di runtime. Poiché il modello Word aggiunto è stato progettato esternamente, il formato ER modificabile potrebbe contenere riferimenti ai controlli del contenuto di Word non presenti nel modello aggiunto. La progettazione del formato ER ti avvisa di eventuali incongruenze tra le proprietà degli elementi del formato ER che fanno riferimento a controlli del contenuto che non sono inclusi nel modello Word aggiunto.

Per un esempio che mostra come potrebbe verificarsi questo problema, vedere [Configurare il formato modificabile per sopprimere la sezione di riepilogo](er-design-configuration-word-suppress-controls.md#configure-to-suppress-control).

### <a name="automatic-resolution"></a>Risoluzione automatica

Non è disponibile alcuna opzione per risolvere automaticamente questo problema.

### <a name="manual-resolution"></a>Risoluzione manuale

#### <a name="option-1"></a>Opzione 1

Modificare il formato configurato eliminando la formula **Rimosso** dall'elemento di formato menzionato nell'avviso di convalida.

#### <a name="option-2"></a>Opzione 2

Modificare il modello di Word [aggiungendo](er-design-configuration-word-suppress-controls.md#tag-control) il tag necessario per il controllo del contenuto di Word pertinente.

## <a name="no-default-mapping"></a><a id="i15"></a>Nessun mapping predefinito

Al termine della verifica [Associazione mancante](#i11), le associazioni di formato verificate vengono valutate rispetto alle associazioni del componente di mapping del modello pertinente. Perché è possibile importare [varie](./tasks/er-manage-model-mapping-configurations-july-2017.md) configurazioni del mapping di modello ER nell'istanza di Finance e ogni configurazione potrebbe contenere il componente di mapping del modello applicabile, una configurazione deve essere selezionata come configurazione predefinita. In caso contrario, quando si tenta di eseguire, modificare o convalidare il formato ER ispezionato, si verificherà un'eccezione e verrà visualizzato il messaggio seguente: "Esiste più di un mapping del modello per il \<model name (root descriptor)\> modello dati nelle configurazioni \<configuration names separated by comma\>. Impostare una delle configurazioni come predefinita."

Per un esempio che mostra come potrebbe verificarsi questo problema e come risolverlo, vedere [Gestire diversi mapping derivati per una singola radice del modello](er-multiple-model-mappings.md).

## <a name="inconsistent-setting-of-header-or-footer-components"></a><a id="i16"></a>Impostazione incoerente dei componenti di intestazione o piè di pagina

Quando si [configura](er-fillable-excel.md) un componente formato ER per utilizzare un modello di Excel per generare un documento in uscita, è possibile aggiungere il componente **Excel\\Intestazione** per compilare le intestazioni nella parte superiore di un foglio di lavoro in una cartella di lavoro di Excel. È anche possibile aggiungere il componente **Excel\\Piè di pagina** per compilare i piè di pagina nella parte inferiore di un foglio di lavoro. Per ogni componente **Excel\\Intestazione** o **Excel\\Piè di pagina** aggiunto, è necessario impostare la proprietà **Aspetto intestazione/piè di pagina** per specificare le pagine per le quali viene eseguito il componente. Poiché è possibile configurare diversi componenti **Excel\\Intestazione** o **Excel\\Piè di pagina** per un singolo componente **Foglio** ed è possibile generare intestazioni o piè di pagina diversi per diversi tipi di pagine in un foglio di lavoro di Excel, è necessario configurare un singolo componente **Excel\\Intestazione** o **Excel\\Piè di pagina** per un valore specifico della proprietà **Aspetto intestazione/piè di pagina**. Se più di un componente **Excel\\Intestazione** o **Excel\\Piè di pagina** è configurato per un valore specifico della proprietà **Aspetto intestazione/piè di pagina**, si verifica un errore di convalida e viene visualizzato il seguente messaggio di errore: "Le intestazioni/piè di pagina (&lt;tipo di componente: intestazione o piè di pagina&gt;) sono incoerenti."

### <a name="automatic-resolution"></a>Risoluzione automatica

Non è disponibile alcuna opzione per risolvere automaticamente questo problema.

### <a name="manual-resolution"></a>Risoluzione manuale

#### <a name="option-1"></a>Opzione 1

Modificare il formato configurato eliminando uno dei componenti **Excel\\Intestazione** o **Excel\\Piè di pagina** incoerenti.

#### <a name="option-2"></a>Opzione 2

Modifica il valore della proprietà **Aspetto intestazione/piè di pagina** per uno dei componenti **Excel\\Intestazione** o **Excel\\Piè di pagina** incoerenti.

## <a name="additional-resources"></a>Risorse aggiuntive

[Funzione ER ALLITEMS](er-functions-list-allitems.md)

[Funzione ER ALLITEMSQUERY](er-functions-list-allitemsquery.md)

[Funzione ER INT64VALUE](er-functions-conversion-int64value.md)

[Funzione ER INTVALUE](er-functions-conversion-intvalue.md)

[Funzione ER FILTER](er-functions-list-filter.md)

[Funzione ER WHERE](er-functions-list-where.md)

[Utilizzare le origini dati JOIN nei mapping di modello ER per ottenere i dati da più tabelle dell'applicazione](er-join-data-sources.md)

[Tenere traccia dell'esecuzione dei formati di creazione di report elettronici per risolvere i problemi di prestazioni](trace-execution-er-troubleshoot-perf.md)

[Panoramica di gestione dei documenti aziendali](er-business-document-management.md)

[Sopprimere i controlli del contenuto di Word nei report generati](er-design-configuration-word-suppress-controls.md)

[Gestire diversi mapping derivati per una singola radice del modello](er-multiple-model-mappings.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
