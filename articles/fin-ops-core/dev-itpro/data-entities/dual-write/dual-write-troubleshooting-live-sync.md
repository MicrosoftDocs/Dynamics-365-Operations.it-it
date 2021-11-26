---
title: Risoluzione dei problemi di sincronizzazione in tempo reale
description: Questo argomento fornisce informazioni che possono aiutarti a risolvere i problemi relativi alla sincronizzazione in tempo reale.
author: RamaKrishnamoorthy
ms.date: 08/19/2021
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: 69667f8b64c048f5957168d1af21a6c858bc0bad
ms.sourcegitcommit: 9acfb9ddba9582751f53501b82a7e9e60702a613
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/10/2021
ms.locfileid: "7782581"
---
# <a name="troubleshoot-live-synchronization-issues"></a>Risoluzione dei problemi di sincronizzazione in tempo reale

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

In questo argomento vengono fornite informazioni sulla risoluzione dei problemi di integrazione della doppia scrittura tra le app Finance and Operations e Microsoft Dataverse. In particolare, fornisce informazioni che possono aiutarti a risolvere i problemi relativi alla sincronizzazione in tempo reale.

> [!IMPORTANT]
> Alcuni problemi che questo argomento tratta potrebbero richiedere il ruolo di amministratore di sistema o le credenziali di amministratore del tenant Azure Active Directory (Azure AD). Ogni sezione spiega se sono richiesti ruolo o credenziali specifici.

## <a name="live-synchronization-shows-an-error-when-you-create-a-row"></a>La sincronizzazione in tempo reale mostra un errore quando si crea una riga

È possibile che venga visualizzato il seguente messaggio di errore quando si crea una riga in un'app Finance and Operations:

*\[{\\"errore\\":{\\"codice\\":\\"0x80072560\\",\\"messaggio\\":\\"L'utente non è un membro dell'organizzazione.\\"}}\], Il server remoto ha restituito un errore: (403) Accesso negato."}}".*

Per risolvere il problema, seguire i passaggi in [Requisiti e prerequisiti di sistema](requirements-and-prerequisites.md). Per completare questi passaggi, gli utenti dell'applicazione di doppia scrittura che sono stati creati in Dataverse devono avere il ruolo di amministratore di sistema. Anche il team proprietario predefinito deve avere il ruolo di amministratore di sistema.

## <a name="live-synchronization-shows-an-error-when-you-try-to-save-table-data"></a>La sincronizzazione in tempo reale mostra un errore quando si tenta di salvare i dati della tabella

**Ruolo richiesto per risolvere il problema:** amministratore di sistema

È possibile che venga visualizzato il seguente messaggio di errore quando si tenta di salvare dati di tabella in un'app Finance and Operations:

*Impossibile salvare le modifiche nel database. L'unità di lavoro non può eseguire il commit della transazione. Impossibile scrivere i dati nell'entità unità di misura. Scrittura su UnitOfMeasureEntity non riuscita con messaggio di errore Impossibile sincronizzare con l'entità unità di misura.*

Per risolvere il problema, assicurarsi che i dati di riferimento dei prerequisiti esistano nell'app Finance and Operations e in Dataverse. Ad esempio, se un record cliente appartiene a un gruppo di clienti specifico, assicurarsi che il record del gruppo di clienti esista in Dataverse.

Se i dati esistono in entrambe le posizioni e si conferma che il problema non è relativo ai dati, procedere nel seguente modo.

1. Aprire l'entità **DualWriteProjectConfigurationEntity** utilizzando il componente aggiuntivo di Excel. Per utilizzare il componente aggiuntivo, abilitare la modalità di progettazione nel componente aggiuntivo di Excel di Finance and Operations e aggiungere **DualWriteProjectConfigurationEntity** a un foglio di lavoro. Per ulteriori informazioni, vedi [Visualizzare e aggiornare i dati entità con Excel](../../office-integration/use-excel-add-in.md).
2. Selezionare ed eliminare i record che presentano problemi nella mappa e nel progetto a doppia scrittura. Vi saranno due record per ogni mapping a doppia scrittura.
3. Pubblicare le modifiche utilizzando il componente aggiuntivo di Excel. Questo passaggio è importante perché elimina i record dall'entità e dalle tabelle sottostanti.

## <a name="handle-read-or-write-privilege-errors-when-you-create-data-in-a-finance-and-operations-app"></a>Gestire gli errori dei privilegi di lettura o scrittura quando si creano i dati in un'app Finance and Operations

È possibile che venga visualizzato un messaggio di errore "Richiesta non valida" quando si creano dati in un'app Finance and Operations.

![Esempio del messaggio di errore Richiesta non valida.](media/error_record_id_source.png)

Per risolvere il problema, è necessario abilitare il privilegio mancante assegnando il ruolo di sicurezza corretto al team delle Business Unit Dynamics 365 Sales o Dynamics 365 Customer Service mappate.

1. Nell'app Finance and Operations, trovare la Business Unit mappata nel set di connessioni Integrazione dati.

    ![Mapping dell'organizzazione.](media/mapped_business_unit.png)

2. Nell'app Customer Engagement, accedere all'ambiente, andare a **Impostazioni \> Sicurezza** e trovare il team della Business Unit mappata.

    ![Team della Business Unit mappata.](media/setting_security_page.png)

3. Aprire la pagina del team per la modifica, quindi selezionare **Gestisci ruoli**.

    ![Pulsante Gestisci ruoli.](media/manage_team_roles.png)

4. Nella finestra di dialogo **Gestisci ruoli del team**, assegnare il ruolo che dispone del privilegio di lettura/scrittura per le tabelle pertinenti, quindi selezionare **OK**.

## <a name="fix-synchronization-issues-in-an-environment-that-has-a-recently-changed-dataverse-environment"></a>Risoluzione dei problemi di sincronizzazione in un ambiente in cui è stato recentemente modificato Dataverse

**Ruolo richiesto per risolvere il problema:** amministratore di sistema

È possibile che venga visualizzato il seguente messaggio di errore quando si creano dati in un'app Finance and Operations:

*{"entityName":"CustCustomerV3Entity","executionStatus":2,"fieldResponses":\[\],"recordResponses":\[{"errorMessage":"**Impossibile generare il payload per l'entità CustCustomerV3Entity**","logDateTime":"2019-08-27T18:51:52.5843124Z","verboseError":"Creazione del payload non riuscita con errore URI non valido: L'URI è vuoto."}\],"isErrorCountUpdated":true}*

Di seguito è indicato l'errore nell'app Customer Engagement:

> Si è verificato un errore imprevisto del codice ISV. (ErrorType = ClientError) Eccezione imprevista dal plug-in (Execute): Microsoft.Dynamics.Integrator.DualWriteRuntime.Plugins.PostCommitPlugin: System.Exception: impossibile elaborare l'account dell'entità - Tentativo di connessione non riuscito perché la parte connessa non ha risposto correttamente dopo un periodo di tempo o connessione stabilita non riuscita perché l'host connesso non ha risposto.

Questo errore si verifica se l'ambiente Dataverse viene reimpostato in modo errato quando si tenta di creare dati nell'app Finance and Operations.

> [!IMPORTANT]
> Se gli ambienti sono stati ricollegati, è necessario interrompere tutte le mappe di entità prima di continuare con i passaggi di mitigazione.

Per risolvere il problema, è necessario completare i passaggi sia in Dataverse che nell'app Finance and Operations.

1. Nell'app Finance and Operations, effettuare le seguenti operazioni:

    1. Aprire l'entità **DualWriteProjectConfigurationEntity** utilizzando il componente aggiuntivo di Excel. Per utilizzare il componente aggiuntivo, abilitare la modalità di progettazione nel componente aggiuntivo di Excel di Finance and Operations e aggiungere **DualWriteProjectConfigurationEntity** a un foglio di lavoro. Per ulteriori informazioni, vedi [Visualizzare e aggiornare i dati entità con Excel](../../office-integration/use-excel-add-in.md).
    2. Selezionare ed eliminare i record che presentano problemi nella mappa e nel progetto a doppia scrittura. Vi saranno due record per ogni mapping a doppia scrittura.
    3. Pubblicare le modifiche utilizzando il componente aggiuntivo di Excel. Questo passaggio è importante perché elimina i record dall'entità e dalle tabelle sottostanti.
    4. Per aiutare a prevenire errori quando si ricollegano gli ambienti Finance and Operations o Dataverse, assicurarsi che non rimangano configurazioni a doppia scrittura.

2. In Dataverse, effettuare le seguenti operazioni:

    1. Accedere al proprio ambiente Dataverse (ad esempio `https://*****.crm.dynamics.com/`).
    2. Andare a **Impostazioni avanzate** \> **Ricerca avanzata**.
    3. Selezionare **Configurazione di runtime DualWrite**.
    4. Selezionare la colonna da visualizzare.
    5. Selezionare **Risultati** per visualizzare le configurazioni.
    6. Eliminare tutte le istanze.

3. Nell'app Finance and Operations, effettuare le seguenti operazioni:

    1. Aprire l'entità **DualWriteProjectConfigurationEntity** utilizzando il componente aggiuntivo di Excel. Per utilizzare il componente aggiuntivo, abilitare la modalità di progettazione nel componente aggiuntivo di Excel di Finance and Operations e aggiungere **DualWriteProjectConfigurationEntity** a un foglio di lavoro. Per ulteriori informazioni, vedi [Visualizzare e aggiornare i dati entità con Excel](../../office-integration/use-excel-add-in.md).
    2. Selezionare ed eliminare i record che presentano problemi nella mappa e nel progetto a doppia scrittura. Vi saranno due record per ogni mapping a doppia scrittura.
    3. Pubblicare le modifiche utilizzando il componente aggiuntivo di Excel. Questo passaggio è importante perché elimina i record dall'entità e dalle tabelle sottostanti.
    4. Per aiutare a prevenire errori quando si ricollegano gli ambienti Finance and Operations o Dataverse, assicurarsi che non rimangano configurazioni a doppia scrittura.

## <a name="live-synchronization-error-after-you-do-a-full-database-copy"></a>Errore di sincronizzazione in tempo reale dopo aver eseguito una copia completa del database

È possibile che venga visualizzato il seguente messaggio di errore dopo aver eseguito una copia completa del database da un sistema a un altro e aver tentato di eseguire un'operazione sul database:

*L'organizzazione SecureConfig (???) non corrisponde all'effettiva organizzazione CRM (???).*

Il messaggio di errore viene visualizzato dal plug-in di runtime a doppia scrittura per garantire che la configurazione a doppia scrittura impostata in un sistema non possa essere utilizzata in un altro sistema.

Per risolvere il problema, eliminare tutti i record nella tabella **msdyn_dualwriteruntimeconfig** dopo aver ripristinato il database. Per ulteriori informazioni, vedere [Scollegare e ricollegare ambienti a doppia scrittura](relink-environments.md).

## <a name="live-synchronization-issues-that-are-caused-by-incorrect-query-filter-syntax-on-the-dual-write-maps"></a>Problemi di sincronizzazione in tempo reale causati da una sintassi errata del filtro di query sulle mappe a doppia scrittura

Anche se l'espressione di query per un filtro di mappa a doppia scrittura è sintatticamente corretta, potrebbe non funzionare come previsto. L'espressione filtro si trova su un'entità, non su una singola origine dati di un oggetto query. Pertanto, la query SQL generata non restituisce i risultati previsti.

Ecco un esempio.

```dos
Query entity = PROJECTENTITY
Query expression = (ParentProject == "")
```

Ci si protebbe aspettare che i progetti senza padre vengano filtrati. Tuttavia, il filtro non funziona perché viene tradotto in una query simile all'esempio seguente.

```sql
SELECT T1.RECID,T1.MODIFIEDDATETIME,T1.RECVERSION,T1.RECID,T1.DIMENSION,
T1.LOCATION,T1.PROJECTCONTROLLER,T1.PROJECTID,T1.PROJECTMANAGER,T1.REFERENCE,
T1.SALESMANAGER,T1.SCHEDULED,T1.RECVERSION#8,T1.RECVERSION#7,
T1.RECVERSION#6,T1.RECVERSION#5,T1.RECVERSION#4,T1.RECVERSION#3,
T1.RECVERSION#2,T1.RECID#8,T1.RECID#7,T1.RECID#6,T1.RECID#5,
T1.RECID#4,T1.RECID#3,T1.RECID#2,T1.PARTITION FROM PROJECTENTITY T1 
WHERE(((((((((((PARTITION=5637144576) AND (DATAAREAID=N'usmf')) AND 
((PARTITION#2=5637144576) OR (PARTITION#2 IS NULL))) AND 
((PARTITION#3=5637144576) OR (PARTITION#3 IS NULL))) AND 
((PARTITION#4=5637144576) OR (PARTITION#4 IS NULL))) AND 
((PARTITION#5=5637144576) OR (PARTITION#5 IS NULL))) AND 
((PARTITION#6=5637144576) OR (PARTITION#6 IS NULL))) AND 
((PARTITION#7=5637144576) OR (PARTITION#7 IS NULL))) AND 
((PARTITION#8=5637144576) OR (PARTITION#8 IS NULL))) AND 
((DATAAREAID#8=N'usmf') OR (DATAAREAID#8 IS NULL))) AND 
(PARENTPROJECT='')) 
ORDER BY T1.PROJECTID
```

Il risultato effettivo è che il campo `parentProject` viene valutato come `null`. Tuttavia, `null` non corrisponde alla stringa vuota. A causa di questa mancata corrispondenza, il filtro di query non restituisce risultati validi.

Per risolvere il problema, procedere come segue.

1. Aggiungere una colonna calcolata che può essere aggiunta in un modello di estensione e che è supportata da una logica che converte `null` nella stringa vuota.

    ```dos
    SysComputedColumn::if(SysComputedColumn::isNullExpression(ParentProject), SysComputedColumn::returnLiteral(""), fieldName);
    ```

2. Utilizzare il filtro sulla nuova colonna calcolata anziché sulla colonna predefinita.

Per valutare il filtro in un ambiente di sviluppo, è possibile utilizzare il seguente codice X++ per convalidare i risultati. Eseguire questo codice come programma autonomo. È possibile utilizzarlo per valutare diversi tipi di filtri applicabili a un'entità prima di utilizzare tali filtri su mappe a doppia scrittura. La query può essere eseguita sul database per valutare le discrepanze.

```xpp
var entityName = "PROJECTENTITY";
var filterExpression = '(ParentProject == "")';
Query query = new Query();
query.literals(NoYes::Yes); 
QueryBuildDataSource qbd = query.addDataSource(tablename2id(entityName));
qbd.addRange(fieldname2id(qbd.table(),identifierStr(RecVersion))).value(filterExpression);
qbd.addSelectionField(fieldname2id(qbd.table(),identifierStr(RecId)));
QueryRun qRun = new QueryRun(query);
// This provides the actual sql statement to execute
var actualSqlStatement = query.getSQLStatement();
while(qRun.next())
{
    var rec = qRun.get(tableName2Id(entityName));
}
```

## <a name="data-from-finance-and-operations-apps-isnt-synced-to-dataverse"></a>Dati dall'app Finance and Operations non sono sincronizzati in Dataverse

Durante la sincronizzazione in tempo reale, si potrebbe riscontrare un problema per cui solo una parte dei dati viene sincronizzata dalle app Finance and Operations in Dataverse o i dati non vengono sincronizzati affatto.

> [!NOTE]
> È necessario risolvere questo problema durante la fase di sviluppo.

Prima di iniziare a risolvere il problema, rivedere i seguenti prerequisiti:

+ Assicurarsi che le modifiche personalizzate siano scritte in un unico ambito di transazione.
+ Gli eventi aziendali e il framework a doppia scrittura non gestiscono operazioni `doinsert()`, `doUpdate()` e `recordset()` o record in cui `skipBusinessEvents(true)` è contrassegnato. Se il codice è all'interno di queste funzioni, la doppia scrittura non verrà attivata.
+ Gli eventi aziendali devono essere registrati per l'origine dati mappata. Alcune origini dati potrebbero utilizzare un outer join e potrebbero essere contrassegnate come di sola lettura nelle app Finance and Operations. Queste origini dati non vengono tracciate.
+ Le modifiche verranno attivate solo se sono sui campi mappati. Le modifiche ai campi non mappati non attiveranno la doppia scrittura.
+ Assicurarsi che le valutazioni dei filtri forniscano un risultato valido.

### <a name="troubleshooting-steps"></a>Passaggi per la risoluzione dei problemi

1. Rivedere i mapping dei campi nella pagina di amministrazione a doppia scrittura. Se un campo non è mappato dalle app Finance and Operations in Dataverse, non verrà tracciato. Ad esempio, nella figura seguente, il campo **Descrizione** è tracciato da Dataverse ma non dalle app Finance and Operations. Nessuna modifica a tale campo all'interno delle app Finance and Operations verrà tracciata.

    ![Campo tracciato.](media/live-sync-troubleshooting-1.png)

2. Determinare se l'origine dati è tracciata nella definizione degli eventi aziendali. Ad esempio, nella figura seguente, nessun campo dalla tabella **DefaultDimensionDAVs** e dalle tabelle sottostanti verrà tracciato per le modifiche. Le origini dati che utilizzano un outer join e che sono contrassegnate come di sola lettura non vengono tracciate.

    ![Campo non tracciato.](media/live-sync-troubleshooting-2.png)

3. Determinare se i campi della tabella mappati vengono visualizzati nella tabella **BUSINESSEVENTSDEFINITION**, come mostrato nella figura seguente. Se non si trova il campo che si sta cercando nel risultato della query, il campo non verrà attivato dalla doppia scrittura.

    ![Campo tracciato nella tabella.](media/live-sync-troubleshooting-3.png)

### <a name="sample-scenario"></a>Scenario di esempio

Nelle app Finance and Operations, è presente un aggiornamento all'indirizzo per un record di contatto, ma la modifica dell'indirizzo non è sincronizzata in Dataverse. Questo scenario si verifica perché nessun record nella tabella **BusinessEventsDefinition** ha la combinazione della tabella interessata e dell'entità. Nello specifico, la tabella **LogisticsPostalAddress** non è l'origine dati diretta per l'entità **smmContactpersonCDSV2Entity**. L'entità **smmContactpersonCDSV2Entity** ha **smmContactPersonV2Entity** come origine dati e **smmContactPersonV2Entity**, a sua volta, ha **LogisticsPostalAddressBaseEntity** come origine dati. La tabella **LogisticsPostalAddress** è l'origine dati per **LogisticsPostalAddressBaseEntity**.

Una situazione simile può verificarsi in alcuni modelli non standard, come i casi in cui la tabella che viene modificata nelle app Finance and Operations non è chiaramente collegata all'entità che la contiene. Ad esempio, i dati dell'indirizzo principale vengono calcolati sull'entità **smmContactPersonCDSV2Entity**. Il framework a doppia scrittura tenta di determinare in che modo una modifica a una tabella sottostante viene mappata alle entità. Di solito, questo approccio è sufficiente. Tuttavia, in alcuni casi, il collegamento è così complesso che è necessario essere specifici. È necessario assicurarsi che **RecId** della relativa tabella sia direttamente disponibile sull'entità. Quindi, aggiungere un metodo statico per monitorare la tabella per le modifiche.

Ad esempio, rivedere il metodo **smmContactPersonCDSV2Entity::getEntityDataSourceToFieldMapping()**. **CustCustomerV3entity** e **VendVendorV2Entity** sono stati modificati per gestire questa situazione.

Per risolvere il problema, procedere come segue.

1. Aggiungere un campo **PrimaryPostalAddressRecId** all'entità **smmContactPersonV2Entity**. Rendere interna questa impostazione.

    ![Campo aggiunto all'entità smmContactPersonV2Entity.](media/Troubleshoot_live_sync_issue_1.png)

2. Aggiungere lo stesso campo all'entità **smmContactPersonCDSV2Entity**.

    ![Campo aggiunto all'entità smmContactPersonCDSV2Entity.](media/Troubleshoot_live_sync_issue_2.png)

3. Aggiungere il seguente metodo alla classe **smmContactPersonCDSV2Entity**.

    ```xpp
    public static container getEntityDataSourceToFieldMapping(container mapping)
    {
        mapping += [[tablestr(smmContactPersonCDSV2Entity), tablenum(LogisticsPostalAddress), fieldstr(smmContactPersonCDSV2Entity, PrimaryPostalAddressRecId)]];
        return mapping;
    }
    ```

4. Sincronizzare il database e creare l'applicazione.
5. Interrompere tutte le mappe a doppia scrittura che vengono create sull'entità **smmContactPersonCDSV2Entity**.
6. Avviare la mappa. Dovrebbe venire visualizzata la nuova tabella (**LogisticsPostalAddress** in questo esempio) che si è iniziato a monitorare utilizzando la colonna **RefTableName** per la riga in cui il valore **refentityname** è uguale a **smmContactPersonCDSV2Entity** nella tabella **BusinessEventsDefinition**.

## <a name="error-when-you-create-a-record-where-multiple-records-are-sent-from-a-finance-and-operations-app-to-dataverse-in-the-same-batch"></a>Errore durante la creazione di un record in cui vengono inviati più record da un'app Finance and Operations a Dataverse nello stesso batch

Per qualsiasi transazione, un'app Finance and Operations crea dati in un batch e li invia come batch a Dataverse. Se due record vengono creati come parte della stessa transazione e fanno riferimento l'uno all'altro, è possibile che venga visualizzato un messaggio di errore simile all'esempio seguente nell'app Finance and Operations:

*Impossibile scrivere i dati nell'entità aaa_fundingsources. Impossibile cercare ebecsfs_contracts con valori {PC00...}. Impossibile cercare aaa_fundingsources con valori {PC00...}. Scritture su aaa_fundingsources non riuscite con messaggio di errore Messaggio di eccezione: il server remoto ha restituito un errore: (400) Richiesta non valida.*

Per risolvere il problema, creare relazioni di entità nell'app Finance and Operations per indicare che le due entità sono correlate tra loro e che i relativi record vengono gestiti nella stessa transazione.

## <a name="enable-verbose-logging-of-error-messages"></a>Abilitare la registrazione dettagliata dei messaggi di errore

In un'app Finance and Operations, potrebbero verificarsi errori relativi all'ambiente Dataverse. Il messaggio di errore potrebbe non contenere il testo completo del messaggio o altri dati rilevanti. Per ottenere maggiori informazioni, puoi abilitare la registrazione dettagliata impostando il flag **IsDebugMode** che è presente sull'entità **DualWriteProjectConfigurationEntity** in tutte le configurazioni di progetto nelle app Finance and Operations.

1. Aprire l'entità **DualWriteProjectConfigurationEntity** utilizzando il componente aggiuntivo di Excel. Per utilizzare il componente aggiuntivo, abilitare la modalità di progettazione nel componente aggiuntivo di Excel di Finance and Operations e aggiungere **DualWriteProjectConfigurationEntity** a un foglio di lavoro. Per ulteriori informazioni, vedi [Visualizzare e aggiornare i dati entità con Excel](../../office-integration/use-excel-add-in.md).
2. Impostare il flag **IsDebugMode** su **Sì** sul progetto.
3. Eseguire lo scenario.
4. I log dettagliati sono disponibili nella tabella **DualWriteErrorLog**. Per cercare i dati utilizzando il browser della tabella, utilizzare il seguente URL: `https://XXXaos.cloudax.dynamics.com/?mi=SysTableBrowser&tableName=DualWriteErrorLog`.
5. Per acquisire più log in modalità di debug, installare l'aggiornamento in [KB 4595434 (Correzione per i valori vuoti propagati nella sincronizzazione in tempo reale a doppia scrittura)](https://fix.lcs.dynamics.com/Issue/Details?kb=4595434&bugId=527820&dbType=3&qc=c29ce15a80e6b3b4c01a722d9bdae1d7e71aa3662a044cfd0b765f736cfa98e9).

## <a name="error-when-you-add-an-address-for-a-customer-or-contact"></a>Errore durante l'aggiunta di un indirizzo per un cliente o un contatto

Potrebbe venire visualizzato il seguente messaggio di errore quando si tenta di aggiungere un indirizzo per un cliente o un contatto nelle app Finance and Operations o Dataverse:

*Impossibile scrivere dati sull'entità msdyn_partypostaladdresses.Writes per DirPartyPostalAddressLocationCDSEntity operazione non riuscita con messaggio di errore Richiesta non riuscita con codice di stato BadRequest e codice di errore CDS: 0x80040265 messaggio di risposta: si è verificato un errore nel plug-in. Esiste già un record con valori di attributo ID posizione. La chiave dell'entità Chiave ID posizione richiede che questo set di attributi contenga valori univoci. Selezionare valori univoci e riprovare.*

Per risolvere il problema, installare la versione del pacchetto di orchestrazione a doppia scrittura (2.2.2.60) in modo che le chiavi sulla tabella **Indirizzo** siano definite come mostrato nella tabella seguente.

| Proprietà | Valore |
|---|---|
| Nome visualizzato | **Chiave posizione** |
| Nome | **msdyn_locationkey** |
| Campi | **msdyn_locationid**, **parentid** |
| Stato | **Attive** |
| Processo di sistema | Vuoto |

## <a name="error-when-you-add-a-customer-in-dataverse"></a>Errore durante l'aggiunta di un cliente in Dataverse

È possibile che venga visualizzato il seguente messaggio di errore quando si tenta di aggiungere un cliente in Dataverse:

*"RecordError0":"Scrittura non riuscita per entità Clienti V3 con eccezione sconosciuta - Record di parte non trovato per il tipo di parte 'Organizzazione'"}.*

Quando un cliente viene creato in Dataverse, viene generato un nuovo numero di parte. Il messaggio di errore viene visualizzato quando il record cliente, insieme alla parte, viene sincronizzato nelle app Finance and Operations, ma esiste già un record cliente con un numero di parte diverso.

Per risolvere il problema, trovare il cliente tramite la ricerca della parte. Se il cliente non esiste, creare un nuovo record cliente. Se il cliente esiste, utilizzare la parte esistente per creare il nuovo record cliente.

## <a name="error-when-you-create-a-new-customer-vendor-or-contact-in-dataverse"></a>Errore durante la creazione di un nuovo cliente, fornitore o contatto in Dataverse

Potrebbe venire visualizzato il seguente messaggio di errore quando si tenta di creare un nuovo cliente, fornitore o contatto in Dataverse:

*Impossibile aggiornare il tipo di una parte da "DirOrganization" a "DirPerson", dovrebbe essere eseguita invece l'eliminazione della parte esistente seguita da un inserimento con il nuovo tipo.*

In Dataverse, è presente una sequenza numerica sulla tabella **msdyn_party**. Quando viene creato un account in Dataverse, viene creata una nuova parte (ad esempio **Party-001** del tipo **Organizzazione**). Questi dati vengono inviati all'app Finance and Operations. Se l'ambiente Dataverse viene ripristinato o l'ambiente Finance and Operations è collegato a un ambiente Dataverse diverso e quindi viene creato un nuovo record contatto in Dataverse, viene creato un nuovo valore di parte che inizia con **Party-001**. Questa volta, il record della parte creato sarà **Party-001** del tipo **Persona**. Quando questi dati vengono sincronizzati, le app Finance and Operations mostrano il messaggio di errore precedente, perché il record della parte **Party-001** del tipo **Organizzazione** esiste già.

Per risolvere il problema, modificare la sequenza numerica automatica per il campo **msdyn_partynumber** della tabella **msdyn_party** in Dataverse in una sequenza numerica automatica diversa.

## <a name="performance-issue-with-customer-or-contact-mappings"></a>Problema di prestazioni relativo ai mapping dei clienti o dei contatti

Potrebbe essere possibile migliorare marginalmente le prestazioni della sincronizzazione in tempo reale per clienti e contatti personalizzando il metodo **getEntityDataSourceToFieldMapping** (nell'entità **CustCustomerV3Entity**) e il metodo **getEntityDataSourceToFieldMapping** (nell'entità **smmContactPersonCDSV2Entity**). Queste personalizzazioni riducono il numero di record nella tabella **BusinessEventsDefinition**. Questa riduzione del numero di record, a sua volta, riduce il numero di eventi generati.

Il metodo **getEntityDataSourceToFieldMapping** nell'entità **CustCustomerV3Entity** garantisce che un aggiornamento dell'indirizzo elettronico o dell'indirizzo postale del cliente attivi eventi aziendali, in modo che i dati aggiornati vengano inviati a Dataverse. Se non si utilizzano tutti i campi e non si ha bisogno delle informazioni in doppia scrittura, commentare le righe appropriate nel metodo. Ogni tabella e campo tracciato aggiunto in questo metodo aggiunge un record nella tabella **BusinessEventsDefinition** per la combinazione della tabella tracciata e dell'entità tracciata.

```xpp
public static container getEntityDataSourceToFieldMapping(container mapping)
{
    mapping += [
        [tablestr(DirPartyBaseEntity), tablenum(LogisticsPostalAddress), fieldstr(CustCustomerV3Entity, AddressRecordId)],
        [identifierstr(DirPartyBaseEntity), tablenum(LogisticsElectronicAddress), fieldstr(CustCustomerV3Entity, PrimaryContactURLRecordId)],
        [identifierstr(DirPartyBaseEntity1), tablenum(LogisticsElectronicAddress), fieldstr(CustCustomerV3Entity, PrimaryContactPhoneRecordId)],
        [identifierstr(DirPartyBaseEntity2), tablenum(LogisticsElectronicAddress), fieldstr(CustCustomerV3Entity, PrimaryContactEmailRecordId)],
        [identifierstr(DirPartyBaseEntity3), tablenum(LogisticsElectronicAddress), fieldstr(CustCustomerV3Entity, PrimaryContactFaxRecordId)],
        [identifierstr(DirPartyBaseEntity4), tablenum(DirPartyLocation), fieldstr(CustCustomerV3Entity, DirPartyLocationRecordId)],
        [identifierstr(DirPartyBaseEntity5), tablenum(LogisticsPostalAddress), fieldstr(CustCustomerV3Entity, InvoiceAddressRecordId)],
        [identifierstr(DirPartyBaseEntity6), tablenum(LogisticsPostalAddress), fieldstr(CustCustomerV3Entity, DeliveryAddressRecordId)],
        [identifierStr(DirPartyBaseEntity7), tablenum(DirPartyTable), fieldstr(CustCustomerV3Entity, PartyRecordId)]];
    return mapping;
}
```

Analogamente, il metodo **getEntityDataSourceToFieldMapping** nell'entità **smmContactPersonCDSV2Entity** garantisce che un aggiornamento dell'indirizzo elettronico o dell'indirizzo postale del contatto attivi eventi aziendali, in modo che i dati aggiornati vengano inviati a Dataverse. Nel metodo, è possibile commentare le righe per tutti i campi che non si utilizzano.

```xpp
public static container getEntityDataSourceToFieldMapping(container mapping)
{
    mapping += [
        [tablestr(DirPartyBaseEntity), tablenum(LogisticsPostalAddress), fieldstr(smmContactPersonCDSV2Entity, PrimaryPostalAddressRecId)],
        [identifierStr(DirPartyBaseEntity), tablenum(DirPartyTable), fieldstr(smmContactPersonCDSV2Entity, PrimaryAddressLocation)],
        [identifierStr(DirPartyBaseEntity1), tablenum(LogisticsElectronicAddress), fieldstr(smmContactPersonCDSV2Entity, PrimaryContactEmailRecordId)],
        [identifierStr(DirPartyBaseEntity2), tablenum(LogisticsElectronicAddress), fieldstr(smmContactPersonCDSV2Entity, PrimaryContactFaxRecordId)],
        [identifierStr(DirPartyBaseEntity3), tablenum(LogisticsElectronicAddress), fieldstr(smmContactPersonCDSV2Entity, PrimaryContactPhoneRecordId)],
        [identifierStr(DirPartyBaseEntity4), tablenum(LogisticsElectronicAddress), fieldstr(smmContactPersonCDSV2Entity, PrimaryContactFacebookRecordId)],
        [identifierStr(DirPartyBaseEntity5), tablenum(LogisticsElectronicAddress), fieldstr(smmContactPersonCDSV2Entity, PrimaryContactTwitterRecordId)],
        [identifierStr(DirPartyBaseEntity6), tablenum(LogisticsElectronicAddress), fieldstr(smmContactPersonCDSV2Entity, PrimaryContactURLRecordId)],
        [identifierStr(DirPartyBaseEntity7), tablenum(LogisticsElectronicAddress), fieldstr(smmContactPersonCDSV2Entity, PrimaryContactLinkedInRecordId)],
        [identifierStr(DirPartyBaseEntity8), tablenum(LogisticsElectronicAddress), fieldstr(smmContactPersonCDSV2Entity, PrimaryContactTelexRecordId)],
        [identifierStr(DirPartyBaseEntity9), tablenum(DirPartyTable), fieldstr(smmContactPersonCDSV2Entity, PartyRecordId)]];
    return mapping;
}
```

Dopo aver aggiornato i metodi, effettuare le seguenti operazioni.

1. Sincronizzare il database e creare l'applicazione.
2. Interrompere tutte le mappe a doppia scrittura sulle entità **smmContactPersonCDSV2Entity** e **CustCustomerV3Entity**.
3. Avviare le mappe. Dovrebbero essere visibili meno record nelle entità **smmContactPersonCDSV2Entity** and **CustCustomerV3Entity** e nella tabella **BusinessEventsDefinition** e le prestazioni potrebbero migliorare leggermente.

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
