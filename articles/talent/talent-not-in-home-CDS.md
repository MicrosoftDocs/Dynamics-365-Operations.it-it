---
title: Talent non appare tra le app Microsoft Dynamics 365 (Common Data Service 1.0)
description: Questo argomento descrive come procedere se Microsoft Dynamics 365 for Talent non è visualizzato tra le app di Microsoft Dynamics 365.
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
ms.openlocfilehash: ad5add2b572ccb6bff175806b965f63b53986152
ms.sourcegitcommit: 45b79d1e587e03f5cde2766cdec4eaa7a2a897a3
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "949784"
---
# <a name="talent-doesnt-appear-among-the-microsoft-dynamics-365-apps-common-data-service-10"></a>Talent non appare tra le app Microsoft Dynamics 365 (Common Data Service 1.0)

[!include [banner](includes/banner.md)]

**Uscita**

Microsoft Dynamics 365 for Talent non è visualizzato tra le app di Microsoft Dynamics 365.

**Risoluzione**

L'utente deve essere aggiunto al ruolo Creatore dell'utente per l'ambiente in Microsoft PowerApps.

1. L'utente amministratore che dispone di una licenza di PowerApps Piano 2 deve aprire il [Portale di amministrazione di PowerApps)](https://preview.admin.powerapps.com/).
2. Selezionare **Ambienti** e scegliere l'ambiente corretto per Talent.
3. Nella scheda **Ruoli ambiente** della scheda **Sicurezza**, selezionare **Creatore dell'ambiente**.

    ![Scheda Ruoli ambiente](media/environment-roles.png)

4. Nella scheda **Utenti**, aggiungere l'utente o l'organizzazione.

    ![Scheda Utenti](media/environment-maker.png)

5. Selezionare **Salva**.
6. L'utente deve ora accedere a [Microsoft Dynamics 365](https://home.dynamics.com/).
7. Selezionare **Sincronizza** per aggiornare le app dell'utente.

    ![Pulsante Sincronizza](media/get-more.png)

    Dopo che la sincronizzazione viene completata, Talent verrà visualizzato nella home page.
