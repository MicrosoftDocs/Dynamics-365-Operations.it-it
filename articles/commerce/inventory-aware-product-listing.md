---
title: Elenco dei prodotti in base all'inventario
description: Questo articolo descrive come le organizzazioni possono configurare le pagine di elenco dei prodotti sul loro sito Web di e-commerce di Microsoft Dynamics 365 Commerce in modo che siano basati sull'inventario.
author: boycez
ms.date: 08/31/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: boycez
ms.search.validFrom: 2022-08-23
ms.openlocfilehash: e33a4dd8650ee2e371c51c5a19e955f2d2bdade2
ms.sourcegitcommit: 1d5cebea3e05b6d758cd01225ae7f566e05698d2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/02/2022
ms.locfileid: "9405553"
---
# <a name="inventory-aware-product-listing"></a>Elenco dei prodotti in base all'inventario

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

Questo articolo descrive come le organizzazioni possono configurare le pagine di elenco dei prodotti sul loro sito Web di e-commerce di Microsoft Dynamics 365 Commerce in modo che siano basati sull'inventario. Le pagine dell'elenco dei prodotti includono pagine di destinazione delle categorie e pagine dei risultati della ricerca.

Gli acquirenti generalmente si aspettano che la ricerca di un prodotto tramite un sito Web di e-commerce sia basata sull'inventario, in modo che possano decidere cosa fare se non ci sono scorte per un prodotto. La categoria [Libreria di moduli di Commerce](starter-kit-overview.md) e i moduli dei risultati di ricerca possono essere configurati per incorporare i dati di inventario. In questo modo, possono offrire le seguenti esperienze:

- Visualizzare le etichette del livello di inventario accanto ai prodotti.
- Nascondere i prodotti esauriti dall'elenco dei prodotti.
- Sposta i prodotti esauriti alla fine delle pagine di elenco dei prodotti.
- Supportare il filtraggio dei prodotti basato sull'inventario.

Per abilitare queste esperienze, devi prima abilitare la funzionalità **Individuazione di prodotti e-commerce migliorata basata sulle scorte** in Commerce headquarters.

> [!NOTE]
> In Commerce versione 10.0.29 e successive, la funzionalità **Individuazione di prodotti e-commerce migliorata basata sulle scorte** è abilitata per impostazione predefinita.

## <a name="set-up-product-attribute-for-inventory-availability"></a>Configurare l'attributo del prodotto per la disponibilità di scorte

L'elenco dei prodotti basati sull'inventario utilizza il framework degli attributi del prodotto. Come prerequisito, è necessario creare un attributo di prodotto dedicato per acquisire i dati sulla disponibilità delle scorte.

Per configurare l'attributo di prodotto per la disponibilità di scorte in Commerce headquarters, seguire questi passaggi.

1. Andare a **Retail e Commerce \> Vendita al dettaglio e commercio IT \> Prodotti e inventario \> Popola attributi di prodotto con livello scorte**.
1. Nella finestra di dialogo **Popola attributi di prodotto con livello scorte**, nel campo **Nome tipo e attributo di prodotto**, inserisci un nome personalizzato per l'attributo del prodotto dedicato che verrà creato per acquisire i dati di inventario.
1. Nel campo **Disponibilità scorte basata su**, seleziona il tipo di quantità su cui basare il calcolo del livello di scorte: **Fisico disponibile** o **Totale disponibile**.
1. Impostare l'opzione **Elaborazione batch** su **Sì**.
1. Seleziona **OK**.

> [!NOTE]
> Per un calcolo coerente del livello di scorte tra le pagine del sito web di e-commerce, assicurarsi di selezionare lo stesso tipo di quantità nel campo **Disponibilità scorte basata su** per il processo **Popola attributi di prodotto con livello scorte** e l'impostazione **Livello scorte basato su** nel generatore di siti di Commerce.

Dopo aver creato l'attributo del prodotto dedicato, il passaggio successivo consiste nel configurare l'attributo per il canale online.

Per configurare l'attributo per il canale online in Commerce headquarters, seguire questi passaggi.

1. Passare a **Retail e Commerce \> Impostazione canale \> Categorie canale e attributi del prodotto**.
1. Seleziona il canale online per il quale abilitare l'esperienza dell'elenco di prodotti basata sull'inventario.
1. Selezionare e aprire un gruppo di attributi associato e aggiungere il nuovo attributo di prodotto appena creato.
1. Andare a **Retail e Commerce \> Retail e Commerce IT \> Programmazione della distribuzione** ed eseguire il processo **1150** (**Catalogo**). È consigliabile pianificare questo processo come processo batch in quanto un processo batch viene eseguito con la stessa frequenza del processo **Popola attributi di prodotto con livello scorte**.

> [!NOTE]
> In Commerce versione 10.0.26 e precedenti, dopo aver aggiunto l'attributo del prodotto disponibilità di scorte a un gruppo di attributi, è necessario selezionare anche **Imposta metadati di attributi**, quindi attivare le opzioni **Mostra attributo sul canale**, **Recuperabile**, **Ridefinizione possibile** e **Esecuzione query possibile** per il nuovo attributo del prodotto.

## <a name="configure-the-display-behavior-for-out-of-stock-products-on-product-listing-pages"></a>Configurare il comportamento di visualizzazione per i prodotti esauriti nelle pagine dell'elenco dei prodotti

Dopo che tutti i passaggi di configurazione precedenti sono stati completati, i criteri di affinamento nelle pagine delle categorie e dei risultati di ricerca disporranno di un'opzione di filtro basata sull'inventario. Verrà visualizzata un'etichetta del livello di scorte per ogni riquadro del prodotto visualizzato nella pagina.

La pagina della categoria e dei risultati della ricerca mostra i prodotti a livello principale, non a livello di variante di prodotto. Il livello di scorte visualizzato accanto a ciascun prodotto è un livello di scorte aggregato determinato dal livello di inventario di tutte le varianti di un prodotto. Il livello di scorte di una variante viene calcolato in base alle scorte disponibili di tale variante nel magazzino predefinito del canale online di Commerce headquarters. Il livello di scorte di un prodotto principale ha due possibili valori che rappresentano gli stati in magazzino e esaurito. Una rappresentazione generale prodotto è considerata esaurita quando tutte le sue varianti sono esaurite. Altrimenti, il prodotto è considerato in stock. L'etichetta per il valore viene recuperata dalla definizione [livello di scorte](inventory-buffers-levels.md). Se non viene definito alcun livello di scorte, lo etichette predefinite (in inglese) sono **Disponibile** e **Esaurito**.

Puoi configurare l'opzione **Impostazioni inventario per le pagine elenco prodotti** nel generatore di siti di Commerce per controllare il modo in cui la pagina delle categorie e dei risultati della ricerca mostra i prodotti esauriti. Per ulteriori informazioni, vedere [Applicare impostazioni relative alle scorte](inventory-settings.md).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
