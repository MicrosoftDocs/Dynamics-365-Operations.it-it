---
title: Linee guida per la distribuzione dei registratori di cassa per la Norvegia (legacy)
description: Questo articolo è una guida alla distribuzione che mostra come abilitare la localizzazione Microsoft Dynamics 365 Commerce per la Norvegia.
author: EvgenyPopovMBS
ms.date: 08/23/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2018-2-28
ms.openlocfilehash: fb597add48ac3508a88142e63d80f405b6b5f8b4
ms.sourcegitcommit: 1dbff0b5fa1f4722a1720fac35cce94606fa4320
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/24/2022
ms.locfileid: "9346047"
---
# <a name="deployment-guidelines-for-cash-registers-for-norway-legacy"></a>Linee guida per la distribuzione dei registratori di cassa per la Norvegia (legacy)

[!include [banner](../includes/banner.md)]

> [!WARNING]
> Questo funzionalità di integrazione fiscale di esempio non utilizza il [framework di integrazione fiscale](./fiscal-integration-for-retail-channel.md) e verrà deprecata negli aggiornamenti successivi. Dovresti invece usare la [funzionalità basata sul framework di integrazione fiscale](./emea-nor-fi-deployment.md).

Questo articolo è una guida alla distribuzione che mostra come abilitare la localizzazione Microsoft Dynamics 365 Commerce per la Norvegia. La localizzazione è costituita da diverse estensioni dei componenti Commerce. Ad esempio, le estensioni consentono di stampare campi personalizzati sulle ricevute, registrare ulteriori eventi di controllo, transazioni di vendita e transazioni di pagamento in Point of Sale (POS), firma digitale delle transazioni di vendita e stampa di report X e Z in formati locali. Per ulteriori informazioni sulla localizzazione per la Norvegia, vedi [Funzionalità del registratore di cassa per la Norvegia](./emea-nor-cash-registers.md).

Questo esempio fa parte di Retail software development kit (SDK). Per informazioni su SDK, vedi [Architettura di Retail SDK](../dev-itpro/retail-sdk/retail-sdk-overview.md).

Questo esempio è costituito da estensioni per Commerce Runtime (CRT), Retail Server, e POS. Per eseguire questo esempio, è necessario modificare e creare progetti CRT, Retail Server e POS. Ti consigliamo di utilizzare un SDK Retail non modificato per apportare le modifiche descritte in questo articolo. Si consiglia inoltre di utilizzare un sistema di controllo del codice sorgente, come Microsoft Visual Studio Online (VSO), dove nessun file è stato ancora modificato.

> [!NOTE]
> In Commerce 10.0.8 e versioni successive, Retail Server è noto come Commerce Scale Unit. Poiché questo articolo si applica a più versioni precedenti dell'app, *Retail Server* viene utilizzato in tutto l'articolo.
>
> Alcuni passaggi delle procedure di questo articolo variano in base alla versione di Commerce in uso. Per ulteriori informazioni, vedere [Novità o modifiche in Dynamics 365 Retail](../get-started/whats-new.md).

### <a name="using-certificate-profiles-in-commerce-channels"></a>Utilizzo dei profili dei certificati nei canali Commerce

In Commerce versione 10.0.15 e successive, puoi utilizzare la funzionalità [Profili di certificati definiti dall'utente per punti vendita al dettaglio](./certificate-profiles-for-retail-stores.md) che supporta il failover offline quando Key Vault o Commerce headquarters non sono disponibili. La funzione estende la funzionalità [Gestisci i segreti per i canali di vendita al dettaglio](../dev-itpro/manage-secrets.md).

Attieniti alla seguente procedura per applicare la funzionalità nell'estensione CRT.

1. Crea un nuovo progetto di estensione CRT (tipo di progetto della libreria di classi C#). Usa i modelli di esempio di Retail software development kit (SDK) (RetailSDK\SampleExtensions\CommerceRuntime).

2. Aggiungi un gestore personalizzato per CertificateSignatureServiceRequest nel progetto SequentialSignatureRegister.

3. Per leggere una chiamata segreta, `GetUserDefinedSecretCertificateServiceRequest` utilizzando un costruttore con il parametro profileId. Ciò avvia la funzionalità che usa le impostazioni dai profili del certificato. In base alle impostazioni, il certificato verrà recuperato da Azure Key Vault o dall'archiviazione del computer locale.

    ```csharp
    GetUserDefinedSecretCertificateServiceRequest getUserDefinedSecretCertificateServiceRequest = new GetUserDefinedSecretCertificateServiceRequest(profileId: "ProfileId", secretName: null, thumbprint: null, expirationInterval: null);
    GetUserDefinedSecretCertificateServiceResponse getUserDefinedSecretCertificateServiceResponse = request.RequestContext.Execute<GetUserDefinedSecretCertificateServiceResponse>(getUserDefinedSecretCertificateServiceRequest);

    X509Certificate2 Certificate = getUserDefinedSecretCertificateServiceResponse.Certificate;
    ```

4. Quando il certificato viene recuperato, procedi con la firma dei dati.

5. Compila il progetto di estensione CRT.

6. Copia la libreria di classi di output e incollala in ...\RetailServer\webroot\bin\Ext per il test manuale.

7. Nel file CommerceRuntime.Ext.config, aggiorna la sezione di composizione dell'estensione con le informazioni sulla libreria personalizzata.

## <a name="development-environment"></a>Ambiente di sviluppo

Completa queste procedure per configurare un ambiente di sviluppo in modo da poter testare ed estendere l'esempio.

### <a name="the-crt-extension-components"></a>Componenti dell'estensione CRT

I componenti dell'estensione CRT sono inclusi negli esempi CRT. Per completare le seguenti procedure, aprire la soluzione CRT, **CommerceRuntimeSamples.sln**, in **RetailSdk\\SampleExtensions\\CommerceRuntime**.

#### <a name="receiptsnorway-component"></a>Componente ReceiptsNorway

1. Individua il progetto **Runtime.Extensions.ReceiptsNorway** e compilalo.
2. Nella cartella **Extensions.ReceiptsNorway\\bin\\Debug**, trova il file assembly **Contoso.Commerce.Runtime.ReceiptsNorway.dll**.
3. Copiare il file assembly alla cartella dell'estensione CRT:

    - **Server Retail**: copiare l'assembly nella cartella **\\bin\\ext** nella posizione del sito del Server Retail Microsoft Internet Information Services (IIS).
    - **CRT locale su POS moderno**: copiare l'assembly nella cartella **\\ext** nella posizione del broker client CRT locale.

4. Individua il file di configurazione dell'estensione per CRT:

    - **Retail Server:** il file si chiama **commerceruntime.ext.config** e si trova nella cartella **bin\\ext** nella posizione del sito IIS Retail Server.
    - **CRT locale sul POS moderno:** il file si chiama **CommerceRuntime.MPOSOffline.Ext.config** e si trova nella posizione del broker client CRT locale.

5. Registra la modifica CRT nel file di configurazione dell'estensione.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.ReceiptsNorway" />
    ```

    > [!WARNING]
    > **Non** modificare i file CommerceRuntime.MPOSOffline.config e commerceruntime.config. Questi file non sono progettati per essere personalizzati.

#### <a name="salespaymenttransext-component"></a>Componente SalesPaymentTransExt

1. Individua il progetto **Runtime.Extensions.SalesPaymentTransExt** e compilalo.
2. Nella cartella **Extensions.SalesPaymentTransExt\\bin\\Debug**, trova il file assembly **Contoso.Commerce.Runtime.SalesPaymentTransExt.dll**.
3. Copiare il file assembly alla cartella dell'estensione CRT:

    - **Retail Server**: copia l'assembly nella cartella **\\bin\\ext** nella posizione del sito IIS Retail Server.
    - **CRT locale su POS moderno**: copiare l'assembly nella cartella **\\ext** nella posizione del broker client CRT locale.

4. Individua il file di configurazione dell'estensione per CRT:

    - **Retail Server:** il file si chiama **commerceruntime.ext.config** e si trova nella cartella **bin\\ext** nella posizione del sito IIS Retail Server.
    - **CRT locale sul POS moderno:** il file si chiama **CommerceRuntime.MPOSOffline.Ext.config** e si trova nella posizione del broker client CRT locale.

5. Registra la modifica CRT nel file di configurazione dell'estensione.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.SalesPaymentTransExt" />
    ```

    > [!WARNING]
    > **Non** modificare i file CommerceRuntime.MPOSOffline.config e commerceruntime.config. Questi file non sono progettati per essere personalizzati.

#### <a name="xzreportsnorway-component"></a>Componente XZReportsNorway

1. Individua il progetto **Runtime.Extensions.XZReportsNorway** e compilalo.
2. Nella cartella **Extensions.XZReportsNorway\\bin\\Debug**, trova il file assembly **Contoso.Commerce.Runtime.XZReportsNorway.dll**.
3. Copiare il file assembly alla cartella dell'estensione CRT:

    - **Retail Server**: copia l'assembly nella cartella **\\bin\\ext** nella posizione del sito IIS Retail Server.
    - **CRT locale su POS moderno**: copiare l'assembly nella cartella **\\ext** nella posizione del broker client CRT locale.

4. Individua il file di configurazione dell'estensione per CRT:

    - **Retail Server:** il file si chiama **commerceruntime.ext.config** e si trova nella cartella **bin\\ext** nella posizione del sito IIS Retail Server.
    - **CRT locale sul POS moderno:** il file si chiama **CommerceRuntime.MPOSOffline.Ext.config** e si trova nella posizione del broker client CRT locale.

5. Registra la modifica CRT nel file di configurazione dell'estensione.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.XZReportsNorway" />
    ```

    > [!WARNING]
    > **Non** modificare i file CommerceRuntime.MPOSOffline.config e commerceruntime.config. Questi file non sono progettati per essere personalizzati.

# <a name="application-update-4"></a>[Aggiornamento applicazione 4](#tab/app-update-4)

#### <a name="registerauditevent-sample-component"></a>Componente di esempio RegisterAuditEvent

1. Individua il progetto **Runtime.Extensions.RegisterAuditEventSample** e compilalo.
2. Nella cartella **Extensions.RegisterAuditEventSample\\bin\\Debug**, trova il file assembly **Contoso.Commerce.Runtime.RegisterAuditEventSample.dll**.
3. Copiare il file assembly alla cartella dell'estensione CRT:

    - **Retail Server**: copia l'assembly nella cartella **\\bin\\ext** nella posizione del sito IIS Retail Server.
    - **CRT locale su POS moderno**: copiare l'assembly nella cartella **\\ext** nella posizione del broker client CRT locale.

4. Individua il file di configurazione dell'estensione per CRT:

    - **Retail Server:** il file si chiama **commerceruntime.ext.config** e si trova nella cartella **bin\\ext** nella posizione del sito IIS Retail Server.
    - **CRT locale sul POS moderno:** il file si chiama **CommerceRuntime.MPOSOffline.Ext.config** e si trova nella posizione del broker client CRT locale.

5. Registra la modifica CRT nel file di configurazione dell'estensione.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.RegisterAuditEventSample" />
    ```

    > [!WARNING]
    > **Non** modificare i file CommerceRuntime.MPOSOffline.config e commerceruntime.config. Questi file non sono progettati per essere personalizzati.

#### <a name="salestransactionsignature-sample-component"></a>Componente di esempio SalesTransactionSignature

1. Individua il progetto **Runtime.Extensions.SalesTransactionSignatureSample**.
2. Modifica il file **App.config** specificando l'identificazione personale, la posizione del negozio e il nome del negozio per il certificato da utilizzare per firmare le transazioni di vendita.
3. Compila il progetto.
4. Nella cartella **Extensions.SalesTransactionSignatureSample\\bin\\Debug** trova i seguenti file:

    - Il file assembly **Contoso.Commerce.Runtime.SalesTransactionSignatureSample.dll**
    - Il file di configurazione **Contoso.Commerce.Runtime.SalesTransactionSignatureSample.dll.config**

5. Copia i file assembly nella cartella dell'estensione CRT:

    - **Retail Server**: copia l'assembly nella cartella **\\bin\\ext** nella posizione del sito IIS Retail Server.
    - **CRT locale su POS moderno**: copiare l'assembly nella cartella **\\ext** nella posizione del broker client CRT locale.

6. Individua il file di configurazione dell'estensione per CRT:

    - **Retail Server:** il file si chiama **commerceruntime.ext.config** e si trova nella cartella **bin\\ext** nella posizione del sito IIS Retail Server.
    - **CRT locale sul POS moderno:** il file si chiama **CommerceRuntime.MPOSOffline.Ext.config** e si trova nella posizione del broker client CRT locale.

7. Registra la modifica CRT nel file di configurazione dell'estensione.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.SalesTransactionSignatureSample" />
    ```

    > [!WARNING]
    > **Non** modificare i file CommerceRuntime.MPOSOffline.config e commerceruntime.config. Questi file non sono progettati per essere personalizzati.

# <a name="application-update-5-and-later"></a>[Aggiornamento applicazione 5 e successivi](#tab/app-update-5-and-later)

#### <a name="registerauditevent-sample-component"></a>Componente di esempio RegisterAuditEvent

1. Individua il progetto **Runtime.Extensions.RegisterAuditEventSample** e compilalo.
2. Nella cartella **Extensions.RegisterAuditEventSample\\bin\\Debug**, trova il file assembly **Contoso.Commerce.Runtime.RegisterAuditEventSample.dll**.
3. Copiare il file assembly alla cartella dell'estensione CRT:

    - **Retail Server**: copia l'assembly nella cartella **\\bin\\ext** nella posizione del sito IIS Retail Server.
    - **CRT locale su POS moderno**: copiare l'assembly nella cartella **\\ext** nella posizione del broker client CRT locale.

4. Individua il file di configurazione dell'estensione per CRT:

    - **Retail Server:** il file si chiama **commerceruntime.ext.config** e si trova nella cartella **bin\\ext** nella posizione del sito IIS Retail Server.
    - **CRT locale sul POS moderno:** il file si chiama **CommerceRuntime.MPOSOffline.Ext.config** e si trova nella posizione del broker client CRT locale.

5. Registra la modifica CRT nel file di configurazione dell'estensione.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.RegisterAuditEventSample" />
    ```

    > [!WARNING]
    > **Non** modificare i file CommerceRuntime.MPOSOffline.config e commerceruntime.config. Questi file non sono progettati per essere personalizzati.

#### <a name="salestransactionsignature-sample-component"></a>Componente di esempio SalesTransactionSignature

1. Individua il progetto **Runtime.Extensions.SalesTransactionSignatureSample**.
2. Modifica il file **App.config** specificando l'identificazione personale, la posizione del negozio e il nome del negozio per il certificato da utilizzare per firmare le transazioni di vendita.
3. Compila il progetto.
4. Nella cartella **Extensions.SalesTransactionSignatureSample\\bin\\Debug** trova i seguenti file:

    - Il file assembly **Contoso.Commerce.Runtime.SalesTransactionSignatureSample.dll**
    - Il file di configurazione **Contoso.Commerce.Runtime.SalesTransactionSignatureSample.dll.config**

5. Copia i file assembly nella cartella dell'estensione CRT:

    - **Retail Server**: copia l'assembly nella cartella **\\bin\\ext** nella posizione del sito IIS Retail Server.
    - **CRT locale su POS moderno**: copiare l'assembly nella cartella **\\ext** nella posizione del broker client CRT locale.

6. Individua il file di configurazione dell'estensione per CRT:

    - **Retail Server:** il file si chiama **commerceruntime.ext.config** e si trova nella cartella **bin\\ext** nella posizione del sito IIS Retail Server.
    - **CRT locale sul POS moderno:** il file si chiama **CommerceRuntime.MPOSOffline.Ext.config** e si trova nella posizione del broker client CRT locale.

7. Registra la modifica CRT nel file di configurazione dell'estensione.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.SalesTransactionSignatureSample" />
    ```

    > [!WARNING]
    > **Non** modificare i file CommerceRuntime.MPOSOffline.config e commerceruntime.config. Questi file non sono progettati per essere personalizzati.

#### <a name="salestransactionsignaturesamplemessages-component"></a>Componente di esempio SalesTransactionSignatureSample.Messages

1. Individua il progetto **Runtime.Extensions.SalesTransactionSignatureSample.Messages**.
2. Nella cartella **Extensions.SalesTransactionSignatureSample.Messages\\bin\\Debug** trova il file assembly **Contoso.Commerce.Runtime.SalesTransactionSignatureSample.Messages.dll**.
3. Copiare il file assembly alla cartella dell'estensione CRT:

    - **Retail Server**: copia l'assembly nella cartella **\\bin\\ext** nella posizione del sito IIS Retail Server.
    - **CRT locale su POS moderno**: copiare l'assembly nella cartella **\\ext** nella posizione del broker client CRT locale.

4. Individua il file di configurazione dell'estensione per CRT:

    - **Retail Server:** il file si chiama **commerceruntime.ext.config** e si trova nella cartella **bin\\ext** nella posizione del sito IIS Retail Server.
    - **CRT locale sul POS moderno:** il file si chiama **CommerceRuntime.MPOSOffline.Ext.config** e si trova nella posizione del broker client CRT locale.

5. Registra la modifica CRT nel file di configurazione dell'estensione.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.SalesTransactionSignatureSample.Messages" />
    ```

    > [!WARNING]
    > **Non** modificare i file CommerceRuntime.MPOSOffline.config e commerceruntime.config. Questi file non sono progettati per essere personalizzati.

# <a name="retail-731"></a>[Retail 7.3.1](#tab/retail-7-3-1)

#### <a name="registerauditevent-sample-component"></a>Componente di esempio RegisterAuditEvent

1. Individua il progetto **Runtime.Extensions.RegisterAuditEventSample** e compilalo.
2. Nella cartella **Extensions.RegisterAuditEventSample\\bin\\Debug**, trova il file assembly **Contoso.Commerce.Runtime.RegisterAuditEventSample.dll**.
3. Copiare il file assembly alla cartella dell'estensione CRT:

    - **Retail Server**: copia l'assembly nella cartella **\\bin\\ext** nella posizione del sito IIS Retail Server.
    - **CRT locale su POS moderno**: copiare l'assembly nella cartella **\\ext** nella posizione del broker client CRT locale.

4. Individua il file di configurazione dell'estensione per CRT:

    - **Retail Server:** il file si chiama **commerceruntime.ext.config** e si trova nella cartella **bin\\ext** nella posizione del sito IIS Retail Server.
    - **CRT locale sul POS moderno:** il file si chiama **CommerceRuntime.MPOSOffline.Ext.config** e si trova nella posizione del broker client CRT locale.

5. Registra la modifica CRT nel file di configurazione dell'estensione.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.RegisterAuditEventSample" />
    ```

    > [!WARNING]
    > **Non** modificare i file CommerceRuntime.MPOSOffline.config e commerceruntime.config. Questi file non sono progettati per essere personalizzati.

#### <a name="salestransactionsignature-sample-component"></a>Componente di esempio SalesTransactionSignature

1. Individua il progetto **Runtime.Extensions.SalesTransactionSignatureSample**.
2. Modifica il file **App.config** specificando l'identificazione personale, la posizione del negozio e il nome del negozio per il certificato da utilizzare per firmare le transazioni di vendita.
3. Compila il progetto.
4. Nella cartella **Extensions.SalesTransactionSignatureSample\\bin\\Debug** trova i seguenti file:

    - Il file assembly **Contoso.Commerce.Runtime.SalesTransactionSignatureSample.dll**
    - Il file di configurazione **Contoso.Commerce.Runtime.SalesTransactionSignatureSample.dll.config**

5. Copia i file assembly nella cartella dell'estensione CRT:

    - **Retail Server**: copia l'assembly nella cartella **\\bin\\ext** nella posizione del sito IIS Retail Server.
    - **CRT locale su POS moderno**: copiare l'assembly nella cartella **\\ext** nella posizione del broker client CRT locale.

6. Individua il file di configurazione dell'estensione per CRT:

    - **Retail Server:** il file si chiama **commerceruntime.ext.config** e si trova nella cartella **bin\\ext** nella posizione del sito IIS Retail Server.
    - **CRT locale sul POS moderno:** il file si chiama **CommerceRuntime.MPOSOffline.Ext.config** e si trova nella posizione del broker client CRT locale.

7. Registra la modifica CRT nel file di configurazione dell'estensione.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.SalesTransactionSignatureSample" />
    ```

    > [!WARNING]
    > **Non** modificare i file CommerceRuntime.MPOSOffline.config e commerceruntime.config. Questi file non sono progettati per essere personalizzati.

#### <a name="sequentialsignatureregistercontracts-component"></a>Componente SequentialSignatureRegister.Contracts

1. Individua il progetto **Runtime.Extensions.SequentialSignatureRegister.Contracts**.
2. Nella cartella **Extensions.SequentialSignatureRegister.Contracts\\bin\\Debug**, trova il file assembly **Contoso.Commerce.Runtime.SequentialSignatureRegister.Contracts.dll**.
3. Copiare il file assembly alla cartella dell'estensione CRT:

    - **Retail Server**: copia l'assembly nella cartella **\\bin\\ext** nella posizione del sito IIS Retail Server.
    - **CRT locale su POS moderno**: copiare l'assembly nella cartella **\\ext** nella posizione del broker client CRT locale.

# <a name="retail-732-and-later"></a>[Retail 7.3.2 e versioni successive](#tab/retail-7-3-2)

#### <a name="registerauditevent-sample-component"></a>Componente di esempio RegisterAuditEvent

1. Individua il progetto **Runtime.Extensions.RegisterAuditEventSample** e compilalo.
2. Nella cartella **Extensions.RegisterAuditEventSample\\bin\\Debug**, trova il file assembly **Contoso.Commerce.Runtime.RegisterAuditEventSample.dll**.
3. Copiare il file assembly alla cartella dell'estensione CRT:

    - **Retail Server**: copia l'assembly nella cartella **\\bin\\ext** nella posizione del sito IIS Retail Server.
    - **CRT locale su POS moderno**: copiare l'assembly nella cartella **\\ext** nella posizione del broker client CRT locale.

4. Individua il file di configurazione dell'estensione per CRT:

    - **Retail Server:** il file si chiama **commerceruntime.ext.config** e si trova nella cartella **bin\\ext** nella posizione del sito IIS Retail Server.
    - **CRT locale sul POS moderno:** il file si chiama **CommerceRuntime.MPOSOffline.Ext.config** e si trova nella posizione del broker client CRT locale.

5. Registra la modifica CRT nel file di configurazione dell'estensione.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.RegisterAuditEventSample" />
    ```

    > [!WARNING]
    > **Non** modificare i file CommerceRuntime.MPOSOffline.config e commerceruntime.config. Questi file non sono progettati per essere personalizzati.

#### <a name="sequentialsignatureregister-component"></a>Componente SequentialSignatureRegister

1. Individua il progetto **Runtime.Extensions.SequentialSignatureRegister** e compilalo.
2. Modifica il file **App.config** specificando l'identificazione personale, la posizione del negozio e il nome del negozio per il certificato da utilizzare per firmare le transazioni di vendita.
3. Compila il progetto.
4. Nella cartella **Extensions.SequentialSignatureRegister\\bin\\Debug** trova i seguenti file:

    - Il file assembly **Contoso.Commerce.Runtime.SequentialSignatureRegister.dll**
    - Il file di configurazione **Contoso.Commerce.Runtime.SequentialSignatureRegister.dll.config**

5. Copia i file assembly nella cartella dell'estensione CRT:

    - **Retail Server**: copia l'assembly nella cartella **\\bin\\ext** nella posizione del sito IIS Retail Server.
    - **CRT locale su POS moderno**: copiare l'assembly nella cartella **\\ext** nella posizione del broker client CRT locale.

6. Individua il file di configurazione dell'estensione per CRT:

    - **Retail Server:** il file si chiama **commerceruntime.ext.config** e si trova nella cartella **bin\\ext** nella posizione del sito IIS Retail Server.
    - **CRT locale sul POS moderno:** il file si chiama **CommerceRuntime.MPOSOffline.Ext.config** e si trova nella posizione del broker client CRT locale.

7. Registra la modifica CRT nel file di configurazione dell'estensione.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.SequentialSignatureRegister" />
    ```

    > [!WARNING]
    > **Non** modificare i file CommerceRuntime.MPOSOffline.config e commerceruntime.config. Questi file non sono progettati per essere personalizzati.

#### <a name="salestransactionsignaturenorway-component"></a>Componente di esempio SalesTransactionSignatureNorway

1. Individua il progetto **Runtime.Extensions.SalesTransactionSignatureNorway**.
2. Nella cartella **Extensions.SalesTransactionSignatureNorway\\bin\\Debug**, trova il file assembly **Contoso.Commerce.Runtime.SalesTransactionSignatureNorway.dll**.
3. Copiare il file assembly alla cartella dell'estensione CRT:

    - **Retail Server**: copia l'assembly nella cartella **\\bin\\ext** nella posizione del sito IIS Retail Server.
    - **CRT locale su POS moderno**: copiare l'assembly nella cartella **\\ext** nella posizione del broker client CRT locale.

4. Individua il file di configurazione dell'estensione per CRT:

    - **Retail Server:** il file si chiama **commerceruntime.ext.config** e si trova nella cartella **bin\\ext** nella posizione del sito IIS Retail Server.
    - **CRT locale sul POS moderno:** il file si chiama **CommerceRuntime.MPOSOffline.Ext.config** e si trova nella posizione del broker client CRT locale.

5. Registra la modifica CRT nel file di configurazione dell'estensione.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.SalesTransactionSignatureNorway" />
    ```

    > [!WARNING]
    > **Non** modificare i file CommerceRuntime.MPOSOffline.config e commerceruntime.config. Questi file non sono progettati per essere personalizzati.

#### <a name="sequentialsignatureregistercontracts-component"></a>Componente SequentialSignatureRegister.Contracts

1. Individua il progetto **Runtime.Extensions.SequentialSignatureRegister.Contracts**.
2. Nella cartella **Extensions.SequentialSignatureRegister.Contracts\\bin\\Debug**, trova il file assembly **Contoso.Commerce.Runtime.SequentialSignatureRegister.Contracts.dll**.
3. Copiare il file assembly alla cartella dell'estensione CRT:

    - **Retail Server**: copia l'assembly nella cartella **\\bin\\ext** nella posizione del sito IIS Retail Server.
    - **CRT locale su POS moderno**: copiare l'assembly nella cartella **\\ext** nella posizione del broker client CRT locale.

#### <a name="salespaymenttransextnorway-component"></a>Componente SalesPaymentTransExtNorway

1. Individua il progetto **Runtime.Extensions.SalesPaymentTransExtNorway** e compilalo.
2. Nella cartella **Extensions.SalesPaymentTransExtNorway\\bin\\Debug**, trovare il file assembly **Contoso.Commerce.Runtime.SalesPaymentTransExtNorway.dll**.
3. Copiare il file assembly alla cartella dell'estensione CRT:

    - **Retail Server**: copia l'assembly nella cartella **\\bin\\ext** nella posizione del sito IIS Retail Server.
    - **CRT locale su POS moderno**: copiare l'assembly nella cartella **\\ext** nella posizione del broker client CRT locale.

4. Individua il file di configurazione dell'estensione per CRT:

    - **Retail Server:** il file si chiama **commerceruntime.ext.config** e si trova nella cartella **bin\\ext** nella posizione del sito IIS Retail Server.
    - **CRT locale sul POS moderno:** il file si chiama **CommerceRuntime.MPOSOffline.Ext.config** e si trova nella posizione del broker client CRT locale.

5. Registra la modifica CRT nel file di configurazione dell'estensione.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.SalesPaymentTransExtNorway" />
    ```

    > [!WARNING]
    > **Non** modificare i file CommerceRuntime.MPOSOffline.config e commerceruntime.config. Questi file non sono progettati per essere personalizzati.

# <a name="retail-735-and-later"></a>[Retail 7.3.5 e versioni successive](#tab/retail-7-3-5)

#### <a name="registerauditeventnorway-component"></a>Componente di esempio RegisterAuditEventNorway

1. Individua il file di configurazione dell'estensione per CRT:

    - **Retail Server:** il file si chiama **commerceruntime.ext.config** e si trova nella cartella **bin\\ext** nella posizione del sito IIS Retail Server.
    - **CRT locale sul POS moderno:** il file si chiama **CommerceRuntime.MPOSOffline.Ext.config** e si trova nella posizione del broker client CRT locale.

2. Registra la modifica CRT nel file di configurazione dell'estensione.

    ``` xml
    <add source="assembly" value="Microsoft.Dynamics.Commerce.Runtime.RegisterAuditEventNorway" />
    ```

    > [!WARNING]
    > **Non** modificare i file CommerceRuntime.MPOSOffline.config e commerceruntime.config. Questi file non sono progettati per essere personalizzati.

#### <a name="sequentialsignatureregister-component"></a>Componente SequentialSignatureRegister

1. Individua il progetto **Runtime.Extensions.SequentialSignatureRegister** e compilalo.
2. Modifica il file **App.config** specificando l'identificazione personale, la posizione del negozio e il nome del negozio per il certificato da utilizzare per firmare le transazioni di vendita.
3. Compila il progetto.
4. Nella cartella **Extensions.SequentialSignatureRegister\\bin\\Debug** trova i seguenti file:

    - Il file assembly **Contoso.Commerce.Runtime.SequentialSignatureRegister.dll**
    - Il file di configurazione **Contoso.Commerce.Runtime.SequentialSignatureRegister.dll.config**

5. Copia i file assembly nella cartella dell'estensione CRT:

    - **Retail Server**: copia l'assembly nella cartella **\\bin\\ext** nella posizione del sito IIS Retail Server.
    - **CRT locale su POS moderno**: copiare l'assembly nella cartella **\\ext** nella posizione del broker client CRT locale.

6. Individua il file di configurazione dell'estensione per CRT:

    - **Retail Server:** il file si chiama **commerceruntime.ext.config** e si trova nella cartella **bin\\ext** nella posizione del sito IIS Retail Server.
    - **CRT locale sul POS moderno:** il file si chiama **CommerceRuntime.MPOSOffline.Ext.config** e si trova nella posizione del broker client CRT locale.

7. Registra la modifica CRT nel file di configurazione dell'estensione.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.SequentialSignatureRegister" />
    ```

    > [!WARNING]
    > **Non** modificare i file CommerceRuntime.MPOSOffline.config e commerceruntime.config. Questi file non sono progettati per essere personalizzati.

#### <a name="salestransactionsignaturenorway-component"></a>Componente di esempio SalesTransactionSignatureNorway

1. Individua il progetto **Runtime.Extensions.SalesTransactionSignatureNorway**.
2. Nella cartella **Extensions.SalesTransactionSignatureNorway\\bin\\Debug**, trova il file assembly **Contoso.Commerce.Runtime.SalesTransactionSignatureNorway.dll**.
3. Copiare il file assembly alla cartella dell'estensione CRT:

    - **Retail Server**: copia l'assembly nella cartella **\\bin\\ext** nella posizione del sito IIS Retail Server.
    - **CRT locale su POS moderno**: copiare l'assembly nella cartella **\\ext** nella posizione del broker client CRT locale.

4. Individua il file di configurazione dell'estensione per CRT:

    - **Retail Server:** il file si chiama **commerceruntime.ext.config** e si trova nella cartella **bin\\ext** nella posizione del sito IIS Retail Server.
    - **CRT locale sul POS moderno:** il file si chiama **CommerceRuntime.MPOSOffline.Ext.config** e si trova nella posizione del broker client CRT locale.

5. Registra la modifica CRT nel file di configurazione dell'estensione.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.SalesTransactionSignatureNorway" />
    ```

    > [!WARNING]
    > **Non** modificare i file CommerceRuntime.MPOSOffline.config e commerceruntime.config. Questi file non sono progettati per essere personalizzati.

#### <a name="sequentialsignatureregistercontracts-component"></a>Componente SequentialSignatureRegister.Contracts

1. Individua il progetto **Runtime.Extensions.SequentialSignatureRegister.Contracts**.
2. Nella cartella **Extensions.SequentialSignatureRegister.Contracts\\bin\\Debug**, trova il file assembly **Contoso.Commerce.Runtime.SequentialSignatureRegister.Contracts.dll**.
3. Copiare il file assembly alla cartella dell'estensione CRT:

    - **Retail Server**: copia l'assembly nella cartella **\\bin\\ext** nella posizione del sito IIS Retail Server.
    - **CRT locale su POS moderno**: copiare l'assembly nella cartella **\\ext** nella posizione del broker client CRT locale.

#### <a name="salespaymenttransextnorway-component"></a>Componente SalesPaymentTransExtNorway

1. Individua il progetto **Runtime.Extensions.SalesPaymentTransExtNorway** e compilalo.
2. Nella cartella **Extensions.SalesPaymentTransExtNorway\\bin\\Debug**, trovare il file assembly **Contoso.Commerce.Runtime.SalesPaymentTransExtNorway.dll**.
3. Copiare il file assembly alla cartella dell'estensione CRT:

    - **Retail Server**: copia l'assembly nella cartella **\\bin\\ext** nella posizione del sito IIS Retail Server.
    - **CRT locale su POS moderno**: copiare l'assembly nella cartella **\\ext** nella posizione del broker client CRT locale.

4. Individua il file di configurazione dell'estensione per CRT:

    - **Retail Server:** il file si chiama **commerceruntime.ext.config** e si trova nella cartella **bin\\ext** nella posizione del sito IIS Retail Server.
    - **CRT locale sul POS moderno:** il file si chiama **CommerceRuntime.MPOSOffline.Ext.config** e si trova nella posizione del broker client CRT locale.

5. Registra la modifica CRT nel file di configurazione dell'estensione.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.SalesPaymentTransExtNorway" />
    ```

    > [!WARNING]
    > **Non** modificare i file CommerceRuntime.MPOSOffline.config e commerceruntime.config. Questi file non sono progettati per essere personalizzati.

# <a name="retail-811-and-later"></a>[Retail 8.1.1 e versioni successive](#tab/retail-8-1-1)

#### <a name="registerauditeventnorway-component"></a>Componente di esempio RegisterAuditEventNorway

1. Individua il file di configurazione dell'estensione per CRT:

    - **Retail Server:** il file si chiama **commerceruntime.ext.config** e si trova nella cartella **bin\\ext** nella posizione del sito IIS Retail Server.
    - **CRT locale sul POS moderno:** il file si chiama **CommerceRuntime.MPOSOffline.Ext.config** e si trova nella posizione del broker client CRT locale.

2. Registra la modifica CRT nel file di configurazione dell'estensione.

    ``` xml
    <add source="assembly" value="Microsoft.Dynamics.Commerce.Runtime.RegisterAuditEventNorway" />
    ```

    > [!WARNING]
    > **Non** modificare i file CommerceRuntime.MPOSOffline.config e commerceruntime.config. Questi file non sono progettati per essere personalizzati.

#### <a name="sequentialsignatureregister-component"></a>Componente SequentialSignatureRegister

1. Individua il progetto **Runtime.Extensions.SequentialSignatureRegister** e compilalo.
2. Modifica il file **App.config** specificando l'identificazione personale, la posizione del negozio e il nome del negozio per il certificato da utilizzare per firmare le transazioni di vendita.
3. Compila il progetto.
4. Nella cartella **Extensions.SequentialSignatureRegister\\bin\\Debug** trova i seguenti file:

    - Il file assembly **Contoso.Commerce.Runtime.SequentialSignatureRegister.dll**
    - Il file di configurazione **Contoso.Commerce.Runtime.SequentialSignatureRegister.dll.config**

5. Copia i file assembly nella cartella dell'estensione CRT:

    - **Retail Server**: copia l'assembly nella cartella **\\bin\\ext** nella posizione del sito IIS Retail Server.
    - **CRT locale su POS moderno**: copiare l'assembly nella cartella **\\ext** nella posizione del broker client CRT locale.

6. Individua il file di configurazione dell'estensione per CRT:

    - **Retail Server:** il file si chiama **commerceruntime.ext.config** e si trova nella cartella **bin\\ext** nella posizione del sito IIS Retail Server.
    - **CRT locale sul POS moderno:** il file si chiama **CommerceRuntime.MPOSOffline.Ext.config** e si trova nella posizione del broker client CRT locale.

7. Registra la modifica CRT nel file di configurazione dell'estensione.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.SequentialSignatureRegister" />
    ```

    > [!WARNING]
    > **Non** modificare i file CommerceRuntime.MPOSOffline.config e commerceruntime.config. Questi file non sono progettati per essere personalizzati.

#### <a name="salestransactionsignaturenorway-component"></a>Componente di esempio SalesTransactionSignatureNorway

1. Individua il progetto **Runtime.Extensions.SalesTransactionSignatureNorway**.
2. Nella cartella **Extensions.SalesTransactionSignatureNorway\\bin\\Debug**, trova il file assembly **Contoso.Commerce.Runtime.SalesTransactionSignatureNorway.dll**.
3. Copiare il file assembly alla cartella dell'estensione CRT:

    - **Retail Server**: copia l'assembly nella cartella **\\bin\\ext** nella posizione del sito IIS Retail Server.
    - **CRT locale su POS moderno**: copiare l'assembly nella cartella **\\ext** nella posizione del broker client CRT locale.

4. Individua il file di configurazione dell'estensione per CRT:

    - **Retail Server:** il file si chiama **commerceruntime.ext.config** e si trova nella cartella **bin\\ext** nella posizione del sito IIS Retail Server.
    - **CRT locale sul POS moderno:** il file si chiama **CommerceRuntime.MPOSOffline.Ext.config** e si trova nella posizione del broker client CRT locale.

5. Registra la modifica CRT nel file di configurazione dell'estensione.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.SalesTransactionSignatureNorway" />
    ```

    > [!WARNING]
    > **Non** modificare i file CommerceRuntime.MPOSOffline.config e commerceruntime.config. Questi file non sono progettati per essere personalizzati.

#### <a name="sequentialsignatureregistercontracts-component"></a>Componente SequentialSignatureRegister.Contracts

1. Individua il progetto **Runtime.Extensions.SequentialSignatureRegister.Contracts**.
2. Nella cartella **Extensions.SequentialSignatureRegister.Contracts\\bin\\Debug**, trova il file assembly **Contoso.Commerce.Runtime.SequentialSignatureRegister.Contracts.dll**.
3. Copiare il file assembly alla cartella dell'estensione CRT:

    - **Retail Server**: copia l'assembly nella cartella **\\bin\\ext** nella posizione del sito IIS Retail Server.
    - **CRT locale su POS moderno**: copiare l'assembly nella cartella **\\ext** nella posizione del broker client CRT locale.

#### <a name="salespaymenttransextnorway-component"></a>Componente SalesPaymentTransExtNorway

1. Individua il progetto **Runtime.Extensions.SalesPaymentTransExtNorway** e compilalo.
2. Nella cartella **Extensions.SalesPaymentTransExtNorway\\bin\\Debug**, trovare il file assembly **Contoso.Commerce.Runtime.SalesPaymentTransExtNorway.dll**.
3. Copiare il file assembly alla cartella dell'estensione CRT:

    - **Retail Server**: copia l'assembly nella cartella **\\bin\\ext** nella posizione del sito IIS Retail Server.
    - **CRT locale su POS moderno**: copiare l'assembly nella cartella **\\ext** nella posizione del broker client CRT locale.

4. Individua il file di configurazione dell'estensione per CRT:

    - **Retail Server:** il file si chiama **commerceruntime.ext.config** e si trova nella cartella **bin\\ext** nella posizione del sito IIS Retail Server.
    - **CRT locale sul POS moderno:** il file si chiama **CommerceRuntime.MPOSOffline.Ext.config** e si trova nella posizione del broker client CRT locale.

5. Registra la modifica CRT nel file di configurazione dell'estensione.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.SalesPaymentTransExtNorway" />
    ```

    > [!WARNING]
    > **Non** modificare i file CommerceRuntime.MPOSOffline.config e commerceruntime.config. Questi file non sono progettati per essere personalizzati.

---

### <a name="the-retail-server-extension-components"></a>Componenti dell'estensione Retail Server

#### <a name="salestransactionsignature-retail-server-sample-component"></a>Componente di esempio SalesTransactionSignature Retail Server

1. Nella cartella **RetailSDK\\SampleExtensions\\RetailServer\\RetailServer.Extensions.SalesTransactionSignatureSample** trova il progetto **RetailServer.Extensions.SalesTransactionSignatureSample** e compilalo.
2. Nella cartella **RetailServer\\Extensions.SalesTransactionSignatureSample\\bin\\Debug** trova il file assembly **Contoso.RetailServer.SalesTransactionSignatureSample.dll**.
3. Copia il file assembly nella cartella dell'estensione Retail Server.

    # <a name="application-update-4"></a>[Aggiornamento applicazione 4](#tab/app-update-4)

    La cartella è la cartella **\\bin** nella posizione del sito IIS Retail Server.

    # <a name="application-update-5-and-later"></a>[Aggiornamento applicazione 5 e successivi](#tab/app-update-5-and-later)

    La cartella è la cartella **\\bin** nella posizione del sito IIS Retail Server.

    # <a name="retail-731"></a>[Retail 7.3.1](#tab/retail-7-3-1)

    La cartella è la cartella **\\bin\\ext** nella posizione del sito IIS Retail Server.

    # <a name="retail-732-and-later"></a>[Retail 7.3.2 e versioni successive](#tab/retail-7-3-2)

    La cartella è la cartella **\\bin\\ext** nella posizione del sito IIS Retail Server.

    # <a name="retail-735-and-later"></a>[Retail 7.3.5 e versioni successive](#tab/retail-7-3-5)

    La cartella è la cartella **\\bin\\ext** nella posizione del sito IIS Retail Server.

    # <a name="retail-811-and-later"></a>[Retail 8.1.1 e versioni successive](#tab/retail-8-1-1)

    La cartella è la cartella **\\bin\\ext** nella posizione del sito IIS Retail Server.

    ---

4. Individua il file di configurazione per Retail Server. Il file si chiama **web.config** e si trova nella cartella radice nella posizione del sito IIS Retail Server.
5. Registra le estensioni Retail Server nella sezione **extensionComposition** del file di configurazione.

    ``` xml
    <add source="assembly" value="Contoso.RetailServer.SalesTransactionSignatureSample" />
    ```

6. Registra le dipendenze delle estensioni Retail Server.

    # <a name="application-update-4"></a>[Aggiornamento applicazione 4](#tab/app-update-4/)

    1. Nella cartella **CommerceRuntime\\Extensions.SalesTransactionSignatureSample\\bin\\Debug** trova i seguenti file:

        - Il file assembly **Contoso.Commerce.Runtime.SalesTransactionSignatureSample.dll**
        - Il file di configurazione **Contoso.Commerce.Runtime.SalesTransactionSignatureSample.dll.config**

    2. Copia i file nella cartella **\\bin** nella posizione del sito IIS Retail Server.
    3. Registra la modifica CRT nel file di configurazione dell'estensione per CRT. Il file si chiama **commerceruntime.ext.config** e si trova nella cartella **bin** nella posizione del sito IIS Retail Server.

        ``` xml
        <add source="assembly" value="Contoso.Commerce.Runtime.SalesTransactionSignatureSample" />
        ```

    # <a name="application-update-5-and-later"></a>[Aggiornamento applicazione 5 e successivi](#tab/app-update-5-and-later/)

    1. Nella cartella **CommerceRuntime\\Extensions.SalesTransactionSignatureSample.Messages\\bin\\Debug** trova il file assembly **Contoso.Commerce.Runtime.SalesTransactionSignatureSample.Messages.dll**.
    2. Copia il file nella cartella **\\bin** nella posizione del sito IIS Retail Server.
    3. Registra la modifica CRT nel file di configurazione dell'estensione per CRT. Il file si chiama **commerceruntime.ext.config** e si trova nella cartella **bin** nella posizione del sito IIS Retail Server.

        ``` xml
        <add source="assembly" value="Contoso.Commerce.Runtime.SalesTransactionSignatureSample.Messages" />
        ```

    # <a name="retail-731"></a>[Retail 7.3.1](#tab/retail-7-3-1)

    > [!NOTE]
    > Non è richiesta alcuna azione.

    # <a name="retail-732-and-later"></a>[Retail 7.3.2 e versioni successive](#tab/retail-7-3-2)

    > [!NOTE]
    > Non è richiesta alcuna azione.

    # <a name="retail-735-and-later"></a>[Retail 7.3.5 e versioni successive](#tab/retail-7-3-5)

    > [!NOTE]
    > Non è richiesta alcuna azione.

    # <a name="retail-811-and-later"></a>[Retail 8.1.1 e versioni successive](#tab/retail-8-1-1)

    > [!NOTE]
    > Non è richiesta alcuna azione.

    ---

### <a name="the-modern-pos-extension-components"></a>Componenti dell'estensione Modern POS

#### <a name="implement-the-proxy-code-for-offline-mode"></a>Implementa il codice proxy per la modalità offline

Questa parte è equivalente al controller Retail Server, ma estende il CRT locale che viene utilizzato quando il client non è connesso.

1. Nel file **customization.settings** cambia la sezione **@(RetailServerLibraryPathForProxyGeneration)** in modo che utilizzi il nuovo assembly Retail Server per la generazione del proxy.
2. Implementa i seguenti metodi di interfaccia nella classe **StoreOperationsManager**. Per la prima iterazione, aggiungi il seguente codice:

    # <a name="application-update-4"></a>[Aggiornamento applicazione 4](#tab/app-update-4)

    ``` csharp
    public Task<bool> SalesTransactionSignatureServiceIsReady()
    {
        throw new NotImplementedException();
    }
    public Task<FiscalTransaction> GetLastFiscalTransaction(string storeNumber, string terminalId)
    {
        throw new NotImplementedException();
    }
    ```

    # <a name="application-update-5-and-later"></a>[Aggiornamento applicazione 5 e successivi](#tab/app-update-5-and-later)

    ``` csharp
    public Task<bool> SalesTransactionSignatureServiceIsReady(string correlationId)
    {
        throw new NotImplementedException();
    }
    public Task<FiscalTransaction> GetLastFiscalTransaction(string storeNumber, string terminalId)
    {
        throw new NotImplementedException();
    }
    ```

    # <a name="retail-731"></a>[Retail 7.3.1](#tab/retail-7-3-1)

    > [!NOTE]
    > Questo passaggio non si applica a questa versione.

    # <a name="retail-732-and-later"></a>[Retail 7.3.2 e versioni successive](#tab/retail-7-3-2)

    > [!NOTE]
    > Questo passaggio non si applica a questa versione.

    # <a name="retail-735-and-later"></a>[Retail 7.3.5 e versioni successive](#tab/retail-7-3-5)

    > [!NOTE]
    > Questo passaggio non si applica a questa versione.

    # <a name="retail-811-and-later"></a>[Retail 8.1.1 e versioni successive](#tab/retail-8-1-1)

    > [!NOTE]
    > Questo passaggio non si applica a questa versione.

    ---

3. Per rigenerare il codice proxy, crea la cartella **Proxies** dalla riga di comando utilizzando il comando **msbuild /t:Rebuild**.
4. Risolvi le dipendenze del progetto **Proxy.RetailProxy**:

    # <a name="application-update-4"></a>[Aggiornamento applicazione 4](#tab/app-update-4)

    Apri **RetailSDK\\Proxies\\RetailProxy\\Proxies.RetailProxy.csproj**, aggiungi il progetto **RetailSDK\\SampleExtensions\\CommerceRuntime\\Extensions.SalesTransactionSignatureSample\\CommerceRuntime.Extensions.SalesTransactionSignatureSample** alla soluzione e aggiungi un riferimento al progetto **RetailProxy** per fare riferimento a **SalesTransactionSignatureSample**.

    # <a name="application-update-5-and-later"></a>[Aggiornamento applicazione 5 e successivi](#tab/app-update-5-and-later)

    Apri **RetailSDK\\Proxies\\RetailProxy\\Proxies.RetailProxy.csproj**, aggiungi il progetto **RetailSDK\\SampleExtensions\\CommerceRuntime\\Extensions.SalesTransactionSignatureSample.Messages\\CommerceRuntime.Extensions.SalesTransactionSignatureSample.Messages** alla soluzione e aggiungi un riferimento al progetto **RetailProxy** per fare riferimento a **SalesTransactionSignatureSample.Messages**.

    # <a name="retail-731"></a>[Retail 7.3.1](#tab/retail-7-3-1)

    > [!NOTE]
    > Questo passaggio non si applica a questa versione.

    # <a name="retail-732-and-later"></a>[Retail 7.3.2 e versioni successive](#tab/retail-7-3-2)

    > [!NOTE]
    > Questo passaggio non si applica a questa versione.

    # <a name="retail-735-and-later"></a>[Retail 7.3.5 e versioni successive](#tab/retail-7-3-5)

    > [!NOTE]
    > Questo passaggio non si applica a questa versione.

    # <a name="retail-811-and-later"></a>[Retail 8.1.1 e versioni successive](#tab/retail-8-1-1)

    > [!NOTE]
    > Questo passaggio non si applica a questa versione.

    ---

5. Modifica i metodi di interfaccia nella classe **StoreOperationsManager**:

    # <a name="application-update-4"></a>[Aggiornamento applicazione 4](#tab/app-update-4)

    ``` csharp
    public Task<bool> SalesTransactionSignatureServiceIsReady()
    {
        return Task.Run(() => CommerceRuntimeManager.Runtime.Execute<SalesTransactionSignatureServiceIsReadyResponse>(new SalesTransactionSignatureServiceIsReadyRequest(), null).IsReady);
    }
    public Task<FiscalTransaction> GetLastFiscalTransaction(string storeNumber, string terminalId)
    {
        return Task.Run(() => CommerceRuntimeManager.Runtime.Execute<GetLastFiscalTransactionResponse>(new GetLastFiscalTransactionRequest(), null).FiscalTransaction);
    }
    ```

    # <a name="application-update-5-and-later"></a>[Aggiornamento applicazione 5 e successivi](#tab/app-update-5-and-later)

    ``` csharp
    public Task<bool> SalesTransactionSignatureServiceIsReady(string correlationId)
    {
        return Task.Run(() => CommerceRuntimeManager.Runtime.Execute<SalesTransactionSignatureServiceIsReadyResponse>(new SalesTransactionSignatureServiceIsReadyRequest(), null).IsReady);
    }
    public Task<FiscalTransaction> GetLastFiscalTransaction(string storeNumber, string terminalId)
    {
        return Task.Run(() => CommerceRuntimeManager.Runtime.Execute<GetLastFiscalTransactionResponse>(new GetLastFiscalTransactionRequest(), null).FiscalTransaction);
    }
    ```

    # <a name="retail-731"></a>[Retail 7.3.1](#tab/retail-7-3-1)

    > [!NOTE]
    > Questo passaggio non si applica a questa versione.

    # <a name="retail-732-and-later"></a>[Retail 7.3.2 e versioni successive](#tab/retail-7-3-2)

    > [!NOTE]
    > Questo passaggio non si applica a questa versione.

    # <a name="retail-735-and-later"></a>[Retail 7.3.5 e versioni successive](#tab/retail-7-3-5)

    > [!NOTE]
    > Questo passaggio non si applica a questa versione.

    # <a name="retail-811-and-later"></a>[Retail 8.1.1 e versioni successive](#tab/retail-8-1-1)

    > [!NOTE]
    > Questo passaggio non si applica a questa versione.

    ---

6. Aggiorna il file **dllhost.exe.config** in modo che il broker client carichi il nuovo assembly RetailProxy.

    ``` xml
    <add key="RetailProxyAssemblyName" value="Contoso.Commerce.RetailProxy" />
    <add key="AdaptorCallerFullTypeName" value="Contoso.Commerce.RetailProxy.Adapters.AdaptorCaller" />
    ```

#### <a name="retail-proxy-extension-component-retail-731-and-later"></a>Componente di estensione Retail proxy (Retail 7.3.1 e versioni successive)

Completa la seguente procedura solo se utilizzi Retail 7.3.1 e versioni successive.

1. Nella cartella **RetailSDK\\SampleExtensions\\RetailProxy\\RetailProxy.Extensions.SalesTransactionSignatureSample** trova il progetto **RetailServer.Extensions.SalesTransactionSignatureSample** e compilalo.
2. Nella cartella **RetailProxy\\RetailProxy.Extensions.SalesTransactionSignatureSample\\bin\\Debug** trova il file assembly **Contoso.Commerce.RetailProxy.SalesTransactionSignatureSample**.
3. Copia i file assembly nella cartella **\\ext** nella posizione del broker client CRT locale.
4. Registra la modifica Retail proxy nel file di configurazione dell'estensione. Il file si chiama **RetailProxy.MPOSOffline.ext.config** e si trova nella posizione del broker client CRT locale.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.RetailProxy.SalesTransactionSignatureSample" />
    ```

#### <a name="modern-pos-extension-components"></a>Componenti dell'estensione POS moderno

1. Apri la soluzione in **RetailSdk\\POS\\ModernPOS.sln** e assicurati che possa essere compilata senza errori. Inoltre, assicurati di poter eseguire Modern POS da Microsoft Visual Studio usando il comando **Esegui**.

    > [!NOTE]
    > Il Modern POS non deve essere personalizzato. È necessario abilitare il controllo dell'account utente (UAC) e disinstallare le istanze di Modern POS installate in precedenza come richiesto.

2. Includi le seguenti cartelle del codice sorgente esistenti nel progetto **Pos.Extensions**.

    # <a name="application-update-4"></a>[Aggiornamento applicazione 4](#tab/app-update-4)

    - AuditEventExtensionSample
    - SalesTransactionSignatureSample

    # <a name="application-update-5-and-later"></a>[Aggiornamento applicazione 5 e successivi](#tab/app-update-5-and-later)

    - AuditEventExtensionSample
    - SalesTransactionSignatureSample

    # <a name="retail-731"></a>[Retail 7.3.1](#tab/retail-7-3-1)

    - AuditEventExtensionSample
    - SalesTransactionSignatureSample

    # <a name="retail-732-and-later"></a>[Retail 7.3.2 e versioni successive](#tab/retail-7-3-2)

    - AuditEventExtensionSample
    - SalesTransactionSignatureSample
    - SalesTransactionSignatureNorway
    - SequentialSignature

    # <a name="retail-735-and-later"></a>[Retail 7.3.5 e versioni successive](#tab/retail-7-3-5)

    - SalesTransactionSignatureSample
    - SalesTransactionSignatureNorway
    - SequentialSignature

    # <a name="retail-811-and-later"></a>[Retail 8.1.1 e versioni successive](#tab/retail-8-1-1)

    - SalesTransactionSignatureSample
    - SalesTransactionSignatureNorway
    - SequentialSignature

    ---

3. Abilita le estensioni da compilare in **tsconfig.json** rimuovendo le seguenti cartelle dall'elenco di esclusione.

    # <a name="application-update-4"></a>[Aggiornamento applicazione 4](#tab/app-update-4)

    - AuditEventExtensionSample
    - SalesTransactionSignatureSample

    # <a name="application-update-5-and-later"></a>[Aggiornamento applicazione 5 e successivi](#tab/app-update-5-and-later)

    - AuditEventExtensionSample
    - SalesTransactionSignatureSample

    # <a name="retail-731"></a>[Retail 7.3.1](#tab/retail-7-3-1)

    - AuditEventExtensionSample
    - SalesTransactionSignatureSample

    # <a name="retail-732-and-later"></a>[Retail 7.3.2 e versioni successive](#tab/retail-7-3-2)

    - AuditEventExtensionSample
    - SalesTransactionSignatureSample
    - SalesTransactionSignatureNorway
    - SequentialSignature

    # <a name="retail-735-and-later"></a>[Retail 7.3.5 e versioni successive](#tab/retail-7-3-5)

    - SalesTransactionSignatureSample
    - SalesTransactionSignatureNorway
    - SequentialSignature

    # <a name="retail-811-and-later"></a>[Retail 8.1.1 e versioni successive](#tab/retail-8-1-1)

    - SalesTransactionSignatureSample
    - SalesTransactionSignatureNorway
    - SequentialSignature

    ---

4. Abilita le estensioni da caricare in **extensions.json** aggiungendo le seguenti righe al posto appropriato.

    # <a name="application-update-4"></a>[Aggiornamento applicazione 4](#tab/app-update-4)

    ``` json
    {
        "baseUrl": "AuditEventExtensionSample"
    },
    {
        "baseUrl": "SalesTransactionSignatureSample"
    }
    ```

    # <a name="application-update-5-and-later"></a>[Aggiornamento applicazione 5 e successivi](#tab/app-update-5-and-later)

    ``` json
    {
        "baseUrl": "AuditEventExtensionSample"
    },
    {
        "baseUrl": "SalesTransactionSignatureSample"
    }
    ```

    # <a name="retail-731"></a>[Retail 7.3.1](#tab/retail-7-3-1)

    ``` json
    {
        "baseUrl": "AuditEventExtensionSample"
    },
    {
        "baseUrl": "SalesTransactionSignatureSample"
    }
    ```

    # <a name="retail-732-and-later"></a>[Retail 7.3.2 e versioni successive](#tab/retail-7-3-2)

    ``` json
    {
        "baseUrl": "AuditEventExtensionSample"
    },
    {
        "baseUrl": "SalesTransactionSignatureSample"
    },
    {
        "baseUrl": "SalesTransactionSignatureNorway"
    },
    {
        "baseUrl": "SequentialSignature"
    }
    ```

    # <a name="retail-735-and-later"></a>[Retail 7.3.5 e versioni successive](#tab/retail-7-3-5)

    ``` json
    {
        "baseUrl": "Microsoft/AuditEvent.NO"
    },
    {
        "baseUrl": "SalesTransactionSignatureSample"
    },
    {
        "baseUrl": "SalesTransactionSignatureNorway"
    },
    {
        "baseUrl": "SequentialSignature"
    }
    ```

    # <a name="retail-811-and-later"></a>[Retail 8.1.1 e versioni successive](#tab/retail-8-1-1)

    ``` json
    {
        "baseUrl": "Microsoft/AuditEvent.NO"
    },
    {
        "baseUrl": "SalesTransactionSignatureSample"
    },
    {
        "baseUrl": "SalesTransactionSignatureNorway"
    },
    {
        "baseUrl": "SequentialSignature"
    }
    ```

    ---

    > [!NOTE]
    > Per ulteriori informazioni e per esempi che mostrano come includere le cartelle del codice sorgente e abilitare il caricamento delle estensioni, vedi le istruzioni nel file readme.md nel progetto **Pos.Extensions**.

5. Ricompila la soluzione.
6. Esegui Modern POS nel debugger e verifica la funzionalità.

### <a name="cloud-pos-extension-components"></a>Componenti dell'estensione POS cloud

1. Apri la soluzione in **RetailSdk\\POS\\CloudPOS.sln** e assicurati che possa essere compilata senza errori.
2. Includi le seguenti cartelle del codice sorgente esistenti nel progetto **Pos.Extensions**.

    # <a name="application-update-4"></a>[Aggiornamento applicazione 4](#tab/app-update-4)

    - AuditEventExtensionSample
    - SalesTransactionSignatureSample

    # <a name="application-update-5-and-later"></a>[Aggiornamento applicazione 5 e successivi](#tab/app-update-5-and-later)

    - AuditEventExtensionSample
    - SalesTransactionSignatureSample

    # <a name="retail-731"></a>[Retail 7.3.1](#tab/retail-7-3-1)

    - AuditEventExtensionSample
    - SalesTransactionSignatureSample

    # <a name="retail-732-and-later"></a>[Retail 7.3.2 e versioni successive](#tab/retail-7-3-2)

    - AuditEventExtensionSample
    - SalesTransactionSignatureSample
    - SalesTransactionSignatureNorway
    - SequentialSignature

    # <a name="retail-735-and-later"></a>[Retail 7.3.5 e versioni successive](#tab/retail-7-3-5)

    - SalesTransactionSignatureSample
    - SalesTransactionSignatureNorway
    - SequentialSignature

    # <a name="retail-811-and-later"></a>[Retail 8.1.1 e versioni successive](#tab/retail-8-1-1)

    - SalesTransactionSignatureSample
    - SalesTransactionSignatureNorway
    - SequentialSignature

    ---

3. Abilita le estensioni da compilare in **tsconfig.json** rimuovendo le seguenti cartelle dall'elenco di esclusione.

    # <a name="application-update-4"></a>[Aggiornamento applicazione 4](#tab/app-update-4)

    - AuditEventExtensionSample
    - SalesTransactionSignatureSample

    # <a name="application-update-5-and-later"></a>[Aggiornamento applicazione 5 e successivi](#tab/app-update-5-and-later)

    - AuditEventExtensionSample
    - SalesTransactionSignatureSample

    # <a name="retail-731"></a>[Retail 7.3.1](#tab/retail-7-3-1)

    - AuditEventExtensionSample
    - SalesTransactionSignatureSample

    # <a name="retail-732-and-later"></a>[Retail 7.3.2 e versioni successive](#tab/retail-7-3-2)

    - AuditEventExtensionSample
    - SalesTransactionSignatureSample
    - SalesTransactionSignatureNorway
    - SequentialSignature

    # <a name="retail-735-and-later"></a>[Retail 7.3.5 e versioni successive](#tab/retail-7-3-5)

    - SalesTransactionSignatureSample
    - SalesTransactionSignatureNorway
    - SequentialSignature

    # <a name="retail-811-and-later"></a>[Retail 8.1.1 e versioni successive](#tab/retail-8-1-1)

    - SalesTransactionSignatureSample
    - SalesTransactionSignatureNorway
    - SequentialSignature

    ---

4. Abilita le estensioni da caricare in **extensions.json** aggiungendo le seguenti righe al posto appropriato.

    # <a name="application-update-4"></a>[Aggiornamento applicazione 4](#tab/app-update-4)

    ``` json
    {
        "baseUrl": "AuditEventExtensionSample"
    },
    {
        "baseUrl": "SalesTransactionSignatureSample"
    }
    ```

    # <a name="application-update-5-and-later"></a>[Aggiornamento applicazione 5 e successivi](#tab/app-update-5-and-later)

    ``` json
    {
        "baseUrl": "AuditEventExtensionSample"
    },
    {
        "baseUrl": "SalesTransactionSignatureSample"
    }
    ```

    # <a name="retail-731"></a>[Retail 7.3.1](#tab/retail-7-3-1)

    ``` json
    {
        "baseUrl": "AuditEventExtensionSample"
    },
    {
        "baseUrl": "SalesTransactionSignatureSample"
    }
    ```

    # <a name="retail-732-and-later"></a>[Retail 7.3.2 e versioni successive](#tab/retail-7-3-2)

    ``` json
    {
        "baseUrl": "AuditEventExtensionSample"
    },
    {
        "baseUrl": "SalesTransactionSignatureSample"
    },
    {
        "baseUrl": "SalesTransactionSignatureNorway"
    },
    {
        "baseUrl": "SequentialSignature"
    }
    ```

    # <a name="retail-735-and-later"></a>[Retail 7.3.5 e versioni successive](#tab/retail-7-3-5)

    ``` json
    {
        "baseUrl": "Microsoft/AuditEvent.NO"
    },
    {
        "baseUrl": "SalesTransactionSignatureSample"
    },
    {
        "baseUrl": "SalesTransactionSignatureNorway"
    },
    {
        "baseUrl": "SequentialSignature"
    }
    ```

    # <a name="retail-811-and-later"></a>[Retail 8.1.1 e versioni successive](#tab/retail-8-1-1)

    ``` json
    {
        "baseUrl": "Microsoft/AuditEvent.NO"
    },
    {
        "baseUrl": "SalesTransactionSignatureSample"
    },
    {
        "baseUrl": "SalesTransactionSignatureNorway"
    },
    {
        "baseUrl": "SequentialSignature"
    }
    ```

    ---

    > [!NOTE]
    > Per ulteriori informazioni e per esempi che mostrano come includere le cartelle del codice sorgente e abilitare il caricamento delle estensioni, vedi le istruzioni nel file readme.md nel progetto **Pos.Extensions**.

5. Ricompila la soluzione.
6. Esegui la soluzione usando il comando **Esegui** e seguendo i passaggi nel manuale di Retail SDK.
7. Testa la funzionalità.

### <a name="set-up-required-parameters-in-headquarters"></a>Impostare i parametri richiesti in Headquarters

Per ulteriori informazioni, vedi [Funzionalità del registro di cassa per la Norvegia](./emea-nor-cash-registers.md).

## <a name="production-environment"></a>Ambiente di produzione

Attenersi alla procedura seguente per creare pacchetti distribuibili contenenti componenti Commerce e per applicare quei pacchetti a un ambiente di produzione.

1. Completa i passaggi nella sezione [Componenti dell'estensione Cloud POS](#cloud-pos-extension-components) o [Componenti dell'estensione Modern POS](#modern-pos-extension-components) precedente in questo articolo.
2. Apportare le seguenti modifiche nei file di configurazione dei pacchetti nella cartella **RetailSdk\\Assets** :

    1. Nei file di configurazione **CommerceRuntime.MPOSOffline.Ext.config** e **commerceruntime.ext.config**, aggiungere le seguenti righe alla sezione **composition**:

        # <a name="application-update-4"></a>[Aggiornamento applicazione 4](#tab/app-update-4)

        ``` xml
        <add source="assembly" value="Contoso.Commerce.Runtime.ReceiptsNorway" />
        <add source="assembly" value="Contoso.Commerce.Runtime.RegisterAuditEventSample" />
        <add source="assembly" value="Contoso.Commerce.Runtime.SalesPaymentTransExt" />
        <add source="assembly" value="Contoso.Commerce.Runtime.SalesTransactionSignatureSample" />
        <add source="assembly" value="Contoso.Commerce.Runtime.XZReportsNorway" />
        ```

        # <a name="application-update-5-and-later"></a>[Aggiornamento applicazione 5 e successivi](#tab/app-update-5-and-later)

        ``` xml
        <add source="assembly" value="Contoso.Commerce.Runtime.ReceiptsNorway" />
        <add source="assembly" value="Contoso.Commerce.Runtime.RegisterAuditEventSample" />
        <add source="assembly" value="Contoso.Commerce.Runtime.SalesPaymentTransExt" />
        <add source="assembly" value="Contoso.Commerce.Runtime.SalesTransactionSignatureSample" />
        <add source="assembly" value="Contoso.Commerce.Runtime.SalesTransactionSignatureSample.Messages" />
        <add source="assembly" value="Contoso.Commerce.Runtime.XZReportsNorway" />
        ```

        # <a name="retail-731"></a>[Retail 7.3.1](#tab/retail-7-3-1)

        ``` xml
        <add source="assembly" value="Contoso.Commerce.Runtime.ReceiptsNorway" />
        <add source="assembly" value="Contoso.Commerce.Runtime.RegisterAuditEventSample" />
        <add source="assembly" value="Contoso.Commerce.Runtime.SalesPaymentTransExt" />
        <add source="assembly" value="Contoso.Commerce.Runtime.SalesTransactionSignatureSample" />
        <add source="assembly" value="Contoso.Commerce.Runtime.XZReportsNorway" />
        ```

        # <a name="retail-732-and-later"></a>[Retail 7.3.2 e versioni successive](#tab/retail-7-3-2)

        ``` xml
        <add source="assembly" value="Contoso.Commerce.Runtime.ReceiptsNorway" />
        <add source="assembly" value="Contoso.Commerce.Runtime.RegisterAuditEventSample" />
        <add source="assembly" value="Contoso.Commerce.Runtime.SalesPaymentTransExt" />
        <add source="assembly" value="Contoso.Commerce.Runtime.SalesPaymentTransExtNorway" />
        <add source="assembly" value="Contoso.Commerce.Runtime.SequentialSignatureRegister" />
        <add source="assembly" value="Contoso.Commerce.Runtime.SalesTransactionSignatureNorway" />
        <add source="assembly" value="Contoso.Commerce.Runtime.XZReportsNorway" />
        ```

        # <a name="retail-735-and-later"></a>[Retail 7.3.5 e versioni successive](#tab/retail-7-3-5)

        ``` xml
        <add source="assembly" value="Microsoft.Dynamics.Commerce.Runtime.RegisterAuditEventNorway" />
        <add source="assembly" value="Contoso.Commerce.Runtime.ReceiptsNorway" />
        <add source="assembly" value="Contoso.Commerce.Runtime.RegisterAuditEventSample" />
        <add source="assembly" value="Contoso.Commerce.Runtime.SalesPaymentTransExt" />
        <add source="assembly" value="Contoso.Commerce.Runtime.SalesPaymentTransExtNorway" />
        <add source="assembly" value="Contoso.Commerce.Runtime.SequentialSignatureRegister" />
        <add source="assembly" value="Contoso.Commerce.Runtime.SalesTransactionSignatureNorway" />
        <add source="assembly" value="Contoso.Commerce.Runtime.XZReportsNorway" />
        ```

        # <a name="retail-811-and-later"></a>[Retail 8.1.1 e versioni successive](#tab/retail-8-1-1)

        ``` xml
        <add source="assembly" value="Microsoft.Dynamics.Commerce.Runtime.RegisterAuditEventNorway" />
        <add source="assembly" value="Contoso.Commerce.Runtime.ReceiptsNorway" />
        <add source="assembly" value="Contoso.Commerce.Runtime.SalesPaymentTransExt" />
        <add source="assembly" value="Contoso.Commerce.Runtime.SalesPaymentTransExtNorway" />
        <add source="assembly" value="Contoso.Commerce.Runtime.SequentialSignatureRegister" />
        <add source="assembly" value="Contoso.Commerce.Runtime.SalesTransactionSignatureNorway" />
        <add source="assembly" value="Contoso.Commerce.Runtime.XZReportsNorway" />
        ```

        ---

    2. Abilita la personalizzazione di Commerce Proxy:

        # <a name="application-update-4"></a>[Aggiornamento applicazione 4](#tab/app-update-4)

        Nel file di configurazione **dllhost.exe.config**, aggiungi le seguenti righe alla sottosezione **appSettings** della sezione **configuration**.

        ``` xml
        <add key="RetailProxyAssemblyName" value="Contoso.Commerce.RetailProxy"/>
        <add key="AdaptorCallerFullTypeName" value ="Contoso.Commerce.RetailProxy.Adapters.AdaptorCaller"/>
        ```

        # <a name="application-update-5-and-later"></a>[Aggiornamento applicazione 5 e successivi](#tab/app-update-5-and-later)

        Nel file di configurazione **dllhost.exe.config**, aggiungi le seguenti righe alla sottosezione **appSettings** della sezione **configuration**.

        ``` xml
        <add key="RetailProxyAssemblyName" value="Contoso.Commerce.RetailProxy"/>
        <add key="AdaptorCallerFullTypeName" value ="Contoso.Commerce.RetailProxy.Adapters.AdaptorCaller"/>
        ```

        # <a name="retail-731"></a>[Retail 7.3.1](#tab/retail-7-3-1)

        Nel file di configurazione **RetailProxy.MPOSOffline.ext.config**, aggiungi le seguenti righe alla sezione **composition**:

        ``` xml
        <add source="assembly" value="Contoso.Commerce.RetailProxy.SalesTransactionSignatureSample" />
        ```

        # <a name="retail-732-and-later"></a>[Retail 7.3.2 e versioni successive](#tab/retail-7-3-2)

        Nel file di configurazione **RetailProxy.MPOSOffline.ext.config**, aggiungi le seguenti righe alla sezione **composition**:

        ``` xml
        <add source="assembly" value="Contoso.Commerce.RetailProxy.SalesTransactionSignatureSample" />
        ```

        # <a name="retail-735-and-later"></a>[Retail 7.3.5 e versioni successive](#tab/retail-7-3-5)

        Nel file di configurazione **RetailProxy.MPOSOffline.ext.config**, aggiungi le seguenti righe alla sezione **composition**:

        ``` xml
        <add source="assembly" value="Contoso.Commerce.RetailProxy.SalesTransactionSignatureSample" />
        ```

        # <a name="retail-811-and-later"></a>[Retail 8.1.1 e versioni successive](#tab/retail-8-1-1)

        Nel file di configurazione **RetailProxy.MPOSOffline.ext.config**, aggiungi le seguenti righe alla sezione **composition**:

        ``` xml
        <add source="assembly" value="Contoso.Commerce.RetailProxy.SalesTransactionSignatureSample" />
        ```

        ---

3. Apporta le seguenti modifiche nel file di configurazione di personalizzazione dei pacchetti **Customization.settings**:

    1. Abilita la personalizzazione di Retail Proxy.

        # <a name="application-update-4"></a>[Aggiornamento applicazione 4](#tab/app-update-4)

        Aggiungi le seguenti righe alla sezione **&lt;ItemGroup Condition="'@(RetailServerLibraryPathForProxyGeneration)' == ''"&gt;**.

        ``` xml
        <RetailServerLibraryPathForProxyGeneration Include="$(SdkReferencesPath)\Contoso.RetailServer.SalesTransactionSignatureSample.dll"/>
        ```

        # <a name="application-update-5-and-later"></a>[Aggiornamento applicazione 5 e successivi](#tab/app-update-5-and-later)

        Aggiungi le seguenti righe alla sezione **&lt;ItemGroup Condition="'@(RetailServerLibraryPathForProxyGeneration)' == ''"&gt;**.

        ``` xml
        <RetailServerLibraryPathForProxyGeneration Include="$(SdkReferencesPath)\Contoso.RetailServer.SalesTransactionSignatureSample.dll"/>
        ```

        # <a name="retail-731"></a>[Retail 7.3.1](#tab/retail-7-3-1)

        Aggiungi le seguenti righe alla sezione **ItemGroup** per includere l'estensione Retail proxy nei pacchetti distribuibili:

        ``` xml
        <ISV_RetailProxy_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.RetailProxy.SalesTransactionSignatureSample.dll" />
        ```

        # <a name="retail-732-and-later"></a>[Retail 7.3.2 e versioni successive](#tab/retail-7-3-2)

        Aggiungi le seguenti righe alla sezione **ItemGroup** per includere l'estensione Retail proxy nei pacchetti distribuibili:

        ``` xml
        <ISV_RetailProxy_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.RetailProxy.SalesTransactionSignatureSample.dll" />
        ```

        # <a name="retail-735-and-later"></a>[Retail 7.3.5 e versioni successive](#tab/retail-7-3-5)

        Aggiungi le seguenti righe alla sezione **ItemGroup** per includere l'estensione Retail proxy nei pacchetti distribuibili:

        ``` xml
        <ISV_RetailProxy_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.RetailProxy.SalesTransactionSignatureSample.dll" />
        ```

        # <a name="retail-811-and-later"></a>[Retail 8.1.1 e versioni successive](#tab/retail-8-1-1)

        Aggiungi le seguenti righe alla sezione **ItemGroup** per includere l'estensione Retail proxy nei pacchetti distribuibili:

        ``` xml
        <ISV_RetailProxy_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.RetailProxy.SalesTransactionSignatureSample.dll" />
        ```

        ---

    2. Aggiungi le seguenti righe alla sezione **ItemGroup** per includere le estensioni CRT nei pacchetti distribuibili:

        # <a name="application-update-4"></a>[Aggiornamento applicazione 4](#tab/app-update-4)

        ``` xml
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.ReceiptsNorway.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.RegisterAuditEventSample.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesPaymentTransExt.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesTransactionSignatureSample.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesTransactionSignatureSample.dll.config" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.XZReportsNorway.dll" />
        ```

        # <a name="application-update-5-and-later"></a>[Aggiornamento applicazione 5 e successivi](#tab/app-update-5-and-later)

        ``` xml
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.ReceiptsNorway.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.RegisterAuditEventSample.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesPaymentTransExt.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesTransactionSignatureSample.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesTransactionSignatureSample.dll.config" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesTransactionSignatureSample.Messages.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.XZReportsNorway.dll" />
        ```

        # <a name="retail-731"></a>[Retail 7.3.1](#tab/retail-7-3-1)

        ``` xml
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.ReceiptsNorway.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.RegisterAuditEventSample.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesPaymentTransExt.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesTransactionSignatureSample.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesTransactionSignatureSample.dll.config" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SequentialSignatureRegister.Contracts.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.XZReportsNorway.dll" />
        ```

        # <a name="retail-732-and-later"></a>[Retail 7.3.2 e versioni successive](#tab/retail-7-3-2)

        ``` xml
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.ReceiptsNorway.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.RegisterAuditEventSample.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesPaymentTransExt.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesPaymentTransExtNorway.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SequentialSignatureRegister.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesTransactionSignatureNorway.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SequentialSignatureRegister.dll.config" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SequentialSignatureRegister.Contracts.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.XZReportsNorway.dll" />
        ```

        # <a name="retail-735-and-later"></a>[Retail 7.3.5 e versioni successive](#tab/retail-7-3-5)

        ``` xml
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.ReceiptsNorway.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesPaymentTransExt.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesPaymentTransExtNorway.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SequentialSignatureRegister.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesTransactionSignatureNorway.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SequentialSignatureRegister.dll.config" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SequentialSignatureRegister.Contracts.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.XZReportsNorway.dll" />
        ```

        # <a name="retail-811-and-later"></a>[Retail 8.1.1 e versioni successive](#tab/retail-8-1-1)

        ``` xml
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.ReceiptsNorway.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesPaymentTransExt.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesPaymentTransExtNorway.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SequentialSignatureRegister.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesTransactionSignatureNorway.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SequentialSignatureRegister.dll.config" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SequentialSignatureRegister.Contracts.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.XZReportsNorway.dll" />
        ```

        ---

    3. Aggiungi le seguenti righe alla sezione **ItemGroup** per includere l'estensione Retail Server nei pacchetti distribuibili:

        # <a name="application-update-4"></a>[Aggiornamento applicazione 4](#tab/app-update-4)

        ``` xml
        <ISV_RetailServer_CustomizableFile Include="$(SdkReferencesPath)\Contoso.RetailServer.SalesTransactionSignatureSample.dll" />
        <ISV_RetailServer_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesTransactionSignatureSample.dll" />
        <ISV_RetailServer_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesTransactionSignatureSample.dll.config" />
        ```

        # <a name="application-update-5-and-later"></a>[Aggiornamento applicazione 5 e successivi](#tab/app-update-5-and-later)

        ``` xml
        <ISV_RetailServer_CustomizableFile Include="$(SdkReferencesPath)\Contoso.RetailServer.SalesTransactionSignatureSample.dll" />
        <ISV_RetailServer_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesTransactionSignatureSample.Messages.dll" />
        ```

        # <a name="retail-731"></a>[Retail 7.3.1](#tab/retail-7-3-1)

        ``` xml
        <ISV_RetailServer_CustomizableFile Include="$(SdkReferencesPath)\Contoso.RetailServer.SalesTransactionSignatureSample.dll" />
        ```

        # <a name="retail-732-and-later"></a>[Retail 7.3.2 e versioni successive](#tab/retail-7-3-2)

        ``` xml
        <ISV_RetailServer_CustomizableFile Include="$(SdkReferencesPath)\Contoso.RetailServer.SalesTransactionSignatureSample.dll" />
        ```

        # <a name="retail-735-and-later"></a>[Retail 7.3.5 e versioni successive](#tab/retail-7-3-5)

        ``` xml
        <ISV_RetailServer_CustomizableFile Include="$(SdkReferencesPath)\Contoso.RetailServer.SalesTransactionSignatureSample.dll" />
        ```

        # <a name="retail-811-and-later"></a>[Retail 8.1.1 e versioni successive](#tab/retail-8-1-1)

        ``` xml
        <ISV_RetailServer_CustomizableFile Include="$(SdkReferencesPath)\Contoso.RetailServer.SalesTransactionSignatureSample.dll" />
        ```

        ---

4. Modifica i seguenti file per includere i file di risorse per la Norvegia nei pacchetti distribuibili:
    - Packages\_SharedPackagingProjectComponents\Sdk.ModernPos.Shared.csproj
    - Packages\RetailServer\Sdk.RetailServerSetup.proj
  
  - Per il file **Sdk.ModernPos.Shared.csproj** 
    - Aggiungi la riga alla sezione **ItemGroup**
    
        ``` xml
        <<File_name> Include="$(SdkReferencesPath)\nb-NO\*" />
        ```
    > [!Note]
    > Invece di <File_name>, specifica il nome del file di risorse. Lo stesso vale per gli altri esempi forniti di seguito.
 
    - Aggiungi la riga alla sezione **Target Name="CopyPackageFiles"**
       ``` xml
        <Copy SourceFiles="@(<File_name>)" DestinationFolder="$(OutputPath)content.folder\CustomizedFiles\ClientBroker\ext\nb-NO" SkipUnchangedFiles="true" />
        ```
  
  - Per il file **Sdk.RetailServerSetup.proj** 
    - Aggiungi la riga alla sezione **ItemGroup**
        ``` xml
        <<File_name> Include="$(SdkReferencesPath)\nb-NO\*" />
        ```    
    - Aggiungi la riga alla sezione **Target Name="CopyPackageFiles"**
         ``` xml
        <Copy SourceFiles="@(<File_name>)" DestinationFolder="$(OutputPath)content.folder\RetailServer\Code\bin\ext\nb-NO" SkipUnchangedFiles="true" />
        ```    

5. Modifica il file di configurazione del certificato specificando l'identificazione personale, la posizione del negozio e il nome del negozio per il certificato da utilizzare per firmare le transazioni di vendita. Quindi copia il file di configurazione nella cartella **References**.

    # <a name="application-update-4"></a>[Aggiornamento applicazione 4](#tab/app-update-4)

    Il file si chiama **Contoso.Commerce.Runtime.SalesTransactionSignatureSample.dll.config** e si trova in **CommerceRuntime\\Extensions.SalesTransactionSignatureSample\\bin\\Debug**.

    # <a name="application-update-5-and-later"></a>[Aggiornamento applicazione 5 e successivi](#tab/app-update-5-and-later)

    Il file si chiama **Contoso.Commerce.Runtime.SalesTransactionSignatureSample.dll.config** e si trova in **CommerceRuntime\\Extensions.SalesTransactionSignatureSample\\bin\\Debug**.

    # <a name="retail-731"></a>[Retail 7.3.1](#tab/retail-7-3-1)

    Il file si chiama **Contoso.Commerce.Runtime.SalesTransactionSignatureSample.dll.config** e si trova in **CommerceRuntime\\Extensions.SalesTransactionSignatureSample\\bin\\Debug**.

    # <a name="retail-732-and-later"></a>[Retail 7.3.2 e versioni successive](#tab/retail-7-3-2)

    Il file si chiama **Contoso.Commerce.Runtime.SequentialSignatureRegister.dll.config** e si trova in **Extensions.SequentialSignatureRegister\\bin\\Debug**.

    # <a name="retail-735-and-later"></a>[Retail 7.3.5 e versioni successive](#tab/retail-7-3-5)

    Il file si chiama **Contoso.Commerce.Runtime.SequentialSignatureRegister.dll.config** e si trova in **Extensions.SequentialSignatureRegister\\bin\\Debug**.

    # <a name="retail-811-and-later"></a>[Retail 8.1.1 e versioni successive](#tab/retail-8-1-1)

    Il file si chiama **Contoso.Commerce.Runtime.SequentialSignatureRegister.dll.config** e si trova in **Extensions.SequentialSignatureRegister\\bin\\Debug**.

    ---

6. Aggiorna il file di configurazione per Retail Server. Nel file **RetailSDK\\Packages\\RetailServer\\Code\\web.config** aggiungi le seguenti righe alla sezione **extensionComposition**.

    ``` xml
    <add source="assembly" value="Contoso.RetailServer.SalesTransactionSignatureSample" />
    ```

7. Esegui **msbuild** per l'intero Retail SDK per creare i pacchetti distribuibili.
8. Applicare i pacchetti via Microsoft Dynamics Lifecycle Services (LCS) o manualmente. Per ulteriori informazioni, vedere [Creare pacchetti distribuibili](../dev-itpro/retail-sdk/retail-sdk-packaging.md).

### <a name="enable-the-digital-signature-in-offline-mode-for-modern-pos"></a>Abilitare la firma digitale in modalità offline per Modern POS

Per abilitare la firma digitale in modalità offline per Modern POS, devi seguire questi passaggi dopo aver attivato Modern POS su un nuovo dispositivo.

1. Accedere a POS.
2. Nella pagina **Stato della connessione al database** assicurati che il database offline sia completamente sincronizzato. Quando il valore del campo **Download sospesi** è **0** (zero), il database è completamente sincronizzato.
3. Esci da POS.
4. Attendi qualche istante affinché il database offline sia completamente sincronizzato.
5. Accedere a POS.
6. Nella pagina **Stato della connessione al database** assicurati che il database offline sia completamente sincronizzato. Quando il valore del campo **Transazioni in sospeso nel database offline** è **0** (zero), il database è completamente sincronizzato.
7. Riavvia Modern POS.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
