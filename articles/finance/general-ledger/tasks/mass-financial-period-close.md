---
title: Chiusura in massa del periodo fiscale
description: In questo argomento viene illustrato come mettere in sospeso un periodo o chiudere in modo permanente un periodo o più di una persona giuridica alla volta.
author: aprilolson
manager: AnnBe
ms.date: 08/16/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerCalendar, LedgerPeriodModuleAccessControlUpdate, SysLookupPicklist, LedgerFiscalCalendarPeriodStatus
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4db0f68a22f9129041c7a7c081f397c34c2b07eb
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5254441"
---
# <a name="mass-financial-period-close"></a>Chiusura in massa del periodo fiscale

[!include [banner](../../includes/banner.md)]

In questo argomento viene illustrato come mettere in sospeso un periodo o chiudere in modo permanente un periodo o più di una persona giuridica alla volta. Inoltre, l'attività mostrerà come limitare a moduli specifici la registrazione del gruppo utenti.

1. Nel pannello di navigazione, andare a **Moduli > Contabilità generale > Periodo chiuso > Calendari contabilità generale**. Tenere presente che l'elenco delle persone giuridiche visualizzato dipende dal calendario fiscale selezionato nella pagina. Solo le persone giuridiche che usano il calendario fiscale selezionato vengono visualizzate.
2. Selezionare **Modifica**.
3. Selezionare il periodo per cui si desidera modificare lo stato.
4. Selezionare le persone giuridiche per cui si desidera aggiornare lo stato. È possibile selezionare rapidamente tutte le persone giuridiche selezionando il segno di spunta sul lato in alto a sinistra della griglia.  
5. Selezionare **Aggiorna accesso al modulo** per definire l'accesso di registrazione a un modulo selezionato. Stato del modulo può anche essere aggiornato uno a uno modificando i record nella griglia. Il pulsante è utile se si desidera aggiornare rapidamente i record di più persone giuridiche.  
6. Nel campo **Modulo applicazione** selezionare il modulo di cui si desidera aggiornare lo stato. Fare clic su **Seleziona**.
7. In **Livello di accesso**, selezionare **Tutti**, **Nessuno** o un gruppo utenti specifico. Fare clic su **Seleziona**. Tutti indica che tutti gli utenti con accesso in modifica nel modulo possono registrare se il periodo è aperto. Nessuno indica che gli utente non possono registrare nel modulo se il periodo è aperto. Un gruppo di utenti specifico indica che solo gli utenti nel gruppo possono effettuare registrazioni nel modulo se il periodo è aperto.  
8. Selezionare **Aggiornamento**.
9. Selezionare un altro periodo per aggiornare lo stato.
10. Selezionare le persone giuridiche per cui si desidera aggiornare lo stato del periodo.
11. Selezionare **Aggiorna stato periodo** e impostare lo stato su **In attesa**, **Aperto** o **Chiuso in modo permanente**. **Aperto** indica che è possibile registrare nel periodo, se l'utente ha accesso. **In attesa** significa che il periodo non può essere registrato, ma il periodo può essere riaperto. **Chiuso in modo permanente** significa che il periodo è chiuso e non può mai essere aperto. Non possono essere registrate rettifiche. Non si consiglia di impostare un periodo su **Chiuso in modo permanente** fino a che tutte le rettifiche e i controlli sono completi.  
12. Selezionare **Aggiornamento**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]