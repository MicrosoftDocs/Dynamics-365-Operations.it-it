---
title: Provisioning di Human Resources nell'infrastruttura di finanza e operazioni
description: Questo articolo spiega il processo di approvvigionamento di un nuovo ambiente di produzione per Microsoft Dynamics 365 Human Resources nell'infrastruttura di finanza e operazioni.
author: twheeloc
ms.date: 01/07/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SystemAdministrationWorkspaceForm
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 2fd8176d16178ecc4ba667e5937f2cec2e0af2c3
ms.sourcegitcommit: bd3b55e1af28e592c97b540de1e87cd8ba9c35a8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/03/2022
ms.locfileid: "9221595"
---
# <a name="provision-human-resources-in-the-finance-and-operations-infrastructure"></a>Provisioning di Human Resources nell'infrastruttura di finanza e operazioni

_**Si applica a**: Human Resources nell'infrastruttura delle app per la finanza e le operazioni_ 

> [!NOTE]
> A partire da luglio 2022, non sarà possibile eseguire il provisioning dei nuovi ambienti Human Resources nell'infrastruttura Human Resources autonoma, né potranno essere creati nuovi progetti Microsoft Dynamics Lifecycle Services (LCS) sull'infrastruttura stessa. I clienti potranno distribuire gli ambienti Human Resources nell'infrastruttura di finanza e operazioni.

Questo articolo spiega il processo di approvvigionamento di un nuovo ambiente di produzione per Microsoft Dynamics 365 Human Resources nell'infrastruttura di finanza e operazioni.

## <a name="prerequisites"></a>Prerequisiti

I seguenti prerequisiti devono essere presenti prima di poter eseguire il provisioning di un nuovo ambiente:

- Hai acquistato Human Resources tramite un accordo con un Cloud Solution Provider (CSP) o un'architettura aziendale (EA). Se disponi di una licenza per Dynamics 365 che include già il piano di assistenza per Human Resources e non puoi completare i passaggi in questo articolo, contatta il Supporto tecnico.
- L'amministratore globale ha effettuato l'accesso a [Microsoft Dynamics Lifecycle Services (LCS)](https://lcs.dynamics.com) e ha creato un nuovo progetto di finanza e operazioni.

## <a name="provision-a-human-resources-trial-environment"></a>Effettuare il provisioning di un ambiente di valutazione per Human Resources

> [!NOTE]
> A partire da aprile 2022, gli ambienti di valutazione di Human Resources non saranno disponibili nell'applicazione autonoma. I potenziali clienti interessati a valutare le funzionalità di Human Resources all'interno delle app per la finanza e le operazioni possono farlo utilizzando la versione di valutazione gratuita di 30 giorni insieme ai dati demo. Dynamics 365 Finance includerà le funzionalità di Human Resources introdotte nell'infrastruttura di Finance tramite l'unione dell'applicazione autonoma. Per ulteriori informazioni, vedere[L'unione delle offerte per HR riunisce le funzionalità per i clienti](https://cloudblogs.microsoft.com/dynamics365/it/2021/09/15/merging-of-hr-offerings-brings-capabilities-together-for-customers). Per ulteriori informazioni sulle versioni di valutazione di Dynamics 365 Finance, consultare la [guida dettagliata](../fin-ops-core/fin-ops/get-started/before-you-buy.md).

## <a name="plan-human-resources-environments"></a>Pianificare gli ambienti Human Resources

Prima di creare il primo ambiente Human Resources, è necessario pianificare attentamente le esigenze ambientali per il progetto. Un abbonamento di base a Human Resources include due ambienti: un ambiente di produzione e un ambiente di test di accettazione standard predefinito (sandbox). A seconda della complessità del progetto, avrai la possibilità di acquistare ambienti aggiuntivi per supportare le attività del progetto.

Di seguito sono riportate alcune considerazioni per gli ambienti opzionali aggiuntivi:

- **Migrazione dei dati**: le attività di migrazione dei dati permettono di usare l'ambiente sandbox a scopo di test durante il progetto. Avere un ambiente aggiuntivo significa poter continuare le attività di migrazione dei dati mentre le attività di test e la configurazione si verificano simultaneamente in un ambiente diverso.
- **Integrazione**: configurazione e test delle integrazioni, che potrebbe includere integrazioni native o personalizzate come quelle per le retribuzioni, i sistemi di tracciamento dei candidati o i sistemi di benefit e i fornitori.
- **Formazione**: potresti avere bisogno di un ambiente separato configurato con una serie di dati di formazione per formare i dipendenti sull'uso del nuovo sistema. 
- **Progetto multifase**: potresti avere bisogno di un ambiente aggiuntivo per supportare la configurazione, la migrazione dei dati, il test o altre attività in una fase del progetto pianificata dopo la fase operativa iniziale del progetto.
- **Sviluppo**: nell'infrastruttura di finanza e operazioni ora puoi estendere la soluzione e sviluppare nuove personalizzazioni. Ogni sviluppatore deve usare il proprio ambiente di sviluppo. Per ulteriori informazioni, vedere [Distribuzione e accesso agli ambienti di sviluppo](../fin-ops-core/dev-itpro/dev-tools/access-instances.md).
- **GOLD**: per le nuove distribuzioni, è prassi comune usare un ambiente GOLD separato e incontaminato per la configurazione e la migrazione dei dati. Questo ambiente può essere usato nel corso dell'implementazione per aggiornare altri ambienti. Verrà usato per creare il nuovo ambiente di produzione che adotta la configurazione base e la migrazione dei dati. Non puoi distribuire un ambiente di produzione nell'infrastruttura di finanza e operazioni fino al completamento del processo di predisposizione al go-live. Per ulteriori informazioni, vedere [Preparazione per il go-live](../fin-ops-core/fin-ops/imp-lifecycle/prepare-go-live.md).

<!--NOTE: Need to come back and verify Tier-1 can be used and if a customer cannot purchase tier 3-5 need specific documentation about this.-->

> [!IMPORTANT]
> Quando consideri i tuoi ambienti, ti raccomandiamo il seguente approccio:
>
> - Usa l'ambiente di test di accettazione standard predefinito (in precedenza sandbox) o un altro ambiente per eseguire un cutover fittizio prima del go-live.
> - Prepara una lista di controllo dettagliata per il cutover che includa ciascuno dei pacchetti di dati richiesti per migrare i dati finali nell'ambiente di produzione durante il cutover del go-live. Questa raccomandazione è particolarmente importante se non disponi di un ambiente GOLD separato per l'archiviazione delle configurazioni.
> - Usa l'ambiente di test di accettazione standard predefinito (in precedenza sandbox) o un altro ambiente di livello 2 o superiore come ambiente di TEST nel corso del progetto. Se hai bisogno di ambienti aggiuntivi, la tua organizzazione può acquistarli a un costo aggiuntivo.

## <a name="create-an-lcs-project"></a>Creare un progetto LCS

Per utilizzare LCS per la gestione degli ambienti Human Resources, è dapprima necessario creare un progetto LCS. Se stai migrando il tuo ambiente Human Resources all'infrastruttura di finanza e operazioni, devi creare un nuovo progetto LCS per le app per la finanza e le operazioni. Se hai già un progetto LCS per altre app per la finanza e le operazioni, puoi abilitare le funzionalità di Human Resources nell'area di lavoro **Gestione delle funzionalità**. Per ulteriori informazioni, vedere [Panoramica della gestione funzionalità](../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

Quando un nuovo cliente si iscrive a Human Resources, l'abbonamento include un'area di lavoro per il progetto di implementazione. Una volta che il cliente ha attivato il servizio, l'amministratore del tenant deve accedere a <https://lcs.dynamics.com> usando l'account del tenant. L'area di lavoro del progetto viene automaticamente creata per l'organizzazione. Per ulteriori informazioni, vedere [Lifecycle Services (LCS) per i clienti delle app per la finanza e le operazioni](../fin-ops-core/dev-itpro/lifecycle-services/lcs-works-lcs.md).

> [!NOTE]
> Per garantire il corretto provisioning, l'account utilizzato per eseguire il provisioning dell'ambiente Human Resources deve essere assegnato al ruolo **Amministratore di sistema** o **Personalizzatore di sistema** nell'ambiente Power Apps associato all'ambiente Human Resources. Per ulteriori informazioni su come assegnare ruoli di sicurezza agli utenti in Microsoft Power Platform, vedere [Configurare la sicurezza degli utenti per le risorse](/power-platform/admin/database-security).

Prima di poter distribuire gli ambienti, devi completare il processo di onboarding del progetto LCS. Per ulteriori informazioni, vedere [Onboarding del progetto](../fin-ops-core/dev-itpro/lifecycle-services/project-onboarding.md). Per ulteriori informazioni su come usare LCS, vedere [Manuale dell'utente di Lifecycle Services (LCS)](../fin-ops-core/dev-itpro/lifecycle-services/lcs-user-guide.md).

## <a name="deploy-human-resources-environments"></a>Distribuire gli ambienti Human Resources

La distribuzione delle app per la finanza e le operazioni, inclusa Human Resources, nel cloud richiede che tu abbia ben chiaro l'ambiente e l'abbonamento oggetto della distribuzione, chi può eseguire queste attività e quali dati e personalizzazioni devi gestire. Ti consigliamo di usare un account di servizio anziché un utente con nome quando distribuisci i nuovi ambienti. Per ulteriori informazioni su come distribuire gli ambienti nell'infrastruttura di finanza e operazioni, vedere [Panoramica della distribuzione nel cloud](/fin-ops-core/dev-itpro/deployment/cloud-deployment-overview).

Per distribuire un ambiente di produzione per Human Resources nell'infrastruttura di finanza e operazioni, devi prima completare il processo di predisposizione al go-live. Per ulteriori informazioni, vedere [Preparazione per il go-live](../fin-ops-core/fin-ops/imp-lifecycle/prepare-go-live.md). Questo processo include la stima dell'abbonamento in LCS. Per ulteriori informazioni, vedere [Stima dell'abbonamento](../fin-ops-core/dev-itpro/lifecycle-services/subscription-estimator.md).

## <a name="integrate-microsoft-power-platform-with-human-resources"></a>Integrare Microsoft Power Platform con Human Resources

Microsoft Power Platform fornisce una suite di funzionalità per le app Dynamics 365 tramite l'interfaccia di amministrazione di Power Platform. È possibile integrare ed estendere l'utilizzo dei dati di Human Resources usando gli strumenti di Microsoft Power Platform. Per informazioni su come integrare Human Resources con Microsoft Power Platform, vedere [Integrazione di Microsoft Power Platform con le app per la finanza e le operazioni](../fin-ops-core/dev-itpro/power-platform/overview.md).

## <a name="supported-geographies"></a>Aree geografiche supportate

Per informazioni sulle lingue e le aree geografiche supportate per Human Resources, vedere [Globale per progettazione: informazioni sui Paesi e le lingue supportati](https://dynamics.microsoft.com/availability-reports/).

## <a name="grant-access-to-the-environment"></a>Concedere l'accesso all'ambiente

Per impostazione predefinita, l'accesso è consentito solo all'amministratore globale che ha creato ambiente. È necessario concedere esplicitamente l'accesso ad altri utenti dell'applicazione. È necessario aggiungere utenti e assegnare loro i ruoli appropriati nell'ambiente Human Resources. Per ulteriori informazioni, vedere [Creare nuovi utenti](/dynamics365/unified-operations/dev-itpro/sysadmin/tasks/create-new-users) e [Assegnare gli utenti ai ruoli di sicurezza](/dynamics365/unified-operations/dev-itpro/sysadmin/tasks/assign-users-security-roles).

## <a name="additional-resources"></a>Risorse aggiuntive
Altre informazioni su come usare e gestire i progetti in LCS nell'infrastruttura delle app per la finanza e le operazioni sono disponibili nelle seguenti risorse:

- [Risorse Lifecycle Services](../fin-ops-core/dev-itpro/lifecycle-services/lcs.md)
- [Manuale dell'utente di Lifecycle Services (LCS)](../fin-ops-core/dev-itpro/lifecycle-services/lcs-user-guide.md)
- [Panoramica distribuzione self-service](../fin-ops-core/dev-itpro/deployment/infrastructure-stack.md)
- [Home page delle operazioni di spostamento dei database](../fin-ops-core/dev-itpro/database/dbmovement-operations.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
