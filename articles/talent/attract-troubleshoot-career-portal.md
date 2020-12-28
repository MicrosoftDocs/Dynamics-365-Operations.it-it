---
title: Gli utenti di Attract non possono candidarsi per mansioni dal portale delle carriere
description: Questo argomento spiega come risolvere un problema a causa del quale gli utenti di Attract non possono candidarsi per lavori dal portale delle carriere.
author: andreabichsel
manager: AnnBe
ms.date: 09/23/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-09-23
ms.dyn365.ops.version: Platform update 24
ms.openlocfilehash: e1d72bef6d8bbe15e27326f66341915ba44a09b4
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4461604"
---
# <a name="attract-users-cant-apply-for-jobs-from-career-portal"></a>Gli utenti di Attract non possono candidarsi per mansioni dal portale delle carriere

[!include [banner](includes/banner.md)]

## <a name="issue"></a>Uscita

Gli utenti di Attract non possono candidarsi per mansioni dal portale delle carriere. Quando cercano di candidarsi per un lavoro creato in Dynamics 365 Talent: Attract, il browser carica la pagina continuamente e non completa l'azione.

## <a name="cause"></a>Causa

Questo problema si verifica quando il team delle relazioni di Talent non ha il ruolo utente Talent.

## <a name="resolution"></a>Risoluzione

Assegnare il ruolo utente Talent al team delle relazioni di Talent.

1. Accedere all'[interfaccia di amministrazione di Power Platform](https://admin.powerplatform.microsoft.com) con una delle seguenti credenziali di amministratore:

   - Amministratore di Dynamics 365
   - Amministratore globale
   - Amministratore di Power Platform

2. Nel riquadro di spostamento selezionare **Ambienti**, quindi selezionare l'ambiente in cui assegnare il ruolo utente Talent al team delle relazioni di Talent.

   ![Selezionare l'ambiente](./media/attract-troubleshoot-career-portal-select-environment.png)

3. Nel riquadro **Ambienti** selezionare l'**URL dell'ambiente** e accedere al portale di amministrazione dell'ambiente (ad esempio, https:<orgname>.crm.dynamics.com).

4. Selezionare **Impostazioni**, **Sistema** e quindi selezionare **Sicurezza**.

   ![Passare a Sicurezza](./media/attract-troubleshoot-career-portal-security.png)

5. Selezionare **Teams**.

   ![Selezionare Teams](./media/attract-troubleshoot-career-portal-security-teams.png)

6. Cercare **Team delle relazioni di Talent** nella casella di ricerca, quindi selezionare il team dai risultati della ricerca.

7. Selezionare **GESTISCI RUOLI** dalla barra multifunzione.

8. Nella finestra di dialogo **Gestisci i ruoli del team**, selezionare **Utente di Talent** dall'elenco dei ruoli disponibili, quindi selezionare **OK** per applicare il ruolo.

   ![Applicare il ruolo](./media/attract-troubleshoot-career-portal-apply-role.png)

9. Testare le modifiche:

   1. Accedere al portale delle carriere da una nuova finestra del browser.
   2. Candidarsi per il lavoro dal portale delle carriere. 