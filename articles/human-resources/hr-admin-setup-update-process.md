---
title: Aggiornare un processo
description: Microsoft Dynamics 365 Human Resources è un vero software come un servizio (SaaS, software as a service) che fornisce aggiornamenti di servizio continui e touchless per modifiche di applicazioni o piattaforme.
author: twheeloc
ms.date: 12/01/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SystemAdministrationWorkspaceForm
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-27
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 197b3c5717494ab3c80a57cda337a9021293bf73
ms.sourcegitcommit: 68efa7b89273d04484566cbe14d3533a8fd4ee53
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2022
ms.locfileid: "9819298"
---
# <a name="update-process"></a>Aggiornare un processo

_**Si applica a**: Human Resources nell'infrastruttura autonoma_ 

> [!NOTE]
> A partire da luglio 2022, non sarà possibile eseguire il provisioning dei nuovi ambienti Human Resources nell'infrastruttura Human Resources autonoma, né potranno essere creati nuovi progetti Microsoft Dynamics Lifecycle Services (LCS) sull'infrastruttura stessa. I clienti potranno distribuire gli ambienti Human Resources nell'infrastruttura di finanza e operazioni. Per ulteriori informazioni, vedere [Provisioning di Human Resources nell'infrastruttura di finanza e operazioni](hr-admin-setup-provision-fo.md).

> [!IMPORTANT]
> Il processo di aggiornamento e applicazione di hotfix nell'infrastruttura delle app per la finanza e le operazioni è diverso rispetto a quello per l'infrastruttura Human Resources autonoma. Per ulteriori informazioni su come eseguire il processo di aggiornamento, vedere [Processo per il passaggio all'ultimo aggiornamento di finanza e operazioni](../fin-ops-core/dev-itpro/migration-upgrade/upgrade-latest-update.md). Per ulteriori informazioni sugli hotfix, vedere [Download degli aggiornamenti da Lifecycle Services (LCS)](/fin-ops-core/dev-itpro/migration-upgrade/download-hotfix-lcs.md). 

Microsoft Dynamics 365 Human Resources è un vero software come un servizio (SaaS, software as a service) che fornisce aggiornamenti di servizio continui e touchless. Questi aggiornamenti contengono modifiche all'applicazione e alla piattaforma che spesso generano miglioramenti fondamentali nel servizio, inclusi aggiornamenti normativi.

## <a name="update-policy"></a>Criteri di aggiornamento

Gli aggiornamenti vengono rilasciati a cadenza regolare per tutti gli ambienti. Human Resources è supportato secondo i [criteri relativi al ciclo di vita di Microsoft](https://support.microsoft.com/hub/4095338/microsoft-lifecycle-policy), i quali offrono linee guida coerenti e prevedibili per la disponibilità del supporto.

## <a name="release-cadence"></a>Cadenza di rilascio 

Gli aggiornamenti di Human Resources vengono applicati automaticamente a tutti gli ambienti. Human Resources fornisce due tipi di rilasci:

- **Aggiornamenti del servizio**: gli aggiornamenti del servizio includono anche gli aggiornamenti applicabili della piattaforma quando vengono rilasciati. Oltre agli aggiornamenti basati sulle eccezioni, gli aggiornamenti regolari del servizio si verificano in seguito agli aggiornamenti della piattaforma Dynamics 365 Finance (generalmente disponibili) di Dynamics 365 Finance. Per ulteriori informazioni sui rilasci della piattaforma, vedere [Novità o modifiche negli aggiornamenti della piattaforma](../fin-ops-core/dev-itpro/get-started/whats-new-home-page.md). Gli aggiornamenti prevedono un'implementazione globale in fasi tra le regioni. Per ulteriori informazioni sugli aggiornamenti, vedere [Novità o modifiche in Dynamics 365 Human Resources](hr-admin-whats-new.md).

- **Aggiornamenti della soluzione Dataverse**: questi aggiornamenti si verificano all'incirca ogni sei settimane, come necessario. Includono nuove entità e modifiche a entità esistenti in Dataverse. Questi aggiornamenti vengono rilasciati nelle stesse aree degli aggiornamenti bisettimanali e richiedono circa sei settimane per replicarsi in tutti i datacenter. Gli aggiornamenti della soluzione possono essere allineati o meno agli aggiornamenti del servizio bisettimanali.

> [!NOTE]
> Gli aggiornamenti della soluzione sono disponibili in tutti i datacenter una volta rilasciati. Se non si desidera attendere la replica automatica degli aggiornamenti, è possibile applicare manualmente questi aggiornamenti in qualsiasi datacenter di qualsiasi ambiente.

Quando necessario, Human Resources fornisce i seguenti tipi di correzioni:

- **Revisione (aggiornamento rapido)**: correzioni di bug che possono verificarsi con o indipendentemente da una versione di aggiornamento del servizio bisettimanale

- **Correzione di emergenza**: aggiornamenti rapidi proattivi e reattivi in genere autonomi che possono includere modifiche al codice o solo alla configurazione per risolvere problemi del sito live e possono verificarsi separatamente da una versione di aggiornamento del servizio bisettimanale

I rilasci sono verificati, testati e convalidati in un ambiente interno. Dopo essere state autorizzate, le build vengono distribuite alla produzione.

## <a name="communications"></a>Comunicazioni

È possibile scoprire cosa c'è in cantiere per Human Resources e cosa abbiamo rilasciato nelle seguenti pagine:

- [Roadmap di Dynamics 365 Human Resources](https://dynamics.microsoft.com/roadmap/human-resources/)

- [Piani di rilascio di Dynamics 365](/dynamics365/release-plans/)

- [Novità o modifiche in Dynamics 365 Human Resources](hr-admin-whats-new.md)

- [Ricerca di problemi in Lifecycle Services (LCS)](../fin-ops-core/dev-itpro/lifecycle-services/issue-search-lcs.md) (solo per bug relativi alla piattaforma)

- [Blog di Human Resources](https://community.dynamics.com/365/talent/b/dynamics365fortalent)

- [Comunità Yammer di Human Resources](https://www.yammer.com/dynamicsaxfeedbackprograms/#/threads/inGroup?type=in_group&feedId=10542230)

## <a name="preview-features-in-a-sandbox-environment"></a>Funzionalità di anteprima in un ambiente sandbox

È possibile convalidare le funzionalità di anteprima in un ambiente sandbox prima di abilitarle nell'ambiente di produzione. Per ulteriori informazioni sull'abilitazione delle funzionalità, vedere [Panoramica della gestione funzionalità](../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

Tutte le nuove funzionalità rimangono in anteprima per almeno 30 giorni e in genere per 30-60 giorni. Le principali funzionalità sono generalmente disponibili in ottobre e aprile di ogni anno successivo al periodo di anteprima. Non appena nuove funzioni sono presenti nell'area di lavoro **Gestione funzionalità**, è possibile attivarle. Alcune funzionalità possono essere attive per impostazione predefinita.

Talvolta, una funzionalità integrale viene attivata per impostazione predefinita e non può essere disattivata, ad esempio l'area di lavoro Gestione funzionalità.

Una volta che una funzionalità è generalmente disponibile, può essere attivata o disattivata negli ambienti di produzione. L'area di lavoro **Gestione funzionalità** indica quando una funzionalità di anteprima diventa obbligatoria. Questa data è in genere il 1° ottobre o il 1° aprile in base ai piani di rilascio semestrali. Non è possibile disattivare le funzionalità obbligatorie. Finché non diventa obbligatoria, è possibile attivare e disattivare una funzionalità in tutti gli ambienti.

Consigliamo vivamente di visualizzare in anteprima le funzionalità in un ambiente sandbox o di prova. È meglio creare una copia dell'ambiente di produzione o del database corrente in un ambiente sandbox in modo da poter ottenere l'esperienza completa delle nuove funzionalità con i propri dati.

Per ulteriori informazioni sul provisioning di un ambiente sandbox, vedere [Eseguire il provisioning di un progetto di Human Resources](hr-admin-setup-provision.md). Per rimuovere un ambiente di test, vedere [Rimuovere un'istanza](hr-admin-setup-remove-instance.md#remove-a-test-drive-environment). 

## <a name="report-bugs"></a>Segnalare i bug

Durante il test delle funzionalità di anteprima o di nuove funzionalità, è possibile che vengano rilevati elementi che non funzionano come previsto. Si prega di segnalare eventuali bug mediante il [supporto di Microsoft Dynamics 365](https://dynamics.microsoft.com/support/).

## <a name="see-also"></a>Vedere anche

[Piani di rilascio di Dynamics 365 e Power Platform](/dynamics365/release-plans)</br>
[Novità o modifiche in Dynamics 365 Human Resources](hr-admin-whats-new.md)</br>
[Criteri del ciclo di vita del software](../fin-ops-core/dev-itpro/migration-upgrade/versions-update-policy.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
