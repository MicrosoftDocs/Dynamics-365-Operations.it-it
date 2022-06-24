---
title: Sincronizzare la gestione delle attività tra POS di Microsoft Teams e Dynamics 365 Commerce
description: Questo articolo descrive come sincronizzare la gestione delle attività tra i POS Microsoft Teams e Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 02/17/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2021-01-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 23da56f4f6aee906aad261939d1c7ef9feac5922
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8874871"
---
# <a name="synchronize-task-management-between-microsoft-teams-and-dynamics-365-commerce-pos"></a>Sincronizzare la gestione delle attività tra POS di Microsoft Teams e Dynamics 365 Commerce

[!include [banner](includes/banner.md)]

Questo articolo descrive come sincronizzare la gestione delle attività tra i POS Microsoft Teams e Dynamics 365 Commerce.

Uno degli scopi principali dell'integrazione di Teams è abilitare la sincronizzazione della gestione delle attività tra l'applicazione POS e Teams. In questo modo, i dipendenti del negozio possono utilizzare l'applicazione POS o Teams per gestire le attività e non devono cambiare applicazione.

Poiché Planner viene usato come repository per le attività in Teams, deve esserci un collegamento tra Teams e Dynamics 365 Commerce. Questo collegamento viene stabilito utilizzando un ID piano specifico per un determinato team del negozio.

Le procedure seguenti mostrano come configurare la sincronizzazione della gestione delle attività tra le applicazioni POS e Teams.

## <a name="publish-a-test-task-list-in-teams"></a>Pubblicare un elenco di attività di test in Teams

La procedura seguente presuppone che i team del tuo negozio stiano utilizzando l'integrazione della gestione delle attività di Microsoft Teams con Commerce per la prima volta.

Per pubblicare un elenco di attività di test in Teams, attieniti alla seguente procedura.

1. Accedi a Teams come responsabile delle comunicazioni. In genere, i responsabili delle comunicazioni sono utenti che hanno il ruolo **responsabile regionale** in Commerce.
1. Nel riquadro di spostamento a sinistra, seleziona **Attività di Planner**.
1. Nella scheda **Elenchi pubblicati** seleziona **Nuovo elenco** in basso a sinistra e assegna al nuovo elenco il nome **Elenco delle attività di test**.
1. Selezionare **Crea**. Il nuovo elenco viene visualizzato sotto **Bozze**.
1. Sotto **Titolo attività**, assegna alla prima attività il titolo **Integrazione di Teams di test**. Quindi seleziona **Immetti**.
1. Nell'elenco **Bozze** seleziona l'elenco delle attività. Quindi seleziona  **Pubblica**  nell'angolo in alto a destra.
1. Nella finestra di dialogo **Seleziona per chi pubblicare** seleziona i team che devono ricevere l'elenco delle attività di test.
1. Seleziona **Avanti** per rivedere il tuo piano di pubblicazione. Se è necessario apportare modifiche, seleziona  **Indietro**. 
1. Seleziona **Conferma per procedere** e quindi seleziona **Pubblica**.
1. Al termine della pubblicazione, viene visualizzato un messaggio nella parte superiore della scheda **Elenchi pubblicati** indica se l'elenco delle attività è stato consegnato correttamente.

Per ulteriori informazioni, vedi [Pubblicare gli elenchi di attività per creare e monitorare il lavoro nell'organizzazione](https://support.microsoft.com/office/publish-task-lists-to-create-and-track-work-in-your-organization-095409b3-f5af-40aa-9f9e-339b54e705df).

## <a name="link-pos-and-teams-for-task-management"></a>Collegare POS e Teams per la gestione delle attività

Per collegare le applicazioni POS e Microsoft Teams per la gestione delle attività in Commerce headquarters, segui questi passaggi.

> [!NOTE]
> Prima di provare a integrare Gestione delle attività con Microsoft Teams, assicurati di aver attivato l'[integrazione di Dynamics 365 Commerce e Microsoft Teams](enable-teams-integration.md). 

1. Vai a **Retail e Commerce \> Gestione delle attività \> Integrazione di attività con Microsoft Teams**.
1. Nel riquadro azioni, seleziona **Modifica**.
1. Imposta l'opzione **Abilita l'integrazione di gestione delle attività** su **Sì**.
1. Nel riquadro azioni selezionare **Salva**.
1. Nel riquadro azioni seleziona **Imposta gestione delle attività**. Ricevi una notifica che indica che un processo batch denominato **Provisioning di Team** è in fase di creazione.
1. Vai a **Amministrazione sistema \> Richieste di informazioni \> Processi batch** e trova il processo più recente con la descrizione **Provisioning di Team**. Attendi fino al termine dell'esecuzione di questo processo.
1. Corri il **processo CDX 1070** per pubblicare l'ID del piano e memorizzare i riferimenti a Retail Server.

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica dell'integrazione di Dynamics 365 Commerce e Microsoft Teams](commerce-teams-integration.md)

[Abilitare l'integrazione di Dynamics 365 Commerce e Microsoft Teams](enable-teams-integration.md)

[Provisioning di Microsoft Teams da Dynamics 365 Commerce](provision-teams-from-commerce.md)

[Gestire i ruoli utente in Microsoft Teams](manage-user-roles-teams.md)

[Mappare negozi e team se ci sono team preesistenti in Microsoft Teams](map-stores-existing-teams.md)

[Domande frequenti sull'integrazione di Dynamics 365 Commerce e Microsoft Teams](teams-integration-faq.md)
