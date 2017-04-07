---
title: Requisiti di sistema
description: Di seguito sono elencati i requisiti di sistema della versione corrente di Microsoft Dynamics 365 per le operazioni.
author: sericks007
manager: AnnBe
ms.date: 2017-04-04
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, Developer, IT Pro
ms.search.scope: Core
ms.custom: 55651
ms.assetid: e564d51d-42d3-47c5-b388-93b8219c692a
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-08-30
ms.dyn365.ops.version: Platform update 2
translationtype: Human Translation
ms.sourcegitcommit: c8c96dc9705688308dd4a5c720700ddc17657d75
ms.openlocfilehash: 9220c093d3f6d6700127c93651db4083be300311
ms.lasthandoff: 03/31/2017


---

# <a name="system-requirements"></a>Requisiti di sistema

Di seguito sono elencati i requisiti di sistema della versione corrente di Microsoft Dynamics 365 per le operazioni.

<a name="supported-web-browsers"></a>Web browser supportati
----------------------

Microsoft Dynamics 365 per l'applicazione Web delle operazioni è possibile eseguire nei seguenti browser Web che utilizzano sistemi operativi specificati:

-   Bordo Microsoft (il più tardi pubblicamente - versione se disponibili in Windows 10
-   Internet Explorer 11 in Windows 10, Windows 8.1 o Windows 7
-   Google Cromato (il più tardi pubblicamente - versione se disponibili in compressa di Windows 10, 8.1 di Windows, di Windows 8, 7 di Windows, o del Google Nexus 10
-   Apple Safari (il più tardi pubblicamente - versione) disponibile in Mac OS X 10.10 (Yosemite), 10.11 (EL Capitan) o 10.12 (sierra), ovvero iPad di Apple

Per trovare l'ultima versione rilasciata di ogni Web browser, andare al sito Web del produttore software. **Note:**

-   Per acquisire le immagini generate dal Registrazione attività e comprenderle nei documenti di Microsoft Word, è necessario avere estensione Cromato impostato. <!---For instructions about how to install the extension, see [Screenshot Extension setup](/dynamics365/operations/dev-itpro/user-interface/task-recorder).-->
-   L'editor flusso di lavoro viene attivato come applicazione ClickOnce. Solo il bordo e Internet Explorer Microsoft (su una versione supportata di Microsoft Windows) supporto le applicazioni ClickOnce. L'applicazione ClickOnce dell'editor flusso di lavoro richiede un sistema operativo compatibile a 64 bit.
-   In Progettazione report per i report finanziari viene avviato come applicazione ClickOnce. Richiede un sistema operativo compatibile a 64 bit. Se si utilizza Cromato, è necessario impostare un'estensione ClickOnce per scaricare il client di Progettazione report. Se si utilizza Cromato in incognito la modalità, verificare che la proroga ClickOnce anche attivata per incognito nella modalità.

### <a name="supported-web-browsers-for-retail-cloud-pos"></a>Web browser supportati per POS cloud vendita al dettaglio

In Retail POS verrà su cloud per Dynamics 365 per le operazioni è possibile eseguire nei seguenti browser Web che utilizzano sistemi operativi specificati:

-   Bordo Microsoft (il più tardi pubblicamente - versione se disponibili in Windows 10
-   Internet Explorer 11 in Windows 10, Windows 8.1 o Windows 7
-   Cromato (il più tardi pubblicamente - versione se disponibili in Windows 10, Windows 8.1, o su Windows 7

## <a name="network-requirements"></a>Requisiti di rete
-   Dynamics 365 per le operazioni è progettato per le reti alla latenza inferiore a 150 attesa di (ms). Si tratta della latenza da un client del browser al centro dati di Microsoft Azure tale host Dynamics 365 per le operazioni. Si consiglia di verificare la latenza di rete< all'> indirizzo http://www.azurespeed.com.
-   I requisiti di larghezza di banda di Dynamics 365 per le operazioni dipendono dal scenario. La maggior parte dei tipici scenari che richiedono una larghezza di banda di più di 50 eventi al secondo kbps (). Tuttavia, per scenari con una richiesta del carico utile, ad esempio le aree di lavoro o gli scenari che includono estesa personalizzazione, oltre a larghezza di banda è consigliata.

Dynamics 365 per le operazioni è in genere ricerca per Internet. Numero di round trip da un client del browser al centro azzurrato dati sia troppo esiguo e l'intero carico utile è compresso. ** Avvertendo: ** Non computi i requisiti di larghezza di banda ridotta da un'ubicazione del client moltiplicando il numero di utenti per i requisiti minimi di larghezza di banda. L'utilizzo di concorrente una posizione data è molto difficile calcolare. Per i clienti a cui sono interessati sui fabbisogni di larghezza di banda, utilizzare una versione di previsione di Dynamics 365 per le operazioni.

## <a name="net-framework-requirements"></a>requisiti di .NET Framework
Dynamics 365 per le operazioni richiede la versione 4.6.2 di .NET Framework per tutti clic- una modifica delle applicazioni, ad esempio l'agente di registrazione del documento. Per istruzioni di installazione, vedere [installato .NET Framework] (https://msdn.microsoft.com/en-us/library/5a4x27ek(v=vs.110).aspx).

## <a name="supported-microsoft-office-applications"></a>Applicazioni di supporto Microsoft Office
-   Per eseguire Microsoft Excel e per esprimere i componenti aggiuntivi, è necessario che Microsoft Office 2016 per Windows o Mac impostato. Per ulteriori informazioni sui requisiti di rilascio, vedere [] risoluzione di integrazione di Office (/dynamics365/operations/dev-itpro/office-integration/office-integration-troubleshooting).
-   Per visualizzare i documenti generati dall'esportazione in Excel o dall'esportazione per esprimere la funzionalità, è necessario che Microsoft Office 2007 o versione successiva eseguita.

## <a name="retail-modern-pos-requirements"></a>Requisiti moderni Retail POS
### <a name="supported-operating-systems"></a>Liquidare operativi supportati

-   In Retail POS moderno al dettaglio è un'applicazione a 32 bit, ma verrà eseguito le architetture su x86 che in x64.
-   In Retail POS moderno al dettaglio è supportato solo su Windows 10 uscite di assistenza a lungo termine con di impresa, e impresa della filiale (LTSB).

### <a name="minimum-system-requirements"></a>Requisiti di sistema minimi

-   La risoluzione di supporto minima è 1280 × 1024.
-   Il computer su cui il POS moderno al dettaglio viene eseguito deve soddisfare tali requisiti:
    -   Disporre di, al minimo, il processore dual-core che opera per non inferiore a 2 GHz (GHz).
    -   Disporre di, al minimo, 3 gigabyte di (GB) di RAM.
    -   Disporre di accesso a Internet.

## <a name="retail-hardware-station-requirements"></a>Requisiti di articoli al dettaglio della propria postazione hardware
### <a name="supported-operating-systems"></a>Liquidare operativi supportati

-   La propria postazione di articoli al dettaglio hardware è un'applicazione a 32 bit, ma verrà eseguito le architetture su x86 che in x64.
-   La propria postazione di articoli al dettaglio hardware è supportata sui sistemi operativi:
    -   Professionista di Windows 7, contenuti organizzazione e le uscite ** nota: ** Windows 7 è supportato solo se Internet Explorer 11 è impostato manualmente nel sistema.
    -   Professionista di servizi di Windows 8.1, 1 e uscite medie incluse
    -   Windows 10, uscite di impresa e impresa LTSB

### <a name="minimum-system-requirements"></a>Requisiti di sistema minimi

La macchina deve soddisfare tutte le richieste di sistema dell'installazione e all'utilizzo dei seguenti elementi:

-   Internet Information Services (IIS)
-   Hardware di terze parti

## <a name="retail-store-scale-unit-requirements"></a>Richieste di unità della scala punto vendita al dettaglio
### <a name="supported-operating-systems"></a>Liquidare operativi supportati

-   Unità di pesatura punto vendita al dettaglio è un'applicazione a 32 bit, ma verrà eseguito le architetture su x86 che in x64.
-   Unità di pesatura punto vendita al dettaglio è supportata sui sistemi operativi:
    -   Professionista di Windows 7, contenuti organizzazione e le uscite
    -   Professionista di servizi di Windows 8.1, 1 e uscite medie incluse
    -   Windows 10, uscite di impresa e impresa LTSB

### <a name="minimum-system-requirements"></a>Requisiti di sistema minimi

-   GB di RAM
-   Processore 1.6 GHz di picco di velocità di CPU di tempo (i due centri al minimo).
-   Almeno 10 GB di spazio libero (il database del canale può richiedere molto elevato di spazio).

### <a name="recommended-system-requirements"></a>Requisiti di sistema consigliati

-   6Gb Di RAM
-   Processore 2.4 GHz o equivalenti (i7) di picco di velocità di CPU di tempo (pezzi disponibili centri utilizzare).
-   Almeno 10 GB di spazio libero (il database del canale può richiedere molto elevato di spazio).

## <a name="requirements-for-development-on-local-vms"></a>Requisiti di sviluppo locale in VM
Per ulteriori informazioni sui requisiti di sviluppo sulle macchine virtuali locali (VMs), vedere in locali [] correnti in VM (/dynamics365/operations/dev-itpro/dev-tools/access-instances #vm-that-is-running-in-premises).

<a name="see-also"></a>Vedere anche
--------

[Ottenere una copia di valutazione Dynamics 365 per le operazioni] (/dynamics365/operations/dev-itpro/dev-tools/get-evaluation-copy)


