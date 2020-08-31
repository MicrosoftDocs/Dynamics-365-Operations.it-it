---
title: App Human Resources in Teams
description: Questo argomento introduce l'app Microsoft Dynamics 365 Human Resources in Microsoft Teams.
author: andreabichsel
manager: AnnBe
ms.date: 08/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: FeatureManagementWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-05-18
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 4822cc6560926df878a8b4e9f821b331ede27a8c
ms.sourcegitcommit: 15c68822f4d412bfc609be31b3702f18c81ea0bc
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2020
ms.locfileid: "3666362"
---
# <a name="human-resources-app-in-teams"></a>App Human Resources in Teams

[!include [banner](includes/preview-feature.md)]

L'app Microsoft Dynamics 365 Human Resources in Microsoft Teams consente ai dipendenti di richiedere rapidamente permessi e di visualizzare le informazioni sul loro saldo permessi in Microsoft Teams. I dipendenti possono interagire con un bot per richiedere informazioni. La scheda **Tempo libero** fornisce informazioni più dettagliate.

![Bot dell'app per i permessi Human Resources in Teams](./media/hr-admin-teams-leave-app-bot.png)

![Scheda Tempo libero dell'app per i permessi Human Resources in Teams](./media/hr-teams-leave-app-timeoff-tab.png)

## <a name="install-and-setup"></a>Installa e configura

Puoi trovare l'app Human Resources nello store di Teams. Per informazioni sull'installazione dell'app Teams, vedi [Gestisci richieste di permessi in Teams](hr-teams-leave-app.md).

Per informazioni sulla gestione delle autorizzazioni delle app in Teams, vedi [Gestire i criteri delle autorizzazioni delle app in Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/teams-app-permission-policies).

## <a name="known-issues"></a>Problemi noti

| Uscita | Stato |
| --- | --- |
| Lo scorrimento orizzontale non funziona su telefoni Android | Lo scorrimento orizzontale non è un problema su iOS o su dispositivi desktop. Stiamo lavorando a una correzione per Android. |
| Errore: si è verificato un problema durante la ricerca di un ambiente a cui connettersi. | Questo errore potrebbe essere visualizzato anche se hai verificato che l'utente può accedere a uno o più ambienti di Human Resources. Inoltre, potresti non vedere tutti gli ambienti previsti. Fino a quando questo problema non vine risolto, elimina l'utente e quindi importalo di nuovo per risolvere il problema. |
| Il saldo non è corretto quando richiedi permessi per una data futura. | Le previsioni non sono ancora disponibili. Il saldo visualizza la data corrente. |
| Quando si riduce il numero di ore impiegate in una richiesta esistente, il **Saldo restante** scende invece di salire. | Affronteremo questo problema noto in futuro. La visualizzazione non è corretta, ma gli importi corretti vengono adeguati al momento dell'invio. |
| Impossibile annullare una richiesta **In revisione**. | Questa funzionalità non è attualmente supportata e verrà aggiunta in una versione futura. |
| Le informazioni sul saldo sono calcolate a partire da oggi. | Il sistema al momento non visualizza i saldi al momento del periodo di competenza, anche se configurato nei parametri congedo e assenza. |

## <a name="privacy-notice"></a>Informativa sulla privacy

Con il bot Dynamics 365 Human Resources in Microsoft Teams, gli input di testo dell'utente vengono analizzati per comprendere la query/l'intento sottostanti. L'input dell'utente, ad esempio "Cerca account Contoso", viene indirizzato a uno dei servizi cognitivi di Microsoft chiamato Language Understanding Intelligent Service (LUIS). Ulteriori informazioni su LUIS [qui](https://www.luis.ai/). Il servizio LUIS disambigua o comprende l'intento dell'input dell'utente (in questo caso, l'intento è quello di trovare informazioni) e l'entità di destinazione (in questo caso, l'entità desiderata è un account chiamato Contoso). Queste informazioni vengono quindi trasmesse al [Framework bot di Azure](https://azure.microsoft.com/services/bot-service/) di Microsoft che interagisce con i dati da Dynamics 365 Human Resources e recupera le informazioni desiderate per la query dell'utente. 

Installando e consentendo l'accesso all'uso del bot, l'utente accetta di consentire al servizio LUIS e al framework del bot di Azure di elaborare l'intento dietro l'input, il che si traduce in un'esperienza utente conversazionale migliorata. Il servizio LUIS e il framework dei bot di Azure possono presentare livelli di conformità diversi rispetto a Dynamics 365 Human Resources. Mentre il servizio LUIS ha accesso solo alle query dell'utente e non è progettato per essere collegato ai dati o all'account Dynamics 365 Human Resources dell'utente, un utente del bot Dynamics 365 Human Resources potrebbe inserire volontariamente una query contenente dati del cliente, dati personali o altri dati e tale contenuto della query potrebbe essere inviato al servizio LUIS e al framework del bot di Azure. 

Il contenuto delle query e dei messaggi dell'utente viene conservato nel sistema LUIS per un massimo di 30 giorni, viene crittografato a riposo e non viene utilizzato per migliorare la formazione o il servizio. Ulteriori informazioni sui servizi cognitivi [qui](https://azure.microsoft.com/services/cognitive-services/language-understanding-intelligent-service/). 

Per gestire le impostazioni di amministrazione per le app in Microsoft Teams, vai all'[interfaccia di amministrazione di Microsoft Teams](https://admin.teams.microsoft.com/). 

## <a name="see-also"></a>Vedere anche 

[Scaricare e installare Microsoft Teams](https://support.office.com/article/download-and-install-microsoft-teams-422bf3aa-9ae8-46f1-83a2-e65720e1a34d)</br>
[Centro assistenza di Microsoft Teams](https://support.office.com/teams)</br>
[Gestire le richieste di congedo in Teams](hr-teams-leave-app.md)

