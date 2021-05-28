---
title: Modelli ondata
description: In questo argomento viene descritto come impostare i criteri che determinano se i cicli vengono elaborati manualmente o automaticamente e il lavoro generato per un magazzino quando viene elaborato un ciclo.
author: Mirzaab
ms.date: 03/08/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-03-08
ms.dyn365.ops.version: Release 10.0.18
ms.openlocfilehash: 95e315c1bf1e363db413abae985d510848059e62
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2021
ms.locfileid: "6020061"
---
# <a name="wave-templates"></a>Modelli ondata

[!include [banner](../includes/banner.md)]

In questo argomento viene descritto come impostare i criteri che determinano se i cicli vengono elaborati manualmente o automaticamente e il lavoro generato per un magazzino quando viene elaborato un ciclo. Specifica i criteri impostando i modelli ciclo e le query che corrispondono a un ciclo con le righe rilasciate negli ordini cliente, ordini di produzione e kanban.

## <a name="settings-for-wave-templates"></a>Impostazione dei modelli ciclo

Quando viene impostato un modello ciclo, specifica quanto segue:

- Il **Sito** e il **Magazzino** per cui modello creerà il lavoro.
- L'ordine in cui verranno valutati i modelli. La sequenza in cui i modelli vengono associati alle righe rilasciate negli ordini cliente, ordini di produzione e kanban. Quando una linea viene rilasciata, il sistema applica il primo modello ciclo per cui la linea soddisfa i criteri. Più ampi sono i criteri, più è probabile che una linea soddisfi i criteri, quindi dovresti inserire i modelli con i criteri più specifici all'inizio dell'elenco. Utilizza i pulsanti **Sposta su** e **Sposta giù** nel riquadro azioni per disporre i modelli nell'elenco.
- Le azioni intraprese da ogni modello. I **metodi** di ciclo che eseguono azioni create dal modello, come la creazione o la distribuzione del lavoro per ogni tipo di modello di ciclo.
- Gli attributi (filtri) del ciclo che devono essere applicati per utilizzare il modello ciclo.

> [!NOTE]
> Se necessario, uno sviluppatore può creare metodi aggiuntivi. È possibile visualizzare l'elenco completo dei metodi nella pagina **Metodi di elaborazione ciclo**.

Alcune impostazioni rappresentano le decisioni strategiche per l'elaborazione ciclo, come indicato di seguito:

- Se il modello viene utilizzato per la spedizione di articoli per gli ordini cliente e gli ordini di trasferimento, o viene utilizzato per lo spostamento di articoli nella produzione per gli ordini di produzione o i kanban.
- Se un ciclo viene elaborato manualmente o automaticamente, come indicato di seguito:

  - **Elaborazione manuale** – La riga viene aggiunta a un ciclo e le scorte vengono prenotate, tuttavia, devi selezionare **Elabora** nella pagina elenco **Tutti i cicli** per creare il lavoro di prelievo dell'ordine.
  - **Elaborazione automatica** – Puoi automatizzare completamente o parzialmente l'elaborazione ciclo. Se automatizzi completamente l'elaborazione ciclo viene creato un ciclo che include la riga dall'ordine cliente, dall'ordine di produzione o dal kanban quando viene creato un ordine cliente, un ordine di produzione o un kanban. Gli articoli vengono dedotti dalle scorte disponibili e il viene creato il lavoro di prelievo. Se l'elaborazione ciclo viene elaborata parzialmente, è possibile specificare valori che avvieranno l'elaborazione ciclo. Ad esempio, puoi specificare un peso massimo per le spedizioni che avvieranno l'elaborazione ciclo quando il peso totale delle righe nel ciclo raggiunge il valore.

- Se vengono assegnate le spedizioni a un ciclo aperto. Ad esempio, se viene promesso ai clienti che un ordine emesso entro le 12:00 PM verrà spedito entro 24 ore, puoi impostare il modello ciclo per assegnare automaticamente le righe ordine a un ciclo aperto fino alle 12:00. A quell'ora il ciclo viene elaborato automaticamente.

Quando un ciclo viene elaborato, il lavoro di prelievo creato viene basato sul modello di lavoro e sulla direttiva ubicazione specificata per il magazzino. Il modello di lavoro specifica come viene creato il lavoro di prelievo e la direttiva di ubicazione specifica le ubicazioni di prelievo e stoccaggio.

## <a name="create-a-wave-template"></a>Creare un modello ciclo

Per impostare un modello ciclo, effettua le operazioni seguenti:

1. Vai a **Gestione magazzino** \> **Impostazione** \> **Ondate** \> **Modelli ondata**.
1. Seleziona **Nuovo** per creare un nuovo modello ciclo.
1. Nel campo **Tipo di modello ciclo** seleziona una delle seguenti opzioni:

    - *Spedizione* - Utilizza il modello ciclo per la spedizione di articoli per gli ordini cliente e gli ordini di trasferimento.
    - *Ordini di produzione* - Utilizza il modello ciclo per spostare gli articoli per gli ordini di produzione.
    - *Kanban* - Utilizza il modello ciclo per spostare gli articoli per gli ordini kanban.

1. Nei campi **Nome modello ciclo** e **Descrizione modello ciclo** immetti un nome e una descrizione per il modello ciclo.

    > [!NOTE]
    > Se vengono creati più modelli per un magazzino, il numero nel campo **Sequenza modello ciclo** indica la posizione del modello nella sequenza in cui i modelli vengono applicati quando vengono soddisfatti i criteri di modello. Puoi selezionare **Sposta su** o **Sposta su** per riorganizzare la sequenza dei modelli.

1. Nei campi **Sito** e **Magazzino**, seleziona il sito e il magazzino per cui il modello ciclo creerà cicli e lavoro di prelievo.
1. Se desideri automatizzare l'elaborazione ciclo, effettua le seguenti impostazioni secondo necessità:

    - **Automatizza creazione ciclo** - Imposta su *Sì* per creare un ciclo automaticamente quando viene rilasciato un ordine cliente, un ordine di produzione, un kanban al magazzino.
    - **Assegna a cicli aperti** - Imposta su *Sì* per assegnare automaticamente le righe a un ciclo aperto quando le righe vengono rilasciate. Le righe vengono assegnate a ondate sul filtro di query per il modello ondata.
    - **Elabora ciclo al rilascio in magazzino** - Imposta su *Sì* per elaborare automaticamente il ciclo e creare il lavoro quando una riga viene rilasciata al magazzino.
    - **Elabora ciclo automaticamente alla soglia** - Imposta su *Sì* per elaborare automaticamente l'ondata quando i relativi valori raggiungono le soglie di peso, la spedizione e le righe specificate nel gruppo di campi **Soglie ciclo**. Questa impostazione è attiva solo se nel campo *Tipo di modello ciclo* è selezionata l'opzione **Spedizione**.
    - **Automatizza rilascio ciclo** - Imposta su *Sì* per rilasciare automaticamente il ciclo. Il lavoro di prelievo viene creato e reso disponibile sui dispositivi mobili.
    - **Automatizza rilascio lavoro di rifornimento** - Imposta su *Sì* per creare lavoro di rifornimento basato sulla domanda e per rilasciarlo automaticamente. È necessario aggiungere il metodo ciclo di rifornimento al modello di ciclo e creare un modello rifornimento di tipo *Domanda ciclo*. Impostare un modello di rifornimento nella pagina **Modelli di rifornimento**. È necessario aggiungere il metodo rifornimento al modello ondata.
    - **Continua elaborazione ciclo quando la creazione lavoro non riesce** - Se impostato su *Sì*, il sistema utilizza una posizione vuota se non può prenotare le scorte nella posizione proposta dalla direttiva di ubicazione (ad esempio perché le scorte non sono più disponibili). Se impostato su *No* il ciclo non riesce se il sistema non può prenotare le scorte.

1. Imposta il gruppo di campi **Soglie ciclo** secondo necessità:
    - **Soglia peso ciclo** - Immetti il peso massimo che un ciclo può contenere.
    - **Soglia spedizione** - Inserisci il numero massimo di spedizioni che possono essere incluse in un ciclo.
    - **Soglia riga** - Inserisci il numero massimo di righe che possono essere incluse in un ciclo.

1. Nel gruppo di campi **Valori predefiniti** seleziona gli attributi ciclo da utilizzare come criteri aggiuntivi per il modello ciclo. Gli attributi di ciclo sono utili per l'assegnazione di criteri aggiuntivi, ad esempio il nome di un cliente specifico, a un modello di ciclo. Puoi creare questi attributi nella pagina **Attributi ciclo**. 

1. Imposta **Criterio di notifica ciclo** sul criterio che desideri utilizzare per generare le notifiche relative ai cicli che utilizzano questo modello. Per un esempio di un criterio di notifica ciclo, vedi [Notifiche di esecuzione ciclo](wave-execution-notifications.md).

1. Nella scheda dettaglio **Metodi**, nel riquadro **Metodi selezionati** sono elencati i metodi per il tipo di modello ciclo selezionato. I metodi di ciclo che eseguono azioni create dal modello, come la creazione o la distribuzione del lavoro. Queste azioni sono anche denominate passaggi di ciclo. I metodi ciclo sono predefiniti per ogni tipo di modello ciclo. Non è possibile rimuovere i metodi di ciclo predefiniti, tuttavia, è possibile ridisporre l'ordine dei metodi e aggiungere altri metodi. Ad esempio, se stai creando un modello di ciclo per la spedizione, puoi aggiungere i metodi per il rifornimento fornitura e la containerizzazione. La containerizzazione del ciclo può essere aggiunta a una sequenza di metodi di ciclo per definire la containerizzazione delle righe elaborate in un modello di ciclo. Per aggiungere un metodo aggiuntivo, effettua le seguenti operazioni:

    - Nel riquadro **Progetti rimanenti** seleziona un metodo e quindi seleziona la freccia **Sinistra** per aggiungerlo al riquadro **Metodi selezionati**.
    - Per modificare la sequenza, seleziona un metodo, quindi seleziona le frecce **Su** o **Giù**.

    > [!NOTE]
    > Quando si aggiunge un metodo, viene automaticamente elencato nella posizione appropriata nella sequenza delle fasi.

1. Per impostare la query che abbinerà le righe rilasciate a un ciclo appropriato, seleziona **Modifica query** nel riquadro azioni.
1. Per verificare che le impostazioni del modello ciclo siano valide, seleziona **Convalida modello**.
