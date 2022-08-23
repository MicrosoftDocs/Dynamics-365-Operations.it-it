---
title: Libri IVA italiani
description: Nell'articolo viene descritto come impostare e utilizzare i libri IVA italiani e i sezionali IVA italiani.
author: mrolecki
ms.date: 06/24/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Italy
ms.author: mrolecki
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.custom: 268654
ms.search.form: CustParameters, LedgerJournalSetup, ProjJournalName, TaxBook, TaxBookSection, TaxBookSectionLookupVoucherSeries, TaxBookStatus, TaxBookTable, VendParameters, LedgerParameters
ms.openlocfilehash: 3d515576abed83f91f9cd594945338324b7049bb
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9268529"
---
# <a name="italian-sales-tax-books"></a>Libri IVA italiani

[!include [banner](../includes/banner.md)]

Nell'articolo viene descritto come impostare e utilizzare i libri IVA italiani e i sezionali IVA italiani.

In base alla legislazione tributaria italiana, ciascuna transazione IVA (imposta sul valore aggiunto) deve appartenere a un *Libro IVA* che verrà utilizzato per il reporting fiscale. Per soddisfare questi requisiti legislativi, Dynamics 365 Finance implementa i libri IVA italiani. I libri IVA possono essere di diversi tipi. È necessario specificare il tipo di libro IVA per assicurarsi che tutte le transazioni di vendita e acquisti siano incluse nel report **Liquidazione IVA italiana**. È possibile mantenere tutti i libri IVA di tipo **Vendite** e **Acquisti** necessari. Ciascun libro IVA può essere diviso in più *Sezionali IVA*. Tutte le transazioni IVA devono essere numerate in sequenza (senza interruzioni) e ordinate in base alla data di registrazione. Un sezionale IVA equivale a una sequenza numerica per il numero di giustificativo IVA italiano (*Protocollo IVA*) che deve essere applicato sempre durante la registrazione per assicurare l'ordine cronologico in base alla data di registrazione.

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
<td>L'indirizzo principale della persona giuridica deve essere in Italia. (Fare clic su <strong>Amministrazione organizzazione</strong> &gt; <strong>Organizzazioni</strong> &gt; <strong>Persone giuridiche</strong> &gt; <strong>Indirizzi</strong> &gt; <strong>Paese</strong>.)</td>
</tr>
<tr class="even">
<td><strong>Impostazione:</strong> sequenze numeriche</td>
<td>Impostare il numero di sequenze necessario per coprire tutti i tipi necessari di transazioni IVA. Fare clic su <strong>Amministrazione organizzazione</strong> &gt;<strong>Sequenze numeriche</strong> &gt; <strong>Sequenze numeriche</strong>. Tutte le sequenze numeriche devono essere continue e avere ambito <strong>Società</strong>.</td>
</tr>
<tr class="odd">
<td><strong>Impostazione:</strong> nomi di giornali di registrazione</td>
<td>Impostare i nomi di giornale di registrazione necessari. (Fare clic su <strong>Contabilità generale</strong> &gt; <strong>Impostazione giornale di registrazione</strong> &gt; <strong>Nomi giornale di registrazione</strong> o <strong>Gestione progetti e contabilità</strong> &gt; <strong>Imposta</strong> &gt; <strong>Giornali di registrazione </strong> &gt; <strong>Nomi giornale di registrazione</strong>.) Nella Scheda dettaglio <strong>Generale</strong>, nella sezione <strong>IVA</strong>, nel campo <strong>Libro IVA italiano</strong> specificare uno dei valori seguenti:
<ul>
<li><strong>Non incluso</strong> Selezionare questo valore per le fatture e le note di accredito che provengono dai paesi esterni alla comunità europea.</li>
<li><strong>Acquisti</strong> Selezionare questo valore per le fatture e note di accredito di acquisto.</li>
<li><strong>Vendite</strong> Selezionare questo valore per le fatture e note di accredito di vendita.</li>
<li><strong>Vuoto</strong> Selezionare questo valore per tutti gli altri tipi di transazioni.</li>
</ul>
In alcuni casi, il campo <strong>Libro IVA italiano</strong> viene impostato automaticamente, in base al valore <strong>Tipo di giornale di registrazione</strong>. Ad esempio, se il campo <strong>Tipo di giornale di registrazione</strong> è impostato su <strong>Registro fatture</strong>, il campo <strong>Libro IVA italiano</strong> è  impostato su <strong>Acquisti</strong> per impostazione predefinita.</td>
</tr>
<tr class="even">
<td><strong>Impostazione:</strong> parametri del modulo</td>
<td>Per consentire ai giustificativi di seguire le sequenze numeriche delle fatture e delle note di accredito correlate, è necessario selezionare la casella di controllo <strong>Riutilizza numeri</strong> quando vengono definite le sequenze numeriche per tali fatture e note di accredito. È possibile trovare questa casella di controllo nella scheda <strong>Sequenze numeriche</strong> delle pagine seguenti:
<ul>
<li>Parametri contabilità clienti</li>
<li>Parametri contabilità fornitori</li>
<li>Parametri Gestione progetti e contabilità</li>
</ul>
Ad esempio, nella pagina <strong>Parametri contabilità clienti</strong>, scheda <strong>Sequenze numeriche</strong>, selezionare la casella di controllo <strong>Riutilizza numeri</strong> per <strong>Giustificativo di fattura a testo libero</strong> per sincronizzare l'allocazione dei numeri per i giustificativi fattura a testo libero e fatture a testo libero.


Nella localizzazione italiana, le correzioni al report di pagamento IVA italiano per un periodo IVA già regolato non sono supportate. Quindi nella pagina <strong>Parametri di contabilità generale</strong>, nella scheda <strong>IVA</strong>, impostare l'opzione **Includi correzioni** del report speciale su **NO**.
</td>
</tr>
</tbody>
</table>

## <a name="set-up-sales-tax-books"></a>Impostare i libri IVA
I libri IVA vengono utilizzati per il reporting IVA. Per impostare i libri IVA italiani, fare clic su **Imposta** &gt; **Imposta** &gt; **IVA** &gt; **Libri IVA italiani**. Nella tabella seguente vengono descritti i campi disponibili nella pagina **Libri IVA italiani**.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Campo</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Libro IVA</td>
<td>Immettere l'ID del libro IVA.</td>
</tr>
<tr class="even">
<td>Nome</td>
<td>Consente di immettere una descrizione del libro IVA.</td>
</tr>
<tr class="odd">
<td>Tipo di libro IVA</td>
<td>Selezionare la natura delle operazioni che verranno eseguite tramite i sezionali IVA che allegherai al libro IVA. Sono disponibili i valori seguenti:
<ul>
<li><strong>Acquisti</strong> Selezionare questo valore per le fatture e note di accredito di acquisto.</li>
<li><strong>Vendite</strong> Selezionare questo valore per le fatture e note di accredito di vendita.</li>
<li><strong>Non incluso</strong> Selezionare questo valore per le fatture e le note di accredito che provengono dai paesi esterni alla comunità europea. Questo tipo viene utilizzato solo a fini statistici e non verrà incluso nei report dei libri fiscali finali.</li>
</ul></td>
</tr>
<tr class="even">
<td>Periodo di liquidazione</td>
<td>Selezionare un periodo di liquidazione IVA esistente. Quando viene stampato un libro IVA, se la casella di controllo <strong>Aggiorna</strong> è  selezionata nella pagina <strong>Pagamento IVA</strong>, la data immessa nel campo <strong>Dal</strong> viene confrontata con il periodo di liquidazione selezionato. Questo periodo viene utilizzato anche per identificare i libri e i sezionali IVA da chiudere al momento dell'aggiornamento di una liquidazione IVA per un determinato periodo.</td>
</tr>
<tr class="odd">
<td>Chiuso al</td>
<td>Data di chiusura più recente dai sezionali IVA correlati che appartengono al libro IVA selezionato.</td>
</tr>
<tr class="even">
<td>Vendite UE</td>
<td>Selezionare un libro IVA di tipo <strong>Vendite</strong> e collegarlo al libro IVA corrente di tipo <strong>Acquisti</strong>. Questo campo viene utilizzata se il libro IVA selezionato deve includere le transazioni di acquisto avvenute nell'Unione Europea (UE) dal libro corrente nei report IVA. Il campo non è disponibile per i libri IVA di tipo <strong>Vendite</strong> e <strong>Non incluso</strong>.</td>
</tr>
<tr class="odd">
<td>Codice ATECOFIN</td>
<td>Selezionare il codice imposta per il reporting.</td>
</tr>
<tr class="even">
<td>Stampa riepilogo e pagamenti</td>
<td>Selezionare questa opzione per stampare il riepilogo e il report di pagamento. Il campo è disponibile solo per i libri IVA di tipo <strong>Vendite</strong>.</td>
</tr>
</tbody>
</table>

## <a name="set-up-sales-tax-book-sections"></a>Impostare i sezionali IVA
I sezionali IVA sono un archivio in cui le transazioni di contabilità generale devono essere registrate in base alla natura. La numerazione dei giustificativi viene determinata dai sezionali IVA. Per impostare i sezionali IVA italiani, fare clic su **Imposta** &gt; **Imposta** &gt; **IVA** &gt; **Sezionali IVA italiani**. Nella tabella seguente vengono descritti i campi disponibili nella pagina **Sezionali IVA italiani**.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Campo</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Libro IVA</td>
<td>Selezionare uno dei libri IVA esistenti a cui è collegato il sezionale IVA.</td>
</tr>
<tr class="even">
<td>Sezionale IVA</td>
<td>Immettere l'ID del sezionale IVA.</td>
</tr>
<tr class="odd">
<td>Nome</td>
<td>Consente di immettere una descrizione del sezionale IVA.</td>
</tr>
<tr class="even">
<td>Codice sequenza numerica</td>
<td>Selezionare il codice di sequenza numerica per il sezionale IVA. Il codice di sequenza numerica selezionato dipende dal tipo di libro IVA a cui il sezionale IVA è collegato:
<ul>
<li>Per un libro IVA di tipo <strong>Acquisti</strong>: selezionare i codici di sequenza numerica definiti per i giustificativi fattura di acquisto o i giustificativi note di accredito di acquisto nella pagina <strong>Parametri contabilità fornitori</strong> o i codici di sequenza numerica usati nella pagina <strong>Nomi giornale di registrazione</strong> per i giustificativi che hanno il campo <strong>Libro VAT italiano</strong> impostato su <strong>Acquisti</strong>.</li>
<li>Per un libro IVA di tipo <strong>Vendite</strong>: selezionare i codici di sequenza numerica definiti per i giustificativi fattura di vendita o i giustificativi nota di accredito di vendita o i giustificativi fattura a testo libero o i giustificativi nota di accredito a testo libero nella pagina <strong>Parametri</strong> <strong>contabilità clienti</strong> o i codici di sequenza numerica usati nella pagina <strong>Nomi giornale</strong> di registrazione per i giustificativi che hanno il campo <strong>Libro VAT italiano</strong> impostato su <strong>Vendite</strong>.</li>
<li>Per un libro IVA di tipo  <strong>Non incluso</strong>: Selezionare il codice di sequenza numerica appropriato.</li>
</ul></td>
</tr>
<tr class="odd">
<td>Chiuso al</td>
<td>Immettere la data di fine dell'ultimo periodo di liquidazione IVA chiuso. Questo campo è utilizzato per filtrare i dati nel report IVA.</td>
</tr>
<tr class="even">
<td>Chiudi sezionale IVA italiani</td>
<td>Data di chiusura del libro IVA italiano per un periodo fiscale. Non è possibile registrare o stornare una fattura se la relativa data è precedente alla data di chiusura del periodo fiscale. Questo campo viene aggiornato con la data di chiusura del periodo fiscale. La casella di controllo <strong>Aggiorna</strong> deve anche essere selezionata nella pagina <strong>Pagamento IVA</strong>.</td>
</tr>
</tbody>
</table>

Sono disponibili inoltre il seguente pulsante.

| Pulsante | Descrizione                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
|--------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Creazione | Crea automaticamente tutti i sezionali IVA richiesti per i libri IVA esistenti del tipo **Vendite** e **Acquisti**. I sezionali IVA vengono creati per ciascuna sequenza numerica definita per i giustificativi fattura di acquisto o giustificativi nota di accredito di acquisto o giustificativi fattura di vendita o giustificativi nota di accredito di vendita o giustificativi fattura a testo libero o giustificativi note di accredito a testo libero nella pagina **Parametri contabilità fornitori**, **Parametri contabilità clienti** o **Parametri Gestione progetti e contabilità** e per ciascuna sequenza numerica utilizzata nella pagina **Nomi giornale di registrazione** per i giustificativi che hanno il campo **Libro IVA italiano** impostato su **Acquisti** o **Vendite**. Ogni sezionale IVA creato è collegato automaticamente al libro IVA predefinito. Il libro IVA deve essere creato prima dei sezionali IVA. Se più libri IVA dello stesso tipo di libro IVA  (**Vendite** o **Acquisti**) esistono, il primo libro IVA viene utilizzato per impostazione predefinita. Tuttavia, è possibile modificare manualmente il collegamento. Se nessun libro IVA è disponibile, nessun sezionale IVA viene creato automaticamente. |

## <a name="sales-tax-book-status"></a>Stato libro IVA
Quando si crea un nuovo periodo IVA, per ciascun libro IVA esistente vengono impostate automaticamente le righe corrispondenti. Se si crea un libro IVA aggiuntivo, è possibile creare manualmente anche le righe per i periodi esistenti non ancora chiusi. Fare clic su **Imposta** &gt; **Imposte indirette** &gt; **IVA** &gt; **Periodi liquidazione IVA**, quindi fare clic su **Stato libro IVA**. Nella tabella seguente vengono descritte le schede della pagina **Stato libro IVA**.

| Scheda      | Descrizione                                                                                               |
|----------|-----------------------------------------------------------------------------------------------------------|
| Panoramica | Consente di visualizzare lo stato delle pagine dei libri IVA. Tutti i campi risultano bloccati per gli aggiornamenti manuali.                |
| Generale  | Consente di visualizzare le stesse informazioni disponibili nella scheda **Panoramica** ma solo per il libro IVA selezionato. |

Nella seguente tabella vengono illustrati i campi disponibili.

| Campo             | Descrizione                                                                                      |
|-------------------|--------------------------------------------------------------------------------------------------|
| Libro IVA    | Selezionare l'ID libro IVA impostato nella pagina **Libri IVA italiani**.            |
| Nome              | Immettere il nome del libro IVA.                                                                  |
| Primo numero di pagina | Il primo numero di pagina che verrà utilizzato nel report IVA finale per questo periodo IVA. |
| Modificato in        | Il numero di pagina specificato nella finestra di dialogo **Cambia numero prima pagina**.                |
| Ultimo numero di pagina  | L'ultimo numero di pagina che verrà utilizzato nel report IVA finale per questo periodo IVA.  |
| Periodo di liquidazione | Il periodo di liquidazione utilizzato nel libro IVA.                                        |
| Dal         | Data di inizio del periodo di liquidazione.                                                        |
| Al           | Data di fine del periodo di liquidazione.                                                          |

Sono disponibili inoltre il seguente pulsante.

| Pulsante                   | Descrizione                                                                                                                                            |
|--------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------|
| Cambia numero prima pagina | Apre la finestra di dialogo **Cambia numero prima pagina**, in cui è possibile modificare il numero della prima pagina da utilizzare per il periodo di liquidazione aperto corrente. |

### <a name="change-first-page-number-dialog-box"></a>Cambia numero prima pagina (finestra di dialogo)

Utilizzare la finestra di dialogo **Cambia numero prima pagina** per modificare il numero della prima pagina del report IVA finale per il periodo di liquidazione IVA in corso. Il numero di pagina viene quindi visualizzato nella colonna **Modificato in** della pagina **Stato libro IVA** e utilizzato come numero della prima pagina del report IVA finale che viene stampato per il periodo fiscale corrente. Nella tabella seguente vengono descritti i campi disponibili nella finestra di dialogo **Cambia numero prima pagina**.

| Campo             | Descrizione                                                           |
|-------------------|-----------------------------------------------------------------------|
| Primo numero di pagina | Primo numero di pagina corrente per il libro IVA selezionato.        |
| Modificato in        | Immettere il nuovo primo numero di pagina da utilizzare nel report IVA finale. |

## <a name="using-sales-tax-books"></a>Uso dei libri IVA
Una volta completata l'impostazione, la sezione del libro IVA che corrisponde al codice di sequenza numerica appropriato viene visualizzata nella colonna **Sezione libro IVA** sulla scheda **Sequenze numeriche** delle seguenti pagine:

-   Parametri contabilità clienti
-   Parametri contabilità fornitori
-   Parametri Gestione progetti e contabilità

I numeri di giustificativo assegnati durante la registrazione devono essere ordinati in sequenza per data di registrazione. Le transazioni IVA che utilizzano lo stesso codice di sequenza numerica devono essere registrate in ordine. Se i numeri di giustificativo non vengono ordinati in sequenza, verrà visualizzato un messaggio di errore. Inoltre, se una transazione IVA non viene assegnata ad alcun sezionale IVA durante l'aggiornamento di una fattura, la registrazione verrà interrotta. Quando un giustificativo viene registrato utilizzando un sezionale IVA, gli identificatori del libro IVA e del sezionale IVA correlati vengono salvati nelle transazioni IVA. (Accedere a **Imposta** \> **Richieste di informazioni su IVA** \> **IVA registrata**, quindi selezionare la scheda **Registrazione**). Questi dati possono quindi essere utilizzati durante il reporting IVA. I libri IVA italiani vengono utilizzati per filtrare, raggruppare e ordinare nel report **Imposta sulle vendite (Italia)**.

## <a name="sales-tax-italy-report"></a>Report IVA (Italia)

Per dichiarare l'IVA per l'Italia, attenersi alla seguente procedura.

1. Andare a **Imposta** \> **Dichiarazioni** \> **IVA** \> **IVA (Italia)**.
2. Nel campo **Periodo di liquidazione** selezionare il periodo di liquidazione IVA per cui generare il report.
3. Nel campo **Da data** specificare una data nell'intervallo del periodo di liquidazione per cui si desidera generare il report.
4. Nel campo **Tipo di libro IVA** selezionare il tipo di libro IVA per cui generare il report. Se questo campo è vuoto, il report viene generato per tutti i tipi.
5. Nei campi **Dal libro IVA** e **Al libro IVA** specificare i libri IVA per cui generare il report. Se questi campi sono vuoti, il report viene generato per tutti i libri IVA.
6. Nella sezione **Stampato** selezionare la casella di controllo **Libri IVA** per generare un report che includa i dettagli dei documenti imponibili nei libri IVA.
7. Selezionare la casella di controllo **Riepilogo IVA** per generare un report che includa una sezione di riepilogo dei libri IVA.
8. Selezionare la casella di controllo **Pagamento IVA** per generare un report che includa la pagina **Pagamento IVA** del report.
9. Selezionare la casella di controllo **Includi linee zero** se è stata selezionata la casella di controllo **Libri IVA** e si desidera generare un report che includa dettagli e dettagli a riga zero dei documenti imponibili nei libri IVA.
10. Selezionare la casella di controllo **Includi transazione di storno** se è stata selezionata la casella di controllo **Libri IVA** e si desidera generare un report che includa dettagli e dettagli di transazione di storno dei documenti imponibili nei libri IVA.
11. Nella Scheda dettaglio **Destinazione** impostare una destinazione in cui deve essere generato il report.
12. Nella Scheda dettaglio **Esecuzione in background** impostare i parametri batch se si desidera generare il report in modalità batch.
13. Scegliere **OK** per generare il report.

## <a name="additional-information"></a>Informazioni aggiuntive
A causa dei requisiti fiscali della numerazione sequenziale dei documenti e del modo in cui queste informazioni vengono utilizzate nei libri delle imposte sulle vendite, gli utenti in Italia non dovrebbero avere accesso alle seguenti funzioni:

 - Storna la transazione cliente (pagina **Tutti i clienti**, seleziona **Transazioni** > **Storna**) 
 - Storna la transazione fornitore (pagina **Tutti i fornitori**, seleziona **Transazioni** > **Storna**). 
 
Queste funzioni devono essere nascoste utilizzando la funzionalità Privilegi. Per ulteriori informazioni, vedere [Privilegi di sicurezza basati sul ruolo](../../fin-ops-core/dev-itpro/sysadmin/role-based-security.md#privileges) 

Per nascondere queste funzioni dall'interfaccia utente per tutti i ruoli di sicurezza, attenersi alla seguente procedura:

1.  Vai ad **Amministrazione sistema** > **Sicurezza** > **Configurazione sicurezza**.
2.  Nella scheda **Privilegi**, seleziona **Storna transazioni clienti**.
3.  Seleziona **Voci del menu azioni** > **TransactionReversal_Cust**. 
4.  Seleziona **Nega** per **Leggi**, **Aggiorna**, **Crea**, **Elimina**.

![Configurazione sicurezza.](./media/security-configuration.png)

5.  Nella scheda **Oggetti non pubblicati**, seleziona **Pubblica tutto**.

![Oggetti non pubblicati.](./media/unpublished-objects.png)

7.  Ripeti questi passaggi per il privilegio, **Storna transazioni fornitore**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
