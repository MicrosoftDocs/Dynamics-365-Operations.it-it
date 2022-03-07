---
title: Configurare l'integrazione con Dayforce
description: Questo argomento descrive i passi di configurazione necessari per l'integrazione tra Microsoft Dynamics 365 Human Resources e Ceridian Dayforce.
author: twheeloc
ms.date: 08/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: PersonnelIntegrationConfiguration
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 7e2043e75aa647e21f3e0816247dcf651be64730
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/31/2022
ms.locfileid: "8067078"
---
# <a name="configure-integration-with-dayforce"></a>Configurare l'integrazione con Dayforce


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

L'integrazione tra Microsoft Dynamics 365 Human Resources e Ceridian Dayforce si basa su vari passaggi di configurazione descritti in questo argomento. È necessario configurare l'integrazione sia in Human Resources che in Dayforce prima di poter elaborare un ciclo di pagamenti.

Quando si utilizza un servizio, ad esempio Dayforce, per completare i cicli di pagamenti, è necessario abilitare l'integrazione in Human Resources. L'integrazione richiede dati specifici da Human Resources. Di conseguenza, è necessario verificare che i dati che vengono mappati a Dayforce siano configurati in Human Resources in modo che supporti l'integrazione. L'integrazione utilizza le seguenti categorie generiche di dati:

- Dati di Risorse umane
- Dati di compensazione
- Data di retribuzione, ad esempio i cicli di pagamenti, i periodi retributivi e i codici reddito
- Dati del lavoratore

Questo argomento descrive i passi da seguire per abilitare l'integrazione e spiega i tipi di dati e i dettagli di configurazione che l'integrazione richiede.

## <a name="enable-the-integration"></a>Abilitare l'integrazione

In Human Resources è necessario attivare l'integrazione e immettere le informazioni di configurazione per connettersi a Dayforce. Se si desidera che la transazione contabile prodotta venga importata in Microsoft Dynamics 365 Finance, è necessario impostare anche un conto di archiviazione di Microsoft Azure e immettere la stringa di connessione di Archiviazione di Azure in Finance.

Per attivare l'integrazione in Human Resources, seguire questi passaggi.

1. Nella pagina **Amministrazione sistema** selezionare **Configurazione di integrazione**.
2. Immettere l'endpoint FTP (File Transfer Protocol) e il percorso protetto della cartella FTP.
3. Immettere il nome utente e la password dell'utente che accederà al percorso protetto dell'endpoint e della cartella FTP.
4. Verificare la connessione, secondo le esigenze, e impostare l'opzione **Abilita integrazione retribuzioni** su **Sì**.

Quando l'integrazione viene attivata, vengono creati i file e il pacchetto di esportazione dei dati e viene impostata la frequenza. È possibile cambiare la frequenza in base alle esigenze.

Per altre informazioni sugli account di Archiviazione di Azure e sulle stringhe di connessione di Archiviazione di Azure, vedere gli argomenti di Azure seguenti:

- [Account di Archiviazione di Azure](/azure/storage/common/storage-create-storage-account?toc=%2fazure%2fstorage%2ffiles%2ftoc.json)
- [Configurare le stringhe di connessione di Archiviazione di Azure](/azure/storage/common/storage-configure-connection-string)

### <a name="technical-details-when-payroll-integration-is-enabled"></a>Dettagli tecnici quando l'integrazione delle retribuzioni è attivata

L'attivazione dell'integrazione delle retribuzioni comporta due effetti primari:

- Viene creato un progetto di esportazione di dati denominato "Esportazione integrazione delle retribuzioni". Questo progetto contiene le entità e i campi necessari per l'integrazione delle retribuzioni. Per esaminare il progetto, andare a **Amministrazione sistema**, selezionare il riquadro **Gestione dati** e infine aprire il progetto dati dall'elenco di progetti.
- Questo processo batch esegue il progetto di esportazione dei dati, codifica il pacchetto dati risultante e trasferisce il file del pacchetto dati all'endpoint SFTP configurato nella schermata **Configurazione di integrazione**.

> [!NOTE]
> Il pacchetto dati trasferito all'endpoint SFTP viene codificato utilizzando una chiave univoca per il pacchetto. La chiave è un Azure Key Vault accessibile solo da Ceridian. Non è possibile decrittografare ed esaminare il contenuto del pacchetto dati. Se è necessario esaminare il contenuto del pacchetto dati, esportare manualmente il progetto dati "Esportazione integrazione delle retribuzioni", scaricarlo e quindi aprirlo. L'esportazione manuale non comporta la crittografia o il trasferimento del pacchetto.

## <a name="configure-your-data"></a>Configurare i dati 

Per elaborare le retribuzioni, è necessario configurare i dati di Risorse umane in Human Resources. È necessario impostare i dati dell'organizzazione, ad esempio mansioni e posizioni, insieme alle informazioni sui benefit e sulle compensazioni. Queste informazioni includono informazioni sull'impiego, la retribuzione e le detrazioni che sono richieste per generare la retribuzione del dipendente.

### <a name="human-resource-data"></a>Dati di Risorse umane

#### <a name="benefits"></a>Benefit 

Le risorse umane dispongono di strumenti per impostare e gestire i benefit, le detrazioni e i piani di retribuzione dei lavoratori che un'organizzazione offre o elabora per i propri lavoratori.

Quando si creano i benefit, tenere presenti i seguenti dati e configurazioni utilizzati in Dayforce.

##### <a name="benefit-plans"></a>Piani di benefit

- Piano (obbligatorio)
- Tipo (obbligatorio)
- Impatto retribuzioni (obbligatorio)
- Recupera arretrati
- Metodo di detrazione
- Priorità detrazione
- Periodo limite
- Importo limite

##### <a name="benefits"></a>Benefit

- Piano (obbligatorio)
- Tipo (obbligatorio)
- Opzione (obbligatoria)
- ID benefit (obbligatorio)
- Frequenza
- Base
- Importo o coefficiente
- Codice di reddito

##### <a name="supported-frequencies"></a>Frequenze supportate 

- Ogni settimana
- Bisettimanale
- Quindicinale
- Ogni mese

##### <a name="supported-bases"></a>Basi supportate 

- Importo fisso
- Percentuale di redditi
- Ore di produzione

Dayforce crea le seguenti detrazioni, in base all'impatto delle retribuzioni definito nel piano di benefit.

| Selezione in Human Resources        | Risultato in Dayforce                            |
|----------------------------|-----------------------------------------------|
| Nessuna                       | Non viene creata alcuna detrazione.                      |
| Solo detrazione             | Viene creata una detrazione del dipendente.             |
| Solo contribuzione          | Viene creata una detrazione del datore di lavoro.             |
| Detrazione e contribuzione | Vengono create detrazioni del datore di lavoro e del dipendente. |

Per altre informazioni su come definire e gestire un programma di benefit, vedere gli argomenti seguenti:

- [Realizzare un programma di benefit per i dipendenti](/dynamics365/unified-operations/fin-and-ops/hr/tasks/deliver-employee-benefits-program)
- [Creare un nuovo benefit](/dynamics365/unified-operations/fin-and-ops/hr/tasks/create-new-benefit)
- [Definire regole e criteri di idoneità ai benefit](/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-benefit-eligibility-rules-policies)
- [Iscrivere e rimuovere benefit da lavoratori](/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-remove-benefits-workers)

#### <a name="compensation"></a>Retribuzione 

La gestione delle retribuzioni consente di controllare la liquidazione dei premi e della retribuzione base. La retribuzione di base fissa di un dipendente e gli aumenti per merito sono controllati mediante piani di retribuzione fissa. È possibile controllare il pagamento degli incentivi, ad esempio il pagamento dei bonus, dei premi produttività, dei diritti di opzione, delle sovvenzioni, oltre che dei premi una tantum, tramite i piani di retribuzione variabile.

Dayforce utilizza le informazioni sulla compensazione per calcolare la retribuzione annuale o oraria di un dipendente. I piani di retribuzione fissa e conversioni della retribuzione sono obbligatori. I dipendenti devono essere associati a un piano di retribuzione fissa.

Per ulteriori informazioni sui piani di retribuzione, vedere gli argomenti seguenti:

- [Creare i piani di retribuzione fissa](/dynamics365/unified-operations/talent/create-fixed-compensation-plans)
- [Creare i piani di retribuzione variabile](/dynamics365/unified-operations/talent/create-variable-compensation-plans)
- [Sviluppare una struttura e piani di stipendi/retribuzioni](/dynamics365/unified-operations/fin-and-ops/hr/tasks/develop-salary-compensation-structure-plan)
- [Processo retributivo](/dynamics365/unified-operations/talent/process-compensation)
- [Definire il processo retributivo e calcolare i risultati](/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-compensation-process-calculate-results)
- [Iscrivere un dipendente a un piano di retribuzione fisso](/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-employee-fixed-compensation-plan)
- [Iscrivere un dipendente a un piano di retribuzione variabile](/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-employee-variable-compensation-plan)

#### <a name="jobs"></a>Mansioni 

Una mansione è una raccolta delle attività e delle responsabilità proprie della persona assegnata a una mansione. Per ulteriori informazioni, vedere i seguenti argomenti:

- [Impostazione dei componenti di una mansione](/dynamics365/unified-operations/talent/create-job)
- [Definire nuovi processi](/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-new-jobs)

##### <a name="positions"></a>Posizioni

Una posizione è una singola istanza di un processo. Ad esempio, la posizione "Manager vendite (Est") è una delle posizioni associate alla mansione "Manager vendite". Una posizione è presente in un reparto. È possibile associare un solo lavoratore a ogni posizione.

Tenere a mente i seguenti dati e la configurazione quando si impostano le posizioni:

- Posizione (obbligatoria)
- Descrizione (obbligatoria)
- Mansione (obbligatoria)
- Reparto (obbligatorio)
- Tipo di posizione (obbligatorio)
- Equivalente a tempo pieno
- Ore regolari annuali (obbligatorie)
- Pagamento in base alla persona giuridica (obbligatorio)
- Ciclo retributivo (obbligatorio).
- Dimensione finanziaria predefinita - Centro di costo (obbligatorio)
- Assegnazione del lavoratore - Lavoratore, inizio assegnazione, fine assegnazione, codice motivo

Se nello stesso reparto più posizioni sono associate alla stessa mansione, vengono consolidate in una singola posizione in Dayforce.

Per ulteriori informazioni, vedere i seguenti argomenti:

- [Organizzare la forza lavoro utilizzando i reparti, le mansioni e le posizioni](/dynamics365/unified-operations/talent/departments-jobs-positions#positions)
- [Impostare le posizioni](/dynamics365/unified-operations/fin-and-ops/hr/tasks/set-up-positions)

#### <a name="departments"></a>Reparti

Un reparto è un'unità operativa che rappresenta una categoria o un'area operativa di un'organizzazione. Un reparto è responsabile di una specifica area dell'organizzazione, ad esempio la vendita, la contabilità o le risorse umane. È possibile utilizzare i reparti per creare report sulle aree operative. I reparti possono essere responsabili di profitti e perdite.

Per ulteriori informazioni, vedere i seguenti argomenti:

- [Creare un reparto e associarlo alla gerarchia reparti](/dynamics365/unified-operations/talent/create-department-add-department-hierarchy)
- [Definire nuovi reparti](/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-new-departments)

#### <a name="pay-cycles-and-pay-periods"></a>Cicli e periodi retributivi

Un ciclo retributivo determina la frequenza di elaborazione delle retribuzioni e i giorni specifici in cui i lavoratori vengono pagati. Un ciclo retributivo può essere ad esempio mensile e i dipendenti possono essere pagati l'ultimo giorno del mese. Un ciclo retributivo può in alternativa essere settimanale e i dipendenti possono essere pagati il giovedì successivo alla fine del periodo retributivo. I cicli retributivi vengono assegnati alle posizioni per controllare quando i lavoratori in tali posizioni vengono pagati.

Dopo aver creato i cicli retributivi, è possibile generare periodi retributivi per ogni ciclo. Ogni periodo retributivo include una data di pagamento predefinita in base alle informazioni specificate. Tuttavia, è possibile modificare la data di pagamento predefinita in un periodo retributivo per consentire eccezioni, ad esempio quando la data di pagamento cade in un giorno festivo.

Le informazioni seguenti vengono utilizzate in Dayforce:

- Ciclo retributivo (obbligatorio).
- Frequenza ciclo retributivo (obbligatoria)
- Data di inizio del periodo (primo periodo retributivo obbligatorio)
- Data di pagamento predefinita (primo periodo retributivo obbligatorio)

Queste informazioni sono integrate con Dayforce come gruppi retributivi e sono separata in base al paese o alla regione per ogni ciclo retributivo. Prima dell'integrazione è necessario generare almeno un periodo retributivo. Dayforce genera calendari di gruppi retributivi e date di pagamento, in base alla data di inizio del primo periodo retributivo e alla data di pagamento predefinita che viene impostata in Human Resources.

#### <a name="earning-codes"></a>Codici di reddito

I codici di reddito identificano in modo univoco ogni tipo di reddito che i lavoratori ricevono. I codici contengono vari parametri correlati ai ricavi, ad esempio regole contabili, leggi fiscali, requisiti di reporting e capacità di calcolo lordo.

Le informazioni seguenti vengono utilizzate in Dayforce:

- Codice di reddito (obbligatorio)
- Descrizione
- Unità di misura
- Produttivo

### <a name="worker-data"></a>Dati del lavoratore

I record per i diversi tipi di lavoratori a disposizione sono importanti per i sistemi di gestione delle risorse umane e delle retribuzioni. Le informazioni immesse possono essere utilizzate per tenere traccia di informazioni personali e sui dipendenti.

È possibile gestire le seguenti informazioni per i lavoratori:

- **Base** - Gestire le informazioni di base su un lavoratore, ad esempio le informazioni sui contatti, le informazioni demografiche, le informazioni di identificazione, le informazioni sulla famiglia, lo stato di servizio militare, le informazioni sull'espatrio, e i contatti personali e di emergenza.
- **Impiego** - Consente di gestire le informazioni sull'impiego di un lavoratore, ad esempio rapporto con l'organizzazione o la società, assegnazione della posizione, date di inizio e fine, idoneità al lavoro, condizioni di impiego, pensionamento, ferie e trasferimento.
- **Congedo e assenza** - Consente di gestire le informazioni sulle assenze di un lavoratore, ad esempio calendari di lavoro, transazioni assenze e impostazione assenze.
- **Retribuzioni** - Consente di gestire le informazioni sui piani di retribuzione di un lavoratore, ad esempio registrazione del piano, premi, prestazioni, provvigione, dati fiscali, pensionamento e detrazioni sullo stipendio.

Quando si immettono le informazioni su un lavoratore, tenere presenti i seguenti dati e le configurazioni utilizzati in Dayforce.

#### <a name="general-information"></a>Informazioni generali

- Numero dipendente (obbligatorio)
- Nome (obbligatorio)
- Cognome (obbligatorio)
- Secondo nome
- Data di anzianità
- Nome noto

#### <a name="personal-information"></a>Informazioni personali

- Stato civile (obbligatorio)
- Data di nascita (obbligatorio)
- Sesso (obbligatorio)
- Persona disabile
- Nazionalità paese regione (solo per il Messico)

#### <a name="address-information"></a>Informazioni indirizzo

- Principale (obbligatorio)
- Paese/regione (obbligatorio)
- Codice postale (obbligatorio)
- Numero civico (obbligatorio) (solo per il Messico)
- Informazioni aggiuntive sull'indirizzo (solo per il Messico)
- Città (obbligatoria)
- Stato (obbligatorio)
- Regione (obbligatoria)

#### <a name="contact-information"></a>Informazioni contatto 

- Principale (obbligatorio)
- Numero contatto (obbligatorio)
- Interno

#### <a name="payroll-information-and-earning-codes"></a>Informazioni sulle retribuzioni e codici di reddito

Ai dipendenti possono essere assegnati redditi specifici a una determinata frequenza di pagamento e un metodo di pagamento preferito. I campi seguenti vengono utilizzati in Dayforce per garantire che le preferenze e le impostazioni vengano utilizzate.

##### <a name="earning-codes"></a>Codici di reddito

- Posizione (obbligatoria)
- Codice di reddito (obbligatorio)
- Frequenza (obbligatoria)
- Importo (obbligatorio)

##### <a name="payroll-information"></a>Informazioni retribuzioni

- Metodo di pagamento
- Area economica (obbligatoria)
- ID benefit dipendente
- Numero documento identità (obbligatorio)
- Numero servizio militare
- ID turno (obbligatorio)
- Numero imposta (obbligatorio)
- ID sindacato (obbligatorio)
- ID giorno lavorativo (obbligatorio)
- Numero permesso di lavoro

> [!NOTE]
> Per il metodo di pagamento, il Messico supporta **Contante**, **Assegno** (l'assegno fisico della società) e **Pagamento elettronico**. Se non viene specificato alcun metodo di pagamento, **Assegno** è 'impostazione predefinita.

#### <a name="employment-details"></a>Dettagli impiego

Lo storico dei dettagli impiego viene utilizzato come informazioni chiave da cui derivare gli stati di assunzione, termine e riassunzione di un dipendente Dayforce. Dayforce supporta solo un record di impiego attivo alla volta.

- Data di inizio impiego (obbligatoria)
- Data di fine impiego
- Data di inizio
- Data di inizio rettificata
- Data fine rapporto (obbligatoria con il fine rapporto)
- Motivo fine rapporto (obbligatorio con il fine rapporto)

Le date chiave del dipendente sono derivate utilizzando le informazioni riportate di seguito.

| Risorse umane                | Dayforce                                                                                             |
|-----------------------|------------------------------------------------------------------------------------------------------|
| Data di assunzione più recente | Inizio dell'impiego del record corrente dello storico di impiego non concluso                                 |
| Data fine rapporto      | Data di fine rapporto del record corrente dello storico di impiego non concluso                                 |
| Data di inizio            | Data di inizio rettificata, data di inizio o inizio dell'impiego del record corrente dello storico di impiego non attivo |
| Data di assunzione originale    | Inizio dell'impiego del record dello storico di impiego meno recente                                               |

#### <a name="compensation"></a>Retribuzione

Un piano di retribuzione fissa deve essere associato alla posizione primaria di ogni dipendente durante un periodo di impiego. Questo periodo inizia alla data in cui il dipendente è stato assunto (o la data di inizio dell'impiego) e continua fino alla fine del rapporto.

- Data di validità (obbligatoria)
- Data di scadenza
- Retribuzione (obbligatoria)
- Conversioni retribuzione (obbligatorio)
- Equivalente annuale (obbligatorio)
- Equivalente orario (obbligatorio)

Se un dipendente a ore ha più posizioni, la retribuzione fissa della posizione primaria viene importata in Dayforce come il tariffa/stipendio di base del dipendente. Per le posizioni non principali, la tariffa oraria viene salvata nella posizione corrispondente in Dayforce.

Se un dipendente stipendiato ha più posizioni, la tariffa oraria cumulativa e lo stipendio annuale di tutte le posizioni attive vengono calcolati e utilizzati come tariffa/stipendio di base del dipendente.

#### <a name="identification-numbers"></a>Numeri di identificazione

##### <a name="social-security-identifier"></a>Numero di Previdenza sociale 

Ogni dipendente deve avere un identificatore primario. Questo identificatore deve essere di tipo identificatore **SSN**. In Dayforce, viene ricavato automaticamente come identificatore di previdenza sociale del dipendente per l'assunzione.

- Principale (obbligatorio)
- Tipo di identificazione = "SSN"
- Data di emissione
- Data di scadenza

I dipendenti possono dichiarare più numeri di identificazione più del tipo di identificazione **SSN**. Tuttavia, solo il record che è contrassegnato come **Primario** viene integrato in Dayforce, a prescindere che il numero sia attivo o scaduto.

#### <a name="bank-accounts-and-disbursements"></a>Esborsi e conti bancari

È necessario immettere informazioni sul conto bancario valide per un dipendente che scelga di essere pagato tramite trasferimenti di conto bancario.

| Risorse umane                         | Dayforce                                                                                                    |
|--------------------------------|-------------------------------------------------------------------------------------------------------------|
| Numero conto bancario (obbligatorio) |                                                                                                             |
| Codice SWIFT (obbligatorio)          | Campo **ID banca** utilizzato durante l'elaborazione delle retribuzioni in Messico.                                                             |
| Codice filiale (obbligatorio)       |                                                                                                             |
| Tipo di conto bancario (obbligatorio)   | Campo **Tipo di conto** utilizzando durante l'elaborazione delle retribuzioni in Messico. I valori supportati includono **Controllo** e **Retribuzioni**. |

> [!NOTE]
> I dipendenti che scelgono di essere pagati tramite trasferimenti di conto bancario devono fornire un collegamento a un conto rimanente che è sotto la persona giuridica che ha l'indirizzo primario in Messico ed è associato a un conto bancario valido presso una banca messicana. Tutti gli altri account non di rimanenze verranno ignorati.

#### <a name="address-information"></a>Informazioni indirizzo

Ogni dipendente deve avere un'ubicazione primaria. In Dayforce, questa ubicazione viene utilizzata per determinare la principale residenza del dipendente a scopo fiscale.

- Principale (obbligatorio)
- Paese/regione (obbligatorio)
- CAP/Codice postale (obbligatorio)
- Via (obbligatoria)
- Numero civico (obbligatorio)
- Informazioni aggiuntive sull'indirizzo
- Città (obbligatoria)
- Stato (obbligatorio)
- Regione (obbligatoria)

## <a name="configure-your-data-to-generate-payroll-in-united-states-and-canada"></a>Configurare i dati per generare le retribuzioni negli Stati Uniti e in Canada

Se si desidera generare la retribuzione per i dipendenti negli Stati Uniti e in Canada, i seguenti elementi devono essere configurati:

- I reparti sono necessari nelle posizioni.
- I centri di costo devono essere impostati come dimensioni finanziarie ed essere il primo elemento nella stringa della dimensione finanziaria predefinita.

> [!NOTE] 
> È possibile configurare Human Resources per far sì che Posizioni specifichi un reparto. A tale scopo, andare a **Posizioni condivise Risorse umane > Posizioni > Richiedi reparti su posizioni**. Si consiglia di applicare questa impostazione per l'integrazione.

### <a name="job-types"></a>Tipi di lavoro

I tipi di mansione vengono utilizzati per raggruppare mansioni simili in categorie. I tipi di mansione sono necessari per elaborare le retribuzioni negli Stati Uniti e in Canada. Alcuni esempi di tipi di mansione includono il tempo pieno e il part-time o stipendio e retribuzione oraria. I tipi di mansioni vengono mappati in Dayforce come tipi di retribuzione che indicano se un dipendente viene pagato a ore o è stipendiato.

I seguenti tipi di mansione e le descrizioni sono obbligatori.

| Tipo di processo   | Descrizione |
|------------|-------------|
| Su base oraria     | Su base oraria      |
| Stipendiato   | Stipendiato    |

### <a name="position-types"></a>Tipi di posizione 

Si utilizzano i tipi di posizione per descrivere se è la posizione è a tempo pieno, part-time o altro. I tipi di posizione vengono mappati in Dayforce come classi di retribuzione che indicano se un dipendente viene pagato a tempo pieno o part-time.

I seguenti tipi di posizione e le descrizioni sono obbligatori.

| Tipo di posizione   | Descrizione        |
|-----------------|--------------------|
| A tempo pieno       | Dipendente a tempo pieno |
| A tempo parziale       | Dipendente a tempo parziale |

### <a name="reason-codes"></a>Codici causale

I codici motivo forniscono informazioni sullo stato di un dipendente. I codici motivo vengono mappati in Dayforce come motivi di stato che indicano il motivo dei cambiamenti nella posizione del dipendente o nello stato di impiego.

I seguenti codici motivo e le descrizioni sono obbligatori.

| Codice motivo    | Descrizione      | Scenari applicabili |
|----------------|------------------|----------------------|
| RESIGNATION    | Dimissioni      | Termina rapporto con lavoratore     |
| TERMINATION    | Fine      | Termina rapporto con lavoratore     |
| RETIREMENT     | Pensione       | Termina rapporto con lavoratore     |
| OTHER          | Altri motivi    | Termina rapporto con lavoratore     |
| DEATH          | Decesso            | Termina rapporto con lavoratore     |
| LEAVEOFABSENCE | Congedo e assenza | Termina rapporto con lavoratore     |
| CONTRACTEND    | Fine di contratto  | Termina rapporto con lavoratore     |
| SALARYCHANGE   | Modifica dello stipendio | Retribuzione         |

### <a name="marital-status"></a>Stato civile

I valori dello stato civile vengono mappati in Dayforce e tradotti, come appropriato, nei valori accettati con l'integrazione.

Nella tabella seguente vengono illustrati in che modo i valori dello stato civile vengono mappati in Dayforce.

| Risorse umane                 | Dayforce             |
|------------------------|----------------------|
| Sposato/a                | Sposato/a              |
| Celibe/nubile                 | Celibe/nubile               |
| Vedovo/a                | Vedovo/a              |
| Divorziato/a               | Divorziato/a             |
| Relazione registrata | Relazione nazionale |
| Nessuna                   | Nessuna                 |
| Coabitazione             | Coabitazione           |

### <a name="gender"></a>Genere

Le designazioni di sesso vengono mappate in Dayforce e tradotte, come appropriato, nei valori accettati con l'integrazione.

Nella tabella seguente vengono illustrati in che modo le designazioni di sesso vengono mappate in Dayforce.

| Risorse umane       | Dayforce        |
|--------------|-----------------|
| Maschio         | Maschio            |
| Femmina       | Femmina          |
| Non specifico | *Non supportato* |

### <a name="earning-codes"></a>Codici di reddito

I codici di reddito identificano in modo univoco ogni tipo di reddito che i lavoratori ricevono. I codici contengono vari parametri correlati ai ricavi, ad esempio regole contabili, leggi fiscali, requisiti di reporting e capacità di calcolo lordo. Se una frequenza non supportata viene utilizzata, la frequenza **Ogni retribuzione** viene utilizzata per impostazione predefinita per il calcolo.

#### <a name="supported-frequencies"></a>Frequenze supportate

- Tutti
- EVERYPAY
- EACHPAYPERIOD
- EVRYOTHRPAYODD
- EVRYOTHRPAYEVN
- 1OFMTH
- LASTOFMTH
- 2OFMTH
- 3OFMTH
- 4OFMTH
- 5OFMTH
- 1N2OFMTH
- 3N4OFMTH
- 1N3OFMTH
- 1N4OFMTH
- 2N3OFMTH
- 2N4OFMTH
- 1N2N3OFMTH
- 1N2N4OFMTH
- 1N3N4OFMTH
- 2N3N4OFMTH
- 1N2N3N4OFMTH - 1N2N3N4OFMTH
- 2N3N4N5OFMth - 2N3N4N5OFMth
- 1OFQTR - 1OFQTR
- LASTOFQTR - LASTOFQTR
- LASTMTHOFQTR - LASTMTHOFQTR
- 1OFYEAR - 1OFYEAR
- LASTOFYEAR - LASTOFYEAR
- NOVNDECOFYEAR - NOVNDECOFYEAR

### <a name="addresses"></a>Indirizzi

L'identificazione del paese specifico o dei codici di paese, stato e provincia (municipalità) richiede formati specifici che i fornitori di Dayforce e nazionali/regionali possono riconoscere. Sebbene il formato per le città sia flessibile, ogni città deve essere associata a uno stato.

| Risorse umane          | Dayforce              |
|-----------------|-----------------------|
| Paese/area geografica  | Codice paese          |
| CAP/Codice postale | CAP           |
| Stato/regione           | Codice stato            |
| Città            | Città                  |
| Regione          | Provincia (municipalità) |
| Via          | Riga indirizzo 1        |

### <a name="tax-regions"></a>Regioni fiscali

Le regioni fiscali vengono utilizzate per determinare l'imposta appropriata che deve essere applicata durante la generazione delle retribuzioni. Le regioni fiscali vengono mappate in Dayforce come indirizzi di ubicazione. La regione fiscale predefinita deve essere associata alla posizione attiva del lavoratore. 

- Regione fiscale (obbligatoria)
- Paese/regione (obbligatorio)
- Stato (obbligatorio)
- Regione 
- Città (obbligatoria)

## <a name="configure-your-data-to-generate-payroll-in-mexico"></a>Configurare i dati per generare le retribuzioni in Messico

Se si desidera generare la retribuzione per i dipendenti in Messico, i seguenti elementi devono essere configurati:

- I reparti sono necessari nelle posizioni.
- I centri di costo devono essere impostati come dimensioni finanziarie ed essere il primo elemento nella stringa della dimensione finanziaria predefinita.

### <a name="job-types"></a>Tipi di posizione lavorativa

I tipi di mansione vengono utilizzati per raggruppare mansioni simili in categorie. Tipi di mansione necessari per elaborare le retribuzioni in Messico. Alcuni esempi di tipi di mansione includono il tempo pieno e il part-time o stipendio e retribuzione oraria. I tipi di mansioni vengono mappati in Dayforce come tipi di retribuzione che indicano se un dipendente viene pagato a ore o è stipendiato.

I seguenti tipi di mansione e le descrizioni sono obbligatori.

| Tipo di processo   | Descrizione |
|------------|-------------|
| Su base oraria     | Su base oraria MX   |
| Stipendiato   | Stipendiato MX |

### <a name="position-types"></a>Tipi di posizione 

Si utilizzano i tipi di posizione per descrivere se è la posizione è a tempo pieno, part-time o altro. I tipi di posizione vengono mappati in Dayforce come classi di retribuzione che indicano se un dipendente viene pagato a tempo pieno o part-time.

I seguenti tipi di posizione e le descrizioni sono obbligatori.

| Tipo di posizione   | Descrizione        |
|-----------------|--------------------|
| A tempo pieno       | Dipendente a tempo pieno |
| A tempo parziale       | Dipendente a tempo parziale |

### <a name="reason-codes"></a>Codici causale

I codici motivo forniscono informazioni sullo stato di un dipendente. I codici motivo vengono mappati in Dayforce come motivi di stato che indicano il motivo dei cambiamenti nella posizione del dipendente o nello stato di impiego.

I seguenti codici motivo e le descrizioni sono obbligatori.

| Codice motivo            | Descrizione                    | Scenari applicabili |
|------------------------|--------------------------------|----------------------|
| DEPARTUREBEFOREPAYMENT | Partenza prima della prima retribuzione | Termina rapporto con lavoratore     |
| RESIGNATION            | Dimissioni                    | Termina rapporto con lavoratore     |
| PENSION                | Pensionamento                        | Termina rapporto con lavoratore     |
| TERMINATION            | Fine                    | Termina rapporto con lavoratore     |
| RETIREMENT             | Pensione                     | Termina rapporto con lavoratore     |
| ABSENTEE               | Assente                       | Termina rapporto con lavoratore     |
| OTHER                  | Altri motivi                  | Termina rapporto con lavoratore     |
| CLOSURE                | Chiusura attività               | Termina rapporto con lavoratore     |
| DEATH                  | Decesso                          | Termina rapporto con lavoratore     |
| LEAVEOFABSENCE         | Congedo e assenza               | Termina rapporto con lavoratore     |
| CONTRACTEND            | Fine di contratto                | Termina rapporto con lavoratore     |
| SALARYCHANGE           | Modifica dello stipendio               | Retribuzione         |

### <a name="terms-of-employment"></a>Condizioni di impiego

Le condizioni di impiego vengono utilizzate per creare categorie di termini di impiego. I termini vengono mappati in Dayforce come valori degli indicatori di impiego.

I seguenti termini di impiego e le descrizioni sono obbligatori.

| Condizioni di impiego   | Descrizione |
|-----------------------|-------------|
| Regolare               | Regolare     |
| Diretto                | Diretto      |
| Internato            | Internato  |
| Permanente             | Permanente   |

### <a name="marital-status"></a>Stato civile

I valori dello stato civile vengono mappati in Dayforce e tradotti, come appropriato, nei valori accettati con l'integrazione.

Nella tabella seguente vengono illustrati in che modo i valori dello stato civile vengono mappati in Dayforce.

| Risorse umane                 | Dayforce                  |
|------------------------|---------------------------|
| Sposato/a                | Sposato/a                   |
| Celibe/nubile                 | Celibe/nubile                    |
| Vedovo/a                | Vedovo/a                   |
| Divorziato/a               | Divorziato/a                  |
| Relazione registrata | Relazione nazionale      |
| Nessuna                   | *Non supportato in Messico* |
| Coabitazione             | *Non supportato in Messico* |

### <a name="gender"></a>Genere

Le designazioni di sesso vengono mappate in Dayforce e tradotte, come appropriato, nei valori accettati con l'integrazione.

Nella tabella seguente vengono illustrati in che modo le designazioni di sesso vengono mappate in Dayforce.

| Risorse umane       | Dayforce                  |
|--------------|---------------------------|
| Maschio         | Maschio                      |
| Femmina       | Femmina                    |
| Non specifico | *Non supportato in Messico* |

### <a name="payment-method"></a>Metodo di pagamento

I metodi di pagamento offrono al dipendente e all'azienda un modo per descrivere la modalità di pagamento dei dipendenti. I metodi di pagamento vengono mappati in Dayforce e tradotti, come appropriato, nei valori accettati con l'integrazione.

Nella tabella seguente vengono illustrati in che modo i metodi di pagamento vengono mappati in Dayforce.

| Risorse umane             | Dayforce                  |
|--------------------|---------------------------|
| Contanti               | Contanti                      |
| Pagamento elettronico | Trasferimenti                  |
| Seleziona              | Assegno                    |
| Assegno circolare         | *Non supportato in Messico* |
| Altro              | *Non supportato in Messico* |

### <a name="bank-account-type"></a>Tipo di conto bancario

I tipi di conto bancario vengono utilizzati per i pagamenti elettronici ai dipendenti. I tipi di conto bancario vengono mappati in Dayforce come informazioni sul conto di trasferimento. I tipi di conto bancario vengono convertiti, come appropriato, nei valori accettati per l'integrazione.

| Risorse umane            | Dayforce                  |
|-------------------|---------------------------|
| Conto corrente  | CheckingAccount           |
| Conto retribuzioni   | PayrollAccount            |
| Conto di risparmio   | *Non supportato in Messico* |
| Conto Bankgirot | *Non supportato in Messico* |
| Conto PlusGirot | *Non supportato in Messico* |

### <a name="earning-codes"></a>Codici di reddito

I codici di reddito identificano in modo univoco ogni tipo di reddito che i lavoratori ricevono. I codici contengono vari parametri correlati ai ricavi, ad esempio regole contabili, leggi fiscali, requisiti di reporting e capacità di calcolo lordo. Se una frequenza non supportata viene utilizzata, la frequenza **Ogni retribuzione** viene utilizzata per impostazione predefinita per il calcolo.

#### <a name="supported-frequencies"></a>Frequenze supportate

- Tutti
- EVERYPAY
- EACHPAYPERIOD
- EVRYOTHRPAYODD
- EVRYOTHRPAYEVN
- 1OFMTH
- LASTOFMTH
- 2OFMTH
- 3OFMTH
- 4OFMTH
- 5OFMTH
- 1N2OFMTH
- 3N4OFMTH
- 1N3OFMTH
- 1N4OFMTH
- 2N3OFMTH
- 2N4OFMTH
- 1N2N3OFMTH
- 1N2N4OFMTH
- 1N3N4OFMTH
- 2N3N4OFMTH
- 1N2N3N4OFMTH - 1N2N3N4OFMTH
- 2N3N4N5OFMth - 2N3N4N5OFMth
- 1OFQTR - 1OFQTR
- LASTOFQTR - LASTOFQTR
- LASTMTHOFQTR - LASTMTHOFQTR
- 1OFYEAR - 1OFYEAR
- LASTOFYEAR - LASTOFYEAR
- NOVNDECOFYEAR - NOVNDECOFYEAR

### <a name="addresses"></a>Indirizzi

L'identificazione del paese specifico o dei codici di paese, stato e provincia (municipalità) richiede formati specifici che i fornitori di Dayforce e nazionali/regionali possono riconoscere. Sebbene il formato per le città sia flessibile, ogni città deve essere associata a uno stato.

| Risorse umane              | Dayforce              |
|---------------------|-----------------------|
| Paese/area geografica      | Codice paese          |
| CAP/Codice postale     | CAP           |
| Stato/regione               | Codice stato            |
| Città                | Città                  |
| Regione              | Provincia (municipalità) |
| Via              | Riga indirizzo 1        |
| Numero civico       | Riga indirizzo 2        |
| Informazioni aggiuntive sull'indirizzo | Riga indirizzo 5        |

### <a name="passport-number"></a>Numero passaporto

I dipendenti possono indicare le informazioni sul passaporto. Queste informazioni sono del tipo di identificazione **Passaporto** e vengono integrate in Dayforce come parte delle informazioni di un dipendente specifiche per il Messico.

- Tipo di identificazione = "Passaporto"
- Data di emissione
- Data di scadenza

I dipendenti possono dichiarare più numeri di identificazione più del tipo di identificazione **Passaporto**. Tuttavia, solo l'immissione del passaporto attivo corrente viene integrata in Dayforce. Se tutte le immissioni di passaporto sono scadute, in Dayforce viene integrato il passaporto di emissione più recente.



[!INCLUDE[footer-include](../includes/footer-banner.md)]
