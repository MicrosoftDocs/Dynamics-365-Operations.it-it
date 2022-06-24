---
title: Configurare l'autenticazione da servizio a servizio
description: Questo articolo descrive come configurare l'autenticazione da servizio a servizio in Microsoft Dynamics 365 Commerce per chiamare in modo sicuro le API di servizio per valutazioni e recensioni.
author: gvrmohanreddy
ms.date: 01/12/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgri
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2017-06-20
ms.openlocfilehash: acb3a6220d146d32bbeb5bd8169033bc897ec3fe
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8871609"
---
# <a name="configure-service-to-service-authentication"></a>Configurare l'autenticazione da servizio a servizio

[!include [banner](includes/banner.md)]

Questo articolo descrive come configurare l'autenticazione da servizio a servizio (S2S) in Microsoft Dynamics 365 Commerce per chiamare in modo sicuro le API di servizio per valutazioni e recensioni.

Dynamics 365 Commerce offre [valutazioni e recensioni](ratings-reviews-overview.md) come soluzione multicanale. Questa soluzione consente l'accesso alle API di servizio dall'esterno di Commerce, in modo che possano essere eseguite varie attività. Queste attività includono l'importazione di valutazioni e recensioni dal tuo sistema esterno in Commerce e l'esportazione di valutazioni e recensioni da Commerce. Per consentire a Commerce di chiamare in modo sicuro le API del servizio di valutazione e recensione, devi prima configurare l'autenticazione S2S completando le procedure in questo articolo.

## <a name="add-a-new-app-registration"></a>Aggiungere una nuova registrazione app

Prima di aggiungere una nuova registrazione per l'app, devi creare un'applicazione utilizzando il [Portale di Azure](https://portal.azure.com). Per registrare un'app in Azure Active Directory (Azure AD) e abilitare l'autenticazione, segui i passaggi in [Uso di Azure Active Directory con un connettore personalizzato in Power Automate](/connectors/custom-connectors/azure-active-directory-authentication).

Raccogli gli ID seguenti dal portale di Azure. Avrai bisogno di questi ID nei passaggi che seguono.

- ID applicazione client
- ID directory client (tenant)

Per aggiungere una nuova registrazione app in Creazione di siti Web di Commerce, segui questi passaggi.

1. Andare a **Home \> Recensioni \> Impostazioni**.
1. Sotto **Autenticazione da servizio a servizio (S2S)**, seleziona **Gestisci**.

    ![Pulsante Gestisci nella sezione Autenticazione da servizio a servizio (S2S) nel generatore di siti di Commerce.](media/Ratings-reviews-settings-service-to-service-authentication.png)

1. Nel riquadro **Voci dell'app S2S** visualizzato a destra, seleziona **Aggiungi una nuova registrazione app S2S**.
1. Nella finestra di dialogo **Aggiungi voce dell'app S2S** immetti le seguenti informazioni richieste. Usa i valori della registrazione dell'applicazione Azure.

    - **Nome** – immetti il nome dell'applicazione (ad esempio **App Fabrikam**).
    - **ID app client** – Immetti l'ID applicazione (ad esempio **00000000-0000-0000-0000-000000000000**).
    - **ID directory (tenant)** – Immetti l'ID directory (ad esempio, **00000000-0000-0000-0000-000000000000**).

    ![Finestra di dialogo Aggiungi voce app S2S nel generatore di siti di Commerce.](media/Ratings-reviews-settings-S2S-APP-entry.png)

1. Selezionare **Invia**. Il nome della tua applicazione appare nell'elenco nel riquadro **Voci app S2S**.
1. Chiudi il riquadro **Voci app S2S**.
1. Seleziona **Salva**.

## <a name="edit-an-existing-app-registration"></a>Modificare la registrazione di un'app esistente

Per modificare la registrazione di un'app esistente in Creazione di siti Web di Commerce, segui questi passaggi.

1. Andare a **Home \> Recensioni \> Impostazioni**.
1. Sotto **Autenticazione da servizio a servizio (S2S)**, seleziona **Gestisci**.
1. Nel riquadro **Voci app S2S** seleziona il simbolo della matita accanto alla voce che vuoi modificare.
1. Aggiorna i valori nei campi **Nome**, **ID app client**, e **ID directory (tenant)** come richiesto.
1. Selezionare **Invia**.
1. Chiudi il riquadro **Voci app S2S**.
1. Seleziona **Salva**.

## <a name="remove-an-existing-app-registration"></a>Rimuovere la registrazione di un'app esistente

Per rimuovere la registrazione di un'app esistente in Creazione di siti Web di Commerce, segui questi passaggi.

1. Andare a **Home \> Recensioni \> Impostazioni**.
1. Sotto **Autenticazione da servizio a servizio (S2S)**, seleziona **Gestisci**.
1. Nel riquadro **Voci app S2S** seleziona il simbolo del cestino accanto alla voce che vuoi rimuovere. La voce viene rimossa dall'elenco.
1. Chiudi il riquadro **Voci app S2S**.
1. Seleziona **Salva**.

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica valutazioni e revisioni](ratings-reviews-overview.md)

[Consentire utilizzo di valutazioni e sulle revisioni](opt-in-ratings-reviews.md)

[Gestire valutazioni e revisioni](manage-reviews.md)

[Configurare valutazioni e revisioni](configure-ratings-reviews.md)

[Sincronizzare valutazioni sul prodotto](sync-product-ratings.md)

[Abilitare la pubblicazione manuale di valutazioni e recensioni da parte di un moderatore](manual-publish-rating-reviews.md)

[Importare ed esportare valutazioni e recensioni](import-export-reviews.md)

[Recensioni e valutazioni - Domande frequenti](ratings-reviews-faq.md) 
