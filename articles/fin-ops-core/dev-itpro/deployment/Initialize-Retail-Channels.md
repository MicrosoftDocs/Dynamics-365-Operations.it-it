---
title: Inizializzare Commerce Scale Unit (cloud)
description: Questo articolo spiega come inizializzare Commerce Scale Unit (cloud) in Microsoft Dynamics 365 Commerce.
author: jashanno
ms.date: 06/03/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: jashanno
ms.search.validFrom: 2018-04-30
ms.openlocfilehash: 25ca054df6422370b1e61dff7965189ad90d7fcc
ms.sourcegitcommit: 7bcaf00a3ae7e7794d55356085e46f65a6109176
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2022
ms.locfileid: "9357660"
---
# <a name="initialize-commerce-scale-unit-cloud"></a>Inizializzare Commerce Scale Unit (cloud)

[!include[banner](../includes/banner.md)]

Questo articolo spiega come inizializzare Commerce Scale Unit (cloud) in Microsoft Dynamics 365 Commerce.

Se stai utilizzando un ambiente sandbox di livello 2 o un ambiente di produzione con la versione dell'applicazione 8.1.2.x o successiva, devi inizializzare Commerce Scale Unit (cloud) prima di poter utilizzare la funzionalità del canale di vendita al dettaglio per le operazioni POS (Point of sale) o per operazioni di e-commerce che utilizzano Retail Server nel cloud. L'inizializzazione distribuirà una Commerce Scale Unit (cloud).

> [!IMPORTANT]
> Per i clienti esistenti che utilizzano la funzionalità del canale di vendita al dettaglio nel cloud, per garantire un supporto continuo e ininterrotto per la tua azienda, viene richiesto di aggiornare i tuoi canali di vendita al dettaglio per utilizzare Commerce Scale Unit. I nuovi ambienti distribuiti senza Commerce Scale Unit non riceveranno più aggiornamenti di qualità e servizio per i componenti del canale di vendita al dettaglio ospitato nel cloud. Non è richiesta alcuna azione per i clienti che utilizzano esclusivamente Commerce Scale Unit (self-hosted). Contatta il tuo Microsoft FastTrack Solution Architect se hai bisogno di un'estensione.

## <a name="prerequisites"></a>Prerequisiti

1. Distribuisci un ambiente sandbox di livello 2 o un ambiente di produzione con versione 8.1.2.x o successiva.
2. Puoi distribuire autonomamente fino a 2 Commerce Scale Unit per ambiente. Se hai bisogno di più di 2 Commerce Scale Unit per ambiente, in Microsoft Dynamics Lifecycle Services (LCS), crea una richiesta di supporto e immetti **Richiesta di Commerce Scale Unit aggiuntiva**, quindi indica l'ID ambiente, il numero di Commerce Scale Unit e le aree del datacenter desiderate. La richiesta sarà completata entro cinque giorni lavorativi. Se non sono necessarie più di 2 Commerce Scale Unit per ambiente, non è necessario creare una richiesta di supporto. 
3. È necessario disporre delle autorizzazioni di proprietario del progetto in Lifecycle Services prima di poter inizializzare Commerce Scale Unit.
4. Assicurati che le chiavi di configurazione della licenza Retail siano abilitate nel tuo ambiente. Per altre informazioni, vedi [Report su codici di licenza e chiavi di configurazione](../sysadmin/license-codes-configuration-keys-report.md). È necessario che i seguenti tasti siano attivati per utilizzare Commerce Scale Unit.

    - RetailBasic
    - RetaileCommerce - Se prevedi di utilizzare l'e-commerce per Dynamics 365 Commerce.
    - RetailGiftCard - Se prevedi di utilizzare gift card.
    - RetailInvent - Se prevedi di utilizzare l'inventario.
    - RetailModernPos - Se prevedi di utilizzare il punto vendita (POS).
    - RetailReplenishment - Se prevedi di utilizzare i rifornimenti.
    - RetailScheduler
    - RetailStores - Se prevedi di utilizzare POS.


## <a name="region-availability"></a>Disponibilità regionale
Commerce Scale Unit è disponibile per la distribuzione nelle seguenti aree geografiche.

| Posizione globale | Area geografica              | Disponibilità        | Commenti                  |
|-----------------|---------------------|---------------------|---------------------------|
| AMERICHE        | Stati Uniti orientali             | Generalmente disponibile |  Nessun commento.                         |
| AMERICHE        | Stati Uniti orientali 2           | Generalmente disponibile |  Nessun commento.                          |
| AMERICHE        | Stati Uniti centro-settentrionali    | Capacità limitata    |  Nessun commento.                            |
| AMERICHE        | Stati Uniti centro-meridionali    | Capacità limitata    |  Nessun commento.                            |
| AMERICHE        | Stati Uniti centrali          | Generalmente disponibile |  Nessun commento.                            |
| AMERICHE        | Stati Uniti occidentali             | Generalmente disponibile |  Nessun commento.                            |
| AMERICHE        | Stati Uniti occidentali 2           | Generalmente disponibile |  Nessun commento.                            |
| AMERICHE        | Canada centrale      | Capacità limitata    |  Nessun commento.                            |
| AMERICHE        | Canada orientale         | Capacità limitata    |   Nessun commento.                           |
| AMERICHE        | Stati Uniti centro-occidentali     | Capacità limitata    |   Nessun commento.                           |
| Asia Pacifico            | Australia orientale      | Generalmente disponibile |   Nessun commento.                           |
| Asia Pacifico            | Asia sud-orientale      | Capacità limitata | Non sono consentite distribuzioni.    |
| Asia Pacifico            | Giappone orientale          | Generalmente disponibile |  Nessun commento.                            |
| Asia Pacifico            | Giappone occidentale          | Generalmente disponibile |   Nessun commento.                           |
| Asia Pacifico            | Australia sud-orientale | Generalmente disponibile |   Nessun commento.                           |
| Asia Pacifico            | Asia orientale           | Capacità limitata    |   Nessun commento.                           |
| Asia Pacifico            | India meridionale         | Capacità limitata | Non sono consentite distribuzioni.    |
| Asia Pacifico            | India centrale       | Capacità limitata    | Richiede il processo di approvazione. |
| EMEA            | Europa occidentale         | Generalmente disponibile    |  Nessun commento. |
| EMEA            | Europa settentrionale        | Generalmente disponibile    |  Nessun commento. |
| EMEA            | Regno Unito meridionale            | Generalmente disponibile |    Nessun commento.                          |
| EMEA            | Regno Unito occidentale             | Generalmente disponibile |    Nessun commento.                          |
| Svizzera     | Svizzera settentrionale   | Capacità limitata    | Richiede il processo di approvazione. |
| Emirati Arabi Uniti             | Emirati Arabi Uniti settentrionali           | Capacità limitata    | Richiede il processo di approvazione. |

La capacità di distribuzione nelle aree geografiche a capacità limitata è estremamente limitata. Le richieste di distribuzione vengono valutate caso per caso. Se hai un'esigenza aziendale impellente per la distribuzione in aree geografiche a capacità limitata, puoi presentare una richiesta di supporto da aggiungere alla lista d'attesa. Le aree con limitazione di capacità attualmente non consentono la distribuzione di Commerce Scale Unit. 

![Mappa che mostra la disponibilità nell'area geografica.](media/Commerce-Scale-Unit-Region-Availability.png "Mappa che mostra la disponibilità nell'area geografica")

## <a name="initialize-commerce-scale-unit-as-part-of-a-new-environment-deployment"></a>Inizializzare Commerce Scale Unit come parte di una nuova distribuzione dell'ambiente

Assicurati che la sede sia disponibile. Ciò è necessario per registrare l'unità di scala presso la sede centrale durante il processo di inizializzazione. Non è consigliabile inizializzare un'unità di scala quando la sede centrale è in manutenzione, poiché potrebbe non essere disponibile durante il processo di manutenzione.

1. Assicurati che l'ambiente della sede centrale sia disponibile e non in [Modalità di manutenzione](../sysadmin/maintenance-mode.md).
2. In LCS, nella pagina dei dettagli dell'ambiente, seleziona **Funzionalità ambiente \> Commerce**.
3. Nella pagina di distribuzione della configurazione di Commerce seleziona **Inizializza**.
4. Seleziona la versione di Commerce Scale Unit da inizializzare.
5. Seleziona un'area geografica in cui inizializzare Commerce Scale Unit.

## <a name="configure-channels-to-use-commerce-scale-unit"></a>Configurare i canali per utilizzare Commerce Scale Unit

Dopo che Commerce Scale Unit è stata distribuita, devi assicurarti che i tuoi canali siano configurati per utilizzare il database per essa. 

Per configurare i tuoi canali per l'utilizzo del database Commerce Scale Unit, segui questi passaggi.

1. In Commerce headquarters accedere a **Vendita al dettaglio e commercio \> Impostazione sedi centrali \> Utilità di pianificazione di commercio \> Database del canale**.
1. Nel riquadro a sinistra, seleziona un database del canale.
1. Nella Scheda dettaglio **Canale di vendita al dettaglio**, seleziona **Aggiungi**, quindi seleziona il tuo canale di vendita al dettaglio nell'elenco a discesa.
1. Seleziona **Aggiungi**, quindi seleziona il tuo canale online nell'elenco a discesa. 

Al termine, vai a **Vendita al dettaglio e commercio \> Vendita al dettaglio e commercio IT \> Programmazione della distribuzione** ed esegui il processo 9999.

> [!NOTE] 
> Il processo 9999 sincronizza tutti i nuovi prodotti e clienti con Commerce Scale Unit. Il processo può richiedere diverso tempo. Se il canale deve essere disponibile solo per la configurazione del generatore di siti di e-commerce, puoi eseguire il processo 1070 anziché il processo 9999.

### <a name="database-refresh-and-commerce-scale-units"></a>Aggiornamento del database e Commerce Scale Unit

Prima di iniziare, assicurati di avere familiarità con i [Passaggi da completare dopo un aggiornamento del database per gli ambienti che utilizzano la funzionalità Commerce](../database/database-refresh.md).

I record del database del canale dell'unità di scala (nel modulo Database del canale) non possono essere spostati tra gli ambienti come parte dell'aggiornamento del database. Questo perché i record rappresentano la configurazione specifica dell'ambiente.

Dopo l'aggiornamento del database, è possibile rigenerare il record del database di canale dell'unità di scala emettendo una nuova distribuzione dell'unità di scala in LCS. Qualsiasi operazione di distribuzione o manutenzione nell'unità di scala tenterà di registrare l'unità di scala presso la sede centrale, se la registrazione viene rilevata come mancante.

È possibile eseguire una nuova distribuzione dell'unità di scala, senza modificare alcun componente, scegliendo di distribuire la stessa versione in cui si trova già l'unità di scala. Questo può essere fatto in LCS con i seguenti passaggi:

1. In LCS, nella pagina dei dettagli dell'ambiente, seleziona **Funzionalità ambiente \> Retail**.
2. Nella pagina di distribuzione della configurazione, seleziona l'unità di scala che desideri ridistribuire.
3. Nel menu operativo dell'unità di scala, seleziona **Aggiorna**.
4. Sul dispositivo di scorrimento, sul menu a discesa per **Seleziona versione**, scegli l'opzione **Specifica una versione**.
5. Nella casella di testo sotto **Specifica una versione**, digita la versione mostrata per la tua unità di scala, mostrata accanto all'etichetta **Versione corrente**.
6. Fai clic sul pulsante **Aggiorna**.

Non è necessario selezionare **Aggiorna estensioni**, anche se sono state applicate estensioni in precedenza, poiché l'ultimo pacchetto di estensioni applicato all'unità di scala viene selezionato automaticamente durante l'aggiornamento di un'unità di scala.

Se disponi di più unità di scala, devi eseguire l'operazione sopra per ciascuna unità di scala. Puoi eseguire queste operazioni in parallelo, se lo desideri.

## <a name="deploy-additional-commerce-scale-units-optional"></a>Distribuire altre Commerce Scale Unit (facoltativo)

Dopo aver inizializzato Commerce Scale Unit, puoi distribuire automaticamente una seconda unità di scala se la tua licenza te lo consente. Per distribuire più di due unità di scala, è necessario creare una richiesta di supporto. Nella richiesta di supporto, indica il numero di Commerce Scale Unit di cui hai bisogno, il nome dell'ambiente e le aree geografiche desiderate. Per ulteriori informazioni sulle licenze, consulta [la guida alle licenze di Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544&clcid=0x409). 

Per ogni Commerce Scale Unit aggiuntiva che distribuisci, ti consigliamo di creare un gruppo di database di canale separato seguendo questi passaggi.

1. Nella sede centrale di Commerce, accedi a **Vendita al dettaglio e commercio > Retail Headquarters > Configurazione Retail Scheduler >Gruppo di database del canale**.
2. Creare un nuovo gruppo di database canale.
3. Vai a **Vendita al dettaglio e commercio > Retail Headquarters > Configurazione Retail Scheduler > Database dei canali** e seleziona il database del canale che corrisponde alla Commerce Scale Unit appena creata.
4. Seleziona **Modifica** e seleziona il nuovo gruppo di database dei canali.
5. Seleziona **Salva**.
6. Seleziona **Esegui sincronizzazione dati completa** per il database del canale selezionato.

## <a name="additional-considerations-if-you-initialize-cloud-hosted-commerce-channel-components-in-an-existing-environment"></a>Considerazioni aggiuntive se inizializzi i componenti del canale Commerce ospitati nel cloud in un ambiente esistente

Se stai già utilizzando componenti del canale Commerce ospitati nel cloud in un ambiente, l'inizializzazione di Commerce Scale Unit aiuterà a ridurre i tempi di inattività quando tali componenti vengono aggiornati. È necessaria una pianificazione aggiuntiva prima dell'inizializzazione di Commerce Scale Unit.

Quando inizializzi la prima Commerce Scale Unit in un ambiente che utilizza i componenti del canale Commerce ospitato nel cloud, il processo di inizializzazione migra i canali associati ai componenti del canale ospitato nel cloud alla prima unità di scala. I canali associati alle unità di scala del punto vendita non sono interessati.

Il processo di migrazione è trasparente ai canali. Dopo l'avvio dell'inizializzazione dell'unità di scala, vengono eseguite automaticamente le seguenti operazioni:

1. Verrà creata una nuova Commerce Scale Unit che verrà associata all'ambiente.
2. La Commerce Scale Unit verrà registrata come database di canale disponibile nella sede centrale.
3. Tutti i canali mappati al database dei canali **Predefinito** nella sede centrale verranno aggiornati per il mapping alla nuova Commerce Scale Unit.
4. Una sincronizzazione completa dei dati Commerce Data Exchange (CDX) verrà eseguita per trasferire i dati del canale sulla nuova unità di scala.

**Pianificazione e test per l'inizializzazione di Commerce Scale Unit** Come regola generale, durante l'inizializzazione di Commerce Scale Unit, è necessario pianificare un periodo di inattività di cinque ore per le operazioni del punto vendita e per tutte le operazioni del canale di e-commerce che utilizzano Retail Server o Cloud Point of Sale.

1. Esegui un aggiornamento del database dal tuo ambiente di produzione a un ambiente UAT sandbox. 
2. Inizializza Commerce Scale Unit nell'ambiente UAT sandbox. 
3. Prendi nota del tempo di inizializzazione da completare per Commerce Scale Unit. Questo sarà paragonabile al tempo impiegato da questa operazione nell'ambiente di produzione, durante il quale le operazioni del punto vendita e le operazioni di e-commerce non saranno disponibili.

È necessario eseguire i seguenti passaggi aggiuntivi prima di inizializzare Commerce Scale Unit.

- **Chiudi tutti i turni del punto vendita** - Dopo la migrazione, gli utenti POS non potranno chiudere i turni attivi durante il processo di migrazione.
- **Convalida che tutti i processi P siano stati completati con successo** - Si consiglia di completare i processi P per sincronizzare le transazioni in sospeso prima dell'inizializzazione della CSU.
- **Esci da tutti i dispositivi POS** - Le operazioni POS non sono supportate durante la migrazione.
- **Richiama e annulla tutte le transazioni sospese nel punto vendita** - Le transazioni sospese non vengono conservate come parte dell'inizializzazione.

> [!IMPORTANT]
> Nell'ambito dell'inizializzazione di Commerce Scale Unit, le transazioni sospese precedenti andranno perse e non potranno essere richiamate. 

Ecco cosa succede durante il periodo di inizializzazione:

- I canali Commerce ospitati nel cloud non funzioneranno, a meno che non attivi la funzionalità POS offline.
- I dispositivi POS con funzionalità offline attiva avranno funzionalità ridotte.
- Tutti i client di e-commerce che dipendono da Retail Server verranno interrotti.
- I canali ospitati su Commerce Scale Unit (auto-ospitati) non saranno interessati.
- La funzionalità della sede centrale non è interessata.

Ecco cosa succede dopo che l'inizializzazione è stata completata:

- Lo stato di attivazione del dispositivo di tutti i dispositivi POS attivati viene mantenuto, il che significa che i dispositivi non dovranno essere riattivati.
- Le istanze di stazioni hardware autonome continueranno a funzionare.
- I report lato canale POS verranno reimpostati e non mostreranno i dati precedenti all'inizializzazione.
- Anche l'operazione di visualizzazione del giornale di registrazione verrà reimpostata e non verranno visualizzati i dati precedenti all'inizializzazione.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
