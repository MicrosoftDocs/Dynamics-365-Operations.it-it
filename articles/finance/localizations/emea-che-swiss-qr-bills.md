---
title: Fatture QR per la Svizzera
description: Questo argomento fornisce informazioni su come generare fatture QR (QR-slip) ed elaborare fatture QR in entrata.
author: neserovleo
manager: AnnBe
ms.date: 03/25/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Switzerland
ms.author: v-lenest
ms.search.validFrom: 2020-06-01
ms.dyn365.ops.version: 10.0.9
ms.openlocfilehash: 1c58aa35dacb719eeef3a9b8d5f4904beefc73a0
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4408095"
---
# <a name="swiss-qr-bills"></a>Fatture QR per la Svizzera

[!include [banner](../includes/banner.md)]


A partire da luglio 2020, oltre alle fatture dovranno essere elaborate ed emesse fatture QR (QR-slips). Questo argomento spiega come generare fatture QR ed elaborare fatture QR in entrata in Microsoft Dynamics 365 Finance.

Per rendere disponibile la funzionalità di fatturazione QR, è necessario attivare le seguenti funzionalità nel modulo **Gestione delle funzionalità**:

- ID pagamento configurabile
- Fatture QR (Svizzera)

> [!NOTE]
> Quando si attiva la funzionalità di Fattura QR per la Svizzera, questa diventa disponibile anche per altri paesi. A seconda dell'indirizzo dell'entità giuridica, tali paesi includono Svizzera (CH), Germania (DE), Austria (AT), Francia (FR) e Italia (IT).

## <a name="electronic-reporting-configurations"></a>Configurazioni creazione di report elettronici

Le versioni più recenti delle seguenti configurazioni di report elettronico (ER) devono essere importate da Microsoft Dynamics Lifecycle Services (LCS):

- Testo della fattura QR per la Svizzera
- Informazioni strutturate della fattura QR per la Svizzera
- Bonifico ISO20022 (CH)
- ISO20022 pain.002
- ISO20022 Camt.054

Tutte le configurazioni di mappatura modello e di modello richieste verranno importate automaticamente.

## <a name="setup-of-company-bank-accounts"></a>Impostazione di conti bancari aziendali

Nella pagina **Conto bancario** (**Gestione cassa e banche** \> **Conti bancari** \> **Conti bancari**), nel campo **IBAN QR**, specificare l'IBAN QR. Questo numero può essere utilizzato insieme al normale numero di conto bancario internazionale (IBAN) e ha convalide simili nel sistema.

### <a name="cash-discount-and-tax-code-descriptions"></a>Sconto di cassa e descrizioni dei codici IVA

Il campo per la descrizione della fattura QR deve essere compilato per tutti gli sconti di cassa e codici IVA. Questa descrizione viene utilizzata quando vengono stampate le fatture QR.

## <a name="setup-of-the-legal-entity-registration-ids"></a>Impostazione degli ID di registrazione della persona giuridica

Affinché l'identificatore univoco (UID) sia compilato correttamente sulla fattura QR generata, il valore UID deve essere inserito nel campo **ID registrazione** nell'impostazione della persona giuridica. Inoltre, il valore nel campo **Categoria di registrazione** deve corrispondere al valore **ID IVA**.

## <a name="accounts-receivable-setup"></a>Impostazioni della contabilità clienti

### <a name="payment-id"></a>ID pagamento

Nella pagina **ID pagamento**, è possibile configurare la struttura dell'ID pagamento applicata quando vengono generate le fatture QR in uscita dal modulo **Contabilità clienti**. La lunghezza dell'ID pagamento deve essere impostata su 27 cifre e la cifra di controllo deve essere generata utilizzando l'algoritmo **Modulo11**. I simboli non numerici vengono esclusi dagli ID pagamento quando viene eseguito l'algoritmo. Pertanto, le sequenze numeriche utilizzate per gli account cliente e le fatture devono contenere solo cifre.

Per impostazione predefinita, il tipo di ID applicato alla fattura può utilizzare la seguente gerarchia di livelli:

- Pagina **Parametri contabilità clienti** \> scheda **Contabilità generale e IVA**
- Pagina **Gruppi di clienti**
- Pagina **Conto cliente** \> scheda **Impostazioni predefinite di pagamento**
- Pagina **Metodo di pagamento** \> scheda **Controllo dei pagamenti**

### <a name="methods-of-payment--customers"></a>Metodi di pagamento - Clienti

Il metodo di pagamento deve essere impostato sui conti dei clienti che utilizzano le fatture QR, per definire i dettagli del conto bancario dell'azienda a cui viene emessa una fattura QR. Per elaborare i pagamenti in entrata in formato camt.054, è necessario impostare la configurazione dell'importazione ER.

### <a name="customer-account"></a>Account cliente

È necessario selezionare il metodo di pagamento predefinito e compilare il tipo di ID pagamento se non è già stato specificato nella configurazione predefinita per i gruppi di clienti nella pagina **Parametri contabilità clienti**.

Nel gruppo di campi **Allegato pagamento associato**, viene aggiunto il nuovo tipo **Fattura QR**. Quando è selezionato, la fattura QR verrà stampata nel momento in cui viene stampato il documento del tipo dedicato.

### <a name="giro-report-processing-group"></a>Gruppo di elaborazione report ordine di accredito

Le informazioni sulle impostazioni fornite nei gruppi di elaborazione elaborazione report ordine di accredito determinano il modo in cui viene compilata la sezione **Informazioni di fatturazione** su una fattura QR. Se necessario, è possibile configurare e utilizzare diverse parti di questa sezione sulla fattura QR in ER. Di seguito sono riportati alcuni esempi.

- **Codice conto** - Il formato specifico dedicato al conto cliente specifico.
- **Relazione cliente** – Il valore del conto cliente o del gruppo di clienti specifico.
- **Informazioni su fattura QR** - La configurazione del formato ER responsabile della compilazione delle informazioni di fatturazione.
- **Stampa il simbolo delle forbici** - L'inclusione del simbolo delle forbici nel rapporto stampato. L'inclusione di questo simbolo potrebbe essere importante quando si sceglie se inviare una versione stampata della fattura QR o una versione elettronica.

## <a name="accounts-payable-setup"></a>Impostazioni della contabilità fornitori

### <a name="methods-of-payment--vendors"></a>Metodi di pagamento - Fornitori

Per i metodi di pagamento del fornitore, è necessario specificare il conto bancario associato, selezionare le configurazioni ER richieste per l'esportazione e l'importazione per l'elaborazione dei file di pagamento e impostare le specifiche di pagamento. Un nuovo valore del parametro delle specifiche di pagamento, **Tp3.QR**, è disponibile per pagamenti corrispondenti alle fatture QR in entrata. Inoltre, è possibile utilizzare un'opzione disponibile sul conto bancario del fornitore per ridefinire il parametro **Specificazione**.

L'ID pagamento deve essere attivato sulla scheda **Attributi di pagamento**, in modo che possa essere ereditato durante la proposta di pagamento per i pagamenti associati alle fatture QR.

### <a name="return-format-error-codes-and-return-format-status-mapping"></a>Codici di errore del formato di risposta e mappatura dello stato del formato di risposta

Se pain.002 verrà utilizzato come formato di file di risposta, è necessario impostare i codici di errore del formato di risposta e la mappatura dello stato del formato di risposta. Per ulteriori informazioni, vedere [Importare file ISO20022](emea-iso20022-file-formats.md).

### <a name="vendor-account"></a>Account fornitore

È prevista la configurazione standard del conto fornitore per i pagamenti ISO20022. Per ulteriori informazioni, vedere [Impostare i fornitori e i conti bancari dei fornitori per i bonifici ISO20022](tasks/set-up-vendor-iso20022-credit-transfers.md).

### <a name="vendor-bank-account"></a>Conto bancario fornitore

Un IBAN QR deve essere assegnato ai conti bancari del fornitore. Si prevede che altri campi verranno impostati in base alla tipica procedura di pagamento per il tipo di pagamento 3 in Svizzera.

Inoltre, esiste un'opzione per selezionare un parametro delle specifiche di pagamento direttamente sul conto bancario del fornitore. Se è stata effettuata una specifica di pagamento, al valore viene data una priorità più alta rispetto al metodo di specifica di pagamento quando viene generato un file di trasferimento del credito.

## <a name="accounts-receivable-process"></a>Processo di contabilità clienti

### <a name="generate-the-qr-bills"></a>Generare le fatture QR

Per generare la fattura QR per un documento, ad esempio una fattura cliente, stampare il documento. La fattura QR verrà generata automaticamente come report aggiuntivo. È quindi possibile esportare la fattura QR come file PDF, stamparla o inviarla elettronicamente.

Di seguito sono riportati alcuni documenti che supportano questa funzionalità:

- Fatture ordine cliente
- Fatture a testo libero
- Fatture progetto
- Note d'interesse
- Lettere di sollecito
- Estratti conto

### <a name="import-payments-in-camt054-format"></a>Importare pagamenti in formato camt.054

Per importare un estratto conto in formato camt.054 dalla banca, aprire la riga del giornale di registrazione pagamenti del cliente ed eseguire la funzione **Importa pagamento**. Il riferimento a 27 cifre è previsto nel tag **Ref** nella sezione **RmtInf** del file. Dopo l'importazione, le transazioni di pagamento verranno create e regolate con le transazioni dei clienti in base all'ID pagamento. Per ulteriori informazioni, vedere [Importare file ISO20022](emea-iso20022-file-formats.md).

## <a name="accounts-payable-process"></a>Processo di contabilità fornitori

L'ambito delle funzionalità supportate include il processo di importazione manuale dei valori del codice QR nella finestra di dialogo di input. Questa importazione può essere effettuata utilizzando dispositivi di scansione che trasmettono il valore di testo del codice QR. La struttura delle informazioni nel codice QR deve seguire gli standard disponibili sul sito Web del gruppo SIX al momento del rilascio della funzione. Qualsiasi derivazione dalla struttura delle informazioni crittografate nel codice QR o qualsiasi modifica del formato richiesta per seguire il comportamento specifico del dispositivo, può essere configurata utilizzando il modulo **Creazione di report elettronici** (ER). Non sono necessarie modifiche al codice.

### <a name="import-qr-bills"></a>Importare fatture QR

È possibile importare le fatture QR nel giornale di registrazione fatture o nelle destinazioni di fattura fornitore in sospeso.

Per importare le fatture QR nel giornale di registrazione fatture, eseguire la funzione **Importa fattura QR** disponibile sulla pagina **Righe giornale di registrazione fatture**.

Nella finestra di dialogo **Importazione**, il campo **Fattura QR** mostra il nome della configurazione del formato ER che verrà utilizzata. È possibile specificare un formato ER diverso. Nel testo in chiaro del campo **Fattura QR**, inserire il valore del codice QR. Selezionare **OK**.

Nella pagina successiva, la scheda **Fattura QR** mostra i valori analizzati della fattura QR. Nella scheda **Generale**, è possibile visualizzare i valori del fornitore, del conto bancario, dell'importo riconosciuti e altri dettagli che verranno importati nel sistema. Dopo aver selezionato **OK**, vengono create le righe del giornale di registrazione fatture. Se la fattura QR è stata precedentemente importata, si riceve una notifica tramite un messaggio di avviso. Le informazioni della fattura QR importata sono archiviate e disponibili per la revisione sulla pagina **Fatture QR importate**.

Per le fatture associate agli ordini fornitore, è possibile creare intestazioni di fattura fornitore in sospeso basate sulle informazioni della fattura QR. Per importare la fattura QR, sulla pagina **Fatture fornitore in sospeso**, nella scheda **Processo**, selezionare **Importa fattura QR**. La procedura per l'aggiunta, la revisione e l'importazione del codice QR assomiglia alla procedura descritta nel paragrafo precedente.

È inoltre possibile importare la fattura QR quando la fattura fornitore viene aperta dalla pagina **Ordine fornitore**. La procedura di importazione è uguale alla procedura per le fatture fornitore in sospeso. Se la fattura è associata a un ordine fornitore, l'importazione avviene automaticamente.

Per elaborare la fattura QR quando non esiste una destinazione predefinita o utilizzare una destinazione personalizzata, è possibile usare un'opzione speciale disponibile in **Attività periodiche** nel modulo **Contabilità fornitori**. In questo caso, è necessario selezionare manualmente la destinazione.

Quando il testo normale della fattura QR viene lasciato in bianco, è possibile eseguire l'importazione dal file di testo che si trova nella cartella SharePoint, basata sull'impostazione dell'origine ER.

Dopo che la fattura è stata registrata, la transazione del fornitore con l'ID pagamento importato è disponibile per la liquidazione nel giornale di registrazione pagamenti.

## <a name="payment-file-processing"></a>Elaborazione del file di pagamento

Creare le righe di registrazione pagamenti fornitore utilizzando la funzionalità di proposta di pagamento. Per ulteriori informazioni,vedere [Creare ed esportare pagamenti fornitore usando il formato di pagamento ISO20022](tasks/create-export-vendor-payments-iso20022-payment-format.md).

Per i pagamenti correlati alle fatture QR, il file di bonifico viene generato in base al valore dell'ID pagamento. Questo valore viene recuperato dal codice QR.

È possibile importare i file pain.002 e i file camt.054 dalla pagina **Trasferimenti di pagamento**. Per ulteriori informazioni, vedere [Importare file ISO20022](emea-iso20022-file-formats.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]