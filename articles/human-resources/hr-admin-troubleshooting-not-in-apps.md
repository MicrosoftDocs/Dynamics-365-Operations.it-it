---
title: Human Resources non appare nelle app Microsoft Dynamics 365
description: Questo articolo descrive come procedere se l'app Microsoft Dynamics 365 Human Resources non è visualizzata tra le app di Microsoft Dynamics 365.
author: andreabichsel
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 17a454cd32a08db105a13577c32368ad819bed1c
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/18/2021
ms.locfileid: "6053378"
---
# <a name="human-resources-doesnt-appear-in-microsoft-dynamics-365-apps"></a>Human Resources non appare nelle app Microsoft Dynamics 365

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

**Problema**

Il cliente non vede Dynamics 365 Human Resources tra le app di Microsoft Dynamics 365.

**Risoluzione**

L'utente deve essere aggiunto al ruolo Creatore dell'utente per l'ambiente in Microsoft Power Apps.

1. L'utente amministratore che dispone di una licenza di Power Apps Piano 2 deve aprire il [Portale di amministrazione di Power Apps](https://preview.admin.powerapps.com/).

2. Selezionare **Ambienti** e scegliere l'ambiente corretto per Human Resources.

3. Nella scheda **Ruoli ambiente** della scheda **Sicurezza**, selezionare **Creatore dell'ambiente**.

    ![Scheda Ruoli ambiente](media/environment-roles.png)

4. Nella scheda **Utenti**, aggiungere l'utente o l'organizzazione.

    ![Scheda Utenti](media/environment-maker.png)

5. Selezionare **Salva**.

6. L'utente deve ora accedere a [Microsoft Dynamics 365](https://home.dynamics.com/).

7. Selezionare **Sincronizza** per aggiornare le app dell'utente.

    ![Pulsante Sincronizza](media/get-more.png)

    Dopo che la sincronizzazione viene completata, l'app Human Resources verrà visualizzata nella home page.


[!INCLUDE[footer-include](../includes/footer-banner.md)]