---
title: Domande frequenti sull'integrazione di Dynamics 365 Commerce e Microsoft Teams
description: In questo articolo vengono fornite risposte alle domande frequenti relative all'integrazione di Microsoft Dynamics 365 Commerce e Microsoft Teams.
author: gvrmohanreddy
ms.date: 03/31/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2021-01-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 02f10e446349803ce5629fed0be4176f2df2be0c
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8869129"
---
# <a name="dynamics-365-commerce-and-microsoft-teams-integration-faq"></a>Domande frequenti sull'integrazione di Dynamics 365 Commerce e Microsoft Teams

[!include [banner](includes/banner.md)]

In questo articolo vengono fornite risposte alle domande frequenti relative all'integrazione di Microsoft Dynamics 365 Commerce e Microsoft Teams.

### <a name="who-in-the-store-becomes-an-owner-of-a-team-while-provisioning-teams-from-commerce"></a>Chi nel negozio diventa proprietario di un team durante il provisioning di Teams da Commerce? 

Tutti i responsabili dei negozi vengono aggiunti automaticamente come proprietari al gruppo del team corrispondente in modo che possano eseguire operazioni come l'aggiunta di un canale privato e l'aggiunta o l'eliminazione di membri. 

### <a name="how-do-i-assign-the-communications-manager-role-to-an-employee-in-commerce-headquarters"></a>Come si assegna il ruolo di "responsabile delle comunicazioni" a un dipendente in Commerce headquarters? 

I responsabili della comunicazione in Microsoft Teams hanno la capacità di creare e pubblicare elenchi di attività. I dipendenti dell'organizzazione che devono diventare responsabili della comunicazione devono avere il ruolo di "responsabile attività di vendita al dettaglio" assegnato loro in Commerce headquarters.

Per assegnare il ruolo di responsabile dell'attività di vendita al dettaglio a un dipendente in Commerce headquarters, attieniti alla seguente procedura.

1. Passare a **Retail e Commerce \> Dipendenti \> Utenti**.
1. Selezionare un dipendente.
1. Nella scheda dettaglio **Ruoli utente**, selezionare **Assegna ruoli**.
1. Nella finestra di dialogo **Assegna ruoli all'utente** selezionare il ruolo **Responsabile attività vendita al dettaglio**, quindi selezionare **OK**.

### <a name="how-do-i-make-a-specific-organization-hierarchy-available-to-upload-into-microsoft-teams"></a>Come faccio a rendere disponibile una gerarchia organizzativa specifica per il caricamento in Microsoft Teams?

In Commerce headquarters, la gerarchia di ogni organizzazione è associata a uno o più scopi. Assicurati che la gerarchia in cui desideri eseguire il provisioning in Microsoft Teams abbia lo scopo **Report per vendita al dettaglio** ad essa associato, come mostrato nella seguente immagine di esempio. 

![Esempio di scopo della gerarchia organizzativa in Commerce headquarters.](media/d365-commerce-organization-hierarchies-purpose.png)

### <a name="how-do-i-enable-retail-store-workers-to-sign-in-to-commerce-point-of-sale-pos-using-azure-active-directory-azure-ad"></a>Come si consente ai lavoratori dei punti vendita al dettaglio di accedere al POS di Commerce utilizzando Azure Active Directory (Azure AD)?

Per informazioni su come configurare l'esperienza di accesso a Commerce POS per utilizzare l'autenticazione Azure AD, vedi [Abilitare l'autenticazione Azure Active Directory per l'accesso al POS](aad-pos-logon.md).

### <a name="how-do-i-map-stores-and-corresponding-teams-in-commerce-headquarters-if-my-organization-has-already-created-teams-in-microsoft-teams"></a>Come faccio a mappare i negozi e i team corrispondenti in Commerce headquarters se la mia organizzazione ha già creato team in Microsoft Teams?

Per informazioni su come mappare negozi e team se sono presenti team preesistenti, vedi [Mappare negozi e team corrispondenti se l'organizzazione ha team preesistenti in Microsoft Teams](map-stores-existing-teams.md).

### <a name="how-do-i-clear-the-microsoft-graph-api-token-stored-in-the-session-storage"></a>Come si cancella il token dell'API Microsoft Graph archiviato nell'archiviazione della sessione?

Un utente che ha effettuato l'accesso al POS con un account Azure Active Directory (Azure AD) deve disconnettersi dal POS o chiudere l'applicazione per cancellare l'archiviazione della sessione. 

> [!TIP]
> Una procedura consigliata è quella di chiedere sempre ai dipendenti del negozio di bloccare il terminale POS o di disconnettersi da una sessione quando non utilizzano il terminale. 

### <a name="what-happens-if-a-store-doesnt-have-store-managers"></a>Cosa succede se un negozio non ha responsabili del negozio?

Se un negozio non ha responsabili, non verrà creato un gruppo di team per il negozio o in Teams. 

### <a name="what-happens-if-a-store-manager-leaves-the-company"></a>Cosa succede se un responsabile del negozio lascia l'azienda?

Chiunque abbia il ruolo di proprietario può aggiungere un nuovo responsabile del negozio in Commerce headquarters ed eseguire il reprovisioning dei team in modo che il nuovo responsabile disponga dei privilegi necessari in Teams per il gruppo. 

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica dell'integrazione di Dynamics 365 Commerce e Microsoft Teams](commerce-teams-integration.md)

[Abilitare l'integrazione di Dynamics 365 Commerce e Microsoft Teams](enable-teams-integration.md)

[Provisioning di Microsoft Teams da Dynamics 365 Commerce](provision-teams-from-commerce.md)

[Sincronizzare la gestione delle attività tra POS di Microsoft Teams e Dynamics 365 Commerce](synchronize-tasks-teams-pos.md)

[Gestire i ruoli utente in Microsoft Teams](manage-user-roles-teams.md)

[Mappare negozi e team se ci sono team preesistenti in Microsoft Teams](map-stores-existing-teams.md)
