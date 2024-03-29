---
title: Panoramica della fidelizzazione dei clienti
description: In questo articolo viene fornita una panoramica delle funzionalità di fidelizzazione dei clienti disponibili nell'applicazione del punto vendita.
author: bebeale
ms.date: 11/16/2022
ms.topic: overview
audience: Application User, Developer, IT Pro
ms.reviewer: josaw
ms.custom:
- "260624"
- intro-internal
ms.assetid: a4f9d315-9951-451c-8ee6-37f9b3b15ef0
ms.search.region: Global
ms.author: shajain
ms.search.validFrom: 2018-10-01
ms.openlocfilehash: fc7daeb27c25efa21fd34b0456af8892074056d5
ms.sourcegitcommit: 774f8f97a0b14cf1199bd1802178ccf536a25ade
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/17/2022
ms.locfileid: "9785047"
---
# <a name="clienteling-overview"></a>Panoramica della fidelizzazione dei clienti

[!include [banner](includes/banner.md)]


Molti rivenditori, in particolare i rivenditori specializzati di fascia alta, desiderano che gli addetti alle vendite stabiliscano relazioni a lungo termine con i clienti chiave. Gli addetti sono tenuti a conoscere le simpatie e le antipatie dei clienti, la cronologia degli acquisti, le preferenze sui prodotti e le date importanti, come anniversari e compleanni. Gli addetti hanno bisogno di un luogo in cui è possibile acquisire queste informazioni per usarle facilmente se necessario. Se queste informazioni sono disponibili in un'unica vista, gli addetti possono facilmente indirizzare i clienti che soddisfano criteri specifici. Ad esempio, possono trovare tutti i clienti che preferiscono acquistare borse o i clienti che si stanno avvicinando a un evento importante, come un compleanno o un anniversario.

Il seguente video illustra uno scenario di esempio di clienteling in Dynamics 365 Commerce.


> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE5bMSP]

## <a name="client-book"></a>Libro clienti

In Microsoft Dynamics 365 Commerce, i rivenditori possono utilizzare la funzionalità del libro del cliente per aiutare i collaboratori del negozio a stabilire relazioni a lungo termine con i clienti chiave.

Il libro clienti include le schede cliente che mostrano le informazioni di contatto per ciascun cliente, insieme a tre altre proprietà che sono definite dal rivenditore e configurate in Headquarters. I rivenditori possono decidere le tre cose più importanti che i venditori devono sapere sui clienti. Ad esempio, un rivenditore di gioielli potrebbe voler includere date importanti come anniversari o compleanni, perché queste date sono occasioni in cui le persone potrebbero acquistare gioielli. Allo stesso modo, un rivenditore di articoli di moda potrebbe voler includere gli interessi e i marchi di acquisto preferiti dal cliente.

Il libro clienti consente inoltre agli addetti alle vendite di filtrare l'elenco in modo da mostrare solo i clienti che soddisfano criteri specifici. Ad esempio, una nuova collezione di scarpe è arrivata nel negozio e un addetto vuole informare i clienti a cui piace comprare le scarpe. In questo caso, l'addetto può filtrare il libro clienti per trovare i clienti rilevanti e quindi intraprendere ulteriori azioni.

Se per qualche motivo i clienti non vengono più considerati clienti chiave e pertanto non devono essere gestiti da vicino, gli addetti alle vendite possono rimuoverli dal libro clienti.

Alcuni rivenditori non desiderano gestire i clienti a livello di addetto alle vendite. Vogliono invece gestire un elenco dei clienti chiave a livello di punto vendita. I rivenditori possono visualizzare i clienti dai libri clienti del punto vendita. Utilizzando questa opzione, i rivenditori possono visualizzare i clienti dai libri clienti di tutti gli addetti alle vendite la cui rubrica corrisponde alla rubrica del negozio corrente. In questo modo, se un addetto lavora in più negozi della persona giuridica, il libro clienti mostra i clienti di tutti quei negozi. Questa funzionalità supporta funzionalità aggiuntive. Ad esempio, i clienti possono essere riassegnati da un addetto a un altro. Questa funzionalità è utile se gli addetti vengono trasferiti o lasciano la società.

Ogni addetto alle vendite può avere un libro clienti per persona giuridica e gli addetti possono aggiungere uno o più clienti al libro clienti. In Commerce, ogni cliente attualmente può essere aggiunto a un solo libro clienti. Tuttavia, Microsoft prevede di aggiungere funzionalità che consentono di aggiungere un singolo cliente a più libri clienti.

> [!NOTE]
> Diversamente dalla ricerca del cliente, il libro clienti non consente di filtrare i record del cliente in base alle rubriche del punto vendita.

## <a name="activities-and-notes"></a>Attività e note

I canali online offrono ai rivenditori modi di conoscere le preferenze dei clienti senza richiedere che i clienti forniscano esplicitamente queste informazioni. Al contrario, quando i clienti interagiscono con gli addetti alle vendite nel negozio, condividono esplicitamente le informazioni sulle loro preferenze. Sfortunatamente, queste informazioni possono andare perse al termine della vendita. Tuttavia, se queste informazioni vengono registrate, possono aiutare i rivenditori a comprendere meglio i clienti e quindi aiutarli a fornire consigli migliori e una migliore esperienza di acquisto complessiva.

Per acquisire le informazioni critiche condivise dai clienti, gli addetti alle vendite possono utilizzare non solo gli attributi del libro clienti, ma anche la funzionalità delle attività e delle note. I rivenditori possono configurare i tipi di attività, come le informazioni sulla visita del negozio, l'indirizzo e-mail, il numero di telefono e gli appuntamenti. Le attività create dagli addetti possono essere visualizzate in un formato di sequenza temporale nel punto vendita (POS). È inoltre possibile visualizzarle nella scheda **Attività** della pagina **Tutti i clienti \> Generale** in Headquarters.

Gli addetti alle vendite possono anche utilizzare le note per acquisire informazioni generiche sui clienti a cui è possibile fare riferimento prima di ogni interazione. Queste note vengono salvate in Headquarters e possono essere visualizzate nel profilo del cliente o nella pagina dei dettagli del cliente del call center.

> [!NOTE]
> Attualmente, tutte le note e le attività possono essere visualizzate da qualsiasi addetto alle vendite che lavora per la persona giuridica e può visualizzare le pagine dei dettagli del cliente. Le note e le attività non si limitano all'addetto che ha aggiunto un cliente al libro clienti.

## <a name="integration-with-dynamics-365-customer-insights"></a>Integrazione con Dynamics 365 Customer Insights

Con l'applicazione Dynamics 365 Customer Insights, i rivenditori possono aggregare i dati dei vari sistemi utilizzati dai clienti per interagire con il marchio del rivenditore. Possono quindi utilizzare questi dati per generare un'unica vista del cliente e ricavare informazioni dettagliate. L'integrazione di Customer Insights con Commerce consente ai rivenditori di selezionare una o più misure che devono essere mostrate sulla scheda cliente nel libro clienti. Ad esempio, i rivenditori possono utilizzare i dati in Customer Insights per calcolare la "probabilità di abbandono" per un cliente e definire la "migliore azione successiva". Se questi valori sono definiti come misure, possono essere mostrati sulla carta del cliente e possono fornire informazioni cruciali ai venditori. Per ulteriori informazioni su Customer Insights, vedere la documentazione [Dynamics 365 Customer Insights](/dynamics365/ai/customer-insights/overview). Per ulteriori informazioni sulle misure, vedere [Misure](/dynamics365/ai/customer-insights/pm-measures).

## <a name="set-up-clienteling"></a>Impostare la fidelizzazione dei clienti

Per attivare la funzionalità di fidelizzazione dei clienti nel proprio ambiente, attenersi alla seguente procedura.

1. Nell'area di lavoro **Gestione funzionalità**, filtrare le funzionalità dal modulo **Vendita al dettaglio e commercio**.

    ![Fidelizzazione dei clienti nell'elenco delle funzionalità per il modulo Commercio.](./media/Enable_clienteling.png "Fidelizzazione dei clienti nell'elenco delle funzionalità per il modulo Vendita al dettaglio e commercio")

2. Attivare la funzionalità **Fidelizzazione dei clienti** selezionando **Abilita ora**.
3. Nella pagina **Parametri di commercio**, nella scheda **Sequenza numerica**, selezionare la riga **Identificatore del libro clienti**. Nel campo **Codice sequenza numerica** selezionare una sequenza numerica. Il sistema utilizzerà questa sequenza numerica per assegnare un ID ai libri clienti.
4. Selezionare **Salva**.
5. Creare un nuovo gruppo di attributi che contiene gli attributi che si desidera acquisire per i clienti gestiti nei libri clienti. Per istruzioni, vedere [Attributi e gruppi di attributi](./attribute-attributegroups-lifecycle.md).

    - Definire gli attributi richiesti come **Ridefinizione possibile**. Gli addetti alle vendite possono quindi utilizzare questi attributi per filtrare il libro clienti.
    - Impostare l'ordine di visualizzazione di questi attributi. Questo ordine di visualizzazione determina quali attributi devono essere mostrati sulla scheda cliente nel libro clienti. Un ordine di visualizzazione di 1 verrà considerato superiore a un ordine di visualizzazione di 2. Pertanto, l'attributo che ha un ordine di visualizzazione di 1 verrà mostrato prima dell'attributo che ha un ordine di visualizzazione di 2.

    > [!NOTE]
    > È possibile rendere disponibile Customer Insights dalla stessa pagina. Tuttavia, è necessario creare un ID applicazione e un segreto di Azure, a fini dell'autenticazione. Per informazioni sui requisiti, vedi la sezione [Attivare l'integrazione di Customer Insights con Commerce](#turn-on-the-integration-of-customer-insights-with-commerce) più avanti in questo articolo. Se Customer Insights è abilitato e si seleziona una o più misure che devono essere visualizzate nella scheda cliente, tali misure verranno visualizzate per prime. Successivamente, verranno visualizzati i gruppi di attributi del libro clienti, in base all'ordine di visualizzazione. Ad esempio, se si selezionano due misure da Customer Insights, queste due misure e un attributo del libro clienti verranno visualizzati sulla scheda cliente. L'attributo libro clienti visualizzato sarà l'attributo con l'ordine di visualizzazione più elevato.

6. Nella pagina **Parametri di commercio**, nella scheda **Fidelizzazione dei clienti**, nel campo **Gruppo di attributi del libro clienti**, selezionare il gruppo di attributi appena creato.

    ![Gruppo di attributi del libro clienti selezionato.](./media/Client%20book%20attributes.png "Gruppo di attributi del libro clienti selezionato")

7. Per acquisire le attività eseguite al POS, definire i tipi di attività nella pagina **Tipi di attività** (**Retail e Commerce \> Clienti \> Tipi di attività**).

    > [!NOTE]
    > I tipi di attività vengono estratti da Commerce Scale Unit quando effettua per la prima volta una chiamata in tempo reale. Dopo che le attività vengono acquisite, vengono memorizzate nella cache per alcune ore. Se si modificano i tipi di attività, attendere finché la cache non sia più valida. In alternativa, per gli ambienti non di produzione, riavviare il servizio Commerce Scale Unit.

8. Aggiungere due pulsanti al layout dello schermo POS appropriato, in modo che gli addetti alle vendite possano visualizzare il libro clienti e il libro clienti del negozio. I libri dei clienti del negozio includono i clienti di tutti i libri clienti di tutti gli addetti che condividono una rubrica con il negozio. Le operazioni corrispondenti sono denominate **Visualizza clienti nel libro clienti** e **Visualizza clienti dai libri clienti del negozio**, rispettivamente. Sono disponibili tre operazioni aggiuntive correlate ai libri clienti. Queste operazioni determinano quali addetti possono aggiungere, rimuovere e riassegnare i clienti dal libro clienti. Sono denominate **Aggiungi cliente al libro clienti**, **Rimuovi clienti dal libro clienti** e **Riassegna clienti a un libro clienti**, rispettivamente.
9. Eseguire i seguenti processi di programmazione di distribuzione: 1040, 1150, 1110 e 1090.

Dopo aver completato questa procedura, gli addetti alle vendite possono aprire la pagina dei dettagli del cliente nel POS e aggiungere clienti al libro clienti, visualizzare e acquisire attività e note per i clienti e indirizzare i clienti utilizzando gli attributi del cliente e del libro clienti per filtrare il libro clienti. Nella figura seguente viene illustrato un esempio di un libro clienti.

![Esempio di un libro clienti.](./media/client_book.png "Esempio di un libro clienti")

## <a name="turn-on-the-integration-of-customer-insights-with-commerce"></a>Attivare l'integrazione di Customer Insights con Commerce

Per attivare l'integrazione di Customer Insights con Commerce, è necessario assicurarsi di disporre di un'istanza attiva di Customer Insights nel tenant in cui viene eseguito il provisioning di Commerce. È inoltre necessario disporre di un account utente Azure Active Directory (Azure AD) con una sottoscrizione Azure.

Seguire questi passaggi per configurare l'integrazione.

1. Nel portale di Azure registra una nuova applicazione e prendi nota del nome dell'applicazione, dell'ID dell'applicazione e del segreto. Queste informazioni verranno utilizzate per l'autenticazione da servizio a servizio tra Commerce e Customer Insights. Annota il segreto in modo sicuro, poiché sarà necessario salvarlo nell'insieme di credenziali delle chiavi. Per il seguente esempio, utilizza CI_Access_name, CI_Access_AppID, CI_Access_Secret rispettivamente per il nome dell'applicazione, l'ID dell'applicazione e il segreto. Per altre informazioni, vedi [Avvio rapido: Registrare un'applicazione con la piattaforma di identità di Microsoft](/azure/active-directory/develop/quickstart-register-app).

    > [!IMPORTANT]
    > Intraprendere le azioni in modo da ricordare di cambiare il segreto prima che scada. In caso contrario, l'integrazione verrà interrotta in modo imprevisto.

2. Vai alla tua istanza Customer Insights e cerca il nome dell'applicazione creata sopra (in questo esempio, "CI_Access_name").
3. Crea un insieme di credenziali delle chiavi di Azure e prendi nota del nome e dell'URL (in questo esempio, "KeyVaultName", "KeyVaultURL"). Per istruzioni, vedere [Avvio rapido: Impostare e recuperare un segreto da Azure Key Vault tramite il portale di Azure](/azure/key-vault/quick-create-portal).
4. Salva il segreto (in questo esempio, "CI_Access_Secret") nell'insieme di credenziali. Quando questo segreto viene archiviato nell'insieme di credenziali, il segreto ottiene un nome. Annota il nome del segreto (in questo esempio, "SecretName").
5. Per accedere al segreto dall'Insieme di credenziali delle chiavi di Azure, è necessario creare un'altra applicazione con un ID applicazione e un segreto (in questo esempio, "KeyVault_Access_AppID" e "KeyVault_Access_Secret"). Annota il segreto in modo sicuro, poiché non verrà più visualizzato.
6. Successivamente, concedi le autorizzazioni all'applicazione per accedere all'insieme di credenziali delle chiavi da Commerce utilizzando le API. Nel portale di Azure vai alla pagina dell'applicazione. Sotto la sezione **Gestione** seleziona **Autorizzazioni API**. Aggiungi l'autorizzazione per accedere all'**Insieme di credenziali delle chiavi di Azure**. Per questa autorizzazione, seleziona **Criteri di accesso**. Seleziona il modello come **Gestione segreto** e seleziona le opzioni **Ottieni**, **Elenco**, **Decrittografa** e **Crittografa**. 
5. In Commerce Headquarters, passa a **Amministrazione sistema \> Impostazione \> Parametri Key Vault** e immetti le informazioni necessarie per l'insieme di credenziali delle chiavi. Quindi nel campo **Client Key Vault**, immettere l'ID applicazione utilizzato nel passaggio 4, in modo che Commerce possa accedere ai segreti nel Key Vault.
6. Per aggiungere l'applicazione creata al passaggio 1 all'elenco di applicazioni sicure (a volte indicato come elenco sicuro), vai a Customer Insights e fornisci l'accesso **Visualizzazione** all'applicazione. Per istruzioni, vedere [Autorizzazioni](/dynamics365/ai/customer-insights/pm-permissions).
7. Nella pagina **Amministrazione di sistema > Impostazione > Parametri insieme di credenziali delle chiavi** in Commerce HQ, aggiorna i campi come descritto di seguito: 

- **URL insieme di credenziali delle chiavi**: "KeyVaultURL" (dal passaggio 3 sopra).
- **Client insieme di credenziali delle chiavi** : "KeyVault_Access_AppID" (dal passaggio 5 precedente).
- **Chiave segreta insieme di credenziali delle chiavi** : "KeyVault_Access_Secret" (dal passaggio 5 precedente).
- Sotto la sezione **Segreti**:
    - **Nome**: Qualsiasi nome, ad esempio "CISecret".
    - **Descrizione**: Qualsiasi valore.
    - **Segreto**: **insieme di credenziali**:`//<Name of key vault>/<name of secret>>` in questo esempio sarà `vault://KeyVaultName/SecretName`.

Dopo aver aggiornato i campi, seleziona **Convalida** per garantire che il segreto sia accessibile dall'applicazione Commerce.

8. In Commerce, nella pagina **Parametri di Commerce** nella scheda **Clientela** nella scheda dettaglio **Dynamics 365 Customer Insights** imposta **ID applicazione** su "CI_Access_AppID" (dal passaggio 1 sopra). Per **Nome segreto**, seleziona il nome del segreto inserito al passaggio 7 sopra ("CISecret"). Impostare l'opzione **Abilita Customer Insights** su **Sì**. Se l'impostazione per qualsiasi motivo non riesce, viene visualizzato un messaggio di errore e questa opzione viene impostata su **No**. 

È possibile avere più ambienti in Customer Insights, ad esempio ambienti di produzione e test. Nel campo **ID istanza dell'ambiente**, immettere l'ambiente appropriato. Nel campo **ID cliente alternativo**, immettere la proprietà in Customer Insights mappata al numero del conto del cliente (In Commerce, il numero di conto del cliente è l'ID del cliente.) Le tre proprietà rimanenti sono le misure che verranno mostrate sulla scheda cliente nel libro clienti. È possibile selezionare fino a tre misure da visualizzare nella scheda cliente. Tuttavia, non è necessario selezionare alcuna misura. Come accennato in precedenza, il sistema mostra prima questi valori, quindi mostra i valori per il gruppo di attributi del libro clienti.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
