---
title: "Novità o modifiche in Dynamics 365 for Talent Core HR (10 settembre 2018)"
description: "Questo argomento descrive le funzionalità nuove o modificate di Microsoft Dynamics 365 for Talent Core HR."
author: Darinkramer
manager: AnnBe
ms.date: 09/12/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
ms.search.form: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2018-09-06
ms.dyn365.ops.version: Talent September 10, 2018 update
ms.translationtype: HT
ms.sourcegitcommit: 7d4a049a44374276655dce696b5bbbe2e6f9fba9
ms.openlocfilehash: b41ce93c8ae93054d2b0d71340b99e0910d4510f
ms.contentlocale: it-it
ms.lasthandoff: 10/16/2018

---

# <a name="whats-new-or-changed-in-dynamics-365-for-talent-core-hr-september-10-2018"></a>Novità o modifiche in Dynamics 365 for Talent Core HR (10 settembre 2018)

[!include [banner](includes/banner.md)]

**Build 8.1.138.0**

Questo argomento descrive le funzionalità nuove o modificate di Microsoft Dynamics 365 for Talent Core HR.

## <a name="allow-specific-time-of-day-on-time-off-requests-half-days"></a>Consentire tempo specifico per le richieste di permessi (mezze giornate)

Se il Riquadri Dettaglio informazioni è impostato in modo che il permesso sia inviato per giorni, è ora possibile abilitare una definizione di mezza giornata. In seguito, quando gli utenti inviano le richieste di permesso, possono specificare se richiedono un permesso per la prima parte o la seconda parte della giornata.

Per impostazione predefinita, questa opzione è disattivata. Per fare in modo che i dipendenti possano richiedere un permesso per la prima parte o la seconda parte della giornata, è necessario attivare questa opzione nell'area **Congedo e assenza** di Parametri Risorse umane.

Il privilegio di sicurezza per questa funzionalità è Gestisci parametri Risorse umane.

## <a name="validation-of-leave-and-absence-entries"></a>Convalida delle voci di congedo e assenza

A seconda di come è configurato il permesso, i dipendenti che tentano di inviare una richiesta di permesso superiore alla giornata lavorativa ricevono un messaggio di avviso. In altre parole vengono avvisati se tentano di prendere più di un giorno di permesso in una data specifica.

Questa convalida è sempre attivata. Ogni volta che i dipendenti superano la soglia della giornata definita, ricevono un messaggio di avviso nella richiesta di permesso.

## <a name="additional-fields-for-conditional-statements-in-workflows"></a>Campi aggiuntivi per istruzioni condizionali nei flussi di lavoro

Sono stati aggiunti altri campi alle istruzioni condizionali e ai segnaposto per vari flussi di lavoro in Core HR.

Sono stati aggiunti i campi seguenti ai flussi di lavoro di retribuzione, fine rapporto e trasferimento:

- EmploymentType
- LegalEntity
- AdjustedWorkerStartDate
- EmployerNoticeAmount
- EmployerUnitOfNotice
- TransitionDate
- WorkerNoticeAmount
- WorkerStartDate
- WorkerUnitOfNotice
- ProbationEndDate
- Posizione
- Sindacato
- Reparto
- PositionType
- CompLocation
- Funzione
- Mansione
- JobType
- JobFamily
- JobFunction

Sono stati aggiunti i campi seguenti al flusso di lavoro posizione:

- Posizione
- Sindacato
- Reparto
- PositionType
- CompLocation
- Funzione
- Mansione
- JobType
- JobFamily
- JobFunction

I campi nelle istruzioni condizionali e nei segnaposto sono disponibili a tutti gli utenti che hanno accesso per configurare i flussi di lavoro sopra menzionati.

## <a name="navigation-to-attract-from-personnel-management"></a>Passaggio ad Attract dalla gestione del personale

Nella gestione del personale, se Attract non è stato installato, la sezione **Candidati da assumere** indirizza gli utenti a un'introduzione di Attract invece di visualizzare il messaggio "Nessun elemento da visualizzare."

## <a name="other-changes"></a>Altre modifiche

In questa versione sono incluse altre correzioni di bug:

- Quando viene assunto un terzista, la scheda **Retribuzione** non deve essere disponibile nella pagina azione di richiesta.
- Durante il processo di richiesta di fine rapporto, non è possibile continuare fino a quanto non sono stati completati tutti i campi obbligatori.
- Sono stati risolti i problemi relativi all'ordinamento e alla visualizzazione delle date nell'analisi della gestione del personale.
