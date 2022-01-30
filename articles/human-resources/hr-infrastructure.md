---
title: Unione dell'infrastruttura Dynamics 365 Human Resources - Aggiornamento della versione 10.0.25
description: Questo argomento fornisce informazioni su Microsoft Dynamics 365 Human Resources versione 10.0.25, che porta il primo ciclo di funzionalità nell'unione dell'infrastruttura.
author: twheeloc
ms.date: 01/19/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-27
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: ec6d47c44136f7a105a702358370dd676d9339c1
ms.sourcegitcommit: 96f936267d3f314f06da6ce6f809eba2ec3b205f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2022
ms.locfileid: "8018350"
---
# <a name="dynamics-365-human-resources-infrastructure-merge---release-10025-update"></a>Unione dell'infrastruttura Dynamics 365 Human Resources - Aggiornamento della versione 10.0.25

La versione 10.0.25 introduce il primo ciclo di funzionalità nell'unione dell'infrastruttura. Durante l'unione dell'infrastruttura, Microsoft Dynamics 365 Human Resources viene unito con l'infrastruttura Finance and Operations. Tuttavia, continuerà ad essere concesso in licenza come applicazione indipendente, come Dynamics 365 Finance e Dynamics 365 Supply Chain Management. Per ulteriori informazioni sull'unione dell'infrastruttura, vedi [Domande frequenti sull'unione dell'infrastruttura Dynamics 365 Human Resources](../human-resources/hr-infrastructure-merge-faq.md).

L'unione fornirà coerenza agli utenti di Human Resources nei seguenti modi:

- [La gestione dell'ambiente e le integrazioni sono coerenti tra le app Human Resources e Finance and Operations.](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/consistent-environment-management-integrations-between-human-resources-finance-operations-apps)

    - Gestisci gli ambienti in Microsoft Dynamics Lifecycle Services, ricerca di problemi e Regression Suite Automation Tool.
    - Esiste un'unica base di codice, in cui vengono rilasciate nuove funzionalità per Human Resources come parte del normale processo di aggiornamento di una versione.
    - Il modo in cui gli aggiornamenti e gli hotfix vengono applicati agli ambienti è coerente.

- [Le opzioni di estensibilità sono migliorate.](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/improve-extensibility-options.md)

    - Puoi continuare a usare gli strumenti Microsoft Power Platform per estendere secondo le necessità.
    - Puoi estendere la funzionalità tramite moduli, tabelle, metodi e API (Application Programming Interface).
    - Puoi creare ed estendere le entità.

    Per ulteriori informazioni sulle opzioni di estensione disponibili, vedi [Panoramica dell'estendibilità in Dynamics 365](../fin-ops-core/dev-itpro/extensibility/extensibility-home-page.md).

- [Crea un set di funzionalità per Human Resources in Dynamics 365.](/dynamics365-release-plan/2021wave2/human-resources/create-one-set-human-resources-capabilities-within-dynamics-365.md)

    Nella versione 10.0.25, le capacità funzionali che esistevano solo in Human Resources sono state rese disponibili sull'infrastruttura Finance and Operations. Affinché i clienti possano trarre vantaggio da queste funzionalità in un ambiente Finance and Operations, le seguenti funzionalità di Human Resources devono essere abilitate in Gestione funzionalità.

    | Nome funzionalità | Panoramica | Stato rilascio | 
    |--------------|----------|----------------| 
    | Calcolo degli anni di servizio | Un'opzione di configurazione consente di selezionare la data utilizzata per il calcolo **Anni di servizio**. | Generalmente disponibile | 
    | Miglioramenti dell'esperienza flusso di lavoro | Questa funzione offre un'esperienza utente migliorata per gli invii e le approvazioni del flusso di lavoro. | Generalmente disponibile | 
    | Stampa revisioni delle prestazioni | È possibile stampare le revisioni delle prestazioni in formato PDF. | Generalmente disponibile | 
    | Collegamenti personalizzati in **Self-service responsabile** | Puoi creare collegamenti personalizzati che vengono visualizzati nella sezione **Collegamenti correlati** di **Self service responsabile**. | Generalmente disponibile | 
    | Visualizzazione retribuzione interaziendale | Gli utenti possono visualizzare i piani di compensazione in **Self service responsabile** per tutte le persone giuridiche, senza dover cambiare società. | Generalmente disponibile | 
    | Configurazione di più livelli retributivi per mansione\*&dagger; | Ora più livelli retributivi sono supportati nelle mansioni. | Generalmente disponibile | 
    | Gestione attività\* | È possibile creare elenchi di controllo e attività per il processo di onboarding, offboarding e transizione. | Anteprima | 
    | Immissione dati dipendente semplificata | Questa funzione fornisce un'esperienza utente aggiornata nell'esistente pagina **Lavoratore**. | Anteprima | 
    | Miglioramenti all'esperienza utente in Risorse umane | Vedi la tabella nella sezione successiva.  | Anteprima | 

\* Questa funzione deve essere attivata prima della funzionalità **Miglioramenti dell'esperienza utente Human Resources**.

&dagger; Questa funzionalità non può essere disabilitata dopo l'abilitazione.

## <a name="human-resource-user-experience-enhancements"></a>Miglioramenti dell'esperienza utente Human Resources

| Nome funzionalità | Panoramica | 
|--------------|----------| 
| Elimina impiego | È possibile eliminare un impiego di un dipendente. | 
| Famiglie di mansioni | Puoi tenere traccia di un gruppo di mansioni che implicano lavori, formazione, competenze, conoscenze ed esperienze simili. | 
| Campi di impiego aggiuntivi | Sono stati aggiunti i seguenti campi: **Categoria di impiego**, **Tipo di impiego**, e **Stato di impiego**. | 
| Pagina **Lavoratori senza impiego** | La pagina mostra un elenco di lavoratori che non hanno un record di impiego. | 
| Aggiornamento dell'esperienza utente della dimensione della posizione | È disponibile un'esperienza utente migliorata per l'assegnazione di dimensioni di posizione per persona giuridica. | 
| Modifiche all'indirizzo nell'area di lavoro **Gestione personale** | Questa funzionalità fornisce un conteggio di tutte le modifiche agli indirizzi avvenute durante il numero di giorni specificato, come definito nella pagina **Parametri di Human Resources**. | 
| Record in scadenza nell'area di lavoro **Gestione personale** | Questa funzione fornisce un elenco di articoli che sono scaduti o che scadranno per certificati, identificazioni, periodi di prova, analisi o test. | 
| Pagina **Convalida gerarchia posizioni** | Viene eseguito un controllo per i riferimenti circolari nella gerarchia delle righe di posizione. | 
| Informazioni sulla retribuzione specifiche per paese | Ulteriori campi sulla retribuzione sono disponibili nella pagina **Impiego lavoratore**, a seconda del paese o dell'area geografica della persona giuridica in cui i lavoratori sono impiegati. | 
| Miglioramenti dei report di conformità | Ulteriori opzioni di report sono disponibili per EEO-1, Vets 4212 e OSHA300a. | 
| Aggiornamenti all'area di lavoro **Gestione personale** | Sono stati apportati aggiornamenti per tenere traccia delle modifiche agli indirizzi e dei record in scadenza. Inoltre, le nuove schede elencano le azioni dei lavoratori e delle posizioni. | 
