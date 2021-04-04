---
title: Fatture elettroniche dei clienti
description: Questo argomento fornisce informazioni sulla gestione delle fatture elettroniche dei clienti per l'Italia.
author: v-oloski
manager: tfehr
ms.date: 02/24/2021
ms.topic: article
ms.: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: ''
ms.search.region: Italy
ms.author: v-oloski
ms.openlocfilehash: 084c5cdcd4e7a5444883218272029ba7993403c0
ms.sourcegitcommit: 08ac570bece3e4ee4a0f632f51623e328536dfcf
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/08/2021
ms.locfileid: "5557440"
---
# <a name="customer-electronic-invoices"></a>Fatture elettroniche dei clienti

[!include [banner](../includes/banner.md)]

Questo argomento descrive come configurare e utilizzare le funzionalità per la creazione e l'invio di fatture di vendita e progetto in un formato elettronico (FatturaPA).

A partire dalla versione 1.2 del formato FatturaPA, le fatture elettroniche possono essere utilizzate per tutti i tipi di aziende. Tali tipi comprendono le amministrazioni pubbliche, le imprese private e i professionisti.

## <a name="prerequisites"></a>Prerequisiti

L'indirizzo principale della persona giuridica deve essere in Italia.

In questo argomento sono incluse le seguenti informazioni:

- [Informazioni di impostazione](#setup)
- [Gestione dei documenti di base correlati](#relateddoc)
- [Panoramica del registro delle fatture elettroniche](#einvoiceregister)
- [Funzionalità aggiuntiva che riguarda il file XML](#additionalfunctionality)

## <a name="setup"></a><a id="setup"></a>Attrezzaggio

Prima di poter iniziare a lavorare con la funzionalità di fatturazione elettronica, è necessario impostare i seguenti dati:

- [Parametri contabilità clienti](#arparameters)
- [Valuta delle fatture elettroniche](#electronicinvoicecurrency)
- [Parametri fatture elettroniche](#einvoicesparameters)
- [Proprietà documento elettronico](#edproperties)
- [Clienti](#customers)
- [Articoli](#items)
- [Codici Natura](#natura)
- [Tipi di fattura](#invoicetypes)
- [Certificati digitali](#digitalcert)
- [Facoltativo: Destinazione per l'output del file XML](#destination)

### <a name="accounts-receivable-parameters"></a><a id="arparameters"></a>Parametri contabilità clienti

Selezionare le configurazioni utilizzate per creare file XML di fatture elettroniche per fatture di vendita e a testo libero, note di accredito di vendita e a testo libero, fatture progetto e note di accredito di progetto. È possibile trovare queste configurazioni nella scheda **Documento elettronico** della pagina **Parametri contabilità clienti** (**Contabilità clienti** \> **Impostazioni** \> **Parametri contabilità clienti**).

![Scheda Documento elettronico della pagina Parametri contabilità clienti](media/emea-ita-electronic-invocies-AR-parameter-e-invoices.png)

> [!NOTE]
> Le configurazioni devono essere importate prima di poter essere selezionate. Per ulteriori informazioni, vedere [Scaricare configurazioni ER dall'archivio globale del servizio di configurazione](../../fin-ops-core/dev-itpro/analytics/er-download-configurations-global-repo.md).

### <a name="electronic-invoice-currency"></a><a id="electronicinvoicecurrency"></a>Valuta delle fatture elettroniche

Per segnalare fatture nella valuta euro (EUR) in un file XML, impostare l'opzione **Stampa l'importo nella valuta che rappresenta l'euro** su **Sì** nella Scheda dettaglio **Generale** della pagina **Impostazione moduli** in Contabilità clienti (**Contabilità clienti** \> **Impostazioni** \> **Impostazione moduli**) e/o in Gestione progetti e contabilità (**Gestione progetti e contabilità** \> **Impostazioni** \> **Impostazioni moduli**).

> [!NOTE] 
> Se l'opzione **Stampa l'importo nella valuta che rappresenta l'euro** è impostata su **No**, verrà generato un file XML correlato nella valuta della fattura originale. 

Per utilizzare questa funzionalità, importare le seguenti configurazioni di Creazione di report elettronici (ER), o versioni successive, dalla libreria di risorse condivise in Microsoft Dynamics Lifecycle Services (LCS):

- Fattura model.version.231
- Modello fattura mapping.version.231.164
- Fattura di vendita (IT).version.231.91
- Fattura progetto (IT).version.231.90

### <a name="electronic-invoice-parameters"></a><a id="einvoicesparameters"></a>Parametri fatture elettroniche

È necessario impostare parametri per le fatture elettroniche per specificare scenari aziendali e informazioni specifiche dell'impresa.

1. Andare a **Contabilità clienti** \> **Impostazioni** \> **Parametri fatture elettroniche**.
2. Nella scheda **Generale**, specificare il requisito della firma elettronica.
3. Nella scheda **Informazioni società**, specificare le informazioni sull'impresa e il rappresentante fiscale, come richiesto. Queste informazioni sostituiscono le informazioni nel record della persona giuridica.
4. Nella scheda **Registrazione art. 2250 del codice civile**, fornire tutte le informazioni richieste se l'impresa è registrata secondo i termini dell'articolo 2250 del codice civile italiano.
5. Nella scheda **Sequenze numeriche**, inserire sequenze numeriche per i riferimenti **Numero di file univoco eInvoice** e **Numero di trasmissione eInvoice**.

### <a name="electronic-document-properties"></a><a id="edproperties"></a>Proprietà documento elettronico

La funzionalità per le proprietà dei documenti elettronici viene utilizzata per configurare l'output a blocchi di documenti XML per diversi casi aziendali. Di seguito sono riportati alcuni esempi.

- Un numero di partita IVA per i clienti che non si trovano nell'Unione Europea (UE) e non dispongono di codici di partita IVA
- Un indirizzo e-mail certificato (posta elettronica certificata \[PEC\]) per imprese private o professionisti
- Un'imposta di bollo (pagabile e non pagabile da parte del cliente)
- Dati sul rappresentante di un cliente

Perché la funzionalità funzioni, è necessario impostare i seguenti dati:

- Tipi di proprietà di documenti elettronici (**Contabilità clienti** \> **Impostazioni** \> **Tipi di proprietà di documenti elettronici**) e la tabella a cui ciascun tipo di proprietà di documenti è applicabile. Per la funzionalità di fatturazione elettronica, sono utilizzate le tabelle **Clienti** e **Persone giuridiche**.

    ![Impostazione dell'applicabilità nella pagina Tipi di proprietà di documenti elettronici](media/emea-ita-electronic-invocies-electronic-document-property-types.png)

- Valori richiesti nelle tabelle specificate a livello di cliente e persona giuridica:

    - **Cliente:** andare a **Contabilità clienti** \> **Clienti** \> **Tutti i clienti**, quindi, nel riquadro azioni, nella scheda **Cliente** selezionare **Proprietà dei documenti elettronici**.
    - **Persona giuridica:** andare a **Amministrazione organizzazione** \> **Organizzazioni** \> **Persone giuridiche**, quindi, nel riquadro azioni, selezionare **Proprietà dei documenti elettronici**.

I valori specificati sono utilizzati per l'output ai blocchi di file XML. La tabella seguente fornisce informazioni su come e dove vengono utilizzati tali valori.

| Scenario aziendale | Tipo di proprietà di documenti elettronici | Descrizione tipo di proprietà di documenti elettronici | Applicabilità (tabella) | Dove usare i valori | Elemento nel file XML |
|-------------------|-----------------------------------|-----------------------------------------------|-----------------------|--------------|-------------------------|
| Clienti che si trovano al di fuori dell'UE e non dispongono di codici di partita IVA. Per questi clienti, il numero di partita IVA deve essere **00000000000**. | VATnonEU | Esempio: **Cliente, partita IVA non UE** | **CustTable** (Clienti) | Nelle proprietà dei documenti elettronici dei clienti, impostare il campo **Valore** su **00000000000**. | **IdCodice** (**CessionarioCommittente\\DatiAnagrafici\\IdFiscaleIVA** block) |
| Indirizzo e-mail certificato (PEC) per imprese private o professionisti | PEC | Esempio: **Cliente, Indirizzo e-mail certificato** | **CustTable** (Clienti) | Nelle proprietà dei documenti elettronici dei clienti, impostare il campo **Valore** su **\<PEC\>**. | **PECDestinatario** (**DatiTrasmissione** block) |
| Imposta di bollo che non è inclusa nel totale della fattura per le fatture di vendita ed è o non è inclusa per le fatture di progetto | Bollo<p><strong>Nota:</strong> questo tipo di proprietà di documenti viene utilizzato per fatture di ordini cliente, fatture a testo libero e fatture di progetto.</p> | Esempio: **Imposta di bollo, inclusa/non inclusa nei totali della fattura** | **CompanyInfo** (Persone giuridiche) | Nelle proprietà dei documenti elettronici delle persone giuridiche, impostare il campo **Valore** su **\<Charge code/project category that is used for stamp duties\>**.<ul><li>**Codice di addebito** - Il tipo di addebito per questo codice di addebito deve essere **Contabilità generale**.</li><li>**Categoria progetto** - Questa categoria di progetto deve essere fatturabile.</li></ul> | **ImportoBollo** (**DatiBollo** block) |
| Imposta di bollo inclusa nel totale della fattura | BolloPay<p><strong>Nota:</strong> questo tipo di proprietà di documenti viene utilizzato solo per fatture di ordini e fatture a testo libero.</p> | Esempio: **Imposta di bollo, inclusa/non inclusa nei totali della fattura** | **CompanyInfo** (Persone giuridiche) | Nelle proprietà dei documenti elettronici delle persone giuridiche, impostare il campo **Valore** su **\<Charge code/project category that is used for stamp duties\>**.<ul><li>**Codice di addebito** - Il tipo di addebito deve essere **Cliente/fornitore**.</li></ul> | **ImportoBollo** (**DatiBollo** block) |
| Rappresentante | TaxRepPaese, TaxRepCodice, TaxRepDenominazione, TaxRepNome, TaxRepCognome | Qualsiasi descrizione | **CustTable** (Clienti) | Nelle proprietà dei documenti elettronici dei clienti, impostare il campo **Valore** su **IT** per il tipo di proprietà di documenti **TaxRepPaese**. Per altri tipi, immettere i dati per il rappresentante. | **Cognome** (**RappresentanteFiscale** block) |
| Tipi di fattura | DocumentType | Esempio: **fattura, tipo di documento** | **CustInvoiceJour** (Giornale di registrazione fatture cliente), **ProjInvoiceJour** (Fattura di progetto) | Andare a **Contabilità clienti \> Richieste di informazioni e report \> Fatture \> Giornale di registrazione fatture** o **Gestione progetti e contabilità \> Fatture di progetto \> Fatture di progetto** e impostare il campo **Valore** su un tipo di documento, ad esempio **TD16**. | **TipoDocumento** (blocco **DatiGeneraliDocumento**) |

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

Andare a **Gestione progetti e contabilità** \> **Impostazioni** \> **Categorie** \> **Categorie di progetto** per impostare categorie di progetto che hanno un tipo di transazione **Commissioni** o **Spese**. L'ID categoria deve essere uguale al valore definito per il tipo di proprietà documento **Bollo** a livello di entità giuridica. Per ulteriori informazioni, vedere la tabella precedente.

La categoria di progetto del tipo di transazione **Commissioni** può essere utilizzata solo per l'imposta di bollo inclusa nella fattura. La categoria di progetto del tipo di transazione **Spese** può essere utilizzata per l'imposta di bollo che è inclusa in una fattura cliente e che non è inclusa. In entrambi i casi, viene utilizzato il tipo di proprieta di documenti **Bollo**.

Quando si creano righe di giornale di registrazione **Commissioni** o **Spese**, selezionare la categoria definita per l'imposta di bollo e immettere un prezzo di costo. Il sistema considera questo prezzo di costo come l'importo dell'imposta di bollo. Se si immette un prezzo di vendita uguale all'importo del prezzo di costo, il sistema considera tale importo incluso nei totali della fattura. L'importo del prezzo di vendita è uguale a 0 (zero) e la transazione non è inclusa nei totali della fattura.

> [!NOTE]
> È possibile utilizzare solo uno dei tipi di giornale di registrazione (**Commissioni** o **Spese**) per l'imposta di bollo. Un'impresa che utilizza solo l'imposta di bollo pagabile può utilizzare il tipo di giornale di registrazione **Commissioni**. Se un'impresa utilizza un'imposta di bollo sia pagabile che non pagabile, è meglio utilizzare il tipo di giornale di registrazione **Spese**.

### <a name="customers"></a><a id="customers"></a>Clienti

#### <a name="authority-office-field"></a>Campo Ufficio di controllo

È possibile trovare il campo **Ufficio di controllo** nella Scheda dettagli **Dati demografici vendite** di un record cliente (andare a **Contabilità clienti** \> **Clienti** \> **Tutti i clienti** e aprire il record del cliente in modalità **Modifica**).

Il valore di questo campo viene utilizzato per definire il tipo di comunicazione (business to government \[B2G\] o business to business \[B2B\]):

- Se la lunghezza del valore è 6, il cliente è considerato un'amministrazione pubblica (il formato di trasmissione è uguale a **FPA12**).
- Se la lunghezza del valore è 7, il cliente è considerato un'impresa privata o un professionista (il formato di trasmissione è uguale a **FPR12**).

In entrambi i casi, il sistema immette il valore di questo campo nel tag **CodiceDestinatario** nel file XML.

![Campo Ufficio di controllo nella scheda dettaglio Dati demografici vendite di un record cliente](media/emea-ita-electronic-invocies-customer-authority-office.png)

Se il campo **Ufficio di controllo** è vuoto, il sistema considera il cliente come un'impresa privata o un professionista (il formato di trasmissione è uguale a **FPR12**) e immette **0000000** nel tag **CodiceDestinatario** nel file XML. In questo caso, deve essere configurato un indirizzo e-mail certificato (PEC). Per ulteriori informazioni, consultare la tabella nella sezione [Proprietà dei documenti elettronici](#edproperties) vista precedentemente in questo argomento.

#### <a name="activate-automatic-creation-of-electronic-invoices"></a>Attivare la creazione automatica di fatture elettroniche

Andare a **Contabilità clienti** \> **Clienti** \> **Tutti i clienti** e aprire un record cliente in modalità di **Modifica**. Quindi nella Scheda dettaglio **Fattura e consegna**, nella sezione **Fattura elettronica**, trovare l'opzione **Registro eInvoice**. Se questa opzione è impostata su **Sì**, il sistema crea automaticamente il record nella pagina elenco **Fatture elettroniche clienti**. Per ulteriori informazioni, vedere la sezione [Registro delle fatture elettroniche](#einvoiceregister) più avanti in questo argomento.

![Sezione Fattura elettronica nella Scheda dettaglio Fattura e consegna di un record cliente](media/emea-ita-electronic-invocies-customer-e-invoice.png)

Nella sezione **Fattura elettronica** è possibile anche impostare l'opzione **Allegato fattura elettronica** su **Sì**. In questo caso, dopo aver stampato una fattura (durante o dopo la registrazione), il sistema allega automaticamente il file PDF alla fattura e alla fattura elettronica (vedere la sezione [Registro delle fatture elettroniche](#einvoiceregister)) e il file è incluso nel file XML (blocco **Allegati**).

### <a name="items"></a><a id="items"></a>Articoli

Se in una fattura sono presenti righe di prodotti, il blocco **CodiceArticolo** viene compilato in base ai dati del prodotto. Questi dati includono il codice a barre del prodotto, il numero del prodotto interno o il numero dell'articolo e la descrizione dell'articolo esterna. Queste informazioni possono essere trovate selezionando le opzioni nel gruppo **Informazioni correlate** nella scheda **Vendi** del riquadro azioni della pagina **Prodotti rilasciati** (**Gestione informazioni sul prodotto** \> **Prodotti** \> **Prodotti rilasciati**).

Il campo **CodiceTipo** è impostato in base alla seguenti regole:

- Se è presente un codice a barre, questo campo è impostato su **EAN**.
- Se non è presente un codice a barre e il record nella pagina **Descrizione esterna articolo** esiste per il prodotto e il cliente, questo campo è impostato sul valore del campo **Descrizione**.
- Se non è presente un codice a barre e il record nella pagina **Descrizione articolo esterno** non esiste per il prodotto, questo campo è impostato sul testo **Codice Art. fornitore**.

Il campo **CodiceValore** è impostato in base alla seguenti regole:

- Se è presente un codice a barre, questo campo è impostato sul codice a barre.
- Se non è presente un codice a barre e il record nella pagina **Descrizione esterna articolo** esiste per il prodotto e il cliente, questo campo è impostato sul valore del campo **Numero articolo esterno**.
- Se non è presente un codice a barre e il record nella pagina **Descrizione esterna articolo** non esiste per il prodotto e il cliente, questo campo è impostato sul valore del campo **Numero articolo**.

### <a name="natura-codes"></a><a id="natura"></a>Codici Natura

È possibile associare manualmente i codici Natura a codici IVA correlati oppure lasciare che il sistema determini automaticamente i codici Natura appropriati per le transazioni. I codici Natura associati manualmente hanno una maggiore priorità rispetto ai codici Natura determinati automaticamente e li sovrascriveranno.

Seguire questi passaggi per definire i codici Natura e associarli manualmente ai codici IVA.

1. Selezionare **Imposta** \> **Impostazione** \> **IVA** \> **Codici Natura**.
2. Creare un record.
3. Nel campo **Codice Natura** immettere un codice Natura valido.
4. Nel campo **Descrizione**, immettere una spiegazione dell'utilizzo del codice.
5. Ripetere i passaggi da 2 a 4 per creare tutti i codici Natura aggiuntivi necessari per coprire tutte le operazioni aziendali correlate.
6. Selezionare **Imposta** \> **Imposte indirette** \> **IVA** \> **Codici IVA** e selezionare un codice IVA necessario.
7. Nella scheda Dettaglio **Generale**, nel campo **Codice Natura**, selezionare uno dei codici Natura appena creati.

![Impostazione del campo Codice Natura nella pagina Codici IVA](media/emea-ita-natura.jpg)

### <a name="reverse-charge-groups"></a>Gruppi reverse charge

I gruppi reverse charge sono necessari quando una società utilizza la funzionalità di reverse charge. Sono utilizzati per determinare automaticamente i codici Natura specifici per le operazioni reverse charge.

Per definire specifici gruppi reverse charge per specifici prodotti o categorie, selezionare **Imposta** \> **Impostazioni** \> **Gruppi di articoli reverse charge**.

![Pagina dei gruppi di articoli di reverse charge](media/emea-ita-FatturaPA-161-RC-groups.png)

Inoltre, è necessario impostare parametri specifici dell'applicazione che utilizzano questi gruppi reverse charge.

Per ulteriori informazioni su questa funzionalità, vedere la sezione "Configurazione di reverse charge" in [Hotfix specifico del paese per supportare le modifiche nel formato "FatturaPA" delle fatture elettroniche italiane in Microsoft Dynamics 365 Finance](https://support.microsoft.com/help/4569342/a-country-specific-hotfix-to-support-changes-in-fatturapa-format-of-it).

### <a name="invoice-types"></a><a id="invoicetypes"></a>Tipi di fattura

I seguenti tipi di documenti di fatturazione sono supportati e verranno compilati automaticamente:

- TD01 - Fattura
- TD04 - Nota di accredito
- TD05 - Nota di addebito
- TD20 - Fatturazione automatica

Se un tipo di documento richiesto non è elencato, è possibile modificare manualmente il tipo di documento nei giornali di registrazione fatture. Per attivare la rettifica manuale completare la seguente impostazione:

- Definizione di proprietà di documenti elettronici
- Registrazione del tipo di documento fattura

Per ulteriori informazioni, vedere la sezione "Configurazione dei tipi di fatture" in [Hotfix specifico del paese per supportare le modifiche nel formato "FatturaPA" delle fatture elettroniche italiane in Microsoft Dynamics 365 Finance](https://support.microsoft.com/help/4569342/a-country-specific-hotfix-to-support-changes-in-fatturapa-format-of-it).

### <a name="digital-certificates"></a><a id="digitalcert"></a>Certificati digitali

Selezionare **Contabilità clienti** \> **Impostazioni** \> **Certificati di firma elettronica** per firmare elettronicamente fatture elettroniche utilizzando un certificato di tipo **Società** o **Utente**.

![Pagina Certificati di firma elettronica](media/emea-ita-electronic-invocies-certificate.png)

La parte che emette le fatture deve utilizzare un certificato di firma qualificato per firmare ogni file FatturaPA che viene trasmessa al sistema di scambio (Sistema di Interscambio \[Sdl\]). Un certificato di firma qualificato può essere ottenuto da uno dei certificatori nell'[elenco di certificatori autorizzati](http://www.digitpa.gov.it/firma-digitale/certificatori-accreditati).

Microsoft Dynamics 365 Finance supporta il formato di firma **XAdES-BES**. Per consentire a Finance di supportare FatturaPA, attenersi alla seguente procedura.

1. Nei computer client installare e configurare certificati digitali che hanno chiavi private e pubbliche nel campo **Macchina server delle applicazioni** del nodo **Personale**.

    > [!NOTE]
    > È possibile completare l'installazione e la configurazione utilizzando la funzionalità standard di Windows.

2. Definire certificati a livello di impresa e certificati a livello di utente, come richiesto.

### <a name="destination-for-xml-file-output"></a><a id="destination"></a>Destinazione per l'output dei file XML

Se i file XML devono essere inviati come output a una posizione specifica quando vengono registrate le fatture (ad esempio, se devono essere inviate a una cartella SharePoint), impostare un tipo di documento, quindi impostare una destinazione. Per ulteriori informazioni su questi passaggi, vedere [Configurare la gestione dei documenti](../../fin-ops-core/fin-ops/organization-administration/configure-document-management.md) e [Destinazioni dei report elettronici (ER)](../../dev-itpro/analytics/electronic-reporting-destinations.md).

> [!NOTE]
> L'opzione **Stampa fattura** deve essere impostata su **Sì**. Se la destinazione è impostata, lo stato del record della fattura elettronica per la fattura viene automaticamente impostato su **Inviata**.

## <a name="maintain-related-base-documents"></a><a id="relateddoc"></a>Gestione dei documenti di base correlati

Le imprese possono immettere ulteriori informazioni su alcuni documenti di base correlati alle fatture. Questa sezione descrive come inserire dati aggiuntivi, come il codice identificativo della procedura di gara (Codice Identificativo di Gara \[CIG\]) e il codice univoco del progetto (Codice Unico di Progetto \[CUP\]) gestito dal Comitato Interministeriale per la Programmazione Economica.

Di seguito sono riportati alcuni esempi.

- Il blocco **DatiOrdineAcquisto** contiene informazioni correlate all'ordine fornitore.
- Il blocco **DatiContratto** contiene informazioni correlate al contratto.
- Il blocco **DatiConvenzione** contiene informazioni correlate all'accordo.
- Il blocco **DatiRicezione** contiene le informazioni relative ai dati sulla fase di ricezione. Questi dati sono presenti nel sistema di gestione utilizzato dalle PA (agenzie fiscali).
- Il blocco **DatiFattureCollegate** contiene informazioni correlate alle fatture precedentemente trasmesse e alle quali è collegato il documento corrente. Questo blocco viene utilizzato nei casi in cui una nota di accredito e/o una fattura vengono inoltrate in seguito a precedenti fatture di pagamento anticipato.

Per consentire al sistema di immettere informazioni in questi blocchi, impostare i seguenti campi:

- Nella pagina **Ordine cliente** (**Contabilità** \> **Ordini** \> **Tutti gli ordini cliente**) nella visualizzazione **Intestazione**, nella Scheda dettaglio **Impostazione** impostare i campi nella sezione **Documento di base**.
- Nella pagina **Fattura a testo libero** (**Contabilità** \> **Fatture** \> **Tutte le fatture a testo libero**) nella visualizzazione **Intestazione**, nella Scheda dettaglio **Generale** impostare i campi nella sezione **Documento di base**.
- Nella pagina **Proposta di progetto** (**Gestione progetti e contabilità** \> **Progetti** \> **Tutti i progetti**), nel riquadro azioni, nel gruppo **Fatturazione** della scheda **Gestione**, selezionare **Proposta di fatturazione**, quindi impostare i campi nella sezione **Documento di base**.

> [!NOTE]
> Come mostrato nella tabella seguente, i dati dei campi nella sezione **Documento di base** sono inviati come output da blocchi diversi, a seconda del valore del campo **Documento di base**.
> 
> | Valore del campo Documento di base | Blocca da cui vengono inviati i dati |
> |---|---|
> | Ordine di pagamento | DatiOrdineAcquisto |
> | Contratto | DatiContratto |
> | Contratto | DatiConvenzione |
> | Sistema di gestione | DatiRicezione |
> | Fattura originale | DatiFattureCollegate |

Per ciascun documento di base, gli utenti possono aggiungere dettagli sul numero e sulla data del documento, il CIG (Codice Identificativo di Gara), il CUP (Codice Unico di Progetto) e il codice dell'accordo.

### <a name="base-documents-for-public-sector-companies"></a>Documenti di base per aziende del settore pubblico

In Italia, esiste un requisito legale che obbliga le aziende del settore pubblico a fornire la tracciabilità dei codici delle procedure di gara (CIG) e dei codici dei progetti (CUP) durante la fatturazione e i pagamenti. Per fornire la tracciabilità, viene implementato un controllo aggiuntivo dei codici CIG e CUP per le aziende del settore pubblico. Per ulteriori informazioni su questa funzionalità, vedere [Localizzazione italiana - Tracciabilità dei pagamenti](emea-ita-payment-traceability.md).

## <a name="electronic-invoice-register"></a><a id="einvoiceregister"></a>Registro delle fatture elettroniche

Per visualizzare tutte le fatture elettroniche dei clienti ed eseguire varie azioni, andare a **Contabilità clienti** \> **Fatture** \> **Fatture elettroniche** \> **Fatture elettroniche**.

Nella pagina **Fatture elettroniche clienti** è possibile effettuare le seguenti azioni:

- Selezionare **Seleziona** per selezionare le fatture, in base a vari criteri. Questa funzione è utile se l'opzione **Registro eInvoice** è impostata su **No**.
- Selezionare **Crea XML**, **Crea firma** e **Invia** per creare file XML e una firma digitale per le fatture selezionate e inviare le fatture.
- Selezionare **Esporta** per esportare una fattura selezionata in un file XML.

    > [!NOTE]
    > Il sistema invia un file alla cartella impostata sul computer. Le impostazioni relative alla destinazione non sono utilizzate.

- Selezionare la scheda **Dettagli** per visualizzare i dettagli della fattura elettronica.

> [!NOTE]
> La pagina **Fatture elettroniche** (**Gestione progetti e contabilità** \> **Fatture progetto** \> **Fatture elettroniche** \> **Fatture elettroniche**) è simile alla pagina **Fatture elettroniche clienti** e ha le stesse funzioni.

![Pagina Fatture elettroniche clienti](media/emea-ita-electronic-invocies-electronic-customer-invoices.png)

## <a name="additional-functionality-that-affects-the-xml-file"></a><a id="additionalfunctionality"></a>Funzionalità aggiuntiva che riguarda il file XML

### <a name="tax-invoice-for-goods-delivered-for-free"></a>Fattura fiscale per le merci consegnate gratuitamente

Per informazioni su come configurare e utilizzare questa funzionalità, vedere [Fattura fiscale per le merci consegnate gratuitamente](emea-ita-exil-goods-for-free.md).

Nella pagina **Distribuzione** (**Vendite e marketing** \> **Impostazioni** \> **Distribuzione**), se **Merci gratuite** è selezionato nel campo **Motivo della consegna** e il campo **Conto fattura** è vuoto, l'elemento **TipoCessionePrestazione** viene inviato come output nel file XML.

### <a name="intent-letters--invoicing-of-usual-exporters"></a>Lettere di intenti - Fatturazione di esportatori abituali

Per informazioni su come configurare e utilizzare questa funzionalità, vedere [Lettere di intenti - Fatturazione di esportatori abituali](emea-ita-exil-intent-letter.md).

Se viene impostata una lettera di intenti per un cliente, l'elemento **Causale** (blocco **DatiGeneraliDocumento**) che ha il numero della lettera di intenti viene inviato come output nel file XML.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
