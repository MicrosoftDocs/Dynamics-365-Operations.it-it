---
title: Human Resources non appare nelle app Microsoft Dynamics 365
description: Questo articolo spiega cosa fare se Microsoft Dynamics 365 Human Resources non è elencato tra le app di Microsoft Dynamics 365.
author: twheeloc
ms.date: 08/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 2d520ac06bcc0990714929c0fdd622516eda5f30
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8872241"
---
# <a name="human-resources-app-doesnt-appear-in-microsoft-dynamics-365-apps"></a>L'app Risorse Umane non appare in Microsoft Dynamics 365 apps


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

**Problema**

Il cliente non vede Dynamics 365 Human Resources tra le app di Microsoft Dynamics 365.

**Risoluzione**

L'utente deve essere aggiunto al ruolo Creatore dell'utente per l'ambiente in Microsoft Power Apps.

1. L'utente amministratore che dispone di una licenza di Power Apps Piano 2 deve aprire il [Portale di amministrazione di Power Apps](https://preview.admin.powerapps.com/).

2. Selezionare **Ambienti** e scegliere l'ambiente corretto per Human Resources.

3. Nella scheda **Ruoli ambiente** della scheda **Sicurezza**, selezionare **Creatore dell'ambiente**.

    ![Scheda Ruoli ambiente.](media/environment-roles.png)

4. Nella scheda **Utenti**, aggiungere l'utente o l'organizzazione.

    ![Scheda Utenti.](media/environment-maker.png)

5. Selezionare **Salva**.

6. L'utente deve ora accedere a [Microsoft Dynamics 365](https://home.dynamics.com/).

7. Selezionare **Sincronizza** per aggiornare le app dell'utente.

    ![Pulsante Sincronizza.](media/get-more.png)

    Dopo che la sincronizzazione viene completata, l'app Human Resources verrà visualizzata nella home page.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
