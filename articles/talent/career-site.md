---
title: Funzionalità del sito di avanzamento professionale in Attract
description: Questo articolo fornisce una panoramica delle funzionalità del sito di avanzamento professionale rivolto ai candidati in Attract.
author: josaw1
manager: AnnBe
ms.date: 02/12/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2019-02-12
ms.dyn365.ops.version: AX 7.1.0, Talent April 2018 update
ms.openlocfilehash: 087ab4034a1e601e7f3514c77d56ef54b0c5c52d
ms.sourcegitcommit: 1ee613a88edddab036d145f27f19d071a4b8ad24
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/13/2019
ms.locfileid: "389970"
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

    >   [!NOTE] 
    >   Immagine di logo visualizzata nel sito di avanzamento professionale ha un'altezza fissa di 20 pixel. L'immagine che si aggiunge nell'Interfaccia di amministrazione viene ridimensionata in base allo spazio disponibile. Di conseguenza, a seconda dell'immagine, la larghezza può cambiare.
 
Per impostare i valori per i seguenti elementi, accedere ad Attract come amministratore, selezionare **Interfaccia di amministrazione** dal menu **Impostazioni**, quindi selezionare la scheda **Gestione del sito per le possibilità di carriera**.

-   **Ottimizzazione motore di ricerca** - Quando abilitati, tutti gli annunci di lavoro pubblici pubblicati sul sito di avanzamento professionale Attract saranno individuabili mediante motori di ricerca come Bing e Google.

    >   [!NOTE] 
    >   È possibile che i risultati di ricerca non siano visualizzati subito dopo l'attivazione di questa impostazione, a seconda del motore di ricerca che si sta utilizzando.
         
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

## <a name="create-and-maintain-a-profile"></a>Creazione e gestione di un profilo

Dopo che i candidati accedono al sito di avanzamento professionale, possono selezionare **Profilo personale** sulla barra di spostamento nella parte superiore della pagina per creare e gestire il proprio profilo.
Il profilo include le informazioni personali, le informazioni sull'esperienza di lavoro, i dettagli del percorso formativo, i documenti, i collegamenti e le informazioni sugli insiemi delle competenze. Dopo che un profilo viene creato, può essere utilizzato per fare domanda per le mansioni a cui il candidato è interessato. I profili consentono anche ad Attract di consigliare le mansioni giuste ai candidati.

>   [!NOTE]
>   Se un candidato utilizza un ID di posta elettronica per eseguire l'accesso mediante uno dei provider di autenticazione sopra elencati, il valore predefinito di quell'ID di posta elettronica sarà l'indirizzo di posta elettronica del contatto associato al profilo. Tuttavia, quest'ultimo può essere modificato in qualsiasi momento ed è completamente indipendente dal precedente. Attract utilizzerà sempre l'ID di posta elettronica del contatto da associare al profilo per tutte le comunicazioni di posta elettronica.

## <a name="find-the-right-job"></a>Individuare la giusta mansione

Nella pagina con l'elenco delle mansioni, i candidati possono cercare una mansione specifica immettendo i termini di ricerca. La funzionalità di ricerca cerca i termini di ricerca nei titoli e nelle le descrizioni delle mansioni e visualizza le mansioni rilevanti come risultati. I candidati possono filtrare in qualsiasi momento i risultati, in base alla posizione della mansione o alla funzione lavorativa.

I candidati possono inoltre visualizzare un insieme di mansioni consigliate nel sito di avanzamento professionale. Le mansioni consigliate a un candidato si basano sulle passate domande di lavoro, profilo e curriculum del candidato.

>   [!NOTE] 
>   I suggerimenti di mansioni vengono visualizzati solo se almeno 10 posizioni lavorative sono pubblicate nel sito di avanzamento professionale e se il candidato ha completato un profilo.

## <a name="apply-for-jobs"></a>Inviare candidature per posizioni lavorative

Dopo che i candidati individuano la giusta mansione, possono inviare la candidatura tramite il pulsante **Applica** nella pagina **Dettagli mansione**. A questo punto, i candidati possono creare un nuovo profilo oppure modificare le informazioni nel profilo esistente.
I candidati possono inoltre possibile caricare un curriculum, secondo le esigenze, e quindi inviare la domanda di lavoro.

## <a name="check-application-status"></a>Verificare lo stato della domanda di lavoro

Dopo che i candidati inviano la propria candidatura per una o più mansioni, possono selezionare **Domande di lavoro** sulla barra di spostamento nella parte superiore della pagina per visualizzare le domande aperte e chiuse. Quando i candidati aprono una delle domande, vedono la fase corrente e le eventuali azioni in sospeso da completare. Ad esempio, se un candidato deve fornire date potenziali per un colloquio di persona, la pagina mostra le opzioni disponibili.

## <a name="internal-jobs"></a>Mansioni interne

Attualmente, le mansioni contrassegnate come interne e pubblicate nel sito di avanzamento professionale Attract non vengono visualizzate nel sito di avanzamento professionale. Sono accessibili tramite l'URL diretto di **Domanda di lavoro** che può essere copiato dall'applicazione Attract.
