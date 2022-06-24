---
title: Modulo conferma ordine
description: In questo articolo vengono descritti i moduli Conferma ordine e la procedura per usarli in Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 05/18/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 994ec92abc53efeb240bca5dc8d67aabb45fbe55
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8845780"
---
# <a name="order-confirmation-module"></a>Modulo conferma ordine

[!include [banner](includes/banner.md)]

In questo articolo vengono descritti i moduli Conferma ordine e la procedura per usarli in Microsoft Dynamics 365 Commerce.

Il modulo Conferma ordine viene utilizzato per visualizzare i dettagli di conferma di un ordine dopo l'esecuzione dell'ordine. Mostra l'ID di conferma dell'ordine, le informazioni di contatto dell'ordine e altri dettagli, come gli articoli acquistati, le informazioni di pagamento, le opzioni di ritiro e il metodo di spedizione.

## <a name="order-confirmation-module-properties"></a>Proprietà del modulo Conferma ordine

| Nome proprietà  | Valori | Descrizione |
|----------------|--------|-------------|
| Intestazione        | Testo e tag di intestazione (**H1**, **H2**, **H3**, **H4**, **H5** o **H6**), | Il modulo Conferma ordine può avere un'intestazione. Per impostazione predefinita, il tag di intestazione **H2** è utilizzato per l'intestazione. Tuttavia, il tag può essere modificato per soddisfare i requisiti di accessibilità. |
| Numero contatto | Text | È possibile fornire un numero di contatto per domande relative all'ordine. |
| Mostrare le informazioni sulla fascia oraria per il ritiro | True o false | Questa proprietà è disponibile in Dynamics 365 Commerce 10.0.15 e versioni successive. Quando è impostata su vero, visualizza le informazioni sulla fascia oraria per il ritiro se fornite per un articolo da ritirare|

## <a name="modules-that-can-be-used-on-an-order-confirmation-page"></a>Moduli che possono essere utilizzati in una pagina Conferma ordine

Quando si crea una pagina Conferma ordine, è possibile aggiungere altri moduli pertinenti oltre al modulo Conferma ordine. Di seguito sono riportati alcuni esempi.

- **Modulo Suggerimenti** - Il modulo Suggerimenti può essere aggiunto alla pagina Conferma ordine per suggerire altri prodotti al cliente.
- **Moduli Marketing** - È possibile aggiungere qualsiasi modulo Marketing alla pagina Conferma ordine per visualizzare contenuti di marketing.

## <a name="add-an-order-confirmation-module-to-a-page"></a>Aggiungere un un modulo Conferma ordine a una pagina

Per aggiungere un modulo Conferma ordine a una nuova pagina e impostare le proprietà necessarie, effettuare le seguenti operazioni.

1. Andare a **Modelli** e selezionare **Nuovo** per creare un nuovo modello.
1. Nella finestra di dialogo **Nuovo modello**, sotto **Nome modello**, immetti un nome per **Modello Conferma ordine**, quindi seleziona **OK**.
1. Nello slot **Corpo** seleziona i puntini di sospensione (**...**) quindi seleziona **Aggiungi modulo**.
1. Nella finestra di dialogo **Seleziona moduli** seleziona il modulo **Pagina predefinita** e quindi seleziona **OK**.
1. Nello slot **Principale** del modulo **Pagina predefinita**, seleziona i puntini di sospensione (**...**) e quindi **Aggiungi modulo**.
1. Nella finestra di dialogo **Seleziona moduli**, seleziona il modulo **Conferma ordine** quindi **OK**.
1. Seleziona **Salva**, quindi **Anteprima** per visualizzare l'anteprima del modello. Non si deve eseguire il rendering del modulo Conferma ordine in quanto richiede il contesto del numero di conferma ordine.
1. Selezionare **Fine modifica** per archiviare il modello, quindi selezionare **Pubblica** per pubblicarlo.
1. Accedi a **Pagine** e quindi seleziona **Nuovo** per creare una nuova pagina.
1. Nella finestra di dialogo **Crea una nuova pagina**, sotto **Nome pagina**, immetti **Pagina conferma ordine**, quindi seleziona **Avanti**.
1. In **Scegli un modello**, seleziona **Modello Conferma ordine**, e seleziona **Avanti**.
1. Sotto **Scegli un layout**, seleziona un layout di pagina (ad esempio, **Layout flessibile**), quindi seleziona **Avanti**.
1. Sotto **Verifica e termina**, rivedi la configurazione della pagina. Se è necessario modificare le informazioni sulla pagina, seleziona **Indietro**. Se le informazioni sulla pagina sono corrette, seleziona **Crea pagina**. 
1. Nello slot **Principale** del modulo **Pagina predefinita**, seleziona i puntini di sospensione (**...**) e quindi **Aggiungi modulo**.
1. Nella finestra di dialogo **Seleziona moduli**, seleziona il modulo **Conferma ordine** quindi **OK**.
1. Nel riquadro delle proprietà del modulo Conferma ordine, selezionare **Intestazione** accanto al simbolo della matita.
1. Nel campo **Titolo dell'intestazione** della finestra di dialogo **Intestazione**, immettere il testo dell'intestazione **Conferma ordine**, quindi selezionare **OK**.
1. Selezionare **Salva**, quindi selezionare **Anteprima** per visualizzare l'anteprima della pagina.
1. Selezionare **Fine modifica** per archiviare la pagina, quindi selezionare **Pubblica** per pubblicarla.

## <a name="additional-resources"></a>Risorse aggiuntive

[Modulo carrello](add-cart-module.md)

[Modulo icona carrello](cart-icon-module.md)

[Modulo checkout](add-checkout-module.md)

[Modulo pagamento](payment-module.md)

[Modulo indirizzo di spedizione](ship-address-module.md)

[Modulo opzioni di consegna](delivery-options-module.md)

[Modulo di informazioni sul ritiro](pickup-info-module.md)

[Modulo gift card](add-giftcard.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
