---
title: Moduli di confronto dei prodotti
description: Questo articolo descrive i moduli di confronto dei prodotti e come implementarli di modo che i clienti possano confrontare i prodotti nei siti Web di e-commerce di Microsoft Dynamics 365 Commerce.
author: ashishmsft
ms.date: 08/09/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: asharchw
ms.search.validFrom: 2022-02-28
ms.openlocfilehash: 6fd851ce6b32d0772c3fe23c4d7bd4dae2616fdc
ms.sourcegitcommit: b1df4db7facb5e7094138836c41a65c4a158f01d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/13/2022
ms.locfileid: "9474128"
---
# <a name="product-comparison-modules"></a>Moduli di confronto dei prodotti

[!include [banner](../includes/banner.md)]

Questo articolo descrive i moduli di confronto dei prodotti e come implementarli di modo che i clienti possano confrontare i prodotti nei siti Web di e-commerce di Microsoft Dynamics 365 Commerce.

> [!NOTE]
> I moduli di confronto dei prodotti e dei pulsanti di confronto dei prodotti sono disponibili a partire dalla versione 10.0.29 di Dynamics 365 Commerce. Possono essere utilizzati sia per i siti Web business-to-consumer (B2C) che business-to-business (B2B).

La funzionalità di confronto dei prodotti consente agli acquirenti di confrontare i dettagli dei prodotti in una pagina di confronto dei prodotti per aiutarli a prendere decisioni di acquisto migliori. Questa funzionalità viene configurata nel generatore di siti di Commerce utilizzando il modulo di confronto dei prodotti. Nelle pagine elenco di prodotti (PLP), come le pagine dei risultati di categoria, dei risultati di ricerca e delle raccolte di prodotti, puoi configurare un pulsante per il confronto dei prodotti che consente agli acquirenti di aggiungere prodotti a una barra di confronto. Questa funzionalità viene configurata nel generatore di siti utilizzando il modulo del pulsante di confronto dei prodotti, che funziona come il [modulo di visualizzazione rapida](quick-view-module.md).

Quando gli utenti del sito aggiungono prodotti per il confronto selezionandoli nei riquadri dei prodotti, nella parte inferiore della pagina viene visualizzata una barra di confronto. Questa barra mostra i prodotti che l'acquirente sta attualmente confrontando, insieme a brevi anteprime dei prodotti. Gli utenti del sito possono anche aggiungere prodotti dalle pagine dei dettagli del prodotto (PDP) e possono aggiungere specifiche varianti dei prodotti da confrontare con le rappresentazioni generali dei prodotti.

Dopo che i clienti hanno aggiunto alcuni prodotti alla barra di confronto, possono selezionare **Confronta** per accedere a una pagina di confronto dei prodotti. La pagina di confronto dei prodotti mostra i dettagli di ciascun prodotto selezionato di modo che i clienti possano confrontare immagini, prezzi, dimensioni dei prodotti (taglia, stile e colore), informazioni aggregate sulle valutazioni e altri attributi dei prodotti.

L'illustrazione seguente mostra esempi del pulsante Confronta prodotti, del pulsante Rimuovi dal confronto, della barra di confronto e della pagina di confronto dei prodotti.

![La panoramica del confronto dei prodotti che mostra il pulsante Confronta prodotti, il pulsante Rimuovi dal confronto, la barra di confronto e la pagina di confronto dei prodotti.](./media/Product-Comparison-Overview.png)

> [!NOTE]
> - La pagina di confronto dei prodotti confronta un insieme predefinito di proprietà dei prodotti e tutti gli attributi che possono essere visualizzati in una pagina PDP di un determinato prodotto.
> - Proprietà come la modalità di consegna, le scorte disponibili e l'unità di misura non possono essere visualizzate in una pagina di confronto dei prodotti.
> - I clienti possono aggiungere prodotti di diverse categorie alla barra di confronto, a condizione che i prodotti provengano dallo stesso catalogo.
> - La funzionalità di confronto dei prodotti è attualmente limitata al confronto dei prodotti di un singolo catalogo. Gli utenti del sito non possono confrontare prodotti di differenti cataloghi.
> - Dovresti assicurarti che la proprietà **Lato client modulo di rendering** sia deselezionata per tutti i moduli di confronto dei prodotti.
> - Verifica che la memorizzazione nella cache a livello di pagina sia disabilitata per tutte le pagine in cui viene utilizzato il modulo di confronto dei prodotti. Queste pagine includono pagine PDP, PLP e di confronto dei prodotti. Per ulteriori informazioni, vedi [Configurare la memorizzazione della pagina nella cache](e-commerce-extensibility/page-caching.md).

Nella figura seguente viene illustrato un esempio di pagina di confronto dei prodotti.

![Pagina di confronto dei prodotti.](./media/Product-Comparison-Page.png)

## <a name="add-the-product-comparison-module-to-a-new-product-comparison-page"></a>Aggiungere il modulo di confronto dei prodotti a una nuova pagina di confronto dei prodotti

Puoi creare una pagina di confronto dei prodotti dedicata aggiungendo un modulo di confronto dei prodotti al corpo di una pagina. Oltre a consentire ai clienti di confrontare i dettagli di diversi prodotti, puoi configurare il modulo di confronto dei prodotti per offrire ai clienti la possibilità di completare rapidamente l'acquisto dopo aver confrontato i prodotti. Il modulo di confronto dei prodotti contiene anche uno slot **Confronto vuoto**, in cui puoi aggiungere un modulo di blocco dei contenuti che descriva lo stato vuoto (ad esempio "Il confronto dei prodotto è vuoto").

Per aggiungere un modulo di confronto dei prodotti a una nuova pagina di confronto dei prodotti, procedi come segue.

1. Accedere a **Pagine** e quindi selezionare **Nuovo** per creare una nuova pagina.
1. Nella finestra di dialogo **Crea una nuova pagina**, sotto **Nome pagina** immetti un nome di pagina appropriato (ad esempio **Confronto prodotti**), quindi seleziona **Avanti**.
1. Sotto **Scegli un modello**, seleziona il modello appropriato (ad esempio, il modello utilizzato dalla pagina di categoria predefinita), quindi seleziona **Avanti**.
1. Sotto **Scegli un layout**, seleziona un layout di pagina (ad esempio, **Layout flessibile**), quindi seleziona **Avanti**.
1. In **Verifica e termina**, rivedere la configurazione della pagina. Se è necessario modificare le informazioni sulla pagina, selezionare **Indietro**. Se le informazioni sulla pagina sono corrette, selezionare **Crea pagina**.
1. Nello slot **Principale** seleziona i puntini di sospensione (**...**), quindi seleziona **Aggiungi modulo**.
1. Nella finestra di dialogo **Seleziona moduli** selezionare il modulo **Contenitore** e quindi **OK**.
1. Nello slot **Contenitore** seleziona i puntini di sospensione (**...**) quindi seleziona **Aggiungi modulo**.
1. Nella finestra di dialogo **Seleziona moduli**, seleziona il modulo **Confronto prodotti** e quindi **OK**.
1. Nello slot **Pulsante di visualizzazione rapida** seleziona i puntini di sospensione (**...**), quindi seleziona **Aggiungi modulo**.
1. Nella finestra di dialogo **Seleziona moduli** seleziona il modulo **Visualizzazione rapida prodotti** e quindi **OK**.
1. Nel riquadro proprietà a destra, configura le proprietà del modulo **Visualizzazione rapida prodotti**.
1. Nello slot **Confronto vuoto**, seleziona i puntini di sospensione (**...**), quindi seleziona **Aggiungi modulo**.
1. Nella finestra di dialogo **Seleziona moduli** seleziona il modulo **Blocco contenuto** e quindi **OK**.
1. Nel riquadro proprietà a destra, configura le proprietà del modulo **Blocco contenuto**. 
1. Selezionare **Salva**, quindi selezionare **Anteprima** per visualizzare l'anteprima della pagina.
1. Selezionare **Fine modifica** per archiviare la pagina, quindi selezionare **Pubblica** per pubblicarla.

La figura seguente mostra un esempio di pagina di confronto vuota nel generatore di siti.

![Moduli di confronto dei prodotti.](./media/Product-comparison-module.png)

## <a name="add-a-product-comparison-button-to-product-tiles-on-search-and-category-results-pages"></a>Aggiungere un pulsante di confronto dei prodotti ai riquadri dei prodotti nelle pagine dei risultati di ricerca e di categoria

Il pulsante di confronto dei prodotti consente agli utenti di aggiungere rapidamente un prodotto alla barra di confronto quando esaminano i prodotti in una pagina elenco. Possono aggiungere uno o più prodotti alla barra di confronto da una pagina elenco senza dover accedere a una pagina PDP.

Il pulsante di confronto dei prodotti è supportato dai moduli della raccolta di prodotti, dei risultati della ricerca e della casella di acquisti PDP.

Per aggiungere un pulsante di confronto dei prodotti ai riquadri dei prodotti nelle pagine dei risultati di ricerca e di categoria, procedi come segue.

1. Nel generatore di siti, vai a **Pagine** e apri la pagina di categoria a cui vuoi aggiungere un pulsante di confronto dei prodotti.
1. Nello slot **Principale** seleziona i puntini di sospensione (**...**), quindi seleziona **Aggiungi modulo**.
1. Nella finestra di dialogo **Seleziona moduli** seleziona il modulo **Risultati di ricerca** e quindi **OK**.
1. Nello slot **Pulsante di confronto dei prodotti** del modulo **Risultati di ricerca**, seleziona i puntini di sospensione (**...**) e quindi **Aggiungi modulo**.
1. Nella finestra di dialogo **Seleziona moduli**, seleziona il modulo **Pulsante di confronto dei prodotti** e quindi **OK**.
1. Nel riquadro proprietà a destra, configura le proprietà del modulo **Pulsante di confronto dei prodotti**.
1. Selezionare **Salva**, quindi selezionare **Anteprima** per visualizzare l'anteprima della pagina.
1. Selezionare **Fine modifica** per archiviare la pagina, quindi selezionare **Pubblica** per pubblicarla.

## <a name="specify-the-maximum-number-of-products-to-show-in-the-comparison-tray"></a>Impostare il numero massimo di prodotti da mostrare nella barra di confronto

Puoi impostare il numero massimo di prodotti da mostrare nella barra di confronto selezionando **Impostazioni sito \> Estensioni** nel generatore di siti. Puoi configurare limiti massimi distinti per le visualizzazioni in dispositivi desktop e dispostivi mobili/tablet. Per impostazione predefinita, non verrà applicato alcun limite se non viene definito alcun limite massimo.

> [!NOTE]
> Per un'esperienza di navigazione ottimale, ti consigliamo di impostare il numero massimo di prodotti nella barra di confronto su **2** per il viewport di dispositivi mobili e su **4** per il viewport di dispositivi desktop per ridurre la quantità di scorrimento orizzontale necessaria.

Per impostare il numero massimo di prodotti nella barra di confronto, procedi come segue.

1. Nel generatore di siti, vai a **Impostazioni sito \> Estensioni**.
1. Per la proprietà **Prodotti nel limite di confronto - dispositivi desktop**, immetti il numero massimo di prodotti che devono essere mostrati nella barra di confronto per le viewport di dispositivi desktop.
1. Per la proprietà **Prodotti nel limite di confronto - dispositivi mobili e tablet**, immetti il numero massimo di prodotti che devono essere mostrati nella barra di confronto per le viewport di dispositivi mobili e tablet.
1. Nella barra dei comandi, seleziona **Salva e pubblica**.

![Impostazioni del sito per limitare i prodotti nella barra di confronto.](./media/Site-settings-to-limit-products-in-comparison-tray.png)
