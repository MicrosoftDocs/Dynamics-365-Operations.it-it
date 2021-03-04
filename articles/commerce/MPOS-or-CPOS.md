---
title: Scegliere tra Modern POS (MPOS) e Cloud POS
description: In questo argomento vengono illustrate le differenze chiave tra Modern POS e Cloud POS. Sono inoltre descritti i diversi fattori che i rivenditori che implementano Dynamics 365 Commerce devono considerare per operare la scelta più adatta alle proprie esigenze.
author: jblucher
manager: AnnBe
ms.date: 10/13/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2017-10-12
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 508fda28d8f815f030e7b163709393f70904a5fd
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4413364"
---
# <a name="choose-between-modern-pos-mpos-and-cloud-pos"></a>Scegliere tra Modern POS (MPOS) e Cloud POS

[!include [banner](includes/banner.md)]

In questo argomento vengono fornite agli implementatori contesto, suggerimenti e indicazioni supplementari per i fattori da considerare durante la distribuzione di Dynamics 365 Commerce. Esaminando e seguendo queste indicazioni durante il processo di distribuzione, gli implementatori possono evitare eventuali problemi che potrebbero influire sulla soddisfazione dell'utente o sulle prestazioni.

## <a name="insights"></a>Informazioni dettagliate

Commerce offre un'ampia gamma di opzioni di distribuzione e topologia. Di conseguenza, i rivenditori possono scegliere i componenti e la configurazione che meglio si adattano ai propri requisiti aziendali e tecnologici. Un aspetto di implementazione che richiede un'attenta considerazione è la scelta della piattaforma e del fattore di forma per il componente POS.

### <a name="pos-platform-and-form-factor-considerations"></a>Considerazioni sulla piattaforma e sul fattore di forma per il POS

Commerce supporta le opzioni POS seguenti:

- Modern POS (MPOS) per Microsoft Windows
- MPOS per Microsoft Windows Phone
- MPOS per iPad di Apple o tablet Android di Google
- Cloud POS (CPOS), che supporta i browser Microsoft Edge, Internet Explorer e Google Chrome

In tutti i casi, il POS (MPOS e CPOS) condivide lo stesso codice applicazione di base. Questo punto è importante per i motivi seguenti:

- L'interfaccia utente (UI) è coerente, indipendentemente dalla piattaforma o dal fattore di forma.
- La maggior parte delle capacità funzionali è uguale, indipendentemente dalla piattaforma o dal fattore di forma. Tuttavia, esistono delle differenze importanti. Le differenze sono descritte in questo argomento.
- In un punto vendita specifico, le variazioni POS possono essere combinate e possono essere eseguite simultaneamente. Ad esempio, per i registri principali, un rivenditore può utilizzare MPOS in computer che eseguono Windows. Tuttavia, il rivenditore può completare questi registri con terminali basati su browser o dispositivi mobili.
- Le personalizzazioni e le estensioni possono essere facilmente essere utilizzate su più piattaforme e più fattori di forma. Poiché il codice applicazione di base è condiviso, le personalizzazioni possono essere implementate una volta anziché più volte.

### <a name="mpos-vs-cpos"></a>MPOS rispetto a CPOS

Sebbene MPOS e CPOS siano in gran parte uguali, esistono delle differenze importanti con cui sarà necessario acquisire familiarità.

#### <a name="mpos"></a>MPOS

MPOS in un dispositivo Windows, iOS o Android è un'applicazione in pacchetto che viene installato e supportato nel dispositivo.

- **Windows** - L'applicazione MPOS per Windows contiene tutto il codice applicazione e il Commerce Runtime (CRT) incorporato. 
- **iOS/Android** - In queste piattaforme, l'applicazione agisce da host per il codice applicazione CPOS. In altre parole, il codice applicazione deriva dal server CPOS in Microsoft Azure o da Commerce Scale Unit. Per ulteriori informazioni, vedere [Panoramica di Commerce Scale Unit](https://docs.microsoft.com/dynamics365/unified-operations/retail/dev-itpro/retail-store-system-begin).

#### <a name="cpos"></a>CPOS

Poiché CPOS viene eseguito in un browser, l'applicazione non viene installata nel dispositivo. Il browser accede invece al codice applicazione dal server CPOS. Di conseguenza, CPOS non può accedere direttamente all'hardware POS o lavorare in uno stato offline.

### <a name="store-deployment-considerations"></a>Considerazioni sulla distribuzione in punti vendita

Oltre alla piattaforma e al fattore di forma, i rivenditori devono scegliere anche un'opzione di distribuzione presso il punto vendita. Nella seguente tabella sono descritte le configurazioni disponibili per ogni opzione POS.

| Applicazione POS         | Commerce Scale Unit | Disponibile offline |
|-------------------------|---------------|-------------------|
| MPOS per Windows        | Cloud o RSSU | Sì               |
| MPOS per iOS o Android | Cloud o RSSU | Nessuno                |
| POS cloud               | Cloud o RSSU | Nessuno                |

#### <a name="commerce-scale-unit"></a>Commerce Scale Unit

Commerce Scale Unit è un componente che ospita CRT. Il CRT contiene tutta la logica di business utilizzata dal POS e offre accesso al database di canale. Quando sono online, tutti i client POS nel punto vendita utilizzano Commerce Scale Unit. Commerce Scale Unit può essere distribuito nel cloud o nel punto vendita.

#### <a name="offline-mode"></a>Modalità offline

MPOS per Windows supporta la modalità offline. In questa modalità, il POS può continuare a elaborare le vendite anche se è disconnesso da Commerce Scale Unit. Può quindi essere sincronizzato con il database del canale quando viene ripristinata la connessione. MPOS utilizza la propria istanza integrata del CRT e al contempo utilizza la propria origine dati locale (database SQL Server offline). Per ulteriori informazioni sul funzionamento offline, vedere [Funzionamento offline di POS](https://docs.microsoft.com/dynamics365/unified-operations/retail/pos-offline-functionality) (in lingua inglese).

### <a name="pos-peripheralhardware-considerations"></a>Considerazioni sull'unità periferica/hardware POS

I rivenditori devono inoltre considerare in che modo il POS accederà ai dispositivi e alle unità periferiche, ad esempio le stampanti, i cassetti della cassa e i terminali di pagamento. Solo MPOS per Windows supporta la comunicazione diretta con tali dispositivi. MPOS per Windows Phone, iOS o Android e Cloud POS richiedono l'utilizzo di una stazione hardware per accedere a questi dispositivi. Le stazioni hardware possono essere dedicate a un registratore di cassa POS o essere suddivise tra i registratori di cassa in un punto vendita. Per ulteriori informazioni su come installare le stazioni hardware, vedere [Configurare e installare una stazione hardware per la vendita al dettaglio](https://docs.microsoft.com/dynamics365/unified-operations/retail/retail-hardware-station-configuration-installation).

## <a name="implementation-considerations"></a>Considerazioni sull'implementazione

Considerare le seguenti informazioni quando si pianifica l'implementazione di POS nei propri punti vendita:

- **Requisiti funzionali** - I processi e le funzionalità aziendali di base sono gli stessi, indipendentemente dalla piattaforma, il fattore di forma o la topologia della distribuzione. Di conseguenza, la maggior parte dei rivenditori non deve considerare i requisiti funzionali nella pianificazione dell'implementazione.
- **Connettività** – La disponibilità della rete (Wide Area Network \[WAN\] e rete locale \[LAN\]) è il principale fattore che richiede un'attenta considerazione. Tutti i vantaggi che una soluzione ospitata nel cloud e a emissione zero porta in termini di costi e di semplicità vengono persi se il sistema non è disponibile per i processi di rilevanza per l'azienda.

    A meno che la connettività per uno specifico dispositivo non sia molto credibile e resiliente o a meno che una certa quantità di inattività non sia accettabile per il rivenditore, è consigliabile utilizzare una delle opzioni seguenti:

    - Utilizzare MPOS in Windows e attivare la modalità offline.
    - Distribuire Commerce Scale Unit locale.

    Le due opzioni non si escludono a vicenda. Per la topologia più attendibile, i rivenditori possono distribuire una RSSU locale per ridurre la dipendenza dalla connettività Internet o la disponibilità di Azure e possono inoltre distribuire registratori POS dove è attivata la modalità offline se è presente un problema con il server locale o la rete.

- **Dispositivi hardware e periferiche** - Un aspetto importante di un sistema Retail POS è la capacità di utilizzare le periferiche POS, ad esempio le stampanti, i cassetti di cassa e i terminali di pagamento. Sebbene tutte le opzioni disponibili di POS possano utilizzare le periferiche, solo MPOS per Windows le supporta direttamente. Per tutte le altre applicazioni, è necessario munirsi di una o più stazioni hardware. Sebbene aggiunga flessibilità, questo approccio richiede l'aggiunta, la configurazione e il supporto di componenti aggiuntivi.
- **Requisiti di sistema** - I requisiti di sistema dell'applicazione POS variano. Assicurarsi di controllare le informazioni più recenti prima di scegliere. Ad esempio, poiché CPOS viene eseguito in un browser, supporta una gamma più ampia di sistemi operativi. Per ulteriori informazioni sui requisiti di sistema, vedere [Requisiti di sistema per le distribuzioni cloud](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/system-requirements).
- **Distribuzione e assistenza** - La complessità di requisiti di assistenza e di distribuzione può variare, a seconda delle scelte di distribuzione e di applicazioni. Ad esempio, per una distribuzione CPOS ospitata nel cloud, non è necessario installare e aggiornare in ogni dispositivo. Di conseguenza, tale approccio semplifica notevolmente la complessità e riduce i costi. Tuttavia, se si distribuisce MPOS in ogni registratore e si attiva la modalità offline e si distribuiscono anche stazioni hardware condivise, si aumenta enormemente il numero di endpoint che devono essere gestiti.


[!INCLUDE[footer-include](../includes/footer-banner.md)]