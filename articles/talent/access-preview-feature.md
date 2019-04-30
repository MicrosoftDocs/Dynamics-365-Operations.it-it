---
title: Accesso alle funzionalità di anteprima in Talent
description: Questo argomento descrive come un amministratore può attivare le funzionalità in anteprima ed elenca le funzionalità attualmente attivate per l'anteprima.
author: andreabichsel
manager: AnnBe
ms.date: 04/17/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-04-30
ms.dyn365.ops.version: AX 7.1.0, Talent April 2018 update
ms.openlocfilehash: 060a36185641d5bb7912631b7c857c5c4331c8b7
ms.sourcegitcommit: 608e68b603afef9eb98d8fb25e90109c2473ef87
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2019
ms.locfileid: "856326"
---
# <a name="access-preview-features-in-talent"></a>Accesso alle funzionalità di anteprima in Talent

[!include[banner](../includes/banner.md)]

Nell'ambito della continua implementazione di funzionalità del prodotto, vogliamo consentire ai clienti di utilizzare al più presto le nuove funzionalità. Gli amministratori possono visualizzare e utilizzare le funzionalità in anteprima nei loro ambienti. Queste funzionalità sono quasi pronte per la disponibilità generale e sono state sottoposte a test esaurienti. Il nostro scopo è di ottenere un ultimo riscontro e la convalida dai clienti prima del rilascio generale delle funzionalità.

Questo argomento descrive come un amministratore può attivare le funzionalità in anteprima ed elenca le funzionalità attualmente disponibili per l'anteprima. L'elenco sarà aggiornato a mano a mano che vengono rilasciate nuove funzionalità in anteprima e le versioni di disponibilità generale delle funzionalità. Il rilascio di nuove funzionalità in anteprima non viene notificato. Gli utenti scopriranno tali funzionalità durante l'utilizzo del prodotto.

## <a name="enable-or-disable-preview-features"></a>Attivare o disattivare le funzionalità in anteprima

È possibile utilizzare l'impostazione **Funzionalità di anteprima** nell'interfaccia di amministrazione di Microsoft Dynamics 365 for Talent per attivare o disattivare le funzionalità in anteprima. Per impostazione predefinita, l'impostazione è disattivata. L'azione di attivazione o disattivazione delle funzionalità in anteprima è specifica dell'ambiente.

> [!IMPORTANT]
> Attivando l'impostazione **Funzionalità di anteprima**, si attivano le funzionalità in anteprima per tutti gli utenti dell'organizzazione in quell'ambiente. Disattivando l'impostazione, si disattivano le funzionalità in anteprima e le si rendono inaccessibili agli utenti. Il supporto delle funzionalità in anteprima in Talent è limitato. È possibile che utilizzino minori misure di privacy e di sicurezza e non sono incluse nel contratto di servizio di Talent. Si consiglia di non utilizzare le funzionalità in anteprima per elaborare dati personali (ovvero qualsiasi informazione che potrebbe consentire l'identificazione dell'utente) o per elaborare altri dati soggetti a requisiti di conformità legali o normativi.

### <a name="enable-or-disable-preview-features-for-your-organization"></a>Attivare o disattivare le funzionalità in anteprima per l'organizzazione

#### <a name="attract"></a>Attrai

1. Accedere a Microsoft Dynamics 365 for Talent: Attract.
2. Nel menu **Impostazione** (il simbolo di ingranaggio) nell'angolo superiore destro, selezionare **Impostazioni di amministrazione**.
3. Nella scheda **Gestione funzionalità**, selezionare l'opzione accanto a **Funzionalità di anteprima** di modo che diventi blu.
4. Facoltativamente è possibile controllare le singole funzionalità abilitando/disabilitando specifiche funzionalità in questa pagina.
5. Aggiornare il browser per visualizzare le nuove funzionalità. Tutti gli utenti che hanno già eseguito l'accesso, vedranno le funzionalità all'accesso successivo oppure possono aggiornare il browser per visualizzare le funzionalità immediatamente.

#### <a name="core-hr"></a>Core HR

1. Accedere a Talent. Viene visualizzata l'area di lavoro delle risorse Core HR, da cui verranno completati i passaggi rimanenti. 
2. Selezionare **Amministrazione sistema \> Parametri sistema Links**.
3. Nella **pagina Parametri di sistema** nella scheda **Funzionalità di anteprima**, impostare l'opzione **Abilitare la modalità di anteprima per tutti gli utenti** su **Sì** per rendere disponibili le funzionalità in anteprima.

> [!NOTE]
> Per disattivare le funzionalità in anteprima, utilizzare gli stessi passaggi. Quando si disattivano le funzionalità in anteprima, diventano inaccessibili agli utenti e potrebbero verificarsi degli errori nei processi associati alle funzionalità.

## <a name="features-that-are-currently-in-preview"></a>Funzionalità attualmente in anteprima

### <a name="attract"></a>Attrai

- **Candidati pertinenti in una mansione** - I selezionatori e responsabili di assunzione possono verificare facilmente quali candidati possono essere il più appropriati per la mansione tra tutti i candidati. I 5 candidati principali vengono visualizzati in base alla rilevanza del profilo/curriculum rispetto alla descrizione mansione.
- **Mansioni pertinenti** - I candidati ora vedono un elenco di altri mansioni rilevanti in base al relativo curriculum/profilo e alle descrizioni di posizione lavorativa.  Attualmente questo viene visualizzato ai candidati una volta che presentano una domanda di lavoro come suggerimento per altre opportunità.
- **Supporto di EEO/OFCCP** - Nuovi tipi di attività consentono l'utilizzo di un modulo predefinito per la raccolta dei dati per le pari opportunità di impiego e OFCCP (Office of Federal Contract Compliance Program) del candidato.  Questo modulo è predefinito e non può essere modificato.

    > [!NOTE]
    > Le posizioni lavorative pubblicate sono visibili solo ai clienti che effettuano la sottoscrizione a uno o più prodotti LinkedIn relativi alle posizioni lavorative. In caso contrario, i clienti vedranno una posizione lavorativa solo se la cercano. Le posizioni lavorative pubblicate su LinkedIn non sono visibili immediatamente. È possibile che lo diventino dopo alcune ore dalla pubblicazione eseguita da Attract.

- **Applicazione candidato** – Ora i candidati interni ed esterni possono inviare la loro candidatura direttamente dalla pagina delle posizioni lavorative sul sito delle carriere.
- **Gestione offerta** – Gli utenti possono ora creare lettere di offerta a partire da modelli che includono segnaposto. A mano a mano che i candidati avanzano nella fase di offerta, i reclutatori e i responsabili assunzioni possono utilizzare lo strumento Offerta per preparare un'offerta formale di un candidato tramite modelli, inviare l'offerta per l'approvazione interna e inviare l'offerta al candidato per la firma. Molte nuove funzioni saranno aggiunte allo strumento Offerta nel tempo e la funzionalità in anteprima verrà aggiornata con queste funzioni non appena saranno pronte per il rilascio in anteprima.

### <a name="core-hr"></a>Core HR

- **Iscrizione aperta** - L'iscrizione aperta per benefit fornisce ai dipendenti una semplice esperienza Self-service per selezionare i loro benefit. Gli amministratori delle Risorse umane possono configurare il processo di registrazione aperta di benefit per la propria organizzazione nonché l'esperienza di registrazione per i dipendenti utilizzando una soluzione guidata semplice.

## <a name="feedback"></a>Feedback

Indipendentemente che il riscontro sia positivo o negativo, vogliamo ricevere commenti degli utenti riguardo l'utilizzo delle funzionalità in anteprima. Invitiamo gli utenti a pubblicare regolarmente i loro commenti relativi all'utilizzo di queste o altre funzionalità sui siti elencati di seguito.

- [Community](https://community.dynamics.com/enterprise/f/759?pi53869=0&category=Talent) - Questo sito è una risorsa eccellente dove gli utenti possono discutere casi d'uso, porre domande e ottenere informazioni dalla community.
- I siti elencati di seguito possono essere utilizzati per suggerire idee sul prodotto. Invitiamo gli utenti a indicare le funzionalità che vorrebbero fossero integrate nel prodotto e anche le eventuali modifiche che vorrebbero apportare alle funzionalità esistenti.

    - [Idee per Attract](https://powerusers.microsoft.com/t5/Ideas-for-Attract/idb-p/Attract)
    - [Core HR](https://powerusers.microsoft.com/t5/Ideas-for-Human-Resources/idb-p/HumanResources)

Si raccomanda di non includere dati personali (qualsiasi informazione che possa consentire l'identificazione dell'utente) nel riscontro o nei commenti sul prodotto inviati. Le informazioni raccolte potrebbero essere analizzate ulteriormente e non saranno utilizzate per soddisfare richieste in base alle normative sulla privacy applicabili. I dati personali raccolti separatamente in questi programmi sono soggetti all'[Informativa sulla privacy di Microsoft](https://privacy.microsoft.com/privacystatement).

> [!TIP]
> Si consiglia di aggiungere questo argomento ai Preferiti per mantenersi aggiornati sulle nuove funzionalità in anteprima che vengono rilasciate.
