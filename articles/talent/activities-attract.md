---
title: Aggiungere attività a un processo di assunzione
description: Di seguito vengono descritti i vari tipi di attività che si possono aggiungere a un processo di assunzione in Microsoft Dynamics 365 Talent - Attract.
author: hasrivas
manager: AnnBe
ms.date: 05/28/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: shielas
ms.search.validFrom: 2018-10-15
ms.dyn365.ops.version: Talent October 2018 update
ms.openlocfilehash: ce8c0bd74a41b9857538b37d0875583d06e8c11d
ms.sourcegitcommit: 1d5a4f70a931e78b06811add97c1962e8d93689b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/13/2020
ms.locfileid: "3124775"
---
# <a name="add-activities-to-a-hiring-process"></a>Aggiungere attività a un processo di assunzione

[!include [banner](includes/banner.md)]

Le attività è possibile aggiungere come parte del processo di assunzione in Microsoft Dynamics 365 Talent: Attract. Le attività possono essere aggiunte a un modello di processo, oppure possono essere aggiunte direttamente al processo di assunzione nella mansione. Quando viene definita una mansione, viene selezionato un modello di processo e le attività incluse nel modello verranno applicati al mansione. Se un modello non è selezionata, il modello predefinito viene utilizzato. Il processo di assunzione può anche essere modificato nella mansione dopo che il modello è applicato.

> [!NOTE] 
> I modelli di processo sono disponibili con il componente aggiuntivo per l'assunzione a livello globale. Per ulteriori informazioni, vedere [Quale versione di Microsoft Dynamics 365 Talent - Attract](./attract-comprehensive-hiring.md).

## <a name="prospect-activity"></a>Attività per prospect

L'attività di prospect controlla se i prospect possano essere aggiunte a una mansione. Per impostazione predefinita, i prospect possono essere aggiunte a una mansione. Per disattivare l'attività di prospect, impostare l'opzione **Abilita candidato** su **Disattivato**. Quando l'attività di prospect abilitata, i responsabili delle assunzioni possono aggiungere e visualizzare i prospect e la scheda **Candidato** viene visualizzata nella mansione.

> [!NOTE]
> Per consentire ai candidati da aggiungere a un processo da LinkedIn, è necessario impostare l'opzione **Abilita prospect** **Il**.

## <a name="application-activity"></a>Attività per domande di lavoro

L'attività per domande di lavoro è necessaria nel modello di processo di assunzione. Per inviare messaggi di posta elettronica ai candidati quando presentano la domanda di lavoro o vengono aggiunti alla fase domanda di lavoro, impostare l'opzione **Invia messaggio di posta elettronica al candidato** su **Attivato**.

## <a name="interview-schedule-and-feedback-activity"></a>Attività di programmazione e riscontro del colloquio

Questa attività ha tre componenti: Richiedi disponibilità candidato, Programmazione e Riscontro. Utilizzare l'attività di colloquio nel modello posizioni lavorative se si desidera includere la richiesta di disponibilità del candidato, la programmazione e il riscontro durante il processo anziché utilizzarle singolarmente durante il processo di assunzione. Per ulteriori informazioni, vedere [Programmazione e riscontro del colloquio](interview-scheduling-feedback.md).

## <a name="power-apps-activity"></a>Attività Power Apps

L'attività Power Apps consente di incorporare un'app Microsoft Power Apps nel processo di assunzione. Il app può essere necessaria per tutti i candidati, solo candidati interni, solo i candidati esterni o per nessun candidato. Se il app viene contrassegnato come obbligatoria, deve essere completata prima procedere con la fase. Per essere considerato completo, il campo **JobApplicationStatus** deve essere impostato su **Completo**. Questo campo si trova nell'entità JobApplicationActivity, quindi l'app di Power Apps dovrà aggiornare questo campo affinché la fase possa procedere. Se il app non viene contrassegnato come obbligatoria, l'attività è un passaggio facoltativo e la fase può procedere anche se il app non viene completata.

Per salvare l'attività Power Apps nel processo di assunzione, è necessario immettere un ID Power Apps. Per trovare l'ID Power Apps, passare a [Power Apps](https://web.powerapps.com), selezionare **App**, quindi selezionare **Dettagli**.

Per impostazione predefinita, l'attività di Power Apps è disponibile per il responsabile delle assunzioni, il selezionatore e i rispettivi delegati. Se si seleziona l'opzione **Consenti aggiunta di partecipanti per l'attività**, i partecipanti supplementari del team di assunzione possono essere aggiunti per un'applicazione che utilizza l'attività Power Apps. Ad esempio, un'organizzazione ha creato un app di Power Apps che è una raccolta delle domande nei colloqui per i ruoli tecnici. L'organizzazione sta assumendo ora un nuovo sviluppatore software e ha aggiunto l'attività Power Apps al processo di assunzione per il ruolo di sviluppatore software. Se l'opzione **Consenti aggiunta di partecipanti per l'attività** è selezionata, un selezionatore o un responsabile delle assunzioni che sta esaminando un candidato per il ruolo Sviluppatore software può aggiungere responsabili del colloquio all'attività Power Apps. Queste persone possono quindi visualizzare il app con le domande del colloquio.

> [!NOTE]
> L'attività Power Apps è disponibile solo con il componente aggiuntivo per l'assunzione a livello globale. Per ulteriori informazioni, vedere [Quale versione di Microsoft Dynamics 365 Talent - Attract](./attract-comprehensive-hiring.md).

## <a name="youtube-activity"></a>Attività YouTube

L'attività YouTube consente di condividere un video YouTube come parte del processo di assunzione. Per salvare l'attività YouTube nel processo di assunzione, è necessario specificare l'URL del video di YouTube. È possibile scegliere di visualizzare il contenuto per **Team di assunzione**, **Candidati solo interni**, **Candidati esterni solo** oppure **Tutti i candidati**. Come per l'attività Power Apps, è possibile consentire l'aggiunta dei partecipanti del team di assunzione all'attività. Se si sceglie di rendere visibile il contenuto ai candidati, il video viene visualizzato solo come parte dell'esperienza del candidato e non nel processo di assunzione.

> [!NOTE]
> L'attività YouTube è disponibile solo con il componente aggiuntivo per l'assunzione a livello globale. Per ulteriori informazioni, vedere [Quale versione di Microsoft Dynamics 365 Talent - Attract](./attract-comprehensive-hiring.md).

## <a name="web-content-activity"></a>Attività contenuto Web

L'attività contenuto Web consente di includere contenuto online nel processo di assunzione. Per salvare l'attività contenuto Web nel processo di assunzione, è necessario specificare l'URL del contenuto. È possibile scegliere di visualizzare il contenuto per **Team di assunzione**, **Candidati solo interni**, **Candidati esterni solo** oppure **Tutti i candidati**. Come per le attività Power Apps e YouTube, è possibile consentire l'aggiunta dei partecipanti del team di assunzione all'attività. Se si sceglie di rendere visibile il contenuto ai candidati, il contenuto Web viene visualizzato solo come parte dell'esperienza del candidato e non nel processo di assunzione. È possibile scegliere le dimensioni del contenuto mostrato.

> [!NOTE]
> L'attività contenuto Web è disponibile solo con il componente aggiuntivo per l'assunzione a livello globale. Per ulteriori informazioni, vedere [Quale versione di Microsoft Dynamics 365 Talent - Attract](./attract-comprehensive-hiring.md).

## <a name="microsoft-forms-activity"></a>Attività Microsoft Forms

L'attività Microsoft Forms consente di incorporare un'attività di Microsoft Forms nel processo di assunzione. Microsoft Forms consente di creare quiz e sondaggi. Per salvare l'attività Microsoft Forms nel processo di assunzione, è necessario specificare l'URL del modulo. È possibile scegliere di visualizzare il contenuto per **Team di assunzione**, **Candidati solo interni**, **Candidati esterni solo** oppure **Tutti i candidati**. Come per le attività Power Apps, YouTube e contenuto Web è possibile consentire l'aggiunta dei partecipanti del team di assunzione all'attività. Se si sceglie di rendere visibile il contenuto ai candidati, il modulo viene visualizzato solo come parte dell'esperienza del candidato e non nel processo di assunzione.

In Microsoft Forms, gli autori possono modificare le relative impostazioni per consentire agli utenti esterni alla propria organizzazione di rispondere al sondaggio o al quiz. In questo caso, gli utenti inviano le risposte in modo anonimo. Se si desidera visualizzare chi ha compilato il sondaggio o il quiz, è possibile richiedere che gli intervistati immettano il nome come parte del sondaggio o quiz.

> [!NOTE]
> L'attività Microsoft Forms è disponibile solo con il componente aggiuntivo per l'assunzione a livello globale. Per ulteriori informazioni, vedere [Quale versione di Microsoft Dynamics 365 Talent - Attract](./attract-comprehensive-hiring.md).

## <a name="offer-activity"></a>Attività Offerta

Il modello del processo di assunzione richiede l'attività Offerta. Per utilizzare l'app Offer Management integrata, impostare **Avvia l'app Offer Management per la preparazione dell'offerta** su **Attivato**. Se questa impostazione è disattivata, il candidato non verrà visualizzato nell'app Offer, quindi sarà necessario tenere traccia degli aggiornamenti all'attività Offerta di un candidato manualmente. Per definire se i responsabili delle assunzioni possono preparare l'offerta per il candidato nell'app Offer, impostare **I responsabili delle assunzioni possono preparare l'offerta** su **Attivato**. Se la mansione ha più posizioni ad essa associate, è possibile decidere se si desidera preparare più offerte per lo stesso numero di posizione. Se si desidera consentire una sola offerta per posizione per mansione, impostare **Consenti alle posizioni di essere riutilizzate** su **Disattivato**.

> [!NOTE]
> L'app Offer Management integrata è disponibile solo con il componente aggiuntivo per l'assunzione a livello globale. Per ulteriori informazioni, vedere [Quale versione di Microsoft Dynamics 365 Talent - Attract](./attract-comprehensive-hiring.md).


