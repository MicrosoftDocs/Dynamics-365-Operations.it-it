---
title: Convenzioni
description: Questo argomento descrive come impostare le convenzioni per stabilire come contabilizzare i costi in Contabilità inventario globale.
author: AndersGirke
ms.date: 06/18/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2021-06-18
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 2d629b082b423edf417714b8362be3364bc861e78f62d430a4d7083b8c49611a
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6773419"
---
# <a name="conventions"></a>Convenzioni

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]

Una convenzione è un contenitore per un set di criteri che influiscono sul comportamento del sistema. In base ai requisiti aziendali, è necessario definire le convenzioni utilizzando una combinazione dei vari criteri che stabiliscono come contabilizzare i costi in Contabilità inventario globale. È possibile associare ogni convenzione a uno o più libri contabili per garantire la coerenza nei criteri contabili applicati tra i libri contabili.

Per impostare le convenzioni, vai a **Contabilità inventario globale \> Impostazione \> Convenzioni**. Per ciascuna convenzione imposta i seguenti campi:

- **Nome**: immetti il nome della convenzione.
- **Descrizione** - Immetti una descrizione della convenzione.
- **Criteri oggetto di costo** - Seleziona un criterio oggetto di costo. Questi criteri determinano il livello di granularità che il sistema applica per calcolare e mantenere il valore dell'inventario. Di seguito vengono illustrate le opzioni predefinite disponibili:

    - Prodotto
    - Prodotto - Sito
    - Prodotto - Sito - Magazzino

    Ad esempio, se selezioni *Prodotto - Sito*, per ogni movimento scorte (in entrata o in uscita), il sistema calcola e mantiene il costo di inventario di ciascun prodotto a livello di sito. Pertanto, i movimenti scorte a livelli inferiori, come il livello di magazzino, non influiscono sul valore di inventario. Un esempio di trasferimento a livello di magazzino è un trasferimento di articolo tra due magazzini in un sito. Allo stesso modo, non è possibile visualizzare il costo delle scorte a un livello inferiore, come il livello di magazzino.

- **Criterio di base di misura di input** – Selezionare un criterio di base di misura di input. Questi criteri determinano i costi che devono confluire nel conto di magazzino e i costi che devono essere addebitati. Le seguenti opzioni sono rilevanti per le società commerciali:

    - **Normale storico** – Tutti i componenti di costo confluiscono nel conto di magazzino.
    - **Standard** – Il costo standard confluisce nei conti di magazzino e la differenza tra il costo applicato e i costi effettivi viene addebitata ai conti di scostamento. Se vuoi creare un criterio di base di misura di input *Standard* è necessario prima creare un listino prezzi in cui il criterio può cercare il costo standard dell'articolo.
    - **Listini prezzi** – La Contabilità inventario globale supporta il recupero dei prezzi degli articoli da più persone giuridiche. È possibile definire un listino prezzi che verrà utilizzato dai criteri di base di misura di input. In questo modo il sistema saprà dove cercare il prezzo dell'articolo. Per impostare i listini prezzi, effettua le seguenti operazioni:

        1. Nel campo **Nome** immettere un nome.
        1. Nel campo **Descrizione** immettere una descrizione.
        1. Nel campo **Tipo di costo** seleziona un tipo di costo (*Costo standard* o *Costo pianificato*).
        1. Nel campo **Tipo di prezzo** seleziona un tipo di prezzo (*Costo*, *Acquisto*, o *Prezzo di vendita*).
        1. Aggiungi una versione di determinazione costi.
        1. Nel riquadro azioni, seleziona **Prezzo** per convalidare i prezzi degli articoli nel listino prezzi.

- **Criteri di assunzione del flusso dei costi** – Seleziona un criterio di assunzione del flusso dei costi. Questi criteri determinano il modo in cui i costi vengono rimossi dall'inventario e riportati come costo delle merci vendute. Di seguito vengono illustrate le opzioni predefinite disponibili:

    - Medio
    - Specifico – Batch

    > [!NOTE]
    > La Contabilità inventario globale è un sistema di inventario perpetuo. Pertanto, il sistema tiene traccia del valore dell'inventario transazione per transazione.

- **Criteri dell'elemento di costo** – È possibile definire i criteri degli elementi di costo e collegarli a questo campo. Un *elemento di costo* è il costo di una risorsa usata da un evento. È possibile utilizzare gli elementi di costo per tenere traccia e classificare i costi. Per creare i criteri per gli elementi di costo, inserisci le informazioni nei seguenti punti:

    - Campo **Nome**
    - Campo **Descrizione**
    - Elenco di **elementi di costo**
    - Griglia delle **regole**

    Se non vuoi suddividere ulteriormente il valore dell'inventario, devi creare un elenco di elementi di costo con un singolo elemento di costo. È quindi necessario creare un criterio dell'elemento di costo per mappare tutti i tipi di misura pertinenti (componenti di costo) a quell'elemento di costo.
