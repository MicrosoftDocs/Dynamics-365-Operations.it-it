---
title: Gestione attività
description: In questo argomento viene illustrata la funzionalità di gestione delle attività disponibile in Microsoft Dynamics 365 Human Resources.
author: twheeloc
ms.date: 12/20/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2021-29-11
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 727e1eb75f807d84f088cf3dd139eb094aa76618
ms.sourcegitcommit: 7893ffb081c36838f110fadf29a183f9bdb72dd3
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/02/2022
ms.locfileid: "8087219"
---
# <a name="task-management"></a>Gestione attività

[!INCLUDE [PEAP](../includes/peap-1.md)]

La gestione delle attività consente di creare attività che devono essere completate per assumere (onboard), licenziare (offboard) e trasferire (transizione) dipendenti. La gestione delle attività utilizza il concetto di elenchi di controllo. Un elenco di controllo è un elenco di attività di onboarding, offboarding o transizione. La gestione delle attività utilizza gli elenchi di controllo per raggruppare le attività e per assegnarle a individui o gruppi. La funzionalità dell'elenco di controllo per l'onboarding, l'offboarding e le transizioni è simile.

## <a name="checklist-overview"></a>Panoramica dell'elenco di controllo

Un elenco di controllo è un gruppo di attività. Gli elenchi di controllo ti offrono un modo flessibile per raggruppare le attività e possono essere riutilizzati (ad esempio, quando assumi altri dipendenti). Puoi creare tutti gli elenchi di controllo di cui hai bisogno e puoi assegnare le stesse attività a più elenchi di controllo.

### <a name="examples"></a>Esempi

Gli esempi seguenti mostrano come utilizzare gli elenchi di controllo nel processo di onboarding. Tuttavia, poiché la funzionalità dell'elenco di controllo per l'onboarding, l'offboarding e le transizioni è simile, le informazioni si applicano anche ai processi di offboarding e transizione.

Come parte del processo di onboarding, i professionisti delle risorse umane (HR) possono creare attività che tengono traccia dei progressi di onboarding dei dipendenti in entrata e di recente assunzione. Poiché il processo di onboarding può variare, a seconda della posizione del dipendente o della posizione geografica, è possibile creare più elenchi di controllo di onboarding per adattarsi a diverse situazioni di assunzione.

**Esempio 1**

Ogni dipendente assunto negli Stati Uniti deve completare attività come la compilazione di moduli di ritenuta d'acconto. Tuttavia, attività come l'assegnazione di un'auto aziendale potrebbero essere applicabili solo al personale di livello esecutivo. In questo caso, è possibile creare due elenchi di controllo di onboarding: **Dipendenti con sede negli Stati Uniti** e **Solo dirigenti**. Quindi, quando un manager di medio livello viene assunto negli Stati Uniti, l'elenco di controllo **Dipendenti con sede negli Stati Uniti** è selezionato. Tuttavia, quando un dirigente viene assunto negli Stati Uniti, entrambi gli elenchi di controllo vengono selezionati per garantire che tutte le attività di onboarding richieste siano completate.

**Esempio 2**

Un'azienda ha sia dipendenti stagionali che dipendenti regolari a tempo pieno. Sebbene alcune attività (come la verifica dell'orario di arrivo del nuovo dipendente) si applichino ai dipendenti di entrambi i tipi, alcune attività aggiuntive si applicano solo ai normali dipendenti a tempo pieno. In questo caso, puoi creare due elenchi di controllo. Entrambi gli elenchi di controllo includono le attività che si applicano ai dipendenti a tempo pieno sia stagionali che regolari, ma solo un elenco di controllo include le attività specifiche per i dipendenti regolari a tempo pieno.

## <a name="task-management-workspace"></a>Area di lavoro gestione attività

L'area di lavoro **Gestione attività** elenca tutte le attività che sono state assegnate alle persone nei processi di onboarding, offboarding e transizione. Per visualizzare le attività di un processo, seleziona la scheda appropriata nell'angolo in alto a sinistra: **Onboarding**, **Offboarding**, o **Transizioni**. Per impostazione predefinita, solo i professionisti delle risorse umane possono accedere all'area di lavoro **Gestione attività**.

La scheda **Onboarding** contiene un elenco **Inizio a breve** che mostra i dipendenti in entrata e un elenco **Assunzioni recenti** che mostra i dipendenti assunti di recente. In entrambi gli elenchi puoi selezionare un solo dipendente. Quando selezioni un dipendente, tutte le attività correlate all'onboarding di quel dipendente vengono visualizzate sul lato destro della pagina. La scheda **Onboarding** contiene anche un elenco **Tutte le attività** che mostra tutte le attività per tutti i dipendenti in entrata o assunti di recente. Infine, contiene un elenco di attività scadute e un elenco di attività assegnate all'utente corrente.

La scheda **Offboarding** contiene un elenco di dipendenti che stanno uscendo dall'azienda e un elenco di dipendenti che sono già usciti dall'azienda. In entrambi gli elenchi puoi selezionare un solo dipendente. Quando selezioni un dipendente, tutte le attività correlate all'offboarding di quel dipendente vengono visualizzate. La scheda **Offboarding** contiene anche un elenco **Tutte le attività** che mostra tutte le attività per tutti i dipendenti in uscita o usciti di recente. Infine, contiene un elenco di attività scadute e un elenco di attività assegnate all'utente corrente.

La scheda **Transizioni** contiene un elenco **Tutte le attività** che mostra tutte le attività per tutti i dipendenti che cambieranno posizione o che hanno cambiato posizione di recente. Contiene anche un elenco di attività scadute e un elenco di attività assegnate all'utente corrente.

In tutte e tre le schede, gli assistenti e i manager delle risorse umane possono completare le seguenti attività:

- Applicare un elenco di controllo a un dipendente.
- Aggiornare lo stato di un'attività.
- Riassegnare un'attività.
- Aggiornare la data di scadenza di un'attività.

> [!NOTE]
> Per impostazione predefinita, la scheda **Onboarding** mostra i dipendenti assunti negli ultimi sette giorni. Per modificare questa impostazione, nella pagina **Parametri di Human Resources**, nella scheda **Generale**, immettere un intervallo di tempo nel campo **Assunzioni recenti**. Le informazioni nell'elenco **Assunzioni recenti** possono essere visualizzate per un numero specifico di giorni, mesi o anni. Ad esempio, per visualizzare l'elenco dei dipendenti assunti negli ultimi 14 giorni, imposta il campo **Periodo** su **14** e il campo **Unità** su **giorni**.
>
> Nella pagina **Parametri risorse umane** puoi anche aggiornare l'intervallo di date per gli elenchi dei dipendenti usciti e in uscita che vengono visualizzati nella scheda **Offboarding**.
>
> Queste impostazioni si applicano anche all'area di lavoro **Gestione personale**.

## <a name="setting-up-tasks"></a>Impostazione delle attività

Puoi creare attività individualmente e quindi riutilizzarle in più elenchi di controllo. Per creare un'attività, nella pagina **Impostazione onboarding** nella scheda **Attività** seleziona **Nuovo**.

In alternativa, puoi aggiungere attività direttamente a un elenco di controllo. Per aggiungere un'attività a un elenco di controllo, nella pagina **Impostazione onboarding** nella scheda **Elenco di controllo** crea un nuovo elenco di controllo a cui aggiungere l'attività o aggiungi l'attività a un elenco di controllo esistente.

> [!NOTE]
> Se aggiungi un'attività direttamente a un elenco di controllo, non puoi riutilizzarla in altri elenchi di controllo.

Nella tabella seguente vengono descritti i campi disponibili quando crei un'attività con entrambi i metodi.

| Campo           | Description |
|-----------------|-------------|
| Compito            | Immetti il nome dell'attività. |
| Description     | Immetti una descrizione dell'attività. |
| Facoltativo        | Specifica se l'attività è facoltativa ed è solo informativa. |
| Collegamento attività       | Immetti l'URL di una pagina Web esterna o di una pagina specifica nell'app in cui l'utente deve completare l'attività. Per ulteriori informazioni, vedi la sezione [Collegamenti di attività](#task-links). |
| Tipo di assegnazione | Le attività possono essere assegnate a un lavoratore, una posizione o un gruppo di posizioni specifico, il manager del dipendente interessato (ovvero il dipendente che fa parte del processo di onboarding, offboarding o transizione) o il dipendente interessato. Seleziona il tipo di assegnazione. Per ulteriori informazioni, vedi la sezione [Tipi di assegnazione](#assignment-types). |
| Assegnato a     | Seleziona il lavoratore, la posizione o il gruppo di posizioni specifici a cui assegnare l'attività. |
| Contatto  | Specifica la persona da contattare in caso di domande sull'attività. |
| Offset data di scadenza | Specificare il numero di giorni prima o dopo la data di onboarding, licenziamento o transizione alla scadenza dell'attività. Per ulteriori informazioni, vedi la sezione [Date di scadenza attività e campo Offset data di scadenza](#task-due-dates-and-the-due-date-offset-field). |
| Istruzioni    | Immetti le istruzioni per completare l'attività. Per ulteriori informazioni, vedi la sezione [Istruzioni](#instructions). |

### <a name="task-links"></a>Collegamento attività

Un collegamento attività fornisce un collegamento a una pagina Web esterna o a una pagina nell'app Dynamics 365. Puoi specificare un collegamento attività se la persona assegnata a un'attività deve accedere a una pagina Web specifica o a una pagina specifica nell'app Dynamics 365 per completare l'attività. Quando crei un collegamento attività, puoi selezionare una delle seguenti opzioni:

- **Voce di menu** – Se selezioni questa opzione, viene visualizzato un elenco di tutte le pagine nell'app Dynamics 365. Seleziona una pagina nell'elenco.
- **URL** – Se selezioni questa opzione, immetti l'URL della pagina Web a cui vuoi indirizzare la persona assegnata all'attività. La pagina specificata può essere una pagina che non fa parte dell'app Dynamics 365.
- **Dettagli lavoratore** – Se selezioni questa opzione, seleziona una delle seguenti opzioni:

    - **Azioni self-service dipendenti** – Questa opzione mostra un elenco di pagine disponibili in **Self-service dipendenti**. Usala se l'attività assegnata al dipendente inserito deve essere completata in **Self-service dipendenti**. Ad esempio, se il dipendente deve inserire le proprie informazioni di contatto personali, seleziona **Azioni self-service dipendenti**, quindi seleziona **Dettagli personali&gt;Informazioni personali**.
    - **Azioni di gestione lavoratori** – Questa opzione mostra un elenco di pagine correlate al record del lavoratore, ma che non sono accessibili al dipendente. Ad esempio, se il titolare dell'attività deve inserire informazioni specifiche per un lavoratore inserito, come le informazioni sulla retribuzione, seleziona **Azioni di gestione lavoratori**, quindi seleziona **Retribuzione&gt;Retribuzione fissa**.

### <a name="assignment-types"></a>Tipi di assegnazione

Quando un dipendente viene assunto, licenziato o trasferito, è possibile selezionare uno o più elenchi di controllo. Dopo aver selezionato un elenco di controllo e completato il processo di assunzione, licenziamento o trasferimento, le attività vengono create e assegnate agli utenti per tenere traccia dell'avanzamento.

Quando un'attività viene creata, viene assegnata a un utente specifico. L'utente a cui è assegnata un'attività dipende dal tipo di assegnazione selezionato per tale attività. I valori seguenti sono disponibili nel campo **Tipo di assegnazione**:

- **Lavoratore** – Assegna l'attività a un lavoratore specifico. Dopo aver selezionato questo valore, seleziona il lavoratore nel campo **Assegnato a**.
- **Posizione** – Assegna l'attività a una posizione specifica. Dopo aver selezionato questo valore, seleziona la posizione nel campo **Assegnato a**.

    Ad esempio, un tecnico IT sarà sempre responsabile della preparazione di un laptop per un nuovo dipendente. In questo caso, quando crei l'attività di configurazione del laptop, seleziona **Posizione** come tipo di assegnazione, quindi seleziona **Tecnico informatico** come posizione. Quindi, quando un dipendente viene assunto e l'elenco di controllo viene assegnato, l'attività di configurazione del laptop viene assegnata a qualsiasi lavoratore si trovi nella posizione di tecnico IT al momento in cui viene immessa l'azione di assunzione.

- **Gruppo** – Assegna l'attività a un gruppo di posizioni (gruppo di assegnazioni). Dopo aver selezionato questo valore, seleziona il gruppo nel campo **Assegnato a**. Per ulteriori informazioni, vedi la sezione [Impostazione di gruppi di assegnazioni (facoltativo)](#setting-up-assignment-groups-optional).
- **Manager** – Assegna l'attività al manager del dipendente che viene assunto, licenziato o trasferito.

    > [!IMPORTANT]
    > Quando viene applicato un elenco di controllo, se non è attualmente assegnata alcuna posizione al dipendente assunto, licenziato o trasferito, il manager non può essere determinato. In questo caso, l'attività viene assegnata al proprietario dell'elenco di controllo. Per ulteriori informazioni, vedi la sezione [Impostazione di elenchi di controllo](#setting-up-checklists).

- **Dipendente** – Assegna il dipendente che viene assunto, licenziato o trasferito.

### <a name="task-due-dates-and-the-due-date-offset-field"></a>Date di scadenza attività e campo Offset data di scadenza

Le date di scadenza delle attività si basano sulla data di inizio del rapporto di lavoro, sulla data di licenziamento o sulla data di transizione. Alcune attività devono essere completate prima della data di inizio di un dipendente, mentre altre attività possono essere completate dopo. Quando definisci un'attività, imposti il campo **Offset data di scadenza** per specificare una data di scadenza relativa alla data di inizio, licenziamento o transizione. Ad esempio, un tecnico IT deve preparare un laptop per un nuovo dipendente due giorni prima della data di inizio del dipendente. In questo caso, quando crei l'attività di configurazione del laptop, imposta il campo **Offset data di scadenza** su **-2**. Quindi, se la data di inizio di un dipendente è il 5 maggio, l'attività scadrà il 3 maggio.

> [!NOTE]
> Le date di scadenza possono essere modificate anche dopo che l'attività è stata creata.

Le date di scadenza vengono calcolate in base al calendario associato all'elenco di controllo. Per ulteriori informazioni, vedi la sezione [Impostazione di elenchi di controllo](#setting-up-checklists).

### <a name="instructions"></a>Istruzioni

Attività complesse possono richiedere più passaggi, o la persona che esegue l'attività potrebbe dover fornire ulteriori informazioni. Nel campo **Istruzioni** puoi inserire istruzioni o informazioni aggiuntive per aiutare la persona assegnata all'attività a completarla.

## <a name="setting-up-checklists"></a>Impostazione di elenchi di controllo

Un elenco di controllo è un gruppo di attività. Puoi creare tutti gli elenchi di controllo di cui hai bisogno e puoi assegnare le stesse attività a più elenchi di controllo. Quando crei un elenco di controllo, specifichi un proprietario e un calendario.

Se il campo **Tipo di assegnazione** per un'attività è impostato su **Posizione**, **Manager**, o **Gruppo**, ma non è possibile derivare alcun individuo specifico dal tipo di assegnazione, l'attività verrà assegnata al proprietario dell'elenco di controllo. Di seguito sono riportati alcuni esempi di situazioni in cui le attività verranno assegnate al proprietario dell'elenco di controllo:

- Nessuna posizione viene assegnata al dipendente in fase di assunzione o licenziamento. Poiché il dipendente non ha un'assegnazione di posizione, il suo manager non può essere determinato.
- Il campo **Tipo di assegnazione** è impostato su **Posizione**, ma nessun dipendente è assegnato alla posizione al momento della creazione dell'attività. Ad esempio, l'attività **Installazione laptop** è assegnata alla posizione numero 000876 (**Specialista del supporto tecnico**). Al momento dell'assunzione di un dipendente, nessun dipendente viene assegnato alla posizione 000876. Pertanto, verrà creata un'attività per il proprietario dell'elenco di controllo.
- Il campo **Tipo di assegnazione** è impostato su **Gruppo**, ma nessun dipendente è assegnato alle posizioni nel gruppo al momento della creazione dell'attività.

Il calendario specificato per un elenco di controllo viene utilizzato per calcolare la data di scadenza delle attività che fanno parte dell'elenco di controllo. I giorni lavorativi e non lavorativi sono definiti nell'impostazione del calendario. I giorni lavorativi sono inclusi quando viene calcolata la data di scadenza delle attività e sono esclusi i giorni non lavorativi. I giorni non lavorativi includono i fine settimana e i giorni festivi. 

Dopo aver impostato un calendario, viene associato a un modello di elenco di controllo. In questo modo, la data di scadenza di ogni attività nell'elenco di controllo viene calcolata allo stesso modo. Puoi impostare più calendari, ma è possibile associare un solo calendario a ciascun elenco di controllo.

## <a name="setting-up-assignment-groups-optional"></a>Impostazione dei gruppi di assegnazione (facoltativo)

A volte, un gruppo di individui è responsabile di un'attività. Ad esempio, un gruppo di lavoratori IT potrebbe essere responsabile della preparazione dei laptop per le nuove assunzioni.

Per impostare un gruppo di assegnazioni effettua le seguenti operazioni.

1. Nella pagina **Assegnazione gruppo**, seleziona **Nuovo**.
1. Immetti un nome (ad esempio, **IT Laptop**) e una descrizione per il gruppo.
1. Seleziona **Salva**.
1. Nella Scheda dettaglio **Membri** seleziona **Aggiungi**.
1. Nel campo **Posizioni** seleziona tutte le posizioni responsabili dell'attività.

Dopo aver creato un gruppo di assegnazioni, è disponibile per la selezione quando viene creata un'attività. Per selezionare un gruppo specifico per un'attività, devi selezionare **Gruppo** in **Tipo di assegnazione**. Il gruppo che hai creato sarà quindi disponibile per la selezione nel campo **Assegnato a**.

> [!IMPORTANT]
> Se un'attività viene assegnata a un gruppo, l'attività viene contrassegnata come **Completato** quando una persona del gruppo la completa. Le attività vengono create al momento dell'assunzione, del licenziamento o della transizione. Vengono creati per gli utenti assegnati alle posizioni incluse nel gruppo.

## <a name="setting-up-task-groups-optional"></a>Impostazione dei gruppi di attività (facoltativo)

Un processo di onboarding, offboarding o transizione può includere molte attività. Per semplificare l'assegnazione di tutte le attività richieste a un elenco di controllo, è possibile creare gruppi di attività facoltativi per classificare le attività correlate. Ad esempio, i dipartimenti delle risorse umane, dell'IT e dell'amministrazione devono completare ciascuno compiti specifici per assumere un nuovo dipendente. Pertanto, crei i seguenti gruppi di attività: **Risorse umane**, **IT**, e **Amministrazione**. Quindi, quando crei un'attività, puoi associarla a uno di quei gruppi di attività.

Quando vuoi aggiungere un'attività a un elenco di controllo, puoi filtrare l'elenco delle attività in base al gruppo di attività a cui è assegnata l'attività desiderata. Ad esempio, quando crei un modello di elenco di controllo, puoi filtrare l'elenco in modo che solo le attività IT assegnate al gruppo di attività **IT** sono mostrate. Pertanto, è possibile garantire che vengano selezionate solo le attività IT pertinenti.

## <a name="using-checklists"></a>Utilizzo degli elenchi di controllo

Quando un lavoratore viene assunto, licenziato o trasferito, è possibile selezionare uno o più elenchi di controllo. Le date di scadenza delle attività e le assegnazioni dei lavoratori vengono create dopo il completamento del processo di assunzione, licenziamento o transizione. Ad esempio, quando selezioni il pulsanti **Assumi** o **Assumi e aggiungi dettagli** le attività vengono create per gli individui, in base al tipo di assegnazione.

Una data di scadenza viene assegnata a ciascuna attività aggiungendo o sottraendo l'offset data di scadenza dalla data di inizio del dipendente. Per ulteriori informazioni, vedi la sezione [Date di scadenza attività e campo Offset data di scadenza](#task-due-dates-and-the-due-date-offset-field).

Se stai utilizzando le azioni del personale, le attività vengono create quando il pulsante **Completa** è selezionato o l'azione è stata approvata.

Nell'area di lavoro **Gestione attività** puoi applicare un elenco di controllo a un dipendente selezionando il dipendente nella pagina dell'elenco semplice o nella pagina dei dettagli, quindi selezionando **Applica elenco di controllo**. Il valore del campo **Data stabilita** verrà utilizzato per calcolare la data di scadenza delle attività. In genere, la data stabilita corrisponde alla data di assunzione, licenziamento o transizione del dipendente.

Puoi anche applicare un elenco di controllo a un dipendente aprendo la pagina **Lavoratore** e selezionando **Elenchi di controllo** nel menu.

## <a name="completing-tasks"></a>Completamento delle attività

Nella pagina **Self-service dipendenti** un dipendente può visualizzare tutte le attività che gli sono state assegnate. Per ogni attività assegnata, sono mostrati i valori **Attività**, **Descrizione**, **Istruzioni**, e **Contatto**. Inoltre, per ogni attività, il dipendente può aprire la pagina Web esterna associata o la pagina associata nell'app Dynamics 365.

Le attività possono essere contrassegnate come **In corso**, **Annullato**, o **Completato**. Se un'attività viene assegnata a un gruppo, viene contrassegnata come **Completato** quando una persona del gruppo la completa.

Le attività possono anche essere riassegnate.
