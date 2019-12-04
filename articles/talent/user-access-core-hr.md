---
title: L'utente può accedere a Core HR ma non a Onboard o Attract
description: In questo argomento viene descritto come risolvere il problema in cui un utente può accedere a Microsoft Dynamics 365 Talent - Core HR ma non ad Attract o Onboard.
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
ms.openlocfilehash: 1a86936d756d8375761ce50c9d9bf33dc638dfad
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/06/2019
ms.locfileid: "2772921"
---
# <a name="user-can-access-core-hr-but-not-onboard-or-attract"></a>L'utente può accedere a Core HR ma non a Onboard o Attract

[!include [banner](includes/banner.md)]

**Dettagli ambiente**

- La distribuzione di Microsoft Dynamics Lifecycle Services (LCS) è stata effettuata dall'utente A.
- L'utente A ha aggiunto l'utente B come utente a Microsoft Dynamics 365 Talent: Core HR.

**Problema**

L'utente B può accedere a Core HR, ma non può accedere all'app Talent: Attract o Talent: Onboard. Quando l'utente tenta di accedere a **App esperienza**, viene invece visualizzato un ambiente di test.

**Soluzione**

All'utente B devono essere assegnati i diritti di visualizzare l'ambiente di Microsoft Power Apps creato dall'utente A durante il processo di provisioning.

Per informazioni, vedere la sezione "Concedere l'accesso all'ambiente" in [Eseguire il provisioning di Talent](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent).

**Soluzione a lungo termine**

Microsoft sta considerando l'assegnazione automatica dei diritti appropriati a Onboard e Attract quando un utente viene aggiunto a Core HR.
