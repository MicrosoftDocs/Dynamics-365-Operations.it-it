---
title: Attività nei processi
description: Di seguito vengono descritti i vari tipi di attività da utilizzare nel processo di assunzione.
author: hasrivas
manager: AnnBe
ms.date: 04/10/2019
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
ms.openlocfilehash: c975b95e4195c795ec4c816b1f3a50461715feea
ms.sourcegitcommit: 9796d022a8abf5c07abcdee6852ee34f06d2eb57
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/12/2019
ms.locfileid: "989916"
---
# <a name="activities-in-the-hiring-processes"></a>Attività nei processi di assunzione

[!include[banner](../includes/banner.md)]

Le attività è possibile aggiungere come parte del processo di assunzione in Microsoft Dynamics 365 for Talent: Attract. Le attività possono essere aggiunte a un modello di processo, oppure possono essere aggiunte direttamente al processo di assunzione nella mansione. Quando viene definita una mansione, viene selezionato un modello di processo e le attività incluse nel modello verranno applicati al mansione. Se un modello non è selezionata, il modello predefinito viene utilizzato. Il processo di assunzione può anche essere modificato nella mansione dopo che il modello è applicato.

> [!NOTE] 
> I modelli di processo sono disponibili con il componente aggiuntivo per l'assunzione a livello globale. Per ulteriori informazioni, vedere [Attract con componente aggiuntivo per l'assunzione a livello globale](./attract-comprehensive-hiring.md)

## <a name="prospect-activity"></a>Attività per prospect

L'attività di prospect controlla se i prospect possano essere aggiunte a una mansione. Per impostazione predefinita, i prospect possono essere aggiunte a una mansione. Per disattivare l'attività di prospect, impostare l'opzione **Abilita candidato** su **Disattivato**. Quando l'attività di prospect abilitata, i responsabili delle assunzioni possono aggiungere e visualizzare i prospect e la scheda **Candidato** viene visualizzata nella mansione.

## <a name="application-activity"></a>Attività per domande di lavoro

L'attività per domande di lavoro è necessaria nel modello di processo di assunzione. Per inviare messaggi di posta elettronica ai candidati quando presentano la domanda di lavoro o vengono aggiunti alla fase domanda di lavoro, impostare l'opzione **Invia messaggio di posta elettronica al candidato** su **Attivato**.

## <a name="interview-schedule-and-feedback-activity"></a>Attività di programmazione e riscontro del colloquio

Questa attività ha tre componenti: Richiedi disponibilità candidato, Programmazione e Riscontro. Utilizzare l'attività di colloquio nel modello posizioni lavorative se si desidera includere la richiesta di disponibilità del candidato, la programmazione e il riscontro durante il processo anziché utilizzarle singolarmente durante il processo di assunzione. Per ulteriori informazioni, vedere [Programmazione e riscontro del colloquio](interview-scheduling-feedback.md).

## <a name="powerapps-activity"></a>Attività PowerApps

L'attività PowerApps consente di incorporare un'app Microsoft PowerApps nel processo di assunzione. Il app può essere necessaria per tutti i candidati, solo candidati interni, solo i candidati esterni o per nessun candidato. Se il app viene contrassegnato come obbligatoria, deve essere completata prima procedere con la fase. Per essere considerato completo, il campo **JobApplicationStatus** deve essere impostato su **Completo**. Questo campo si trova nell'entità JobApplicationActivity, quindi l'app di PowerApps dovrà aggiornare questo campo affinché la fase possa procedere. Se il app non viene contrassegnato come obbligatoria, l'attività è un passaggio facoltativo e la fase può procedere anche se il app non viene completata.

Per salvare l'attività PowerApps nel processo di assunzione, è necessario immettere un ID PowerApps. Per trovare l'ID PowerApps, passare a [PowerApps](https://web.powerapps.com), selezionare **App**, quindi selezionare **Dettagli**.

Per impostazione predefinita, l'attività di PowerApps è disponibile per il responsabile delle assunzioni, il selezionatore e i rispettivi delegati. Se si seleziona l'opzione **Consenti aggiunta di partecipanti per l'attività**, i partecipanti supplementari del team di assunzione possono essere aggiunti per un'applicazione che utilizza l'attività PowerApps. Ad esempio, un'organizzazione ha creato un app di PowerApps che è una raccolta delle domande nei colloqui per i ruoli tecnici. L'organizzazione sta assumendo ora un nuovo sviluppatore software e ha aggiunto l'attività PowerApps al processo di assunzione per il ruolo di sviluppatore software. Se l'opzione **Consenti aggiunta di partecipanti per l'attività** è selezionata, un selezionatore o un responsabile delle assunzioni che sta esaminando un candidato per il ruolo Sviluppatore software può aggiungere responsabili del colloquio all'attività PowerApps. Queste persone possono quindi visualizzare il app con le domande del colloquio.

> [!NOTE]
> L'attività PowerApps è disponibile solo con il componente aggiuntivo per l'assunzione a livello globale. Per ulteriori informazioni, vedere [Attract con componente aggiuntivo per l'assunzione a livello globale](./attract-comprehensive-hiring.md)

## <a name="youtube-activity"></a>Attività YouTube

L'attività YouTube consente di condividere un video YouTube come parte del processo di assunzione. Per salvare l'attività YouTube nel processo di assunzione, è necessario specificare l'URL del video di YouTube. È possibile scegliere di visualizzare il contenuto per **Team di assunzione**, **Candidati solo interni**, **Candidati esterni solo** oppure **Tutti i candidati**. Come per l'attività PowerApps, è possibile consentire l'aggiunta dei partecipanti del team di assunzione all'attività. Se si sceglie di rendere visibile il contenuto ai candidati, il video viene visualizzato solo come parte dell'esperienza del candidato e non nel processo di assunzione.

> [!NOTE]
> L'attività YouTube è disponibile solo con il componente aggiuntivo per l'assunzione a livello globale. Per ulteriori informazioni, vedere [Attract con componente aggiuntivo per l'assunzione a livello globale](./attract-comprehensive-hiring.md)

## <a name="web-content-activity"></a>Attività contenuto Web

L'attività contenuto Web consente di includere contenuto online nel processo di assunzione. Per salvare l'attività contenuto Web nel processo di assunzione, è necessario specificare l'URL del contenuto. È possibile scegliere di visualizzare il contenuto per **Team di assunzione**, **Candidati solo interni**, **Candidati esterni solo** oppure **Tutti i candidati**. Come per l'attività PowerApps e YouTube, è possibile consentire l'aggiunta dei partecipanti del team di assunzione all'attività. Se si sceglie di rendere visibile il contenuto ai candidati, il contenuto Web viene visualizzato solo come parte dell'esperienza del candidato e non nel processo di assunzione. È possibile scegliere le dimensioni del contenuto mostrato.

> [!NOTE]
> L'attività contenuto Web è disponibile solo con il componente aggiuntivo per l'assunzione a livello globale. Per ulteriori informazioni, vedere [Attract con componente aggiuntivo per l'assunzione a livello globale](./attract-comprehensive-hiring.md)

## <a name="microsoft-forms-activity"></a>Attività Microsoft Forms

L'attività Microsoft Forms consente di incorporare un'attività di Microsoft Forms nel processo di assunzione. Microsoft Forms consente di creare quiz e sondaggi. Per salvare l'attività Microsoft Forms nel processo di assunzione, è necessario specificare l'URL del modulo. È possibile scegliere di visualizzare il contenuto per **Team di assunzione**, **Candidati solo interni**, **Candidati esterni solo** oppure **Tutti i candidati**. Come per l'attività PowerApps? YouTube e contenuto Web è possibile consentire l'aggiunta dei partecipanti del team di assunzione all'attività. Se si sceglie di rendere visibile il contenuto ai candidati, il modulo viene visualizzato solo come parte dell'esperienza del candidato e non nel processo di assunzione.

In Microsoft Forms, gli autori possono modificare le relative impostazioni per consentire agli utenti esterni alla propria organizzazione di rispondere al sondaggio o al quiz. In questo caso, gli utenti inviano le risposte in modo anonimo. Se si desidera visualizzare chi ha compilato il sondaggio o il quiz, è possibile richiedere che gli intervistati immettano il nome come parte del sondaggio o quiz.

> [!NOTE]
> L'attività Microsoft Forms è disponibile solo con il componente aggiuntivo per l'assunzione a livello globale. Per ulteriori informazioni, vedere [Attract con componente aggiuntivo per l'assunzione a livello globale](./attract-comprehensive-hiring.md)

## <a name="offer-activity"></a>Attività Offerta

Il modello del processo di assunzione richiede l'attività Offerta. Per utilizzare l'app Offer Management integrata, impostare **Avvia l'app Offer Management per la preparazione dell'offerta** su **Attivato**. Se questa impostazione è disattivata, il candidato non verrà visualizzato nell'app Offer, quindi sarà necessario tenere traccia degli aggiornamenti all'attività Offerta di un candidato manualmente. Per definire se i responsabili delle assunzioni possono preparare l'offerta per il candidato nell'app Offer, impostare **I responsabili delle assunzioni possono preparare l'offerta** su **Attivato**. Se la mansione ha più posizioni ad essa associate, è possibile decidere se si desidera preparare più offerte per lo stesso numero di posizione. Se si desidera consentire una sola offerta per posizione per mansione, impostare **Consenti alle posizioni di essere riutilizzate** su **Disattivato**.

> [!NOTE]
> L'app Offer Management integrata è disponibile solo con il componente aggiuntivo per l'assunzione a livello globale. Per ulteriori informazioni, vedere [Attract con componente aggiuntivo per l'assunzione a livello globale](./attract-comprehensive-hiring.md)


