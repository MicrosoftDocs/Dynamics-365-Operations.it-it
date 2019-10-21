---
title: Accedere alle funzionalità in anteprima in Microsoft Dynamics 365 Talent
description: Questo argomento descrive come un amministratore può attivare le funzionalità in anteprima in Microsoft Dynamics 365 Talent ed elenca le funzionalità attualmente attivate per l'anteprima.
author: tracykeya
manager: AnnBe
ms.date: 05/30/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: trkeya
ms.search.validFrom: 2018-04-30
ms.dyn365.ops.version: AX 7.1.0, Talent April 2019 update
ms.openlocfilehash: e607c2ba4b544d60c97d98bd49b07d912d83ebc6
ms.sourcegitcommit: 434dd21450bddcd891aba0555b9853d9ba0afb6f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2019
ms.locfileid: "2008704"
---
# <a name="manage-preview-features"></a>Gestire le funzionalità di anteprima

[!include[banner](../includes/banner.md)]

Nell'ambito della continua implementazione di funzionalità di gestione risorse umane per Microsoft Dynamics 365 Talent, vogliamo consentire ai clienti di utilizzare al più presto le nuove funzionalità. Gli amministratori possono visualizzare e utilizzare le funzionalità in anteprima nei loro ambienti. Queste funzionalità sono quasi pronte per la disponibilità generale e sono state sottoposte a test esaurienti. Il nostro scopo è di ottenere un ultimo riscontro e la convalida dai clienti prima del rilascio delle funzionalità per una disponibilità generale.

Questo argomento descrive come è possibile attivare le funzionalità in anteprima ed elenca le funzionalità attualmente disponibili per l'anteprima. L'elenco sarà aggiornato a mano a mano che vengono rilasciate nuove funzionalità in anteprima e le versioni di disponibilità generale delle funzionalità. Il rilascio di nuove funzionalità in anteprima non viene notificato. Gli utenti scopriranno tali funzionalità durante l'utilizzo del prodotto. Per ulteriori informazioni sulle nuove funzionalità, vedere [Novità o modifiche in Dynamics 365 Talent](./whats-new.md) e [Note sulla versione di Dynamics 365 e Power Platform](https://docs.microsoft.com/business-applications-release-notes).

## <a name="enable-or-disable-preview-features"></a>Attivare o disattivare le funzionalità in anteprima

Per accedere alle funzionalità in anteprima, è necessario dapprima attivarle nel proprio ambiente. L'attivazione o la disattivazione delle funzionalità in anteprima è specifica dell'ambiente.

> [!IMPORTANT]
> Quando si attiva l'impostazione **Funzionalità in anteprima**, si attivano le funzionalità in anteprima per tutti gli utenti dell'organizzazione in quell'ambiente. Quando si disattiva l'impostazione, si disattivano le funzionalità in anteprima e le si rendono inaccessibili agli utenti. Il supporto delle funzionalità in anteprima in Talent è limitato. È possibile che utilizzino minori misure di privacy e di sicurezza e non sono incluse nel contratto di servizio di Talent. Si consiglia di non utilizzare le funzionalità in anteprima per elaborare dati personali (ovvero qualsiasi informazione che potrebbe consentire l'identificazione dell'utente) o per elaborare altri dati soggetti a requisiti di conformità legali o normativi.

### <a name="attract"></a>Attract

1. Accedere a Microsoft Dynamics 365 Talent: Attract.
2. Nel menu **Impostazione** (il simbolo di ingranaggio) nell'angolo superiore destro, selezionare **Interfaccia di amministrazione**.
3. Nella scheda **Gestione funzionalità**, selezionare l'opzione accanto a **Funzionalità in anteprima** di modo che diventi blu e sia impostata su **Attivata**.

    ![Attivare funzionalità in anteprima in Attract](./media/attract-enable-preview-features.png)

4. Selezionare o deselezionare singole funzionalità in anteprima. Se non si esegue alcuna operazione, tutte le funzionalità in anteprima disponibili vengono attivate.
5. Aggiornare il browser per visualizzare le nuove funzionalità. Tutti gli utenti che hanno già eseguito l'accesso, vedranno le funzionalità all'accesso successivo oppure possono aggiornare il browser per visualizzare le funzionalità immediatamente.

> [!NOTE]
> Alcune funzionalità in anteprima potrebbero richiedere una configurazione aggiuntiva. Utilizzare i collegamenti accanto alla funzionalità in anteprima per completarne la configurazione.

### <a name="core-hr"></a>Core HR

1. Accedere a Talent.
2. Selezionare **Amministrazione sistema** e quindi la scheda **Collegamenti**.
3. Nella pagina **Amministrazione sistema**, in **Impostazione**, selezionare **Parametri di sistema**.
4. Nella pagina **Parametri di sistema**, selezionare la scheda **Funzionalità in anteprima**.
5. Impostare l'opzione **Abilitare la modalità in anteprima per tutti gli utenti** su **Sì** per rendere disponibili le funzionalità in anteprima.

    ![Abilitare le funzionalità in anteprima in Core HR](./media/corehr-enable-preview-features.png)

> [!NOTE]
> Per disattivare le funzionalità in anteprima, utilizzare la stessa procedura, ma impostare **Abilitare la modalità in anteprima per tutti gli utenti** su **No**. Quando si disattivano le funzionalità in anteprima, diventano inaccessibili agli utenti e potrebbero verificarsi degli errori nei processi associati alle funzionalità.

### <a name="onboard"></a>Inserisci

Non sono disponibili funzionalità in anteprima per Microsoft Dynamics 365 Talent: Onboard.

## <a name="features-that-are-currently-in-preview"></a>Funzionalità attualmente in anteprima

### <a name="attract"></a>Attract

- [Suggerimento candidato](./intelligent-recommendations.md#candidate-recommendations) - Se sono disponibili più di dieci candidati con curriculum o profili completi, i candidati che soddisfano maggiormente i requisiti di una posizione vengono visualizzati nella sezione **Candidati da considerare** della pagina di quella posizione.
- [Suggerimento posizione](./intelligent-recommendations.md#job-recommendations) - Se più di dieci posizioni vengono pubblicate sul sito di avanzamento professionale, Attract fornisce suggerimenti sulle posizioni ai prospect.
- [Integrazione di Broadbean](./posting-jobs-external.md#post-jobs-to-broadbean) - È possibile pubblicare annunci di lavoro da Attract a Broadbean, un sito di pubblicazione di annunci di lavoro esterno. Dopo l'attivazione di questa funzionalità in anteprima, è necessario completare l'impostazione immettendo il nome utente, l'ID client e il token di crittografia Broadbean.
- [Analisi](./analytic-reports.md) - In Hub analisi, i team di assunzione possono visualizzare le metriche chiave per una singola posizione, nonché metriche aggregate per tutte le posizioni.
- [Pari opportunità di impiego](./activities-attract.md) - Nuovi tipi di attività consentono l'utilizzo di un modulo predefinito per la raccolta dei dati per le pari opportunità di impiego e OFCCP (Office of Federal Contract Compliance Program) di un candidato. Il modulo predefinito non può essere modificato.
- [Suggerimento prospect](./intelligent-recommendations.md#prospect-recommendations) - Attract esamina i candidati passati e quelli correnti per fornire un elenco di prospect appropriati per la posizione.
- [Ricerca per pertinenza](./attract-talent-pools.md#search-and-view-candidate-profiles) - È possibile cercare competenze specifiche, nomi o percorsi formativi nell'intero database del candidato. Attract esegue la ricerca nell'intero profilo ed evidenzia tutte le corrispondenze trovate. Attract esegue la ricerca anche in tutti i documenti disponibili di un candidato e classifica i risultati della ricerca in modo intelligente.
- [Destinatari delle attività](./whats-new-talent-march-20.md#setting-the-audience-on-activities)  – È possibile impostare i destinatari delle attività (ad esempio Colloquio, Programmazione o Feedback) su **Tutti i candidati**, **Candidati interni** o **Candidati esterni**. È possibile inviare attività ai clienti, ad esempio Microsoft Forms, video YouTube e contenuto Web, a tutti i candidati, solo ai candidati interni, solo ai candidati esterni o al team di assunzione.
- [Domanda con LinkedIn](./career-site.md#enable-applying-for-jobs-with-linkedin-profiles) - È possibile impostare un'opzione nel sito di avanzamento professionale di Attract per consentire ai candidati di fare domanda utilizzando LinkedIn. Questa funzionalità migliora il processo di candidatura consentendo ai candidati di utilizzare il relativo profilo LinkedIn per completare automaticamente le candidature sul sito di avanzamento professionale.
- [Tracciabilità origine](./source-tracking.md) - Attract tiene traccia dell'origine delle domande di lavoro dei candidati per fornire informazioni utili che consentono di migliorare il processo di selezione. È inoltre possibile selezionare l'origine di una domanda di lavoro quando si aggiunge un candidato a una posizione o a un pool di talenti.
- [Medaglia d'argento](./whats-new-talent-march-20.md#designate-silver-medalists-to-assign-high-value-applicants-for-future-positions) Se dei candidati sono un'ottima soluzione per la posizione corrente nell'organizzazione, ma a questi non è stata fatta un'offerta, è possibile designarli come medaglie d'argento. Questa funzionalità consente di ridurre la durata del processo di assunzione quando sarà necessario coprire una posizione simile in futuro.

### <a name="core-hr"></a>Core HR

- [Convalidare i dati della gerarchia delle posizioni](./whats-new-talent-may-13-2019.md#new-page-to-validate-position-hierarchy-data) - È possibile convalidare la gerarchia manageriale per tutti i riferimenti circolari che sono stati importati inavvertitamente.
- [Specificare i codici motivo per i tipi di congedo](./whats-new-talent-may-13-2019.md#specify-reason-codes-on-leave-types) - È possibile specificare i codici motivo per i tipi di congedo.
- [Richiedere codici motivo per richieste di permesso](./whats-new-talent-may-13-2019.md#require-reason-codes-for-specific-leave-types-on-time-off-requests) - Oltre alla definizione dei codici motivo per i tipi di congedo, è possibile richiedere codici motivo per le richieste di permesso.
- [Fornire un elenco di transazioni assenze e congedo per le Risorse umane](./whats-new-talent-may-13-2019.md#provide-a-leave-and-absence-transaction-list-for-hr) - È possibile visualizzare un elenco di transazioni assenze e congedi per fornire informazioni sui saldi permesso.

### <a name="onboard"></a>Inserisci

Non sono attualmente disponibili funzionalità in anteprima per Onboard.

## <a name="feedback"></a>Commenti e suggerimenti

Vogliamo ricevere commenti degli utenti riguardo l'utilizzo di una o più di queste funzionalità in anteprima. Invitiamo gli utenti a pubblicare regolarmente i loro commenti relativi all'utilizzo di queste o altre funzionalità sui siti elencati di seguito:

- [Community](https://community.dynamics.com/enterprise/f/759?pi53869=0&category=Talent) - Questo sito è una risorsa eccellente dove gli utenti possono discutere casi d'uso, porre domande e ottenere informazioni dalla community.
- Invitiamo gli utenti a indicare le funzionalità che vorrebbero fossero integrate nel prodotto o le modifiche che dovrebbero essere apportate alle funzionalità esistenti. È possibile suggerire idee sul prodotto su tali siti:

    - [Idee per Attract](https://powerusers.microsoft.com/t5/Ideas-for-Attract/idb-p/Attract)
    - [Idee per Core HR](https://powerusers.microsoft.com/t5/Ideas-for-Human-Resources/idb-p/HumanResources)
    - [Idee per Onboard](https://powerusers.microsoft.com/t5/Ideas-for-Onboard/idb-p/Onboard)

Assicurarsi di non includere dati personali (qualsiasi informazione che possa consentire l'identificazione dell'utente) nel riscontro o nei commenti sul prodotto inviati. Le informazioni raccolte potrebbero essere analizzate ulteriormente e non vengono utilizzate per soddisfare richieste in base alle normative sulla privacy applicabili. I dati personali raccolti separatamente in questi programmi sono soggetti all'[Informativa sulla privacy di Microsoft](https://privacy.microsoft.com/privacystatement).

> [!TIP]
> Si consiglia di aggiungere questo argomento ai Preferiti per mantenersi aggiornati sulle nuove funzionalità in anteprima che vengono rilasciate.

## <a name="see-also"></a>Vedere anche

- [Provare o acquistare app Talent](https://dynamics.microsoft.com/talent/overview/)
- [Novità](./whats-new.md)
- [Note sulla versione](https://docs.microsoft.com/business-applications-release-notes/index)
- [Ottenere supporto per Talent](./talent-support.md)
