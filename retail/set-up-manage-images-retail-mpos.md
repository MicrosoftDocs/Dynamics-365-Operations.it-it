---
title: Consente di impostare e gestire le immagini per il POS moderno al dettaglio
description: "L&quot;articolo vengono descritti i passaggi inclusi nelle immagini dell&quot;impostazione e sulla gestione delle varie entità visualizzate nel POS moderno al dettaglio MPOS ()."
author: MargoC
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 52851
ms.assetid: 5c21385e-64e0-4091-98fa-6a662eb33010
ms.search.region: global
ms.search.industry: Retail
ms.author: athinesh
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: dbcf6d2ca3a6009c1631636309ff55cebb0551e6
ms.lasthandoff: 03/31/2017


---

# <a name="set-up-and-manage-images-for-retail-modern-pos"></a>Consente di impostare e gestire le immagini per il POS moderno al dettaglio

L'articolo vengono descritti i passaggi inclusi nelle immagini dell'impostazione e sulla gestione delle varie entità visualizzate nel POS moderno al dettaglio MPOS ().

<a name="setting-up-the-media-base-url-and-defining-media-templates-to-configure-the-format-for-image-urls"></a>Impostazione dell'URL di base multimediale e definizione dei modelli media per la configurazione del formato per gli URL dell'immagine
-------------------------------------------------------------------------------------------------

Le immagini visualizzate nel POS moderno al dettaglio (MPOS devono essere ospitate esternamente, Microsoft Dynamics esterno 365 per le operazioni al dettaglio. In genere, sono ospitate in un sistema di gestione dei contenuti, una rete per la distribuzione di contenuti (CDN, Content Delivery Network) di consegna o in un server media. MPOS quindi recupera e visualizza le immagini per le entità appropriate, ad esempio prodotti e cataloghi, accedendo all'URL di destinazione. Per recuperare le immagini ospitate esternamente, MPOS richiede un formato corretto per l'URL delle immagini. È possibile configurare il formato URL richiesto per le immagini impostando il valore **URL di base multimediale **nel profilo del canale e utilizzando la funzionalità **Definisci modello media **per ogni entità. È inoltre possibile sovrascrivere il formato standard dell'URL per un sottoinsieme di entità utilizzando la funzionalità **Modifica in Excel**. ** Nota importante: ** Nella versione corrente di Dynamics 365 per le operazioni, non è più possibile impostare il formato di URL utilizzando ** immagine ** XML di attributo per MPOS ** standard ** nel gruppo per le entità. Se si ha dimestichezza con Microsoft Dynamics AX 2012 R3 e ora si utilizza la versione corrente di Dynamics 365 per le operazioni, assicurarsi di utilizzare sempre la nuova ** definire il modello di media ** funzionalità per impostare le immagini. Non utilizzare o non modificare l'attributo **Immagine** nel gruppo di attributi **Predefinito** per alcuna entità, inclusi i prodotti. Le modifiche apportate direttamente nel gruppo di attributi **Predefinito** per le immagini non verranno applicate. Questa opzione verrà disabilitata in una versione successiva. Nelle procedure indicate di seguito, le immagini vengono impostate per l'entità del catalogo come esempio. Queste procedure contribuiranno a garantire che il percorso di destinazione dell'immagine corretto venga impostato in modo implicito per tutte le immagini del catalogo che utilizzano un percorso comune. Ad esempio, se è stato impostato un server media o un CDN esternamente e si desidera che le immagini vengano visualizzate in MPOS per un punto vendita specifico, la funzione **Definisci modello media** consente di impostare il percorso in cui MPOS può recuperare le immagini. **Nota**: per questo esempio di dati dimostrativi, il server media viene distribuito nel server Retail. Tuttavia, è possibile avere esterno in Dynamics 365 per le operazioni.

### <a name="set-up-the-media-base-url-for-a-channel"></a>Impostare gli URL di base multimediale per un canale

1.  Avviare Dynamics 365 per il portale HQ delle operazioni.
2.  ** Fare clic su Retail e il commercio ** &gt; ** Manica Impostazioni ** &gt; ** profili di Manica **. ![[] (channel-profile1. /media/channel-profile1.png)](. /media/channel-profile1.png)
3.  Nel profilo del canale che il punto vendita utilizza per MPOS, aggiornare il campo **URL di base multimediale** con l'URL di base del media server o CDN. Base URL è la prima parte dell'URL restituito è condiviso da tutte le cartelle di immagine di entità differenti.![[] (channel-profile2. /media/channel-profile2.png)](. /media/channel-profile2.png)

### <a name="define-the-media-template-for-an-entity"></a>Definire il modello media per un'entità

1.  ** Fare clic su Retail e il commercio ** &gt; ** gestione catalogo ** &gt; ** immagine del catalogo **.
2.  Nella pagina **Immagini di catalogo**, nel Riquadro azioni fare clic su **Definisci modello media**. Nella finestra di dialogo **Definisci modello media**, nel campo **Entità** il valore **Catalogo** deve essere selezionato per impostazione predefinita.
3.  Nella scheda dettaglio **Percorso media** immettere il percorso rimanente della posizione dell'immagine. Il percorso media supporta **LanguageID** come variabile. Ad esempio, per i dati dimostrativi, è possibile creare una cartella **Cataloghi** per tutte le immagini del catalogo nell'URL di base multimediale per il server media (https://testax3ret.cloud.test.dynamics.com/RetailServer/MediaServer). È quindi possibile creare una cartella per ciascuna lingua, ad esempio en-US o fr-FR e copiare le immagini appropriate in ogni cartella. Se non si dispone di immagini diverse per le varie lingue, è possibile omettere la variabile **LanguageID** dalla struttura di cartelle e puntare direttamente alla cartella dei cataloghi che contiene le immagini del catalogo. **Nota**: la versione corrente di Dynamics AX supporta il token **{LanguageId}** per le entità catalogo, prodotto e categoria. (Il token **{LanguageID}** non è supportato per le entità lavoratore e cliente, in base allo standard esistente che è stato valido a partire dalla versione Microsoft Dynamics AX 6.x).
4.  Per le immagini, il formato del nome file è hardcoded al catalogo e non può essere modificato. Di conseguenza, rinominare le immagini in modo che abbiano nomi di catalogo appropriati, per garantire che MPOS possa gestirli in modo corretto.
5.  Nel campo **Estensione del file** selezionare l'estensione del nome file prevista, a seconda del tipo delle immagini di cui si dispone. Ad esempio, per i dati dimostrativi, le immagini di catalogo sono impostate con estensione .jpg. (I file di immagine sono anche rinominati in modo da avere nomi di catalogo.)
6.  Click **OK**.
7.  Per verificare che il modello media per le immagini sia stato salvato correttamente, nella pagina **Immagini di catalogo** fare di nuovo clic su **Definisci modello media**. Per convalidare il modello senza chiudere la finestra di dialogo **Definisci modello media**, è possibile utilizzare la scheda dettaglio **Genera URL immagine per Excel**. Controllare l'aspetto dell'URL di immagine e verificare che URL sia conforme al modello citato in precedenza. Tramite la finestra di dialogo **Definisci modello media** è stato ora impostato il percorso immagine in modo implicito per tutte le immagini di catalogo che utilizzano il percorso URL comune. Questo percorso URL viene applicato a tutte le immagini di catalogo, a meno che non vengano sovrascritte. La prima parte del percorso immagine viene ricavata dall'URL di base multimediale definito nel profilo del canale. La parte restante del percorso viene ricavata dal percorso definito nel modello di media. Le due parti sono concatenate per fornire l'URL completo del percorso di immagine. Ad esempio, un catalogo dei dati dimostrativi è denominato Fabrikam Base Catalog. Di conseguenza, il nome di immagine dovrà essere Fabrikam Base Catalog.jpg in modo che venga utilizzato il nome di catalogo e l'estensione file .jpg configurata nel modello. In questo caso, dopo la concatenazione, l'URL apparirà come https://testax3ret.cloud.test.dynamics.com/RetailServer/MediaServer/Catalogs/en-US/Fabrikam Base Catalog.jpg.
8.  Eseguire i processi di sincronizzazione per eseguire il push del nuovo modello nel database del canale, in modo che MPOS possa utilizzare il modello per accedere alle immagini.
9.  Per aggiornare il modello di media per le immagini catalogo dal lato di canale, assicurarsi di cataloghi ** eseguire il processo 1150 ** ** IT al dettaglio ** &gt; ** dalla programmazione di distribuzione **.![[] (catalog1. /media/catalog1.png)](. /media/catalog1.png)

## <a name="previewing-an-image-from-the-entity-level"></a>Visualizzare in anteprima un'immagine dal livello dell'entità
1.  Nella pagina per l'elemento entità in Sede centrale, è possibile visualizzare in anteprima l'URL immagine derivato dal modello media. Per questo esempio, visita il catalogo appropriato, quindi nel riquadro azioni, fare clic su ** media ** &gt; ** immagine **. Utilizzare l'elenco a discesa per selezionare i diversi punti vendita che potrebbero avere diversi profili di canale.
2.  Per modificare o rimuovere i modelli media impliciti, è necessario tornare alla finestra di dialogo **Definisci modello media** per la pagina **Immagini di catalogo**.
3.  È possibile utilizzare i pulsanti **Aggiungi** e **Rimuovi** per modificare manualmente il percorso basato sul modello implicito e utilizzato per un'immagine specifica. Per ulteriori informazioni, vedere la sezione "Sovrascrittura del modello media per gli elementi entità" più avanti in questo articolo.
4.  Al termine di visualizzare l'anteprima di un'immagine e di apportare modifiche desiderato, avviare l'istanza di MPOS per il punto vendita appropriata e vedere se i prodotti del catalogo vengono visualizzate.![[] (catalog4. /media/catalog4.png)](. /media/catalog4.png)

**Nota**: è possibile utilizzare la stessa procedura per tutte cinque le entità supportate: lavoratore, cliente, catalogo, categoria e prodotti. Le entità "prodotti di catalogo" (prodotti impostati a livello di catalogo) e "prodotti di canale" (prodotti impostati a livello di canale) utilizzano il modello media che è impostato per l'entità prodotti. Per il modello media prodotti, è possibile selezionare il numero delle immagini del prodotto da visualizzare per prodotto. È inoltre possibile impostare l'immagine predefinita per un prodotto specifico. In questo modo, è possibile impedire che vengano visualizzate immagini vuote in MPOS e controllare quale immagine viene utilizzata come predefinita per un articolo di tipo prodotto. Nel seguente esempio, ogni prodotto dispone di cinque immagini e la prima immagine viene impostata come immagine predefinita. Le varianti di prodotto vengono gestite nello stesso modo dei prodotti principali. Il nome file del file di immagine deve essere basato sul numero di prodotto. Alcuni caratteri vengono anche utilizzati come caratteri di escape nella generazione del nome file. Pertanto, è opportuno verificare il nome file tramite la sezione **Genera URL immagine per Excel**. [pungoli![(]. /media/prods.png)](. /media/prods.png)  

## <a name="synchronization-jobs-to-send-a-media-template-to-the-channel-side"></a>Processi di sincronizzazione per l'invio di un modello media al canale
Per tutti i cinque è supportato le entità (operaio, Cliente, catalogo, categoria e prodotti), ogni volta che sono state aggiornate ** definire il modello di media ** dialogate per impostare un'immagine, si garantisce che si allontanaste il processo di catalogo (1150) ** IT al dettaglio ** &gt; ** dalla programmazione di distribuzione **. Questo processo abiliterà il modello media aggiornato da sincronizzare nel canale e da utilizzare utilizzato in MPOS. Eseguire il processo di catalogo (1150) dopo aver apportato una delle seguenti modifiche:

-   Aggiornare il modello di supporto di immagine del catalogo da ** immagine del catalogo ** &gt; ** definire il modello di media **.
-   Aggiornare il modello di media di l dipendente per ** immagine del dipendente ** &gt; ** definire il modello di media **.
-   Aggiornare il modello di supporto di immagine del cliente da ** immagine del cliente ** &gt; ** definire il modello di media **.
-   Aggiornare il modello di supporto di immagine di prodotti da ** immagini dei prodotti ** &gt; ** definire il modello di media **.
-   Aggiornare il modello di supporto di immagine di categoria da ** immagini di categoria ** &gt; ** definire il modello di media **. È inoltre possibile pubblicare il canale.

## <a name="overwriting-the-media-template-for-entity-items"></a>Sovrascrittura del modello media per gli elementi entità
Come illustrato nella sezione precedente, il modello media per un'entità specifica supporta solo un percorso comune. Questo percorso si basa sull'URL di base multimediale configurato e sul percorso media definito. Tuttavia, in molti casi, il rivenditore desidera poter utilizzare le immagini da origini diverse per un sottoinsieme degli articoli in un'entità. Ad esempio, un punto vendita utilizza il media server indipendente per un set di immagini di catalogo ma usa URL CDN per un altro insieme. Per sovrascrivere gli URL delle immagini basati su un modello media per le immagini dell'entità a livello di entità, è possibile utilizzare le funzionalità Modifica in Excel e di modifica manuale nella pagina **Anteprima**.

### <a name="overwrite-by-using-edit-in-excel"></a>Sovrascrivere utilizzando Modifica in Excel

1.  ** Fare clic su Retail e il commercio ** &gt; ** gestione catalogo ** &gt; ** immagine del catalogo **.
2.  Nella pagina **Immagini di catalogo** fare clic su **Definisci modello media**. Nella finestra di dialogo **Definisci modello media**, nel campo **Entità** deve essere selezionato il valore **Catalogo**.
3.  Nella scheda dettaglio **Percorso di media** prendere nota della posizione dell'immagine.
4.  Nella scheda dettaglio **Genera URL immagine per Excel** fare clic su **Genera**. **Importante**: ogni volta che il modello media viene modificato, necessario fare clic su **Genera** prima di poter utilizzare la funzione Modifica in Excel. ![[] (excel1. /media/excel1.jpg)](. /media/excel1.jpg) Ora è presente una previsione dell'immagine URL generati in base all'ultimo modello salvato di media. ![[] (excel2. /media/excel2.png)](. /media/excel2.png) ** nota: ** Gli URL generati per l'utilizzo di Excel il percorso e le convenzioni del modello di media definito. Le convenzioni includono le convenzioni relative ai nomi file. L'aspettativa è che l'utente abbia impostato le immagini fisiche esternamente a Dynamics AX e che le immagini possano essere recuperate tramite gli URL derivati dal modello media definito in precedenza. È possibile sovrascrivere gli URL derivati utilizzando la funzionalità Modifica in Excel.
5.  Fare clic su **Modifica in Excel**.
6.  Dopo l'apertura del foglio di lavoro di Microsoft Excel, fare clic su **Abilita modifica** quando richiesto.
7.  Quando richiesto, fare clic su **Considera attendibile questo componente aggiuntivo** nel riquadro destro e attendere il completamento dell'installazione del componente aggiuntivo. [fiducia![questo componente aggiuntivo (]. /media/excel4.jpg)](. /media/excel4.jpg)
8.  Se richiesto, immettere le credenziali utilizzate per accedere alla sede centrale. [![Segno- la richiesta (]. /media/excel5.png)](. /media/excel5.png)
9.  Dopo aver eseguito l'accesso, è possibile visualizzare l'elenco degli URL di immagine per le varie voci del catalogo.
10. È possibile modificare, aggiungere e rimuovere gli URL di immagine per i vari tipi di entità.
11. Per tutte le entità ad eccezione dei prodotti, è possibile sovrascrivere gli URL di immagine. Modificare l'URL di immagine esistente in modo che venga utilizzato il nuovo URL di destinazione di immagine e aggiornare il nome file con il nuovo nome file dell'immagine. Il nome file deve essere univoco per garantire che il record sia univoco. [![sovrascrive l'immagine URL in Excel (]. /media/excel6.jpg)](. /media/excel6.jpg) ** nota: ** Se l'immagine verrà sovrascritta da URL per le entità di voce doganale utilizzando la modifica della funzionalità di Excel o nella pagina dell'entità, MPOS vengono sempre eventuali l'immagine URL del modello di media insieme all'immagine sovrascritta URL.
12. Al termine delle modifiche, fare clic su **Pubblica in Excel** per creare una nuova voce esplicita di associazione.
13. Tornare alla sede centrale e fare clic su **OK**.
14. Eseguire i processi di sincronizzazione appropriati per l'entità e controllare l'anteprima nella pagina dell'entità o in MPOS.

#### <a name="creating-new-records"></a>Creazione di nuovi record

È possibile creare nuovi record in Excel. Tuttavia, accertarsi di fornire le informazioni corrette. Ad esempio, per creare una nuova voce per un catalogo, assicurarsi che l'ID del catalogo e il nome del catalogo siano corretti e immettere un nome file univoco. Il nome file univoco è molto importante, poiché l'unicità dei record in Excel viene convalidata durante la pubblicazione. Copiare innanzitutto i dettagli dal catalogo per cui si desidera creare un nuovo record, quindi copiare il record. È sufficiente aggiornare il nome file e l'URL, poiché il resto delle informazioni sarà uguale. Per creare nuovi record per entità prodotto, seguire la stessa procedura di base. Nel foglio di lavoro di Excel, copiare un record esistente per il prodotto per cui si desidera creare un nuovo record, quindi sostituire l'URL dell'immagine e il nome file. Verificare che il nome file sia univoco.

#### <a name="deleting-an-existing-record"></a>Eliminazione di un record esistente.

Solo i record di URL di immagine sovrascritti possono essere eliminati. Dopo aver eliminato un'immagine e completato la sincronizzazione, l'immagine non verrà più visualizzata nella pagina **Anteprima**, né in MPOS. I record degli URL di immagine che vengono derivati del modello media non possono essere eliminati, poiché questi record vengono derivati sempre dal modello di media ogni volta.

### <a name="overwrite-from-the-entity-level-preview-page"></a>Sovrascrivere l'URL a livello dell'entità dalla pagina di anteprima

Per tutte le entità, ad eccezione dei prodotti, è possibile sovrascrivere l'URL dell'immagine per un entità specifica a livello di entità tramite la pagina di **Anteprima**. Per i prodotti, è possibile utilizzare la pagina dell'entità del catalogo dei prodotti. In questo esempio viene illustrato come sovrascrivere un'immagine del catalogo.

1.  Fare clic su ** cataloghi ** &gt; ** media ** &gt; ** immagine ** e selezionare l'immagine da catalogo per aggiornare.
2.  Fare clic su **Aggiungi** e immettere l'URL dell'immagine per sovrascrivere L'URL del modello media.
3.  Se si desidera visualizzare questa immagine in MPOS per il catalogo, è possibile impostarla come immagine predefinita.
4.  Scegliere **OK**. L'URL dell'immagine viene aggiornato per l'immagine del catalogo e viene visualizzata un'anteprima. ![[] (preview3. /media/preview3.png)](. /media/preview3.png)
5.  È inoltre possibile visualizzare l'anteprima di immagine per tutti gli URL di immagine sovrascritti nella pagina della raccolta di **Immagini di catalogo**.

**![[] (preview-4. /media/preview-4.png)](. Nota di /media/preview-4.png): ** Attualmente, la raccolta non vengono visualizzate le previsioni di immagine per l'immagine URL del modello di media. Per le entità di catalogo, lavoratore, cliente e categoria, se l'utente fornisce un URL in modo esplicito tramite questa pagina, si consiglia di indicare quale immagine visualizzare come immagine predefinita, poiché i client del server Retail mostrano solo un'immagine per catalogo, cliente, lavoratore e categoria. Se l'utente non specifica un'immagine predefinita, il sistema determina automaticamente l'immagine predefinita e la invia al chiamante del servizio Retail (MPOS o eCommerce).

### <a name="overwrite-the-image-url-for-catalog-product-images-from-the-preview-page"></a>Sovrascrivere l'URL di immagine per le immagini dei prodotti del catalogo dalla pagina di anteprima

Per sovrascrivere gli URL di immagine per le immagini dei prodotti del catalogo è necessario utilizzare la pagina **Anteprima**. Non è possibile utilizzare la funzionalità Modifica in Excel.

1.  Per sovrascrivere le immagini dei prodotti a livello del catalogo, selezionare un catalogo e quindi selezionare il prodotto per cui sovrascrivere l'immagine.
2.  Fare clic su **Attributi**.
3.  Nella pagina successiva, selezionare **Immagine** e quindi fare clic su **Modifica**. La pagina **Anteprima** si apre come finestra di dialogo dispositivo di scorrimento.
4.  Fare clic su **Aggiungi** e sovrascrivere l'URL di immagine con un nuovo URL.
5.  Scegliere **OK**. Si può notare ora un'anteprima della nuova immagine ed è possibile impostarla come immagine predefinita.

**![[] (cat3. /media/cat3.png)](. Nota di /media/cat3.png): ** Dopo l'associazione di l di categoria, è necessario pubblicarlo il canale ed eseguire il processo di Manica consentono di assicurarsi che le modifiche vengono pubblicati nel database del canale.

## <a name="setting-up-images-to-appear-in-offline-mode-for-mpos"></a>Impostazione delle immagini da visualizzare in modalità offline per MPOS
MPOS può essere eseguito in modalità online, se connesso al server Retail, oppure in modalità Offline, se il server Retail o la connettività di rete e le transazioni sono archiviati in un database offline locale. Quando MPOS viene eseguito in modalità offline, non può ottenere le immagini dal server esterno delle immagini per visualizzarle nel server Retail, poiché la connettività server Retail è stata persa. Tuttavia, è comunque possibile impostare le immagini in modo da visualizzarle anche quanto MPOS viene eseguito in modalità offline.

### <a name="set-up-product-images-to-appear-in-offline-mode-for-mpos"></a>Impostare le immagini di prodotto da visualizzare in modalità offline per MPOS

Le immagini dei prodotti che devono essere utilizzate in modalità non offline possono essere impostate caricando l'immagine fisica necessaria nell'immagine del prodotto di base.

1.  ** Fare clic su Gestione delle informazioni sul prodotto ** &gt; ** prodotti ** &gt; ** ** prodotti.
2.  Selezionare il prodotto per cui impostare l'immagine offline.
3.  Fare su **Modifica** e quindi sulla freccia nell'angolo a destra per visualizzare il riquadro destro.
4.  Nella scheda dettaglio **Immagine prodotto** fare clic su **Cambia immagine** e caricare l'immagine fisica da utilizzare per il prodotto selezionato per la modalità offline.
5.  Salvare e chiudere la pagina.
6.  Quando MPOS è in modalità online, eseguire il processo del catalogo nella sede centrale per assicurarsi che i dati vengano inviati almeno una volta al database offline.
7.  Attivare la modalità offline per MPOS. Si consiglia di visualizzare l'immagine caricata per il prodotto specifico nella sede centrale. ![[] (offline1. /media/offline1.png)](. /media/offline1.png)

 

### <a name="set-up-catalog-category-employee-and-customer-images-to-appear-in-offline-mode-for-mpos"></a>Impostare le immagini di catalogo, categoria, dipendente e cliente da visualizzare in modalità offline per MPOS

Le immagini di catalogo, categoria, dipendente e cliente che devono essere utilizzate in modalità offline possono essere impostate aggiungendo il collegamento di destinazione dell'immagine necessaria alla raccolta e impostando l'immagine come predefinita per l'entità selezionata.

1.  Va al catalogo, quindi nel riquadro azioni, fare clic su ** media ** &gt; ** immagine **.
2.  Seguire i passaggi elencati nella sezione **Sovrascrivere l'URL a livello dell'entità dalla pagina di anteprima** per aggiungere l'URL dell'immagine esterna.
3.  Contrassegnare questa immagine come l'immagine predefinita per il catalogo selezionando la casella di controllo dell'immagine elencata nella griglia.
4.  Eseguire il processo Catalogo. Questa immagine verrà ora utilizzata come immagine offline per il catalogo specifico in MPOS.
5.  Utilizzare un processo analogo per altre le entità, ad esempio categoria, dipendente e cliente.

![[] (offline2. /media/offline2.png)](. /media/offline2.png)    


