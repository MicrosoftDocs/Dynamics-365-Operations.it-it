---
title: Configurare l'interfaccia di esecuzione dell'area di produzione
description: Questo argomento descrive come creare una o più configurazioni per l'interfaccia di esecuzione dell'area di produzione. Quando si apre l'interfaccia di esecuzione dell'area di produzione, viene automaticamente caricata una configurazione selezionata e un filtro di processo specifici per il browser e il dispositivo. Nella configurazione si impostano i criteri che devono essere applicabili per un utilizzo specifico.
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
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: c1739c9b50cb3f09696bf95730cd62fc9960ed5d
ms.sourcegitcommit: 908a85987b604a7782407da70fb70ef75c07989f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/19/2021
ms.locfileid: "6641082"
---
# <a name="configure-the-production-floor-execution-interface"></a>Configurare l'interfaccia di esecuzione dell'area di produzione

[!include [banner](../includes/banner.md)]

I lavoratori del reparto di produzione usano l'interfaccia di esecuzione dell'area di produzione per registrare il loro lavoro quotidiano, ad esempio ora di inizio dei lavori, invio del feedback sui lavori, registrazione delle attività indirette e segnalazione delle assenze. Queste registrazioni sono la base per monitorare l'avanzamento e il costo degli ordini di produzione e per calcolare la base per la retribuzione dei lavoratori.

Quando si apre l'interfaccia di esecuzione dell'area di produzione, viene automaticamente caricata una configurazione selezionata e un filtro di processo specifici per il browser e il dispositivo. Nella configurazione si impostano i criteri che devono essere applicabili per un utilizzo specifico. Di seguito sono riportati alcuni esempi di utilizzo:

- Con un dispositivo all'ingresso della società i dipendenti timbrano quando entrano in ufficio e quando escono.
- Con un dispositivo in officina, gli operatori della macchina registrano quando iniziano e completano i lavori. Registrano anche le pause e le attività indirette.

Questo argomento descrive le varie opzioni per la configurazione dei dispositivi scheda processo.

## <a name="turn-on-the-production-floor-execution-interface-and-its-related-optional-features"></a>Attivare l'interfaccia di esecuzione dell'area di produzione e le relative funzionalità opzionali

L'interfaccia di esecuzione dell'area di produzione stessa, più molte delle impostazioni opzionali descritte in questo argomento, devono essere attivate nel sistema prima di poterle utilizzare. Utilizzare la pagina [Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) per attivare una o tutte le funzionalità descritte nelle sottosezioni seguenti secondo le necessità.

### <a name="the-production-floor-execution-interface"></a>Interfaccia di esecuzione dell'area di produzione

Questa è la funzionalità principale descritta in questo argomento. Aggiunge l'interfaccia di esecuzione dell'area di produzione al sistema. Per abilitarla, attivare la seguente funzionalità in [Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md):

- Esecuzione dell'area di produzione

### <a name="generate-license-plates"></a>Generare le targhe

Queste funzioni rendono la funzionalità targa disponibile all'interfaccia di esecuzione dell'area di produzione. Per usarle, abilitare le seguenti funzionalità in [Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) (in quest'ordine):

1. Targa per la dichiarazione di finito aggiunta al dispositivo della scheda processo
1. Abilitare la generazione automatica del numero di identificazione durante la dichiarazione di finito nel dispositivo scheda processo

### <a name="print-labels"></a>Stampa etichette

Queste funzioni rendono la funzionalità stampa dell'etichetta disponibile all'interfaccia di esecuzione dell'area di produzione. Per usarle, abilitare le seguenti funzionalità in [Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) (in quest'ordine):

1. Targa per la dichiarazione di finito aggiunta al dispositivo della scheda processo
1. Stampa etichetta dal dispositivo scheda processo

### <a name="allow-locking-the-touch-screen"></a>Consenti blocco del touchscreen

Questa funzione aggiunge un pulsante all'interfaccia di esecuzione dell'area di produzione che consente ai lavoratori di sanificare il touch screen. Per usarla, attivare la seguente funzionalità in [Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md):

- Funzionalità per bloccare il dispositivo scheda processo e il terminale scheda processo di modo che possano essere puliti

### <a name="asset-management-functionality-for-the-production-floor-execution-interface"></a>Funzionalità di gestione cespiti per l'interfaccia di esecuzione dell'area di produzione

Questa funzionalità aggiunge una scheda di gestione dei cespiti all'interfaccia di esecuzione del piano di produzione. I lavoratori possono utilizzare questa scheda per selezionare un cespite connesso a una risorsa macchina che si trova all'interno del filtro selezionato dell'elenco lavori. Per il cespite macchina selezionato, il lavoratore può visualizzare lo stato e l'integrità del cespite dai valori contatore per un massimo di quattro contatori selezionati. Per usarla, attivare la seguente funzionalità in [Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md):

- Funzionalità di gestione cespiti per l'interfaccia di esecuzione dell'area di produzione

### <a name="enable-job-search"></a>Abilitare la ricerca di lavoro

Questa funzionalità consente di aggiungere un campo di ricerca all'elenco dei processi. I lavoratori possono trovare un processo specifico inserendo l'ID lavoro o trovare tutti i lavori per un ordine specifico inserendo l'ID ordine. I lavoratori possono inserire l'ID utilizzando una tastiera o eseguendo la scansione di un codice a barre. Per usarla, attivare la seguente funzionalità in [Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md):

- Ricerca del processo per l'interfaccia di esecuzione dell'area di produzione

## <a name="work-with-production-floor-execution-configurations"></a>Utilizzare le configurazioni di esecuzione dell'area di produzione

Per creare e gestire le configurazioni del dispositivo, andare a **Controllo produzione \> Imposta \> Esecuzione produzione \> Configura esecuzione area di produzione**. La pagina **Configura esecuzione area di produzione** mostra un elenco di configurazioni esistenti. In questa pagina è possibile effettuare le azioni riportate di seguito:

- Selezionare una configurazione dell'area di produzione elencata nella colonna di sinistra per visualizzarla e modificarla.
- Selezionare **Nuovo** nel riquadro azioni per aggiungere una nuova configurazione di dispositivo all'elenco. Immettere un nome nel campo **Configurazione** per identificare la nuova configurazione. Il nome inserito deve essere univoco tra tutte le configurazioni di dispositivo e non sarà possibile modificarlo in un secondo momento.

Successivamente, configurare le varie impostazioni per la configurazione del dispositivo selezionato. Sono disponibili i campi seguenti:

- **Solo ora di entrata e di uscita** - Impostare questa opzione su *Sì* per creare un'interfaccia semplificata che fornisca solo la funzionalità ora di entrata e ora di uscita. Ciò disabilita la maggior parte delle altre opzioni in questa pagina. È necessario rimuovere tutte le righe dalla Scheda dettaglio **Selezione scheda** per poter abilitare questa opzione.
- **Abilita la ricerca**: imposta questa opzione su *Sì* per includere un campo di ricerca nell'elenco dei lavori. I lavoratori possono trovare un processo specifico inserendo l'ID lavoro o trovare tutti i lavori per un ordine specifico inserendo l'ID ordine. I lavoratori possono inserire l'ID utilizzando una tastiera o eseguendo la scansione di un codice a barre.
- **Segnala quantità all'uscita** - Impostare questa opzione su *Sì* per richiedere ai lavoratori di fornire il loro feedback sui lavori in corso quando timbrano il cartellino. Se impostato su *No*, ai lavoratori non verrà richiesto di eseguire questa operazione.
- **Blocca dipendente** - Quando questa opzione è impostata su *No*, i lavoratori verranno disconnessi immediatamente dopo aver effettuato una registrazione (ad esempio un nuovo lavoro). Il dispositivo tornerà quindi alla pagina di accesso. Quando questa opzione è impostata su *Sì*, i lavoratori rimarranno connessi al dispositivo con la scheda lavoro. Tuttavia, un lavoratore può disconnettersi manualmente in modo che un altro lavoratore possa accedere mentre il dispositivo con la scheda lavoro continua a funzionare con lo stesso account utente di sistema. Per ulteriori informazioni su questi tipi di account, vedere [Utenti assegnati](config-job-card-device.md#assigned-users).
- **Utilizza ora di registrazione effettiva** - Impostare questa opzione su *Sì* affinché l'ora di ogni nuova registrazione sia uguale all'ora esatta in cui la registrazione è stata presentata dal lavoratore. Quando questa opzione è impostata su *No*, viene utilizzata l'ora di accesso. Di solito si imposta questa opzione su *Sì* se sono state impostate le opzioni **Blocca dipendente** e/o **Singolo lavoratore** su *Sì* per i casi dove i lavoratori rimangono spesso connessi per periodi più lunghi.
- **Singolo Lavoratore** - Impostare questa opzione su *Sì* se un solo lavoratore utilizza ciascun dispositivo scheda lavoro in cui è attiva questa configurazione. Quando questa opzione è impostata su *Sì*, l'opzione **Blocca dipendente** viene automaticamente impostata su *Sì*. Inoltre, questa impostazione rimuove la necessità (e la possibilità) per il lavoratore di accedere utilizzando un ID badge (o altro ID simile). Al contrario, il lavoratore accede a Microsoft Dynamics 365 Supply Chain Management utilizzando un account utente di sistema collegato a un *lavoratore registrato nel tempo* (nella tabella *lavoratori*) e si connette al dispositivo con la scheda lavoro come quel lavoratore nello stesso tempo.
- **Consenti blocco del touchscreen** - Impostare questa opzione su *Sì* per consentire ai lavoratori di bloccare il touchscreen del dispositivo con la scheda lavoro di modo che possano pulirlo. Quando questa opzione è impostata su *Sì*, il pulsante **Blocca schermo per pulizia** viene aggiunto alla pagina di accesso del dispositivo. Quando un lavoratore seleziona questo pulsante, il touchscreen viene bloccato temporaneamente per impedire un'immissione involontaria. Viene visualizzato anche un timer per il conto alla rovescia. L'operatore può pulire in sicurezza il dispositivo e lo schermo. Al termine del conto alla rovescia, il touchscreen si sblocca automaticamente.
- **Durata blocco schermo** - Quando l'opzione **Consenti blocco del touchscreen** è impostata su *Sì*, utilizzare questa opzione per specificare il numero di secondi in cui il touchscreen deve essere bloccato per la pulizia. La durata deve essere un numero tra 5 e 120 secondi.
- **Genera targa** - Impostare questa opzione su *Sì* per generare una nuova targa ogni volta che un lavoratore utilizza il dispositivo scheda lavoro per la dichiarazione di finito. Il numero di targa viene generato da una sequenza numerica impostata nella pagina **Parametri di gestione magazzino**. Quando l'opzione è impostata su *No*, i lavoratori devono specificare una targa esistente al momento della dichiarazione di finito.
- **Stampa etichetta** - Impostare questa opzione su *Sì* per stampare l'etichetta di una targa quando un lavoratore utilizza il dispositivo scheda lavoro per la dichiarazione di finito. La configurazione dell'etichetta è impostata nella distribuzione dei documenti, come descritto in [Layout di distribuzione del documento per le etichette della targa](../warehousing/document-routing-layout-for-license-plates.md).
- **Selezione delle schede** - Utilizzare le impostazioni in questa sezione per scegliere quali schede devono essere visualizzate dall'interfaccia di esecuzione dell'area di produzione quando la configurazione corrente è attiva. È possibile progettare tutte le schede necessarie, quindi aggiungerle e disporle qui come richiesto. Per dettagli su come progettare le schede e lavorare con le impostazioni qui, vedere [Progettare l'interfaccia di esecuzione dell'area di produzione](production-floor-execution-tabs.md).

## <a name="clean-up-job-configurations"></a>Pulire le configurazioni dei processi

Quando il supervisore del reparto di produzione imposta l'interfaccia di esecuzione dell'area di produzione, seleziona una configurazione e un filtro di processo. Queste selezioni vengono memorizzate in una tabella di riferimento in Supply Chain Management e il browser utilizza un ID memorizzato in un cookie locale per trovare la riga corretta in quella tabella. La tabella registra anche la data e l'ora dell'ultimo accesso di un lavoratore a ciascun dispositivo.

Un processo batch pulisce periodicamente le voci nella tabella dei riferimenti per i dispositivi che non hanno registrato alcuna attività negli ultimi 60 giorni. È possibile anche pulire manualmente le voci in qualsiasi momento seguendo questi passaggi.

1. Andare a **Controllo produzione \> Imposta \> Esecuzione produzione \> Configura esecuzione area di produzione**.
1. Nel riquadro azioni selezionare **Pulisci configurazioni client**.
1. Nella finestra di dialogo **Pulisci configurazione client** impostare il campo **Numero di giorni** sul numero di giorni di inattività (precedenti a oggi) da considerare. Verranno rimosse tutte le configurazioni e i record di accesso per i dispositivi che non sono stati attivi durante quel periodo.
1. Selezionare **OK** per pulire le configurazioni pertinenti, in base all'impostazione **Numero di giorni**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
