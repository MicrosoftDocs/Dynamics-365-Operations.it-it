---
title: Calendari fiscali, anni fiscali e periodi
description: In questo articolo vengono illustrati calendari fiscali, anni fiscali e periodi e il modo in cui utilizzarli per le persone giuridiche, i cespiti e l'impostazione del budget.
author: aprilolson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: FiscalCalendars
audience: Application User
ms.reviewer: robinr
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 25851
ms.assetid: a968a5e5-585e-4389-aa4e-c885a7e23413
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 22a08b1b9e819f5c683d278f37bf3404e757d200
ms.contentlocale: it-it
ms.lasthandoff: 05/25/2017

---

# <a name="fiscal-calendars-fiscal-years-and-periods"></a>Calendari fiscali, anni fiscali e periodi

[!include[banner](../includes/banner.md)]


In questo articolo vengono illustrati calendari fiscali, anni fiscali e periodi e il modo in cui utilizzarli per le persone giuridiche, i cespiti e l'impostazione del budget.

I calendari fiscali forniscono una struttura per l'attività finanziaria di un'organizzazione. Ogni calendario fiscale contiene uno o più anni fiscali e ogni anno fiscale contiene più periodi. I calendari fiscali possono essere basati su un anno di calendario dal 1° gennaio al 31 dicembre o su date selezionate. Alcune organizzazioni selezionano, ad esempio, un calendario fiscale che inizia il 1° luglio di un anno e termina il 30 giugno dell'anno successivo. 

Non esiste un limite al numero di calendari fiscali che è possibile creare o al numero di anni fiscali che possono essere creati per un calendario fiscale. Ogni calendario fiscale è indipendente dall'organizzazione e può essere utilizzato da più persone giuridiche all'interno dell'organizzazione. Un'organizzazione, ad esempio, è composta da otto reparti e ogni reparto è una persona giuridica distinta. Cinque di esse condividono lo stesso calendario fiscale e tre utilizzano calendari fiscali diversi. È possibile creare un unico calendario fiscale per le cinque persone giuridiche che condividono lo stesso calendario fiscale e quindi creare calendari fiscali separati per le altre persone giuridiche.

## <a name="create-fiscal-calendars-fiscal-years-and-periods"></a>Creare calendari fiscali, anni fiscali e periodi
È possibile creare ed eliminare calendari fiscali, anni fiscali e periodi nella pagina Calendari fiscali. È inoltre possibile dividere periodi esistenti e creare periodi di chiusura che possono essere utilizzati per chiudere un anno fiscale. 

Un periodo di chiusura viene utilizzato per separare le transazioni di contabilità generale generate alla chiusura di un anno fiscale. Quando le transazioni di chiusura fanno parte di un unico periodo fiscale, è più semplice creare rendiconti finanziari che includono o escludono i diversi tipi di movimenti di chiusura. Se un anno fiscale è suddiviso in 12 periodi fiscali, il periodo di chiusura è in genere il 13° periodo. Tuttavia, è possibile creare un periodo di chiusura da qualsiasi periodo il cui stato sia Aperto. 

Quando si crea un periodo di chiusura, selezionare un periodo con stato Aperto e con le date che si desidera utilizzare. Il nuovo periodo di chiusura copierà le date di inizio e di fine dal periodo esistente. Il periodo originale continuerà a esistere. Selezionare ad esempio il Periodo 12, ovvero l'ultimo periodo dell'anno fiscale, le cui date vanno dal 1 agosto al 31 agosto. Immettere il nome del periodo di chiusura, ad esempio Chiuso. Dopo aver creato il nuovo periodo di chiusura, si avranno sia il periodo originale che quello di chiusura. In entrambi la data di inizio sarà il 1° agosto e la data di fine il 31 agosto.

## <a name="select-fiscal-calendars-for-ledgers-fixed-assets-and-budget-cycles"></a>Selezionare i calendari fiscali per le contabilità generali, i cespiti e i cicli di budget
I calendari fiscali vengono utilizzati con l'ammortamento cespiti, le transazioni finanziarie e i cicli di budget. Quando si crea un calendario fiscale è possibile utilizzarlo per più scopi. È possibile selezionare un calendario fiscale per un modello di valore o un registro beni ammortizzabili e utilizzarlo come calendario cespiti. È possibile selezionare un calendario fiscale per la contabilità generale e utilizzarlo come calendario contabilità generale. È inoltre possibile selezionare un calendario fiscale per un ciclo di budget e utilizzarlo come calendario di budget. È possibile utilizzare lo stesso calendario fiscale per tutti questi scopi.

### <a name="select-a-fiscal-calendar-for-your-legal-entity"></a>Selezionare un calendario fiscale per la persona giuridica

Selezionare il calendario fiscale da utilizzare per la contabilità generale della persona giuridica nel modulo Contabilità generale. È necessario selezionare un calendario fiscale nella pagina Contabilità generale per ogni persona giuridica. Dopo aver selezionato un calendario fiscale, nella pagina Calendario contabilità generale è possibile impostare gli stati e le autorizzazioni dei periodi che fanno parte di un anno fiscale.

### <a name="select-a-fiscal-calendar-for-fixed-assets"></a>Selezionare un calendario fiscale per i cespiti

È possibile selezionare un calendario fiscale per un modello di valore o un registro beni ammortizzabili e tale calendario verrà utilizzato dai cespiti che utilizzano il modello di valore o il registro beni ammortizzabili selezionato. È possibile effettuare la selezione tra tutti i calendari fiscali definiti nella pagina Calendari fiscali.

### <a name="define-budget-cycle-time-spans"></a>Definire gli intervalli di durata del ciclo di budget

I cicli di budget sono periodi di tempo durante i quali viene utilizzato un budget. I cicli di budget possono includere parte di un anno fiscale o più anni fiscali, ad esempio un ciclo di budget biennale di due anni o un ciclo di budget triennale di tre anni. La durata del ciclo di budget definisce il numero di periodi inclusi nel ciclo di budget. Per specificare la durata del ciclo di budget, utilizzare la pagina Durata ciclo di budget.

## <a name="maintain-periods-for-your-organization"></a>Gestire i periodi per l'organizzazione
È possibile utilizzare la pagina Calendario contabilità generale per visualizzare i dettagli del calendario fiscale, gli anni fiscali e i periodi utilizzati dall'organizzazione. È inoltre possibile modificare lo stato dei periodi e selezionare gli utenti che possono registrare transazioni contabili nei periodi. È possibile ad esempio che all'inizio di un nuovo periodo un gruppo utenti debba concludere la registrazione di transazioni finanziarie nel periodo precedente, mentre altri gruppi debbano gestire solo il nuovo periodo.






