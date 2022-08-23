---
title: Configurare l'interfaccia di esecuzione dell'area di produzione
description: Questo articolo descrive come creare una o più configurazioni per l'interfaccia di esecuzione dell'area di produzione. Quando si apre l'interfaccia di esecuzione dell'area di produzione, viene automaticamente caricata una configurazione selezionata e un filtro di processo specifici per il browser e il dispositivo. Nella configurazione si impostano i criteri che devono essere applicabili per un utilizzo specifico.
author: johanhoffmann
ms.date: 10/05/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: JmgProductionFloorExecutionConfiguration
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2020-10-05
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 2a77924e6133158d538a3eb8365def92c9354b0e
ms.sourcegitcommit: c98d55a4a6e27239ae6b317872332f01cbe8b875
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/02/2022
ms.locfileid: "9220364"
---
# <a name="configure-the-production-floor-execution-interface"></a>Configurare l'interfaccia di esecuzione dell'area di produzione

[!include [banner](../includes/banner.md)]

I lavoratori del reparto di produzione usano l'interfaccia di esecuzione dell'area di produzione per registrare il loro lavoro quotidiano, ad esempio ora di inizio dei lavori, invio del feedback sui lavori, registrazione delle attività indirette e segnalazione delle assenze. Queste registrazioni sono la base per monitorare l'avanzamento e il costo degli ordini di produzione e per calcolare la base per la retribuzione dei lavoratori.

Quando si apre l'interfaccia di esecuzione dell'area di produzione, viene automaticamente caricata una configurazione selezionata e un filtro di processo specifici per il browser e il dispositivo. Nella configurazione si impostano i criteri che devono essere applicabili per un utilizzo specifico. Di seguito sono riportati alcuni esempi di utilizzo:

- Con un dispositivo all'ingresso della società i dipendenti timbrano quando entrano in ufficio e quando escono.
- Con un dispositivo in officina, gli operatori della macchina registrano quando iniziano e completano i lavori. Registrano anche le pause e le attività indirette.

Questo articolo descrive le varie opzioni per la configurazione di un'interfaccia di esecuzione dell'area di produzione per ogni dispositivo in uso nel sito.

## <a name="turn-on-the-production-floor-execution-interface-and-its-related-optional-features"></a>Attivare l'interfaccia di esecuzione dell'area di produzione e le relative funzionalità opzionali

L'interfaccia di esecuzione dell'area di produzione stessa, più molte delle impostazioni opzionali descritte in questo articolo, devono essere attivate nel sistema prima di poterle utilizzare. Utilizzare la pagina [Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) per attivare una o tutte le funzionalità descritte nelle sottosezioni seguenti secondo le necessità.

### <a name="the-production-floor-execution-interface"></a>Interfaccia di esecuzione dell'area di produzione

Questa è la funzionalità principale descritta in questo articolo ed è un prerequisito per tutte le altre funzionalità menzionate in questa sezione. A partire dalla versione 10.0.25 di Supply Chain Management, questa funzionalità è obbligatoria e non può essere disattivata. Se si sta eseguendo una versione precedente alla versione 10.0.25, gli amministratori possono attivare o disattivare questa funzionalità cercando la funzionalità *Esecuzione area di produzione* nell'area di lavoro [Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

### <a name="generate-license-plates"></a>Generare le targhe

Queste funzioni rendono la funzionalità targa disponibile all'interfaccia di esecuzione dell'area di produzione. Per usarle, abilitare le seguenti funzionalità in [Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) (in quest'ordine):

1. *Targa per la dichiarazione di finito aggiunta al dispositivo della scheda processo*<br>A partire dalla versione 10.0.21 di Supply Chain Management, questa funzionalità è attivata per impostazione predefinita. A partire dalla versione 10.0.25 di Supply Chain Management, questa funzionalità è obbligatoria.
1. *Abilitare la generazione automatica del numero di identificazione durante la dichiarazione di finito nel dispositivo scheda processo*<br>A partire dalla versione 10.0.25 di Supply Chain Management, questa funzionalità è obbligatoria.

### <a name="print-labels"></a>Stampa etichette

Queste funzioni rendono la funzionalità stampa dell'etichetta disponibile all'interfaccia di esecuzione dell'area di produzione. Per usarle, abilitare le seguenti funzionalità in [Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) (in quest'ordine):

1. *Targa per la dichiarazione di finito aggiunta al dispositivo della scheda processo*<br>A partire dalla versione 10.0.21 di Supply Chain Management, questa funzionalità è attivata per impostazione predefinita. A partire dalla versione 10.0.25 di Supply Chain Management, questa funzionalità è obbligatoria.
1. *Stampa etichetta dal dispositivo scheda processo*<br>A partire dalla versione 10.0.25 di Supply Chain Management, questa funzionalità è obbligatoria.

### <a name="allow-locking-the-touch-screen"></a>Consenti blocco del touchscreen

Questa funzionalità consente ai lavoratori di bloccare il touchscreen in modo da poterlo pulire.

A partire dalla versione 10.0.21 di Supply Chain Management, questa funzionalità è attivata per impostazione predefinita. A partire dalla versione 10.0.25 di Supply Chain Management, questa funzionalità è obbligatoria e non può essere disattivata. Se si sta eseguendo una versione precedente alla versione 10.0.25, gli amministratori possono attivare o disattivare questa funzionalità cercando la funzionalità *Funzionalità per bloccare il dispositivo scheda processo e il terminale scheda processo di modo che possano essere puliti* nell'area di lavoro [Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

### <a name="asset-management-functionality-for-the-production-floor-execution-interface"></a>Funzionalità di gestione cespiti per l'interfaccia di esecuzione dell'area di produzione

Questa funzionalità aggiunge una scheda di gestione dei cespiti all'interfaccia di esecuzione del piano di produzione. I lavoratori possono utilizzare questa scheda per selezionare un cespite connesso a una risorsa macchina che si trova all'interno del filtro selezionato dell'elenco lavori. Per il cespite macchina selezionato, il lavoratore può visualizzare lo stato e l'integrità del cespite dai valori contatore per un massimo di quattro contatori selezionati. Per usarla, attivare la seguente funzionalità in [Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md):

- *Funzionalità di gestione cespiti per l'interfaccia di esecuzione dell'area di produzione*<br>A partire dalla versione 10.0.25 di Supply Chain Management, questa funzionalità è attivata per impostazione predefinita.

### <a name="enable-job-search"></a>Abilitare la ricerca di lavoro

Questa funzionalità consente di aggiungere un campo di ricerca all'elenco dei processi. I lavoratori possono trovare un processo specifico inserendo l'ID lavoro o trovare tutti i lavori per un ordine specifico inserendo l'ID ordine. I lavoratori possono inserire l'ID utilizzando una tastiera o eseguendo la scansione di un codice a barre. Per usarla, attivare la seguente funzionalità in [Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md):

- *Ricerca del processo per l'interfaccia di esecuzione dell'area di produzione*<br>A partire dalla versione 10.0.25 di Supply Chain Management, questa funzionalità è attivata per impostazione predefinita.

### <a name="enable-reporting-on-co-products-and-by-products"></a>Abilitare la dichiarazione in co-prodotti e sottoprodotti

Questa funzionalità consente ai lavoratori di utilizzare l'interfaccia di esecuzione dell'area di produzione per dichiarare lo stato di avanzamento degli ordini batch. Questo report include la dichiarazione di co-prodotti e sottoprodotti. Per usare questa funzionalità, attiva la seguente funzionalità in [Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md):

- *Report sui sotto/co-prodotti dall'interfaccia di esecuzione dell'area di produzione*

### <a name="enable-the-display-of-full-serial-batch-and-license-plate-numbers"></a>Abilitare la visualizzazione dei numeri di serie, batch e targa completi

Questa funzionalità offre un'esperienza migliorata per la visualizzazione di elenchi di numeri di serie, batch e targa nell'interfaccia di esecuzione dell'area di produzione. La visualizzazione cambia da una visualizzazione scheda che mostra un numero limitato di caratteri a una visualizzazione elenco che fornisce spazio sufficiente per mostrare i valori completi. L'elenco offre anche la possibilità di cercare numeri specifici.

A partire dalla versione 10.0.25 di Supply Chain Management, questa funzionalità è attivata per impostazione predefinita. Gli amministratori possono attivare o disattivare questa funzionalità cercando la funzionalità *Mostra i numeri di identificazione, serie e batch completi nell'interfaccia di esecuzione area di produzione* nell'area di lavoro [Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

### <a name="enable-registering-of-material-consumption"></a>Abilitare la registrazione del consumo materiali

Questa funzionalità consente ai lavoratori di utilizzare l'interfaccia di esecuzione del piano di produzione per registrare il consumo di materiale, i numeri di batch e i numeri di serie. Alcuni produttori, in particolare quelli all'interno delle industrie di processo, devono registrare esplicitamente la quantità di materiale consumato per ogni batch oppure ordine di produzione. Ad esempio, i lavoratori potrebbero utilizzare una bilancia per pesare la quantità di materiale consumato mentre lavorano. Per garantire la completa tracciabilità dei materiali, le organizzazioni devono anche registrare quali numeri di batch sono stati consumati durante la produzione di ciascun prodotto.

Sono disponibili due versioni di questa funzionalità. Una supporta gli articoli che *non sono* abilitati per l'utilizzo di processi di gestione del magazzino (WMS). L'altra supporta gli articoli che *sono* abilitati all'utilizzo di WMS. Per utilizzare questa funzionalità, attiva una o entrambe le seguenti funzionalità in [Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) (in questo ordine), a seconda che siano presenti articoli abilitati per WMS:

- *Registra il consumo di materiali nell'interfaccia di esecuzione dell'area di produzione (non WMS)*
- *Registra il consumo di materiali nell'interfaccia di esecuzione dell'area di produzione (abilitato per WMS)*

> [!IMPORTANT]
> È possibile utilizzare solo la funzionalità non WMS. Tuttavia, se utilizzi WMS, devi abilitare entrambe le funzionalità.

### <a name="enable-reporting-on-catch-weight-items"></a>Abilitare la creazione di report di articoli a peso variabile

I lavoratori possono utilizzare l'interfaccia di esecuzione del reparto di produzione per dichiarare lo stato di avanzamento degli ordini batch per gli articoli a peso variabile. Gli ordini batch vengono creati da formule che possono essere definite in modo che abbiano articoli a peso variabile come articoli formula, co-prodotti e sottoprodotti. È anche possibile definire una formula per avere righe di formula per gli ingredienti definiti per il peso variabile. Gli articoli a peso variabile utilizzano due unità di misura per tener traccia dell'inventario: la quantità a peso variabile e la quantità di inventario. Ad esempio, nell'industria alimentare, la carne in scatola può essere definita come un articolo a peso variabile, in cui la quantità a peso variabile viene utilizzata per tenere traccia del numero di scatole e la quantità di inventario viene utilizzata per tenere traccia del peso delle scatole.

Per usare questa funzionalità, attiva la seguente funzionalità in [Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md):

- *Report sugli articoli a peso variabile dall'interfaccia di esecuzione area di produzione*

### <a name="enable-the-my-day-dialog"></a>Abilitare la finestra di dialogo "Registrazioni quotidiane"

La finestra di dialogo **Registrazioni quotidiane** fornisce ai lavoratori una panoramica delle loro registrazioni giornaliere e dei saldi correnti per ore retribuite, straordinari retribuiti, assenze e assenze retribuite.

Per usare questa funzionalità, attiva la seguente funzionalità in [Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md):

- *Visualizzazione "Registrazioni quotidiane" per l'interfaccia di esecuzione dell'area di produzione*

### <a name="enable-teams"></a>Abilitare i team

Quando più lavoratori vengono assegnati allo stesso processo di produzione, possono formare un team. Il team può nominare un lavoratore come pilota. I restanti lavoratori quindi diventano automaticamente assistenti del pilota. Per il team risultante, solo il pilota deve registrare lo stato del processo. I record di tempo si applicano a tutti i membri del team.

Per usare questa funzionalità, attiva la seguente funzionalità in [Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md):

- *Team di produzione nell'interfaccia di esecuzione dell'area di produzione*

### <a name="enable-additional-configuration-in-the-production-floor-execution-interface"></a>Abilitare la configurazione aggiuntiva nell'interfaccia di esecuzione dell'area di produzione

Questa funzione aggiunge le impostazioni per la seguente funzionalità alla pagina **Configurare esecuzione area di produzione**:

- Viene visualizzata automaticamente la finestra di dialogo **Avvia processo** al termine di una ricerca.
- Viene visualizzata automaticamente la finestra di dialogo **Segnala stato** al termine di una ricerca.
- Precompila la quantità rimanente nella finestra di dialogo **Segnala stato**.
- Abilita le rettifiche al consumo di materiale dalla finestra di dialogo **Segnala stato**. (Questa funzionalità richiede anche la funzionalità *Registra il consumo di materiali nell'interfaccia di esecuzione dell'area di produzione (non WMS)*.)
- Abilita le ricerche per ID progetto.

Le informazioni su come utilizzare le impostazioni sono fornite più avanti in questo articolo.

Per usare questa funzionalità, attiva la seguente funzionalità in [Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md):

- *Configurazione aggiuntiva nell'interfaccia di esecuzione dell'area di produzione*


## <a name="work-with-production-floor-execution-configurations"></a>Utilizzare le configurazioni di esecuzione dell'area di produzione

Per creare e gestire configurazioni di esecuzione dell'area di produzione, andare a **Controllo produzione \> Imposta \> Esecuzione produzione \> Configura esecuzione area di produzione**. La pagina **Configura esecuzione area di produzione** mostra un elenco di configurazioni esistenti. In questa pagina è possibile effettuare le azioni riportate di seguito:

- Selezionare una configurazione dell'area di produzione elencata nella colonna di sinistra per visualizzarla e modificarla.
- Seleziona **Nuovo** nel riquadro azioni per aggiungere una nuova configurazione all'elenco. Immettere un nome nel campo **Configurazione** per identificare la nuova configurazione. Il nome inserito deve essere univoco tra tutte le configurazioni e non sarà possibile modificarlo in un secondo momento. Nel campo **Descrizione** puoi immettere facoltativamente una descrizione della configurazione.

Quindi, configura le varie impostazioni per la configurazione selezionata, come descritto nelle seguenti sottosezioni.

### <a name="the-general-fasttab"></a>Scheda dettaglio Generale

Le seguenti impostazioni sono disponibili nella scheda dettaglio **Generale**:

- **Solo ora di entrata e di uscita** - Impostare questa opzione su *Sì* per creare un'interfaccia semplificata che fornisca solo la funzionalità ora di entrata e ora di uscita. Questa impostazione disabilita la maggior parte delle altre opzioni in questa pagina. È necessario rimuovere tutte le righe dalla Scheda dettaglio **Selezione scheda** per poter abilitare questa opzione.
- **Abilita la ricerca**: imposta questa opzione su *Sì* per includere un campo di ricerca nell'elenco dei lavori. I lavoratori possono trovare un processo specifico inserendo l'ID lavoro o possono trovare tutti i lavori per un ordine specifico inserendo l'ID ordine. I lavoratori possono inserire l'ID utilizzando una tastiera o eseguendo la scansione di un codice a barre.
- **Abilita la ricerca per ID progetto** – Imposta questa opzione su *sì* per consentire ai lavoratori di cercare per ID progetto (oltre a ID processo e ID ordine) nel campo di ricerca dell'interfaccia di esecuzione dell'area di produzione. È possibile impostare questa opzione su *Sì* solo se anche l'opzione **Abilita ricerca** è impostata su *Sì*.
- **Apri automaticamente la finestra di dialogo di avvio** – Quando questa opzione è impostata su *sì*, la finestra di dialogo **Avvia processo** viene aperta automaticamente quando i lavoratori utilizzano la barra di ricerca per trovare un processo.
- **Apri automaticamente la finestra di dialogo di Segnala stato** – Quando questa opzione è impostata su *sì*, la finestra di dialogo **Segnala stato** viene aperta automaticamente quando i lavoratori utilizzano la barra di ricerca per trovare un processo.
- **Abilita rettifica materiali** – Imposta questa opzione su *sì* per abilitare il pulsante **Rettifica materiali** nella finestra di dialogo **Segnala stato**. I lavoratori possono selezionare questo pulsante per rettificare il consumo di materiale per il processo.
- **Segnala quantità all'uscita** - Impostare questa opzione su *Sì* per richiedere ai lavoratori di fornire il loro feedback sui lavori in corso quando timbrano il cartellino. Se impostato su *No*, ai lavoratori non verrà richiesto di eseguire questa operazione.
- **Blocca dipendente** - Quando questa opzione è impostata su *No*, i lavoratori verranno disconnessi immediatamente dopo aver effettuato una registrazione (ad esempio un nuovo lavoro). L'interfaccia tornerà quindi alla pagina di accesso. Quando questa opzione è impostata su *Sì*, i lavoratori rimarranno connessi all'interfaccia di esecuzione dell'area di produzione. Tuttavia, un lavoratore può disconnettersi manualmente di modo che un altro lavoratore possa accedere mentre l'Interfaccia di esecuzione dell'area di produzione continua a funzionare con lo stesso account utente di sistema. Per ulteriori informazioni su questi tipi di account, vedere [Utenti assegnati](config-job-card-device.md#assigned-users).
- **Utilizza ora di registrazione effettiva** - Impostare questa opzione su *Sì* affinché l'ora di ogni nuova registrazione sia uguale all'ora esatta in cui la registrazione è stata presentata dal lavoratore. Quando questa opzione è impostata su *No*, viene utilizzata l'ora di accesso. Di solito si imposta questa opzione su *Sì* se sono state impostate le opzioni **Blocca dipendente** e/o **Singolo lavoratore** su *Sì* per i casi dove i lavoratori rimangono spesso connessi per periodi più lunghi.
- **Singolo lavoratore** - Impostare questa opzione su *Sì* se un solo lavoratore utilizza ogni interfaccia di esecuzione dell'area di produzione in cui questa configurazione è attiva. Quando questa opzione è impostata su *Sì*, l'opzione **Blocca dipendente** viene automaticamente impostata su *Sì*. Inoltre, questa impostazione rimuove la necessità (e la possibilità) per il lavoratore di accedere utilizzando un ID badge (o altro ID simile). Al contrario, il lavoratore accede a Microsoft Dynamics 365 Supply Chain Management utilizzando un account utente di sistema collegato a un *lavoratore registrato nel tempo* (nella tabella *lavoratori*) e si connette all'interfaccia di esecuzione dell'area di produzione come quel lavoratore nello stesso tempo.
- **Consenti blocco del touchscreen** - Impostare questa opzione su *Sì* per consentire ai lavoratori di bloccare il touchscreen dell'interfaccia di esecuzione dell'area di produzione di modo che possano pulirla. Quando questa opzione è impostata su *Sì*, un pulsante **Blocca schermo per pulizia** viene aggiunto alla pagina di accesso. Quando un lavoratore seleziona questo pulsante, il touchscreen viene bloccato temporaneamente per impedire un'immissione involontaria. Viene visualizzato anche un timer per il conto alla rovescia. Il lavoratore può pulire in sicurezza il dispositivo e lo schermo. Al termine del conto alla rovescia, il touchscreen si sblocca automaticamente.
- **Durata blocco schermo** - Quando l'opzione **Consenti blocco del touchscreen** è impostata su *Sì*, utilizzare questa opzione per specificare il numero di secondi in cui il touchscreen deve essere bloccato per la pulizia. La durata deve essere un numero tra 5 e 120 secondi.
- **Genera targa** - Impostare questa opzione su *Sì* per generare una nuova targa ogni volta che un lavoratore utilizza l'interfaccia di esecuzione dell'area di produzione. Il numero di targa viene generato da una sequenza numerica impostata nella pagina **Parametri di gestione magazzino**. Quando l'opzione è impostata su *No*, i lavoratori devono specificare una targa esistente al momento della dichiarazione di finito.
- **Stampa etichetta** - Impostare questa opzione su *Sì* per stampare l'etichetta di una targa quando un lavoratore utilizza l'interfaccia di esecuzione dell'area di produzione per la dichiarazione di finito. La configurazione dell'etichetta è impostata nella distribuzione dei documenti, come descritto in [Layout di distribuzione del documento per le etichette della targa](../warehousing/document-routing-layout-for-license-plates.md).

### <a name="the-tab-selection-fasttab"></a>Scheda dettaglio Selezione scheda

Utilizza le impostazioni della scheda dettaglio **Selezione scheda** per scegliere quali schede devono essere visualizzate dall'interfaccia di esecuzione dell'area di produzione quando la configurazione corrente è attiva. Puoi progettare tutte le schede di cui hai bisogno, quindi aggiungerle e disporle come desideri utilizzando i pulsanti sulla barra degli strumenti della Scheda dettaglio. Per informazioni su come progettare le schede e lavorare con le impostazioni qui, vedi [Progettare l'interfaccia di esecuzione dell'area di produzione](production-floor-execution-tabs.md).

### <a name="the-report-progress-fasttab"></a>Scheda dettaglio Segnala stato

Le seguenti impostazioni sono disponibili nella scheda dettaglio **Segnala stato**.

- **Abilita rettifica materiali** – Imposta questa opzione su *sì* per includere il pulsante **Rettifica materiali** nella finestra di dialogo **Segnala stato**. I lavoratori possono selezionare questo pulsante per rettificare il consumo di materiale per il processo.
- **Quantità rimanente predefinita** – Imposta questa opzione su *sì* per precompilare la quantità rimanente prevista per un processo di produzione nella finestra di dialogo **Segnala stato**.

## <a name="clean-up-job-configurations"></a>Pulire le configurazioni dei processi

Quando il supervisore del reparto di produzione imposta l'interfaccia di esecuzione dell'area di produzione, seleziona una configurazione e un filtro di processo. Queste selezioni vengono memorizzate in una tabella di riferimento in Supply Chain Management e il browser utilizza un ID memorizzato in un cookie locale per trovare la riga corretta in quella tabella. La tabella registra anche la data e l'ora dell'ultimo accesso di un lavoratore a ciascun dispositivo.

Un processo batch pulisce periodicamente le voci nella tabella dei riferimenti per i dispositivi che non hanno registrato alcuna attività negli ultimi 60 giorni. È possibile anche pulire manualmente le voci in qualsiasi momento seguendo questi passaggi.

1. Andare a **Controllo produzione \> Imposta \> Esecuzione produzione \> Configura esecuzione area di produzione**.
1. Nel riquadro azioni selezionare **Pulisci configurazioni client**.
1. Nella finestra di dialogo **Pulisci configurazione client** impostare il campo **Numero di giorni** sul numero di giorni di inattività (precedenti a oggi) da considerare. Verranno rimosse tutte le configurazioni e i record di accesso per i dispositivi che non sono stati attivi durante quel periodo.
1. Selezionare **OK** per pulire le configurazioni pertinenti, in base all'impostazione **Numero di giorni**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
