---
title: Libri IVA italiani
description: Nell&quot;argomento viene descritto come impostare e utilizzare i libri VAT italiani e sezionali VAT italiani del libro VAT.
author: ShylaThompson
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: CustParameters, LedgerJournalSetup, ProjJournalName, TaxBook, TaxBookSection, TaxBookSectionLookupVoucherSeries, TaxBookStatus, TaxBookTable, VendParameters
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 268654
ms.assetid: 3e761795-22e4-4d40-8c51-1f4a3f94b573
ms.search.region: Italy
ms.author: ilyako
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 6bb98cc72c2ec0c1551412dd39d5bea3ce10e2cd
ms.openlocfilehash: d481471d81878d13f0af0ee946210fcdd524fa50
ms.lasthandoff: 03/31/2017


---

# <a name="italian-sales-tax-books"></a>Libri IVA italiani

Nell'argomento viene descritto come impostare e utilizzare i libri VAT italiani e sezionali VAT italiani del libro VAT.

In base alla legislazione tributaria italiana, ciascuna transazione (VAT) dell'imposta sul valore aggiunto devono appartenere a un libro VAT (*Libro IVA*) che verrà utilizzato per il reporting VAT. Per soddisfare questi fabbisogni legislative, Microsoft Dynamics 365 delle operazioni per implementare i libri VAT italiani. I libri VAT possono essere di diversi tipi. È necessario specificare il tipo di libro VAT per garantire che tutte le fatture di vendita e di acquisto sono incluse ** pagamento VAT italiano ** nel report. È possibile mantenere tutti i libri VAT ** ** vendita e acquisto ** ** di tipi come ordinati. Ciascun libro VAT può essere diviso in più aree del libro VAT (*Sezionale IVA*). Tutte le transazioni VAT devono essere numerate (senza interruzioni) e essere ordinati in sequenza in base alla data di registrazione. Area del libro VAT equivale a una sequenza numerica per il numero di giustificativo italiano VAT (*Protocollo IVA*) che deve essere applicato sempre durante la registrazione consentono di assicurarsi dell'ordine cronologico in base alla data di registrazione.

## <a name="prerequisites"></a>Prerequisiti
Nella seguente tabella vengono visualizzati i prerequisiti che devono essere validi prima di iniziare.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Categoria</th>
<th>Prerequisito</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><strong>Impostazione:</strong> persona giuridica</td>
<td>L'indirizzo principale della persona giuridica deve essere in Italia. Fare <strong>Amministrazione organizzazione</strong> &gt; <strong>Organizzazioni</strong> &gt; <strong>Persone giuridiche</strong> &gt; <strong>Indirizzi</strong> &gt; <strong>Paese</strong>clic su ().</td>
</tr>
<tr class="even">
<td><strong>Attrezzaggio:</strong> Sequenze numeriche</td>
<td>Impostare un numero illimitato di sequenze numeriche come ordinati per coprire tutti i tipi necessari per transazioni VAT. Fare <strong>Amministrazione organizzazione</strong> &gt; <strong>Sequenze numeriche</strong> &gt; <strong>Sequenze numeriche</strong>clic su (). Tutte le sequenze numeriche devono essere continue e avere <strong>Società</strong> ambito.</td>
</tr>
<tr class="odd">
<td><strong>Attrezzaggio:</strong> Nomi giornale di registrazione</td>
<td>Impostare i nomi obbligatori del giornale di registrazione. Fare <strong>Contabilità generale</strong> &gt; <strong>Impostazione del giornale di registrazione</strong> &gt; <strong>Nomi giornale di registrazione</strong> clic su (o <strong>Gestione progetti e contabilità</strong> &gt; <strong>Impostazione</strong> &gt; <strong>Giornali</strong> &gt; <strong>Nomi giornale di registrazione</strong>). <strong>Generale</strong> Nella scheda dettaglio, <strong>VAT</strong> nell'area, nel <strong>Libro VAT italiano</strong> campo, specificare uno dei seguenti valori:
<ul>
<li><strong>Non incluso</strong> Consente di selezionare il valore per le fatture e le note di accredito che provengono dai paesi esterni alla Community Europea.</li>
<li><strong>Acquisti</strong> Consente di selezionare il valore per le fatture di acquisto e note di accredito.</li>
<li><strong>Vendite</strong> Consente di selezionare il valore per le fatture di vendita e note di accredito.</li>
<li><strong>Spese</strong> Consente di selezionare il valore per tutti gli altri tipi di transazioni.</li>
</ul>
In alcuni casi, <strong>Libro VAT italiano</strong> il campo viene impostato automaticamente, in <strong>Tipo di giornale di registrazione</strong> base al valore. Ad esempio, se <strong>Tipo di giornale di registrazione</strong> il campo è impostato su, <strong>Libro VAT italiano</strong> il campo è <strong>Acquisti</strong> impostato su per impostazione predefinita.</td>
</tr>
<tr class="even">
<td><strong>Attrezzaggio:</strong> Parametri del modulo</td>
<td>Per i giustificativi seguire le sequenze numeriche delle fatture e sulle note di accredito correlate, è <strong>Numeri di riutilizzo</strong> necessario selezionare la casella di controllo quando si definisce le sequenze numeriche per tali fatture e note di accredito. Per questa casella <strong>Sequenze numeriche</strong> di controllo nella scheda delle pagine seguenti:
<ul>
<li>Parametri contabilità clienti</li>
<li>Parametri contabilità fornitori</li>
<li>Parametri Gestione progetti e contabilità</li>
</ul>
Ad esempio, <strong>Parametri contabilità clienti</strong> nella pagina, <strong>Sequenze numeriche</strong> nella scheda, selezionare la casella di controllo per <strong>Giustificativo di fattura a testo libero</strong> sincronizzare l'allocazione dei giustificativi fattura a testo libero e fatture a testo libero.</td>
</tr>
</tbody>
</table>

## <a name="set-up-sales-tax-books"></a>Impostare i libri VAT
I libri VAT vengono utilizzati per il reporting VAT. Per impostare i libri VAT italiani, fare clic su ** imposta ** &gt; ** l'impostazione ** &gt; ** VAT ** &gt; ** libri VAT italiani **. Nella tabella seguente vengono descritti i campi disponibili ** libri VAT italiani ** nella pagina.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Campo</th>
<th>descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Libro IVA</td>
<td>Immettere l'identificazione del libro VAT.</td>
</tr>
<tr class="even">
<td>Nome</td>
<td>Immettere una descrizione del libro VAT.</td>
</tr>
<tr class="odd">
<td>Tipo di libro IVA</td>
<td>Selezionare la natura di operazioni che verranno eseguite tramite i sezionali VAT che attaccherete al libro VAT. Sono disponibili i valori seguenti:
<ul>
<li><strong>Acquisti</strong> Consente di selezionare il valore per le fatture di acquisto e note di accredito.</li>
<li><strong>Vendite</strong> Consente di selezionare il valore per le fatture di vendita e note di accredito.</li>
<li><strong>Non incluso</strong> Consente di selezionare il valore per le fatture e le note di accredito che provengono dai paesi esterni alla Community Europea. Questo tipo viene utilizzato solo a fini statistici e non verrà incluso nei riepiloghi fiscali finali del libro VAT.</li>
</ul></td>
</tr>
<tr class="even">
<td>Periodo di liquidazione</td>
<td>Selezionare un periodo di liquidazione VAT esistente. Quando viene stampato un libro VAT, se <strong>Aggiornamento</strong> la casella di controllo è <strong>Pagamento VAT</strong> selezionata nella pagina, la data <strong>In data</strong> nel campo viene confrontata con il periodo di liquidazione selezionato. Questo periodo viene utilizzato anche per identificare i libri e i sezionali IVA da chiudere al momento dell'aggiornamento di una liquidazione IVA per un determinato periodo.</td>
</tr>
<tr class="odd">
<td>Chiuso al</td>
<td>Data di chiusura più recente le aree correlate di libro VAT che appartengono al libro VAT selezionato.</td>
</tr>
<tr class="even">
<td>Vendite UE</td>
<td>Selezionare un libro VAT <strong>Vendite</strong> di tipo e collegarlo al libro VAT <strong>Acquisti</strong> corrente di tipo. Questo campo viene utilizzato se il libro VAT selezionato deve includere le transazioni di acquisto di l 'Unione Europea (EU) dal libro corrente nei report VAT. Questo campo non è disponibile per i libri VAT e <strong>Non incluso</strong> del <strong>Vendite</strong> tipo.</td>
</tr>
<tr class="odd">
<td>Codice ATECOFIN</td>
<td>Selezionare il codice imposta per il reporting.</td>
</tr>
<tr class="even">
<td>Stampa riepilogo e pagamenti</td>
<td>Selezionare questa opzione per stampare il riepilogo e il report di pagamento. Questo campo è disponibile solo per i libri VAT <strong>Vendite</strong> di tipo.</td>
</tr>
</tbody>
</table>

## <a name="set-up-sales-tax-book-sections"></a>Sezionali VAT di impostazione
I sezionali VAT vengono un archivio in cui le transazioni devono essere registrate in base alla natura. La numerazione dei giustificativi viene determinata dai sezionali VAT. Per impostare i sezionali VAT italiani del libro VAT, fare clic su ** imposta ** &gt; ** l'impostazione ** &gt; ** ** &gt; ** VAT italiani sezioni del libro VAT **. Nella tabella seguente vengono descritti i campi disponibili ** sezionali VAT italiani del libro VAT ** nella pagina.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Campo</th>
<th>descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Libro IVA</td>
<td>Selezionare uno dei libri VAT esistenti che il sezionale VAT è collegata.</td>
</tr>
<tr class="even">
<td>Sezionale IVA</td>
<td>Immettere l'identificazione del sezionale VAT.</td>
</tr>
<tr class="odd">
<td>Nome</td>
<td>Immettere una descrizione del sezionale VAT.</td>
</tr>
<tr class="even">
<td>Codice sequenza numerica</td>
<td>Selezionare il codice di sequenza numerica per il sezionale IVA. Il codice di sequenza numerica selezionato dipende dal tipo di libro VAT del sezionale VAT è collegata:
<ul>
<li>Per un libro VAT <strong>Acquisti</strong> di tipo: Selezionare i codici di sequenza numerica definiti per i giustificativi fattura di acquisto o di <strong>Parametri contabilità fornitori</strong> nota di accredito di acquisto nella pagina, ovvero i codici di sequenza numerica da <strong>Nomi giornale di registrazione</strong> utilizzare nella pagina per i giustificativi in cui impostare <strong>Libro VAT italiano</strong> il campo <strong>Acquisti</strong>.</li>
<li>Per un libro VAT <strong>Vendite</strong> di tipo: Selezionare i codici di sequenza numerica definiti per giustificativi fatture di vendita o di nota di accredito di vendita o di fattura a testo libero o di nota di accredito a <strong>Contabilità clienti</strong><strong>parametri</strong> testo libero nella pagina, ovvero i codici di sequenza numerica da <strong>Nomi giornale di registrazione</strong> utilizzare nella pagina per i giustificativi in cui impostare <strong>Libro VAT italiano</strong> il campo <strong>Vendite</strong>.</li>
<li>Per un libro VAT <strong>Non incluso</strong> di tipo: Selezionare tutto il codice di sequenza numerica appropriato.</li>
</ul></td>
</tr>
<tr class="odd">
<td>Chiuso al</td>
<td>Immettere la data di fine dell'ultimo periodo di liquidazione VAT chiuso. Questo campo viene utilizzato per filtrare i dati nel report VAT.</td>
</tr>
<tr class="even">
<td>Chiudi sezionale IVA italiani</td>
<td>Data di chiusura del libro IVA italiano per un periodo fiscale. Non è possibile registrare o stornare una fattura se la relativa data è precedente alla data di chiusura del periodo fiscale. Questo campo viene aggiornato con la data di chiusura del periodo fiscale. <strong>Aggiornamento</strong> La casella di controllo deve essere <strong>Pagamento VAT</strong> selezionata nella pagina.</td>
</tr>
</tbody>
</table>

Nella tabella riportata di seguito pulsante è disponibile anche.

| Pulsante | descrizione                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
|--------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Creazione | Creare automaticamente tutte le richieste sezioni del libro VAT per i libri VAT esistenti ** ** vendita e acquisto ** ** di tipi. I sezionali VAT vengono create per ciascuna sequenza numerica definita per i giustificativi fattura di acquisto o giustificativi note di accredito di acquisto o vendita i giustificativi fattura o giustificativi note di accredito di vendita o giustificativi fattura a testo libero o giustificativi note di accredito a testo libero in ** parametri di contabilità fornitori, ** ** parametri di contabilità clienti **, o ** gestione progetti e parametri di contabilità ** pagina e per ciascuna sequenza numerica utilizzata ** nomi di giornale di registrazione ** nella pagina per i giustificativi in cui impostare ** libro VAT italiano ** il campo ** ** acquisto o vendita ** **. Ogni sezionale VAT creata è collegata automaticamente nel libro VAT predefinita. Il libro VAT deve essere creato prima dei sezionali VAT.) Se più libri VAT dello stesso tipo di libro VAT (** ** vendita o acquisto ** **) presenti, il primo libro VAT utilizzato per impostazione predefinita. Tuttavia, è possibile modificare manualmente questo collegamento. Se nessun libro VAT non è disponibile, il sezionale VAT viene creata automaticamente. |

## <a name="sales-tax-book-status"></a>Stato libro IVA
Quando si crea un nuovo periodo VAT, le righe del libro VAT vengono impostate automaticamente per ciascun libro VAT esistente. Se si crea un libro VAT aggiuntivo, le righe possono essere create manualmente per i periodi esistenti non ancora chiusi. Fare clic su ** imposta ** &gt; ** imposte indirette ** &gt; ** VAT ** &gt; ** periodi di liquidazione VAT ** quindi fare clic su ** lo stato del libro VAT **. Nella tabella seguente vengono descritte le schede ** lo stato del libro VAT ** nella pagina.

| Scheda      | descrizione                                                                                               |
|----------|-----------------------------------------------------------------------------------------------------------|
| Panoramica | Consente di visualizzare lo stato delle pagine dei libri IVA. Tutti i campi risultano bloccati per gli aggiornamenti manuali.                |
| Generale  | Consente di visualizzare le stesse informazioni visualizzate ** panoramica ** nella scheda, ma solo per il libro VAT selezionato. |

Nella tabella seguente vengono descritti i campi disponibili.

| Campo             | descrizione                                                                                      |
|-------------------|--------------------------------------------------------------------------------------------------|
| Libro IVA    | Selezionare l'identificazione del libro VAT impostata ** libri VAT italiani ** nella pagina.            |
| Nome              | Immettere il nome del libro VAT.                                                                  |
| Primo numero di pagina | Primo numero di pagina da utilizzare nel report VAT finale per questo periodo VAT. |
| Modificato in        | Il numero di pagina specificato in ** modificare il primo numero di pagina ** finestra di dialogo.                |
| Ultimo numero di pagina  | Ultimo numero di pagina da utilizzare nel report VAT finale per questo periodo VAT.  |
| Periodo di liquidazione | Il periodo di liquidazione utilizzato nel libro VAT.                                        |
| Dal         | Data di inizio del periodo di liquidazione.                                                        |
| Al           | Data di fine del periodo di liquidazione.                                                          |

Nella tabella riportata di seguito pulsante è disponibile anche.

| Pulsante                   | descrizione                                                                                                                                            |
|--------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------|
| Cambia numero prima pagina | Aprire ** modificare il primo numero di pagina ** la finestra di dialogo, in cui è possibile modificare il primo numero di pagina da utilizzare per il periodo di liquidazione aperto corrente. |

### <a name="change-first-page-number-dialog-box"></a>Modificare la prima finestra di dialogo del numero di pagina

Utilizzare ** modificare il primo numero di pagina ** la finestra di dialogo per modificare il primo numero di pagina del report VAT finale per il periodo di liquidazione VAT. Il numero di pagina verrà visualizzato ** variabile a ** nella colonna ** sullo stato del libro VAT impagina ** e utilizzato come primo numero di pagina del report VAT finale stampata per il periodo fiscale corrente. Nella tabella seguente vengono descritti i campi disponibili ** modificare il primo numero di pagina ** nella finestra di dialogo.

| Campo             | descrizione                                                           |
|-------------------|-----------------------------------------------------------------------|
| Primo numero di pagina | Primo numero di pagina corrente per il libro IVA selezionato.        |
| Modificato in        | Immettere il nuovo primo numero di pagina da utilizzare nel report IVA finale. |

## <a name="using-sales-tax-books"></a>Utilizzo dei libri VAT
Se il programma di installazione viene completata, i sezionali VAT vengono visualizzati ** sequenze numeriche ** nella scheda delle pagine seguenti:

-   Parametri contabilità clienti
-   Parametri contabilità fornitori
-   Parametri Gestione progetti e contabilità

I numeri di giustificativo assegnati durante la registrazione devono essere ordinati in sequenza in base alla data di registrazione e le transazioni VAT con lo stesso codice di sequenza numerica devono essere registrate nell'ordine. Se i numeri di giustificativi non vengono ordinati in sequenza, verrà generato un messaggio di errore. Inoltre, la registrazione viene interrotto se una transazione VAT non viene assegnata ad alcun sezionale VAT quando l'utente aggiorna una fattura. Ogni volta che un giustificativo viene registrato utilizzando un sezionale VAT, gli identificatori della sezione relativa del libro VAT e del libro VAT vengono salvati nelle transazioni VAT. Fare clic su ** imposta ** &gt; ** Informazioni VAT ** &gt; ** VAT registrata ** quindi fare clic su ** registrazione ** la tabella) Questi dati possono quindi essere utilizzati durante il reporting VAT. I libri VAT italiani vengono utilizzati per filtrare, il raggruppamento e ordinamento del report che si accede ** imposta ** &gt; ** alle dichiarazioni VAT ** &gt; ** ** &gt; ** VAT (Italia) **.


