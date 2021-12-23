---
title: Esempio di integrazione di stampante fiscale per l'Italia
description: In questo argomento viene fornita una panoramica dell'esempio di integrazione fiscale per l'Italia.
author: EvgenyPopovMBS
ms.date: 11/30/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailFunctionalityProfile, RetailFormLayout, RetailParameters
audience: Application User
ms.reviewer: josaw
ms.search.region: Italy
ms.search.industry: Retail
ms.author: sepism
ms.search.validFrom: 2018-11-1
ms.dyn365.ops.version: 8.1.1
ms.openlocfilehash: d9feeeec934e85dc9c5033e6fcd827a05e73ff5b
ms.sourcegitcommit: 971456c197820421f108ad7345001cc1b6c99949
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/01/2021
ms.locfileid: "7875439"
---
# <a name="fiscal-printer-integration-sample-for-italy"></a>Esempio di integrazione di stampante fiscale per l'Italia

[!include [banner](../includes/banner.md)]

## <a name="introduction"></a>Introduzione

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

### <a name="default-data-mapping"></a>Mapping dei dati predefiniti

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
- L'esempio supporta l'integrazione solo con una stampante fiscale che funziona in modalità RT (Registrazione Telematico).

## <a name="set-up-commerce-for-italy"></a>Impostazione di Commerce per l'Italia

### <a name="configure-fiscal-integration"></a>Configurare l'integrazione fiscale

Completare la procedura di configurazione dell'integrazione fiscale come descritto in [Impostare l'integrazione fiscale per canali di Commerce](setting-up-fiscal-integration-for-retail-channel.md):

- [Configurare un processo di registrazione fiscale](setting-up-fiscal-integration-for-retail-channel.md#set-up-a-fiscal-registration-process). Da notare anche le impostazioni per il processo di registrazione fiscale che sono [specifiche dell'esempio di integrazione della stampante fiscale](#set-up-the-registration-process).
- [Impostare testi fiscali per sconti](setting-up-fiscal-integration-for-retail-channel.md#set-up-fiscal-texts-for-discounts).
- [Configurare le impostazioni di gestione degli errori](setting-up-fiscal-integration-for-retail-channel.md#set-error-handling-settings).
- [Configurare report X/Z fiscali dal POS](setting-up-fiscal-integration-for-retail-channel.md#set-up-fiscal-xz-reports-from-the-pos).
- [Abilitare l'esecuzione manuale della registrazione fiscale posticipata](setting-up-fiscal-integration-for-retail-channel.md#enable-manual-execution-of-postponed-fiscal-registration).
- [Impostare la funzionalità per la gestione delle informazioni del cliente nel POS](emea-ita-customer-information.md#setup)

### <a name="enable-extensions"></a>Abilitare le estensioni

#### <a name="commerce-runtime-extension-components"></a>Componenti dell'estensione di Commerce Runtime

I componenti dell'estensione di Commerce Runtime sono inclusi in Retail SDK. Per completare le seguenti procedure, aprire la soluzione CRT, **CommerceRuntimeSamples.sln**, in **RetailSdk\\SampleExtensions\\CommerceRuntime**.

1. Individuare il progetto **Runtime.Extensions.DocumentProvider.EpsonFP90IIISample** e compilarlo.
1. Nella cartella **Extensions.DocumentProvider.EpsonFP90IIISample\\bin\\Debug**, trovare il file assembly **Contoso.Commerce.Runtime.DocumentProvider.EpsonFP90IIISample.dll**.
1. Copiare il file assembly alla cartella dell'estensione CRT:

    - **Commerce Scale Unit**: copiare l'assembly nella cartella **\\bin\\ext** nella posizione del sito di Commerce Scale Unit Internet Information Services (IIS).
    - **CRT locale su POS moderno**: copiare l'assembly nella cartella **\\ext** nella posizione del broker client CRT locale.

1. Individuare il file di configurazione di estensioni per il CRT:

    - **Commerce Scale Unit**: il file si chiama **commerceruntime.ext.config** e si trova nella cartella bin\\ext nella posizione del sito di Commerce Scale Unit IIS.
    - **CRT locale sul POS moderno:** il file si chiama **CommerceRuntime.MPOSOffline.Ext.config** e si trova nella posizione del broker client CRT locale.

1. Registrare la modifica CRT nel file di configurazione di estensioni. Aggiungere **source="assembly" value="Contoso.Commerce.Runtime.DocumentProvider.EpsonFP90IIISample"**.
1. Riavviare Commerce Scale Unit:

    - **Commerce Scale Unit:** riavviare il sito Commerce Scale Unit da IIS Manager.
    - **Broker client**: terminare il processo **dllhost.exe** in Gestione attività quindi riavviare il POS moderno.

#### <a name="hardware-station-extension-components"></a>Componenti dell'estensione stazione hardware

I componenti dell'estensione stazione hardware sono inclusi in Retail SDK. Per completare le seguenti procedure, aprire la soluzione Stazione hardware, **HardwareStationSamples.sln**, in **RetailSdk\\SampleExtensions\\HardwareStation**.

1. Individuare il progetto **HardwareStation.Extensions.EpsonFP90IIIFiscalDeviceSample** e compilarlo.
2. Nella cartella **Extensions.EpsonFP90IIIFiscalDeviceSample\\bin\\Debug**, trovare il file assembly **Contoso.Commerce.HardwareStation.EpsonFP90IIIFiscalDeviceSample.dll**.
3. Copiare i file in un computer stazione hardware distribuito:

    - **Stazione hardware remota**: copiare i file nella cartella **bin** nella posizione del sito stazione hardware IIS.
    - **Stazione hardware locale**: copiare i file nella posizione del broker client POS moderno.

4. Individuare il file di configurazione per le estensioni della stazione hardware. Il file si chiama **HardwareStation.Extension.config**:

    - **Stazione hardware remota**: il file si trova sotto la posizione del sito della stazione hardware IIS.
    - **Stazione hardware locale**: il file si trova nella posizione del broker client POS moderno.
    
5. Aggiungere la sezione seguente alla sezione di **composizione** del file di configurazione.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.HardwareStation.Extension.EpsonFP90IIIFiscalDeviceSample" />
    ```

6. Riavviare il servizio della stazione hardware:

    - **Stazione hardware remota**: Riavviare il sito della stazione hardware da Gestione IIS.
    - **Stazione hardware locale**: terminare il processo **dllhost.exe** in Gestione attività quindi riavviare il POS moderno.

### <a name="set-up-the-registration-process"></a>Impostare il processo di registrazione

Per abilitare il processo di registrazione, seguire questi passaggi per configurare Headquarters: Per ulteriori informazioni, vedere [Configurare un processo di registrazione fiscale](setting-up-fiscal-integration-for-retail-channel.md#set-up-a-fiscal-registration-process).

1. Accedere a **Retail e Commerce \> Impostazione canale \> Integrazione fiscale \> Connettori fiscali**. Importare la configurazione da **RetailSdk\\SampleExtensions\\HardwareStation\\Entension.EpsonFP90IIIFiscalDeviceSample\\Configuration\\ConnectorEpsonFP90IIISample.xml**.
2. Accedere a **Retail e Commerce \> Impostazione canale \> Integrazione fiscale \> Provider di documenti fiscali**. Importare la configurazione da **RetailSdk\\SampleExtensions\\CommerceRuntime\\Entension.DocumentProvider.EpsonFP90IIISample\\Configuration\\DocumentProviderEpsonFP90IIISample.xml**.
3. Accedere a **Retail e Commerce \> Impostazione canale \> Integrazione fiscale \> Profili tecnici del connettore**. Creare un nuovo profilo, quindi selezionare il connettore caricato nel passaggio precedente. Aggiornare le impostazioni di connessione se un aggiornamento è necessario.
4. Accedere a **Retail e Commerce \> Impostazione canale \> Integrazione fiscale \> Profili funzionali del connettore**. Creare un nuovo profilo, quindi selezionare il connettore e il provider di documenti caricati nei passaggi precedenti. Aggiornare le impostazioni di mapping dei dati se un aggiornamento è necessario.
5. Accedere a **Retail e Commerce \> Impostazione canale \> Integrazione fiscale \> Gruppo funzionale di connettori**. Creare un nuovo gruppo, quindi selezionare il profilo funzionale del connettore del passaggio precedente.
6. Accedere a **Retail e Commerce \> Impostazione canale \> Integrazione fiscale \> Processo di registrazione**. Creare un nuovo processo, quindi selezionare il gruppo funzionale di connettori del passaggio precedente.
7. Passare a **Retail e Commerce \> Impostazione canale \> Impostazione POS \> Profili POS \> Profili funzionalità**. Aprire il profilo funzionalità collegato al punto vendita in cui il processo di registrazione deve essere attivato. Nella scheda Dettaglio **Processo di registrazione fiscale**, selezionare il processo di registrazione creato nel precedentemente.
8. Andare a **Retail e Commerce \> Impostazione canale \> Impostazioni POS \> Profili POS \> Profili hardware**. Aprire il profilo hardware collegato alla stazione hardware a cui la stampante fiscale sarà collegata. Nella scheda Dettaglio **Periferiche fiscali**, selezionare il profilo tecnico del connettore.
9. Aprire la programmazione della distribuzione (**Retail e Commerce \> Vendita al dettaglio e commercio IT \> Programmazione della distribuzione**), quindi selezionare i processi **1070** e **1090** per trasferire i dati al database del canale.

### <a name="production-environment"></a>Ambiente di produzione

Per creare pacchetti distribuibili contenenti componenti Commerce e per applicare quei pacchetti a un ambiente di produzione, attenersi alla procedura seguente.

1. Completare la procedura descritta nella sezione [Abilitare le estensioni](#enable-extensions) vista in precedenza in questo argomento.
2. Apportare le seguenti modifiche nei file di configurazione dei pacchetti nella cartella **RetailSdk\\Assets** :

    - Nei file di configurazione **CommerceRuntime.MPOSOffline.Ext.config** e **commerceruntime.ext.config**, aggiungere la seguente riga alla sezione **composition**.

        ``` xml 
        <add source="assembly" value="Contoso.Commerce.Runtime.DocumentProvider.EpsonFP90IIISample" />
        ```

    - Nel file di configurazione **HardwareStation.Extension.config**, aggiungere la seguente riga alla sezione **composition**.

        ``` xml 
        <add source="assembly" value="Contoso.Commerce.HardwareStation.Extension.EpsonFP90IIIFiscalDeviceSample" />
        ```

3. Apportare le seguenti modifiche nel file di configurazione di personalizzazione dei pacchetti **BuildTools\\Customization.settings**:

    - Aggiungere la seguente riga per includere l'estensione CRT nei pacchetti distribuibili.

        ``` xml 
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.DocumentProvider.EpsonFP90IIISample.dll"/>
        ```

    - Aggiungere la seguente riga per includere l'estensione stazione hardware nei pacchetti distribuibili.

        ``` xml 
        <ISV_HardwareStation_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.HardwareStation.EpsonFP90IIIFiscalDeviceSample.dll"/>
        ```

4. Avviare il prompt dei comandi di MSBuild per l'utilità Visual Studio, quindi eseguire **msbuild** nella cartella Retail SDK per creare pacchetti distribuibili.
5. Applicare i pacchetti via Microsoft Dynamics Lifecycle Services (LCS) o manualmente. Per ulteriori informazioni, vedere [Creare pacchetti distribuibili](../dev-itpro/retail-sdk/retail-sdk-packaging.md).

## <a name="design-of-extensions"></a>Progettazione delle estensioni

### <a name="commerce-runtime-extension-design"></a>Progettazione dell'estensione di Commerce Runtime

Lo scopo dell'estensione (provider di documenti) è di generare documenti specifici per la stampante e di gestire le risposte dalla stampante fiscale.

L'estensione di Commerce Runtime è **Runtime.Extensions.DocumentProvider.EpsonFP90IIISample**.

Per ulteriori informazioni sulla progettazione della soluzione di integrazione fiscale, vedere [Processo di registrazione fiscale ed esempi di integrazione fiscale per dispositivi fiscali](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices).

#### <a name="request-handler"></a>Gestore richieste
    
Il gestore richieste **DocumentProviderEpsonFP90III** è il punto di ingresso per la richiesta di generare documenti dalla stampante fiscale.

Il gestore viene ereditato dall'interfaccia **INamedRequestHandler**. Il metodo **HandlerName** è responsabile della restituzione del nome del gestore. Il nome del gestore deve corrispondere al nome del provider di documenti del connettore specificato in Headquarters.

Il connettore supporta le seguenti richieste:

- **GetFiscalDocumentDocumentProviderRequest** - Contiene informazioni su quale documento dovrà essere generato. Restituisce un documento specifico della stampante che deve essere registrato nella stampante fiscale.
- **GetSupportedRegistrableEventsDocumentProviderRequest** - Restituisce l'elenco degli eventi da sottoscrivere. Attualmente, i seguenti eventi sono supportati: vendita, stampa del report X e stampa del report Z.

#### <a name="configuration"></a>Configurazione

Il file di configurazione si trova nella cartella **Configuration** del progetto di estensione. Lo scopo del file è di consentire la configurazione delle impostazioni per il provider di documenti da Headquarters. Il formato di file è allineato ai requisiti per la configurazione dell'integrazione fiscale. Vengono aggiunte le seguenti impostazioni:

- Mapping codici IVA
- Mapping aliquote IVA
- Mapping tipo di metodo di pagamento
- Tipo di codice a barre per numero ricevuta
- Tipo di pagamento deposito

### <a name="hardware-station-extension-design"></a>Progettazione dell'estensione stazione hardware

Lo scopo dell'estensione (connettore fiscale) è di comunicare con la stampante fiscale.

L'estensione stazione hardware è **HardwareStation.Extension.EpsonFP90IIIFiscalDeviceSample**. Questa estensione utilizza il protocollo HTTP per inviare documenti generati dall'estensione di Commerce Runtime per la stampante fiscale. Gestisce inoltre le risposte ricevute dalla stampante fiscale.

#### <a name="request-handler"></a>Gestore richieste

Il gestore richieste **EpsonFP90IIISample** è il punto di ingresso per la trasmissione della richiesta alla periferica fiscale.

Il gestore viene ereditato dall'interfaccia **INamedRequestHandler**. Il metodo **HandlerName** è responsabile della restituzione del nome del gestore. Il nome del gestore deve corrispondere al nome del connettore fiscale specificato in Headquarters.

Il connettore supporta le seguenti richieste:

- **SubmitDocumentFiscalDeviceRequest** - Invia documenti alle stampanti e restituisce la risposta dalla stampante fiscale.
- **IsReadyFiscalDeviceRequest** - Viene utilizzata per un controllo di integrità del dispositivo.
- **InitializeFiscalDeviceRequest** - È utilizzata per l'inizializzazione della stampante.

#### <a name="configuration"></a>Configurazione

Il file di configurazione si trova nella cartella **Configuration** del progetto di estensione. Lo scopo del file è di consentire la configurazione delle impostazioni per il connettore da Headquarters. Il formato di file è allineato ai requisiti per la configurazione dell'integrazione fiscale. Vengono aggiunte le seguenti impostazioni:

- **Indirizzo endpoint** - L'URL della stampante.
- **Sincronizzazione data e ora** - Questa impostazione specifica se la data e l'ora della stampante devono essere sincronizzate con la stazione hardware collegata.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
