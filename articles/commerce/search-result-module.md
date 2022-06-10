---
title: Modulo dei risultati di ricerca
description: Questo argomento tratta i moduli dei risultati di ricerca e descrive come aggiungerli alle pagine del sito in Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 05/18/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: dcf3dedbb7c499135bbae45b917153854ecd4a28
ms.sourcegitcommit: ccb39767bd3430c24f4653c26560bba2cd66553c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2022
ms.locfileid: "8780920"
---
# <a name="search-results-module"></a>Modulo dei risultati di ricerca

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

Questo argomento tratta i moduli dei risultati di ricerca e descrive come aggiungerli alle pagine del sito in Microsoft Dynamics 365 Commerce.

Il modulo dei risultati di ricerca restituisce i risultati della ricerca del prodotto e un elenco di criteri di affinamento applicabili per i prodotti. Moduli dei risultati di ricerca nei siti Dynamics 365 Commerce possono essere utilizzati per visualizzare le pagine per i seguenti scenari:

- Risultati della ricerca avviati da una ricerca utente
- I risultati di ricerca che mostrano un insieme specifico di prodotti, ad esempio "Acquista articoli simili"
- Elenchi di prodotti appartenenti a una categoria

Per ulteriori informazioni sulle pagine dei risultati di ricerca e categoria, vedi [Pagina di destinazione della categoria predefinita e panoramica della pagina dei risultati di ricerca](category-search-page-overview.md).

La figura seguente mostra un esempio di una pagina dei risultati della ricerca per una categoria per il sito Fabrikam.

![Esempio di pagina dei risultati della ricerca sul sito Fabrikam.](./media/SimpleCategoryLandingDressCategory.png)

## <a name="search-results-module-properties"></a>Proprietà del modulo dei risultati di ricerca

La tabella seguente elenca le proprietà dei moduli dei risultati di ricerca, insieme ai relativi valori e descrizioni.

| Proprietà | Valori | Descrizione |
|----------|--------|-------------|
| Articoli per pagina | Integer | Il numero di articoli che devono essere visualizzati su ciascuna pagina. |
| Consenti di tornare indietro su PDP | **True** o **False** | Se questa proprietà è impostata su **True**, quando un utente seleziona un prodotto nella pagina dei risultati di ricerca, il Percorso di navigazione nella pagina dei dettagli del prodotto (PDP) che viene aperto mostrerà un collegamento "Torna ai risultati". |
| Espandi affinamenti | **Tutto**, **1**, **2**, **3**, o **4** | Il numero di affinamenti principali da espandere quando viene caricata una pagina. Ad esempio, se questa proprietà è impostata su **3**, verranno espansi i primi tre criteri di affinamento della pagina. |
| Nascondi visualizzazione gerarchia di categorie | **True** o **False** | Se questa proprietà è impostata su **True**, la visualizzazione della gerarchia delle categorie nella pagina verrà nascosta. Questa proprietà deve essere impostata su **True** se stai usando il [modulo Percorso di navigazione](add-breadcrumb.md) per mostrare la gerarchia delle categorie.|
| Includi attributi del prodotto nei risultati di ricerca | **True** o **False** | Se questa proprietà è impostata su **True**, verranno restituiti gli attributi per i prodotti nei risultati di ricerca. Sebbene questi attributi possano essere visualizzati su un sito di Commerce, è necessaria un'estensione.|
| Mostra i prezzi del rapporto | **True** o **False** | Se questa proprietà è impostata su **True**, i prezzi di affiliazione per i prodotti verranno visualizzati nei risultati di ricerca quando un utente che ha eseguito l'accesso naviga alla pagina. |
| Aggiorna il pannello di affinamento | **True** o **False** | Se questa proprietà è impostata su **Vero**, il pannello dell'affinamento verrà aggiornato quando vengono selezionati gli affinamenti. In questa modalità, alcuni affinamenti a selezione multipla si comporteranno come affinamenti a selezione singola quando il pannello di affinamento viene aggiornato. |

> [!IMPORTANT]
> In Commerce versione 10.0.16 e successive, la configurazione **Mostra prezzi di affiliazione** può essere utilizzata per mostrare i prezzi di affiliazione sulla pagina.
>
> In Commerce versione 10.0.20 e successive, la configurazione **Aggiorna pannello di affinamento** può essere utilizzata per aggiornare il pannello di affinamento durante la selezione dell'affinamento.

## <a name="supported-modules"></a>Moduli supportati

Il modulo di risultati di ricerca supporta il [modulo di visualizzazione rapida](quick-view-module.md), che consente agli utenti di visualizzare le informazioni sul prodotto e aggiungere articoli al carrello da una pagina di risultati di ricerca.

## <a name="add-a-search-results-module-to-a-category-page"></a>Aggiungere un modulo dei risultati di ricerca a una pagina di categoria

Per aggiungere un modulo di risultati della ricerca alla pagina di una categoria in Creazione di siti Web, effettua le seguenti operazioni.

1. Andare a **Modelli** e selezionare **Nuovo** per creare un nuovo modello.
1. Nella finestra di dialogo **Nuovo modello**, immetti il nome **Risultati di ricerca** e seleziona **OK**.
1. Nello slot **Corpo** seleziona i puntini di sospensione (...), quindi seleziona **Aggiungi modulo**.
1. Nella finestra di dialogo **Seleziona moduli** seleziona il modulo **Pagina predefinita** e quindi seleziona **OK**.
1. Nello slot **Principale** del modulo **Pagina predefinita**, seleziona i puntini di sospensione (...) e quindi **Aggiungi modulo**.
1. Nella finestra di dialogo **Seleziona moduli** selezionare il modulo **Contenitore** e quindi **OK**.
1. Nello slot **Contenitore** seleziona i puntini di sospensione (...), quindi seleziona **Aggiungi modulo**.
1. Nella finestra di dialogo **Seleziona moduli** seleziona il modulo **Breadcrumb** e quindi **OK**.
1. Nel riquadro delle proprietà **Percorso di navigazione** immetti il valore **1** per **Numero minimo ricorrenze**.
1. Nello slot **Contenitore** seleziona i puntini di sospensione (...), quindi seleziona **Aggiungi modulo**.
1. Nella finestra di dialogo **Seleziona moduli** seleziona il modulo **Risultati di ricerca** e quindi **OK**.
1. Nel riquadro delle proprietà **Risultati di ricerca**, immetti il valore **1** per **Numero minimo ricorrenze** e quindi imposta qualsiasi altra proprietà richiesta per il modulo dei risultati di ricerca. Impostando queste proprietà nel modello, ti assicuri che qualsiasi personalizzazione per una pagina di categoria specifica includerà automaticamente queste impostazioni.
1. Selezionare **Fine modifica**, quindi selezionare **Pubblica** per pubblicare il modello.
1. Accedi a **Pagine** e quindi seleziona **Nuovo** per creare una nuova pagina.
1. Nella finestra di dialogo **Crea una nuova pagina**, sotto **Nome pagina**, immetti **Pagina categoria**, quindi seleziona **Avanti**.
1. Sotto **Scegli un modello**, seleziona il modello **Risultati della ricerca** creato e seleziona **Avanti**.
1. Sotto **Scegli un layout**, seleziona un layout di pagina (ad esempio, **Layout flessibile**), quindi seleziona **Avanti**.
1. Sotto **Verifica e termina**, rivedi la configurazione della pagina. Se è necessario modificare le informazioni sulla pagina, seleziona **Indietro**. Se le informazioni sulla pagina sono corrette, seleziona **Crea pagina**.
1. Selezionare **Fine modifica** per archiviare la pagina, quindi selezionare **Pubblica** per pubblicarla.

## <a name="enable-inventory-awareness-for-the-search-results-module"></a>Abilitare la consapevolezza dell'inventario per il modulo dei risultati di ricerca

I clienti generalmente si aspettano che un sito web di e-commerce sia consapevole dell'inventario durante l'esperienza di esplorazione, in modo che possano decidere cosa fare se non ci sono scorte per un prodotto. Il modulo dei risultati di ricerca può essere configurato per incorporare i dati di inventario e fornire le seguenti esperienze:

- Mostrare un'etichetta di disponibilità delle scorte insieme al prodotto.
- Nascondere i prodotti esauriti dall'elenco dei prodotti.
- Mostrare i prodotti esauriti alla fine dell'elenco dei prodotti.
- Filtrare i prodotti nei risultati di ricerca per livello di inventario.

Per abilitare queste esperienze, devi prima abilitare la funzionalità **Individuazione di prodotti e-commerce migliorata basata sulle scorte** nell'area di lavoro **Gestione funzionalità**.

> [!NOTE]
> La funzionalità **Individuazione di prodotti e-commerce migliorata basata sulle scorte** è disponibile in Commerce versione 10.0.20 e successive.

La ricerca di prodotti in base all'inventario utilizza gli attributi del prodotto per ottenere informazioni sulla disponibilità delle scorte. Come prerequisito per la funzionalità, devono essere creati attributi di prodotto dedicati, devono essere inseriti i dati di inventario che poi devono essere aggiunti al canale online. 

Per creare attributi di prodotto dedicati per supportare il modulo dei risultati di ricerca in base all'inventario, segui questi passaggi.

1. In headquarters vai a **Vendita al dettaglio e commercio \> Vendita al dettaglio e commercio IT \> Prodotti e inventario**.
1. Seleziona e apri **Popola attributi di prodotto con livello scorte**.
1. Nella finestra di dialogo immetti le seguenti informazioni:

    1. Nel campo **Nome tipo e attributo di prodotto**, specifica un nome per l'attributo di prodotto dedicato che verrà creato per acquisire i dati delle scorte.
    1. Nel campo **Disponibilità scorte basata su**, seleziona il tipo di quantità su cui basare il calcolo del livello di scorte (ad esempio, **Fisico disponibile**). 

1. Esegui il processo in background. Poiché la disponibilità di magazzino di un prodotto cambia costantemente in un ambiente multicanale, ti consigliamo vivamente di pianificare il processo come processo batch.

> [!NOTE]
> Per un calcolo coerente del livello di scorte tra le pagine e i moduli sul tuo sito web di e-commerce, assicurati di selezionare lo stesso tipo di quantità per l'impostazione **Disponibilità scorte basata su** in Commerce headquarters e l'impostazione **Livello scorte basato su** nel generatore di siti di Commerce. Per ulteriori informazioni sulle impostazioni relative alle scorte in generatore di siti, vedi [Applicare le impostazioni relative alle scorte](inventory-settings.md).

Per configurare gli attributi del prodotto per un canale online, attieniti alla seguente procedura. 

1. Nelle sedi centrali, andare a **Vendita al dettaglio e commercio \> Impostazione canale \> Categorie canale e attributi del prodotto**.
1. Seleziona un canale online per il quale abilitare il modulo dei risultati di ricerca in base all'inventario.
1. Seleziona e apri un gruppo di attributi associato e aggiungi l'attributo di prodotto appena creato.
1. Per le versioni di Commerce precedenti alla versione 10.0.27, seleziona **Imposta metadati di attributi**, seleziona l'attributo di prodotto appena aggiunto, quindi attiva le opzioni **Mostra attributo sul canale**, **Recuperabile**, **Ridefinizione possibile**, ed **Esecuzione query possibile**.
1. Vai a **Vendita al dettaglio e commercio \> Vendita al dettaglio e commercio IT \> Programmazione della distribuzione**, ed esegui il processo **1150 (Catalogo)**. Se pianifichi il processo **Popola attributi di prodotto con livello scorte** come processo batch, ti consigliamo di pianificare anche il processo 1150 come processo batch che viene eseguito con la stessa frequenza.

> [!NOTE]
> Per i prodotti visualizzati nel modulo dei risultati di ricerca, il livello di scorte viene visualizzato a livello di rappresentazione generale prodotto anziché a livello di singola variante. Ha solo due valori possibili: "disponibile" ed "esaurito". L'etichetta effettiva per il valore viene recuperata dalla definizione [profilo del livello di scorte](inventory-buffers-levels.md). Una rappresentazione generale prodotto è considerata esaurita solo quando tutte le sue varianti sono esaurite.

Dopo che tutti i passaggi di configurazione precedenti sono stati completati, gli affinamenti nelle pagine dei risultati di ricerca mostreranno un filtro basato sull'inventario e il modulo dei risultati di ricerca recupererà i dati di inventario in background. Puoi quindi configurare l'opzione **Impostazioni inventario per le pagine elenco prodotti** nel generatore di siti di Commerce per controllare il modo in cui il modulo dei risultati di ricerca mostra i prodotti esauriti. Per ulteriori informazioni, vedere [Applicare impostazioni relative alle scorte](inventory-settings.md).

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica della pagina di destinazione di categoria e della pagina dei risultati di ricerca predefinite](category-search-page-overview.md)

[Panoramica della libreria moduli](starter-kit-overview.md)

[Modulo visualizzazione rapida](quick-view-module.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
