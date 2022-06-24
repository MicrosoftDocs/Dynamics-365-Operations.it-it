---
title: Applicare le impostazioni Aggiungi prodotto a carrello
description: In questo articolo vengono descritte le impostazioni "Aggiungi prodotto a carrello" e la procedura per applicarle in Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 07/08/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 336bea289b22e4f6f98077f915d7d35f2a48682d
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8866032"
---
# <a name="apply-add-product-to-cart-settings"></a>Applicare le impostazioni Aggiungi prodotto a carrello

[!include [banner](includes/banner.md)]

In questo articolo vengono descritte le impostazioni **Aggiungi prodotto a carrello** e la procedura per applicarle in Microsoft Dynamics 365 Commerce.

Sono supportati diversi flussi di lavoro quando un prodotto viene aggiunto al carrello su un sito di e-commerce di Dynamics 365 Commerce. Ad esempio, l'utente del sito potrebbe essere indirizzato alla pagina del carrello. In alternativa, l'utente potrebbe rimanere sulla pagina corrente, ma ricevere una notifica che conferma che il prodotto è stato aggiunto al carrello.

Per supportare i diversi flussi di lavoro, un campo **Aggiungi prodotto a carrello** è disponibile su **Impostazioni \> Estensioni** in Creazione di siti di Commerce. Selezionare una delle seguenti opzioni di impostazione per implementare il flusso di lavoro corrispondente:

- **Vai alla pagina del carrello** - Quando gli utenti aggiungono un articolo al carrello, accedono alla pagina del carrello.
- **Mostra notifica** - Quando gli utenti aggiungono un articolo al carrello, ricevono una notifica di conferma e possono continuare a navigare nella pagina dettagli prodotto (PDP).
- **Mostra mini carrello** - Quando gli utenti aggiungono un articolo al carrello, viene mostrato il contenuto del mini carrello. Gli utenti possono rivedere tutti gli articoli nel carrello e possono procedere al pagamento se sono pronti.
- **Mostra notifica utilizzando il modulo Notifiche** - Quando gli utenti aggiungono un articolo al carrello, il modulo delle notifiche viene utilizzato per mostrare una notifica di conferma. Affinché questa opzione di impostazione funzioni, il modulo delle notifiche deve essere aggiunto all'intestazione della pagina.
- **Non andare alla pagina del carrello** - Quando gli utenti aggiungono un articolo al carrello, rimangono sulla pagina corrente.

L'illustrazione seguente mostra un esempio delle opzioni di impostazione **Aggiungi prodotto a carrello** in Creazione di siti Web.

![Esempio di opzioni di impostazione Aggiungi prodotto a carrello in Creazione di siti Web](./media/AW_sitesettings.PNG)

> [!IMPORTANT]
> - Le impostazioni del sito **Aggiungi prodotto a carrello** sono disponibili a partire da Dynamics 365 Commerce versione 10.0.11. Se stai aggiornando da una versione precedente di Dynamics 365 Commerce, devi aggiornare manualmente il file appsettings.json. Per informazioni su come aggiornare il file appsettings.json, vedere [SDK e aggiornamenti della libreria moduli](e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).
> - L'opzione di impostazione **Mostra mini carrello** è disponibile a partire da Dynamics 365 Commerce, versione 10.0.20. Se stai aggiornando da una versione precedente di Dynamics 365 Commerce, devi aggiornare manualmente il file appsettings.json. Per informazioni su come aggiornare il file appsettings.json, vedere [SDK e aggiornamenti della libreria moduli](e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).

L'immagine seguente mostra un esempio di notifica di conferma "aggiunto al carrello" sul sito di Fabrikam.

![Esempio di notifica di conferma "aggiunto al carrello" sul sito di Fabrikam](./media/ecommerce-addtocart-notifications.PNG)

L'immagine seguente mostra un esempio di notifica di conferma "aggiunto al carrello" sul sito di Adventure Works.

![Esempio di notifica di conferma "aggiunto al carrello" sul sito di Adventure Works](./media/AW_minicart.PNG)

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica della libreria moduli](starter-kit-overview.md)

[Modulo casella acquisti](add-buy-box.md)

[Memorizzare il modulo di selezione](store-selector.md)
