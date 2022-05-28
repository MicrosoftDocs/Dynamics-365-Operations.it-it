---
title: Configurare i pagamenti rapidi per PayPal
description: Questo argomento descrive come configurare i pagamenti rapidi per PayPal per abilitare funzionalità di check out più rapide in Microsoft Dynamics 365 Commerce.
author: BrianShook
ms.date: 05/11/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2017-06-20
ms.openlocfilehash: 5fff17959e7ed9299df169c68b2ed07f6b7c7d2c
ms.sourcegitcommit: e4cc43b06ef3f0f562849e2c960025cb244d6017
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2022
ms.locfileid: "8743575"
---
# <a name="configure-express-payments-for-paypal"></a>Configurare i pagamenti rapidi per PayPal

[!include [banner](../includes/banner.md)]

Questo argomento descrive come configurare i pagamenti rapidi per PayPal per abilitare funzionalità di check out più rapide in Microsoft Dynamics 365 Commerce.

## <a name="key-terms"></a>Termini importanti

| Termine | Description |
|---|---|
| Portafoglio PayPal | L'integrazione e l'esperienza del cliente supportate dal connettore PayPal. È anche noto come il pulsante PayPal. |
| Portafoglio | Un tipo di pagamento che non include le caratteristiche di pagamento tradizionali, come l'intervallo BIN (Bank Identification Number, numero di identificazione della banca) e la data di scadenza, utilizzate per differenziare i tipi di carta di credito e di debito. |
| Pagamento rapido | Un modulo Commerce che supporta un comportamento di check out più rapido quando vengono utilizzati i metodi di pagamento supportati. Questo argomento tratta l'uso del modulo di pagamento rapido con PayPal. |

Dynamics 365 Commerce offre un'integrazione predefinita per Portafoglio PayPal. Quando è configurato Dynamics 365 Payment Connector per PayPal, il pulsante PayPal viene visualizzato come metodo di pagamento selezionabile durante il check out dell'ordine online. Quando gli utenti selezionano PayPal, vengono indirizzati a completare il pagamento direttamente tramite PayPal e vengono quindi riportati al negozio online per completare l'ordine. Il check out del carrello PayPal consente ai clienti di utilizzare le informazioni del proprio conto di pagamento per precompilare il modulo di check out, in modo che possano completare il processo di check out più rapidamente.

Commerce ha aggiunto un modulo di pagamento rapido per facilitare i check out rapidi. Il modulo di pagamento rapido può essere utilizzato in un frammento che può essere incluso in una pagina di check out o carrello. Quando PayPal è configurato, lo stesso riferimento al connettore Dynamics 365 Payment Connector per PayPal viene utilizzato sia per l'opzione di pagamento rapido che per l'opzione di check out normale.

## <a name="paypal-checkout-in-commerce"></a>Check out PayPal in Commerce

### <a name="prerequisites"></a>Prerequisiti

Configurare il portafoglio PayPal per l'ambiente come descritto in [Dynamics 365 Payment Connector per PayPal](../paypal.md).

Se si utilizza PayPal come opzione nel normale flusso di check out (in cui gli utenti inseriscono manualmente le informazioni sul proprio conto senza utilizzare le azioni di precompilazione del pagamento rapido), seguire le istruzioni di configurazione in [Modulo di pagamento](../payment-module.md).

### <a name="payment-express-module-with-paypal"></a>Modulo di pagamento rapido con PayPal

Il modulo di pagamento rapido funziona con i metodi di pagamento di supporto per offrire ai clienti del sito la possibilità di effettuare il check out più rapidamente precompilando le informazioni sul conto del servizio di pagamento durante il processo di check out. Il modulo di pagamento rapido utilizza il connettore di pagamento configurato per precompilare il modulo di check out con i dettagli dell'account utente come l'indirizzo, le informazioni di contatto e il metodo di pagamento selezionato.

Quando viene utilizzato il pagamento rapido PayPal e un utente seleziona il pulsante PayPal nella sezione di pagamento rapido della pagina di check out, si apre una finestra iFrame di pagamento PayPal. L'utente accede quindi al proprio account PayPal per utilizzare l'indirizzo di spedizione, l'indirizzo di fatturazione, l'indirizzo e-mail e il metodo di pagamento PayPal scelto per pagare la transazione.

Dopo che l'utente ha completato l'azione nella finestra di PayPal, viene reindirizzato alla pagina di pagamento del sito Commerce, dove il modulo di check out è precompilato con i dettagli selezionati. Nel flusso di pagamento rapido, la prima opzione di consegna disponibile per l'indirizzo di spedizione restituito sarà precompilata per l'utente. L'utente ha quindi la possibilità di rivedere l'ordine e modificare i dettagli dell'ordine di check out prima di selezionare **Effettua ordine** per finalizzare l'ordine.

### <a name="add-the-payment-express-module-with-paypal-to-a-fragment"></a>Aggiungere il modulo di pagamento rapido con PayPal a un frammento

Per aggiungere il modulo di pagamento rapido con PayPal a un frammento in Creazione di siti di Commerce, effettuare le seguenti operazioni.

1. Andare al sito.
1. Nel riquadro di spostamento a sinistra, selezionare **Frammenti** e quindi **Nuovo**.
1. Nella finestra di dialogo **Nuovo frammento**, trovare e selezionare il modulo **Pagamento rapido**, quindi sotto **Nome frammento**, inserire un nome per il frammento (ad esempio, **Check out rapido**).
1. Selezionare **OK** per creare il frammento.
1. Nella vista struttura, selezionare lo slot del modulo di pagamento rapido creato.
1. Nel riquadro delle proprietà, selezionare **Intestazione**.
1. Nella finestra di dialogo **Intestazione**, nel campo **Testo intestazione**, inserire il testo dell'intestazione da visualizzare per la sezione di check out rapido del sito (ad esempio, **Check out rapido**).
1. In **Livello intestazione**, selezionare il livello di intestazione (ad esempio, **H2**).
1. Seleziona **OK**.
1. Nel riquadro delle proprietà, nel campo **Altezza iFrame**, immettere o regolare l'altezza dell'elemento iFrame (ad esempio, **60**).
1. In campo **Tipi di metodi di pagamento supportati** immettere **PayPal**.
1. Selezionare **Salva**, selezionare **Fine modifica** per archiviare il frammento, quindi selezionare **Pubblica** per pubblicarlo.

### <a name="add-the-payment-express-fragment-to-the-checkout-page"></a>Aggiungere il frammento di pagamento rapido alla pagina di check out

Per aggiungere un frammento di pagamento rapido alla pagina di check out in Creazione di siti, seguire questi passaggi.

1. Andare al sito.
1. Nel riquadro di spostamento a sinistra, selezionare **Pagine**, quindi selezionare la pagina di check out del sito.
1. Selezionare **Modifica** per modificare la pagina.
1. Nello slot **Principale** selezionare i puntini di sospensione (**...**) quindi selezionare **Aggiungi modulo**.
1. Nella finestra di dialogo **Seleziona moduli** selezionare il modulo **Contenitore** e quindi **OK**.

    > [!NOTE]
    > Se esiste già un modulo contenitore che contiene un frammento di check out, spostare la sezione di pagamento rapido in modo che appaia sopra il contenitore di check out esistente nello slot **Principale**. La sezione di pagamento rapido verrà quindi visualizzata sopra il normale contenitore di check out. Per spostare un modulo contenitore verso l'alto o verso il basso, selezionare i puntini di sospensione (**...**), quindi selezionare **Sposta su** o **Sposta giù**.

1. Nel riquadro delle proprietà **Contenitore**, si consiglia di configurare le impostazioni delle proprietà nel modo seguente:

    - **Layout contenitore**: selezionare **In pila**.
    - **Larghezza**: selezionare **Riempi contenitore**.
    - **Figli visualizzati**: selezionare **Tre**.

1. Nello slot **Contenitore** selezionare i puntini di sospensione (**...**), quindi selezionare **Aggiungi frammento**.
1. Nella finestra di dialogo **Seleziona un frammento**, trovare e selezionare il frammento di pagamento rapido creato, quindi selezionare **OK**.
1. Selezionare **Salva**, selezionare **Fine modifica** per archiviare la pagina, quindi selezionare **Pubblica** per pubblicarla.

### <a name="add-the-payment-express-fragment-to-the-cart-page"></a>Aggiungere il frammento di pagamento rapido alla pagina del carrello

Per aggiungere un frammento di pagamento rapido alla pagina del carrello in Creazione di siti, seguire questi passaggi.

1. Andare al sito.
1. Nel riquadro di spostamento a sinistra, selezionare **Pagine**, quindi selezionare la pagina del carrello del sito.
1. Selezionare **Modifica** per modificare la pagina.
1. Nello slot **Principale**, trovare il contenitore che contiene il modulo **Carrello**. Il modulo **Carrello** conterrà uno slot **Pagamento rapido**.
1. Selezionare lo slot **Pagamento rapido**, selezionare i puntini di sospensione (**...**), quindi selezionare **Aggiungi modulo**.
1. Nella finestra di dialogo **Seleziona moduli** selezionare il modulo **Pagamento rapido** e quindi **OK**.
1. Nel riquadro delle proprietà, nel campo **Tipi di metodi di pagamento supportati** immettere **Paypal**.
1. Selezionare **Salva**, selezionare **Fine modifica** per archiviare la pagina, quindi selezionare **Pubblica** per pubblicarla.

### <a name="modes-of-delivery"></a>Modalità di consegna

Quando il modulo di pagamento rapido è configurato per utilizzare PayPal, verrà precompilata la prima opzione di consegna restituita per l'indirizzo di spedizione selezionato per l'account PayPal. Gli utenti potranno modificare l'indirizzo di spedizione se lo desiderano.

L'ordine della modalità di consegna è configurato nella sezione **Modalità di consegna** per il canale in Commerce headquarters. Per ulteriori informazioni, vedi [Impostare modalità di consegna](/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery).

Il modulo di check out utilizzerà anche il modulo delle opzioni di consegna quando le modalità di consegna vengono visualizzate durante il check out. Per ulteriori informazioni, vedere [Modulo Opzioni di consegna](../delivery-options-module.md).

Le modalità di consegna vengono aggiunte all'elenco per il negozio online in Commerce headquarters. Andare a **Vendita al dettaglio e commercio \> Canali \> Negozi online** e selezionare l'ID canale per il negozio. Quindi selezionare **Impostazione \> Modalità di consegna**. Le modalità di consegna del modulo che vengono mostrate nella configurazione appariranno in maniera analoga sul sito. Per aggiungere o rimuovere modalità di consegna per un canale di vendita al dettaglio o un prodotto, selezionare **Gestisci modalità di consegna** nel riquadro azioni.

## <a name="additional-resources"></a>Risorse aggiuntive

[Domande frequenti sui pagamenti](payments-retail.md)

[Modulo checkout](../add-checkout-module.md)

[Modulo pagamento](../payment-module.md)

[Imposta la modalità di consegna](/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery)

[Modulo opzioni di consegna](../delivery-options-module.md)
