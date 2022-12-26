---
title: Aggiornamenti qualitativi proattivi
description: Questo articolo fornisce informazioni sulla distribuzione proattiva di aggiornamenti qualitativi.
author: rashmansur
ms.date: 11/07/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: rashmim
ms.search.validFrom: 2022-08-19
ms.search.form: ''
ms.dyn365.ops.version: 10.0.29
ms.openlocfilehash: 7d8de017c54a13a9935d74d33a57813922c9f823
ms.sourcegitcommit: 8aee31d6dffabe13969dd5b9de4e0bf95f53e67e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/19/2022
ms.locfileid: "9887132"
---
# <a name="proactive-quality-updates"></a>Aggiornamenti qualitativi proattivi

[!include[banner](../includes/banner.md)]

Nel corso degli ultimi anni, Microsoft ha fatto continui progressi su ciò che chiamiamo [One Version](../../dev-itpro/lifecycle-services/oneversion-overview.md). Il principio di One Version è semplice: più ci avviciniamo allo scenario che consiste nell'avere tutti i clienti sulla stessa versione del software, più la qualità che possiamo fornire è elevata. Identifichiamo e risolviamo i problemi una sola volta e forniamo queste soluzioni a più clienti più rapidamente.

Questo principio è confermato dai risultati: un minor numero di incidenti per i nostri prodotti. Quando i clienti non utilizzano la stessa versione, constatiamo sistematicamente che sono interessati da problemi per i quali è già disponibile una soluzione. Abbiamo già fatto grandi passi avanti con Dynamics 365 Finance, Dynamics 365 Supply Chain, Dynamics 365 Project Operations e Dynamics 365 Commerce, e grazie ai recenti progressi tecnici, possiamo ormai passare alla fase successiva. Le informazioni seguenti descrivono ciò che faremo, ciò che abbiamo già fatto per preparare il terreno e come e quando introdurremo le nuove funzionalità senza interruzioni.

## <a name="what-you-need-to-know"></a>Cosa hai bisogno di sapere

- Gli aggiornamenti proattivi della qualità vengono applicati su base mensile.
- Saranno consentite eccezioni per gli aggiornamenti proattivi della qualità solo per i clienti regolamentati dalla Food and Drug Administration (FDA) statunitense.
- Gli aggiornamenti qualitativi proattivi non eseguiranno mai il downgrade dell'ambiente né l'upgrade automatico da una versione dell'aggiornamento del servizio a un'altra. 
- Microsoft sta determinando come verranno gestiti gli aggiornamenti di qualità proattivi per gli ambienti regolamentati e per i clienti cloud sovrani e governativi.
- Le notifiche relative agli aggiornamenti qualitativi proattivi vengono pubblicate nel [Centro messaggi Microsoft 365](https://admin.microsoft.com/AdminPortal/).
- Cinque giorni prima dell'applicazione di un aggiornamento proattivo della qualità a un ambiente, i clienti vengono informati che l'aggiornamento si verificherà.
- I clienti non possono annullare o posticipare gli aggiornamenti di qualità proattivi.
- Gli aggiornamenti della qualità proattivi vengono installati durante la [finestra di manutenzione pianificata](../../dev-itpro/deployment/plannedmaintenance-selfservice.md#windows) specifica dell'area geografica.
- Gli aggiornamenti di qualità sono progettati per avere un basso rischio di problemi o regressioni e questo è supportato dai dati di Microsoft.
- Microsoft consiglia di eseguire test mirati per problemi specifici o hotfix specifiche correlate a un aggiornamento proattivo della qualità.
- TUTTE le sandbox, ad eccezione di quelle che hanno un'eccezione legata al tempo per motivi normativi, saranno integrate entro il 7 gennaio 2023.
- L'onboarding della produzione per gli aggiornamenti qualitativi proattivi inizierà dal 21 gennaio 2023. 
- L'onboarding della produzione inizierà solo per i progetti di Lifecycle Services che hanno sandbox inserite e ricevono aggiornamenti qualitativi proattivi a cadenza regolare per tutte le versioni di aggiornamento del servizio supportate. Ciò è applicabile solo agli ambienti dei clienti a cui non sono state fornite eccezioni a causa di normative o altri motivi legali.
- Per un programma completo di aggiornamenti qualitativi proattivi per gli ambienti sandbox e di produzione nel corso del 2023, vedi di seguito.
- Ogni aggiornamento del servizio ha almeno un rilascio degli aggiornamenti della qualità proattivi in corso o programmato per l'inizio. Una volta che i tuoi ambienti sono stati inseriti nel processo di aggiornamenti della qualità proattivi, potresti ricevere un aggiornamento di qualità proattivo pre programmato quando passi a un aggiornamento del servizio della versione più recente. Controlla la pianificazione per determinare quando è pianificata un aggiornamento della qualità proattivo per un aggiornamento del servizio se pensi di eseguire l'upgrade a una versione più recente dell'aggiornamento del servizio. 

> [!Note]
> Test delle prestazioni standard (tier4), sandbox per test delle prestazioni premium (tier5) e ambienti di produzione riceveranno gli aggiornamenti della qualità proattivi nei fine settimana. 

## <a name="focus-on-quality-updates"></a>Aggiornamenti qualitativi

Attualmente forniamo sette [aggiornamenti del servizio](public-preview-releases.md) all'anno. Ad esempio, la versione 10.0.29 è un aggiornamento del servizio. Fino a poco tempo, gli aggiornamenti all'anno erano otto. Tuttavia, ne abbiamo abbandonato uno in risposta al feedback dei clienti che indicava il desiderio di evitare modifiche verso la fine dell'anno di calendario.

Non cambieremo la cadenza degli aggiornamenti del servizio. La fase successiva del processo relativo a One Version è invece incentrata sugli *aggiornamenti qualitativi*. Gli aggiornamenti qualitativi sono build cumulative di aggiornamenti rapidi. Non includono nuove funzionalità. In qualsiasi momento, la nostra intera comunità di clienti è ripartita tra i tre o quattro aggiornamenti del servizio più recenti. Tuttavia, per ogni dato aggiornamento del servizio, varie dozzine di differenti versioni di aggiornamenti qualitativi possono essere utilizzate nel gruppo, a seconda delle date di distribuzione. Nella fase successiva, trasmetteremo in modo proattivo aggiornamenti qualitativi. Utilizziamo già questo modello per le nostre applicazioni basate su Dataverse e abbiamo osservato i risultati previsti, ovvero una migliore qualità e la diminuzione degli incidenti di supporto.

Naturalmente, una riduzione dei difetti potrebbe ridurre o eliminare completamente la necessità di aggiornamenti qualitativi. Abbiamo varie iniziative in corso per ridurre i difetti che richiedono aggiornamenti qualitativi. Anche quando i payload vengono ridotti nell'aggiornamento qualitativo, la coerenza nella base clienti migliorerà il supporto, apporterà miglioramenti per i clienti più rapidamente e ridurrà la frequenza alla quale i clienti incorrono in problemi per i quali esistono già soluzioni.

## <a name="making-proactive-distribution-possible"></a>Rendere possibile la distribuzione proattiva

Sono già stati ottenuti numerosi progressi che consentono la consegna proattiva degli aggiornamenti qualitativi:

- **Aggiornamento con tempi di inattività prossimi allo zero** – Per eseguire il push di ambienti più frequenti, è essenziale ridurre l'impatto sulla disponibilità dell'ambiente per preservare i contratti di servizio (SLA, Service Level Agreement) di Dynamics 365. L'aggiornamento con tempi di inattività prossimi allo zero è stato originariamente introdotto per migliorare le patch mensili del sistema operativo utilizzando un failover del cluster per attivare l'immagine aggiornata con interruzioni minime. Il meccanismo per l'applicazione degli aggiornamenti è stato migliorato in modo da ridurre le perturbazioni e riguarderà sia le patch del sistema operativo che la distribuzione degli aggiornamenti qualitativi.

    Per gli utenti interattivi, è possibile che una sessione attiva venga interrotta e che il nuovo tentativo passi all'ambiente aggiornato. Con l'introduzione della [programmazione batch basata su priorità](../../dev-itpro/sysadmin/priority-based-batch-scheduling.md), la programmazione e l'elaborazione batch vengono ripristinate e riprese immediatamente dopo l'aggiornamento. La programmazione batch basata su priorità sarà disponibile per i clienti prima che inizino a partecipare alla distribuzione proattiva degli aggiornamenti qualitativi per i loro ambienti di produzione.

- **Ore notturne** – Le ore notturne sono definite per ogni area di Azure e gli aggiornamenti con tempi di inattività prossimi allo zero si verificheranno durante il periodo di ore notturne.

## <a name="the-proactive-update-process"></a>Processo di aggiornamento proattivo

La distribuzione degli aggiornamenti qualitativi proattivi seguirà un processo di distribuzione sicura (SDP). Le specifiche dell'SDP si evolveranno, ma gli aggiornamenti qualitativi verranno inizialmente distribuiti in ambienti sandbox. Con l'aumento della percentuale di sandbox distribuite correttamente, inizierà la distribuzione negli ambienti di produzione. I sistemi di ascolto monitoreranno la telemetria del sistema e gli incidenti Livesite e interromperanno il rollout di una versione specifica se viene rilevata una qualsiasi regressione. I clienti potranno comunque eseguire il pull degli aggiornamenti qualitativi prima dell'implementazione proattiva, se lo desiderano.

I dati sulla gestione delle release correnti mostrano che meno del 3% delle regressioni viene introdotto negli aggiornamenti qualitativi. Con una maggiore attenzione all'eliminazione della regressione e un SDP migliorato, il potenziale impatto delle regressioni sarà notevolmente inferiore rispetto ai guadagni in termini di qualità che si ottengono con una distribuzione più rapida delle correzioni ai clienti.

## <a name="process-changes"></a>Elabora modifiche

È attualmente in corso l'implementazione di una serie di modifiche al processo prima dell'attivazione della distribuzione proattiva degli aggiornamenti qualitativi:

- **Schema** – Gli strumenti garantiranno che le build degli aggiornamenti qualitativi includano solo le modifiche dello schema che possono essere applicate mentre il servizio è online. Questo approccio consentirà di preservare la capacità di applicare l'aggiornamento con tempi di inattività prossimi allo zero.
- **Maggiore controllo delle modifiche** – Attualmente, esiste già una fase supplementare del processo per approvare le modifiche da includere in un aggiornamento qualitativo. Il controllo nella fase supplementare verrà aumentato per contribuire a ridurre il potenziale delle regressioni. Non sono consentite modifiche che causano interruzioni negli aggiornamenti qualitativi e il maggiore controllo delle modifiche contribuirà a garantire il raggiungimento di questo obiettivo.
- **Visibilità** – Le notifiche vengono inviate tramite l'interfaccia di amministrazione, Lifecycle Services e altri canali disponibili per i prossimi aggiornamenti qualitativi proattivi. Inoltre, i team di supporto e i responsabili della gestione degli incidenti avranno visibilità su dove gli aggiornamenti qualitativi sono stati implementati in modo proattivo.

    > [!NOTE]
    > Il team di Microsoft Communications sta investigando sul continuo degrado degli strumenti di posta elettronica che impedisce il recapito delle notifiche di posta elettronica. Continua a monitorare il Centro messaggi di Microsoft 365 per l'onboarding e i messaggi relativi alla notifica.

- **Errore sicuro con la versione di anteprima** – La versione di anteprima verrà utilizzata per proteggere le modifiche al codice ove applicabile in una correzione di bug dell'aggiornamento della qualità o utilizzare la versione di anteprima di funzionalità esistente pertinente alla correzione. Se è necessario un fallback o disattivare una modifica dopo una distribuzione proattiva, è possibile farlo tramite il sistema di versione di anteprima per evitare ulteriori errori.
- **Designazione sincronizzazione sandbox** – Al momento non è supportato l'aggiornamento scaglionato a una sandbox isolata di scelte insieme alla produzione. Tutti i sandbox di livello 2 e di livello 3 riceveranno aggiornamenti proattivi almeno 7 giorni prima dell'ambiente di produzione in un progetto Lifecycle Services. Di nuovo, ciò è applicabile solo agli ambienti dei clienti a cui non sono state fornite eccezioni a causa di normative o altri motivi legali.

## <a name="what-is-the-rollout-roadmap-for-quality-updates"></a>Qual è la roadmap per l'implementazione degli aggiornamenti di qualità?

La distribuzione degli aggiornamenti qualitativi proattivi per gli ambienti sandbox inizia a settembre 2022 per i clienti del cloud pubblico di Azure. Entro il 1° gennaio 2023, completeremo l'onboarding del 99% delle sandbox per gli aggiornamenti qualitativi proattivi.

Le eccezioni al processo di distribuzione proattiva degli aggiornamenti saranno consentite solo per i clienti regolamentati dalla FDA. Stiamo ancora lavorando su come verranno gestiti gli ambienti regolamentati e i clienti cloud sovrani e governativi. 

Poiché i clienti riceveranno regolarmente payload più piccoli, prevediamo che il processo di aggiornamento diventerà più semplice. Adegueremo la frequenza della distribuzione degli aggiornamenti mentre dimostreremo la capacità di eseguire il processo senza interruzioni. Questo processo sta già funzionando efficacemente per la nostra piattaforma e le applicazioni Dataverse e fornisce i miglioramenti previsti nella qualità del servizio. Stiamo facendo lo stesso passo avanti per le applicazioni per la finanza e le operazioni.


## <a name="when-will-quality-updates-start-for-production-environments"></a>Quando inizieranno gli aggiornamenti di qualità per gli ambienti di produzione?
Nei primi mesi del 2023, a partire dal 15 gennaio, inizieremo a eseguire l'onboarding degli ambienti di produzione per gli aggiornamenti proattivi e aumenteremo gradualmente la percentuale di ambienti di produzione che ricevono aggiornamenti proattivi. Prenderemo in considerazione solo un ambiente di produzione in un progetto Lifecycle Services in cui gli ambienti sandbox sono già integrati per ricevere aggiornamenti proattivi. Prima di un aggiornamento, i clienti con l'onboarding degli ambienti di produzione riceveranno una notifica tramite il centro messaggi o il banner di Lifecycle Services. Per un programma completo di aggiornamenti qualitativi proattivi per gli ambienti sandbox e di produzione nel corso del 2023, vedi di seguito.

## <a name="what-is-the-schedule-for-sandbox-proactive-quality-updates"></a>Qual è la pianificazione per gli aggiornamenti proattivi di qualità sandbox?
Per informazioni sulle ore notturne per ciascuna area, vedi [Quali sono le finestre di manutenzione pianificate per area?](../../dev-itpro/deployment/plannedmaintenance-selfservice.md#windows).

### <a name="proactive-quality-update-release-10029"></a><a name="schedule"></a>Rilascio dell'aggiornamento qualitativo proattivo: 10.0.29
**Versione app: 10.0.1326.70**  
**Articolo della knowledge base corrispondente più recente: 750332**

| Stazione | Regioni | Programmazione completata | Prossima programmazione sandbox|
|---|---|---|---|
| Stazione 1 | Canada centrale, Canada orientale, Francia centrale, India centrale, Norvegia orientale, Svizzera occidentale | Dal 14 ottobre al 17 ottobre 2022, dal 2 novembre al 5 novembre 2022, dal 13 novembre al 16 novembre 2022, dal 5 dicembre all'8 dicembre 2022 | Dal 2 al 5 gennaio 2023 |
| Stazione 2 | Francia meridionale, India meridionale, Norvegia occidentale, Svizzera settentrionale, Sud Africa settentrionale, Australia orientale, Regno Unito meridionale, Emirati Arabi Uniti settentrionale, Giappone orientale, Australia sud est, Sud Est Asiatico | Dal 15 ottobre al 18 ottobre 2022, dal 2 novembre al 5 novembre 2022, dal 13 novembre al 16 novembre 2022, dal 5 dicembre all'8 dicembre 2022 | Dal 2 al 5 gennaio 2023 |
| Stazione 3 | Asia orientale, Regno Unito occidentale, Giappone occidentale, Brasile meridionale, Europa occidentale, Stati Uniti orientali, Emirati Arabi Uniti centrali | Dal 16 ottobre al 19 ottobre 2022, dal 2 novembre al 5 novembre 2022, dal 13 novembre al 16 novembre 2022, dal 5 dicembre all'8 dicembre 2022 | Dal 2 al 5 gennaio 2023 |
| Stazione 4 | Nord Europa, Stati Uniti centrali, Stati Uniti occidentali | Dal 17 ottobre al 20 ottobre 2022, dal 2 novembre al 5 novembre 2022, dal 15 novembre al 18 novembre 2022, dal 5 dicembre all'8 dicembre 2022 | Dal 2 al 5 gennaio 2023 |
| Stazione 5 | DoD, Government Community Cloud, Cina | Non programmato | Non programmato |

### <a name="proactive-quality-update-release-10030"></a><a name="schedule"></a>Rilascio dell'aggiornamento qualitativo proattivo: 10.0.30
**Versione dell'app: 10.0.1362.77**
**Articolo corrispondente più recente della KB: 767597**

| Stazione | Regioni | Programmazione completata | Prossima programmazione sandbox |
|---|---|---|---|
| Stazione 1 | Canada centrale, Canada orientale, Francia centrale, India centrale, Norvegia orientale, Svizzera occidentale | Dal 1 dicembre al 4 dicembre 2022 |  Dal 13 dicembre al 16 dicembre 2022 | 
| Stazione 2 | Francia meridionale, India meridionale, Norvegia occidentale, Svizzera settentrionale, Sud Africa settentrionale, Australia orientale, Regno Unito meridionale, Emirati Arabi Uniti settentrionale, Giappone orientale, Australia sud est, Sud Est Asiatico | Dal 2 dicembre al 5 dicembre 2022 |  Dal 13 dicembre al 16 dicembre 2022 | 
| Stazione 3 | Asia orientale, Regno Unito occidentale, Giappone occidentale, Brasile meridionale, Europa settentrionale, Stati Uniti orientali, Emirati Arabi Uniti centrali | Dal 3 dicembre al 6 dicembre 2022 |  Dal 13 dicembre al 16 dicembre 2022 | 
| Stazione 4 | Stati Uniti occidentali, Stati Uniti centrali, Stati Uniti occidentali | Dal 4 dicembre al 7 dicembre 2022 |  Dal 13 dicembre al 16 dicembre 2022 | 
| Stazione 5 | DoD, Government Community Cloud, Cina | Non programmato | Non programmato |

### <a name="proactive-quality-update-calendar-year-2023-schedule"></a><a name="schedule"></a> Aggiornamento proattivo della qualità - Programma dell'anno di calendario 2023

#### <a name="stations-to-region-mapping"></a><a name="Stations-Regions"></a> Mappatura da stazioni ad area

| Stazioni | Regioni |
|---|---|
| Stazione 1 | Da definire |
| Stazione 2 | Canada centrale, Canada orientale, Francia centrale, India centrale, Norvegia orientale, Svizzera occidentale |
| Stazione 3 | Francia meridionale, India meridionale, Norvegia occidentale, Svizzera settentrionale, Sud Africa settentrionale, Australia orientale, Regno Unito meridionale, Emirati Arabi Uniti settentrionale, Giappone orientale, Australia sud est, Sud Est Asiatico |
| Stazione 4 | Asia orientale, Regno Unito occidentale, Giappone occidentale, Brasile meridionale, Europa settentrionale, Stati Uniti orientali, Emirati Arabi Uniti centrali |
| Stazione 5 | Stati Uniti occidentali, Stati Uniti centrali, Stati Uniti occidentali |
| Stazione 6 | DoD, Government Community Cloud, Cina |


> [!IMPORTANT]
> Questo è un programma di alto livello per l'anno 2023. Per una pianificazione più concreta, vedi l'esempio riportato di seguito per la versione 2 10.0.30 di gennaio. Il programma esatto e la versione dell'app verranno aggiornati 7 giorni prima dell'inizio di un aggiornamento della qualità.

> [!Note]
> Solo gli ambienti di produzione inseriti riceveranno l'aggiornamento per la versione 2 10.0.30, gli ambienti inseriti riceveranno comunicazione esplicita.

| Aggiornamento qualitativo | Rilascio | Durata serie |
|---|---|---|
| Versione 2 10.0.30 | 16 dicembre 2022 | Dal 2 al 29 gennaio 2023 |
| Versione 3 10.0.30 | 13 gennaio 2023 | Dal 30 gennaio al 25 febbraio 2023 |
| Versione 4 10.0.30 | 24 febbraio 2023 | Dal 6 marzo all'8 aprile 2023 |
| Versione 1 10.0.31 | 3 febbraio 2023 | Dal 13 febbraio 2023 al 18 marzo 2023|
| Versione 2 10.0.31 | 3 marzo 2023 | Dal 13 marzo al 15 aprile 2023|
| Versione 3 10.0.31 | 14 aprile 2023 | Dal 24 aprile 2023 al 27 maggio 2023|
| Versione 1 10.0.32 | 31 marzo 2023 | Dal 10 aprile 2023 al 13 maggio 2023|
| Versione 2 10.0.32 | 28 aprile 2023 | Dall'8 maggio 2023 al 10 giugno 2023|
| Versione 3 10.0.32 | 26 maggio 2023 | Dal 5 giugno 2023 all'8 luglio 2023|
| Versione 1 10.0.33 | 28 aprile 2023 | Dall'8 maggio 2023 al 10 giugno 2023|
| Versione 2 10.0.33 | 26 maggio 2023 | Dal 5 giugno 2023 all'8 luglio 2023|
| Versione 3 10.0.33 | 14 luglio 2023 | Dal 24 luglio 2023 al 26 agosto 2023|
| Versione 1 10.0.34 | 23 giugno 2023 | Dal 3 luglio 2023 al 5 agosto 2023|
| Versione 2 10.0.34 | 21 luglio 2023 | Dal 31 luglio 2023 al 2 settembre 2023|
| Versione 3 10.0.34 | 1 settembre 2023 | Dall'11 settembre 2023 al 14 ottobre 2023|
| Versione 1 10.0.35 | 28 luglio 2023 | Dal 7 agosto 2023 al 9 settembre 2023|
| Versione 2 10.0.35 | 25 agosto 2023 | Dall'4 settembre 2023 al 7 ottobre 2023|
| Versione 3 10.0.35 | 20° ottobre 2023 | Dal 30 ottobre 2023 al 16 dicembre 2023|
| Versione 1 10.0.36 | 29 settembre 2023 | Dal 9 ottobre 2023 all'11 novembre 2023|
| Versione 2 10.0.36 | 27° ottobre 2023 | Dal 6 novembre 2023 al 16 dicembre 2023|
| Versione 3 10.0.36 | 12 gennaio 2024 | Dal 22 gennaio 2023 al 24 febbraio 2024|
| Versione 1 10.0.37 | 3 novembre 2023 | Dal 13 novembre 2023 al 6 gennaio 2024|
| Versione 2 10.0.37 | 30 dicembre 2023 | Dall'8 gennaio 2024 al 10 febbraio 2024|
| Versione 3 10.0.37 | 27 gennaio 2024 | Dal 5 febbraio 2024 al 9 marzo 2024|
| Versione 4 10.0.37 | 23 febbraio 2024 | Dal 4 marzo al 6 aprile 2024|

### <a name="proactive-quality-update-upcoming-10030-release-2-train-schedule"></a><a name="schedule"></a> Aggiornamento proattivo della qualità: programmazione futura per la versione 2 10.0.30
**Versione app: 10.0.1362.99**

| Stazioni | Prossima programmazione sandbox | Programmazione di produzione futura |
|---|---|---|
| Stazione 1 | NA | NA |
| Stazione 2 | Dal 2 al 5 gennaio 2023 | Dal 21 al 22 gennaio 2023 |
| Stazione 3 | Dal 3 al 6 gennaio 2023 | Dal 28 al 29 gennaio 2023 |
| Stazione 4 | Dal 9 al 12 gennaio 2023 | NA |
| Stazione 5 | Dal 16 al 19 gennaio 2023 | NA |
| Stazione 6 | NA | NA |

> [!IMPORTANT] 
> Con cinque giorni di anticipo, Microsoft aggiornerà la pianificazione precedente e invierà una notifica per l'insieme di ambienti pianificati per ricevere questi aggiornamenti di qualità. La pianificazione precedente è applicabile solo agli ambienti a cui è stato notificato un aggiornamento imminente. Per informazioni sulle ore notturne per ciascuna area, vedi [Quali sono le finestre di manutenzione pianificate per area?](../../dev-itpro/deployment/plannedmaintenance-selfservice.md#windows).
>
> Per ogni gruppo di aree, o *stazione*, dove è attualmente pianificata l'implementazione di un aggiornamento della qualità, la pianificazione mostra un intervallo di quattro giorni. Gli aggiornamenti della qualità inizieranno solo con gli ambienti sandbox. Quindi, con l'aumento della percentuale di sandbox distribuite correttamente, inizierà la distribuzione negli ambienti di produzione con notifiche anticipate ai clienti.
> 
> Gli aggiornamenti della qualità avverranno sempre in modo continuativo che ci consente di scegliere come destinazione un insieme di ambienti per programma e di completare tutti i set entro la fine del quarto giorno per una stazione. Tuttavia, ciò non significa che un aggiornamento dell'ambiente durerà quattro giorni. Significa solo che non possiamo predeterminare quale set di ambienti verrà aggiornato in un determinato giorno nell'intervallo di quattro giorni. Tutti gli aggiornamenti verranno effettuati durante le ore notturne, con tempi di inattività prossimi allo zero. Gli aggiornamenti termineranno definitivamente entro la finestra delle ore notturne di una determinata area.

## <a name="how-are-the-dark-hours-handled-for-customers-that-have-one-finance-and-operations-apps-instance-but-are-active-in-multiple-time-zones"></a>Come vengono gestite le ore notturne per i clienti che hanno un'istanza di app per la finanza e le operazioni ma sono attivi in più fusi orari? 
Non ci sono programmi speciali al di fuori delle ore notturne in cui esiste un'istanza di app per la finanza e le operazioni, poiché prevediamo di implementare aggiornamenti di qualità in modo minimamente dirompente con [nZDT](../../dev-itpro/deployment/plannedmaintenance-selfservice.md#what-does-near-zero-downtime-maintenance-mean).

## <a name="what-is-the-current-rollout-cadence-for-proactive-quality-updates"></a>Qual è l'attuale cadenza di implementazione per gli aggiornamenti di qualità proattivi?
Gli aggiornamenti della qualità proattivi vengono attualmente forniti una volta al mese per ciascuna versione supportata di un aggiornamento del servizio. Viene inviato un solo aggiornamento al mese per ambienti sandbox selezionati, a meno che i clienti non passino a una nuova versione di aggiornamento del servizio. In tal caso, possono ottenere aggiornamenti della qualità proattivi preprogrammati come parte di un addestramento esistente per il nuovo aggiornamento del servizio. Dopo che l'implementazione mondiale sarà completata nel 2023, la frequenza di questi aggiornamenti aumenterà. Riceverai sempre un preavviso di almeno un mese ogni volta che cambia la cadenza di spedizione.

## <a name="how-will-microsoft-ensure-the-quality-of-these-updates"></a>In che modo Microsoft garantirà la qualità di questi aggiornamenti?
Microsoft si impegna a mantenere la pipeline di rilascio sufficientemente efficiente da fornire piccoli payload per mantenere bassi i costi di convalida. Ogni correzione in un aggiornamento di qualità passa attraverso un processo di distribuzione rigoroso e sicuro che aiuta a migliorare la qualità e l'affidabilità, riducendo così l'impatto sui clienti. La distribuzione avverrà in più fasi prima negli ambienti sandbox, quindi nella produzione. Le distribuzioni graduali consentono un monitoraggio adeguato per determinare se la distribuzione è sicura. Interromperemo l'implementazione se vengono rilevati problemi con ciascun gruppo di clienti distribuito e garantiremo che ogni fase dell'implementazione abbia tempo a sufficienza per far emergere i problemi. Per ogni imminente aggiornamento di qualità, forniremo visibilità sulla pianificazione tramite aggiornamenti alla documentazione pubblica e alle e-mail, in modo che i clienti possano pianificare in anticipo.

## <a name="can-customers-delay-reschedule-or-pause-a-quality-update"></a>I clienti possono ritardare, riprogrammare o sospendere un aggiornamento di qualità?
N. L'obiettivo principale degli aggiornamenti di qualità è garantire che elementi fondamentali come sicurezza, privacy, affidabilità, disponibilità e prestazioni siano in continuo miglioramento per i nostri clienti. Ritardando o sospendendo un aggiornamento, la sicurezza, la disponibilità e l'affidabilità saranno a rischio.

## <a name="how-do-i-know-what-set-of-changes-went-into-a-quality-update-payload"></a>Come posso conoscere quale insieme di modifiche è stato apportato a un payload di aggiornamento di qualità?
Segui i passaggi di seguito per identificare l'elenco delle modifiche che entrano in un payload di aggiornamento qualitativo. 

Utilizza l'addestramento di aggiornamento della qualità 10.0.28 e la relativa versione dell'app 10.0.1265.89.

1. In Lifecycle Services e apri la pagina **Dettagli ambiente** per il tuo sandbox. 
2. Nella sezione **Aggiornamenti disponibili** seleziona **Visualizza aggiornamento** per l'ultima build di aggiornamento della qualità. 
3. Esporta la build in un CSV o in un file Microsoft Excel.
4. Nel file esportato, filtra e seleziona la **versione della build** che è precedente o uguale al numero build 10.0.1265.89. Dovrebbe essere possibile vedere il payload delta.
 
> [!NOTE]
> L'esportazione in un file CSV o di Excel deve avvenire prima dell'aggiornamento dell'ambiente. In caso contrario, puoi utilizzare un ambiente con una configurazione simile in cui non è installato l'aggiornamento e seguire i passaggi precedenti.

[![Esempio di ambiente con aggiornamento della qualità.](./media/how-to-get-kb-list-pqu.png)](./media/how-to-get-kb-list-pqu.png)

## <a name="what-is-the-process-if-a-critical-issue-is-found-after-a-quality-update"></a>Qual è la procedura se viene rilevato un problema critico dopo un aggiornamento di qualità?
Un problema critico o una regressione è uno o più eventi che in genere causano a più clienti un'esperienza degradata con uno o più dei nostri servizi. Questi problemi possono causare tempi di inattività non pianificati, tra cui indisponibilità, degrado delle prestazioni e interferenza con la gestione del servizio. Se c'è un ampio impatto sui clienti a causa di tali regressioni, interromperemo l'implementazione di un aggiornamento di qualità finché non saremo in grado di comunicare e risolvere il problema. In genere, il successivo aggiornamento di qualità avrà la correzione necessaria per riprendere la distribuzione.

Se l'ambiente di un singolo cliente è interessato, contatta il supporto Microsoft per aprire un ticket. Sulla base della giustificazione, interromperemo l'implementazione dell'aggiornamento di qualità in tutti gli altri ambienti di quel progetto fino a quando il problema non sarà risolto.

## <a name="can-customers-still-manually-apply-hotfix-updates-from-lifecycle-services"></a>I clienti possono ancora applicare manualmente gli aggiornamenti degli hotfix da Lifecycle Services?
Sì. Per garantire la parità continua con il funzionamento degli hotfix, gli aggiornamenti degli hotfix possono ancora essere applicati agli ambienti dei clienti in Lifecycle Services. Tuttavia, è importante notare che gli hotfix distribuiti come parte di un aggiornamento di qualità passano attraverso l'SDP standard prima della distribuzione dell'aggiornamento. Ciò riduce il rischio di regressioni dovute alla qualità superiore. Si consiglia di scegliere un aggiornamento di qualità rispetto all'applicazione manuale degli hotfix per una maggiore affidabilità.

## <a name="can-customers-proactively-install-a-quality-update-build-ahead-of-the-schedule"></a>I clienti possono installare in modo proattivo un aggiornamento di qualità prima della pianificazione?
Sì. È possibile installare un aggiornamento di qualità in modo proattivo. Microsoft salterà l'aggiornamento se la versione di build corrente dell'ambiente è uguale o superiore all'aggiornamento di qualità in questione.

## <a name="if-an-environment-has-an-upcoming-scheduled-monthly-service-update-within-a-week-will-it-still-receive-quality-updates"></a>Se un ambiente ha un imminente aggiornamento del servizio mensile programmato entro una settimana, riceverà comunque aggiornamenti della qualità?
- Gli aggiornamenti della qualità non vengono applicati negli ambienti di produzione se è previsto un aggiornamento del servizio imminente pianificato entro una settimana dalla pianificazione dell'aggiornamento della qualità.
- Se un ambiente sandbox ha la stessa versione di build o superiore rispetto all'imminente aggiornamento della qualità, verrà ignorato.
- Se un ambiente di produzione ha la stessa versione di build o superiore rispetto all'imminente aggiornamento della qualità, verrà ignorato.
- Se un sandbox ha una versione di build uguale o superiore a causa di un aggiornamento della qualità o di un aggiornamento manuale della produzione, la produzione riceverà comunque la versione pianificata dell'aggiornamento mensile del servizio. Se non si desidera che l'ambiente di produzione pianificato venga aggiornato alla versione di aggiornamento del servizio, è possibile sospendere l'aggiornamento del servizio da Lifecycle Services. 
- Ti consigliamo di utilizzare l'ultima build di aggiornamento della qualità per testare le modifiche per un aggiornamento del servizio imminente per stabilità e risultati migliorati.

## <a name="if-an-environment-has-an-upcoming-scheduled-action-and-a-scheduled-quality-update-in-the-same-maintenance-window-will-it-still-receive-the-quality-update"></a>Se un ambiente ha un'azione pianificata imminente e un aggiornamento della qualità pianificato nella stessa finestra di manutenzione, riceverà comunque l'aggiornamento della qualità?
In caso di contesa con un'azione preprogrammata, ad esempio un Ripristino temporizzato, l'aggiornamento della qualità verrà riprogrammato alla successiva finestra di manutenzione disponibile entro la finestra di quattro giorni. Per altre informazioni sulla programmazione, vedi [Qual è la pianificazione per gli aggiornamenti di qualità proattivi?](#schedule). 

## <a name="can-an-environment-be-brought-back-to-its-previous-state-if-there-are-issues-after-a-quality-update-is-applied"></a>È possibile riportare un ambiente allo stato precedente se si verificano problemi dopo l'applicazione di un aggiornamento della qualità?
Dopo l'applicazione di un aggiornamento di qualità, non viene eseguito il rollback in nessun caso. Sono disponibili solo opzioni di patch forward per mitigare i problemi.

## <a name="what-about-fda-regulation-and-gxp"></a>Che dire del regolamento FDA e del GxP?
Il piano per i clienti soggetti a convalida e regolamentazione FDA è ancora in evoluzione. Aspettati presto altri aggiornamenti in questo argomento. Per ora, tutti questi clienti sono esenti da aggiornamenti di qualità. Per garantire che un cliente rientri nelle normative FDA, visita [Offerta Microsoft Azure GxP](/azure/compliance/offerings/offering-gxp).

## <a name="what-versions-of-service-updates-are-supported-for-these-quality-updates"></a>Quali versioni degli aggiornamenti del servizio sono supportate per questi aggiornamenti di qualità?
I clienti che utilizzano tutte le versioni supportate degli aggiornamenti del servizio si qualificano per gli aggiornamenti della qualità. 

## <a name="finance-and-operations-apps-deployments-with-retail-components-typically-require-additional-work-in-addition-to-having-to-redeploy-mpos-how-will-these-quality-updates-impact-the-retail-sdk"></a>Le distribuzioni di app per la finanza e le operazioni con componenti di vendita al dettaglio in genere richiedono lavoro aggiuntivo oltre alla ridistribuzione di MPOS. In che modo questi aggiornamenti di qualità influiranno su Retail SDK? 
Poiché la natura degli hotfix in sé non cambia nel payload degli aggiornamenti di qualità, non prevediamo alcun impatto aggiuntivo in questo momento specificamente correlato ai componenti di vendita al dettaglio.

## <a name="is-there-any-impact-to-cloud-hosted-environments-che"></a>C'è qualche impatto sugli ambienti ospitati nel cloud (CHE)? 
Gli ambienti CHE non rientrano nell'ambito degli aggiornamenti di qualità perché non rientrano nell'ambito di competenza di Microsoft.

## <a name="are-there-any-integration-issues-with-microsoft-dataverse"></a>Ci sono problemi di integrazione con Microsoft Dataverse? 
Non sono noti problemi di integrazione per gli aggiornamenti di qualità con Dataverse.

