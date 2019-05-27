---
title: Funzionalità del sito di avanzamento professionale in Attract
description: Questo articolo fornisce una panoramica delle funzionalità del sito di avanzamento professionale rivolto ai candidati in Attract.
author: hasrivas
manager: AnnBe
ms.date: 03/20/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: hasrivas
ms.search.validFrom: 2019-02-12
ms.dyn365.ops.version: AX 7.1.0, Talent April 2018 update
ms.openlocfilehash: a56f162ccc6b6099fd62e0cb7e10076368d8e653
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2019
ms.locfileid: "1518409"
---
# <a name="career-site-functionality-in-attract"></a>Funzionalità del sito di avanzamento professionale in Attract

[!include[banner](../includes/banner.md)]

Questo articolo fornisce una panoramica delle funzionalità del sito di avanzamento professionale rivolto ai candidati in Microsoft Dynamics 365 for Talent: Attract. Descrive inoltre come configurare queste funzionalità.

Attract fornisce un sito di avanzamento professionale per ogni ambiente in un tenant. Ad esempio, se un'organizzazione ha un ambiente di sviluppo e un ambiente di test, un sito di avanzamento professionale viene fornito per l'ambiente di sviluppo e un altro sito di avanzamento professionale per l'ambiente di test. Ogni sito di avanzamento professionale è completamente isolato e ha un proprio meccanismo di autenticazione. Le mansioni e i profili dei candidati non sono condivisi tra siti di avanzamento professionale.

Per impostazione predefinita, il sito di avanzamento professionale è pubblico. Di conseguenza, i candidati possono visualizzare tutte le mansioni contrassegnate come esterne senza eseguire l'accesso. Tuttavia, tutte le altre azioni richiedono l'accesso dei candidati.

## <a name="career-site-management"></a>Gestione del sito per le possibilità di carriera

Per impostare i valori per i seguenti elementi, accedere ad Attract come amministratore, selezionare **Interfaccia di amministrazione** dal menu **Impostazioni** (il simbolo di ingranaggio) e quindi fare clic sulla scheda **Informazioni società**.

-   **Nome organizzazione** - Il nome dell'organizzazione appare sulla barra di spostamento nella parte superiore del sito di avanzamento professionale. Selezionando il nome di organizzazione, i candidati vanno a una pagina contenente tutte le posizioni aperte.

-   **Logo organizzazione** - Un'immagine del logo dell'organizzazione appare in alto a sinistra del sito di avanzamento professionale. Selezionando l'immagine del logo, i candidati vanno a una pagina contenente tutte le posizioni aperte.

    > [!NOTE] 
    > Immagine di logo visualizzata nel sito di avanzamento professionale ha un'altezza fissa di 20 pixel. L'immagine che si aggiunge nell'Interfaccia di amministrazione viene ridimensionata in base allo spazio disponibile. Di conseguenza, a seconda dell'immagine, la larghezza può cambiare.
 
Per impostare i valori per i seguenti elementi, accedere ad Attract come amministratore, selezionare **Interfaccia di amministrazione** dal menu **Impostazioni**, quindi selezionare la scheda **Gestione del sito per le possibilità di carriera**.

-   **Ottimizzazione motore di ricerca** - Quando abilitati, tutti gli annunci di lavoro pubblici pubblicati sul sito di avanzamento professionale Attract saranno individuabili mediante motori di ricerca come Bing e Google.

    > [!NOTE] 
    > È possibile che i risultati di ricerca non siano visualizzati subito dopo l'attivazione di questa impostazione, a seconda del motore di ricerca che si sta utilizzando.
         
## <a name="career-site-urls"></a>URL del sito di avanzamento professionale

Nell'elenco seguente sono riportati gli URL del sito di avanzamento professionale utilizzati comunemente e viene descritto come accedervi.

-   **URL home page del sito di avanzamento professionale** - Per visualizzare l'URL della home page del sito di avanzamento professionale, accedere a Attract come amministratore, selezionare **Interfaccia di amministrazione** dal menu **Impostazioni** e quindi selezionare la scheda **Gestione del sito per le possibilità di carriera**.

-   **URL domanda singolo annuncio di lavoro** - Quando si [pubblica un annuncio di lavoro esterno](Creating-jobs-Attract.md#postings) per la prima volta, è possibile copiare il collegamento **Domanda di lavoro** dall'applicazione Attract. L'URL per questo collegamento avrà il formato seguente: [https://jobs.talent.dynamics.com/jobs/\<company_name\>/\<environment_number\>/\<job_number\>/apply](https://jobs.talent.dynamics.com/jobs/%3ccompany_name%3e/%3cenvironment_number%3e/%3cjob_number%3e/apply)

-   **URL singolo annuncio di lavoro** - L'URL dell'annuncio è una sottostringa dell'URL della domanda e include tutte le parti fino al numero di annuncio. Di conseguenza, per l'URL della domanda di lavoro precedente, l'URL dell'annuncio è [https://jobs.talent.dynamics.com/jobs/\<company_name\>/\<environment_number\>/\<job_number\>](https://jobs.talent.dynamics.com/jobs/%3ccompany_name%3e/%3cenvironment_number%3e/%3cjob_number%3e)

## <a name="authentication-options"></a>Opzioni di autenticazione

I candidati dispongono delle seguenti opzioni di accesso per un sito di avanzamento professionale Attract:

-   Account personale:

    -   LinkedIn

    -   Microsoft

    -   Google

    -   Facebook

-   Account di lavoro o dell'istituto di istruzione:

    -   Microsoft Azure Active Directory (Azure AD)

L'accesso a Azure AD è inteso solo per i candidati interni. Di conseguenza, funziona solo per i candidati interni che utilizzano le proprie credenziali Azure AD aziendali. Ad esempio, un candidato che è attualmente un dipendente di Contoso Ltd desidera inviare una candidatura per una mansione in una società non correlata, Alpine Ski House. In questo caso, l'accesso non riuscirà se il dipendente tenta di utilizzare le credenziali Azure AD di Contoso Ltd. 

I candidati devono accedere utilizzando Azure AD se la mansione che stanno esaminando o per la quale si stanno candidando è elencata come solo interna.

## <a name="create-and-maintain-a-profile"></a>Creazione e gestione di un profilo

Dopo che i candidati accedono al sito di avanzamento professionale, possono selezionare **Profilo personale** sulla barra di spostamento nella parte superiore della pagina per creare e gestire il proprio profilo.
Il profilo include le informazioni personali, le informazioni sull'esperienza di lavoro, i dettagli del percorso formativo, i documenti, i collegamenti e le informazioni sugli insiemi delle competenze. Dopo che un profilo viene creato, può essere utilizzato per fare domanda per le mansioni a cui il candidato è interessato. I profili consentono anche ad Attract di consigliare le mansioni giuste ai candidati.

> [!NOTE]
> Se un candidato utilizza un ID di posta elettronica per eseguire l'accesso mediante uno dei provider di autenticazione sopra elencati, il valore predefinito di quell'ID di posta elettronica sarà l'indirizzo di posta elettronica del contatto associato al profilo. Tuttavia, quest'ultimo può essere modificato in qualsiasi momento ed è completamente indipendente dal precedente. Attract utilizzerà sempre l'ID di posta elettronica del contatto da associare al profilo per tutte le comunicazioni di posta elettronica.

## <a name="find-the-right-job"></a>Individuare la giusta mansione

Nella pagina con l'elenco delle mansioni, i candidati possono cercare una mansione specifica immettendo i termini di ricerca. La funzionalità di ricerca cerca i termini di ricerca nei titoli e nelle le descrizioni delle mansioni e visualizza le mansioni rilevanti come risultati. I candidati possono filtrare in qualsiasi momento i risultati, in base alla posizione della mansione o alla funzione lavorativa.

I candidati possono inoltre visualizzare un insieme di mansioni consigliate nel sito di avanzamento professionale. Le mansioni consigliate a un candidato si basano sulle passate domande di lavoro, profilo e curriculum del candidato.

> [!NOTE] 
> I suggerimenti di mansioni vengono visualizzati solo se almeno 10 posizioni lavorative sono pubblicate nel sito di avanzamento professionale e se il candidato ha completato un profilo.

I candidati interni possono anche vedere chi è il responsabile delle assunzioni e/o il selezionatore per una mansione, nel caso vogliano contattare quei membri del team di assunzione. Tuttavia, i candidati esterni non possono visualizzare i membri del team di assunzione per qualsiasi mansione.

## <a name="contact-the-hiring-team"></a>Contatta il team di assunzione
Solo i candidati interni possono contattare il team di assunzione. Questa limitazione si applica a tutte le mansioni, indipendentemente dal fatto che siano interne o pubblicate.

I candidati potrebbero voler contattare il team di assunzione per esprimere interesse in una mansione pubblicata o ottenere ulteriori informazioni. Possono contattare qualsiasi membro del team di assunzione elencato (responsabile delle assunzioni o selezionatori). Possono inoltre eventualmente allegare un curriculum al messaggio, oppure selezionare un curriculum esistente che hanno caricato in precedenza come parte del proprio profilo.

Dopo che un candidato interno seleziona i membri del team di assunzione da contattare, Attract invia un messaggio di posta elettronica a tali persone per conto del candidato. Nello stesso tempo, il profilo del candidato viene aggiunto alla fase **Prospect**, se tale fase è disponibile per la mansione. Nella fase **Prospect**, i selezionatori o i responsabili delle assunzioni possono visualizzare i candidati che li hanno contattati. Possono inoltre esaminare i profili dei candidati e invitare i candidati potenziali a inviare una domanda di lavoro.

I candidati possono candidarsi a una mansione per la quale hanno già contattato i membri del team di assunzione. Dopo la candidatura, non possono più contattare il team di assunzione tramite il sito di avanzamento professionale.

## <a name="apply-for-jobs"></a>Inviare candidature per posizioni lavorative

Dopo che i candidati trovano la giusta mansione, possono inviare la candidatura tramite il pulsante **Applica**  nella pagina  **Dettagli mansione**. A questo punto, i candidati possono creare un nuovo profilo oppure modificare le informazioni nel profilo esistente.
I candidati possono inoltre possibile caricare un curriculum, secondo le esigenze, e quindi inviare la domanda di lavoro.

### <a name="enable-applying-for-jobs-with-linkedin-profiles"></a>Abilitare l'invio di domande di candidatura con profili LinkedIn

È possibile facilitare la candidatura a posizioni configurando Attract di modo che i candidati possano utilizzare LinkedIn per candidarsi.

> [!NOTE] 
> È necessario avere una o più licenze di selezionatore di LinkedIn per consentire ai candidati di candidarsi con LinkedIn.

1. Accedere a Attract come amministratore.
2. Selezionare il pulsante **Impostazioni** (il simbolo dell'ingranaggio) nell'angolo superiore destro della pagina, quindi selezionare **Interfaccia di amministrazione**.
3. Selezionare la scheda **Integrazione di LinkedIn** e connettersi a un conto di LinkedIn Recruiter.
4. Nella sezione **Integrazione di LinkedIn Recruiter System Connect** selezionare **Abilitato** per l'impostazione **Fai domanda con LinkedIn**.

Dopo avere abilitato l'impostazione, i candidati possono candidarsi utilizzando i dati dei propri profili LinkedIn. Quando i candidati si candidano scegliendo il pulsante **Fai domanda con LinkedIn**, verrà chiesto loro di eseguire l'autenticazione con LinkedIn se non hanno ancora eseguito l'accesso. Dopo l'autenticazione, il relativo profilo LinkedIn sostituisce tutti i dati di profilo esistenti visualizzati nella pagina dell'applicazione. I candidati possono modificare le informazioni come necessario e quindi inviare la domanda. Se un candidato esce dalla pagina senza inviare la domanda di candidatura per la mansione, i dati del relativo profilo non vengono aggiornati in Attract.

## <a name="check-application-status"></a>Verificare lo stato della domanda di lavoro

Dopo che i candidati inviano la propria candidatura per una o più mansioni, possono selezionare **Domande di lavoro** sulla barra di spostamento nella parte superiore della pagina per visualizzare le domande aperte e chiuse. Quando i candidati aprono una delle domande, vedono la fase corrente e le eventuali azioni in sospeso da completare. Ad esempio, se un candidato deve fornire date potenziali per un colloquio di persona, la pagina mostra le opzioni disponibili.

## <a name="internal-jobs"></a>Mansioni interne

Attualmente, le mansioni contrassegnate come interne e pubblicate nel sito di avanzamento professionale Attract non vengono visualizzate nel sito di avanzamento professionale. Sono accessibili tramite l'URL diretto di **Domanda di lavoro** che può essere copiato dall'applicazione Attract.
