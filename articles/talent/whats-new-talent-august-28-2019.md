---
title: Novità e modifiche in Dynamics 365 for Talent (27 agosto 2019)
description: Questo argomento descrive le funzionalità nuove o modificate di Microsoft Dynamics 365 for Talent.
author: Darinkramer
manager: AnnBe
ms.date: 8/27/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: andreabichsel
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2019-08-27
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 8965636e539345be5ef0ad591f7017938efd322d
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/17/2020
ms.locfileid: "4529806"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-august-27-2019"></a>Novità e modifiche in Dynamics 365 for Talent (27 agosto 2019)

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Questo argomento descrive le funzionalità nuove o modificate in Dynamics 365 for Talent.

## <a name="changes-in-attract"></a>Modifiche in Attract

Questa versione include correzioni di bug minori per Dynamics 365 Talent: Attract.

## <a name="changes-in-onboard"></a>Modifiche in Onboard

Questa versione include correzioni di bug minori per Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Modifiche di Core HR

Le modifiche descritte in questo sezione sono valide per la build numero 8.1.2447. I numeri tra parentesi in alcune intestazioni si riferiscono ai numeri del supporto in Microsoft Dynamics Lifecycle Services (LCS).

### <a name="preview-features-are-enabled-only-in-sandbox-instances"></a>Le funzionalità di anteprima vengono attivate solo nelle istanze sandbox

Quando si esegue il provisioning di una nuova istanza di Talent, è possibile specificare se il tipo di istanza è Produzione o Sandbox. Le istanze Sandbox consentono di testare tle nuove funzionalità prima dell'utilizzo. Tutte le istanze Talent esistenti verranno aggiornate al tipo di istanza di produzione. Se si desidera aggiornare una delle istanze esistenti al tipo di istanza Sandbox, contattare il supporto tecnico per avviare la richiesta di modifica.

Per ulteriori informazioni su come vengono pubblicate le modifiche, vedere [Eseguire il provisioning di Talent](./provisioning-talent.md).

### <a name="view-extended-information-for-performance-in-manager-self-service"></a>Visualizzare informazioni estese per le prestazioni in Responsabile self-service

Una nuova opzione consentirà ai responsabili di visualizzare le prestazioni dei report diretti ed estesi. Attualmente, i responsabili linea possono assegnare e aggiornare obiettivi prestazionali e pubblicare nuove revisioni. Inoltre, i responsabili diretti e i relativi dipendenti possono gestire e aggiornare giornali di registrazione prestazioni per garantire la corretta esecuzione del processo di valutazione delle prestazioni. Una volta questa modifica implementata, i responsabili potranno visualizzare e gestire informazioni relative alle prestazioni per i report estesi oltre che per quelli diretti.

### <a name="deleting-legal-entities-isnt-allowed-if-employees-exist-within-the-company-339849"></a>L'eliminazione di persone giuridiche non è consentita se nell'azienda sono presenti dipendenti (339849)

Con questa modifica, non è possibile rimuovere o eliminare società se per quella persona giuridica sono presenti dipendenti e altri dati correlati.

### <a name="compensation-management-business-intelligence-analytics-dont-match-on-the-compensation-workspace-322493"></a>L'analisi dei dati di business intelligence per la gestione delle retribuzioni non corrisponde all'area di lavoro della retribuzione (322493)

In questa versione, l'analisi dei dati delle retribuzioni è stata rettificata in modo da riflettere con precisione i piani assegnati ai dipendenti.

### <a name="workflow-placeholder-company-displays-dat-when-hiring-employees-through-workflow-343905"></a>Il segnaposto dell'area di lavoro %società% visualizza DAT quando si assumono dipendenti attraverso il flusso di lavoro (343905)

In questa versione, il segnaposto società visualizza la persona giuridica associata all'impiego del nuovo dipendente.

### <a name="the-cdsjobposition-entity-displays-an-error-when-valid-to-date-is-set-349387"></a>L'entità CDSJobPosition visualizza un errore quando viene impostata una data di fine validità (349387)

In questa versione, le origini dati **Dettagli posizione** e **Durata posizione** nell'entità **CDSJobPosition** consentono modifiche da Common Data Service ai campi **Data valida**. 

### <a name="for-employee-termination-the-last-day-worked-is-populated-on-assignment-end-date-332496"></a>Per il fine rapporto del dipendente, l'ultimo giorno lavorato viene visualizzato nella data di fine assegnazione (332496)

Questa modifica determina l'impostazione della **Data di fine assegnazione** sul valore predefinito **Data di fine impiego**. È possibile modificare queste impostazioni predefinite mentre di immettono i dati.

### <a name="legal-entities-arent-limited-with-hire-338871"></a>Le persone giuridiche non vengono limitate con l'assunzione (338871)
 
Questa modifica limita il processo di assunzione in modo che vengano visualizzate solo le persone giuridiche a cui si ha accesso.  

## <a name="in-preview"></a>In anteprima

### <a name="streamlined-employee-entry-and-navigation"></a>Inserimento e navigazione dei dipendenti semplificati

Questa funzionalità è ora disponibile negli ambienti sandbox e di prova. Per attivare questa funzionalità, passare ad **Amministrazione sistema > Collegamenti > Impostazioni > Parametri di sistema > Funzionalità di anteprima**. Selezionare **Navigazione e modulo lavoratore avanzati**. In questo modo le modifiche sono valide per tutti gli utenti. È possibile disattivare questa opzione in qualsiasi momento.

Per ulteriori informazioni, vedere [Inserimento e navigazione dei dipendenti semplificati](./streamlined-employee-entry.md).

## <a name="coming-soon"></a>Presto disponibili

### <a name="platform-update-29"></a>Update 29 della piattaforma

Per ulteriori dettagli sull'aggiornamento 29 della piattaforma, vedere [Funzionalità di anteprima nell'aggiornamento 29 della piattaforma Dynamics 365 for Finance and Operations (ottobre 2019)](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/whats-new-platform-update-29).
