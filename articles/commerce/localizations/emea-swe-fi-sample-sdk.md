---
title: Linee guida per la distribuzione per l'esempio di integrazione dell'unità di controllo per la Svezia (legacy)
description: Questo argomento fornisce le linee guida per la distribuzione dell'esempio di integrazione dell'unità di controllo per la Svezia da Retail SDK
author: EvgenyPopovMBS
ms.date: 12/20/2021
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: epopov
ms.search.validFrom: 2019-3-1
ms.openlocfilehash: b8d60f32d986dec6bb26d78ebdfe8cee3a6b688a
ms.sourcegitcommit: 5cefe7d2a71c6f220190afc3293e33e2b9119685
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/01/2022
ms.locfileid: "8077040"
---
# <a name="deployment-guidelines-for-the-control-unit-integration-sample-for-sweden-legacy"></a>Linee guida per la distribuzione per l'esempio di integrazione dell'unità di controllo per la Svezia (legacy)

[!include [banner](../includes/banner.md)]

Questo argomento fornisce le linee guida per la distribuzione dell'esempio di integrazione dell'unità di controllo per la Svezia da Retail software development kit (SDK) in una macchina virtuale per lo sviluppo (VM) in Microsoft Dynamics Lifecycle Services (LCS). Per maggiori informazioni sull'esempio di integrazione fiscale, vedi [Esempio di integrazione dell'unità di controllo per la Svezia](emea-swe-fi-sample.md). 

L'esempio di integrazione fiscale per la Svezia fa parte di Retail SDK. Per informazioni su come installare e utilizzare SDK, vedi [Architettura di Retail SDK](../dev-itpro/retail-sdk/retail-sdk-overview.md). Questo esempio è costituito da estensioni per Commerce Runtime (CRT), stazione hardware e point of sale (POS). Per eseguire questo esempio, è necessario modificare e creare progetti CRT, stazione hardware e POS. Si consiglia di utilizzare un SDK Retail non modificato per apportare le modifiche descritte in questo argomento. Si consiglia inoltre di utilizzare un sistema di controllo del codice sorgente, come Azure DevOps dove nessun file è stato ancora modificato.

## <a name="development-environment"></a>Ambiente di sviluppo

Segui questi passaggi per configurare un ambiente di sviluppo in modo da poter testare ed estendere l'esempio.

### <a name="enable-crt-extensions"></a>Abilitare le estensioni CRT

I componenti dell'estensione CRT sono inclusi negli esempi CRT. Per completare le seguenti procedure, apri la soluzione **CommerceRuntimeSamples.sln** in **RetailSdk\\SampleExtensions\\CommerceRuntime**.

#### <a name="documentprovidercleancashsample-component"></a>Componente DocumentProvider.CleanCashSample

1. Individua il progetto **Runtime.Extensions.DocumentProvider.CleanCashSample** e compilalo.
2. Nella cartella **Runtime.Extensions.DocumentProvider.CleanCashSample\\bin\\Debug**, trovare il file assembly **Contoso.Commerce.Runtime.DocumentProvider.CleanCashSample.dll**.
3. Copiare il file assembly alla cartella dell'estensione CRT:

    - **Commerce Scale Unit**: copia il file nella cartella **\\bin\\ext** nella posizione del sito Internet Information Services (IIS) Commerce Scale Unit.
    - **CRT locale su POS moderno**: copia il file nella cartella **\\ext** nella posizione del broker client CRT locale.

4. Individua il file di configurazione dell'estensione per CRT:

    - **Commerce Scale Unit:** il file si chiama **commerceruntime.ext.config** e si trova nella cartella **bin\\ext** nella posizione del sito IIS Commerce Scale Unit.
    - **CRT locale sul POS moderno:** il file si chiama **CommerceRuntime.MPOSOffline.Ext.config** e si trova nella posizione del broker client CRT locale.

5. Registra la modifica CRT nel file di configurazione dell'estensione.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.DocumentProvider.CleanCashSample" />
    ```

#### <a name="extension-configuration-file"></a>File di configurazione dell'estensione

1. Individua il file di configurazione dell'estensione per CRT:

    - **Commerce Scale Unit:** il file si chiama **commerceruntime.ext.config** e si trova nella cartella **bin\\ext** nella posizione del sito IIS Commerce Scale Unit.
    - **CRT locale sul POS moderno:** il file si chiama **CommerceRuntime.MPOSOffline.Ext.config** e si trova nella posizione del broker client CRT locale.

2. Registra la modifica CRT nel file di configurazione dell'estensione.

    ``` xml
    <add source="assembly" value="Microsoft.Dynamics.Commerce.Runtime.ReceiptsSweden" />
    ```

### <a name="enable-hardware-station-extensions"></a>Abilitare le estensioni della stazione hardware

I componenti dell'estensione stazione hardware sono inclusi negli esempi per stazione hardware. Per completare le seguenti procedure, apri la soluzione **HardwareStationSamples.sln** in **RetailSdk\\SampleExtensions\\HardwareStation**.

#### <a name="cleancash-component"></a>Componente CleanCash

1. Individua il progetto **HardwareStation.Extension.CleanCashSample** e compilalo.
2. Nella cartella **Extension.CleanCashSample\\bin\\Debug** trova i file assembly **Contoso.Commerce.HardwareStation.CleanCashSample.dll** e **Interop.CleanCash\_1\_1.dll**.
3. Copia i file assembly nella cartella delle estensioni stazione hardware:

    - **Stazione hardware condivisa**: copia i file nella cartella **bin** nella posizione del sito stazione hardware IIS.
    - **Stazione hardware dedicata in Modern POS**: copia i file nella posizione del broker client Modern POS.

4. Individuare il file di configurazione dell'estensione per le estensioni della stazione hardware. Il file si chiama **HardwareStation.Extension.config**.

    - **Stazione hardware condivisa**: il file si trova sotto la posizione del sito della stazione hardware IIS.
    - **Stazione hardware dedicata in Modern POS**: il file si trova nella posizione del broker client Modern POS.

5. Aggiungi la riga seguente alla sezione **composition** del file di configurazione.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.HardwareStation.CleanCashSample" />
    ```

### <a name="enable-modern-pos-extension-components"></a>Abilitare i componenti dell'estensione Modern POS

1. Apri la soluzione **ModernPOS.sln** in **RetailSdk\\POS** e assicurati che possa essere compilata senza errori. Inoltre, assicurati di poter eseguire Modern POS da Visual Studio usando il comando **Esegui**.

    > [!NOTE]
    > Il Modern POS non deve essere personalizzato. È necessario abilitare il controllo dell'account utente (UAC) e disinstallare le istanze di Modern POS installate in precedenza come richiesto.

2. Abilita le estensioni che devi caricare aggiungendo le seguenti righe nel file **extensions.json**.

    ``` json
    {
        "extensionPackages": [
            {
                "baseUrl": "Microsoft/AuditEvent.SE"
            }
        ]
    }
    ```

    > [!NOTE]
    > Per ulteriori informazioni e per esempi che mostrano come includere le cartelle del codice sorgente e abilitare il caricamento delle estensioni, vedi le istruzioni nel file readme.md nel progetto **Pos.Extensions**.

3. Ricompila la soluzione.
4. Esegui Modern POS nel debugger e verifica la funzionalità.

### <a name="enable-cloud-pos-extension-components"></a>Abilitare i componenti dell'estensione Cloud POS

1. Apri la soluzione **CloudPOS.sln** in **RetailSdk\\POS** e assicurati che possa essere compilata senza errori.
2. Abilita le estensioni che devi caricare aggiungendo le seguenti righe nel file **extensions.json**.

    ``` json
    {
        "extensionPackages": [
            {
                "baseUrl": "Microsoft/AuditEvent.SE"
            }
        ]
    }
    ```

    > [!NOTE]
    > Per ulteriori informazioni e per esempi che mostrano come includere le cartelle del codice sorgente e abilitare il caricamento delle estensioni, vedi le istruzioni nel file readme.md nel progetto **Pos.Extensions**.

3. Ricompila la soluzione.
4. Esegui la soluzione usando il comando **Esegui** e seguendo i passaggi nel manuale di Retail SDK.

## <a name="production-environment"></a>Ambiente di produzione

Nella procedura precedente sono state abilitate le estensioni che sono componenti dell'esempio di integrazione dell'unità di controllo. Inoltre devi seguire la procedura seguente per creare pacchetti distribuibili contenenti componenti Commerce e per applicare quei pacchetti a un ambiente di produzione.

1. Apportare le seguenti modifiche nei file di configurazione dei pacchetti nella cartella **RetailSdk\\Assets** :

    - Nei file di configurazione **CommerceRuntime.MPOSOffline.Ext.config** e **commerceruntime.ext.config**, aggiungi le seguenti righe alla sezione **composition**.

        ``` xml
        <add source="assembly" value="Contoso.Commerce.Runtime.DocumentProvider.CleanCashSample" />
        <add source="assembly" value="Microsoft.Dynamics.Commerce.Runtime.ReceiptsSweden" />
        ```

    - Nel file di configurazione **HardwareStation.Extension.config**, aggiungere la seguente riga alla sezione **composition**.

        ``` xml
        <add source="assembly" value="Contoso.Commerce.HardwareStation.CleanCashSample" />
        ```

2. Apporta le seguenti modifiche nel file di configurazione di personalizzazione dei pacchetti **Customization.settings** nella cartella **BuildTools**:

    - Aggiungi la seguente riga per includere le estensioni CRT nei pacchetti distribuibili.

        ``` xml
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.DocumentProvider.CleanCashSample.dll" />
        ```

    - Aggiungi le seguenti righe per includere l'estensione stazione hardware nei pacchetti distribuibili.

        ``` xml
        <ISV_HardwareStation_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.HardwareStation.CleanCashSample.dll" />
        <ISV_HardwareStation_CustomizableFile Include="$(SdkReferencesPath)\Interop.CleanCash_1_1.dll" />
        ```

3. Abilita l'estensione POS aggiungendo le seguenti righe nel file **extensions.json** nella cartella **RetailSDK\\POS\\Extensions**.

    ``` json
    {
        "extensionPackages": [
            {
            "baseUrl": "Microsoft/AuditEvent.SE"
            }
        ]
    }
    ```

4. Avviare il prompt dei comandi di MSBuild per l'utilità Visual Studio ed eseguire **msbuild** nella cartella Retail SDK per creare pacchetti distribuibili.
5. Applica i pacchetti via LCS o manualmente. Per ulteriori informazioni, vedere [Creare pacchetti distribuibili](../dev-itpro/retail-sdk/retail-sdk-packaging.md).
6. Completa tutte le attività di configurazione richieste descritte in [Impostazione dell'integrazione con le unità di controllo](emea-swe-fi-sample.md#setting-up-the-integration-with-control-units).

## <a name="design-of-the-extensions"></a>Progettazione delle estensioni

### <a name="crt-extension-design"></a>Progettazione delle estensioni CRT

Lo scopo dell'estensione (provider di documenti) è di generare documenti specifici per il servizio e di gestire le risposte dall'unità di controllo.

L'estensione CRT è **Runtime.Extensions.DocumentProvider.CleanCashSample**.

Per ulteriori informazioni sulla progettazione della soluzione di integrazione fiscale, vedi [Processo di registrazione fiscale ed esempi di integrazione fiscale per dispositivi fiscali e servizi](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices-and-services).

#### <a name="request-handler"></a>Gestore richieste

È disponibile un solo gestore di richiesta **DocumentProviderCleanCash** per il provider di documenti. Questo gestore viene utilizzato per generare documenti fiscali per l'unità di controllo.

Il gestore viene ereditato dall'interfaccia **INamedRequestHandler**. Il metodo **HandlerName** è responsabile della restituzione del nome del gestore. Il nome del gestore deve corrispondere al nome del fornitore di documenti del connettore specificato in Commerce headquarters.

Il connettore supporta le seguenti richieste:

- **GetFiscalDocumentDocumentProviderRequest** - Contiene informazioni su quale documento dovrà essere generato. Restituisce un documento specifico del servizio che deve essere registrato nell'unità di controllo.
- **GetSupportedRegistrableEventsDocumentProviderRequest** - Restituisce l'elenco degli eventi da sottoscrivere. Attualmente sono supportati gli eventi di vendita e gli eventi di controllo.

#### <a name="configuration"></a>Configurazione

Il file di configurazione **DocumentProviderFiscalCleanCashSample** si trova nella cartella **Configuration** del progetto di estensione. Lo scopo di questo file è di consentire la configurazione delle impostazioni per il provider di documenti da Commerce headquarters. Il formato di file è allineato ai requisiti per la configurazione dell'integrazione fiscale. Vengono aggiunte le seguenti impostazioni:

- Mapping codici IVA

### <a name="hardware-station-extension-design"></a>Progettazione dell'estensione stazione hardware

Lo scopo dell'estensione (connettore fiscale) è di comunicare con l'unità di controllo.

L'estensione stazione hardware è **HardwareStation.Extension.CleanCashSample**. Utilizza il protocollo HTTP per inviare documenti generati dall'estensione CRT per l'unità di controllo. Gestisce inoltre le risposte ricevute dall'unità di controllo.

#### <a name="request-handler"></a>Gestore richieste

Il gestore richieste **CleanCashHandler** è il punto di ingresso per la trasmissione delle richieste all'unità di controllo.

Il gestore viene ereditato dall'interfaccia **INamedRequestHandler**. Il metodo **HandlerName** è responsabile della restituzione del nome del gestore. Il nome del gestore deve corrispondere al nome del connettore fiscale specificato in Commerce headquarters.

Il connettore supporta le seguenti richieste:

- **SubmitDocumentFiscalDeviceRequest** - Invia documenti alle unità di controllo e restituisce la risposta.
- **IsReadyFiscalDeviceRequest** - Viene utilizzata per un controllo di integrità dell'unità di controllo.
- **InitializeFiscalDeviceRequest** - È utilizzata per l'inizializzazione dell'unità di controllo.

#### <a name="configuration"></a>Configurazione

Il file di configurazione si trova nella cartella **Configuration** del progetto di estensione. Lo scopo del file è di consentire la configurazione delle impostazioni per il connettore fiscale da Commerce headquarters. Il formato di file è allineato ai requisiti per la configurazione dell'integrazione fiscale. Vengono aggiunte le seguenti impostazioni:

- **Stringa di connessione** – Le impostazioni di connessione dell'unità di controllo.
- **Timeout** – La quantità di tempo, in millisecondi, che il driver trascorre in attesa di una risposta dall'unità di controllo.

## <a name="migrating-from-the-earlier-integration-sample"></a>Migrazione dal precedente esempio di integrazione

Se stai usando il precedente [esempio di integrazione POS con unità di controllo per la Svezia](retail-sdk-control-unit-sample.md), potrebbe essere necessario eseguire la migrazione all'esempio di integrazione corrente. Per accettare la modifica e ricevere aggiornamenti tempestivi per le funzionalità per la Svezia in futuro, potresti dover aggiornare, apportare modifiche minori al codice e alla configurazione nelle estensioni che hai creato e ricostruire le soluzioni. Non sono necessarie modifiche importanti nella logica dell'estensione creata. L'esempio di integrazione precedente e le tue personalizzazioni continueranno a funzionare se non vengono apportate modifiche da parte tua. Pertanto, puoi pianificare, prepararti e fare l'aggiornamento per il tuo ambiente.

### <a name="migration-process"></a>Processo di migrazione

La migrazione dal precedente esempio di integrazione all'attuale esempio di integrazione dell'unità di controllo dovrebbe basarsi sul concetto di aggiornamento graduale. In altre parole, tutti i componenti di Commerce headquarters e Commerce Scale Unit devono essere già aggiornati prima di iniziare ad aggiornare i componenti POS e della stazione hardware.

Per evitare una situazione in cui un evento o una transazione viene firmata due volte (vale a dire, è firmata sia dall'estensione precedente che dall'estensione corrente) o in cui un evento o una transazione non possono essere firmati a causa della configurazione mancante, si consiglia di disattivare tutti i dispositivi POS e stazione hardware che utilizzano l'esempio precedente e quindi aggiornarli contemporaneamente. Questo aggiornamento simultaneo può essere effettuato, ad esempio, negozio per negozio aggiornando il profilo di funzionalità del negozio e il profilo hardware della stazione hardware.

Il processo di migrazione consiste nei seguenti passaggi.

1. Aggiorna i componenti Commerce headquarters.
1. Aggiorna i componenti Commerce Scale Unit e abilita le estensioni dell'esempio corrente.
1. Assicurati che tutte le transazioni offline siano sincronizzate dai dispositivi MPOS abilitati offline.
1. Disattiva tutti i dispositivi che utilizzano i componenti dell'esempio precedente.
1. Completa tutte le attività di configurazione richieste descritte in [Impostazione dell'integrazione con le unità di controllo](emea-swe-fi-sample.md#setting-up-the-integration-with-control-units).
1. Aggiorna i componenti POS e Stazione hardware, disabilita le estensioni che fanno parte dell'esempio precedente e abilita le estensioni dell'esempio corrente.

    > [!NOTE]
    > A seconda del tipo di ambiente, è possibile trovare maggiori dettagli tecnici sul processo di migrazione nella sezione [Migrazione in un ambiente di sviluppo](#migration-in-a-development-environment) o nella sezione [Migrazione in un ambiente di produzione](#migration-in-a-production-environment) di questo argomento.

### <a name="migration-in-a-development-environment"></a>Migrazione in un ambiente di sviluppo

#### <a name="update-crt"></a>Aggiorna CRT

1. Individua il progetto **Runtime.Extensions.DocumentProvider.CleanCashSample** e compilalo.
2. Nella cartella **Runtime.Extensions.DocumentProvider.CleanCashSample\\bin\\Debug**, trovare il file assembly **Contoso.Commerce.Runtime.DocumentProvider.CleanCashSample.dll**.
3. Copiare il file assembly alla cartella dell'estensione CRT:

    - **Commerce Scale Unit**: copia il file nella cartella **\\bin\\ext** nella posizione del sito IIS Commerce Scale Unit.
    - **CRT locale su POS moderno**: copia il file nella cartella **\\ext** nella posizione del broker client CRT locale.

4. Individua il file di configurazione dell'estensione per CRT:

    - **Commerce Scale Unit:** il file si chiama **CommerceRuntime.ext.config** e si trova nella cartella **bin\\ext** nella posizione del sito IIS Commerce Scale Unit.
    - **CRT locale su Modern POS:** il file si chiama **CommerceRuntime.MPOSOffline.Ext.config**, e si trova nella cartella **bin\\ext** nella posizione del broker CRT locale.

    > [!WARNING]
    > **Non** modificare i file CommerceRuntime.MPOSOffline.config e CommerceRuntime.config. Questi file non sono progettati per essere personalizzati.

5. Trova e rimuovi l'estensione CRT precedente dal file di configurazione dell'estensione.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.FiscalRegisterReceiptSample" />
    ```

    > [!WARNING]
    > Non completare questo passaggio finché non aggiorni tutti i dispositivi POS che funzionano con questa istanza di CRT.

6. Registra le estensioni CRT dell'esempio corrente nel file di configurazione dell'estensione aggiungendo le seguenti righe.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.DocumentProvider.CleanCashSample" />
    <add source="assembly" value="Microsoft.Dynamics.Commerce.Runtime.ReceiptsSweden" />
    ```

#### <a name="update-hardware-station"></a>Aggiornare la stazione hardware

1. Individua il progetto **HardwareStation.Extension.CleanCashSample** e compilalo.
2. Nella cartella **Extension.CleanCashSample\\bin\\Debug** trova i file assembly **Contoso.Commerce.HardwareStation.CleanCashSample.dll** e **Interop.CleanCash\_1\_1.dll**.
3. Copia i file assembly nella cartella delle estensioni stazione hardware:

    - **Stazione hardware condivisa**: copia i file nella cartella **bin** nella posizione del sito stazione hardware IIS.
    - **Stazione hardware dedicata in Modern POS**: copia i file nella posizione del broker client Modern POS.

4. Individua il file di configurazione dell'estensione **HardwareStation.Extension.config**:

    - **Stazione hardware remota**: il file si trova sotto la posizione del sito della stazione hardware IIS.
    - **Stazione hardware locale in Modern POS**: il file si trova nella posizione del broker client Modern POS.

    > [!WARNING]
    > **Non** modificare i file CommerceRuntime.MPOSOffline.config e CommerceRuntime.config. Questi file non sono progettati per essere personalizzati.

5. Trova e rimuovi l'estensione stazione hardware precedente dal file di configurazione dell'estensione.

    # <a name="retail-73-and-earlier"></a>[Retail 7.3 e versioni precedenti](#tab/retail-7-3)

    ``` xml
    <add source="assembly" value="Contoso.Commerce.HardwareStation.Extension.FiscalRegisterSample" />
    ```

    # <a name="retail-731-and-later"></a>[Retail 7.3.1 e versioni successive](#tab/retail-7-3-1)

    ``` xml
    <add source="assembly" value="Contoso.Commerce.HardwareStation.Extension.FiscalRegisterSample" />
    ```

    # <a name="retail-100-and-later"></a>[Retail 10.0 e versioni successive](#tab/retail-10-0)

    ``` xml
    <add source="assembly" value="Contoso.Commerce.HardwareStation.FiscalRegisterSample" />
    ```
    ---

6. Aggiungi la riga seguente alla sezione **composition** del file di configurazione dell'estensione.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.HardwareStation.CleanCashSample" />
    ```

#### <a name="update-modern-pos"></a>Aggiornare Modern POS

1. Apri la soluzione **CloudPOS.sln** in **RetailSdk\\POS**.
2. Disabilitare l'estensione POS precedente rimuovendo le seguenti righe dal file **extensions.json**.

    ``` json
    {
        "baseUrl": "FiscalRegisterSample"
    }
    ```

2. Abilita l'estensione POS dell'esempio corrente aggiungendo le seguenti righe nel file **extensions.json**.

    ``` json
    {
        "extensionPackages": [
            {
                "baseUrl": "Microsoft/AuditEvent.SE"
            }
        ]
    }
    ```

#### <a name="update-cloud-pos"></a>Aggiornare Cloud POS

1. Apri la soluzione **ModernPOS.sln** in **RetailSdk\\POS**.
2. Disabilitare l'estensione POS precedente rimuovendo le seguenti righe dal file **extensions.json**.

    ``` json
    {
        "baseUrl": "FiscalRegisterSample"
    }
    ```

2. Abilita l'estensione POS dell'esempio corrente aggiungendo le seguenti righe nel file **extensions.json**.

    ``` json
    {
        "extensionPackages": [
            {
                "baseUrl": "Microsoft/AuditEvent.SE"
            }
        ]
    }
    ```

### <a name="migration-in-a-production-environment"></a>Migrazione in un ambiente di produzione

#### <a name="update-crt"></a>Aggiorna CRT

1. Rimuovi l'estensione CRT precedente dai file di configurazione **CommerceRuntime.ext.config** e **CommerceRuntime.MPOSOffline.Ext.config** nella cartella **RetailSdk\\Assets**.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.FiscalRegisterReceiptSample" />
    ```

    > [!WARNING]
    > Non completare questo passaggio finché non aggiorni tutti i dispositivi POS che funzionano con questa istanza di CRT.

2. Abilita le estensioni CRT dell'esempio corrente apportando le seguenti modifiche nei file di configurazione **CommerceRuntime.ext.config** e **CommerceRuntime.MPOSOffline.Ext.config** nella cartella **RetailSdk\\Assets**.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.DocumentProvider.CleanCashSample" />
    <add source="assembly" value="Microsoft.Dynamics.Commerce.Runtime.ReceiptsSweden" />
    ```

3. Nel file di configurazione della personalizzazione del pacchetto **Customization.settings** sotto la cartella **BuildTools**, aggiungi la seguente riga per includere l'estensione CRT dell'esempio corrente in pacchetti distribuibili.

    ``` xml
    <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.DocumentProvider.CleanCashSample.dll" />
    ```

#### <a name="update-hardware-station"></a>Aggiornare la stazione hardware

1. Rimuovi l'estensione stazione hardware precedente modificando il file di configurazione **HardwareStation.Extension.config**.

    # <a name="retail-73-and-earlier"></a>[Retail 7.3 e versioni precedenti](#tab/retail-7-3)

    Rimuovi la sezione seguente dai file di configurazione **HardwareStation.Shared.config** e **HardwareStation.Dedicated.config**.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.HardwareStation.Extension.FiscalRegisterSample" />
    ```

    # <a name="retail-731-and-later"></a>[Retail 7.3.1 e versioni successive](#tab/retail-7-3-1)

    Rimuovi la seguente sezione dal file di configurazione **HardwareStation.Extension.config**.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.HardwareStation.Extension.FiscalRegisterSample" />
    ```

    # <a name="retail-100-and-later"></a>[Retail 10.0 e versioni successive](#tab/retail-10-0)

    Rimuovi la seguente sezione dal file di configurazione **HardwareStation.Extension.config**.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.HardwareStation.FiscalRegisterSample" />
    ```
    ---

2. Abilita l'estensione stazione hardware dell'esempio corrente aggiungendo la seguente riga alla sezione **composition** del file di configurazione **HardwareStation.Extension.config**.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.HardwareStation.CleanCashSample" />
    ```

3. Apporta le seguenti modifiche nel file di configurazione di personalizzazione dei pacchetti **Customization.settings** nella cartella **BuildTools**:

    - Rimuovi la seguente riga per escludere l'estensione stazione hardware precedente dai pacchetti distribuibili.

        ``` xml
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.HardwareStation.Extension.FiscalRegisterSample.dll" />
        ```

    - Aggiungi le seguenti righe per includere l'estensione stazione hardware dell'esempio corrente nei pacchetti distribuibili.

        ``` xml
        <ISV_HardwareStation_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.HardwareStation.CleanCashSample.dll" />
        <ISV_HardwareStation_CustomizableFile Include="$(SdkReferencesPath)\Interop.CleanCash_1_1.dll" />
        ```

#### <a name="update-modern-pos"></a>Aggiornare Modern POS

1. Apri la soluzione **CloudPOS.sln** in **RetailSdk\\POS**.
2. Disabilita l'estensione POS precedente:

    - Nel file **tsconfig.json** aggiungi la cartella **FiscalRegisterSample** nell'elenco di esclusione.
    - Rimuovi le seguenti righe dal file **extensions.json** nella cartella **RetailSDK\\POS\\Extensions**.

        ``` json
        {
            "baseUrl": "FiscalRegisterSample"
        }
        ```

3. Abilita l'estensione POS dell'esempio corrente aggiungendo le seguenti righe nel file **extensions.json** nella cartella **RetailSDK\\POS\\Extensions**.

    ``` json
    {
        "extensionPackages": [
            {
                "baseUrl": "Microsoft/AuditEvent.SE"
            }
        ]
    }
    ```

#### <a name="update-cloud-pos"></a>Aggiornare Cloud POS

1. Apri la soluzione **ModernPOS.sln** in **RetailSdk\\POS**.
2. Disabilita l'estensione POS precedente:

    - Nel file **tsconfig.json** aggiungi la cartella **FiscalRegisterSample** nell'elenco di esclusione.
    - Rimuovi le seguenti righe dal file **extensions.json** nella cartella **RetailSDK\\POS\\Extensions**.

        ``` json
        {
            "baseUrl": "FiscalRegisterSample"
        }
        ```

3. Abilita l'estensione POS dell'esempio corrente aggiungendo le seguenti righe nel file **extensions.json** nella cartella **RetailSDK\\POS\\Extensions**.

    ``` json
    {
        "extensionPackages": [
            {
                "baseUrl": "Microsoft/AuditEvent.SE"
            }
        ]
    }
    ```

#### <a name="create-deployable-packages"></a>Creare pacchetti distribuibili

Esegui **msbuild** per l'intero Retail SDK per creare i pacchetti distribuibili. Applica i pacchetti via LCS o manualmente. Per ulteriori informazioni, vedere [Confezione di Retail SDK](../dev-itpro/retail-sdk/retail-sdk-packaging.md).
