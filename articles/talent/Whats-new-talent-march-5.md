---
title: Novità o modifiche in Dynamics 365 Talent (5 marzo 2019)
description: Questo argomento descrive le funzionalità nuove o modificate di Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 03/05/2019
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
ms.search.validFrom: 2019-03-05
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 115d7cd3d71eaddce2434cb1939c503d36bccdf8
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/17/2020
ms.locfileid: "4527292"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-march-5-2019"></a>Novità o modifiche in Dynamics 365 Talent (5 marzo 2019)

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Questo argomento descrive le funzionalità nuove o modificate di Talent.

## <a name="changes-in-attract"></a>Modifiche in Attract

### <a name="extending-option-sets-in-attract"></a>Estensione di set di opzioni in Attract

In Attract, molteplici campi sono set di opzioni in Common Data Service. Sono state introdotte nuove funzionalità per l'estensione di set di opzioni, a partire dai campi **Rifiuto**, **Tipo di impiego** e **Tipo di anzianità**.

> [!IMPORTANT]
> La funzionalità di pubblicazione di annunci di lavoro in LinkedIn richiede l'utilizzo dei campi **Tipo di impiego** e **Tipo di anzianità** nella pagina **Dettagli mansione**. I valori predefiniti in questi campi sono supportati da LinkedIn e visualizzati quando l'annuncio viene pubblicato. Se si pubblicano annunci di lavoro in LinkedIn e si modificano i valori del set di opzioni esistente per questi campi, l'annuncio di lavoro verrà comunque pubblicato ma LinkedIn non visualizzerà i valori **Tipo di anzianità** e **Tipo di impiego**.

## <a name="changes-in-onboarding"></a>Modifiche in Onboard

### <a name="private-preview-for-onboard-teams"></a>Anteprima privata per i team Onboard
Ora è possibile condividere e collaborare facilmente sui modelli nell'intera organizzazione. Per ulteriori informazioni, vedere [Procedura consigliate sulla condivisione nell'organizzazione mediante i team Onboard](https://docs.microsoft.com/business-applications-release-notes/April19/dynamics365-talent/onboard/share-best-practices-teams).

### <a name="private-preview-for-assignee-placeholders"></a>Anteprima privata per segnaposto di assegnatari
È possibile arricchire i modelli assegnando attività a ruoli anziché a individui. I ruoli sono quindi assegnati a utenti al momento della creazione della guida. Per ulteriori informazioni, vedere [Semplificare l'amministrazione della guida assegnando attività a ruoli](https://docs.microsoft.com/business-applications-release-notes/April19/dynamics365-talent/onboard/assign-activities-roles).

## <a name="changes-in-core-hr"></a>Modifiche di Core HR
**Build 8.1.2178**

### <a name="configure-workflow-to-auto-approve-or-follow-workflow-when-an-hr-or-line-manager-submits-or-updates-time-off-requests"></a>Configurare il flusso di lavoro per l'approvazione automatica o tenere traccia del flusso di lavoro quando un superiore o un responsabile risorse umane invia o aggiorna le richieste di permesso
Nuove condizioni di flusso di lavoro sono state aggiunte per l'approvazione automatica delle richieste di congedo se inviate dal manager del dipendente o dalle Risorse umane. Un modo di ottenere questa approvazione automatica in un flusso di lavoro è di abilitare un'azione automatica nell'approvazione del flusso di lavoro.

Le condizioni aggiunte includono:

- Inviata da - Utilizzata per valutare l'ID utente di sistema dell'utente che ha inviato la richiesta al flusso di lavoro.
- Inviata per conto di - Utilizzata per valutare se la richiesta di congedo è stata inviata per conto del lavoratore associato alla richiesta.
- Inviata da Risorse umane - Utilizzata per valutare se l'utente di sistema che ha inviato la richiesta al flusso di lavoro ha un ruolo Risorse umane.
- Inviata da Responsabile - Utilizzata per valutare se l'utente che ha inviato la richiesta di congedo al flusso di lavoro è un responsabile gerarchia del lavoratore associato alla richiesta.

### <a name="enable-employee-fixed-compensation-for-future-position-assignments"></a>Attivare la retribuzione fissa dei dipendenti per assegnazioni di posizione future
È tipico per i dipendenti entrare a far parte di un'organizzazione con una data di inizio futura. Questa modifica consente di definire la retribuzione fissa dei dipendenti con assegnazioni di posizione future.

### <a name="position-payroll-fields-are-blank-when-editing-the-position"></a>I campi delle retribuzioni di posizione sono vuoti durante la modifica della posizione
Con questa modifica, quando si richiedono modifiche alle posizioni esistenti, per impostazione predefinita i valori dei campi delle retribuzioni saranno i valori correnti.

### <a name="other-miscellaneous-bug-fixes"></a>Altre correzioni di bug varie
Altre correzioni di bug minori incluse in questa versione.

### <a name="upgrade-to-common-data-service"></a>Eseguire l'aggiornamento a Common Data Service
Le scadenze per l'aggiornamento di Common Data Service sono imminenti. Accedere all'interfaccia di amministrazione Power Apps per determinare se il database deve essere aggiornato. Per ulteriori informazioni sulle scadenze e sui passaggi necessari per eseguire l'aggiornamento, vedere [Aggiornamento di Common Data Service](https://docs.microsoft.com/common-data-service/upgradecds/introduction-upgrade-cds).

## <a name="coming-soon"></a>Presto disponibili

###  <a name="advanced-compensation-security-fixed-and-variable"></a>Protezione retribuzione avanzata (fissa e variabile)
In molte organizzazioni, i responsabili retribuzione e benefit possono accedere solo a determinati record di retribuzione, ad esempio i record di dirigenti o di dipendenti in base all'area geografica. Con questa modifica, è possibile gestire i piani di retribuzione per differenti popolazioni di dipendenti nell'organizzazione. Ai piani fissi e variabili è possibile assegnare ruoli di sicurezza, che determineranno l'accesso ai piani e ai dati dei dipendenti correlati ai piani, ad esempio i record di stipendi o premi. Solo i ruoli con l'accesso potranno elaborare la retribuzione per quei dipendenti.

###  <a name="platform-update-24-for-finance-and-operations"></a>Update 24 della piattaforma per Finance and Operations
Per ulteriori informazioni sull'aggiornamento 24 della piattaforma per Finance and Operations, vedere [Novità o modifiche nell'aggiornamento 24 della piattaforma Finance and Operations (marzo 2019)](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/whats-new-platform-update-24).


[!INCLUDE[footer-include](../includes/footer-banner.md)]