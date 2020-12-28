---
title: Novità o modifiche in Dynamics 365 Talent (16 aprile 2019)
description: Questo argomento descrive le funzionalità nuove o modificate di Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 04/16/2019
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
ms.search.validFrom: 2019-04-16
ms.dyn365.ops.version: Talent
ms.openlocfilehash: d9802848c90b2b1c8d5e3cb3280dfa6ebc948ff2
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/17/2020
ms.locfileid: "4527182"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-april-16-2019"></a>Novità o modifiche in Dynamics 365 Talent (16 aprile 2019)

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Questo argomento descrive le funzionalità nuove o modificate in Dynamics 365 Talent.

## <a name="changes-in-attract"></a>Modifiche in Attract

### <a name="process-auditing"></a>Controllo dei processi

Ora è possibile tenere traccia delle modifiche apportate ai candidati, alle posizioni di lavoro o alle domande di lavoro. Per ulteriori informazioni, vedere [Utilizzare le modifiche ai dati del personale](process-auditing.md).

## <a name="changes-in-onboard"></a>Modifiche in Onboard

Questa versione include correzioni di bug minori per Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Modifiche di Core HR

Le modifiche descritte in questo sezione sono valide per la build numero 8.1.2239. I numeri tra parentesi in alcune intestazioni si riferiscono ai numeri del supporto in Lifecycle Services (LCS).

### <a name="compensation-region-compensation-level-benefit-option-and-skill-type-entities-in-common-data-service-updated-to-include-customer-field-support"></a>Le entità di paese di retribuzione, livello retributivo, opzione di benefit e tipo di competenza di Common Data Service sono state aggiornate per includere il supporto del campo del cliente

In questa versione, queste entità di Common Data Service sono state aggiornate con la possibilità di includere il campo personalizzato aggiunto tramite Talent: Core HR.

### <a name="powerbi-refresh-issues-314342"></a>Problemi di aggiornamento di PowerBI (314342)

Questa modifica corregge un problema con i report PowerBI che si aggiornano correttamente.

### <a name="unable-to-click-directly-through-on-transition-tasks-in-employee-self-service-303309"></a>Impossibile fare clic direttamente sulle attività di transizione nel Self Service dipendenti (303309)

Questa modifica consente agli utenti con il ruolo di dipendente di selezionare e aggiornare le attività di transizione dall'elenco di cose da fare di Talent.

### <a name="performance-feedback-email-message-updated-309615"></a>Messaggio email di feedback sulle prestazioni aggiornato (309615)

Con questa modifica, viene visualizzato un messaggio di conferma quando il feedback viene inviato correttamente.

### <a name="missing-tables-in-word-template-308048"></a>Tabelle mancanti nel modello di Word (308048)

Con questa modifica, quando si crea un modello di Word con informazioni su dipendenti e competenze, nel documento di Word vengono visualizzate solo le competenze per il dipendente selezionato.

### <a name="when-applying-an-offboarding-checklist-an-error-is-displayed-299877"></a>Quando si applica un elenco di controllo di offboarding viene visualizzato un errore. (299877)

Questa modifica corregge un problema quando si applicano un elenco di controllo di offboarding direttamente dal modulo del lavoratore.

## <a name="in-preview"></a>In anteprima

### <a name="allow-reason-codes-to-be-specified-on-leave-types"></a>Consentire la specifica dei codici motivo nei tipi di congedo

Le organizzazioni potrebbero necessitare di informazioni aggiuntive sulle richieste di permesso. Ora è possibile specificare i codici motivo per i tipi di congedo e consentire ai dipendenti di selezionare un codice motivo nelle relative richieste di permesso.

### <a name="require-reason-codes-for-certain-leave-types-on-time-off-requests"></a>Richiedere codici motivo per alcuni tipi di congedo nelle richieste di permesso

Le organizzazioni potrebbero richiedere codici motivo per determinati tipi di congedo quando i dipendenti inviano richieste di permesso. Ciò potrebbe essere dovuto ai criteri o ai requisiti normativi della società. Ora è possibile specificare quali tipi di congedo richiedono un codice motivo ed è possibile richiedere ai dipendenti di fornire un codice motivo per il tipo di congedo nelle relative richieste di permesso.

### <a name="provide-leave-and-absence-transaction-list-for-hr"></a>Fornire un elenco di transazioni assenze e congedo per le Risorse umane

La tracciabilità del tempo libero dei dipendenti e la comprensione di come tale tempo viene calcolato non solo consente alle Risorse umane di rispondere alle domande dei dipendenti, ma anche di garantire premi appropriati per il tempo libero dei dipendenti. Ora le Risorse umane hanno una nuova visibilità sulle transazioni (concessioni, accumuli, rettifiche e richieste) per determinare i motivi dei saldi.

## <a name="coming-soon"></a>Presto disponibili

### <a name="improvements-to-the-user-interface-for-duplicate-employee-check"></a>Miglioramenti all'interfaccia utente per la verifica di dipendenti duplicati

Con questa modifica, i duplicati vengono rilevati durante l'immissione nei campi Nome e uno stato indica il numero di duplicati trovati. È possibile selezionare il collegamento fornito per aprire una nuova pagina e valutare se utilizzare la corrispondenza rilevata. Per evitare di interrompere l'immissione di dati, il modulo Duplicati non viene aperto automaticamente.

### <a name="email-support-for-alerts"></a>Supporto di messaggi di posta elettronica per avvisi

Con l'aggiornamento 25 della piattaforma per Finance and Operations, gli utenti possono creare regole di avviso che inviano automaticamente notifiche di posta elettronica ai contatti quando avviate da un evento.


