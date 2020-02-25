---
title: Gestire utenti e ruoli di e-Commerce
description: In questo argomento viene descritto come concedere agli utenti l'accesso all'ambiente di creazione del sito di Microsoft Dynamics 365 Commerce.
author: bicyclingfool
manager: AnnBe
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: stuharg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 9a1f9abae20d0f2e71790a3b27337338dc042b52
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/01/2020
ms.locfileid: "3003535"
---
# <a name="manage-e-commerce-users-and-roles"></a>Gestire utenti e ruoli di e-Commerce


[!include [banner](includes/banner.md)]

In questo argomento viene descritto come concedere agli utenti l'accesso all'ambiente di creazione del sito di Microsoft Dynamics 365 Commerce.

Per consentire il controllo dell'accesso utente e concedere agli utenti l'autorizzazione di eseguire specifiche attività, l'ambiente di creazione di siti utilizza gruppi di sicurezza creati in Microsoft Azure Active Directory (Azure AD). Innanzitutto si assegna un gruppo di sicurezza nuovo o esistente da Azure AD a ogni ruolo nell'ambiente di creazione. Quindi si concedono o si revocano le autorizzazioni per singoli utenti aggiungendo quegli utenti a un gruppo di sicurezza appropriato o rimuovendoli da un gruppo di sicurezza.

## <a name="overview-of-roles-in-the-authoring-environment"></a>Panoramica dei ruoli nell'ambiente di creazione

L'ambiente di creazione di Dynamics 365 for Commerce supporta i ruoli seguenti.

| Ruolo                 | Descrizione |
|----------------------|-------------|
| Amministratore di sistema | Gli utenti con questo ruolo hanno tutti i privilegi per tutti gli strumenti e tutte le valutazioni e recensioni. Possono inoltre creare siti. |
| Amministratore   | Gli utenti con questo ruolo hanno tutti i privilegi per tutti gli strumenti e per il servizio Valutazioni e recensioni in una determinata struttura del sito. |
| Produttore Web         | Gli utenti con questo ruolo possono creare pagine, frammenti e modelli, caricare e gestire asset e arricchire prodotti e categorie. |
| Lettore               | Gli utenti con questo ruolo possono visualizzare pagine, modelli, asset, frammenti, layout e impostazioni, ma non apportare modifiche. |
| Moderatore valutazioni e recensioni        | Gli utenti con questo ruolo possono moderare le recensioni sui prodotti. |

## <a name="system-administrator-role"></a>Ruolo Amministratore di sistema

Quando si esegue il provisioning di Dynamics 365 Commerce nell'ambiente di Microsoft Dynamics Lifecycle Services (LCS), viene richiesto di fornire un gruppo di sicurezza per il ruolo **Amministratore di sistema**. Questo ruolo viene applicato automaticamente a tutti i siti creati nell'ambiente che si sta configurando. Il gruppo di sicurezza per questo ruolo può essere aggiornato solo in LCS. Nella pagina **Amministrazione sito** di tutti i siti, viene visualizzato come di sola lettura e solo a scopo informativo.

## <a name="administrator-role"></a>Ruolo Amministratore

Quando si crea un nuovo sito in Commerce, viene richiesto di fornire un gruppo di sicurezza per il ruolo **Amministratore**. Vedere la tabella precedente in questo argomento per una panoramica delle autorizzazioni concesse da questo ruolo.

## <a name="add-or-update-security-groups"></a>Aggiungere o aggiornare gruppi di sicurezza

Dopo la creazione del sito, solo gli utenti nei gruppi di sicurezza associati ai ruoli **Amministratore** e **Amministratore di sistema** possono accedere all'ambiente di creazione per quel sito. Per assegnare utenti ai ruoli **Produttore Web**, **Moderatore valutazioni e recensioni** e **Lettore**, è necessario assegnare gruppi di sicurezza a tali ruoli. Per aggiungere un gruppo di sicurezza a un ruolo o per aggiornare un gruppo di sicurezza correntemente assegnato a un ruolo, procedere come segue.

1. Accedere al sito che si intende aggiornare.
1. In **Gestione sito**, aprire la pagina **Sicurezza**.
1. Selezionare il ruolo da modificare.
1. Aggiungere gruppi di sicurezza a ruoli o rimuovere gruppi di sicurezza da ruoli.

## <a name="additional-resources"></a>Risorse aggiuntive

[Aggiungere codice script nelle pagine del sito per supportare la telemetria](add-telemetry.md)

[Considerazioni SEO (ottimizzazione del motore di ricerca) per il proprio sito](search-engine-optimization-considerations.md)

[Gestire i criteri di sicurezza del contenuto (CSP)](manage-csp.md)
