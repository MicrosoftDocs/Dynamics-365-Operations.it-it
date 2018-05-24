---
title: "Attributi, gruppi di attributi e le relative associazioni a diverse entità Retail in Finance and Operations"
description: In questo argomento viene illustrato come utilizzare gli attributi per fornire un modo per descrivere un prodotto e le relative caratteristiche tramite campi definiti dall'utente.
author: ashishmsft
manager: AnnBe
ms.date: 04/28/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2018-03-30
ms.dyn365.ops.version: Application pdate 5, AX 8.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 5e04b1f6ef58836eeac85be074e295e6d1f42c52
ms.contentlocale: it-it
ms.lasthandoff: 05/08/2018

---

# <a name="attributes-attribute-groups-and-their-associations-with-various-retail-entities-in-finance-and-operations"></a>Attributi, gruppi di attributi e le relative associazioni a diverse entità Retail in Finance and Operations

[!include [banner](includes/banner.md)]

Gli *attributi* forniscono un modo per descrivere ulteriormente un prodotto e le sue caratteristiche tramite campi definiti dall'utente (ad esempio **Dimensione di memoria**, **Capacità del disco rigido**, **Conformità allo standard Energy Star** e così via). In Microsoft Dynamics 365 for Finance and Operations, gli attributi possono essere associati a diverse entità Retail, ad esempio a categorie di prodotti e canali di vendita al dettaglio, ed è possibile impostare per tali attributi valori predefiniti. I prodotti ereditano quindi gli attributi e i valori predefiniti quando vengono associati alle categorie di prodotti o ai canali di vendita al dettaglio. I valori predefiniti possono essere sovrascritti a livello di singolo prodotto, a livello di canale di vendita al dettaglio o in un catalogo al dettaglio.
 
Ad esempio, un prodotto tipico nell'ambito dei televisori può avere i seguenti attributi.

| Categoria   | Attributo                | Valori permessi          | Valore predefinito |
|------------|--------------------------|-----------------------------|---------------|
| TV e video | Marchio                    | Qualsiasi valore di marchio valido       | Nessuna          |
| TV         | Dimensioni schermo              | 20-80 pollici                | Nessuna          |
|            | Risoluzione verticale      | 480i, 720p, 1080i o 1080p | 1080p         |
|            | Frequenza di aggiornamento schermo      | 60 hz, 120 hz o 240 hz       | 60 hz          |
|            | Ingressi HDMI              | 0–10                        | 3             |
|            | Ingressi DVI               | 0–10                        | 1             |
|            | Ingressi compositi         | 0–10                        | 2             |
|            | Ingressi per componenti         | 0–10                        | 1             |
| LCD        | Predisposizione al 3D                 | Sì o No                   | Sì           |
|            | Abilitato 3D               | Sì o No                   | No            |
| Plasma     | Temperatura d'esercizio da      | 32-110 gradi              | 32            |
|            | Temperatura d'esercizio fino a        | 32-110 gradi              | 100           |
| LCD | Garanzia tubo a proiezione | 6, 12 o 18 mesi         | 12            |
|            | N. di tubi di proiezione    | 1–5                         | 3             |

## <a name="attributes-and-attribute-types"></a>Attributi e tipi di attributo

Gli attributi si basano sui *tipi di attributo*. Il tipo di attributo identifica il tipo di dati che possono essere immessi per un attributo specifico. Finance and Operations attualmente supporta i seguenti tipi di attributo:

- **Valuta** - Questo tipo supporta un valore di valuta. Può essere associato (ovvero può supportare un intervallo di valori) oppure può essere lasciato aperto.
- **Data/ora** - Questo tipo supporta un valore di data e ora. Può essere limitato o lasciato aperto.
- **Decimale** - Questo tipo supporta un valore numerico che include posizioni decimali. Supporta anche un'unità di misura. Può essere limitato o lasciato aperto.
- **Intero** - Questo tipo supporta un valore numerico. Supporta anche un'unità di misura. Può essere limitato o lasciato aperto.
- **Testo** - Questo tipo supporta un valore di testo. Supporta anche un set predefinito di valori possibili, ovvero una *enumerazione*.
- **Booleano** - Questo tipo supporta un valore binario (**vero** o **falso**).
- **Riferimento** - Questo tipo fa riferimento ad altri attributi.

### <a name="set-up-attribute-types-in-finance-and-operations"></a>Impostare tipi di attributo in Finance and Operations

1. Accedere al client di back-office di Finance and Operations come responsabile merchandising della vendita.
2. Scegliere **Gestione informazioni sul prodotto** &gt; **Impostazioni** &gt; **Categorie e attributi** &gt; **Tipi di attributo**.
3. Creare due tipi di attributo di tipo **Testo**, impostare l'opzione **Elenco fisso** su **Sì**, quindi aggiungere un elenco di valori:

    - Denominare un tipo di attributo **Forma di lente**, quindi aggiungere i seguenti valori: **Ovale**, **Quadrato** e **Rettangolo**.
    - Denominare l'altro tipo di attributo **Marca di occhiali da sole**, quindi aggiungere i seguenti valori: **Ray ban**, **Aviator** e **Oakley**.

![Tipi di attributo](media/AttributeType.png)

### <a name="set-up-an-attribute-in-finance-and-operations"></a>Impostare un attributo in Finance and Operations

1. Accedere al client di back-office come responsabile merchandising della vendita.
2. Scegliere **Gestione informazioni sul prodotto** &gt; **Impostazioni** &gt; **Categorie e attributi** &gt; **Attributi**.
3. Creare un attributo denominato **Lente**.
4. Impostare il campo **Tipo di attributo** su **Forma di lente**.

![Attributi](media/Attribute.png)

## <a name="attribute-metadata"></a>Metadati di attributi

*Metadati di attributi* consente di selezionare le opzioni per specificare come gli attributi per ogni prodotto devono comportarsi. Ad esempio, è possibile specificare se gli attributi sono obbligatori, se possono essere utilizzati per le ricerche e come filtro.

Per i prodotti al dettaglio, le impostazioni dei metadati di attributi possono essere sostituite a livello di canale. Questa funzionalità verrà descritta più avanti in questo argomento.

Come è possibile notare, la pagina **Attributi** include opzioni correlate ai metadati di attributi. In **Metadati di attributi per POS**, un'opzione denominata **"Ridefinizione possibile"** influisce sul comportamento dei valori di attributo nel punto vendita (POS) al dettaglio o sul modo in cui il sistema gestisce tali valori di attributo. Solo gli attributi per cui è possibile impostare l'opzione **"Ridefinizione possibile"** su **"Sì"** verranno visualizzati per la ridefinizione o il filtro dei prodotti in Retail POS.

Di seguito sono riportate le opzioni rimanenti relative ai metadati di attributi nella pagina **Attributi**:

- Ricercabile
- Recuperabile
- Esecuzione query possibile
- Classificabile
- Consenti più valori
- Ignora distinzione tra maiuscole e minuscole e formato
- Corrispondenza completa

Queste opzioni sono state inizialmente progettate per migliorare le funzionalità di ricerca per la vetrina virtuale online. Sebbene Finance and Operations non includa la vetrina virtuale online per impostazione predefinita, include l'eCommerce Publishing Software Development Kit (SDK). I clienti possono utilizzare questo SDK per inserire i prodotti in un indice di ricerca di propria scelta. Sebbene i dati dei prodotti siano importati, i clienti dovrebbero comunque essere in grado di distinguere i dati in cui è possibile eseguire le ricerche, quelli nei quali è possibile eseguire le interrogazioni e così via. In questo modo, gli utenti possono creare un indice ottimale per assicurarsi di indicizzare solo gli attributi che, *a loro parere*, devono essere indicizzati.

Per informazioni sullo scopo di queste opzioni rimanenti, vedere [Panoramica dello schema di ricerca in SharePoint Server 2013](https://technet.microsoft.com/en-us/library/jj219669.aspx).

## <a name="filter-settings-for-attributes"></a>Impostazioni di filtro per attributi

Le impostazioni di filtro per gli attributi consentono di definire il modo in cui i filtri per attributi vengono visualizzati in Retail POS. Per accedere alle impostazioni di filtro per un attributo, nella pagina **Attributi** in Finance and Operations, selezionare l'attributo, quindi, nel riquadro azioni, selezionare **Impostazioni filtro**.

La pagina **Preferenze di visualizzazione filtro** include i seguenti campi:

- **Nome** - Per impostazione predefinita, questo campo è impostato sul nome dell'attributo. È tuttavia possibile modificare tale valore.
- **Opzione di visualizzazione** - Sono disponibili le opzioni seguenti:

    - **Valore singolo** - Questa opzione è disponibile per i seguenti tipi di attributo: **Booleano**, **Valuta**, **Decimale**, **Intero** e **Testo**. Questa opzione consente la selezione di un valore singolo per questi attributi nel client per il perfezionamento.
    - **Multi-valore** - Questa opzione è disponibile per i seguenti tipi di attributo: **Valuta**, **Decimale**, **Intero** e **Testo**. Questa opzione consente la selezione di più valori per questo attributo nel client per il perfezionamento.

- **Controllo di visualizzazione** - Sono disponibili le opzioni seguenti:

    - **Elenco** - Questa opzione è disponibile per tutti i tipi di attributo.
    - **Intervallo** - Questa opzione è disponibile per i seguenti tipi di attributo: **Valuta**, **Decimale** e **Intero**. 
    - **Dispositivo di scorrimento** - Questa opzione è disponibile per i seguenti tipi di attributo: **Valuta**, **Decimale** e **Intero**.
    - **Dispositivo di scorrimento con barre** - Questa opzione è disponibile per i seguenti tipi di attributo: **Valuta**, **Decimale** e **Intero**.

- **Valore di soglia** - Questa impostazione è necessaria se è stato selezionato **Intervallo** come tipo di controllo di visualizzazione. È possibile definire i valori utilizzando un punto e virgola (;) come separatore.

    Ad esempio, per il filtro come **Volume borsa**, il valore soglia può essere **10; 20; 50; 100; 200; 500; 1000; 5000**. In questo caso, in Retail POS verranno visualizzati i seguenti intervalli. Tutti gli intervalli privi di prodotti nel set di risultati risulteranno disattivati.

    - Minore di 10
    - 10 – 20
    - 20 – 50
    - 50 – 100
    - 100 – 200
    - 200 – 500
    - 500 o più

![Impostazioni di filtro di attributi](media/AttributeFilterSettings.PNG)

## <a name="attribute-groups"></a>Gruppi di attributi

Dopo che gli attributi sono stati definiti, possono essere assegnati a gruppi di attributi. Un *gruppo di attributi* viene utilizzato per raggruppare i singoli attributi per un componente o un sottocomponente in un modello di configurazione prodotto. È possibile includere un attributo in più gruppi di attributi. I gruppi di attributi possono consentire agli utenti di configurare i prodotti, poiché le varie selezioni vengono disposte in un contesto specifico. È possibile assegnare i gruppi di attributi ai canali di vendita al dettaglio o alle categorie di vendita al dettaglio.

È inoltre possibile impostare i valori predefiniti per gli attributi inclusi in un gruppo di attributi. Ad esempio, si aggiunge un attributo per il colore a un gruppo di attributi e si seleziona **Blu** come valore di attributo predefinito. In questo caso, quando il gruppo di attributi viene aggiunto a un prodotto al dettaglio che include il colore come uno degli attributi, **Blu** apparirà come il colore predefinito per quel prodotto.

![Gruppi di attributi](media/AttributeGroup.png)

### <a name="create-an-attribute-group"></a>Crea un gruppo attributi

1. Accedere al client di back-office come responsabile merchandising della vendita.
2. Scegliere **Gestione informazioni sul prodotto** &gt; **Impostazioni** &gt; **Categorie e attributi** &gt; **Gruppi di attributi**.
3. Creare un gruppo di attributi denominato **Occhiali da sole di moda**.
4. Aggiungere i seguenti attributi: **Forma di lente** e **Marca di occhiali da sole**.

### <a name="assign-attribute-groups-to-retail-categories"></a>Assegnare i gruppi di attributi alle categorie di vendita al dettaglio

È possibile associare uno o più gruppi di attributi ai nodi di categoria nei seguenti tipi di gerarchie di categorie di vendita al dettaglio: Gerarchia di prodotti al dettaglio, Gerarchia di categorie di navigazione nei canali e Gerarchia di categorie di prodotti supplementari. Quindi, una volta che i prodotti sono stati classificati in categorie, ereditano gli attributi inclusi nei gruppi di attributi.

![Gerarchia di prodotti al dettaglio - Gruppi di attributi del prodotto](media/AGRetailProdHierarchy.PNG)

Attenersi alla procedura seguente per assegnare gruppi di attributi alle categorie nella gerarchia di prodotti al dettaglio.

1. Accedere al client di back-office come responsabile merchandising della vendita.
2. Passare a **Vendita al dettaglio** &gt; **Gestione categorie e prodotti** &gt; **Gerarchia di prodotti al dettaglio**.
3. Selezionare **Gerarchia di navigazione articoli di moda**.
4. In **Abbigliamento maschile**, selezionare la categoria **Pantaloni**, quindi, nella scheda dettaglio **Gruppi di attributi del prodotto**, aggiungere un gruppo di attributi denominato **Cintura uomo**.
5. Selezionare la categoria **Occhiali da sole di moda**, quindi verificare i nuovi attributi nel gruppo di attributi **Occhiali da sole di moda** selezionando **Visualizza attributi**.

    Nel gruppo di attributi vengono visualizzati i nuovi attributi **Forma di lente** e **Marca di occhiali dal sole**.

6. In **Abbigliamento maschile**, selezionare la categoria **Pantaloni** e verificare gli attributi per il gruppo di attributi **Cintura uomo** selezionando **Visualizza attributi**.

    Nel gruppo di attributi vengono visualizzati gli attributi **Marca di cintura uomo**, **Tessuto cintura** e **Taglia cintura**.

> [!NOTE]
> Questa procedura può essere utilizzata anche per assegnare gruppi di attributi alle categorie nella gerarchia di categorie di navigazione nei canali e nella gerarchia di categorie di prodotti supplementari. Nel passaggio 2, utilizzare i seguenti percorsi di navigazione:
>
> - **Vendita al dettaglio** &gt; **Gestione categorie e prodotti** &gt; **Categorie di navigazione nei canali**
> - **Vendita al dettaglio** &gt; **Gestione categorie e prodotti** &gt; **Categorie di prodotti supplementari**.

### <a name="assign-attribute-groups-to-retail-stores"></a>Assegnare i gruppi di attributi ai punti vendita al dettaglio

È possibile associare uno o più gruppi di attributi a uno o più punti vendita al dettaglio nella gerarchia dei punti vendita al dettaglio. Quindi, una volta che i prodotti sono stati migliorati per gli specifici punti vendita al dettaglio, ereditano gli attributi inclusi nei gruppi di attributi.

1. Accedere al client di back-office come responsabile merchandising della vendita.
2. Passare a **Vendita al dettaglio** &gt; **Impostazione canale** &gt; **Categorie canale e attributi del prodotto**.
3. Assegnare gruppi di attributi al canale Houston:

    1. Selezionare il canale **Houston**.
    2. Nella scheda dettaglio **Gruppo di attributi**, selezionare **Aggiungi**, quindi, nel campo **Nome**, selezionare **SharePointProvisionedProductAttributeGroup**.
    3. Selezionare nuovamente **Aggiungi**, quindi, nel campo **Nome**, selezionare **Cintura uomo**.
    4. Selezionare nuovamente **Aggiungi**, quindi, nel campo **Nome**, selezionare **Occhiali da sole di moda**.

        > [!NOTE]
        > Un'opzione consente di specificare che questo canale deve ereditare i gruppi di attributi dal relativo canale padre nella gerarchia. Se si imposta l'opzione **Eredita** su **Sì**, il nodo del canale figlio eredita tutti i gruppi di attributi e tutti gli attributi in tali gruppi di attributi.

4. Attivare gli attributi in modo che siano disponibili nel canale Houston:

    1. Nel riquadro azioni, selezionare **Imposta metadati di attributi**.
    2. Selezionare il nodo della categoria **Moda**, quindi, nella scheda dettaglio **Attributi del prodotto del canale**, selezionare **Includi attributo** per ciascun attributo.
    3. Selezionare il nodo della categoria **Accessori di moda**,selezionare la categoria **Occhiali da sole di moda**, quindi, nella scheda dettaglio **Attributi del prodotto del canale**, selezionare **Includi attributo** per ciascun attributo.
    4. Selezionare il nodo della categoria **Abbigliamento maschile**, selezionare la categoria **Pantaloni**, quindi, nella scheda dettaglio **Attributi del prodotto del canale**, selezionare **Includi attributo** per ciascun attributo.

![Categorie canale e attributi del prodotto - Gruppi di attributi](media/CCPAttrGrp.png)

## <a name="overriding-attribute-values"></a>Sostituzione dei valori di attributi

È possibile sovrascrivere i valori predefiniti degli attributi per singoli prodotti a livello di prodotto. È inoltre possibile sovrascrivere i valori predefiniti per singoli prodotti in specifici cataloghi che sono destinati a canali di vendita al dettaglio specifici.

### <a name="override-the-attribute-values-of-an-individual-product"></a>Sostituire i valori degli attributi di un singolo prodotto

1. Accedere al client di back-office come responsabile merchandising della vendita.
2. Passare a **Vendita al dettaglio** &gt; **Gestione categorie e prodotti** &gt; **Prodotti rilasciati per categoria**.
3. Selezionare il nodo della categoria **Moda** &gt; **Accessori di moda** &gt; **Occhiali da sole di moda**.
4. Selezionare il prodotto richiesto nella griglia. Quindi, nel riquadro azioni, nella scheda **Prodotto**, nel gruppo **Imposta**, selezionare **Attributi del prodotto**.
5. Selezionare un attributo nel riquadro sinistro, quindi aggiornare il relativo valore nel riquadro destro.

![Pagina Dettagli prodotto - Gruppi di attributi del prodotto](media/ProdDetailsProdAttrValues.png)

### <a name="override-the-attribute-values-of-products-in-a-catalog"></a>Sostituire i valori degli attributi dei prodotti in un catalogo

1. Accedere al client di back-office come responsabile merchandising della vendita.
2. Passare a **Vendita al dettaglio** &gt; **Gestione cataloghi** &gt; **Tutti i cataloghi**.
3. Selezionare il catalogo **Fabrikam Base Catalog**.
4. Selezionare il nodo della categoria **Moda** &gt; **Accessori di moda** &gt; **Occhiali da sole di moda**.
5. Nella scheda dettaglio **Prodotti**, selezionare il prodotto richiesto, quindi selezionare **Attributi** sopra la griglia del prodotto.
6. Nelle seguenti schede dettaglio, aggiornare i valori degli attributi richiesti:

   - Supporti prodotto condivisi
   - Attributi del prodotto condivisi
   - Supporti canale
   - Attributi del prodotto del canale

     > [!NOTE]
     > Se i supporti prodotto condivisi e gli attributi del prodotto condivisi vengono creati in Finance and Operations, vengono applicati a tutti i prodotti al dettaglio.

![Gruppi di attributi del prodotto del catalogo](media/CatalogProdAttrValues.png)

### <a name="override-the-attribute-values-of-products-in-a-channel"></a>Sostituire i valori degli attributi dei prodotti in un canale

1. Accedere al client di back-office come responsabile merchandising della vendita.
2. Passare a **Vendita al dettaglio** &gt; **Impostazione canale** &gt; **Categorie canale e attributi del prodotto**.
3. Selezionare il canale **Houston**.
4. Nella scheda dettaglio **Prodotti**, selezionare il prodotto richiesto, quindi selezionare **Attributi** sopra la griglia del prodotto.

    > [!NOTE]
    > Se non sono disponibili prodotti, aggiungere prodotti selezionando **Aggiungi** nella scheda dettaglio **Prodotti**, quindi selezionando i prodotti richiesti nella finestra di dialogo **Aggiungi prodotti**.

5. Nelle seguenti schede dettaglio, aggiornare i valori degli attributi richiesti:

   - Supporti prodotto condivisi
   - Attributi del prodotto condivisi
   - Supporti canale
   - Attributi del prodotto del canale

     > [!NOTE]
     > Se i supporti prodotto condivisi e gli attributi del prodotto condivisi vengono creati in Finance and Operations, vengono applicati a tutti i prodotti al dettaglio.

