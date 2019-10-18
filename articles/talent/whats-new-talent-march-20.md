---
title: Novità o modifiche in Dynamics 365 Talent (20 marzo 2019)
description: Questo argomento descrive le funzionalità nuove o modificate di Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 03/20/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2019-03-20
ms.dyn365.ops.version: Talent
ms.openlocfilehash: c16082bb18ac5c170aab30f1a2033e0790cbacc1
ms.sourcegitcommit: f87de0f949b5d60993b19e0f61297f02d42b5bef
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/24/2019
ms.locfileid: "2026006"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-march-20-2019"></a>Novità o modifiche in Dynamics 365 Talent (20 marzo 2019)

[!include [banner](includes/banner.md)]

Questo argomento descrive le funzionalità nuove o modificate di Microsoft Dynamics 365 Talent.

## <a name="changes-in-attract"></a>Modifiche in Attract

### <a name="setting-the-audience-on-activities"></a>Impostazione dei destinatari delle attività
Ora è possibile definire i destinatari delle attività nel sistema. Le attività relative al processo (ad esempio Colloquio, Programmazione, Riscontro e Pari opportunità) possono essere impostate per tutti i candidati, i candidati interni e i candidati esterni. Le attività personalizzate, ad esempio Microsoft Forms, video YouTube e contenuto Web, possono essere inviate a tutti i candidati, ai candidati interni, ai candidati esterni o al team di assunzione.  

### <a name="improve-career-site-job-discoverability-search-engine-optimization"></a>Migliorare la possibilità di trovare mansioni nei siti di avanzamento professionale: ottimizzazione per motori di ricerca
Questa funzionalità consente ai crawler dei motori di ricerca di trovare e indicizzare pubblicazioni di annunci di lavoro sul sito di avanzamento professionale di Attract. In questo modo i candidati possono trovare annunci di lavoro pubblicati sul sito di avanzamento professionale di Attract utilizzando motori di ricerca popolari.

### <a name="show-login-hint-to-candidates-who-forgot-their-credentials"></a>Visualizzare il suggerimento di login ai candidati che hanno dimenticato le proprie credenziali
Se un candidato dimentica le credenziali utilizzate per candidarsi a una mansione durante l'apertura di un collegamento salvato o che ha ricevuto tramite posta elettronica, ora vedranno un suggerimento con il nome del provider e il nome utente (offuscati). Ciò consente ai candidati di utilizzare le credenziali corrette per accedere alle domande di lavoro.

### <a name="help-internal-candidates-explore-internal-jobs"></a>Consentire ai candidati interni di esaminare mansioni interne
È stato risolto il problema in cui i candidati esterni potevano visualizzare il nome del selezionatore o del responsabile delle assunzioni di una mansione. Ora solo i candidati interni possono visualizzare i membri del team di assunzione di una mansione. È inoltre più semplice per i candidati interni visualizzare solo le mansioni interne e candidarsi alle stesse. Quando un candidato tenta di accedere al collegamento per visualizzare una mansione interna o candidarsi alla stessa, è obbligato a eseguire l'autenticazione con le credenziali di Azure Active Directory. I candidati interni hanno inoltre la possibilità di contattare il membro del team di assunzione per esprimere il proprio interesse alla mansione o per ottenere ulteriori informazioni sulla stessa. Questa funzionalità è disponibile per tutte le mansioni solo per i candidati interni. Per ulteriori informazioni, vedere [Funzionalità del sito di avanzamento professionale in Attract](./career-site.md).

### <a name="designate-silver-medalists-to-assign-high-value-applicants-for-future-positions"></a>Designare le medaglie d'argento per assegnare candidati di qualità alle posizioni future
I selezionatori e i responsabili delle assunzioni spesso gestiscono un elenco di candidati che erano un'ottima soluzione per una posizione ma ai quali non è stata formulata un'offerta in quanto la posizione era già stata coperta. Tali candidati, definiti medaglie d'argento, sono preziosi in quanto possono ridurre i tempi di assunzione nel caso sia necessario coprire una posizione simile in futuro. Attract ora consente ai selezionatori e ai responsabili delle assunzioni di designare le medaglie d'argento nell'elenco di candidati se i candidati arrivano fino alla fase Offerta. La designazione delle medaglie d'argento sarà visualizzata nell'elenco dei candidati per la mansione, ma anche nella visualizzazione del pool di talenti quando tali candidati sono membri di un qualsiasi pool del selezionatore o del responsabile delle assunzioni. Inoltre, la designazione sarà visualizzata nello storico delle mansioni come parte del profilo del pool di talenti di un candidato. È possibile visualizzare in anteprima questa funzionalità se un amministratore la attiva utilizzando [Gestione funzionalità nell'interfaccia di amministrazione ](https://docs.microsoft.com/dynamics365/unified-operations/talent/access-preview-feature).

### <a name="add-applicants-to-talent-pools"></a>Aggiungere candidati a pool di talenti
È ora più semplice aggiungere candidati a pool di talenti utilizzando una nuova azione nell'elenco Candidati. Selezionando l'icona **Aggiungi a pool di talenti**, il selezionatore o il responsabile delle assunzioni può scegliere dal relativo elenco di pool di talenti e aggiungere facilmente candidati a pool di talenti direttamente dall'elenco Candidati di una mansione.

### <a name="configure-whether-a-resume-is-required-to-apply-for-a-particular-job"></a>Configurare se un curriculum è obbligatorio per candidarsi a una determinata mansione
In base ai suggerimenti dei clienti, i selezionatori possono ora configurare se un curriculum, sotto forma di file caricato, è obbligatorio quando ci si candida a una determinata mansione. Questa configurazione fa parte dell'attività Domanda di lavoro, accessibile nel processo di assunzione. Quando abilitata, a ogni candidato potenziale verrà richiesto di caricare un curriculum quando si candida per quella posizione. La domanda di lavoro non verrà considerata completa se il curriculum non viene caricato. In questo modo, ogni candidato fornirà informazioni sufficienti per consentire al selezionatore di valutarlo.

### <a name="candidates-can-apply-to-a-job-using-their-linkedin-profile"></a>I candidati possono candidarsi a una mansione utilizzando il relativo profilo LinkedIn
I candidati che hanno già un profilo aggiornato in LinkedIn possono candidarsi alle mansioni con un solo clic utilizzando quel profilo.

### <a name="track-how-a-candidate-profile-originated-in-the-system-and-where-your-applicants-discover-the-jobs-they-applied-for"></a>Tenere traccia dell'origine del profilo di un candidato nel sistema e del modo in cui i candidati hanno trovato le mansioni alle quali si candidano
Ora è possibile trovare l'origine del profilo di un determinato candidato in Attract esaminando l'origine del profilo sotto Dettagli candidato nella pagina **Profilo** di una domanda di lavoro o di un profilo del pool di talenti. Analogamente, è possibile stabilire il modo in cui un candidato ha trovato la mansione esaminando l'origine della domanda di lavoro indicata in **Attività per domande di lavoro** nel relativo feed. Queste informazioni sono inoltre disponibili nello storico delle mansioni nel profilo del pool di talenti. Quando i selezionatori o i responsabili delle assunzioni aggiungo manualmente i candidati, verrà loro richiesto di indicare l'origine dalla domanda di lavoro o del profilo del candidato. Quando un candidato si candida per la prima volta, l'origine del profilo sarà quella della domanda di lavoro. È possibile visualizzare in anteprima questa funzionalità se un amministratore la attiva utilizzando [Gestione funzionalità nell'interfaccia di amministrazione ](https://docs.microsoft.com/dynamics365/unified-operations/talent/access-preview-feature). Si noti che i candidati esistenti non disporranno delle informazioni sull'origine. Tuttavia, i selezionatori possono aggiungere tali informazioni manualmente.

## <a name="changes-in-onboard"></a>Modifiche in Onboard

Questa versione include correzioni di bug minori per Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Modifiche di Core HR

Le modifiche descritte in questo sezione sono valide per la build numero 8.1.2195

### <a name="attract-integration-throws-duplicate-record-error-for-applications"></a>L'integrazione di Attract genera un error di record duplicato per Domande di lavoro
In questo aggiornamento, è stato corretto un problema relativo ai record duplicati. Questo problema si verifica all'apertura dell'area di lavoro **Gestione dipendente**.

### <a name="unable-to-close-form-when-editing-name-sequence"></a>Impossibile chiudere il modulo durante la modifica della sequenza nome
Sono state apportate modifiche per correggere un problema durante la modifica della sequenza nome nel modulo Lavoratore.

## <a name="coming-soon"></a>Presto disponibili

###  <a name="advanced-compensation-security-fixed-and-variable"></a>Protezione retribuzione avanzata (fissa e variabile)
In molte organizzazioni, i responsabili delle retribuzioni e dei benefit potrebbero accedere solo a determinati record di retribuzione. Questi record potrebbero essere per dirigenti o dipendenti regionali. Con questa modifica, le Risorse umane possono gestire i piani di retribuzione per differenti gruppi di dipendenti nell'organizzazione. È possibile assegnare ruoli di sicurezza a piani fissi e variabili che determinano l'accesso ai piani e ai dati dei dipendenti correlati ai piani, ad esempio record di stipendi o premi. Solo i ruoli con l'accesso concesso possono elaborare la retribuzione per quei dipendenti.

###  <a name="email-support-for-alerts"></a>Supporto di messaggi di posta elettronica per avvisi
Con l'aggiornamento 24 della piattaforma per Finance and Operations, gli utenti possono creare regole di avviso che inviano automaticamente notifiche di posta elettronica ai contatti quando le notifiche sono attivate da un evento.

### <a name="duplicate-employee-check-interface-changes"></a>Verifica di dipendenti duplicati: modifiche dell'interfaccia
Con questa modifica, i duplicati vengono rilevati durante l'immissione nei campi Nome e uno stato indica il numero di duplicati trovati. È possibile selezionare il collegamento fornito per aprire una nuova pagina e valutare se utilizzare la corrispondenza rilevata. Il modulo Duplicati non si apre automaticamente per non interrompere l'immissione dei dati.


