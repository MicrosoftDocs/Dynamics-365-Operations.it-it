---
title: Esempio di integrazione di stampante fiscale per l'Italia
description: In questo articolo viene fornita una panoramica dell'esempio di integrazione fiscale per l'Italia in Microsoft Dynamics 365 Commerce.
author: EvgenyPopovMBS
ms.date: 12/20/2021
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2018-11-01
ms.openlocfilehash: e63f8d68b8b79143771c0b1c757cb78659183b67
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9280270"
---
# <a name="fiscal-printer-integration-sample-for-italy"></a>Esempio di integrazione di stampante fiscale per l'Italia

[!include[banner](../includes/banner.md)]

In questo articolo viene fornita una panoramica dell'esempio di integrazione fiscale per l'Italia in Microsoft Dynamics 365 Commerce.

La funzionalità di Commerce per l'Italia include un'integrazione di esempio del POS con una stampante fiscale. L'esempio estende la [funzionalità di integrazione fiscale](fiscal-integration-for-retail-channel.md) di modo che sia utilizzabile con le stampanti [Epson FP-90III Series](https://www.epson.it/products/sd/pos-printer/epson-fp-90iii-series) di Epson e abilita la comunicazione con una stampante fiscale in modalità server Web via il servizio Web EpsonFPMate utilizzando l'API Fiscal ePOS-Print. L'esempio supporta soltanto la modalità Registratore Telematico (RT). L'esempio viene fornito sotto forma di codice sorgente e fa parte del kit SDK.

Microsoft non rilascia hardware, software o documentazione di Epson. Per informazioni su come ottenere la stampante fiscale e utilizzarla, contattare [Epson Italia S.p.A](https://www.epson.it).

## <a name="scenarios"></a>Scenari

Gli scenari seguenti sono coperti dall'esempio di integrazione di stampante fiscale per l'Italia:

- Scenari di vendita:

    - Stampare una ricevuta fiscale per le vendite cash and carry e i resi.
    - Ottenure una risposta dalla stampante fiscale e archiviarla nel database del canale.
    - Imposte:

        - Eseguire il mapping ai codici imposta (reparti) della stampante fiscale.
        - Trasferire i dati fiscali mappati alla stampante fiscale.
        - Stampare le imposte su una ricevuta fiscale.

    - Pagamenti:

        - Eseguire il mapping ai metodi di pagamento della stampante fiscale.
        - Stampare i pagamenti su una ricevuta fiscale.
        - Stampare le informazioni sulle modifiche.

    - Stampare gli sconti riga
    - Gift card:

        - Escludere una riga gift card emessa/ricaricata da una ricevuta fiscale per una vendita.
        - Stampare un pagamento che utilizza una gift card come metodo di pagamento normale.

    - Stampare ricevute fiscali per operazioni di ordini cliente:

        - Una ricevuta fiscale non viene stampata per un deposito ordine cliente.
        - Stampa una ricevuta fiscale per righe di esecuzione di un ordine cliente ibrido.
        - Stampare una ricevuta fiscale per l'operazione di prelievo per un ordine cliente.
        - Stampare una ricevuta fiscale per un ordine di reso.

    - Stampare un codice a barre per il numero di ricevuta su una ricevuta fiscale.
    - Stampare le [informazioni del cliente](emea-ita-customer-information.md) specificate per una transazione di vendita in una ricevuta fiscale. Un esempio di queste informazioni è il codice fiscale del cliente. 

- Rendiconti di riepilogo giornalieri (report X e Z fiscali).
- Gestione degli errori, ad esempio le seguenti opzioni:

    - Se possibile, ripetere la registrazione fiscale nel caso la stampante fiscale non sia collegata, pronta o non risponda o se la carta risulta mancante o inceppata.
    - Posticipare la registrazione fiscale.
    - Ignorare la registrazione fiscale, o contrassegnare la transazione come registrata, e includere i codici informativi per acquisire il motivo dell'errore e ulteriori informazioni.
    - Verificare la disponibilità della stampante fiscale prima dell'apertura di una nuova transazione di vendita o della finalizzazione di una transazione di vendita.

### <a name="gift-cards"></a>Gift card

L'esempio di integrazione della stampante fiscale implementa le seguenti regole relative alle gift card:

- Escludere le righe di vendita correlate alle operazioni *Emetti gift card* e *Aggiungi a gift card* della ricevuta fiscale.
- Non stampare una ricevuta fiscale se comporta soltanto righe gift card.
- Dedurre l'importo totale delle gift card emesse o ricaricate in una transazione dalle righe di pagamento della ricevuta fiscale.
- Salvare le rettifiche calcolate delle righe di pagamento nel database del canale con un riferimento a una transazione fiscale corrispondente.
- Il pagamento tramite gift card è considerato un pagamento normale.

### <a name="customer-deposits-and-customer-order-deposits"></a>Depositi cliente e depositi ordine cliente

L'esempio di integrazione della stampante fiscale implementa le seguenti regole relative a depositi cliente e a depositi ordine cliente:

- Non stampare una ricevuta fiscale se una transazione è un deposito cliente.
- Non stampare una ricevuta fiscale se una transazione contiene solo un deposito ordine cliente o un rimborso di deposito ordine cliente.
- Stampare l'importo del deposito pagato in precedenza su una ricevuta fiscale per un'operazione di prelievo ordine cliente.
- Dedurre l'importo del deposito ordine cliente dalle righe di pagamento quando si crea un ordine cliente ibrido.
- Salvare le rettifiche calcolate delle righe di pagamento nel database del canale con un riferimento a una transazione fiscale per un ordine cliente ibrido.

### <a name="limitations-of-the-sample"></a>Limitazioni dell'esempio

- La stampante fiscale supporta solo gli scenari in cui l'IVA è inclusa nel prezzo. Di conseguenza, l'opzione **Prezzi IVA inclusa** deve essere impostata su **Sì** per i punti vendita e i clienti.
- I report giornalieri (X e Z fiscali) vengono stampati utilizzando il formato incorporato nel firmware della stampante fiscale.
- Le transazioni miste non sono supportate dalla stampante fiscale. L'opzione **Impedisci di combinare vendite e resi in una ricevuta** deve essere impostata su **Sì** nei profili funzionalità POS.
- L'esempio supporta l'integrazione solo con una stampante fiscale che funziona in modalità Registrazione Telematico (RT).

## <a name="set-up-fiscal-integration-for-italy"></a>Impostare l'integrazione fiscale per l'Italia

L'esempio di integrazione della stampante fiscale per l'Italia si basa sulla [funzionalità di integrazione fiscale](fiscal-integration-for-retail-channel.md) e fa parte di Retail SDK. L'esempio si trova nella cartella **src\\FiscalIntegration\\EpsonFP90IIISample** del repository [Soluzioni Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/) (ad esempio, [l'esempio in release/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/tree/release/9.33/src/FiscalIntegration/EpsonFP90IIISample)). L'esempio [consiste](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices-and-services) di un provider di documenti fiscali, che è un'estensione di Commerce Runtime (CRT) e un connettore fiscale, che è un'estensione di Commerce Hardware Station. Per ulteriori informazioni su come utilizzare Retail SDK, vedi [Architettura di Retail SDK](../dev-itpro/retail-sdk/retail-sdk-overview.md) e [Configurare una pipeline di compilazione per SDK a pacchetti indipendenti](../dev-itpro/build-pipeline.md).

> [!WARNING]
> A causa delle limitazioni del [nuovo modello di packaging ed estensione indipendente](../dev-itpro/build-pipeline.md), non può essere attualmente utilizzato per questo esempio di integrazione fiscale. È necessario utilizzare la versione precedente di Retail SDK su una macchina virtuale per sviluppatori (VM) in Microsoft Dynamics Lifecycle Services (LCS). Per ulteriori informazioni, vedi [Linee guida per la distribuzione per l'esempio di integrazione della stampante fiscale per l'Italia (legacy)](emea-ita-fpi-sample-sdk.md).
>
> Il supporto per il nuovo modello di packaging ed estensione indipendente per gli esempi di integrazione fiscale è previsto per le versioni successive.

Completa la procedura di configurazione dell'integrazione fiscale come descritto in [Impostare l'integrazione fiscale per canali di Commerce](setting-up-fiscal-integration-for-retail-channel.md).

1. [Configurare un processo di registrazione fiscale](setting-up-fiscal-integration-for-retail-channel.md#set-up-a-fiscal-registration-process). Inoltre, prendi nota delle impostazioni per il processo di registrazione fiscale che sono [specifiche dell'esempio di integrazione della stampante fiscale](#set-up-the-registration-process).
1. [Impostare testi fiscali per sconti](setting-up-fiscal-integration-for-retail-channel.md#set-up-fiscal-texts-for-discounts).
1. [Configurare le impostazioni di gestione degli errori](setting-up-fiscal-integration-for-retail-channel.md#set-error-handling-settings).
1. [Configurare report X/Z fiscali dal POS](setting-up-fiscal-integration-for-retail-channel.md#set-up-fiscal-xz-reports-from-the-pos).
1. [Abilitare l'esecuzione manuale della registrazione fiscale posticipata](setting-up-fiscal-integration-for-retail-channel.md#enable-manual-execution-of-postponed-fiscal-registration).
1. [Impostare la funzionalità per la gestione delle informazioni del cliente nel POS](emea-ita-customer-information.md#setup).
1. [Configura i componenti del canale](#configure-channel-components).

### <a name="set-up-the-registration-process"></a>Impostare il processo di registrazione

Per abilitare il processo di registrazione, segui questi passaggi per configurare Commerce headquarters. Per ulteriori informazioni vedi [Impostare l'integrazione fiscale per i canali di Commerce](setting-up-fiscal-integration-for-retail-channel.md#set-up-a-fiscal-registration-process).

1. Scarica i file di configurazione per il provider di documenti fiscali e il connettore fiscale:

    1. Apri il repository [Soluzioni Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/).
    1. Seleziona una versione del ramo di rilascio corretta in base alla versione dell'SDK/dell'applicazione (ad esempio, **[release/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/tree/release/9.33)**).
    1. Apri **src \> FiscalIntegration \> EpsonFP90IIISample**.
    1. Scarica il file di configurazione del provider di documenti fiscali in **CommerceRuntime \> DocumentProvider.EpsonFP90IIISample \> Configuration \> DocumentProviderEpsonFP90IIISample.xml** (ad esempio, [il file per release/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/blob/release/9.33/src/FiscalIntegration/EpsonFP90IIISample/CommerceRuntime/DocumentProvider.EpsonFP90IIISample/Configuration/DocumentProviderEpsonFP90IIISample.xml)).
    1. Scarica il file di configurazione del connettore fiscale in **HardwareStation \> EpsonFP90IIIFiscalDeviceSample \> Configuration \> ConnectorEpsonFP90IIISample.xml**, ad esempio, [il file per release/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/blob/release/9.33/src/FiscalIntegration/EpsonFP90IIISample/HardwareStation/EpsonFP90IIIFiscalDeviceSample/Configuration/ConnectorEpsonFP90IIISample.xml).

    > [!WARNING]
    > A causa delle limitazioni del [nuovo modello di packaging ed estensione indipendente](../dev-itpro/build-pipeline.md), non può essere attualmente utilizzato per questo esempio di integrazione fiscale. È necessario utilizzare la versione precedente di Retail SDK su una macchina virtuale per sviluppatori in LCS. I file di configurazione per questo esempio di integrazione fiscale si trovano nelle seguenti cartelle di Retail SDK su una macchina virtuale per sviluppatori in LCS:
    >
    > - **File di configurazione del provider di documenti fiscali:** RetailSdk\\SampleExtensions\\CommerceRuntime\\Extension.DocumentProvider.EpsonFP90IIISample\\Configuration\\DocumentProviderEpsonFP90IIISample.xml
    > - **File di configurazione del connettore fiscale:** RetailSdk\\SampleExtensions\\HardwareStation\\Extension.EpsonFP90IIIFiscalDeviceSample\\Configuration\\ConnectorEpsonFP90IIISample.xml
    > 
    > Il supporto per il nuovo modello di packaging ed estensione indipendente per gli esempi di integrazione fiscale è previsto per le versioni successive.

1. Accedere a **Retail e Commerce \> Impostazione sedi centrali \> Parametri \> Parametri condivisi di commercio**. Nella Scheda **Generale**, imposta l'opzione **Abilita integrazione fiscale** su **Sì**.
1. Vai a **Retail e Commerce \> Impostazione canale \> Integrazione fiscale \> Provider di documenti fiscali**, e carica il file di configurazione del provider di documenti fiscali che hai scaricato prima.
1. Vai a **Retail e Commerce \> Impostazione canale \> Integrazione fiscale \> Connettori fiscali**, e carica il file di configurazione del connettore fiscale che hai scaricato prima.
1. Vai a **Retail e Commerce \> Impostazione canale \> Integrazione fiscale \> Profili funzionali del connettore**. Crea un nuovo profilo funzionale del connettore. Seleziona il provider di documenti e il connettore che hai caricato in precedenza. Aggiorna le [impostazioni di mapping dei dati](#default-data-mapping) se necessario.
1. Vai a **Retail e Commerce \> Impostazione canale \> Integrazione fiscale \> Profili tecnici del connettore**. Crea un nuovo profilo tecnico del connettore, quindi seleziona il connettore fiscale caricato in precedenza. Aggiorna le [impostazioni del connettore](#fiscal-connector-settings) se necessario.
6. Vai a **Retail e Commerce \> Impostazione canale \> Integrazione fiscale \> Gruppi di connettori fiscali**. Crea un nuovo gruppo di connettori fiscali per il profilo funzionale del connettore che hai creato in precedenza.
7. Vai a **Retail e Commerce \> Impostazione canale \> Integrazione fiscale \> Processi di registrazione fiscale**. Crea un nuovo processo di registrazione fiscale e un passaggio del processo di registrazione fiscale e seleziona il gruppo di connettori fiscali creato in precedenza.
8. Passare a **Retail e Commerce \> Impostazione canale \> Impostazione POS \> Profili POS \> Profili funzionalità**. Seleziona il profilo funzionalità collegato al punto vendita in cui il processo di registrazione deve essere attivato. Nella scheda Dettaglio **Processo di registrazione fiscale**, seleziona il processo di registrazione fiscale creato precedentemente.
9. Andare a **Retail e Commerce \> Impostazione canale \> Impostazioni POS \> Profili POS \> Profili hardware**. Seleziona un profilo hardware collegato alla stazione hardware a cui la stampante fiscale sarà collegata. Nella scheda Dettaglio **Periferiche fiscali**, seleziona il profilo tecnico del connettore creato in precedenza.
10. Aprire la programmazione della distribuzione (**Retail e Commerce \> Vendita al dettaglio e commercio IT \> Programmazione della distribuzione**) e selezionare i processi **1070** e **1090** per trasferire i dati al database del canale.

#### <a name="default-data-mapping"></a>Mapping dei dati predefiniti

Il mapping dei dati predefiniti seguente è incluso nella configurazione di provider di documenti fiscali fornita nell'esempio di integrazione fiscale:

- **Mapping del tipo metodo di pagamento** – Il mapping dei metodi di pagamento configurati per il negozio ai tipi di pagamento supportati dalla stampante fiscale. L'esempio seguente mostra il mapping predefinito.

    ```JSON
    {"PaymentMethods": [
        {"StorePaymentMethod":"1", "PrinterPaymentType":"0", "PrinterPaymentIndex":"00"},
        {"StorePaymentMethod":"3", "PrinterPaymentType":"2", "PrinterPaymentIndex":"00"},
        {"StorePaymentMethod":"4", "PrinterPaymentType":"2", "PrinterPaymentIndex":"01"},
        {"StorePaymentMethod":"6", "PrinterPaymentType":"0", "PrinterPaymentIndex":"01"},
        {"StorePaymentMethod":"8", "PrinterPaymentType":"6", "PrinterPaymentIndex":"01"}
        ],
        "DepositPaymentMethod": {"PrinterPaymentType":"2", "PrinterPaymentIndex":"00"}}
    ```

    Ecco una spiegazione degli attributi nel mapping:

    - **StorePaymentMethod** è un metodo di pagamento impostato per il negozio in **Retail e Commerce  \> Configurazione canale \> Modalità di pagamento \> Modalità di pagamento**.
    - **PrinterPaymentType** e **PrinterPaymentIndex** sono il tipo di pagamento e l'indice corrispondenti definiti nella documentazione della stampante fiscale Epson.
    - **DepositPaymentMethod** viene utilizzato per specificare il tipo di pagamento e l'indice di una stampante per la parte dell'importo del ritiro dell'ordine del cliente che viene saldata con il deposito dell'ordine del cliente.

    La tabella seguente mostra come il mapping di esempio dei metodi di pagamento corrisponda ai metodi di pagamento memorizzati che sono configurati nei dati demo standard.

    | Metodo di pagamento | Nome metodo di pagamento |
    |----------------|---------------------|
    | 1              | Cassa                |
    | 3              | Scheda                |
    | 4              | Conto cliente    |
    | 6              | Valuta            |
    | 8              | Gift card           |

    È necessario modificare il mapping di esempio in base ai metodi di pagamento configurati nell'applicazione.

- **Tipo di codice a barre per il numero di ricevuta** – Il tipo di codice a barre utilizzato per mostrare il numero di ricevuta fiscale. Il mapping predefinito è **CODICE128**.
- **Stampa i dati fiscali nell'intestazione della ricevuta** – Se questo parametro è attivo, sulla ricevuta fiscale verranno stampate le informazioni sul punto vendita. Queste informazioni includono il nome, l'indirizzo e il codice fiscale del negozio e il nome del cassiere.
- **Mapping del reparto stampante fiscale** – Il mapping dei reparti della stampante fiscale alle aliquote dell'IVA, ai motivi di esenzione da IVA e ai tipi di prodotto. L'esempio seguente mostra il mapping predefinito.

    ```JSON
    {"Departments": [
        {"VATRate":"2200", "VATExemptNature":"", "ProductType":"0", "DepartmentNumber":"01"},
        {"VATRate":"2200", "VATExemptNature":"", "ProductType":"1", "DepartmentNumber":"02"},
        {"VATRate":"1000", "VATExemptNature":"", "ProductType":"0", "DepartmentNumber":"03"},
        {"VATRate":"1000", "VATExemptNature":"", "ProductType":"1", "DepartmentNumber":"04"},
        {"VATRate":"0500", "VATExemptNature":"", "ProductType":"0", "DepartmentNumber":"05"},
        {"VATRate":"0500", "VATExemptNature":"", "ProductType":"1", "DepartmentNumber":"06"},
        {"VATRate":"0400", "VATExemptNature":"", "ProductType":"0", "DepartmentNumber":"07"},
        {"VATRate":"0400", "VATExemptNature":"", "ProductType":"1", "DepartmentNumber":"08"},
        {"VATRate":"0000", "VATExemptNature":"", "ProductType":"0", "DepartmentNumber":"09"},
        {"VATRate":"0000", "VATExemptNature":"", "ProductType":"1", "DepartmentNumber":"10"},
        {"VATRate":"0000", "VATExemptNature":"NS", "ProductType":"0", "DepartmentNumber":"99"}]}
    ```

    Ecco una spiegazione degli attributi nel mapping:

    - **VATRate** è un'aliquota IVA supportata configurata come codice IVA. Il valore nel mapping ha due posizioni decimali ma nessun separatore decimale. Per esempio, **2200** rappresenta il 22 percento, e **1000** rappresenta il 10 per cento.
    - **VATExemptNature** è applicabile solo nei casi in cui l'aliquota IVA è 0 (zero), inclusi i casi in cui non è prevista l'imposta. Attualmente, **VATExemptNature** è supportato solo per le gift card e il valore nel mapping deve corrispondere al valore della proprietà **VATExemptNatureForGiftCard** nel file di configurazione XML.
    - **ProductType** è il tipo di prodotto. Il valore **0** rappresenta beni mentre il valore **1** rappresenta servizi.
    - **DepartmentNumber** è il numero del reparto che è configurato nella stampante e che corrisponde ai tre attributi precedenti.

    È necessario modificare il mapping di esempio in base alle aliquote IVA configurate nell'applicazione e ai reparti corrispondenti configurati nella stampante fiscale.

- **Motivo di esenzione IVA per gift card** – Il motivo di esenzione IVA che deve essere applicato quando una gift card viene emessa o ricaricata. Il valore deve corrispondere a una voce nel mapping del reparto della stampante fiscale. Il mapping predefinito è **NS**.
- **Abilita articoli gratuiti** – Se questo parametro è attivato, lo speciale tipo di rettifica dello sconto *omaggio* è abilitato per gli articoli con uno sconto del 100%.
- **Codice informativo per origine di reso** – Il codice informativo utilizzato per acquisire l'origine di una transazione di reso se non viene fornita alcuna ricevuta di vendita originale. Questo parametro viene utilizzato insieme ai parametri **Codice informativo per data di vendita originale** e **Mapping origine di reso** per generare un messaggio corretto nello scontrino fiscale circa l'origine di una transazione di reso se non esiste una transazione di vendita originale. 

    Questo codice informativo deve essere configurato per consentire all'utente di selezionare o inserire una delle possibili origini di reso nei negozi. Ad esempio, può essere configurato come un elenco di sottocodici (come **Reso dal sito** o **Reso dal chiosco**). Il parametro **Mapping origine di reso** viene poi utilizzato per tradurre il valore del codice informativo in un comando per la stampante fiscale.

    Il codice informativo selezionato per **Codice informativo per origine di reso** deve essere configurato come un codice informativo obbligatorio che viene attivato una volta per transazione di vendita. Deve essere assegnato come il codice informativo **Reso prodotto** nel profilo della funzionalità POS, in modo che venga attivato quando l'operazione **Reso prodotto** viene eseguita.

    Nessun valore predefinito è specificato per questo mapping. Devi selezionare un codice informativo configurato nella tua applicazione.

- **Codice informativo per data di vendita originale** – Il codice informativo utilizzato per acquisire la data di vendita originale di una transazione di reso se non viene fornita alcuna ricevuta di vendita originale. Questo parametro viene utilizzato insieme ai parametri **Codice informativo per origine di reso** e **Mapping origine di reso** per generare un messaggio corretto nello scontrino fiscale circa l'origine di una transazione di reso se non esiste una transazione di vendita originale.

    Il codice informativo deve essere configurato in modo che il campo **Tipo di input** sia impostato su **Data**. Dovrebbe essere configurato come un codice informativo obbligatorio che viene attivato una volta per transazione di vendita. Dovrebbe anche essere assegnato come **Codice informazioni collegato** per il codice informativo selezionato per il parametro **Codice informativo per origine di reso** , in modo che i due codici informativi vengano attivati uno dopo l'altro.

    Nessun valore predefinito è specificato per questo mapping. Devi selezionare un codice informativo configurato nella tua applicazione.

- **Mapping origine di reso** – Il mapping di origine di reso utilizzato per stampare l'origine di una transazione di reso se non viene fornita alcuna ricevuta di vendita originale. Questo parametro viene utilizzato insieme ai parametri **Codice informativo per origine di reso** e **Codice informativo per data di vendita originale** per generare un messaggio corretto nello scontrino fiscale circa l'origine di una transazione di reso se non esiste una transazione di vendita originale. L'esempio seguente mostra il mapping predefinito.

    ```JSON
    {"ReturnOrigins": [
        {"ReturnOrigin":"1", "PrinterReturnOrigin":"POS"},
        {"ReturnOrigin":"2", "PrinterReturnOrigin":"ND"}
        ],
        "PrinterReturnOriginWithoutFiscalData":"POS"}
    ```

    Ecco una spiegazione degli attributi nel mapping:

    - **ReturnOrigin** è una delle possibili origini do resi nei tuoi negozi. Il valore deve corrispondere a un valore del parametro **Codice informativo per origine di reso**.
    - **PrinterReturnOrigin** è una delle origini di reso accettate dalla stampante fiscale (**POS**, **VR**, o **ND**).
    - **PrinterReturnOriginWithoutFiscalData** è l'origine di reso che la stampante fiscale accetta e che corrisponde a una transazione di reso collegata a una transazione di vendita originale che non ha dati fiscali collegati, perché non è stata registrata tramite una stampante fiscale. In questo caso, la data di vendita originale è identificata come la data della transazione di vendita originale.

I seguenti mapping di dati predefiniti sono obsoleti e vengono conservati solo per compatibilità con le versioni precedenti:

- Mapping dei codici IVA
- Tipo di pagamento deposito

#### <a name="fiscal-connector-settings"></a>Impostazioni del connettore fiscale

Le seguenti impostazioni sono incluse nella configurazione del connettore fiscale fornita nell'esempio di integrazione fiscale:

- **Indirizzo endpoint** - L'URL della stampante.
- **Sincronizzazione data e ora** - Valore che specifica se la data e l'ora della stampante devono essere sincronizzate con la stazione hardware collegata.

### <a name="configure-channel-components"></a>Configurare i componenti del canale

> [!WARNING]
> A causa delle limitazioni del [nuovo modello di packaging ed estensione indipendente](../dev-itpro/build-pipeline.md), non può essere attualmente utilizzato per questo esempio di integrazione fiscale. È necessario utilizzare la versione precedente di Retail SDK su una macchina virtuale per sviluppatori in LCS. Per ulteriori informazioni, vedi [Linee guida per la distribuzione per l'esempio di integrazione della stampante fiscale per l'Italia (legacy)](emea-ita-fpi-sample-sdk.md).
>
> Il supporto per il nuovo modello di packaging ed estensione indipendente per gli esempi di integrazione fiscale è previsto per le versioni successive.

#### <a name="set-up-the-development-environment"></a>Impostare un ambiente di sviluppo

Segui questi passaggi per impostare un ambiente di sviluppo in modo da poter testare ed estendere l'esempio.

1. Clona o scarica il repository [Soluzioni Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions). Seleziona una versione del ramo di rilascio corretta in base alla versione dell'SDK/dell'applicazione. Per altre informazioni vedi [Scaricare gli esempi Retail SDK e i pacchetti di riferimento da GitHub e NuGet](../dev-itpro/retail-sdk/sdk-github.md).
1. Apri la soluzione di integrazione della stampante fiscale in **Dynamics365Commerce.Solutions\\FiscalIntegration\\EpsonFP90IIISample\\EpsonFP90IIISample.sln** e compila.
1. Installa le estensioni CRT:

    1. Trova il programma di installazione dell'estensione CRT:

        - **Commerce Scale Unit:** Nella directory **EpsonFP90IIISample\\ScaleUnit\\ScaleUnit.EpsonFP90III.Installer\\bin\\Debug\\net461** trova il programma di installazione **ScaleUnit.EpsonFP90III.Installer**.
        - **CRT locale su POS moderno:** Nella cartella **EpsonFP90IIISample\\ModernPOS\\ModernPOS.EpsonFP90III.Installer\\bin\\Debug\\net461** trova il programma di installazione **ModernPOS.EpsonFP90III.Installer**.

    1. Avvia il programma di installazione dell'estensione CRT dalla riga di comando:

        - **Commerce Scale Unit:**

            ```Console
            ScaleUnit.EpsonFP90III.Installer.exe install --verbosity 0
            ```

        - **CRT locale su Modern POS:**

            ```Console
            ModernPOS.EpsonFP90III.Installer.exe install --verbosity 0
            ```

1. Installa le estensioni stazione hardware:

    1. Nella cartella **EpsonFP90IIISample\\HardwareStation\\HardwareStation.EpsonFP90III.Installer\\bin\\Debug\\net461** trova il programma di installazione **HardwareStation.EpsonFP90III.Installer**.
    1. Avvia il programma di installazione dell'estensione dalla riga di comando:

        ```Console
        HardwareStation.EpsonFP90III.Installer.exe install --verbosity 0
        ```

#### <a name="production-environment"></a>Ambiente di produzione

Segui i passaggi in [Configurare una pipeline di compilazione per un esempio di integrazione fiscale](fiscal-integration-sample-build-pipeline.md) per generare e rilasciare Cloud Scale Unit e pacchetti distribuibili self-service per l'esempio di integrazione fiscale. Il file YAML del modello **EpsonFP90III build-pipeline.yml** è disponibile nella cartella **Pipeline\\YAML_Files** del repository [Soluzioni Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions).

## <a name="design-of-extensions"></a>Progettazione delle estensioni

L'esempio di integrazione della stampante fiscale per l'Italia si basa sulla [funzionalità di integrazione fiscale](fiscal-integration-for-retail-channel.md) e fa parte di Retail SDK. L'esempio si trova nella cartella **src\\FiscalIntegration\\EpsonFP90IIISample** del repository [Soluzioni Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/) (ad esempio, [l'esempio in release/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/tree/release/9.33/src/FiscalIntegration/EpsonFP90IIISample)). L'esempio [consiste](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices-and-services) di un provider di documenti fiscali, che è un'estensione di CRT e un connettore fiscale, che è un'estensione di Commerce Hardware Station. Per ulteriori informazioni su come utilizzare Retail SDK, vedi [Architettura di Retail SDK](../dev-itpro/retail-sdk/retail-sdk-overview.md) e [Configurare una pipeline di compilazione per SDK a pacchetti indipendenti](../dev-itpro/build-pipeline.md).

> [!WARNING]
> A causa delle limitazioni del [nuovo modello di packaging ed estensione indipendente](../dev-itpro/build-pipeline.md), non può essere attualmente utilizzato per questo esempio di integrazione fiscale. È necessario utilizzare la versione precedente di Retail SDK su una macchina virtuale per sviluppatori in LCS. Per ulteriori informazioni, vedi [Linee guida per la distribuzione per l'esempio di integrazione della stampante fiscale per l'Italia (legacy)](emea-ita-fpi-sample-sdk.md). Il supporto per il nuovo modello di packaging ed estensione indipendente per gli esempi di integrazione fiscale è previsto per le versioni successive.

### <a name="commerce-runtime-extension-design"></a>Progettazione dell'estensione di Commerce Runtime

Lo scopo dell'estensione (provider di documenti) è di generare documenti specifici per la stampante e di gestire le risposte dalla stampante fiscale.

#### <a name="request-handler"></a>Gestore richieste

Il gestore richieste **DocumentProviderEpsonFP90III** è il punto di ingresso per la richiesta di generare documenti dalla stampante fiscale.

Il gestore viene ereditato dall'interfaccia **INamedRequestHandler**. Il metodo **HandlerName** è responsabile della restituzione del nome del gestore. Il nome del gestore deve corrispondere al nome del fornitore di documenti del connettore specificato in Commerce headquarters.

Il connettore supporta le seguenti richieste:

- **GetFiscalDocumentDocumentProviderRequest** - Contiene informazioni su quale documento dovrà essere generato. Restituisce un documento specifico della stampante che deve essere registrato nella stampante fiscale.
- **GetSupportedRegistrableEventsDocumentProviderRequest** - Restituisce l'elenco degli eventi da sottoscrivere. Attualmente, i seguenti eventi sono supportati: vendita, stampa del report X e stampa del report Z.

#### <a name="configuration"></a>Configurazione

Il file di configurazione per il provider di documenti fiscali si trova in **src\\FiscalIntegration\\EpsonFP90IIISample\\CommerceRuntime\\DocumentProvider.EpsonFP90IIISample\\Configuration\\DocumentProviderEpsonFP90IIISample.xml** nel repository [Soluzioni Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/). Lo scopo del file è di consentire la configurazione delle impostazioni per il provider di documenti da Commerce headquarters. Il formato di file è allineato ai requisiti per la configurazione dell'integrazione fiscale.

### <a name="hardware-station-extension-design"></a>Progettazione dell'estensione stazione hardware

Lo scopo dell'estensione (connettore fiscale) è di comunicare con la stampante fiscale. Questa estensione utilizza il protocollo HTTP per inviare documenti generati dall'estensione CRT per la stampante fiscale. Gestisce inoltre le risposte ricevute dalla stampante fiscale.

#### <a name="request-handler"></a>Gestore richieste

Il gestore richieste **EpsonFP90IIISample** è il punto di ingresso per la trasmissione della richiesta alla periferica fiscale.

Il gestore viene ereditato dall'interfaccia **INamedRequestHandler**. Il metodo **HandlerName** è responsabile della restituzione del nome del gestore. Il nome del gestore deve corrispondere al nome del connettore fiscale specificato in Commerce headquarters.

Il connettore supporta le seguenti richieste:

- **SubmitDocumentFiscalDeviceRequest** - Invia documenti alle stampanti e restituisce la risposta dalla stampante fiscale.
- **IsReadyFiscalDeviceRequest** - Viene utilizzata per un controllo di integrità del dispositivo.
- **InitializeFiscalDeviceRequest** - È utilizzata per l'inizializzazione della stampante.

#### <a name="configuration"></a>Configurazione

Il file di configurazione per il connettore fiscale si trova in **src\\FiscalIntegration\\EpsonFP90IIISample\\HardwareStation\\EpsonFP90IIIFiscalDeviceSample\\Configuration\\ConnectorEpsonFP90IIISample.xml** nel repository [Soluzioni Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/). Lo scopo del file è di consentire la configurazione delle impostazioni per il connettore da Commerce headquarters. Il formato di file è allineato ai requisiti per la configurazione dell'integrazione fiscale.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
