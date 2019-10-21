---
title: Esempio di integrazione di stampante fiscale per l'Italia
description: In questo argomento viene fornita una panoramica dell'esempio di integrazione fiscale per l'Italia.
author: josaw
manager: annbe
ms.date: 01/23/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailFunctionalityProfile, RetailFormLayout, RetailParameters
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.search.region: Italy
ms.search.industry: Retail
ms.author: sepism
ms.search.validFrom: 2018-11-1
ms.dyn365.ops.version: 8.1.1
ms.openlocfilehash: 71b9514d63668ed1ba0935f049ade48c99b211be
ms.sourcegitcommit: f87de0f949b5d60993b19e0f61297f02d42b5bef
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/24/2019
ms.locfileid: "2023380"
---
# <a name="fiscal-printer-integration-sample-for-italy"></a>Esempio di integrazione di stampante fiscale per l'Italia

[!include [banner](../includes/banner.md)]

## <a name="introduction"></a>Introduzione

La funzionalità di Retail per l'Italia include un'integrazione di esempio del POS con una stampante fiscale. L'esempio estende la [funzionalità di integrazione fiscale](fiscal-integration-for-retail-channel.md) di modo che sia utilizzabile con le stampanti [Epson FP-90III Series](https://www.epson.it/products/sd/pos-printer/epson-fp-90iii-series) di Epson e abilita la comunicazione con una stampante fiscale in modalità server Web via il servizio Web EpsonFPMate utilizzando l'API Fiscal ePOS-Print. L'esempio supporta soltanto la modalità Registratore Telematico (RT). L'esempio viene fornito sotto forma di codice sorgente e fa parte del kit SDK.

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
        - Stampare una ricevuta fiscale per righe di esecuzione di un ordine cliente ibrido.
        - Stampare una ricevuta fiscale per l'operazione di prelievo per un ordine cliente.
        - Stampare una ricevuta fiscale per un ordine di reso.

    - Stampare un codice a barre per il numero di ricevuta su una ricevuta fiscale.

- Rendiconti di riepilogo giornalieri (report X e Z fiscali).
- Gestione degli errori, ad esempio le seguenti opzioni:

    - Se possibile, ripetere la registrazione fiscale nel caso la stampante fiscale non sia collegata, pronta o non risponda o se la carta risulta mancante o inceppata.
    - Posticipare la registrazione fiscale.
    - Ignorare la registrazione fiscale, o contrassegnare la transazione come registrata, e includere i codici informativi per acquisire il motivo dell'errore e ulteriori informazioni.
    - Verificare la disponibilità della stampante fiscale prima dell'apertura di una nuova transazione di vendita o della finalizzazione di una transazione di vendita.

### <a name="default-data-mapping"></a>Mapping dei dati predefiniti

Il mapping dei dati predefiniti seguente è incluso nella configurazione di fornitore di documenti fiscali fornita nell'esempio di integrazione fiscale:

- Mapping delle aliquote IVA:

    *1 : 22.00 ; 2 : 10.00 ; 3 : 4.00 ; 4 : 0.00*

- Mapping del tipo di metodo di pagamento:

    *1 : 0 ; 2 : 1 ; 3 : 2 ; 4 : 2 ; 5 : 0 ; 6 : 0 ; 7 : 0 ; 8 : 2 ; 9 : 0 ; 10 : 2 ; 11 : 1*

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

- La stampante fiscale supporta solo gli scenari in cui l'IVA è inclusa nel prezzo. Di conseguenza, l'opzione **Prezzi IVA inclusa** deve essere impostata su **Sì** per i punti vendita al dettaglio e i clienti.
- I report giornalieri (X e Z fiscali) vengono stampati utilizzando il formato incorporato nel firmware della stampante fiscale.
- Le transazioni miste non sono supportate dalla stampante fiscale. L'opzione **Impedisci di combinare vendite e resi in una ricevuta** deve essere impostata su **Sì** nei profili funzionalità POS.
- L'esempio supporta l'integrazione solo con una stampante fiscale che funziona in modalità RT (Registrazione Telematico).

## <a name="set-up-retail-for-italy"></a>Impostazione vendita al dettaglio per l'Italia

### <a name="configure-fiscal-integration"></a>Configurare l'integrazione fiscale

Completare la procedura di configurazione dell'integrazione fiscale come descritto in [Impostare l'integrazione fiscale per canali di vendita al dettaglio](setting-up-fiscal-integration-for-retail-channel.md):

- [Configurare un processo di registrazione fiscale](setting-up-fiscal-integration-for-retail-channel.md#set-up-a-fiscal-registration-process). Da notare anche le impostazioni per il processo di registrazione fiscale che sono [specifiche dell'esempio di integrazione della stampante fiscale](#set-up-the-registration-process).
- [Impostare testi fiscali per sconti](setting-up-fiscal-integration-for-retail-channel.md#set-up-fiscal-texts-for-discounts).
- [Configurare le impostazioni di gestione degli errori](setting-up-fiscal-integration-for-retail-channel.md#set-error-handling-settings).
- [Configurare report X/Z fiscali dal POS](setting-up-fiscal-integration-for-retail-channel.md#set-up-fiscal-xz-reports-from-the-pos).
- [Abilitare l'esecuzione manuale della registrazione fiscale posticipata](setting-up-fiscal-integration-for-retail-channel.md#enable-manual-execution-of-postponed-fiscal-registration).

### <a name="enable-extensions"></a>Abilitare le estensioni

#### <a name="commerce-runtime-extension-components"></a>Componenti dell'estensione di Commerce Runtime

I componenti dell'estensione di Commerce Runtime sono inclusi in Retail SDK. Per completare le seguenti procedure, aprire la soluzione CRT, **CommerceRuntimeSamples.sln**, in **RetailSdk\\SampleExtensions\\CommerceRuntime**.

1. Individuare il progetto **Runtime.Extensions.DocumentProvider.EpsonFP90IIISample** e compilarlo.
1. Nella cartella **Extensions.DocumentProvider.EpsonFP90IIISample\\bin\\Debug**, trovare il file assembly **Contoso.Commerce.Runtime.DocumentProvider.EpsonFP90IIISample.dll**.
1. Copiare il file assembly alla cartella dell'estensione CRT:

    - **Server Retail**: copiare l'assembly nella cartella **\\bin\\ext** nella posizione del sito del Server Retail Microsoft Internet Information Services (IIS).
    - **CRT locale su POS moderno**: copiare l'assembly nella cartella **\\ext** nella posizione del broker client CRT locale.

1. Individuare il file di configurazione di estensioni per il CRT:

    - **Server Retail**: il file si chiama **commerceruntime.ext.config** e si trova nella cartella bin\\ext nella posizione del sito del Server Retail IIS.
    - **CRT locale sul POS moderno:** il file si chiama **CommerceRuntime.MPOSOffline.Ext.config** e si trova nella posizione del broker client CRT locale.

1. Registrare la modifica CRT nel file di configurazione di estensioni. Aggiungere **source="assembly" value="Contoso.Commerce.Runtime.DocumentProvider.EpsonFP90IIISample"**.
1. Riavviare il servizio vendita al dettaglio:

    - **Server Retail**: riavviare il sito del servizio di vendita al dettaglio da Gestione IIS.
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

Per abilitare il processo di registrazione, seguire la procedura seguente per configurare Retail Headquarters. Per ulteriori informazioni, vedere [Configurare un processo di registrazione fiscale](setting-up-fiscal-integration-for-retail-channel.md#set-up-a-fiscal-registration-process).

1. Accedere a **Vendita al dettaglio \> Impostazione canale \> Integrazione fiscale \> Connettori fiscali**. Importare la configurazione da **RetailSdk\\SampleExtensions\\HardwareStation\\Entension.EpsonFP90IIIFiscalDeviceSample\\Configuration\\ConnectorEpsonFP90IIISample.xml**.
2. Accedere a **Vendita al dettaglio \> Impostazione canale \> Integrazione fiscale \> Fornitori di documenti fiscali**. Importare la configurazione da **RetailSdk\\SampleExtensions\\CommerceRuntime\\Entension.DocumentProvider.EpsonFP90IIISample\\Configuration\\DocumentProviderEpsonFP90IIISample.xml**.
3. Accedere a **Vendita al dettaglio \> Impostazione canale \> Integrazione fiscale \> Profili tecnici del connettore**. Creare un nuovo profilo e selezionare il connettore caricato nel passaggio precedente. Aggiornare le impostazioni di connessione se un aggiornamento è necessario.
4. Accedere a **Vendita al dettaglio \> Impostazione canale \> Integrazione fiscale \> Profili funzionali del connettore**. Creare un nuovo profilo e selezionare il connettore e il fornitore di documenti caricati nei passaggi precedenti. Aggiornare le impostazioni di mapping dei dati se un aggiornamento è necessario.
5. Accedere a **Vendita al dettaglio \> Impostazione canale \> Integrazione fiscale \> Gruppo funzionale di connettori**. Creare un nuovo gruppo e selezionare il profilo funzionale del connettore del passaggio precedente.
6. Accedere a **Vendita al dettaglio \> Impostazione canale \> Integrazione fiscale \> Processo di registrazione**. Creare un nuovo processo e selezionare il gruppo funzionale di connettori del passaggio precedente.
7. Passare a **Vendita al dettaglio \> Impostazione canale \> Impostazioni POS \> Profili POS \> Profili funzionalità**. Aprire il profilo funzionalità collegato al punto vendita in cui il processo di registrazione deve essere attivato. Nella scheda Dettaglio **Processo di registrazione fiscale**, selezionare il processo di registrazione creato nel precedentemente.
8. Passare a **Vendita al dettaglio \> Impostazione canale \> Impostazioni POS \> Profili POS \> Profili hardware**. Aprire il profilo hardware collegato alla stazione hardware a cui la stampante fiscale sarà collegata. Nella scheda Dettaglio **Periferiche fiscali**, selezionare il profilo tecnico del connettore.
9. Aprire la programmazione della distribuzione (**Vendita al dettaglio \> Vendita al dettaglio IT \> Programmazione della distribuzione**) e selezionare i processi **1070** e **1090** per trasferire i dati al database del canale.

### <a name="production-environment"></a>Ambiente di produzione

Attenersi alla procedura seguente per creare pacchetti distribuibili contenenti componenti Retail e per applicare quei pacchetti a un ambiente di produzione.

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

4. Avviare il prompt dei comandi di MSBuild per l'utilità Visual Studio ed eseguire **msbuild** nella cartella Retail SDK per creare pacchetti distribuibili.
5. Applicare i pacchetti via Microsoft Dynamics Lifecycle Services (LCS) o manualmente. Per ulteriori informazioni, vedere [Creare pacchetti distribuibili di vendita al dettaglio](../dev-itpro/retail-sdk/retail-sdk-packaging.md).

## <a name="design-of-extensions"></a>Progettazione delle estensioni

### <a name="commerce-runtime-extension-design"></a>Progettazione dell'estensione di Commerce Runtime

Lo scopo dell'estensione (fornitore di documenti) è di generare documenti specifici per la stampante e di gestire le risposte dalla stampante fiscale.

L'estensione di Commerce Runtime è **Runtime.Extensions.DocumentProvider.EpsonFP90IIISample**.

Per ulteriori informazioni sulla progettazione della soluzione di integrazione fiscale, vedere [Processo di registrazione fiscale ed esempi di integrazione fiscale per dispositivi fiscali](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices).

#### <a name="request-handler"></a>Gestore richieste
    
Il gestore richieste **DocumentProviderEpsonFP90III** è il punto di ingresso per la richiesta di generare documenti dalla stampante fiscale.

Il gestore viene ereditato dall'interfaccia **INamedRequestHandler**. Il metodo **HandlerName** è responsabile della restituzione del nome del gestore. Il nome del gestore deve corrispondere al nome del fornitore di documenti del connettore specificato in Retail Headquarters.

Il connettore supporta le seguenti richieste:

- **GetFiscalDocumentDocumentProviderRequest** - Contiene informazioni su quale documento dovrà essere generato. Restituisce un documento specifico della stampante che deve essere registrato nella stampante fiscale.
- **GetSupportedRegistrableEventsDocumentProviderRequest** - Restituisce l'elenco degli eventi da sottoscrivere. Attualmente, i seguenti eventi sono supportati: vendita, stampa del report X e stampa del report Z.

#### <a name="configuration"></a>Configurazione

Il file di configurazione si trova nella cartella **Configuration** del progetto di estensione. Lo scopo del file è di consentire la configurazione delle impostazioni per il fornitore di documenti da Retail Headquarters. Il formato di file è allineato ai requisiti per la configurazione dell'integrazione fiscale. Vengono aggiunte le seguenti impostazioni:

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

Il gestore viene ereditato dall'interfaccia **INamedRequestHandler**. Il metodo **HandlerName** è responsabile della restituzione del nome del gestore. Il nome del gestore deve corrispondere al nome del connettore fiscale specificato in Retail Headquarters.

Il connettore supporta le seguenti richieste:

- **SubmitDocumentFiscalDeviceRequest** - Invia documenti alle stampanti e restituisce la risposta dalla stampante fiscale.
- **IsReadyFiscalDeviceRequest** - Viene utilizzata per un controllo di integrità del dispositivo.
- **InitializeFiscalDeviceRequest** - È utilizzata per l'inizializzazione della stampante.

#### <a name="configuration"></a>Configurazione

Il file di configurazione si trova nella cartella **Configuration** del progetto di estensione. Lo scopo del file è di consentire la configurazione delle impostazioni per il connettore da Retail Headquarters. Il formato di file è allineato ai requisiti per la configurazione dell'integrazione fiscale. Vengono aggiunte le seguenti impostazioni:

- **Indirizzo endpoint** - L'URL della stampante.
- **Sincronizzazione data e ora** - Questa impostazione specifica se la data e l'ora della stampante devono essere sincronizzate con la stazione hardware collegata.
