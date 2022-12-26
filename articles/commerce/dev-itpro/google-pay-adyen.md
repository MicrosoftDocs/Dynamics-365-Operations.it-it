---
title: Configurare Google Pay con Adyen
description: Questo articolo descrive come configurare Google Pay con Adyen in Microsoft Dynamics 365 Commerce.
author: BrianShook
ms.date: 07/05/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2017-06-20
ms.openlocfilehash: cdf950fc7b3720543d93e108d4e3c3c2ab254e09
ms.sourcegitcommit: bdee5e642d417a13abdb778c14ec5f2dbbf8dee7
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2022
ms.locfileid: "9838393"
---
# <a name="configure-google-pay-with-adyen"></a>Configurare Google Pay con Adyen

[!include [banner](../includes/banner.md)]

Questo articolo descrive come configurare Google Pay con Adyen in Microsoft Dynamics 365 Commerce.

Dynamics 365 Commerce fornisce una soluzione pronta per l'integrazione Google Pay quando si usa il servizio gateway per i pagamenti Ayden. Google Pay è un metodo di pagamento tramite portafoglio digitale che usa un conto esercente Google Pay congiuntamente al servizio di pagamento Ayden. Quando è configurato, il pulsante Google Pay è disponibile come metodo di pagamento selezionato durante il checkout degli ordini online. Quando gli utenti selezionano **Google Pay** in un browser o in un dispositivo supportato, vengono indirizzati al servizio Google Pay per completare il pagamento. Vengono quindi riportati alla vetrina online per completare l'ordine.

Quando si usa Google Pay con il modulo di checkout rapido in Commerce, le informazioni sul conto di pagamento dell'utente vengono automaticamente precompilate nel modulo di checkout per velocizzare il processo di checkout dell'utente. Commerce include un modulo di pagamento rapido che abilita il comportamento di checkout rapido. Il modulo di pagamento rapido può essere utilizzato in un frammento incluso in una pagina di checkout o del carrello. Viene usato il riferimento al connettore Dynamics 365 Payment Connector per Google Pay oltre a Dynamics 365 Payment Connector per Adyen per abilitare entrambe le opzioni di checkout rapido e normale per il pagamento quando è configurato PayPal. Google Pay può essere configurato con i terminali di pagamento Adyen e con il POS di Commerce per l'uso nel punto vendita.

## <a name="key-terms"></a>Termini importanti

| Termine | Description |
|---|---|
| Google Pay | Noto anche come "pulsante" Google Pay", Google Pay è un'offerta di pagamento tramite portafoglio supportata mediante il connettore Adyen. Fornisce l'integrazione e l'esperienza del cliente supportate dal connettore Google Pay di Dynamics. |
| Portafoglio | Un tipo di pagamento che non include le caratteristiche di pagamento tradizionali, come l'intervallo BIN (Bank Identification Number, numero di identificazione della banca) e la data di scadenza, usate per differenziare i tipi di carta di credito e di debito. |
| Modulo di pagamento rapido | Un modulo Dynamics 365 Commerce che supporta un comportamento di checkout più rapido con i metodi di pagamento supportati. |

## <a name="prerequisites"></a>Prerequisiti

Per usare Google Pay con Adyen in Commerce è necessario disporre di un conto esercente Google. Per informazioni su come impostare il tuo conto esercente Google, vedi [Documentazione Adyen in Google Pay](https://docs.adyen.com/payment-methods/google-pay/) e la [checklist di integrazione](https://developers.google.com/pay/api/web/guides/test-and-deploy/integration-checklist) di Google.

Il metodo di pagamento Google Pay deve inoltre essere integrato con il tuo conto Adyen. Per istruzioni sul collegamento di integrazione, vedi [Adyen Google Pay](https://www.adyen.com/payment-methods/google-pay).

Devi inoltre abilitare la funzionalità di portafoglio avanzato in Dynamics 365 Commerce Headquarters. Vai ad **Aree di lavoro \> Gestione funzionalità**, cerca la funzionalità **Supporto portafoglio avanzato e miglioramenti dei pagamenti**, seleziona la funzionalità, quindi seleziona **Abilita**. Una volta abilitata la funzionalità, esegui la pianificazione della distribuzione **1110** per rendere disponibile la modifica in tutti i canali.

## <a name="map-the-google-pay-payment-method"></a>Mappare il metodo di pagamento Google Pay

Google Pay è un metodo di pagamento tramite portafoglio digitale. Per informazioni su come configurare il mapping dei pagamenti per Google Pay, vedi [Supporto del pagamento tramite portafoglio](../wallets.md).

Per mappare il metodo di pagamento Google Pay ai tipi di metodi di pagamento tramite carta per POS e canali online, segui questa procedura.

1. In Commerce headquarters accedi a **Vendita al dettaglio e commercio \> Impostazione canale \> Metodi di pagamento \> Tipi di carte**.
1. Seleziona **Nuovo** per aggiungere una riga per Google Pay.
1. Nel campo **ID** immetti **GooglePay**.
1. Nel campo **Nome pagamento elettronico** immetti **Google Pay**.
1. Nel campo **Tipo** immetti **Portafoglio**.
1. Nel campo **Emittente** immetti **Google**.
1. Nel riquadro Azioni seleziona **Mapping processore** per aprire la finestra di dialogo **Mapping del metodo di pagamento del processore**.
1. In **Metodi di pagamento del processore non mappati** viene riportato un elenco di metodi di pagamento del processore non mappati, ognuno dei quali accoppiato al connettore appropriato. Per mappare i metodi di pagamento del processore Google Pay non mappati ai tipi di metodi di pagamento tramite carta, attieniti alla seguente procedura per ciascun tipo di metodo di pagamento tramite carta:

    1. In **Tipi di metodi di pagamento tramite carta**, seleziona un metodo di pagamento tramite carta.
    1. Nella colonna **Metodi di pagamento del processore non mappati**, seleziona entrambi i connettori **Dynamics 365 Payment Connector per Adyen** (da usare per il POS) che **Dynamics 365 Payment Connector per Google Pay** (da usare per i canali online).
    1. Seleziona **Aggiungi**. Le selezioni vengono aggiunte alla colonna **Metodi di pagamento del processore mappati**.

1. Una volta impostati i metodi di pagamento con mapping, seleziona **Salva**.
1. Nella pagina **Tipi di carta**, seleziona **Salva**.

## <a name="configure-a-commerce-online-store-for-google-pay"></a>Configurare un punto vendita Commerce online per Google Pay

Per configurare un punto vendita Commerce online per usare Google Pay, attieniti alla seguente procedura.

1. In Commerce headquarters, vai a **Vendita al dettaglio e commercio \> Canali \> Negozi online**.
1. Seleziona il canale del punto vendita online del sito selezionando il valore **ID canale di vendita al dettaglio**.
1. Nella Scheda dettaglio **Conti pagamenti**, in **Connettore**, verifica che **Dynamics 365 Payment Connector per Adyen** sia incluso nell'elenco. In caso contrario, segui le istruzioni in [Impostare Dynamics 365 Payment Connector per Adyen](adyen-connector-setup.md) per aggiungerlo.

    > [!NOTE]
    > Nella maggior parte dei casi, il connettore **Dynamics 365 Payment Connector per Adyen** deve essere elencato come primo connettore per il canale (il primo connettore è anche detto connettore primario). Deve essere seguito da altri connettori che verranno usati, ad esempio **Dynamics 365 Payment Connector per PayPal** e **Dynamics 365 Payment Connector per GooglePay**.

1. Una volta aggiunto il connettore **Dynamics 365 Payment Connector per Adyen**, seleziona **Aggiungi** per aggiungere il connettore **Dynamics 365 Payment Connector per GooglePay**. Quindi, imposta le proprietà seguenti per il connettore.

    | Campo                  | Description | Obbligatorio | Impostazione automatica | Valore di esempio |
    | ---------------------- | ----------- | -------- | ----------------- | ------------ |
    | Nome assembly          | Il nome dell'assembly per Dynamics 365 Payment Connector per GooglePay. | Sì | Sì | *Nome binario* |
    | ID account servizio     | L'identificatore univoco per l'impostazione delle proprietà dell'esercente. Questo identificatore è riportato nelle transazioni di pagamento e identifica le proprietà del venditore che i processi a valle devono usare (come la fatturazione). | Sì | Sì | *GUID* |
    | ID esercente Google     | Immetti l'ID esercente Google assegnato al tuo conto esercente Google. Questa proprietà è obbligatoria per gli ambienti di produzione ma opzionale per gli ambienti di test. Per ulteriori informazioni, visita <https://pay.google.com/>. | Sì | Numero | *Identificatore numerico* |
    | ID conto esercente    | Immetti l'identificatore univoco dell'esercente Adyen. Questo valore viene fornito al momento della registrazione ad Adyen, come descritto in [Registrazione ad Adyen](adyen-connector-setup.md#sign-up-with-adyen). | Sì | Numero | *Identificatore esercente* |
    | Chiave API cloud          | Immetti la chiave API cloud di Ayden. Per ottenere questa chiave, segui le istruzioni in [Come ottenere la chiave API](https://docs.adyen.com/developers/user-management/how-to-get-the-api-key). | Sì | Numero | "abcdefg" |
    | Ambiente gateway    | L'ambiente gateway Adyen al quale eseguire il mapping. I valori possibili sono **Prova** e **Dinamico**. Imposta questo campo su **Dinamico** solo per i dispositivi di produzione e le transazioni. | Sì | Sì | "Dinamico" |
    | Valute supportate   | Le valute che il connettore deve elaborare. Negli attuali scenari per le carte, Adyen può supportare valute aggiuntive tramite la funzionalità [Dynamic Currency Conversion](https://www.adyen.com/pos-payments/dynamic-currency-conversion) una volta che la richiesta di transazione viene inviata al terminale di pagamento. Contatta il supporto Adyen per ottenere un elenco delle valute supportate. | Sì | Sì | "USD;EUR" |
    | Tipi di metodi di pagamento supportati | I tipi di metodi di pagamento che il connettore deve elaborare. | Sì | Sì | "GooglePay" |

1. Una volta completata l'impostazione delle proprietà dei connettori, esegui il processo di pianificazione della distribuzione **1070 (configurazione del canale**).


### <a name="use-the-payment-express-module-with-google-pay"></a>Usare il modulo di pagamento rapido con Google Pay

Il modulo di pagamento rapido di Commerce funziona con i metodi di pagamento di supporto per offrire ai clienti del sito la possibilità di effettuare il checkout più rapidamente precompilando le informazioni sul conto del servizio di pagamento durante il processo di checkout. Il modulo di pagamento rapido fa riferimento al pulsante del connettore configurato e restituisce i dettagli dell'ordine selezionati dall'utente (indirizzo, informazioni di contatto e metodo di pagamento) per precompilare il modulo di checkout.

Quando il modulo di pagamento rapido viene usato con Google Pay, se i clienti selezionano il pulsante Google Pay nella sezione **Pagamento rapido**, viene aperta la finestra iframe di Google Pay. L'utente accede quindi al proprio account Google per utilizzare l'indirizzo di spedizione, l'indirizzo di fatturazione, l'indirizzo e-mail e il metodo di pagamento Google Pay scelto per pagare la transazione.

Dopo che l'utente ha completato l'azione nella finestra di Google Pay, viene reindirizzato alla pagina di pagamento del sito Commerce, dove il modulo di checkout è precompilato con i dettagli selezionati. Una volta tornato alla pagina di checkout dalla finestra di Google Pay, l'utente vedrà i seguenti dettagli:

- Nel flusso di pagamento rapido, la prima opzione di consegna disponibile per l'indirizzo di spedizione restituito sarà preselezionato per il cliente.
- Quando si usa Google Pay, non viene restituito alcun indirizzo e-mail di contatto. Gli utenti del checkout Guest dovranno immettere un indirizzo e-mail nella sezione dei contatti della pagina di checkout. I dati di contatto degli utenti registrati verranno compilati automaticamente dal relativo account cliente Dynamics (l'indirizzo e-mail primario usato per l'autenticazione).

I clienti hanno la possibilità di rivedere gli ordini e modificare i dettagli dell'ordine di checkout prima di selezionare **Effettua ordine** per finalizzare l'ordine.

### <a name="configure-google-pay-in-site-builder"></a>Configurare Google Play nel generatore di siti 

Prima di configurare i frammenti o le pagine con Google Pay, devi verificare che i criteri di sicurezza dei contenuti per il tuo sito siano impostati nel generatore di siti di Commerce.

Per verificare che i criteri di sicurezza dei contenuti siano impostati nel generatore di siti, attieniti alla seguente procedura.

1. Nel tuo sito, vai a **Impostazioni sito \> Estensioni**.
1. Nella scheda **Criteri di sicurezza dei contenuti**, aggiungi una riga per `*.google.com` alle direttive **child-src**, **connect-src**, **frame-ancestors**, **frame-src**, **img-src**, **script-src** e **style-src**.
1. Al termine dell'operazione, seleziona **Salva e pubblica**.

### <a name="configure-the-payment-express-fragment-with-google-pay-in-site-builder"></a>Configurare il frammento di pagamento rapido con Google Pay nel generatore di siti

Per impostare il frammento di pagamento rapido con Google Pay per il punto vendita online, segui questi passaggi.

1. Nel generatore di siti, accedi a **Frammenti**.
1. Selezionare **Nuovo**.
1. Nella finestra di dialogo **Nuovo frammento**, seleziona il modulo **Contenitore**, immetti un nome per il frammento (ad esempio, **Checkout rapido**), quindi seleziona **OK**. 
1. Seleziona lo slot **Contenitore predefinito** del nuovo frammento.
1. Nel riquadro proprietà a destra, imposta le proprietà per il modulo contenitore:

    - **Intestazione**: immetti un'intestazione per visualizzare la sezione del checkout rapido del sito (ad esempio, **Checkout rapido**).
    - **Layout contenitore**: seleziona **Flusso**.
    - **Larghezza**: selezionare **Riempi contenitore**.
    - **Figli visualizzati**: seleziona **Tre** per specificare il numero di figli che dovranno essere contenuti in una riga della sezione di checkout rapido della pagina di checkout (ad esempio una casella di testo, pagamento rapido per PayPal e pagamento rapido per Google Pay).
    - **Nome classe CSS**: immetti **msc-express-payment-container** (obbligatorio).

    > [!IMPORTANT]
    > - Il valore **Nome classe CSS** deve essere impostato su **msc-express-payment-container** per controllare il comportamento del contenitore durante il checkout. Questo comportamento include la possibilità di nascondere, ridurre a icona e altre azioni applicabili alla sezione di checkout rapido durante il flusso di checkout. La classe **msc-express-payment-container** funziona con le operazioni predefinite rilasciate con il modulo di checkout della libreria di moduli.
    > - È possibile includere stili aggiuntivi per **Nome classe CSS**. Se si personalizza il comportamento del modulo, esegui una verifica incrociata sui controlli di stile se stai usando lo stesso comportamento codificato della libreria di moduli nel modulo di checkout per il comportamento di checkout rapido.

1. Nello slot **Contenitore predefinito** seleziona i puntini di sospensione (**...**) quindi seleziona **Aggiungi modulo**.
1. Nella finestra di dialogo **Seleziona moduli** selezionare il modulo **Pagamento rapido** e quindi **OK**.
1. Nel riquadro delle proprietà del modulo **Pagamento rapido**, imposta o modifica il valore di **Altezza dell'iFrame** in pixel (ad esempio, **60**).
1. Nel campo **Tipi di metodi di pagamento supportati**, immetti **GooglePay**. Il valore deve corrispondere alla stringa **Tipi di metodi di pagamento supportati** nel connettore impostato per il canale (come descritto nella sezione [Configurare un punto vendita online di Commerce per Google Pay](#configure-a-commerce-online-store-for-google-pay) in questo articolo).

    > [!NOTE]
    > Puoi ripetere i passaggi da 6 a 9 per aggiungere moduli di **Pagamento rapido** per altri metodi di pagamento. Allinea il valore di **Tipi di metodi di pagamento supportati** ai tipi di pagamento configurati aggiuntivi (ad esempio, **Paypal**).

1. Facoltativo: puoi aggiungere un modulo blocco di testo al modulo contenitore predefinito per includere istruzioni o informazioni sulla divulgazione. Dopo aver aggiunto il modulo, nel riquadro delle proprietà, immetti il testo desiderato nel campo **RTF**. Puoi posizionare il testo al di sopra o al di sotto dei moduli di pagamento rapido selezionando i puntini di sospensione (**...**) nello slot **Blocco di testo** e selezionando quindi **Sposta su** o **Sposta giù**.
1. Seleziona **Salva** per salvare le modifiche, quindi seleziona **Termina modifica**.
1. Seleziona **Pubblica** per pubblicare il frammento.

### <a name="add-the-payment-express-fragment-to-the-checkout-page"></a>Aggiungere il frammento di pagamento rapido alla pagina di checkout

Per aggiungere un frammento di pagamento rapido alla pagina di checkout nel generatore di siti, segui questi passaggi.

1. Nel generatore di siti, vai a **Pagine**, quindi seleziona la pagina di checkout del tuo sito.
1. Seleziona **Modifica**.
1. Nello slot **Principale** seleziona i puntini di sospensione (**...**), quindi seleziona **Aggiungi modulo**.
1. Nella finestra di dialogo **Seleziona moduli** seleziona il modulo **Contenitore** e quindi **OK**.
1. Nel riquadro proprietà a destra, imposta le proprietà per il modulo contenitore:

    - **Layout contenitore**: seleziona **In pila**.
    - **Larghezza**: selezionare **Riempi contenitore**.
    - **Figli visualizzati**: seleziona **Tre** per specificare il numero di figli che dovranno essere contenuti in una riga della sezione di checkout rapido della pagina di checkout (ad esempio una casella di testo, pagamento rapido per PayPal e pagamento rapido per Google Pay).

1. Nello slot del modulo **Contenitore** seleziona i puntini di sospensione (**...**), quindi seleziona **Aggiungi frammento**.
1. Nella finestra di dialogo **Seleziona un frammento**, seleziona il frammento di pagamento rapido creato, quindi seleziona **OK**.
1. Seleziona **Salva** per salvare le modifiche, quindi seleziona **Termina modifica**.
1. Seleziona **Pubblica** per pubblicare la pagina.

> [!NOTE]
> Se la pagina di checkout include già un contenitore con il frammento di checkout e si desidera che il modulo di pagamento rapido venga visualizzato al di sopra del normale contenitore di checkout, puoi posizionarlo al di sopra o al di sotto del checkout esistente selezionando i puntini di sospensione (**...**) nello **Slot principale** e poi selezionando **Sposta su** o **Sposta giù**.

### <a name="add-the-payment-express-fragment-to-the-cart-page"></a>Aggiungere il frammento di pagamento rapido alla pagina del carrello

Per aggiungere un frammento di pagamento rapido alla pagina del carrello nel generatore di siti, segui questi passaggi.

1. Nel generatore di siti, vai a **Pagine**, quindi seleziona la pagina del carrello del tuo sito.
2. Seleziona **Modifica**.
3. Nella vista struttura, espandi lo **Slot principale** nella visualizzazione albero e trova il contenitore che contiene il modulo **Carrello**.
4. Nel modulo **Carrello** seleziona lo slot **Pagamento rapido**, seleziona i puntini di sospensione (**...**), quindi seleziona **Aggiungi modulo**.
5. Nella finestra di dialogo **Seleziona moduli** selezionare il modulo **Pagamento rapido** e quindi **OK**.
6. Seleziona lo slot del modulo **Pagamento rapido**. Quindi, nel riquadro delle proprietà a destra, in **Tipi di metodi di pagamento supportati**, immetti **GooglePay**. Il valore deve corrispondere alla stringa **Tipi di metodi di pagamento supportati** nel connettore impostato per il canale (come descritto nella sezione [Configurare un punto vendita online di Commerce per Google Pay](#configure-a-commerce-online-store-for-google-pay) in questo articolo).
1. Seleziona **Salva** per salvare le modifiche, quindi seleziona **Termina modifica**.
1. Seleziona **Pubblica** per pubblicare la pagina.

Gli utenti possono includere fino a tre moduli **Pagamento rapido** supportati (altrimenti detto, tre opzioni di pagamento supportate disponibili) nello slot **Pagamento rapido** del carrello.

### <a name="set-up-google-pay-as-an-option-in-the-checkout-payment-section"></a>Impostare Google Pay come opzione nella sezione di pagamento del checkout

Puoi impostare Google Pay come opzione nella sezione di pagamento del checkout per la funzionalità di solo pagamento non rapido Il modulo di checkout verrà compilato dall'utente e la pagina di pagamento di Google Pay mostrerà solo l'opzione di pagamento tramite Google Pay per il checkout. Nessuna informazione dell'account Google verrà usata per sovrascrivere i dettagli di checkout compilati.

> [!NOTE]
> La procedura seguente presuppone che il sito usi un frammento di checkout configurato con le informazioni di prelievo, un indirizzo di spedizione, opzioni di consegna, informazioni di contatto, termini e condizioni facoltative e una sezione per gli elementi di checkout. Il modulo di checkout della libreria di moduli predefinita viene rilasciato con un contenitore della sezione di checkout con moduli per blocco di testo, punti fedeltà, gift card e pagamento. Per ulteriori informazioni, vedi [Modulo di pagamento](../payment-module.md).

Per impostare Google Pay come opzione standard di pagamento nella sezione **Metodo di pagamento** della pagina di checkout, segui questi passaggi.

1. Nel generatore di siti, vai a **Frammenti**, quindi seleziona il frammento di checkout del tuo sito.
1. Seleziona **Modifica**.
1. Nello slot **Informazioni checkout** seleziona i puntini di sospensione (**...**) quindi seleziona **Aggiungi modulo**.
1. Nella finestra di dialogo **Seleziona moduli** seleziona il modulo **Pagamento** e quindi **OK**.
1. Nel riquadro proprietà del modulo **Pagamento** a destra, imposta le proprietà per il modulo contenitore:

    - **Intestazione**: immetti un'intestazione per visualizzare la sezione del checkout rapido del sito (ad esempio, **Google Pay**).
    - **Altezza dell'iFrame**: modifica il valore impostando l'altezza di design preferita in pixel (ad esempio, **75**). 
    - **Tipi di metodi di pagamento supportati**: immetti **GooglePay** per conformarti alla configurazione del connettore Google Pay in Commerce headquarters.
    - **Pagamento principale**: non selezionare questa casella di controllo. (Questa proprietà è in genere abilitata per il modulo di checkout di Adyen.)
    - **Sostituzione stile pagamento**: questa proprietà non è supportata per la configurazione di Google Pay.
    - **Utilizza ID connettore**: questa proprietà deve essere selezionata se si usano più connettori di pagamento nella pagina.

1. Posiziona il modulo al di sopra o al di sotto degli altri moduli di pagamento rapido selezionando i puntini di sospensione (**...**) nello slot **Pagamento** e selezionando quindi **Sposta su** o **Sposta giù**.
1. Seleziona **Salva** per salvare le modifiche, quindi seleziona **Termina modifica**.
1. Selezionare **Pubblica**

### <a name="modes-of-delivery"></a>Modalità di consegna

Con il modulo di pagamento rapido configurato per l'uso di PayPal, verrà preselezionata la prima opzione di consegna restituita per l'indirizzo di spedizione selezionato per l'account Google Pay. Gli utenti hanno la possibilità di modificare l'indirizzo di spedizione impostando una diversa opzione, se lo desiderano.

L'ordine di visualizzazione dei metodi di consegna nel modulo di pagamento rapido è configurato nella pagina **Modalità di consegna** del canale in Commerce headquarters. In Commerce headquarters, vai a **Vendita al dettaglio e commercio \> Canali \> Punti vendita online**, quindi seleziona **ID canale di vendita al dettaglio** per il punto vendita. Nel riquadro Azioni, nella scheda **Imposta**, seleziona **Modalità di consegna**. Le modalità di consegna elencate verranno visualizzate nello stesso ordine nel modulo di pagamento rapido. Seleziona **Gestisci modalità di consegna** nel riquadro Azioni per aggiungere o rimuovere modalità di consegna per un prodotto o un canale di vendita al dettaglio. Per ulteriori informazioni su come configurare le modalità di consegna, vedi [Configurare le modalità di consegna](/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery).

Il modulo di check out usa anche il modulo delle opzioni di consegna quando le modalità di consegna vengono visualizzate durante il checkout. Per ulteriori informazioni, vedere [Modulo Opzioni di consegna](../delivery-options-module.md).

Le modalità di consegna vengono visualizzate man mano che vengono aggiunte all'elenco **Modalità di consegna** nel punto vendita online.

## <a name="configure-commerce-pos-for-google-pay"></a>Configurare il POS di Commerce per Google Pay

La configurazione del POS usa l'impostazione del campo **Servizio EFT** del profilo hardware per Dynamics 365 Payment Connector per Adyen. Per informazioni su come configurare il servizio di trasferimento elettronico di fondi (EFT) per Dynamics 365 Payment Connector per Adyen in Commerce headquarters, fai riferimento a [Profilo hardware del POS di Dynamics 365](adyen-connector-setup.md#set-up-a-dynamics-365-pos-hardware-profile).

Il mapping del processore per il connettore Adyen acquisisce i tipi di carta portafoglio che Google Pay usa nel terminale POS.

## <a name="additional-resources"></a>Risorse aggiuntive

[Domande frequenti sui pagamenti](payments-retail.md)

[Modulo checkout](../add-checkout-module.md)

[Modulo pagamento](../payment-module.md)
