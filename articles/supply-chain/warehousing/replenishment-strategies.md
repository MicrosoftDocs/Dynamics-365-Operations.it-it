---
title: Strategie di rifornimento
description: Questo articolo fornisce informazioni sulle strategie di rifornimento e spiega come utilizzare il campo Strategia di rifornimento nelle righe del modello di rifornimento della domanda ciclo per selezionare la modalità di rifornimento.
author: Mirzaab
ms.date: 10/29/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-10-29
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: 1245d07436a9b57ee4f0402687e7a4367668cbfa
ms.sourcegitcommit: 203c8bc263f4ab238cc7534d4dd902fd996d2b0f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/23/2022
ms.locfileid: "9336277"
---
# <a name="replenishment-strategies"></a>Strategie di rifornimento

[!include [banner](../includes/banner.md)]

I modelli definiti nella pagina **Modelli di rifornimento** includono le righe del modello di rifornimento della domanda ciclo che consentono di selezionare la modalità di rifornimento. Ogni riga ora include un campo **Strategia di rifornimento**.

La strategia *Quantità di domanda ciclo* è la strategia predefinita. È la strategia di rifornimento utilizzata prima dell'introduzione del campo **Strategia di rifornimento**. Utilizza le direttive ubicazione di rifornimento per trovare le ubicazioni che possono essere rifornite. Quindi rifornisce quelle ubicazioni fino a coprire la domanda.

La strategia *Capacità massima ubicazione* introduce alcune nuove funzionalità. Come la strategia *Quantità di domanda ciclo*, questa strategia utilizza le direttive ubicazione di rifornimento per trovare le ubicazioni che possono essere rifornite, quindi rifornisce quelle ubicazioni fino a coprire la domanda. È diversa dalla strategia *Quantità di domanda ciclo* in quanto tutte le ubicazioni rifornite vengono rifornite alla loro capacità massima, come definito dai limiti di stoccaggio dell'ubicazione. La strategia *Capacità massima ubicazione* cerca di creare lavoro per portare la quantità richiesta, più una quantità extra, per riempire le ubicazioni che vengono rifornite. Tuttavia, in alcuni casi, il tentativo potrebbe non riuscire. Ad esempio, le ubicazioni in blocco potrebbero non avere inventario sufficiente per coprire la quantità extra. In questi casi, il sistema rileva l'errore e tenta di ripristinarlo.

L'alta stagione è un esempio di una situazione in cui la strategia *Capacità massima ubicazione* è preferibile alla strategia *Quantità di domanda ciclo*. Durante l'alta stagione, alcuni articoli potrebbero essere venduti a volumi elevati. Pertanto, potrebbe essere necessario rifornire in modo proattivo le ubicazioni di prelievo rilevanti il più possibile, per ridurre il numero di ID lavoro creati per il rifornimento.

> [!IMPORTANT]
> Per sfruttare appieno la strategia *Capacità massima ubicazione* è necessario ridefinire i limiti di stoccaggio per le ubicazioni pertinenti. Altrimenti, questa strategia funziona proprio come la strategia *Quantità di domanda ciclo*.

## <a name="turn-on-the-replenish-to-max-based-on-stocking-limits-feature"></a>Attivare la funzione Rifornisci al massimo in base ai limiti di stoccaggio

Per poter utilizzare la funzionalità, è necessario attivarla per il sistema. Gli amministratori possono utilizzare l'area di lavoro della [gestione delle funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) per controllare lo stato della funzione e se necessario abilitarla. Nell'area di lavoro, la funzionalità è elencata nel modo seguente:

- **Modulo:** *Gestione Magazzino*
- **Nome funzione:** *Rifornisci al massimo in base ai limiti di stoccaggio*

## <a name="set-up-replenishment-strategies"></a>Impostare le strategie di rifornimento

Per accedere ai modelli andare a **Gestione magazzino \> Impostazione \> Rifornimento \> Modelli di rifornimento**. Nella sezione **Panoramica** selezionare o creare un modello di rifornimento della domanda ciclo in cui il campo **Tipo di rifornimento** è impostato su *Domanda ciclo*. Quindi impostare le righe del modello di rifornimento nella sezione **Dettagli del modello di rifornimento**. Per ogni riga, nel campo **Strategia di rifornimento** selezionare la strategia di rifornimento che si desidera utilizzare.

![Pagina Modelli di rifornimento.](media/ReplenTempWaveDmdMaxLocCap.png "Pagina Modelli di rifornimento")

Se la colonna **Strategia di rifornimento** non appare nella griglia della sezione **Dettagli del modello di rifornimento** assicurarsi che la funzione sia stata attivata e che il modello di rifornimento selezionato abbia un tipo di rifornimento *Domanda ciclo*.

> [!NOTE]
> La strategia *Quantità di domanda ciclo* è la strategia predefinita. Pertanto, è sufficiente aggiornare le righe del modello di rifornimento in cui si desidera utilizzare la strategia *Capacità massima ubicazione*.

## <a name="example-scenarios"></a>Scenari di esempio

### <a name="example-1"></a>Esempio 1

Per questo esempio, esiste un solo modello di rifornimento con una sola riga del modello di rifornimento.

Si crea un ordine cliente per 130 pezzi (pezzi) dell'articolo A0001. Prima di rilasciare l'ordine al magazzino, il magazzino viene impostato nel modo seguente:

- Esiste solo una ubicazione in blocco e ha 500 pezzi di inventario disponibile.
- Sono disponibili tre ubicazioni di prelievo, ciascuna delle quali ha un limite di stoccaggio di 100 pezzi. Ricordare che i limiti di stoccaggio sono obbligatori per la strategia *Capacità massima ubicazione*.
- Le ubicazione di stoccaggio rifornimento sono uguali alle ubicazioni di prelievo vendita.
- L'unità di rifornimento è una scatola (1 scatola = 20 pezzi).

Al momento dell'ordine, il seguente inventario è disponibile presso le ubicazioni di prelievo vendita:

- **Prelievo-001:** 20 pz (1 scatola)
- **Prelievo-002:** 0 pz
- **Prelievo-003:** 0 pz

Inizialmente, la strategia di rifornimento è impostata su *Quantità di domanda ciclo*.

Dopo aver rilasciato l'ordine cliente al magazzino e viene eseguita l'elaborazione del ciclo, si ottiene il seguente lavoro di rifornimento:

- **Lavoro di rifornimento 1:** Scegli 4 scatole dall'ubicazione in blocco e inseriscile nell'ubicazione prelievo-001.
- **Lavoro di rifornimento 2:** Scegli 2 scatole dall'ubicazione in blocco e inseriscile nell'ubicazione prelievo-002.

Si ottengono due ID lavoro di rifornimento perché è necessario rifornire due ubicazioni e lo stoccaggio in più ubicazioni non è supportato.

Se si imposta la strategia di rifornimento su *Capacità massima ubicazione* si ottiene il seguente lavoro di rifornimento:

- **Lavoro di rifornimento 1:** Scegli 4 scatole dall'ubicazione in blocco e inseriscile nell'ubicazione prelievo-001.
- **Lavoro di rifornimento 2:** Scegli 5 scatole dall'ubicazione in blocco e inseriscile nell'ubicazione prelievo-002.

[![Esempio 1.](media/ReplenTemp_example_1.png "Esempio 1")](media/ReplenTemp_example_1_large.png)

### <a name="example-2"></a>Esempio 2

Questo esempio mostra cosa succede quando l'ubicazione in blocco non dispone di inventario sufficiente per coprire la quantità extra. Utilizza lo stesso scenario dell'esempio 1, ma l'ubicazione in blocco ha 160 pezzi (8 scatole).

La strategia *Quantità di domanda ciclo* crea lo stesso lavoro come nell'esempio 1.

Tuttavia, poiché la strategia *Capacità massima ubicazione* tenta di creare gli ID lavoro come nell'esempio 1, potrebbe non riuscire. A quel punto, il sistema tenta di ripristinare.

A seconda dell'impostazione dell'opzione **Consenti divisione** delle direttive di ubicazione per il prelievo di rifornimento, sono possibili due risultati:

- Se l'opzione **Consenti divisione** è impostata su *Sì*, viene creato il seguente lavoro di rifornimento:

    - **Lavoro di rifornimento 1:** Scegli 4 scatole dall'ubicazione in blocco e inseriscile nell'ubicazione prelievo-001.
    - **Lavoro di rifornimento 2:** Scegli 4 scatole dall'ubicazione in blocco e inseriscile nell'ubicazione prelievo-002.

- Se l'opzione **Consenti divisione** è impostata su *No*, viene creato il seguente lavoro di rifornimento:

    - **Lavoro di rifornimento 1:** Scegli 4 scatole dall'ubicazione in blocco e inseriscile nell'ubicazione prelievo-001.
    - **Lavoro di rifornimento 2:** Scegli 2 scatole dall'ubicazione in blocco e inseriscile nell'ubicazione prelievo-002.

I risultati differiscono a causa delle informazioni disponibili quando si crea il lavoro. Quando l'opzione **Consenti divisione** è impostata su *Sì* nelle direttive di ubicazione per il prelievo di rifornimento, sono stati trovati 160 pezzi. Pertanto, è possibile creare lavoro per quella quantità. Tuttavia, quando l'opzione **Consenti divisione** è impostata su *No*, non si conosce l'esistenza dei 160 pezzi. Poiché la quantità extra che deve essere reintegrata è di 3 scatole, rilasciare quella quantità extra e riprovare la quantità originale.

[![Esempio 2.](media/ReplenTemp_example_2.png "Esempio 2")](media/ReplenTemp_example_2_large.png)

Pertanto, per ottenere la quantità massima nelle ubicazioni rifornite, è necessario impostare l'opzione **Consenti divisione** su *Sì* nelle direttive di ubicazione per il prelievo di rifornimento.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]