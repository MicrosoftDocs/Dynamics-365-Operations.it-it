---
title: Modulo carrello
description: In questo articolo vengono descritti i moduli Carrello e la procedura per aggiungerli alle pagine di siti Web in Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 05/18/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.search.industry: ''
ms.search.form: ''
ms.openlocfilehash: f3bf61d03d6e318494a13af6721028ac573d7424
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9277060"
---
# <a name="cart-module"></a>Modulo carrello

[!include [banner](includes/banner.md)]

In questo articolo vengono descritti i moduli Carrello e la procedura per aggiungerli alle pagine di siti Web in Microsoft Dynamics 365 Commerce.

Un modulo Carrello mostra gli articoli che sono stati aggiunti al carrello prima che il cliente proceda al checkout. Il modulo mostra anche un riepilogo dell'ordine e consente al cliente di applicare o rimuovere codici promozionali.

Il modulo Carrello supporta il checkout come utente connesso e il checkout come guest. Supporta inoltre il collegamento **Continua gli acquisti**. È possibile configurare la route per questo collegamento in **Impostazioni sito \> Estensioni \> Route**.

Il modulo Carrello visualizza i dati in base all'ID carrello, che è un cookie del browser disponibile in tutto il sito. 

L'immagine seguente mostra un esempio di una pagina del carrello sul sito Fabrikam.

![Esempio di un modulo carrello sul sito Fabrikam.](./media/cart2.PNG)

L'immagine seguente mostra un esempio di una pagina del carrello sul sito Fabrikam. In questo esempio, è prevista una commissione di gestione per una voce.

![Esempio di un modulo carrello con una commissione di gestione per una voce.](./media/ecommerce-handling-fee.png)

## <a name="cart-module-properties-and-slots"></a>Proprietà e slot del modulo Carrello

| Proprietà | Valori | descrizione |
|----------------|--------|-------------|
| Intestazione | Testo e tag dell'intestazione (**H1**, **H2**, **H3**, **H4**, **H5** o **H6**) | Un'intestazione per il carrello, ad esempio "Carrello della spesa" o "Articoli nel carrello". |
| Mostra errori scorte esaurite | **True** o **False** | Se questa proprietà è impostata su **True**, la pagina del carrello mostrerà errori relativi alle scorte. Ti consigliamo di impostare questa proprietà su **True** se le verifiche delle scorte disponibili vengono applicate sul sito. |
| Mostra spese di spedizione per voci | **True** o **False** | Se questa proprietà è impostata su **True**, le voci del carrello mostreranno le spese di spedizione, se queste informazioni sono disponibili. Questa funzione non è supportata nel tema Fabrikam, perché gli utenti selezionano la spedizione solo nel flusso di checkout. Tuttavia, questa funzione può essere abililtata in altri flussi di lavoro, se applicabile. |
| Mostra promozioni disponibili| **True** o **False** | Se questa proprietà è impostata su **True**, il carrello mostra le promozioni disponibili, in base agli articoli nel carrello. Questa capacità è disponibile nella versione 10.0.16 di Dynamics 365 Commerce. |

## <a name="modules-that-can-be-used-in-a-cart-module"></a>Moduli che è possibile utilizzare in un modulo Carrello

- **Blocco di testo** - Questo modulo supporta messaggistica personalizzata nel modulo Carrello. I messaggi sono gestiti dal sistema di gestione dei contenuti. È possibile aggiungere un messaggio qualsiasi, ad esempio "Per problemi relativi all'ordine, contattare il numero verde di Fabrikam".
- **Selettore punto vendita** - Questo modulo visualizza un elenco dei punti vendita vicini in cui un articolo è disponibile per il ritiro. Consente agli utenti di immettere un'ubicazione per trovare punti vendita nelle vicinanze. Per ulteriori informazioni su questo modulo, vedere [Modulo Selettore punto vendita](store-selector.md).

## <a name="module-properties"></a>Proprietà del modulo

Le seguenti impostazioni del modulo Carrello possono essere configurate in **Impostazioni sito \> Estensioni**:

- **Quantità massima** - Questa proprietà viene utilizzata per specificare il numero massimo di pezzi di ogni articolo che possono essere aggiunti al carrello. Ad esempio, un rivenditore potrebbe decidere che solo 10 pezzi di ogni prodotto possono essere venduti in una singola transazione.
- **Scorte** - Per informazioni su come applicare le impostazioni relative alle scorte, vedere [Applicare le impostazioni relative alle scorte](inventory-settings.md).
- **Continua gli acquisti** - Questa proprietà viene utilizzata per specificare la route per il collegamento **Continua gli acquisti**. Il ciclo di lavorazione può essere configurato a livello di sito, consentendo ai rivenditori al dettaglio di riportare il cliente sulla home page o su qualsiasi altra pagina del sito.

> [!IMPORTANT]
> In Dynamics 365 Commerce versione 10.0.14 e successive, gli articoli nel carrello vengono aggregati in base alle impostazioni definite nel profilo delle funzionalità online per il punto vendita online in Commerce headquarters. Per ulteriori informazioni su come creare un profilo di funzionalità online e impostare le proprietà richieste per l'aggregazione, vedere [Creare un profilo di funzionalità online](online-functionality-profile.md).

## <a name="commerce-scale-unit-interaction"></a>Interazione con Commerce Scale Unit

Il modulo Carrello recupera le informazioni sul prodotto utilizzando le API di Commerce Scale Unit. L'ID carrello del cookie del browser viene utilizzato per recuperare tutte le informazioni sui prodotti da Commerce Scale Unit.

## <a name="add-a-cart-module-to-a-page"></a>Aggiungere un modulo Carrello a una pagina

Per aggiungere un modulo Carrello a una nuova pagina e impostare le proprietà necessarie, effettuare le seguenti operazioni.

1. Andare a **Frammenti** e selezionare **Nuovo** per creare un nuovo frammento.
1. Nella finestra di dialogo **Seleziona frammento**, seleziona il modulo **Carrello**.
1. In **Nome frammento**, inserire il nome **Frammento carrello**, quindi selezionare **OK**.
1. Selezionare lo slot **Carrello**.
1. Nel riquadro delle proprietà a destra, selezionare il simbolo della matita, immettere il testo dell'intestazione nel campo, quindi selezionare il simbolo del segno di spunta.
1. Nello slot **Carrello** seleziona i puntini di sospensione (**...**) quindi seleziona **Aggiungi modulo**.
1. Nella finestra di dialogo **Seleziona moduli** seleziona il modulo **Selettore punto vendita** e quindi seleziona **OK**.
1. Selezionare **Salva**, selezionare **Fine modifica** per archiviare il frammento, quindi selezionare **Pubblica** per pubblicarlo.
1. Andare a **Modelli** e selezionare **Nuovo** per creare un nuovo modello.
1. Nella finestra di dialogo **Nuovo modello**, sotto **Nome modello**, immettere un nome per il modello.
1. Nell'albero, selezionare lo slot **Corpo**, selezionare i puntini di sospensione (**...**) e quindi **Aggiungi frammento**.
1. Nella finestra di dialogo **Seleziona frammento** selezionare il frammento **Frammento carrello** e quindi selezionare **OK**.
1. Selezionare **Salva**, selezionare **Fine modifica** per archiviare il modello, quindi selezionare **Pubblica** per pubblicarlo.
1. Andare a **Pagine** e quindi selezionare **Nuovo** per creare una nuova pagina.
1. Nella finestra di dialogo **Scegli un modello**, selezionare il modello creato, quindi immettere un nome di pagina e selezionare **OK**.
1. Selezionare **Salva**, quindi selezionare **Anteprima** per visualizzare l'anteprima della pagina.
1. Selezionare **Fine modifica** per archiviare la pagina, quindi selezionare **Pubblica** per pubblicarla.

## <a name="additional-resources"></a>Risorse aggiuntive

[Modulo icona carrello](cart-icon-module.md)

[Modulo checkout](add-checkout-module.md)

[Modulo pagamento](payment-module.md)

[Modulo indirizzo di spedizione](ship-address-module.md)

[Modulo opzioni di consegna](delivery-options-module.md)

[Modulo di informazioni sul ritiro](pickup-info-module.md)

[Modulo Dettagli ordini](order-confirmation-module.md)

[Modulo gift card](add-giftcard.md)

[Calcolare la disponibilità scorte per i canali di vendita al dettaglio](calculated-inventory-retail-channels.md)

[Creare un profilo funzionalità online](online-functionality-profile.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
