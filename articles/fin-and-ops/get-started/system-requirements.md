---
title: Requisiti di sistema per le distribuzioni cloud
description: In questo argomento vengono elencati i requisiti di sistema per la versione corrente di Microsoft Dynamics 365 for Finance and Operations, Enterprise edition per le distribuzioni nel cloud.
author: sericks007
manager: AnnBe
ms.date: 08/02/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 55651
ms.assetid: e564d51d-42d3-47c5-b388-93b8219c692a
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-08-30
ms.dyn365.ops.version: Platform update 8
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 83637b4b2ccc01950e68569b3b8bee1a7cd69855
ms.contentlocale: it-it
ms.lasthandoff: 11/03/2017

---

# <a name="system-requirements-for-cloud-deployments"></a>Requisiti di sistema per le distribuzioni cloud

[!include[banner](../includes/banner.md)]

In questo argomento vengono elencati i requisiti di sistema per la versione corrente di Microsoft Dynamics 365 for Finance and Operations, Enterprise edition per le distribuzioni nel cloud. Prima di installare Finance and Operations, laddove appropriato, verificare che il sistema su cui si sta lavorando soddisfi almeno i requisiti minimi di rete, hardware e software.

## <a name="supported-web-browsers"></a>Web browser supportati
L'applicazione Web può essere eseguita in uno dei seguenti Web browser eseguiti sui sistemi operativi specificati:

-   Microsoft Edge (ultima versione pubblicamente disponibile) su Windows 10
-   Internet Explorer 11 in Windows 10, Windows 8.1 o Windows 7
-   Google Chrome (ultima versione pubblicamente disponibile) su Windows 10, Windows 8.1, Windows 8, Windows 7 o tablet Google Nexus 10
-   Apple Safari (ultima versione pubblicamente disponibile) su Mac OS X 10.10 (Yosemite), 10.11 (El Capitan), 10.12 (Sierra) o Apple iPad

Per trovare l'ultima versione rilasciata di ogni Web browser, andare al sito Web del produttore software. 

> [!NOTE]
> -   Per acquisire screenshot con Registrazione attività e includerli nei documenti di Microsoft Word generati, è necessario installare un'estensione Chrome pre-release. <!---For instructions about how to install the extension, see [Screenshot Extension setup](../../dev-itpro/user-interface/task-recorder).-->
> -   L'editor flusso di lavoro viene avviato come un'applicazione ClickOnce. Solo Microsoft Edge e Internet Explorer (su una versione supportata di Microsoft Windows) supportano le applicazioni ClickOnce. L'applicazione ClickOnce dell'editor flusso di lavoro richiede un sistema operativo compatibile a 64 bit.
> -   La funzionalità Progettazione report per i report finanziari viene avviata come un'applicazione ClickOnce. Richiede un sistema operativo compatibile a 64 bit. Se si utilizza Chrome, è necessario installare un'estensione ClickOnce per scaricare il client di progettazione report. Se si utilizza Chrome con la modalità in incognito, assicurarsi che l'estensione ClickOnce sia abilitata anche per tale modalità.
> -   Per visualizzare l'anteprima dei file PDF, si consiglia di utilizzare browser come Microsoft Edge (versione pubblica più recente) su Windows 10 o Google Chrome (versione pubblica più recente) su Windows 10, Windows 8.1, Windows 8, Windows 7 o tablet Google Nexus 10.

### <a name="supported-web-browsers-for-retail-cloud-pos"></a>Web browser supportati per POS cloud vendita al dettaglio

Retail Cloud POS può essere eseguito in uno dei seguenti Web browser eseguiti sui sistemi operativi specificati:

-   Microsoft Edge (ultima versione pubblicamente disponibile) su Windows 10
-   Internet Explorer 11 in Windows 10, Windows 8.1 o Windows 7
-   Chrome (ultima versione pubblicamente disponibile) su Windows 10, Windows 8.1 o Windows 7

## <a name="network-requirements"></a>Requisiti di rete
-   Finance and Operations è progettato per reti con latenza pari a 250-300 millisecondi (ms) o inferiore. Questa è la latenza da un client browser al data center di Microsoft Azure che ospita Finance and Operations. Si consiglia di verificare la latenza di rete all'indirizzo <http://www.azurespeed.com>.
-   I requisiti di larghezza di banda per Finance and Operations dipendono dallo scenario. La maggior parte degli scenari tipici richiede una larghezza di banda superiore a 50 kilobyte al secondo (Kbps). Tuttavia, per scenari con requisiti di carico utile elevati, che implicano ad esempio aree di lavoro o personalizzazioni estese, è consigliabile disporre di maggiore larghezza di banda.

In genere, Finance and Operations è ottimizzato per Internet. Il numero di round trip da un client del browser al data center di Azure è esiguo e l'intero carico utile è compresso. 

> [!WARNING]
> Non calcolare i requisiti di larghezza di banda da un'ubicazione client moltiplicando il numero di utenti per i requisiti minimi di larghezza di banda. L'utilizzo simultaneo di una determinata ubicazione è molto difficile da calcolare. I clienti con problemi relativi ai requisiti di larghezza di banda devono utilizzare una versione di anteprima di Finance and Operations.

## <a name="net-framework-requirements"></a>Requisiti per .NET Framework
Finance and Operations richiede Microsoft .NET Framework versione 4.6.2 per tutte le applicazioni ClickOnce, ad esempio l'agente di distribuzione documenti. Per istruzioni relative all'installazione, vedere [Installazione di .NET Framework](https://msdn.microsoft.com/en-us/library/5a4x27ek(v=vs.110).aspx).

## <a name="supported-microsoft-office-applications"></a>Applicazioni di Microsoft Office supportate
Le applicazioni di Microsoft Office seguenti sono supportate nelle distribuzioni locali e cloud di Finance and Operations:

-   Per eseguire i componenti aggiuntivi di Microsoft Excel e Word, è necessario che sia installato Microsoft Office 2016 per Windows o Mac. Per ulteriori informazioni sui requisiti di versione, vedere [Risoluzione dei problemi di integrazione di Office](../../dev-itpro/office-integration/office-integration-troubleshooting.md).
-   Per visualizzare i documenti generati dalla funzionalità Esporta in Excel o Esporta in Word, è necessario che sia installato Microsoft Office 2007 o versioni successive.

## <a name="retail-modern-pos-requirements"></a>Requisiti per Retail Modern POS

> [!NOTE]
> Se Retail Modern POS utilizza un database offline, il computer deve soddisfare tutte i requisiti di sistema per Microsoft SQL Server. Un database offline di Retail Modern POS è compatibile con Microsoft SQL Server 2012 con Service Pack 3 o versione successiva, Microsoft SQL Server 2014 con Service Pack 2 o versione successiva e Microsoft SQL Server 2016. Si consiglia di utilizzare sempre l'ultima versione disponibile e di installare tutti i Service Pack più recenti.

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

-   Il connettore per Microsoft Dynamics AX dispone di due programmi di installazione distinti, uno per Async Server Connector service e un altro per Real-time service for Dynamics AX 2012 R3.
-   Entrambi i componenti sono applicazioni a 32 bit, ma vengono eseguiti sia su architetture x86 che x64.
-   Entrambi i componenti sono supportati nei sistemi operativi seguenti:

    -   Windows 7 edizioni Professional, Enterprise e Ultimate
    -   Windows 8.1 Update 1 edizioni Professional, Enterprise ed Embedded
    -   Windows 10 edizioni Pro, Enterprise ed Enterprise LTSB
    -   Microsoft Windows Server 2012 R2 e Microsoft Windows Server 2016

### <a name="minimum-system-requirements"></a>Requisiti minimi di sistema
-   2 GB di RAM (4 GB di RAM consigliati)
-   CPU con velocità di picco da 1,6 GHz per core (minimo due core).
-   Almeno 10 GB di spazio libero (il database del canale può richiedere una quantità di spazio notevole).

## <a name="requirements-for-development-on-local-vms"></a>Requisiti per sviluppo su VM locali
Per ulteriori informazioni sui requisiti per lo sviluppo su macchine virtuali locali (VM), vedere [VM in esecuzione presso la sede](../../dev-itpro/dev-tools/access-instances.md).


## <a name="see-also"></a>Vedere anche

[Ottenere una copia di valutazione di Dynamics 365 for Finance and Operations, Enterprise edition](../../dev-itpro/dev-tools/get-evaluation-copy.md)

