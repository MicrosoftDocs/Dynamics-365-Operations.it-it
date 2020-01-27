---
title: Talent non appare tra le app Microsoft Dynamics 365 (Common Data Service 1.0)
description: Questo argomento descrive come procedere se Microsoft Dynamics 365 Talent non è visualizzato tra le app di Microsoft Dynamics 365.
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
ms.openlocfilehash: a44d2e43752960d3026fa7ac92c7b261aee05448
ms.sourcegitcommit: 871707a3fd236da693a3d51f401eb0cb9d4bae39
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/06/2019
ms.locfileid: "2897029"
---
# <a name="talent-doesnt-appear-among-the-microsoft-dynamics-365-apps-common-data-service-10"></a>Talent non appare tra le app Microsoft Dynamics 365 (Common Data Service 1.0)

**Uscita**

Microsoft Dynamics 365 Talent non è visualizzato tra le app di Microsoft Dynamics 365.

**Risoluzione**

L'utente deve essere aggiunto al ruolo Creatore dell'utente per l'ambiente in Microsoft Power Apps.

1. L'utente amministratore che dispone di una licenza di Power Apps Piano 2 deve aprire il [Portale di amministrazione di Power Apps](https://preview.admin.powerapps.com/).
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
