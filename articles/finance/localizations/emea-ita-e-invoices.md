---
title: Fatture elettroniche dei clienti
description: Questo argomento fornisce informazioni sulla gestione delle fatture elettroniche dei clienti per l'Italia.
author: v-oloski
manager: ''
ms.date: 10/15/2020
ms.topic: article
ms.: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: ''
ms.search.scope: Core, Operations
ms.search.region: Italy
ms.author: v-oloski
ms.openlocfilehash: 1775eaf7f48035cc92062c6050d3df948345438d
ms.sourcegitcommit: d6250ee5ced43be39e789324a895fd1c07178935
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/19/2020
ms.locfileid: "4039835"
---
# <a name="customer-electronic-invoices"></a>Fatture elettroniche dei clienti

[!include [banner](../includes/banner.md)]

Questo argomento descrive come impostare e utilizzare le funzionalità per la creazione e l'invio di fatture di vendita e progetto in un formato elettronico (FatturaPA).

La versione 1.2 delle fatture elettroniche FatturaPA può essere utilizzata per tutti i tipi di aziende, comprese le amministrazioni pubbliche, le imprese private e i professionisti.

> [!NOTE]
> L'indirizzo principale della persona giuridica deve essere in Italia.

In questo argomento sono incluse le seguenti informazioni:

- [Informazioni di impostazione](#setup)
- [Come compilare i dati per l'output di un codice identificativo della procedura di gara (Codice Identificativo di Gara \[CIG\]) e un codice unico di progetto (Codice Unico di Progetto \[CUP\])](#releteddoc)
- [Panoramica del registro delle fatture elettroniche](#einvoiceregister)
- [Funzionalità aggiuntiva che riguarda il file XML](#additionalfunctionality)
- [Funzionalità disponibile nell'aggiornamento mensile 10.0.12 e nelle versioni successive](#fatturaPA)

## <a name="setup"></a><a name="setup"></a>Attrezzaggio

Prima di poter iniziare a lavorare con la funzionalità di fatturazione elettronica, è necessario impostare i seguenti dati:

- [Parametri contabilità clienti](#arparameters)
- [Parametri fatture elettroniche](#einvoicesparameters)
- [Proprietà documento elettronico](#edproperties)
- [Clienti](#customers)
- [Articoli](#items)
- [Certificati digitali](#digitalcert)
- [Facoltativo: Destinazione per l'output del file XML](#destination)

### <a name="accounts-receivable-parameters"></a><a name="arparameters"></a>Parametri contabilità clienti

Selezionare le configurazioni utilizzate per creare file XML di fatture elettroniche per fatture di vendita e a testo libero, note di accredito di vendita e a testo libero, fatture progetto e note di accredito di progetto. È possibile trovare queste configurazioni nella scheda **Documento elettronico** della pagina **Parametri contabilità clienti** ( **Contabilità clienti** \> **Impostazioni** \> **Parametri contabilità clienti** ).

![Scheda Documento elettronico della pagina Parametri contabilità clienti](media/emea-ita-electronic-invocies-AR-parameter-e-invoices.png)

> [!NOTE]
> Le configurazioni devono essere importate prima di poter essere selezionate. Per ulteriori informazioni, vedere [Scaricare configurazioni ER dall'archivio globale del servizio di configurazione](../../fin-ops-core/dev-itpro/analytics/er-download-configurations-global-repo.md).

### <a name="electronic-invoice-parameters"></a><a name="einvoicesparameters"></a>Parametri fatture elettroniche

Utilizzare questi parametri per specificare scenari aziendali e informazioni specifiche dell'impresa.

1. Andare a **Contabilità clienti** \> **Impostazioni** \> **Parametri fatture elettroniche**.
2. Nella scheda **Generale** , specificare il requisito della firma elettronica.
3. Nella scheda **Informazioni società** , specificare le informazioni sull'impresa e il rappresentante fiscale, come richiesto. Queste informazioni sostituiscono le informazioni nel record della persona giuridica.
4. Nella scheda **Registrazione art. 2250 del codice civile** , fornire tutte le informazioni richieste se l'impresa è registrata secondo i termini dell'articolo 2250 del codice civile italiano.
5. Nella scheda **Sequenze numeriche** , inserire sequenze numeriche per i riferimenti **Numero di file univoco eInvoice** e **Numero di trasmissione eInvoice**.

### <a name="electronic-document-properties"></a><a name="edproperties"></a>Proprietà documento elettronico

La funzionalità per le proprietà dei documenti elettronici viene utilizzata per configurare l'output a blocchi di documenti XML per diversi casi aziendali. Di seguito sono riportati alcuni esempi.

- Un numero di partita IVA per i clienti che non si trovano nell'Unione Europea (UE) e non dispongono di codici di partita IVA
- Un indirizzo e-mail certificato (posta elettronica certificata \[PEC\]) per imprese private o professionisti
- Un'imposta di bollo (pagabile e non pagabile da parte del cliente)
- Dati sul rappresentante di un cliente

Perché la funzionalità funzioni, è necessario impostare i seguenti dati:

- Tipi di proprietà di documenti elettronici ( **Contabilità clienti** \> **Impostazioni** \> **Tipi di proprietà di documenti elettronici** ) e la tabella a cui ciascun tipo di proprietà di documenti è applicabile. Per la funzionalità di fatturazione elettronica, sono utilizzate le tabelle **Clienti** e **Persone giuridiche**.

    ![Impostazione dell'applicabilità nella pagina Tipi di proprietà di documenti elettronici](media/emea-ita-electronic-invocies-electronic-document-property-types.png)

- Valori richiesti nelle tabelle specificate a livello di cliente e persona giuridica:

    - **Cliente:** andare a **Contabilità clienti** \> **Clienti** \> **Tutti i clienti** , quindi, nel riquadro azioni, nella scheda **Cliente** selezionare **Proprietà dei documenti elettronici**.
    - **Persona giuridica:** andare a **Amministrazione organizzazione** \> **Organizzazioni** \> **Persone giuridiche** , quindi, nel riquadro azioni, selezionare **Proprietà dei documenti elettronici**.

I valori specificati sono utilizzati per l'output ai blocchi di file XML. La tabella seguente fornisce informazioni su come e dove vengono utilizzati tali valori.

| Scenario aziendale | Tipo di proprietà di documenti elettronici | Descrizione tipo di proprietà di documenti elettronici | Applicabilità (tabella) | Dove usare i valori | Elemento nel file XML |
|-------------------|-----------------------------------|-----------------------------------------------|-----------------------|--------------|-------------------------|
| Clienti che si trovano al di fuori dell'UE e non dispongono di codici di partita IVA. Per questi clienti, il numero di partita IVA deve essere **00000000000**. | VATnonEU | Esempio: **Cliente, partita IVA non UE** | **CustTable** (Clienti) | Nelle proprietà dei documenti elettronici dei clienti, impostare il campo **Valore** su **00000000000**. | **IdCodice** ( **CessionarioCommittente\\DatiAnagrafici\\IdFiscaleIVA** block) |
| Indirizzo e-mail certificato (PEC) per imprese private o professionisti | PEC | Esempio: **Cliente, Indirizzo e-mail certificato** | **CustTable** (Clienti) | Nelle proprietà dei documenti elettronici dei clienti, impostare il campo **Valore** su **\<PEC\>**. | **PECDestinatario** ( **DatiTrasmissione** block) |
| Imposta di bollo che non è inclusa nel totale della fattura per le fatture di vendita ed è o non è inclusa per le fatture di progetto | Bollo<p><strong>Nota:</strong> questo tipo di proprietà di documenti viene utilizzato per fatture di ordini cliente, fatture a testo libero e fatture di progetto.</p> | Esempio: **Imposta di bollo, inclusa/non inclusa nei totali della fattura** | **CompanyInfo** (Persone giuridiche) | Nelle proprietà dei documenti elettronici delle persone giuridiche, impostare il campo **Valore** su **\<Charge code/project category that is used for stamp duties\>**.<ul><li>**Codice di addebito** - Il tipo di addebito per questo codice di addebito deve essere **Contabilità generale**.</li><li>**Categoria progetto** - Questa categoria di progetto deve essere fatturabile.</li></ul> | **ImportoBollo** ( **DatiBollo** block) |
| Imposta di bollo inclusa nel totale della fattura | BolloPay<p><strong>Nota:</strong> questo tipo di proprietà di documenti viene utilizzato solo per fatture di ordini e fatture a testo libero.</p> | Esempio: **Imposta di bollo, inclusa/non inclusa nei totali della fattura** | **CompanyInfo** (Persone giuridiche) | Nelle proprietà dei documenti elettronici delle persone giuridiche, impostare il campo **Valore** su **\<Charge code/project category that is used for stamp duties\>**.<ul><li>**Codice di addebito** - Il tipo di addebito deve essere **Cliente/fornitore**.</li></ul> | **ImportoBollo** ( **DatiBollo** block) |
| Rappresentante | TaxRepPaese, TaxRepCodice, TaxRepDenominazione, TaxRepNome, TaxRepCognome | Qualsiasi descrizione | **CustTable** (Clienti) | Nelle proprietà dei documenti elettronici dei clienti, impostare il campo **Valore** su **IT** per il tipo di proprietà di documenti **TaxRepPaese**. Per altri tipi, immettere i dati per il rappresentante. | **Cognome** ( **RappresentanteFiscale** block) |
| Tipi di fattura | DocumentType | Esempio: **fattura, tipo di documento** | **CustInvoiceJour** (Giornale di registrazione fatture cliente), **ProjInvoiceJour** (Fattura di progetto) | Andare a **Contabilità clienti \> Richieste di informazioni e report \> Fatture \> Giornale di registrazione fatture** o **Gestione progetti e contabilità \> Fatture di progetto \> Fatture di progetto** e impostare il campo **Valore** su un tipo di documento, ad esempio **TD16**. | **TipoDocumento** (blocco **DatiGeneraliDocumento** ) |

> [!NOTE]
> La tabella precedente utilizza la seguente soluzione rapida:
>
> - "Proprietà dei documenti elettronici dei clienti" si riferisce alla pagina **Proprietà dei documenti elettronici** che viene aperta selezionando **Proprietà dei documenti elettronici** nella scheda **Cliente** del riquadro azioni nella pagina **Tutti i clienti** ( **Contabilità clienti \> Clienti \> Tutti i clienti** ).
> - "roprietà dei documenti elettronici delle persone giuridiche" si riferisce alla pagina **Proprietà dei documenti elettronici** che viene aperta selezionando **Proprietà dei documenti elettronici** nel riquadro azioni della pagina **Persone giuridiche** ( **Amministrazione organizzazione \> Organizzazioni \> Persone giuridiche** ).
> 
> Nella pagina elenco **Tipi di proprietà di documenti elettronici** , il campo **Descrizione** viene automaticamente compilato quando un utente immette informazioni nei campi **Descrizione gruppo** e **Descrizione**.
>
> Il tipo di proprietà di documenti elettronici deve avere lo stesso codice specificato nella tabella.

#### <a name="use-project-categories-for-stamp-duty"></a>Utilizzare categorie di progetto per l'imposta di bollo

Andare a **Gestione progetti e contabilità** \> **Impostazioni** \> **Categorie** \> **Categorie di progetto** per impostare categorie di progetto che hanno un tipo di transazione **Commissioni** o **Spese**. L'ID categoria deve essere uguale al valore definito per il tipo di proprietà documento **Bollo** a livello di entità giuridica. Per ulteriori informazioni, vedere la tabella precedente.

La categoria di progetto del tipo di transazione **Commissioni** può essere utilizzata solo per l'imposta di bollo inclusa nella fattura. La categoria di progetto del tipo di transazione **Spese** può essere utilizzata per l'imposta di bollo che è inclusa in una fattura cliente e che non è inclusa. In entrambi i casi, viene utilizzato il tipo di proprieta di documenti **Bollo**.

Quando si creano righe di giornale di registrazione **Commissioni** o **Spese** , selezionare la categoria definita per l'imposta di bollo e immettere un prezzo di costo. Il sistema considera questo prezzo di costo come l'importo dell'imposta di bollo. Se si immette un prezzo di vendita uguale all'importo del prezzo di costo, il sistema considera tale importo incluso nei totali della fattura. L'importo del prezzo di vendita è uguale a 0 (zero) e la transazione non è inclusa nei totali della fattura.

> [!NOTE]
> È possibile utilizzare solo uno dei tipi di giornale di registrazione ( **Commissioni** o **Spese** ) per l'imposta di bollo. Un'impresa che utilizza solo l'imposta di bollo pagabile può utilizzare il tipo di giornale di registrazione **Commissioni**. Se un'impresa utilizza un'imposta di bollo sia pagabile che non pagabile, è meglio utilizzare il tipo di giornale di registrazione **Spese**.

### <a name="customers"></a><a name="customers"></a>Clienti

#### <a name="authority-office-field"></a>Campo Ufficio di controllo

È possibile trovare il campo **Ufficio di controllo** nella Scheda dettagli **Dati demografici vendite** di un record cliente (andare a **Contabilità clienti** \> **Clienti** \> **Tutti i clienti** e aprire il record del cliente in modalità **Modifica** ).

Il valore di questo campo viene utilizzato per definire il tipo di comunicazione (business to government \[B2G\] o business to business \[B2B\]):

- Se la lunghezza del valore è 6, il cliente è considerato un'amministrazione pubblica (il formato di trasmissione è uguale a **FPA12** ).
- Se la lunghezza del valore è 7, il cliente è considerato un'impresa privata o un professionista (il formato di trasmissione è uguale a **FPR12** ).

In entrambi i casi, il sistema immette il valore di questo campo nel tag **CodiceDestinatario** nel file XML.

![Campo Ufficio di controllo nella scheda dettaglio Dati demografici vendite di un record cliente](media/emea-ita-electronic-invocies-customer-authority-office.png)

Se il campo **Ufficio di controllo** è vuoto, il sistema considera il cliente come un'impresa privata o un professionista (il formato di trasmissione è uguale a **FPR12** ) e immette **0000000** nel tag **CodiceDestinatario** nel file XML. In questo caso, deve essere impostato un indirizzo e-mail certificato (PEC). Per ulteriori informazioni, consultare la tabella nella sezione [Proprietà dei documenti elettronici](#edproperties) vista precedentemente in questo argomento.

#### <a name="activate-automatic-creation-of-e-invoices"></a>Attivare la creazione automatica di fatture elettroniche

Andare a **Contabilità clienti** \> **Clienti** \> **Tutti i clienti** e aprire un record cliente in modalità di **Modifica**. Quindi nella Scheda dettaglio **Fattura e consegna** , nella sezione **Fattura elettronica** , trovare l'opzione **Registro eInvoice**. Se questa opzione è impostata su **Sì** , il sistema crea automaticamente il record nella pagina elenco **Fatture elettroniche clienti**. Per ulteriori informazioni, vedere [Registro delle fatture elettroniche](#einvoiceregister).

![Sezione Fattura elettronica nella Scheda dettaglio Fattura e consegna di un record cliente](media/emea-ita-electronic-invocies-customer-e-invoice.png)

Nella sezione **Fattura elettronica** è possibile anche impostare l'opzione **Allegato fattura elettronica** su **Sì**. In questo caso, dopo aver stampato una fattura (durante o dopo la registrazione), il sistema allega automaticamente il file PDF alla fattura e alla fattura elettronica (vedere [Registro delle fatture elettroniche](#einvoiceregister)) e il file è incluso nel file XML (blocco **Allegati** ).

### <a name="items"></a><a name="items"></a>Articoli

Se in una fattura sono presenti righe di prodotti, il blocco **CodiceArticolo** viene compilato in base ai dati del prodotto. Questi dati includono il codice a barre del prodotto, il numero del prodotto interno o il numero dell'articolo e la descrizione dell'articolo esterna. Queste informazioni possono essere trovate andando su **Gestione informazioni prodotto** > **Prodotti** > **Prodotti rilasciati** e nel riquadro azioni selezionare **Vendi** > **Informazioni correlate**.    

Il campo **CodiceTipo** viene completato come segue:
- Se è presente un codice a barre, questo campo = **EAN**.
- Se non è presente un codice a barre e il record nella **Descrizione articolo esterno** esiste per il prodotto e il cliente, questo campo ha il valore del campo **Descrizione**.
- Se non è presente un codice a barre e il record nella **Descrizione articolo esterno** non esiste per il prodotto, questo campo include il testo **Codice Art. fornitore**.

Il campo **CodiceValore** viene completato come segue:
- Se è presente un codice a barre, questo campo include il codice a barre.
- Se non è presente un codice a barre e il record nella **Descrizione articolo esterno** esiste per il prodotto e il cliente, questo campo include il valore del campo **Numero articolo esterno**.
- Se non è presente un codice a barre e il record nella **Descrizione articolo esterno** non esiste per il prodotto e il cliente, questo campo include il valore del campo **Numero articolo**. 


### <a name="digital-certificates"></a><a name="digitalcert"> </a>Certificati digitali

Andare a **Contabilità clienti** \> **Impostazioni** \> **Certificati di firma elettronica** per firmare elettronicamente fatture elettroniche utilizzando un certificato di tipo **Società** o **Utente**.

![Pagina Certificati di firma elettronica](media/emea-ita-electronic-invocies-certificate.png)

La parte che emette le fatture deve utilizzare un certificato di firma qualificato per firmare ogni file FatturaPA che viene trasmessa al sistema di scambio - **SDI** ( *Sistema di Interscambio* ). Un certificato di firma qualificato può essere ottenuto da uno dei certificatori nell'[elenco di certificatori autorizzati](http://www.digitpa.gov.it/firma-digitale/certificatori-accreditati).

Microsoft Dynamics 365 Finance supporta il formato di firma **XAdES-BES**. Per consentire a Finance di supportare FatturaPA, attenersi alla seguente procedura.

1. Nei computer client installare e configurare certificati digitali che hanno chiavi private e pubbliche nel campo **Macchina server delle applicazioni** del nodo **Personale**.

    > [!NOTE]
    > È possibile completare l'installazione e la configurazione utilizzando la funzionalità standard di Windows.

2. Definire certificati a livello di impresa e certificati a livello di utente, come richiesto.

### <a name="destination-for-xml-file-output"></a><a name="destination"></a>Destinazione per l'output dei file XML

Se i file XML devono essere inviati come output a una posizione specifica quando vengono registrate le fatture (ad esempio, se devono essere inviate a una cartella SharePoint), impostare un tipo di documento, quindi impostare una destinazione. Per ulteriori informazioni su questi passaggi, vedere [Configurare la gestione dei documenti](../../fin-ops-core/fin-ops/organization-administration/configure-document-management.md) e [Destinazioni dei report elettronici (ER)](../../dev-itpro/analytics/electronic-reporting-destinations.md).

> [!NOTE]
> L'opzione **Stampa fattura** deve essere impostata su **Sì**. Se la destinazione è impostata, lo stato del record della fattura elettronica per la fattura viene automaticamente impostato su **Inviata**.

## <a name="fill-in-data-for-related-documents"></a><a name="releteddoc"></a>Immettere dati per documenti correlati

Le imprese possono immettere ulteriori informazioni su alcuni documenti di base correlati alle fatture. Di seguito sono riportati alcuni esempi.

- Il blocco **DatiOrdineAcquisto** contiene informazioni correlate all'ordine fornitore.
- Il blocco **DatiContratto** contiene informazioni correlate al contratto.
- Il blocco **DatiConvenzione** contiene informazioni correlate all'accordo.
- Il blocco **DatiRicezione** contiene le informazioni relative ai dati sulla fase di ricezione. Questi dati sono presenti nel sistema di gestione utilizzato dalle PA (agenzie fiscali).
- Il blocco **DatiFattureCollegate** contiene informazioni correlate alle fatture precedentemente trasmesse e alle quali è collegato il documento corrente. Questo blocco viene utilizzato nei casi in cui una nota di accredito e/o una fattura vengono inoltrate in seguito a precedenti fatture di pagamento anticipato.

Per consentire al sistema di immettere informazioni in questi blocchi, impostare i seguenti campi:

- Nella pagina **Ordine cliente** ( **Contabilità** \> **Ordini** \> **Tutti gli ordini cliente** ) nella visualizzazione **Intestazione** , nella Scheda dettaglio **Impostazione** impostare i campi nella sezione **Documento di base**.
- Nella pagina **Fattura a testo libero** ( **Contabilità** \> **Fatture** \> **Tutte le fatture a testo libero** ) nella visualizzazione **Intestazione** , nella Scheda dettaglio **Generale** impostare i campi nella sezione **Documento di base**.
- Nella pagina **Proposta di progetto** ( **Gestione progetti e contabilità** \> **Progetti** \> **Tutti i progetti** ), nel riquadro azioni, nel gruppo **Fatturazione** della scheda **Gestione** , selezionare **Proposta di fatturazione** , quindi impostare i campi nella sezione **Documento di base**.

> [!NOTE]
> I dati dei campi nella sezione **Documento di base** sono inviati come output da blocchi diversi, a seconda del valore del campo **Documento di base**.
> 
> | Valore del campo Documento di base | Blocca da cui vengono inviati i dati |
> |---|---|
> | Ordine di pagamento | DatiOrdineAcquisto |
> | Contratto | DatiContratto |
> | Contratto | DatiConvenzione |
> | Sistema di gestione | DatiRicezione |
> | Fattura originale | DatiFattureCollegate |

Per ciascun documento di base, gli utenti possono aggiungere dettagli sul numero e sulla data del documento, il CUP (Codice Unico di Progetto, gestito dal Ministero dello sviluppo economico), il CIG (Codice Identificativo di Gara) e il codice dell'accordo.

## <a name="electronic-invoice-register"></a><a name="einvoiceregister"></a>Registro delle fatture elettroniche

Per visualizzare tutte le fatture elettroniche dei clienti ed eseguire varie azioni, andare a **Contabilità clienti** \> **Fatture** \> **Fatture elettroniche** \> **Fatture elettroniche** per aprire la pagina **Fatture elettroniche clienti**.

In questa pagina, è possibile eseguire le azioni riportate di seguito:

- Selezionare **Seleziona** per selezionare le fatture, in base a vari criteri. Questa funzione è utile se l'opzione **Registro eInvoice** è impostata su **No**.
- Selezionare **Crea XML** , **Crea firma** e **Invia** per creare file XML e una firma digitale per le fatture selezionate e inviarle.
- Selezionare **Esporta** per esportare una fattura selezionata in un file XML.

    > [!NOTE]
    > Il sistema invia un file alla cartella impostata sul computer. Le impostazioni relative alla destinazione non sono utilizzate.

- Selezionare la scheda **Dettagli** per visualizzare i dettagli della fattura elettronica.

> [!NOTE]
> La pagina **Fatture elettroniche** ( **Gestione progetti e contabilità** \> **Fatture progetto** \> **Fatture elettroniche** \> **Fatture elettroniche** ) è simile alla pagina **Fatture elettroniche clienti** e ha le stesse funzioni.

![Pagina Fatture elettroniche clienti](media/emea-ita-electronic-invocies-electronic-customer-invoices.png)

## <a name="additional-functionality-that-affects-the-xml-file"></a><a name="additionalfunctionality"></a>Funzionalità aggiuntiva che riguarda il file XML

### <a name="tax-invoice-for-goods-delivered-for-free"></a>Fattura fiscale per le merci consegnate gratuitamente

Per informazioni su come configurare e utilizzare questa funzionalità, vedere [Fattura fiscale per le merci consegnate gratuitamente](emea-ita-exil-goods-for-free.md).

Nella pagina **Distribuzione** ( **Vendite e marketing** \> **Impostazioni** \> **Distribuzione** ), se **Merci gratuite** è selezionato nel campo **Motivo della consegna** e il campo **Conto fattura** è vuoto, l'elemento **TipoCessionePrestazione** viene inviato come output nel file XML.

### <a name="intent-letters--invoicing-of-usual-exporters"></a>Lettere di intenti - Fatturazione di esportatori abituali

Per informazioni su come configurare e utilizzare questa funzionalità, vedere [Lettere di intenti - Fatturazione di esportatori abituali](emea-ita-exil-intent-letter.md).
Se viene impostata una lettera di intenti per un cliente, l'elemento **Causale** (blocco **DatiGeneraliDocumento** ) che ha il numero della lettera di intenti viene inviato come output nel file XML.

## <a name="functionality-that-is-available-in-finance-version-10012"></a><a name='fatturaPA'></a>Funzionalità disponibile in Finance versione 10.0.12

### <a name="reverse-charge-and-reverse-charge-group-configuration"></a>Configurazione di reverse charge e gruppo di reverse charge

Le impostazioni in questa sezione sono necessarie quando una società utilizza la funzionalità di reverse charge. Inoltre, devono essere impostati i parametri specifici dell'applicazione che hanno questi gruppi. Per ulteriori informazioni su questa funzionalità, vedere [Hotfix specifico del paese per supportare le modifiche nel formato "FatturaPA" delle fatture elettroniche italiane in Microsoft Dynamics 365 Finance](https://support.microsoft.com/help/4569342/a-country-specific-hotfix-to-support-changes-in-fatturapa-format-of-it).

Andare a **Imposta** \> **Impostazioni** \> **Gruppi di articoli reverse charge** per definire gruppi di reverse charge specifici per prodotti o categorie specifici.

![Pagina dei gruppi di articoli di reverse charge](media/emea-ita-FatturaPA-161-RC-groups.png)

### <a name="invoice-type-configuration"></a>Configurazione del tipo di fattura

I seguenti tipi di documenti di fatturazione sono supportati e verranno compilati automaticamente:

- TD01 - Fattura
- TD04 - Nota di accredito
- TD05 - Nota di addebito
- TD20 - Fatturazione automatica

Se un tipo di documento richiesto non è coperto dai valori nell'elenco precedente, è possibile modificare manualmente il tipo di documento nei giornali di registrazione fatture. Per attivare la rettifica manuale è necessario completare la seguente impostazione:

- Definizione di proprietà di documenti elettronici
- Registrazione del tipo di documento fattura

Per ulteriori informazioni, vedere [Hotfix specifico del paese per supportare le modifiche nel formato "FatturaPA" delle fatture elettroniche italiane in Microsoft Dynamics 365 Finance](https://support.microsoft.com/help/4569342/a-country-specific-hotfix-to-support-changes-in-fatturapa-format-of-it).
