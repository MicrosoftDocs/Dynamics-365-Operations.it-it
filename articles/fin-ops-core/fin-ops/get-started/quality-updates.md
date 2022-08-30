---
title: Aggiornamenti qualitativi proattivi
description: Questo articolo fornisce informazioni sulla distribuzione proattiva di aggiornamenti qualitativi.
author: rashmansur
ms.date: 08/23/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: rashmim
ms.search.validFrom: 2022-08-19
ms.search.form: ''
ms.dyn365.ops.version: 10.0.29
ms.openlocfilehash: 9d81cb15e9a127e7bea7ad9b5e0f50a1ee543f71
ms.sourcegitcommit: 78e85ad49634cd31459fdb7325cb273352bf1501
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/23/2022
ms.locfileid: "9338138"
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

    Per gli utenti interattivi, è possibile che una sessione attiva venga interrotta e che il nuovo tentativo passi all'ambiente aggiornato. Con l'introduzione della [programmazione batch basata su priorità](../../dev-itpro/sysadmin/priority-based-batch-scheduling.md), ora disponibile dietro consenso esplicito, la programmazione e l'elaborazione batch vengono ripristinate e riprese immediatamente dopo l'aggiornamento. La programmazione batch basata su priorità sarà disponibile per i clienti prima che inizino a partecipare alla distribuzione proattiva degli aggiornamenti qualitativi per i loro ambienti di produzione.

- **Ore notturne** – Le ore notturne sono definite per ogni area di Azure e gli aggiornamenti con tempi di inattività prossimi allo zero si verificheranno durante il periodo di ore notturne.

## <a name="the-proactive-update-process"></a>Processo di aggiornamento proattivo

La distribuzione degli aggiornamenti qualitativi proattivi seguirà un processo di distribuzione sicura (SDP). Le specifiche dell'SDP si evolveranno, ma gli aggiornamenti qualitativi verranno inizialmente distribuiti in ambienti sandbox. Il processo inizierà con gli ambienti che acconsentono esplicitamente alla distribuzione anticipata. Con l'aumento della percentuale di sandbox distribuite correttamente, inizierà la distribuzione negli ambienti di produzione. Ancora una volta, il processo inizierà con gli ambienti che acconsentono esplicitamente alla distribuzione anticipata. I sistemi di ascolto monitoreranno la telemetria del sistema e gli incidenti Livesite e interromperanno il rollout di una versione specifica se viene rilevata una qualsiasi regressione. I clienti potranno comunque eseguire il pull degli aggiornamenti qualitativi prima dell'implementazione proattiva, se lo desiderano.

I dati sulla gestione delle release correnti mostrano che meno del 3% delle regressioni viene introdotto negli aggiornamenti qualitativi. Con una maggiore attenzione all'eliminazione della regressione e un SDP migliorato, il potenziale impatto delle regressioni sarà notevolmente inferiore rispetto ai guadagni in termini di qualità che si ottengono con una distribuzione più rapida delle correzioni ai clienti.

## <a name="process-changes"></a>Elabora modifiche

È attualmente in corso l'implementazione di una serie di modifiche al processo prima dell'attivazione della distribuzione proattiva degli aggiornamenti qualitativi:

- **Schema** – Gli strumenti garantiranno che le build degli aggiornamenti qualitativi includano solo le modifiche dello schema che possono essere applicate mentre il servizio è online. Questo approccio consentirà di preservare la capacità di applicare l'aggiornamento con tempi di inattività prossimi allo zero.
- **Maggiore controllo delle modifiche** – Attualmente, esiste già una fase supplementare del processo per approvare le modifiche da includere in un aggiornamento qualitativo. Il controllo nella fase supplementare verrà aumentato per contribuire a ridurre il potenziale delle regressioni. Non sono consentite modifiche che causano interruzioni negli aggiornamenti qualitativi e il maggiore controllo delle modifiche contribuirà a garantire il raggiungimento di questo obiettivo.
- **Visibilità** – Invieremo notifiche tramite e-mail e Lifecycle Services (LCS) per i prossimi aggiornamenti qualitativi proattivi. Inoltre, i team di supporto e i responsabili della gestione degli incidenti avranno visibilità su dove gli aggiornamenti qualitativi sono stati implementati in modo proattivo.
- **Fallback della versione** – La distribuzione di versioni di anteprima verrà utilizzata per raggruppare tutte le modifiche in un aggiornamento qualitativo proattivo. Se il fallback è necessario dopo una distribuzione proattiva, è possibile eseguirlo tramite il sistema di distribuzione di versioni di anteprima.
- **Designazione della sincronizzazione sandbox** – Meno del 20% dei clienti dispone attualmente di più sandbox e mantiene una sandbox distribuita dove la versione corrisponde alla produzione, per agevolare la risoluzione dei problemi. Nel prossimo futuro, introdurremo la possibilità per i clienti di specificare un ambiente sandbox che non deve ricevere la distribuzione proattiva degli aggiornamenti qualitativi insieme ad altre sandbox, ma che deve invece riceverla in un secondo momento, insieme all'ambiente di produzione. Tieni presente che se un cliente utilizza una sandbox per testare una versione più recente rispetto alla propria produzione, tale sandbox riceverà aggiornamenti qualitativi alla versione più recente.
- 
## <a name="when-will-proactive-quality-updates-start"></a>Quando inizieranno gli aggiornamenti qualitativi proattivi?

La distribuzione degli aggiornamenti qualitativi proattivi per gli ambienti sandbox dovrebbe iniziare a fine settembre o ottobre 2022 per i clienti del cloud pubblico di Azure. Anche gli ambienti di prova inizieranno a ricevere la distribuzione proattiva degli aggiornamenti in quel periodo. A settembre, verrà inviata una notifica a ogni cliente per informarlo sulla pianificazione prevista per gli ambienti. Le eccezioni al processo di distribuzione proattiva degli aggiornamenti saranno consentite solo per i clienti regolamentati dalla FDA. Stiamo ancora lavorando su come verranno gestiti gli ambienti regolamentati e i clienti cloud sovrani e governativi.

Nei prossimi sei mesi, aumenteremo gradualmente la percentuale di ambienti sandbox che ricevono aggiornamenti proattivi, fino a quando tutti gli ambienti designati non saranno inclusi e passeremo all'aggiornamento degli ambienti di produzione. Durante questo periodo, eseguiremo controlli per assicurarci che il processo di distribuzione sia ottimale e che stiamo raggiungendo il nostro obiettivo di payload senza interruzioni.

Poiché i clienti riceveranno regolarmente payload più piccoli, prevediamo che il processo di aggiornamento diventerà più semplice. Adegueremo la frequenza della distribuzione degli aggiornamenti mentre dimostreremo la capacità di eseguire il processo senza interruzioni. Questo processo sta già funzionando efficacemente per la nostra piattaforma e le applicazioni Dataverse e fornisce i miglioramenti previsti nella qualità del servizio. Siamo impazienti di fare lo stesso passo avanti per le applicazioni per la finanza e le operazioni.
