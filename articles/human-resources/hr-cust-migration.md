---
title: Migrazione dei clienti Dynamics 365 Human Resources all'infrastruttura per la finanza e le operazioni
description: In questo articolo viene descritta la migrazione dei clienti di Microsoft Dynamics 365 Human Resources nell'infrastruttura per la finanza e le operazioni.
author: twheeloc
ms.date: 10/25/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-10-13
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 63b08a8493702cf319aa078ef6aa787e2094be87
ms.sourcegitcommit: 088a7b5eb9a3b68710dfe012abf4c24776978750
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/01/2022
ms.locfileid: "9733446"
---
# <a name="dynamics-365-human-resources-customer-migration"></a>Migrazione dei clienti Dynamics 365 Human Resources

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]
[!include [preview banner](../includes/preview-banner.md)]

La migrazione dei clienti è una "migrazione lift-and-shift" (spostamento) di un database clienti all'infrastruttura per la finanza e le operazioni. A tale scopo vengono utilizzati strumenti di migrazione automatizzata. Il risultato è un nuovo ambiente per la finanza e le operazioni che utilizza il database Human Resources del cliente.

## <a name="prerequisites"></a>Prerequisiti

### <a name="user-access-and-permissions"></a>Accesso e autorizzazioni dell'utente

- L'utente di Microsoft Dynamics Lifecycle Services deve avere il ruolo **Amministratore dell'organizzazione**.
- L'utente deve essere in grado di [creare progetti Azure DevOps](/azure/devops/organizations/projects/create-project) o utilizzare un progetto esistente Azure DevOps.
- L'utente deve avere accesso per [creare un Token di sicurezza dell'accesso personale Azure DevOps](/azure/devops/organizations/accounts/use-personal-access-tokens-to-authenticate) o deve avere un token disponibile per l'uso.

### <a name="dataverse-environment-backup-sandbox"></a>Backup dell'ambiente Dataverse (sandbox)

1. Facoltativo ma consigliato: aggiorna l'ambiente sandbox Human Resources esistente utilizzando una copia dell'ambiente di produzione Human Resources.
2. [Crea un nuovo ambiente Dataverse](/power-platform/admin/create-environment#create-an-environment-with-a-database) utilizzando l'interfaccia di amministrazione di Power Platform.

    > [!NOTE]
    > Quando aggiungi un database, assicurati che l'opzione **Abilita app Dynamics 365** sia impostata su **sì**.

3. [Copia l'ambiente esistente Dataverse](/power-platform/admin/copy-environment), che è collegato all'app autonoma Human Resources, all'ambiente che hai creato nel passaggio precedente.

### <a name="dataverse-capacity"></a>Capacità di Dataverse

1. Utilizza la pagina **Riepilogo** nell'interfaccia di amministrazione di Power Platform per verificare che [l'archivio di Dataverse](/power-platform/admin/finance-operations-storage-capacity) disponga della capacità sufficiente per la copia dell'ambiente.
2. Se la capacità disponibile non è sufficiente, utilizza la [guida per liberare spazio di archiviazione](/power-platform/admin/free-storage-space) per ridurre i consumi complessivi. I clienti possono anche [aggiungere ulteriore capacità di archiviazione](/power-platform/admin/add-storage).

## <a name="customer-migration-process"></a>Processo di migrazione dei clienti

### <a name="create-a-lifecycle-services-project-for-human-resources-migration"></a>Creare un progetto Lifecycle Services per la migrazione Human Resources

Il primo passo è creare un nuovo progetto di implementazione per la finanza e le operazioni in Lifecycle Services. Il cliente disporrà di un progetto Human Resources Lifecycle Services esistente. Gli ambienti Human Resources esistenti verranno migrati al nuovo progetto di implementazione per la finanza e le operazioni.

Per creare un nuovo progetto, completa i passaggi seguenti:

1. Accedi a Lifecycle Services come amministratore globale o utente dell'account del servizio designato.
2. Nella home page di Lifecycle Services, seleziona **Crea/nuovo (+)**.
3. Seleziona le app per la finanza e le operazioni come prodotto.
4. Nel campo **Scopo del progetto** seleziona **Implementazione**.
5. Immetti un nome e una descrizione del progetto.
6. Nel campo **Tipo di progetto personalizzato** seleziona **Migrazione Microsoft Dynamics 365 Human Resources**.
7. Seleziona la casella di controllo per accettare i termini e le condizioni.
8. Seleziona **Crea**.

Dopo aver creato un nuovo progetto Lifecycle Services, segui questi passaggi per impostarlo e configurarlo.

1. Seleziona **Onboarding del progetto** per completare l'onboarding del progetto. Per ulteriori informazioni, vedere [Onboarding del progetto](../fin-ops-core/dev-itpro/lifecycle-services/project-onboarding.md).

    - Seleziona la stessa area geografica degli ambienti attuali. Questa selezione non influirà sulla migrazione.
    - Per i sistemi legacy, seleziona **Altro**.

2. Completa le impostazioni del progetto. Come parte di questo passaggio, devi configurare le connessioni per la libreria SharePoint Online, Azure DevOps e Azure, se necessarie. Per ulteriori informazioni, vedi [Manuale per l'utente di Lifecycle Services (LCS)](../dev-itpro/lifecycle-services/lcs-user-guide.md).

> [!NOTE]
> I clienti possono utilizzare un progetto esistente Azure DevOps e il token di sicurezza dell'accesso personale associato. Se viene utilizzato un progetto esistente, le configurazioni correlate al progetto sono automaticamente disponibili e possono essere riviste per verificarne l'accuratezza.

### <a name="migrate-a-human-resources-sandbox-environment"></a>Migrazione di un ambiente sandbox Human Resources

#### <a name="prepare-to-migrate-the-sandbox-environment"></a>Preparare la migrazione dell'ambiente sandbox

Dopo che un nuovo progetto Lifecycle Services è stato creato e il processo di onboarding del progetto è stato completato, sei pronto per migrare il tuo primo ambiente. Prima di avviare questo processo, ti consigliamo di aggiornare l'ambiente sandbox da migrare dall'ambiente di produzione nell'infrastruttura autonoma.

#### <a name="prepare-a-power-platform-environment"></a>Preparare un ambiente Power Platform

> [!NOTE]
> Questo passaggio è applicabile solo alla migrazione dell'ambiente sandbox. Quando si migra l'ambiente di produzione, l'esistente ambiente dell'interfaccia di amministrazione di Power Platform collegato all'ambiente di produzione verrà riportato.

- Nell'interfaccia di amministrazione di Power Platform, [crea un ambiente Power Platform](/power-platform/admin/create-environment#create-an-environment-in-the-power-platform-admin-center) da utilizzare per la migrazione sandbox o seleziona un ambiente esistente.
- [Copia un ambiente](/power-platform/admin/copy-environment) per aggiornare l'ambiente Power Platform utilizzato per la mappatura.

#### <a name="migrate-the-sandbox-environment"></a>Migrazione dell'ambiente sandbox

1. Accedi a Lifecycle Services come amministratore globale o utente dell'account del servizio designato.

    > [!NOTE]
    > Ti consigliamo di utilizzare un account utente denominato. L'utente che ha eseguito l'accesso deve avere il ruolo di sicurezza **Proprietario del progetto** o **Responsabile dell'ambiente** nel progetto autonomo Human Resources Lifecycle Services.

2. Apri il progetto di migrazione Human Resources appena creato.
3. Rivedi e completa le fasi appropriate della metodologia di migrazione e dell'onboarding del progetto.
4. Nel dashboard del progetto, nel riquadro **Predefinito: test di accettazione standard**, seleziona **Migrazione di HR**.
5. Nel riquadro **Seleziona l'ambiente da migrare**, seleziona il progetto Lifecycle Services appropriato e l'ambiente Human Resources di origine (dall'applicazione Human Resources autonoma di origine).
6. Abilita **Mappa al nuovo ambiente Power Platform** e seleziona l'ambiente appropriato Power Platform. Quindi seleziona **Avanti**.
7. Completa la procedura guidata **Impostazioni di distribuzione (finanza e operazioni - sandbox)** per confermare i dettagli e la disconnessione del cliente, quindi seleziona **Distribuisci**.

Lo stato dell'ambiente mostrerà l'avanzamento. Lo stato verrà modificato da **Caricamento in corso** a **Distribuzione in corso** a **Distribuito**.

> [!NOTE]
> Il riquadro di produzione non sarà disponibile fino al completamento dell'elenco di controllo per la preparazione del progetto della fase operativa. Per ulteriori informazioni, vedere [Preparazione per il go-live](../fin-ops-core/fin-ops/imp-lifecycle/prepare-go-live.md).

#### <a name="considerations-and-assumptions"></a>Considerazioni e presupposti

Un ambiente sandbox Human Resources esiste in un progetto Lifecycle Services sul tenant che presenta le seguenti caratteristiche:

- L'ambiente sandbox Human Resources non è collegato a un ambiente unito esistente. Può essere in corso una sola migrazione alla volta per un determinato ambiente Human Resources.
- Il numero di ambienti sandbox consentiti alla volta si basa sulla licenza Human Resources. Se è stata acquistata una licenza sufficiente per il tenant, gli ambienti sandbox aggiuntivi verranno elencati nel riquadro **Ambienti** del progetto.
- Le migrazioni devono essere eseguite in ambienti dello stesso tipo. In altre parole, possono essere eseguite solo migrazioni da sandbox a sandbox o da produzione a produzione.

    > [!NOTE]
    > Solo i tipi di ambiente Human Resources vengono presi in considerazione quando viene determinato lo stato di produzione o sandbox. Se gli ambienti sono classificati in modo errato (ovvero, un ambiente di produzione è contrassegnato come ambiente sandbox o un ambiente sandbox è contrassegnato come ambiente di produzione), contatta l'assistenza.

- Se la migrazione non riesce, verrà visualizzato un messaggio di errore e il pulsante **Elimina** diventerà disponibile. Utilizza questo pulsante per eliminare la migrazione non riuscita. È quindi possibile ripetere la migrazione dell'ambiente.

#### <a name="validate-the-sandbox-migration"></a>Convalidare la migrazione sandbox

Dopo che il processo di migrazione della sandbox è stato completato con successo, crea un piano di test dettagliato per verificare e firmare tutti i processi aziendali.

Prima di iniziare il test, convalida i seguenti dettagli:

- Verifica che l'ambiente migrato sia accessibile dall'URL generato.
- Conferma che gli utenti possano accedere alla sandbox migrata.
- Conferma che l'ambiente Dataverse associato all'ambiente sandbox migrato sia accessibile.
- Controlla a campione dati diversi per confermare che siano disponibili i dati più aggiornati.
- Completa i processi aziendali critici per la convalida.
- Conferma che i criteri di sicurezza siano applicabili.
- Conferma che i processi batch vengano attivati come previsto.

Non avrai accesso Desktop remoto alla sandbox migrata. Puoi utilizzare le funzionalità e gli strumenti self-service per eseguire le seguenti azioni per i tuoi ambienti sandbox di livello 2+:

- Accedi al [database SQL di Azure](../fin-ops-core/dev-itpro/deployment/deploymentfaq.md#access-the-azure-sql-database).
- Accedei ai [file di log](../fin-ops-core/dev-itpro/deployment/deploymentfaq.md#access-log-files).
- Usa gli [strumenti perfmon](../fin-ops-core/dev-itpro/deployment/deploymentfaq.md#use-perfmon-tools).
- Attiva o disattiva la [Modalità manutenzione](../fin-ops-core/dev-itpro/deployment/deploymentfaq.md#access-self-service-logs).
- Riavvia i [servizi](../fin-ops-core/dev-itpro/deployment/deploymentfaq.md#restart-services).
- Configura [Regression Suite Automation Tool](../fin-ops-core/dev-itpro/deployment/deploymentfaq.md#configure-the-regression-suite-automation-tool).

Per ulteriori informazioni, vedi [Domande frequenti per la distribuzione self-service](../fin-ops-core/dev-itpro/deployment/deploymentfaq.md).

### <a name="migrate-a-human-resources-production-environment"></a>Migrazione di un ambiente di produzione Human Resources

Al termine della migrazione e della convalida di un ambiente sandbox, segui questa procedura per migrare l'ambiente di produzione.

#### <a name="prerequisites"></a>Prerequisiti

- Lo Strumento di stima delle sottoscrizioni deve essere completato.
- La [valutazione della preparazione](../fin-ops-core/fin-ops/imp-lifecycle/prepare-go-live.md) per la fase operativa deve essere completata.

#### <a name="migrate-the-production-environment"></a>Migrazione dell'ambiente di produzione

1. Accedi a Lifecycle Services come amministratore globale o utente dell'account del servizio designato.

    > [!NOTE]
    > Ti consigliamo di utilizzare un account utente denominato. L'utente che ha eseguito l'accesso deve avere il ruolo di sicurezza **Proprietario del progetto** o **Responsabile dell'ambiente** nel progetto Lifecycle Services.

2. Apri il nuovo progetto di migrazione Human Resources.
3. Rivedi e completa le fasi appropriate della metodologia di migrazione e dell'onboarding del progetto.
4. Nel dashboard del progetto, nel riquadro **Produzione**, seleziona **Migrazione di HR**.
5. Nel riquadro **Seleziona l'ambiente da migrare**, seleziona il progetto Lifecycle Services appropriato e l'ambiente Human Resources di origine (dall'applicazione Human Resources autonoma di origine). Quindi seleziona **Avanti**.
6. Completa la procedura guidata **Impostazioni di distribuzione (finanza e operazioni - sandbox)** per confermare i dettagli e la disconnessione del cliente, quindi seleziona **Distribuisci**.

Lo stato dell'ambiente mostrerà l'avanzamento della distribuzione. Lo stato verrà modificato da **Caricamento in corso** a **Distribuzione in corso** a **Distribuito**.

#### <a name="post-migration-considerations"></a>Considerazioni successive alla migrazione

- Applica gli ultimi [aggiornamenti di qualità](/fin-ops-core/fin-ops/get-started/quality-updates) agli ambienti.
- Se stai usando le [tabelle virtuali](hr-admin-integration-common-data-service-virtual-entities.md), riconfigura gli endpoint.
- Riconfigura l'integrazione della doppia scrittura. Valuta quali entità devono essere abilitate.
- Prendi in considerazione l'utilizzo di tabelle virtuali per sostituire la doppia scrittura per l'integrazione.

#### <a name="dual-write-integration"></a>Integrazione con doppia scrittura

##### <a name="set-up-microsoft-power-platform-dual-write-integration"></a>Configurare l'integrazione della doppia scrittura Microsoft Power Platform

1. Vai all'interfaccia di amministrazione di Power Platform e seleziona **Ambienti** nel riquadro di navigazione a sinistra.
2. Seleziona l'ambiente precedentemente copiato/aggiornato e conferma che lo stato sia **Pronto**.
3. Vai a Lifecycle Services e conferma che lo stato del progetto di migrazione sia **Distribuito**.
4. Nell'ambiente migrato, seleziona **Dettagli completi** per rivedere ulteriori dettagli e [configurare un'applicazione a doppia scrittura](../fin-ops-core/dev-itpro/data-entities/dual-write/lcs-setup.md#set-up-dual-write-for-new-or-existing-dataverse-environments).
5. Nel riquadro **Configurazione dell'applicazione a doppia scrittura**, seleziona la casella di controllo per accettare di mappare e sincronizzare i dati tra i database, quindi seleziona **Configura**.
6. Quando una finestra di messaggio notifica il completamento della configurazione della doppia scrittura, seleziona **OK**.
7. Puoi monitorare lo stato di avanzamento della configurazione nei dettagli.
8. Al termine della configurazione, seleziona **Collegamento all'ambiente Power Platform** per sincronizzare le entità di dati disponibili.
9. Quando lo stato indica che gli ambienti sono stati collegati correttamente, vai nell'interfaccia di amministrazione di Power Platform per esaminare e selezionare le entità di dati appropriate.
10. Nel riquadro a sinistra, seleziona **App Dynamics 365 \> Risorse**.
11. Conferma che lo stato dell'app Human Resources a doppia scrittura sia **Abilitato**.
12. Seleziona l'app Human Resources a doppia scrittura, quindi seleziona **Installa**.
13. Nel riquadro **Installa l'app Dynamics 365 Human Resources a doppia scrittura** seleziona l'ambiente appropriato in cui installare il pacchetto.
14. Seleziona la casella di controllo per accettare i termini di servizio, quindi seleziona **Installa**.
15. Nell'ambiente dell'app Dynamics 365, lo stato sarà **Installazione in corso** mentre l'installazione è in esecuzione. Verrà aggiornato a **Installato** quando l'installazione è completata.

##### <a name="review-and-apply-a-dual-write-solution"></a>Rivedere e applicare una soluzione a doppia scrittura

1. Nell'ambitente per la finanza e le operazioni, passa a **Gestione dei dati \> Doppia scrittura**.
2. Seleziona **Applica soluzione**.
3. Nel riquadro, seleziona **Soluzioni installate Dynamics**, **Mappe di entità principali di applicazioni a doppia scrittura**, e **Mappe di Dynamics 365 Human Resources**. Quindi seleziona **Applica**. Un messaggio conferma che la soluzione è stata applicata. Dopo che la soluzione è stata applicata con successo, verranno mostrate tutte le mappe delle tabelle disponibili.
4. Esamina le mappe delle tabelle disponibili per selezionare ed eseguire l'integrazione utilizzando la doppia scrittura.
5. Quando esegui per la prima volta l'integrazione a doppia scrittura per le mappe delle tabelle, seleziona la casella di controllo **Sincronizzazione iniziale**. Se esiste un'integrazione esistente dall'ambiente Human Resources di origine, non è necessario selezionare la casella di controllo **Sincronizzazione iniziale** quando si esegue l'integrazione per le mappe tabella.

#### <a name="recommended-practices"></a>Procedure consigliate

Questa sezione delinea le raccomandazioni per la migrazione dall'infrastruttura autonoma all'infrastruttura per la finanza e le operazioni.

- Ti consigliamo vivamente di lavorare con il tuo partner Microsoft Dynamics per ottenere assistenza con la migrazione dell'ambiente Human Resources.
- Pianifica il tempo appropriato per eseguire il test di accettazione utenti (UAT) completo nell'ambiente migrato sandbox.
- Pianifica e documenta i passaggi dettagliati per migrare le integrazioni nell'ambiente migrato.
- Crea un elenco di controllo dettagliato per delineare il processo di cutover per la tua migrazione.
- Pianifica un periodo di inattività adeguato per la migrazione nella tua azienda.
- Consigliamo vivamente ai clienti qualificati FastTrack di collaborare con l'architetto di soluzioni FastTrack per ottenere assistenza nella supervisione del processo di migrazione.
- Ti consigliamo vivamente di aggiornare l'ambiente sandbox nell'infrastruttura autonoma prima di eseguire la prima migrazione. Questo aggiornamento deve includere l'ambiente Dataverse connesso all'ambiente sandbox a cui intendi migrare.
- Ti consigliamo vivamente di utilizzare un account di servizio durante la distribuzione, la migrazione e la creazione del progetto Lifecycle Services.
- Pianifica l'aggiornamento dell'ambiente sandbox per la convalida UAT sull'ultima versione di disponibilità generale (GA). Per maggiori informazioni, vedi [Considerazioni](hr-infrastructure-merge.md#considerations).
