---
title: Domini in Dynamics 365 Commerce
description: In questo articolo viene descritto come vengono gestiti i domini in Microsoft Dynamics 365 Commerce.
author: BrianShook
ms.date: 11/08/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: BrShoo
ms.search.validFrom: 2017-06-20
ms.openlocfilehash: f1a2de7984aad7d291b8a4dc68f5690d57ebe6cc
ms.sourcegitcommit: 2b654e60e2553a5835ab5790db4ccfa58828fae7
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2022
ms.locfileid: "9750682"
---
# <a name="domains-in-dynamics-365-commerce"></a>Domini in Dynamics 365 Commerce

[!include [banner](includes/banner.md)]

In questo articolo viene descritto come vengono gestiti i domini in Microsoft Dynamics 365 Commerce.

I domini sono indirizzi Web utilizzati per accedere ai siti Dynamics 365 Commerce in un browser Web. È possibile controllare la gestione del dominio con un provider DNS (Domain Name Server) scelto. Si fa riferimento ai domini ovunque tramite la Creazione di siti Web di Dynamics 365 Commerce per coordinare le modalità di accesso a un sito una volta pubblicato. Questo articolo esamina il modo in cui i domini vengono gestiti e referenziati durante tutto il ciclo di vita dello sviluppo e del lancio del sito di Commerce.

> [!NOTE]
> A partire dal 6 maggio 2022, per tutti gli ambienti creati in Dynamics 365 Commerce verrà eseguito il provisioning del dominio `.dynamics365commerce.ms`, sostituendo il modello precedente di `.commerce.dynamics.com`. Gli ambienti esistenti per cui è stato eseguito il provisioning del dominio `.commerce.dynamics.com` continueranno a funzionare.

## <a name="provisioning-and-supported-host-names"></a>Provisioning e nomi host supportati

Durante il provisioning di un ambiente di e-commerce in [Microsoft Dynamics Lifecycle Services (LCS)](https://lcs.dynamics.com/), la casella **Nomi host supportati** nella schermata di provisioning di e-commerce viene utilizzata per inserire i domini che verranno associati all'ambiente Commerce distribuito. Questi domini saranno i nomi DNS (Domain Name Server) per il cliente in cui saranno ospitati i siti Web di e-commerce. L'inserimento di un dominio in questa fase non avvia la deviazione del traffico per il dominio a Dynamics 365 Commerce. Il traffico per un dominio verrà instradato all'endpoint di Commerce solo quando il record DNS CNAME viene aggiornato per utilizzare l'endpoint di Commerce con il dominio.

> [!NOTE]
> È possibile inserire più domini nella casella **Nomi host supportati** separandoli con un punto e virgola.

La seguente illustrazione mostra la schermata di provisioning di e-commerce LCS con la casella **Nomi host supportati** evidenziata. 

![Schermata di provisioning di e-commerce LCS con la casella **Nomi host supportati** evidenziata.](./media/Domains_ProvisioningeCommerceScreen_publish.png)

È possibile creare una richiesta di assistenza per aggiungere ulteriori domini a un ambiente se il provisioning è già stato eseguito. Per creare una richiesta di assistenza in LCS, all'interno dell'ambiente andare a **Supporto \> Problemi di supporto** e selezionare **Invia un evento imprevisto**.

## <a name="commerce-generated-urls"></a>URL generati da Commerce

Durante il provisioning di un ambiente di e-commerce Dynamics 365 Commerce, Commerce genererà un URL che sarà l'indirizzo di lavoro per l'ambiente. A questo URL si fa riferimento nel collegamento del sito di e-commerce mostrato in LCS dopo il provisioning dell'ambiente. Un URL generato da Commerce è nel formato `https://<e-commerce tenant name>.dynamics365commerce.ms`, dove il nome del tenant di e-commerce è il nome immesso in LCS per l'ambiente Commerce.

È possibile utilizzare i nomi host del sito di produzione anche in un ambiente sandbox. Questa opzione è ideale quando si copia un sito da un ambiente sandbox a quello di produzione.

## <a name="site-setup"></a>Impostazione del sito

Dopo aver eseguito il provisioning dell'ambiente di e-commerce, è necessario configurare il sito in Creazione di siti Web di Commerce per associare il sito all'URL di lavoro.

Quando si imposta per la prima volta un sito in Creazione di siti Web, viene visualizzata la finestra di dialogo **Configurare il sito**.

La figura seguente mostra la finestra di dialogo **Configurare il sito** per un sito denominato "predefinito" quando si accede a Creazione di siti Web per la prima volta.

![Finestra di dialogo **Configurare il sito**.](./media/Domains_SetupyoursiteScreen.png)

La casella **Seleziona un dominio** consente di associare uno dei nomi host supportati forniti per il sito in LCS al sito in Creazione di siti Web.

La casella **Percorso** può essere lasciata vuota oppure è possibile aggiungere una stringa di percorso aggiuntiva che si rifletterà nell'URL di lavoro. Lasciando la casella **Percorso** vuota l'URL di base generato da Commerce viene associato al sito che si sta configurando in Creazione di siti Web. I percorsi devono essere univoci per ogni coppia sito/dominio. All'interno del sito e del dominio selezionati, solo un sito nell'ambiente può utilizzare il percorso vuoto o essere associato a una stringa di percorso univoca. Qualsiasi stringa aggiunta al campo **Percorso** durante la configurazione del sito diventerà un percorso secondario dell'URL di base generato da Commerce utilizzato per accedere al sito in un browser Web.

> [!NOTE]
> Il percorso è anche conosciuto come **Percorso di corrispondenza** quando si aggiunge un canale nella sezione di configurazione **Impostazioni sito \> Canali** di Creazione di siti Web.

Ad esempio, se è disponibile un sito in Creazione di siti Web chiamato "fabrikam" in un tenant di e-commerce denominato "xyz" e se si imposta il sito con un percorso vuoto, si accede al contenuto del sito pubblicato in un browser Web accedendo direttamente all'URL di base generato da Commerce:

`https://xyz.dynamics365commerce.ms`

In alternativa, se si fosse aggiunto un percorso "fabrikam" durante la configurazione di questo stesso sito, si avrebbe accesso al contenuto del sito pubblicato in un browser Web utilizzando il seguente URL:

`https://xyz.dynamics365commerce.ms/fabrikam`

## <a name="pages-and-urls"></a>Pagine e URL

Dopo che il sito è stato impostato con un percorso, tutti gli URL associati alle pagine in Creazione di siti Web si baseranno sull'URL di lavoro (l'URL generato da Commerce o l'URL generato da Commerce più il percorso) per il sito. Creare un nuovo URL in Creazione di siti Web (**URL /> +Nuovo**) selezionando una pagina dall'elenco nella finestra di dialogo **Nuovo URL** e inserendo il percorso dell'URL per quella pagina, assocerà quell'URL alla pagina selezionata. Il valore del percorso dell'URL viene quindi aggiunto all'URL di lavoro del sito per accedere alla pagina e viene etichettato come `./<URL path>` nell'elenco degli URL della pagina **URL** di Creazione di siti Web.

La figura seguente mostra la finestra di dialogo **Nuovo URL** in Creazione di siti Web con un percorso URL di esempio evidenziato. 

![Finestra di dialogo **Nuovo URL** in Creazione di siti Web.](./media/Domains_PageSetup2a.png)

La figura seguente mostra la pagina **URL** in Creazione di siti Web con un URL di esempio evidenziato nell'elenco.

![Eseguire l'opzione flusso utente nel flusso dei criteri.](./media/Domains_URLsInSiteBuilder2a.png)

## <a name="domains-in-site-builder"></a>Domini in Creazione di siti Web

I valori dei nomi host supportati possono essere associati come dominio durante la configurazione di un sito. Quando si seleziona un valore di nome host supportato come dominio, al dominio scelto si fa riferimento in Creazione di siti Web. Questo dominio è solo un riferimento all'interno dell'ambiente Commerce, il traffico in tempo reale per quel dominio non verrà ancora inoltrato a Dynamics 365 Commerce.

Quando si utilizzano i siti in Creazione di siti Web, se sono disponibili due siti configurati con due domini diversi, è possibile aggiungere l'attributo **?domain=** all'URL di lavoro per accedere al contenuto del sito pubblicato in un browser.

Ad esempio, è stato eseguito il provisioning dell'ambiente "xyz" e due siti sono stati creati e associati in Creazione siti Web: uno con il dominio `www.fabrikam.com` e l'altro con il dominio `www.constoso.com`. Ogni sito è stato impostato utilizzando un percorso vuoto. È quindi possibile accedere a questi due siti in un browser Web come segue utilizzando l'attributo **?domain=**:
- `https://xyz.dynamics365commerce.ms?domain=www.fabrikam.com`
- `https://xyz.dynamics365commerce.ms?domain=www.contoso.com`

Quando una stringa di query di dominio non viene fornita in un ambiente con più domini specificati, Commerce utilizza il primo dominio fornito. Ad esempio, se il percorso "fabrikam" è stato fornito per primo durante la configurazione del sito, l'URL `https://xyz.dynamics365commerce.ms` può essere utilizzato per accedere al sito di contenuto del sito pubblicato per `www.fabrikam.com`.

Puoi anche aggiungere domini personalizzati. Per fare ciò, nella pagina di gestione di Commerce dell'ambiente per il progetto, sotto l'intestazione secondaria **e-Commerce**, seleziona **+ Aggiungi dominio personalizzato**. Il dispositivo di scorrimento mostra i domini personalizzati esistenti e offre la possibilità di aggiungere un nuovo dominio personalizzato.

## <a name="update-which-commerce-scale-unit-is-used"></a>Aggiornare quale Commerce Scale Unit viene utilizzata

La Commerce Scale Unit (CSU) utilizzata da Commerce viene in genere selezionata al momento della creazione iniziale di un ambiente. Commerce consente di modificare l'istanza CSU utilizzata dal tuo ambiente, consentendoti di gestire meglio la tua architettura attraverso la funzionalità self-service e riducendo la necessità di contattare l'assistenza. Per aggiornare la tua istanza CSU, vai alla pagina di gestione di Commerce del tuo ambiente per il progetto, quindi seleziona **Aggiorna unità di scala**. Utilizza il dispositivo di scorrimento **Nuova Commerce Scale Unit** per selezionare una nuova istanza CSU dall'elenco di CSU disponibili per il tuo ambiente.

## <a name="traffic-forwarding-in-production"></a>Inoltro del traffico in produzione

È possibile simulare più domini utilizzando i parametri della stringa di query del dominio sull'endpoint commerce.dynamics.com. Tuttavia quando è necessario passare in produzione, è necessario inoltrare il traffico per il dominio personalizzato all'endpoint `<e-commerce tenant name>.dynamics365commerce.ms`.

L'endpoint `<e-commerce tenant name>.dynamics365commerce.ms` non supporta Secure Sockets Layer (SSL) del dominio personalizzato, quindi è necessario configurare domini personalizzati utilizzando un Front Door Service o una rete per la distribuzione di contenuti (CDN). 

Per impostare domini personalizzati utilizzando un Front Door Service o una CDN, sono disponibili due opzioni:

- Configura un servizio front-end come Azure Front Door per gestire il traffico front-end e connettersi al tuo ambiente Commerce, che offre un maggiore controllo sulla gestione di domini e certificati e criteri di sicurezza più granulari.

- Utilizza l'istanza Frontdoor di Azure fornita da Commerce che richiede un'azione di coordinamento con il team di Dynamics 365 Commerce per la verifica del dominio e l'ottenimento dei certificati SSL per il dominio di produzione.

> [!NOTE]
> Se stai utilizzando una rete CDN esterna o un servizio frontdoor, assicurati che la richiesta arrivi alla piattaforma Commerce con il nome host fornito da Commerce, ma con l'intestazione X-Forwarded-Host (XFH) \<custom-domain\>. Ad esempio, se il tuo endpoint Commerce è `xyz.dynamics365commerce.ms` e il dominio personalizzato è `www.fabrikam.com`, l'intestazione host della richiesta inoltrata deve essere `xyz.dynamics365commerce.ms` e l'intestazione XFH deve essere `www.fabrikam.com`.

Per informazioni su come configurare direttamente un servizio CDN, vedere [Aggiungere il supporto per una rete per la distribuzione di contenuti (CDN)](add-cdn-support.md).

Per usare l'istanza di Azure Front Door fornita da Commerce, è necessario creare una richiesta di assistenza per l'assistenza alla configurazione della rete CDN del team di onboarding di Commerce. 

- Sarà necessario fornire il nome della società, il dominio di produzione, l'ID ambiente e il nome del tenant e-commerce di produzione. 
- Sarà necessario confermare se questa richiesta di servizio è per un dominio esistente (utilizzato per un sito attualmente attivo) o di un nuovo dominio. 
- Per un nuovo dominio, la verifica del dominio e il certificato SSL possono essere ottenuti in un unico passaggio. 
- Per un dominio che serve un sito Web esistente, è necessario un processo a più fasi per stabilire la verifica del dominio e il certificato SSL. Questo processo prevede un contratto di servizio (SLA) di 7 giorni lavorativi per l'attivazione di un dominio, poiché include più passaggi sequenziali.

Per creare una richiesta di assistenza in LCS, all'interno dell'ambiente andare a **Supporto \> Problemi di supporto** e selezionare **Invia un evento imprevisto**.

> [!NOTE]
> I domini personalizzati con SSL sono supportati solo negli ambienti di produzione. Per ambienti non di produzione come sandbox e test di accettazione dell'utente (UAT), utilizzare l'URL generato da Commerce per accedere al contenuto pubblicato in un browser Web.

## <a name="ssl-certificate-process"></a>Processo del certificato SSL

Quando viene presentata una richiesta di assistenza, il team di Commerce coordinerà con l'utente i seguenti passaggi.

Per i nuovi domini:
- Il team di Commerce configurerà l'istanza di Azure Front Door (ospitata da Commerce).
- Il team di Commerce fornirà quindi il record CNAME per puntare al dominio personalizzato.
- Dopo l'aggiornamento del record CNAME, l'istanza di Azure Front Door ospitata da Commerce sarà in grado di verificare la proprietà del dominio e ottenere il certificato SSL.

Per domini esistenti/attivi:
- Il team di Commerce chiederà di aggiungere un record CNAME `afdverify.<custom-domain>` da fornire al provider DNS del dominio.
- Al termine, il team di Commerce aggiungerà il dominio all'istanza di Azure Front Door e fornirà record TXT DNS aggiuntivi da aggiungere al DNS per il dominio.
- Dopo che i record TXT sono stati completati, il team di Commerce completerà gli aggiornamenti di Azure Front Door per il dominio che configurerà il certificato SSL.

## <a name="apex-domains"></a>Domini Apex

L'istanza di Azure Front Door fornita da Commerce non supporta i domini Apex (domini radice che non contengono sottodomini). I domini Apex richiedono un indirizzo IP per essere risolti e l'istanza di Azure Front Door di Commerce esiste solo con endpoint virtuali. Per utilizzare un dominio Apex, sono disponibili le seguenti opzioni:

- **oOpzione 1** - Utilizza il provider DNS per reindirizzare il dominio Apex a un dominio "www". Ad esempio, fabrikam.com reindirizza a `www.fabrikam.com` dove `www.fabrikam.com` è il record CNAME che punta all'istanza di Azure Front Door ospitata da Commerce.

- **Opzione 2** - Se il provider DNS supporta i record ALIAS, è possibile puntare il dominio Apex all'endpoint di Azure Front Door, in modo che la modifica dell'IP da parte dell'endpoint venga riflessa. È necessario ospitare personalmente l'istanza di Azure Front Door.
  
- **Opzione 3** - Se il provider DNS non supporta i record ALIAS, è necessario modificare il provider DNS in DNS di Azure e ospitare personalmente sia il DNS di Azure che l'istanza di Azure Front Door.

> [!NOTE]
> Se si usa Azure Front Door, è necessario anche configurare un DNS di Azure nella stessa sottoscrizione. Il dominio Apex ospitato su DNS Azure può puntare ad Azure Front Door come record alias. Questa è l'unica soluzione, poiché i domini Apex devono sempre puntare a un indirizzo IP.
  
In caso di domande sui domini Apex, contatta il [supporto tecnico Microsoft](https://support.microsoft.com/).

  ## <a name="additional-resources"></a>Risorse aggiuntive

  [Distribuire un nuovo tenant di e-commerce](deploy-ecommerce-site.md)

  [Impostare un canale punto vendita online](./channel-setup-online.md)

  [Creare un sito di e-commerce](create-ecommerce-site.md)

  [Associare un sito Dynamics 365 Commerce a un canale online](associate-site-online-store.md)

  [Gestire i file robots.txt](manage-robots-txt-files.md)

  [Caricare reindirizzamenti URL in blocco](upload-bulk-redirects.md)

  [Impostare un tenant B2C in Commerce](set-up-B2C-tenant.md)

  [Impostare pagine personalizzate per l'accesso degli utenti](custom-pages-user-logins.md)

  [Configurare più tenant B2C in un ambiente Commerce](configure-multi-B2C-tenants.md)

  [Aggiungere il supporto per una rete per la distribuzione di contenuti (CDN)](add-cdn-support.md)

  [Abilitare il rilevamento del punto vendita basato sull'ubicazione](enable-store-detection.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
