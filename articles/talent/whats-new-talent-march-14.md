---
title: Novità o modifiche in Dynamics 365 for Talent (14 marzo 2019)
description: Questo argomento descrive le funzionalità nuove o modificate di Microsoft Dynamics 365 for Talent.
author: Darinkramer
manager: AnnBe
ms.date: 03/14/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2019-03-14
ms.dyn365.ops.version: Talent
ms.openlocfilehash: ee8e076174acba8e706991f3086d6299a10945ec
ms.sourcegitcommit: 45f8cea6ac75bd2f4187380546a201c056072c59
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/12/2019
ms.locfileid: "1742495"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-march-14-2019"></a>Novità o modifiche in Dynamics 365 for Talent (14 marzo 2019)

[!include [banner](includes/banner.md)]

Questo argomento descrive le funzionalità nuove o modificate di Talent.

## <a name="changes-in-attract"></a>Modifiche in Attract
Questa versione include correzioni di bug minori.

## <a name="changes-in-onboarding"></a>Modifiche in Onboard
Questa versione include correzioni di bug minori.

## <a name="changes-in-core-hr"></a>Modifiche di Core HR
**Build 8.1.2186**

### <a name="performance-management-not-working-in-all-scenarios-when-using-duplicate-security-roles"></a>La gestione delle prestazioni non funziona in tutti gli scenari quando si utilizzano ruoli di sicurezza duplicati
Le modifiche apportate in questa versione abilitano gli scenari di gestione delle prestazioni quando si utilizzano ruoli predefiniti o duplicati.

### <a name="mass-assign-checklists-to-workers"></a>Assegnazione di massa di elenchi di controllo ai lavoratori
Con questa modifica, è ora possibile selezionare più dipendenti ed eseguire l'assegnazione di massa di uno o più elenchi di controllo a tali dipendenti. 

### <a name="platform-update-24"></a>Update 24 della piattaforma
Per ulteriori informazioni sull'aggiornamento 24 della piattaforma, vedere [Novità o modifiche nell'aggiornamento 24 della piattaforma Finance and Operations (marzo 2019)](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/whats-new-platform-update-24). Modifiche significative nella piattaforma 24 includono: 

- Gli avvisi sono abilitati in Talent.
- La barra di navigazione aggiornata ora è allineata all'intestazione di Office.

### <a name="office-location-update-switches-the-context-to-the-top-of-the-worker-list"></a>L'aggiornamento di un'ubicazione ufficio sposta il contesto nella parte superiore dell'elenco dei lavoratori
Con la versione corrente, la modifica dell'ubicazione ufficio non sposterà il contesto del lavoratore che si sta esaminando quando si assegna un ubicazione ufficio.

### <a name="position-assignment-end-date-doesnt-display-correctly-on-worker-hire-and-transfer-actions"></a>La data di fine dell'assegnazione della posizione non viene visualizzata correttamente nelle azioni di assunzione e trasferimento dei lavoratori
Le date di fine dell'assegnazione della posizione sono ora visualizzate correttamente in base al fuso orario preferito dell'utente quando si utilizzano le azioni.

### <a name="common-data-service-job-entity-doesnt-allow-job-type-and-job-function-fields-to-update"></a>L'entità mansione di Common Data Service non consente l'aggiornamento dei campi Tipo di mansione e Funzione lavorativa
Le entità Common Data Service ora vengono sincronizzate correttamente quando sono aggiornate utilizzando Common Data Service.

## <a name="coming-soon"></a>Presto disponibili

###  <a name="advanced-compensation-security-fixed-and-variable"></a>Protezione retribuzione avanzata (fissa e variabile)
In molte organizzazioni, i responsabili delle retribuzioni e dei benefit potrebbero accedere solo a determinati record di retribuzione. Questi record potrebbero essere per dirigenti o dipendenti regionali. Con questa modifica, le Risorse umane possono gestire i piani di retribuzione per differenti gruppi di dipendenti nell'organizzazione. È possibile assegnare ruoli di sicurezza a piani fissi e variabili che determinano l'accesso ai piani e ai dati dei dipendenti correlati ai piani, ad esempio record di stipendi o premi. Solo i ruoli con l'accesso concesso possono elaborare la retribuzione per quei dipendenti.

###  <a name="email-support-for-alerts"></a>Supporto di messaggi di posta elettronica per avvisi
Grazie all'aggiornamento 24 della piattaforma, gli utenti possono creare regole di avviso che inviano automaticamente notifiche tramite posta elettronica ai contatti quando avviate da un evento.

### <a name="duplicate-employee-check-interface-changes"></a>Verifica di dipendenti duplicati: modifiche dell'interfaccia
Con questa modifica, i duplicati vengono rilevati durante l'immissione nei campi Nome e uno stato indica quanti ne sono stati trovati. È possibile selezionare il collegamento fornito per aprire una nuova pagina e valutare se utilizzare la corrispondenza rilevata. Il modulo Duplicati non si apre automaticamente per non interrompere l'immissione dei dati.
