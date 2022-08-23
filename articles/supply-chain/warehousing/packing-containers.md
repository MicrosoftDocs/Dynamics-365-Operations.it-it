---
title: Imballare contenitori per la spedizione
description: In questo articolo viene descritto il processo di imballaggio che ti consente di convalidare articoli di magazzino e di imballarli in contenitori.
author: perlynne
ms.date: 7/13/2022
ms.topic: business-process
ms.search.form: WHSLocationType, WHSLocationProfile, WHSParameters, WHSContainerType, WHSPackProfile, WHSCloseContainerProfile, InventLocationIdLookup, UnitOfMeasureLookup, WHSPack, WHSContainerTable,
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2022-08-01
ms.dyn365.ops.version: 10.0.29
ms.openlocfilehash: 171b9f1dcb1d4ece63bc0beeb71f45b9f8ae7bba
ms.sourcegitcommit: c98d55a4a6e27239ae6b317872332f01cbe8b875
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/02/2022
ms.locfileid: "9220610"
---
# <a name="pack-containers-for-shipment"></a>Imballare contenitori per la spedizione

[!include [banner](../../includes/banner.md)]

Il processo di imballaggio di contenitori ti consente di convalidare gli articoli di magazzino e di imballarli in contenitori. Durante tale processo, gli addetti al magazzino in genere prelevano articoli di magazzino dalle aree di stoccaggio in blocco e li spostano in un'area di imballaggio. In quell'area, più addetti al magazzino controllano le quantità e i tipi di articoli e li assegnano alle dimensioni di contenitore appropriate. Quando un contenitore è completamente imballato, viene chiuso e spostato alla banchina di uscita per essere spedito.

I contenitori rappresentano le strutture fisiche in cui vengono imballati gli articoli ed è possibile tenere traccia delle informazioni relative ai contenitori nel sistema. Queste informazioni possono essere utili durante la pianificazione del trasporto, soprattutto se si calcolano le spese di spedizione in base ai contenitori. Prima della spedizione, puoi visualizzare il numero di contenitori utilizzati in una spedizione, i tipi di contenitori utilizzati e le dimensioni fisiche di ogni contenitore (come il peso e il volume totale).

Varie funzionalità di magazzino in uscita correlate possono essere utilizzate con i contenitori. Per ulteriori informazioni, vedere gli articoli seguenti:

- [Containerizzazione del ciclo](wave-containerization.md)
- [Ordinamento in uscita](outbound-sorting.md)
- [Spedizione pacchi di piccole dimensioni](small-parcel-shipping.md)
- [Conferma e trasferimento](confirm-and-transfer.md)
- [Impostare dimensioni diverse per l'imballaggio e l'immagazzinamento](packing-vs-storage-dimensions.md)
- [Lavoro di imballaggio per l'imballaggio di contenitori in uscita e l'elaborazione di spedizioni](packing-work.md)
<!-- KFM: Add link to upcoming topic when available (10.0.31): [Manual packing on the Warehouse management mobile app](manual-packing-on-the-warehouse-management-mobile-app.md) -->

## <a name="set-up-your-warehouse-to-use-manual-packing-operations"></a>Configurare il magazzino per utilizzare operazioni di imballaggio manuale

Esistono due modi basilari per organizzare le operazioni in uscita:

- **Creazione ed elaborazione dei cicli**: i lavoratori prelevano gli articoli in base al lavoro di magazzino in uscita. Li dispongono quindi direttamente in un'ubicazione di spedizione in uscita, dove sono pronti per una spedizione immediata. Per informazioni sulla configurazione e sull'utilizzo di questo processo, vedi [Creazione ed elaborazione dei cicli](wave-processing.md).
- **Imballaggio manuale nelle stazioni di imballaggio**: questo processo prevede un'operazione aggiuntiva tra le operazioni di prelievo e spedizione. Anziché collocare gli articoli in un'*ubicazione di spedizione finale*, i lavoratori li mettono in un'*ubicazione di imballaggio*. Gestiscono quindi il processo di imballaggio presso la stazione di imballaggio utilizzando la pagina **Imballaggio** nel client web. Per abilitare questo processo, devi configurare il sistema come descritto in questa sezione.

### <a name="set-up-warehouse-locations-for-packing"></a>Configurare ubicazioni di magazzino per l'imballaggio

Devi disporre di almeno un'ubicazione di imballaggio dove i lavoratori collocheranno gli articoli di magazzino di modo che possano essere imballati in contenitori. Per ulteriori informazioni su come creare ubicazioni di magazzino, vedi [Configurare le ubicazioni in un magazzino abilitato WMS](tasks\configure-locations-wms-enabled-warehouse.md). Le seguenti sottosezioni descrivono come creare e configurare ubicazioni di imballaggio.

#### <a name="set-up-location-types-for-packing"></a>Configurare tipi di ubicazione per l'imballaggio

Devi definire un *tipo di ubicazione* per le ubicazioni di imballaggio. I tipi di ubicazione possono essere utilizzati come opzioni di filtro per verificare i diversi processi di gestione del magazzino. Il nome di un tipo di ubicazione in genere descrive come quel tipo di ubicazione deve essere usato. Il tipo di ubicazione che configuri deve essere associato a ogni ubicazione utilizzata per le operazioni di imballaggio.

Segui questi passaggi per configurare un tipo di ubicazione.

1. Andare a **Gestione magazzino \> Impostazioni \> Magazzino \> Tipi di ubicazione**.
1. Nel riquadro Azioni, seleziona **Nuovo** per aggiungere un tipo di ubicazione alla griglia.
1. Imposta i seguenti campi per il nuovo tipo di ubicazione:

    - **Tipo di ubicazione**: immetti un nome per il tipo di ubicazione. Ogni nome deve essere univoco e deve descrivere l'uso previsto del tipo di ubicazione.
    - **Descrizione**: immetti una breve descrizione del tipo di ubicazione.

#### <a name="inform-the-system-about-the-packing-location-type"></a>Informare il sistema sul tipo di ubicazione di imballaggio

Dopo aver creato un tipo di ubicazione, devi configurare il sistema di modo che lo riconosca come tipo di ubicazione da utilizzare per le operazioni di imballaggio.

Attieniti alla procedura seguente per impostare il tipo di ubicazione utilizzato per le operazioni di imballaggio.

1. Vai a **Gestione magazzino \> Impostazioni \> Parametri di gestione magazzino**
2. Nella scheda **Generale**, nella Scheda dettaglio **Tipi di ubicazione**, imposta il campo **Tipo di ubicazione imballaggio** sul tipo di ubicazione che utilizzerai per identificare le stazioni di imballaggio.

> [!NOTE]
> Se stai eseguendo l'aggiornamento da una versione di Microsoft Dynamics AX, nota che lo stato *In imballaggio* è stato rimosso da spedizioni e carichi poiché non funzionava in modo coerente e generava dati ridondanti. Le pagine di elenco **In spedizioni** e **Carichi in imballaggio** sono state quindi deprecate. I container che devono essere imballati vengono tracciati a livello di ubicazione.
>
> Nelle versioni precedenti, l'ubicazione di imballaggio viene definita utilizzando il campo **ID profilo per l'ubicazione imballaggio** nella scheda **Imballaggio** della pagina **Parametri di gestione magazzino** per specificare un *profilo di ubicazione*. Nella versione corrente, usi il campo **Tipo di ubicazione imballaggio** della scheda **Generale** della pagina **Parametri di gestione magazzino** per specificare un *tipo di ubicazione*, come descritto in questo articolo. Il nuovo campo è meglio allineato al processo di identificazione delle ubicazioni di gestione temporanea e di spedizione finale.
>
> Sebbene sia possibile continuare a usare il vecchio campo **ID profilo per l'ubicazione imballaggio**, ti consigliamo di iniziare a utilizzare il nuovo campo **Tipo di ubicazione imballaggio** poiché il primo verrà deprecato.
>
> Se deselezioni l'impostazione del vecchio campo **ID profilo per l'ubicazione imballaggio** e quindi salvi la pagina, il campo verrà disabilitato in modo permanente. Per le installazioni dove il campo **ID profilo per l'ubicazione imballaggio** non è mai stato utilizzato, sarà sempre disabilitato. Dopo aver deselezionato l'impostazione del campo **ID profilo per l'ubicazione imballaggio**, utilizza le impostazioni descritte in questo articolo per configurare e identificare l'ubicazione di imballaggio.

#### <a name="set-up-location-profiles-for-packing-locations"></a>Configurare profili di ubicazione per ubicazioni di imballaggio

Ogni *profilo di ubicazione* stabilisce le informazioni e le regole che si applicano alle ubicazioni associate. Poiché è necessaria almeno un'ubicazione da utilizzare per le operazioni di imballaggio, devi creare un profilo di ubicazione oltre a un tipo di ubicazione. Ogni profilo può essere utilizzato da un numero qualsiasi di ubicazioni. Le ubicazioni utilizzate per l'imballaggio devono essere configurate per tenere traccia delle targhe.

Attieniti alla procedura seguente per configurare un profilo di ubicazione per un'ubicazione di imballaggio.

1. Vai a **Gestione magazzino \> Impostazioni \> Magazzino \> Profili ubicazione**.
1. Seleziona un profilo esistente nel riquadro elenco oppure seleziona **Nuovo** nel riquadro Azioni per crearne uno.
1. Nell'intestazione del nuovo profilo o del profilo selezionato, imposta i seguenti campi:

    - **ID profilo ubicazione**: immetti un ID univoco per il profilo.
    - **Nome**: immetti un nome descrittivo per il profilo.

1. Nella scheda dettaglio **Generale**, impostare i seguenti campi:

    - **Formato ubicazione**: seleziona il formato da utilizzare per l'ubicazione corrente. I formati di ubicazione sono un sistema di denominazione utilizzato per creare nomi univoci e coerenti per le diverse posizioni di ubicazione usate in un magazzino. Se non hai già il formato necessario, puoi crearlo in **Gestione magazzino \> Impostazioni \> Magazzino \> Formati ubicazione**. Per ulteriori informazioni, vedere [Configurare le ubicazioni in un magazzino abilitato WMS](tasks/configure-locations-wms-enabled-warehouse.md).
    - **Tipo di ubicazione**: seleziona il tipo di ubicazione impostato come tipo di ubicazione di imballaggio nella pagina **Parametri di gestione magazzino**, come descritto in precedenza in questo articolo.
    - **Usa rilevamento targa**: per le ubicazioni di imballaggio, imposta questa opzione su *Sì*. Il sistema deve essere in grado di rilevare gli ID targa nelle ubicazioni di imballaggio, in modo da poter controllare il processo di imballaggio.
    - **Consenti inventario negativo**: per le ubicazioni di imballaggio, imposta questa opzione su *No*.
    - **Consenti articoli combinati**: per le ubicazioni di imballaggio, imposta questa opzione su *Sì*. Questa impostazione è necessaria poiché in genere molti numeri di articolo differenti vengono spostati contemporaneamente alle ubicazioni di imballaggio.
    - **Consenti stati inventario combinati**: per le ubicazioni di imballaggio, imposta questa opzione su *Sì*. Questa impostazione è necessaria poiché gli articoli che hanno stati di inventario differenti in genere vengono portati contemporaneamente nelle ubicazioni di imballaggio.
    - **Consenti batch inventario combinati**: per le ubicazioni di imballaggio, imposta questa opzione su *Sì*. Questa opzione è impostata automaticamente su *Sì* ogni volta che l'opzione **Consenti articoli combinati** viene impostata su *Sì*.

#### <a name="set-up-packing-locations"></a>Configurare ubicazioni di imballaggio

Devi disporre di almeno un'*ubicazione* dove i lavoratori collocheranno gli articoli di magazzino che devono essere imballati in contenitori.

Segui questi passaggi per aggiungere un'ubicazione di imballaggio.

1. Vai a **Gestione magazzino \> Impostazioni \> Magazzino \> Ubicazioni**.
1. Nel riquadro Azioni, seleziona **Nuova** per aggiungere un'ubicazione.
1. Imposta i seguenti campi per la nuova ubicazione:

    - **Magazzino**: specifica il magazzino in cui deve esistere l'ubicazione di imballaggio.
    - **Ubicazione**: immetti un nome per la nuova ubicazione.
    - **ID profilo ubicazione**: assicurati di specificare l'ID che hai creato nella sezione precedente.

## <a name="set-up-the-packing-process"></a>Configurare il processo di imballaggio

Questa sezione descrive come configurare le impostazioni che abilitano il processo di imballaggio e consentono ai lavoratori di imballare gli articoli in contenitori.

### <a name="set-up-container-packing-policies"></a><a name="packing-policy"></a>Impostare i criteri di imballaggio dei contenitori

I *criteri di imballaggio dei contenitori* definiscono come deve essere elaborato un contenitore. Ogni volta che crei un nuovo contenitore, selezionerai anche dei criteri di imballaggio da applicare al contenitore.

Per configurare i criteri di imballaggio del contenitore, seguire questi passaggi.

1. Passare a **Gestione magazzino \> Impostazioni \> Contenitori \> Criteri imballaggio contenitore**.
1. Seleziona dei criteri esistenti nel riquadro elenco oppure seleziona **Nuovo** nel riquadro Azioni per crearne altri.
1. Nell'intestazione della politica nuova o selezionata, imposta i seguenti campi:

    - **Criteri imballaggio contenitore**: immetti un nome univoco per i criteri.
    - **Descrizione**: immetti un nome descrittivo per i criteri.

1. Nella scheda **Panoramica**, imposta i campi seguenti. Questi campi ti consentono di specificare quali azioni devono essere intraprese quando il contenitore viene chiuso, se si deve operare con o senza creazione di lavoro e quando il container deve essere rilasciato dalla stazione di imballaggio.

    - **Magazzino**: seleziona il magazzino a cui si applicano i criteri di imballaggio.
    - **Ubicazione predefinita per spedizione finale**: specifica l'ubicazione preferita per il contenitore dopo la chiusura dello stesso. Questo campo è disponibile solo quando il campo **Criteri rilascio contenitore** è impostato su *Rendi disponibile in ubicazione di spedizione finale*.
    - **Ubicazione predefinita per ordinamento**: questo campo viene utilizzato con la funzionalità [ordinamento in uscita](outbound-sorting.md).
    - **Unità peso**: seleziona l'unità di misura predefinita da utilizzare quando un contenitore viene chiuso e viene creato un manifesto. In genere, questa unità di misura sarà l'unità di misura utilizzata da una bilancia nella stazione di imballaggio. Questo campo si applica ai criteri con o senza creazione di lavoro.
    - **Criteri chiusura contenitore**: seleziona una delle seguenti opzioni per definire cosa deve accadere quando il contenitore viene chiuso:

        - *Rilascio automatico*: il contenitore si intenderà rilasciato dalla stazione di imballaggio e l'azione che è specificata nel campo **Criteri rilascio contenitore** verrà eseguita.
        - *Rilascio ritardato*: il contenitore non verrà rilasciato immediatamente dalla stazione di imballaggio. Un addetto al magazzino deve rilasciarlo manualmente in seguito.
        - *Facoltativo*: quando un lavoratore chiude il contenitore, potrà scegliere se deve essere rilasciato.

        Se la stazione di imballaggio gestisce principalmente singoli contenitori che vengono spediti direttamente ai clienti, l'approccio più naturale è quello di rilasciare immediatamente i contenitori. Se la stazione di imballaggio gestisce spedizioni composte da più contenitori o addirittura pallet, è probabilmente meglio ritardare il rilascio fino a quando l'intera spedizione o pallet non è stato imballato ed è pronto per il prelievo.

    - **Criteri rilascio contenitore**: seleziona una delle seguenti opzioni per definire cosa deve accadere quando il contenitore viene rilasciato dall'ubicazione di imballaggio:

        - *Rendi disponibile in ubicazione di spedizione finale*: aggiorna il contenitore per l'ubicazione di spedizione finale. Se selezioni questa opzione, usa il campo **Ubicazione predefinita per spedizione finale** per specificare un'ubicazione preferita per il contenitore dopo la chiusura dello stesso.
        - *Crea lavoro per spostare il contenitore dalla stazione di imballaggio*: crea lavoro per spostare il contenitore dalla stazione di imballaggio all'area di gestione temporanea o direttamente nell'area del portellone del magazzino. Usa il campo **Modello di lavoro** per specificare il modello di lavoro da applicare quando viene creato lavoro per il contenitore.
        - *Assegna contenitore alla posizione di ordinamento in uscita*: questa opzione viene utilizzata con la funzionalità [ordinamento in uscita](outbound-sorting.md).

        Nella maggior parte dei casi, è consigliabile creare lavoro per spostare i contenitori poiché questo approccio rappresenta meglio i processi manuali effettivi nel magazzino. Tuttavia, per scenari semplici o situazioni in cui la stazione di imballaggio si trova direttamente nell'area del portellone, potrebbe essere preferibile avere il contenitore immediatamente disponibile nell'ubicazione di spedizione finale.

    - **Modello di lavoro**: seleziona il modello di lavoro da applicare quando viene creato lavoro per il contenitore. Questo campo è disponibile solo quando il campo **Criteri rilascio contenitore** è impostato su *Crea lavoro per spostare il contenitore dalla stazione di imballaggio* e correlato a un tipo di ordine di lavoro denominato *Prelievo contenitore imballato*. Per ulteriori informazioni, vedi [Modelli di lavoro e direttive ubicazione](control-warehouse-location-directives.md).

    Nei passaggi rimanenti, configurerai le impostazioni correlate alla *creazione del manifesto*. Con creazione del manifesto si intende il processo che consente di specificare il peso di un contenitore, di un gruppo di contenitori o di una spedizione, insieme all'ID di traccia ricevuto da un fornitore di servizi di trasporto. Dynamics 365 Supply Chain Management non si integra con i sistemi di fornitori di trasporto esterni. Gli addetti al magazzino devono stampare le etichette ricevute dal fornitore di servizi di trasporto e quindi eseguire la scansione di un numero di tracciabilità quando completano la procedura di creazione del manifesto.

    Poiché i requisiti del manifesto variano da cliente a cliente e persino da spedizione a spedizione, i criteri di imballaggio consentono una notevole flessibilità nel flusso di lavoro. Puoi configurare manifesti per contenitori, gruppi di contenitori e spedizioni in qualsiasi combinazione.

    Se utilizzi una procedura di creazione di manifesti a più livelli, i lavoratori devono dapprima creare il manifesto di tutti i contenitori, quindi quello del gruppo di contenitori correlato e infine quello della spedizione correlata.

1. Nella Scheda dettaglio **Manifesto contenitore**, imposta i seguenti campi:

    - **Manifesto automatico alla chiusura del contenitore**: imposta questa opzione su *Sì* per applicare le informazioni del manifesto come parte del processo di chiusura del contenitore. Se non stai utilizzando l'integrazione del trasporto, le informazioni devono essere registrate manualmente.
    - **Requisiti manifesto per contenitore**: seleziona una delle seguenti opzioni:

        - *Nessuna*: non verrà utilizzato alcuno processo di creazione di manifesto.
        - *Manuale*: la creazione del manifesto sarà richiesta dal flusso di lavoro di imballaggio. Il sistema non consentirà la chiusura o il rilascio di un contenitore fino al completamento della creazione del manifesto.
        - *Gestione trasporto*: la creazione del manifesto verrà eseguita tramite i motori tariffe di Gestione trasporto (TMS). Poiché questa opzione richiede uno sviluppo personalizzato per implementare un motore specifico per il fornitore di servizi di trasporto, non funzionerà immediatamente nella versione corrente.

    - **Stampa contenuto contenitore**: imposta questa opzione su *Sì* per stampare automaticamente il report sul contenuto del contenitore quando un contenitore viene registrato come chiuso. Il report può anche essere stampato su richiesta.

1. Nella Scheda dettaglio **Manifesto gruppo di contenitori**, nel campo **Requisiti manifesto per gruppo di contenitori**, seleziona una delle seguenti opzioni:

    - *Nessuno*: il manifesto del gruppo di contenitori non sarà incluso come requisito nel flusso di lavoro di imballaggio.
    - *Manuale*: il manifesto del gruppo di contenitori sarà incluso come requisito nel flusso di lavoro di imballaggio. Tutti i contenitori nel gruppo devono essere chiusi affinché sia possibile creare il manifesto del gruppo. Seleziona questa opzione se ti viene richiesto di completare un manifesto per ogni gruppo di contenitori imballato nella stazione di imballaggio. In genere selezioni questa opzione se i contenitori sono imballati su un pallet e un manifesto viene creato per l'intero pallet.

    > [!NOTE]
    > La versione corrente non supporta i report sui manifesti per i gruppi di contenitori e non è disponibile il supporto del motore TMS per i gruppi di contenitori.

1. Nella Scheda dettaglio **Manifesto spedizione**, imposta i seguenti campi:

    - **Requisiti manifesto per spedizione**: seleziona una delle seguenti opzioni:

        - *Nessuno*: il manifesto della spedizione non sarà incluso come requisito nel flusso di lavoro di imballaggio.
        - *Manuale*: il manifesto della spedizione sarà incluso come requisito nel flusso di lavoro di imballaggio. Nessun contenitore per una spedizione può essere rilasciato fino al completamento della creazione del manifesto.
        - *Gestione trasporto*: la creazione del manifesto verrà eseguita tramite i motori tariffe di Gestione trasporto (TMS). Poiché questa opzione richiede uno sviluppo personalizzato per implementare un motore specifico per il fornitore di servizi di trasporto, non funzionerà immediatamente nella versione corrente.

        La creazione del manifesto della spedizione deve essere abilitata se devi completare un manifesto per l'intera spedizione imballata presso la stazione di imballaggio. Viene in genere utilizzata quando è richiesto un manifesto consolidato anche se la spedizione è composta da più contenitori o gruppi di contenitori.

    - **Stampa documento di trasporto**: imposta questa opzione su *Sì* per stampare automaticamente il documento di trasporto come parte del manifesto della spedizione. Il documento di trasporto può anche essere stampato su richiesta.

### <a name="set-up-container-types"></a>Impostare i tipi di contenitore

Durante il processo di imballaggio manuale, è necessario creare dapprima i contenitori affinché gli articoli possano essere imballati negli stessi. Ogni contenitore deve essere basato su un *tipo di contenitore*, che definisce la capacità di peso e volume fisico massima di un contenitore.

Per creare un tipo di contenitore, procedi come descritto di seguito.

1. Vai a **Gestione magazzino \> Impostazioni \> Contenitori \> Tipi di contenitore**.
1. Nel riquadro Azioni seleziona **Nuovo** per aggiungere un tipo di contenitore.
1. Imposta i seguenti campi per il nuovo tipo di contenitore:

    - **Codice tipo di contenitore**: immetti un ID univoco per il tipo di contenitore.
    - **Descrizione**: immetti una descrizione del nuovo tipo di contenitore.
    - **Tara**: immetti il peso effettivo o stimato del contenitore.
    - **Peso netto massimo**: immetti il peso massimo del contenitore.

1. Nella sezione **Dimensioni contenitore**, nei campi **Lunghezza**, **Larghezza**, **Altezza**, e **Volume**, immetti le dimensioni fisiche del contenitore.
1. Nella sezione **Valori massimi**, nei campi **Lunghezza**, **Larghezza**, **Altezza**, e **Volume**, immetti le dimensioni fisiche massime che il contenitore può gestire.
1. Puoi definire attributi aggiuntivi per i tipi di contenitore associati ad altre operazioni che utilizzano contenitori. Per ulteriori informazioni, vedi [Containerizzazione](wave-containerization.md).

> [!NOTE]
> Per il processo di imballaggio manuale, il sistema utilizza solo il valore del campo **Peso netto massimo** e il valore del campo **Volume** nella sezione **Valori massimi**.

### <a name="set-up-packing-profiles"></a>Impostare i profili imballaggio

Per il processo di imballaggio sono necessari *profili di imballaggio*. Questi possono essere selezionati o impostati per impostazione predefinita quando inizi un'operazione di imballaggio nella pagina **Imballaggio**.

Per configurare un profilo di imballaggio, seguire questi passaggi.

1. Andare a **Gestione magazzino \> Impostazioni \> Imballaggio \> Profili imballaggio**.
1. Seleziona un profilo esistente nel riquadro elenco oppure seleziona **Nuovo** nel riquadro Azioni per crearne uno.
1. Nell'intestazione del nuovo profilo o del profilo selezionato, imposta i seguenti campi:

    - **ID profilo imballaggio**: immetti un ID breve per il profilo.
    - **Descrizione**: immetti una descrizione del profilo di imballaggio.
    - **Criteri imballaggio contenitore**: seleziona i criteri di imballaggio che si applicano al profilo. Per ulteriori informazioni, vedi la sezione [Impostare criteri di imballaggio dei contenitori](#packing-policy) in questo articolo.
    - **Modalità ID contenitore**: scegli se un ID contenitore deve essere generato automaticamente quando viene creato un contenitore o se deve essere creato manualmente.
    - **Tipo di contenitore**: seleziona il tipo di contenitore che viene utilizzato per impostazione predefinita quando viene creato un nuovo contenitore.
    - **Crea automaticamente il contenitore alla chiusura**: seleziona questa casella di controllo per creare automaticamente un nuovo contenitore se il contenitore precedente viene chiuso e una o più righe rimangono nella spedizione corrente.

### <a name="set-up-warehouse-workers"></a>Configurare gli addetti al magazzino

Ogni utente o lavoratore che imballa i contenitori utilizzando la pagina **Imballaggio** del client Web o il codice attività *Imballaggio* nell'app per dispositivi mobili Warehouse Management deve avere un account utente associato a un record *lavoratore/persona* a cui sono assegnati i diritti di accesso di sicurezza necessari (per ulteriori informazioni su come configurare gli utenti, vedi [Creare nuovi utenti](../../fin-ops-core/dev-itpro/sysadmin/tasks/create-new-users.md)).

Segui questi passaggi per configurare un record *lavoratore/persona* per il processo di imballaggio.

1. Andare a **Gestione magazzino \> Impostazioni \> Lavoratore**.
1. Nel riquadro Azioni, seleziona **Nuovo** per aggiungere un utente di lavoro.
1. Imposta il campo **Lavoratore** sul record lavoratore esistente definito nel modulo **Risorse umane** dell'utente che completerà il processo di imballaggio.
1. Nella scheda dettaglio **Profilo**, imposta i seguenti campi:

    - **Criteri imballaggio contenitore**: seleziona criteri di imballaggio dei container che definiscano come devono essere elaborati i container presso la stazione di imballaggio. I criteri di imballaggio di contenitori selezionati saranno preselezionati per il lavoratore quando questi apre la stazione di imballaggio. Per ulteriori informazioni, vedi il seguente post di blog: [Funzionalità di imballaggio migliorate](https://cloudblogs.microsoft.com/dynamics365/no-audience/2016/12/01/improved-packing-functionality-dynamics-365-for-operations-1611).
    - **ID profilo imballaggio**: seleziona un ID profilo di imballaggio che definisce i criteri di imballaggio e le impostazioni del contenitore che devono essere utilizzate. Se l'ID profilo di imballaggio selezionato è associato a criteri di imballaggio di contenitori, non potrai modificare l'impostazione del campo **Criteri imballaggio contenitore** in questa pagina.

1. Nella Scheda dettaglio **Stazione di imballaggio predefinita**, seleziona il sito, il magazzino e l'ubicazione predefiniti che si applicano al lavoratore.
1. Se il lavoratore utilizzerà l'app per dispositivi mobili Warehouse Management per gestire e registrare il suo lavoro di imballaggio di contenitori, nella Scheda dettaglio **Utenti**, imposta uno o più account che il lavoratore può utilizzare per accedere all'app. Per ulteriori informazioni, vedi [Account utente dispositivo mobile](mobile-device-work-users.md).

## <a name="example-scenario"></a><a name="scenario"></a>Scenario di esempio

Questa sezione fornisce uno scenario di esempio che mostra come creare un ordine e imballare gli articoli.

### <a name="make-sample-data-available"></a>Rendi disponibili i dati di esempio

Per elaborare lo scenario utilizzando i record e i valori di esempio specificati qui, devi utilizzare un sistema in cui sono installati i [dati dimostrativi](../../fin-ops-core/fin-ops/get-started/demo-data.md) standard. È inoltre necessario selezionare la persona giuridica **USMF** prima di iniziare.

Puoi anche utilizzare questo scenario come guida all'uso della funzionalità in un sistema di produzione. Tuttavia, in tal caso, devi sostituire i tuoi valori per ciascuna impostazione descritta qui.

### <a name="sign-in-as-a-user-that-can-do-packing-work"></a>Accedere come utente che può svolgere operazioni di imballaggio

Accedi a Supply Chain Management utilizzando un account utente che dispone delle autorizzazioni necessarie per imballare i contenitori. L'utente *Julia Funderburk* è incluso come parte dei dati demo e dispone delle autorizzazioni necessarie. Questo utente ha l'ID utente *Amministratore*.

### <a name="create-a-sales-order-and-complete-the-work"></a>Creare un ordine cliente e completare il lavoro

Attieniti alla procedura seguente per creare un ordine cliente e completare il lavoro di spostamento di articoli ordinati nella stazione di imballaggio.

1. Seleziona **Vendite e marketing \> Ordini cliente \> Tutti gli ordini cliente**.
1. Nel Riquadro azioni selezionare **Nuovo**.
1. Nella finestra di dialogo **Crea ordine cliente**, nel campo **Conto cliente**, seleziona *US-005*.
1. Selezionare **OK** per chiudere la finestra di dialogo.
1. Il nuovo ordine cliente viene aperto e include un'unica riga vuota nella Scheda dettaglio **Righe ordine cliente**. Imposta i seguenti valori per la nuova riga ordine:

    - **Numero articolo:** *A0001*
    - **Quantità:** *2*
    - **Sito:** *6*
    - **Magazzino:** *62*

1. Quando la riga ordine è ancora selezionata, seleziona **Inventario \> Prenotazione** nella barra degli strumenti della Scheda dettaglio **Righe ordine cliente**.
1. Nella pagina **Prenotazione**, nel riquadro azioni, seleziona **Prenota lotto** per prenotare l'intera quantità della riga selezionata nel magazzino.
1. Chiudi la pagina **Prenotazione** per tornare all'ordine cliente.
1. Nel riquadro azioni, nella scheda **Magazzino**, seleziona **Rilascia in magazzino**.

    Un messaggio mostra gli ID spedizione e ciclo per l'ordine.

1. Quando la riga ordine è ancora selezionata, seleziona **Magazzino** \> **Dettagli lavoro** nella barra degli strumenti della Scheda dettaglio **Righe ordine cliente**. Se utilizzi l'elaborazione batch per eseguire i tuoi cicli, è possibile che sia necessario attendere un breve lasso di tempo per la creazione del lavoro.
1. Nella pagina **Lavoro**, nel riquadro Azioni, nella scheda **Lavoro**, seleziona **Lavoro completo**.
1. Nella pagina **Completamento lavoro**, imposta il campo **ID utente** su *62*.
1. Nel riquadro Azioni, seleziona **Convalida lavoro**.
1. Quando viene visualizzato un messaggio indicante che il tuo lavoro è valido, seleziona **Lavoro completo** per completare il processo di prelievo degli articoli di magazzino e di inserimento degli stessi nell'ubicazione *Imballaggio*.
1. Prendi nota del valore **ID spedizione** mostrato per il lavoro nella griglia superiore.

### <a name="pack-the-ordered-items-into-a-container"></a>Imballare gli articoli ordinati in un contenitore

Ora gli articoli di magazzino si trovano nell'area di imballaggio e sono pronti per essere imballati in contenitori. Segui questi passaggi per creare un nuovo contenitore nel sistema e imballarlo.

1. Andare a **Gestione magazzino \> Imballaggio e containerizzazione \> Imballaggio**.
1. Nella finestra di dialogo **Seleziona stazione di imballaggio**, imposta i seguenti valori:

    - **Sito:** *6*
    - **Magazzino:** *62*
    - **Ubicazione:** *Imballaggio*
    - **ID profilo imballaggio:** *WH62*

1. Seleziona **OK**.
1. Nella pagina **Imballaggio**, nel campo **Targa o spedizione**, immetti l'ID spedizione che hai annotato in precedenza. Ora dovresti vedere gli articoli non imballati rimanenti nella Scheda dettaglio **Righe aperte**.
1. Nel riquadro Azioni, seleziona **Nuovo contenitore** per creare un contenitore nel sistema.
1. Nella finestra di dialogo **ID del nuovo contenitore**, imposta il campo **Tipo di contenitore** su *Scatola piccola*.
1. Seleziona **OK** per creare il contenitore.
1. Seleziona **OK** per tornare alla pagina **Imballaggio**. La Scheda dettaglio **Contenitori aperti** ora mostra il valore **ID contenitore** del contenitore che hai creato.
1. Per questo scenario, imballerai per ora solo uno degli articoli ordinati. Pertanto, nella Scheda dettaglio **Imballaggio articolo**, imposta i seguenti valori:

    - **Quantità:** *1.00*
    - **Identificatore:** *A0001*

    Subito dopo aver selezionato il valore **Identificatore**, la pagina aggiorna le Schede dettaglio **Righe aperte** e **Tutte le righe** per indicare che un articolo è stato imballato. Ora dovresti aver imballato uno dei due pezzi dell'articolo *A0001*.

1. Nel riquadro azioni selezionare **Chiudi contenitore**.
1. Nella finestra di dialogo **Chiudi contenitore**, seleziona **Ottieni peso sistema** per riempire il campo **Peso lordo** con il valore predefinito.
1. Seleziona **OK** per chiudere il contenitore.

> [!TIP]
> Esistono vari modi per visualizzare i contenitori in base al contesto. Ad esempio, quando imballi una spedizione, è spesso utile visualizzare i contenitori che fanno parte della spedizione o tutti i container che si trovano fisicamente in una stazione di imballaggio. La pagina **Stazione di imballaggio** include pulsanti che puoi utilizzare per visualizzare tutti i contenitori aperti e chiusi in una stazione di imballaggio. Queste viste non sono limitate a una spedizione specifica. Possono essere molto utili nelle situazioni in cui un lavoratore sta imballando un contenitore e un altro sta creando il manifesto del contenitore e rilasciando il contenitore.
>
> È inoltre disponibile una vista consolidata di tutti i contenitori. Questa vista è utile principalmente per gli utenti che lavorano al di fuori del contesto di una singola stazione di imballaggio. Per vederla, vai a **Gestione magazzino \> Imballaggio e containerizzazione \> Contenitori**.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
