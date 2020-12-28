---
title: Configurare l'interfaccia di esecuzione dell'area di produzione
description: Questo argomento descrive come creare una o più configurazioni per l'interfaccia di esecuzione dell'area di produzione. Quando si apre l'interfaccia di esecuzione dell'area di produzione, viene automaticamente caricata una configurazione selezionata e un filtro di processo specifici per il browser e il dispositivo. Nella configurazione si impostano i criteri che devono essere applicabili per un utilizzo specifico.
author: johanhoffmann
manager: tfehr
ms.date: 10/05/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2020-10-05
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: cf58a7d851577854d08bad70cff69794c3841a2d
ms.sourcegitcommit: 9dd2d38e76d4d93171315ec319e6ce7d51d4e6c7
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/15/2020
ms.locfileid: "4012486"
---
# <a name="configure-the-production-floor-execution-interface"></a>Configurare l'interfaccia di esecuzione dell'area di produzione

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

I lavoratori del reparto di produzione usano l'interfaccia di esecuzione dell'area di produzione per registrare il loro lavoro quotidiano, ad esempio ora di inizio dei lavori, invio del feedback sui lavori, registrazione delle attività indirette e segnalazione delle assenze. Queste registrazioni sono la base per monitorare l'avanzamento e il costo degli ordini di produzione e per calcolare la base per la retribuzione dei lavoratori.

Quando si apre l'interfaccia di esecuzione dell'area di produzione, viene automaticamente caricata una configurazione selezionata e un filtro di processo specifici per il browser e il dispositivo. Nella configurazione si impostano i criteri che devono essere applicabili per un utilizzo specifico. Di seguito sono riportati alcuni esempi di utilizzo:

- Con un dispositivo all'ingresso della società i dipendenti timbrano quando entrano in ufficio e quando escono.
- Con un dispositivo in officina, gli operatori della macchina registrano quando iniziano e completano i lavori. Registrano anche le pause e le attività indirette.

Questo argomento descrive le varie opzioni per la configurazione dei dispositivi scheda processo.

## <a name="turn-on-new-features-in-feature-management"></a>Attivare nuove funzionalità nella gestione delle funzionalità

Alcune delle impostazioni descritte in questo argomento devono essere attivate nel sistema affinché siano disponibili. Utilizzare la pagina [Gestione delle funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) per attivare una o tutte le seguenti funzionalità come richiesto.

### <a name="generate-license-plate"></a>Genera targa

Per rendere disponibile questa funzionalità, abilitare le seguenti funzionalità in [Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) (in quest'ordine):

1. Targa per la dichiarazione di finito aggiunta al dispositivo della scheda processo
1. Abilitare la generazione automatica del numero di identificazione durante la dichiarazione di finito nel dispositivo scheda processo

### <a name="print-label"></a>Stampa etichetta

Per rendere disponibile questa funzionalità, abilitare le seguenti funzionalità in [Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) (in quest'ordine):

1. Targa per la dichiarazione di finito aggiunta al dispositivo della scheda processo
1. Stampa etichetta dal dispositivo scheda processo

### <a name="allow-locking-the-touch-screen"></a>Consenti blocco del touchscreen

Per rendere disponibile questa funzionalità, attivare la seguente funzionalità in [Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md):

- (Anteprima) Funzionalità per bloccare il dispositivo scheda processo e il terminale scheda processo di modo che possano essere puliti

## <a name="work-with-production-floor-execution-configurations"></a>Utilizzare le configurazioni di esecuzione dell'area di produzione

Per creare e gestire le configurazioni del dispositivo, andare a **Controllo produzione \> Imposta \> Esecuzione produzione \> Configura esecuzione area di produzione**. La pagina **Configura esecuzione area di produzione** mostra un elenco di configurazioni esistenti. In questa pagina è possibile effettuare le azioni riportate di seguito:

- Selezionare una configurazione dell'area di produzione elencata nella colonna di sinistra per visualizzarla e modificarla.
- Selezionare **Nuovo** nel riquadro azioni per aggiungere una nuova configurazione di dispositivo all'elenco. Immettere un nome nel campo **Configurazione** per identificare la nuova configurazione. Il nome inserito deve essere univoco tra tutte le configurazioni di dispositivo e non sarà possibile modificarlo in un secondo momento.

Successivamente, configurare le varie impostazioni per la configurazione del dispositivo selezionato. Sono disponibili i campi seguenti:

- **Segnala quantità all'uscita** - Impostare questa opzione su *Sì* per richiedere ai lavoratori di fornire il loro feedback sui lavori in corso quando timbrano il cartellino. Se impostato su *No* , ai lavoratori non verrà richiesto di eseguire questa operazione.
- **Blocca dipendente** - Quando questa opzione è impostata su *No* , i lavoratori verranno disconnessi immediatamente dopo aver effettuato una registrazione (ad esempio un nuovo lavoro). Il dispositivo tornerà quindi alla pagina di accesso. Quando questa opzione è impostata su *Sì* , i lavoratori rimarranno connessi al dispositivo con la scheda lavoro. Tuttavia, un lavoratore può disconnettersi manualmente in modo che un altro lavoratore possa accedere mentre il dispositivo con la scheda lavoro continua a funzionare con lo stesso account utente di sistema. Per ulteriori informazioni su questi tipi di account, vedere [Utenti assegnati](config-job-card-device.md#assigned-users).
- **Utilizza ora di registrazione effettiva** - Impostare questa opzione su *Sì* affinché l'ora di ogni nuova registrazione sia uguale all'ora esatta in cui la registrazione è stata presentata dal lavoratore. Quando questa opzione è impostata su *No* , viene utilizzata l'ora di accesso. Di solito si imposta questa opzione su *Sì* se sono state impostate le opzioni **Blocca dipendente** e/o **Singolo lavoratore** su *Sì* per i casi dove i lavoratori rimangono spesso connessi per periodi più lunghi.
- **Singolo Lavoratore** - Impostare questa opzione su *Sì* se un solo lavoratore utilizza ciascun dispositivo scheda lavoro in cui è attiva questa configurazione. Quando questa opzione è impostata su *Sì* , l'opzione **Blocca dipendente** viene automaticamente impostata su *Sì*. Inoltre, questa impostazione rimuove la necessità (e la possibilità) per il lavoratore di accedere utilizzando un ID badge (o altro ID simile). Al contrario, il lavoratore accede a Microsoft Dynamics 365 Supply Chain Management utilizzando un account utente di sistema collegato a un *lavoratore registrato nel tempo* (nella tabella *lavoratori* ) e si connette al dispositivo con la scheda lavoro come quel lavoratore nello stesso tempo.
- **Consenti blocco del touchscreen** - Impostare questa opzione su *Sì* per consentire ai lavoratori di bloccare il touchscreen del dispositivo con la scheda lavoro di modo che possano pulirlo. Quando questa opzione è impostata su *Sì* , il pulsante **Blocca schermo per pulizia** viene aggiunto alla pagina di accesso del dispositivo. Quando un lavoratore seleziona questo pulsante, il touchscreen viene bloccato temporaneamente per impedire un'immissione involontaria. Viene visualizzato anche un timer per il conto alla rovescia. L'operatore può pulire in sicurezza il dispositivo e lo schermo. Al termine del conto alla rovescia, il touchscreen si sblocca automaticamente.
- **Durata blocco schermo** - Quando l'opzione **Consenti blocco del touchscreen** è impostata su *Sì* , utilizzare questa opzione per specificare il numero di secondi in cui il touchscreen deve essere bloccato per la pulizia. La durata deve essere un numero tra 5 e 120 secondi.
- **Genera targa** - Impostare questa opzione su *Sì* per generare una nuova targa ogni volta che un lavoratore utilizza il dispositivo scheda lavoro per la dichiarazione di finito. Il numero di targa viene generato da una sequenza numerica impostata nella pagina **Parametri di gestione magazzino**. Quando l'opzione è impostata su *No* , i lavoratori devono specificare una targa esistente al momento della dichiarazione di finito.
- **Stampa etichetta** - Impostare questa opzione su *Sì* per stampare l'etichetta di una targa quando un lavoratore utilizza il dispositivo scheda lavoro per la dichiarazione di finito. La configurazione dell'etichetta è impostata nella distribuzione dei documenti, come descritto in [Layout di distribuzione del documento per le etichette della targa](../warehousing/document-routing-layout-for-license-plates.md).

## <a name="clean-up-job-configurations"></a>Pulire le configurazioni dei processi

Quando il supervisore del reparto di produzione imposta l'interfaccia di esecuzione dell'area di produzione, seleziona una configurazione e un filtro di processo. Queste selezioni vengono memorizzate in una tabella di riferimento in Supply Chain Management e il browser utilizza un ID memorizzato in un cookie locale per trovare la riga corretta in quella tabella. La tabella registra anche la data e l'ora dell'ultimo accesso di un lavoratore a ciascun dispositivo.

Un processo batch pulisce periodicamente le voci nella tabella dei riferimenti per i dispositivi che non hanno registrato alcuna attività negli ultimi 60 giorni. È possibile anche pulire manualmente le voci in qualsiasi momento seguendo questi passaggi.

1. Andare a **Controllo produzione \> Imposta \> Esecuzione produzione \> Configura esecuzione area di produzione**.
1. Nel riquadro azioni selezionare **Pulisci configurazioni client**.
1. Nella finestra di dialogo **Pulisci configurazione client** impostare il campo **Numero di giorni** sul numero di giorni di inattività (precedenti a oggi) da considerare. Verranno rimosse tutte le configurazioni e i record di accesso per i dispositivi che non sono stati attivi durante quel periodo.
1. Selezionare **OK** per pulire le configurazioni pertinenti, in base all'impostazione **Numero di giorni**.