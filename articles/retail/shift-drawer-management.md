---
title: Gestione turni e cassetto della cassa
description: "In questo articolo viene spiegato come impostare e utilizzare i due tipi di turni POS al dettaglio: condiviso e autonomo. I turni condivisi possono essere utilizzati da più utenti in più posizioni, mentre i turni autonomi possono essere utilizzati da un solo lavoratore alla volta."
author: rubencdelgado
manager: AnnBe
ms.date: 02/15/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
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
ms.translationtype: HT
ms.sourcegitcommit: 8a24f8adc4f7886a1f942d83f7a4eb12e7034fcd
ms.openlocfilehash: c1483d3240d266845cea7789b70c038cb98fdfcc
ms.contentlocale: it-it
ms.lasthandoff: 03/22/2018

---

# <a name="shift-and-cash-drawer-management"></a>Gestione turni e cassetto della cassa

[!include[banner](includes/banner.md)]


In questo articolo viene spiegato come impostare e utilizzare i due tipi di turni POS al dettaglio: condiviso e autonomo. I turni condivisi possono essere utilizzati da più utenti in più posizioni, mentre i turni autonomi possono essere utilizzati da un solo lavoratore alla volta.

Esistono due tipi di turni POS al dettaglio: autonomo e condiviso. I turni autonomi sono utilizzabili da un solo lavoratore alla volta. I turni condivisi possono essere utilizzati da più utenti in più posizioni. Pertanto, creano in modo efficace un turno singolo per più lavoratori in un punto vendita.

## <a name="standalone-shifts"></a>Turni autonomi
I turni autonomi vengono utilizzati in uno scenario POS fisso tradizionale, in cui la cassa è riconciliata in modo indipendente per ogni registratore di cassa POS. Ad esempio, in un negozio di alimentari, in genere esistono più registratori di cassa POS fissi e un cassiere viene assegnato a ciascun registratore. In questo caso, ciascun registratore probabilmente utilizza un turno autonomo e il cassiere è responsabile per il cassetto o la cassa fisica di quel registratore di cassa. Un turno autonomo include tutte le attività su tale registratore di cassa durante il turno di lavoro del cassiere. Le attività possono includere l'importo di apertura che viene depositato nel cassetto, tutte le rimozioni e le aggiunte di contanti tramite operazioni quali depositi bancari e immissioni fondo di cassa, e il riepilogo degli incassi alla fine del turno.

### <a name="set-up-a-stand-alone-shift"></a>Impostare un turno autonomo

Un turno autonomo viene definito a livello di cassetto della cassa. Questa procedura illustra come impostare un turno autonomo su un registratore di cassa POS.

1.  Fare clic su **Vendita al dettaglio** &gt; **Impostazione canale** &gt; **Impostazioni POS** &gt; **Profili POS** &gt; **Profili hardware**.
2.  Selezionare il profilo dhardware a utilizzare per il turno autonomo.
3.  Nella scheda dettaglio **Cassetto**, verificare che l'opzione **Cassetto turno condiviso** sia impostata su **No**.
4.  Fare clic su **Salva**.
5.  Fare clic su **Vendita al dettaglio** &gt; **Impostazione canale** &gt; **Impostazioni POS** &gt; **Registratori di cassa**.
6.  Selezionare il registratore di cassa che richiede un turno autonomo e quindi fare clic su **Modifica**.
7.  Nel campoa **Profilo hardware** selezionare il profilo hardware selezionato nel passaggio 2.
8.  Fare clic su **Salva**.
9.  Fare clic su **Vendita al dettaglio** &gt; **IT vendita al dettaglio** &gt; **Programmazione della distribuzione**.
10. Selezionare la programmazione di distribuzione **1090** e quindi fare clic su **Esegui adesso** per sincronizzare le modifiche nel POS.

### <a name="use-a-stand-alone-shift"></a>Utilizzare turno autonomo

1.  Accedere al POS.
2.  Se nessun turno è aperto, selezionare **Apri un nuovo turno**.
3.  Vai all'operazione **Dichiara importo iniziale** e specificare l'importo di contanti aggiunto al cassetto per iniziare la giornata di lavoro.
4.  Eseguire alcune transazioni.
5.  Alla fine del giorno, selezionare **Dichiara metodo di pagamento** per dichiarare l'importo di contanti che rimane nel cassetto della cassa.
6.  Immettere l'importo di contanti quindi fare clic su **Salva** per salvare il riepilogo incassi.
7.  Selezionare **Chiudi turno** per chiudere il turno.

**Nota:** sono disponibili altre operazioni durante il turno, a seconda dei processi aziendali implementati. Le operazioni **Deposito in cassaforte**, **Deposito bancario**, e **Rimozione metodo di pagamento** possono essere utilizzate per rimuovere denaro dal cassetto durante il giorno o prima della chiusura del turno. Se un cassetto non ha contanti sufficienti, l'operazione **Immissione fondo cassa** può essere utilizzata per aggiungere contanti alla cassa.

## <a name="shared-shifts"></a>Turni condivisi
Un turno condiviso viene utilizzato in un ambiente in cui più cassieri condividono un cassetto o un insieme di cassetti di registratori di cassa nel corso della giornata di lavoro. In genere, un turno condiviso viene utilizzato in ambienti di POS mobili. In un ambiente mobile, ogni cassiere non è assegnato né responsabile di un singolo cassetto della cassa. Invece tutti i cassieri devono poter gestire una vendita e aggiungere contanti a qualsiasi cassetto della cassa sia più vicino. In questo scenario, i cassetti della cassa che vengono condivisi tra i cassieri sono inclusi in un turno condiviso. Tutti i cassetti della cassa in un turno condiviso sono inclusi nello stesso turno per le attività correlate alla gestione di cassa per il turno. Pertanto, l'importo iniziale del turno deve includere la somma di tutti i contanti in tutti i cassetti inclusi nel turno condiviso. Analogamente, il riepilogo incassi sarà la somma di tutti i contanti in tutti i cassetti inclusi nel turno condiviso. **Nota**: un solo turno condiviso può essere aperto contemporaneamente in ogni punto vendita. I turni condivisi e autonomi possono essere utilizzati nello stesso punto vendita.

### <a name="set-up-a-shared-shift"></a>Impostare un turno condiviso

1.  Fare clic su **Vendita al dettaglio** &gt; **Impostazione canale** &gt; **Impostazioni POS** &gt; **Profili POS** &gt; **Profili hardware**.
2.  Selezionare il profilo dhardware da utilizzare per il turno condiviso.
3.  Nella scheda dettaglio **Cassetto**, impostare l'opzione **Cassetto turno condiviso** su **Sì**.
4.  Fare clic su **Salva**.
5.  Fare clic su **Vendita al dettaglio** &gt; **Impostazione canale** &gt; **Impostazioni POS** &gt; **Registratori di cassa**.
6.  Selezionare il registratore di cassa che richiede un turno condiviso e quindi fare clic su **Modifica**.
7.  Nel campoa **Profilo hardware** selezionare il profilo hardware selezionato nel passaggio 2.
8.  Fare clic su **Salva**.
9.  Fare clic su **Vendita al dettaglio** &gt; **IT vendita al dettaglio** &gt; **Programmazione della distribuzione**.
10. Selezionare la programmazione di distribuzione **1090** e quindi fare clic su **Esegui adesso** per sincronizzare le modifiche nel POS.

### <a name="use-a-shared-shift"></a>Utilizzare un turno condiviso

1.  Accedere al POS.
2.  Se il POS non è ancora connesso a una stazione hardware, selezionare **Operazione non relativa a cassetto**, quindi selezionare l'operazione **Seleziona stazione hardware** per attivare una stazione hardware per il turno condiviso. Questo passaggio è necessario solo la prima volta che viene aggiunto un registratore di cassa in un ambiente di turno condiviso.
3.  Uscire dal POS, e quindi accedere di nuovo.
4.  Selezionare **Crea un nuovo turno**.
5.  Selezionare **Dichiara importo iniziale**.
6.  Immettere l'importo iniziale di tutti i registratori di cassa nel punto vendita che fanno parte del turno condiviso e quindi fare clic su **Salva**.
    -   Per aggiungere una parte dell'importo iniziale a ogni successivo cassetto della cassa, utilizzare l'operazione **Seleziona stazione hardware** per rendere attiva la stazione hardware.
    -   Per aggiungere un cassetto a un cassetto della cassa specifico, utilizzare l'operazione **Apri cassetto**.
    -   Continuare fino a quando tutti i cassetti della cassa nel turno condiviso hanno la propria parte dell'importo iniziale.

7.  Alla fine del giorno, aprire ogni cassetto della cassa e rimuovere i contanti.
8.  Dopo aver rimosso il denaro dal cassetto della cassa ultimo, contare tutti i contanti da tutti i cassetti della cassa.
9.  Utilizzare l'operazione **Dichiara metodo di pagamento** per dichiarare l'importo totale di contanti di tutti i cassetti inclusi nel turno condiviso.
10. Utilizzare l'operazione **Chiudi turno** per chiudere il turno condiviso.

## <a name="shift-operations"></a>Operazioni per turni
È possibile eseguire vari azioni per cambiare lo stato di un turno o per aumentare o ridurre la somma di denaro in cassa. La sezione seguente descrive queste operazioni per turni per Dynamics 365 for Retail Modern POS e Cloud POS.

**Turno aperto**

POS richiede che un utente abbia un turno aperto attivo per eseguire qualsiasi operazione che provocherebbe una transazione finanziaria ad esempio una vendita, un reso o un ordine cliente.  

Durante la registrazione nel POS, il sistema dapprima verifica se l'utente ha un turno attivo disponibile nel registro corrente. In caso contrario, l'utente può scegliere di aprire un nuovo turno, riattivarne uno esistente o continuare ad accedere in modalità "non relativa al cassetto", a seconda della configurazione del sistema e delle autorizzazioni.

**Dichiara importo iniziale**

Questa operazione è spesso la prima azione eseguita con un turno appena aperto. Gli utenti specificano l'importo di cassa iniziale nella cassa per il turno. Ciò è importante in quanto il calcolo in eccesso/in difetto che si verifica alla chiusura di un turno tiene conto di questo importo.

**Immissione fondo di cassa**

Le voci fondo di cassa sono transazioni non di vendita che vengono eseguite in un turno attivo e aumentano l'importo della liquidità in cassa. Un esempio comune di immissione fondo di cassa consiste nell'immettere importi aggiuntivi nella cassa quando il livello è basso.

**Rimozione metodo di pagamento**

Le rimozioni metodo di pagamento sono transazioni non di vendita che vengono eseguite in un turno attivo per ridurre l'importo della liquidità in cassa. Ciò è più utilizzato insieme a un'immissione fondo di cassa per un turno differente. Ad esempio, il Registro 1 è scarso di liquidità, pertanto l'utente del Registro 2 esegue una rimozione del metodo di pagamento per ridurre l'importo in cassa. L'utente nel Registro 1 eseguirebbe quindi un'immissione fondo di cassa per aumentare il relativo importo.

**Sospendi turno**

Gli utenti possono sospendere il relativo turno attivo per mantenere disponibile il registro corrente per un altro utente o per spostare il turno in un registro differente (questo scenario è spesso denominato "cassetto con postazione variabile"). 

La sospensione del turno impedisce qualsiasi nuova transazione o modifica al turno finché a che non viene ripreso.

**Riprendi il turno**

Questa operazione consente a un utente di riprendere un turno sospeso in precedenza in un registro che non ha un turno attivo.

**Riepilogo incassi**

Il riepilogo incassi è un'azione che l'utente intraprende per specificare l'importo totale di denaro attualmente in cassa, spesso prima della chiusura del turno di lavoro. Si tratta del valore che viene confrontato al turno previsto per calcolare l'importo in eccesso/in difetto.

**Deposito in cassaforte**

I depositi in cassaforte possono essere eseguiti in qualsiasi momento per un turno attivo. Questa operazione rimuove denaro dalla cassa, in modo da poter essere trasferito in un luogo più sicuro ad esempio una cassaforte nella stanza sul retro. L'importo totale registrato per depositi in cassaforte è ancora incluso nei totali relativi ai turni, ma non deve essere conteggiato nel riepilogo incassi.

**Deposito bancario**

Come i depositi in cassaforte, anche i depositi bancari vengono eseguiti su turni attivi. Questa operazione rimuove denaro dal turno per preparare il deposito bancario.

**Chiusura forzata turno**

Un turno con chiusura forzata è un turno che non è più attivo ma non è stato chiuso completamente. I turni con chiusura forzata non possono essere riattivati come i turni sospesi. Tuttavia è possibile eseguire procedure come la dichiarazione di importi iniziali e i riepiloghi incassi in un momento successivo o da un registro diverso.

I turni con chiusura forzata vengono spesso utilizzati per liberare un registro per un nuovo utente o un nuovo turno, senza dover prima effettuare il conteggio, riconciliare e chiudere il turno. 

**Chiusura turno**

Questa operazione calcola i totali relativi ai turni, gli importi in eccesso/in difetto e quindi finalizza un turno attivo o con chiusura forzata. I turni chiusi non possono essere riattivati o modificati.  

**Gestisci turni**

Questa operazione consente agli utenti di visualizzare qualsiasi turno attivo, sospeso e con chiusura forzata per il punto vendita. A seconda delle autorizzazioni, gli utenti possono eseguire procedure di chiusura finali quali il riepilogo incassi e la chiusura dei turni per i turni con chiusura forzata. Questa operazione consentirà inoltre agli utenti di visualizzare ed eliminare i turni non validi nel raro evento che un turno sia in un cattivo stato dopo il passaggio tra la modalità offline e online. Questi turni non validi non contengono informazioni finanziarie o dati transazionali necessari per la riconciliazione. 

