---
title: Importare ed esportare valutazioni e recensioni
description: Questo argomento descrive come importare ed esportare valutazioni e recensioni dei prodotti in Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 01/12/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgri
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2017-06-20
ms.openlocfilehash: 3ae85f21f7a78d56621aed60527207badcee9c75
ms.sourcegitcommit: 7adf9ad53b4e6d1c4d5d612ce0977b76c61ec173
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/13/2022
ms.locfileid: "7968531"
---
# <a name="import-and-export-ratings-and-reviews"></a>Importare ed esportare valutazioni e recensioni

[!include [banner](includes/banner.md)]

Questo argomento descrive come importare ed esportare valutazioni e recensioni dei prodotti in Microsoft Dynamics 365 Commerce.

Dynamics 365 Commerce offre [valutazioni e recensioni](ratings-reviews-overview.md) come soluzione multicanale. Quando passi alla soluzione di valutazioni e recensioni di Dynamics 365 Commerce, potresti voler spostare i dati di valutazioni e recensioni esistenti sulla piattaforma Commerce. Potresti anche voler esportare i dati di valutazioni e recensioni da Commerce, in base ai tuoi requisiti aziendali. Un connettore Power Automate ti consente di importare valutazioni e recensioni in Commerce ed esportarle da Commerce.

> [!NOTE]
> Per informazioni su come iniziare con i flussi logici in Power Automate, vedi [Creare un flusso cloud in Power Automate](/power-automate/get-started-logic-flow).

## <a name="prerequisites"></a>Prerequisiti

Prima di poter importare ed esportare valutazioni e recensioni, devi soddisfare i seguenti prerequisiti:

- La soluzione di valutazioni e recensioni deve essere abilitata per il tuo sito e-commerce sulla piattaforma Commerce. Per ulteriori informazioni, vedi [Consenso esplicito per l'uso di valutazioni e recensioni](opt-in-ratings-reviews.md).
- Il connettore Power App di valutazioni e recensioni Dynamics 365 deve essere configurato per abilitare le azioni "invia recensioni" o "esporta recensioni" in Power Automate. Per ulteriori informazioni, vedi [Dynamics 365 Commerce - Valutazioni e recensioni (anteprima)](/connectors/dynamics365ratingsre/).
- L'autenticazione da servizio a servizio (S2S) deve essere configurata per chiamare in modo sicuro l'API (Application Programming Interface) di valutazione e recensione dall'esterno di Commerce. Per ulteriori informazioni, vedi [Configurare l'autenticazione da servizio a servizio](service-to-service-auth.md).

## <a name="import-ratings-and-reviews"></a>Importare valutazioni e revisioni

Per importare i dati di valutazioni e recensioni dal tuo sistema esistente in Commerce, devi aggiungere il connettore Power Automate di valutazioni e recensioni Dynamics 365 a un flusso Power Automate nuovo o esistente. Per ulteriori informazioni, vedi [Dynamics 365 Commerce - Valutazioni e recensioni (anteprima)](/connectors/dynamics365ratingsre/).

> [!IMPORTANT]
> Prima di completare questa procedura è necessario [configurare l'autenticazione S2S](service-to-service-auth.md).

Per importare valutazioni e recensioni in Commerce utilizzando il connettore Power Automate di valutazioni e recensioni Dynamics 365, attientiti alla seguente procedura.

1. Seleziona l'azione **Invia recensione utente**.
1. Stabilisci una connessione utilizzando le informazioni dell'app Azure Active Directory (Azure AD) create durante la configurazione dell'autenticazione S2S. Per ulteriori informazioni, vedi [Configurare l'autenticazione da servizio a servizio](service-to-service-auth.md).
1. L'azione **Invia recensione utente** richiede una recensione alla volta. Pertanto, ripeti l'azione. Utilizza le recensioni di origine come elenco per inviare recensioni in blocco.
    
## <a name="export-ratings-and-reviews"></a>Esportare valutazioni e revisioni

Per esportare i dati di valutazioni e recensioni da Commerce, devi aggiungere il connettore Power Automate di valutazioni e recensioni Dynamics 365 a un flusso Power Automate nuovo o esistente. Per ulteriori informazioni, vedi [Dynamics 365 Commerce - Valutazioni e recensioni (anteprima)](/connectors/dynamics365ratingsre/).

Per esportare valutazioni e recensioni da Commerce utilizzando il connettore Power Automate di valutazioni e recensioni Dynamics 365, attientiti alla seguente procedura.

1. Seleziona l'azione **Esporta tutte le recensioni**.
1. Completa l'azione. 

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica valutazioni e revisioni](ratings-reviews-overview.md)

[Consentire utilizzo di valutazioni e sulle revisioni](opt-in-ratings-reviews.md)

[Gestire valutazioni e revisioni](manage-reviews.md)

[Configurare valutazioni e revisioni](configure-ratings-reviews.md)

[Sincronizzare valutazioni sul prodotto](sync-product-ratings.md)

[Abilitare la pubblicazione manuale di valutazioni e recensioni da parte di un moderatore](manual-publish-rating-reviews.md)

[Configurare l'autenticazione da servizio a servizio](service-to-service-auth.md)

[Recensioni e valutazioni - Domande frequenti](ratings-reviews-faq.md)
