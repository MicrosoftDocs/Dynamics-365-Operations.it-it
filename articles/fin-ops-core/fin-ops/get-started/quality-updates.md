---
title: Aggiornamenti qualitativi proattivi
description: Questo articolo fornisce informazioni sulla distribuzione proattiva di aggiornamenti qualitativi.
author: rashmansur
ms.date: 09/12/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: rashmim
ms.search.validFrom: 2022-08-19
ms.search.form: ''
ms.dyn365.ops.version: 10.0.29
ms.openlocfilehash: da5881a901d3ba4d01e6d4510a53ca079efd7e75
ms.sourcegitcommit: c8b97eea28f07b6b179825f3b134c8c8704ff8fc
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/29/2022
ms.locfileid: "9731612"
---
# <a name="proactive-quality-updates"></a>Aggiornamenti qualitativi proattivi

[!include[banner](../includes/banner.md)]

Nel corso degli ultimi anni, Microsoft ha fatto continui progressi su ciò che chiamiamo [One Version](../../dev-itpro/lifecycle-services/oneversion-overview.md). Il principio di One Version è semplice: più ci avviciniamo allo scenario che consiste nell'avere tutti i clienti sulla stessa versione del software, più la qualità che possiamo fornire è elevata. Identifichiamo e risolviamo i problemi una sola volta e forniamo queste soluzioni a più clienti più rapidamente.

Questo principio è confermato dai risultati: un minor numero di incidenti per i nostri prodotti. Quando i clienti non utilizzano la stessa versione, constatiamo sistematicamente che sono interessati da problemi per i quali è già disponibile una soluzione. Abbiamo già fatto grandi passi avanti con Dynamics 365 Finance, Dynamics 365 Supply Chain, Dynamics 365 Project Operations e Dynamics 365 Commerce, e grazie ai recenti progressi tecnici, possiamo ormai passare alla fase successiva. Le informazioni seguenti descrivono ciò che faremo, ciò che abbiamo già fatto per preparare il terreno e come e quando introdurremo le nuove funzionalità senza interruzioni.

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
- **Visibilità** – Invieremo notifiche tramite l'interfaccia di amministrazione, Lifecycle Services (LCS) e altri canali disponibili per i prossimi aggiornamenti qualitativi proattivi. Inoltre, i team di supporto e i responsabili della gestione degli incidenti avranno visibilità su dove gli aggiornamenti qualitativi sono stati implementati in modo proattivo.
 > [!NOTE]
 > Il team di Microsoft Communications sta investigando sul continuo degrado degli strumenti di posta elettronica che impedisce il recapito delle notifiche di posta elettronica. Continua a monitorare il Centro messaggi di Microsoft 365 per l'onboarding e i messaggi relativi alla notifica.
- **Errore sicuro con la versione di anteprima** – La versione di anteprima verrà utilizzata per proteggere le modifiche al codice ove applicabile in una correzione di bug dell'aggiornamento della qualità o utilizzare la versione di anteprima di funzionalità esistente pertinente alla correzione. Se è necessario un fallback o disattivare una modifica dopo una distribuzione proattiva, è possibile farlo tramite il sistema di versione di anteprima per evitare ulteriori errori.
- **Designazione della sincronizzazione sandbox** – Meno del 20% dei clienti dispone attualmente di più sandbox e mantiene una sandbox distribuita dove la versione corrisponde alla produzione, per agevolare la risoluzione dei problemi. Se un cliente utilizza una sandbox per testare una versione più recente rispetto alla propria produzione, tale sandbox riceverà aggiornamenti qualitativi alla versione più recente.

## <a name="what-is-the-rollout-roadmap-for-quality-updates"></a>Qual è la roadmap per l'implementazione degli aggiornamenti di qualità?

La distribuzione degli aggiornamenti qualitativi proattivi per gli ambienti sandbox dovrebbe iniziare a fine settembre o ottobre 2022 per i clienti del cloud pubblico di Azure. Anche gli ambienti di prova inizieranno a ricevere la distribuzione proattiva degli aggiornamenti in quel periodo. A settembre, verrà inviata una notifica a ogni cliente per informarlo sulla pianificazione prevista per gli ambienti. Le eccezioni al processo di distribuzione proattiva degli aggiornamenti saranno consentite solo per i clienti regolamentati dalla FDA. Stiamo ancora lavorando su come verranno gestiti gli ambienti regolamentati e i clienti cloud sovrani e governativi.

Nei prossimi sei mesi, aumenteremo gradualmente la percentuale di ambienti sandbox che ricevono aggiornamenti proattivi, fino a quando tutti gli ambienti designati non saranno inclusi e passeremo all'aggiornamento degli ambienti di produzione. Durante questo periodo, eseguiremo controlli per assicurarci che il processo di distribuzione sia ottimale e che stiamo raggiungendo il nostro obiettivo di payload senza interruzioni.

Poiché i clienti riceveranno regolarmente payload più piccoli, prevediamo che il processo di aggiornamento diventerà più semplice. Adegueremo la frequenza della distribuzione degli aggiornamenti mentre dimostreremo la capacità di eseguire il processo senza interruzioni. Questo processo sta già funzionando efficacemente per la nostra piattaforma e le applicazioni Dataverse e fornisce i miglioramenti previsti nella qualità del servizio. Siamo impazienti di fare lo stesso passo avanti per le applicazioni per la finanza e le operazioni.

## <a name="when-will-quality-updates-start-for-production-environments"></a>Quando inizieranno gli aggiornamenti di qualità per gli ambienti di produzione?
Al momento, gli aggiornamenti di qualità riguardano solo i sandbox. Aggiorneremo questo spazio con una data di inizio per gli ambienti di produzione quando avremo dati e metriche più concreti da aggiornamenti proattivi per sandbox per valutare la preparazione per la produzione.

## <a name="what-is-the-schedule-for-sandbox-proactive-quality-updates"></a>Qual è la pianificazione per gli aggiornamenti proattivi di qualità sandbox?
Per informazioni sulle ore notturne per ciascuna area, vedi [Quali sono le finestre di manutenzione pianificate per area?](../../dev-itpro/deployment/plannedmaintenance-selfservice.md#windows).

### <a name="proactive-quality-update-release-10028"></a>Rilascio dell'aggiornamento qualitativo proattivo: 10.0.28
**Versione dell'app: 10.0.1265.89**
**Articolo corrispondente più recente della KB: 745340**

| Stazione | Regioni | Programmazione completata| Prossima programmazione sandbox
|---|---|---|---|
| Stazione 1 | Canada centrale, Canada orientale, Francia centrale, India centrale, Norvegia orientale, Svizzera occidentale | Dal 15 settembre al 18 settembre 2022, dal 19 settembre al 22 settembre 2022 e dal 7 ottobre al 10 ottobre 2022 | Dal 25 ottobre al 28 ottobre 2022 |
| Stazione 2 | Francia meridionale, India meridionale, Norvegia occidentale, Svizzera settentrionale, Sud Africa settentrionale, Australia orientale, Regno Unito meridionale, Emirati Arabi Uniti settentrionale, Giappone orientale, Australia sud est, Sud Est Asiatico | Dal 25 settembre al 28 settembre 2022 e dal 7 ottobre al 10 ottobre 2022 | Dal 25 ottobre al 28 ottobre 2022 |
| Stazione 3 | Asia orientale, Regno Unito occidentale, Giappone occidentale, Brasile meridionale, Europa occidentale, Stati Uniti orientali, Emirati Arabi Uniti centrali | Dal 26 settembre al 29 settembre 2022 e dal 7 ottobre al 10 ottobre 2022 | Dal 25 ottobre al 28 ottobre 2022 |
| Stazione 4 | Nord Europa, Stati Uniti centrali, Stati Uniti occidentali | Dal 28 settembre al 1 ottobre 2022 e dal 7 ottobre al 10 ottobre 2022 | Dal 25 ottobre al 28 ottobre 2022 |
| Stazione 5 | DoD, Government Community Cloud, Cina | Non programmato | Non programmato |

### <a name="proactive-quality-update-release-10029"></a><a name="schedule"></a>Rilascio dell'aggiornamento qualitativo proattivo: 10.0.29
**Versione dell'app: 10.0.1326.70**
**Articolo corrispondente più recente della KB: 748926**

| Stazione | Regioni | Programmazione completata | Prossima programmazione sandbox|
|---|---|---|---|
| Stazione 1 | Canada centrale, Canada orientale, Francia centrale, India centrale, Norvegia orientale, Svizzera occidentale | Dal 14 ottobre al 17 ottobre 2022 | Dal 2 novembre al 5 novembre 2022 |
| Stazione 2 | Francia meridionale, India meridionale, Norvegia occidentale, Svizzera settentrionale, Sud Africa settentrionale, Australia orientale, Regno Unito meridionale, Emirati Arabi Uniti settentrionale, Giappone orientale, Australia sud est, Sud Est Asiatico | Dal 15 ottobre al 18 ottobre 2022 | Dal 2 novembre al 5 novembre 2022 |
| Stazione 3 | Asia orientale, Regno Unito occidentale, Giappone occidentale, Brasile meridionale, Europa occidentale, Stati Uniti orientali, Emirati Arabi Uniti centrali | Dal 16 ottobre al 19 ottobre 2022 | Dal 2 novembre al 5 novembre 2022 |
| Stazione 4 | Nord Europa, Stati Uniti centrali, Stati Uniti occidentali | Dal 17 ottobre al 20 ottobre 2022 | Dal 2 novembre al 5 novembre 2022 |
| Stazione 5 | DoD, Government Community Cloud, Cina | Non programmato | Non programmato |

> [!IMPORTANT] 
> Con cinque giorni di anticipo, Microsoft aggiornerà la pianificazione precedente e invierà notifiche tramite posta elettronica all'insieme di ambienti pianificati per ricevere questi aggiornamenti di qualità. La pianificazione precedente è applicabile solo agli ambienti a cui è stato notificato un aggiornamento imminente. Per informazioni sulle ore notturne per ciascuna area, vedi [Quali sono le finestre di manutenzione pianificate per area?](../../dev-itpro/deployment/plannedmaintenance-selfservice.md#windows).
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
I passaggi seguenti sono una soluzione temporanea mentre continuiamo a lavorare per fornire una soluzione migliore per identificare l'elenco delle modifiche che entrano in un payload di aggiornamento della qualità. 

Utilizza KB# 745340 per l'addestramento di aggiornamento della qualità 10.0.28 e la relativa versione dell'app 10.0.1265.89.

1. In LCS e apri la pagina **Dettagli ambiente** per il tuo sandbox. 
2. Nella sezione **Aggiornamenti disponibili** seleziona **Visualizza aggiornamento** per l'ultima build di aggiornamento della qualità. 
3. Esporta la build in un CSV o in un file Microsoft Excel.
4. Nel file esportato, ordina le informazioni in base all'ora (prima la meno recente) e quindi cerca il numero KB 745340 nella colonna **ID aggiornamento**. Dovrebbe essere possibile vedere l'elenco delta degli articoli KB.
 
 > [!NOTE]
 > L'esportazione in un file CSV o di Excel deve avvenire prima dell'aggiornamento dell'ambiente. In caso contrario, puoi utilizzare un ambiente con una configurazione simile in cui non è installato l'aggiornamento e seguire i passaggi precedenti.

[![Esempio di ambiente con aggiornamento della qualità.](./media/how-to-get-kb-list-pqu.png)](./media/how-to-get-kb-list-pqu.png)

## <a name="what-is-the-process-if-a-critical-issue-is-found-after-a-quality-update"></a>Qual è la procedura se viene rilevato un problema critico dopo un aggiornamento di qualità?
Un problema critico o una regressione è uno o più eventi che in genere causano a più clienti un'esperienza degradata con uno o più dei nostri servizi. Questi problemi possono causare tempi di inattività non pianificati, tra cui indisponibilità, degrado delle prestazioni e interferenza con la gestione del servizio. Se c'è un ampio impatto sui clienti a causa di tali regressioni, interromperemo l'implementazione di un aggiornamento di qualità finché non saremo in grado di comunicare e risolvere il problema. In genere, il successivo aggiornamento di qualità avrà la correzione necessaria per riprendere la distribuzione.

Se l'ambiente di un singolo cliente è interessato, contatta il supporto Microsoft per aprire un ticket. Sulla base della giustificazione, interromperemo l'implementazione dell'aggiornamento di qualità in tutti gli altri ambienti di quel progetto fino a quando il problema non sarà risolto.

## <a name="can-customers-still-manually-apply-hotfix-updates-from-lcs"></a>I clienti possono ancora applicare manualmente gli aggiornamenti degli hotfix da LCS?
Sì. Per garantire la parità continua con il funzionamento degli hotfix, gli aggiornamenti degli hotfix possono ancora essere applicati agli ambienti dei clienti in LCS. Tuttavia, è importante notare che gli hotfix distribuiti come parte di un aggiornamento di qualità passano attraverso l'SDP standard prima della distribuzione dell'aggiornamento. Ciò riduce il rischio di regressioni dovute alla qualità superiore. Si consiglia di scegliere un aggiornamento di qualità rispetto all'applicazione manuale degli hotfix per una maggiore affidabilità.

## <a name="can-customers-proactively-install-a-quality-update-build-ahead-of-the-schedule"></a>I clienti possono installare in modo proattivo un aggiornamento di qualità prima della pianificazione?
Sì. È possibile installare un aggiornamento di qualità in modo proattivo. Microsoft salterà l'aggiornamento se la versione di build corrente dell'ambiente è uguale o superiore all'aggiornamento di qualità in questione.

## <a name="if-an-environment-has-an-upcoming-scheduled-monthly-service-update-within-a-week-will-it-still-receive-quality-updates"></a>Se un ambiente ha un imminente aggiornamento del servizio mensile programmato entro una settimana, riceverà comunque aggiornamenti della qualità?
- Gli aggiornamenti della qualità non vengono applicati negli ambienti di produzione se è previsto un aggiornamento del servizio imminente pianificato entro una settimana dalla pianificazione dell'aggiornamento della qualità.
- Se un ambiente sandbox ha la stessa versione di build o superiore rispetto all'imminente aggiornamento della qualità, verrà ignorato.
- Se un ambiente di produzione ha la stessa versione di build o superiore rispetto all'imminente aggiornamento della qualità, verrà ignorato.
- Se un sandbox ha una versione di build uguale o superiore a causa di un aggiornamento della qualità o di un aggiornamento manuale della produzione, la produzione riceverà comunque la versione pianificata dell'aggiornamento mensile del servizio. Se non si desidera che l'ambiente di produzione pianificato venga aggiornato alla versione di aggiornamento del servizio, è possibile sospendere l'aggiornamento del servizio da LCS. 
- Ti consigliamo di utilizzare l'ultima build di aggiornamento della qualità per testare le modifiche per un aggiornamento del servizio imminente per stabilità e risultati migliorati.

## <a name="if-an-environment-has-an-upcoming-scheduled-action-and-a-scheduled-quality-update-in-the-same-maintenance-window-will-it-still-receive-the-quality-update"></a>Se un ambiente ha un'azione pianificata imminente e un aggiornamento della qualità pianificato nella stessa finestra di manutenzione, riceverà comunque l'aggiornamento della qualità?
In caso di contesa con un'azione preprogrammata, ad esempio un Ripristino temporizzato, l'aggiornamento della qualità verrà riprogrammato alla successiva finestra di manutenzione disponibile entro la finestra di quattro giorni. Per altre informazioni sulla programmazione, vedi [Qual è la pianificazione per gli aggiornamenti di qualità proattivi?](#schedule). 

## <a name="can-an-environment-be-brought-back-to-its-previous-state-if-there-are-issues-after-a-quality-update-is-applied"></a>È possibile riportare un ambiente allo stato precedente se si verificano problemi dopo l'applicazione di un aggiornamento della qualità?
Dopo l'applicazione di un aggiornamento di qualità, non viene eseguito il rollback in nessun caso. Sono disponibili solo opzioni di patch forward per mitigare i problemi.

## <a name="what-about-fda-regulation-and-gpx"></a>Che dire del regolamento FDA e del GPX?
Il piano per i clienti soggetti a convalida e regolamentazione FDA è ancora in evoluzione. Aspettati presto altri aggiornamenti in questo argomento. Per ora, tutti questi clienti sono esenti da aggiornamenti di qualità. Per garantire che un cliente rientri nelle normative FDA, visita [Offerta Microsoft Azure GPX](/azure/compliance/offerings/offering-gxp).

## <a name="what-versions-of-service-updates-are-supported-for-these-quality-updates"></a>Quali versioni degli aggiornamenti del servizio sono supportate per questi aggiornamenti di qualità?
I clienti che utilizzano tutte le versioni supportate degli aggiornamenti del servizio si qualificano per gli aggiornamenti della qualità. 

## <a name="finance-and-operations-apps-deployments-with-retail-components-typically-require-additional-work-in-addition-to-having-to-redeploy-mpos-how-will-these-quality-updates-impact-the-retailsdk"></a>Le distribuzioni di app per la finanza e le operazioni con componenti di vendita al dettaglio in genere richiedono lavoro aggiuntivo oltre alla ridistribuzione di MPOS. In che modo questi aggiornamenti di qualità influiranno su RetailSDK? 
Poiché la natura degli hotfix in sé non cambia nel payload degli aggiornamenti di qualità, non prevediamo alcun impatto aggiuntivo in questo momento specificamente correlato ai componenti di vendita al dettaglio.

## <a name="is-there-any-impact-to-cloud-hosted-environments-che"></a>C'è qualche impatto sugli ambienti ospitati nel cloud (CHE)? 
Gli ambienti CHE non rientrano nell'ambito degli aggiornamenti di qualità perché non rientrano nell'ambito di competenza di Microsoft

## <a name="are-there-any-integration-issues-with-microsoft-dataverse"></a>Ci sono problemi di integrazione con Microsoft Dataverse? 
Non sono noti problemi di integrazione per gli aggiornamenti di qualità con Dataverse.

