---
title: Chiusura in massa del periodo fiscale
description: In questo articolo viene illustrato come mettere in sospeso un periodo o chiudere in modo permanente un periodo o più di una persona giuridica alla volta.
author: aprilolson
ms.date: 11/16/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerCalendar, LedgerPeriodModuleAccessControlUpdate, SysLookupPicklist, LedgerFiscalCalendarPeriodStatus
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8a85d512842b27f2d74507be16a8f2819f483e0d
ms.sourcegitcommit: cf6b764824bd1cf2c0dde6d37ddd0a7abab87ff0
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/16/2022
ms.locfileid: "9779828"
---
# <a name="mass-financial-period-close"></a>Chiusura in massa del periodo fiscale

[!include [banner](../../includes/banner.md)]

In questo articolo viene illustrato come mettere in sospeso un periodo o chiudere in modo permanente un periodo o più di una persona giuridica alla volta. Inoltre, l'attività mostrerà come limitare a moduli specifici la registrazione del gruppo utenti.

1. Nel pannello di navigazione, andare a **Contabilità generale > Periodo chiuso > Calendari contabilità generale**. 

>[!NOTE]
> L'elenco delle persone giuridiche visualizzato dipende dal calendario fiscale selezionato nella pagina. Solo le persone giuridiche che usano il calendario fiscale selezionato vengono visualizzate.

2. Selezionare **Modifica**.
3. Selezionare il periodo per cui si desidera modificare lo stato.
4. Selezionare le persone giuridiche per cui si desidera aggiornare lo stato. È possibile selezionare rapidamente tutte le persone giuridiche selezionando il segno di spunta sul lato in alto a sinistra della griglia.  
5. Selezionare **Aggiorna accesso al modulo** per definire l'accesso di registrazione a un modulo selezionato. Stato del modulo può anche essere aggiornato uno a uno modificando i record nella griglia. Il pulsante è utile se si desidera aggiornare rapidamente i record di più persone giuridiche.  
6. Nel campo **Modulo applicazione** selezionare il modulo di cui si desidera aggiornare lo stato. Fare clic su **Seleziona**.
7. In **Livello di accesso**, selezionare **Tutti**, **Nessuno** o un gruppo utenti specifico. Fare clic su **Seleziona**.  
- **Tutti**: tutti gli utenti con accesso in modifica nel modulo possono registrare se il periodo è aperto. 
- **Nessuno**: gli utenti non possono registrare nel modulo se il periodo è aperto. Un gruppo di utenti specifico indica che solo gli utenti nel gruppo possono effettuare registrazioni nel modulo se il periodo è aperto.  
8. Seleziona **Aggiorna**. 
9. Selezionare un altro periodo per aggiornare lo stato.
10. Selezionare le persone giuridiche per cui si desidera aggiornare lo stato del periodo.
11. Selezionare **Aggiorna stato periodo** e impostare lo stato su **In attesa**, **Aperto** o **Chiuso in modo permanente**. **Aperto** indica che è possibile registrare nel periodo, se l'utente ha accesso. **In attesa** significa che il periodo non può essere registrato, ma il periodo può essere riaperto. **Chiuso in modo permanente** significa che il periodo è chiuso e non può mai essere aperto. Non possono essere registrate rettifiche. Non si consiglia di impostare un periodo su **Chiuso in modo permanente** fino a che tutte le rettifiche e i controlli sono completi.  
12. Selezionare **Aggiornamento**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
