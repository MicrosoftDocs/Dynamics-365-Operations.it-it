---
title: Panoramica dell'integrazione di Dynamics 365 Commerce e Microsoft Teams
description: Questo argomento presenta una panoramica dell'integrazione di Microsoft Dynamics 365 Commerce e Microsoft Teams.
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
ms.openlocfilehash: b9289aca4f53eb2ae8f1fa06d5f80b7ee0bbab8e
ms.sourcegitcommit: 34b478f175348d99df4f2f0c2f6c0c21b6b2660a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/16/2021
ms.locfileid: "5908469"
---
# <a name="dynamics-365-commerce-and-microsoft-teams-integration-overview"></a>Panoramica dell'integrazione di Dynamics 365 Commerce e Microsoft Teams

[!include [banner](includes/banner.md)]

Questo argomento presenta una panoramica dell'integrazione di Microsoft Dynamics 365 Commerce e Microsoft Teams.

Dynamics 365 Commerce si integra con Teams per aiutare i clienti e i loro dipendenti a migliorare la produttività sincronizzando la gestione delle attività tra le due applicazioni. La gestione delle attività semplice offerta dall'integrazione di Commerce e Teams consente ai responsabili dei negozi e ai dipendenti di creare elenchi di attività, assegnare attività a più negozi e tenere traccia dello stato delle attività nei negozi, da entrambe le applicazioni.

L'integrazione di Commerce e Teams è disponibile a partire dalla versione 10.0.18 di Commerce.

## <a name="key-features"></a>Funzionalità principali

Ecco alcune delle funzionalità principali fornite dall'integrazione di Commerce e Microsoft Teams:

- Provisioning di Teams utilizzando le informazioni ben definite di Commerce, come la struttura organizzativa e le informazioni su negozi, lavoratori, autorizzazioni e contesto aziendale.
- Sincronizzazione facile delle modifiche in corso (ad esempio, l'aggiunta di nuovi negozi o l'assunzione di nuovi dipendenti) tra Commerce e Teams, ma mantenendo Commerce come fonte principale dei dati della struttura organizzativa.
- Integrazione della gestione delle attività tra Commerce e Teams per aiutare i dipendenti del negozio, i gestori del negozio, i responsabili di area e i responsabili delle comunicazioni a gestire le attività da entrambe le applicazioni.

## <a name="prerequisites-for-using-integration-features"></a>Prerequisiti per l'utilizzo delle funzionalità di integrazione

I seguenti prerequisiti devono essere soddisfatti prima di poter iniziare a utilizzare le funzionalità di integrazione di Microsoft Teams:

- Licenza Microsoft 365 Business Standard (questa licenza include Teams).
- Account Azure Active Directory (Azure AD) per tutti i responsabili e i lavoratori del negozio
- Sistemi POS configurati con l'autenticazione Azure AD

## <a name="conceptual-architecture"></a>Architettura concettuale

La figura seguente mostra l'architettura concettuale dell'integrazione di Dynamics 365 Commerce e Microsoft Teams, utilizzando un negozio di San Francisco come esempio. L'applicazione POS di Teams e Commerce utilizza Microsoft Planner come repository in modo che le attività pubblicate da Teams vengano visualizzate nell'applicazione POS e le attività ad hoc create dai responsabili del negozio nell'applicazione POS vengano visualizzate in Teams, garantendo un'esperienza di gestione delle attività fluida tra le applicazioni.    

![Architettura dell'integrazione di Commerce e Teams](media/d365-commerce-teams-integration-conceptual-architecture.png)

## <a name="additional-resources"></a>Risorse aggiuntive

[Abilitare l'integrazione di Dynamics 365 Commerce e Microsoft Teams](enable-teams-integration.md)

[Provisioning di Microsoft Teams da Dynamics 365 Commerce](provision-teams-from-commerce.md)

[Sincronizzare la gestione delle attività tra POS di Microsoft Teams e Dynamics 365 Commerce](synchronize-tasks-teams-pos.md)

[Gestire i ruoli utente in Microsoft Teams](manage-user-roles-teams.md)

[Mappare negozi e team se ci sono team preesistenti in Microsoft Teams](map-stores-existing-teams.md)

[Domande frequenti sull'integrazione di Dynamics 365 Commerce e Microsoft Teams](teams-integration-faq.md)
