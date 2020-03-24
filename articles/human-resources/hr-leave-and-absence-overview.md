---
title: Panoramica
description: L'area di lavoro **Congedo e assenza** in Dynamics 365 Human Resources fornisce un framework flessibile per la creazione di nuovi piani di congedo, flussi di lavoro per la gestione delle richieste e una pagina self-service intuitiva per consentire ai dipendenti di richiedere permessi.
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
ms.openlocfilehash: 493bc3abe82103541125914896252b2eae596b38
ms.sourcegitcommit: f38302b9430f2ab3efe91d0a7beff946bc610e8f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2020
ms.locfileid: "3091750"
---
# <a name="overview"></a>Panoramica

Dynamics 365 Human Resources consente di fornire importanti benefit di congedo ai propri lavoratori. L'area di lavoro **Congedo e assenza** fornisce un framework flessibile per la creazione di nuovi piani di congedo, flussi di lavoro per la gestione delle richieste e una pagina self-service intuitiva per consentire ai dipendenti di richiedere permessi. Le funzionalità di analisi consentono all'organizzazione di misurare e monitorare i saldi di congedo e l'utilizzo per i piani di congedo.

## <a name="set-up-leave-and-absence"></a>Configurare Congedo e assenza

Prima di poter creare piani di congedo per i dipendenti, è necessario eseguire alcuni passaggi:

- [Configurare i parametri di congedo e assenza](hr-leave-and-absence-parameters.md)
- [Creare un calendario orario di lavoro](hr-leave-and-absence-working-time-calendar.md)
- [Creare un flusso di lavoro di richieste di congedo](hr-leave-and-absence-workflow.md)

## <a name="create-and-manage-leave-plans"></a>Creare e gestire piani di congedo

Prima di creare piani di congedo per i lavoratori, è ncessario creare tipi di congedo e assenza. Dopo aver creato un piano di congedo, è possibile iscrivere i lavoratori al piano. È anche possibile eseguire il processo di accumulo, creare avvisi e visualizzare dati analitici per i piani.

- [Configurare tipi di congedo e assenza](hr-leave-and-absence-types.md)
- [Creare un piano di congedo e assenza](hr-leave-and-absence-plans.md)
- [Assegnare i lavoratori a un piano di congedo](hr-leave-and-absence-enroll.md)
- [Accumulare piani di congedo e assenza](hr-leave-and-absence-accrue.md)
- [Visualizzare analisi per congedi e assenze](hr-leave-and-absence-analytics.md)

## <a name="request-time-off-and-manage-requests"></a>Richiedere permessi e gestire le richieste

Le richieste di permesso possono essere inviate dai dipendenti e gestite nell'area di lavoro **Dipendente self-service**.

- [Richiedere permessi](hr-employee-self-service-request-time-off.md)
- [Gestire richieste di congedo e assenza](hr-employee-self-service-manage-requests.md)

## <a name="leave-and-absence-preview-features"></a>Funzionalità di anteprima di Congedo e assenza

È possibile provare le nuove funzionalità di anteprima di Congedo e assenza in un ambiente **Sandbox**. Per informazioni su come attivare le funzionalità di anteprima, vedere [Gestire le funzionalità](hr-admin-manage-features.md). Le funzionalità di anteprima includono:

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
