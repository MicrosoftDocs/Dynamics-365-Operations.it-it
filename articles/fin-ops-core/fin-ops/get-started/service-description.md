---
title: Descrizione del servizio per le app Finance and Operations
description: Questo argomento fornisce la descrizione del servizio per le app Finance and Operations.
author: tomhig
ms.date: 12/07/2021
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: whigginb
ms.search.validFrom: 2021-09-03
ms.openlocfilehash: f7ce73018fda79156cc7ef3d4e1faa3fedf966f8
ms.sourcegitcommit: b101c21f972fdad2667431f712222e040cd69d43
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/07/2021
ms.locfileid: "7898391"
---
# <a name="service-description-for-finance-and-operations-apps"></a>Descrizione del servizio per le app Finance and Operations

[!include[banner](../includes/banner.md)]

Le app Finance and Operations sono offerte di software come servizio (SaaS) ERP (Enterprise Resource Planning) basate su e per [Microsoft Azure](https://azure.microsoft.com/overview/what-is-azure/). Il servizio Finance and Operations fornisce alle organizzazioni funzionalità ERP che supportano i loro requisiti unici e le aiutano ad adattarsi ad ambienti aziendali in continua evoluzione, senza richiedere la gestione dell'infrastruttura. Le app Finance and Operations possono includere una o più delle seguenti aree di soluzione:

- [Dynamics 365 Finance](/dynamics365/finance/)
- [Dynamics 365 Human Resources](/dynamics365/human-resources/)
- [Dynamics 365 Supply Chain Management](/dynamics365/supply-chain/)
- [Dynamics 365 Commerce](/dynamics365/commerce/)
- [Dynamics 365 Project Operations](/dynamics365/project-operations/)

Insieme a [business intelligence](/power-bi/fundamentals/power-bi-service-overview), [infrastruttura](https://azure.microsoft.com/global-infrastructure/), [calcolare](/azure/service-fabric/service-fabric-overview) e [servizi di database](https://devblogs.microsoft.com/azure-sql/running-1m-databases-on-azure-sql-for-a-large-saas-provider-microsoft-dynamics-365-and-power-platform/), queste app consentono alle organizzazioni di eseguire processi aziendali e operativi specifici del settore. Supportati dal partner di implementazione, i clienti determinano la configurazione della logica dell'applicazione aziendale che meglio si adatta ai loro processi aziendali unici. Funzionalità e processi aziendali possono essere aumentati o estesi attraverso una o una combinazione delle seguenti soluzioni:

- [esperienza di personalizzazione](personalize-user-experience.md) integrata
- Strumenti di [Microsoft Power Platform](../../dev-itpro/power-platform/overview.md)
- Basato su [Visual Studio](https://visualstudio.microsoft.com) [Finance and Operations software development kit (SDK)](../../dev-itpro/dev-tools/developer-home-page.md) e [Azure DevOps sviluppare l'automazione](../../dev-itpro/dev-tools/developer-home-page.md#build-automation-using-azure)
- Soluzioni di fornitori di software indipendenti (ISV) da [AppSource](https://appsource.microsoft.com/partners)

In base ai requisiti, i clienti scelgono il loro approccio alla soluzione. Lavorano con il loro partner di implementazione per definire, sviluppare e testare la loro soluzione utilizzando gli strumenti e le migliori pratiche fornite in [Microsoft Dynamics Lifecycle Services (LCS)](../../dev-itpro/lifecycle-services/lcs.md). Esistono quattro scenari comuni:

- Configurazione standard predefinita (nessuna estensione) delle app Finance and Operations
- Configurazione delle app Finance and Operations che include una o più soluzioni ISV
- Configurazione delle app Finance and Operations che include una o più estensioni specifiche del cliente
- Configurazione delle app Finance and Operations che include una combinazione di estensioni specifiche del cliente e una o più soluzioni ISV

Le organizzazioni possono eguagliare la loro crescita aziendale aggiungendo facilmente utenti e processi aziendali attraverso un modello di abbonamento semplice e trasparente. Per ulteriori informazioni, consultare la [guida alle licenze di Dynamics 365](https://www.microsoft.com/licensing/docs/view/Microsoft-Dynamics-365).

## <a name="operating-model"></a>Modello operativo

Il modello operativo delle app Finance and Operations definisce ruoli e responsabilità specifici per il cliente, il partner di implementazione e Microsoft durante l'intero ciclo di vita del servizio. Per ulteriori informazioni, vedere [Operazioni e assistenza cloud](../../dev-itpro/lifecycle-services/cloud-operations-servicing.md).

### <a name="customer-activities"></a>Attività clienti

I clienti lavorano con il loro partner e [Microsoft FastTrack](/dynamics365/fasttrack/) seguendo [Dynamics 365 Implementation Guide](https://community.dynamics.com/365/dynamics-365-fasttrack/p/dynamics365implementationguide), il framework [Success by Design](/dynamics365/fasttrack/success-by-design-overview) e utilizzando strumenti e modelli di procedure consigliate fornite in [Lifecycle Services](../../dev-itpro/lifecycle-services/lcs.md) per implementare la loro soluzione. Le attività comuni includono:

- Gestione identità utente e sicurezza
- Definire, sviluppare e gestire i processi aziendali
- Definire, sviluppare, testare e gestire le estensioni
- Monitorare e gestire le implementazioni non di produzione
- Gestire gli aggiornamenti delle applicazioni e convalidare le estensioni
- Gestire soluzioni ISV e integrazioni di terze parti

### <a name="microsoft-responsibilities"></a>Responsabilità di Microsoft

Microsoft gestisce il servizio Finance and Operations distribuendo, monitorando attivamente e servendo gli ambienti sandbox e di produzione dei clienti nell'abbonamento Microsoft SaaS. Questa gestione include l'allocazione dell'infrastruttura di sistema necessaria per eseguire il servizio e comunicare in modo proattivo con i clienti sull'integrità del servizio. Le responsabilità includono:

**Gestione dell'infrastruttura**
- Sicurezza e isolamento
- Sistemi operativi e virtualizzazione
- Server, risorse di archiviazione e rete
- Alimentazione, rete, raffreddamento del data center

**Gestione delle piattaforme applicative**
- Monitoraggio e notifiche delle applicazioni 24 ore su 24, 7 giorni su 7
- Diagnostica, aggiornamenti della piattaforma, patch, aggiornamenti dei servizi
- Routing delle applicazioni, bilanciamento del carico, replica del sito
- Approvvigionamento e gestione dell'ambiente
- Gestione del database, alta disponibilità (HA)/ripristino di emergenza (DR), scalabilità, operazioni
- Distribuzione del calcolo, aumentare, ridurre

## <a name="system-configuration"></a>Configurazione sistema

Le app Finance and Operations scalano in base al volume delle transazioni e al carico degli utenti. Ogni implementazione del cliente produce una soluzione unica che consiste dei seguenti elementi:

- **Composizione dei dati** – Un insieme univoco di parametri che controllano il comportamento, il layout dell'organizzazione, la struttura dei dati master (come le dimensioni finanziarie e di inventario) e la granularità del monitoraggio delle transazioni.
- **Estensione e configurazione** – Meccanismi di estensione che utilizzano estensioni di codice, soluzioni ISV e configurazioni univoche che includono flussi di lavoro, integrazioni e configurazioni di report.
- **Modelli di utilizzo** – Una combinazione unica di utilizzo online e batch, insieme alla capacità di integrarsi con i sistemi upstream e downstream per un flusso di dati unificato e la capacità di differenziare in base alle visualizzazioni delle informazioni che i clienti utilizzano nei loro processi aziendali.

Microsoft configura gli ambienti di produzione dei clienti dimensionati per gestire i volumi delle transazioni e la concorrenza degli utenti. Microsoft è responsabile delle seguenti attività:

- Allocare correttamente le risorse degli ambienti di produzione, sulla base delle informazioni di profilazione del cliente nello [Strumento di stima degli abbonamenti LCS](../../dev-itpro/lifecycle-services/subscription-estimator.md)
- Monitoraggio e diagnosi continui della disponibilità del servizio degli ambienti di produzione
- Analisi e risoluzione dei problemi relativi alle prestazioni del sistema con le app Finance and Operations

Per garantire che un'implementazione sia configurata per prestazioni elevate, i clienti devono completare queste attività:

- Fornire informazioni accurate sull'utilizzo dell'implementazione di Finance and Operations nello [Strumento di stima degli abbonamenti LCS](../../dev-itpro/lifecycle-services/subscription-estimator.md).
- Creare e testare le estensioni per prestazioni e scalabilità.
- Testare opportunamente le configurazioni dei dati per le prestazioni.
- Garantire la scalabilità facendo i [test delle prestazioni](https://community.dynamics.com/365/b/techtalks/posts/performance-testing-approach-april-30-2018) prima della fase operativa.

## <a name="onboarding-and-implementation"></a>Onboarding e implementazione

La tabella seguente mostra gli eventi tipici di onboarding e implementazione.

| Richiesta | Azione Microsoft prevista | Azione prevista del cliente/partner di implementazione |
|---|---|---|
| Acquisto offerta iniziale | Un progetto LCS viene creato dopo l'acquisto dell'offerta, in base a un evento attivato dal cliente. | Passa attraverso l'Enterprise Agreement (EA) o il Cloud Solution Provider (CSP) [processo commerciale](before-you-buy.md). Il partner crea un tenant per il cliente, se applicabile. |
| Acquisto aggiuntivo | Concedi al cliente l'accesso al componente aggiuntivo selezionato durante l'implementazione. | Non applicabile |
| Pianificazione e analisi dell'implementazione | Fornire strumenti pertinenti in LCS, come [Modellatore di processi aziendali (BPM)](../../dev-itpro/lifecycle-services/bpm-overview.md) e [interoperabilità con Azure DevOps](../../dev-itpro/lifecycle-services/synchronize-bpm-vsts.md). | Pianificare il progetto, impostare Azure DevOps, completare l'onboarding del sistema e configurare gli account amministratore. |

Per ulteriori informazioni, vedere [Onboarding di un progetto di implementazione](../imp-lifecycle/onboard.md).

## <a name="globalization"></a>Globalizzazione

Le app Finance and Operations sono servite da diverse aree di Azure in tutto il mondo. Le app Finance and Operations forniscono funzionalità per supportare diversi paesi/aree geografice e lingue native. Per ulteriori informazioni, vedere [Funzionalità per la normativa e la localizzazione](../../dev-itpro/lcs-solutions/country-region.md#localization-and-regulatory-features).

### <a name="countryregion-specific-considerations"></a>Considerazioni specifiche di paese/area geografica

- I clienti del settore regolamentato o le organizzazioni commerciali che fanno affari con entità in Francia che richiedono la residenza dei dati locali dovrebbero rivedere [Finance and Operations in Francia](../../dev-itpro/deployment/france-local-deployment.md).
- I clienti che hanno operazioni in Cina dovrebbero rivedere [Finance and Operations gestito da 21Vianet in Cina](../../dev-itpro/deployment/china-local-deployment.md).
- I clienti che operano in Russia dovrebbero rivedere il [Legge russa sulla localizzazione dei dati personali](/business-applications-release-notes/october18/dynamics365-finance-operations/russian-regulations-on-prem#when-will-the-cloud-deployment-option-of-dynamics-365-for-finance-and-operations-be-generally-available-for-russia).

### <a name="general-data-protection-regulation-gdpr"></a>Regolamento generale sulla protezione dei dati (RGDP)

Per le app Finance and Operations, Microsoft funge da processore. In qualità di responsabile del trattamento, Finance and Operations fornisce processi e funzionalità che aiutano i clienti a rispettare gli obblighi GDPR in qualità di titolari del trattamento dei dati. Per ulteriori informazioni, vedere [Panoramica del GDPR](../../dev-itpro/gdpr/gdpr-guide.md).

## <a name="environment-and-data-management"></a>Gestione ambiente e dati

Questa sezione descrive alcuni tipici eventi di gestione ambiente e dati che si verificano nel servizio.

### <a name="environment-and-data-management-events-for-production-instances"></a>Eventi di gestione dell'ambiente e dei dati per le istanze di produzione

LCS fornisce [strumenti self-service](../../dev-itpro/deployment/infrastructure-stack.md) e [operazioni di spostamento del database](../../dev-itpro/database/dbmovement-operations.md) utilizzati per eseguire attività di gestione dell'ambiente e dei dati. Di seguito sono riportati alcuni esempi.

**Evento:** [Richiedere un'istanza di produzione](../imp-lifecycle/prepare-go-live.md#requesting-the-production-environment)

- Completare la [Lista di controllo per la fase operativa](../imp-lifecycle/prepare-go-live.md) e inviarla al team [Microsoft FastTrack](/dynamics365/fasttrack/).
- Completare lo [Strumento di stima degli abbonamenti LCS](../../dev-itpro/lifecycle-services/subscription-estimator.md) prima di richiedere un'istanza di produzione.
- Completare tutte le attività di implementazione specificate nella [Metodologia LCS](../../dev-itpro/lifecycle-services/create-methodology.md).

**Evento:** [Copia di un database sandbox in un'istanza di produzione](../../dev-itpro/database/dbmovement-scenario-goldenconfig.md)

- Eseguito per la simulazione della fase operativao per la fase operativa effettiva.

**Evento:** [Modalità manutenzione](../../dev-itpro/sysadmin/maintenance-mode.md)

1. Attiva la modalità manutenzione in LCS.
2. Completa la manutenzione richiesta.
3. Disabilitare la modalità manutenzione in LCS.

### <a name="environment-and-data-management-events-for-non-production-instances"></a>Eventi di gestione dell'ambiente e dei dati per le istanze di non produzione

LCS fornisce [provisioning self-service](../../dev-itpro/deployment/infrastructure-stack.md) e le [operazioni di spostamento del database](../../dev-itpro/database/dbmovement-operations.md) utilizzati per eseguire attività di gestione dell'ambiente e dei dati. Di seguito sono riportati alcuni esempi.

**Evento:** [Distribuzione di una nuova istanza sandbox](../../dev-itpro/deployment/deployenvironment-newinfrastructure.md)

- Assicurati che tutte le istanze richieste siano state [pianificate](../imp-lifecycle/environment-planning.md) e che le offerte aggiuntive applicabili sono state acquistate.
- Eseguire il processo di distribuzione in LCS.
- Completare tutte le attività specificate nelle liste di controllo LCS.
    
>[!NOTE]
>Un ambiente sandbox di sviluppo è una macchina virtuale (VM) che è [distribuito nella sottoscrizione di Azure del cliente](../../dev-itpro/dev-tools/access-instances.md) e gestito dal cliente.

**Evento:** [Copia di un database di configurazione da un ambiente sandbox a quello di produzione](../../dev-itpro/database/dbmovement-scenario-goldenconfig.md)

- Eseguito per la simulazione della fase operativao per la fase operativa effettiva.

**Evento:** [Ripristino di un backup temporizzato di produzione in un'istanza non di produzione](../../dev-itpro/database/database-pitr-prod-sandbox.md)

- Esegui l'opzione [Aggiorna database](../../dev-itpro/database/database-refresh.md) in LCS.
- Post-copia: elimina o offusca i dati sensibili tramite script, regola le configurazioni delle applicazioni specifiche dell'ambiente (come gli endpoint di integrazione) e abilita o aggiungi utenti. Nota che queste modifiche vengono apportate applicando un [pacchetto dati](../../dev-itpro/data-entities/data-entities-data-packages.md#import-a-data-package).

**Evento:** [Ripristino temporizzato del database dell'istanza non di produzione](../../dev-itpro/database/database-point-in-time-restore.md)

- Accetta che il processo non può essere annullato.
- Eseguire l'operazione di ripristino temporizzato in LCS.

**Evento:** Copia di un database sandbox di livello 2 in una sandbox di sviluppo per la risoluzione dei problemi e [debug](../../dev-itpro/database/dbmovement-scenario-debugdiag.md)

- Eseguire l'operazione di esportazione del database in LCS nell'ambiente sandbox di livello 2.
- Importa e aggiorna il database nell'ambiente di sviluppo.

## <a name="data-backup-and-retention"></a>Backup e conservazione dei dati

I database per gli ambienti Finance and Operations nell'abbonamento SaaS sono protetti da backup automatici. Per gli ambienti di produzione, i backup automatici vengono conservati per 28 giorni, a meno che Microsoft non esegua un rollback. Per gli ambienti sandbox (di livello 2+), vengono conservati per sette giorni. È possibile eseguire un rollback dell'ambiente di produzione se si verifica un errore durante un aggiornamento di manutenzione pianificato.

Per ulteriori informazioni sui backup automatici, vedere [Backup automatici - Database SQL di Azure e Istanza gestita SQL](/azure/azure-sql/database/automated-backups-overview?tabs=single-database).

## <a name="service-activity-responsibilities"></a>Responsabilità delle attività di assistenza

La tabella seguente descrive alcuni scenari e attività tipiche per il servizio. Indica inoltre se Microsoft, il cliente o sia Microsoft che il cliente sono responsabili delle attività.

| Attività | Responsabilità di Microsoft | Responsabilità del cliente |
|---|---|---|
| **Provisioning dei tenant iniziali** | | |
| Dimensiona il carico previsto in LCS utilizzando lo strumento di stima degli abbonamenti e richiedi il provisioning di ambienti specifici. | | X |
| Effettua il provisioning di tutte le istanze di produzione e non di produzione. | X | |
| Convalida le istanze di produzione e non di produzione distribuite. | | X |
| **Aggiornamenti del servizio** | |
| Applicare gli aggiornamenti del servizio alle istanze designate non di produzione e di produzione. | X | |
| Applicare manualmente gli aggiornamenti del servizio da LCS alle istanze sandbox. Definire, sviluppare, testare l'aggiornamento e fornire il pacchetto di aggiornamento del codice a LCS. | | X |
| Richiede e programmare le operazioni in modo che gli aggiornamenti delle estensioni vengano applicati all'istanza di produzione. | | X |
| Crea un backup del codice e dei dati per l'istanza di produzione prima che vengano applicati gli aggiornamenti. | X | |
| In caso di errore, eseguire il rollback dell'istanza di produzione al backup del codice e dei dati. | X | |
| **Gestione dati (backup, ripristino e aggiornamento)** | | |
| Eseguire il backup del database. | X | |
| Determinare l'alta disponibilità e un piano di ripristino di emergenza. | X | |
| Monitora le prestazioni del database dell'istanza di produzione. | X | |
| Ottimizza le prestazioni del database dell'istanza di produzione. | X | |
| Eseguire l'aggiornamento temporizzato del database delle istanze di produzione su un'istanza non di produzione. | | X |
| **Aggiornamento dell'infrastruttura** | | |
| Pianifica gli aggiornamenti regolari dell'infrastruttura. | X | |
| **Scalabilità verso l'alto e verso il basso (utenti, spazio di archiviazione e istanze)** | | |
| Acquista utenti aggiuntivi e componenti aggiuntivi non di produzione. | | X |
| Aggiorna le modifiche all'utilizzo nello Strumento di stima degli abbonamenti LCS. | | X |
| Segnalare eventuali problemi di prestazioni significativi che influiscono sull'utilizzo del servizio. | | X |
| Gestire in modo proattivo le risorse necessarie per il servizio applicabile. | X | |
| Indagare e risolvere gli incidenti. | X | |
| **Sicurezza (accesso utente)** | | |
| Fornire all'utente l'accesso al servizio. | | X |
| Fornire l'accesso al progetto LCS per la gestione e il funzionamento delle istanze che sono state distribuite tramite LCS. | | X |
| **Monitoraggio delle istanze di produzione** | | |
| Monitoraggio delle istanze di produzione 24 ore su 24, 7 giorni su 7. | X | |
| Comunica in modo proattivo al cliente gli incidenti che coinvolgono l'istanza di produzione. | X | |
| **Gestione e monitoraggio delle istanze non di produzione** | | |
| Gestisci le istanze non di produzione utilizzando LCS. | | X |
| Monitora le istanze di produzione. | | X |

## <a name="service-update-strategy"></a>Strategia di aggiornamenti del servizio

In conformità ai [criteri del ciclo di vita del software](../../dev-itpro/migration-upgrade/versions-update-policy.md),Finance and Operations le app seguono i [criteri del ciclo di vita moderni](../../dev-itpro/migration-upgrade/versions-update-policy.md#modern-lifecycle-policy) di Microsoft, che copre i prodotti che sono continuamente assistiti e supportati. 

Microsoft rilascia otto aggiornamenti del servizio per le app Finance and Operations ogni anno nei seguenti mesi:

- gennaio
- febbraio
- aprile
- Mag
- luglio
- agosto
- ottobre
- novembre

>[!NOTE]
>Aprile e ottobre sono i principali cicli di rilascio delle funzionalità. I clienti possono sospendere un singolo aggiornamento del servizio per un massimo di tre cicli di aggiornamento consecutivi.

Per ulteriori informazioni, rivedere gli argomenti seguenti:

- [Panoramica aggiornamenti del servizio One Version](../../dev-itpro/lifecycle-services/oneversion-overview.md)
- [Configurare gli aggiornamenti del servizio tramite LCX](../../dev-itpro/lifecycle-services/configure-service-updates.md)
- [Sospendere gli aggiornamenti del servizio tramite LCX](../../dev-itpro/lifecycle-services/pause-service-updates.md)
- [Ricevere notifiche sugli aggiornamenti del servizio tramite LCS](../../dev-itpro/lifecycle-services/notifications-service-updates.md)
- [Strumenti di test di regressione per convalidare gli aggiornamenti del servizio](../../dev-itpro/perf-test/rsat/rsat-overview.md)
- [Roadmap di Dynamics 365 e cicli di rilascio](https://dynamics.microsoft.com/roadmap/overview/)

## <a name="security-and-administrative-access"></a>Accesso di sicurezza e amministrativo

L'accesso amministrativo all'ambiente di produzione Finance and Operations è rigorosamente controllato e registrato. I dati del cliente sono trattati in conformità alle [Condizioni dei Microsoft Online Services](https://www.microsoft.com/licensing/terms/productoffering). 

### <a name="customer-administrative-access"></a>Accesso amministrativo del cliente

L'amministratore del tenant del cliente può accedere alle istanze di produzione o alle istanze non di produzione, come descritto nella tabella seguente:

| Tipo di ambiente | Scopo | Livello di accesso del cliente |
|---|---|---|
| **Non produzione**<br>Sandbox di livello 1 | Un ambiente non di produzione che i clienti distribuiscono per scopi di sviluppo, dimostrazione o formazione. | Una sandbox di livello 1 (nota anche come ambiente ospitato nel cloud) è una macchina virtuale gestita dal cliente che viene distribuita alla sottoscrizione di Azure del cliente da LCS. Poiché si tratta di una macchina virtuale nella sottoscrizione di Azure del cliente, il cliente dispone dell'accesso amministrativo completo all'ambiente tramite Desktop remoto. |
| **Non produzione**<br>Sandbox di livello 2 (o superiore) | Un ambiente non di produzione che i clienti distribuiscono per test di accettazione degli utenti, test di integrazione, formazione, gestione temporanea o qualsiasi altro scenario di pre-produzione. | Le sandbox di livello 2 e superiori vengono distribuite nell'abbonamento SaaS di Finance and Operations. L'accesso ai database SQL di Azure associati all'ambiente non di produzione è concesso tramite [accesso just-in-time](../../dev-itpro/database/database-just-in-time-jit-access.md). L'accesso a Desktop remoto non è disponibile. |
| **Produzione** | Un ambiente di produzione viene distribuito quando il progetto è [pronto per la fase operativa iniziale](/imp-lifecycle/environment-planning.md#production-system-readiness). | Gli ambienti di produzione vengono distribuiti all'abbonamento SaaS. Tutto l'accesso avviene tramite il browser, gli endpoint di servizio o LCS. |

### <a name="microsoft-administrative-access"></a>Accesso amministrativo Microsoft

La tabella seguente mostra i diversi livelli di accesso per i diversi amministratori Microsoft:

| Amministratore | Dati cliente |
|---|---|
| Team di risposte operative<br>(Limitato al solo personale chiave) | L'accesso è concesso tramite un ticket di supporto. L'accesso è verificato e limitato alla durata dell'attività di supporto. |
| Microsoft Customer Support Services (CSS) | Nessun accesso diretto. Il cliente può utilizzare la condivisione dello schermo per collaborare con il personale di supporto per il debug dei problemi. |
| Progettazione | Nessun accesso diretto. Il team di risposte operative può utilizzare la condivisione dello schermo per collaborare con i tecnici per il debug dei problemi. |
| Altri in Microsoft | Nessun accesso. |

## <a name="monitoring"></a>Monitoraggio

Microsoft ha investito in un ampio set di strumenti per monitorare e diagnosticare le istanze di produzione dei clienti. Microsoft monitora gli ambienti di produzione dei clienti 24 ore al giorno, 7 giorni alla settimana. Per ulteriori informazioni, vedere [Supporto e monitoraggio della produzione](../imp-lifecycle/production-support-monitoring.md).

| Responsabilità di Microsoft | Responsabilità del cliente |
|---|---|
| <ul><li>Monitora la disponibilità del servizio.</li><li>Monitora e invia continuamente avvisi tramite metriche di integrità e watchdog per componenti critici come Application Object Server (AOS), Batch, Data Import/Export Framework (DIXF), Commerce e Management Reporter.</li><li>Monitorare il degrado delle prestazioni causato dai servizi di infrastruttura (come Azure Active Directory \[Azure AD\] e Azure SQL).</li><li>Se Microsoft determina che un singolo processo o processo batch sta causando aberrazioni, tale processo verrà terminato dopo la comunicazione con il cliente.</li></ul> | <ul><li>Monitorare le modifiche alle configurazioni e alle estensioni delle applicazioni che possono causare problemi di funzionalità e prestazioni.</li><li>Gli errori dell'applicazione devono essere diagnosticati utilizzando gli strumenti di monitoraggio. Utilizzare questi strumenti per diagnosticare le aberrazioni delle prestazioni segnalate dall'utente.</li><li>Informare Microsoft se è previsto un carico sul sistema oltre il picco di utilizzo previsto.</li><li>Se il servizio applicabile non è disponibile nell'istanza di produzione, il cliente può utilizzare LCS per segnalare un'[interruzione della produzione](../../dev-itpro/lifecycle-services/report-production-outage.md).</li></ul> |

Inviando richieste di supporto online, tramite LCS, i clienti consentono a Microsoft di fornire competenze tecniche rapide e approfondite nel modo più efficace ed efficiente. Sebbene sia disponibile un'opzione telefonica, dovrebbe essere utilizzata solo se l'opzione online non è disponibile. Per ulteriori informazioni, vedere [Opzioni di supporto telefonico](/power-platform/admin/support-overview.md?toc=/dynamics365/fin-ops-core/dev-itpro/toc.json&bc=/dynamics365/breadcrumb/toc.json#is-there-a-phone-number-i-can-call-to-contact-support).

## <a name="incident-management"></a>Gestione incidenti

Microsoft risponde e risolve gli incidenti in base ai livelli di gravità. I livelli di gravità dell'incidente di Microsoft possono essere modificati durante la valutazione iniziale dell'incidente e man mano che diventano disponibili ulteriori informazioni sull'impatto e sull'ambito. Se l'incidente viene mitigato, la gravità dell'incidente rimane invariata.

Per ulteriori informazioni sui livelli di gravità, vedere [questa tabella di gravità](/power-platform/admin/support-overview#what-is-initial-response-time-and-how-quickly-can-i-expect-to-hear-back-from-someone-after-submitting-my-support-request).

## <a name="business-continuity-through-high-availability-and-disaster-recovery"></a>Continuità aziendale tramite alta disponibilità e ripristino di emergenza 

Microsoft fornisce continuità aziendale e ripristino di emergenza per le istanze di produzione delle app Finance and Operations in caso di interruzioni a livello di area di Azure. Per ulteriori informazioni, vedere [Continuità aziendale e ripristino di emergenza](../../dev-itpro/sysadmin/business-continuity-disaster-recovery.md).

- **Alta disponibilità** – La funzionalità HA fornisce modi per prevenire i tempi di inattività causati dall'errore di un singolo nodo in un data center di Azure. L'architettura cloud di ogni servizio usa i set di disponibilità di Azure per il livello di calcolo per evitare eventi di errore singolo. L'HA per i database è fornito tramite [Funzionalità di Azure SQL HA](/azure/azure-sql/database/high-availability-sla).
- **Ripristino di emergenza** – [Funzionalità di ripristino di emergenza di Azure](/azure/best-practices-availability-paired-regions) proteggere ogni servizio dalle interruzioni che interessano ampiamente un intero data center di Azure. Di seguito sono riportate alcune funzionalità:

    - Replica geografica attiva SQL di Azure per il database primario (database aziendale).
    - Copie con ridondanza geografica di Archiviazione BLOB di Azure (che contiene allegati di documenti) in altre aree di Azure.
    - Area secondaria per le repliche SQL di Azure e Archiviazione BLOB di Azure.

Gli archivi dati primari sono supportati per la replica. Pertanto, i componenti per ogni servizio, come Management Reporter e l'archivio entità, utilizzano i dati trasformati dal database primario. Questi dati devono essere generati dopo la configurazione del sito di ripristino e l'avvio del servizio. Gli elementi del codice cliente e gli archivi dati recuperati vengono utilizzati per ridistribuire il sito. La ridistribuzione consente la replica dello stato dei nodi di calcolo, insieme alla rete e ad altri componenti, per utilizzare gli archivi dati ripristinati per configurare il sito secondario. Se viene utilizzato il ripristino di emergenza per ripristinare l'istanza di produzione del cliente, Microsoft e il cliente adempieranno alle proprie responsabilità di [gestione degli incidenti](service-description.md#incident-management).

I piani e le procedure di ripristino di emergenza di Microsoft vengono esaminati regolarmente tramite audit System and Organization Controls (SOC). Questi controlli di conformità attestano il processo tecnico e procedurale del ripristino di emergenza di Microsoft, tra cui le app Dynamics 365 Finance and Operations. [Conformità SOC](/compliance/regulatory/offering-soc-2) i report di controllo e tutti gli altri report di conformità sono disponibili su [Offerte di conformità del Centro protezione Microsoft](/compliance/regulatory/offering-home).

| Responsabilità di Microsoft | Responsabilità del cliente |
|---|---|
| Microsoft effettua il provisioning di un ambiente secondario nel data center associato di Azure quando viene distribuita l'istanza di produzione primaria. Per ulteriori informazioni, vedi [Continuità aziendale e ripristino di emergenza: aree associate di Azure](/azure/best-practices-availability-paired-regions). | Nessuno |
| Microsoft abilita la ridondanza geografica di Azure SQL e Archiviazione BLOB di Azure quando viene distribuita l'istanza di produzione primaria. | Nessuno |
| Microsoft abilita il backup automatico sui database SQL di Azure. | Nessuno |
| <p>Quando si verifica un'interruzione, Microsoft determina se è necessario eseguire un failover per il cliente e se si verificherà una perdita di dati. I clienti potrebbero riscontrare una perdita di dati fino a 15 minuti, a seconda della natura e dei tempi dell'interruzione. | In caso di perdita di dati, il cliente potrebbe dover fornire un'autorizzazione scritta per attivare il failover. |
| Quando si verifica un failover, il servizio applicabile funziona in modalità limitata. La manutenzione degli aggiornamenti non può essere attivata in modalità di failover. | Il cliente non può richiedere distribuzioni di pacchetti o altre richieste di intervento di manutenzione regolare in modalità di failover. |
| Quando il data center diventa operativo, Microsoft esegue il failback all'istanza di produzione nell'area di Azure primaria. Riprendono le normali operazioni. | Il cliente potrebbe dover disconnettersi in caso di failback all'istanza di produzione nell'area di Azure primaria. |

## <a name="finance-and-operations-support-offerings"></a>Offerte di supporto Finance and Operations

Il supporto tecnico è disponibile nei mercati in cui vengono offerti i servizi Finance and Operations. [Esperienze di supporto](../../dev-itpro/lifecycle-services/lcs-support.md) sono forniti in LCS o nelle app Finance and Operations. Di seguito sono riportati alcuni esempi.

- [Ricerca argomento](../../dev-itpro/lifecycle-services/issue-search-lcs.md) in LCS
- [Supporto tecnico integrato](../../dev-itpro/lifecycle-services/support-experience.md) nelle app Finance and Operations
- [Supporto basato sul cloud](../../dev-itpro/lifecycle-services/cloud-powered-support-lcs.md) in LCS

Microsoft offre ai clienti Finance and Operations tre piani di supporto: Premier, Professional Direct e il supporto incluso nell'abbonamento. Il livello di supporto varia in base al piano. La tabella seguente mostra un confronto tra i tre piani.

| Funzione di supporto | Premier | Professional Direct | Abbonamento |
|---|---|---|---|
| Invio illimitato di interruzioni/riparazioni di incidenti | Sì | Sì | Sì |
| Accesso 24 ore su 24, 7 giorni su 7 tramite LCS | Sì | Sì | Sì |
| Tempo di risposta all'incidente | Meno di un'ora | Meno di un'ora | Il giorno lavorativo successivo |
| Orari di consulenza | Pool acquisiti per accordo. | No | No |
| Account manager di supporto dedicato | Sì | No | No |
| Tecnico di supporto dedicato | Impegnato con un contratto separato | No | No |

Per ulteriori informazioni, vedere [Panoramica sul supporto](/power-platform/admin/support-overview).

### <a name="process-to-engage-support"></a>Processo per coinvolgere il supporto

In caso di incidenti che coinvolgono le app Finance and Operations, i clienti inviano ticket di supporto a Microsoft tramite LCS. CSS gestisce gli incidenti, in base al piano di supporto del cliente e alla gravità dell'incidente come indicato da CSS.

### <a name="service-level-agreement"></a>Contratto di servizio

Microsoft si impegna a un tasso di disponibilità del 99,9% al mese del servizio. Se Microsoft non raggiunge e non mantiene il livello di servizio per il servizio applicabile come descritto nel contratto di servizio, il cliente potrebbe avere diritto a un credito per una parte delle sue tariffe mensili per quel servizio. Per informazioni su come avviare un credito di servizio, vedere la sezione "Reclami" del [Contratto di servizio](https://www.microsoft.com/licensing/docs/view/Service-Level-Agreements-SLA-for-Online-Services).

## <a name="important-resources"></a>Risorse importanti

- **[Centro protezione](https://www.microsoft.com/trust-center)** – Ottieni informazioni su dove vengono archiviati i dati Finance and Operations , oltre a ulteriori informazioni sulla privacy, la conformità e le procedure di sicurezza.
- **[Termini di licenza e documentazione](https://www.microsoftvolumelicensing.com/)** – Accesso rapido ai termini, alle condizioni e alle informazioni supplementari relative alle licenze relative all'utilizzo di prodotti e servizi concessi in licenza tramite i programmi Microsoft Volume Licensing.
- **[Termini di licenza](https://www.microsoft.com/licensing/product-licensing/)** – Le risorse in questa pagina definiscono i termini e le condizioni per i prodotti software e servizi online acquistati tramite i programmi di licenza commerciale Microsoft.
- **[Criterio del ciclo di vita di Microsoft](/lifecycle/)** – Questa pagina fornisce linee guida coerenti e prevedibili per la disponibilità del supporto per tutta la durata di un prodotto.
- **[Guida alle licenze](https://www.microsoft.com/licensing/docs/view/Microsoft-Dynamics-365)** – Utilizza questa guida per ulteriori informazioni su come ottenere la licenza di Dynamics 365.
- **[Servizio Clienti](https://dynamics.microsoft.com/support/)** – Ottieni supporto leader del settore per le tue app Dynamics 365.
- **[Dynamics Lifecycle Services](https://lcs.dynamics.com/)** – Gestisci il ciclo di vita delle tue applicazioni e passa a implementazioni prevedibili, ripetibili e di alta qualità.

## <a name="definitions"></a>Definizioni

### <a name="azure-region"></a>[Regione Azure](/azure/availability-zones/az-overview#regions)

Un'area geografica in cui esistono uno o più data center di Azure. Gli esempi includono Stati Uniti ed Europa.

### <a name="business-process-modeler-bpm"></a>[Modellatore di processi aziendali](../../dev-itpro/lifecycle-services/bpm-overview.md)

Uno strumento in LCS che aiuta a completare un'analisi degli scostamenti/adeguatezza per una data implementazione utilizzando le definizioni dei processi aziendali dell'American Productivity & Quality Center (APQC) supportate nelle app Finance and Operations.

### <a name="cloud-solution-provider"></a>Fornitore di soluzioni cloud

Un partner che fa parte del programma Microsoft Cloud Solution Provider (CSP) e che fornisce ai clienti servizi cloud a valore aggiunto, supporto, una fattura e gestione dei clienti su larga scala.

### <a name="customer"></a>Cliente

Un'entità aziendale che utilizza app Finance and Operations ed è rappresentata da un tenant in Office 365.

### <a name="development-environment"></a>Ambiente di sviluppo

Un ambiente sandbox non di produzione utilizzato per sviluppare estensioni. I clienti distribuiscono questo ambiente alla propria sottoscrizione di Azure da LCS. Questo ambiente può essere utilizzato anche per la dimostrazione, la formazione o altre attività di test. È anche noto come [Sandbox di livello 1](../imp-lifecycle/environment-planning.md#tier-1-vs-tier-2-and-higher).

### <a name="downtime"></a>Tempi di fermo

Qualsiasi periodo in cui gli utenti non possono accedere al loro tenant attivo a causa di un errore nella piattaforma non scaduta o nell'infrastruttura del servizio, come determinato da Microsoft dal monitoraggio automatico dell'integrità e dai registri di sistema. Il tempo di inattività non include il tempo di inattività pianificato, l'indisponibilità delle funzionalità aggiuntive del servizio, l'impossibilità di accedere al servizio a causa delle modifiche apportate al servizio o i periodi in cui viene superata la capacità dell'unità di scala.

### <a name="implementation-partner"></a>Partner implementazione

Il partner che il cliente seleziona per personalizzare, configurare, implementare e gestire le proprie soluzioni Finance and Operations.

### <a name="incident"></a>Evento imprevisto

Un problema che i clienti incontrano mentre usano il servizio Finance and Operations e inviano un ticket tramite LCS.

### <a name="microsoft-customer-support-services-css"></a>Microsoft Customer Support Services (CSS)

Il team di supporto globale Microsoft dedicato a fornire un servizio di qualità per le app Finance and Operations.

### <a name="microsoft-dynamics-lifecycle-services-lcs"></a>Microsoft Dynamics Lifecycle Services (LCS)

Il portale amministrativo per la gestione del ciclo di vita delle app Finance and Operations dalla prova, all'implementazione, alla gestione e al supporto della post-produzione. Per ulteriori informazioni, vedere [Risorse Lifecycle Services](../../dev-itpro/lifecycle-services/lcs.md).

### <a name="non-production-instance"></a>Istanza non di produzione

Qualsiasi delle seguenti istanze di un servizio che il cliente utilizza per convalidare le estensioni ed eseguire altre attività di sviluppo:

- **Sandbox di livello 1** – Istanza sviluppatore (ospitata dal cliente)
- **Sandbox di livello 2** – Istanza di test di accettazione standard
- **Livelli sandbox 3-5** – Sandbox aggiuntivi

Per ulteriori informazioni sui livelli da 2 a 5, vedere [Selezione dell'ambiente di livello 2 o superiore corretto](../imp-lifecycle/environment-planning.md#selecting-the-correct-tier-2-or-higher-environment).

### <a name="production-instance"></a>Istanza di produzione

Un ambiente Finance and Operations che il cliente utilizza per gestire le sue transazioni quotidiane "live" e i processi aziendali.

### <a name="sandbox-environment"></a>Ambiente sandbox

Un ambiente non di produzione che il cliente utilizza per la dimostrazione, la formazione, il test di accettazione dell'utente, la convalida delle estensioni e altre attività di test.

### <a name="service"></a>Gestione assistenza

Tutti i servizi principali inclusi nelle app Finance and Operations.

### <a name="service-level-agreement-sla-for-microsoft-online-services"></a>Contratto di servizio per i servizi online Microsoft

Il contratto di servizio si applica ai servizi online Microsoft. Per ulteriori informazioni, vedere [Contratti di servizio](https://www.microsoft.com/licensing/docs/view/Service-Level-Agreements-SLA-for-Online-Services).

### <a name="service-update"></a>Aggiornamento del servizio

Ambienti Finance and Operations dei servizi Microsoft su base coerente attraverso gli aggiornamenti del servizio. I clienti impostano il proprio calendario di aggiornamento del servizio, in base alle proprie esigenze aziendali. Per ulteriori informazioni, vedi [Aggiornamenti del servizio One Version](../../dev-itpro/lifecycle-services/oneversion-overview.md).

### <a name="user"></a>Utente

Una sola persona che usa gli ambienti Finance and Operations e chi è associato al tenant di un cliente.
