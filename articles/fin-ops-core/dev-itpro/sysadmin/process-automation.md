---
title: Automazione del processo
description: Questo argomento fornisce dettagli su come l'automazione dei processi consente una semplice pianificazione dei processi che verranno eseguiti dal server batch.
author: RyanCCarlson2
ms.date: 04/20/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ProcessScheduleSeries
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: rcarlson
ms.search.validFrom: 2020-06-30
ms.dyn365.ops.version: AX 10.0.11
ms.openlocfilehash: a8722adfe410f15bc379f9b550f0618c881f067d
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/20/2021
ms.locfileid: "5920831"
---
# <a name="process-automation"></a>Automazione del processo

[!include[banner](../includes/banner.md)]

L'automazione dei processi consente una semplice pianificazione dei processi che verranno eseguiti dal server batch. La visualizzazione calendario aggiornata del lavoro pianificato consente agli utenti finali di visualizzare e agire sul lavoro programmato e completato.

## <a name="administration"></a>Amministrazione sistema

La pagina di amministrazione centrale per tutte le automazioni di processo si trova nel modulo Amministrazione di sistema nel menu **Impostazione**. Questa pagina elencherà tutti i processi automatizzati (serie) impostati nel sistema. Consentirà anche di aggiungere nuove automazioni di processo direttamente da questa pagina. Dopo aver impostato una serie, è possibile gestire ogni serie da questo elenco. È possibile scegliere di modificare l'intera serie, eliminarla, visualizzare tutte le occorrenze in una vista elenco o disabilitare la serie se si desidera sospendere il lavoro pianificato per un periodo di tempo. 

Tutti i processi disabilitati nella gestione delle funzionalità non verranno visualizzati quando la funzionalità è disabilitata. Inoltre, il motore di pianificazione dell'automazione dei processi non pianificherà alcuna occorrenza o processo in background per una funzione disabilitata. La riattivazione della funzione provocherà l'esecuzione immediata di eventuali ricorrenze pianificate o processi in background precedenti. Il motore di pianificazione dell'automazione del processo si basa sull'esecuzione del processo batch di sistema, **Processo di sistema polling automazione processo**. Il processo non deve essere alterato o manomesso in nessun momento. 

## <a name="calendar-view"></a>Visualizzazione calendario

Uno dei principali vantaggi dell'automazione di processo è la capacità di vedere il lavoro pianificato in una semplice vista del calendario.  Questa vista ti consente di vedere il lavoro per una settimana alla volta. Vedrai questa vista sul lato destro della pagina **Automazione processo**. Verrà popolata con il lavoro pianificato per le serie selezionate. 

[![Calendario di automazione del processo](./media/CalendarView2.png)](./media/CalendarView2.png)

## <a name="occurrence-changes"></a>Modifiche alle occorrenze

Ogni occorrenza può essere modificata senza influire su altre occorrenze definite dalle serie che le hanno originate. Le occorrenze di lavoro pianificato possono essere modificate dalla vista del calendario selezionando il pulsante **Visualizza/Modifica** e selezionando **Occorrenza**. Questa pagina consente di accedere a tutte le impostazioni originariamente mostrate nella procedura guidata di configurazione della serie e offre la possibilità di apportare una modifica una tantum per l'occorrenza selezionata. Un'occorrenza di lavoro pianificato può anche essere disattivata selezionando il pulsante **Disabilita** dalla vista del calendario.

## <a name="developer-documentation"></a>Documentazione sviluppatori

Il framework di automazione dei processi consente agli sviluppatori di estendere il framework di automazione dei processi. La documentazione relativa al [framework di automazione dei processi](../process-automation/process-automation-framework.md) fornisce informazioni su come è possibile creare processi personalizzati che devono essere eseguiti dal server batch pianificato con la procedura guidata di automazione dei processi e visualizzati automaticamente nella vista del calendario.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
