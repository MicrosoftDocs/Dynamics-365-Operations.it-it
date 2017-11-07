---
title: Requisiti di sistema per le distribuzioni locali
description: In questo argomento vengono elencati i requisiti di sistema per la versione corrente di Microsoft Dynamics 365 for Finance and Operations, Enterprise edition per le distribuzioni locali.
author: kfend
manager: AnnBe
ms.date: 08/02/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 55651
ms.assetid: 
ms.search.region: Global
ms.author: kfend
ms.search.validFrom: 2016-08-30
ms.dyn365.ops.version: Platform update 8
ms.translationtype: HT
ms.sourcegitcommit: 25a6f326c57e84d6a7c356ac5407be7ed3095f83
ms.openlocfilehash: 5edc6f0b2240e9dd2d3b72a13f35e96f016aa013
ms.contentlocale: it-it
ms.lasthandoff: 10/04/2017

---

# <a name="system-requirements-for-on-premises-deployments"></a>Requisiti di sistema per le distribuzioni locali

[!include[banner](../includes/banner.md)]

In questo argomento vengono elencati i requisiti di sistema per la versione corrente di Microsoft Dynamics 365 for Finance and Operations, Enterprise edition per le distribuzioni locali. Prima di installare Finance and Operations, laddove appropriato, verificare che il sistema su cui si sta lavorando soddisfi almeno i requisiti minimi di rete, hardware e software.

## <a name="network-requirements"></a>Requisiti di rete
Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (locale) può operare su reti che usano il protocollo Internet versione 4 (IPv4) o versione 6 (IPv6). Considerare l'ambiente di rete quando si pianifica il sistema e utilizzare le linee guida esposte di seguito.

### <a name="network-response-time"></a>Tempo di risposta della rete
La tabella seguente elenca i requisiti minimi di rete per la connessione tra il Web browser e il Server oggetti applicativi (AOS) e per la connessione tra AOS e il database in un sistema locale.

| Valore     | Web browser ad AOS                      | AOS a database |
|-----------|-----------------------------------------|------------------------------------------------------------------------------------------|
| Larghezza di banda | 50 kilobyte al secondo (KBps) per utente | 100 megabyte al secondo (MBps) |
| Latenza   | Meno di 250-300 millisecondi (ms)     | Meno di 1 ms (solo LAN). AOS e il database devono essere collocati insieme. |

- Finance and Operations (locale) è progettato per reti con latenza pari a 250-300 millisecondi (ms) o inferiore. Questa è la latenza da un client browser al data center che ospita Finance and Operations.
- I requisiti di larghezza di banda per Finance and Operations (locale) dipendono dallo scenario. Gli scenari comuni richiedono una larghezza di banda di oltre 50 KBps tra il browser e il server di Finance and Operations. Tuttavia, per scenari con requisiti di carico utile elevati, che implicano ad esempio aree di lavoro o personalizzazioni estese, è consigliabile disporre di maggiore larghezza di banda. La quantità specifica di larghezza di banda dipende dall'uso.

Le distribuzioni dove AOS e il database Microsoft SQL Server risiedono in data center diversi non sono supportate. AOS e il database SQL Server devono essere collocati nella stessa ubicazione. 

In generale, Finance and Operations è ottimizzato per ridurre di round trip browser-a-server. Il numero di round trip da un client browser al data center è pari a zero o a uno per ogni interazione di utente e il carico utile è compresso.

> [!WARNING]
> Non calcolare i requisiti di larghezza di banda da un'ubicazione client moltiplicando il numero di utenti per i requisiti minimi di larghezza di banda. L'utilizzo simultaneo di una determinata ubicazione è molto difficile da calcolare. Si consiglia di utilizzare una simulazione di vita reale con un ambiente non di produzione di Finance and Operations come migliore rilevatore delle prestazioni per il caso specifico. 

### <a name="lan-environments"></a>Ambienti LAN
Negli ambienti LAN, non è necessario utilizzare Desktop remoto Microsoft in Microsoft Windows Server per connettersi a Finance and Operations. Tuttavia, Desktop remoto potrebbe essere necessario per le operazioni di manutenzione sulle macchina virtuali (VM) che costituiscono le distribuzioni server.

### <a name="wan-environments"></a>Ambienti WAN
Negli ambienti WAN (Wide Area Network), non è necessario utilizzare Desktop remoto in Windows Server per connettersi a Finance and Operations.

### <a name="internet-connectivity-requirements"></a>Requisiti di connettività Internet
Finance and Operations (locale) non richiede la connettività Internet da workstation di utenti. Alcune funzionalità non saranno tuttavia disponibili senza connettività Internet.

|                    |   |
|--------------------|---|
| **Client browser** | Uno scenario della rete Intranet senza connettività Internet è un punto di progettazione per l'opzione di distribuzione in locale. Alcune funzionalità che richiedono servizi cloud non saranno disponibili, ad esempio librerie della Guida di attività e della Guida in Microsoft Dynamics Lifecycle Services (LCS). |
| **Server**         | Il livello Microsoft Azure Service Fabric o AOS deve essere in grado di comunicare con LCS. Il client basato su browser in locale non necessita dell'accesso a Internet. |
| **Telemetria**      | I dati di telemetria potrebbero venire persi se si verificano interruzioni lunghe nella connettività. Le interruzioni nella connettività a LCS non influiscono sulle funzionalità dell'applicazione in locale. |
| **LCS**            | La connettività a LCS è necessaria per la distribuzione, la distribuzione del codice e le operazioni di manutenzione. |

## <a name="telemetry-data-transfer-to-the-cloud"></a>Trasferimento dei dati di telemetria al cloud
La maggior parte dei dati di telemetria viene archiviata localmente ed è accessibile tramite il Visualizzatore eventi di Microsoft Windows. Un piccolo sottoinsieme di eventi di telemetria viene trasferito alla pipeline di telemetria Microsoft nel cloud per la diagnostica. I dati dei clienti e i dati identificabili degli utenti non fanno parte dei dati di telemetria inviati a Microsoft. I nomi di VM vengono inviati a Microsoft a supporto della gestione e della diagnostica dell'ambiente dal portale di LCS.

## <a name="domain-requirements"></a>Requisiti di dominio
Considerare i requisiti di dominio seguenti quando si installa Finance and Operations (locale):

- Le macchine virtuali che ospitano i componenti di Finance and Operations (locale) devono appartenere a un dominio Active Directory. Active Directory Domain Services (AD DS) deve essere configurato nella modalità nativa.
- Le macchine virtuali in cui sono in esecuzione componenti di Finance and Operations (locale) devono avere accesso reciproco. Questo accesso è configurato in AD DS. 
- Il controller di dominio deve essere Microsoft Windows Server 2012 R2 o versione successiva e il livello funzionale di dominio deve essere 2012 R2 o superiore.

## <a name="hardware-requirements"></a>Requisiti hardware
Questa sezione descrive i componenti hardware necessari per l'esecuzione di Finance and Operations (locale).

I requisiti hardware effettivi possono variare in base a configurazione del sistema, composizione dei dati, applicazioni e funzionalità che si sceglie di utilizzare. Di seguito sono riportati alcuni dei fattori che possono influire sulla scelta dell'hardware appropriato per Finance and Operations (locale):

- Numero di transazioni all'ora
- Numero di utenti simultanei

## <a name="minimum-infrastructure-requirements"></a>Requisiti minimi dell'infrastruttura
Finance and Operations (locale) utilizza Service Fabric per ospitare i servizi AOS, batch, Gestione dati, Strumento di creazione report di gestione e Agente di orchestrazione dell'ambiente. 

SQL Server deve avere una configurazione HADRON a disponibilità elevata che abbia almeno due nodi per la produzione.

L'illustrazione seguente mostra il numero minimo di nodi consigliato per il cluster Service Fabric.

[![Numero di nodi consigliato per il cluster Service Fabric](./media/system-reqs-on-premises-01.png)](./media/system-reqs-on-premises-01.png) 

## <a name="processor-and-ram-requirements"></a>Requisiti del processore e della RAM
La tabella seguente elenca il numero di processori e la quantità di memoria ad accesso casuale (RAM) che sono necessari per ognuno dei ruoli richiesti per eseguire questa opzione di distribuzione. Per altre informazioni, vedere i requisiti minimi consigliati per un cluster Service Fabric autonomo in [Pianificare e preparare il cluster Service Fabric](/azure/service-fabric/service-fabric-cluster-standalone-deployment-preparation).

> [!NOTE]
> Se nel computer è installato altro software Microsoft software, il sistema deve anche rispettare i requisiti hardware previsti dal software installato. Se altre applicazioni server sono installate nello stesso computer come AOS, è consigliabile limitare tali applicazioni server a 1 gigabyte (GB) di RAM.

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

**Stime minime di dimensionamento per distribuzioni sandbox e di produzione\***

| Topologia                                        | Ruolo                          | Numero di istanze |
|-------------------------------------------------|-------------------------------|---------------------|
| Produzione                                      | AOS (Gestione dati, Batch)  | 3                   |
|                                                 | Strumento di creazione report di gestione           | 2                   |
|                                                 | SQL Server Reporting Services | 1                   |
|                                                 | Agente di orchestrazione\*\*              | 3                   |
| Sandbox                                         | AOS, Gestione dati, Batch   | 2                   |
|                                                 | Strumento di creazione report di gestione           | 1                   |
|                                                 | SQL Server Reporting Services | 1                   |
|                                                 | Agente di orchestrazione                  | 3                   |
| *Riepilogo per topologie sandbox e di produzione* |                               | *16*                |

\* I numeri in questa tabella vengono convalidati dai clienti dell'anteprima e potrebbero essere rettificati in base al feedback di quei clienti.

\*\* L'Agente di orchestrazione è progettato come tipo di nodo primario e viene inoltre utilizzato per eseguire i servizi Service Fabric.

**Stime iniziali di AD DS e SQL Server back-end**

<table>
<thead>
<tr>
<th></th>
<th>Ruolo</th>
<th>VM/Istanze</th>
<th>Core</th>
<th>Core totali</th>
<th>Memoria per istanza (GB)</th>
<th>Memoria totale (GB)</th>
</tr>
</thead>
<tbody>
<tr>
<td rowspan="3"><strong>Infrastruttura condivisa</strong></td>
<td>SQL Server*</td>
<td>2</td>
<td>8</td>
<td>16</td>
<td>32</td>
<td>64</td>
</tr>
<tr>
<td>File server/Storage area network (SAN)/Spazio di archiviazione a disponibilità elevata</td>
<td colspan="5"><p>Lo spazio di archiviazione back-end deve essere basato su unità SSD in una rete SAN di runtime.</p>
<p>Dimensioni e velocità effettiva delle operazioni di I/O al secondo (IOPS) sono basate sulla dimensione del carico di lavoro.</p></td>
</tr>
<tr>
<td>Active Directory</td>
<td>3</td>
<td>4</td>
<td>12</td>
<td>16</td>
<td>48</td>
</tr>
<tr>
<td><em>Riepilogo per infrastruttura condivisa</em></td>
<td></td>
<td><em>5</em></td>
<td></td>
<td><em>28</em></td>
<td></td>
<td><em>112</em></td>
</tr>
</tbody>
</table>

\*Le dimensioni di SQL Server sono fortemente dipendenti dai carichi di lavoro. Per ulteriori informazioni, vedere [Dimensionamento hardware per ambienti locali](hardware-sizing-on-premises-environments.md).

## <a name="storage"></a>Immagazzinamento

- **AOS** - Finance and Operations (locale) utilizza una condivisione Server Message Block (SMB) 3.0 per archiviare i dati non strutturati. Per altre informazioni, vedere [Spazi di archiviazione diretta in Windows Server 2016](/windows-server/storage/storage-spaces/storage-spaces-direct-overview).
- **SQL** - Opzioni possibili:

    - Installazione di un'unità a stato solido (SSD) a disponibilità elevata
    - Rete SAN (Storage Area Network) ottimizzata per le velocità effettive OLTP
    - Archiviazione collegata direttamente (DAS) a disponibilità elevata 

- **IOPS di gestione dati e SQL Server** - L'archiviazione sia della gestione dei dati che di SQL Server dovrebbe avere almeno 2.000 IOPS. Gli IOPS di produzione dipendono da molti fattori. Per ulteriori informazioni, vedere [Dimensionamento hardware per ambienti locali](hardware-sizing-on-premises-environments.md).
- **IOPS di macchina virtuale** - Ogni VM deve effettuare almeno 100 IOPS in scrittura.

## <a name="virtual-host-requirements"></a>Requisiti degli host virtuali
Quando si installano gli host virtuali per un ambiente Finance and Operations (locale), fare riferimento alle linee guida in [Pianificare e preparare il cluster Service Fabric](/azure/service-fabric/service-fabric-cluster-standalone-deployment-preparation) e [Descrizione di cluster Service Fabric](/azure/service-fabric/service-fabric-cluster-resource-manager-cluster-description). Ogni host virtuale deve avere un numero di core sufficiente per l'infrastruttura che viene dimensionata. Sono possibili più configurazioni avanzate, dove SQL Server risiede nell'hardware fisico ma tutto il resto è virtualizzato. Se SQL Server è virtualizzato, il sottosistema del disco deve essere un SAN veloce o un equivalente. In tutti i casi, assicurarsi che l'impostazione di base dell'host virtuale abbia disponibilità elevata e sia ridondante. In tutti i casi, quando si utilizza la virtualizzazione, non devono essere presi snapshot delle VM.

## <a name="software-requirements-for-all-server-computers"></a>Requisiti software di tutti i computer server
Il software seguente deve essere installato in un computer prima di installare qualsiasi componente di Finance and Operations (locale):

- Microsoft .NET Framework 4.5.1 o versione successiva
- Service Fabric

Per ulteriori informazioni, vedere [Pianificare e preparare il cluster Service Fabric](/azure/service-fabric/service-fabric-cluster-standalone-deployment-preparation).

## <a name="supported-server-operating-systems"></a>Sistemi operativi server supportati
La tabella seguente elenca i sistemi operativi server che sono supportati per i componenti di Finance and Operations.

| Sistema operativo                                     | Note |
|------------------------------------------------------|-------|
| Microsoft Windows Server 2016 Datacenter o Standard | Questi requisiti riguardano il database e il cluster Service Fabric che ospita AOS. |

## <a name="software-requirements-for-database-servers"></a>Requisiti software dei server di database

- Sono supportate solo le versioni a 64 bit di SQL Server 2016.
- In un ambiente di produzione, è consigliabile installare l'aggiornamento cumulativo (CU) più recente per la versione di SQL Server che si sta utilizzando.
- Finance and Operations (locale) supporta le regole di confronto Unicode che non rilevano la distinzione tra maiuscole e minuscole e la distinzione delle larghezze, ma distinguono gli accenti e i Kana. La regola di confronto deve corrispondere alle impostazioni locali Windows dei computer che eseguono le istanze di AOS. Se si configura una nuova installazione, è consigliabile selezionare una regola di confronto di Windows invece di una regola di confronto di SQL Server. Per altre informazioni su come selezionare una regola di confronto per un database SQL Server, vedere la [documentazione di SQL Server](/sql/sql-server/sql-server-technical-documentation).

La tabella seguente elenca le versioni di SQL Server che sono supportate per i database di Finance and Operations. Per altre informazioni, vedere i requisiti minimi hardware per [SQL Server](https://www.microsoft.com/en-us/sql-server/sql-server-2016).

| Fabbisogno                                                      | Note |
|------------------------------------------------------------------|-------|
| Microsoft SQL Server 2016 Standard Edition o Enterprise Edition | Per i requisiti hardware di SQL Server 2016, vedere [Requisiti hardware e software per l'installazione di SQL Server 2016](/sql/sql-server/install/hardware-and-software-requirements-for-installing-sql-server). |

## <a name="software-requirements-for-application-object-server-aos"></a>Requisiti software per Server oggetti applicativi (AOS) 
- SQL Server Integration Services (SSIS)

## <a name="software-requirements-for-reporting-server-bi"></a>Requisiti software per Server di report (BI)
- SQL Server Reporting Services (SSRS)

## <a name="software-requirements-for-client-computers"></a>Requisiti software dei computer client
L'applicazione Web Finance and Operations può essere eseguita su qualsiasi dispositivo che disponga di un Web browser conforme a HTML 5.0. Le combinazioni dispositivo/browser specifiche confermate da Microsoft includono:

- Microsoft Edge (ultima versione pubblicamente disponibile) su Windows 10
- Internet Explorer 11 in Windows 10, Windows 8.1 o Windows 7
- Google Chrome (ultima versione pubblicamente disponibile) su Windows 10, Windows 8.1, Windows 8, Windows 7 o tablet Google Nexus 10
- Apple Safari (ultima versione pubblicamente disponibile) su Mac OS X 10.10 (Yosemite), 10.11 (El Capitan), 10.12 (Sierra) o Apple iPad

## <a name="software-requirements-for-active-directory-federation-services"></a>Requisiti software di Active Directory Federation Services 
Active Directory Federation Services (AD FS) su Windows Server 2016

Il controller di dominio deve essere Windows Server 2012 R2 o versione successiva e il livello funzionale di dominio deve essere 2012 R2 o superiore. Per ulteriori informazioni sui livelli funzionali di dominio, vedere le pagine seguenti:

- [Livelli funzionali di Active Directory](https://technet.microsoft.com/en-us/library/cc787290(v=ws.10).aspx)
- [Informazioni sui livelli funzionali di Active Directory Domain Services](https://technet.microsoft.com/en-us/library/understanding-active-directory-functional-levels(v=ws.10).aspx)

## <a name="supported-microsoft-office-applications"></a>Applicazioni di Microsoft Office supportate
Le applicazioni di Microsoft Office seguenti sono supportate nelle distribuzioni locali e cloud di Finance and Operations:

-   Per eseguire i componenti aggiuntivi di Microsoft Excel e Microsoft Word, è necessario che sia installato Microsoft Office 2016 per Windows o Mac. Per ulteriori informazioni sui requisiti di versione, vedere [Risoluzione dei problemi di integrazione di Office](../../dev-itpro/office-integration/office-integration-troubleshooting.md).
-   Per visualizzare i documenti generati dalla funzionalità Esporta in Excel o Esporta in Word, è necessario che sia installato Microsoft Office 2007 o versione successiva.
 
## <a name="hardware-and-software-requirements-for-retail-components"></a>Requisiti hardware e software dei componenti Retail
Finance and Operations (locale) non include al momento componenti Retail.

