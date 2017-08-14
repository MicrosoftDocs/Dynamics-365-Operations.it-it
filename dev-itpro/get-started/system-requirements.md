---
title: Requisiti di sistema
description: In questo argomento vengono elencati i requisiti di sistema per la versione corrente di Microsoft Dynamics 365 for Finance and Operations, Enterprise edition per le distribuzioni locali e nel cloud.
author: sericks007
manager: AnnBe
ms.date: 07/14/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, Developer, IT Pro
ms.reviewer: robinr
ms.search.scope: Core
ms.custom: 55651
ms.assetid: e564d51d-42d3-47c5-b388-93b8219c692a
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-08-30T00:00:00.000Z
ms.dyn365.ops.version: Platform update 2
ms.translationtype: HT
ms.sourcegitcommit: 08c38aada355583c5a6872f75b57db95d9b81786
ms.openlocfilehash: 871ba89973f6af341c536f67db056bebb54600b3
ms.contentlocale: it-it
ms.lasthandoff: 07/25/2017

---

# <a name="system-requirements"></a>Requisiti di sistema

[!include[banner](../includes/banner.md)]


In questo argomento vengono elencati i requisiti di sistema per la versione corrente di Microsoft Dynamics 365 for Finance and Operations, Enterprise edition per le distribuzioni locali e nel cloud. Prima di installare Finance and Operations, laddove appropriato, verificare che il sistema su cui si sta lavorando soddisfi almeno i requisiti minimi di rete, hardware e software.


## <a name="supported-microsoft-office-applications"></a>Applicazioni di Microsoft Office supportate
Le applicazioni di Office seguenti sono supportate nelle distribuzioni locali e cloud di Finance and Operations.
-   Per eseguire i componenti aggiuntivi di Microsoft Excel e Word, è necessario che sia installato Microsoft Office 2016 per Windows o Mac. Per ulteriori informazioni sui requisiti di versione, vedere [Risoluzione dei problemi di integrazione di Office](/dynamics365/unified-operations/dev-itpro/office-integration/office-integration-troubleshooting).
-   Per visualizzare i documenti generati dalla funzionalità Esporta in Excel o Esporta in Word, è necessario che sia installato Microsoft Office 2007 o versioni successive.

# <a name="system-requirements-specific-to-cloud-deployments"></a>Requisiti di sistema specifici per le distribuzioni nel cloud
## <a name="network-requirements"></a>Requisiti di rete
-   Finance and Operations è progettato per reti con latenza pari a 250-300 millisecondi (ms) o inferiore. Questa è la latenza da un client browser al data center di Microsoft Azure che ospita Finance and Operations. Si consiglia di verificare la latenza di rete all'indirizzo <http://www.azurespeed.com>.
-   I requisiti di larghezza di banda per Finance and Operations dipendono dallo scenario. La maggior parte degli scenari tipici richiede una larghezza di banda superiore a 50 kilobyte al secondo (Kbps). Tuttavia, per scenari con requisiti di carico utile elevati, ad esempio aree di lavoro o scenari che implicano personalizzazioni estese, è consigliabile disporre di maggiore larghezza di banda.

In genere, Finance and Operations è ottimizzato per Internet. Il numero di round trip da un client del browser al data center di Azure è esiguo e l'intero carico utile è compresso. 

> [!WARNING]
> Non calcolare i requisiti di larghezza di banda da un'ubicazione client moltiplicando il numero di utenti per i requisiti minimi di larghezza di banda. L'utilizzo simultaneo di una determinata ubicazione è molto difficile da calcolare. Per i clienti con problemi relativi ai requisiti di larghezza di banda, utilizzare una versione di anteprima di Finance and Operations.

## <a name="net-framework-requirements"></a>Requisiti per .NET Framework
Finance and Operations richiede .NET Framework versione 4.6.2 per tutte le applicazioni ClickOnce, ad esempio l'agente di distribuzione documenti. Per istruzioni relative all'installazione, vedere [Installazione di .NET Framework](https://msdn.microsoft.com/en-us/library/5a4x27ek(v=vs.110).aspx).

## <a name="supported-web-browsers"></a>Web browser supportati
L'applicazione Web può essere eseguita in uno dei seguenti Web browser eseguiti sui sistemi operativi specificati:


-   Microsoft Edge (ultima versione pubblicamente disponibile) su Windows 10
-   Internet Explorer 11 in Windows 10, Windows 8.1 o Windows 7
-   Google Chrome (ultima versione pubblicamente disponibile) su Windows 10, Windows 8.1, Windows 8, Windows 7 o tablet Google Nexus 10
-   Apple Safari (ultima versione pubblicamente disponibile) su Mac OS X 10.10 (Yosemite), 10.11 (El Capitan), 10.12 (Sierra) o Apple iPad

Per trovare l'ultima versione rilasciata di ogni Web browser, andare al sito Web del produttore software. 

> [!NOTE]
> -   Per acquisire le immagini screenshot con Registrazione attività e includerle nei documenti di Microsoft Word generati, è necessario installare un'estensione Chrome pre-release. <!---For instructions about how to install the extension, see [Screenshot Extension setup](/dynamics365/unified-operations/dev-itpro/user-interface/task-recorder).-->
> -   L'editor flusso di lavoro viene avviato come un'applicazione ClickOnce. Solo Microsoft Edge e Internet Explorer (su una versione supportata di Microsoft Windows) supportano le applicazioni ClickOnce. L'applicazione ClickOnce dell'editor flusso di lavoro richiede un sistema operativo compatibile a 64 bit.
> -   La funzionalità Progettazione report per i report finanziari viene avviata come un'applicazione ClickOnce. Richiede un sistema operativo compatibile a 64 bit. Se si utilizza Chrome, è necessario installare un'estensione ClickOnce per scaricare il client di progettazione report. Se si utilizza Chrome con la modalità in incognito, assicurarsi che l'estensione ClickOnce sia abilitata anche per tale modalità.
> -   Per visualizzare l'anteprima dei file PDF, si consiglia di utilizzare browser come Microsoft Edge (versione pubblica più recente) su Windows 10 o Google Chrome (versione pubblica più recente) su Windows 10, Windows 8.1, Windows 8, Windows 7 o tablet Google Nexus 10.


### <a name="supported-web-browsers-for-retail-cloud-pos"></a>Web browser supportati per POS cloud vendita al dettaglio

Retail Cloud POS può essere eseguito in uno dei seguenti Web browser eseguiti sui sistemi operativi specificati:

-   Microsoft Edge (ultima versione pubblicamente disponibile) su Windows 10
-   Internet Explorer 11 in Windows 10, Windows 8.1 o Windows 7
-   Chrome (ultima versione pubblicamente disponibile) su Windows 10, Windows 8.1 o Windows 7

## <a name="retail-modern-pos-requirements"></a>Requisiti per Retail Modern POS
### <a name="supported-operating-systems"></a>Sistemi operativi supportati

-   Retail Modern POS è un'applicazione a 32 bit, ma verrà eseguita su entrambe le architetture x86 e x64.
-   Retail Modern POS è supportato solo su Windows 10 edizioni Pro, Enterprise ed Enterprise Long Term Servicing Branch (LTSB).

### <a name="minimum-system-requirements"></a>Requisiti minimi di sistema

-   La risoluzione minima supportata è 1280 × 1024.
-   Il computer su cui viene eseguito Retail Modern POS deve soddisfare i seguenti requisiti:
    -   Deve disporre, come minimo, di un processore dual-core in esecuzione ad almeno 2 gigahertz (GHz).
    -   Deve disporre, come minimo, di 3 gigabyte (GB) di RAM.
    -   Deve disporre dell'accesso a Internet.

## <a name="retail-hardware-station-requirements"></a>Requisiti per Retail hardware station
### <a name="supported-operating-systems"></a>Sistemi operativi supportati

-   Retail hardware station è un'applicazione a 32 bit, ma verrà eseguita su entrambe le architetture x86 e x64.
-   Retail hardware station è supportata sui seguenti sistemi operativi:
    -   Windows 7 edizioni Professional, Enterprise e Ultimate 
    
    > [!NOTE]
    > Windows 7 è supportato solo se Internet Explorer 11 viene installato manualmente nel sistema.

    -   Windows 8.1 Update 1 edizioni Professional, Enterprise ed Embedded
    -   Windows 10 edizioni Pro, Enterprise ed Enterprise LTSB

### <a name="minimum-system-requirements"></a>Requisiti minimi di sistema

Il computer deve soddisfare tutti i requisiti di sistema per l'installazione e l'utilizzo dei seguenti elementi:

-   Internet Information Services (IIS)
-   Hardware di terze parti

## <a name="retail-store-scale-unit-requirements"></a>Requisiti per Retail Store Scale Unit
### <a name="supported-operating-systems"></a>Sistemi operativi supportati

-   Retail Store Scale Unit è un'applicazione a 32 bit, ma verrà eseguita su entrambe le architetture x86 e x64.
-   Retail Store Scale Unit è supportata sui seguenti sistemi operativi:
    -   Windows 7 edizioni Professional, Enterprise e Ultimate
    -   Windows 8.1 Update 1 edizioni Professional, Enterprise ed Embedded
    -   Windows 10 edizioni Pro, Enterprise ed Enterprise LTSB

### <a name="minimum-system-requirements"></a>Requisiti minimi di sistema

-   4 GB di RAM
-   CPU con velocità di picco da 1,6 GHz per core (minimo due core).
-   Almeno 10 GB di spazio libero (il database del canale può richiedere una quantità di spazio notevole).

### <a name="recommended-system-requirements"></a>Requisiti di sistema consigliati

-   6 GB di RAM
-   CPU con velocità di picco da 2,4 GHz i7 (o equivalente) per core (quattro core consigliati).
-   Almeno 10 GB di spazio libero (il database del canale può richiedere una quantità di spazio notevole).

## <a name="connector-requirements"></a>Requisiti del connettore
### <a name="supported-operating-systems"></a>Sistemi operativi supportati

-   Il connettore per Microsoft Dynamics AX dispone di due programmi di installazione distinti, **Async Server Connector service** e **Real-time service for Dynamics AX 2012 R3**.
-   Entrambi i componenti sono applicazioni a 32 bit, ma vengono eseguiti sia su architetture x86 che su quelle x64.
-   Entrambi i componenti sono supportati nei sistemi operativi seguenti:
    -   Windows 7 edizioni Professional, Enterprise e Ultimate
    -   Windows 8.1 Update 1 edizioni Professional, Enterprise ed Embedded
    -   Windows 10 edizioni Pro, Enterprise ed Enterprise LTSB
    -   Windows Server 2012 R2, Windows Server 2016

### <a name="minimum-system-requirements"></a>Requisiti minimi di sistema

-   2 GB di RAM, 4 GB di RAM consigliati
-   CPU con velocità di picco da 1,6 GHz per core (minimo due core).
-   Almeno 10 GB di spazio libero (il database del canale può richiedere una quantità di spazio notevole).

## <a name="requirements-for-development-on-local-vms"></a>Requisiti per sviluppo su VM locali
Per ulteriori informazioni sui requisiti per lo sviluppo su macchine virtuali locali (VM), vedere [VM in esecuzione presso la sede](../dev-tools/access-instances.md).

# <a name="system-requirements-for-on-premises-deployments"></a>Requisiti di sistema per le distribuzioni locali

## <a name="network-requirements"></a>Requisiti di rete
Finance and Operations (locale) può operare su reti che usano il protocollo Internet versione 4 (IPv4) o versione 6 (IPv6). Considerare l'ambiente di rete quando si pianifica il sistema e utilizzare le linee guida seguenti.

### <a name="network-response-time"></a>Tempo di risposta della rete
La tabella seguente elenca i requisiti minimi di rete per la connessione tra il Web browser e il Server oggetti applicativi (AOS) e per la connessione tra AOS e il database in un sistema locale.

| Valore     | Web browser ad AOS | AOS a database                                            |
|-----------|--------------------|------------------------------------------------------------|
| Larghezza di banda | 50 KBps per utente   | 100 MBps                                                   |
| Latenza   | < 250-300 ms       | < 1 ms (solo LAN). AOS e database devono essere collocati insieme. |

- Finance and Operations (locale) è progettato per reti con latenza pari a 250-300 millisecondi (ms) o inferiore. Questa è la latenza da un client browser al data center che ospita Finance and Operations.
- I requisiti di larghezza di banda per Finance and Operations (locale) dipendono dallo scenario. Gli scenari comuni richiedono una larghezza di banda di oltre 50 kilobyte al secondo (KBps) tra il browser e il server di Finance and Operations. Tuttavia, per scenari con requisiti di carico utile elevati, ad esempio le aree di lavoro o gli scenari che implicano personalizzazioni estese, è consigliabile disporre di maggiore larghezza di banda, a seconda dell'utilizzo.
Le distribuzioni dove AOS e il database SQL Server risiedono in data center diversi non sono supportate. AOS e il database SQL Server devono essere collocati nella stessa ubicazione. In generale, Finance and Operations è ottimizzato per ridurre di round trip browser-a-server. Il numero di round trip da un client browser al data center è pari a zero o a uno per ogni interazione di utente e il carico utile è compresso.

> [!WARNING]
> Non calcolare i requisiti di larghezza di banda da un'ubicazione client moltiplicando il numero di utenti per i requisiti minimi di larghezza di banda. L'utilizzo simultaneo di una determinata ubicazione è molto difficile da calcolare. Si consiglia di utilizzare una simulazione di vita reale con un ambiente non di produzione di Finance and Operations come migliore rilevatore delle prestazioni per il caso specifico. 

### <a name="lan-environments"></a>Ambienti LAN
Negli ambienti LAN (Local Area Network) non è necessario utilizzare Desktop remoto Microsoft in Microsoft Windows Server per connettersi a Finance and Operations. Tuttavia, potrebbe essere necessario per le operazioni di manutenzione sulle VM che costituiscono le distribuzioni server.

### <a name="wan-environments"></a>Ambienti WAN
Negli ambienti WAN (Wide Area Network) non è necessario utilizzare Desktop remoto in Windows Server per connettersi a Finance and Operations.

### <a name="internet-connectivity-requirements"></a>Requisiti di connettività Internet
Finance and Operations (locale) non richiede la connettività Internet da workstation di utenti finali. Tuttavia, alcune funzionalità non saranno disponibili senza Internet.

| Client browser | Uno scenario della rete Intranet senza connettività Internet è un punto di progettazione per l'opzione di distribuzione in locale. Alcune funzionalità che richiedono servizi cloud non saranno disponibili, ad esempio librerie della Guida di attività e della Guida in LCS. |
|----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Server         | Il livello AOS o Service Fabric deve essere in grado di comunicare con LCS. Il client basato su browser in locale non necessita dell'accesso a Internet.                                                                                |
| Telemetria      | I dati di telemetria potrebbero venire persi se si verificano interruzioni lunghe nella connettività. Le interruzioni nella connettività a LCS non influiscono sulle funzionalità dell'applicazione in locale.                                                |
| LCS            | La connettività a LCS è necessaria per la distribuzione, la distribuzione del codice e le operazioni di manutenzione.                                                                                                                                 |
## <a name="telemetry-data-transfer-to-the-cloud"></a>Trasferimento dei dati di telemetria al cloud
La maggior parte dei dati di telemetria viene archiviata localmente ed è accessibile tramite il Visualizzatore eventi di Microsoft Windows. Un piccolo sottoinsieme di eventi di telemetria viene trasferito alla pipeline di telemetria Microsoft nel cloud per la diagnostica. I dati dei clienti e i dati identificabili degli utenti finali non fanno parte dei dati di telemetria inviati a Microsoft. I nomi di VM vengono inviati a Microsoft a supporto della gestione e della diagnostica dell'ambiente dal portale di LCS.

## <a name="domain-requirements"></a>Requisiti di dominio
Considerare i requisiti di dominio seguenti quando si installa Finance and Operations (locale):

- Le macchine virtuali che ospitano i componenti di Finance and Operations (locale) devono appartenere a un dominio Active Directory. Active Directory Domain Services (AD DS) deve essere configurato nella modalità nativa.
- Le macchine virtuali che eseguono componenti di Finance and Operations (locale) devono avere l'accesso reciproco configurato in Active Directory Domain Services. 
- Il controller di dominio deve essere in esecuzione in Microsoft Windows Server 2016.

## <a name="hardware-requirements"></a>Requisiti hardware
Questa sezione descrive i componenti hardware necessari per l'esecuzione di Finance and Operations (locale).
In base alla configurazione del sistema, la composizione dei dati, le applicazioni e le funzionalità che si sceglie di utilizzare, i requisiti hardware effettivi possono variare. Di seguito sono riportati alcuni dei fattori che possono influire sulla scelta dell'hardware appropriato per Finance and Operations (locale):

- Numero di transazioni all'ora.
- Numero di utenti simultanei.

## <a name="minimum-infrastructure-requirements"></a>Requisiti minimi dell'infrastruttura
Finance and Operations (locale) utilizza Microsoft Azure Service Fabric per ospitare i servizi AOS, batch, Gestione dati, Strumento di creazione report di gestione e Agente di orchestrazione dell'ambiente. I servizi Microsoft SQL Server Reporting Services (SSRS) non sono ospitati nel cluster Service Fabric.
SQL Server deve essere installato in una configurazione HADRON a disponibilità elevata che abbia almeno due nodi per la produzione.
La figura seguente mostra in numero minimo consigliato di nodi nel cluster Service Fabric.

[![Numero di nodi consigliato per il cluster service fabric](./media/system-reqs-on-premises-01.png)](./media/system-reqs-on-premises-01.png) 

## <a name="processor-and-ram-requirements"></a>Requisiti del processore e della RAM
La tabella seguente elenca il numero di processori e la quantità di memoria ad accesso casuale (RAM) che sono necessari per ognuno dei ruoli richiesti per eseguire questa opzione di distribuzione. Per altre informazioni, leggere i requisiti minimi consigliati per un cluster Service Fabric autonomo, [Pianificare e preparare il cluster Service Fabric](/azure/service-fabric/service-fabric-cluster-standalone-deployment-preparation).

> [!NOTE]
> Se nel computer è installato altro software Microsoft software, il sistema deve anche rispettare i requisiti hardware previsti dal software installato. È consigliabile limitare altre applicazioni server nello stesso computer di AOS a 1 gigabyte (GB) di RAM.

**Dimensionamento in base al ruolo e al tipo di topologia**

| Topologia   | Ruolo (tipo di nodo)              | Core di processore consigliati | Memoria consigliata (GB) |
|------------|-------------------------------|-----------------------------|-------------------------|
| Produzione | AOS, Gestione dati, Batch   | 8                           | 24                      |
|            | Strumento di creazione report di gestione           | 4                           | 16                      |
|            | SQL Server Reporting Services | 4                           | 16                      |
|            | Agente di orchestrazione                  | 4                           | 16                      |
| Sandbox    | AOS, Gestione dati, Batch   | 4                           | 24                      |
|            | Strumento di creazione report di gestione           | 4                           | 16                      |
|            | SQL Server Reporting Services | 4                           | 16                      |
|            | Agente di orchestrazione                  | 4                           | 16                      |

**Stime minime di dimensionamento per distribuzioni sandbox e di produzione**\*

| Topologia                                  | Ruolo                          | Numero di istanze |
|-------------------------------------------|-------------------------------|---------------------|
| Produzione                                | AOS (Gestione dati, Batch)  | 3                   |
|                                           | Strumento di creazione report di gestione           | 2                   |
|                                           | SQL Server Reporting Services | 1                   |
|                                           | Agente di orchestrazione\*\*                | 3                   |
| Sandbox                                   | AOS, Gestione dati, Batch   | 2                   |
|                                           | Strumento di creazione report di gestione           | 1                   |
|                                           | SQL Server Reporting Services | 1                   |
|                                           | Agente di orchestrazione                  | 3                   |
| *Topologie sandbox e di produzione di riepilogo* |                               | 16                  |

\*Questi numeri vengono convalidati dai clienti dell'anteprima e possono essere rettificati in base alle necessità in base al feedback.

\*\*L'Agente di orchestrazione è progettato come tipo di nodo primario e viene utilizzato per eseguire anche i servizi Service Fabric.

**Stime iniziali di Ad e SQL Server back-end**

[![Stime iniziali di Ad e SQL Server back-end](./media/system-reqs-on-premises-02.PNG)](./media/system-reqs-on-premises-02.PNG) 

\*Le dimensioni di SQL Server sono fortemente dipendenti dai carichi di lavoro. Per altre informazioni, vedere la sezione [Dimensionamento hardware per ambienti locali](#Hardware-sizing-for-on-premises-environments).

## <a name="storage"></a>Immagazzinamento

- **AOS** - Finance and Operations (locale) utilizza una condivisione Server Message Block (SMB) 3.0 per archiviare i dati non strutturati. Per altre informazioni, vedere [Spazi di archiviazione diretta in Windows Server 2016](/windows-server/storage/storage-spaces/storage-spaces-direct-overview).
- **SQL** - Opzioni possibili:
    - Installazione di un'unità a stato solido (SSD) a disponibilità elevata.
    - Rete SAN (Storage Area Network) ottimizzata per le velocità effettive OLTP.
    - Archiviazione collegata direttamente (DAS) a disponibilità elevata 
- **IOPS di gestione dati e SQL** - L'archiviazione sia della gestione dei dati che di SQL Server dovrebbe avere almeno 2.000 operazioni input/output al secondo (IOPS). Gli IOPS di produzione dipendono da molti fattori. Per altre informazioni, vedere la sezione "Dimensionamento hardware per ambienti locali". 
- **IOPS di macchina virtuale** - Ogni macchina virtuale deve effettuare almeno 100 IOPS in scrittura.

## <a name="virtual-host-requirements"></a>Requisiti degli host virtuali
Quando si installano gli host virtuali per un ambiente Finance and Operations (locale), fare riferimento alle liee guida seguenti: [Pianificare e preparare il cluster Service Fabric](/azure/service-fabric/service-fabric-cluster-standalone-deployment-preparation) e [Descrizione di cluster Service Fabric](/azure/service-fabric/service-fabric-cluster-resource-manager-cluster-description). Ogni host virtuale deve avere un numero di core sufficiente per l'infrastruttura che viene dimensionata. Sono possibili più configurazioni avanzate, dove SQL Server risiede nell'hardware fisico ma tutto il resto è virtualizzato. Se SQL Server è virtualizzato, il sottosistema del disco deve essere un SAN veloce o un equivalente. In tutti i casi, assicurarsi che l'impostazione di base dell'host virtuale abbia disponibilità elevata e sia ridondante. In tutti i casi, quando si utilizza la virtualizzazione, non devono essere presi snapshot delle VM.

## <a name="software-requirements-for-all-server-computers"></a>Requisiti software di tutti i computer server
Il software seguente deve essere installato in un computer prima di installare qualsiasi componente di Finance and Operations (locale):

- Microsoft .NET Framework 4.5.1 o versioni successive
- Service Fabric Per altre informazioni, vedere [Pianificare e preparare il cluster Service Fabric](/azure/service-fabric/service-fabric-cluster-standalone-deployment-preparation).

## <a name="supported-server-operating-systems"></a>Sistemi operativi server supportati
La tabella seguente elenca i sistemi operativi server che sono supportati per i componenti di Finance and Operations.

| Sistema operativo                                     | Note                                                                                  |
|------------------------------------------------------|----------------------------------------------------------------------------------------|
| Microsoft Windows Server 2016 Datacenter o Standard | Questi requisiti riguardano il database e il cluster Service Fabric che ospita AOS. |

## <a name="software-requirements-for-database-servers"></a>Requisiti software dei server di database

- Sono supportate solo le versioni a 64 bit di SQL Server 2016.
- In un ambiente di produzione, è consigliabile installare l'aggiornamento cumulativo (CU) più recente per la versione di SQL Server che si sta utilizzando.
- Finance and Operations (locale) supporta le regole di confronto Unicode che non rilevano la distinzione tra maiuscole e minuscole e la distinzione delle larghezze, ma distinguono gli accenti e i Kana. La regola di confronto deve corrispondere alle impostazioni locali Windows dei computer che eseguono le istanze di AOS. Se si configura una nuova installazione, è consigliabile selezionare una regola di confronto di Windows invece di una regola di confronto di SQL Server. Per altre informazioni su come selezionare una regola di confronto per un database SQL Server, vedere la [documentazione di SQL Server](/sql/sql-server/sql-server-technical-documentation).
La tabella seguente elenca le versioni di SQL Server che sono supportate per i database di Finance and Operations. Per altre informazioni, vedere i requisiti minimi hardware per [SQL Server](https://www.microsoft.com/en-us/sql-server/sql-server-2016).

| Fabbisogno                                                      | Note                                                                                                                     |
|------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------|
| Microsoft SQL Server 2016 Standard Edition o Enterprise Edition | Per i requisiti hardware di SQL Server 2016, vedere [Requisiti hardware e software per l'installazione di SQL Server 2016](/sql/sql-server/install/hardware-and-software-requirements-for-installing-sql-server). |

## <a name="software-requirements-for-client-computers"></a>Requisiti software dei computer client
L'applicazione Web Finance and Operations può essere eseguita su qualsiasi dispositivo che disponga di un Web browser conforme a HTML5.0. Le combinazioni dispositivo/browser specifiche confermate da Microsoft includono:

- Microsoft Edge (ultima versione pubblicamente disponibile) su Windows 10
- Internet Explorer 11 in Windows 10, Windows 8.1 o Windows 7
- Google Chrome (ultima versione pubblicamente disponibile) su Windows 10, Windows 8.1, Windows 8, Windows 7 o tablet Google Nexus 10
- Apple Safari (ultima versione pubblicamente disponibile) su Mac OS X 10.10 (Yosemite), 10.11 (El Capitan), 10.12 (Sierra) o Apple iPad

## <a name="software-requirements-for-active-directory-federation-services"></a>Requisiti software di Active Directory Federation Services 
Active Directory Federation Services (AD FS) su Windows Server 2016

Il controller di dominio deve essere Windows Server 2012 R2 o versione successiva con un livello funzionale di dominio 2012 R2 o superiore

Per ulteriori informazioni sui livelli funzionali di dominio, vedere: 
- [Livelli funzionali di Active Directory](https://technet.microsoft.com/en-us/library/cc787290(v=ws.10).aspx)
- [Informazioni sui livelli funzionali di Active Directory Domain Services](https://technet.microsoft.com/en-us/library/understanding-active-directory-functional-levels(v=ws.10).aspx)
 
## <a name="hardware-and-software-requirements-for-retail-components"></a>Requisiti hardware e software dei componenti Retail
Finance and Operations (locale) non include al momento componenti Retail.

<a name="see-also"></a>Vedere anche
--------

[Ottenere una copia di valutazione di Dynamics 365 for Finance and Operations, Enterprise edition](/dynamics365/unified-operations/dev-itpro/dev-tools/get-evaluation-copy)

