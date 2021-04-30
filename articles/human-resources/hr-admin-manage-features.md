---
title: Gestisci funzionalità in Human Resources
description: Informazioni su come attivare o disattivare nuove funzionalità in Dynamics 365 Human Resources.
author: andreabichsel
ms.date: 04/06/2020
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 038e741978bce033621bad428321a4b14ac90650
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2021
ms.locfileid: "5889838"
---
# <a name="manage-features-in-human-resources"></a>Gestisci funzionalità in Human Resources

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Nell'ambito della continua implementazione di nuove funzionalità per Microsoft Dynamics 365 Human Resources, vogliamo consentire ai clienti di utilizzare al più presto le nuove funzionalità. Forniamo funzionalità di anteprima che sono quasi pronte per la disponibilità generale e che sono state sottoposte a test esaurienti. Il nostro scopo è di ottenere un ultimo riscontro e la convalida dai clienti prima del rilascio delle funzionalità per una disponibilità generale.

Per ulteriori informazioni sulle nuove funzionalità in Human Resources, vedere [Novità o modifiche in Human Resources](hr-admin-whats-new.md) e [Piano di rilascio di Dynamics 365 e Power Platform](/dynamics365/release-plans/?panel=products1#pivot=products).

L'area di lavoro **Gestione funzionalità** fornisce l'elenco delle funzionalità offerte in ciascuna versione. Per impostazione predefinita, le nuove funzionalità sono disabilitate. È possibile utilizzare l'area di lavoro per accendere alle funzionalità e visualizzare la documentazione correlata. Per ulteriori informazioni sulla gestione funzionalità, vedere [Panoramica della gestione funzionalità](../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

Tutte le nuove funzionalità rimangono in anteprima per almeno 30 giorni e in genere per 30-60 giorni. Le principali funzionalità sono generalmente disponibili in ottobre e aprile di ogni anno successivo al periodo di anteprima. Non appena nuove funzioni sono presenti nell'area di lavoro **Gestione funzionalità**, è possibile attivarle. Alcune funzionalità possono essere attive per impostazione predefinita.

Una volta che una funzionalità è generalmente disponibile, può essere attivata o disattivata negli ambienti di produzione. L'area di lavoro **Gestione funzionalità** indica quando una funzionalità di anteprima diventa obbligatoria. Questa data è in genere il 1° ottobre o il 1° aprile in base ai piani di rilascio semestrali. Non è possibile disattivare le funzionalità obbligatorie. Finché non diventa obbligatoria, è possibile attivare e disattivare una funzionalità in tutti gli ambienti.

## <a name="enable-or-disable-preview-features"></a>Attivare o disattivare le funzionalità in anteprima

Per accedere alle funzionalità in anteprima, è necessario dapprima attivarle nel proprio ambiente. L'attivazione o la disattivazione delle funzionalità in anteprima è specifica dell'ambiente.

> [!IMPORTANT]
> Le funzionalità di anteprima sono disponibili solo negli ambienti **sandbox**. Quando si attiva una funzionalità di anteprima, la si abilita per tutti gli utenti dell'organizzazione in quell'ambiente. Quando la si disattiva, la si disabilita e la si rende inaccessibile agli utenti. Il supporto delle funzionalità in anteprima in Human Resources è limitato. È possibile che tali funzionalità utilizzino minori misure di privacy e di sicurezza e che non siano incluse nel contratto di servizio di Human Resources. Si consiglia di non utilizzare le funzionalità in anteprima per elaborare dati personali (ovvero qualsiasi informazione che potrebbe consentire l'identificazione dell'utente) o per elaborare altri dati soggetti a requisiti di conformità legali o normativi.

1. In Risorse umane, selezionare **Amministrazione sistema**.

2. Selezionare il riquadro **Gestione funzionalità**.

3. Per abilitare una funzionalità di anteprima, selezionarla dall'elenco, quindi selezionare **Abilita**. Per disabilitare una funzionalità di anteprima, selezionarla dall'elenco, quindi selezionare **Disabilita**.

## <a name="enable-or-disable-benefits-management"></a>Abilitare o disabilitare Gestione benefit

Per abilitare Gestione benefit utilizzare la stessa procedura descritta in [Abilitare o disabilitare le funzionalità di anteprima](hr-admin-manage-features.md?enable-or-disable-preview-features).

> [!IMPORTANT]
> Non è possibile disabilitare Gestione benefit in un ambiente di **Produzione** dopo averlo abilitato. È tuttavia possibile disabilitare Gestione benefit in ambienti **Sandbox**.

Per ulteriori informazioni sulla configurazione e l'utilizzo di Gestione benefit, consultare [Panoramica di Gestione benefit](hr-benefits-management-overview.md).

Gestione benefit sostituisce la funzionalità nell'area di lavoro **Benefit**. Quando si abilita la funzione di anteprima Gestione benefit, non è più possibile accedere ai seguenti moduli nell'area di lavoro **Benefit**:

- **Benefit**
- **Elementi benefit**
- **Coefficienti di calcolo retribuzione**
- **Risultati iscrizione al benefit**
- **Risultati estensione e scadenza benefit**
- **Tipi di regole dei criteri di idoneità al benefit**
- **Criteri di idoneità benefit**
- **Eventi di idoneità**

È possibile visualizzare le informazioni in questi moduli in modalità di sola lettura. Se si desidera modificare le informazioni, è necessario dapprima disabilitare Gestione benefit (applicabile solo per gli ambienti **Sandbox**).

## <a name="enable-or-disable-leave-and-absence"></a>Abilitare o disabilitare congedo e assenza

Per abilitare Congedo e assenza utilizzare la stessa procedura descritta in [Abilitare o disabilitare le funzionalità di anteprima](hr-admin-manage-features.md?enable-or-disable-preview-features).

> [!IMPORTANT]
> Non è possibile disabilitare la funzionalità **Più tipi di congedo** in Congedo e assenza dopo averla abilitata. Questo vale per entrambi gli ambienti **sandbox** e di **produzione**.

Per ulteriori informazioni sulle funzionalità di anteprima in Congedo e assenza, vedere [Funzionalità di anteprima di Congedo e assenza](hr-leave-and-absence-overview.md?leave-and-absence-preview-features).

## <a name="send-us-feedback"></a>Invia commenti e suggerimenti

Vogliamo ricevere commenti degli utenti riguardo l'utilizzo delle funzionalità di anteprima. Invitiamo gli utenti a pubblicare regolarmente i loro commenti relativi all'utilizzo di queste o altre funzionalità sui siti elencati di seguito:

- [Community](https://community.dynamics.com/enterprise/f/759?pi53869=0&category=Talent) - Questo sito è una risorsa eccellente dove gli utenti possono discutere casi d'uso, porre domande e ottenere informazioni dalla community.
- Invitiamo gli utenti a indicare le funzionalità che vorrebbero fossero integrate nel prodotto o le modifiche che dovrebbero essere apportate alle funzionalità esistenti. Suggerire idee sui prodotti in [Idee per Human Resources](https://powerusers.microsoft.com/t5/Ideas-for-Human-Resources/idb-p/HumanResources).
    
Si raccomanda di non includere dati personali (qualsiasi informazione che possa consentire l'identificazione dell'utente) nel riscontro o nei commenti sul prodotto inviati. Le informazioni raccolte potrebbero essere analizzate ulteriormente e non vengono utilizzate per soddisfare richieste in base alle normative sulla privacy applicabili. I dati personali raccolti separatamente in questi programmi sono soggetti all'[Informativa sulla privacy di Microsoft](https://privacy.microsoft.com/privacystatement).

## <a name="see-also"></a>Vedere anche

- [Novità in Risorse umane](hr-admin-whats-new.md)
- [Piani di rilascio di Dynamics 365 e Power Platform](/dynamics365/release-plans/?panel=products1#pivot=products)

[!INCLUDE[footer-include](../includes/footer-banner.md)]