---
title: Aggiornare un processo
description: Microsoft Dynamics 365 Human Resources è un vero software come un servizio (SaaS, software as a service) che fornisce aggiornamenti di servizio continui e touchless per modifiche di applicazioni o piattaforme.
author: andreabichsel
ms.date: 09/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SystemAdministrationWorkspaceForm
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-27
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 4069e369b1a9f15372d1e29e3809198b90b12c7e
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5791535"
---
# <a name="update-process"></a>Aggiornare un processo

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Microsoft Dynamics 365 Human Resources è un vero software come un servizio (SaaS, software as a service) che fornisce aggiornamenti di servizio continui e touchless. Questi aggiornamenti contengono modifiche all'applicazione e alla piattaforma che spesso generano miglioramenti fondamentali nel servizio, inclusi aggiornamenti normativi.

## <a name="update-policy"></a>Criteri di aggiornamento

Gli aggiornamenti vengono rilasciati a cadenza regolare per tutti gli ambienti. Human Resources è supportato secondo i [criteri relativi al ciclo di vita di Microsoft](https://support.microsoft.com/hub/4095338/microsoft-lifecycle-policy), i quali offrono linee guida coerenti e prevedibili per la disponibilità del supporto.

## <a name="release-cadence"></a>Cadenza di rilascio 

Gli aggiornamenti di Human Resources vengono applicati automaticamente a tutti gli ambienti. Human Resources fornisce due tipi di rilasci:

- **Aggiornamenti del servizio**: aggiornamenti bisettimanali che includono correzioni di bug e nuove funzionalità. Gli aggiornamenti del servizio includono anche gli aggiornamenti applicabili della piattaforma quando vengono rilasciati. Per avere un'idea di quando vengono rilasciati gli aggiornamenti della piattaforma, vedere [Tabella 3: versioni della piattaforma ](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/migration-upgrade/versions-update-policy#table-3-platform-releases). Gli aggiornamenti bisettimanali prevedono un'implementazione globale in fasi tra le regioni. Per ulteriori informazioni sugli aggiornamenti bisettimanali, vedere [Novità o modifiche in Dynamics 365 Human Resources](hr-admin-whats-new.md).

    Tutti i datacenter supportati vengono aggiornati ogni due settimane, salvo diversa indicazione. Gli Stati Uniti, l'Australia, l'Europa, il Regno Unito, l'Asia e il Canada sono inclusi negli aggiornamenti bisettimanali. 

- **Aggiornamenti della soluzione Dataverse**: questi aggiornamenti si verificano all'incirca ogni sei settimane, come necessario. Includono nuove entità e modifiche a entità esistenti in Dataverse. Questi aggiornamenti vengono rilasciati nelle stesse aree degli aggiornamenti bisettimanali e richiedono circa sei settimane per replicarsi in tutti i datacenter. Gli aggiornamenti della soluzione possono essere allineati o meno agli aggiornamenti del servizio bisettimanali.

> [!NOTE]
> Gli aggiornamenti della soluzione sono disponibili in tutti i datacenter una volta rilasciati. Se non si desidera attendere la replica automatica degli aggiornamenti, è possibile applicare manualmente questi aggiornamenti in qualsiasi datacenter di qualsiasi ambiente.

Quando necessario, Human Resources fornisce anche i seguenti tipi di correzioni:

- **Revisione (aggiornamento rapido)**: correzioni di bug che possono verificarsi con o indipendentemente da una versione di aggiornamento del servizio bisettimanale

- **Correzione di emergenza**: aggiornamenti rapidi proattivi e reattivi in genere autonomi che possono includere modifiche al codice o solo alla configurazione per risolvere problemi del sito live e possono verificarsi separatamente da una versione di aggiornamento del servizio bisettimanale

I rilasci sono verificati, testati e convalidati in un ambiente interno. Dopo essere state autorizzate, le build vengono distribuite alla produzione.

## <a name="release-cadence-exceptions-in-2021"></a>Eccezioni di cadenza di rilascio nel 2021

Per tenere conto delle festività, il programma di rilascio per novembre e dicembre 2021 è il seguente:

- Versione di novembre: 1 novembre - 14 novembre
- Versione di dicembre: 29 dicembre - 12 dicembre
 
La cadenza di rilascio bisettimanale riprenderà come al solito l'10 gennaio 2022.

## <a name="communications"></a>Comunicazioni

È possibile scoprire cosa c'è in cantiere per Human Resources e cosa abbiamo rilasciato nelle seguenti pagine:

- [Roadmap di Dynamics 365 Human Resources](https://dynamics.microsoft.com/roadmap/human-resources/)

- [Piani di rilascio di Dynamics 365](https://docs.microsoft.com/dynamics365/release-plans/)

- [Novità o modifiche in Dynamics 365 Human Resources](hr-admin-whats-new.md)

- [Ricerca di problemi in Lifecycle Services (LCS)](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/lifecycle-services/issue-search-lcs) (solo per bug relativi alla piattaforma)

- [Blog di Human Resources](https://community.dynamics.com/365/talent/b/dynamics365fortalent)

- [Comunità Yammer di Human Resources](https://www.yammer.com/dynamicsaxfeedbackprograms/#/threads/inGroup?type=in_group&feedId=10542230)

## <a name="preview-features-in-a-sandbox-environment"></a>Funzionalità di anteprima in un ambiente sandbox

È possibile convalidare le funzionalità di anteprima in un ambiente sandbox prima di abilitarle nell'ambiente di produzione. Per ulteriori informazioni sull'abilitazione delle funzionalità, vedere [Panoramica della gestione funzionalità](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview).

Tutte le nuove funzionalità rimangono in anteprima per almeno 30 giorni e in genere per 30-60 giorni. Le principali funzionalità sono generalmente disponibili in ottobre e aprile di ogni anno successivo al periodo di anteprima. Non appena nuove funzioni sono presenti nell'area di lavoro Gestione funzionalità, è possibile attivarle. Alcune funzionalità possono essere attive per impostazione predefinita.

Talvolta, una funzionalità integrale viene attivata per impostazione predefinita e non può essere disattivata, ad esempio l'area di lavoro Gestione funzionalità.

Una volta che una funzionalità è generalmente disponibile, può essere attivata o disattivata negli ambienti di produzione. L'area di lavoro Gestione funzionalità indica quando una funzionalità di anteprima diventa obbligatoria. Questa data è in genere il 1° ottobre o il 1° aprile in base ai piani di rilascio semestrali. Non è possibile disattivare le funzionalità obbligatorie. Finché non diventa obbligatoria, è possibile attivare e disattivare una funzionalità in tutti gli ambienti.

Consigliamo vivamente di visualizzare in anteprima le funzionalità in un ambiente sandbox o di prova. È meglio creare una copia dell'ambiente di produzione o del database corrente in un ambiente sandbox in modo da poter ottenere l'esperienza completa delle nuove funzionalità con i propri dati.

Per ulteriori informazioni sul provisioning di un ambiente sandbox, vedere [Eseguire il provisioning di un progetto di Human Resources](hr-admin-setup-provision.md). Per rimuovere un ambiente di test, vedere [Rimuovere un'istanza](hr-admin-setup-remove-instance.md#remove-a-test-drive-environment). 

## <a name="report-bugs"></a>Segnalare i bug

Durante il test delle funzionalità di anteprima o di nuove funzionalità, è possibile che vengano rilevati elementi che non funzionano come previsto. Si prega di segnalare eventuali bug mediante il [supporto di Microsoft Dynamics 365](https://dynamics.microsoft.com/support/).

## <a name="see-also"></a>Vedere anche

[Piani di rilascio di Dynamics 365 e Power Platform](https://docs.microsoft.com/dynamics365/release-plans)</br>
[Novità o modifiche in Dynamics 365 Human Resources](hr-admin-whats-new.md)</br>
[Criteri del ciclo di vita del software](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/migration-upgrade/versions-update-policy)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
