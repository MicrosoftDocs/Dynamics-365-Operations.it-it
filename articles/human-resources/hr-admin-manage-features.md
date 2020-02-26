---
title: Gestire le funzionalità
description: Informazioni su come attivare o disattivare nuove funzionalità in Dynamics 365 Human Resources.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: FeatureManagementWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 84ff11e8237ce0669f7f6ac70c5b4411c5d4b466
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2020
ms.locfileid: "3009513"
---
# <a name="manage-features"></a>Gestire le funzionalità

Nell'ambito della continua implementazione di nuove funzionalità per Microsoft Dynamics 365 Human Resources, vogliamo consentire ai clienti di utilizzare al più presto le nuove funzionalità. Forniamo funzionalità di anteprima che sono quasi pronte per la disponibilità generale e che sono state sottoposte a test esaurienti. Il nostro scopo è di ottenere un ultimo riscontro e la convalida dai clienti prima del rilascio delle funzionalità per una disponibilità generale.

Per ulteriori informazioni sulle nuove funzionalità in Human Resources, vedere [Novità o modifiche in Human Resources](hr-admin-whats-new.md) e [Piano di rilascio di Dynamics 365 e Power Platform](https://docs.microsoft.com/dynamics365/release-plans/#pivot=products&panel=products1).

L'area di lavoro **Gestione funzionalità** fornisce l'elenco delle funzionalità offerte in ciascuna versione. Per impostazione predefinita, le nuove funzionalità sono disabilitate. È possibile utilizzare l'area di lavoro per accendere alle funzionalità e visualizzare la documentazione correlata. Per ulteriori informazioni sulla gestione funzionalità, vedere [Panoramica della gestione funzionalità](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview).

Tutte le nuove funzionalità rimangono in anteprima per almeno 30 giorni e in genere per 30-60 giorni. Le principali funzionalità sono generalmente disponibili in ottobre e aprile di ogni anno successivo al periodo di anteprima. Non appena nuove funzioni sono presenti nell'area di lavoro **Gestione funzionalità**, è possibile attivarle. Alcune funzionalità possono essere attive per impostazione predefinita.

Una volta che una funzionalità è generalmente disponibile, può essere attivata o disattivata negli ambienti di produzione. L'area di lavoro **Gestione funzionalità** indica quando una funzionalità di anteprima diventa obbligatoria. Questa data è in genere il 1° ottobre o il 1° aprile in base ai piani di rilascio semestrali. Non è possibile disattivare le funzionalità obbligatorie. Finché non diventa obbligatoria, è possibile attivare e disattivare una funzionalità in tutti gli ambienti.

## <a name="enable-or-disable-preview-features"></a>Attivare o disattivare le funzionalità in anteprima

Per accedere alle funzionalità in anteprima, è necessario dapprima attivarle nel proprio ambiente. L'attivazione o la disattivazione delle funzionalità in anteprima è specifica dell'ambiente.

> [!IMPORTANT]
> Le funzionalità di anteprima sono disponibili solo negli ambienti **sandbox**. Quando si attiva una funzionalità di anteprima, la si abilita per tutti gli utenti dell'organizzazione in quell'ambiente. Quando la si disattiva, la si disabilita e la si rende inaccessibile agli utenti. Il supporto delle funzionalità in anteprima in Human Resources è limitato. È possibile che tali funzionalità utilizzino minori misure di privacy e di sicurezza e che non siano incluse nel contratto di servizio di Human Resources. Si consiglia di non utilizzare le funzionalità in anteprima per elaborare dati personali (ovvero qualsiasi informazione che potrebbe consentire l'identificazione dell'utente) o per elaborare altri dati soggetti a requisiti di conformità legali o normativi.

1. In Risorse umane, selezionare **Amministrazione sistema**.

2. Selezionare il riquadro **Gestione funzionalità**.

3. Per abilitare una funzionalità di anteprima, selezionarla dall'elenco, quindi selezionare **Abilita**. Per disabilitare una funzionalità di anteprima, selezionarla dall'elenco, quindi selezionare **Disabilita**.

## <a name="preview-feature-benefits-management"></a>Funzionalità di anteprima: Gestione benefit

Gestione benefit fornisce una soluzione flessibile che supporta una vasta gamma di opzioni di benefit nonché un'esperienza per i dipendenti di facile utilizzo che evidenzia le offerte proposte. Per ulteriori informazioni sulla configurazione e l'utilizzo di Gestione benefit, consultare [Panoramica di Gestione benefit](hr-benefits-management-overview.md).

Gestione benefit sostituisce la funzionalità nell'area di lavoro **Benefit**. Quando si abilita la funzione di anteprima Gestione benefit, non è più possibile accedere ai seguenti moduli nell'area di lavoro **Benefit**:

- **Benefit**
- **Elementi benefit**
- **Coefficienti di calcolo retribuzione**
- **Risultati iscrizione al benefit**
- **Risultati estensione e scadenza benefit**
- **Tipi di regole dei criteri di idoneità al benefit**
- **Criteri di idoneità benefit**
- **Eventi di idoneità**

È possibile visualizzare le informazioni in questi moduli in modalità di sola lettura. Se si desidera modificare le informazioni, è necessario dapprima disabilitare la funzionalità di anteprima Gestione benefit.

### <a name="benefits-management-known-issues"></a>Problemi noti di Gestione benefit

#### <a name="life-events"></a>Eventi reali

Durante l'elaborazione di eventi reali, l'utente riceve un messaggio di errore:

La data di inizio della copertura deve essere compresa tra *inizio del periodo del piano* e *fine del periodo del piano*. 

L'evento reale continuerà a essere elaborato come previsto.

#### <a name="eligibility-processing"></a>Elaborazione dell'idoneità

Quando si esegue l'idoneità per benefit che utilizzano un importo di copertura 1-5X stipendio, % di stipendio e Importo forfettario, è necessario impostare la data di Dettagli del benefit su Data di inizio del dipendente in **Storico esperienze lavorative**, con le ore lavorate, la frequenza di pagamento e l'importo di retribuzione benefit annuale. Se esiste una retribuzione fissa per il lavoratore, immettere le ore lavorate insieme alla frequenza di pagamento e l'importo di retribuzione annuale verrà calcolato. Se il dipendente è stipendiato, non è necessario specificare le ore lavorate. Quando si creano nuovi lavoratori, si consiglia di immettere prima la retribuzione fissa. Per aggiornare il record Dettagli del benefit, selezionare **Lavoratore > Storico lavoratore > Dettagli impiego**. Modificare la data in base alla data di inizio del lavoratore.

#### <a name="employee-self-service"></a>Dipendente self-service

I dipendenti possono selezionare un piano per il quale non sono qualificati. Ad esempio, un lavoratore non ha persone a carico, ma è autorizzato a selezionare un piano sanitario con un'opzione di copertura familiare.

L'importo del dipendente non viene calcolato durante l'aggiornamento dell'importo della copertura per l'assicurazione sulla vita. Ad esempio, quando a un dipendente viene offerto un piano di assicurazione sulla vita, può selezionare fino a $50.000 in copertura al costo di $ 0,36 per $1.000 di copertura.  Quando il dipendente aggiorna l'importo della copertura, il costo associato del dipendente rimane a zero.

Per un piano di benefit che consente una sola selezione di quel tipo di piano, l'utente riceverà un errore se tenta di rinunciare a un piano dopo aver selezionato un piano. Ad esempio, un utente seleziona un piano sanitario e lo inserisce nel carrello. L'utente quindi seleziona **Rinuncia** per un altro piano sanitario. L'utente riceverà un messaggio di errore.

## <a name="preview-features-in-leave-and-absence"></a>Funzionalità di anteprima in Congedo e assenza

Le funzionalità di anteprima in Congedo e assenza includono:

- **Calendario congedo e assenza** - I parametri di Congedo e assenza verranno spostati da **Parametri Risorse umane** a una nuova schermata chiamata **Parametri di congedo e assenza**. La nuova schermata include una nuova scheda **Calendario**. Questa anteprima abilita solo un sottoinsieme dei parametri. È possibile accedere alla nuova schermata dalla scheda **Collegamenti** dell'area di lavoro **Congedo e assenza**. I calendari includono:
  - **Calendario aziendale** - Mostra tutte le richieste di permesso dei dipendenti. Le persone con il ruolo **Risorse umane** possono accedere a questo calendario dalla scheda **Collegamenti** dell'area di lavoro **Congedo e assenza**.
  - **Calendario team responsabile** - Mostra tutte le richieste di permesso dei diretti subalterni. I responsabili possono accedere al calendario dalla scheda **Team personale** in Dipendente self-service sotto **Congedo e assenza**. 

- **Calendario festività congedo e assenza** - I tipi di congedo includono una nuova opzione **Giorni festivi**, utilizzata insieme al calendario orario di lavoro. I giorni definiti come festività e chiusure sono ora designati **Giorni festivi** quando vengono generati giorni lavorativi. Quando vengono elaborati gli accumuli, vengono apportate correzioni ai dipendenti assegnati al calendario per tenere conto delle festività che cadono in un giorno lavorativo.

- **Controllo accumuli congedi** - Una nuova schermata consente di verificare quando gli accumuli sono stati elaborati ed eliminati, da tutti i dipendenti e dai singoli dipendenti. È possibile accedere a questa nuova schermata dalla scheda **Collegamenti** dell'area di lavoro **Congedo e assenza**.

- **Eliminazione accumuli congedi** - Ora è possibile eliminare i record di accumuli per specifici piani di congedo. È possibile accedere a questa nuova opzione dalla scheda **Collegamenti** dell'area di lavoro **Congedo e assenza**. Per i singoli dipendenti, questa opzione appare in **Congedo e assenza** nel profilo del dipendente. 

- **Arrotondamento accumulo congedo** - Nuove opzioni di **Tipo di congedo** definiscono quale tipo di arrotondamento deve essere utilizzato per l'accumulo nonché la precisione decimale dell'arrotondamento durante il processo di accumulo. Quando gli accumuli vengono elaborati, l'arrotondamento e la precisione vengono applicati ai record degli accumuli. 

- **configurare più tipi di congedo per un singolo piano di congedo** - Una nuova colonna nella programmazione degli accumuli di congedi per i tipi di congedi consente di definire più tipi di congedi in un piano di congedo e assenza con diverse programmazioni degli accumuli. Il campo **Tipo di congedo** precedente è stato rimosso. Al momento dell'iscrizione dei dipendenti, i saldi per i tipi di congedo ora vengono visualizzati in una tabella anziché nella parte superiore dello schermo.

  > [!IMPORTANT]
  > Dopo aver abilitato questa funzionalità, non è possibile disattivarla.

- **Utilizza equivalenza a tempo pieno di un dipendente** - Una nuova colonna nella programmazioni degli accumuli di congedi consente di utilizzare l'equivalenza a tempo pieno. Quando gli accumuli vengono elaborati, l'applicazione utilizza la posizione primaria del dipendente e l'equivalenza a tempo pieno per determinare l'importo dell'accumulo ripartito proporzionalmente.

  > [!NOTE]
  > Questa funzionalità è disponibile solo se si abilita **Configura più tipi di congedo per un singolo piano di congedo**. 

## <a name="feedback"></a>Commenti e suggerimenti

Vogliamo ricevere commenti degli utenti riguardo l'utilizzo delle funzionalità di anteprima. Invitiamo gli utenti a pubblicare regolarmente i loro commenti relativi all'utilizzo di queste o altre funzionalità sui siti elencati di seguito:

- [Community](https://community.dynamics.com/enterprise/f/759?pi53869=0&category=Talent) - Questo sito è una risorsa eccellente dove gli utenti possono discutere casi d'uso, porre domande e ottenere informazioni dalla community.
- Invitiamo gli utenti a indicare le funzionalità che vorrebbero fossero integrate nel prodotto o le modifiche che dovrebbero essere apportate alle funzionalità esistenti. Suggerire idee sui prodotti in [Idee per Human Resources](https://powerusers.microsoft.com/t5/Ideas-for-Human-Resources/idb-p/HumanResources)
    
Si raccomanda di non includere dati personali (qualsiasi informazione che possa consentire l'identificazione dell'utente) nel riscontro o nei commenti sul prodotto inviati. Le informazioni raccolte potrebbero essere analizzate ulteriormente e non vengono utilizzate per soddisfare richieste in base alle normative sulla privacy applicabili. I dati personali raccolti separatamente in questi programmi sono soggetti all'[Informativa sulla privacy di Microsoft](https://privacy.microsoft.com/privacystatement).

## <a name="see-also"></a>Vedere anche

- [Novità in Risorse umane](hr-admin-whats-new.md)
- [Piani di rilascio di Dynamics 365 e Power Platform](https://docs.microsoft.com/dynamics365/release-plans/#pivot=products&panel=products1)