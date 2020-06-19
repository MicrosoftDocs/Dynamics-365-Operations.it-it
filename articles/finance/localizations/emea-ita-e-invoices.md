---
title: Fatture elettroniche dei clienti
description: Questo argomento fornisce informazioni sulla gestione delle fatture elettroniche dei clienti per l'Italia.
author: v-oloski
manager: ''
ms.date: 05/21/2020
ms.topic: article
ms.: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: ''
ms.search.scope: Core, Operations
ms.search.region: Italy
ms.author: v-oloski
ms.openlocfilehash: fee07dbf679a25515760839115e5fb61c8685722
ms.sourcegitcommit: ace6451fde3e4b20cbcaa6279fa1da4d7151ad1e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/28/2020
ms.locfileid: "3409559"
---
# <a name="customer-electronic-invoices"></a>Fatture elettroniche dei clienti

[!include [banner](../includes/banner.md)]

Questo argomento descrive come impostare e utilizzare le funzionalità per la creazione e l'invio di fatture di vendita e progetto in un formato elettronico (FatturaPA).

La versione 1.2 delle fatture elettroniche FatturaPA può essere utilizzata per tutti i tipi di aziende, comprese le amministrazioni pubbliche, le imprese private e i professionisti. 

> [!NOTE] 
> L'indirizzo principale della persona giuridica deve essere in Italia.

In questo argomento sono incluse le seguenti informazioni:

- Informazioni di impostazione
- Come compilare i dati per l'output di un codice identificativo della procedura di gara (Codice Identificativo di Gara \[CIG\]) e un codice unico di progetto (Codice Unico di Progetto \[CUP\])
- Panoramica del registro delle fatture elettroniche.

## <a name="setup"></a>Attrezzaggio

Prima di poter iniziare a lavorare con la funzionalità di fatturazione elettronica, è necessario impostare i seguenti dati:

- [Parametri contabilità clienti](#arparameters)
- [Parametri fatture elettroniche](#einvoicesparameters)
- [Proprietà dei documenti elettronici](#edproperties)
- [Clienti](#customers)
- [Certificati digitali](#digitalcert)
- Facoltativo: [Destinazione per l'output del file XML](#destination)

### <a name="accounts-receivable-parameters"></a><a name="arparameters"></a>Parametri contabilità clienti

Selezionare le configurazioni utilizzate per creare file XML di fatture elettroniche per fatture di vendita e a testo libero, note di accredito di vendita e a testo libero, fatture progetto e note di accredito di progetto. È possibile trovare queste configurazioni nella scheda **Documento elettronico** della pagina **Parametri contabilità clienti** (**Contabilità clienti \> Impostazioni \> Parametri contabilità clienti**).

![Scheda Documento elettronico della pagina Parametri contabilità clienti](media/emea-ita-electronic-invocies-AR-parameter-e-invoices.png)

> [!NOTE] 
> Le configurazioni devono essere importate prima di poter essere selezionate. Per ulteriori informazioni, vedere [Scaricare le configurazioni per la creazione di report elettronici da Lifecycle Services](../../dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md).

### <a name="electronic-invoice-parameters"></a><a name="einvoicesparameters"></a>Parametri fatture elettroniche

Utilizzare questi parametri per specificare scenari aziendali e informazioni specifiche dell'impresa. 

1. Andare a **Contabilità clienti \> Impostazioni \> Parametri fatture elettroniche**.
2. Nella scheda **Generale**, specificare il requisito della firma elettronica.
3. Nella scheda **Informazioni società**, specificare le informazioni sull'impresa e il rappresentante fiscale, come richiesto. Queste informazioni sostituiscono le informazioni nel record della persona giuridica.
4. Nella scheda **Registrazione art. 2250 del codice civile**, fornire tutte le informazioni richieste se l'impresa è registrata secondo i termini dell'articolo 2250 del codice civile italiano.
5. Nella scheda **Sequenze numeriche**, inserire sequenze numeriche per i riferimenti **Numero di file univoco eInvoice** e **Numero di trasmissione eInvoice**.

### <a name="electronic-document-properties"></a><a name="edproperties"></a>Proprietà documento elettronico

La funzionalità Proprietà dei documenti elettronici viene utilizzata per impostare l'output a blocchi di documenti XML per diversi casi aziendali. Di seguito sono riportati alcuni esempi. 

- Un numero di partita IVA per i clienti che non si trovano nell'Unione Europea (UE) e non dispongono di codici di partita IVA
- Un indirizzo e-mail certificato (posta elettronica certificata \[PEC\]) per imprese private o professionisti
- Un'imposta di bollo (pagabile e non pagabile da parte del cliente)
- Dati sul rappresentante di un cliente 

Perché la funzionalità funzioni, è necessario impostare i seguenti dati:

- Tipi di proprietà di documenti elettronici (**Contabilità clienti \> Impostazioni \> Tipi di proprietà di documenti elettronici**) e la tabella a cui ciascun tipo di proprietà di documenti è applicabile. Per la funzionalità di fatturazione elettronica, sono utilizzate le tabelle **Clienti** e **Persone giuridiche**.

    ![Impostazione dell'applicabilità nella pagina Tipi di proprietà di documenti elettronici](media/emea-ita-electronic-invocies-electronic-document-property-types.png)

- Valori richiesti nelle tabelle specificate a livello di cliente e persona giuridica:

    - **Cliente:** andare a **Contabilità clienti \> Clienti \> Tutti i clienti**, quindi, nel riquadro azioni, nella scheda **Cliente**, selezionare **Proprietà dei documenti elettronici**.
    - **Persona giuridica:** andare a **Amministrazione organizzazione \> Organizzazioni \> Persone giuridiche**, quindi, nel riquadro azioni, selezionare **Proprietà dei documenti elettronici**.

I valori specificati sono utilizzati per l'output ai blocchi di file XML. La tabella seguente fornisce informazioni su come e dove vengono utilizzati tali valori.

| Scenario aziendale | Tipo di proprietà di documenti elettronici | Descrizione tipo di proprietà di documenti elettronici | Applicabilità (tabella) | Dove usare i valori | Elemento nel file XML |
|-------------------|-----------------------------------|-----------------------------------------------|-----------------------|--------------|-------------------------|
| Clienti che si trovano al di fuori dell'UE e non dispongono di codici di partita IVA. Per questi clienti, il numero di partita IVA deve essere **00000000000**. | VATnonEU | Esempio: **Cliente, partita IVA non UE** | **CustTable** (Clienti) | Nelle proprietà dei documenti elettronici dei clienti, impostare il campo **Valore** su **00000000000**. | **IdCodice** (**CessionarioCommittente\\DatiAnagrafici\\IdFiscaleIVA** block) |
| Indirizzo e-mail certificato (PEC) per imprese private o professionisti | PEC | Esempio: **Cliente, Indirizzo e-mail certificato** | **CustTable** (Clienti) | Nelle proprietà dei documenti elettronici dei clienti, impostare il campo **Valore** su **\<PEC\>**. | **PECDestinatario** (**DatiTrasmissione** block) |
| Imposta di bollo che non è inclusa nel totale della fattura per le fatture di vendita ed è o non è inclusa per le fatture di progetto | Bollo<p><strong>Nota:</strong> questo tipo di proprietà di documenti viene utilizzato per fatture di ordini cliente, fatture a testo libero e fatture di progetto.</p> | Esempio: **Imposta di bollo, inclusa/non inclusa nei totali della fattura** | **CompanyInfo** (Persone giuridiche) | Nelle proprietà dei documenti elettronici delle persone giuridiche, impostare il campo **Valore** su **\<Charge code/Project category that is used for stamp duties\>**.<ul><li>**Codice di addebito** - Il tipo di addebito per questo codice di addebito deve essere **Contabilità generale**.</li><li>**Categoria progetto** - Questa categoria di progetto deve essere fatturabile.</li></ul> | **ImportoBollo** (**DatiBollo** block) |
| Imposta di bollo inclusa nel totale della fattura | BolloPay<p><strong>Nota:</strong> questo tipo di proprietà di documenti viene utilizzato solo per fatture di ordini e fatture a testo libero.</p> | Esempio: **Imposta di bollo, inclusa/non inclusa nei totali della fattura** | **CompanyInfo** (Persone giuridiche) | Nelle proprietà dei documenti elettronici delle persone giuridiche, impostare il campo **Valore** su **\<Charge code/Project category that is used for stamp duties\>**.<ul><li>**Codice di addebito** - Il tipo di addebito deve essere **Cliente/fornitore**.</li></ul> | **ImportoBollo** (**DatiBollo** block) |
| Rappresentante | TaxRepPaese, TaxRepCodice, TaxRepDenominazione, TaxRepNome, TaxRepCognome | Qualsiasi descrizione | **CustTable** (Clienti) | Nelle proprietà dei documenti elettronici dei clienti, impostare il campo **Valore** su **IT** per il tipo di proprietà di documenti **TaxRepPaese**. Per altri tipi, immettere i dati del rappresentante. | **Cognome** (**RappresentanteFiscale** block) |

> [!NOTE] 
> La tabella precedente utilizza la seguente soluzione rapida:
>
> - "Proprietà dei documenti elettronici dei clienti" si riferisce alla pagina **Proprietà dei documenti elettronici** che viene aperta selezionando **Proprietà dei documenti elettronici** nella scheda **Cliente** del riquadro azioni nella pagina **Tutti i clienti** (**Contabilità clienti \> Clienti \> Tutti i clienti**).
> - "roprietà dei documenti elettronici delle persone giuridiche" si riferisce alla pagina **Proprietà dei documenti elettronici** che viene aperta selezionando **Proprietà dei documenti elettronici** nel riquadro azioni della pagina **Persone giuridiche** (**Amministrazione organizzazione \> Organizzazioni \> Persone giuridiche**).
> 
> Nella pagina elenco **Tipi di proprietà di documenti elettronici**, il campo **Descrizione** viene automaticamente compilato quando un utente immette informazioni nei campi **Descrizione gruppo** e **Descrizione**.
>
> Il tipo di proprietà di documenti elettronici deve avere lo stesso codice specificato nella tabella.

#### <a name="use-project-categories-for-stamp-duty"></a>Utilizzare categorie di progetto per l'imposta di bollo

Andare a **Gestione progetti e contabilità \> Impostazioni \> Categorie \> Categorie di progetto** per impostare categorie di progetto che hanno un tipo di transazione **Commissioni** o **Spese**. L'ID categoria deve essere uguale al valore definito per **Bollo** a livello di entità giuridica. Per ulteriori informazioni, vedere la tabella precedente.

La categoria di progetto del tipo di transazione **Commissioni** può essere utilizzata solo per l'imposta di bollo inclusa nella fattura. La categoria di progetto del tipo di transazione **Spese** può essere utilizzata per l'imposta di bollo che è inclusa e non inclusa in una fattura cliente. In entrambi i casi, viene utilizzato il tipo di proprieta di documenti **Bollo**.

Quando si creano righe di giornale di registrazione **Commissioni** o **Spese**, selezionare la categoria definita per l'imposta di bollo e immettere un prezzo di costo. Il sistema considera questo prezzo di costo come l'importo dell'imposta di bollo. 'Se si immette un prezzo di vendita uguale all'importo del prezzo di costo, il sistema considera tale importo incluso nei totali della fattura. L'importo del prezzo di vendita è uguale a 0 (zero) e la transazione non è inclusa nei totali della fattura. 

> [!NOTE]
> È possibile utilizzare solo uno dei tipi di giornale di registrazione (**Commissioni** o **Spese**) per l'imposta di bollo. Un'impresa che utilizza solo l'imposta di bollo pagabile può utilizzare il tipo di giornale di registrazione **Commissioni**. Se un'impresa utilizza un'imposta di bollo sia pagabile che non pagabile, è meglio utilizzare il tipo di giornale di registrazione **Spese**.

### <a name="customers"></a><a name="customers"></a>Clienti 

#### <a name="authority-office-field"></a>Campo Ufficio di controllo

È possibile trovare il campo **Ufficio di controllo** nella Scheda dettagli **Dati demografici vendite** di un record cliente (andare a **Contabilità clienti** \> **Clienti** \> **Tutti i clienti** e aprire il record del cliente in modalità **Modifica**).

Il valore di questo campo viene utilizzato per definire il tipo di comunicazione (business to government \[B2G\] o business to business \[B2B\]):

- Se la lunghezza del valore è 6, il cliente è considerato un'amministrazione pubblica (il formato di trasmissione è uguale a **FPA12**).
- Se la lunghezza del valore è 7, il cliente è considerato un'impresa privata o un professionista (il formato di trasmissione è uguale a **FPR12**).

In entrambi i casi, il sistema immette il valore di questo campo nel tag **CodiceDestinatario** nel file XML.

![Campo Ufficio di controllo nella scheda dettaglio Dati demografici vendite di un record cliente](media/emea-ita-electronic-invocies-customer-authority-office.png)

Se il campo **Ufficio di controllo** è vuoto, il sistema considera il cliente come un'impresa privata o un professionista (il formato di trasmissione è uguale a **FPR12**) e immette **0000000** nel tag **CodiceDestinatario** nel file XML. In questo caso, deve essere impostato un indirizzo e-mail certificato (PEC). Per ulteriori informazioni, consultare la tabella nella sezione [Proprietà dei documenti elettronici](/electronic-document-properties) vista precedentemente in questo argomento.

#### <a name="activate-automatic-creation-of-e-invoices"></a>Attivare la creazione automatica di fatture elettroniche

Selezionare **Contabilità clienti** \> **Clienti** \> **Tutti i clienti**. Aprire un record cliente in modalità **Modifica** e quindi nella Scheda dettaglio **Fattura e consegna**, nella sezione **Fattura elettronica**, trovare l'opzione **Registro eInvoice**. Se questa opzione è impostata su **Sì**, il sistema crea automaticamente il record nella pagina elenco **Fatture elettroniche clienti**. Per ulteriori informazioni, vedere [Panoramica della pagina delle fatture elettroniche](/overview-of-electronic-invoices-page).

![Sezione Fattura elettronica nella Scheda dettaglio Fattura e consegna di un record cliente](media/emea-ita-electronic-invocies-customer-e-invoice.png)

### <a name="digital-certificates"></a><a name="digitalcert"></a>Certificati digitali

Andare a **Contabilità clienti** \> **Impostazioni** \> **Certificati di firma elettronica** per firmare elettronicamente fatture elettroniche utilizzando un certificato di tipo **Società** o **Utente**.

![Pagina Certificati di firma elettronica](media/emea-ita-electronic-invocies-certificate.png)

Ogni [file FatturaPA](http://www.fatturapa.gov.it/export/fatturazione/en/b-2.htm) che viene trasmesso al [Sistema di scambio](http://www.fatturapa.gov.it/export/fatturazione/en/sdi.htm) deve essere firmato dalla parte che emette la fattura, utilizzando un certificato di firma qualificato.

Un certificato di firma qualificato può essere ottenuto da uno dei certificatori nell'[elenco di certificatori autorizzati](http://www.digitpa.gov.it/firma-digitale/certificatori-accreditati).

Microsoft Dynamics 365 Finance supporta il formato di firma **XAdES-BES**. Per consentire a Finance di supportare FatturaPA, attenersi alla seguente procedura.

1. Nei computer client, installare e configurare certificati digitali che hanno chiavi private e pubbliche nella **macchina server delle applicazioni** nel nodo **Personale**.

    > [!NOTE] 
    > È possibile completare l'installazione e la configurazione utilizzando la funzionalità standard di Windows.

2. Definire certificati a livello di impresa e certificati a livello di utente, come richiesto.

### <a name="destination-for-xml-file-output"></a><a name="destination"></a>Destinazione per l'output dei file XML

Se i file XML devono essere inviati come output a una posizione specifica quando vengono registrate le fatture (ad esempio, a una cartella SharePoint), impostare un tipo di documento, quindi impostare una destinazione. Per ulteriori informazioni su questi passaggi, vedere [Configurare la gestione dei documenti](../../fin-ops-core/fin-ops/organization-administration/configure-document-management.md) e [Destinazioni dei report elettronici (ER)](../../dev-itpro/analytics/electronic-reporting-destinations.md).

> [!NOTE] 
> L'opzione **Stampa fattura** deve essere impostata su **Sì**. Se la destinazione è impostata, lo stato del record della fattura elettronica per questa fattura viene automaticamente impostato su **Inviata**.

## <a name="fill-in-data-for-related-documents"></a>Immettere dati per documenti correlati

Le imprese possono immettere ulteriori informazioni su alcuni documenti di base correlati alle fatture. Di seguito sono riportati alcuni esempi. 

- Il blocco **DatiOrdineAcquisto** contiene informazioni correlate all'ordine fornitore. 
- Il blocco **DatiContratto** contiene informazioni correlate al contratto. 
- Il blocco **DatiConvenzione** contiene informazioni correlate all'accordo. 
- Il blocco **DatiRicezione** contiene informazioni correlate ai dati sulla fase di ricevimento presenti nel sistema di gestione utilizzato dall'amministrazione pubblica (agenzie fiscali). 
- Il blocco **DatiFattureCollegate** contiene informazioni correlate alle fatture precedentemente trasmesse e alle quali è collegato il presente documento. Questo blocco viene utilizzato nei casi in cui una nota di accredito e/o una fattura vengono inoltrate in seguito a precedenti fatture di pagamento anticipato.

Per consentire al sistema di immettere informazioni in questi blocchi, impostare i seguenti campi:

- Nella pagina **Ordine cliente** (**Contabilità** \> **Ordini** \> **Tutti gli ordini cliente**) nella visualizzazione **Intestazione**, nella Scheda dettaglio **Impostazione** impostare i campi nella sezione **Documento di base**.
- Nella pagina **Fattura a testo libero** (**Contabilità** \> **Fatture** \> **Tutte le fatture a testo libero**) nella visualizzazione **Intestazione**, nella Scheda dettaglio **Generale** impostare i campi nella sezione **Documento di base**.
- Nella pagina **Proposta di progetto** (**Gestione progetti e contabilità** \> **Progetti** \> **Tutti i progetti**), nel riquadro azioni, nel gruppo **Fatturazione** della scheda **Gestione**, selezionare **Proposta di fatturazione**, quindi impostare i campi nella sezione **Documento di base**.


> [!NOTE]
> I dati dei campi nella sezione **Documento di base** sono inviati come output da blocchi diversi, a seconda del valore del campo **Documento di base**.
> 
> | Valore del campo Documento di base | Blocca da cui vengono inviati i dati |
> |---|---|
> | Ordine di pagamento | DatiOrdineAcquisto |
> | Contratto | DatiContratto |
> | Contratto | DatiConvenzione |
> | Sistema di gestione | DatiRicezione |
> | Fattura originale | DatiFattureCollegate

Per ciascun documento di base, gli utenti possono aggiungere dettagli sul numero e sulla data del documento, il CUP (Codice Unico di Progetto, gestito dal Ministero dello sviluppo economico), il CIG (Codice Identificativo di Gara) e il codice dell'accordo.

## <a name="electronic-invoice-register"></a>Registro delle fatture elettroniche 

Per visualizzare tutte le fatture elettroniche dei clienti ed eseguire varie azioni, andare a **Contabilità clienti** \> **Fatture** \> **Fatture elettroniche** \> **Fatture elettroniche** per aprire la pagina **Fatture elettroniche clienti**.

In questa pagina, è possibile eseguire le azioni riportate di seguito:

- Selezionare **Seleziona** per selezionare le fatture, in base a vari criteri. Questa funzione è utile se l'opzione **Registro eInvoice** è impostata su **No**.
- Selezionare **Crea XML**, **Crea firma** e **Invia** per creare file XML e una firma digitale per le fatture selezionate e inviarle.
- Selezionare **Esporta** per esportare una fattura selezionata in un file XML.

    > [!NOTE]
    > Il sistema invia un file alla cartella impostata sul computer. Le impostazioni relative alla destinazione non sono utilizzate.

- Selezionare la scheda **Dettagli** per visualizzare i dettagli della fattura elettronica.

> [!NOTE]
> La pagina **Fatture elettroniche** (**Gestione progetti e contabilità** \> **Fatture progetto** \> **Fatture elettroniche** \> **Fatture elettroniche**) è simile alla pagina **Fatture elettroniche clienti** e ha le stesse funzioni.

![Pagina Fatture elettroniche clienti](media/emea-ita-electronic-invocies-electronic-customer-invoices.png)
