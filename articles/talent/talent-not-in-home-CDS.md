---
title: "Talent non è visualizzato come app di Microsoft Dynamics 365 (CDS1.0)"
description: "Questo argomento descrive come procedere se Microsoft Dynamics 365 for Talent non è visualizzato tra le app di Microsoft Dynamics 365."
author: Darinkramer
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Talent
ms.translationtype: HT
ms.sourcegitcommit: d3f974f94b6c327fd70b8098d24f9e1f1e1e8eeb
ms.openlocfilehash: 32ae0ab807e953bd811a557e6878b9bee79d293c
ms.contentlocale: it-it
ms.lasthandoff: 12/04/2018

---

# <a name="talent-doesnt-appear-among-the-microsoft-dynamics-365-apps-cds10"></a>Talent non è visualizzato come app di Microsoft Dynamics 365 (CDS1.0)

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

