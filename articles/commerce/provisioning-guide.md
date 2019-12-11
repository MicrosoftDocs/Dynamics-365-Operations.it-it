---
title: Configurare un ambiente di valutazione di e-Commerce
description: In questo manuale sono disponibili istruzioni dettagliate per il provisioning e la configurazione dell'ambiente di anteprima di Microsoft Dynamics 365 Commerce.
author: v-chgri
manager: annbe
ms.date: 10/15/2019
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
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: b0dce2796e69cd8dee87cba176a521c26c81eb1a
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/06/2019
ms.locfileid: "2771682"
---
# <a name="configure-an-e-commerce-evaluation-environment"></a>Configurare un ambiente di valutazione di e-Commerce

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

In questo manuale sono disponibili istruzioni dettagliate per il provisioning e la configurazione dell'ambiente di anteprima di Microsoft Dynamics 365 Commerce. Prima di iniziare, è consigliabile almeno scorrere la documentazione per avere un'idea di ciò che il processo implica e del contenuto della Guida.

*Nota: se non si dispone dell'autorizzazione di accesso all'anteprima di Microsoft Dynamics 365 Commerce, è possibile richiedere l'accesso all'anteprima dal [sito Web di Commerce](https://aka.ms/Dynamics365CommerceWebsite).*

## <a name="summary"></a>Riepilogo
Per eseguire correttamente il provisioning dell'ambiente, il progetto deve essere creato con un nome e un tipo di prodotto specifici. Anche l'ambiente e Retail Cloud Scale Unit hanno alcuni parametri specifici che devono essere utilizzati per iniziare il provisioning di e-Commerce in seguito. Le istruzioni nel presente manuale contengono tutti i passaggi necessari e i parametri che devono essere utilizzati.

Dopo il completamento del provisioning, è necessario svolgere alcuni passaggi post-provisioning per preparare l'ambiente di anteprima. Alcuni passaggi sono facoltativi, a seconda degli aspetti del sistema che si desidera valutare. Se successivamente si dovesse cambiare idea, è sempre possibile eseguirli in seguito.

Per eventuali domande sui passaggi di provisioning o in caso di problemi, contattarci tramite il [gruppo Yammer di Microsoft Dynamics 365 Commerce ](https://aka.ms/Dynamics365CommercePreviewYammer). 

## <a name="prerequisites"></a>Prerequisiti
Di seguito sono riportati i prerequisiti per il provisioning dell'ambiente di anteprima di Dynamics 365:
* Si ha accesso al **portale di Lifecycle Services (LCS)**
* Si è **membri del programma Anteprima di Dynamics 365 Commerce**
* Si dispone delle autorizzazioni necessarie per creare un progetto per **Pre-vendite potenziali** o **Migrare, creare soluzioni e ottenere informazioni**
* Si è membro del ruolo **Responsabile ambiente** o **Proprietario di progetto** nel progetto in cui verrà eseguito il provisioning dell'ambiente
* Si dispone dell'accesso di amministratore alla sottoscrizione Azure, oppure contattare un amministratore della sottoscrizione che può eseguire le due operazioni che richiedono autorizzazioni di amministratore per proprio conto
* Si dispone dell'**ID tenant AAD**
* Si è creato un **Gruppo di sicurezza AAD** da utilizzare come **gruppo Amministratori del sistema di e-Commerce** e si dispone del relativo ID
* Si è creato un **gruppo di sicurezza AAD** da utilizzare come **Gruppo moderatore di valutazioni e recensioni** e si dispone del relativo ID disponibile (può essere lo stesso gruppo di sicurezza del gruppo Amministratori del sistema precedente)
## <a name="provisioning-preview-environment"></a>Provisioning dell'ambiente di anteprima
Queste istruzioni sono relative al provisioning dell'ambiente di anteprima di Microsoft Dynamics 365 Commerce. Dopo aver completato correttamente la procedura, si disporrà di un ambiente di anteprima pronto per la configurazione. Tutte le attività descritte qui possono verificarsi nel portale di LCS.

*Da notare che l'accesso di anteprima è associato all'organizzazione e all'account LCS specificati nell'applicazione di anteprima. È necessario utilizzare lo stesso account per il provisioning. Se si deve utilizzare un tenant o un account LCS differente per l'ambiente di anteprima, è necessario fornire tali dettagli. Per informazioni di contatto, vedere "Risorse aggiuntive" qui sotto.*
### <a name="before-starting"></a>Prima di iniziare
##### <a name="grant-access-to-e-commerce-applications"></a>Concedere l'accesso alle applicazioni di e-Commerce

*Nota: **la persona che esegue l'accesso deve essere l'amministratore tenant AAD**. Se non si completa correttamente questo passaggio, gli altri passaggi di provisioning non riusciranno.*

1. Per questo passaggio, è necessario il proprio **ID tenant AAD**. Si devono autorizzare le applicazioni di e-Commerce ad accedere alla sottoscrizione Azure. Il modo più semplice per ottenere questo risultato è assemblare un URL nel seguente modo:

https://login.windows.net/{AAD_TENANT_ID}/oauth2/authorize?client_id=fbcbf727-cd18-4422-a723-f8274075331a&response_type=code&redirect_uri=https://sb.manage.commerce.dynamics.com/_commerce/Consent&response_mode=query&prompt=admin_consent&state=12345

2. **Non fare clic direttamente sull'URL**, ma copiarlo e incollarlo nel browser o nell'editor di testo e sostituire **\{AAD_TENANT_ID\}** con il proprio **ID tenant AAD**, prima di accedere all'URL.
3. Verrà visualizzata la finestra per l'accesso a Microsoft ADD in cui si confermerà che si desidera concedere a "Dynamics 365 Commerce (Anteprima) l'accesso alla sottoscrizione.
4. Verrà visualizzata una pagina che conferma se l'operazione è riuscita.

##### <a name="log-in-to-the-lcs"></a>Accedere a LCS
1. Accedere al portale LCS: https://lcs.dynamics.com
1. Assicurarsi di aver effettuato l'accesso con lo stesso account LCS utilizzato per richiedere l'accesso all'anteprima.
##### <a name="confirm-that-preview-features-are-available-and-enabled"></a>Verificare che le funzionalità di anteprima siano disponibili e abilitate
1. Nella pagina riepilogativa di LCS, scorrere tutto a destra e fare clic sul riquadro **Gestione funzionalità di anteprima**.
1. Scorrere in basso fino a fino a "FUNZIONALITÀ DI ANTEPRIMA PRIVATA" e assicurarsi che le seguenti funzionalità siano disponibili e abilitate:
    1. **Valutazione di e-Commerce**
    1. **Ambienti del programma di anteprima di Commerce**
1. Se queste funzionalità non sono visualizzate nell'elenco, contattarci con l'indirizzo e-mail di lavoro, l'account LCS e i dettagli sul tenant. Consultare **Risorse aggiuntive** di seguito per informazioni su come contattarci.

![Riquadro Gestione funzionalità di anteprima](./media/preview1.png)

![Funzionalità di anteprima](./media/preview2.png)
### <a name="create-project"></a>Crea progetto
##### <a name="creating-new-project"></a>Creare un nuovo progetto
1. Fare clic su **+** per creare un nuovo progetto.
1. Se si è un partner, scegliere **Migrare, creare soluzioni e ottenere informazioni**.
1. Se si è un cliente, scegliere **Pre-vendite potenziali**.
1. Immettere un nome, una descrizione e un settore come necessario.
1. In **Nome prodotto**, selezionare **Dynamics 365 Retail**.
1. In **Versione prodotto**, selezionare **Dynamics 365 Retail**.
1. In **Metodologia**, selezionare **Metodologia di implementazione di Dynamics Retail**.
1. È possibile importare ruoli e utenti da un progetto esistente se desiderato.
1. Fare clic su **Crea**.
1. Viene visualizzata la visualizzazione del progetto.
##### <a name="add-azure-connector"></a>Aggiungere un connettore di Azure
1. Se si è un partner, fare clic su **Impostazioni progetto** nel riquadro degli strumenti all'estrema destra.
1. Se si è un cliente, scegliere **Impostazioni progetto** nel menu superiore.
1. Selezionare **Connettori di Azure**.
1. Fare clic su **+ Aggiungi** per aggiungere un connettore di Azure.
1. Immettere un nome.
1. Immettere l'**ID sottoscrizione Azure**.
1. Abilitare **Configura per l'utilizzo di Azure Resource Manager (ARM)**.
1. Verificare che **Dominio tenant AAD di sottoscrizione Azure (o ID)** sia corretto. Consultare l'amministratore della sottoscrizione Azure, se necessario.
1. Fare clic su **Avanti**.
1. Seguire le istruzioni sullo schermo per concedere alle applicazioni necessarie l'accesso alla sottoscrizione. Consultare l'amministratore della sottoscrizione Azure, se necessario:
    1. Accedere al portale di Azure: https://portal.azure.com/
    1. Assicurarsi di aver selezionato la directory corretta.
    1. Fare clic su **Sottoscrizioni** nel menu a sinistra.
    1. Individuare la sottoscrizione corretta nell'elenco e selezionarla. Utilizzare la funzionalità di ricerca se necessario.
    1. Scegliere **Controllo dei diritti di accesso (IAM)** dal menu.
    1. Fare clic su **Aggiungi** in **Aggiungi un'assezione di ruolo** a destra. Il riquadro **Aggiungi un'assegnazione di ruolo** viene aperto.
    1. Per **Ruolo**, selezionare **Collaboratore**.
    1. In **Assegna accesso a**, mantenere **Utente, gruppo o entità servizio Azure AD**.
    1. In **Selezioa**, immettere **b96b7e94-b82e-4e71-99a0-cf7fb188acea**.
    1. Selezionare **Servizi di distribuzione di Dynamics [abilitati con WsFed]** nell'elenco.
    1. Fare clic su **Salva**.
1. Fare clic su **Avanti**.
1. Seguire le istruzioni sullo schermo per concedere alle applicazioni necessarie l'accesso alla sottoscrizione. Consultare l'amministratore della sottoscrizione Azure, se necessario.
1. Fare clic su **Avanti**.
1. In **Area di Azure**, scegliere **Stati Uniti orientali**, **Stati Uniti orientali 2**, **Stati Uniti occidentali** o **Stati Uniti occidentali 2**.
1. Fare clic su **Connetti**.
1. Il connettore di Azure deve apparire nell'elenco.
### <a name="import-extension"></a>Importare un'estensione
1. Ritornare alla pagina riepilogativa del progetto facendo clic sul nome del progetto nella parte superiore.
1. Se si è un partner, fare clic su **Raccolta di asset** nei riquadri degli strumenti all'estrema destra.
1. Se si è un cliente, scegliere **Raccolta di asset** nel menu superiore.
1. Selezionare **Pacchetto software distribuibile** nell'elenco a sinistra.
1. Fare clic su **IMPORTA** nel riquadro azioni.
1. Selezionare **Estensione di base dimostrativa anteprima di Commerce** dall'elenco degli asset in **RACCOLTA DI ASSET CONDIVISE**.
1. Fare clic su **Preleva**.
1. Si viene reindirizzati alla raccolta di asset e l'estensione dovrebbe essere visualizzata nell'elenco.

![Creazione del progetto - versioni](./media/import.png)
### <a name="deploy-environment"></a>Ambiente di distribuzione

*Nota: è possibile che i passaggi 6, 7 e/o 8 non siano visualizzati, in quanto le schermate con un'unica opzione vengono ignorate. Quando si è nella visualizzazione **parametri ambiente**, confermare di avere il testo "Dynamics 365 Commerce (Anteprima) - Demo (10.0.6 con update 30 della piattaforma)" direttamente sopra il campo **Nome ambiente**. Vedere la schermata seguente.*

1. Nel menu superiore, selezionare **Distribuzione ambienti ospitati nel cloud**.
1. Fare clic su **+ Aggiungi** per aggiungere un ambiente.
1. In **Versione applicazione** selezionare **10.0.6**.
1. In **Versione piattaforma**, selezionare **Update 30 della piattaforma**.
1. Fare clic su **Avanti**.
1. Per la topologia dell'ambiente, scegliere **DEMO**.
1. Per la topologia dell'ambiente, scegliere **Dynamics 365 Commerce (Anteprima) - Demo**.
1. Se in precedenza è stato configurato un singolo connettore di Azure, verrà utilizzato per tale ambiente. Se sono stati configurati molteplici connettori di Azure, è possibile scegliere di selezionare il connettore che si desidera utilizzare: **Stati Uniti orientali**, **Stati Uniti orientali 2**, **Stati Uniti occidentali** o **Stati Uniti occidentali 2** (consigliati per le migliori prestazioni end-to-end)
1. Immettere un **nome di ambiente**.
1. Modificare le dimensioni della VM come necessario (si consiglia l'unità SKU VM **D13 v2**).
1. Non modificare le **impostazioni avanzate**.
1. Dopo avere esaminato i termini relativi a licenze e prezzi visualizzati, selezionare la casella per indicare il contratto.
1. Fare clic su **Avanti**.
1. Nella schermata di conferma della distribuzione, dopo aver verificato che i dettagli siano corretti, fare clic su **Distribuisci**.
1. Si ritorna alla visualizzazione **Distribuzione ambienti ospitati nel cloud** e il proprio l'ambiente deve essere visualizzato nell'elenco.
1. L'ambiente richiesto viene visualizzato come accodato e quindi in fase di distribuzione. Il completamento di tutti i flussi di lavoro dell'ambiente richiederà qualche tempo, quindi controllare più tardi dopo alcune ore (circa 6 - 9).
1. Prima di procedere, assicurarsi che lo stato dell'ambiente sia **Distribuito**.

![Creazione del progetto - versioni](./media/project1.png)

![Creazione progetto - topologia 1](./media/project2.png)

![Creazione progetto - topologia 2](./media/project3.png)

![Creazione di progetto - parametri dell'ambiente](./media/project4.png)
### <a name="initialize-rcsu"></a>Inizializzare la RCSU
1. Nella visualizzazione **Distribuzione ambienti ospitati nel cloud**, selezionare l'ambiente nell'elenco.
1. Nella visualizzazione dell'ambiente a destra dello schermo, fare clic su **Dettagli completi**. Vengono visualizzati i dettagli dell'ambiente.
1. In **FUNZIONALITÀ E AMBIENTE**, fare clic su **Gestisci**.
1. Nella scheda **Vendita al dettaglio**, scegliere **Inizializza**. Vengono visualizzati i parametri di inizializzazione della RCSU.
1. In **AREA**, selezionare **Stati Uniti orientali**, **Stati Uniti orientali 2**, **Stati Uniti occidentali** o **Stati Uniti occidentali 2**.
1. In **VERSIONE**, selezionare innanzitutto **Specificare una versione** dall'elenco a discesa, quindi specificare **9.16.19262.5** nel campo di testo visualizzato sotto. *Nota: assicurarsi di **specificare la versione esatta** elencata qui per evitare di dover aggiornare la RCSU in seguito per correggere la versione.*
1. Abilitare **Applica l'estensione**.
1. Nell'elenco delle estensioni, scegliere **Estensione di base dimostrativa anteprima di Commerce**.
1. Fare clic su **Inizializza**.
1. Nella schermata di conferma della distribuzione, dopo aver verificato che i dettagli siano corretti, fare clic su **Sì**.
1. Viene visualizzata di nuovo la visualizzazione **Gestione vendita al dettaglio** con la scheda **Vendita al dettaglio** attivata. La RCSU è stata accodata per il provisioning.
1. Attendere che lo stato della RCSU sia **OPERAZIONE COMPLETATA** prima di continuare (sono necessarie all'incirca 2 - 5 ore).
### <a name="initialize-e-commerce"></a>Inizializzare e-Commerce
1. Passare alla scheda **e-Commerce (anteprima)**.
1. Dopo avere esaminato il consenso dell'anteprima, fare clic su **Imposta**.
1. Immettere un nome per **Nome tenant e-Commerce**. Tuttavia, da notare che ciò sarà visibile in alcuni degli URL che puntano all'istanza di e-Commerce.
1. In **Nome Retail Cloud Scale Unit**, selezionare la propria RCSU dall'elenco (che dovrebbe avere una sola opzione).
1. Il campo **Geografica e-Commerce** viene popolato automaticamente e non può essere modificato.
1. Fare clic su **Avanti** per continuare.
1. In **Nomi host supportati**, immettere qualsiasi dominio valido (ad esempio www.fabrikam.com).
1. In **Gruppo di sicurezza AAD per amministratore sistema**, immettere l'ID SG ADD che si desidera utilizzare come gruppo Amministratori del sistema di e-Commerce.
1. In **Gruppo di sicurezza AAD per moderatore di valutazioni e recensioni**, immettere l'ID GS AAD che si desidera utilizzare come gruppo moderatore di valutazioni e recensioni.
1. Lasciare i campi **B2C** vuoti (7 che iniziano con B2C).
1. Lasciare attivato**Abilita servizio Valutazioni e recensioni**.
1. Fare clic su **Inizializza**.
1. Viene visualizzata di nuovo la visualizzazione **Gestione vendita al dettaglio** con la scheda **e-Commerce (anteprima)** attivata. L'inizializzazione di e-Commerce è stata avviata.
1. Prima di procedere, attendere che lo stato dell'inizializzazione di e-Commerce sia **INIZIALIZZAZIONE RIUSCITA**.
1. In **COLLEGAMENTI** nella parte inferiore destra:
    * Prendere nota del collegamento **Sito di e-Commerce**. Si tratta del collegamento alla directory principale del sito C2.
    * Prendere nota del collegamento **Strumento di gestione del sito di e-Commerce**. Si tratta del collegamento allo strumento di gestione del sito (strumento di creazione C1).
## <a name="post-provisioning-steps"></a>Passaggi post-provisioning
A questo punto, è stato eseguito il provisioning end-to-end dell'ambiente, ma vi sono ancora delle operazioni di configurazione da eseguire prima di poter iniziare a valutare l'ambiente.
### <a name="before-starting"></a>Prima di iniziare
1. Nel menu superiore, selezionare **Distribuzione ambienti ospitati nel cloud**.
1. Selezionare l'ambiente dall'elenco.
1. Fare clic su **Dettagli completi** nelle informazioni sull'ambiente a destra.
1. Fare clic su **Accesso** per aprire un menu e scegliere **Accedi all'ambiente**.

Assicurarsi che la persona giuridica **USRT** sia selezionata (angolo in alto a destra).

### <a name="configure-pos"></a>Configura POS
##### <a name="associate-worker-with-your-identity"></a>Associare il lavoratore all'identità
1. Utilizzando il menu a sinistra, scegliere **Moduli > Vendita al dettaglio > Dipendenti > Lavoratori**.
1. Nell'elenco trovare e selezionare il record **000713 - Andrew Collette**.
1. Nel riquadro azioni, fare clic su **Vendita al dettaglio**.
1. Fare clic su **Associa identità esistente**.
1. Nel campo **Indirizzo di posta elettronica** (a destra di **Cerca tramite posta elettronica**), digitare il proprio indirizzo di posta elettronica.
1. Fare clic su **Cerca**.
1. Selezionare il record con il proprio nome.
1. Fare clic su **OK**.
1. Fare clic su **Salva**.
##### <a name="activate-cloud-pos"></a>Attivare il Cloud POS
1. Accedere al portale LCS.
1. Accedere al progetto.
1. Nel menu superiore, selezionare **Distribuzione ambienti ospitati nel cloud**.
1. Selezionare l'ambiente dall'elenco.
1. Fare clic su **Dettagli completi** nelle informazioni sull'ambiente a destra.
1. Fare clic su **Accedi** per aprire un menu e scegliere **Accedi a POS cloud**; il POS dovrebbe essere caricato.
1. Fare clic su **Avanti**.
1. Accedere con l'account AAD.
1. In **Nome punto vendita**, scegliere **San Francisco**.
1. Fare clic su **Avanti**.
1. In **Registro e dispositivo**, scegliere **SANFRAN-1**.
1. Fare clic su **Attiva**.
1. Viene eseguita la disconnessione e viene visualizzato lo schermo di accesso al POS.
1. A questo punto è possibile accedere all'esperienza POS cloud utilizzando l'ID operatore **000713** e la password **123**.
### <a name="site-setup"></a>Impostazione del sito
1. Accedere allo **strumento di gestione del sito** mediante l'URL annotato in precedenza.
1. Fare clic sul sito **Fabrikam** per aprire la finestra di dialogo di impostazione del sito.
1. Come dominio, selezionare il dominio immesso in precedenza durante l'inizializzazione di e-Commerce.
1. Come canale predefinito, selezionare **Punto vendita online esteso Fabrikam**. *Nota: assicurarsi di selezionare il punto vendita online **esteso**.*
1. Come lingua predefinita, selezionare **en-us**.
1. Non modificare il valore di **Percorso**.
1. Fare clic su **OK**.
1. Viene visualizzato l'elenco delle pagine del sito.
### <a name="enable-jobs"></a>Abilitare i processi
1. Accedere all'ambiente (HQ).
1. Utilizzando il menu a sinistra, selezionare **Vendita al dettaglio > Richieste di informazioni e report > Processi batch**.
1. Eseguire i seguenti passaggi per ciascuno dei processi nell'elenco sotto:
    * **Elabora notifica tramite posta elettronica di ordine di vendita al dettaglio**.
    * **Disponibilità prodotto**.
    * **P-0001**.
    * **Sincronizza processo di ordini**.
1. Utilizzare il filtro rapido per cercare il processo mediante il relativo nome (elencato sopra).
1. Se lo stato del processo è **Trattenuto**, effettuare le seguenti operazioni:
    1. Selezionare il record.
    1. Nel riquadro azioni, aprire la barra **Processo batch**e fare clic su **Cambia stato**.
    1. Selezionare **In attesa** e fare clic su **OK**.
### <a name="run-full-data-sync"></a>Esegui sincronizzazione dati completa
1. Utilizzando il menu a sinistra, selezionare **Moduli > Vendita al dettaglio > Impostazione sedi centrali > Retail Scheduler > Database canale**.
1. Il canale**Predefinito** è selezionato nell'elenco a sinistra. *Selezionare l'altro canale disponibile (denominato **scXXXXXXXXX**)*.
1. Fare clic su **Sincronizzazione dati completa** nel riquadro azioni.
1. Immettere **9999** come programmazione della distribuzione.
1. Fare clic su **OK**.
1. Fare clic su **OK**.
### <a name="after-these-steps-you-are-ready-to-start-evaluating-your-preview-environment"></a>Dopo questi passaggi si è pronti per iniziare a valutare l'ambiente di anteprima.
Utilizzare l'URL **Strumento di gestione del sito di e-Commerce** per passare all'esperienza di creazione C1 e l'URL **Sito di e-Commerce** per passare all'esperienza di sito C2.

## <a name="additional-resources"></a>Risorse aggiuntive
### <a name="how-to-find-your-aad-tenant-id"></a>Come trovare l'ID tenant AAD
L'ID tenant AAD è un GUID ed è simile a questo esempio: **72f988bf-86f1-41af-91ab-2d7cd011db47**
##### <a name="from-azure-portal"></a>Dal portale di Azure
1. Accedere al portale di Azure: https://portal.azure.com/
1. Assicurarsi di aver selezionato la directory corretta.
1. Fare clic su **Azure Active Directory** nel menu a sinistra.
1. Scegliere **Proprietà** in **Gestisci**.
1. L'ID tenant AAD è visualizzato sotto **ID directory**.
##### <a name="from-openid-connect-metadata"></a>Dai metadati di OpenID Connect
Creare l'**URL OpenID** sostituendo **\{YOUR_DOMAIN\}** con il dominio, ad esempio microsoft.com: https://login.microsoftonline.com/{YOUR_DOMAIN}/.well-known/openid-configuration diventerebbe https://login.microsoftonline.com/microsoft.com/.well-known/openid-configuration

1. Andare all'**URL OpenID** che include il dominio.
1. L'ID tenant AAD può essere visualizzato in molteplici valori di proprietà.
1. Trovare **authorization_endpoint** ed estrarre il GUID subito dopo **login.microsoftonline.com/**.
### <a name="how-to-find-the-id-of-your-aad-security-group"></a>Come trovare l'ID del gruppo di sicurezza AAD
L'ID gruppo di sicurezza AAD è un GUID ed è simile a questo esempio: **436ea7f5-ee6c-40c1-9f08-825c5811066a**

Questo passaggio presuppone che l'utente è un membro del gruppo per il quale si sta tentando di identificare l'ID.
1. Accedere allo strumento Graph explorer: https://developer.microsoft.com/en-us/graph/graph-explorer#
1. Fare clic su **Accedi a Microsoft** e accedere utilizzando le credenziali.
1. Dopo l'accesso, fare clic su **Mostra altri esempi** a sinistra.
1. Abilitare **Gruppi** nel riquadro a destra.
1. Chiudere il riquadro a destra.
1. Fare clic su **Tutti i gruppi a cui appartengo**.
1. Individuare il gruppo nella casella di testo **Anteprima risposta**.
1. L'ID gruppo di sicurezza si trova sotto la proprietà **ID**.
### <a name="test-credit-card-information-to-perform-test-purchases"></a>Verificare le informazioni sulla carta di credito per eseguire acquisti di prova
Per eseguire transazioni di prova nel sito, è possibile utilizzare queste informazioni sulla carta di credito di prova:

Numero di carta: 4111-1111-1111-1111, scadenza: 10/20, CVV: 737

*Nota: non utilizzare mai le informazioni di una carta di credito effettiva nel sito di prova.*
### <a name="useful-links"></a>Collegamenti utili
* [LCS (Lifecycle Services)](https://docs.microsoft.com/en-us/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide)
* [RCSU (Retail Cloud Scale Unit)](https://docs.microsoft.com/en-us/business-applications-release-notes/october18/dynamics365-retail/retail-cloud-scale-unit)
* [Portale di Microsoft Azure](https://azure.microsoft.com/en-us/features/azure-portal)
* [Sito Web di Dynamics 365 Commerce](https://aka.ms/Dynamics365CommerceWebsite)
* [Risorse di guida per Dynamics 365 Retail](../retail/index.md)
### <a name="microsoft-dynamics-365-commerce-preview-support"></a>Supporto anteprima di Microsoft Dynamics 365 Commerce
In caso di problemi durante l'esecuzione dei passaggi per il provisioning, visitare il [gruppo Yammer per l'anteprima di Microsoft Dynamics 365 Commerce](https://aka.ms/Dynamics365CommercePreviewYammer) per assistenza. 

In caso di problemi nell'accedere al gruppo Yammer, è anche possibile contattarci tramite posta elettronica all'indirizzo **Dynamics365Commerce@microsoft.com**. Questo indirizzo di posta elettronica non è monitorato attivamente, quindi è possibile che la risposta non sia immediata.
***
## <a name="prerequisites-for-optional-features"></a>Prerequisiti per funzionalità facoltative
Se si desidera valutare le funzionalità di posta elettronica transazionali, è necessario soddisfare i prerequisiti seguenti:
* Si dispone di un server di posta elettronica disponibile (server SMTP), che può essere utilizzato dalla sottoscrizione Azure in cui si esegue il provisioning dell'ambiente di anteprima.
* Si dispone del numero di porta SMTP, FQDN/IP e dettagli di autenticazione del server.

Se si desidera valutare le funzionalità di Gestione degli asset digitali, in particolare inserire nuove immagini multicanale, i seguenti prerequisiti devono essere soddisfatti:
* È necessario disporre del **Nome tenant CMS**. Le istruzioni per l'individuazione di questo nome sono esposte di seguito.
### <a name="configure-image-backend-optional"></a>Configurare il backend delle immagini (facoltativo)
##### <a name="finding-your-media-base-url"></a>Individuare l'URL di base multimediale
*Nota: per poter completare questo passaggio, è necessario dapprima completare la procedura in **Impostazione del sito**.*
1. Accedere allo strumento di gestione del sito mediante l'URL annotato in precedenza.
1. Aprire il sito **Fabrikam**.
1. Scegliere **Asset** nel menu a sinistra.
1. Selezionare qualsiasi singolo asset di immagine.
1. Individuare l'**URL pubblico** nel controllo proprietà a destra. Include un URL.
    * Esempio di URL: https://images-us-sb.cms.commerce.dynamics.com/cms/api/fabrikam/imageFileData/MA1nQC
1. Sostituire l'ultimo identificatore nell'URL (MA1nQC nell'URL di esempio sopra) con la stringa seguente: **search?fileName=**
    * URL di esempio dopo la sostituzione: https://images-us-sb.cms.commerce.dynamics.com/cms/api/fabrikam/imageFileData/search?fileName=
    * Questo è '**URL di base multimediale**. Annotarlo.
##### <a name="updating-the-media-base-url"></a>Aggiornare l'URL di base multimediale
1. Accedere all'ambiente (HQ).
1. Utilizzando il menu a sinistra, selezionare **Moduli > Vendita al dettaglio > Impostazione canale > Profili canale**.
1. Fare clic su **Modifica**.
1. Nelle **Proprietà del profilo**, sostituire il valore di **URL di base server multimediale** con l'**URL di base multimediale** creato in precedenza.
1. Selezionare l'altro canale nell'elenco a sinistra, sotto il canale **Predefinito**.
1. In **Proprietà profilo**, fare su **+ Aggiungi**.
1. Per la proprietà che è stata aggiunta, scegliere **URL di base server multimediale** come chiave proprietà e come valore della proprietà, immettere l'**URL di base multimediale** creato in precedenza.
1. Fare clic su **Salva**.

### <a name="configure-email-server-optional"></a>Configurare il server di posta elettronica (facoltativo)
Da notare che il server SMTP o il servizio di posta elettronica specificato qui deve essere accessibile dalla sottoscrizione Azure utilizzata per l'ambiente.
1. Accedere all'ambiente (HQ).
1. Utilizzando il menu a sinistra, selezionare **Moduli > Vendita al dettaglio > Impostazione sedi centrali > Parametri > Parametri posta elettronica**.
1. Fare clic sulla scheda **Impostazioni SMTP**.
1. Nel campo **Server di posta in uscita**, digitare l'indirizzo IP o FQDN del server SMTP o del servizio di posta elettronica.
1. Nel campo **Numero porta SMTP**, immettere il numero di porta (quello predefinito è 25 quando non si utilizza SSL).
1. Nel campo **Nome utente**, immettere un valore (se l'autenticazione è necessaria).
1. Nel campo **Password**, immettere un valore (se l'autenticazione è necessaria).
1. Fare clic su **Salva**.
1. Fare clic su **Aggiorna**.
1. Fare clic sulla scheda **Messaggio e-mail di prova**.
1. Nel campo del provider di posta elettronica, scegliere **SMTP**.
1. Nel campo **Invia a**, immettere l'indirizzo di posta elettronica a cui inviare il messaggio e-mail di prova.
1. Far clic su **Invia messaggio e-mail di prova**.
### <a name="configure-email-templates-optional"></a>Configurare modelli di messaggio di posta elettronica (facoltativo)
Il modello di messaggio di posta elettronica per ciascun evento transazionale per il quale si desidera inviare messaggi di posta elettronica deve essere aggiornato con un indirizzo di posta elettronica del mittente valido.
1. Utilizzando il menu a sinistra, selezionare **Moduli > Amministrazione organizzazione > Impostazione > Parametri > Modelli di posta elettronica a livello di organizzazione**.
1. Fare clic su **Mostra elenco**.
1. Per ogni modello nell'elenco:
    1. Nel campo **Indirizzo di posta elettronica del mittente**, digitare l'indirizzo di posta elettronica del mittente per questo modello di messaggio di posta elettronica.
    1. (Facoltativo) Nel campo **Nome mittente**, digitare un nome che verrà utilizzato come mittente per questo modello di messaggio di posta elettronica.
1. Fare clic su **Salva**.
### <a name="customizing-email-templates-optional"></a>Personalizzare modelli di messaggio di posta elettronica (facoltativo)
È possibile che si intenda personalizzare i modelli di messaggio di posta elettronica per utilizzare differenti immagini o per aggiornare i collegamenti nel modello ed eseguire di nuovo il collegamento all'ambiente di anteprima. I passaggi seguenti illustrato come scaricare i modelli predefiniti, personalizzarli e aggiornarli nel sistema.
1. Mediante un browser, scaricare i [modelli di messaggio di posta elettronica predefiniti dell'anteprima di Microsoft Dynamics 365 Commerce](https://download.microsoft.com/download/d/7/b/d7b6c4d4-fe09-4922-9551-46bbb29d202d/Commerce.Preview.Default.Email.Templates.zip) contenenti i seguenti documenti HTML nel computer locale.
    1. Modello Conferma ordine
    1. Modello Emetti gift card
    1. Modello Nuovo ordine
    1. Modello Ordine di imballaggio
    1. Modello Preleva ordine
1. Personalizzare i modelli utilizzando un editor di testo o HTML. Vedere l'elenco di token supportati più avanti.
1. Accedere all'ambiente (HQ).
1. Utilizzando il menu a sinistra, selezionare **Moduli > Vendita al dettaglio > Impostazione sedi centrali > Parametri > Modelli di posta elettronica a livello di organizzazione**.
1. Espandere l'elenco a sinistra per visualizzare tutti i modelli.
1. Per ciascun modello che si desidera personalizzare, effettuare le seguenti operazioni:
    1. Selezionare il modello dall'elenco.
    1. In **Contenuto messaggio posta elettronica**, selezionare la versione in lingua appropriata dall'elenco ( **en-us** è la lingua predefinita).
    1. In **Contenuto messaggio posta elettronica**, fare clic su **Modifica**. Viene aperto il riquadro **Carica modello di messaggio di posta elettronica**.
    1. Fare clic su **Sfoglia** e trovare il file HTML con il contenuto personalizzato.
    1. Fare clic su **Carica**; il modello viene caricato nel sistema e viene visualizzata un'anteprima.
    1. Fare clic su **OK**.
    1. (Facoltativo) Personalizzare la proprietà **Oggetto** del modello.
    1. Fare clic su **Salva**.

#### <a name="supported-tokens-in-the-email-template"></a>Token supportati nel modello di messaggio di posta elettronica
Questi token verranno sostituiti durante il rendering del messaggio di posta elettronica con i valori effettivi applicabili al cliente e ai suoi ordini.

**Ordine cliente** - I token seguenti si applicano a tutti gli ordini cliente.

|Nome del token|Token |
|---|---|
|Numero ordine|%salesid%|
|Nome cliente|%customername%|
|Indirizzo di consegna|%deliveryaddress%|
|Indirizzo di fatturazione|%customeraddress%|
|Data ordine|%shipdate%|
|Modalità di consegna|%modeofdelivery%|
|Sconto|%discount%|
|IVA|%tax%|
|Totale ordine|%total%|

**Riga di vendita** - I seguenti token vengono popolati per ogni prodotto nell'ordine.

*Nota: posizionare i token **Elenco prodotti - Inizio** e **Elenco prodotti - Fine** all'inizio e alla fine del blocco HTML ripetuto per ogni prodotto.*

|Nome del token|Token |
|---|---|
|Elenco prodotti - Inizio|\<!--%tablebegin.salesline% -->|
|Elenco prodotti - Fine|\<!--%tableend.salesline%-->|
|Nome prodotto|%lineproductname%|
|Descrizione|%lineproductdescription%|
|Quantità|%linequantity%|
|Riga prezzo unitario|%lineprice% (verify)|
|Totale voci|%linenetamount%|
|Riga sconto|%linediscount%|
|Data di spedizione|%lineshipdate%|
|Metodo di approvvigionamento|%linedeliverymode%|
|Indirizzo di consegna|%linedeliveryaddress%|
|Unità di vendita della riga|%lineunit%|

