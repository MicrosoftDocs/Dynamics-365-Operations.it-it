---
title: "Attività nei processi"
description: "Di seguito vengono descritti i vari tipi di attività da utilizzare nel processo di assunzione."
author: 
manager: AnnBe
ms.date: 10/15/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
ms.search.form: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: rschloma
ms.search.validFrom: 2018-10-15
ms.dyn365.ops.version: Talent October 2018 update
ms.translationtype: HT
ms.sourcegitcommit: e890e32049e930b70c2d0aac8aa8206ab999418a
ms.openlocfilehash: ccd9e2d0ff1f7fb6825c6823936b4013b3054f5d
ms.contentlocale: it-it
ms.lasthandoff: 10/22/2018

---

# <a name="activities-in-the-hiring-processes"></a>Attività nei processi di assunzione

[!include[banner](../includes/banner.md)]

Le attività è possibile aggiungere come parte del processo di assunzione in  Microsoft Dynamics 365 for Talent - Attract. Le attività possono essere aggiunte a un modello di processo, oppure possono essere aggiunte direttamente al processo di assunzione nella mansione. Quando viene definita una mansione, viene selezionato un modello di processo e le attività incluse nel modello verranno applicati al mansione. Se un modello non è selezionata, il modello predefinito viene utilizzato. Il processo di assunzione può anche essere modificato nella mansione dopo che il modello è applicato.

> [!NOTE] 
> I modelli di processo sono disponibili con il componente aggiuntivo per l'assunzione a livello globale.

## <a name="prospect-activity"></a>Attività per prospect

L'attività di prospect controlla se i prospect possano essere aggiunte a una mansione. Per impostazione predefinita, i prospect possono essere aggiunte a una mansione. Per disattivare l'attività di prospect, impostare l'opzione **Abilita candidato** su **Disattivato**. Quando l'attività di prospect abilitata, i responsabili delle assunzioni possono aggiungere e visualizzare i prospect e la scheda **Candidato** viene visualizzata nella mansione.

## <a name="application-activity"></a>Attività per domande di lavoro

L'attività per domande di lavoro è necessaria nel modello di processo di assunzione. Per inviare messaggi di posta elettronica ai candidati quando presentano la domanda di lavoro o vengono aggiunti alla fase domanda di lavoro, impostare l'opzione **Invia messaggio di posta elettronica al candidato** su **Attivato**.

## <a name="scheduler-activity"></a>Attività programmazione

L'attività programmazione è facoltativa. Questa attività ha due componenti: Disponibilità candidato e Programmazione. Componente Disponibilità candidato consente di utilizzare la posta elettronica per richiedere la disponibilità del candidato. Il componente Programmazione consente di programmare i colloqui con il candidato e il team di assunzione. Nell'attività programmazione, le seguenti opzioni è possibile configurare: **Richiedi disponibilità candidato**, **Riunione online** e **Invia messaggio di posta elettronica al candidato**.

- Per inviare messaggi di posta elettronica ai candidati per richiedere la disponibilità, impostare l'opzione **Richiedi disponibilità candidato** su **Attivato**. Se si imposta su **Disattivato**, questo passaggio non verrà visualizzato nel processo di assunzione nella mansione.
- Per streaming in diretta o teleconferenza utilizzando Skype for Business, impostare il campo **Riunione online** su **Skype for Business**. Il collegamento corretto **Partecipa a riunione Skype** verrà aggiunto nella richiesta di riunione di colloquio inviata ai responsabili del colloquio.
- Per inviare messaggi di posta elettronica ai candidati per finalizzare la programmazione, impostare l'opzione **Invia messaggio di posta elettronica al candidato** su **Attivato**. Se si imposta su **Disattivato**, candidati riceveranno il programma dei colloqui solo quando accedono al portale del candidato.

## <a name="feedback-activity"></a>Attività di riscontro

L'attività di riscontro è facoltativa. Questa attività consente ai partecipanti al colloquio di fornire indicazioni per un candidato. Possono inoltre immettere qualsiasi commento. Se viene attivata l'opzione **Eredita i partecipanti di riscontro dal team di assunzione**, il selezionatore, il responsabile delle assunzioni e quelli del colloquio vengono immessi automaticamente nell'attività di riscontro. Le organizzazioni possono consentire ai responsabili del colloquio di visualizzare il riscontro di altre persone prima di inviare la propria riscontro. Le organizzazioni possono inoltre possibile consentire ai responsabili del colloquio di modificare il riscontro dopo averlo inviato.

## <a name="interview-activity"></a>Attività di colloquio

L'attività di colloquio è facoltativa. Questa attività ha tre componenti: Disponibilità candidato, Programmazione e Riscontro. Componente Disponibilità candidato consente di utilizzare la posta elettronica per richiedere la disponibilità del candidato. Il componente Programmazione consente di programmare i colloqui con il candidato e il team di assunzione. Nell'attività programmazione, le seguenti opzioni è possibile configurare: **Richiedi disponibilità candidato**, **Riunione online** e **Invia messaggio di posta elettronica al candidato**.

- Per inviare messaggi di posta elettronica ai candidati per richiedere la disponibilità, impostare l'opzione **Richiedi disponibilità candidato** su **Attivato**. Se si imposta su **Disattivato**, questo passaggio non verrà visualizzato nel processo di assunzione nella mansione.
- Per streaming in diretta o teleconferenza utilizzando Skype for Business, impostare il campo **Riunione online** su **Skype for Business**. Il collegamento corretto **Partecipa a riunione Skype** verrà aggiunto nella richiesta di riunione di colloquio.
- Per inviare messaggi di posta elettronica ai candidati per finalizzare la programmazione, impostare l'opzione **Invia messaggio di posta elettronica al candidato** su **Attivato**. Se si imposta su **Disattivato**, candidati riceveranno il programma dei colloqui solo quando accedono al portale del candidato.

Nel componente Riscontro le persone forniscono suggerimenti per un candidato. Possono inoltre immettere qualsiasi commento. Se viene attivata l'opzione **Eredita i partecipanti di riscontro dal team di assunzione**, il selezionatore, il responsabile delle assunzioni e quelli del colloquio vengono immessi automaticamente nel componente Riscontro. Le organizzazioni possono consentire ai responsabili del colloquio di visualizzare il riscontro di altre persone prima di inviare la propria riscontro. Le organizzazioni possono inoltre possibile consentire ai responsabili del colloquio di modificare il riscontro dopo averlo inviato.

## <a name="powerapps-activity"></a>Attività PowerApps

L'attività PowerApps consente di incorporare un'app Microsoft PowerApps nel processo di assunzione. Il app può essere necessaria per tutti i candidati, solo candidati interni, solo i candidati esterni o per nessun candidato. Se il app viene contrassegnato come obbligatoria, deve essere completata prima procedere con la fase. Se il app non viene contrassegnato come obbligatoria, l'attività è un passaggio facoltativo e la fase può procedere anche se il app non viene completata.

Per salvare l'attività PowerApps nel processo di assunzione, è necessario immettere un ID PowerApps. Per trovare l'ID PowerApps, passare a [PowerApps](https://web.powerapps.com), selezionare **App**, quindi selezionare **Dettagli**.

Se si seleziona l'opzione **Consenti aggiunta di partecipanti per l'attività**, i contributori aggiuntivi possono essere aggiunti per un'applicazione che utilizza l'attività PowerApps. Ad esempio, un'organizzazione ha creato un app di PowerApps che è una raccolta delle domande nei colloqui per i ruoli tecnici. L'organizzazione sta assumendo ora un nuovo sviluppatore software e ha aggiunto l'attività PowerApps al processo di assunzione per il ruolo di sviluppatore software. Se l'opzione **Consenti aggiunta di partecipanti per l'attività** è selezionata, un selezionatore o un responsabile delle assunzioni che vede un candidato per il ruolo di sviluppatore software può aggiungere persone all'attività PowerApps. Queste persone possono quindi visualizzare il app con le domande del colloquio.

> [!NOTE]
> L'attività PowerApps è disponibile solo con il componente aggiuntivo per l'assunzione a livello globale.

## <a name="youtube-activity"></a>Attività YouTube

L'attività YouTube consente di condividere un video YouTube come parte del processo di assunzione. Per salvare l'attività YouTube nel processo di assunzione, è necessario specificare l'URL del video di YouTube. Come per l'attività PowerApps, è possibile consentire di aggiungere partecipanti all'attività. Se si seleziona l'opzione **Mostra solo al candidato**, il video viene visualizzato solo come parte dell'esperienza del candidato. Non viene visualizzato nel processo di assunzione in Attract.

> [!NOTE]
> L'attività YouTube è disponibile solo con il componente aggiuntivo per l'assunzione a livello globale.

## <a name="web-content-activity"></a>Attività contenuto Web

L'attività contenuto Web consente di includere contenuto online nel processo di assunzione. Per salvare l'attività contenuto Web nel processo di assunzione, è necessario specificare l'URL del contenuto. Come per le attività PowerApps e YouTube, è possibile consentire di aggiungere partecipanti all'attività. Se si seleziona l'opzione **Mostra solo al candidato**, il contenuto viene visualizzato solo come parte dell'esperienza del candidato. Non viene visualizzato nel processo di assunzione in Attract. È possibile selezionare le dimensioni del contenuto mostrato.

> [!NOTE]
> L'attività contenuto Web è disponibile solo con il componente aggiuntivo per l'assunzione a livello globale.

## <a name="microsoft-forms-activity"></a>Attività Microsoft Forms

L'attività Microsoft Forms consente di incorporare un modulo di Microsoft Forms nel processo di assunzione. Microsoft Forms consente di creare quiz e sondaggi. Per salvare l'attività Microsoft Forms nel processo di assunzione, è necessario specificare l'URL del modulo. Come per le attività PowerApps, YouTube e contenuto Web, è possibile consentire di aggiungere partecipanti all'attività. Se si seleziona l'opzione **Mostra solo al candidato**, il modulo viene visualizzato solo come parte dell'esperienza del candidato. Non viene visualizzato nel processo di assunzione in Attract.

In Microsoft Forms, gli autori possono modificare le relative impostazioni per consentire agli utenti esterni alla propria organizzazione di rispondere al sondaggio o al quiz. In questo caso, gli utenti inviano le risposte in modo anonimo. Se si desidera visualizzare chi ha compilato il sondaggio o il quiz, è possibile richiedere che gli intervistati immettano il nome come parte del sondaggio o quiz.

> [!NOTE]
> L'attività Microsoft Forms è disponibile solo con il componente aggiuntivo per l'assunzione a livello globale.

