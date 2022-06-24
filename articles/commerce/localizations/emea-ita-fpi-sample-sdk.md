---
title: Linee guida per la distribuzione dell'esempio di integrazione della stampante fiscale per l'Italia (legacy)
description: Questo articolo fornisce le linee guida per la distribuzione dell'esempio di integrazione della stampante fiscale per l'Italia da Microsoft Dynamics 365 Commerce Retail software development kit (SDK).
author: EvgenyPopovMBS
ms.date: 03/04/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: epopov
ms.search.validFrom: 2019-3-1
ms.openlocfilehash: bb07ca91c9e5bf1a79f672f9ba29b7bcc21688c6
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8848900"
---
# <a name="deployment-guidelines-for-the-fiscal-printer-integration-sample-for-italy-legacy"></a>Linee guida per la distribuzione dell'esempio di integrazione della stampante fiscale per l'Italia (legacy)

[!include[banner](../includes/banner.md)]

Questo articolo fornisce le linee guida per la distribuzione dell'esempio di integrazione della stampante fiscale per l'Italia da Microsoft Dynamics 365 Commerce Retail software development kit (SDK) in una macchina virtuale per lo sviluppo (VM) in Microsoft Dynamics Lifecycle Services (LCS). Per maggiori informazioni sull'esempio di integrazione fiscale, vedi [Esempio di integrazione della stampante fiscale per l'Italia](emea-ita-fpi-sample.md). 

L'esempio di integrazione fiscale per l'Italia fa parte di Retail SDK. Per informazioni su come installare e utilizzare SDK, vedi [Architettura di Retail SDK](../dev-itpro/retail-sdk/retail-sdk-overview.md). Questo esempio è costituito da estensioni per Commerce Runtime (CRT) e stazione hardware. Per eseguire questo esempio, è necessario modificare e creare progetti CRT e stazione hardware. Ti consigliamo di utilizzare un SDK Retail non modificato per apportare le modifiche descritte in questo articolo. Si consiglia inoltre di utilizzare un sistema di controllo del codice sorgente, come Azure DevOps dove nessun file è stato ancora modificato.

## <a name="development-environment"></a>Ambiente di sviluppo

Segui questi passaggi per configurare un ambiente di sviluppo in modo da poter testare ed estendere l'esempio.

### <a name="commerce-runtime-extension-components"></a>Componenti dell'estensione di Commerce Runtime

I componenti dell'estensione CRT sono inclusi in Retail SDK. Per completare le seguenti procedure, apri la soluzione **CommerceRuntimeSamples.sln** in **RetailSdk\\SampleExtensions\\CommerceRuntime**.

1. Individuare il progetto **Runtime.Extensions.DocumentProvider.EpsonFP90IIISample** e compilarlo.
2. Nella cartella **Extensions.DocumentProvider.EpsonFP90IIISample\\bin\\Debug**, trovare il file assembly **Contoso.Commerce.Runtime.DocumentProvider.EpsonFP90IIISample.dll**.
3. Copiare il file assembly alla cartella dell'estensione CRT:

    - **Commerce Scale Unit**: copia il file nella cartella **\\bin\\ext** nella posizione del sito Internet Information Services (IIS) Commerce Scale Unit.
    - **CRT locale su POS moderno**: copia il file nella cartella **\\ext** nella posizione del broker client CRT locale.

4. Individua il file di configurazione dell'estensione per CRT:

    - **Commerce Scale Unit:** il file si chiama **commerceruntime.ext.config** e si trova nella cartella **bin\\ext** nella posizione del sito IIS Commerce Scale Unit.
    - **CRT locale sul POS moderno:** il file si chiama **CommerceRuntime.MPOSOffline.Ext.config** e si trova nella posizione del broker client CRT locale.

5. Registra la modifica CRT nel file di configurazione dell'estensione.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.DocumentProvider.EpsonFP90IIISample" />
    ```

6. Riavviare Commerce Scale Unit:

    - **Commerce Scale Unit:** riavviare il sito Commerce Scale Unit da IIS Manager.
    - **Broker client**: terminare il processo **dllhost.exe** in Gestione attività quindi riavviare il POS moderno.

### <a name="hardware-station-extension-components"></a>Componenti dell'estensione stazione hardware

I componenti dell'estensione stazione hardware sono inclusi in Retail SDK. Per completare le seguenti procedure, apri la soluzione **HardwareStationSamples.sln** in **RetailSdk\\SampleExtensions\\HardwareStation**.

1. Individuare il progetto **HardwareStation.Extensions.EpsonFP90IIIFiscalDeviceSample** e compilarlo.
2. Nella cartella **Extensions.EpsonFP90IIIFiscalDeviceSample\\bin\\Debug**, trovare il file assembly **Contoso.Commerce.HardwareStation.EpsonFP90IIIFiscalDeviceSample.dll**.
3. Copia il file assembly in un computer stazione hardware distribuito:

    - **Stazione hardware remota**: copia il file nella cartella **bin** nella posizione del sito stazione hardware IIS.
    - **Stazione hardware locale**: copia il file nella posizione del broker client POS moderno.

4. Individuare il file di configurazione per le estensioni della stazione hardware. Il file si chiama **HardwareStation.Extension.config**:

    - **Stazione hardware remota**: il file si trova sotto la posizione del sito della stazione hardware IIS.
    - **Stazione hardware locale**: il file si trova nella posizione del broker client POS moderno.

5. Aggiungi la sezione seguente alla sezione **composition** del file di configurazione.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.HardwareStation.EpsonFP90IIIFiscalDeviceSample" />
    ```

6. Riavviare il servizio della stazione hardware:

    - **Stazione hardware remota**: Riavviare il sito della stazione hardware da Gestione IIS.
    - **Stazione hardware locale**: terminare il processo **dllhost.exe** in Gestione attività quindi riavviare il POS moderno.

## <a name="production-environment"></a>Ambiente di produzione

Per creare pacchetti distribuibili contenenti componenti Commerce e per applicare quei pacchetti a un ambiente di produzione, attenersi alla procedura seguente.

1. Completa la procedura descritta nella sezione [Ambiente di sviluppo](#development-environment) in precedenza in questo articolo.
2. Apportare le seguenti modifiche nei file di configurazione dei pacchetti nella cartella **RetailSdk\\Assets** :

    1. Nei file di configurazione **CommerceRuntime.MPOSOffline.Ext.config** e **commerceruntime.ext.config**, aggiungere la seguente riga alla sezione **composition**.

        ``` xml
        <add source="assembly" value="Contoso.Commerce.Runtime.DocumentProvider.EpsonFP90IIISample" />
        ```

    1. Nel file di configurazione **HardwareStation.Extension.config**, aggiungere la seguente riga alla sezione **composition**.

        ``` xml
        <add source="assembly" value="Contoso.Commerce.HardwareStation.EpsonFP90IIIFiscalDeviceSample" />
        ```

3. Apporta le seguenti modifiche nel file di configurazione di personalizzazione dei pacchetti **Customization.settings** nella cartella **BuildTools**:

    1. Aggiungere la seguente riga per includere l'estensione CRT nei pacchetti distribuibili.

        ``` xml
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.DocumentProvider.EpsonFP90IIISample.dll"/>
        ```

    1. Aggiungere la seguente riga per includere l'estensione stazione hardware nei pacchetti distribuibili.

        ``` xml
        <ISV_HardwareStation_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.HardwareStation.EpsonFP90IIIFiscalDeviceSample.dll"/>
        ```

4. Apporta le seguenti modifiche nel file **Sdk.ModernPos.Shared.csproj** nella cartella **Packages\_SharedPackagingProjectComponents** per includere i file di risorse per l'Italia nei pacchetti distribuibili:

    1. Aggiungi un sezione **ItemGroup** che contiene nodi che puntano ai file di risorse per le traduzioni desiderate. Assicurati di specificare gli spazi dei nomi e i nomi di esempio corretti. L'esempio seguente aggiunge nodi di risorse per le impostazioni locali **it** e **it-CH**.

        ```xml
        <ItemGroup>
            <ResourcesIt Include="$(SdkReferencesPath)\it\Contoso.Commerce.Runtime.DocumentProvider.EpsonFP90IIISample.resources.dll"/>
            <ResourcesItCh Include="$(SdkReferencesPath)\it-CH\Contoso.Commerce.Runtime.DocumentProvider.EpsonFP90IIISample.resources.dll"/>
        </ItemGroup>
        ```

    1. Nella sezione **Nome destinazione="CopyPackageFiles"**, aggiungi una riga per ogni impostazione locale, come mostrato nell'esempio seguente.

        ```xml
        <Copy SourceFiles="@(ResourcesIt)" DestinationFolder="$(OutputPath)content.folder\CustomizedFiles\ClientBroker\ext\it" SkipUnchangedFiles="true" />
        <Copy SourceFiles="@(ResourcesItCh)" DestinationFolder="$(OutputPath)content.folder\CustomizedFiles\ClientBroker\ext\it-CH" SkipUnchangedFiles="true" />
        ```

5. Apporta le seguenti modifiche nel file **Sdk.RetailServerSetup.proj** nella cartella **Packages\_SharedPackagingProjectComponents** per includere i file di risorse per l'Italia nei pacchetti distribuibili:

    1. Aggiungi un sezione **ItemGroup** che contiene nodi che puntano ai file di risorse per le traduzioni desiderate. Assicurati di specificare gli spazi dei nomi e i nomi di esempio corretti. L'esempio seguente aggiunge nodi di risorse per le impostazioni locali **it** e **it-CH**.

        ```xml
        <ItemGroup>
            <ResourcesIt Include="$(SdkReferencesPath)\it\Contoso.Commerce.Runtime.DocumentProvider.EpsonFP90IIISample.resources.dll"/>
            <ResourcesItCh Include="$(SdkReferencesPath)\it-CH\Contoso.Commerce.Runtime.DocumentProvider.EpsonFP90IIISample.resources.dll"/>
        </ItemGroup>
        ```

    1. Nella sezione **Nome destinazione="CopyPackageFiles"**, aggiungi una riga per ogni impostazione locale, come mostrato nell'esempio seguente.

        ``` xml
        <Copy SourceFiles="@(ResourcesIt)" DestinationFolder="$(OutputPath)content.folder\RetailServer\Code\bin\ext\it" SkipUnchangedFiles="true" />
        <Copy SourceFiles="@(ResourcesItCh)" DestinationFolder="$(OutputPath)content.folder\RetailServer\Code\bin\ext\it-CH" SkipUnchangedFiles="true" />
        ```

6. Avviare il prompt dei comandi di MSBuild per l'utilità Visual Studio, quindi eseguire **msbuild** nella cartella Retail SDK per creare pacchetti distribuibili.
7. Applica i pacchetti via LCS o manualmente. Per ulteriori informazioni, vedere [Creare pacchetti distribuibili](../dev-itpro/retail-sdk/retail-sdk-packaging.md).

## <a name="design-of-extensions"></a>Progettazione delle estensioni

### <a name="commerce-runtime-extension-design"></a>Progettazione dell'estensione di Commerce Runtime

Lo scopo dell'estensione (provider di documenti) è di generare documenti specifici per la stampante e di gestire le risposte dalla stampante fiscale.

L'estensione CRT è **Runtime.Extensions.DocumentProvider.EpsonFP90IIISample**.

Per ulteriori informazioni sulla progettazione della soluzione di integrazione fiscale, vedi [Processo di registrazione fiscale ed esempi di integrazione fiscale per dispositivi fiscali e servizi](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices-and-services).

#### <a name="request-handler"></a>Gestore richieste

Il gestore richieste **DocumentProviderEpsonFP90III** è il punto di ingresso per la richiesta di generare documenti dalla stampante fiscale.

Il gestore viene ereditato dall'interfaccia **INamedRequestHandler**. Il metodo **HandlerName** è responsabile della restituzione del nome del gestore. Il nome del gestore deve corrispondere al nome del fornitore di documenti del connettore specificato in Commerce headquarters.

Il connettore supporta le seguenti richieste:

- **GetFiscalDocumentDocumentProviderRequest** - Contiene informazioni su quale documento dovrà essere generato. Restituisce un documento specifico della stampante che deve essere registrato nella stampante fiscale.
- **GetSupportedRegistrableEventsDocumentProviderRequest** - Restituisce l'elenco degli eventi da sottoscrivere. Attualmente, i seguenti eventi sono supportati: vendita, stampa del report X e stampa del report Z.

#### <a name="configuration"></a>Configurazione

Il file di configurazione si trova nella cartella **Configuration** del progetto di estensione. Lo scopo del file è di consentire la configurazione delle impostazioni per il provider di documenti da Commerce headquarters. Il formato di file è allineato ai requisiti per la configurazione dell'integrazione fiscale. Vengono aggiunte le seguenti impostazioni:

- Mapping codici IVA
- Mapping aliquote IVA
- Mapping tipo di metodo di pagamento
- Tipo di codice a barre per numero ricevuta
- Tipo di pagamento deposito

### <a name="hardware-station-extension-design"></a>Progettazione dell'estensione stazione hardware

Lo scopo dell'estensione (connettore fiscale) è di comunicare con la stampante fiscale.

L'estensione stazione hardware è **HardwareStation.Extension.EpsonFP90IIIFiscalDeviceSample**. Questa estensione utilizza il protocollo HTTP per inviare documenti generati dall'estensione CRT per la stampante fiscale. Gestisce inoltre le risposte ricevute dalla stampante fiscale.

#### <a name="request-handler"></a>Gestore richieste

Il gestore richieste **EpsonFP90IIISample** è il punto di ingresso per la trasmissione delle richieste alla periferica fiscale.

Il gestore viene ereditato dall'interfaccia **INamedRequestHandler**. Il metodo **HandlerName** è responsabile della restituzione del nome del gestore. Il nome del gestore deve corrispondere al nome del connettore fiscale specificato in Commerce headquarters.

Il connettore supporta le seguenti richieste:

- **SubmitDocumentFiscalDeviceRequest** - Invia documenti alle stampanti e restituisce la risposta dalla stampante fiscale.
- **IsReadyFiscalDeviceRequest** - Viene utilizzata per un controllo di integrità del dispositivo.
- **InitializeFiscalDeviceRequest** - È utilizzata per l'inizializzazione della stampante.

#### <a name="configuration"></a>Configurazione

Il file di configurazione si trova nella cartella **Configuration** del progetto di estensione. Lo scopo del file è di consentire la configurazione delle impostazioni per il connettore da Commerce headquarters. Il formato di file è allineato ai requisiti per la configurazione dell'integrazione fiscale. Vengono aggiunte le seguenti impostazioni:

- **Indirizzo endpoint** - L'URL della stampante.
- **Sincronizzazione data e ora** - Valore che specifica se la data e l'ora della stampante devono essere sincronizzate con la stazione hardware collegata.
