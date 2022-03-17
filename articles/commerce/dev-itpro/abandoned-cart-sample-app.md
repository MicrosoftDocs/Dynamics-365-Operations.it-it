---
title: Rilevare i carrelli abbandonati e inviare notifiche ai clienti
description: Questo argomento descrive come personalizzare l'app di esempio del connettore per i carrelli abbandonati di Microsoft Dynamics 365 Commerce per rilevare i carrelli abbandonati e inviare notifiche e-mail di promemoria ai clienti.
author: bicyclingfool
ms.date: 02/25/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: stuharg
ms.search.validFrom: 2017-06-20
ms.openlocfilehash: 82848f1ff068cea0adfc6ec1b33fc4bb035f78dc
ms.sourcegitcommit: 374bbdde90fc9a68c0799158a50409bfbe8ca64e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/25/2022
ms.locfileid: "8353362"
---
# <a name="detect-abandoned-carts-and-send-notifications-to-customers"></a>Rilevare i carrelli abbandonati e inviare notifiche ai clienti

[!include [banner](../includes/banner.md)]

Questo argomento descrive come personalizzare l'app di esempio del connettore per i carrelli abbandonati di Microsoft Dynamics 365 Commerce per rilevare i carrelli abbandonati e inviare notifiche e-mail di promemoria ai clienti.

La possibilità di recuperare i ricavi entrate e fidelizzare i clienti attraverso le notifiche del carrello abbandonato è una funzionalità importante che Dynamics 365 Commerce supporta. Personalizzando l'app di esempio del connettore del carrello abbandonato di Commerce, i rivenditori possono accedere ai carrelli degli acquisti su Retail Server che non sono stati modificati durante un intervallo di tempo definito dai rivenditori. Tali carrelli possono quindi essere recuperati, ampliati con dati sui prodotti e sui clienti e trasmessi a un provider di e-mail marketing di terze parti in grado di generare notifiche e-mail e inviare loro clienti.

La notifica e-mail del carrello abbandonato che i clienti ricevono può contenere le seguenti informazioni:

- Nome del cliente.
- Cognome del cliente.
- Indirizzo e-mail del cliente.
- Un URL che riporta il cliente al carrello.
- Valuta della transazione.
- Un elenco di prodotti nel carrello del cliente. Per ogni prodotto sono incluse le seguenti informazioni:

    - Nome visualizzato del prodotto
    - L'ID prodotto (utilizzato per assemblare un URL alla pagina di descrizione del prodotto)
    - Un'immagine del prodotto che può essere ridimensionata automaticamente per adattarsi a dimensioni diverse del viewport
    - Testo alternativo per l'immagine del prodotto
    - Il prezzo unitario del prodotto

## <a name="abandoned-cart-connector-sample"></a>Esempio di connettore del carrello abbandonato

Un modello di connettore fornito da Microsoft tramite il kit di sviluppo software (SDK) per la vendita al dettaglio consente di recuperare e inviare le informazioni sul carrello abbandonato a un provider di marketing tramite posta elettronica di terze parti. Questo connettore gestisce la comunicazione con Retail Server, usa Azure Key Vault per la sicurezza, gestisce la pianificazione del recupero del carrello per un intervallo di tempo specificato e recupera i dati dell'ordine e del prodotto. Fornisce inoltre un'implementazione di esempio per un'integrazione con un provider di e-mail marketing di terze parti. Il connettore è costruito per comunicare con [Emarsy](https://emarsys.com) i modo predefinito. Tuttavia, può essere facilmente personalizzato per integrarsi con altre soluzioni, come Constant Contact, Mailchimp e SendGrid.

L'illustrazione seguente mostra i componenti dell'app di esempio del connettore del carrello abbandonato.

![Componenti dell'app di esempio del connettore del carrello abbandonato](media/AbandonedCartConnector.png)

> [!IMPORTANT]
> Alcune aree geografiche richiedono che i clienti possano rifiutare esplicitamente la trasmissione dei dati del carrello a un provider di e-mail marketing o richiedere la rimozione dei loro dati. Tuttavia, Microsoft non fornisce queste opzioni ai clienti. Pertanto, se prevedi di fare affari in aree geografiche che lo richiedono, devi fornire l'infrastruttura e le personalizzazioni necessarie per tenere traccia delle preferenze dei clienti e, sulla base di esse, impedire che i dati dei clienti vengano trasmessi alla tua piattaforma di posta elettronica. È inoltre necessario definire un processo per eliminare i dati dei clienti dal provider di e-mail marketing su richiesta del cliente.

## <a name="obtain-the-code-sample"></a>Ottenere il codice di esempio

L'app di esempio del connettore del carrello abbandonato è inclusa nell'SDK di Retail a partire dalla versione 10.0.16. IL codice si trova in **\\RetailSDK\\Code\\SampleExtensions\\RetailServer\\Extensions.AbandonedCartSample**. Per altre informazioni su Retail SDK e dove ottenere, vedi [Architettura di Retail SDK](retail-sdk/retail-sdk-overview.md).

> [!NOTE]
> Sebbene il codice di esempio sia stato reso disponibile per la prima volta nelle build della versione 10.0.16, è compatibile con la versione 10.0.13 e le build successive di Retail Server.

## <a name="prerequisites-and-dependencies"></a>Prerequisiti e dipendenze

Prima di poter distribuire e configurare il codice di esempio del connettore del carrello abbandonato, è necessario soddisfare i seguenti prerequisiti.

### <a name="access-to-commerce-resources"></a>Accesso alle risorse di Commerce

Per configurare e distribuire l'app del connettore del carrello abbandonato, devi avere accesso alle seguenti risorse Commerce:

- Accesso come amministratore a Commerce Headquarters per il tuo ambiente
- Accesso al progetto Microsoft Dynamics Lifecycle Services (LCS) per il tuo ambiente

### <a name="azure-cosmos-db"></a>Azure Cosmos DB

L'app del connettore del carrello abbandonato usa Azure Cosmos DB per tener traccia degli ID e dei timestamp dei carrelli che sono stati precedentemente recuperati. Puoi usare Azure Cosmos DB per rendere persistenti questi dati oppure puoi personalizzare l'esempio di codice per integrarlo con un'altra opzione di archiviazione dati. Per ulteriori informazioni su Azure Cosmos DB, vedi [Benvenuto in Azure Cosmos DB](/azure/cosmos-db/introduction).

S utilizzi Azure Cosmos DB, è necessario soddisfare i seguenti prerequisiti prima di eseguire l'esempio:

- Devi avere un account Azure Cosmos DB attivo. Se non hai un account, vedi [Creare un account di database](/azure/cosmos-db/create-sql-api-dotnet#create-a-database-account).
- Devi recuperare i valori **URI** e **CHIAVE PRIMARIA** (o **CHIAVE SECONDARIA**) dal pannello **Chiavi** del tuo account Azure Cosmos DB nel portale di Azure. Per ulteriori informazioni su come recuperare l'endpoint e le informazioni chiave per l'account Azure Cosmos DB, vedi [Visualizzare, copiare e rigenerare chiavi di accesso e password](/azure/cosmos-db/manage-account#keys).

### <a name="azure-key-vault"></a>Azure Key Vault

L'app del connettore del carrello abbandonato utilizza Key Vault per archiviare i nomi e i segreti dei diversi componenti che richiedono un accesso sicuro.

Per impostare un key vault, effettua le seguenti operazioni.

1. Segui le istruzioni in [Gestire Key Vault nell'hub Azure Stack usando il portale](/azure-stack/user/azure-stack-key-vault-manage-portal?view=azs-2002&preserve-view=true).
2. Crea segreti per le seguenti informazioni:

    - Nome utente dell'API (Application Programming Interface) Emarsys e segreto API
    - ID e segreto dell'applicazione del carrello abbandonati

Il codice di esempio del connettore del carrello abbandonato usa le credenziali predefinite di Azure per accedere a Key Vault. Devi fornire le autorizzazioni **Elenco** e **Lettura** per l'identità che prevedi di utilizzare per accedere a Key Vault.

Per ulteriori informazioni sulle credenziali predefinite di Azure, vedi [Classe DefaultAzureCredential](/dotnet/api/azure.identity.defaultazurecredential?view=azure-dotnet&preserve-view=true).

## <a name="create-an-abandoned-cart-connector-sample-app-application-id-for-the-azure-ad-tenant"></a>Creare un ID applicazione dell'app di esempio del connettore del carrello abbandonato per il tenant Azure AD

Devi creare un ID applicazione dell'app di esempio del connettore del carrello abbandonato per il tenant Azure Active Directory. Per informazioni su come creare un ID applicazione, vedi [Usare il portale per creare un'applicazione ed entità servizio Azure AD in grado di accedere alle risorse](/azure/active-directory/develop/howto-create-service-principal-portal).

## <a name="add-the-abandoned-cart-connector-sample-app-application-id-to-the-allow-list-for-the-retail-server-api"></a>Aggiungere l'ID applicazione dell'app di esempio del connettore del carrello abbandonato all'elenco di elementi consentiti per l'API Retail Server

Successivamente, devi aggiungere l'ID applicazione dell'app di esempio del connettore del carrello abbandonato all'elenco di elementi consentiti per l'API Retail Server. Per informazioni su come aggiungere un ID applicazione all'elenco degli elementi consentiti in Azure, vedi [Supporto per l'autenticazione da servizio a servizio in Retail Server](https://community.dynamics.com/ax/b/axforretail/posts/support-for-service-to-service-authentication-in-retail-server).

## <a name="configure-the-abandoned-cart-connector-sample-app"></a>Configurare l'app di esempio del connettore del carrello abbandonato

Per configurare l'app di esempio del connettore del carrello abbandonato, modifica il file di configurazione **appSettings.json** che si trova nella radice della directory **AbandonedCartDetectionSample**. Le tabelle seguenti descrivono le proprietà del file di configurazione.

### <a name="keyvaultoptions"></a>KeyVaultOptions

| Proprietà    | Description |
| ----------- | ----------- |
| KeyVaultURI | Il nome DNS (Domain Name System) del Key Vault in uso nel portale di Azure. |

### <a name="retailserverclientoptions"></a>RetailServerClientOptions

| Proprietà                                      | Description |
| --------------------------------------------- | ----------- |
| TenantId                                      | ID tenant Azure AD del tuo tenant di Azure. |
| RetailServerAudienceId                        | ID gruppo di destinatari di Retail Server. Puoi lasciare il valore predefinito. |
| AppIdKeyVaultSecretName                       | Il nome del segreto che hai creato per l'ID applicazione dell'app di esempio del connettore del carrello abbandonato. |
| AppSecretKeyVaultSecretName                   | Il nome del segreto che archivia il segreto dell'app per l'ID applicazione dell'app di esempio del connettore del carrello abbandonato. |
| RetailServerUrl                               | L'URL della tua istanza di Retail Server. Puoi trovare questo valore in LCS. |
| OperatingUnitNumber                           | Numero dell'unità operativa. Puoi trovare questo valore in Commerce headquarters. |
| IncludeAbandonedCartsModifiedSinceLastMinutes | L'inizio della finestra temporale per i carrelli abbandonati che desideri recuperare. Il valore è espresso come numero di minuti prima dell'ora corrente. Ad esempio, imposta questa proprietà su **120** per recuperare tutti i carrelli che sono stati modificati per l'ultima volta tra 120 minuti fa e la fine della finestra temporale definita dalla proprietà **ExcludeAbandonedCartsModifiedSinceLastMinutes**. |
| ExcludeAbandonedCartsModifiedSinceLastMinutes | La fine della finestra temporale per i carrelli abbandonati che desideri recuperare. Il valore è espresso come numero di minuti prima dell'ora corrente. Ad esempio, se la proprietà **IncludeAbandonedCartsModifiedSinceLastMinutes** è impostata su **120**, imposta questa proprietà su **30** per recuperare tutti i carrelli che sono stati modificati tra 120 minuti fa e 30 minuti fa. In pratica, questa proprietà definisce il tempo che si desidera attendere prima che un carrello venga dichiarato abbandonato. |
| ReturnToCartUrl                               | L'URL del carrello sul tuo sito e-commerce, nel formato utilizzato nel file **app.config**. |

### <a name="azurecosmosoptions"></a>AzureCosmosOptions

Lo stato del processo di recupero del carrello abbandonato, gli ID carrello e i timestamp modificati vengono archiviati in Azure Cosmos DB. Per impostazione predefinita, le impostazioni nel file di configurazione puntano all'istanza dell'emulatore locale di Azure Cosmos DB. Quando distribuisci il connettore in produzione, è necessario aggiornare queste impostazioni in modo che puntino all'istanza di Azure Cosmos DB nella sottoscrizione di Azure. Per i test locali o sandbox, puoi utilizzare l'[emulatore di Azure Cosmos](/azure/cosmos-db/local-emulator).

| Proprietà    | Description |
| ----------- | ----------- |
| EndPointUri | L'URI dell'endpoint fornito da Azure o dall'emulatore. |
| PrimaryKey  | La chiave primaria fornita da Azure o dall'emulatore. |
| DatabaseId  | ID del database. Puoi lasciare il valore predefinito o fornirne uno tuo. |
| ContainerId | ID contenitore. Puoi lasciare il valore predefinito o fornirne uno tuo. |

### <a name="emarsysclientoptions"></a>EmarsysClientOptions

> [!NOTE]
> Se ti stai integrando con un provider di email marketing diverso da Emarsys, devi estendere l'interfaccia **IEmailProvider** per comunicare con quel provider.

| Proprietà                      | Description |
| ----------------------------- | ----------- |
| ApiUrl                        | `https://api.emarsys.net/api/v2/event/{0}/trigger` |
| ExternalEventId               | ID del record dell'evento esterno creato in Emarsys. Puoi trovare il valore in **Impostazioni di attivazione** nella campagna che hai creato per inviare notifiche e-mail di carrello abbandonato. |
| ApiUserNameKeyVaultSecretName | Il nome della chiave in cui è archiviato il nome utente dell'API Emarsys. |
| ApiSecretKeyVaultSecretName   | Il nome della chiave in cui è archiviato il segreto dell'API Emarsys. |
| EmarsysContactKeyId           | L'ID della colonna e-mail nel database dei contatti Emarsys. Il valore predefinito è **3** e non dovrebbe essere cambiato. |

### <a name="mediaoptions"></a>MediaOptions

Se stai utilizzando le funzionalità di e-commerce in Commerce, puoi utilizzare la gestione delle risorse digitali di Commerce per recuperare le immagini dei prodotti. Per ulteriori informazioni sulle funzionalità di ridimensionamento delle immagini nella gestione delle risorse digitali, vedi [Configurazione del viewport di ImageSettings](../e-commerce-extensibility/image-component.md#imagesettings-viewport-configuration).

| Proprietà                             | Description |
| ------------------------------------ | ----------- |
| ImageServerUrl                       | L'URL radice del gestore di risorse digitali del tuo sito. Puoi trovare il valore nella chiave della proprietà **URL di base server multimediale** su **Vendita al dettaglio e commercio \> Configurazione del canale \> Profili di canale** in Commerce Headquarters. |
| ImageViewPorts                       | Il nodo contenitore per le singole configurazioni del viewport. |
| ImageViewPorts/viewport              | La definizione del viewport. Utilizza questa proprietà per specificare gli intervalli di larghezza per la finestra, in pixel. Per un esempio che mostra come viene utilizzata questa proprietà, vedi il file di configurazione **appSettings.json**. |
| ImageViewPorts/imageWidth            | La larghezza dell'immagine del viewport, in pixel. |
| imageViewPorts/imageHeight           | L'altezza dell'immagine del viewport, in pixel. |
| imageViewPorts/useForDefaultImageTag | Un valore **vero**/**falso** che indica se le dimensioni dell'immagine definite dal viewport devono essere utilizzate se il tag HTML `<picture>` non è supportato per un Web browser o un client di posta elettronica. |

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
