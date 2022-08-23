---
title: Linee guida per la distribuzione dell'esempio di integrazione della stampante fiscale per la Polonia (legacy)
description: Questo articolo fornisce le linee guida per la distribuzione dell'esempio di integrazione della stampante fiscale per la Polonia da Microsoft Dynamics 365 Commerce Retail software development kit (SDK).
author: EvgenyPopovMBS
ms.date: 12/20/2021
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2019-03-01
ms.openlocfilehash: 883f09f73e3b372d6896b6702e54e2e664cff4d7
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9286528"
---
# <a name="deployment-guidelines-for-the-fiscal-printer-integration-sample-for-poland-legacy"></a>Linee guida per la distribuzione dell'esempio di integrazione della stampante fiscale per la Polonia (legacy)

[!include[banner](../includes/banner.md)]

Questo articolo fornisce le linee guida per la distribuzione dell'esempio di integrazione della stampante fiscale per la Polonia da Microsoft Dynamics 365 Commerce Retail software development kit (SDK) in una macchina virtuale per lo sviluppo (VM) in Microsoft Dynamics Lifecycle Services (LCS). Per maggiori informazioni sull'esempio di integrazione fiscale, vedi [Esempio di integrazione della stampante fiscale per la Polonia](emea-pol-fpi-sample.md). 

L'esempio di integrazione fiscale per la Polonia fa parte di Retail SDK. Per informazioni su come installare e utilizzare SDK, vedi [Architettura di Retail SDK](../dev-itpro/retail-sdk/retail-sdk-overview.md). Questo esempio è costituito da estensioni per Commerce Runtime (CRT) e stazione hardware. Per eseguire questo esempio, è necessario modificare e creare progetti CRT e stazione hardware. Ti consigliamo di utilizzare un SDK Retail non modificato per apportare le modifiche descritte in questo articolo. Si consiglia inoltre di utilizzare un sistema di controllo del codice sorgente, come Azure DevOps dove nessun file è stato ancora modificato.

## <a name="development-environment"></a>Ambiente di sviluppo

Segui questi passaggi per configurare un ambiente di sviluppo in modo da poter testare ed estendere l'esempio.

### <a name="commerce-runtime-extension-components"></a>Componenti dell'estensione di Commerce Runtime

I componenti dell'estensione CRT sono inclusi in Retail SDK. Per completare le seguenti procedure, apri la soluzione **CommerceRuntimeSamples.sln** in **RetailSdk\\SampleExtensions\\CommerceRuntime**.

1. Individua il progetto **Runtime.Extensions.DocumentProvider.PosnetSample** e compilalo.
2. Nella cartella **Extensions.DocumentProvider.PosnetSample\\bin\\Debug**, trova il file assembly **Contoso.Commerce.Runtime.Extensions.DocumentProvider.PosnetSample.dll**.
3. Copia il file assembly nella cartella dell'estensione CRT:

    - **Commerce Scale Unit**: copia il file nella cartella **\\bin\\ext** nella posizione del sito Internet Information Services (IIS) Commerce Scale Unit.
    - **CRT locale su POS moderno**: copia il file nella cartella **\\ext** nella posizione del broker client CRT locale.

4. Individua il file di configurazione dell'estensione per CRT:

    - **Commerce Scale Unit:** il file si chiama **commerceruntime.ext.config** e si trova nella cartella **bin\\ext** nella posizione del sito IIS Commerce Scale Unit.
    - **CRT locale sul POS moderno:** il file si chiama **CommerceRuntime.MPOSOffline.Ext.config** e si trova nella posizione del broker client CRT locale.

5. Registra la modifica CRT nel file di configurazione dell'estensione.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.Extensions.DocumentProvider.PosnetSample" />
    ```

6. Riavvia il servizio Commerce:

    - **Commerce Scale Unit:** riavvia il sito del servizio Commerce da IIS Manager.
    - **Broker client**: terminare il processo **dllhost.exe** in Gestione attività quindi riavviare il POS moderno.

### <a name="hardware-station-extension-components"></a>Componenti dell'estensione stazione hardware

I componenti dell'estensione stazione hardware sono inclusi in Retail SDK. Per completare le seguenti procedure, apri la soluzione **HardwareStationSamples.sln** in **RetailSdk\\SampleExtensions\\HardwareStation**.

1. Individua il progetto **HardwareStation.Extension.PosnetThermalFVFiscalPrinterSample** e compilalo.
2. Nella cartella **Extension.Posnet.ThermalFVFiscalPrinterSample\\bin\\Debug**, trova il file assembly **Contoso.Commerce.HardwareStation.PosnetThermalFVFiscalPrinterSample.dll**.
3. Copia il file assembly in un computer stazione hardware distribuito:

    - **Stazione hardware remota**: copia il file nella cartella **bin** nella posizione del sito stazione hardware IIS. Copia le librerie dei driver della stampante (**libposcmbth.dll**, **libcmbth\_serial.dll**, e **cmbth\_pl.lng**).

4. Individuare il file di configurazione per le estensioni della stazione hardware. Il file si chiama **HardwareStation.Extension.config**:

    - **Stazione hardware remota**: il file si trova sotto la posizione del sito della stazione hardware IIS.

5. Aggiungi la riga seguente alla sezione **composition** del file di configurazione.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.HardwareStation.PosnetThermalFVFiscalPrinterSample" />
    ```

6. Riavviare il servizio della stazione hardware:

    - **Stazione hardware remota**: Riavviare il sito della stazione hardware da Gestione IIS.

## <a name="production-environment"></a>Ambiente di produzione

Nella procedura precedente sono state abilitate le estensioni che sono componenti dell'esempio di integrazione del servizio di registrazione fiscale. Inoltre devi seguire la procedura seguente per creare pacchetti distribuibili contenenti componenti Commerce e per applicare quei pacchetti a un ambiente di produzione.

1. Apportare le seguenti modifiche nei file di configurazione dei pacchetti nella cartella **RetailSdk\\Assets** :

    - Nei file di configurazione **CommerceRuntime.MPOSOffline.Ext.config** e **commerceruntime.ext.config**, aggiungere la seguente riga alla sezione **composition**.

        ``` xml
        <add source="assembly" value="Contoso.Commerce.Runtime.Extensions.DocumentProvider.PosnetSample" />
        ```

    - Nel file di configurazione **HardwareStation.Extension.config**, aggiungere la seguente riga alla sezione **composition**.

        ``` xml
        <add source="assembly" value="Contoso.Commerce.HardwareStation.PosnetThermalFVFiscalPrinterSample" />
        ```

1. Apporta le seguenti modifiche nel file di configurazione di personalizzazione dei pacchetti **Customization.settings** nella cartella **BuildTools**:

    - Aggiungere la seguente riga per includere l'estensione CRT nei pacchetti distribuibili.

        ``` xml
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.Extensions.DocumentProvider.PosnetSample.dll"/>
        ```

    - Aggiungere la seguente riga per includere l'estensione stazione hardware nei pacchetti distribuibili.

        ``` xml
        <ISV_HardwareStation_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.HardwareStation.PosnetThermalFVFiscalPrinterSample.dll"/>
        ```

1. Avviare il prompt dei comandi di MSBuild per l'utilità Visual Studio ed eseguire **msbuild** nella cartella Retail SDK per creare pacchetti distribuibili.
1. Applica i pacchetti via LCS o manualmente. Per ulteriori informazioni, vedere [Creare pacchetti distribuibili](../dev-itpro/retail-sdk/retail-sdk-packaging.md).

## <a name="design-of-extensions"></a>Progettazione delle estensioni

L'esempio di integrazione della stampante fiscale per la Polonia si basa sulla [funzionalità di integrazione fiscale](fiscal-integration-for-retail-channel.md). Per ulteriori informazioni sulla progettazione della soluzione di integrazione fiscale, vedi [Panoramica di un progetto di esempio di integrazione fiscale](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices-and-services).

### <a name="commerce-runtime-extension-design"></a>Progettazione dell'estensione di Commerce Runtime

Lo scopo dell'estensione (provider di documenti) è di generare documenti specifici per la stampante e di gestire le risposte dalla stampante fiscale.

L'estensione CRT è **Runtime.Extensions.DocumentProvider.PosnetSample**. Questa estensione genera una serie di comandi specifici della stampante in formato JavaScript Object Notation (JSON) definiti dalla specifica POSNET 19-3678.

Per ulteriori informazioni sulla progettazione della soluzione di integrazione fiscale, vedi [Processo di registrazione fiscale ed esempi di integrazione fiscale per dispositivi fiscali e servizi](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices-and-services).

#### <a name="request-handler"></a>Gestore richieste

Il gestore richieste **DocumentProviderPosnetProtocol** è il punto di ingresso per la richiesta di generare documenti dalla stampante fiscale.

Il gestore viene ereditato dall'interfaccia **INamedRequestHandler**. Il metodo **HandlerName** è responsabile della restituzione del nome del gestore. Il nome del gestore deve corrispondere al nome del fornitore di documenti del connettore specificato in Commerce headquarters.

Il connettore supporta le seguenti richieste:

- **GetFiscalDocumentDocumentProviderRequest** - Contiene informazioni su quale documento dovrà essere generato. Restituisce un documento specifico della stampante che deve essere registrato nella stampante fiscale.
- **GetSupportedRegistrableEventsDocumentProviderRequest** - Restituisce l'elenco degli eventi da sottoscrivere. Attualmente, i seguenti eventi sono supportati: vendita, stampa del report X e stampa del report Z.

#### <a name="configuration"></a>Configurazione

Il file di configurazione si trova nella cartella **Configuration** del progetto di estensione. Lo scopo del file è di consentire la configurazione delle impostazioni per il provider di documenti da Commerce headquarters. Il formato di file è allineato ai requisiti per la configurazione dell'integrazione fiscale. Vengono aggiunte le seguenti impostazioni:

- Mapping aliquote IVA
- Mapping tipo di metodo di pagamento
- Tipo di pagamento deposito

### <a name="hardware-station-extension-design"></a>Progettazione dell'estensione stazione hardware

Lo scopo dell'estensione (connettore fiscale) è di comunicare con la stampante fiscale.

L'estensione stazione hardware è **HardwareStation.Extension.PosnetThermalFVFiscalPrinterSample**. Questa estensione chiama le funzioni del driver POSNET per inviare comandi generati dall'estensione CRT alla stampante fiscale. Gestisce anche gli errori del dispositivo.

#### <a name="request-handler"></a>Gestore richieste

Il gestore richieste **FiscalPrinterHandler** è il punto di ingresso per la trasmissione della richiesta alla periferica fiscale.

Il gestore viene ereditato dall'interfaccia **INamedRequestHandler**. Il metodo **HandlerName** è responsabile della restituzione del nome del gestore. Il nome del gestore deve corrispondere al nome del connettore fiscale specificato in Commerce headquarters.

Il connettore supporta le seguenti richieste:

- **SubmitDocumentFiscalDeviceRequest** - Invia documenti alle stampanti e restituisce la risposta dalla stampante fiscale.
- **IsReadyFiscalDeviceRequest** - Viene utilizzata per un controllo di integrità del dispositivo.
- **InitializeFiscalDeviceRequest** - È utilizzata per l'inizializzazione della stampante.

#### <a name="configuration"></a>Configurazione

Il file di configurazione si trova nella cartella **Configuration** del progetto di estensione. Lo scopo del file è di consentire la configurazione delle impostazioni per il connettore da Commerce headquarters. Il formato di file è allineato ai requisiti per la configurazione dell'integrazione fiscale. Vengono aggiunte le seguenti impostazioni:

- **Stringa di connessione** – Una stringa che descrive i dettagli della connessione al dispositivo in un formato supportato dal driver. Per ulteriori informazioni, vedi la documentazione del driver POSNET.
- **Sincronizzazione data e ora** - Valore che specifica se la data e l'ora della stampante devono essere sincronizzate con la stazione hardware collegata.
- **Timeout dispositivo** – La quantità di tempo, in millisecondi, che il driver trascorre in attesa di una risposta dal dispositivo. Per ulteriori informazioni, vedi la documentazione del driver POSNET.
