---
title: L'utente può accedere a Core HR ma non all'app Onboard o Attract
description: In questo argomento viene descritto come risolvere il problema in cui un utente può accedere a Microsoft Dynamics 365 for Talent Core HR ma non all'app Attract o Onboard.
author: Darinkramer
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 2e5d0b1bf993aec89c7d2c6d4916732f5824310d
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2019
ms.locfileid: "305036"
---
# <a name="user-can-access-core-hr-but-not-the-onboard-or-attract-app"></a>L'utente può accedere a Core HR ma non all'app Onboard o Attract

[!include [banner](includes/banner.md)]

**Dettagli ambiente**

- La distribuzione di Microsoft Dynamics Lifecycle Services (LCS) è stata effettuata dall'utente A.
- L'utente A ha aggiunto l'utente B come utente a Microsoft Dynamics 365 for Talent Core HR.

**Uscita**

L'utente B può accedere a Core HR, ma non può accedere all'app Talent: Attract o Talent: Onboard. Quando l'utente tenta di accedere a **App esperienza**, viene invece visualizzato un ambiente di test.

**Soluzione**

All'utente B devono essere assegnati i diritti di visualizzare l'ambiente di Microsoft PowerApps creato dall'utente A durante il processo di provisioning.

Per informazioni, vedere la sezione "Concedere l'accesso all'ambiente" in [Eseguire il provisioning di Talent](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/provisioning-talent).

**Soluzione a lungo termine**

Microsoft sta considerando l'assegnazione automatica dei diritti appropriati a Onboard e Attract quando un utente viene aggiunto a Core HR.
