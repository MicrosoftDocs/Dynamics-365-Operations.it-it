---
title: Aggiornare un processo
description: Microsoft Dynamics 365 Human Resources è un vero software come un servizio (SaaS, software as a service) che fornisce aggiornamenti di servizio continui e touchless per modifiche di applicazioni o piattaforme.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 267682f4497bacf70f93840a948d0e525dfa4aa1
ms.sourcegitcommit: f38302b9430f2ab3efe91d0a7beff946bc610e8f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2020
ms.locfileid: "3092203"
---
# <a name="update-process"></a>Aggiornare un processo

Microsoft Dynamics 365 Human Resources è un vero software come un servizio (SaaS, software as a service) che fornisce aggiornamenti di servizio continui e touchless. Questi aggiornamenti contengono modifiche all'applicazione e alla piattaforma che spesso generano miglioramenti fondamentali nel servizio, inclusi aggiornamenti normativi.

## <a name="update-policy"></a>Criteri di aggiornamento

Gli aggiornamenti vengono rilasciati a cadenza regolare per tutti gli ambienti. Human Resources è supportato secondo i [criteri relativi al ciclo di vita di Microsoft](https://support.microsoft.com/hub/4095338/microsoft-lifecycle-policy), i quali offrono linee guida coerenti e prevedibili per la disponibilità del supporto.

## <a name="release-cadence"></a>Cadenza di rilascio

Gli aggiornamenti di Human Resources vengono applicati automaticamente a tutti gli ambienti. Human Resources fornisce due tipi di rilasci:

- **Aggiornamenti del servizio**: aggiornamenti settimanali che includono correzioni di bug e nuove funzionalità. Gli aggiornamenti del servizio includono anche gli aggiornamenti applicabili della piattaforma quando vengono rilasciati. Per avere un'idea di quando vengono rilasciati gli aggiornamenti della piattaforma, vedere [Tabella 3: versioni della piattaforma ](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/migration-upgrade/versions-update-policy#table-3-platform-releases). In genere gli aggiornamenti settimanali vengono rilasciati il mercoledì. Per ulteriori informazioni sugli aggiornamenti settimanali, vedere [Novità o modifiche in Dynamics 365 Human Resources](https://docs.microsoft.com/dynamics365/talent/whats-new).

    Tutti i datacenter supportati vengono aggiornati settimanalmente, salvo diversa indicazione. Gli aggiornamenti settimanali in genere iniziano il mercoledì e vengono completati entro domenica. Gli Stati Uniti, l'Australia, l'Europa, il Regno Unito, l'Asia e il Canada sono inclusi negli aggiornamenti settimanali. 

- **Aggiornamenti della soluzione Common Data Service**: questi aggiornamenti si verificano all'incirca ogni sei settimane, come necessario. Includono nuove entità e modifiche a entità esistenti in Common Data Service. Questi aggiornamenti vengono rilasciati nelle stesse aree degli aggiornamenti settimanali e richiedono circa sei settimane per replicarsi in tutti i datacenter. Gli aggiornamenti della soluzione possono essere allineati o meno agli aggiornamenti del servizio settimanali.

La tabella seguente mostra un esempio di pianificazione:

| Settimana | Tipo di aggiornamento |
| --- | --- |
| 1 | Aggiornamenti del servizio (tutte le aree) |
| 2 | Aggiornamento del servizio (tutte le aree) + Aggiornamento della soluzione (aree della settimana 1) |
| 3 | Aggiornamento del servizio (tutte le aree) + Aggiornamento della soluzione (aree della settimana 2) |
| 4 | Aggiornamento del servizio (tutte le aree) + Aggiornamento della soluzione (aree della settimana 3) |
| 5 | Aggiornamento del servizio (tutte le aree) + Aggiornamento della soluzione (aree della settimana 4) |
| 6 | Aggiornamento del servizio (tutte le aree) + Aggiornamento della soluzione (aree della settimana 5) |
| 7 | Aggiornamento del servizio (tutte le aree) + Aggiornamento della soluzione (aree della settimana 6) |
| 8 | Aggiornamenti del servizio (tutte le aree) |

> [!NOTE]
> Gli aggiornamenti della soluzione sono disponibili in tutti i datacenter una volta rilasciati. Se non si desidera attendere la replica automatica degli aggiornamenti, è possibile applicare manualmente questi aggiornamenti in qualsiasi datacenter di qualsiasi ambiente.

Quando necessario, Human Resources fornisce anche i seguenti tipi di correzioni:

- **Revisione (aggiornamento rapido)**: correzioni di bug che possono verificarsi con o indipendentemente da una versione di aggiornamento del servizio settimanale

- **Correzione di emergenza**: aggiornamenti rapidi proattivi e reattivi in genere autonomi che possono includere modifiche al codice o solo alla configurazione per risolvere problemi del sito live e possono verificarsi separatamente da una versione di aggiornamento del servizio settimanale

I rilasci sono verificati, testati e convalidati in un ambiente interno. Dopo essere state autorizzate, le build vengono distribuite alla produzione.

## <a name="exceptions-in-2019"></a>Eccezioni nel 2019

Le seguenti date sono eccezioni al normale programma di rilascio:

| Data | Descrizione |
| --- | --- |
| Settimana del 25 novembre | Nessun aggiornamento |
| Settimana del 16 novembre | Solo aggiornamenti minori |
| Settimana del 23 novembre | Nessun aggiornamento |
| Settimana del 30 dicembre | Nessun aggiornamento |

## <a name="communications"></a>Comunicazioni

È possibile scoprire cosa c'è in cantiere per Human Resources e cosa abbiamo rilasciato nelle seguenti pagine:

- [Roadmap di Dynamics 365 Human Resources](https://dynamics.microsoft.com/roadmap/talent/)

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

- [Piani di rilascio di Dynamics 365 e Power Platform](https://docs.microsoft.com/dynamics365/release-plans)
- [Novità o modifiche in Dynamics 365 Human Resources](hr-admin-whats-new.md)
- [Criteri del ciclo di vita del software](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/migration-upgrade/versions-update-policy)

