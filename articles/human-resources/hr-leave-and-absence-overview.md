---
title: Panoramica
description: In Dynamics 365 Human Resources, l'area di lavoro congedo e assenza fornisce un framework flessibile per la creazione di nuovi piani di congedo, flussi di lavoro per la gestione delle richieste e una pagina self-service intuitiva per consentire ai dipendenti di richiedere i permessi.
author: andreabichsel
manager: AnnBe
ms.date: 06/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: LeavePlanFormPart, LeaveAbsenceWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: ec72d2d741f7f8428a7daa97bb982e9fc00b8c3f
ms.sourcegitcommit: ba340f836e472f13f263dec46a49847c788fca44
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "3428969"
---
# <a name="overview"></a>Panoramica

Dynamics 365 Human Resources consente di fornire importanti benefit di congedo ai propri lavoratori. L'area di lavoro **Congedo e assenza** fornisce un framework flessibile per la creazione di nuovi piani di congedo, flussi di lavoro per la gestione delle richieste e una pagina self-service intuitiva per consentire ai dipendenti di richiedere permessi. Analytics aiuta l'organizzazione a misurare e monitorare i saldi delle ferie e l'utilizzo dei piani ferie.

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

- [Richiedere un permesso](hr-employee-self-service-request-time-off.md)
- [Gestire le richieste di congedo e assenza](hr-employee-self-service-manage-requests.md)

## <a name="leave-and-absence-known-issues"></a>Problemi noti di congedo e assenza

### <a name="rounding-precision"></a>Precisione di arrotondamento

Non è possibile impostare la **Precisione di arrotondamento** quando si imposta **Tipo di arrotondamento**. È possibile impostare la **Precisione di arrotondamento** usando l'entità **Tipi di congedo e assenza**. 

1. Da **Tipi di congedo e assenze**, selezionare **Apri in Excel** per aprire l'entità **Congedo e tipo di assenza**.

2. Dopo l'apertura e l'attivazione del file, selezionare **Progetta**.

3. Sulla tabella **Tipo di congedo e assenza**, selezionare l'opzione con la matita per modificare.

4. Selezionare **RoundingPrecision** e **RoundingType**, quindi selezionare **Inserisci** per aggiungere all'elenco dei campi.

5. Selezionare **Aggiorna** e quindi **Fatto**.

6. Immettere o selezionare il **Tipo di arrotondamento** per ogni tipo di congedo se non è già stato impostato. 

7. Inserire la **Precisione di arrotondamento** per i tipi appropriati.

8. Selezionare **Pubblica** per inviare le modifiche in Human Resources.

## <a name="leave-and-absence-preview-features"></a>Funzionalità di anteprima di Congedo e assenza

È possibile provare le nuove funzionalità di anteprima di Congedo e assenza in un ambiente **Sandbox**. Per informazioni su come attivare le funzionalità di anteprima, vedere [Gestire le funzionalità](hr-admin-manage-features.md). 

[!include [banner](includes/preview-feature.md)]

Le funzionalità di anteprima includono:

- **Accumulo di congedi per società o piano** - È possibile eseguire il processo di accumulo per tutte le società o per una singola società. È inoltre possibile eseguire il processo di accumulo per un piano di congedo e assenza specifico per una società specifica. 

- **Acquista congedi** - È possibile abilitare e creare criteri di acquisto di congedi per dipendenti per inviare richieste di acquisto. I dipendenti possono inviare richieste di acquisto e aggiornare automaticamente i saldi per riflettere la richiesta.  

- **Aggiungi allegati a richieste di congedo approvate** - È possibile aggiungere un allegato a una richiesta di congedo già approvata. 

