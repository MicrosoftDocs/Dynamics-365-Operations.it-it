---
title: Memorizzare il modulo di selezione
description: In questo articolo viene descritto il modulo selettore punto vendita e la procedura per aggiungerlo alle pagine del sito in Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 05/18/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2020-02-10
ms.dyn365.ops.version: ''
ms.custom: ''
ms.assetid: ''
ms.search.industry: ''
manager: annbe
ms.openlocfilehash: aa3aed837072cb6c3d4f7f92bec2f4b700408cf7
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9268342"
---
# <a name="store-selector-module"></a>Memorizzare il modulo di selezione

[!include [banner](includes/banner.md)]

In questo articolo viene descritto il modulo selettore punto vendita e la procedura per aggiungerlo alle pagine del sito in Microsoft Dynamics 365 Commerce.

I clienti possono utilizzare il modulo di selezione del punto vendita per ritirare un prodotto in un punto vendita selezionato dopo un acquisto online. In Commerce versione 10.0.13, il modulo di selezione del punto vendita include anche funzionalità aggiuntive che possono mostrare una pagina **Trova un punto vendita** pagina che mostra i punti vendita vicini.

Il modulo di selezione del punto vendita consente agli utenti di inserire una posizione (città, stato, indirizzo e così via) per cercare punti vendita all'interno di un raggio di ricerca. Quando il modulo viene aperto per la prima volta, utilizza la posizione del browser del cliente per trovare i punti vendita (se viene fornito il consenso).

## <a name="store-selector-module-usage"></a>Utilizzo del modulo di selezione del punto vendita

- Un modulo di selezione del punto vendita può essere utilizzato in una pagina dei dettagli del prodotto per selezionare un punto vendita per il ritiro.
- Un modulo di selezione del punto vendita può essere utilizzato in una pagina del carrello per selezionare un punto vendita per il ritiro.
- Un modulo di selezione del punto vendita può essere utilizzato in una pagina autonoma che mostra tutti i punti vendita disponibili.

## <a name="fulfillment-group-setup-in-commerce-headquarters"></a>Configurare gruppi di evasione in Commerce Headquarters

Affinché il modulo di selezione del punto vendita visualizzi i punti vendita disponibili, il gruppo di evasione deve essere impostato in Commerce Headquarters. Per ulteriori informazioni, vedere [Impostare gruppi di evasione](customer-orders-overview.md#set-up-fulfillment-groups).

Inoltre, per ogni punto vendita nel gruppo di evasione, la latitudine e la longitudine dell'ubicazione del punto vendita devono essere definite in Commerce Headquarters.

Per immettere i valori di latitudine e longitudine per l'ubicazione di un punto vendita in Commerce Headquarters, procedere come segue.

1. Selezionare **Gestione inventario \> Impostazioni \> Suddivisione scorte**.
1. Selezionare l'ubicazione del magazzino nel riquadro a sinistra.
1. Nella Scheda dettaglio **Indirizzi**, selezionare **Avanzate**.

    ![Esempio di dettagli del punto vendita in Commercial Headquarters.](./media/Store-address.png)

1. Nel riquadro azioni, seleziona **Modifica**.
1. Nella Scheda dettaglio **Generale**, immettere i valori per **Latitudine** e **Longitudine**.

    ![Esempio di configurazione di latitudine e longitudine per un punto vendita in Commercial Headquarters.](./media/Store-latitude-longitude.png)

1. Nel riquadro azioni selezionare **Salva**. 

### <a name="hide-a-store-from-the-store-selector-module"></a>Nascondere un punto vendita dal modulo di selezione del punto vendita

Alcuni punti vendita in un gruppo di evasione ordini potrebbero non essere luoghi di ritiro validi. Per assicurarti che solo i punti di ritiro validi vengano visualizzati come opzioni nel modulo di selezione del punto vendita, segui questi passaggi in Commerce headquarters.

1. Accedere a **Retail e Commerce \> Impostazione commercio \> Gruppi di adempimento \> Tutti i punti vendita**.
1. Nel riquadro azioni, seleziona **Modifica**.
1. In **Impostazione**, per ogni punto vendita che non è un punto di ritiro valido, deseleziona la casella di controllo **Ubicazione di prelievo**.
1. Nel riquadro azioni selezionare **Salva**.
1. Eseguire il processo di programmazione della distribuzione 1070 **Configurazione canale**.

## <a name="bing-maps-integration"></a>Integrazione di Bing Maps

Il modulo di selezione del punto vendita è integrato nelle [interfacce di programmazione delle applicazioni REST (API) di Bing Maps](/bingmaps/rest-services/) per utilizzare le funzionalità di geocodifica e suggerimenti automatici di Bing. È richiesta una chiave API di Bing Maps che deve essere aggiunta alla pagina Parametri condivisi di commercio in Commerce Headquarters. L'API di geocodifica viene utilizzata per convertire una posizione in valori di latitudine e longitudine. L'integrazione con l'API Suggerimenti automatici viene utilizzata per mostrare suggerimenti di ricerca quando gli utenti immettono posizioni nel campo di ricerca.

Per l'API REST Suggerimenti automatici, è necessario assicurarsi che i seguenti URL siano consentiti in base ai criteri di sicurezza dei contenuti del sito. Questa configurazione viene eseguita durante la creazione del sito di Commerce, aggiungendo gli URL consentiti a varie direttive CSP per il sito (ad esempio, **img-src**). Per altre informazioni, vedere [Criteri di sicurezza dei contenuti](manage-csp.md). 

- Alla direttiva **connect-src**, aggiungere **&#42;bing.com**.
- Alla direttiva **img-src**, aggiungere **&#42; virtualearth.net**.
- Alla direttiva **script-src**, **aggiungere &#42;.bing.com, &#42;.virtualearth.net**.
- Alla direttiva **script style-src**, aggiungere **&#42;.bing.com**.

## <a name="pickup-in-store-mode"></a>Modalità Preleva nel punto vendita

Il modulo di selezione del punto vendita supporta una modalità **Preleva nel punto vendita** che mostra un elenco di punti vendita in cui un prodotto è disponibile per il ritiro. Mostra anche gli orari del punto vendita e le scorte di prodotto per ciascun punto vendita nell'elenco. Il modulo di selezione del punto vendita richiede il contesto di un prodotto per eseguire il rendering della disponibilità del prodotto e per consentire all'utente di aggiungere il prodotto al carrello, se la modalità di consegna del prodotto è impostata su **Preleva** nel punto vendita selezionato. Per ulteriori informazioni, vedere [Impostazioni relative alle scorte](inventory-settings.md). 

Il modulo di selezione del punto vendita può essere aggiunto a un modulo casella acquisti su una pagina dei dettagli del prodotto (PDP) per visualizzare i punti vendita in cui un prodotto è disponibile per il ritiro. Può anche essere aggiunto a un modulo carrello. In questo caso, il modulo di selezione del punto vendita mostra le opzioni di ritiro per ciascuna voce di articolo nel carrello. Il modulo di selezione del punto vendita può essere aggiunto ad altre pagine o moduli tramite estensioni e personalizzazioni.

Affinché lo scenario funzioni, i prodotti devono essere configurati in modo da utilizzare la modalità di consegna **ritiro**. Altrimenti, il modulo non verrà mostrato nelle pagine del prodotto. Per altre informazioni su come configurare la modalità di consegna, vedere [Impostare le modalità di consegna](/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery).

L'immagine seguente mostra un esempio di un modulo selettore punto vendita utilizzato su un PDP.

![Esempio di un modulo selettore punto vendita utilizzato su un PDP.](./media/BOPIS.PNG)

> [!NOTE]
> Nella versione 10.0.16 e successive, è possibile abilitare una nuova funzionalità che consente a un'organizzazione di definire più modalità di ritiro delle opzioni di consegna per i clienti.  Se questa funzione è abilitata, il selettore punto vendita e altri moduli di e-commerce verranno migliorati per consentire all'acquirente di scegliere tra potenzialmente più opzioni di consegna del ritiro, se configurate.  Per saperne di più su questa funzione, fare riferimento a [questa documentazione](./multiple-pickup-modes.md). 

## <a name="find-stores-mode"></a>Modalità Trova punti vendita

Il modulo di selezione del punto vendita supporta anche una modalità **Trova punti vendita**. Questa modalità può essere utilizzata per creare una pagina delle posizioni dei punti vendita che mostra i punti vendita disponibili e le loro informazioni. In questa modalità, il modulo di selezione del punto vendita funziona senza contesto di prodotto e può essere utilizzato come modulo autonomo su qualsiasi pagina del sito. Inoltre, se le impostazioni pertinenti sono attivate per il modulo, gli utenti possono selezionare un punto vendita come preferito. Quando un punto vendita viene selezionato come preferito dell'utente, l'ID punto vendita viene mantenuto nel cookie del browser. Pertanto, l'utente deve accettare un messaggio di consenso per i cookie.

La seguente illustrazione mostra un esempio di un modulo di selezione del punto vendita utilizzato insieme a un modulo mappa in una pagina con le posizioni dei punti vendita.

![Esempio di un modulo di selezione del punto vendita e un modulo di mapping su una pagina delle posizioni dei punti vendita.](./media/ecommerce-Storelocator.PNG)

## <a name="render-a-map"></a>Eseguire il rendering di una mappa

Il modulo di selezione del punto vendita può essere utilizzato insieme al modulo mappa per mostrare le posizioni dei punti vendita su una mappa. Per ulteriori informazioni sul modulo mappa, vedere [Modulo mappa](map-module.md).

## <a name="store-selector-module-properties"></a>Proprietà del modulo selettore punto vendita

| Nome proprietà | Valore | Descrizione |
|---------------|-------|-------------|
| Intestazione | Testo | L'intestazione del modulo. |
| Modo | **Trova punti vendita** o **Preleva al punto vendita** | La modalità **Trova punti vendita** mostra i punti vendita disponibili. La modalità **Preleva al punto vendita** consente agli utenti di selezionare un punto vendita per il ritiro. |
| Stile | **Finestra di dialogo** o **In linea** | Il rendering del modulo può essere effettuato in linea o in una finestra di dialogo. |
| Imposta come punto vendita preferito | **True** o **False** | Quando questa proprietà è impostata su **Vero**, gli utenti possono impostare un punto vendita preferito. Questa funzionalità richiede che gli utenti accettino un messaggio di consenso per i cookie. |
| Visualizza tutti i punti vendita | **True** o **False** | Quando questa proprietà è impostata su **Vero**, gli utenti possono ignorare la proprietà **Raggio di ricerca** e visualizzare tutti i punti vendita. |
| Opzioni di suggerimenti automatici: risultati massimi | Numero | Questa proprietà definisce il numero massimo di risultati di suggerimenti automatici che possono essere visualizzati tramite l'API Suggerimenti automatici di Bing. |
| Raggio di ricerca | Numero | Questa proprietà definisce il raggio di ricerca dei punti vendita, in miglia. Se non viene specificato alcun valore, viene utilizzato il raggio di ricerca predefinito, ovvero 50 miglia. |
| Condizioni d'uso | URL |  Questa proprietà specifica l'URL delle condizioni d'uso necessario per utilizzare il servizio Bing Maps. |

## <a name="site-settings"></a>Impostazioni sito

Il modulo selettore punto vendita rispetta le [Impostazioni Aggiungi prodotto a carrello](add-cart-settings.md). Dopo l'aggiunta di un articolo al carrello dal modulo selettore punto vendita, gli utenti del sito vedranno i flussi di lavoro configurati appropriati.

## <a name="add-a-store-selector-module-to-a-page"></a>Aggiungere un modulo selettore punto vendita a una pagina

Per la modalità **Preleva nel punto vendita**, il modulo può essere utilizzato solo su PDP e pagine del carrello. È necessario impostare la modalità su **Preleva nel punto vendita** nel riquadro delle proprietà del modulo.

- Per informazioni su come aggiungere un modulo modulo selettore punto vendita a un modulo di acquisto, vedere [Modulo casella acquisti](add-buy-box.md). 
- Per informazioni su come aggiungere un modulo modulo selettore punto vendita a un modulo carrello, vedere [Modulo carrello](add-cart-module.md).

Per configurare il modulo di selezione del punto vendita in modo da mostrare i punti vendita disponibili per una pagina delle posizioni dei punti vendita, come nell'illustrazione che appare in precedenza in questo articolo, attieniti alla seguente procedura.

1. Andare a **Modelli** e selezionare **Nuovo** per creare un nuovo modello.
1. Nella finestra di dialogo **Nuovo modello**, sotto **Nome modello**, immetti **Modello di marketing**, quindi seleziona **OK**.
1. Selezionare **Salva**, selezionare **Fine modifica** per archiviare il modello, quindi selezionare **Pubblica** per pubblicarlo.
1. Accedi a **Pagine** e quindi seleziona **Nuovo** per creare una nuova pagina.
1. Nella finestra di dialogo **Crea una nuova pagina**, sotto **Nome pagina**, immetti **Ubicazioni punti vendita**, quindi seleziona **Avanti**.
1. Sotto **Scegli un modello**, seleziona il **modello di marketing** creato e seleziona **Avanti**.
1. Sotto **Scegli un layout**, seleziona un layout di pagina (ad esempio, **Layout flessibile**), quindi seleziona **Avanti**.
1. Sotto **Verifica e termina**, rivedi la configurazione della pagina. Se è necessario modificare le informazioni sulla pagina, seleziona **Indietro**. Se le informazioni sulla pagina sono corrette, seleziona **Crea pagina**. 
1. Nello slot **Principale** della nuova pagina, seleziona i puntini di sospensione (**...**) e quindi **Aggiungi modulo**.
1. Nella finestra di dialogo **Seleziona moduli** selezionare il modulo **Contenitore** e quindi **OK**.
1. Nello slot **Contenitore** seleziona i puntini di sospensione (**...**) quindi seleziona **Aggiungi modulo**.
1. Nella finestra di dialogo **Seleziona moduli** seleziona il modulo **Contenitore con 2 colonne** e quindi **OK**.
1. Nel riquadro delle proprietà del modulo, impostare il valore **Larghezza** su **Riempi contenitore**.
1. Impostare il valore **Configurazione colonna porte di visualizzazione molto piccole** su **100%**.
1. Impostare il valore **Configurazione colonna porte di visualizzazione piccole** su **100%**.
1. Impostare il valore **Configurazione colonna porte di visualizzazione medie** su **33% 67%**.
1. Impostare il valore **Configurazione colonna porte di visualizzazione grandi** su **33% 67%**.
1. Nello slot **Contenitore con 2 colonne** seleziona i puntini di sospensione (**...**), quindi seleziona **Aggiungi modulo**.
1. Nella finestra di dialogo **Seleziona moduli** seleziona il modulo **Selettore punto vendita** e quindi seleziona **OK**.
1. Nel riquadro delle proprietà del modulo, impostare il valore **Modalità** su **Trova punti vendita**.
1. Impostare il valore di **Raggio di ricerca** in miglia.
1. Impostare altre proprietà, ad esempio **Imposta come punto vendita preferito**, **Mostra tutti i punti vendita** e **Abilita suggerimento automatico** in base alle tue esigenze.
1. Nello slot **Contenitore con 2 colonne** seleziona i puntini di sospensione (**...**), quindi seleziona **Aggiungi modulo**.
1. Nella finestra di dialogo **Seleziona moduli** seleziona il modulo **Mappa** e quindi **OK**.
1. Nel riquadro delle proprietà del modulo, impostare tutte le proprietà aggiuntive di cui si ha bisogno.
1. Selezionare **Salva**, selezionare **Fine modifica** per archiviare la pagina, quindi selezionare **Pubblica** per pubblicarla.
 
## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica della libreria dei moduli](starter-kit-overview.md)

[Modulo casella acquisti](add-buy-box.md)

[Modulo carrello](add-cart-module.md)

[Demo veloce di PDP](quick-tour-pdp.md)

[Demo veloce di carrello e check out](quick-tour-cart-checkout.md)

[Imposta la modalità di consegna](/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery)

[Gestire Bing Mappe per la tua organizzazione](dev-itpro/manage-bing-maps.md)

[API REST Bing Maps](/bingmaps/rest-services/)

[Modulo mappe](map-module.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
