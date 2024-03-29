---
title: Configurare i valori di dimensione prodotto in modo che appaiano come campioni
description: Questo articolo descrive come configurare i valori di dimensione prodotto come campioni in Microsoft Dynamics 365 Commerce Headquarters.
author: anupamar-ms
ms.date: 08/02/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2020-09-20
ms.dyn365.ops.version: Retail 10.0.20 update
ms.custom: ''
ms.search.industry: Retail
ms.openlocfilehash: e81c1f03eb6387176ca5ce8f751ce53aa0261679
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9271992"
---
# <a name="configure-product-dimension-values-to-appear-as-swatches"></a>Configurare i valori di dimensione prodotto in modo che appaiano come campioni

[!include [banner](../../includes/banner.md)]

Questo articolo descrive come configurare i valori di dimensione prodotto come campioni in Microsoft Dynamics 365 Commerce Headquarters. Per informazioni sulle dimensioni del prodotto, vedi [Dimensioni prodotto](../../supply-chain/pim/product-dimensions.md).

Dynamics 365 Commerce supporta l'uso di taglia, stile e colore per rappresentare le varianti del prodotto. Le dimensioni del prodotto hanno nomi descrittivi che vengono visualizzati nelle pagine dei dettagli del prodotto (PDP) in modo che le varianti del prodotto possano essere selezionate. Esempi di questi nomi descrittivi includono "Small", "Medium" e "Large" per le taglie e "Black" e "Brown" per i colori. Tuttavia, se un prodotto supporta molte varianti, sono necessarie più selezioni per visualizzare l'immagine per ciascuna variante di prodotto. Pertanto, può essere un processo lento e noioso per i clienti sfogliare e selezionare le varianti di prodotto.

Quando le dimensioni vengono visualizzate come campioni sui PDP, i clienti ottengono un'anteprima visiva delle variazioni di un prodotto. Possono sfogliare facilmente un'ampia varietà di colori, motivi e trame e possono visualizzare rapidamente diverse combinazioni di variazioni del prodotto.

La funzione di visualizzazione delle dimensioni come campioni consente a Commerce di utilizzare codici e immagini esadecimali (esadecimali) per mostrare le dimensioni come campioni. Inoltre, dimensioni simili, come i colori, possono essere raggruppate nelle pagine dell'elenco dei prodotti. Ad esempio, un cliente sta cercando prodotti blu. Se i vari valori di dimensione blu sono raggruppati insieme, la pagina dell'elenco dei risultati di ricerca mostra i prodotti con le diverse sfumature di blu. Il raggruppamento delle dimensioni migliora notevolmente l'esperienza di perfezionamento del prodotto e aiuta i clienti a trovare più prodotti tramite una singola query di ricerca del prodotto.

> [!NOTE]
> La funzione di visualizzazione delle dimensioni come campioni è disponibile a partire dalla versione 10.0.20 di Dynamics 365 Commerce.

La seguente illustrazione mostra un esempio in cui i colori vengono visualizzati come campioni su un PDP di Commerce.

![Esempio di colori mostrati come campioni in una pagina dei dettagli del prodotto.](../dev-itpro/media/swatch_pdp.png)

La seguente illustrazione mostra un esempio in cui i colori vengono visualizzati come campioni su una pagina con l'elenco di risultati della ricerca di Commerce.

![Esempio di colori mostrati come campioni in una pagina con l'elenco di risultati della ricerca.](../dev-itpro/media/swatch_searchresults.PNG)

## <a name="enable-the-display-dimensions-as-swatches-feature-in-commerce-headquarters"></a>Abilitare la funzione di visualizzazione delle dimensioni come campioni in Commerce Headquarters

Per abilitare la funzionalità di visualizzazione delle dimensioni come campioni in Commerce Headquarters, seleziona **Aree di lavoro \> Gestione funzionalità** e attiva la funzionalità **Abilita un meccanismo per rappresentare le dimensioni come campioni**. Quando questo flag di funzionalità è abilitato, vengono aggiunti tre nuovi campi per ogni dimensione nelle tabelle appropriate in Commerce Headquarters: **Codice esadecimale**, **URL** (per le immagini) e **RefinerGroup**.

## <a name="configure-dimension-values-in-commerce-headquarters"></a>Configurare i valori delle dimensioni in Commerce Headquarters

La funzione di visualizzazione delle dimensioni come campioni è supportata per taglia, stile e colore. I valori del codice esadecimale e dell'URL dell'immagine per le dimensioni appropriate possono essere specificati in Commerce Headquarters. Per impostazione predefinita, se non vengono forniti i valori del codice esadecimale e dell'URL dell'immagine per una dimensione, il sistema mostrerà il testo del nome descrittivo della dimensione.

La configurazione può essere eseguita a uno dei seguenti livelli:

- **Dimensione**: in Commerce Headquarters, apri la pagina per una dimensione cercando **Colore**, **Taglia** o **Stile**. In ogni pagina, una griglia elenca i valori delle dimensioni. Puoi gestire l'ordine di visualizzazione, il codice esadecimale e i valori dell'URL dell'immagine. Nella figura seguente è illustrato una configurazione di esempio nella pagina **Colori**.

    ![Esempio di configurazione delle dimensioni nella pagina Colori.](../dev-itpro/media/swatch_Color.PNG)

- **Gruppo di dimensioni**: in Dynamics 365 Commerce, puoi usare la proprietà **RefinerGroup** per creare gruppi di dimensioni. Se sono definiti gruppi di dimensioni, apri la pagina appropriata cercando **Gruppo di colori**, **Gruppo di taglie** o **Gruppo di stili**. In ogni pagina puoi gestire il codice esadecimale, l'URL dell'immagine e i valori del gruppo di affinamento. Nella figura seguente è illustrato una configurazione di esempio nella pagina **Gruppi di colori**.

    ![Esempio di configurazione delle dimensioni nella pagina Gruppi di colori.](../dev-itpro/media/swatch_colorGroup.PNG)

- **Dimensione del prodotto (durante la creazione del prodotto)** quando crei un nuovo prodotto, puoi utilizzare la pagina **Dimensioni del prodotto** per inserire i valori delle dimensioni. Per i prodotti esistenti, i campi **Codice esadecimale**, **URL** (per le immagini) e **RefinerGroup** potrebbero essere già impostati. Tuttavia, è possibile modificare i valori in base alle esigenze. Nella figura seguente è illustrato una configurazione di esempio nella pagina **Dimensioni prodotto**.

    ![Esempio di configurazione delle dimensioni nella pagina Dimensioni prodotto.](../dev-itpro/media/swatch_product_dimensions.PNG)

> [!NOTE]
> Il processo di gestione delle configurazioni del codice esadecimale e dell'URL dell'immagine segue lo stesso modello utilizzato per gestire l'ordine di visualizzazione delle dimensioni.

## <a name="configure-dimension-values-by-using-hex-codes"></a>Configurare i valori delle dimensioni utilizzando codici esadecimali

Per la maggior parte delle dimensioni colore, è necessario fornire un valore di colore del codice esadecimale nelle pagine delle dimensioni in Commerce Headquarters. Ad esempio, il colore nero dovrebbe avere un valore di codice esadecimale di **#00000**. Quando Commerce esegue il rendering di una pagina del sito, il codice esadecimale è rappresentato da un campione colorato.

La figura seguente mostra un esempio in cui le dimensioni del colore sono configurate utilizzando valori di codice esadecimale.

![Esempio di configurazione delle dimensioni che utilizza codici esadecimali.](../dev-itpro/media/swatch_color_hexcode.png)

## <a name="configure-dimension-values-by-using-image-urls"></a>Configurare i valori delle dimensioni utilizzando gli URL delle immagini

Alcune dimensioni di colore rappresentano motivi, non tinte unite. Ad esempio, una dimensione di colore potrebbe essere descritta come "leopardo". In questi casi, puoi rappresentare in modo più efficace le dimensioni del colore utilizzando le immagini pubblicate invece dei codici esadecimali per i campioni.

Devi caricare ciascuna immagine nel generatore di siti di Commerce e pubblicarla. Quindi immetti l'URL dell'immagine per l'immagine pubblicata nelle pagine delle dimensioni appropriate in Commerce Headquarters. Se una dimensione è stata selezionata per la visualizzazione come campione, ma non è stato definito un codice esadecimale, Commerce eseguirà una ricerca dell'immagine durante il rendering della pagina. Se la ricerca dell'immagine non riesce, Commerce mostrerà il testo del nome descrittivo della dimensione.

Nella figura seguente è illustrato un esempio in cui gli URL dell'immagine vengono utilizzati per la configurazione nella pagina **Colori**.

![Esempio di configurazione delle dimensioni che utilizza gli URL dell'immagine.](../dev-itpro/media/swatch_color_urls.PNG)

Puoi utilizzare un modello multimediale per definire gli URL delle immagini, proprio come puoi fare per le immagini dei prodotti e delle categorie. Quando carichi immagini in Site Builder, le convenzioni sui nomi dei file e i percorsi dei file devono essere coerenti.

Nella figura seguente è illustrato un esempio in cui gli URL dell'immagine vengono utilizzati per la configurazione di un modello multimediale.

![Esempio di configurazione del modello multimediale.](../dev-itpro/media/swatch_media_template.PNG)

## <a name="configure-dimension-values-by-using-both-hex-codes-and-image-urls"></a>Configurare i valori delle dimensioni utilizzando codici esadecimali e URL delle immagini

Per la maggior parte delle dimensioni colore, puoi configurare sia codici esadecimali che URL immagine. La logica di fallback del rendering di Commerce cercherà automaticamente un codice esadecimale o un URL di immagine per mostrare un campione di colore. Utilizzando sia i codici esadecimali che gli URL delle immagini per configurare le dimensioni del colore, contribuisci a semplificare la gestione delle immagini quando il numero di colori è elevato.

Nella figura seguente è illustrato un esempio in cui codici esadcimali e gli URL dell'immagine vengono utilizzati per la configurazione nella pagina **Colori**.

![Esempio di configurazione delle dimensioni che utilizza codici esadecimali e URL dell'immagine.](../dev-itpro/media/swatch_color_hexandimage.png)

## <a name="configure-refiner-groups"></a>Configurare i gruppi di affinamento

Quando definisci un codice esadecimale o un URL immagine per un valore di dimensione, puoi anche specificare un valore per il campo **RefinerGroup**. Questo campo definisce la dimensione da utilizzare per raggruppare valori di dimensione simili nell'esperienza di affinamento.

Ad esempio, se i valori della dimensione del colore sono "blu", "blu plaid", "blue wash" e "blu scuro", ogni valore viene mappato a un codice esadecimale o URL immagine diverso. Pertanto, ogni valore apparirà come un colore diverso sui PDP e sulle schede prodotto per i prodotti appropriati. Tuttavia, se si associano tutti questi valori di dimensione del colore a un valore **RefinerGroup** di **Blu**, una ricerca di prodotti "blu" genererà risultati di ricerca nella pagina elenco per i prodotti con valori di colore delle dimensioni "blu", "blu plaid", "blu wash" e "blu scuro".

L'esempio nella figura seguente mostra la relazione tra le proprietà **Colore** e **RefinerGroup** in Commerce Headquarters.

![Esempio di gestione di un gruppo di affinamento.](../dev-itpro/media/swatch_refiner_group.png)

## <a name="manage-images-in-commerce-site-builder"></a>Gestire immagini in Commerce Site Builder

Se vengono utilizzati URL immagine per qualsiasi valore di dimensione, le immagini corrispondenti devono essere caricate in Commerce Site Builder. La posizione di ciascuna immagine deve corrispondere al nome del file e al percorso della cartella definiti per l'immagine in Commerce Headquarters. I file di immagine devono essere caricati nelle posizioni delle categorie appropriate in Site Builder. Ad esempio, le immagini a colori devono essere caricate nella cartella della categoria **Colore**. Per ulteriori informazioni su come caricare immagini in Site Builder, vedi [Caricare immagini](../dam-upload-images.md).

La figura seguente mostra un esempio in cui la finestra di dialogo **Carica file** viene utilizzata per caricare le immagini nella libreria multimediale di Site Builder. Evidenzia le categorie **Taglia**, **Colore** e **Stile** disponibili per la selezione.

![Esempio di categorie di file di immagine durante il caricamento nella libreria multimediale di Creazione di siti Web.](../dev-itpro/media/swatch_sitebuilder.png)

## <a name="enable-swatch-display-on-e-commerce-site-pages"></a>Abilitare la visualizzazione dei campioni nelle pagine del sito di e-commerce

Prima che i campioni possano essere visualizzati nelle pagine del sito e-commerce che richiedono la selezione delle dimensioni, come PDP e pagine di elenco, è necessario configurare le impostazioni del sito delle dimensioni in Commerce Headquarters. Per altre informazioni, vedi [Applicare le impostazioni del sito per le dimensioni](../dimension-settings.md).

Inoltre, è consigliabile abilitare la proprietà **Includi gli attributi del prodotto nei risultati di ricerca** per i moduli dei risultati di ricerca. Se il tuo sito utilizza pagine di categorie personalizzate, è consigliabile aggiornare i moduli dei risultati di ricerca utilizzati in tali pagine, in modo che la proprietà **Includi gli attributi del prodotto nei risultati di ricerca** sia abilitata. Per ulteriori informazioni, vedi [Modulo dei risultati della ricerca](../search-result-module.md).

## <a name="inventory-awareness-on-swatches"></a>Consapevolezza dell'inventario con campioni

I campioni includono la funzionalità facoltativa di mostrare la disponibilità nell'inventario di un colore o di una dimensione di una variante prodotto. Ad esempio, un prodotto viene venduto in più taglie, ma alcune taglie sono esaurite. In questo caso, i campioni dei prodotti esauriti vengono visualizzati differentemente per indicare che non sono disponibili. Questa funzionalità consente di ridurre il numero di clic dei clienti necessari per determinare la disponibilità di un prodotto.

La funzionalità Disponibilità dell'inventario con campioni può essere configurata per l'uso nelle pagine dei dettagli dei prodotti e nelle pagine di ricerca o di elenco di categorie in cui vengono visualizzati i campioni. Per attivarla, devi impostare la proprietà **Aggiorna multimedia alla selezione delle dimensioni** su **True** nel [modulo Galleria multimediale](../media-gallery-module.md). Questa impostazione consente l'aggiornamento delle immagini nella galleria multimediale quando vengono selezionate le dimensioni. 

> [!IMPORTANT]
> La funzionalità Disponibilità dell'inventario con campioni è disponibile a partire dalla versione 10.0.21 di Commerce. Richiede l'installazione del pacchetto della libreria di moduli di Commerce versione 9.31.

L'illustrazione seguente mostra un esempio di consapevolezza dell'inventario con campioni delle taglie di una pagina di dettagli del prodotto.

![Esempio di consapevolezza dell'inventario con campioni delle taglie in una pagina dettagli del prodotto](../dev-itpro/media/swatch_inventory.png)

## <a name="display-swatches-in-pos-and-other-channels"></a>Visualizza i campioni in POS e altri canali

Commerce attualmente non dispone di un'implementazione predefinita che supporti la visualizzazione dei campioni nel POS e in altri canali. Tuttavia, puoi implementare la funzionalità di visualizzazione dei campioni come estensione poiché le API del canale restituiscono i codici esadecimali e gli URL immagine necessari per il rendering dei campioni.

## <a name="additional-resources"></a>Risorse aggiuntive

[Modulo dei risultati di ricerca](../search-result-module.md)

[Applicare le impostazioni del sito per le dimensioni](../dimension-settings.md)

[Dimensioni prodotto](../../supply-chain/pim/product-dimensions.md)

[Carica immagine](../dam-upload-images.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
