---
title: Risoluzione dei problemi di sincronizzazione in tempo reale
description: Questo argomento fornisce informazioni che possono aiutarti a risolvere i problemi relativi alla sincronizzazione in tempo reale.
author: RamaKrishnamoorthy
ms.date: 03/16/2020
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: 2dbb32647e362df05d28bbd7d845e0e4f776d8c9
ms.sourcegitcommit: 259ba130450d8a6d93a65685c22c7eb411982c92
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/24/2021
ms.locfileid: "7416707"
---
# <a name="troubleshoot-live-synchronization-issues"></a>Risoluzione dei problemi di sincronizzazione in tempo reale

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

In questo argomento vengono fornite informazioni sulla risoluzione dei problemi di integrazione della doppia scrittura tra le app Finance and Operations e Dataverse. In particolare, fornisce informazioni che possono aiutarti a risolvere i problemi relativi alla sincronizzazione in tempo reale.

> [!IMPORTANT]
> Alcuni problemi che questo argomento tratta potrebbero richiedere il ruolo di amministratore di sistema o le credenziali di amministratore del tenant Microsoft Azure Active Directory (Azure AD). La sezione per ogni problema spiega se sono richiesti ruolo o credenziali specifici.

## <a name="live-synchronization-throws-a-403-forbidden-error-when-you-create-a-row-in-a-finance-and-operations-app"></a>La sincronizzazione in tempo reale genera un errore 403 Accesso negato quando si crea una riga in un'app Finance and Operations

È possibile che venga visualizzato il seguente messaggio di errore quando si crea una riga in un'app Finance and Operations:

*\[{\\"errore\\":{\\"codice\\":\\"0x80072560\\",\\"messaggio\\":\\"L'utente non è un membro dell'organizzazione.\\"}}\], Il server remoto ha restituito un errore: (403) Accesso negato."}}".*

Per risolvere il problema, seguire i passaggi in [Requisiti e prerequisiti di sistema](requirements-and-prerequisites.md). Per completare questi passaggi, gli utenti dell'applicazione di doppia scrittura che vengono creati in Dataverse devono avere il ruolo di amministratore di sistema. Anche il team proprietario predefinito deve avere il ruolo di amministratore di sistema.

## <a name="live-synchronization-for-any-table-consistently-throws-a-similar-error-when-you-create-a-row-in-a-finance-and-operations-app"></a>La sincronizzazione in tempo reale per una tabella genera coerentemente un errore simile quando si crea una riga in un'app Finance and Operations

**Ruolo richiesto per risolvere il problema:** amministratore di sistema

È possibile che venga visualizzato un messaggio di errore simile al seguente ogni volta che si tenta di salvare i dati della tabella in un'app Finance and Operations:

*Impossibile salvare le modifiche nel database. L'unità di lavoro non può eseguire il commit della transazione. Impossibile scrivere i dati nell'entità unità di misura. Scrittura su UnitOfMeasureEntity non riuscita con messaggio di errore Impossibile sincronizzare con l'entità unità di misura.*

Per risolvere il problema, è necessario assicurarsi che i dati di riferimento dei prerequisiti esistano nell'app Finance and Operations e in Dataverse. Ad esempio, se il cliente dell'app Finance and Operations appartiene a un gruppo di clienti specifico, assicurarsi che il gruppo di clienti esista in Dataverse.

Se i dati esistono su entrambi i lati e si conferma che il problema non è relativo ai dati, procedere nel seguente modo.

1. Arrestare la tabella correlata.
2. Accedere all'app Finance and Operations e assicurarsi che siano presenti righe per la tabella in errore nelle tabelle DualWriteProjectConfiguration e DualWriteProjectFieldConfiguration. Ad esempio, ecco come appare la query se la tabella **Clienti** non riesce.

    ```sql
    Select projectname, externalenvironmentURL ,\* 
    from DUALWRITEPROJECTCONFIGURATION 
    where INTERNALENTITYNAME = 'Customers V3' and
        EXTERNALENTITYNAME = 'accounts' 
    ```

3. Se sono presenti righe per la tabella in errore anche dopo aver interrotto la mappatura della tabella, eliminare le righe correlate alla tabella in errore. Prendere nota della colonna **projectname** nella tabella DualWriteProjectConfiguration e recuperare la riga nella tabella DualWriteProjectFieldConfiguration utilizzando il nome del progetto per eliminare la riga.
4. Avviare la mappatura della tabella. Convalidare se i dati vengono sincronizzati senza problemi.

## <a name="handle-read-or-write-privilege-errors-when-you-create-data-in-a-finance-and-operations-app"></a>Gestire gli errori dei privilegi di lettura o scrittura quando si creano i dati in un'app Finance and Operations

È possibile che venga visualizzato un messaggio di errore "Richiesta non valida" simile al seguente esempio quando si creano dati in un'app Finance and Operations.

![Esempio del messaggio di errore Richiesta non valida.](media/error_record_id_source.png)

Per risolvere il problema, è necessario assegnare il ruolo di sicurezza corretto al team della Business Unit Dynamics 365 Sales o Dynamics 365 Customer Service mappata per abilitare il privilegio mancante.

1. Nell'app Finance and Operations, trovare la Business Unit mappata nel set di connessioni Integrazione dati.

    ![Mapping dell'organizzazione.](media/mapped_business_unit.png)

2. Accedi all'ambiente nell'app customer engagement, vai a **Impostazioni \> Sicurezza** e trova il team della Business Unit mappata.

    ![Team della Business Unit mappata.](media/setting_security_page.png)

3. Aprire la pagina del team per la modifica, quindi selezionare **Gestisci ruoli** per aprire la finestra di dialogo **Gestisci ruoli del team**.

    ![Pulsante Gestisci ruoli.](media/manage_team_roles.png)

4. Assegnare il ruolo con il privilegio di lettura/scrittura per le tabelle pertinenti, quindi selezionare **OK**.

## <a name="fix-synchronization-issues-in-an-environment-that-has-a-recently-changed-dataverse-environment"></a>Risoluzione dei problemi di sincronizzazione in un ambiente in cui è stato recentemente modificato Dataverse

**Ruolo richiesto per risolvere il problema:** amministratore di sistema

È possibile che venga visualizzato il seguente messaggio di errore quando si creano dati in un'app Finance and Operations:

*{"entityName":"CustCustomerV3Entity","executionStatus":2,"fieldResponses":\[\],"recordResponses":\[{"errorMessage":"**Impossibile generare il payload per l'entità CustCustomerV3Entity**","logDateTime":"2019-08-27T18:51:52.5843124Z","verboseError":"Creazione del payload non riuscita con errore URI non valido: L'URI è vuoto."}\],"isErrorCountUpdated":true}*

Ecco come appare l'errore nell'app customer engagement:

*Si è verificato un errore imprevisto del codice ISV. (ErrorType = ClientError) Eccezione imprevista dal plug-in (Execute): Microsoft.Dynamics.Integrator.DualWriteRuntime.Plugins.PostCommitPlugin: System.Exception: impossibile elaborare l'account dell'entità - Tentativo di connessione non riuscito perché la parte connessa non ha risposto correttamente dopo un periodo di tempo o connessione stabilita non riuscita perché l'host connesso non ha risposto*

Questo errore si verifica quando l'ambiente Dataverse viene reimpostato in modo errato mentre si tenta di creare dati nell'app Finance and Operations.

Per risolvere il problema, procedere come segue.

1. Accedere alla macchina virtuale (VM) Finance and Operations, aprire SQL Server Management Studio (SSMS) e cercare le righe nella tabella DUALWRITEPROJECTCONFIGURATIONENTITY dove **internalentityname** equivale a **Clienti V3** e **externalentityname** equivale a **conti**. Ecco come appare la query.

    ```sql
    select projectname, externalenvironmentURL ,\* 
    from DUALWRITEPROJECTCONFIGURATION 
    where INTERNALENTITYNAME = 'Customers V3' and EXTERNALENTITYNAME = 'accounts'
    ```

2. Utilizzare il nome del progetto dai risultati della query precedente per eseguire la query seguente.

    ```sql
    select \* 
    from DUALWRITEPROJECTFIELDCONFIGURATION 
    where projectname = <project name from previous query>
    ```

3. Assicurarsi che la colonna **externalenvironmentURL** abbia l'URL corretto di Dataverse o dell'app. Eliminare tutte le righe duplicate che puntano all'URL Dataverse errato. Eliminare le righe corrispondenti nelle tabelle DUALWRITEPROJECTFIELDCONFIGURATION e DUALWRITEPROJECTCONFIGURATION.
4. Arrestare il mapping della tabella e quindi riavviarlo

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
