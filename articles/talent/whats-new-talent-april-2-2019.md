---
title: Novità o modifiche in Dynamics 365 Talent (2 aprile 2019)
description: Questo argomento descrive le funzionalità nuove o modificate di Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 04/02/2019
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
ms.search.validFrom: 2019-04-02
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 86d81d60fcbc77375f3b8c525e8c084e3a3d8a99
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/06/2019
ms.locfileid: "2773695"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-april-2-2019"></a>Novità o modifiche in Dynamics 365 Talent (2 aprile 2019)

[!include [banner](includes/banner.md)]

Questo argomento descrive le funzionalità nuove o modificate in Dynamics 365 Talent.

## <a name="changes-in-attract"></a>Modifiche in Attract

### <a name="approval-emails-in-attract"></a>Messaggi di posta elettronica di approvazione in Attract
Nuovi messaggi di posta elettronica di approvazione migliorano la visibilità nel processo di approvazione. I messaggi di posta elettronica sono inviati agli approvatori quando si verifica uno degli scenari seguenti:

- Il richiedente invia un processo per l'approvazione.
- Un processo viene approvato o rifiutato.
- Un approvatore non risponde a una richiesta di approvazione entro 24 ore.

È possibile personalizzare il contenuto dei messaggi di posta elettronica di approvazione con nuovi modelli.

### <a name="application-and-profile-attachments"></a>Allegati di profili e domande di lavoro
Grazie a miglioramenti alla scheda **Documenti** delle domande di lavoro e dei profili del pool di talenti, ora è possibile visualizzare il nome e il tipo di documento.

## <a name="changes-in-onboard"></a>Modifiche in Onboard
Questa versione include correzioni di bug minori per Dynamics 365 Talent: Onboard.

## <a name="coming-soon-attract-and-onboard"></a>Presto disponibili (Attract e Onboard)

### <a name="lifecycle-services-lcs-integration-with-report-a-problem"></a>Integrazione di Lifecycle Services (LCS) con Segnala un problema
In Attract and Onboard, i problemi segnalati dagli utenti finali mediante la funzionalità Segnala un problema ora generano automaticamente problemi per il supporto tecnico nel progetto LCS del cliente. Gli amministratori possono quindi valutare i problemi e inviarli a Microsoft quando necessario. Ciò è coerente con il modo in cui Core HR gestisce i problemi segnalati dagli utenti finali.

## <a name="changes-in-core-hr"></a>Modifiche di Core HR
Le modifiche descritte in questo sezione sono valide per la build numero 8.1.2216.

### <a name="platform-update-25-for-finance-and-operations"></a>Aggiornamento 25 della piattaforma per Finance and Operations
Per ulteriori informazioni sull'aggiornamento 25 della piattaforma per Finance and Operations, vedere [Funzionalità di anteprima nell'aggiornamento 25 della piattaforma Dynamics 365 for Finance and Operations (aprile 2019)](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/whats-new-platform-25).

###  <a name="advanced-compensation-security-fixed-and-variable"></a>Protezione retribuzione avanzata (fissa e variabile)
In molte organizzazioni, i responsabili delle retribuzioni e dei benefit potrebbero avere accesso solo a determinati record di retribuzione. Questi potrebbero includere record per dirigenti o dipendenti regionali. Questa modifica consente alle Risorse umane di gestire i piani di retribuzione per differenti gruppi di dipendenti nell'organizzazione. È possibile assegnare ruoli di sicurezza a piani fissi e variabili. Questi ruoli di sicurezza determinano l'accesso a piani e ai dati dei dipendenti correlati, quali record di stipendi e premi, di modo che solo quei ruoli possano elaborare la retribuzione per i gruppi di dipendenti.

### <a name="upgrade-to-common-data-service"></a>Aggiornamento a Common Data Service
Le scadenze per l'aggiornamento a Common Data Service sono imminenti. Accedere all'interfaccia di amministrazione Microsoft Power Apps per determinare se il database deve essere aggiornato. Per ulteriori informazioni sulle scadenze e sui passaggi necessari per eseguire l'aggiornamento, vedere [Aggiornamento di Common Data Service](https://docs.microsoft.com/common-data-service/upgradecds/introduction-upgrade-cds).

## <a name="in-preview"></a>In anteprima

### <a name="allow-reason-codes-to-be-specified-on-leave-types"></a>Consentire la specifica dei codici motivo nei tipi di congedo
Le organizzazioni potrebbero necessitare di informazioni aggiuntive sulle richieste di permesso. Ora è possibile specificare i codici motivo per i tipi di congedo e consentire ai dipendenti di selezionare un codice motivo nelle relative richieste di permesso.

### <a name="require-reason-codes-for-certain-leave-types-on-time-off-requests"></a>Richiedere codici motivo per alcuni tipi di congedo nelle richieste di permesso
Le organizzazioni potrebbero richiedere codici motivo per determinati tipi di congedo quando i dipendenti inviano richieste di permesso. Ciò potrebbe essere dovuto ai criteri o ai requisiti normativi della società. Ora è possibile specificare quali tipi di congedo richiedono un codice motivo ed è possibile richiedere ai dipendenti di fornire un codice motivo per il tipo di congedo nelle relative richieste di permesso.

## <a name="coming-soon"></a>Presto disponibili

### <a name="improvements-to-the-user-interface-for-duplicate-employee-check"></a>Miglioramenti all'interfaccia utente per la verifica di dipendenti duplicati
Con questa modifica, i duplicati vengono rilevati durante l'immissione nei campi Nome e uno stato indica il numero di duplicati trovati. È possibile selezionare il collegamento fornito per aprire una nuova pagina e valutare se utilizzare la corrispondenza rilevata. Per evitare di interrompere l'immissione di dati, il modulo Duplicati non viene aperto automaticamente.

###  <a name="email-support-for-alerts"></a>Supporto di messaggi di posta elettronica per avvisi
Con l'aggiornamento 25 della piattaforma per Finance and Operations, gli utenti possono creare regole di avviso che inviano automaticamente notifiche di posta elettronica ai contatti quando le notifiche sono attivate da un evento. 
