---
title: Configura scheda processo per dispositivi
description: Questo argomento descrive le varie opzioni per la configurazione del dispositivo scheda processo.
author: johanhoffmann
ms.date: 05/29/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: JmgRegistrationSetupTouch, JmgRegistrationTouchUserConfiguration
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2020-05-29
ms.dyn365.ops.version: 10.0.12
ms.openlocfilehash: 4c7a9585d96a1e08790e0f3c972e704971f27dc0
ms.sourcegitcommit: fcb8a3419e3597fe855cae9eb21333698518c2c7
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/09/2022
ms.locfileid: "8103440"
---
# <a name="configure-job-card-for-devices"></a>Configura scheda processo per dispositivi

[!include [banner](../includes/banner.md)]

Il dispositivo scheda processo viene utilizzato dai lavoratori del reparto produzione per registrare il loro lavoro quotidiano, ad esempio ora di inizio dei lavori, feedback sui lavori, registrazione delle attività indirette e segnalazione delle assenze. Queste registrazioni sono la base per monitorare l'avanzamento e il costo degli ordini di produzione e per calcolare la base per la retribuzione dei lavoratori. Questo argomento descrive le varie opzioni per la configurazione dei dispositivi scheda processo.

## <a name="enable-new-features-in-feature-management"></a>Abilitare nuove funzionalità nella gestione delle funzionalità

Alcune delle impostazioni descritte in questo argomento devono essere abilitate nel sistema affinché siano disponibili. Utilizzare la pagina [Gestione delle funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) per abilitare una o tutte le seguenti funzionalità come richiesto.

### <a name="generate-license-plate"></a>Genera targa

Per rendere disponibile questa funzionalità, abilitare le seguenti funzionalità in [Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) (nell'ordine in cui sono elencate):

1. *Targa per la dichiarazione di finito aggiunta al dispositivo della scheda processo*<br>A partire dalla versione 10.0.21 di Supply Chain Management, questa funzionalità è attivata per impostazione predefinita. A partire dalla versione 10.0.25 di Supply Chain Management, questa funzionalità è obbligatoria.
1. *Abilitare la generazione automatica del numero di identificazione durante la dichiarazione di finito nel dispositivo scheda processo*<br>A partire dalla versione 10.0.25 di Supply Chain Management, questa funzionalità è obbligatoria.

### <a name="print-label"></a>Stampa etichetta

Per rendere disponibile questa funzionalità, abilitare le seguenti funzionalità in [Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) (nell'ordine in cui sono elencate):

1. *Targa per la dichiarazione di finito aggiunta al dispositivo della scheda processo*<br>A partire dalla versione 10.0.21 di Supply Chain Management, questa funzionalità è attivata per impostazione predefinita. A partire dalla versione 10.0.25 di Supply Chain Management, questa funzionalità è obbligatoria.
1. *Stampa etichetta dal dispositivo scheda processo*<br>A partire dalla versione 10.0.25 di Supply Chain Management, questa funzionalità è obbligatoria.

### <a name="allow-locking-of-touch-screen"></a>Consenti blocco del touchscreen

A partire dalla versione 10.0.21 di Supply Chain Management, questa funzionalità è attivata per impostazione predefinita. A partire dalla versione 10.0.25 di Supply Chain Management, questa funzionalità è obbligatoria e non può essere disattivata. Se si sta eseguendo una versione precedente alla versione 10.0.25, gli amministratori possono attivare o disattivare questa funzionalità cercando la funzionalità *Funzionalità per bloccare il dispositivo scheda processo e il terminale scheda processo di modo che possano essere puliti* nell'area di lavoro [Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

## <a name="manage-your-device-configurations"></a>Gestisci configurazioni dispositivo

Per configurare le configurazioni di dispositivo, andare a **Controllo produzione > Impostazioni > Esecuzione produzione > Configura scheda processo per dispositivi**. Viene aperta la pagina **Configura scheda processo per dispositivi** che mostra un elenco di configurazioni esistenti. In questa pagina, è possibile effettuare le operazioni seguenti: 

- Selezionare qualsiasi configurazione di dispositivo elencata nella colonna di sinistra per visualizzarla e modificarla.
- Selezionare **Nuovo** nel riquadro azioni per aggiungere una nuova configurazione di dispositivo all'elenco. Immettere quindi un nome nel campo **Configurazione** per identificare la nuova configurazione. Il valore inserito qui deve essere univoco tra tutte le configurazioni di dispositivo e non sarà possibile modificarlo in un secondo momento.

Fare riferimento alle sezioni seguenti per dettagli su ciascuna impostazione per la configurazione dei dispositivi scheda lavoro.

## <a name="general-settings"></a>Impostazioni generali

La Scheda dettaglio **Generale** consente di configurare ciascuna delle varie opzioni disponibili per la configurazione di dispositivo selezionata. Sono disponibili le impostazioni seguenti:

- **Segnala quantità all'uscita** - Impostare questa opzione su **Sì** per richiedere ai lavoratori di fornire il loro feedback sui lavori in corso quando timbrano il cartellino. Se impostato su **No**, ai lavoratori non verrà richiesto di eseguire questa operazione.
- **Blocca dipendente** - Quando questa opzione è impostata su **No**, ogni lavoratore verrà disconnesso immediatamente dopo aver effettuato una registrazione (ad esempio un nuovo lavoro), quindi il dispositivo tornerà alla pagina di accesso. Quando questa opzione è impostata su **Sì**, ciascun lavoratore rimarrà connesso al dispositivo scheda lavoro. Tuttavia, il lavoratore sarà ancora in grado di disconnettersi manualmente per consentire a un altro lavoratore di accedere mentre il dispositivo scheda lavoro rimane in esecuzione con lo stesso account utente del sistema. Per ulteriori informazioni su questi tipi di account, vedere [Utenti assegnati](#assigned-users).
- **Lettore di codici a barre** - Impostare questa opzione su **Sì** per fornire un'opzione sul dispositivo scheda lavoro che consenta ai lavoratori di registrare l'inizio di un nuovo lavoro eseguendo la scansione di un codice a barre.
- **Utilizza ora di registrazione effettiva** - Impostare questa opzione su **Sì** affinché l'ora di ogni nuova registrazione sia uguale all'ora esatta in cui la registrazione è stata presentata da un lavoratore. Impostarla su **No** per utilizzare l'ora di accesso. Di solito la si imposta su **Sì** se sono state abilitate le opzioni **Blocca dipendente** e/o **Singolo lavoratore** dove i lavoratori rimangono spesso connessi per periodi più lunghi.
- **Singolo Lavoratore** - Impostare questa opzione su **Sì** se un solo lavoratore utilizza ciascun dispositivo scheda lavoro in cui è attiva questa configurazione. Quando questa opzione è selezionata, l'opzione **Blocca dipendente** viene automaticamente impostata su **Sì**. Inoltre, questa opzione rimuove la necessità (e la possibilità) per il lavoratore di accedere utilizzando un ID badge (o simile). Al contrario, il lavoratore accede a Supply Chain Management utilizzando un account utente di sistema collegato a un *lavoratore registrato nel tempo* (nella tabella *lavoratori*) e si connette al dispositivo scheda lavoro come quel lavoratore nello stesso tempo.  Per ulteriori informazioni su questi tipi di account, vedere [Utenti assegnati](#assigned-users).
- **Consenti ai lavoratori di impostare filtri personali** - Impostare questa opzione su **Sì** per consentire ai lavoratori di filtrare i lavori che vedono sul dispositivo. Il lavoratore può modificare i valori per uno dei tre criteri di filtro: **Unità di produzione**, **Gruppo di risorse** e **Risorsa**. Nel dispositivo verranno visualizzati solo i lavori pianificati su risorse che corrispondono ai criteri di filtro selezionati. È inoltre possibile assegnare valori predefiniti per uno o tutti questi criteri, che verranno applicati anche se questa opzione non è selezionata.
- **Consenti blocco del touchscreen** - Impostare questa opzione su **Sì** per consentire ai lavoratori di bloccare il touchscreen del dispositivo scheda lavoro di modo che possano pulirlo. Se questa opzione è abilitata, un pulsante **Blocca schermo per pulizia** viene aggiunto alla pagina di accesso del dispositivo. Quando un lavoratore seleziona questo pulsante, il touchscreen si blocca temporaneamente per impedire un'immissione involontaria e viene visualizzato un conto alla rovescia. L'operatore può ora pulire in sicurezza il dispositivo e lo schermo. Al termine del conto alla rovescia, il touchscreen si sblocca automaticamente.
- **Durata blocco schermo** - Quando l'opzione **Consenti blocco del touchscreen** è abilitata, utilizzare questa opzione per specificare il numero di secondi in cui il touchscreen deve essere bloccato per la pulizia. La durata deve essere un numero tra 5 e 120 secondi.
- **Unità di produzione** - Selezionare un'unità di produzione da applicare come criterio di filtro predefinito per l'elenco dei lavori visibili a ciascun lavoratore. Solo i lavori programmati su risorse raggruppate sotto l'unità di produzione selezionata verranno inizialmente visualizzati dal dispositivo. Se l'opzione **Consenti ai lavoratori di impostare filtri personali** è abilitata, i lavoratori saranno in grado di modificare questo valore, altrimenti questo filtro si applicherà sempre quando questa configurazione di dispositivo è attiva.
- **Gruppo di risorse** - Selezionare un gruppo di risorse da applicare come criterio di filtro predefinito per l'elenco dei lavori visibili a ciascun lavoratore. Solo i lavori programmati su risorse raggruppate sotto il gruppo di risorse selezionato verranno inizialmente visualizzati dal dispositivo. Se l'opzione **Consenti ai lavoratori di impostare filtri personali** è abilitata, i lavoratori saranno in grado di modificare questo valore, altrimenti questo filtro si applicherà sempre quando questa configurazione di dispositivo è attiva.
- **Risorsa** - Selezionare una risorsa da applicare come criterio di filtro predefinito per l'elenco dei lavori visibili a ciascun lavoratore. Solo i lavori programmati sulla risorsa selezionata verranno inizialmente visualizzati dal dispositivo. Se l'opzione **Consenti ai lavoratori di impostare filtri personali** è abilitata, i lavoratori saranno in grado di modificare questo valore, altrimenti questo filtro si applicherà sempre quando questa configurazione di dispositivo è attiva.
- **Genera targa** - Impostare questa opzione su **Sì** per generare una nuova targa ogni volta che un lavoratore utilizza il dispositivo scheda lavoro per la dichiarazione di finito. Il numero di targa viene generato da una sequenza numerica impostata nella pagina **Parametri di gestione magazzino**. Quando impostata su **No**, i lavoratori devono specificare una targa esistente al momento della dichiarazione di finito.
- **Stampa etichetta** - Impostare questa opzione su **Sì** per stampare l'etichetta di una targa quando un lavoratore utilizza il dispositivo scheda lavoro per la dichiarazione di finito. La configurazione dell'etichetta è impostata nella distribuzione dei documenti, come descritto in [Layout di distribuzione del documento per le etichette della targa](../warehousing/document-routing-layout-for-license-plates.md).

<a name="assigned-users"></a>

## <a name="assigned-users"></a>Utenti assegnati

Utilizzare la Scheda dettaglio **Utenti assegnati** per associare uno o più utenti del sistema alla configurazione corrente del dispositivo. A ciascun utente del sistema può essere assegnata una sola configurazione di dispositivo di lavoro.

Quando si configura un dispositivo, un lavoratore IT in genere accede a Supply Chain Management utilizzando un account utente di sistema. Successivamente, la configurazione di dispositivo di lavoro associata a tale utente di sistema si applica fino a quando l'utente di sistema rimane connesso. Questi account utente di sistema sono in genere limitati per consentire l'accesso solo alla pagina del dispositivo scheda lavoro e a nessun'altra parte di Supply Chain Management.

Dopo che l'utente di sistema ha effettuato l'accesso e viene caricata la configurazione del dispositivo di lavoro, i lavoratori possono accedere al dispositivo scheda lavoro utilizzando il loro account *lavoratore registrato nel tempo* (ad esempio, eseguendo la scansione di un codice a barre sul loro badge) di modo che possano iniziare nuovi lavori ed effettuare altri tipi di registrazioni. Vari lavoratori possono accedere e disconnettersi durante il giorno, mentre la stessa configurazione di dispositivo rimane attiva su quella macchina poiché l'utente di sistema rimane connesso a Supply Chain Management per tutta la giornata.

Tuttavia, come menzionato in precedenza, quando si utilizza una configurazione di dispositivo con l'opzione **Singolo lavoratore**, i lavoratori stessi in genere accedono a Supply Chain Management utilizzando un utente di sistema collegato al proprio account *lavoratore registrato nel tempo*, quindi caricano la configurazione di dispositivo e accedono come lavoratore sul dispositivo scheda lavoro nello stesso tempo.

## <a name="additional-resources"></a>Risorse aggiuntive

[Dichiarazione di finito dal dispositivo scheda processo](report-finished-job-device.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]