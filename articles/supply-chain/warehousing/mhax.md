---
title: Interfaccia attrezzatura movimentazione materiali (MHAX)
description: In questo argomento viene descritto come impostare l'interfaccia attrezzatura movimentazione materiali (MHAX) di modo che sia possibile connettersi a sistemi di movimentazione materiali (MH) fisici esterni.
author: Mirzaab
ms.date: 03/04/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WMHEParameters, WMHESubscription, WMHEQueueManagerWorkspace, WMHEInboundQueue, WMHEOutboundQueue
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-03-04
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: 9273e4a1f6b3f57086c921c4beb0530a67ccd976
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5810512"
---
# <a name="material-handling-equipment-interface-mhax"></a>Interfaccia attrezzatura movimentazione materiali (MHAX)

[!include [banner](../../includes/banner.md)]

È possibile usare l'*interfaccia attrezzatura movimentazione materiali* (MHAX) per connettere i sistemi di movimentazione materiali (MH) fisici esterni a un magazzino gestito mediante la gestione avanzata del magazzino (WMS) in Microsoft Dynamics 365 Supply Chain Management. L'interfaccia tra i sistemi WMS e MH è costituita da due code: una per gli eventi in uscita (da WMS a MH) e una per gli eventi in entrata (da MH a WMS). Il sistema WMS genera eventi in uscita in base alle righe di lavoro che vengono create durante i vari processi di creazione ed esecuzione del lavoro. Il sistema MH quindi esegue regolarmente il polling di nuovi eventi nel sistema WMS ed elabora le risposte. Dopo che il sistema MH ha terminato la gestione degli eventi in conformità con le istruzioni di lavoro, invia eventi in entrata, come il completamento della riga di lavoro e il prelievo in difetto.

L'illustrazione seguente mostra i vari elementi e l'ordine in cui si verificano i processi quando si utilizza l'integrazione MHAX.

![Interazioni e componenti MHAX](media/mhax-components.png "Interazioni e componenti MHAX")

Di seguito viene riportata una spiegazione delle interazioni mostrate nell'illustrazione precedente:

1. Durante la creazione o l'esecuzione del lavoro, gli eventi in uscita vengono creati nella coda in uscita.
2. L'attrezzatura MH si collega al servizio dell'attrezzatura MH, esegue il polling di nuovi eventi ad essa pertinenti ed elabora tali eventi.
3. Quando l'attrezzatura MH è pronta per eseguire il report, si connette di nuovo al servizio e invia gli eventi in entrata. Questi eventi vengono immediatamente elaborati dal processore della coda.
4. In base ai dati dell'evento in entrata, il processore della coda potrebbe eseguire il lavoro esistente, modificarlo o crearne uno.

## <a name="turn-on-the-mhax-feature"></a>Attivare la funzionalità MHAX

Per poter utilizzare la funzionalità MHAX, è necessario attivare tale funzionalità nonché la relativa chiave di configurazione.

1. Andare a **Amministrazione sistema \> Aree di lavoro \> Gestione funzionalità**.
2. Nell'area di lavoro **[Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)**, attivare la funzionalità denominata *Interfaccia attrezzatura movimentazione materiali*.
3. Mettere il sistema in modalità di manutenzione come descritto in [Modalità di manutenzione](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).
4. Accedere a **Amministrazione sistema \> Imposta \> Configurazione licenza**.
5. Espandere **Commercio \> Gestione magazzino e trasporto**, quindi selezionare la casella di controllo **Interfaccia attrezzatura movimentazione materiali**.
6. Disattivare la modalità di manutenzione come descritto in [Modalità di manutenzione](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).

## <a name="set-mhax-parameters"></a>Impostare i parametri MHAX

È necessario impostare alcuni parametri nella pagina **Parametri dell'interfaccia attrezzatura movimentazione materiali** per configurare la funzionalità.

1. Andare a **Interfaccia attrezzatura movimentazione materiali \> Impostazioni \> Parametri dell'interfaccia attrezzatura movimentazione materiali**.
2. Nella scheda **Generale**, impostare i seguenti campi:

    - **ID utente** - Selezionare un lavoratore. Questo lavoratore verrà utilizzato per eseguire tutte le operazioni di lavoro (prelievi e stoccaggi) elaborate tramite la coda in entrata.
    - **Abilitare ID messaggio in entrata** - Quando questa opzione è impostata su *Sì*, se si riceve un ID messaggio in entrata duplicato, il messaggio verrà rifiutato e un messaggio di errore indicherà che il messaggio esiste già. Quando questa opzione è impostata su *No*, gli ID messaggio in entrata duplicati saranno consentiti.

3. Nella scheda **Sequenze numeriche**, selezionare le sequenze numeriche a livello di sistema da utilizzare per generare ID univoci per gli elementi della coda in entrata, gli elementi della coda in uscita e le coppie di righe di lavoro.

## <a name="outbound-events"></a>Eventi in uscita

In momenti specifici durante la creazione o l'esecuzione del lavoro, il sistema determina se deve generare eventi in uscita da inviare al sistema MH. Se una sottoscrizione è configurata per un momento specifico durante l'elaborazione del magazzino, il sistema genera l'evento in base alla configurazione della sottoscrizione.

### <a name="structure-of-outbound-events"></a>Struttura degli eventi in uscita

Ogni evento in uscita è identificato in modo univoco da un ID coda in uscita. Il tipo di transazione in uscita determina il tipo di evento. Anche il magazzino e l'ID della sottoscrizione che ha generato l'evento sono registrati nell'evento.

Per trasferire i dati nel sistema MH, l'evento in uscita contiene 10 campi per i dati (da **data01** a **data10**). Questi campi dati hanno un mapping uno a uno (1:1) ai campi di database esistenti. In particolare, vengono estratti dai campi nella riga di lavoro e nelle tabelle dell'intestazione del lavoro. I campi possono essere selezionati liberamente. Vengono configurati quando si crea la sottoscrizione.

Oltre ai 10 campi dati che hanno un mapping 1:1 ai campi di database esistenti, l'evento può contenere un campo dati aggiuntivo noto come *payload*. Il contenuto di questo campo viene generato mediante codice X++ personalizzato noto come *generatore payload*. Qualsiasi generatore di payload da utilizzare viene impostato nella sottoscrizione.

Per garantire che il sistema MH riceva ogni ID coda in uscita solo una volta, viene utilizzato un campo di stato per specificare se un evento è pronto per essere inviato al sistema esterno o se è già stato inviato.

### <a name="outbound-queue-subscriptions"></a>Sottoscrizioni di code in uscita

Prima di generare qualsiasi evento, è necessario impostare una sottoscrizione per indicare alla funzionalità MHAX se e come generare eventi. Gli eventi generati vengono contrassegnati dall'identificatore di sottoscrizione. Pertanto, più sistemi MH possono connettersi allo stesso sistema WMS ma mantenere distinti i relativi eventi. Quando il servizio MHAX esegue il polling di nuovi eventi, una sottoscrizione è una delle opzioni disponibili per il recupero degli eventi.

Per creare una sottoscrizione, selezionare **Interfaccia attrezzatura movimentazione materiali \> Impostazione \> Sottoscrizioni**. Per ogni sottoscrizione, sono disponibili i seguenti parametri:

- **ID sottoscrizione** - Un nome univoco che identifica la sottoscrizione.
- **Descrizione** - Una descrizione a testo libero della sottoscrizione.
- **Magazzino** - I magazzini specifici in base ai quali filtrare gli eventi.
- **Tipo di transazione in uscita** - Il tipo di eventi che la sottoscrizione deve contenere.
- **Generatore di payload** - Un'estensione di codice facoltativa che può inserire informazioni aggiuntive nel campo **Payload** dell'evento in uscita.

Una query può essere associata a ciascuna sottoscrizione. Questa query filtra le intestazioni e le righe di lavoro per limitare ulteriormente il lavoro che utilizzerà la sottoscrizione per generare eventi. Per aggiungere una query a una sottoscrizione, selezionare la casella di controllo **Esegui query** per la sottoscrizione pertinente nella pagina **Sottoscrizioni**, quindi selezionare **Modifica query** nel riquadro Azioni. Viene visualizzato l'editor di query standard di Supply Chain Management.

Inoltre, la sottoscrizione include una *mappa di sottoscrizioni* che mappa i campi dell'intestazione di lavoro o della riga di lavoro ad alcuni o tutti i 10 campi dati liberi dell'evento in uscita, come necessario. Per restituire le informazioni al servizio MHAX, in genere si includerà l'ID record della riga di lavoro o l'*ID coppia di righe di lavoro* (l'ID coppia di righe di lavoro è una nuova proprietà che consente al sistema di utilizzare un singolo comando di ritorno per elaborare le righe di prelievo e stoccaggio). I campi rimanenti dipendono dal caso d'uso. Alcuni esempi sono forniti più avanti in questo argomento.

Per impostare una mappa di sottoscrizioni, selezionare la sottoscrizione pertinente nella pagina **Sottoscrizioni**, quindi selezionare **Mappa di sottoscrizioni** nel riquadro Azioni. Nella finestra di dialogo **Mappa di sottoscrizioni** visualizzata, è possibile assegnare una tabella e un campo per ogni campo dati disponibile come necessario.

### <a name="outbound-event-types"></a>Tipi di eventi in uscita

Questa sezione descrive i vari tipi di eventi disponibili. (i tipi di evento sono noti anche come *tipi di transazione*). Spiega anche quando ogni tipo di evento viene creato nel sistema WMS.

#### <a name="work-creation-events"></a>Eventi di creazione di lavoro

Gli eventi di creazione di lavoro vengono creati dopo che il lavoro è stato generato dall'applicazione. Questo comportamento si applica alla maggior parte dei tipi di processi di creazione del lavoro, in particolare alla creazione del lavoro di prelievo e di rifornimento. In genere, se il lavoro viene creato con lo stato *Aperto*, a indicare che il lavoro è pronto per essere eseguito da un lavoratore, verrà generato un evento di creazione del lavoro. Inoltre, gli eventi di creazione del lavoro verranno generati per il lavoro di movimento di base (non movimento tramite lavoro di modello), anche se quel lavoro non viene creato come lavoro aperto.

Un'eccezione importante a questo comportamento è il lavoro di conteggio ciclo, che non è attualmente supportato. I conteggi delle scorte nel sistema MH non rientrano nell'ambito di MHAX e i risultati dei conteggi devono essere importati in un giornale di registrazione conteggi scorte.

Dopo che il lavoro è stato creato, il servizio MHAX elabora le righe di lavoro generate e assegna un ID coppia di righe di lavoro a tutte le righe di lavoro generate per ciascuna intestazione di lavoro. L'obiettivo è raggruppare tutte le linee di lavoro di prelievo con gli stoccaggi successivi sotto un ID coppia di righe di lavoro (i gruppi corrispondono alle coppie prelievo/stoccaggio nei modelli di lavoro). In questo modo, è possibile utilizzare un unico ID per segnalare il completamento del lavoro per tutte le righe di prelievo e stoccaggio correlate. Il processo di raggruppamento inizia con la prima riga e quindi continua con lo stesso ID fino a che non rileva una coppia successiva di righe di lavoro di stoccaggio/prelievo. L'ID corrente viene assegnato alla riga di stoccaggio di quella coppia. Un nuovo ID viene quindi utilizzato per la riga di prelievo della coppia. Questo processo continua fino a che non ha elaborato tutte le righe che appartengono all'intestazione del lavoro.

Come funzionalità speciale degli eventi di creazione di lavoro, se l'opzione **Ciclo bloccato** è impostata su *Sì* nell'intestazione del lavoro, gli eventi generati avranno lo stato *Bloccato* anziché il solito stato *Pronto* che viene utilizzato per inviarli al sistema MH. Il flag **Ciclo bloccato** nell'intestazione del lavoro indica che tale intestazione non è ancora pronta per essere eseguita dai lavoratori, forse a causa del lavoro di rifornimento incompleto. Quando il flag **Ciclo bloccato** viene cancellato, gli eventi che sono già stati generati vengono sbloccati e possono essere recuperati per il sistema MH dalla coda.

#### <a name="work-initiation-events"></a>Eventi di avvio del lavoro

Gli eventi di avvio del lavoro vengono attivati quando lo stato di lavoro passa da *Aperto* a *In corso* durante l'aggiornamento del lavoro.

#### <a name="work-completion-events"></a>Eventi di completamento del lavoro

Gli eventi di completamento del lavoro vengono attivati quando lo stato di lavoro passa da *In corso* a *Chiuso* durante l'aggiornamento del lavoro.

#### <a name="work-cancellation-events"></a>Eventi di annullamento del lavoro

Gli eventi di annullamento del lavoro vengono attivati quando lo stato di lavoro passa da un qualsiasi stato che non sia *Annullato* a *Annullato* durante l'aggiornamento del lavoro. Inoltre, tutti gli altri eventi correlati all'intestazione del lavoro vengono eliminati dalla coda per tutte le sottoscrizioni. In questo modo, ai sistemi esterni viene impedito di elaborare eventi non necessari.

#### <a name="pickput-completion-events"></a>Eventi di completamento di prelievo/stoccaggio

Gli eventi di completamento di prelievo/stoccaggio vengono attivati quando lo stato della riga dio prelievo/stoccaggio passa da *In corso* a *Chiuso* durante l'aggiornamento della riga di lavoro.

### <a name="monitor-the-outbound-queue"></a>Monitorare la coda in uscita

Per esaminare la coda in uscita, selezionare **Interfaccia attrezzatura movimentazione materiali \> Comune \> Coda in uscita**. La pagina **Coda in uscita** elenca ogni elemento della coda in uscita e il relativo stato. Selezionare un elemento della coda per visualizzarne i dettagli. Questi dettagli includono il tipo di transazione dell'elemento, la sottoscrizione utilizzata e i valori di ogni campo dati (da **data01** a **data10**) e il payload.

### <a name="clean-up-the-outbound-queue"></a>Pulizia della coda in uscita

A un certo punto, la coda in uscita inizierà a riempirsi di elementi della coda che sono già stati inviati. Per rimuovere questi elementi, selezionare **Interfaccia attrezzatura movimentazione materiali\> Attività periodiche \> Pulitura \> Pulizia coda in uscita**.

## <a name="inbound-events"></a>Eventi in entrata

Questa sezione descrive i vari tipi di eventi in entrata che il sistema MH può segnalare al sistema WMS. Spiega inoltre che i dati devono essere forniti dal sistema MH e la funzione dell'evento in entrata nel sistema WMS.

### <a name="structure-of-inbound-events"></a>Struttura degli eventi in entrata

Quando viene inviato un evento in entrata, il sistema esterno deve fornire il tipo di transazione in entrata insieme a un massimo di 10 parametri (da **data01** a **data10**). La convalida facoltativa può garantire che il servizio MHAX non abbia ricevuto lo stesso evento in entrata più di una volta. Per abilitare questa convalida, ogni evento in entrata deve avere un ID messaggio univoco. Se viene ricevuto un ID messaggio duplicato e se l'opzione **Abilitare ID messaggio in entrata** è impostata su *Sì* nella pagina **Parametri dell'interfaccia attrezzatura movimentazione materiali**, il messaggio verrà rifiutato. Un messaggio di errore indicherà che il messaggio esiste già.

Oltre ai campi dati in entrata, il sistema assegna all'evento un ID coda in entrata univoco.

### <a name="inbound-event-types"></a>Tipi di eventi in entrata

Questa sezione descrive i tipi di eventi in entrata (tipi di transazione) supportati e i dati che devono essere forniti per l'elaborazione degli eventi.

#### <a name="work-confirm-events"></a>Eventi di conferma del lavoro

Gli eventi di conferma del lavoro richiedono che i campi dati in entrata includano le seguenti informazioni:

- **data01** - L'ID coppia di righe di lavoro.
- **data02** - L'ID record riga di lavoro (valore `RecId`).

    > [!NOTE]
    > *O* il campo **data01** *o* il campo **data02** deve essere presente.

- **data03** - L'ID della targa da cui eseguire il prelevamento.
- **data04** - L'ID targa di destinazione dell'intestazione del lavoro.

Se viene fornito l'ID coppia di righe di lavoro, tutte le righe di lavoro di prelievo, stoccaggio o personalizzate contrassegnate dall'ID coppia di righe di lavoro e che hanno lo stato *Aperto* o *In corso*, vengono eseguite in sequenza. Se un ID record riga di lavoro (valore `RecId`), la riga di lavoro deve essere una riga di lavoro di prelievo, stoccaggio o personalizzata il cui stato è *Aperto* o *In corso*.

Le righe di prelievo delle ubicazioni controllate dalla targa richiedono che **data03** specifichi la targa da cui prelevare, indipendentemente dal fatto che le righe siano contrassegnate dall'ID record riga di lavoro o dall'ID coppia di righe di lavoro. Il campo **data04** deve specificare la targa di destinazione dell'intestazione del lavoro per il prelievo.

Le righe di stoccaggio non accettano ulteriori informazioni. Vengono eseguite solo in base alla posizione della linea di lavoro corrente e alla targa di destinazione del lavoro. Se lo stoccaggio deve essere eseguito in un'ubicazione diversa, modificare l'ubicazione della riga di lavoro come descritto nella sezione [Eventi di sostituzione](#override-events) più avanti in questo argomento.

Le righe di lavoro personalizzate non richiedono, o non supportano, alcuna informazione aggiuntiva nell'evento in entrata.

#### <a name="short-pick-events"></a>Eventi di prelievo in difetto

Gli eventi di prelievo in difetto richiedono che i campi dati in entrata includano le seguenti informazioni:

- **data02** - L'ID record di lavoro (valore `RecId`).
- **data03** - L'ID della targa da cui eseguire il prelevamento.
- **data04** - La quantità da prelevare.
- **data05** - Il codice di eccezione di prelievo in difetto.
- **data06** - L'ID targa di destinazione dell'intestazione del lavoro.

> [!NOTE]
> Il campo **data01** non viene utilizzato per eventi di selezione in difetto.

Questo evento è simile all'evento di conferma del lavoro, ma si applica solo alle righe di prelievo.

#### <a name="override-events"></a><a id="override-events"></a>Eventi di sostituzione

Gli eventi di sostituzione richiedono che i campi dati in entrata includano le seguenti informazioni:

- **data01** - L'ID record di lavoro (valore `RecId`).
- **data02** - Il nuovo ID ubicazione.

La riga di lavoro deve avere lo stato *Aperto* o *In corso* e la nuova ubicazione deve esistere.

#### <a name="license-plate-receipt-events"></a>Eventi di ricezione di targhe

Gli eventi di ricezione di targhe richiedono che i campi dati in entrata includano le seguenti informazioni:

- **data01** - L'ID della targa in entrata da ricevere.

Il sistema esegue un'operazione di ricezione della targa, in base alla targa che viene trasmessa come valore del campo **data01**.

### <a name="monitor-the-inbound-queue"></a>Monitorare la coda in entrata

Per esaminare la coda in uscita, selezionare **Interfaccia attrezzatura movimentazione materiali \> Comune \> Coda in entrata**. La pagina **Coda in entrata** elenca ogni elemento della coda in entrata e il relativo stato. Selezionare un elemento della coda per visualizzarne i dettagli. Questi dettagli includono il tipo di transazione dell'elemento, l'ID messaggio e i valori di ogni campo dati (da **data01** a **data10**).

Se si è verificato un errore o un altro tipo di elemento del registro durante l'elaborazione degli eventi in entrata, è possibile esaminare il registro selezionando **Registro errori** nel riquadro Azioni.

### <a name="inbound-event-processing"></a>Elaborazione di eventi in entrata

Gli eventi in entrata vengono prima scritti nel database e quindi eseguiti immediatamente (in modo sincrono). Se si verifica un errore durante l'elaborazione, l'evento viene comunque scritto nella coda, ma lo stato è impostato su *Con errori*. Il servizio MHAX restituisce un messaggio di errore al sistema MH e memorizza il registro degli errori nel record evento in entrata per un'indagine successiva.

Gli eventi che hanno lo stato *Con errori* possono essere rielaborati in seguito se la condizione di errore è stata risolta. Per rielaborarli, eseguire uno dei passaggi seguenti:

- Selezionare **Interfaccia attrezzatura movimentazione materiali \> Comune \> Coda in entrata**. Selezionare la coda in entrata pertinente, quindi selezionare **Rielabora** nel riquadro Azioni.
- Selezionare **Interfaccia attrezzatura movimentazione materiali \> Comune \> Rielabora coda in entrata con errori**. Viene visualizzata una finestra di dialogo relativa al processo batch standard. In questa finestra, è possibile impostare un filtro di record e pianificare o eseguire un processo batch per rielaborare la coda.

Tutte le operazioni di lavoro (prelievi e stoccaggi) vengono eseguite utilizzando il lavoratore selezionato nel campo **ID utente** nella pagina **Parametri dell'interfaccia attrezzatura movimentazione materiali**.

### <a name="clean-up-the-inbound-queue"></a>Pulizia della coda in entrata

A un certo punto, la coda in entrata inizierà a riempirsi di elementi della coda che sono già stati elaborati. Per rimuovere questi elementi, selezionare **Interfaccia attrezzatura movimentazione materiali \> Attività periodiche \> Pulitura \> Pulizia coda in entrata**.

## <a name="get-a-quick-overview-by-using-the-queue-manager"></a>Ottenere una rapida panoramica utilizzando il gestore code

Per ottenere una rapida panoramica di tutte le attività correlate alle code in entrata e in uscita, selezionare **Interfaccia attrezzatura movimentazione materiali\> Aree di lavoro \> Gestore code**. La pagina **Gestore code** fornisce una serie di schede e riquadri che è possibile utilizzare per monitorare ed esplorare le code. Fornisce inoltre collegamenti utili alla maggior parte delle altre pagine menzionate in questo argomento.

## <a name="connect-to-the-mhax-service"></a>Eseguire la connessione al servizio MHAX

MHAX è implementato come servizio personalizzato. Pertanto, è accessibile tramite chiamate SOAP e REST. Di seguito sono riportati gli indirizzi degli endpoint SOAP e REST:

- **SOAP:** `https://base_environment_URL/soap/services/WMHEServices`
- **REST:** `https://base_environment_URL/api/services/WMHEServices/WMHEService`

## <a name="retrieve-messages-from-the-outbound-queue"></a>Recuperare messaggi dalla coda in uscita

Per recuperare i messaggi dalla coda in uscita, utilizzare uno dei seguenti metodi:

- Usare `readOutboundSubscriptionQueue` per recuperare gli eventi in base all'ID sottoscrizione.
- Usare `readOutboundWarehouseQueue` per recuperare gli eventi in base al tipo di evento e all'ID magazzino tra più sottoscrizioni.
