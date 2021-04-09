---
title: Impostazione del riconoscimento ricavi
description: In questo argomento vengono descritte le opzioni di impostazione per il riconoscimento ricavi e le loro implicazioni.
author: kweekley
ms.date: 08/24/2018
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: Customer
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 8.0.4
ms.openlocfilehash: 294ad788c97850880b479d3c3c44cc19d55e9a6e
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5837155"
---
# <a name="revenue-recognition-setup"></a>Impostazione del riconoscimento ricavi
[!include [banner](../includes/banner.md)]

È stato aggiunto un nuovo modulo di **Riconoscimento ricavi** che include le voci di menu per qualsiasi impostazione richiesta. In questo argomento vengono descritte le opzioni di impostazione e le loro implicazioni.

> [!NOTE]
> Il riconoscimento ricavi non può essere attivato tramite Gestione funzionalità. Per attivarlo, attualmente è necessario utilizzare le chiavi di configurazione.

> Il riconoscimento dei ricavi, inclusa la funzionalità aggregazione, non è supportato per l'utilizzo nei canali di Commerce (e-commerce, POS, servizio clienti). Gli articoli configurati con il riconoscimento dei ricavi non devono essere aggiunti agli ordini o alle transazioni creati nei canali di Commerce.

Il modulo **Riconoscimento ricavi** contiene le seguenti opzioni di impostazione:

- Giornali di registrazione del riconoscimento ricavi
- Parametri per il riconoscimento ricavi
- Programmazione ricavi 
- Impostazione scorte

    - Gruppi di articoli e prodotti rilasciati
    - Definizione della programmazione ricavi
    - Definizione del prezzo dei ricavi

        - Registrazione dei profili
        - Aggregazioni

    - Componenti di aggregazione
    - Articolo di aggregazione

- Impostazione progetto

## <a name="revenue-recognition-journals"></a>Giornali di registrazione del riconoscimento ricavi

È stato introdotto un nuovo tipo di giornale di registrazione per il riconoscimento ricavi. Il giornale di registrazione è obbligatorio e viene utilizzato in due scenari.

Il primo scenario si verifica dopo aver soddisfatto tutti gli obblighi contrattuali, quando i ricavi differiti vengono riconosciuti tramite la creazione di un giornale di registrazione per il riconoscimento ricavi basato sui dettagli della programmazione dei ricavi. Il giornale di registrazione contiene una voce contabile che trasferisce il saldo del conto CoGe dei ricavi differiti sul conto CoGe dei ricavi.

Il secondo scenario si verifica quando il giornale di registrazione viene creato dopo la riallocazione. La riallocazione si verifica quando una riga ordine cliente viene aggiunta a un ordine cliente fatturato in precedenza oppure quando viene creato un nuovo ordine cliente contenente una riga che fa parte del contratto originale. Se una fattura è stata registrata prima di aggiungere la nuova riga ordine cliente, è necessario creare una voce contabile di correzione per la fattura cliente registrata.

Il giornale di registrazione viene impostato nella pagina **Nomi giornale di registrazione** (**Riconoscimento ricavi \> Impostazione \> Nomi giornale di registrazione**). Il tipo di giornale di registrazione deve essere impostato su **Riconoscimento ricavi**. Il giornale di registrazione per il riconoscimento ricavi consente di selezionare il livello di registrazione in cui effettuare la registrazione.

## <a name="parameters-for-revenue-recognition"></a>Parametri per il riconoscimento ricavi

Le impostazioni del riconoscimento ricavi vengono configurate nella scheda **Riconoscimento ricavi** della pagina **Parametri di contabilità generale** (**Riconoscimento ricavi \> Impostazione \> Parametri di contabilità generale**). Sono disponibili le impostazioni seguenti:

- **Nome giornale di registrazione del riconoscimento ricavi**: consente di selezionare il giornale di registrazione creato per il riconoscimento ricavi. Il giornale di registrazione è obbligatorio quando i ricavi vengono riconosciuti dalla programmazione dei ricavi oppure quando si effettua la riallocazione per un ordine cliente che è già stato fatturato.
- **Attiva metodo di allocazione sconto**: impostare questa opzione su **Sì** per determinare il prezzo dei ricavi tramite l'allocazione del valore equo di mercato definito nel prezzo dei ricavi per ogni prodotto rilasciato. Questa procedura prevede l'allocazione di tutti gli sconti riga per gli articoli. Se l'opzione è impostata su **No**, il sistema utilizza il prezzo mediano definito nel prezzo dei ricavi per ogni prodotto rilasciato. Se l'opzione è impostata su **No**, ma non è impostato alcun prezzo mediano per i prodotti rilasciati, l'allocazione del prezzo dei ricavi non verrà eseguita.
- **Includi sconti intestazione**: impostare questa opzione su **Sì** per determinare il prezzo dei ricavi dagli sconti intestazione per i prodotti. Se questa opzione è impostata su **No**, lo sconto intestazione non è incluso nell'allocazione del prezzo dei ricavi.
- **Disabilita termini del contratto**: impostare questa opzione su **Sì** se i prodotti con ricavi del tipo **Supporto contratti registrati** possono essere rilasciati anche se le date di inizio e fine del contratto non sono definite. In genere, le date di inizio e fine del contratto sono necessarie per gli articoli del tipo di ricavi **Supporto contratti registrati**. Quando le date di inizio e fine del contratto non sono specificate, i dettagli della programmazione dei ricavi nella registrazione vengono calcolati utilizzando il numero di occorrenze e la data della fattura.
- **Correzioni delle fatture registrate in contabilità clienti durante la riallocazione**: quando si esegue la riallocazione per le fatture che sono già state registrate, è necessario correggere la voce contabile della fattura registrata. Utilizzare questa opzione per specificare come viene effettuata la correzione.

    - Impostare questa opzione su **No** per limitare la registrazione della transazione di correzione nella contabilità generale. Quando l'opzione è impostata su **No**, non viene creato alcun documento aggiuntivo nella contabilità clienti per la correzione contabile interna. Al pagamento della fattura, il processo di liquidazione utilizza la vecchia voce contabile per registrare tutti gli sconti di cassa, nonché i profitti o le perdite realizzati.
    - Impostare questa opzione su **Sì** per creare automaticamente un documento di storno e una nuova fattura per la transazione di correzione nella contabilità clienti. Poiché si tratta di una correzione contabile interna, i nuovi documenti non vengono inviati o comunicati al cliente. Il documento di storno viene liquidato in base alla fattura originale e la nuova fattura corretta viene pagata dal cliente. Tutti e tre i documenti vengono visualizzati nei report, ad esempio nel rendiconto cliente.

[![Informazioni di impostazione](./media/revenue-recognition-setup-info.png)](./media/revenue-recognition-setup-info.png)

## <a name="revenue-schedules"></a>Programmazione ricavi

La programmazione dei ricavi deve essere creata per ogni occorrenza in cui i ricavi possono essere differiti. Ad esempio, se l'organizzazione offre il servizio clienti per periodi di 6, 12, 18 e 24 mesi, è necessario creare una programmazione dei ricavi per ogni periodo. L'impostazione della programmazione dei ricavi determina la modalità di allocazione del prezzo dei ricavi per il numero di periodi selezionato. Determina, inoltre, le date predefinite che vengono immesse per la programmazione dei ricavi creata quando viene registrata la fattura.

Se i ricavi vengono riconosciuti per fase, si consiglia di creare una programmazione di riconoscimento ricavi per il numero di fasi, indipendentemente dalle date di riconoscimento. Dopo aver creato le programmazioni, è possibile modificarle in modo che riflettano le date previste per le fasi. Questi record possono essere messi in attesa fino alla notifica che conferma l'avvenuto completamento della fase e la possibilità di effettuare il riconoscimento ricavi.

Le programmazioni dei ricavi vengono create nella pagina **Programmazioni ricavi** (**Riconoscimento ricavi \> Impostazione \> Programmazioni ricavi**).

[![Programmazioni ricavi](./media/revenue-recognition-revenue-schedules.png)](./media/revenue-recognition-revenue-schedules.png)

Immettere valori descrittivi nei campi **Programmazione ricavi** e **Descrizione**. Le seguenti impostazioni aggiuntive vengono utilizzate per creare la programmazione dei ricavi quando viene registrata la fattura.

- **Occorrenze**: immettere il numero di mesi o di occorrenze per il differimento dei ricavi.
- **Sospensione automatica**: selezionare questa casella di controllo per mettere automaticamente in attesa tutte le righe della programmazione dei ricavi quando viene registrata la fattura. La sospensione deve essere rimossa manualmente da ogni riga della programmazione prima del riconoscimento dei ricavi differiti della riga.
- **Termini del contratto automatici**: selezionare questa casella di controllo per impostare automaticamente le date di inizio e fine del contratto. Queste date vengono impostate automaticamente solo per i prodotti rilasciati del tipo di ricavi **Supporto contratti registrati**. La data di inizio del contratto viene impostata automaticamente sulla data di spedizione richiesta nella riga ordine cliente e la data di fine del contratto viene impostata automaticamente sulla data di inizio più il numero di mesi o di occorrenze definito nelle impostazioni della programmazione dei ricavi. Ad esempio, il prodotto nella riga ordine cliente è per una garanzia di un anno. La programmazione predefinita dei ricavi è di **12M** (12 mesi) e la casella di controllo **Termini del contratto automatici** è selezionata per tale programmazione. Se la riga ordine cliente ha come data di spedizione richiesta il 16 dicembre 2019, la data predefinita di inizio del contratto è il 16 dicembre 2019 e la data predefinita di fine del contratto è il 15 dicembre 2020.
- **Base di riconoscimento**: la base di riconoscimento determina il modo in cui il prezzo dei ricavi viene allocato tra le occorrenze.

    - **Ogni mese in base alle date**: l'importo è allocato in base ai giorni effettivi di ogni mese.
    - **Ogni mese**: l'importo è allocato equamente tra il numero di mesi definito nelle occorrenze.
    - **Occorrenze**: l'importo è allocato equamente tra le occorrenze, ma può includere un periodo supplementare se si seleziona **Data di inizio effettiva** come convenzione di riconoscimento.

- **Convenzione di riconoscimento**: la convenzione di riconoscimento determina le date predefinite che vengono impostate nella programmazione dei ricavi per la fattura.

    - **Data di inizio effettiva**: la programmazione è creata utilizzando la data di inizio del contratto (per gli articoli \[PCS\] di supporto contratti registrati) o la data della fattura (per gli articoli essenziali e non indispensabili).
    - **Giorno 1 del mese**: la data della prima riga della programmazione è la data di inizio del contratto (o data della fattura). Tuttavia, tutte le righe successive della programmazione sono create per il primo giorno del mese.
    - **Divisione a metà mese**: la data della prima riga della programmazione dipende dalla data della fattura. Se la fattura viene registrata nei primi quindici giorni del mese, la programmazione dei ricavi viene creata utilizzando il primo giorno del mese. Se la fattura viene registrata dal sedicesimo giorno in poi, la programmazione dei ricavi viene creata utilizzando il primo giorno del mese successivo.
    - **Giorno 1 del mese successivo**: la data della programmazione è il primo giorno del mese successivo.

Selezionare il pulsante **Dettagli programmazione ricavi** per visualizzare i periodi generali e le percentuali riconosciute in ogni periodo. Per impostazione predefinita, il valore **Riconosci percentuale** è suddiviso equamente tra il numero di periodi. Se la base di riconoscimento è impostata su **Ogni mese** o su **Occorrenze**, la percentuale di riconoscimento può essere modificata. Quando si modifica la percentuale di riconoscimento, un messaggio di avviso notifica che il totale non è uguale al 100 per cento. Se si riceve il messaggio, si può continuare a modificare le righe. Tuttavia, la percentuale totale deve essere uguale a 100 prima di chiudere la pagina.

[![Dettagli programmazione ricavi](./media/revenue-recognition-revenue-schedule-details.png)](./media/revenue-recognition-revenue-schedule-details.png)

## <a name="inventory-setup"></a>Impostazione scorte

Se il documento non include articoli, è possibile riconoscere i ricavi per i prodotti rilasciati negli ordini cliente, ma non per le categorie di vendita negli ordini cliente o per le fatture a testo libero. Le selezioni effettuate quando si impostano i prodotti rilasciati determinano il modo in cui vengono riconosciuti i ricavi dell'articolo. Ad esempio, consentono di determinare se il prezzo dei ricavi viene allocato e se i ricavi vengono differiti utilizzando una programmazione dei ricavi.

L'impostazione può iniziare dalla Scheda dettaglio **Riconoscimento ricavi** della pagina **Gruppo di articoli** (**Riconoscimento ricavi \> Impostazione \> Scorte e impostazione prodotto \> Gruppo di articoli**). In questa pagina sono disponibili vari campi di configurazione. Questi campi vengono utilizzati per impostare i valori predefiniti solo per i nuovi prodotti rilasciati che vengono creati nel sistema. Quando si creano nuovi prodotti, i valori definiti in questo campo sono inseriti per impostazione predefinita per il gruppo di articoli. È possibile sostituire i valori predefiniti per i prodotti rilasciati nella pagina **Prodotti rilasciati** (**Riconoscimento ricavi \> Impostazione \> Scorte e impostazione prodotto \> Prodotti rilasciati**). I valori predefiniti impostati per i prodotti rilasciati vengono quindi riportati nell'ordine cliente.

## <a name="item-groups-and-released-products"></a>Gruppi di articoli e prodotti rilasciati

### <a name="define-the-revenue-schedule"></a>Definire la programmazione dei ricavi

I ricavi nella riga ordine cliente vengono differiti se per il prodotto rilasciato viene definita una programmazione dei ricavi utilizzata per impostazione predefinita nella riga ordine cliente. Se per il prodotto viene utilizzata l'impostazione predefinita, è possibile definire la programmazione dei ricavi nella Scheda dettaglio **Riconoscimento ricavi** della pagina **Gruppo di articoli** (**Riconoscimento ricavi \> Impostazione \> Scorte e impostazione prodotto \> Gruppo di articoli**). È inoltre possibile definire l'impostazione per il prodotto rilasciato nella Scheda dettaglio **Riconoscimento ricavi** della pagina **Prodotti rilasciati** (**Riconoscimento ricavi \> Impostazione \> Impostazione scorte \> Prodotti rilasciati**).

Nel campo **Programmazione ricavi**, selezionare la programmazione dei ricavi che rappresenta il periodo in cui devono essere differiti. La programmazione dei ricavi è inserita automaticamente nella riga ordine cliente e i dettagli della programmazione vengono creati quando viene registrata la fattura.

### <a name="define-the-revenue-price"></a>Definire il prezzo dei ricavi

I gruppi di articoli e i prodotti rilasciati possono essere impostati utilizzando il metodo del prezzo mediano o il metodo dell'allocazione sconto. Entrambi i metodi richiedono varie impostazioni nella pagina **Prodotti rilasciati**:

- **Allocazione ricavi attiva**: impostare questa opzione su **Sì** per includere il prodotto rilasciato nel calcolo di allocazione dei ricavi. Se l'opzione è impostata su **No**, il prodotto rilasciato utilizza il metodo del prezzo mediano se tale prezzo è specificato. Se il prezzo mediano non è specificato, per la registrazione nei ricavi o nei ricavi differiti viene utilizzato il prezzo unitario nella riga ordine cliente.
- **Tipo di ricavi**: selezionare il tipo di ricavi che definisce il prodotto rilasciato:

    - **Essenziale**: l'articolo è una fonte primaria dei ricavi di un'organizzazione. Questo valore è l'impostazione predefinita.
    - **Non indispensabile**: l'articolo non è una fonte primaria dei ricavi di un'organizzazione. Quando si utilizzano le impostazioni del prezzo mediano, il prezzo è calcolato in base al prezzo mediano ed è quindi allocato. Ad esempio, un articolo essenziale ha un prezzo fisso che deve essere riconosciuto per i ricavi. Se è previsto uno sconto, questo può essere ottenuto dai ricavi di un articolo essenziale, ma **solo** fino all'importo del prezzo fisso. Lo sconto restante è ottenuto dai ricavi per gli articoli non indispensabili. Non è invece possibile ottenere lo sconto dai ricavi di un articolo essenziale.
    - **Supporto contratti registrati**: l'articolo supporta altri elementi inclusi nella vendita al cliente. Il prezzo dei ricavi viene distribuito tra i prodotti essenziali e non indispensabili inclusi nella vendita. A seconda delle impostazioni, è possibile che per gli articoli PCS non sia necessario definire la data di inizio e fine del contratto nella riga ordine cliente.

- **Escludi dal calcolo**: impostare questa opzione su **Sì** per indicare che il prezzo mediano dell'articolo non può essere regolato su un importo inferiore alla percentuale minima specificata o superiore alla percentuale massima. Il prezzo dei ricavi viene ricavato dal prezzo dei ricavi di un altro prodotto rilasciato che è incluso nell'ordine cliente. Se l'opzione è impostata su **No**, è possibile rettificare o calcolare il prezzo mediano dell'articolo. Se si vendono più articoli con prezzo mediano, l'opzione **Escludi dal calcolo** deve essere impostata su **No** per almeno un prodotto rilasciato. In questo modo, è disponibile almeno un articolo a cui è possibile allocare tutte le differenze del prezzo dei ricavi.
- **Prezzo mediano**: impostare questa opzione su **Sì** per indicare che il prezzo dei ricavi dell'articolo deve essere rettificato in modo che equivalga al prezzo mediano se inferiore alla tolleranza minima specificata o superiore alla tolleranza massima e che l'importo calcolato deve essere allocato nelle righe con prodotti in cui l'opzione **Escludi dal calcolo** è impostata su **No**.

    - **Tolleranza massima**: immettere la percentuale consentita superiore al prezzo mediano.
    - **Tolleranza minima**: immettere la percentuale consentita inferiore al prezzo mediano.

Dopo aver configurato le impostazioni per il prodotto rilasciato, è necessario definire manualmente il prezzo dei ricavi immettendo il prezzo di valore equo o il prezzo mediano (quando si utilizza il metodo del prezzo mediano) nella pagina **Prezzi dei ricavi** (andare a **Riconoscimento ricavi \> Impostazione \> Impostazione scorte \> Prodotti rilasciati**, quindi, nel riquadro Azioni, nella scheda **Vendi**, nel gruppo **Riconoscimento ricavi**, selezionare **Prezzi dei ricavi**).

[![Prezzi dei ricavi](./media/revenue-recognition-revenue-prices.png)](./media/revenue-recognition-revenue-prices.png)

Il prezzo dei ricavi definito manualmente in questa pagina viene utilizzato per determinare l'allocazione dei prezzo dei ricavi in ogni ordine cliente, in base ai criteri definiti. Ogni criterio viene abbinato alla riga ordine cliente per determinare il prezzo dei ricavi da utilizzare nel processo di allocazione.

- **Codice articolo** e **Relazione articolo**: il prezzo dei ricavi può essere definito per un singolo prodotto o per un gruppo di prodotti. Se si seleziona **Tabella** nel campo **Codice articolo**, selezionare il prodotto rilasciato nel campo **Relazione articolo**. Se si seleziona **Gruppo** nel campo **Codice articolo**, selezionare il gruppo di articoli nel campo **Relazione articolo**.
- **Codice conto** e **Numero conto/gruppo**: il prezzo dei ricavi può essere definito per tutti i clienti, per un singolo cliente o per un gruppo di clienti. Se si seleziona **Tutti** nel campo **Codice conto**, il prezzo viene utilizzato per tutti i clienti. Se si seleziona **Tabella** nel campo **Codice conto**, selezionare il cliente nel campo **Numero conto/gruppo**. Se si seleziona **Gruppo** nel campo **Codice conto**, selezionare il gruppo di clienti nel campo **Numero conto/gruppo**.
- **Valuta**: è necessario immettere un prezzo dei ricavi separato per ogni valuta in cui è espresso un ordine cliente. Ad esempio, se attualmente si effettuano vendite in dollari statunitensi, dollari canadesi ed euro, è necessario definire un prezzo dei ricavi in tutte e tre le valute. Il prezzo dei ricavi non viene convertito da una valuta, ad esempio la valuta di contabilizzazione, ad altre valute di transazione utilizzate.
- **Importo o percentuale listino**: consente di specificare se il prezzo dei ricavi è impostato su un importo o su una percentuale del prezzo di listino. Se si seleziona **Percentuale listino**, gli utenti possono immettere il prezzo mediano come percentuale del prezzo di listino anziché come un importo. Il valore di **Percentuale listino** viene utilizzato solo per i prodotti rilasciati che vengono impostati come articoli PCS.
- **Prezzo di allocazione ricavi**: in base al valore selezionato nel campo **Importo o percentuale listino**, immettere un importo o una percentuale per rappresentare il prezzo dei ricavi utilizzato per allocare i ricavi tra gli elementi dell'ordine cliente.
- **Dal** e **Al**: immettere l'intervallo di date in cui il prezzo dei ricavi è attivo. Questi campi sono facoltativi.

Se l'opzione **Attiva metodo di allocazione sconto** nella pagina **Parametri di contabilità generale** è impostata su **Sì** e se il campo **Tipo di ricavi** per il prodotto rilasciato è impostato su **Supporto contratti registrati**, è necessario specificare anche gli articoli supportati dal prodotto rilasciato. Questa impostazione viene effettuata nella pagina **Base impostazione** (andare a **Riconoscimento ricavi \> Impostazione \> Impostazione scorte \> Prodotti rilasciati**, quindi nel riquadro Azioni, nella scheda **Vendi**, nel gruppo **Riconoscimento ricavi**, selezionare **Base impostazione**).

Nella pagina **Base impostazione**, aggiungere un record per ogni gruppo di articoli supportato dall'articolo. Quando si effettua l'allocazione dei ricavi, il prezzo dei ricavi viene distribuito tra le parti essenziali e non indispensabili per l'articolo PCS.

### <a name="posting-profiles"></a>Registrazione dei profili

Sono disponibili tre tipi di registrazione aggiuntivi che consentono di differire i ricavi. Questi tipi di registrazione sono impostati nella scheda **Ordine cliente** della pagina **Registrazione** (**Riconoscimento ricavi \> Impostazione \> Scorte e impostazione prodotto \> Registrazione**).

- **Ricavi differiti**: immettere il conto principale per il prezzo dei ricavi che effettua registrazioni dei ricavi differiti (anziché dei ricavi). Il prezzo dei ricavi viene differito se nella riga ordine cliente è disponibile una programmazione dei ricavi.
- **Costo del venduto differito**: immettere il conto principale per l'importo del costo del venduto che effettua registrazioni del costo del venduto differito nel caso in cui anche i ricavi siano differiti.
- **Compensazione parziale dei ricavi fattura**: immettere il conto principale per il conto di compensazione utilizzato quando l'ordine cliente è fatturato parzialmente o quando viene effettuata la riallocazione. Il saldo del conto torna a essere 0 (zero) quando gli ordini cliente sono completamente fatturati.

### <a name="bundles"></a>Aggregazioni

Gli articoli di aggregazione sono prodotti rilasciati univoci, impostati in modo tale da includere i componenti. Questa impostazione viene effettuata utilizzando la funzionalità della distinta base (DBA). Quando si inserisce un articolo di aggregazione in un ordine cliente, i singoli componenti vengono utilizzati per determinare i prezzi dei ricavi e la programmazione dei ricavi. Tuttavia, i documenti stampati per il cliente, ad esempio l'ordine cliente e la fattura, riportano l'articolo di aggregazione.

#### <a name="bundle-components"></a>Componenti di aggregazione

I componenti inclusi nell'aggregazione devono essere impostati nella pagina **Prodotti rilasciati** (**Riconoscimento ricavi \> Impostazione \> Scorte e impostazione prodotto \> Prodotti rilasciati**). Questi componenti sono prodotti rilasciati e devono essere impostati allo stesso modo dei prodotti inclusi in una DBA. Ad esempio, un prodotto rilasciato può essere un articolo del tipo **Articolo** o del tipo **Servizio**, ma deve essere assegnato a un gruppo di modelli di articoli in cui l'opzione **Prodotto stoccato** è impostata su **Sì**. Per ulteriori informazioni, vedere la documentazione relativa all'impostazione per gli articoli DBA.

I componenti devono inoltre essere impostati per il riconoscimento ricavi, come se fossero prodotti che possono essere venduti singolarmente in un ordine cliente. Ad esempio, verificare che il prezzo dei ricavi venga definito correttamente per ogni componente e che la base del prezzo sia impostata per gli articoli PCS.

#### <a name="bundle-items"></a>Articoli di aggregazione

Quando si imposta un articolo di aggregazione, è necessario configurare due campi nella pagina **Prodotti rilasciati** (**Riconoscimento ricavi \> Impostazione \> Scorte e impostazione prodotto \> Prodotti rilasciati**):

- Nella Scheda dettaglio **Progetta**, nel campo **Tipo di produzione**, l'articolo deve essere impostato come un articolo DBA.
- Nella Scheda dettaglio **Generale**, nel campo **Aggregazione**, l'articolo deve essere contrassegnato come un articolo di aggregazione.

I componenti devono quindi essere assegnati all'articolo padre di aggregazione/DBA nella pagina **Versioni DBA** (andare a **Riconoscimento ricavi \> Impostazione \> Scorte e impostazione prodotto \> Prodotti rilasciati**, quindi nel riquadro Azioni, nella scheda **Progetta**, nel gruppo **DBA**, selezionare **Versioni DBA**). Per ulteriori informazioni, vedere la documentazione relativa all'impostazione per le DBA.

[![Prodotti rilasciati, programmazioni DBA](./media/revenue-recognition-bom-scheduleds.jpg)](./media/revenue-recognition-bom-scheduleds.jpg)

Se l'articolo padre di aggregazione e i componenti di aggregazione sono impostati per l'allocazione, il prezzo dei ricavi di aggregazione viene distribuito ai componenti in base alle percentuali del contributo ricavi.

## <a name="project-setup"></a>Impostazione progetto

Il riconoscimento ricavi può anche essere utilizzato per gli ordini cliente creati con un progetto di tempistica e materiali. Per gli ordini cliente originati dai progetti, è necessario definire solo i conti principali nei profili di registrazione progetto utilizzati per registrare le fatture di progetto. I conti principali vengono definiti nella pagina **Impostazione registrazione contabile** (**Riconoscimento ricavi \> Impostazione \> Impostazione progetto \> Impostazione registrazione contabile**).

- **Ricavi fattura differiti** (in **Conti ricavi**): immettere il conto principale per il prezzo dei ricavi che effettua registrazioni dei ricavi differiti (anziché dei ricavi). Il prezzo dei ricavi viene differito se nella riga ordine cliente è disponibile una programmazione dei ricavi.
- **Costo differito** (in **Conti costi**): immettere il conto principale per l'importo del costo del venduto che effettua registrazioni del costo del venduto differito nel caso in cui anche i ricavi siano differiti.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]