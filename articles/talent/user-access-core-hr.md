---
title: L'utente può accedere a Core HR ma non all'app Onboard o Attract
description: In questo argomento viene descritto come risolvere il problema in cui un utente può accedere a Microsoft Dynamics 365 for Talent Core HR ma non all'app Attract o Onboard.
author: andreabichsel
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 6fc27a4c137fef2f8d204d90366c316389da08e6
ms.sourcegitcommit: 45f8cea6ac75bd2f4187380546a201c056072c59
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/12/2019
ms.locfileid: "1741721"
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

Per informazioni, vedere la sezione "Concedere l'accesso all'ambiente" in [Eseguire il provisioning di Talent](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent).

**Soluzione a lungo termine**

Microsoft sta considerando l'assegnazione automatica dei diritti appropriati a Onboard e Attract quando un utente viene aggiunto a Core HR.
