---
title: Modulo Dettagli ordini
description: In questo argomento vengono descritti i moduli Dettagli ordine e la procedura per utilizzarli in Microsoft Dynamics 365 Commerce.
author: anupamar
manager: annbe
ms.date: 06/18/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar-ms
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: c2ec629d9fd027be01652351ab1c99001e063e30
ms.sourcegitcommit: 49656661c89c864e8e067259a601c3bbceb8bef4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/18/2020
ms.locfileid: "3464932"
---
# <a name="order-details-module"></a>Modulo Dettagli ordini


[!include [banner](includes/banner.md)]

In questo argomento vengono descritti i moduli Dettagli ordine e la procedura per utilizzarli in Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Panoramica

Il modulo Dettagli ordine viene utilizzato per visualizzare i dettagli di conferma di un ordine dopo l'esecuzione dell'ordine. Mostra l'ID di conferma dell'ordine, le informazioni di contatto dell'ordine e altri dettagli, come gli articoli acquistati, le informazioni di pagamento e il metodo di spedizione.

## <a name="order-details-module-properties"></a>Proprietà del modulo Dettagli ordine

| Nome proprietà  | Valori | descrizione |
|----------------|--------|-------------|
| Intestazione        | Testo e tag di intestazione (**H1**, **H2**, **H3**, **H4**, **H5** o **H6**), | Il modulo Dettagli ordine può avere un'intestazione. Per impostazione predefinita, il tag di intestazione **H2** è utilizzato per l'intestazione. Tuttavia, il tag può essere modificato per soddisfare i requisiti di accessibilità. |
| Numero contatto | Text | È possibile fornire un numero di contatto per domande relative all'ordine. |

## <a name="modules-that-can-be-used-on-an-order-details-page"></a>Moduli che possono essere utilizzati in una pagina Dettagli ordine

Quando si crea una pagina Dettagli ordine, è possibile aggiungere altri moduli pertinenti oltre al modulo Dettagli ordine. Di seguito sono riportati alcuni esempi.

- **Modulo Suggerimenti** - Il modulo Suggerimenti può essere aggiunto alla pagina Dettagli ordine per suggerire altri prodotti al cliente.
- **Moduli Marketing** - È possibile aggiungere qualsiasi modulo Marketing alla pagina Dettagli ordine per visualizzare contenuti di marketing.

## <a name="add-an-order-details-module-to-a-page"></a>Aggiungi un un modulo Dettagli ordine a una pagina

Per aggiungere un modulo Dettagli ordine a una nuova pagina e impostare le proprietà necessarie, effettua le seguenti operazioni.

1. Andare a **Modelli** e selezionare **Nuovo** per creare un nuovo modello.
1. Nella finestra di dialogo **Nuovo modello**, sotto **Nome modello**, immetti un nome per **Modello Dettagli ordine**, quindi seleziona **OK**.
1. Nello slot **Corpo** selezionare i puntini di sospensione (**...**), quindi selezionare **Aggiungi modulo**.
1. Nella finestra di dialogo **Aggiungi modulo** selezionare il modulo **Pagina predefinita** e quindi selezionare **OK**.
1. Nello slot **Principale** del modulo **Pagina predefinita**, selezionare i puntini di sospensione (**...**) e quindi **Aggiungi modulo**.
1. Nella finestra di dialogo **Aggiungi modulo**, seleziona il modulo **Dettagli ordine** quindi **OK**.
1. Seleziona **Salva**, quindi **Anteprima** per visualizzare l'anteprima del modello. Il rendering del modulo Dettagli ordine non verrà eseguito in quanto richiede il contesto del numero di conferma ordine.
1. Selezionare **Fine modifica** per archiviare il modello, quindi selezionare **Pubblica** per pubblicarlo.
1. Andare a **Pagine** e quindi selezionare **Nuovo** per creare una nuova pagina.
1. Nella finestra di dialogo **Scegli un modello**, seleziona **Modello dettagli ordine**. Sotto **Nome pagina**, immetti **Pagina dettagli ordine** e seleziona **OK**.
1. Nello slot **Principale** del modulo **Pagina predefinita**, selezionare i puntini di sospensione (**...**) e quindi **Aggiungi modulo**.
1. Nella finestra di dialogo **Aggiungi modulo**, seleziona il modulo **Dettagli ordine** quindi **OK**.
1. Nel riquadro delle proprietà del modulo Dettagli ordine, seleziona **Intestazione** accanto al simbolo della matita.
1. Nel campo **Titolo dell'intestazione** della finestra di dialogo **Intestazione**, immetti il testo dell'intestazione **Dettagli ordine**, quindi seleziona **OK**.
1. Selezionare **Salva**, quindi selezionare **Anteprima** per visualizzare l'anteprima della pagina.
1. Selezionare **Fine modifica** per archiviare la pagina, quindi selezionare **Pubblica** per pubblicarla.

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica starter kit](starter-kit-overview.md)

[Modulo contenitore](add-container-module.md)

[Modulo Casella acquisti](add-buy-box.md)

[Modulo Carrello](add-cart-module.md)

[Modulo Checkout](add-checkout-module.md)

[Modulo Intestazione](author-header-module.md)

[Modulo Piè di pagina](author-footer-module.md)
