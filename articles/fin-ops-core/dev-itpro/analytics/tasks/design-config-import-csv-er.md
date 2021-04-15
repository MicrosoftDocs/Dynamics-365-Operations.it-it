---
title: Progettare configurazioni di ER per importare dati da file CSV esterni
description: Utilizzare questa procedura per progettare le configurazioni di creazione di report elettronici per importare i dati in un'app Finance and Operations da un file esterno in formato CSV.
author: NickSelin
ms.date: 12/12/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 05beb15413362aea557fb80fb471c10e1f832184
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5752534"
---
# <a name="design-er-configurations-to-import-data-from-external-csv-files"></a>Progettare configurazioni di ER per importare dati da file CSV esterni

[!include [banner](../../includes/banner.md)]

Utilizzare questa procedura per progettare le configurazioni di creazione di report elettronici (ER) per importare i dati nell'applicazione da un file esterno in formato CSV. In questa procedura verranno create le configurazioni ER necessarie per la società di esempio Litware, Inc. Per effettuare queste operazioni, è innanzitutto necessario completare i passaggi nella procedura "ER Creare un provider di configurazione e contrassegnarlo come attivo".

Questa procedura viene creata per utenti con il ruolo di amministratore di sistema o di sviluppatore di report elettronici. Tali passaggi possono essere completati mediante il set di dati USMF.

È inoltre necessario scaricare e salvare i seguenti file in locale: [Dynamics 365 Finance Esempi di creazione di report elettronici](https://go.microsoft.com/fwlink/?linkid=862266): 1099model.xml, 1099formatcsv.xml, 1099entriescsv.csv.

1. Andare ad Amministrazione organizzazione > Aree di lavoro > Creazione di report elettronici.
    * È possibile configurare un processo per importare i file esterni in formato XML, TXT o CSV nelle tabelle dell'applicazione. Innanzitutto, è necessario creare un modello di dati astratti per rappresentare i dati importati, dal punto di vista aziendale - una configurazione del modello dati ER viene creata. Quindi, definire una struttura del file importato che esegue il mapping al modello di dati progettato come modalità per portare i dati dal file al modello dati astratti - una configurazione del formato ER viene creata. Quindi, la configurazione del modello dati ER deve essere estesa con un nuovo mapping di modello che descrive come i dati del file importato e i dati resi persistenti dal modello dati astratti vengono utilizzati per aggiornare le tabelle dell'applicazione o le entità di dati.
    * Nei passaggi seguenti viene illustrato come le transazioni dei fornitori tracciati esternamente vengono importate dal file CSV esterno per un utilizzo futuro nella liquidazione del fornitore per i moduli 1099.
    * Verificare che il provider di configurazione per la società di esempio Litware Inc. sia disponibile e contrassegnato come attivo. Se il provider di configurazione non viene visualizzato, è necessario innanzitutto completare i passaggi della procedura "Creare un provider di configurazione e contrassegnarlo come attivo".
2. Fare clic su Configurazioni report.
3. Applicare il filtro '1099 Modello pagamenti'. Se è già stata completata la procedura "Creare le configurazioni necessarie per importare dati da un file esterno per la creazione di report elettronici (ER)" e la configurazione "1099 Modello pagamenti" è disponibile nella struttura di configurazione, saltare tutti i passaggi nella sottoattività successiva.

## <a name="add-a-new-er-model-configuration"></a>Aggiungere una nuova configurazione del modello ER

1. Anziché creare un nuovo modello per supportare l'importazione dati, caricare il file 1099model.xml scaricato in precedenza. Questo file contiene il modello dati personalizzati delle transazioni fornitore. Questo modello di dati è già mappato ai componenti di dati necessari.
2. Fare clic su Scambia.
3. Fare clic su Carica da file XML.
4. Fare clic su Sfoglia e trovare il file 1099model.xml in precedenza scaricato.
5. Fare clic su OK.

## <a name="add-a-new-er-format-configuration-that-supports-data-import"></a>Aggiungere una nuova configurazione del formato ER che supporta l'importazione dati

1. Nella struttura selezionare '1099 Modello pagamenti'.
2. Fare clic su Crea configurazione per aprire la finestra di dialogo a discesa .
3. Nel campo Nuovo immettere 'Formato in base al modello dati 1099 Modello pagamenti'.
4. Selezionare Sì nel campo Supporta importazione dati.
5. Premere il tasto ESC per chiudere la pagina.
    * Anziché creare un nuovo formato ER per supportare l'importazione dati, caricare il file 1099formatcsv.xml scaricato in precedenza. Questo file contiene il formato ER richiesto che definisce la struttura del file CSV da importare e il mapping della struttura al modello di dati delle transazioni fornitore.
6. Fare clic su Scambia.
7. Fare clic su Carica da file XML.
    * Fare clic su Sfoglia e trovare il file 1099formatcsv.xml in precedenza scaricato.
8. Fare clic su OK.
9. Nella struttura espandere '1099 Modello pagamenti'.
10. Nella struttura selezionare '1099 Modello pagamenti\Formato per importazione transazioni fornitori (CSV)'.

## <a name="review-format-settings"></a>Esaminare le impostazioni di formato

1. Fare clic su Progettazione.
2. Fare clic su Espandi/Comprimi.
3. Attivare 'Mostra dettagli'.
    * Il formato progettato rappresenta la struttura prevista del file esterno nel formato CSV.
4. Nella struttura selezionare 'Incoming: File\Root: Sequence'.
    * Per l'elemento radice del tipo SEQUENCE, l'opzione "Nuova riga - Windows (CR LF)" è stata selezionata nel campo "Caratteri speciali". In base a questa impostazione, ogni riga del file di analisi deve essere considerata come record separato.
5. Nella struttura selezionare `Incoming: File\Root: Sequence\Line: Sequence 1..*`.
    * Per l'elemento Root\Line di tipo SEQUENCE, l'opzione "Uno molti" è stata selezionata nel campo "Molteplicità". In base a questa impostazione, almeno una riga verrà presentata nel file di analisi.
6. Nella struttura selezionare `Incoming: File\Root: Sequence\Line: Sequence 1..* \Types: Case`.
    * Si noti che l'elemento Root\Line\Types del tipo CASE è stato aggiunto come l'elemento nidificato della sequenza Root\Line. Poiché questo elemento CASE contiene 3 elementi di sequenza nidificati, questa impostazione presuppone che si debbano soddisfare 3 tipi di riga diversi nel file di analisi.
7. Nella struttura selezionare `Incoming: File\Root: Sequence\Line: Sequence 1..* \Types: Case\Header: Sequence 1..1`.
    * L'elemento Root\Line\Types\Header di tipo SEQUENCE contiene l'elemento STRING nidificato il cui valore è stato definito come valore di stringa fisso. Questa sequenza analizzerà la riga di intestazione del file di analisi.
8. Nella struttura selezionare `Incoming: File\Root: Sequence\Line: Sequence 1..* \Types: Case\Record: Sequence 1..1 (,)`.
    * L'elemento Root\Line\Types\Record di tipo SEQUENCE è stato configurato per analizzare le righe di transazione. Tenere presente che l'opzione del carattere "Delimitatore personalizzato" è stata configurata come virgola. Ciò significa che la virgola verrà utilizzata come separatore dei campi per questo tipo di riga nel file di analisi.
    * Tenere presente che molti elementi annidati di tipi di dati diversi sono stati aggiunti all'elemento Root\Line\Types\Record per l'analisi delle righe di transazione come campi separati. Tenere presente che l'opzione "Applicazione offerta" è stata configurata come "Nessuno". Ciò significa che nel file di analisi, tutti i campi di questo tipo verranno considerati come privi di caratteri inclusi.
9. Nella struttura selezionare `Incoming: File\Root: Sequence\Line: Sequence 1..* \Types: Case\Record: Sequence 1..1 (,)\TransactionDate: DateTime`.
    * Ad esempio, l'elemento Root\Line\Types\Record\TransactionDate di tipo DATETIME è stato configurato per ottenere il valore della data e dell'ora della transazione dal file di analisi nel formato "M/d/yyyy".
10. Nella struttura selezionare `Incoming: File\Root: Sequence\Line: Sequence 1..* \Types: Case\Record: Sequence 1..1 (,)\CountryCode: String 0..1`.
    * Tenere presente che l'elemento Root\Line\Types\Record\CountryCode di tipo STRING è stato configurato come contenente l'opzione "Nessuno uno" nel campo "Molteplicità". Questa impostazione prende in considerazione il valore del campo CountryCode nella riga di analisi come facoltativo.
11. Nella struttura selezionare `Incoming: File\Root: Sequence\Line: Sequence 1..* \Types: Case\Record: Sequence 1..1 (,)\Remark: Sequence 1..1 (,)`.
    * Tenere presente che l'elemento Root\Line\Types\Record\Remark di tipo SEQUENCE è stato configurato come contenente l'opzione "Tutto" nel campo "Applicazione offerta" e il carattere di virgolette doppie nel campo "Contrassegno offerta". Ciò significa che tutti i campi di questo tipo di righe nel file di analisi (descritte dagli elementi nidificati: Testo di tipo STRING) verranno considerati come inclusi tra virgolette doppie.
12. Nella struttura selezionare `Incoming: File\Root: Sequence\Line: Sequence 1..* \Types: Case\Unparsed: Sequence 1..1`.
    * L'elemento Root\Line\Types\Unparsed di tipo SEQUENCE è stato configurato per analizzare le righe di transazione per la struttura che non corrisponde alla struttura descritta in precedenza nell'elemento CASE padre.

## <a name="review-the-setting-of-the-format-mapping-to-the-data-model"></a>Esaminare l'impostazione del mapping di formato al modello dati

1. Fare clic su Mapping formato a modello.
    * Il modello di mapping "Mapping al modello dal formato CSV" descrive il flusso di dati del trasferimento dati dal file CSV in entrata al modello dati.
2. Fare clic su Progettazione.
3. Nella struttura espandere "format".
    * Si noti che il formato progettato è visualizzato come componente di origine dati.
4. Nella struttura espandere 'format\Incoming: File(Incoming)'.
5. Nella struttura espandere 'format\Incoming: File(Incoming)\Root: Sequence(Root)'.
6. Nella struttura espandere `format\Incoming: File(Incoming)\Root: Sequence(Root)\Line: Sequence 1..* (Line)`.
7. Nella struttura espandere `format\Incoming: File(Incoming)\Root: Sequence(Root)\Line: Sequence 1..* (Line)\Types: Case(Types)`.
8. Nella struttura espandere `format\Incoming: File(Incoming)\Root: Sequence(Root)\Line: Sequence 1..* (Line)\Types: Case(Types)\Record: Sequence 1..1 (,)(Record)`.
9. Nella struttura espandere `format\Incoming: File(Incoming)\Root: Sequence(Root)\Line: Sequence 1..* (Line)\Types: Case(Types)\Record: Sequence 1..1 (,)(Record)\Data`.
10. Nella struttura espandere `format\Incoming: File(Incoming)\Root: Sequence(Root)\Line: Sequence 1..* (Line)\Types: Case(Types)\Record: Sequence 1..1 (,)(Record)\Data\CountryCode: String 0..1 (CountryCode)`.
11. Nella struttura selezionare `format\Incoming: File(Incoming)\Root: Sequence(Root)\Line: Sequence 1..* (Line)\Types: Case(Types)\Record: Sequence 1..1 (,)(Record)\Data\TransactionDate: DateTime(TransactionDate)`.
    * Tenere presente che gli elementi obbligatori e facoltativi del formato, ad esempio TransactionDate e CountryCode, sono diversi nel componente origine dati "formato" predefinito.
12. Nella struttura espandere 'Transactions = '$both''.
    * Tenere presente che gli elementi del formato che definisce la struttura del file importato sono associati agli elementi del modello dati. In base a queste associazioni, il contenuto del file CSV importato verrà archiviato in fase di esecuzione nel modello dati esistente. Si consiglia di prestare attenzione all'associazione dell'elemento CountryRegion. Per qualsiasi elemento di transazione nel file in entrata che non dispone di un valore codice paese specificato, il codice paese predefinito "USA" verrà inserito nel modello dati.
13. Attivare "Mostra dettagli".
14. Fare clic sulla scheda Convalide.
15. Fare clic su Cerca.
16. Digitare 'vend' nel campo Trova.
17. Fare clic su Trova successivo.
    * Il mapping di formato può contenere la logica definita dall'utente per convalidare l'accuratezza dei dati importati dal punto di vista dell'azienda. Ad esempio, in base all'impostazione, per qualsiasi riga del file di importazione la cui struttura non corrisponde né alla struttura della riga di intestazione né alla riga di transazione, verrà generato un messaggio di avviso nel Registro informazioni che informa l'utente su questo caso, indicando il numero sequenziale della transazione nel file.
18. Chiudere la pagina.

## <a name="run-the-format-mapping"></a>Eseguire il mapping di formato

Per scopi di verifica, eseguire il mapping di formato utilizzando il file 1099entriescsv.csv scaricato in precedenza. L'output generato presenterà i dati che verranno importati dal file CSV selezionato e popolati nel modello dati personalizzati al momento dell'importazione effettiva.

1. Fare clic su Esegui.
    * Fare clic su Sfoglia e trovare il file 1099entriescsv.csv in precedenza scaricato.
2. Fare clic su OK.
    * Si osservino i messaggi di avviso sulle righe non accettate. La riga 4 contiene il valore sul reddito presentato in formato non accettabile mentre la riga 7 non contiene il testo di commento della transazione tra virgolette.
    * Esaminare l'output in formato XML, che rappresenta i dati che sono stati importati dal file selezionato e trasferiti nel modello dati. Tenere presente che tutte le 7 righe del file CSV importato sono state elaborate. La riga 1 dei titoli dei campi è stata ignorata, le transazioni 4 sono state correttamente analizzate e le transazioni 2 sono state riconosciute come non valide.
3. Chiudere la pagina.
4. Chiudere la pagina.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]