---
title: Gestione turni e cassetto della cassa
description: In questo argomento viene descritto come impostare e utilizzare i turni in Commerce POS (POS).
author: jblucher
manager: AnnBe
ms.date: 05/10/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailHardwareProfile, RetailTerminalTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 105011
ms.assetid: 49a0fcc9-d4db-45ad-8c4b-213ccaced82b
ms.search.region: global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 32b7be42509a2c857f1357eb64a6b488f9cd2269
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4413530"
---
# <a name="shift-and-cash-drawer-management"></a>Gestione turni e cassetto della cassa

[!include [banner](includes/banner.md)]

In questo argomento viene descritto come impostare e utilizzare i turni in Commerce POS (POS).

In Dynamics 365 Commerce, il termine *turno* descrive la raccolta di dati e attività transazionali di POS tra due unità temporali. Per ogni turno, la somma di denaro programmata è comparata con l'importo che è stato conteggiato e dichiarato.

In genere, i turni sono aperti all'inizio della giornata lavorativa. A questo punto, un utente indica l'importo iniziale del cassetto della cassa. Le transazioni di vendita vengono eseguite durante la giornata. Infine, al termine della giornata, il cassetto viene contato e gli importi di chiusura vengono dichiarati. Il turno verrà chiuso e un report Z viene generato. Il report Z indica se esistono importi eccedentari o mancanti.

## <a name="typical-shift-scenarios"></a>Scenari dei turni tipici

In Commerce sono disponibili varie opzioni di configurazione e operazioni del POS per supportare un'ampia gamma di processi aziendali di fine giornata per il POS. In questa sezione vengono descritti alcuni scenari comuni di turno.

### <a name="fixed-till"></a>Cassetto fisso

Tradizionalmente, questo scenario è stato utilizzato con maggiore frequenza. Viene ancora utilizzato estesamente. In un turno a "cassetto fisso" il turno e il cassetto sono associati a un registratore di cassa specifico. Non sono spostati da un registratore di cassa a un altro. Un turno a "cassetto fisso" può essere utilizzato da un singolo utente o condiviso tra più utenti. I turni a "cassetto fisso" non richiedono alcuna configurazione speciale.

### <a name="floating-till"></a>Cassetto con postazione variabile

In un turno a "cassetto con postazione variabile", il turno e il cassetto cassa possono essere spostati da un registratore di cassa all'altro. Anche se un registratore di cassa può avere un solo turno attivo per cassetto, i turni possono essere sospesi e poi ripresi in un secondo momento o su un altro registratore di cassa.

Ad esempio, un negozio ha due registratori di cassa. Ogni registratore viene aperto all'inizio del giorno in cui il cassiere apre un nuovo turno e fornisce l'importo di partenza. Quando un cassiere è pronto a prendersi una pausa, sospende il suo turno e rimuove la cassa dal cassetto portavalori. Il registratore quindi diventa disponibile per altri cassieri. Un altro cassiere può accedere e aprire il proprio turno sul registratore. Una volta terminata la prima pausa, il cassiere può riprendere il suo turno quando uno degli altri registri è disponibile. I turni a "cassetto con postazione variabile" non richiedono alcuna configurazione o autorizzazione speciale.

### <a name="single-user"></a>Singolo utente

Molti rivenditori preferiscono consentire un solo utente per turno, per contribuire a garantire il massimo livello di responsabilità per il contante nel cassetto portavalori. Se un solo utente è autorizzato ad utilizzare la cassa associata ad un turno, tale utente può essere ritenuto l'unico responsabile di eventuali discrepanze. Se più di un utente utilizza un turno, è difficile determinare chi ha commesso un errore, o chi potrebbe tentare di rubare dalla cassa.

### <a name="multiple-users"></a>Più utenti

Alcuni rivenditori sono disposti a sacrificare il livello di responsabilità fornito dai turni di un singolo utente e a consentire a più di un utente per turno. Questo approccio è tipico quando gli utenti sono più numerosi dei registri disponibili e la necessità di flessibilità e velocità supera il potenziale di perdita. Tipico anche quando i gestori del negozio non hanno i loro turni, ma può, se necessario, utilizzare i turni di uno qualsiasi dei loro cassieri. Per accedere e utilizzare un turno aperto da un altro utente, un utente deve avere l'autorizzazione POS **Consenti accessi a più turni**.

### <a name="shared-shift"></a>Turno condiviso

La configurazione "turno condiviso" consente ai retailer di avere un unico passaggio tra più registri, cassetti di cassa e utenti. Un turno condiviso ha un unico importo di partenza e un unico importo di chiusura che sono riassunti in tutti i cassetti di cassa. I turni condivisi sono più comuni quando vengono utilizzati dispositivi mobili. In questo scenario, un cassetto di cassa separato non è riservato per ogni registro. Tutti i registri possono invece condividere un cassetto per banconote.

Per utilizzare i turni condivisi in un negozio, il cassetto denaro deve essere configurato come "cassetto turno condiviso" su **Retail e Commerce \> Impostazione canale \> Impostazioni POS \> Profili POS \> Profili hardware \>Cassetto**. Inoltre, gli utenti devono avere una o entrambe le autorizzazioni di turno condivise (Consenti gestione turno condiviso e Consenti utilizzo turno condiviso).

> [!NOTE]
> Un solo turno condiviso può essere aperto contemporaneamente in ogni punto vendita. I turni condivisi e autonomi possono essere utilizzati nello stesso punto vendita.

## <a name="shift-and-drawer-operations"></a>Operazioni di turno e di cassetto

È possibile eseguire varie operazioni per cambiare lo stato di un turno o per aumentare o ridurre la somma di denaro in cassa. La sezione seguente descrive queste operazioni per turni per Modern POS e Cloud POS.

### <a name="open-shift"></a>Turno aperto

POS richiede che un utente abbia un turno aperto attivo per eseguire qualsiasi operazione che provocherebbe una transazione finanziaria ad esempio una vendita, un reso o un ordine cliente.

Quando un utente accede al POS, il sistema prima verifica se un turno attivo è disponibile per quell'utente sul registro corrente. Se non è disponibile un turno attivo, l'utente può aprire un nuovo turno, riprendere un turno esistente o eseguire l'accesso in modalità "non cassetto", a seconda della configurazione del sistema e dei permessi dell'utente.

### <a name="declare-start-amount"></a>Dichiara importo iniziale

Questa operazione è spesso la prima operazione eseguita con un turno appena aperto. Per questa operazione, gli utenti specificano l'importo di cassa iniziale nella cassa per il turno. Questa operazione è importante perché il calcolo dell'eccesso/debolezza che si verifica alla chiusura di un turno considera l'importo di partenza.

### <a name="float-entry"></a>Transazione fondo di cassa

Le *voci fondo di cassa* sono transazioni non di vendita che vengono eseguite in un turno attivo e aumentano l'importo della liquidità in cassa. Un esempio tipico di immissione fondo di cassa consiste nell'immettere importi aggiuntivi nella cassa quando il livello è basso.

### <a name="tender-removal"></a>Rimozione metodo di pagamento

Le *rimozioni metodo di pagamento* sono transazioni non di vendita che vengono eseguite in un turno attivo per ridurre l'importo della liquidità in cassa. Ciò è più utilizzato insieme a un'immissione fondo di cassa per un turno differente. Ad esempio, il Registro 1 è scarso di liquidità, pertanto l'utente del Registro 2 esegue una rimozione del metodo di pagamento per ridurre l'importo in cassa. L'utente sul registratore 1 poi fa una voce di fondo cassa per aumentare l'importo nel suo cassetto di cassa.

### <a name="suspend-shift"></a>Sospendi turno

Gli utenti possono sospendere il relativo turno attivo per mantenere disponibile il registro corrente per un altro utente o per spostare il turno in un registro differente (questo scenario è spesso denominato "cassetto con postazione variabile").

La sospensione del turno impedisce qualsiasi nuova transazione o modifica al turno finché a che non viene ripreso.

### <a name="resume-shift"></a>Riprendi il turno

Questa operazione consente a un utente di riprendere un turno sospeso in precedenza in un registro che non ha un turno attivo.

### <a name="tender-declaration"></a>Riepilogo incassi

Questa operazione viene eseguita per specificare l'importo totale del denaro attualmente nel cassetto. Gli utenti eseguono questa operazione il più delle volte prima di chiudere un turno. L'importo specificato viene confrontato con l'importo previsto per lo spostamento per calcolare l'importo dello scoperto/debito.

### <a name="safe-drop"></a>Deposito in cassaforte

I depositi in cassaforte possono essere effettuati su un turno attivo in qualsiasi momento. Questa operazione rimuove denaro dalla cassa, in modo da poter essere trasferito in un luogo più sicuro ad esempio una cassaforte nella stanza sul retro. L'importo totale registrato per depositi in cassaforte è ancora incluso nei totali relativi ai turni, ma non deve essere conteggiato nel riepilogo incassi.

### <a name="bank-drop"></a>Deposito bancario

Come i depositi in cassaforte, anche i depositi bancari vengono eseguiti su turni attivi. Questa operazione rimuove denaro dal turno per preparare il deposito bancario.

### <a name="blind-close-shift"></a>Chiusura forzata turno

I *turni con chiusura forzata* non sono più attivi ma non sono stati completamente bloccati. A differenza dei turni sospesi, i turni con chiusura forzata chiusi non possono essere riattivati. Tuttavia, operazioni quali la dichiarazione dell'importo di partenza e la dichiarazione d'offerta possono essere effettuate successivamente o a partire da un altro registro.

I turni con chiusura forzata vengono spesso utilizzati per liberare un registro per un nuovo utente o un nuovo turno, senza dover prima effettuare il conteggio, riconciliare e chiudere il turno.

### <a name="close-shift"></a>Chiusura turno

Questa operazione calcola i totali relativi ai turni, gli importi in eccesso/in difetto e quindi finalizza un turno attivo o con chiusura forzata. A seconda delle autorizzazioni dell'utente, viene stampato anche un report Z per il turno. I turni chiusi non possono essere riattivati o modificati.

### <a name="print-x"></a>Stampa X

L'operazione genera e stampa un report X per il turno attivo corrente.

### <a name="reprint-z"></a>Ristampa Z

Questa operazione ristampa l'ultimo report Z generato dal sistema alla chiusura di un turno.

### <a name="manage-shifts"></a>Gestisci turni

Questa operazione consente agli utenti di visualizzare qualsiasi turno attivo, sospeso e con chiusura forzata per il punto vendita. A seconda delle autorizzazioni, gli utenti possono eseguire procedure di chiusura finali quali il riepilogo incassi e la chiusura dei turni per i turni con chiusura forzata. Questa operazione consentirà inoltre agli utenti di visualizzare ed eliminare i turni non validi nel raro evento che un turno sia in un cattivo stato dopo il passaggio tra la modalità offline e online. Questi turni non validi non contengono informazioni finanziarie o dati transazionali necessari per la riconciliazione.

## <a name="shift-and-drawer-permissions"></a>Gestione turni e cassetto della cassa

Le seguenti autorizzazioni POS influenzano ciò che un utente può e non può fare in vari scenari:

- **Consenti chiusura forzata**
- **Consenti stampa report X**
- **Consenti stampa report Z**
- **Consenti riepilogo incassi**
- **Consenti dichiarazione fondo di cassa**
- **Apri cassetto senza vendita**
- **Consenti accessi a più turni** – Questa autorizzazione consente all'utente di accedere e utilizzare un turno aperto da un altro utente. Gli utenti che non hanno questa autorizzazione possono accedere e utilizzare solo i turni che hanno aperto.
- **Consenti gestione turno condiviso** – Gli utenti devono avere questa autorizzazione per aprire o chiudere un turno condiviso.
- **Consenti uso turno condiviso** – Gli utenti devono avere questa autorizzazione per accedere a e usare un turno condiviso.

## <a name="back-office-end-of-day-considerations"></a>Considerazioni fine giornata di back office

Il modo in cui i turni e la riconciliazione dei cassetti di cassa sono utilizzati nei POS differisce dal modo in cui i dati sulle operazioni sono riassunti durante il calcolo del conto economico. È importante capire questa differenza. A seconda della configurazione e dei processi aziendali, i dati di turno nel POS (il report Z) e un conteggio calcolato nel back office possono dare risultati diversi. Questa differenza non significa necessariamente che i dati del turno o il conteggio calcolato non siano corretti o che ci sia un problema con i dati. Significa solo che i parametri forniti possono includere transazioni aggiuntive o meno, o che le transazioni sono state riassunte in modo diverso.

Anche se ogni rivenditore ha esigenze commerciali diverse, si consiglia di configurare il sistema nel modo seguente per evitare situazioni in cui si verificano differenze di questo tipo:

Passare a **Retail e Commerce \> Canali \> Punti vendita \> Tutti i punti vendita \> Rendiconto/chiusura** e per ogni punto vendita, l'impostazione sia il campo **Metodo rendiconto** nel campo **Metodo di chiusura** **Turno**.

Questa impostazione aiuta a garantire che i resoconti di back-office includano le stesse transazioni dei turni nel POS e che i dati siano riepilogati da tale turno.

Per ulteriori informazioni sui metodi di dichiarazione e di chiusura, vedere [Configurazioni dei punti vendita per il Retail](https://docs.microsoft.com/dynamics365/unified-operations/retail/tasks/store-configurations-retail-statements).
