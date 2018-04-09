---
title: Home page di amministrazione organizzazione
description: Sono indicate le risorse che consentono di utilizzare Microsoft Dynamics 365 for Finance and Operations nell'organizzazione.
author: sericks007
manager: AnnBe
ms.date: 08/18/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 20421
ms.assetid: 7aa24a03-d172-47e9-81f8-ebd39e80bc60
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: a2c1d846527eac4db0a043c7f1c51da0e73bd796
ms.contentlocale: it-it
ms.lasthandoff: 03/26/2018

---

# <a name="organization-administration-home-page"></a>Home page di amministrazione organizzazione

[!include[banner](../includes/banner.md)]


Questo argomento descrive le risorse che power user e amministratori possono utilizzare per configurare Microsoft Dynamics 365 for Finance and Operations. Tali risorse consentono di configurare efficacemente il sistema per l'organizzazione e l'attività commerciale.

La maggior parte del contenuto qui elencato si applica alle funzionalità del modulo **Amministrazione organizzazione**. Un paio di attività, ad esempio la creazione e l'uso di un modello di record, sono tuttavia eseguibili in qualsiasi modulo per consentire una gestione ancor più efficace dell'organizzazione. 

<a name="number-sequences"></a>Sequenze numeriche
----------------
Le sequenze numeriche vengono utilizzate per generare identificatori univoci leggibili per record transazioni e dati master che richiedono identificatori. Un record transazioni o dati master che richiede un identificatore viene definito *riferimento*. Prima di poter creare nuovi record per un riferimento, è necessario impostare una sequenza numerica e associarla al riferimento.

-   [Panoramica delle sequenze numeriche](number-sequence-overview.md)
-   [Impostazione guidata sequenze numeriche](tasks/set-up-number-sequences-wizard.md) (guida attività)
-   [Impostare sequenze numeriche singole](tasks/set-up-number-sequences-individual-basis.md) (guida attività)

## <a name="organizations"></a>Organizzazioni
Un'organizzazione è un gruppo di persone che collaborano per svolgere un processo aziendale o raggiungere un obiettivo. Le gerarchie organizzative rappresentano i rapporti tra le organizzazioni che fanno parte dell'azienda.

Prima di impostare le organizzazioni e le gerarchie organizzative in Finance and Operations, assicurarsi di pianificare il modo in cui l'azienda verrà modellata. Il modello di organizzazione ha un effetto significativo sull'implementazione di Finance and Operations e sui processi aziendali.

-   [Organizzazioni e gerarchie organizzative](organizations-organizational-hierarchies.md)
-   [Pianificazione della gerarchia organizzativa](plan-organizational-hierarchy.md)
-   [Creare una gerarchia organizzativa](tasks/create-organization-hierarchy.md) (guida attività)
-   [Creare una persona giuridica](tasks/create-legal-entity.md) (guida attività)
-   [Creare un'unità operativa](tasks/create-operating-unit.md) (guida attività)

## <a name="address-books"></a>Rubriche
La rubrica globale è un archivio centralizzato per dati master che devono essere archiviati per tutte le persone e organizzazioni interne ed esterne con cui la società interagisce. I dati associati ai record della parte includono il nome, l'indirizzo e le informazioni di contatto della parte. 

Dopo aver creato la Rubrica globale, è possibile creare Rubriche aggiuntive in base alle esigenze, ad esempio una Rubrica separata per ogni società nell'organizzazione o per ogni linea di business. 

-   [Rubrica globale](overview-global-address-book.md)
-   [Pianificare la modalità di configurazione della rubrica globale e di rubriche aggiuntive](plan-configuration-global-address-book-additional-address-books.md)
- [Configurare la rubrica globale](tasks/configure-global-address-book.md)
-   [Domande frequenti sulla rubrica](qa-address-books.md)


## <a name="workflow"></a>Workflow
Workflow è un sistema installato con Finance and Operations che consente di creare singoli flussi di lavoro o processi aziendali. Quando si crea un flusso di lavoro, si definisce il modo in cui un documento attraversa il sistema, o si sposta allinterno dello stesso, identificando chi deve completare un'attività, prendere una decisione o approvare un documento. 

-   [Panoramica del flusso di lavoro](overview-workflow-system.md)
-   [Elementi del flusso di lavoro](workflow-elements.md)
-   [Azioni flusso di lavoro](workflow-actions.md)
-   [Creare un flusso di lavoro](create-workflow.md)

## <a name="electronic-signatures"></a>Firme elettroniche
Una firma elettronica consente di confermare l'identità di una persona che sta per avviare o approvare un processo di elaborazione. In alcuni settori una firma elettronica è considerata legalmente vincolante come una firma manuale. Le firme elettroniche rappresentano un requisito di legge per diversi settori regolamentati, tra cui quello farmaceutico, quello alimentare e quello aerospaziale e della difesa.

In Finance and Operations è possibile utilizzare le firme elettroniche per i processi aziendali critici. In alcuni processi sono disponibili funzionalità di firma elettronica incorporate. È inoltre possibile creare requisiti di firma personalizzati per qualsiasi tabella o campo di database.

-   [Panoramica delle firme elettroniche](electronic-signature-overview.md)
-   [Impostare firme elettroniche](tasks/set-up-electronic-signatures.md) (guida attività)

## <a name="case-management"></a>Gestione casi
Grazie alla pianificazione, alla tracciabilità e all'analisi dei casi è possibile sviluppare soluzioni efficienti da poter utilizzare per problemi simili. Quando ad esempio i rappresentanti dell'assistenza clienti o gli specialisti delle risorse umane creano un caso, possono trovare nei file di caratteristiche del caso informazioni utili per gestire e risolvere il caso in modo più efficiente. 

-   [Panoramica della gestione casi](cases.md)
-   [Configurare la sicurezza, i processi e le categorie dei casi](plan-case-management.md)

## <a name="record-templates"></a>Modelli di record
I modelli di record possono risultare utili per creare più rapidamente i record. È possibile creare un modello di record in modo che non sia necessario inserire in modo esplicito per ogni nuovo record i valori dei campi che vengono utilizzati più spesso. 

-   [Modelli record](record-templates.md)
- [Creare un modello di record per facilitare l'immissione dei dati](../../dev-itpro/data-entities/tasks/create-record-template-facilitate-data-entry.md) (Guida attività)
- [Utilizzare un modello di record per creare un nuovo record](../../dev-itpro/data-entities/tasks/use-record-template-new-record.md) (guida attività)

## <a name="general-organization-administration"></a>Amministrazione organizzazione generale
-   [Modificare il banner o il logo](../get-started/tasks/change-banner-or-logo.md) (guida attività)
- [Configurare la gestione dei documenti](configure-document-management.md)
- [Configurare e inviare messaggi di posta elettronica](configure-email.md)
-   [Dati di data/ora e fusi orari](date-time-zones.md)








