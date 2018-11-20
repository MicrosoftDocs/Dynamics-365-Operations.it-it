---
title: "Funzionalità del sito di avanzamento professionale in Attract"
description: "Questo articolo fornisce una panoramica delle funzionalità del sito di avanzamento professionale rivolto ai candidati in Microsoft Dynamics 365 for Talent - Attract. Viene descritto inoltre come impostare le funzionalità."
author: josaw
manager: AnnBe
ms.date: 10/18/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Talent
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: rschloma
ms.search.validFrom: 2018-10-18
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: e890e32049e930b70c2d0aac8aa8206ab999418a
ms.openlocfilehash: 452e3e92ea32ab5f1e3720ab81ff2f7ea18b2a06
ms.contentlocale: it-it
ms.lasthandoff: 10/22/2018

---
# <a name="career-site-functionality-in-attract"></a>Funzionalità del sito di avanzamento professionale in Attract

[!include [banner](includes/banner.md)]

Questo articolo fornisce una panoramica delle funzionalità del sito di avanzamento professionale rivolto ai candidati in Microsoft Dynamics 365 for Talent: Attract. Viene descritto inoltre come impostare le funzionalità.

## <a name="overview"></a>Panoramica

Attract fornisce un sito di avanzamento professionale per ogni ambiente in un tenant. Ad esempio, se un'organizzazione ha un ambiente di sviluppo e un ambiente di test, un sito di avanzamento professionale viene fornito per l'ambiente di sviluppo e un altro sito di avanzamento professionale per l'ambiente di test. Ogni sito di avanzamento professionale è **completamente isolato** e ha un proprio meccanismo di autenticazione. Le mansioni e i profili dei candidati non sono condivisi tra siti di avanzamento professionale.

Per impostazione predefinita, il sito di avanzamento professionale è pubblico. Di conseguenza, i candidati possono visualizzare tutte le mansioni contrassegnate come esterne senza dover accedere. Tuttavia, tutte le altre azioni richiedono l'accesso dei candidati.

## <a name="career-site-management"></a>Gestione del sito per le possibilità di carriera

I seguenti elementi nel sito di avanzamento professionale sono controllati da impostazioni:

- **Nome organizzazione:** Il nome dell'organizzazione appare sulla barra di spostamento nella parte superiore del sito di avanzamento professionale. Selezionando il nome di organizzazione, i candidati vanno a una pagina contenente tutte le posizioni aperte.
- **Logo organizzazione:** Un'immagine del logo dell'organizzazione appare in alto a sinistra del sito di avanzamento professionale. Selezionando l'immagine del logo, i candidati vanno a una pagina contenente tutte le posizioni aperte.

Per impostare i valori per il nome e il logo di organizzazione, accedere ad Attract come amministratore, selezionare **Interfaccia di amministrazione** dal menu **Impostazioni** (il simbolo di ingranaggio) e quindi fare clic sulla scheda **Informazioni società**.

> [!NOTE]
> Immagine di logo visualizzata nel sito di avanzamento professionale ha un'altezza fissa di 20 pixel. L'immagine che si aggiunge nell'Interfaccia di amministrazione viene ridimensionata in base allo spazio disponibile. Di conseguenza, a seconda dell'immagine, la larghezza può cambiare.

## <a name="career-site-url"></a>URL del sito di avanzamento professionale

Quando si [pubblica l'annuncio di una mansione esterna](./Creating-jobs-Attract.md#postings) per la prima volta, è possibile copiare il collegamento **Domanda di lavoro** nell'applicazione Attract. L'URL per il collegamento avrà il formato seguente: `https://jobs.talent.dynamics.com/jobs/<company_name>/<environment_number>/<job_number>/apply`

L'URL del sito di avanzamento professionale è una sottostringa dell'URL **Domanda di lavoro**. È formata da tutte le parti fino al nome della società. Di conseguenza, per l'URL **Domanda di lavoro** precedente, l'URL del sito di avanzamento professionale è `https://jobs.talent.dynamics.com/jobs/<company_name>/`.

## <a name="authentication-options"></a>Opzioni di autenticazione

I candidati hanno le seguenti opzioni di accesso per un sito di avanzamento professionale Attract:

- Account personale:

    - LinkedIn
    - Microsoft
    - Google
    - Facebook

- Account di lavoro o dell'istituto di istruzione:

    - Microsoft Azure Active Directory (Azure AD)

L'accesso tramite Azure AD è destinato solo ai candidati interni. Di conseguenza, funziona solo per i candidati interni che utilizzano le proprie credenziali Azure AD aziendali. Ad esempio, un candidato che è attualmente un dipendente di Contoso Ltd desidera inviare una candidatura per una mansione in una società non correlata, Alpine Ski House. In questo caso, l'accesso non riuscirà se il dipendente tenta di utilizzare le credenziali Azure AD di Contoso Ltd.

## <a name="create-and-maintain-a-profile"></a>Creazione e gestione di un profilo

Dopo che i candidati accedono al sito di avanzamento professionale, possono selezionare **Profilo personale** sulla barra di spostamento nella parte superiore della pagina per creare e gestire il proprio profilo. Il profilo include le informazioni personali, le informazioni sull'esperienza di lavoro, i dettagli del percorso formativo, i documenti, i collegamenti e le informazioni sugli insiemi delle competenze. Dopo che un profilo viene creato, può essere utilizzato per fare domanda per le mansioni a cui il candidato è interessato. I profili consentono anche ad Attract di consigliare le mansioni giuste ai candidati.

## <a name="find-the-right-job"></a>Individuare la giusta mansione

Nella pagina con l'elenco delle mansioni, i candidati possono cercare una mansione specifica immettendo i termini di ricerca. La funzionalità di ricerca cerca i termini di ricerca nei titoli e nelle le descrizioni delle mansioni e visualizza le mansioni rilevanti come risultati. I candidati possono filtrare in qualsiasi momento i risultati, in base alla posizione della mansione o alla funzione lavorativa.

I candidati possono inoltre visualizzare un insieme di mansioni consigliate nel sito di avanzamento professionale. Le mansioni consigliate a un candidato si basano sulle passate domande di lavoro, profilo e curriculum del candidato.

> [!NOTE]
> I suggerimenti di mansioni vengono visualizzati solo se almeno 10 posizioni lavorative sono pubblicate nel sito di avanzamento professionale e se il candidato ha completato il proprio profilo.

## <a name="apply-for-jobs"></a>Inviare candidature per posizioni lavorative

Dopo che i candidati individuano la giusta mansione, possono inviare la candidatura tramite il pulsante **Applica** nella pagina dei dettagli della mansione. A questo punto, i candidati possono creare un profilo nuovo di zecca oppure modificare le informazioni nel profilo esistente. I candidati possono inoltre possibile caricare un curriculum, secondo le esigenze, e quindi inviare la domanda di lavoro.

## <a name="check-application-status"></a>Verificare lo stato della domanda di lavoro

Dopo che i candidati fanno domanda per una o più mansioni, possono selezionare **Domande di lavoro** sulla barra di spostamento nella parte superiore della pagina per visualizzare le domande aperte e chiuse. Quando i candidati aprono una delle domande, vedono la fase corrente e le eventuali azioni in sospeso da completare. Ad esempio, se un candidato deve fornire date potenziali per un colloquio di persona, la pagina mostra le relative opzioni.

## <a name="internal-jobs"></a>Mansioni interne

Attualmente, le mansioni contrassegnate come interne e pubblicate nel sito di avanzamento professionale Attract non vengono visualizzate nel sito di avanzamento professionale. Sono accessibili solo tramite l'URL diretto di **Domanda di lavoro** che può essere copiato dall'applicazione Attract.

