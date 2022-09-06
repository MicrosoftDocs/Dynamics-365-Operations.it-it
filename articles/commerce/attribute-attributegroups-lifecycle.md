---
title: Gestire attributi e gruppi di attributi
description: In questo articolo viene descritto come gestire attributi e gruppi di attributi per descrivere i prodotti e le relative caratteristiche in Microsoft Dynamics 365 Commerce.
author: ashishmsft
ms.date: 08/31/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2018-03-30
ms.openlocfilehash: aad448ea733aabdff3dc4438dcb682d49e0665c0
ms.sourcegitcommit: 09d4805aea6d148de47c8ca38d8244bbce9786ce
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/31/2022
ms.locfileid: "9386974"
---
# <a name="manage-attributes-and-attribute-groups"></a>Gestire attributi e gruppi di attributi

[!include [banner](includes/banner.md)]

In questo articolo viene descritto come gestire attributi e gruppi di attributi per descrivere i prodotti e le relative caratteristiche in Microsoft Dynamics 365 Commerce.

Gli *attributi* forniscono un modo di descrivere i prodotti e le relative caratteristiche tramite campi definiti dall'utente. Gli esempi includono la dimensione della memoria, la capacità del disco rigido e la conformità Energy Star.

Gli attributi possono essere associati a varie entità di Commerce, come ad esempio le categorie di prodotti e canali. Inoltre è possibile impostarne dei valori predefiniti. Quando gli attributi vengono associati a categorie di prodotti o canali, i prodotti ereditano quegli attributi e i relativi valori predefiniti. I valori di attributi predefiniti possono essere sostituiti a livello di singolo prodotto, a livello di canale o in un catalogo.

Ad esempio, un prodotto tipico nell'ambito dei televisori può avere i seguenti attributi.

| Categoria   | Attributo           | Valori permessi                        | Valore predefinito |
|------------|---------------------|-------------------------------------------|---------------|
| TV e video | Marchio               | Qualsiasi valore di marchio valido                     | Nessuna          |
| TV         | Dimensioni schermo         | 20-85 pollici                              | 55 pollici     |
|            | Risoluzione verticale | 4K (2160p), Full HD (1080p) o HD (720p) | 4K (2160p)    |
|            | Frequenza di aggiornamento schermo | 60 hz, 120 hz o 240 hz                     | 60 hz          |
|            | Ingressi HDMI         | 0–10                                      | 3             |

## <a name="attributes-and-attribute-types"></a>Attributi e tipi di attributo

Gli attributi si basano sui *tipi di attributo*. Un tipo di attributo identifica il tipo di dati che possono essere immessi per un attributo specifico. I seguenti tipi di attributo sono supportati in Commerce:

- **Valuta** - Questo tipo supporta un valore di valuta. Può essere associato (ovvero può supportare un intervallo di valori) oppure può essere lasciato aperto.
- **Data/ora** - Questo tipo supporta un valore di data e ora. Può essere limitato o lasciato aperto.
- **Decimale** - Questo tipo supporta un valore numerico che include posizioni decimali. Supporta anche un'unità di misura. Può essere limitato o lasciato aperto.
- **Intero** - Questo tipo supporta un valore numerico. Supporta anche un'unità di misura. Può essere limitato o lasciato aperto.
- **Testo** - Questo tipo supporta un valore di testo. Supporta anche un insieme predefinito di valori possibili quando l'impostazione **Elenco fisso** è abilitata.
- **Booleano** - Questo tipo supporta un valore binario (**true** o **false**).
- **Riferimento** - Questo tipo fa riferimento ad altri attributi.

> [!NOTE]
> A causa delle [limitazioni dell'indice di ricerca di Azure](/rest/api/searchservice/data-type-map-for-indexers-in-azure-search), il tipo di attributo **Decimale** non è supportato per le esperienze di ricerca basate sul cloud. Ricerca cognitiva di Azure non supporta la conversione dei tipi di attributo **Decimale** in tipi di campo di indice di destinazione **Edm.Double**, poiché questa conversione ridurrebbe la precisione.

### <a name="set-up-attribute-types"></a>Impostare i tipi di attributo

Per impostare i tipi di attributo, segui i passaggi in questa procedura di esempio.

1. Accedi a Commerce headquarters come responsabile del merchandising.
1. Vai a **Gestione informazioni sul prodotto \> Impostazioni \> Categorie e attributi \> Tipi di attributo**.
1. Nel Riquadro azioni selezionare **Nuovo**.
1. Nel campo **Nome tipo di attributo**, immetti **Tipo di borsa**.
1. Nel campo **Tipo** selezionare **Testo**.
1. Imposta l'opzione **Elenco fisso** su **Sì**.
1. Nella Scheda dettaglio **Valori** seleziona **Aggiungi**.
1. Nella nuova riga, nel campo **Valore**, immetti **Satchel**.
1. Aggiungi altre cinque righe. Nel campo **Valore** di ognuno, immetti un valore diverso: **Borsetta**, **Borsellino**, **Zaino**, **Borsa a tracolla** o **Portafoglio**.
1. Nel riquadro azioni selezionare **Salva**.
1. Nel Riquadro azioni selezionare **Nuovo**.
1. Nel campo **Nome tipo di attributo**, immetti **Marca di occhiali da sole**.
1. Nel campo **Tipo** selezionare **Testo**.
1. Imposta l'opzione **Elenco fisso** su **Sì**.
1. Nella Scheda dettaglio **Valori** seleziona **Aggiungi**.
1. Nella nuova riga, nel campo **Valore**, immetti **Ray ban**.
1. Aggiungi altre due righe. Nel campo **Valore** di ognuno, immetti un valore diverso: **Aviator** o **Oakley**.
1. Nel riquadro azioni selezionare **Salva**.

![Pagina Tipi di attributo.](media/AttributeType_2022Series.png)

### <a name="set-up-an-attribute"></a>Impostare un attributo

Per impostare un attributo, segui i passaggi in questa procedura di esempio.

1. Accedi a Commerce headquarters come responsabile del merchandising.
1. Vai a **Gestione informazioni sul prodotto \> Impostazioni \> Categorie e attributi \> Attributi**.
1. Nel Riquadro azioni selezionare **Nuovo**.
1. Nel campo **Nome** immetti **Tipo di borsa**.
1. Nel campo **Tipo di attributo**, seleziona **Tipo di borsa**.
1. Nel riquadro azioni selezionare **Salva**.

![Pagina Attributi.](media/Attribute_2022Series.png)

## <a name="attribute-metadata"></a>Metadati di attributi

*Metadati di attributi* consente di selezionare le opzioni per specificare come gli attributi per ogni prodotto devono comportarsi. Ad esempio, è possibile specificare se gli attributi sono obbligatori, se possono essere utilizzati per le ricerche e come filtro.

Per i prodotti, le impostazioni dei metadati di attributi possono essere sostituite a livello di canale.

La pagina **Attributi** di un attributo include varie opzioni correlate ai metadati di attributi. Ad esempio, se imposti l'opzione **Ridefinizione possibile** su **Sì** sotto **Metadati di attributi per i canali di Commerce**, l'attributo verrà mostrato per affinare o filtrare i prodotti nei risultati di ricerca e nelle pagine di navigazione delle categorie. Per configurare un attributo come affinabile, devi prima selezionare **Impostazioni filtro** nel riquadro azioni e confermare le impostazioni di filtro per l'attributo.

## <a name="filter-settings-for-attributes"></a>Impostazioni di filtro per attributi

Le impostazioni di filtro per gli attributi ti consentono di definire il modo in cui i filtri per gli attributi sono visualizzati nel POS. Per accedere alle impostazioni di filtro per un attributo, nella pagina **Attributi** dell'attributo, nel riquadro azioni, seleziona **Impostazioni filtro**.

La pagina **Impostazioni filtro** include i seguenti campi:

- **Nome** - Per impostazione predefinita, questo campo è impostato sul nome dell'attributo. È tuttavia possibile modificare tale valore.
- **Opzione di visualizzazione** - Sono disponibili le opzioni seguenti:

    - **Valore singolo** - Questa opzione è disponibile per i seguenti tipi di attributo: **Booleano**, **Valuta**, **Decimale**, **Intero** e **Testo**. Consente di selezionare un singolo valore per i criteri di affinamento nelle pagine di elenco dei prodotti, come le pagine di navigazione delle categorie e dei risultati di ricerca dei prodotti.
    - **Multi-valore** - Questa opzione è disponibile per i seguenti tipi di attributo: **Valuta**, **Decimale**, **Intero** e **Testo**. Consente la selezione di più valori per l'attributo nel client, per l'affinamento.

- **Controllo di visualizzazione** - Sono disponibili le opzioni seguenti:

    - **Elenco** - Questa opzione è disponibile per tutti i tipi di attributo.
    - **Intervallo** - Questa opzione è disponibile per i seguenti tipi di attributo: **Valuta**, **Decimale** e **Intero**.
    - **Dispositivo di scorrimento** - Questa opzione è disponibile per i seguenti tipi di attributo: **Valuta**, **Decimale** e **Intero**.
    - **Dispositivo di scorrimento con barre** - Questa opzione è disponibile per i seguenti tipi di attributo: **Valuta**, **Decimale** e **Intero**.

- **Valore di soglia** - Questa impostazione è necessaria se è stato selezionato **Intervallo** come tipo di controllo di visualizzazione. È possibile definire i valori utilizzando un punto e virgola (;) come separatore.

    Ad esempio, per un attributo **Volume borsa** che ha un tipo di attributo **Numero intero**, il valore di soglia potrebbe essere **10; 20; 50; 100; 200; 500; 1000; 5000**. In questo caso, nel POS verranno visualizzati i seguenti intervalli. Gli intervalli privi di prodotti nel set di risultati risulteranno disattivati.

    - Minore di 10
    - 10 – 20
    - 20 – 50
    - 50 – 100
    - 100 – 200
    - 200 – 500
    - 500 o più

Le impostazioni di filtro per attributi sono applicabili solo ad attributi di prodotto e possono essere utilizzate per affinare i risultati della ricerca di prodotti e di navigazione delle categorie. Non si applicano alla ricerca di clienti o di ordini, sebbene gli stessi attributi possano essere utilizzati per arricchire le informazioni su clienti o ordini.

Nei moduli di Commerce predefiniti, non è disponibile alcun supporto predefinito per le impostazioni di filtro **Controllo di visualizzazione** come **Intervallo**, **Dispositivo di scorrimento** e **Dispositivo di scorrimento con barre**. Le impostazioni **Intervallo** e **Dispositivo di scorrimento** continuano a essere supportate per le soluzioni POS, mentre l'impostazione **Dispositivo di scorrimento con barre** è applicabile alle vetrine online legacy di SharePoint per scenari personalizzati e di integrazione di terze parti.

È consigliabile che gli attributi affinabili abbiano un attributo di tipo **Testo** dove l'opzione **Elenco fisso** è abilitata e mantenere l'elenco gestibile (fino a 100–200 valori univoci). Se un criterio di affinamento avrà 1.000 o più valori univoci, è più appropriato utilizzare un attributo di tipo **Testo** dove l'opzione **Elenco fisso** è disabilitata.

Le traduzioni sono fondamentali per i nomi di attributi e i relativi valori. Per gli attributi di tipo **Testo** dove l'opzione **Elenco fisso** è abilitata, puoi definire traduzioni per valori di attributi sotto **Tipo di attributo**. Per ogni altro tipo di attributo, puoi definire le traduzioni nella pagina in cui definisci i valori di attributi. Ad esempio, per un attributo di tipo **Testo**, puoi definire le traduzioni per il valore predefinito nella pagina **Attributi** dell'attributo. Tuttavia, se sostituisci il valore predefinito a livello di prodotto, puoi definire le traduzioni per l'attributo nella pagina **Attributi del prodotto** del prodotto.

Dopo che un attributo è stato contrassegnato come affinabile per un canale, non devi aggiornare il tipo di attributo. In caso contrario, influirai sulla pubblicazione dei dati del prodotto nell'indice di ricerca. Ti consigliamo invece di creare un nuovo attributo per un nuovo tipo di criterio di affinamento e di ritirare l'attributo precedente rimuovendolo da altri gruppi di attributi.

La ricerca per attributi è supportata ma recupera i risultati solo per le corrispondenze esatte delle parole di ricerca. Ad esempio, un attributo **Tessuto** ha il valore **Cotone cashmere**. Se un cliente cerca "Cash", nessun prodotto che ha **Cotone cashmere** come tessuto verrà recuperato. Tuttavia, se un cliente cerca "Cashmere", "Cotone" o "Cotone cashmere", verranno recuperati i prodotti che hanno **Cotone cashmere** come tessuto.

### <a name="additional-attribute-metadata-options"></a>Opzioni aggiuntive per metadati di attributi

> [!NOTE]
> Queste opzioni per metadati di attributi sono applicabili solo alle integrazioni esterne e alla vetrina online legacy di SharePoint. Per ulteriori informazioni sulle opzioni per metadati di attributi, vedi [Panoramica dello schema di ricerca in SharePoint Server 2013](/SharePoint/search/search-schema-overview).

Le seguenti opzioni aggiuntive per metadati di attributi sono disponibili anche nella pagina **Attributi**:

- Ricercabile
- Recuperabile
- Esecuzione query possibile
- Classificabile
- Ignora distinzione tra maiuscole e minuscole e formato
- Corrispondenza completa

Queste opzioni sono state inizialmente progettate per migliorare le funzionalità di ricerca per le vetrina online legacy basate su SharePoint. Non si applicano necessariamente ai terminali POS o ai siti Web di e-commerce di Commerce. Poiché l'integrazione headless continua a essere supportata, queste opzioni sono disponibili per l'esportazione dei metadati di attributi tramite l'SDK (Software Development Kit) di Commerce. Puoi utilizzare l'SDK di Commerce per inserire i prodotti in un indice di ricerca esterno personalizzato e ottimizzato. In questo modo, puoi garantire che vengano indicizzati solo gli attributi che devono essere indicizzati.

## <a name="attribute-groups"></a>Gruppi di attributi

Un *gruppo di attributi* viene utilizzato per raggruppare i singoli attributi di un componente o un sottocomponente in un modello di configurazione prodotto. È possibile includere un attributo in più gruppi di attributi. I gruppi di attributi possono consentire agli utenti di configurare i prodotti, poiché le varie selezioni vengono disposte in un contesto specifico. È possibile assegnare i gruppi di attributi ai canali o alle categorie. Puoi inoltre impostare valori predefiniti per gli attributi in un gruppo di attributi.

![Pagina Gruppi di attributi.](media/AttributeGroup_2022Series.png)

### <a name="create-an-attribute-group"></a>Crea un gruppo attributi

Per creare un gruppo di attributi, segui i passaggi in questa procedura di esempio.

1. Accedi a Commerce headquarters come responsabile del merchandising.
1. Vai a **Gestione informazioni sul prodotto \> Impostazioni \> Categorie e attributi \> Gruppi di attributi**.
1. Crea un gruppo di attributi denominato **Camicia elegante**.
1. Aggiungi i seguenti attributi: **CleaningMethod**, **CollarType**, **Collection** e **Design**.

> [!NOTE]
> I valori dell'ordine di visualizzazione degli attributi nel gruppo di attributi non influiscono né si applicano all'ordine dei criteri di affinamento nei risultati di ricerca e di navigazione delle categorie. Sono applicabili solo allo scenario "attributi dell'ordine".

### <a name="assign-attribute-groups-to-categories"></a>Assegnare gruppi di attributi a categorie

Uno o più gruppi di attributi possono essere associati a nodi di categoria nei seguenti tipi di gerarchie di categorie:

- Gerarchia di prodotti di commercio
- Gerarchia di categorie di navigazione nei canali
- Gerarchia di categorie di prodotti supplementari

Quando i prodotti sono categorizzati in categorie associate a gruppi di attributi, ereditano gli attributi inclusi in quei gruppi di attributi.

![Scheda dettaglio Gruppi di attributi del prodotto nella pagina Gerarchia di prodotti di Commerce.](media/AGRetailProdHierarchy_2022Series.png)

Segui i passaggi nella procedura di esempio seguente per assegnare gruppi di attributi alle categorie nella gerarchia di prodotti di Commerce.

1. Accedi a Commerce headquarters come responsabile del merchandising.
1. Selezionare **Retail e Commerce \> Prodotti e categorie \> Gerarchia di prodotti di Commerce**.
1. Seleziona la gerarchia di navigazione **Abbigliamento**.
1. In **Uomo**, seleziona la categoria **Pantaloni**, quindi, nella scheda dettaglio **Gruppi di attributi del prodotto**, aggiungi un gruppo di attributi denominato **Cintura uomo**.
1. Selezionare la categoria **Occhiali da sole di moda**, quindi verificare i nuovi attributi nel gruppo di attributi **Occhiali da sole di moda** selezionando **Visualizza attributi**. Nel gruppo di attributi vengono visualizzati i nuovi attributi **Forma di lente** e **Marca di occhiali dal sole**.
1. Seleziona la categoria **Pantaloni** e verifica gli attributi per il gruppo di attributi **Cintura uomo** selezionando **Visualizza attributi**. Nel gruppo di attributi vengono visualizzati gli attributi **Marca di cintura uomo**, **Tessuto cintura** e **Taglia cintura**.

La stessa procedura di base può essere utilizzata anche per assegnare gruppi di attributi alle categorie nella gerarchia di categorie di navigazione nei canali e nella gerarchia di categorie di prodotti supplementari. Tuttavia, nel passaggio 2, utilizza uno dei seguenti percorsi, a seconda della gerarchia a cui vuoi assegnare i gruppi di attributi:

- **Gerarchia di categorie di navigazione nei canali:** vai a **Retail e Commerce \> Gestione categorie e prodotti \> Categorie di navigazione nei canali**.
- **Gerarchia di categorie di prodotti supplementari:** vai a **Retail e Commerce \> Gestione categorie e prodotti \> Categorie di prodotti supplementari**.

> [!NOTE]
> Assicurati di associare i gruppi di attributi in una gerarchia di categorie solo nella Scheda dettaglio **Gruppi di attributi del prodotto** e non nella Scheda dettaglio **Valori attributi categoria**. Se gli attributi sono visualizzati nella Scheda dettaglio **Valori attributi categoria**, seleziona **Modifica gerarchia di categorie** nel riquadro azioni. Quindi, nella Scheda dettaglio **Gruppi di attributi categoria**, seleziona i nodi della categoria e seleziona **Rimuovi**. Non è disponibile alcun supporto per il recupero di attributi per categoria tramite Commerce Scale Unit.

## <a name="identify-viewable-and-refinable-attributes-for-commerce-channels-for-the-default-product-collection"></a>Identificare attributi visualizzabili e affinabili per canali Commerce per la raccolta prodotti predefinita

Dopo aver associato vari gruppi di attributi alle categorie in varie gerarchie (gerarchia dei prodotti di Commerce o categorie di navigazione nei canali) e definito valori di attributi per ciascun prodotto, in base all'associazione di categoria, devi abilitare il flag **Mostra attributo sul canale** per rendere tali attributi visibili in un canale specifico.

1. Passare a **Retail e Commerce \> Impostazione canale \> Categorie canale e attributi del prodotto**.
1. Seleziona **Imposta metadati di attributi** e quindi un attributo nel riquadro di spostamento a sinistra.
1. Nella Scheda dettaglio **Attributi del prodotto del canale** (non nella Scheda dettaglio **Attributi categoria**), imposta l'opzione **Mostra attributo sul canale** su **Si** per rendere visibile l'attributo.
1. Se vuoi che anche l'attributo sia affinabile, imposta l'opzione **Ridefinizione possibile** su **Sì**.

### <a name="control-visibility-of-dimension-based-refiners-such-as-size-style-and-color"></a>Controllare la visibilità di criteri di affinamento basati su dimensioni come dimensioni, stile e colore

Le dimensioni del prodotto come dimensioni, stile e colore sono i criteri di affinamento più comunemente utilizzati. Per rendere disponibili queste dimensioni di prodotto come criteri di affinamento, devi associare un gruppo di attributi a livello di canale che contenga un riferimento a un tipo di attributo che eredita automaticamente i valori dai valori delle dimensioni di prodotto.

Puoi specificare le dimensioni di prodotto come visualizzabili e affinabili aggiornando i flag nella pagina **Categorie canale e attributi del prodotto**. Seleziona il nodo principale nel riquadro di spostamento e quindi nella Scheda dettaglio **Attributi del prodotto del canale**, imposta l'opzione **Mostra attributo sul canale** su **Sì** per gli attributi **Dimensione**, **Stile** e **Colore**. Se vuoi che anche questi attributi siano affinabili, imposta l'opzione **Ridefinizione possibile** su **Sì** per ognuno.

![Impostare i metadati di attributi per i criteri di affinamento delle dimensioni.](./media/ProductDimensionRefinersMetadataSetup_2022Series.png)

Per abilitare gli attributi di modo che siano disponibili nel canale Houston basato sui dati demo, segui i passaggi in questa procedura di esempio.

1. Passare a **Retail e Commerce \> Impostazione canale \> Categorie canale e attributi del prodotto**.
1. Selezionare il canale **Houston**.
1. Nel riquadro azioni, selezionare **Imposta metadati di attributi**.
1. Selezionare il nodo della categoria **Moda**, quindi, nella scheda dettaglio **Attributi del prodotto del canale**, selezionare **Includi attributo** per ciascun attributo.
1. Selezionare il nodo della categoria **Accessori di moda**,selezionare la categoria **Occhiali da sole di moda**, quindi, nella scheda dettaglio **Attributi del prodotto del canale**, selezionare **Includi attributo** per ciascun attributo.
1. Selezionare il nodo della categoria **Abbigliamento maschile**, selezionare la categoria **Pantaloni**, quindi, nella scheda dettaglio **Attributi del prodotto del canale**, selezionare **Includi attributo** per ciascun attributo.
1. Dopo aver aggiornato i metadati di attributi per gli attributi e i criteri di affinamento desiderati, assicurati di salvare le modifiche ed eseguire il processo **Pubblica aggiornamenti canale**. Quindi, dopo la pubblicazione degli aggiornamenti, devi eseguire i seguenti processi: **1070** (**Configurazione canale**), **1040** (**Prodotti**) e **1150** (**Catalogo**).

> [!NOTE]
> - Se la tua attività richiede di aggiungere o rimuovere frequentemente prodotti nella gerarchia di navigazione o di apportare modifiche come l'aggiornamento dei valori dell'ordine di visualizzazione, l'aggiunta di nuove categorie e l'aggiunta di nuovi gruppi di attributi alle categorie, ti consigliamo di configurare il processo **Pubblica aggiornamenti canale** da eseguire come processo batch frequente. In alternativa, attiva manualmente il processo **Pubblica aggiornamenti canale** e quindi i seguenti processi di Commerce Data Exchange (CDX): **1070** (**Configurazione canale**), **1040** (**Prodotti**) e **1150** (**Catalogo**).
> - Un'opzione **Eredita** ti consente di specificare che un canale deve ereditare i gruppi di attributi dal relativo canale padre nella gerarchia. Se si imposta l'opzione **Eredita** su **Sì**, il nodo del canale figlio eredita tutti i gruppi di attributi e tutti gli attributi in tali gruppi di attributi.
> - Se il pulsante **Imposta metadati di attributi** nel riquadro azioni non è disponibile, assicurati che **Gerarchia di navigazione** sia associato al tuo canale nella Scheda dettaglio **Generale**.
> - Non devi associare alcun gruppo di attributi ad eccezione dei gruppi di attributi basati sulle dimensioni a livello di canale (ad esempio, sotto **Gruppi di attributi** nella pagina **Categorie canale e attributi del prodotto**).
> - Dopo l'introduzione del supporto per cataloghi business-to-business (B2B) specifici del cliente in Commerce versione 10.0.27, dovresti identificare il criterio di affinamento e attribuire le configurazioni degli attributi per ogni catalogo B2B nello stesso modo descritto in questo articolo.

## <a name="override-attribute-values"></a>Sostituire valori di attributi

È possibile sostituire i valori predefiniti degli attributi per singoli prodotti a livello di prodotto. È inoltre possibile sostituire i valori predefiniti per singoli prodotti in specifici cataloghi destinati a canali specifici.

### <a name="override-the-attribute-values-of-an-individual-product"></a>Sostituire i valori di attributi di un singolo prodotto

Per sostituire i valori di attributi di un singolo prodotto, segui i passaggi in questa procedura di esempio.

1. Accedi a Commerce headquarters come responsabile del merchandising.
1. Vai a **Retail e Commerce \> Gestione categorie e prodotti \> Prodotti rilasciati per categoria**.
1. Seleziona **Moda \> Accessori di moda \> Occhiali da sole di moda**.
1. Selezionare il prodotto richiesto nella griglia. Quindi, nel riquadro azioni, nella scheda **Prodotto**, nel gruppo **Imposta**, selezionare **Attributi del prodotto**.
1. Selezionare un attributo nel riquadro sinistro, quindi aggiornare il relativo valore nel riquadro destro.

![Pagina Valori attributi del prodotto](media/ProdDetailsProdAttrValues_2022Series.png)

### <a name="override-the-attribute-values-of-all-products-in-a-catalog"></a>Sostituire i valori di attributi di tutti prodotti in un catalogo

Per sostituire i valori di attributi di tutti i prodotti in un catalogo, segui i passaggi in questa procedura di esempio.

1. Accedi a Commerce headquarters come responsabile del merchandising.
1. Vai a **Retail e Commerce \> Gestione cataloghi \> Tutti i cataloghi**.
1. Selezionare il catalogo **Fabrikam Base Catalog**.
1. Seleziona **Moda \> Accessori di moda \> Occhiali da sole di moda**.
1. Nella scheda dettaglio **Prodotti**, selezionare il prodotto richiesto, quindi selezionare **Attributi** sopra la griglia del prodotto.
1. Nelle seguenti schede dettaglio, aggiornare i valori degli attributi richiesti:

    - Supporti prodotto condivisi
    - Attributi del prodotto condivisi
    - Supporti canale
    - Attributi del prodotto del canale

### <a name="override-the-attribute-values-of-all-products-in-a-channel"></a>Sostituire i valori di attributi di tutti i prodotti in un canale

Per sostituire i valori di attributi di tutti i prodotti in un canale, segui i passaggi in questa procedura di esempio.

1. Accedi a Commerce headquarters come responsabile del merchandising.
1. Passare a **Retail e Commerce \> Impostazione canale \> Categorie canale e attributi del prodotto**.
1. Selezionare il canale **Houston**.
1. Nella scheda dettaglio **Prodotti**, selezionare il prodotto richiesto, quindi selezionare **Attributi** sopra la griglia del prodotto.
1. Se non sono disponibili prodotti, seleziona **Aggiungi** nella scheda dettaglio **Prodotti**, quindi seleziona i prodotti necessari nella finestra di dialogo **Aggiungi prodotti**.
1. Nelle seguenti schede dettaglio, aggiornare i valori degli attributi richiesti:

    - Supporti prodotto condivisi
    - Attributi del prodotto condivisi
    - Supporti canale
    - Attributi del prodotto del canale

### <a name="define-variant-specific-attribute-values-and-define-multiple-values-for-product-attributes"></a>Definire valori di attributi specifici della variante e definire più valori per attributi di prodotto

Per definire valori di attributi specifici della variante e per definire più valori per attributi di prodotto, segui i passaggi in questa procedura di esempio.

1. Accedi a Commerce headquarters come responsabile del merchandising.
1. Passare a **Retail e Commerce \> Impostazione canale \> Categorie canale e attributi del prodotto**.
1. Selezionare il canale **Houston**.
1. Nella scheda dettaglio **Prodotti**, seleziona la variante prodotto necessaria, quindi seleziona **Attributi** sopra la griglia del prodotto.
1. Se non sono disponibili prodotti, seleziona **Aggiungi** nella scheda dettaglio **Prodotti**, quindi seleziona le varianti prodotto necessarie nella finestra di dialogo **Aggiungi prodotti**.
1. Nelle seguenti schede dettaglio, aggiornare i valori degli attributi richiesti:

    - Supporti prodotto condivisi
    - Attributi del prodotto condivisi
    - Supporti canale
    - Attributi del prodotto del canale

#### <a name="example-of-variant-specific-attribute-configuration"></a>Esempio di configurazione di attributi specifici della variante
        
In questo esempio, il prodotto **P001-Master** è una scarpa multi-attività che ha tre varianti: **Corsa**, **Marcia** e **Trekking**. Per ogni variante, vuoi definire in modo univoco il valore dell'attributo **Attività**. Nella Scheda dettagli **Prodotti** della pagina **Categorie canale e attributi del prodotto** per il tuo canale, definisci il valore dell'attributo **Attività** per le varianti come mostrato nella tabella seguente.

| Variante     | Valore dell'attributo Attività |
|-------------|--------------------------|
| P001-Master | Sport                   |
| P001-1      | Corsa                  |
| P001-2      | Marcia                  |
| P001-3      | Trekking                 |

Se un utente cerca "scarpa", il prodotto **P001-Maestro** apparirà nei risultati di ricerca. Se hai configurato l'attributo **Attività** come affinabile, il criterio di affinamento **Attività** elencherà solo **Sport** come valore affinabile perché quel valore è stato definito per l'attributo **Attività** a livello del prodotto **P001-Master**.

Per impostazione predefinita, gli attributi a livello di variante vengono utilizzati solo nelle pagine dei dettagli del prodotto (PDP). Quando selezioni una variante prodotto specifica in una PDP, le specifiche del prodotto nella PDP vengono aggiornate per quella variante specifica.

Affinché i criteri di affinamento raccolgano valori di attributi definiti a livello di variante di prodotto, devi definire un attributo a livello di rappresentazione generale prodotto, selezionare la casella di controllo **Consenti più valori** e impostare il tipo di attributo su **Testo**.

Successivamente, devi determinare tutti i valori possibili per le varianti di prodotto. Per l'attributo **Attività** utilizzato in questo esempio, i possibili valori potrebbero includere **Corsa**, **Marcia**, **Escursionismo**, **Trekking**, **Campeggio**, **Sport acquatici**, e **Sport invernali**.

Dopo aver determinato quali devono essere i valori dell'attributo della variante, puoi definirli a livello di rappresentazione generale prodotto utilizzando valori separati da barra verticale. Per l'attributo **Attività** potresti definire il valore di attributo nella rappresentazione generale prodotto come **Corsa|Marcia|Escursionismo|Trekking|Campeggio|Sport acquatici|Sport invernali**.

Quindi, per ogni variante, puoi definire i valori degli attributi immettendo valori separati da barra verticale o singoli valori. Per l'attributo **Attività** potresti configurare una singola variante prodotto come **Corsa|Marcia|Escursionismo**, **Corsa**, **Corsa|Escursionismo|Sport acquatici** e così via.

Dopo aver definito i valori dell'attributo della variante, nella pagina **Categorie canale e attributi del prodotto**, nel riquadro azioni seleziona **Pubblica aggiornamenti canale** e quindi esegui i processi **1150**, **1040** e **1070**.

Dopo il completamento dei processi e l'aggiornamento dell'indice di ricerca, tutti i valori previsti devono essere visualizzati nei risultati di ricerca e nei risultati di navigazione delle categorie.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
