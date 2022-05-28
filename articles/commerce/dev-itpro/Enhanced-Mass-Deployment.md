---
title: Distribuzione di massa dei componenti self-service Commerce sigillati
description: Questo argomento spiega come utilizzare il framework per i programmi di installazione dei componenti self-service per installare e gestire le distribuzioni in modo invisibile all'utente.
author: jashanno
ms.date: 05/11/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: jashanno
ms.search.validFrom: 2021-04-30
ms.openlocfilehash: 5cb27fd0ea366d12c8bd6ee1cdb0c6d584375862
ms.sourcegitcommit: d70f66a98eff0a2836e3033351b482466bd9c290
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2022
ms.locfileid: "8741559"
---
# <a name="mass-deployment-of-sealed-commerce-self-service-components"></a>Distribuzione di massa dei componenti self-service Commerce sigillati

[!include [banner](../includes/banner.md)]

Questo argomento si applica al framework sigillato, ai programmi di installazione dei componenti che vengono rilasciati ogni mese, a partire dalla versione 10.0.18, e che sono resi disponibili nella libreria di risorse condivise in Microsoft Dynamics Lifecycle Services (LCS). Si noti che le prime versioni di questi nuovi programmi di installazione sono designate come **(Anteprima)**. Tuttavia, l'unico scopo di questa designazione è differenziare i nuovi programmi di installazione mentre Microsoft determina se esistono requisiti funzionali aggiuntivi per utilizzarli. Non significa che i programmi di installazione non siano validi per la produzione. Sulla base del rilascio di questi nuovi programmi di installazione, Microsoft prevede di deprecare i vecchi programmi di installazione (legacy) a partire da ottobre 2023. 

Questo argomento spiega come utilizzare i nuovi programmi di installazione per eseguire in modo invisibile all'utente l'installazione e la manutenzione degli aggiornamenti tramite argomenti della riga di comando. Questi argomenti ti consentono di eseguire la distribuzione di massa in diversi modi.

> [!NOTE]
> I nuovi programmi di installazione self-service sigillati non saranno resi disponibili in Headquarters e sono scaricabili solo tramite LCS.

## <a name="delimiters-for-mass-deployment"></a>Delimitatori per la distribuzione di massa

La tabella seguente mostra i delimitatori che possono essere utilizzati nell'esecuzione della riga di comando.


| Delimitatore                 | Description |
|---------------------------|-------------|
| --AadTokenIssuerPrefix | Il prefisso per l'emittente di token di Microsoft Azure Active Directory (Azure AD). |
| --AsyncClientAadClientId | L'ID client Azure AD che Async Client deve utilizzare durante le comunicazioni con Headquarters. |
| --AsyncClientAppInsightsInstrumentationKey | La chiave di strumentazione AppInsights di Async Client. |
| --AsyncClientCertFullPath | Il percorso URN completamente formattato che utilizza l'identificazione personale come metrica di ricerca della posizione del certificato di identità Async Client che deve essere utilizzato per l'autenticazione con Azure AD per le comunicazioni con Headquarters. Ad esempio, `store://My/LocalMachine?FindByThumbprint=<MyThumbprint>` è un URN formattato correttamente. Il valore **\<MyThumbprint\>** verrà sostituito con l'identificazione personale del certificato da utilizzare. Non utilizzare questo parametro insieme al parametro **-AsyncClientCertThumbprint**. |
| --AsyncClientCertThumbprint | L'identificazione personale del certificato di identità Async Client che deve essere utilizzato per l'autenticazione con Azure AD per le comunicazioni con Headquarters. Questa identificazione personale verrà utilizzata per cercare il nome e la posizione **LocalMachine/My store** per trovare il certificato corretto da utilizzare. Non utilizzare questo parametro insieme al parametro **-AsyncClientCertFullPath**. |
| --ClientAppInsightsInstrumentationKey | La chiave di strumentazione AppInsights del client. |
| --CloudPosAppInsightsInstrumentationKey | La chiave di strumentazione AppInsights di Cloud POS. |
| --Config | Il file di configurazione da utilizzare durante l'installazione. Un esempio di nome file è **Contoso.CommerceScaleUnit.xml**. |
| --CposAadClientId | L'ID client Azure AD che Cloud POS deve utilizzare durante l'attivazione del dispositivo. Questo parametro non è necessario per le distribuzioni locali. |
| --Device | L'ID dispositivo, come mostrato nella pagina **Dispositivi** in Headquarters. |
| --EnvironmentId | L'ID ambiente. |
| --HardwareStationAppInsightsInstrumentationKey | La chiave di strumentazione AppInsights della stazione hardware. |
| --Install | Un parametro che specifica se il componente fornito da questo programma di installazione deve essere installato. Questo parametro non è obbligatorio. |
| --InstallOffline | Per POS moderno, questo parametro specifica che anche il database offline deve essere installato e configurato. Usare anche il parametro **-SQLServerName**. In caso contrario, il programma di installazione proverà a trovare un'istanza predefinita che soddisfi i prerequisiti. |
| --Port | La porta che deve essere associata e utilizzata dalla directory virtuale di Retail Server. Se non viene impostata alcuna porta, verrà utilizzata quella predefinita, 443. |
| --Register | L'ID registro, come mostrato nella pagina **Registri** in Headquarters. |
| --RetailServerAadClientId | L'ID client Azure AD che Retail Server deve utilizzare durante le comunicazioni con Headquarters. |
| --RetailServerAadResourceId | L'ID risorsa dell'app Azure AD Retail Server da usare durante l'attivazione del dispositivo. Questo parametro non è necessario per le distribuzioni locali. |
| --RetailServerCertFullPath | Il percorso URN completamente formattato che utilizza l'identificazione personale come metrica di ricerca del certificato di identità Retail Server che deve essere utilizzato per l'autenticazione con Azure AD per le comunicazioni con Headquarters. Ad esempio, `store://My/LocalMachine?FindByThumbprint=<MyThumbprint>` è un URN formattato correttamente in cui il valore **\<MyThumbprint\>** verrà sostituito con l'identificazione personale del certificato da utilizzare. Non utilizzare questo parametro insieme al parametro **-RetailServerCertThumbprint**. |
| --RetailServerCertThumbprint | L'identificazione personale del certificato di identità Retail Server che deve essere utilizzato per l'autenticazione con Azure AD per le comunicazioni con Headquarters. Questa identificazione personale verrà utilizzata per cercare il nome e la posizione **LocalMachine/My store** per trovare il certificato corretto da utilizzare. Non utilizzare questo parametro insieme al parametro **-RetailServerCertFullPath**. |
| --RetailServerURL | L'URL di Retail Server che il programma di installazione deve utilizzare. (Questo URL è anche noto come URL Commerce Scale Unit \[CSU\].) Per POS moderno, questo valore verrà utilizzato durante l'attivazione del dispositivo. |
| --SkipAadCredentialsCheck| Un'opzione che indica se le verifiche dei prerequisiti delle credenziali Azure AD devono essere ignorate. Il valore predefinito è **false**. |
| --SkipCertCheck | Un'opzione che indica se le verifiche dei prerequisiti dei certificati devono essere ignorate. Il valore predefinito è **false**. |
| --SkipIisCheck | Un'opzione che indica se le verifiche dei prerequisiti di Internet Information Services (IIS) devono essere ignorate. Il valore predefinito è **false**. |
| --SkipNetFrameworkCheck | Un'opzione che indica se le verifiche dei prerequisiti di .NET Framework devono essere ignorate. Il valore predefinito è **false**. |
| --SkipScaleUnitHealthcheck | Un'opzione che indica se il controllo dello stato sui componenti installati deve essere ignorato. Il valore predefinito è **false**. |
| --SkipSChannelCheck | Un'opzione che indica se le verifiche dei prerequisiti dei canali sicuri devono essere ignorate. Il valore predefinito è **false**. |
| --SkipSqlFullTextCheck | Un'opzione che indica se la convalida del prerequisito di SQL Server che richiede la ricerca full-text deve essere ignorata. Il valore predefinito è **false**. |
| --SkipSqlServerCheck | Un'opzione che indica se le verifiche dei prerequisiti di SQL Server devono essere ignorate. Il valore predefinito è **false**. |
| --SqlServerName | Il nome dell'istanza SQL Server. Se il nome non è specificato, il programma di installazione proverà a trovare l'istanza predefinita. |
| --SslcertFullPath | Il percorso URN completamente formattato che utilizza l'identificazione personale come metrica di ricerca della posizione del certificato da utilizzare per crittografare il traffico HTTP verso l'unità di scala. Ad esempio, `store:\/\/My\/LocalMachine\?FindByThumbprint\=\<MyThumbprint\>` è un URN formattato correttamente in cui il valore **\<MyThumbprint\>** verrà sostituito con l'identificazione personale del certificato da utilizzare. Non utilizzare questo parametro insieme al parametro **-SslCertThumbprint**. |
| --SslCertThumbprint | L'identificazione personale del certificato da utilizzare per crittografare il traffico HTTP verso l'unità di scala. Questa identificazione personale verrà utilizzata per cercare il nome e la posizione **LocalMachine/My store** per trovare il certificato corretto da utilizzare. Non utilizzare questo parametro insieme al parametro **-SslCertFullPath**. |
| --StoreSystemAosUrl | L'URL di Headquarters (AOS). |
| --StoreSystemChannelDatabaseId | L'ID database canale (nome). |
| --TenantId | L'ID tenant Azure AD. |
| --TransactionServiceAzureAuthority | L'autorità Azure AD di Transaction Service. |
| --TransactionServiceAzureResource | La risorsa Azure AD di Transaction Service. |
| --TrustSqlServerCertificate | Un'opzione che indica se il certificato del server deve essere considerato attendibile mentre viene stabilita una connessione a SQL Server. Per evitare rischi per la sicurezza, le distribuzioni di produzione non dovrebbero mai fornire un valore **true** qui. Il valore predefinito è **false**. |
| --Verbosity | Il livello di registrazione richiesto durante l'installazione. In genere, questo valore non deve essere usato. |
| --WindowsPhoneAppInsightsInstrumentationKey | La chiave di strumentazione AppInsights della stazione hardware. |

## <a name="general-overview"></a>Panoramica generale

Il nuovo framework per i programmi di installazione self-service presenta varie funzionalità e miglioramenti. Il nuovo framework attualmente genera programmi di installazione solo per POS moderno, stazione hardware e CSU (indipendente). È importante comprendere l'utilizzo di base della riga di comando dei programmi di installazione sigillati, che dovrebbe essere simile a quella utilizzata nell'esempio seguente. 
 
```Console
<Component Installer Name>.exe install --<Parameter Name> "<Parameter Information>"
```

Il programma di installazione richiede il parametro **install** (o **uninstall** per rimuovere l'installazione) e tutti i parametri specifici di tale installazione. **Nome parametro** dovrebbe includere tutti i parametri necessari come registro, URL CSU o informazioni sul certificato. **Informazioni sui parametri** dovrebbe includere qualsiasi informazione aggiuntiva sui parametri.

Il framework sigillato è stato creato per consentire le seguenti alterazioni:
- **Sigillato**: il nuovo framework dei programmi di installazione separa completamente i programmi di installazione dei componenti di base distribuiti da Microsoft dalle personalizzazioni basate sull'estendibilità. Le personalizzazioni verranno installate successivamente, ma saranno scollegate per quanto riguarda gli aggiornamenti (in modo che gli aggiornamenti saranno consentiti solo per il componente di base Microsoft, solo per le personalizzazioni o per entrambi).
- **Senza interfaccia utente grafica**: non è più presente un'interfaccia utente. È invece presente un eseguibile interamente guidato dalla riga di comando per ogni programma di installazione dei componenti. Questa modifica è una delle numerose modifiche o funzionalità chiave utilizzate per consentire l'uso del nuovo framework dei programmi di installazione con la distribuzione di massa.
- **Registrazione più approfondita**: i registri dei programmi di installazione avanzati consentono una migliore convalida del completamento o dell'errore dell'installazione, dei passaggi eseguiti e di eventuali avvisi o errori generati.
- **Pulitura**: nel nuovo framework, i programmi di installazione dei componenti lavorano di più per mantenere la pulizia delle directory di installazione, cancellando l'intero contenuto della cartella dei componenti prima di installare i componenti più recenti. Questa pulitura garantisce che non vi siano file residui che potrebbero causare problemi e impedire una corretta installazione.

Tre componenti non sono stati migrati nel nuovo framework: Virtual Peripheral Simulator, Async Server Connector Service (usato per il supporto di Dynamics AX 2012 R3) e Real-time Service Replacement (usato per il supporto di Dynamics AX 2012 R3).

> [!NOTE]
> I programmi di installazione vengono archiviati localmente e conservati.  Nel tempo, è importante gestire o eliminare i programmi di installazione conservati per non sprecare spazio su disco. Si consiglia di conservare il programma di installazione corrente per i componenti di base ed eventuali programmi di installazione di estensioni per le ultime versioni ai fini del ripristino da situazioni estreme.

## <a name="migration"></a>Migrazione

La migrazione dai programmi di installazione dei componenti del vecchio framework self-service ai programmi di installazione dei componenti del nuovo framework richiede la disinstallazione dei vecchi componenti.

- **POS moderno**: con il nuovo framework dei programmi di installazione l'applicazione ha ricevuto un nuovo ID firma dell'applicazione. Pertanto, è necessario disinstallare completamente i vecchi componenti prima di installare il componente POS moderno del nuovo framework. A causa del requisito per la disinstallazione completa, sarà nuovamente richiesta l'attivazione del dispositivo. (Questa riattivazione del dispositivo è un requisito una tantum, a condizione che la disinstallazione non si ripeta.)
- **Stazione hardware**: in quanto sito Web IIS, il nuovo framework dei programmi di installazione richiede che la struttura delle cartelle di base venga rielaborata. Pertanto, è necessario disinstallare completamente i vecchi componenti prima di installare il componente della stazione hardware del nuovo framework.
- **Commerce Scale Unit (CSU, indipendente)**: in quanto serie di siti Web IIS, il nuovo framework dei programmi di installazione richiede che la struttura delle cartelle di base venga rielaborata.  Pertanto, è necessario disinstallare completamente i vecchi componenti prima di installare il componente CSU (indipendente) del nuovo framework.

## <a name="modern-pos"></a>POS moderno

### <a name="before-you-begin"></a>Prima di iniziare

È fondamentale rimuovere il vecchio componente POS moderno self-service. Per ulteriori informazioni, vedere i passaggi per la migrazione descritti precedentemente in questo argomento.

### <a name="examples-of-silent-deployment"></a>Esempi di distribuzione invisibile all'utente

Questa sezione mostra esempi di comandi utilizzati per installare POS moderno.

#### <a name="silently-install-modern-pos"></a>Installare POS moderno in modo invisibile all'utente

Il comando seguente installa (o aggiorna) POS moderno in modo invisibile all'utente. Ha la struttura dei comandi standard utilizzata per la manutenzione invisibile all'utente dei componenti attualmente installati. La struttura utilizza i valori di base di **&lt;InstallerName&gt;.exe**.

Il seguente comando di base mostra le opzioni disponibili se è richiesta un'installazione. Si consiglia vivamente di utilizzare questo comando durante il primo test o l'utilizzo del programma di installazione.

```Console
CommerceModernPOS.exe --help install
```

> [!NOTE]
> Non è richiesto un file di configurazione per POS moderno. Il programma di installazione dispone ora di parametri (illustrati in precedenza in questo argomento) per i vari valori utilizzati durante l'attivazione del dispositivo.

Il comando seguente specifica tutti i parametri da utilizzare durante l'attivazione del dispositivo dopo l'installazione dell'applicazione POS moderno. Questo esempio usa il registro **Houston-3**, che è un valore comunemente usato nei dati dimostrativi di Dynamics 365 Commerce.

```Console
CommerceModernPOS.exe install --Register "Houston-3" --Device "Houston-3" --RetailServerURL "https://MyDynamics365CommerceURL.dynamics.com/Commerce"
```

Il comando seguente specifica i parametri da utilizzare per installare e configurare il database offline. SQL Server viene specificato insieme al file di configurazione da utilizzare.

```Console
CommerceModernPOS.exe install --InstallOffline --SQLServerName "SQLExpress" --Config "ModernPOS.Houston-3.xml"
```

È possibile combinare questi concetti per ottenere i risultati di installazione desiderati.

## <a name="hardware-station"></a>Stazione hardware

### <a name="before-you-begin"></a>Prima di iniziare

È fondamentale rimuovere il vecchio componente della stazione hardware self-service. Per ulteriori informazioni, vedere i passaggi per la migrazione descritti precedentemente in questo argomento. Non è più disponibile uno strumento di informazioni sul conto esercente. Le informazioni sul conto esercente vengono invece installate quando un terminale POS è associato alla stazione hardware. Quando si esegue il test di questo programma di installazione per la prima volta, si consiglia vivamente di eseguire il comando seguente:

```Console
CommerceHardwareStation.exe --help install
```

### <a name="examples-of-silent-deployment"></a>Esempi di distribuzione invisibile all'utente

Questa sezione mostra esempi di comandi utilizzati per installare la stazione hardware.

#### <a name="silently-install-hardware-station"></a>Installare la stazione hardware in modo invisibile all'utente

Il comando seguente installa (o aggiorna) la stazione hardware in modo invisibile all'utente. Ha la struttura dei comandi standard utilizzata per la manutenzione dei componenti attualmente installati. La struttura utilizza i valori di base di **&lt;InstallerName&gt;.exe**.

Il seguente comando di base esegue il programma di installazione del file eseguibile.

```Console
HardwareStation.exe install --Port 443 --StoreSystemAOSURL "https://MyDynamics365CommerceURL.dynamics.com/" --StoreSystemChannelDatabaseID "Houston" --SSLCertThumbprint "MySSLCertificateThumbprintOftenHasNumbers"
```

> [!NOTE]
> Non è richiesto un file di configurazione per la stazione hardware. Il programma di installazione dispone ora di parametri (illustrati in precedenza in questo argomento) per i vari valori richiesti.

Il comando seguente specifica tutti i parametri necessari per ignorare le verifiche dei prerequisiti durante un'installazione standard. 

> [!NOTE]
> Non è consigliabile ignorare le verifiche senza un test preliminare completo o in situazioni di sviluppo.

```Console
HardwareStation.exe install --SkipFirewallUpdate --SkipOPOSCheck --SkipVersionCheck --SkipURLCheck --Config "HardwareStation.Houston.xml"
```

Come da prassi, è comune combinare questi concetti per ottenere i risultati di installazione desiderati.

## <a name="commerce-scale-unit-self-hosted"></a>Commerce Scale Unit (indipendente)

Quando si esegue il test di questo programma di installazione per la prima volta, si consiglia vivamente di eseguire il comando seguente:

```Console
CommerceStoreScaleUnitSetup.exe --help install
```

### <a name="before-you-begin"></a>Prima di iniziare

È fondamentale rimuovere il vecchio componente CSU (indipendente) self-service. Per ulteriori informazioni, vedere i passaggi per la migrazione descritti precedentemente in questo argomento.

### <a name="examples-of-silent-deployment"></a>Esempi di distribuzione invisibile all'utente

Questa sezione mostra esempi di comandi utilizzati per installare CSU (indipendente).

#### <a name="silently-install-csu-self-hosted"></a>Installare CSU (indipendente) in modo invisibile all'utente

Il comando seguente installa (o aggiorna) CSU (indipendente) in modo invisibile all'utente. Ha la struttura dei comandi standard utilizzata per la manutenzione invisibile all'utente dei componenti attualmente installati. La struttura utilizza i valori di base di **&lt;InstallerName&gt;.exe**.

Rispetto agli altri programmi di installazione self-service, Commerce Scale Unit (CSU) è più complesso e richiede una quantità notevole di informazioni aggiuntive. Il comando seguente è il comando minimo (con parametri) necessario per eseguire il programma di installazione del file eseguibile quando non è presente alcun file di configurazione.

```Console
CommerceScaleUnit.exe install --port 446 --SSLCertThumbprint "MySSLCertificateThumbprintOftenHasNumbers" --RetailServerCertFullPath "store://My/LocalMachine?FindByThumbprint=MyCertificateThumbprintUsedByRetailServer" --AsyncClientAADClientID "MyAAD-Client-IDFor-AsyncClient" --RetailServerAADClientID "MyAAD-Client-IDFor-RetailServer" --CPOSAADClientID "MyAAD-Client-IDFor-CloudPOS" --RetailServerAADResourceID "https://retailstorescaleunit.retailserver.com" --TrustSqlServerCertificate --Config "Contoso.StoreSystemSetup.xml"
```

> [!NOTE]
> È necessario un file di configurazione per CSU (indipendente).

Il comando seguente è un comando più completo che esegue il programma di installazione del file eseguibile con alcuni parametri alternativi.

```Console
CommerceScaleUnit.exe install --Port 446 --SSLCertFullPath "store://My/LocalMachine?FindByThumbprint=MySSLCertificateThumbprintOftenHasNumbers" --AsyncClientCertFullPath "store://My/LocalMachine?FindByThumbprint=MySSLCertificateThumbprintOftenHasNumbers" --RetailServerCertFullPath "store://My/LocalMachine?FindByThumbprint=MyCertificateThumbprintUsedByRetailServer" --AsyncClientAADClientID "MyAAD-Client-IDFor-AsyncClient" --RetailServerAADClientID "MyAAD-Client-IDFor-RetailServer" --CPOSAADClientID "MyAAD-Client-IDFor-CloudPOS" --RetailServerAADResourceID "https://retailstorescaleunit.retailserver.com" --TrustSqlServerCertificate --Verbosity 0 --Config "Contoso.StoreSystemSetup.xml"
```

Il comando seguente specifica i parametri necessari per ignorare le verifiche dei prerequisiti durante un'installazione standard. 

> [!NOTE]
> Non è consigliabile ignorare le verifiche senza un test preliminare completo o in situazioni di sviluppo.


```Console
CommerceScaleUnit.exe installer --skipscaleunithealthcheck --skipcertcheck --skipaadcredentialscheck --skipschannelcheck --skipiischeck --skipnetcorebundlecheck --skipsqlservercheck --skipnetframeworkcheck --skipversioncheck --skipurlcheck --Config "Contoso.StoreSystemSetup.xml" --SSLCertFullPath "store://My/LocalMachine?FindByThumbprint=MySSLCertificateThumbprintOftenHasNumbers" --AsyncClientCertFullPath "store://My/LocalMachine?FindByThumbprint=MySSLCertificateThumbprintOftenHasNumbers" --RetailServerCertFullPath "store://My/LocalMachine?FindByThumbprint=MyCertificateThumbprintUsedByRetailServer" --AsyncClientAADClientID "MyAAD-Client-IDFor-AsyncClient" --RetailServerAADClientID "MyAAD-Client-IDFor-RetailServer" --CPOSAADClientID "MyAAD-Client-IDFor-CloudPOS" --RetailServerAADResourceID "https://retailstorescaleunit.retailserver.com" --TrustSqlServerCertificate
```

È possibile combinare questi concetti per ottenere i risultati di installazione desiderati.

<!--## Mass deployment examples using InTune

This section will be added in a future update.

## Mass deployment examples using System Center Configuration Manager (SCCM)

This section will be added in a future update.-->

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
