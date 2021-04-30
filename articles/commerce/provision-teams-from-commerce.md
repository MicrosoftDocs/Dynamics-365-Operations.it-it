---
title: Provisioning di Microsoft Teams da Dynamics 365 Commerce
description: Questo argomento descrive come eseguire il provisioning di Microsoft Teams utilizzando i dati dell'organizzazione da Dynamics 365 Commerce.
author: gvrmohanreddy
manager: annbe
ms.date: 03/31/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2021-01-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: ba7c74942735b723d1015dc4da0068fbb631bc6b
ms.sourcegitcommit: 34b478f175348d99df4f2f0c2f6c0c21b6b2660a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/16/2021
ms.locfileid: "5908906"
---
# <a name="provision-microsoft-teams-from-dynamics-365-commerce"></a>Provisioning di Microsoft Teams da Dynamics 365 Commerce

[!include [banner](includes/banner.md)]

Questo argomento descrive come eseguire il provisioning di Microsoft Teams utilizzando i dati dell'organizzazione da Dynamics 365 Commerce.

Dynamics 365 Commerce offre un modo semplice per eseguire il provisioning di Teams se non hai ancora impostato i team per i tuoi punti vendita al dettaglio. Utilizzando le informazioni ben definite di Commerce in Teams, puoi aiutare i dipendenti del tuo negozio a iniziare a usare Teams. Queste informazioni includono la gerarchia organizzativa, i nomi dei negozi, le informazioni sui dipendenti e gli account Azure Active Directory (Azure AD). 

Il processo di provisioning di Teams prevede due passaggi principali:

1. In Teams crea un team per ogni punto vendita al dettaglio e aggiungi i lavoratori del negozio come membri del team appropriato. Se un dipendente è associato a più di un punto vendita al dettaglio, l'appartenenza al team rifletterà le associazioni. Verrà creato un team di comunicazione che include i manager regionali come membri per aiutare a pubblicare attività da Teams.
1. Carica la tua gerarchia organizzativa da Commerce a Teams.

## <a name="provision-teams-in-commerce-headquarters"></a>Provisioning di Teams in Commerce headquarters

Prima di eseguire il provisioning di Microsoft Teams, completa queste attività:

- Verifica che tutti i responsabili regionali siano stati nominati responsabili delle comunicazioni.
- Verifica che l'account Azure di ogni responsabile del negozio e lavoratore sia stato associato al record del responsabile o del lavoratore in Commerce headquarters.

Per eseguire il provisioning di Teams in Commerce Headquarters, segui questi passaggi.

1. Vai a **Retail e Commerce \> Impostazione canale \> Configurazione dell'integrazione di Microsoft Teams**.
1. Nel riquadro azioni, seleziona **Provisioning di Team**. Un processo batch denominato **Provisioning di Team** viene creato.
1. Vai a **Amministrazione sistema \> Richieste di informazioni \> Processi batch** e trova il processo più recente con la descrizione **Provisioning di Team**. Attendi fino al termine dell'esecuzione di questo processo.

> [!TIP]
> Se nessuno dei tuoi responsabili regionali, responsabili del negozio e dipendenti del negozio è stato associato a una licenza di Teams, potresti ricevere il seguente messaggio di errore: "Impossibile recuperare le categorie Sku applicabili per l'utente". Per correggere il problema, seleziona **Sincronizza team e membri** nel riquadro azioni.

<!-- ![Dynamics 365 Commerce - Teams integration configuration](media/D365-Commerce-Microsoft-Teams-Configuration_with_disclaimer.png)-->

## <a name="validate-teams-provisioning-in-the-teams-admin-center"></a>Convalidare il provisioning di Teams nell'interfaccia di amministrazione di Teams

Per convalidare il provisioning di Microsoft Teams nell'interfaccia di amministrazione di Microsoft Teams, segui questi passaggi.
    
1. Vai all'[interfaccia di amministrazione di Teams](https://admin.teams.microsoft.com/) e accedi come amministratore del tuo tenant e-commerce.
1. Nel riquadro di spostamento a sinistra, seleziona **Teams** per espanderlo, quindi seleziona **Gestisci team**.
1. Verifica che sia stato creato un team per ogni punto vendita al dettaglio di Commerce.
1. Seleziona un team e verifica che i lavoratori del negozio siano stati aggiunti come membri.
1. Nel riquadro di spostamento a sinistra, seleziona **Utenti** e verifica che tutti i dipendenti del negozio in tutti i negozi siano stati aggiunti come utenti.

La figura seguente mostra un esempio della pagina **Gestisci team** nell'interfaccia di amministrazione di Teams.

![Esempio della pagina Gestisci team nell'interfaccia di amministrazione di Teams](media/Teams-FLW-Admin-Teams.png)

## <a name="upload-a-commerce-organizational-hierarchy-to-teams"></a>Caricare una gerarchia organizzativa di Commerce in Teams
    
La gerarchia organizzativa di Commerce può essere utilizzata in Microsoft Teams per pubblicare le attività in tutti i negozi o in quelli selezionati che utilizzano la stessa struttura gerarchica.

Per caricare una gerarchia organizzativa di Commerce in Teams effettua le seguenti operazioni.
    
1. In Commerce headquarters vai a **Retail e Commerce \> Impostazione canale \> Configurazione dell'integrazione di Microsoft Teams**.
1. Seleziona **Scarica gerarchia di destinazione** e quindi seleziona **Punti vendita per regione** per scaricare un file CSV (valori delimitati da virgole) della gerarchia organizzativa.
1. Installa il modulo Microsoft Teams PowerShell seguendo i passaggi in [Installare Microsoft Teams PowerShell](https://docs.microsoft.com/microsoftteams/teams-powershell-install).
1. Quando ti viene richiesto nella finestra Teams PowerShell, accedi utilizzando l'account amministratore per il tuo tenant Azure AD.
1. Segui i passaggi in [Impostare la gerarchia di destinazione del tuo team](https://docs.microsoft.com/microsoftteams/set-up-your-team-hierarchy) per caricare il file CSV per la gerarchia di destinazione.

## <a name="verify-that-the-organizational-hierarchy-was-uploaded-to-teams"></a>Verificare che la gerarchia organizzativa sia stata caricata in Teams

Per verificare che la gerarchia organizzativa sia stata caricata in Microsoft Teams, segui questi passaggi.

1. Accedi a Teams come responsabile delle comunicazioni.
1. Nel riquadro di spostamento a sinistra, seleziona **Attività di Planner**.
1. Nella scheda **Elenchi pubblicati** crea un nuovo elenco con un'attività fittizia.
1. Selezionare **Pubblica** La gerarchia organizzativa deve apparire nella finestra di dialogo **Seleziona per chi pubblicare** come mostrato nell'esempio della figura seguente.

![Esempio di una gerarchia organizzativa nella finestra di dialogo Seleziona per chi pubblicare](media/Microsoft-teams-verify-org-hierarchy.png)

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica dell'integrazione di Dynamics 365 Commerce e Microsoft Teams](commerce-teams-integration.md)

[Abilitare l'integrazione di Dynamics 365 Commerce e Microsoft Teams](enable-teams-integration.md)

[Sincronizzare la gestione delle attività tra POS di Microsoft Teams e Dynamics 365 Commerce](synchronize-tasks-teams-pos.md)

[Gestire i ruoli utente in Microsoft Teams](manage-user-roles-teams.md)

[Mappare negozi e team se ci sono team preesistenti in Microsoft Teams](map-stores-existing-teams.md)

[Domande frequenti sull'integrazione di Dynamics 365 Commerce e Microsoft Teams](teams-integration-faq.md)
