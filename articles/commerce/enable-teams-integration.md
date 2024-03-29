---
title: Abilitare l'integrazione di Dynamics 365 Commerce e Microsoft Teams
description: Questo articolo descrive come abilitare l'integrazione di Microsoft Dynamics 365 Commerce e Microsoft Teams.
author: gvrmohanreddy
ms.date: 02/17/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2021-01-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: f8b84938c2047ab1102864cc203e0ec853160bb1
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9274315"
---
# <a name="enable-dynamics-365-commerce-and-microsoft-teams-integration"></a>Abilitare l'integrazione di Dynamics 365 Commerce e Microsoft Teams

[!include [banner](includes/banner.md)]

Questo articolo descrive come abilitare l'integrazione di Microsoft Dynamics 365 Commerce e Microsoft Teams.

Per fornire a Teams informazioni da Dynamics 365 Commerce e sincronizzare le funzionalità di gestione delle attività tra Teams e l'applicazione del punto vendita (POS), è necessario abilitare le funzionalità di integrazione in Commerce headquarters.

> [!NOTE]
> Quando abiliti l'integrazione di Teams, acconsenti a condividere i tuoi dati con Teams. I dati condivisi con Teams potrebbero risiedere in un paese diverso rispetto ai dati di Commerce e potrebbero essere soggetti a standard di conformità diversi. Per ulteriori informazioni, vedi il [Centro protezione Microsoft](https://www.microsoft.com/trust-center). Per informazioni sui criteri della privacy di Microsoft, vedi l'[Informativa sulla privacy di Microsoft](https://aka.ms/privacy).

## <a name="enable-teams-integration"></a>Abilitare l'integrazione di Teams

Prima di poter abilitare l'integrazione di Microsoft Teams con Commerce, è necessario registrare l'applicazione Teams con il tenant nel portale di Azure.

Per registrare l'applicazione Teams con il tuo tenant nel portale di Azure, segui questi passaggi.

1. Segui i passaggi in [Guida introduttiva: Registrare un'applicazione con Microsoft Identity Platform](/azure/active-directory/develop/quickstart-register-app) per registrare l'applicazione Teams con il tenant nel portale di Azure.
1. Nella scheda **Registrazione app**, seleziona l'app creata nel passaggio precedente. Quindi, nella scheda **Autenticazione**, seleziona **Aggiungi piattaforma**.
1. Nella finestra di dialogo, seleziona **Web**. Quindi, nel campo **Reindirizza URL**, immetti un URL nel formato **\<HQUrl\>/oauth**. Sostituisci **\<HQUrl\>** con l'URL di Commerce headquarters (ad esempio, `https://hxennugbjtweufmdeo385f47fadb6aa9a0aos.cloudax.int.dynamics.com/oauth`).
1. Copia il valore **ID applicazione (client)** dalla pagina **Panoramica** dell'app registrata. Devi fornire questo valore per abilitare l'integrazione di Teams in Commerce headquarters nella sezione successiva.
1. Segui le istruzioni in [Aggiungere un segreto client](/azure/active-directory/develop/quickstart-register-app#add-a-client-secret) per aggiungere un segreto client. Quindi copia il valore di **Valore segreto** per il client. Devi fornire questo valore per abilitare l'integrazione di Teams in Commerce headquarters nella sezione successiva.
1. Seleziona **Autorizzazioni API** quindi **Aggiungi un'autorizzazione**.
1. Nella finestra di dialogo **Richiedi autorizzazioni API**, seleziona **Microsoft Graph**, seleziona **Autorizzazioni delegate**, espandi **Gruppo**, seleziona **Group.ReadWrite.All** e quindi **Aggiungi autorizzazioni**.
1. Nella finestra di dialogo **Richiedi autorizzazioni API**, seleziona **Aggiungi un'autorizzazione**, seleziona **Microsoft Graph**, seleziona **Autorizzazioni applicazione**, espandi **Gruppo**, seleziona **Group.ReadWrite.All** e quindi **Aggiungi autorizzazioni**.
1. Nella finestra di dialogo **Richiedi autorizzazioni API**, seleziona **Aggiungi un'autorizzazione**. Nella scheda **API utilizzate dalla mia organizzazione**, cerca **Microsoft Teams Retail Service** e selezionalo.
1. Seleziona **Autorizzazioni delegate**, espandi **TaskPublishing**, seleziona **TaskPublising.ReadWrite.All** e quindi **Aggiungi autorizzazioni**. Per ulteriori informazioni, vedi [Configurare un'applicazione client per accedere a un'API Web](/azure/active-directory/develop/quickstart-configure-app-access-web-apis).

Per abilitare l'integrazione di Teams in Commerce headquarters, segui questi passaggi.

1. Vai a **Retail e Commerce \> Impostazione canale \> Configurazione dell'integrazione di Microsoft Teams**.
1. Nel riquadro azioni, seleziona **Modifica**.
1. Imposta l'opzione **Abilita integrazione di Microsoft Teams** su **Sì**.
1. Nel campo **ID applicazione**, immettere **ID applicazione (client)** ottenuti durante la registrazione dell'applicazione Teams nel portale di Azure.
1. Nel campo **Chiave applicazione**, immetti il valore di **Valore segreto** ottenuto durante l'aggiunta di un segreto client nel portale di Azure.
1. Nel riquadro azioni selezionare **Salva**.

La figura seguente mostra un esempio di configurazione dell'integrazione di Teams in Commerce headquarters.

![Configurazione dell'integrazione di Teams in Commerce headquarters.](media/D365-Commerce-Microsoft-Teams-Configuration_with_disclaimer.png)

## <a name="disable-teams-integration"></a>Disabilitare l'integrazione di Teams

Per disabilitare l'integrazione di Microsoft Teams in Commerce headquarters, segui questi passaggi.

1. Vai a **Retail e Commerce \> Impostazione canale \> Configurazione dell'integrazione di Microsoft Teams**.
1. Nel riquadro azioni, seleziona **Modifica**.
3. Imposta l'opzione **Abilita integrazione di Microsoft Teams** su **No**.
4. Cancella i valori dai campi **ID applicazione** e **Chiave applicazione**.
1. Nel riquadro azioni selezionare **Salva**.

> [!NOTE]
> Dopo aver disabilitato l'integrazione di Teams con Commerce, i terminali POS non mostreranno più le attività pubblicate dall'applicazione Teams.

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica dell'integrazione di Dynamics 365 Commerce e Microsoft Teams](commerce-teams-integration.md)

[Provisioning di Microsoft Teams da Dynamics 365 Commerce](provision-teams-from-commerce.md)

[Sincronizzare la gestione delle attività tra POS di Microsoft Teams e Dynamics 365 Commerce](synchronize-tasks-teams-pos.md)

[Gestire i ruoli utente in Microsoft Teams](manage-user-roles-teams.md)

[Mappare negozi e team se ci sono team preesistenti in Microsoft Teams](map-stores-existing-teams.md)

[Domande frequenti sull'integrazione di Dynamics 365 Commerce e Microsoft Teams](teams-integration-faq.md)
