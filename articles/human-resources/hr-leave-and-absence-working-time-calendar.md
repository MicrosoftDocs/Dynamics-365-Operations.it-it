---
title: Creare un calendario orario di lavoro
description: Definire un calendario orario di lavoro, festività e orari non lavorativi in Dynamics 365 Human Resources.
author: twheeloc
ms.date: 10/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LeavePlanFormPart, LeaveAbsenceWorkspace
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: dac3ad583be9e4cbd6eacbc6d228819bd298628b
ms.sourcegitcommit: 66d129874635d34a8b29c57762ecf1564e4dc233
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/23/2022
ms.locfileid: "9323575"
---
# <a name="create-a-working-time-calendar"></a>Creare un calendario orario di lavoro


[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Un calendario orario di lavoro in Dynamics 365 Human Resources mostra i giorni e le ore in cui i dipendenti lavorano nell'organizzazione. Quando un dipendente invia una richiesta di permesso, non deve preoccuparsi di festività e chiusure.

Per semplificare le richieste di permesso, configurare questi elementi per l'organizzazione:

- Calendario orario di lavoro
- Festività e chiusure
- Orario non lavorativo

È possibile aggiungere gli ultimi due elementi mentre si imposta un calendario orario di lavoro. È anche possibile configurarli o aggiornarli separatamente.

## <a name="set-up-a-working-time-calendar"></a>Impostare un calendario orario di lavoro

Impostare almeno un calendario orario di lavoro che mostri i giorni e le ore di lavoro. Se si hanno ubicazioni in più paesi e aree geografiche, è possibile che si intenda impostare un calendario orario di lavoro per ogni area.

1. Nella pagina **Amministrazione organizzazione** selezionare **Calendari**.

2. Selezionare **Nuovo** e immettere un nome e una descrizione per il calendario.

3. Sotto **Opzioni di generazione**, selezionare i giorni lavorativi dell'organizzazione e immettere gli orari di lavoro. 
   - Per aggiungere una festività o una chiusura, selezionare il pulsante **Aggiungi** accanto a **Festività e chiusure**.
   - Per aggiungere un orario non lavorativo, come i pranzi o le pause, selezionare **Aggiungi** sotto **Orario non lavorativo** e immettere il nome e l'intervallo di tempo.

4. Sotto **Giorni** selezionare **Genera** per generare i giorni nel calendario. Immettere l'intervallo di date per il calendario e quindi selezionare **Genera giorni**.

5. Per aggiungere programmi di lavoro, in **Programma lavori**, selezionare **Aggiungi** e quindi immettere gli orari per ogni programma.

## <a name="configure-holidays-and-closures"></a>Configurare festività e chiusure

È possibile aggiungere o modificare festività e chiusure separatamente da un calendario orario di lavoro.

1. Nella pagina **Amministrazione organizzazione** selezionare **Festività e chiusure**.

2. Selezionare **Nuovo** e immettere una data per la festività o la chiusura.

## <a name="configure-non-work-time"></a>Configurare orari non lavorativi

È possibile aggiungere o modificare orari non lavorativi separatamente da un calendario orario di lavoro.

1. Nella pagina **Amministrazione organizzazione** selezionare **Orario non lavorativo**.

2. Selezionare **Nuovo** e immettere un nome e la fascia oraria per l'orario non lavorativo.

Se la funzionalità di anteprima per la correzione di giorni festivi di Congedo e assenza è stata abilitata, Human Resources utilizza le date di festività e chiusura per determinare il numero di giorni da rettificare per i dipendenti iscritti al calendario.

## <a name="see-also"></a>Vedere anche

- [Panoramica di congedo e assenza](hr-leave-and-absence-overview.md)
- [Configurare tipi di congedo e assenza](hr-leave-and-absence-types.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
