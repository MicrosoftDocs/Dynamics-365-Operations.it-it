---
title: Provisioning di un ambiente di anteprima Commerce
description: Questo argomento illustra come eseguire il provisioning di un ambiente di anteprima di Microsoft Dynamics 365 Commerce.
author: psimolin
manager: annbe
ms.date: 01/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: b77d2cbbc100aeae5dcd53ddbe69ff2e4435da13
ms.sourcegitcommit: 4d77d06a07ec9e7a3fcbd508afdffaa406fd3dd8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/06/2020
ms.locfileid: "2934750"
---
# <a name="provision-a-commerce-preview-environment"></a>Provisioning di un ambiente di anteprima Commerce

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Questo argomento illustra come eseguire il provisioning di un ambiente di anteprima di Microsoft Dynamics 365 Commerce.

Prima di iniziare, è consigliabile almeno scorrere l'intero argomento per avere un'idea di ciò che il processo implica e del contenuto dell'argomento.

> [!NOTE]
> Se non hai ricevuto l'accesso all'anteprima di Microsoft Dynamics 365 Commerce, è possibile richiedere l'accesso all'anteprima dal [sito Web di Commerce](https://aka.ms/Dynamics365CommerceWebsite).

## <a name="overview"></a>Panoramica

Per eseguire correttamente il provisioning dell'ambiente di anteprima di Commerce, è necessario creare un progetto con un nome e un tipo di prodotto specifici. Anche l'ambiente e Retail Cloud Scale Unit hanno alcuni parametri specifici che devono essere utilizzati durante il provisioning di e-Commerce in seguito. Le istruzioni in questo argomento descrivono tutti i passaggi che è obbligatorio completare e i parametri da utilizzare.

Dopo aver completato il provisioning dell'ambiente di anteprima di Commerce, è necessario completare alcuni passaggi post-provisioning per prepararlo. Alcuni passaggi sono facoltativi, a seconda degli aspetti del sistema che si desidera valutare. È sempre possibile completare i passaggi facoltativi in seguito.

Per informazioni relative a come configurare l'ambiente di anteprima di Commerce dopo il provisioning, consultare [Configurare un ambiente di anteprima Commerce](cpe-post-provisioning.md). Per informazioni su come configurare funzionalità facoltative per l'ambiente di anteprima Commerce, vedere [Configurare le funzioni facoltative per un ambiente di anteprima Commerce](cpe-optional-features.md).

Per eventuali domande sui passaggi di provisioning o in caso di problemi, contattare Microsoft tramite il [gruppo Yammer di Microsoft Dynamics 365 Commerce](https://aka.ms/Dynamics365CommercePreviewYammer).

## <a name="prerequisites"></a>Prerequisiti

I seguenti prerequisiti devono essere presenti prima di poter eseguire il provisioning dell'ambiente di anteprima di Commerce:

- Si dispone dell'accesso al portale di Microsoft Dynamics Lifecycle Services (LCS).
- Si è membri del programma Anteprima di Dynamics 365 Commerce.
- Si dispone delle autorizzazioni necessarie per creare un progetto per **Pre-vendite potenziali** o **Migrare, creare soluzioni e ottenere informazioni**.
- Si è membri del ruolo **Responsabile ambiente** o **Proprietario di progetto** nel progetto in cui verrà eseguito il provisioning dell'ambiente.
- Si dispone dell'accesso di amministratore alla sottoscrizione Microsoft Azure o essere in contatto con un amministratore della sottoscrizione che può eseguire le due operazioni che richiedono autorizzazioni di amministratore per proprio conto.
- Si ha a disposizione l'ID tenant di Azure Active Directory (Azure AD).
- È stato creato un gruppo di sicurezza Azure AD da utilizzare come gruppo Amministratori del sistema di e-Commerce e si dispone del relativo ID.
- È stato creato un gruppo di sicurezza Azure AD da utilizzare come gruppo di moderatori di Valutazioni e revisioni e devi disporre del relativo ID. (Questo gruppo di sicurezza può essere lo stesso del gruppo di amministratori del sistema e-Commerce).

### <a name="find-your-azure-ad-tenant-id"></a>Trovare l'ID tenant Azure AD

L'ID tenant Azure AD è un identificatore univoco globale (GUID) simile a questo esempio: **72f988bf-86f1-41af-91ab-2d7cd011db47**.

#### <a name="find-your-azure-ad-tenant-id-by-using-the-azure-portal"></a>Trovare l'ID tenant di Azure AD utilizzando il portale di Azure

1. Accedere al [portale Azure](https://portal.azure.com/).
1. Assicurarsi di aver selezionato la directory corretta.
1. Nel menu a sinistra selezionare **Azure Active Directory**.
1. In **Gestisci**, selezionare **Proprietà**. L'ID tenant di Azure AD appare sotto **ID directory**.

#### <a name="find-your-azure-ad-tenant-id-by-using-openid-connect-metadata"></a>Trovare l'ID tenant di Azure AD utilizzando i metadati OpenID Connect

Creare un URL OpenID sostituendo **\{YOUR\_DOMAIN\}** con il dominio, come `microsoft.com`. Ad esempio, `https://login.microsoftonline.com/{YOUR_DOMAIN}/.well-known/openid-configuration` diventerà `https://login.microsoftonline.com/microsoft.com/.well-known/openid-configuration`.

1. Passare all'URL OpenID che contiene il proprio dominio.

    È possibile trovare l'ID tenant Azure AD in più valori di proprietà.

1. Trovare **authorization\_endpoint** ed estrarre il GUID che appare subito dopo `login.microsoftonline.com/`.

### <a name="find-your-azure-ad-security-group-id"></a>Trovare l'ID del gruppo di sicurezza di Azure AD

L'ID del gruppo di sicurezza Azure AD è un GUID che ricorda questo esempio: **436ea7f5-ee6c-40c1-9f08-825c5811066a**.

Questa procedura presuppone l'appartenenza al gruppo per cui si sta cercando di trovare l'ID.

1. Aprire [Graph explorer](https://developer.microsoft.com/graph/graph-explorer#).
1. Selezionare **Accedi a Microsoft** e accedere utilizzando le credenziali.
1. A sinistra, selezionare **Mostra altri esempi**.
1. Abilitare **Gruppi** nel riquadro a destra.
1. Chiudere il riquadro a destra.
1. Selezionare **Tutti i gruppi a cui appartengo**.
1. Nel campo **Anteprima risposta**, trovare il proprio gruppo. L'ID del gruppo di sicurezza appare sotto la proprietà **id**.

## <a name="provision-your-commerce-preview-environment"></a>Eseguire il provisioning di un ambiente di anteprima Commerce

Queste procedure spiegano come eseguire il provisioning di un ambiente di anteprima Commerce. Dopo averle completate, l'ambiente di anteprima di Commerce sarà pronto per la configurazione. Tutte le attività descritte qui possono verificarsi nel portale di LCS.

> [!IMPORTANT]
> L'accesso all'anteprima è legato all'organizzazione e all'account LCS specificati nell'applicazione di anteprima. È necessario utilizzare lo stesso account per eseguire il provisioning dell'ambiente di anteprima Commerce. Se è necessario utilizzare un altro account o tenant LCS per l'ambiente di anteprima Commerce, fornire tali dettagli a Microsoft. Per le informazioni di contatto, vedere la sezione [Supporto dell'ambiente di anteprima Commerce](#commerce-preview-environment-support) più avanti in questo argomento.

### <a name="grant-access-to-e-commerce-applications"></a>Concedere l'accesso alle applicazioni di e-Commerce

> [!IMPORTANT]
> La persona che effettua l'accesso deve essere un amministratore del tenant Azure AD che dispone dell'ID tenant Azure AD. Se questo passaggio non viene completato correttamente, i passaggi rimanenti del provisioning non riusciranno.

Per autorizzare le applicazioni di e-Commerce ad accedere alla sottoscrizione di Azure, attenersi alla seguente procedura.

1. Assemblare un URL nel seguente formato:

    `https://login.windows.net/{AAD_TENANT_ID}/oauth2/authorize?client_id=fbcbf727-cd18-4422-a723-f8274075331a&response_type=code&redirect_uri=https://sb.manage.commerce.dynamics.com/_commerce/Consent&response_mode=query&prompt=admin_consent&state=12345`

1. Copiare e incollare l'URL nel browser o nell'editor di testo e sostituire **\{AAD\_TENANT\_ID\}** con l'ID tenant Azure AD. Quindi aprire l'URL.
1. Nella finestra di dialogo di accesso di Azure AD, accedere e confermare che si desidera concedere a **Dynamics 365 Commerce (Anteprima)** l'accesso al proprio abbonamento. Si aprirà una pagina che indica se l'operazione è riuscita.

### <a name="confirm-that-preview-features-are-available-and-turned-on-in-lcs"></a>Verificare che le funzionalità di anteprima siano disponibili e attivate in LCS

Per verificare che le funzionalità di anteprima siano disponibili e attivate in LCS, seguire questi passaggi.

1. Accedere al [portale LCS](https://lcs.dynamics.com) utilizzando lo stesso account LCS utilizzato per richiedere l'accesso all'anteprima.
1. Nella home pagine di LCS, scorrere tutto a destra e selezionare il riquadro **Gestione funzionalità di anteprima**.

    ![Riquadro Gestione funzionalità di anteprima](./media/preview1.png)

1. Scorrere in basso fino **Funzionalità di anteprima privata** e assicurarsi che le seguenti funzionalità siano attivate:

    - Valutazione di e-Commerce
    - Ambienti del programma di anteprima di Commerce

    ![Funzionalità di anteprima privata](./media/preview2.png)

1. Se tali funzionalità non compaiono nell'elenco, contattare Microsoft e fornire l'indirizzo di posta elettronica aziendale, l'account LCS e i dettagli del tenant. Per le informazioni di contatto, vedere la sezione [Supporto dell'ambiente di anteprima Commerce](#commerce-preview-environment-support).

### <a name="create-a-new-project"></a>Crea un nuovo progetto

Per creare un nuovo progetto in LCS, completare i passaggi seguenti:

1. Nella home page di LCS, selezionare il segno più (**+**) per creare un progetto.
1. Nel riquadro destro, seguire uno di questi passaggi:

    - Se si è un partner, scegliere **Migrare, creare soluzioni e ottenere informazioni**.
    - Se si è un cliente, scegliere **Pre-vendite potenziali**.

1. Immettere un nome, una descrizione e il settore.
1. Nel campo **Nome prodotto**, selezionare **Dynamics 365 Retail**.
1. Nel campo **Versione prodotto**, selezionare **Dynamics 365 Retail**.
1. Nel campo **Metodologia**, selezionare **Metodologia di implementazione di Dynamics Retail**.
1. Facoltativo, è possibile importare ruoli e utenti da un progetto esistente.
1. Selezionare **Crea**. Appare la visualizzazione del progetto.

### <a name="add-the-azure-connector"></a>Aggiungere il connettore di Azure

Per aggiungere il connettore di Azure al progetto LCS, attenersi alla seguente procedura.

1. Eseguire uno dei passaggi riportati di seguito.

    - Se si è un partner, selezionare il riquadro **Impostazioni progetto** sull'estrema destra.
    - Se si è un cliente, scegliere **Impostazioni progetto** nel menu superiore.

1. Selezionare **Connettori di Azure**.
1. Selezionare **Aggiungi** per aggiungere il connettore di Azure.
1. Immettere un nome.
1. Immettere l'ID sottoscrizione Azure.
1. Attivare l'opzione **Configura per l'utilizzo di Azure Resource Manager (ARM)**.
1. Verificare che il valore **Dominio tenant AAD di sottoscrizione Azure (o ID)** sia corretto. Consultare l'amministratore della sottoscrizione Azure, in base alle esigenze.
1. Selezionare **Avanti**.
1. Seguire le istruzioni sulla pagina per concedere alle applicazioni necessarie l'accesso alla sottoscrizione. Consultare l'amministratore della sottoscrizione Azure, in base alle esigenze.

    1. Accedere al [portale Azure](https://portal.azure.com/).
    1. Assicurarsi che sia selezionata la directory corretta e quindi, nel menu a sinistra, selezionare **Sottoscrizioni**.
    1. Individuare la sottoscrizione corretta nell'elenco e selezionarla. Utilizzare la funzionalità di ricerca come richiesto.
    1. Nel menu, selezionare **Controllo dei diritti di accesso (IAM)**.
    1. Sulla destra in **Aggiungi un'assegnazione di ruolo**, selezionare **Aggiungi**. Viene visualizzato il riquadro **Aggiungi un'assegnazione di ruolo**.
    1. Nel campo **Ruolo** selezionare **Collaboratore**.
    1. Nel campo **Assegna accesso a**, lascia il valore predefinito **Utente, gruppo o entità di servizio Azure AD**.
    1. In **Selezioa**, immettere **b96b7e94-b82e-4e71-99a0-cf7fb188acea**.
    1. Seleziona **Servizi di distribuzione di Dynamics \[wsfed-enabled\]** nell'elenco.
    1. Selezionare **Salva**.

1. Selezionare **Avanti**.
1. Seguire le istruzioni sulla pagina per concedere alle applicazioni necessarie l'accesso alla sottoscrizione. Consultare l'amministratore della sottoscrizione Azure, in base alle esigenze.
1. Selezionare **Avanti**.
1. Nel campo **Area di Azure**, scegliere **Stati Uniti orientali**, **Stati Uniti orientali 2**, **Stati Uniti occidentali** o **Stati Uniti occidentali 2**.
1. Selezionare **Connetti**. Il connettore di Azure deve apparire nell'elenco.

### <a name="import-the-commerce-preview-demo-base-extension"></a>Importare l'estensione di base dimostrativa anteprima di Commerce

Per importare l'estensione di base dimostrativa anteprima di Commerce nel progetto, attenersi alla seguente procedura.

1. Aprire la home page del tuo progetto selezionando il nome del progetto in alto.
1. Eseguire uno dei passaggi riportati di seguito.

    - Se si è un partner, selezionare il riquadro **Raccolta di risorse** sull'estrema destra.
    - Se si è un cliente, scegliere **Raccolta di risorse** nel menu superiore.

1. Selezionare **Pacchetto software distribuibile** nell'elenco a sinistra.
1. Selezionare **Importa**.
1. Selezionare **Estensione di base dimostrativa anteprima di Commerce** dall'elenco degli asset in **Raccolta di risorse condivise**.
1. Selezionare **Preleva**. Si viene reindirizzati alla raccolta di asset e l'estensione dovrebbe essere visualizzata nell'elenco.

La seguente illustrazione mostra le azioni che devono essere eseguite nella pagina **Raccolta di risorse** di LCS.

![Importazione dell'estensione di base dimostrativa anteprima di Commerce](./media/import.png)

### <a name="deploy-the-environment"></a>Distribuire l'ambiente

Per distribuire l'ambiente, attenersi a questa procedura.

> [!NOTE]
> Potrebbe non essere necessario completare i passaggi 6, 7 e/o 8, poiché le pagine con una singola opzione vengono ignorate. Nella visualizzazione **Parametri dell'ambiente**, confermare che il testo **Dynamics 365 Commerce (Anteprima) - Demo (10.0.6 con aggiornamento piattaforma 30)** appaia direttamente sopra il campo **Nome dell'ambiente**. Vedere l'illustrazione che appare dopo il passaggio 8.

1. Nel menu superiore, selezionare **Distribuzione ambienti ospitati nel cloud**.
1. Selezionare **Aggiungi** per aggiungere un ambiente.
1. Nel campo **Versione applicazione**, selezionare **10.0.6**.
1. Nel campo **Versione piattaforma**, selezionare **Update 30 della piattaforma**.

    ![Selezione delle versioni della piattaforma e dell'applicazione](./media/project1.png)

1. Selezionare **Avanti**.
1. Selezionare **Demo** come topologia dell'ambiente.

    ![Selezionare della topologia dell'ambiente 1](./media/project2.png)

1. Selezionare **Dynamics 365 Commerce (anteprima) - Demo** come topologia dell'ambiente. Se in precedenza è stato configurato un singolo connettore di Azure, verrà utilizzato per tale ambiente. Se sono stati configurati più connettori di Azure, è possibile selezionare quale connettore usare: **Stati Uniti orientali**, **Stati Uniti orientali 2**, **Stati Uniti occidentali** o **Stati Uniti occidentali 2**. (Per le migliori prestazioni end-to-end, è consigliabile selezionare **Stati Uniti occidentali 2**).

    ![Selezionare della topologia dell'ambiente 2](./media/project3.png)

1. Nella pagina **Ambiente di distribuzione**, inserire un nome di ambiente. Non modificare le impostazioni avanzate.

    ![Pagina dell'ambiente di distribuzione](./media/project4.png)

1. Regolare le dimensioni della VM come richiesto. (Si consiglia un'unità di stockkeeping VM \[SKU\] **D13 v2** .)
1. Rivedere i termini relativi ai prezzi e alle licenze, quindi selezionare la casella di controllo per accettarli.
1. Selezionare **Avanti**.
1. Nella pagina di conferma della distribuzione, verificare che i dettagli siano corretti, quindi selezionare **Distribuisci**. Si ritorna alla visualizzazione **Distribuzione ambienti ospitati nel cloud** e il proprio l'ambiente deve essere visualizzato nell'elenco.

    L'ambiente richiesto viene visualizzato come accodato e quindi in fase di distribuzione. Il completamento dei flussi di lavoro dell'ambiente richiederà del tempo. Pertanto, ricontrollare dopo circa 6-9 ore.

1. Prima di procedere, assicurarsi che lo stato dell'ambiente sia **Distribuito**.

### <a name="initialize-rcsu"></a>Inizializzare la RCSU

Per inizializzare RCSU, procedere come segue.

1. Nella visualizzazione **Distribuzione ambienti ospitati nel cloud**, selezionare l'ambiente nell'elenco.
1. Nella visualizzazione dell'ambiente a destra, selezionare **Dettagli completi**. Vengono visualizzati i dettagli dell'ambiente.
1. In **Funzionalità ambiente**, selezionare **Gestisci**.
1. Nella scheda **Al dettaglio**, selezionare **Inizializza**. Vengono visualizzati i parametri di inizializzazione della RCSU.
1. Nel campo **Area**, scegliere **Stati Uniti orientali**, **Stati Uniti orientali 2**, **Stati Uniti occidentali** o **Stati Uniti occidentali 2**.
1. Nel campo **Versione**, selezionare **Specifica una versione** nell'elenco e quindi specificare **9.16.19262.5** nel campo che appare. Assicurati di specificare la versione esatta indicata qui. Altrimenti, sarà necessario aggiornare RCSU alla versione corretta in un secondo momento.
1. Attivare l'opzione **Applica l'estensione**.
1. Nell'elenco delle estensioni, selezionare **Estensione di base dimostrativa anteprima di Commerce**.
1. Selezionare **Inizializza**.
1. Nella pagina di conferma della distribuzione, verificare che i dettagli siano corretti, quindi selezionare **Sì**. Viene visualizzata di nuovo la visualizzazione **Gestione vendita al dettaglio** con la scheda **Vendita al dettaglio** selezionata. La RCSU è stata accodata per il provisioning.
1. Prima di procedere, assicurarsi che lo stato dell'ambiente RCSU sia **Completato**. L'inizializzazione dura circa 2-5 ore.

### <a name="initialize-e-commerce"></a>Inizializzare e-Commerce

Per inizializzare e-Commerce, procedere come segue.

1. Nella scheda **e-Commerce (anteprima)**, rivedere il consenso di anteprima e quindi selezionare **Configura**.
1. Immettere un nome per **Nome tenant e-Commerce**. Tuttavia, da notare che ciò sarà visibile in alcuni degli URL che puntano all'istanza di e-Commerce.
1. Nel campo **Nome Retail Cloud Scale Unit**, seleziona RCSU nell'elenco. (L'elenco dovrebbe avere una sola opzione).

    Il campo **Geografia e-Commerce** viene impostato automaticamente e il valore non può essere modificato.

1. Selezionare **Avanti** per continuare.
1. Nel campo **Nomi host supportatiN**, immettere qualsiasi dominio valido, ad esempio `www.fabrikam.com`.
1.  Nel **Gruppo di sicurezza AAD per amministratore sistema**, immettere le prime lettere del nome del gruppo di sicurezza che si desidera utilizzare. Selezionare l'icona della lente di ingrandimento per visualizzare i risultati della ricerca. Selezionare un gruppo di sicurezza dall'elenco.
2.  Nel **Gruppo di sicurezza AAD per moderatore di valutazioni e recensioni**, immettere le prime lettere del nome del gruppo di sicurezza che si desidera utilizzare. Selezionare l'icona della lente di ingrandimento per visualizzare i risultati della ricerca. Selezionare un gruppo di sicurezza dall'elenco.
1. Lasciare attivata l'opzione **Abilita servizio Valutazioni e recensioni**.
1. Se si è già completato il passaggio del consenso di Microsoft Azure Active Directory (Azure AD) come descritto nella sezione "Concedere l'accesso alle applicazioni di e-Commerce", reseleziona la casella di controllo per confermare il consenso. Se non si è ancora completato questo passaggio, è necessario farlo prima di procedere con l'inizializzazione. Selezionare il collegamento all'interno del testo accanto alla casella di controllo per aprire la finestra di dialogo del consenso e completare il passaggio.
1. Selezionare **Inizializza**. Viene visualizzata di nuovo la visualizzazione **Gestione vendita al dettaglio** con la scheda **e-Commerce (anteprima)** selezionata. L'inizializzazione di e-Commerce è stata avviata.
1. Prima di procedere, attendere che lo stato dell'inizializzazione di e-Commerce sia **Inizializzazione riuscita**.
1. In **Collegamenti** in basso a destra, prendi nota degli URL per i seguenti collegamenti:

    * **Sito di e-Commerce**: il collegamento alla radice del tuo sito di e-Commerce.
    * **Strumento di gestione del sito e-Commerce**: il collegamento allo strumento di gestione del sito.

## <a name="commerce-preview-environment-support"></a>Supporto dell'ambiente di anteprima Commerce

In caso di problemi durante l'esecuzione dei passaggi per il provisioning, visitare il [gruppo Yammer per l'anteprima di Microsoft Dynamics 365 Commerce](https://aka.ms/Dynamics365CommercePreviewYammer) per assistenza.

Se si verificano problemi quando si tenta di accedere al gruppo Yammer, è possibile contattare Microsoft tramite e-mail all'indirizzo <Dynamics365Commerce@microsoft.com>. Questo indirizzo email non è monitorato attivamente. Pertanto, aspettarsi un ritardo nella risposta.

## <a name="next-steps"></a>Passaggi successivi

Per proseguire il processo di provisioning e configurazione dell'ambiente di anteprima di Commerce, consultare [Configurare un ambiente di anteprima Commerce](cpe-post-provisioning.md).

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica dell'ambiente di anteprima di Commerce](cpe-overview.md)

[Configurare un ambiente di anteprima Commerce](cpe-post-provisioning.md)

[Configurare le funzioni facoltative per un ambiente di anteprima Commerce](cpe-optional-features.md)

[Domande frequenti sull'ambiente di anteprima Commerce](cpe-faq.md)

[Microsoft Lifecycle Services (LCS)](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide)

[Retail Cloud Scale Unit (RCSU)](https://docs.microsoft.com/business-applications-release-notes/october18/dynamics365-retail/retail-cloud-scale-unit)

[Portale di Microsoft Azure](https://azure.microsoft.com/features/azure-portal)

[Sito Web di Dynamics 365 Commerce](https://aka.ms/Dynamics365CommerceWebsite)

[Risorse di guida per Dynamics 365 Retail](../retail/index.md)
