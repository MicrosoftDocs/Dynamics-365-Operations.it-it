---
title: Rendere fisicamente disponibili i prodotti finiti prima della registrazione nei giornali
description: Quando un articolo prodotto viene dichiarato finito, viene registrato come disponibile per un'ulteriore elaborazione fisica e uno o più giornali di registrazione vengono registrati. In questo articolo viene descritto come differire le registrazioni giornale consentendo l'elaborazione delle stesse mediante un processo batch in una coda di messaggi.
author: johanhoffmann
ms.date: 08/02/2022
ms.topic: article
ms.search.form: ProdParameters, JmgProdParameters, InventLocation, JmgMES3PMessageProcessorMessage
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2022-08-02
ms.dyn365.ops.version: 10.0.29
ms.openlocfilehash: 7a8327552d9e6c38721fdac9ee1795e61f90f329
ms.sourcegitcommit: 8d072505f66f507aafbaae65bedf3b530eb6cb7b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9266485"
---
# <a name="make-finished-goods-physically-available-before-posting-to-journals"></a>Rendere fisicamente disponibili i prodotti finiti prima della registrazione nei giornali

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]

Quando un lavoratore dichiara un articolo finito, il sistema lo registra come disponibile per un'ulteriore elaborazione fisica (come la spedizione o lo stoccaggio). Durante questo processo, vengono registrati anche uno o più giornali di registrazione (ad esempio il giornale di registrazione dichiarazioni di finito, il giornale di registrazione distinte di prelievo e il giornale di registrazione schede cicli di lavorazione). Se vuoi rendere fisicamente disponibili gli articoli prima che tutte le registrazioni siano state elaborate, puoi configurare il sistema in modo da differire le registrazioni giornale. Le registrazioni differite vengono quindi gestite da un processo batch che elaborerà le registrazioni come consentito dalle risorse di sistema.

L'illustrazione seguente mostra come vengono richiamati i processi per la registrazione dei giornali di registrazione sia con la registrazione differita che senza.

![Il processo Dichiarazione di finito con e senza registrazione giornale differita.](media/deferred-posting-flowchart.png "Il processo Dichiarazione di finito con e senza registrazione giornale differita")

## <a name="turn-on-deferred-journal-posting-for-your-system"></a>Attivare la registrazione giornale differita per il sistema

Prima di poter utilizzare la registrazione giornale differita, è necessario attivarla nel sistema. Gli amministratori possono utilizzare l'area di lavoro [Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) per controllare lo stato della funzionalità ed eventualmente attivarla. Nell'area di lavoro **Gestione funzionalità**, la funzione è elencata nel modo seguente:

- **Modulo:** *Controllo produzione*
- **Nome funzionalità**: *(Anteprima) Rendi fisicamente disponibili i prodotti finiti prima della registrazione nei giornali*

## <a name="set-up-journal-posting-options-for-reporting-as-finished"></a>Impostare le opzioni di registrazione giornale per la dichiarazione di finito

I lavoratori possono dichiarare gli articoli finiti utilizzando uno dei seguenti client:

- Client Web
- App per dispositivi mobili Warehouse Management
- Interfaccia di esecuzione dell'area di produzione

Il client Web utilizza la stessa configurazione del metodo di registrazione dell'app per dispositivi mobili Warehouse Management. Tuttavia, il metodo di registrazione utilizzato dall'interfaccia di esecuzione del piano di produzione deve essere configurato separatamente.

### <a name="set-journal-posting-options-for-the-web-client-and-the-warehouse-management-mobile-app"></a>Impostare le opzioni di registrazione giornale per il client Web e l'app per dispositivi mobili Warehouse Management

Nell'app per dispositivi mobili, i lavoratori dichiarano gli articoli finiti aprendo una voce di menu del dispositivo mobile in cui **Processo di creazione lavoro** è *Dichiarato finito* o *Dichiarato finito e stoccato*. Nel client Web, i lavoratori dichiarano gli articoli finiti nella pagina elenco **Tutti gli ordini di produzione** o la pagina **Ordine di produzione (dettagli)**. Puoi configurare un metodo predefinito a livello aziendale nonché impostare sostituzioni specifiche del magazzino in base alle tue esigenze.

Utilizza la procedura seguente per configurare il metodo di registrazione predefinito a livello aziendale per dichiarare gli articoli finiti nel client Web o nell'app per dispositivi mobili Warehouse Management.

1. Vai a **Controllo produzione \> Impostazioni \> Parametri di controllo produzione**.
1. Nella scheda **Giornali di registrazione**, nella sezione **Giornale di registrazione dichiarazioni di finito**, imposta il campo **Metodo di registrazione** su uno dei seguenti valori:

    - *Immediato*: quando un articolo viene dichiarato finito, il sistema elabora completamente tutte le registrazioni giornale correlate prima di contrassegnare l'articolo finito come fisicamente disponibile.
    - *Differito*: quando un articolo viene dichiarato finito, il sistema contrassegna l'articolo finito come fisicamente disponibile e aggiunge le registrazioni giornale a una coda di messaggi. Il sistema non attende che le registrazioni siano completamente elaborate prima di contrassegnare l'articolo finito come fisicamente disponibile.

Utilizza la procedura seguente per configurare le sostituzioni specifiche del magazzino per il metodo di registrazione predefinito configurato nella pagina **Parametri di controllo produzione**.

1. Vai a **Gestione inventario \> Impostazioni \> Suddivisione scorte \> Magazzini**.
1. Seleziona il magazzino che vuoi impostare.
1. Nel riquadro azioni, seleziona **Modifica**.
1. Nella Scheda dettaglio **Magazzino**, nella sezione **Ordini di produzione**, imposta il campo **Metodo di registrazione** su uno dei seguenti valori:

    - *Eredita*: il magazzino selezionato eredita l'impostazione nella pagina **Parametri di controllo produzione**.
    - *Immediato*: quando un articolo viene dichiarato finito, il sistema elabora completamente tutte le registrazioni giornale correlate prima di contrassegnare l'articolo finito come fisicamente disponibile.
    - *Differito*: quando un articolo viene dichiarato finito, il sistema contrassegna l'articolo finito come fisicamente disponibile e aggiunge le registrazioni giornale a una coda di messaggi. Il sistema non attende che le registrazioni siano completamente elaborate prima di contrassegnare l'articolo finito come fisicamente disponibile.

### <a name="set-journal-posting-options-for-the-production-floor-execution-interface"></a>Impostare le opzioni di registrazione giornale per l'interfaccia di esecuzione dell'area di produzione

Utilizza la procedura seguente per configurare il metodo di registrazione utilizzato quando gli articoli vengono dichiarati finiti nell'interfaccia di esecuzione dell'area di produzione.

1. Vai **Controllo produzione \> Impostazioni \> Esecuzione produzione \> Impostazioni predefinite ordini di produzione**.
1. Nella scheda **Dichiarazione di finito**, nella sezione **Giornale di registrazione dichiarazioni di finito**, imposta il campo **Metodo di registrazione** su uno dei seguenti valori:

    - *Immediato*: quando un articolo viene dichiarato finito, il sistema elabora completamente tutte le registrazioni giornale correlate prima di contrassegnare l'articolo finito come fisicamente disponibile.
    - *Differito*: quando un articolo viene dichiarato finito, il sistema contrassegna l'articolo finito come fisicamente disponibile e aggiunge le registrazioni giornale a una coda di messaggi. Il sistema non attende che le registrazioni siano completamente elaborate prima di contrassegnare l'articolo finito come fisicamente disponibile.

## <a name="schedule-the-message-processor-batch-job-to-process-deferred-postings"></a>Pianificare il processo batch dell'elaboratore messaggi per elaborare registrazioni differite

Il lavoro batch dell'elaboratore messaggi è responsabile dell'elaborazione delle registrazioni giornale dopo che queste sono state accodate. Per assicurarti che le registrazioni giornale vengano elaborate, devi configurare questo processo in modo che venga eseguito a intervalli regolari. Utilizza la seguente procedura per configurare il processo batch necessario.

1. Vai a **Amministratore di sistema \> Elaboratore messaggi \> Elaboratore messaggi**.
1. Nella Scheda dettaglio **Parametri**, imposta il campo **Coda messaggi** su *Produzione*.
1. Nella Scheda dettaglio **Esecuzione in background**, imposta l'opzione **Elaborazione batch** su *Sì*. Quindi imposta una pianificazione ricorrente e configura altre impostazioni come necessario. Le impostazioni funzionano esattamente come per altri tipi di [processi in background](../../fin-ops-core/dev-itpro/sysadmin/batch-processing-overview.md) in Microsoft Dynamics 365 Supply Chain Management.

## <a name="track-the-progress-of-your-deferred-postings"></a>Tenere traccia dello stato di avanzamento delle registrazioni differite

Le registrazioni giornale differite vengono accodate come *messaggi dell'elaboratore messaggi* che attendono fino a quando non vengono elaborati mediante l'*elaboratore messaggi*. L'elaboratore messaggi deve essere configurato per l'esecuzione come processo batch pianificato. Per visualizzare i messaggi di registrazione differiti che sono stati o saranno elaborati dall'elaboratore di messaggi, vai a **Controllo produzione \> Ordini di produzione \> Registrazione ordine di produzione differita**.

### <a name="message-grid-columns-and-filters"></a>Colonne e filtri della griglia dei messaggi

Puoi utilizzare i campi nella parte superiore della pagina **Registrazione ordine di produzione differita** per trovare messaggi specifici che stai cercando.

Sono disponibili i filtri seguenti:

- **Tipo di messaggio**: specifica il tipo di messaggi visualizzati nella griglia.
- **Stato messaggio**: specifica lo stato dei messaggi visualizzati nella griglia. Sono possibili i seguenti stati:

    - *In coda*: il messaggio è pronto per essere elaborato dall'elaboratore messaggi.
    - *Elaborato*: il messaggio è stato elaborato correttamente dall'elaboratore messaggi.
    - *Annullato*: il messaggio non è stato elaborato durante l'ultimo tentativo ed è stato quindi annullato dall'utente.
    - *Non riuscito*: il messaggio non è stato elaborato durante l'ultimo tentativo. Il sistema riproverà tre volte i messaggi non riusciti. Se nessun tentativo riesce, il messaggio rimarrà nello stato *Non riuscito*. Tieni presente che non puoi annullare o modificare manualmente un messaggio fino al termine dell'ultimo di questi tre tentativi.

- **Contenuto messaggio**: questo filtro esegue una ricerca full-text del contenuto del messaggio. (il contenuto del messaggio non appare nella griglia). Il filtro tratta la maggior parte dei simboli speciali (ad esempio i trattini) come spazi e tutti i caratteri di spazio come operatori booleani OR. Ad esempio, se cerchi uno specifico valore `journalid` corrispondente a *USMF-123456*, il sistema troverà tutti i messaggi che contengono "USMF" o "123456". In questo caso, è probabile che l'elenco dei risultati sia lungo. Pertanto, sarebbe meglio immettere solo *123456* in quanto otterrai risultati più specifici.

Puoi anche ordinare e filtrare l'elenco selezionando una delle intestazioni di colonna e immettendo i criteri nella finestra di dialogo a discesa.

### <a name="view-the-message-log-message-content-and-details"></a>Visualizzare il registro dei messaggi, il contenuto del messaggio e i dettagli

Puoi trovare informazioni dettagliate su un messaggio selezionandolo nella griglia e quindi selezionando la scheda **Registro** o **Contenuto non elaborato** sotto la griglia dei messaggi, dove viene mostrato ogni evento di elaborazione.

La barra degli strumenti nella scheda **Registro** include i seguenti pulsanti:

- **Registro**: seleziona questo pulsante per visualizzare i risultati dell'elaborazione. Questo pulsante è particolarmente utile quando il valore **Risultato elaborazione** dei messaggi è *Non riuscito* e vuoi conoscere i motivi dell'errore di elaborazione.
- **Aggregazione**: è possibile eseguire più operazioni di elaborazione dei messaggi come parte dello stesso processo batch. Seleziona questo pulsante per visualizzare questi dati dettagliati. Ad esempio, puoi verificare se esistono dipendenze che richiedono uno specifico ordine di elaborazione per alcuni messaggi.

### <a name="manually-process-or-cancel-a-message"></a>Elaborare o annullare manualmente un messaggio

Puoi elaborare o annullare manualmente un messaggio, a seconda dello stato corrente dello stesso. Seleziona il messaggio nella griglia e quindi seleziona **Elabora** o **Annulla** nel riquadro azioni.

### <a name="set-up-business-events-to-deliver-alerts-for-failed-processing-results"></a>Impostare eventi aziendali per fornire avvisi per risultati di elaborazione non riusciti

Puoi impostare [eventi aziendali](../../fin-ops-core/dev-itpro/business-events/home-page.md) che ti avvertono di risultati di elaborazione non riusciti. Vai a **Amministrazione di sistema \> Impostazioni \> Eventi aziendali \> Catalogo eventi aziendali** e attiva l'evento aziendale denominato *Messaggio elaboratore messaggi elaborato*.

Nell'ambito del processo di attivazione, ti viene chiesto di specificare se l'evento è specifico per una persona giuridica o si applica a tutte le persone giuridiche. Ti viene anche richiesto di fornire un valore per **Nome endpoint**. Questo valore deve essere definito per primo.

> [!NOTE]
> Se il campo **Quando si verifica un evento aziendale** è impostato su *Microsoft Power Automate* (anziché su *HTTPS*, ad esempio), il valore **Nome di endpoint** viene creato automaticamente in Supply Chain Management in base alla configurazione *Microsoft Power Automate*.
