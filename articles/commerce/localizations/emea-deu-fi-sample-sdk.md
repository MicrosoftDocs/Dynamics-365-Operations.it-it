---
title: Linee guida per la distribuzione dell'esempio di integrazione del servizio di registrazione fiscale per la Germania (legacy)
description: Questo articolo fornisce le linee guida per la distribuzione dell'esempio di integrazione fiscale per la Germania da Microsoft Dynamics 365 Commerce Retail software development kit (SDK).
author: EvgenyPopovMBS
ms.date: 08/17/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2019-03-01
ms.openlocfilehash: 7315b6bb145ccdc5631a558af88de55660ebf877
ms.sourcegitcommit: 0feb5d0b06e04f99903069ff2801577be86b8555
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/18/2022
ms.locfileid: "9313857"
---
# <a name="deployment-guidelines-for-the-fiscal-registration-service-integration-sample-for-germany-legacy"></a>Linee guida per la distribuzione dell'esempio di integrazione del servizio di registrazione fiscale per la Germania (legacy)

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

> [!IMPORTANT]
> Devi seguire le linee guida in questo articolo solo se stai usando Microsoft Dynamics 365 Commerce versione 10.0.28 o precedente. A partire dalla versione 10.0.29 di Commerce, l'esempio di integrazione del servizio di registrazione fiscale per la Germania è disponibile in Commerce SDK. Per ulteriori informazioni, vedi [Configurare i componenti del canale](./emea-deu-fi-sample.md#configure-channel-components).

Questo articolo fornisce le linee guida per la distribuzione dell'esempio di integrazione del servizio di registrazione fiscale per la Germania da Dynamics 365 Commerce Retail SDK in una macchina virtuale per sviluppatori (VM) in Microsoft Dynamics Lifecycle Services (LCS). Per maggiori informazioni sull'esempio di integrazione fiscale, vedi [Esempio di integrazione del servizio di registrazione fiscale per la Germania](emea-deu-fi-sample.md). 

L'esempio di integrazione fiscale per la Germania fa parte di Retail SDK. Per informazioni su come installare e utilizzare SDK, vedi [Architettura di Retail SDK](../dev-itpro/retail-sdk/retail-sdk-overview.md). Questo esempio è costituito da estensioni per Commerce Runtime (CRT) e stazione hardware. Per eseguire questo esempio, è necessario modificare e creare progetti CRT e stazione hardware. Ti consigliamo di utilizzare un SDK Retail non modificato per apportare le modifiche descritte in questo articolo. Si consiglia inoltre di utilizzare un sistema di controllo del codice sorgente, come Azure DevOps dove nessun file è stato ancora modificato.

## <a name="development-environment"></a>Ambiente di sviluppo

Segui questi passaggi per configurare un ambiente di sviluppo in modo da poter testare ed estendere l'esempio.

### <a name="enable-commerce-runtime-extensions"></a>Abilitare le estensioni di Commerce Runtime

I componenti dell'estensione CRT sono inclusi negli esempi CRT. Per completare le seguenti procedure, apri la soluzione **CommerceRuntimeSamples.sln** in **RetailSdk\\SampleExtensions\\CommerceRuntime**.

#### <a name="documentproviderefrsample-component"></a>Componente DocumentProvider.EFRSample

1. Individua il progetto **Runtime.Extensions.DocumentProvider.EFRSample** e compilalo.
2. Nella cartella **Runtime.Extensions.DocumentProvider.EFRSample\\bin\\Debug**, trova il file assembly **Contoso.Commerce.Runtime.DocumentProvider.EFRSample.dll**.
3. Copiare il file assembly alla cartella dell'estensione CRT:

    - **Commerce Scale Unit**: copia il file nella cartella **\\bin\\ext** nella posizione del sito Internet Information Services (IIS) Commerce Scale Unit.
    - **CRT locale su POS moderno**: copia il file nella cartella **\\ext** nella posizione del broker client CRT locale.

4. Individua il file di configurazione dell'estensione per CRT:

    - **Commerce Scale Unit:** il file si chiama **commerceruntime.ext.config** e si trova nella cartella **bin\\ext** nella posizione del sito IIS Commerce Scale Unit.
    - **CRT locale sul POS moderno:** il file si chiama **CommerceRuntime.MPOSOffline.Ext.config** e si trova nella posizione del broker client CRT locale.

5. Registra la modifica CRT nel file di configurazione dell'estensione.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.DocumentProvider.EFRSample" />
    ```

#### <a name="documentproviderdatamodelefr-component"></a>Componente DocumentProvider.DataModelEFR

1. Individua il progetto **Runtime.Extensions.DocumentProvider.DataModelEFR** e compilalo.
2. Nella cartella **Runtime.Extensions.DocumentProvider.DataModelEFR\\bin\\Debug**, trova il file assembly **Contoso.Commerce.Runtime.DocumentProvider.DataModelEFR.dll**.
3. Copiare il file assembly alla cartella dell'estensione CRT:

    - **Commerce Scale Unit**: copia il file nella cartella **\\bin\\ext** nella posizione del sito IIS Commerce Scale Unit.
    - **CRT locale su POS moderno**: copia il file nella cartella **\\ext** nella posizione del broker client CRT locale.

4. Individua il file di configurazione dell'estensione per CRT:

    - **Commerce Scale Unit:** il file si chiama **commerceruntime.ext.config** e si trova nella cartella **bin\\ext** nella posizione del sito IIS Commerce Scale Unit.
    - **CRT locale sul POS moderno:** il file si chiama **CommerceRuntime.MPOSOffline.Ext.config** e si trova nella posizione del broker client CRT locale.

5. Registra la modifica CRT nel file di configurazione dell'estensione.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.DocumentProvider.DataModelEFR" />
    ```

#### <a name="extension-configuration-file"></a>File di configurazione dell'estensione

1. Individua il file di configurazione dell'estensione per CRT:

    - **Commerce Scale Unit:** il file si chiama **commerceruntime.ext.config** e si trova nella cartella **bin\\ext** nella posizione del sito IIS Commerce Scale Unit.
    - **CRT locale sul POS moderno:** il file si chiama **CommerceRuntime.MPOSOffline.Ext.config** e si trova nella posizione del broker client CRT locale.

2. Registra la modifica CRT nel file di configurazione dell'estensione.

    ``` xml
    <add source="assembly" value="Microsoft.Dynamics.Commerce.Runtime.ReceiptsGermany" />
    ```

### <a name="enable-fiscal-connector-extensions"></a>Abilitare le estensioni del connettore fiscale

È possibile abilitare le estensioni del connettore fiscale sulla [stazione hardware](fiscal-integration-for-retail-channel.md#fiscal-registration-is-done-via-a-device-connected-to-the-hardware-station) o il [Registro POS](fiscal-integration-for-retail-channel.md#fiscal-registration-is-done-via-a-device-or-service-in-the-local-network).

#### <a name="enable-hardware-station-extensions"></a>Abilitare le estensioni della stazione hardware

I componenti dell'estensione stazione hardware sono inclusi negli esempi per stazione hardware. Per completare le seguenti procedure, apri la soluzione **HardwareStationSamples.sln** in **RetailSdk\\SampleExtensions\\HardwareStation**.

##### <a name="efrsample-component"></a>Componente EFRSample

1. Individua il progetto **HardwareStation.Extension.EFRSample** e compilalo.
2. Nella cartella **Extension.EFRSample\\bin\\Debug** trova i seguenti file assembly:

    - Contoso.Commerce.HardwareStation.EFRSample.dll
    - Contoso.Commerce.Runtime.DocumentProvider.DataModelEFR.dll

3. Copia i file assembly nella cartella delle estensioni stazione hardware:

    - **Stazione hardware condivisa**: copia i file nella cartella **bin** nella posizione del sito stazione hardware IIS.
    - **Stazione hardware dedicata in Modern POS**: copia i file nella posizione del broker client Modern POS.

4. Individuare il file di configurazione dell'estensione per le estensioni della stazione hardware. Il file si chiama **HardwareStation.Extension.config**.

    - **Stazione hardware condivisa**: il file si trova sotto la posizione del sito della stazione hardware IIS.
    - **Stazione hardware dedicata in Modern POS**: il file si trova nella posizione del broker client Modern POS.

5. Aggiungi la riga seguente alla sezione **composition** del file di configurazione.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.HardwareStation.EFRSample.dll" />
    ```

#### <a name="enable-pos-extensions"></a>Abilitare le estensioni POS

L'esempio di estensione POS si trova nella cartella **src\\FiscalIntegration\\PosFiscalConnectorSample** del repository [Soluzioni Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/).

Per utilizzare l'esempio di estensione POS nell'SDK legacy, segui questi passaggi.

1. Copia la cartella **Pos.Extension** nella cartella **Estensioni** POS dell'SDK legacy (ad esempio, `C:\RetailSDK\src\POS\Extensions`).
1. Rinomina la copia della cartella **Pos.Extension** **PosFiscalConnector**.
1. Rimuovi le seguenti cartelle e file dalla cartella **PosFiscalConnector**:

    - bin
    - DataService
    - devDependencies
    - Librerie
    - obj
    - Contoso.PosFiscalConnectorSample.Pos.csproj
    - RetailServerEdmxModel.g.xml
    - tsconfig.json

1. Apri la soluzione **CloudPos.sln** o **ModernPos.sln**.
1. Nel progetto **Pos.Extensions**, includi la cartella **PosFiscalConnector**.
1. Apri il file **extensions.json** e aggiungi l'estensione **PosFiscalConnector**.
1. Creare l'SDK.

### <a name="production-environment"></a>Ambiente di produzione

Nella procedura precedente sono state abilitate le estensioni che sono componenti dell'esempio di integrazione del servizio di registrazione fiscale. Inoltre devi seguire la procedura seguente per creare pacchetti distribuibili contenenti componenti Commerce e per applicare quei pacchetti a un ambiente di produzione.

1. Apportare le seguenti modifiche nei file di configurazione dei pacchetti nella cartella **RetailSdk\\Assets** :

    - Nei file di configurazione **CommerceRuntime.MPOSOffline.Ext.config** e **commerceruntime.ext.config**, aggiungi le seguenti righe alla sezione **composition**.

        ``` xml
        <add source="assembly" value="Microsoft.Dynamics.Commerce.Runtime.ReceiptsGermany" />
        <add source="assembly" value="Contoso.Commerce.Runtime.DocumentProvider.EFRSample" />
        <add source="assembly" value="Contoso.Commerce.Runtime.DocumentProvider.DataModelEFR" />
        ```

    - Nel file di configurazione **HardwareStation.Extension.config**, aggiungi le seguenti righe alla sezione **composition**.

        ``` xml
        <add source="assembly" value="Contoso.Commerce.HardwareStation.EFRSample" />
        <add source="assembly" value="Contoso.Commerce.Runtime.DocumentProvider.DataModelEFR" />
        ```

2. Apporta le seguenti modifiche nel file di configurazione di personalizzazione dei pacchetti **Customization.settings** nella cartella **BuildTools**:

    - Aggiungi le seguenti righe per includere le estensioni CRT nei pacchetti distribuibili.

        ``` xml
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.DocumentProvider.EFRSample.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.DocumentProvider.DataModelEFR.dll" />
        ```

    - Aggiungi le seguenti righe per includere le estensioni stazione hardware nei pacchetti distribuibili.

        ``` xml
        <ISV_HardwareStation_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.HardwareStation.EFRSample.dll" />
        <ISV_HardwareStation_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.DocumentProvider.DataModelEFR.dll" />
        ```

3. Avviare il prompt dei comandi di MSBuild per l'utilità Visual Studio ed eseguire **msbuild** nella cartella Retail SDK per creare pacchetti distribuibili.
4. Applica i pacchetti via LCS o manualmente. Per ulteriori informazioni, vedere [Creare pacchetti distribuibili](../dev-itpro/retail-sdk/retail-sdk-packaging.md).
5. Completa tutte le attività di configurazione richieste descritte in [Impostare Commerce per la Germania](emea-deu-fi-sample.md#set-up-commerce-for-germany).

## <a name="design-of-extensions"></a>Progettazione delle estensioni

L'esempio di integrazione del servizio di registrazione fiscale per la Germania si basa sulla [funzionalità di integrazione fiscale](fiscal-integration-for-retail-channel.md). Per ulteriori informazioni sulla progettazione della soluzione di integrazione fiscale, vedi [Panoramica di un progetto di esempio di integrazione fiscale](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices-and-services).

### <a name="commerce-runtime-extension-design"></a>Progettazione dell'estensione di Commerce Runtime

Lo scopo dell'estensione (provider di documenti) è di generare documenti specifici per il servizio e di gestire le risposte dal servizio di registrazione fiscale.

L'estensione CRT è **Runtime.Extensions.DocumentProvider.EFRSample**. Per ulteriori informazioni sulla progettazione della soluzione di integrazione fiscale, vedi [Panoramica dell'integrazione fiscale per i canali di Commerce](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices-and-services).

#### <a name="request-handler"></a>Gestore richieste

È disponibile un gestore di richiesta per il provider di documenti, **DocumentProviderEFRFiscalDEU**. Questo gestore viene utilizzato per generare documenti fiscali per il servizio di registrazione fiscale. Viene ereditato dall'interfaccia **INamedRequestHandler**. Il metodo **HandlerName** è responsabile della restituzione del nome del gestore. Il nome del gestore deve corrispondere al nome del fornitore di documenti del connettore specificato in Commerce headquarters.

Il connettore supporta le seguenti richieste:

- **GetFiscalDocumentDocumentProviderRequest** - Contiene informazioni su quale documento dovrà essere generato. Restituisce un documento specifico del servizio che deve essere registrato nel servizio di registrazione fiscale.
- **GetFiscalTransactionExtendedDataDocumentProviderRequest** – Questa richiesta restituisce la risposta insieme ai dati estesi.

#### <a name="configuration"></a>Configurazione

Il file di configurazione **DocumentProviderFiscalEFRSampleGermany** si trova nella cartella **Configuration** del progetto di estensione. Lo scopo di questo file è di consentire la configurazione delle impostazioni per il provider di documenti da Commerce headquarters. Il formato di file è allineato ai requisiti per la configurazione dell'integrazione fiscale.

Vengono aggiunte le seguenti impostazioni:

- **Mapping delle aliquote IVA** – Il mapping dei valori delle percentuali di imposta impostati per i codici IVA sui valori dell'attributo **TaxG** (gruppo di imposte) nelle richieste inviate al servizio fiscale.
- **Gruppo fiscale per gift card e depositi** – Il valore dell'attributo **TaxG** nelle richieste che vengono inviate al servizio fiscale, sulla base di operazioni che prevedono gift card o depositi.
- **Mapping del tipo di metodo di pagamento** – Il mapping dei metodi di pagamento ai valori dell'attributo **PayG** (gruppo di pagamenti) nelle richieste inviate al servizio fiscale.
- **Gruppo di imposte per esenzione IVA** – Il valore dell'attributo **TaxG** nelle richieste che vengono inviate al servizio fiscale, sulla base di operazioni esenti da obblighi fiscali.
- **Includi i dati del cliente** – Se questo parametro è attivato, le richieste al servizio fiscale conterranno informazioni sul cliente, come nomi e indirizzi, nei casi in cui un cliente viene aggiunto a una transazione.

### <a name="hardware-station-extension-design"></a>Progettazione dell'estensione stazione hardware

Lo scopo dell'estensione (connettore fiscale) è di comunicare con il servizio di registrazione fiscale.

L'estensione stazione hardware è **HardwareStation.Extension.EFRSample**. Utilizza il protocollo HTTP per inviare documenti generati dall'estensione CRT per il servizio di registrazione fiscale. Gestisce inoltre le risposte ricevute dal servizio di registrazione fiscale.

#### <a name="request-handler"></a>Gestore richieste

Il gestore richieste **EFRHandler** è il punto di ingresso per la trasmissione delle richieste al servizio di registrazione fiscale. Il gestore viene ereditato dall'interfaccia **INamedRequestHandler**. Il metodo **HandlerName** è responsabile della restituzione del nome del gestore. Il nome del gestore deve corrispondere al nome del connettore fiscale specificato in Commerce headquarters.

Il connettore supporta le seguenti richieste:

- **SubmitDocumentFiscalDeviceRequest** - Invia documenti al servizio di registrazione fiscale e restituisce una risposta.
- **IsReadyFiscalDeviceRequest** - Viene utilizzata per un controllo di integrità del servizio di registrazione fiscale.
- **InitializeFiscalDeviceRequest** - Viene utilizzata per inizializzare il servizio di registrazione fiscale.

#### <a name="configuration"></a>Configurazione

Il file di configurazione si trova nella cartella **Configuration** del progetto di estensione. Lo scopo del file è di consentire la configurazione delle impostazioni per il connettore fiscale da Commerce headquarters. Il formato di file è allineato ai requisiti per la configurazione dell'integrazione fiscale.

Vengono aggiunte le seguenti impostazioni:

- **Indirizzo dell'endpoint** – L'URL del servizio di registrazione fiscale.
- **Timeout** – La quantità di tempo, in millisecondi (ms) che il driver trascorre in attesa di una risposta dal servizio di registrazione fiscale.
- **Mostra notifiche di registrazione fiscale** – Se questo parametro è attivo, le notifiche del servizio fiscale verranno mostrate come messaggi utente al POS.

### <a name="pos-fiscal-connector-extension-design"></a>Progettazione delle estensioni del connettore fiscale POS

Lo scopo dell'estensione del connettore fiscale POS è di comunicare con il servizio di registrazione fiscale dal POS. Utilizza il protocollo HTTPS per la comunicazione.

#### <a name="fiscal-connector-factory"></a>Factory del connettore fiscale

La factory del connettore fiscale associa il nome del connettore all'implementazione del connettore fiscale e si trova nel file **Pos.Extension\\Connectors\\FiscalConnectorFactory.ts**. Il nome del connettore deve corrispondere al nome del connettore fiscale specificato in Commerce headquarters.

#### <a name="efr-fiscal-connector"></a>Connettore fiscale EFR

Il connettore fiscale EFR si trova nel file **Pos.Extension\\Connectors\\Efr\\EfrFiscalConnector.ts**. Implementa l'interfaccia **IFiscalConnector** che supporta le seguenti richieste:

- **FiscalRegisterSubmitDocumentClientRequest** - Invia documenti al servizio di registrazione fiscale e restituisce una risposta.
- **FiscalRegisterIsReadyClientRequest** - Viene utilizzata per un controllo di integrità del servizio di registrazione fiscale.
- **FiscalRegisterInitializeClientRequest** - Viene utilizzata per inizializzare il servizio di registrazione fiscale.

#### <a name="configuration"></a>Configurazione

Il file di configurazione si trova nella cartella **src\\FiscalIntegration\\Efr\\Configurations\\Connectors** del repository [Dynamics 365 Commerce Solutions](https://github.com/microsoft/Dynamics365Commerce.Solutions/). Lo scopo del file è di consentire la configurazione delle impostazioni per il connettore fiscale da Commerce headquarters. Il formato di file è allineato ai requisiti per la configurazione dell'integrazione fiscale. Vengono aggiunte le seguenti impostazioni:

- **Indirizzo dell'endpoint** – L'URL del servizio di registrazione fiscale.
- **Timeout** – La quantità di tempo, in millisecondi (ms) che il connettore trascorre in attesa di una risposta dal servizio di registrazione fiscale.
