---
title: Modulo dei risultati di ricerca
description: Questo argomento tratta i moduli dei risultati di ricerca e descrive come aggiungerli alle pagine del sito in Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 10/15/2021
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
ms.openlocfilehash: bae825ed7093494c48abac119c480be0dba4f951
ms.sourcegitcommit: 9c2bc045eafc05b39ed1a6b601ccef48bd62ec55
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/14/2021
ms.locfileid: "7919476"
---
# <a name="search-results-module"></a>Modulo dei risultati di ricerca

[!include [banner](includes/banner.md)]


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

Per aggiungere un modulo di risultati di ricerca a una pagina di categoria effettua le seguenti operazioni.

1. Andare a **Modelli** e selezionare **Nuovo** per creare un nuovo modello.
1. Nella finestra di dialogo **Nuovo modello**, immetti il nome **Risultati di ricerca** e seleziona **OK**.
1. Nello slot **Corpo** seleziona i puntini di sospensione (...), quindi seleziona **Aggiungi modulo**.
1. Nella finestra di dialogo **Aggiungi modulo** selezionare il modulo **Pagina predefinita** e quindi selezionare **OK**.
1. Nello slot **Principale** del modulo **Pagina predefinita**, seleziona i puntini di sospensione (...) e quindi **Aggiungi modulo**.
1. Nella finestra di dialogo **Aggiungi modulo** selezionare il modulo **Contenitore** e quindi **OK**.
1. Nello slot **Contenitore** seleziona i puntini di sospensione (...), quindi seleziona **Aggiungi modulo**.
1. Nella finestra di dialogo **Aggiungi modulo** selezionare il modulo **Percorso di navigazione** e quindi **OK**.
1. Nel riquadro delle proprietà **Percorso di navigazione** immetti il valore **1** per **Numero minimo ricorrenze**.
1. Nello slot **Contenitore** seleziona i puntini di sospensione (...), quindi seleziona **Aggiungi modulo**.
1. Nella finestra di dialogo **Aggiungi modulo** selezionare il modulo **Risultati di ricerca** e quindi **OK**.
1. Nel riquadro delle proprietà **Risultati di ricerca**, immetti il valore **1** per **Numero minimo ricorrenze** e quindi imposta qualsiasi altra proprietà richiesta per il modulo dei risultati di ricerca. Impostando queste proprietà nel modello, ti assicuri che qualsiasi personalizzazione per una pagina di categoria specifica includerà automaticamente queste impostazioni.
1. Selezionare **Fine modifica**, quindi selezionare **Pubblica** per pubblicare il modello.
1. Accedi a **Pagine** e quindi seleziona **Nuovo** per creare una nuova pagina.
1. Nella finestra di dialogo **Scegli un modello**, seleziona il modello **Risultati di ricerca** creato, quindi immetti **Pagina categoria** per **Nome pagina**, e seleziona **OK**. Poiché tutti i valori sono impostati nel modello, la pagina è pronta per essere pubblicata.
1. Selezionare **Fine modifica** per archiviare la pagina, quindi selezionare **Pubblica** per pubblicarla.

## <a name="enable-inventory-awareness-for-the-search-results-module"></a>Abilitare la consapevolezza dell'inventario per il modulo dei risultati di ricerca

I clienti generalmente si aspettano che un sito di e-commerce sia consapevole dell'inventario durante l'esperienza di esplorazione, in modo che possano decidere cosa fare se non ci sono scorte per un prodotto. Il modulo dei risultati di ricerca può essere migliorato in modo che incorpori i dati di inventario e fornisca le seguenti esperienze:

- Mostra un'etichetta di disponibilità delle scorte insieme ai prodotti.
- Nascondi i prodotti esauriti.
- Mostra i prodotti esauriti alla fine dell'elenco dei risultati di ricerca.
    
Per abilitare queste esperienze, è necessario configurare le seguenti impostazioni dei prerequisiti in Commerce headquarters.

### <a name="enable-the-enhanced-e-commerce-product-discovery-to-be-inventory-aware-feature"></a>Abilitare la funzionalità Individuazione di prodotti e-commerce migliorata basata sulle scorte

> [!NOTE]
> La funzionalità **Individuazione di prodotti e-commerce migliorata basata sulle scorte** è disponibile a partire da Commerce versione 10.0.20.

Per abilitare la funzionalità **Individuazione di prodotti e-commerce migliorata basata sulle scorte** in Commerce headquarters attieniti alla seguente procedura.

1. Vai a **Aree di lavoro \> Gestione funzionalità**.
1. Cerca la funzionalità **Individuazione di prodotti e-commerce migliorata basata sulle scorte** e abilitala.

### <a name="configure-the-populate-product-attributes-with-inventory-level-job"></a>Configurare il processo Popola attributi di prodotto con livello scorte

Il processo **Popola attributi di prodotto con livello scorte** crea un nuovo attributo del prodotto per acquisire la disponibilità delle scorte e quindi impostare tale attributo sull'ultimo valore del livello di scorte per ogni rappresentazione generale prodotto. Poiché la disponibilità di magazzino di un prodotto o assortimento in vendita cambia costantemente, ti consigliamo vivamente di pianificare il processo come processo batch.

Per configurare il processo **Popola attributi di prodotto con livello scorte** in Commerce headquarters, segui questi passaggi.

1. Vai in **Retail e Commerce \> Vendita al dettaglio e commercio IT \> Prodotti e inventario**.
1. Seleziona **Popola attributi di prodotto con livello scorte**.
1. Nella finestra di dialogo **Popola attributi di prodotto con livello scorte** segui questi passaggi:

    1. In **Parametri**, nel campo **Nome tipo e attributo di prodotto**, specifica un nome per l'attributo di prodotto dedicato che verrà creato per acquisire la disponibilità delle scorte.
    1. In **Parametri**, nel campo **Disponibilità scorte basata su**, seleziona la quantità su cui basare il calcolo del livello di scorte (ad esempio, **Fisico disponibile**).
    1. In **Esegui in background**, configura il processo per l'esecuzione in background e, facoltativamente, attiva l'opzione **Elaborazione batch**. 

> [!NOTE]
> Per un calcolo coerente del livello di scorte tra le pagina dettagli prodotto e le pagine elenco prodotti sul tuo sito di e-commerce, assicurati di selezionare la stessa opzione di quantità per l'impostazione **Disponibilità scorte basata su** in Commerce headquarters e l'impostazione **Livello scorte basato su** nel generatore di siti di Commerce. Per ulteriori informazioni sulle impostazioni relative alle scorte in generatore di siti, vedi [Applicare le impostazioni relative alle scorte](inventory-settings.md).

### <a name="configure-the-new-product-attribute"></a>Configurare il nuovo attributo di prodotto

Dopo l'esecuzione del processo **Popola attributi di prodotto con livello scorte** è necessario configurare l'attributo di prodotto appena creato sul sito di e-commerce in cui vuoi abilitare la consapevolezza dell'inventario per il modulo dei risultati di ricerca.

Per configurare il nuovo attributo di prodotto in Commerce headquarters, seguire questi passaggi.

1. Passa a **Retail e Commerce \> Impostazione canale \> Categorie canale e attributi del prodotto** e seleziona un sito di e-commerce.
1. Seleziona e apri un gruppo di attributi associato, aggiungi l'attributo di prodotto appena creato e poi chiudi la pagina.
1. Seleziona **Imposta metadati di attributi**, seleziona l'attributo di prodotto appena aggiunto, quindi attiva le opzioni **Mostra attributo sul canale**, **Recuperabile**, **Ridefinizione possibile**, ed **Esecuzione query possibile**.

> [!NOTE]
> Per i prodotti visualizzati nel modulo dei risultati di ricerca, il livello di scorte viene immesso a livello di rappresentazione generale prodotto anziché a livello di singola variante. Ha solo due valori possibili: "disponibile" ed "esaurito". Il testo effettivo per i valori viene recuperato dalla definizione [profilo del livello di scorte](inventory-buffers-levels.md). Una rappresentazione generale prodotto è considerata esaurita solo quando tutte le sue varianti sono esaurite. Il livello di scorte di una variante viene determinato in base alla definizione del profilo del livello di scorte del prodotto. 

Dopo che tutti i passaggi di configurazione precedenti sono stati completati, gli affinamenti nelle pagine dei risultati di ricerca mostreranno un filtro basato sull'inventario e il modulo dei risultati di ricerca recupererà i dati di inventario in background. Puoi quindi configurare l'opzione **Impostazioni inventario per le pagine elenco prodotti** nel generatore di siti di Commerce per controllare il modo in cui il modulo dei risultati di ricerca mostra i prodotti esauriti. Per ulteriori informazioni, vedere [Applicare impostazioni relative alle scorte](inventory-settings.md).

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica della pagina di destinazione di categoria e della pagina dei risultati di ricerca predefinite](category-search-page-overview.md)

[Panoramica della libreria moduli](starter-kit-overview.md)

[Modulo visualizzazione rapida](quick-view-module.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
