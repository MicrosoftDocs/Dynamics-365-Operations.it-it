---
title: Configurare Apple Pay con Adyen in Dynamics 365 Commerce
description: Questo articolo descrive come configurare Apple Pay con Adyen in Microsoft Dynamics 365 Commerce.
author: BrianShook
ms.date: 11/15/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: josaw
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2022-06-20
ms.openlocfilehash: 0949b9d7a4b181605d43956932b4fc095940bd64
ms.sourcegitcommit: cf6b764824bd1cf2c0dde6d37ddd0a7abab87ff0
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/16/2022
ms.locfileid: "9780372"
---
# <a name="set-up-apple-pay-with-adyen-in-dynamics-365-commerce"></a>Configurare Apple Pay con Adyen in Dynamics 365 Commerce

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

Questo articolo descrive come configurare Apple Pay con Adyen in Microsoft Dynamics 365 Commerce.

## <a name="key-terms"></a>Termini importanti

| Termine | Description |
|---|---|
| Apple Pay | Noto anche come "pulsante" Apple Pay", Apple Pay è un'offerta di pagamento tramite portafoglio supportata mediante il connettore Adyen. Fornisce l'integrazione e l'esperienza del cliente supportate dal connettore Apple Pay di Microsoft Dynamics 365. |
| Portafoglio | Un tipo di pagamento che non include le caratteristiche di pagamento tradizionali, come l'intervallo BIN (Bank Identification Number, numero di identificazione della banca) e la data di scadenza, usate per differenziare i tipi di carta di credito e di debito. |

Dynamics 365 Commerce fornisce una soluzione pronta per l'integrazione Apple Pay quando si usa il servizio gateway per i pagamenti Ayden. Apple Pay è un metodo di pagamento tramite portafoglio digitale che usa un conto esercente Apple Pay congiuntamente al servizio di pagamento Ayden. Quando è configurato, il pulsante Apple Pay è un metodo di pagamento selezionabile incluso in una pagina di checkout degli ordini dello store online. Il pulsante Apple Pay viene presentato come opzione di pagamento solo per i dispositivi Apple Pay supportati. Quando gli utenti selezionano **Apple Pay** in un browser o in un dispositivo supportato, vengono indirizzati al servizio Apple Pay per completare direttamente il pagamento. Vengono quindi riportati alla vetrina online per completare l'ordine.

Viene usato il riferimento al connettore Dynamics 365 Payment Connector per Apple Pay oltre a Dynamics 365 Payment Connector per Adyen per abilitare i pagamenti Apple Pay e con carta di credito in un sito. Apple Pay può anche essere configurato per l'utilizzo nei punti vendita che dispongono di terminali di pagamento Adyen che utilizzano Dynamics 365 Payment Connector per Adyen con il POS di Commerce. In questo caso, Dynamics 365 Payment Connector per Adyen gestisce il tocco del dispositivo Apple Payment attraverso il terminale.

## <a name="prerequisites"></a>Prerequisiti

Per usare Apple Pay con Adyen in Commerce è necessario disporre di un conto esercente Apple. Per informazioni su come configurare Apple Pay nell'area cliente di prova, vedi [Integrazione drop-in di Apple Pay](https://docs.adyen.com/payment-methods/apple-pay/web-drop-in#set-up-apple-pay). Per informazioni su cosa fare quando sei pronto per passare allo stato live nel tuo ambiente di produzione, vedi [Passaggio allo stato live](https://docs.adyen.com/payment-methods/apple-pay/web-drop-in#going-live).

Il metodo di pagamento Apple Pay deve inoltre essere integrato con il tuo conto Adyen. Adyen può aiutarti a configurare il metodo di pagamento e può anche aiutarti a garantire che i domini per i quali utilizzerai il certificato siano assegnati per l'uso con il certificato.

Per abilitare il flag della funzionalità di portafoglio avanzata in Commerce headquarters, accedi a **Aree di lavoro \> Gestione funzionalità** e cerca la funzionalità **Supporto portafoglio avanzato e miglioramenti dei pagamenti**. Seleziona la funzionalità, quindi seleziona **Abilita**. Una volta abilitata la funzionalità, esegui la pianificazione della distribuzione **1110** per rendere disponibile la modifica in tutti i canali.

## <a name="map-the-apple-pay-payment-method"></a>Eseguire il mapping del metodo di pagamento Apple Pay

Apple Pay è un metodo di pagamento tramite portafoglio digitale. Per informazioni su come configurare il mapping dei pagamenti per Apple Pay, vedi [Supporto del pagamento tramite portafoglio](../wallets.md).

Per eseguire il mapping del metodo di pagamento Apple Pay in Commerce Headquarters, seguire questi passaggi.

1. Vai a **Retail e Commerce \> Impostazione canale \> Metodi di pagamento \> Tipi di carte**.
1. Seleziona **Nuova** per aggiungere una riga per Apple Pay, quindi imposta i seguenti valori:

    - **ID:** ApplePay
    - **Nome pagamento elettronico:** Apple Pay
    - **Tipo:** Portafoglio
    - **Emittente:** Apple

1. Seleziona **Mapping processore** per aprire la finestra di dialogo **Mapping del metodo di pagamento del processore**. Nella colonna **Metodi di pagamento del processore non mappati** vengono elencati i metodi di pagamento supportati per ogni connettore disponibile (Adyen, PayPal e Apple).
1. Esegui il mapping dei metodi di pagamento supportati che desideri per i connettori **Dynamics 365 Payment Connector per Adyen** (da usare per il POS) e **Dynamics 365 Payment Connector per Apple Pay** (per il canale online).
1. Per ogni riga di mapping, nella colonna **Metodi di pagamento del processore non mappati**, seleziona la riga da supportare, quindi seleziona **Aggiungi** per spostare le selezioni nella colonna **Metodi di pagamento del processore mappati**.
1. Seleziona **OK**, quindi, nella pagina **Tipi di carta**, seleziona **Salva**.

## <a name="set-up-the-apple-pay-certificate-for-your-site"></a>Configurare il certificato Apple Pay per il tuo sito

Per ogni sito, devi caricare il file di associazione del dominio (noto anche come certificato Apple Pay) come descritto nella [documentazione di Adyen Apple Pay](https://docs.adyen.com/payment-methods/apple-pay/web-drop-in#going-live). Puoi utilizzare Commerce Site Builder per caricare il file di associazione del dominio nella Libreria multimediale per il tuo sito.

Per configurare il certificato Apple Pay in Creazione di siti Web, segui questa procedura.

1. Scarica il certificato (file di associazione del dominio) da [Adyen](https://docs.adyen.com/payment-methods/apple-pay/web-drop-in#going-live).
1. Aggiungi l'estensione .txt al file di associazione del dominio.
1. In Creazione di siti Web, [carica](../upload-serve-static-files.md) il file di associazione del dominio alla Libreria multimediale del tuo sito.
1. Passa a **URL**.
1. Selezionare **Nuovo \> Nuovo URL**.
1. Nella finestra di dialogo **Nuovo URL**, selezionare **Risorsa libreria multimediale**.
1. Nel campo **Percorso URL**, immetti il percorso dell'URL (se non è già stato immesso). Dopo l'URL di base del dominio, immetti la seguente stringa Apple obbligatoria: `<domain>/.well-known/apple-developer-merchantid-domain-association.txt`.
1. Selezionare **Avanti**. La libreria multimediale mostra tutte le risorse multimediali caricate del tipo **documento** (.txt).
1. Seleziona il file di associazione del dominio che deve essere servito per le richieste all'URL definito in precedenza.
1. Seleziona **Crea**.

A questo punto, l'URL creato è in stato bozza. Pubblica l'URL per completare il processo. Il file a cui punta l'URL non verrà restituito finché non si pubblica l'URL.

## <a name="configure-a-commerce-online-store-for-apple-pay"></a>Configurare un punto vendita Commerce online per Apple Pay

Per configurare un punto vendita Commerce online per Apple Pay, attieniti alla seguente procedura.

1. In Commerce headquarters, vai a **Vendita al dettaglio e commercio \> Canali \> Negozi online**.
1. Seleziona il valore **ID canale di vendita al dettaglio** del canale dello store online del sito.
1. Nella Scheda dettaglio **Conti pagamenti**, aggiungi il connettore **Dynamics 365 Payment Connector per Adyen**, se non è già configurato, seguendo le istruzioni in [Configurare Dynamics 365 Payment Connector per Adyen](adyen-connector-setup.md).
1. Dopo aver configurato il connettore Adyen, seleziona **Aggiungi** per aggiungere il connettore **Dynamics 365 Payment Connector per Adyen**.
1. Immetti i valori per le proprietà dell'esercente del connettore.

    | Proprietà               | Description | Obbligatorio | Impostazione automatica | Valore di esempio |
    | ---------------------- | ----------- | -------- | ----------------- | ------------ |
    | Nome assembly          | Il nome dell'assembly per Dynamics 365 Payment Connector per Apple Pay. | Sì | Sì | Nome binario |
    | ID account servizio     | L'identificatore univoco dell'impostazione delle proprietà dell'esercente. Questo identificatore è riportato nelle transazioni di pagamento e identifica le proprietà del venditore che i processi a valle devono usare (come la fatturazione). | Sì | Sì | GUID |
    | ID conto esercente    | Immetti l'identificatore univoco dell'esercente Adyen. Questo valore viene fornito al momento della registrazione ad Adyen, come descritto in [Registrazione ad Adyen](adyen-connector-setup.md#sign-up-with-adyen). | Sì | Numero | MerchantIdentifier |
    | Chiave API cloud          | Immetti la chiave API cloud di Ayden. Puoi ottenere questa chiave seguendo le istruzioni in [Come ottenere la chiave API](https://docs.adyen.com/developers/user-management/how-to-get-the-api-key). | Sì | Numero | abcdefg |
    | Ambiente gateway    | Immetti l'ambiente gateway Adyen al quale eseguire il mapping. I valori possibili sono **Prova** e **Dinamico**. Imposta questo campo su **Dinamico** solo per i dispositivi di produzione e le transazioni. | Sì | Sì | Tempo reale |
    | Valute supportate   | Immetti le valute che il connettore deve elaborare. Negli attuali scenari per le carte, Adyen può supportare valute aggiuntive tramite la funzionalità [Dynamic Currency Conversion](https://www.adyen.com/pos-payments/dynamic-currency-conversion) una volta che la richiesta di transazione viene inviata al terminale di pagamento. Contatta il supporto Adyen per ottenere un elenco delle valute supportate. | Sì | Sì | USD;EUR |
    | Tipi di metodi di pagamento supportati | Immetti i tipi di metodi di pagamento che il connettore deve elaborare. | Sì | Sì | ApplePay |

1. Dopo aver inserito le informazioni dell'esercente, esegui il processo di pianificazione della distribuzione di configurazione del canale **1070**.

## <a name="configure-commerce-pos-for-apple-pay"></a>Configurare il POS di Commerce per Apple Pay

La configurazione del POS usa la configurazione del campo **Servizio EFT** del profilo hardware per Dynamics 365 Payment Connector per Adyen. In Commerce headquarters, configura il servizio di trasferimento elettronico di fondi (EFT) per Dynamics 365 Payment Connector per Adyen come descritto nella sezione [Profilo hardware del POS di Dynamics 365](adyen-connector-setup.md#set-up-a-dynamics-365-pos-hardware-profile).

Assicurati di aggiungere **ApplePay** all'elenco dei tipi di pagamento nel campo **Tipi di metodi di pagamento supportati**. Utilizza il punto e virgola (;) per separare i tipi di pagamento nell'elenco.

Il mapping del processore per il connettore Adyen acquisisce i tipi di carta portafoglio utilizzati da Apple Pay nel terminale POS.

### <a name="configure-content-security-policies-in-site-builder"></a>Configurare i criteri di sicurezza del contenuto in Creazione di siti Web

Prima di configurare i frammenti o le pagine per utilizzare Apple Pay, devi verificare che i criteri di sicurezza dei contenuti per il tuo sito siano configurati nel generatore di siti di Commerce per il tuo sito.

Per configurare i criteri di sicurezza dei contenuti in Creazione di siti Web, attieniti alla seguente procedura.

1. Vai a **Impostazioni sito \> Estensioni**.
1. Nella scheda **Criteri di sicurezza del contenuto**, seleziona **Aggiungi** pe aggiungere una riga che include `https://applepay.cdn-apple.com/jsapi/v1/apple-pay-sdk.js` alle sezioni **child-src**, **connect-src**, **frame-src**, **img-src**, **script-src** e **style-src**.
1. Al termine, seleziona **Salva e pubblica** per applicare le modifiche.

### <a name="set-up-apple-pay-as-a-checkout-payment-option"></a>Configurare Apple Pay come opzione di pagamento per il checkout

Per configurare Apple Pay come opzione di pagamento per il checkout nella pagina di checkout (non espresso) del tuo sito, procedi nel seguente modo.

1. In Creazione di siti Web, vai a **Frammenti**, quindi seleziona il frammento di checkout del tuo sito.
1. Seleziona **Modifica**.
1. Nell'area **Contenitore sezione checkout** seleziona i puntini di sospensione (**...**) quindi seleziona **Aggiungi modulo**.
1. Nella finestra di dialogo **Seleziona moduli** seleziona il modulo **Apple Pay**, quindi scegli **OK**.
1. Seleziona **Salva**.
1. Selezionare **Fine modifica** per archiviare il frammento, quindi selezionare **Pubblica** per pubblicarlo.

Le impostazioni del modulo **Apple Pay** sono incorporate nel modulo e si connettono al connettore Dynamics 365 Payment Connector per Apple Pay configurato per il canale online in Commerce headquarters.

### <a name="apple-pay-payment-behavior"></a>Comportamento di pagamento Apple Pay

Il pulsante di pagamento **Apple Pay** viene visualizzato solo sui dispositivi Apple Pay supportati (iPhone, iPad e browser Safari che supportano Apple Pay). Se un utente non utilizza uno di questi dispositivi, il pulsante di pagamento **Apple Pay** è nascosto dalla visualizzazione.

Quando un utente seleziona il pulsante di pagamento **Apple Pay**, viene visualizzata una finestra di dialogo **Apple Pay**. In questa finestra l'utente può eseguire l'autenticazione a fronte del proprio browser o dispositivo Apple Pay. La finestra di dialogo **Apple Pay** mostra un riepilogo dell'importo dell'ordine e il metodo di pagamento che l'utente ha configurato sul proprio portafoglio Apple. L'utente può rivedere questi dettagli e quindi selezionare **Paga** per completare il pagamento. Dopo che il pagamento è stato completato, l'utente viene indirizzato alla pagina del sito **Ordine completato** che mostra un riepilogo dettagliato dell'ordine per la transazione completata.

## <a name="additional-resources"></a>Risorse aggiuntive

[Domande frequenti sui pagamenti](payments-retail.md)

[Modulo checkout](../add-checkout-module.md)

[Modulo pagamento](../payment-module.md)
