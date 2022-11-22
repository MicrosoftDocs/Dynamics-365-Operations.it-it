---
title: Concetti di configurazione della sicurezza per integrazioni basate su tabelle virtuali
description: Questo articolo illustra un'architettura per creare un'integrazione tra Microsoft Dynamics 365 Human Resources e altri sistemi.
author: twheeloc
ms.date: 11/19/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CDSIntegrationAdministration
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-10-05
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 219ceb0adae0cee5f74a39140ab74af9fdac1eb6
ms.sourcegitcommit: ea79bf014bbf495ac8e28db29502c8bd85a75f32
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/11/2022
ms.locfileid: "9759654"
---
# <a name="security-configuration-concepts-for-virtual-table-based-integrations"></a>Concetti di configurazione della sicurezza per integrazioni basate su tabelle virtuali

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Questo articolo descrive un'architettura per l'utilizzo delle [tabelle virtuali di Microsoft Dataverse (entità)](/dev-itpro/power-platform/virtual-entities-overview) per creare un'integrazione tra Dynamics 365 Human Resources e un sistema di terze parti. Il focus dell'articolo è sulla configurazione della sicurezza e sugli aspetti di autenticazione e autorizzazione obbligatori tra i confini del sistema per creare un sistema funzionale e sicuro.

## <a name="prerequisite-reference-articles"></a>Articoli di riferimento prerequisiti

Negli articoli seguenti vengono fornite altre informazioni sui concetti in questo articolo:

- [Panoramica delle entità virtuali](/dev-itpro/power-platform/virtual-entities-overview)
- [Iniziare con le tabelle virtuali (entità)](/developer/data-platform/virtual-entities/get-started-ve)
- [Utilizzare l'autenticazione da server a server multi-tenant (Microsoft Dataverse)](/developer/data-platform/use-multi-tenant-server-server-authentication)
- [Utilizzare l'autenticazione OAuth con Microsoft Dataverse (Dataverse)](/developer/data-platform/authenticate-oauth)
- [Le credenziali del client OAuth 2.0 passano sulla piattaforma di identità Microsoft](/azure/active-directory/develop/v2-oauth2-client-creds-grant-flow)
- [Autenticazione e autorizzazione](/dev-itpro/power-platform/authentication-and-authorization)

## <a name="architecture"></a>Architettura 

Il diagramma dell'architettura seguente mostra i concetti principali coinvolti in un'integrazione che utilizza tabelle virtuali (entità).

![Integrazione basata su tabelle virtuali.](./media/Hosts.jpg)

Di seguito viene riportata una spiegazione di alcuni degli elementi del diagramma precedente:

- **Microsoft**: Microsoft ospita e gestisce i diversi prodotti Dynamics 365 per conto dei clienti.

    - **Azure Active Directory(Azure AD) tenant C**: un tenant Azure AD di proprietà di Microsoft. Si tratta del tenant in cui sono registrate le applicazioni Dynamics 365.

- **Partner di integrazione**

    - **Sistema di integrazione**: il sistema che viene integrato con Dynamics 365. Potrebbe trattarsi di un sistema di gestione stipendi o di qualsiasi sistema basato sui dati archiviati in Dynamics 365.
    - **Adattatore**: il software o il servizio responsabile dell'interazione sia con Dynamics 365 che con il sistema di integrazione.

        > [!NOTE]
        > Se un adattatore deve essere utilizzato da più clienti Dynamics 365, l'aspettativa è che venga registrato come applicazione multi-tenant in Azure AD.

    - **Azure AD tenant A**: un tenant Azure AD di proprietà del partner di integrazione. Si tratta del tenant in cui è registrato l'ID applicazione dell'adattatore.

- **Cliente reciproco**: un cliente che implementa Dynamics 365 Human Resources e la soluzione del partner di integrazione.

    - **Dynamics 365 Finance o Human Resources**: l'istanza specifica del cliente di Dynamics 365 Finance o Human Resources che contiene i dati del cliente richiesti dal sistema di integrazione.
    - **Dataverse**: l'ambiente Dataverse specifico del cliente connesso a Finance o Human Resources. Dataverse fornisce un'API Web per l'interazione con i dati di Dynamics 365.
    - **Azure AD tenant B**: il tenant Azure AD del cliente. Funziona come provider di identità (server di autorizzazione) ed emette token che autorizzano i chiamanti a chiamare l'istanza Dataverse del cliente.

## <a name="basic-request-flow"></a>Flusso richiesta di base

Questa sezione descrive il flusso di base di una tipica richiesta coinvolta in un'integrazione. Fa riferimento al diagramma architettonico in precedenza in questo articolo.

Una richiesta tipica richiede che l'adapter interroghi Dynamics 365 per i dati, quindi salvi e sincronizzi tali dati nel sistema di integrazione.

1. L'adapter chiama l'API Web Dataverse per interrogare i dati pertinenti.

    > [!NOTE]
    > L'autenticazione è un prerequisito e l'acquisizione di token è una parte importante del processo. L'autenticazione sarà descritta nella sezione [Autenticazione e autorizzazione ai confini del sistema](#authentication-and-authorization-at-system-boundaries).

    Questa chiamata è fatta a fronte dell'API Web Dataverse per eseguire query sui dati dell'applicazione esposti tramite una tabella virtuale. (Vedere "2. Sincronizzazione iniziale" e "3. Sincronizzazione delta" nel diagramma.)

2. Dataverse gestisce la richiesta interrogando la tabella virtuale tramite il plug-in Entità virtuale ("Proxy tabella virtuale" nel diagramma). La richiesta di Dataverse viene inoltrata al servizio dell'entità virtuale Finance o Human Resources per richiedere i dati archiviati fisicamente nel database Finance o Human Resources.
3. Il servizio dell'entità virtuale Finance o Human Resources traduce la richiesta a fronte dell'entità virtuale in una query a fronte dell'entità Finance o Human Resources che supporta l'entità virtuale Dataverse. I dati vengono recuperati dal database, tradotti nuovamente nella rappresentazione dell'entità Dataverse e restituiti al chiamante.
4. L'adapter completa il mapping e la traduzione dei dati richiesti ed effettua una chiamata al sistema di integrazione per rendere persistenti i dati nel database del sistema di integrazione. (Vedere "4. Salva dati" nel diagramma.)

## <a name="authentication-and-authorization-at-system-boundaries"></a>Autenticazione e autorizzazione ai confini del sistema

*Autenticazione* convalida che l'identità di un utente o di un'applicazione è stata dimostrata e conferma che l'utente o l'applicazione è chi dice di essere. *Autorizzazione* concede all'utente o all'applicazione il diritto di accedere a specifiche autorizzazioni a livello di applicazione. Per altre informazioni, vedere [Autenticazione rispetto ad autorizzazione](/azure/active-directory/develop/authentication-vs-authorization).

La maggior parte delle chiamate tra sistemi nel diagramma dell'architettura descritto in precedenza in questo articolo coinvolge l'adapter. L'adapter deve autenticarsi per effettuare le seguenti chiamate:

- La chiamata a Dataverse
- La chiamata al sistema di integrazione

Guarda i confini del sistema nel diagramma. Ogni richiesta Web tra i sistemi deve essere autenticata e i controlli di autorizzazione a livello di applicazione devono essere superati prima che i dati vengano restituiti al chiamante. Per una richiesta a fronte di una tabella virtuale di Dynamics 365 supportata da Finance o Human Resources, i controlli di autenticazione e autorizzazione vengono applicati ai seguenti limiti di sistema:

- La chiamata tra l'adapter e l'endpoint API Web Dataverse (OData)
- La chiamata tra il plug-in Entità virtuale di Dataverse e il servizio Entità virtuale Finance o Human Resources

In entrambi i casi, i controlli di autenticazione vengono eseguiti per primi. Quindi vengono eseguiti controlli di autorizzazione a livello di applicazione per garantire che l'utente o l'applicazione autenticati disponga dei privilegi corretti a livello di applicazione per recuperare i dati richiesti.

L'autenticazione per chiamare Dataverse viene gestita tramite un bearer token che deve essere incluso come intestazione HTTP nella richiesta Web a Dataverse. L'adapter deve ricevere un token dall'istanza Azure AD tenant B. (Vedere "1. Recupera token" nel diagramma.) Azure AD funge da provider di identità nel flusso di autenticazione.

L'adapter esegue l'autenticazione fornendo la propria identità dell'applicazione (non segreta, come registrata in Azure AD tenant A) e un segreto dell'applicazione o un certificato di cui dispone solo l'applicazione dell'adattatore.

Dopo che l'utente o l'applicazione è stata autenticata per effettuare chiamate a Dataverse, vengono eseguiti controlli di autorizzazione a livello di Dataverse a fronte di ogni richiesta. Questi controlli assicurano che il chiamante (l'identità dell'applicazione adapter, designata "\<guid A\>" nel diagramma) dispone delle autorizzazioni dell'applicazione appropriate. L'autorizzazione a livello di applicazione è gestita in Dataverse tramite un utente dell'applicazione che rappresenta l'ID applicazione dell'adapter. Le autorizzazioni a livello di applicazione vengono gestite concedendo l'accesso a ruoli dell'applicazione definiti da Dataverse specifici. Questi ruoli forniscono privilegi granulari all'applicazione.

Per istruzioni più dettagliate, vedi [Utilizzare l'autenticazione da server a server multi-tenant](/power-apps/developer/data-platform/use-multi-tenant-server-server-authentication).

Se vengono superati i controlli delle autorizzazioni dell'applicazione a livello di Dataverse, il plug-in dell'entità virtuale effettua una chiamata all'endpoint del servizio dell'entità virtuale nell'ambiente Finance o Human Resources. Per effettuare questa chiamata viene utilizzata l'autenticazione da server a server (S2S). Utilizza l'identità e il segreto configurati nel record di configurazione dell'origine dati virtuale di Finance and Operations.

![Record di configurazione dell'origine dati virtuale Finance and Operations nell'ambiente sandbox.](./media/sandbox.jpg)

Per ulteriori informazioni, vedi [Configurare entità virtuali di Dataverse](/dev-itpro/power-platform/admin-reference).

La chiamata del plug-in di entità virtuale Dataverse a Finance o Human Resources include l'identità dell'adapter della chiamata originale a Dataverse dall'adapter (l'identità designata "\<guid A\>" nel diagramma architettonico). Se l'origine dati dell'entità virtuale è configurata correttamente e vengono superati i controlli di autenticazione S2S, il servizio Entità virtuale in Finance o Human Resources eseguirà la query nel contesto del chiamante originale (l'adapter, \<guid A\>). I controlli delle autorizzazioni dell'applicazione (autorizzazione) a livello di Finance o Human Resources verranno eseguiti per garantire che l'adapter disponga dei privilegi necessari per accedere alle entità di dati richieste tramite la query.

La sicurezza di Finance e Human Resources è gestita nei seguenti modi:

1. Eseguendo il mapping dell'identità dell'adapter (\<guid A\>) a un utente di Finance o Human Resources specifico. Questo mapping viene eseguito nella pagina **Applicazioni di Azure Active Directory**. Per ulteriori informazioni, vedi [Registrare un'applicazione esterna](/dev-itpro/data-entities/services-home-page.md#register-your-external-application).
2. Concedendo all'utente di Finance o Human Resources i ruoli, i doveri e i privilegi appropriati a livello di applicazione. Per ulteriori informazioni, vedere [Sicurezza basata sul ruolo](/dev-itpro/sysadmin/role-based-security).

Se all'applicazione dell'adapter (\<guid A\>) vengono concessi i privilegi necessari per accedere ai dati richiesti, si verificano i seguenti eventi:

1. La query viene eseguita.
2. I dati vengono riconvertiti nella relativa pagina dell'entità Dataverse.
3. I dati vengono restituiti all'adapter.

> [!IMPORTANT]
> Durante lo sviluppo, l'adapter può essere eseguito utilizzando un utente Finance o Human Resources con ruolo di amministratore. Tuttavia, in un ambiente di produzione, l'adapter non dovrebbe mai essere eseguito con privilegi di amministratore.

## <a name="key-takeaways"></a>Punti chiave

Ecco alcune importanti implicazioni della tabella virtuale o dell'architettura dell'entità:

- La configurazione della sicurezza per le tabelle virtuali supportate da Risorse umane è gestita in Human Resources.
- Il cliente ("Cliente reciproco" nel diagramma dell'architettura in precedenza in questo articolo) ha il controllo completo sui privilegi concessi all'identità dell'adapter integrato (designato "\<guid A\>" nel diagramma).
- Il cliente è responsabile della corretta configurazione di sicurezza del proprio ambiente Human Resources. Il partner di integrazione che crea l'adapter deve fornire indicazioni sui privilegi richiesti dall'adapter.
