---
title: Modulo Checkout
description: In questo argomento viene descritto come aggiungere un modulo Checkout a una pagina e impostare le proprietà necessarie.
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
ms.openlocfilehash: 0d022ad98603b489a133a5b9f2326677e9ebb307
ms.sourcegitcommit: ccb39767bd3430c24f4653c26560bba2cd66553c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2022
ms.locfileid: "8780516"
---
# <a name="checkout-module"></a>Modulo Checkout

[!include [banner](includes/banner.md)]

In questo argomento viene descritto come aggiungere un modulo Checkout a una pagina e impostare le proprietà necessarie.

Un modulo Checkout è un contenitore speciale che ospita tutti i moduli necessari per creare un ordine. Presenta un flusso dettagliato che un cliente utilizza per immettere tutte le informazioni pertinenti per effettuare un acquisto. Acquisisce l'indirizzo di spedizione, il metodo di spedizione e le informazioni di fatturazione. Fornisce inoltre un riepilogo dell'ordine e altre informazioni relative a un ordine cliente.

Un modulo Checkout esegue il rendering dei dati in base all'ID carrello. Questo ID carrello viene salvato come cookie del browser. Un ID carrello è necessario per eseguire il rendering delle informazioni del modulo Checkout, ad esempio gli articoli nell'ordine, l'importo totale e gli sconti. 

L'immagine seguente mostra un esempio di modulo Checkout in una pagina checkout.

![Esempio di modulo Checkout.](./media/Checkout.PNG)

## <a name="checkout-module-properties"></a>Proprietà del modulo Checkout

Un modulo Checkout mostra un riepilogo dell'ordine e fornisce la funzionalità per effettuare un ordine. Per raccogliere tutte le informazioni sul cliente necessarie prima di effettuare un ordine, è necessario aggiungere moduli aggiuntivi al modulo Checkout. Pertanto, i rivenditori hanno la flessibilità di aggiungere moduli personalizzati al flusso di checkout o di escludere moduli, in base alle loro esigenze.

| Nome proprietà | Valori | Descrizione |
|----------------|--------|-------------|
| Intestazione estrazione | Testo e tag dell'intestazione (**H1**, **H2**, **H3**, **H4**, **H5** o **H6**) | Un'intestazione per il modulo Checkout. |
| Intestazione di riepilogo ordini | Testo dell'intestazione | Un'intestazione per la sezione di riepilogo dell'ordine del modulo. |
| Intestazione delle voci del carrello | Testo dell'intestazione | Un'intestazione per le voci del carrello mostrate nel modulo Checkout. |
| Mostra le spese di spedizione su una voce | **True** o **False** | Se questa proprietà è impostata su **True**, le spese di spedizione applicabili per le voci verranno visualizzate nelle righe del carrello. Se la funzione **Spesa intestazione senza ripartizione** è abilitata nella sede in Commerce headquarters, le spese di spedizione verranno applicate a livello dell'intestazione, non a livello di riga. Questa funzione è stata aggiunta nella versione 10.0.13 di Commerce. |

## <a name="modules-that-can-be-used-in-the-checkout-module"></a>Moduli che è possibile utilizzare nel modulo Checkout

- **Indirizzo di spedizione** - Questo modulo consente a un cliente di aggiungere o selezionare l'indirizzo di spedizione per un ordine. Per ulteriori informazioni su questo modulo, vedere il [modulo Indirizzo di spedizione](ship-address-module.md).

    L'immagine seguente mostra un esempio di modulo Indirizzo di spedizione in una pagina checkout.

    ![Esempio di modulo Indirizzo di spedizione.](./media/ecommerce-shippingaddress.PNG)

- **Opzioni di consegna**: questo modulo consente a un cliente di selezionare una modalità di consegna per un ordine. Per ulteriori informazioni su questo modulo, vedere il [modulo Opzioni di consegna](delivery-options-module.md).

    L'immagine seguente mostra un esempio di modulo Opzioni di consegna in una pagina checkout.
 
    ![Esempio di un modulo Opzioni di consegna.](./media/ecommerce-deliveryoptions.PNG)

- **Contenitore sezione checkout** - Questo modulo è un contenitore in cui è possibile includere più moduli allo scopo di creare una sezione nel flusso di checkout. Ad esempio, è possibile inserire tutti i moduli relativi al pagamento in tale contenitore per visualizzarli come un'unica sezione. Questo modulo influisce solo sul layout del flusso.

- **Gift card** - Questo modulo consente a un cliente di pagare un ordine utilizzando una gift card. Per ulteriori informazioni su questo modulo, vedere il [modulo Gift card](add-giftcard.md).

- **Punti fedeltà** - Questo modulo consente a un cliente di pagare un ordine utilizzando i punti fedeltà. Fornisce un riepilogo dei punti disponibili e dei punti in scadenza e consente al cliente di selezionare il numero di punti da utilizzare. Se il cliente non è connesso o non è un membro del programma fedeltà, oppure se l'importo totale nel carrello è 0 (zero) questo modulo viene automaticamente nascosto.

- **Pagamento**: questo modulo consente a un cliente di pagare un ordine utilizzando una carta di credito o di debito. I clienti possono anche fornire un indirizzo di fatturazione per l'opzione di pagamento selezionata. Per ulteriori informazioni su questo modulo, vedere il [modulo Pagamento](payment-module.md).

    L'immagine seguente mostra un esempio di moduli Gift card, Punti fedeltà e Pagamento in una pagina checkout.

    ![Esempio di moduli Gift card, Punti fedeltà e Pagamento in una pagina checkout.](./media/ecommerce-payments.PNG)

- **Informazioni contatto** - Questo modulo consente a un cliente di aggiungere o modificare le informazioni di contatto (indirizzo di posta elettronica) per un ordine.

- **Blocco di testo** - Questo modulo contiene qualsiasi messaggio gestito dal sistema di gestione dei contenuti. Ad esempio, potrebbe contenere un messaggio indicante "Per problemi relativi all'ordine, contattare il numero verde di Fabrikam". 

- **Termini e condizioni di pagamento**: questo modulo mostra il testo RTF che contiene i termini e le condizioni e una casella di controllo per l'input del cliente. La casella di controllo è opzionale e configurabile. L'input viene acquisito dal modulo e può essere utilizzato come verifica prima che venga attivato il posizionamento dell'ordine, ma non è incluso nelle informazioni di riepilogo dell'ordine. Questo modulo può essere aggiunto al contenitore di checkout, al contenitore della sezione di checkout o allo slot di termini e condizioni, in base alle esigenze aziendali. Se viene aggiunto al contenitore di checkout o allo slot del contenitore della sezione di checkout, apparirà come un passaggio del processo di checkout. Se viene aggiunto allo slot Termini e condizioni, apparirà vicino al pulsante di posizionamento dell'ordine.

    L'immagine seguente mostra un esempio di termini e condizioni in una pagina checkout.

    ![Esempio di termini e condizioni in una pagina di checkout.](./media/ecommerce-checkout-terms.PNG)

## <a name="commerce-scale-unit-interaction"></a>Interazione con Commerce Scale Unit

La maggior parte delle informazioni di checkout, come l'indirizzo di spedizione e il metodo di spedizione, è archiviata nel carrello ed elaborata nell'ambito dell'ordine. La sola eccezione è costituita dalle informazioni sulla carta di credito. Queste informazioni vengono elaborate direttamente utilizzando il connettore pagamenti Adyen. Il pagamento è autorizzato, ma non viene addebitato finché l'ordine non viene evaso.

## <a name="add-a-checkout-module-to-a-page-and-set-the-required-properties"></a>Aggiungere un modulo Checkout a una pagina e impostare le proprietà necessarie

Per aggiungere un modulo Checkout a una nuova pagina e impostare le proprietà necessarie, effettuare le seguenti operazioni.

1. Andare a **Frammenti** e selezionare **Nuovo** per creare un nuovo frammento.
1. Nella finestra di dialogo **Seleziona frammento**, seleziona il modulo **Checkout**.
1. Sotto **Nome frammento**, inserire il nome **Frammento checkout**, quindi selezionare **OK**.
1. Selezionare lo slot **Modulo Checkout**.
1. Nel riquadro delle proprietà a destra, selezionare il simbolo della matita, immettere il testo dell'intestazione nel campo, quindi selezionare il simbolo del segno di spunta.
1. Nello slot **Informazioni checkout** seleziona i puntini di sospensione (**...**) quindi seleziona **Aggiungi modulo**.
1. Nella finestra di dialogo **Seleziona moduli**, seleziona i moduli **Indirizzo di spedizione**, **Opzioni di consegna**, **Contenitore sezione checkout** e **Informazioni di contatto**, quindi seleziona **OK**.
1. Nel modulo **Contenitore sezione checkout** seleziona i puntini di sospensione (**...**) quindi seleziona **Aggiungi modulo**.
1. Nella finestra di dialogo **Seleziona moduli** seleziona i moduli **Gift card**, **Punti fedeltà** e **Pagamento**, quindi seleziona **OK**. In questo modo, si garantisce la visualizzazione di tutti i metodi di pagamento in un'unica sezione.
1. Nello slot **Termini e condizioni**, aggiungere un modulo **Termini e condizioni di pagamento** se è richiesto. Nel riquadro delle proprietà del modulo, configurare i termini e il testo delle condizioni come appropriato.
1. Selezionare **Salva**, quindi selezionare **Anteprima** per visualizzare l'anteprima del frammento. È possibile che l'anteprima di alcuni moduli che non hanno un contesto carrello non sia visualizzata.
1. Selezionare **Fine modifica** per archiviare il frammento, quindi selezionare **Pubblica** per pubblicarlo.
1. Creare un modello che utilizza il nuovo frammento checkout.
1. Creare una pagina checkout che utilizza il nuovo modello.

## <a name="additional-resources"></a>Risorse aggiuntive

[Modulo carrello](add-cart-module.md)

[Modulo icona carrello](cart-icon-module.md)

[Modulo pagamento](payment-module.md)

[Modulo indirizzo di spedizione](ship-address-module.md)

[Modulo opzioni di consegna](delivery-options-module.md)

[Modulo di informazioni sul ritiro](pickup-info-module.md)

[Modulo Dettagli ordini](order-confirmation-module.md)

[Modulo gift card](add-giftcard.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
