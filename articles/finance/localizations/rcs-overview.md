---
title: Regulatory Configuration Service
description: Questo argomento fornisce una panoramica delle funzionalità di Regulatory Configuration Service (RCS) e spiega come accedere al servizio.
author: JaneA07
ms.date: 06/04/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RCS, Regulatory Configuration Services, Localization
audience: Application User
ms.reviewer: kfend
ms.custom:
- "97423"
- intro-internal
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-02-01
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: 4ee68b691bba7f3314b5278b0bcc26504c1583335914a1e7c645abd5303f02c6
ms.sourcegitcommit: fa5ff2a0822aac16b518a2aea0d3389f79793390
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2021
ms.locfileid: "7012015"
---
# <a name="regulatory-configuration-service"></a>Regulatory Configuration Service

[!include [banner](../includes/banner.md)]

Regulatory Configuration Service (RCS) è un servizio di progettazione e gestione del ciclo di vita autonomo per funzionalità di globalizzazione senza codice/low-code. RCS consente agli stakeholder della globalizzazione di estendere e personalizzare aree chiave della globalizzazione come imposte, fatturazione elettronica, reporting normativo, documenti bancari e aziendali senza dover coinvolgere gli sviluppatori. Questo approccio alla globalizzazione senza codice/low-code rende la globalizzazione più facile, veloce e conveniente da creare o estendere.

RCS fornisce le seguenti funzionalità:

- Supporto per tutte le funzionalità fornite da Creazione di report elettronici (ER).
- Un prerequisito per configurare nuovi microservizi di globalizzazione.
- Supporto per Fatturazione elettronica. Per ulteriori informazioni, vedi [Fatturazione elettronica](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-finance/electronic-invoicing-add-on-dynamics-365-ga).
- Supporta il calcolo delle imposte. Per ulteriori informazioni, vedi [Servizio fiscale](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-finance/tax-service-preview).
- Supporto per nuove funzionalità di globalizzazione che semplifica la gestione del ciclo di vita delle funzionalità a più componenti e fornisce funzionalità aggiuntive per configurare le azioni e impostare i parametri delle funzionalità. Per ulteriori informazioni, vedi [Regulatory Configuration Service: gestione semplificata delle funzionalità di globalizzazione per i servizi di globalizzazione](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-finance/regulatory-configuration-service-simplified-globalization-feature-management-globalization-services).
- Supporto per la pubblicazione centralizzata, l'archiviazione e la condivisione di configurazioni personalizzate nel repository globale per semplificare la gestione della configurazione senza richiedere l'uso di Microsoft Dynamics Lifecycle Services (LCS).

## <a name="access-rcs"></a>Accedere a RCS

Puoi iscriverti o accedere a RCS dalla [pagina di Regulatory Configuration Service](https://marketing.configure.global.dynamics.com/).

![Iscrizione/accesso a RCS.](media/202103_RCS%20Marketing%20page_updated_1.jpg)

Nella pagina **Regulatory Configuration Service**, esamina e accetta i termini e le condizioni supplementari per l'utilizzo del servizio, quindi seleziona uno dei seguenti pulsanti:

- **Iscriviti** se utilizzi il servizio per la prima volta e utilizzi un indirizzo email aziendale per fornire un ambiente di servizio all'organizzazione
- **Accedi** se ti sei registrato in precedenza al servizio e desideri accedere all'ambiente dell'organizzazione

> [!NOTE] 
> Dopo la registrazione, ti consigliamo di aggiungere un utente SysAdmin aggiuntivo all'ambiente RCS. Questo utente verrà fornito come co-amministratore dell'ambiente. Ciò contribuirà a fornire stabilità per l'accesso all'ambiente RCS, poiché il ruolo SysAdmin è quello di gestire utenti per quell'ambiente. Puoi aggiungere utenti usando **Area di lavoro RCS > Amministrazione sistema**.

## <a name="regional-availability"></a>Disponibilità regionale

RCS è generalmente disponibile nelle seguenti regioni:

- Stati Uniti
- India
- Francia
- Europa

Per un elenco completo delle aree geografiche, vedi [Dynamics 365 e Power Platform: disponibilità, posizione dei dati, lingua e localizzazione](https://aka.ms/dynamics_365_international_availability_deck).

## <a name="rcs-default-company"></a>Azienda predefinita RCS

La funzionalità della fase di progettazione utilizzata in RCS è condivisa tra tutte le aziende. Non esiste una funzionalità specifica dell'azienda. Pertanto, ti consigliamo di utilizzare un'azienda, **DAT**, con il tuo ambiente RCS.

Tuttavia, in alcuni scenari, potresti preferire che i formati ER utilizzino parametri correlati a una persona giuridica specifica. Solo in questi scenari, dovresti usare il commutatore di società predefinito. Per un esempio, vedi [Configurare il formato ER per utilizzare i parametri specifici per la persona giuridica](../../fin-ops-core/dev-itpro/analytics/er-app-specific-parameters-configure-format.md).

## <a name="related-rcs-documentation"></a>Documentazione RCS correlata

Per ulteriori informazioni sui componenti correlati, vedi gli argomenti seguenti:

- **RCS:**

    - [Creare configurazioni ER in RCS e caricarle nel repository globale](rcs-global-repo-upload.md)

- **Repository globale:**

    - [Creare una configurazione ER e caricarla in Repository globale](rcs-global-repo-upload.md)
    - [Condividere una configurazione in Repository globale](rcs-global-repo-share-configuration.md)
    - [Filtro avanzato in Repository globale](enhanced-filtering-global-repo.md)
    - [Scaricare configurazioni ER da Repository globale](../../fin-ops-core/dev-itpro/analytics/er-download-configurations-global-repo.md)
    - [Sospendere le configurazioni in Repository globale](discontinuing-configurations-rcs-global-repo.md)
    - [Regulatory Configuration Service (RCS) – Deprecazione dell'archiviazione di Lifecycle Services (LCS)](rcs-lcs-repo-dep-faq.md)

- **Funzionalità di globalizzazione:**

    - [Regulatory Configuration Service (RCS) - Funzionalità di globalizzazione](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-finance/regulatory-configuration-service-simplified-globalization-feature-management-globalization-services)


## <a name="troubleshooting-rcs-sign-up"></a>Risoluzione dei problemi di iscrizione a RCS

Quando ti iscrivi a RCS dalla pagina del servizio, potresti riscontrare un problema correlato ad Azure Active Directory (Azure AD). Il messaggio di errore che ricevi indica che l'iscrizione a RCS è attualmente disattivata e deve essere attivata prima di poter completare il processo di iscrizione.

![Messaggio di errore di iscrizione a RCS.](media/01_RCSSignUpError.jpg)

Il problema si verifica perché la registrazione per abbonamenti ad-hoc è bloccata e la proprietà `AllowAdHocSubscriptions` deve essere abilitata nel tenant. 

- Se il tuo reparto IT gestisce i tenant di Azure della tua organizzazione, contatta tale reparto per segnalare il problema.
- Se sei responsabile della gestione dei tenant di Azure, puoi risolvere i problemi seguendo i passaggi in [Cos'è l'iscrizione self-service Azure Active Directory](/azure/active-directory/enterprise-users/directory-self-service-signup#how-do-i-control-self-service-settings).
