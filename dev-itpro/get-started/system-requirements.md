---
title: Requisiti di sistema
description: In questo argomento vengono elencati i requisiti di sistema per la versione corrente di Microsoft Dynamics 365 for Finance and Operations, Enterprise edition.
author: sericks007
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, Developer, IT Pro
ms.search.scope: Core
ms.custom: 55651
ms.assetid: e564d51d-42d3-47c5-b388-93b8219c692a
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-08-30
ms.dyn365.ops.version: Platform update 2
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: 724ee7ec29f8a9c4e8cc0b244193cd6c83c37f03
ms.contentlocale: it-it
ms.lasthandoff: 06/13/2017


---

# <a name="system-requirements"></a>Requisiti di sistema

[!include[banner](../includes/banner.md)]


In questo argomento vengono elencati i requisiti di sistema per la versione corrente di Microsoft Dynamics 365 for Finance and Operations, Enterprise edition.

<a name="supported-web-browsers"></a>Web browser supportati
----------------------

L'applicazione Web può essere eseguita in uno dei seguenti Web browser eseguiti sui sistemi operativi specificati:

-   Microsoft Edge (ultima versione pubblicamente disponibile) su Windows 10
-   Internet Explorer 11 in Windows 10, Windows 8.1 o Windows 7
-   Google Chrome (ultima versione pubblicamente disponibile) su Windows 10, Windows 8.1, Windows 8, Windows 7 o tablet Google Nexus 10
-   Apple Safari (ultima versione pubblicamente disponibile) su Mac OS X 10.10 (Yosemite), 10.11 (El Capitan), 10.12 (Sierra) o Apple iPad

Per trovare l'ultima versione rilasciata di ogni Web browser, andare al sito Web del produttore software. 

**Note:**

-   Per acquisire le immagini screenshot con Registrazione attività e includerle nei documenti di Microsoft Word generati, è necessario installare un'estensione Chrome pre-release. <!---For instructions about how to install the extension, see [Screenshot Extension setup](/dynamics365/unified-operations/dev-itpro/user-interface/task-recorder).-->
-   L'editor flusso di lavoro viene avviato come un'applicazione ClickOnce. Solo Microsoft Edge e Internet Explorer (su una versione supportata di Microsoft Windows) supportano le applicazioni ClickOnce. L'applicazione ClickOnce dell'editor flusso di lavoro richiede un sistema operativo compatibile a 64 bit.
-   La funzionalità Progettazione report per i report finanziari viene avviata come un'applicazione ClickOnce. Richiede un sistema operativo compatibile a 64 bit. Se si utilizza Chrome, è necessario installare un'estensione ClickOnce per scaricare il client di progettazione report. Se si utilizza Chrome con la modalità in incognito, assicurarsi che l'estensione ClickOnce sia abilitata anche per tale modalità.
-   Per visualizzare l'anteprima dei file PDF, si consiglia di utilizzare browser come Microsoft Edge (versione pubblica più recente) su Windows 10 o Google Chrome (versione pubblica più recente) su Windows 10, Windows 8.1, Windows 8, Windows 7 o tablet Google Nexus 10.


### <a name="supported-web-browsers-for-retail-cloud-pos"></a>Web browser supportati per POS cloud vendita al dettaglio

Retail Cloud POS può essere eseguito in uno dei seguenti Web browser eseguiti sui sistemi operativi specificati:

-   Microsoft Edge (ultima versione pubblicamente disponibile) su Windows 10
-   Internet Explorer 11 in Windows 10, Windows 8.1 o Windows 7
-   Chrome (ultima versione pubblicamente disponibile) su Windows 10, Windows 8.1 o Windows 7

## <a name="network-requirements"></a>Requisiti di rete
-   Dynamics 365 for Finance and Operations, Enterprise edition è progettato per le reti con latenza di 250-300 millisecondi (ms) o meno. Questa è la latenza da un client browser al data center di Microsoft Azure che ospita Finance and Operations. Si consiglia di verificare la latenza di rete all'indirizzo <http://www.azurespeed.com>.
-   I requisiti di larghezza di banda dipendono dallo scenario in uso. La maggior parte degli scenari tipici richiede una larghezza di banda superiore a 50 kilobyte al secondo (Kbps). Tuttavia, per scenari con requisiti di carico utile elevati, ad esempio aree di lavoro o scenari che implicano personalizzazioni estese, è consigliabile disporre di maggiore larghezza di banda.

In genere, Finance and Operations è ottimizzato per Internet. Il numero di round trip da un client browser al data center di Azure è esiguo e l'intero carico utile è compresso. 

**Avviso:** non calcolare i requisiti di larghezza di banda da un'ubicazione del client moltiplicando il numero di utenti per i requisiti minimi di larghezza di banda. L'utilizzo simultaneo di una determinata ubicazione è difficile da calcolare. Per i clienti con problemi relativi ai requisiti di larghezza di banda, utilizzare una versione di anteprima di Finance and Operations.

## <a name="net-framework-requirements"></a>Requisiti per .NET Framework
.NET Framework versione 4.6.2 è obbligatorio per tutte le applicazioni ClickOnce, ad esempio l'agente di distribuzione documenti. Per istruzioni relative all'installazione, vedere [Installazione di .NET Framework](https://msdn.microsoft.com/en-us/library/5a4x27ek(v=vs.110).aspx).

## <a name="supported-microsoft-office-applications"></a>Applicazioni di Microsoft Office supportate
-   Per eseguire i componenti aggiuntivi di Microsoft Excel e Word, è necessario che sia installato Microsoft Office 2016 per Windows o Mac. Per ulteriori informazioni sui requisiti di versione, vedere [Risoluzione dei problemi di integrazione di Office](/dynamics365/unified-operations/dev-itpro/office-integration/office-integration-troubleshooting).
-   Per visualizzare i documenti generati dalla funzionalità Esporta in Excel o Esporta in Word, è necessario che sia installato Microsoft Office 2007 o versioni successive.

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
    -   Windows 7 edizioni Professional, Enterprise e Ultimate **Nota:** Windows 7 è supportato solo se Internet Explorer 11 viene installato manualmente nel sistema.
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

<a name="see-also"></a>Vedere anche
--------

[Ottenere una copia di valutazione di Dynamics 365 for Finance and Operations, Enterprise edition](/dynamics365/unified-operations/dev-itpro/dev-tools/get-evaluation-copy)





