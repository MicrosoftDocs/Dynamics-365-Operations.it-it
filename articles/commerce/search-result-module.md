---
title: Modulo dei risultati di ricerca
description: Questo articolo tratta i moduli dei risultati di ricerca e descrive come aggiungerli alle pagine del sito in Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 08/31/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.8
ms.search.industry: ''
ms.search.form: ''
ms.openlocfilehash: eeb7cd0769fcb866a3d7dcc03e8e87daf24b2c5d
ms.sourcegitcommit: 1d5cebea3e05b6d758cd01225ae7f566e05698d2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/02/2022
ms.locfileid: "9405295"
---
# <a name="search-results-module"></a>Modulo dei risultati di ricerca

[!include [banner](includes/banner.md)]

Questo articolo tratta i moduli dei risultati di ricerca e descrive come aggiungerli alle pagine del sito in Microsoft Dynamics 365 Commerce.

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

## <a name="inventory-aware-search-results-module"></a>Modulo dei risultati di ricerca sensibile all'inventario

Il modulo dei risultati di ricerca può essere configurato per incorporare i dati di inventario e fornire le seguenti esperienze:

- Visualizzare le etichette del livello di inventario accanto ai prodotti.
- Nascondere i prodotti esauriti dall'elenco dei prodotti.
- Visualizzare i prodotti esauriti alla fine dell'elenco dei prodotti.
- Supportare il filtraggio dei prodotti basato sull'inventario.

Per abilitare queste esperienze, devi prima abilitare la funzionalità **Individuazione di prodotti e-commerce migliorata basata sulle scorte** e quindi configurare le impostazioni di alcuni prerequisiti in Commerce headquarters. Per ulteriori informazioni, vedere [Elenco dei prodotti in base all'inventario](inventory-aware-product-listing.md).

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica della pagina di destinazione di categoria e della pagina dei risultati di ricerca predefinite](category-search-page-overview.md)

[Panoramica della libreria moduli](starter-kit-overview.md)

[Modulo visualizzazione rapida](quick-view-module.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
