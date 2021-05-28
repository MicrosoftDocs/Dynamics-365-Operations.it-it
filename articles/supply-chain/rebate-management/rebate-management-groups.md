---
title: Gruppi di gestione degli sconti
description: In questo argomento viene descritto come impostare i gruppi di gestione degli sconti. I gruppi di gestione degli sconti possono essere utilizzati durante i calcoli degli sconti e possono essere allegati a un record di dati master.
author: sherry-zheng
ms.date: 02/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TAMRebateGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-02-19
ms.dyn365.ops.version: Release 10.0.18
ms.openlocfilehash: c9e1cadae97bd8f0dea270deaa1a8e09bb28eb4b
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2021
ms.locfileid: "6020485"
---
# <a name="rebate-management-groups"></a>Gruppi di gestione degli sconti

[!include [banner](../includes/banner.md)]

I calcoli di sconti e detrazioni possono essere guidati da gruppi. È possibile creare gruppi di gestione degli sconti per clienti, fornitori e articoli. Possono essere allegati a un record di dati master.

## <a name="rebate-management-customer-groups"></a>Gruppi di clienti di gestione degli sconti

Il calcolo per un gruppo di clienti viene spesso creato per una catena di aziende, come una catena di supermercati o una società in franchising. Questo tipo di calcolo è solitamente correlato a uno sconto.

Spesso viene calcolata una detrazione senza considerare a chi è stato venduto l'ordine idoneo. Tuttavia, vi sono alcune eccezioni. Ad esempio, un licenziatario potrebbe creare uno schema di detrazione in cui il gruppo di clienti A riceverà il 4% e il gruppo di clienti B riceverà solo il 3%.

### <a name="set-up-customer-groups"></a>Imposta i gruppi di clienti

Per lavorare con i gruppi di clienti per la gestione degli sconti, vai a **Gestione degli sconti \> Impostazione gruppi di gestione degli sconti \> Gruppi di clienti**. Puoi utilizzare i pulsanti nel riquadro azioni per aggiungere e rimuovere i gruppi come necessario. Per ciascun gruppo imposta i seguenti campi:

- **Gruppi di gestione degli sconti** – Immetti un nome univoco per il gruppo.
- **Descrizione** - Immetti una descrizione del gruppo per fornire ulteriori informazioni su come dovrebbe essere utilizzato.

### <a name="manage-customer-group-assignments"></a>Gestire le assegnazioni dei gruppi di clienti

Ogni cliente può appartenere a un numero qualsiasi di gruppi di gestione degli sconti. Per visualizzare e assegnare i membri del gruppo, puoi iniziare dall'elenco dei gruppi o dall'elenco dei clienti.

Per visualizzare, aggiungere o rimuovere clienti per un gruppo selezionato, segui questi passaggi.

1. Vai a **Gestione degli sconti \> Impostazione gruppi di gestione degli sconti \> Gruppi di clienti**.
1. Seleziona il gruppo da gestire.
1. Nel riquadro azioni seleziona **Clienti**. Viene visualizzata la pagina **Gruppi di gestione degli sconti** e mostra un elenco di clienti che sono già membri del gruppo selezionato.
1. Per aggiungere un nuovo cliente al gruppo seleziona **Nuovo** nel riquadro azioni per aggiungere una riga alla griglia. Quindi imposta i seguenti campi per la nuova riga:

    - **Conto cliente** - Seleziona l'ID conto cliente.
    - **Nome** - Immetti un nome e/o una descrizione del cliente.

1. Per rimuovere un cliente dal gruppo, seleziona il cliente, quindi seleziona **Elimina** nel riquadro azioni.

Per visualizzare, aggiungere o rimuovere le assegnazioni di gruppo per un cliente selezionato, segui questi passaggi.

1. Andare a **Contabilità clienti \> Clienti \> Tutti i clienti**.
1. Seleziona il cliente con cui lavorare.
1. Nel riquadro azioni, nella scheda **Cliente**, nel gruppo **Gestione degli sconti** seleziona **Gruppi di gestione degli sconti**. Viene visualizzata la pagina **Gruppi di gestione degli sconti** e mostra un elenco di gruppi a cui il cliente già fa parte.
1. Per aggiungere il cliente a un nuovo gruppo seleziona **Nuovo** nel riquadro azioni per aggiungere una riga alla griglia. Quindi imposta i seguenti campi per la nuova riga:

    - **Gruppo di gestione degli sconti** - Seleziona il gruppo a cui aggiungere il cliente.
    - **Descrizione** - Immetti una descrizione del gruppo (ad esempio, per spiegare perché il cliente ne fa parte).

1. Per rimuovere un cliente da un gruppo, seleziona il gruppo, quindi seleziona **Elimina** nel riquadro azioni.

## <a name="rebate-management-vendor-groups"></a>Gruppi di fornitori di gestione degli sconti

Il calcolo per un gruppo di fornitori viene spesso creato per un gruppo di punti di consegna. Questo tipo di calcolo è solitamente correlato a uno sconto.

### <a name="set-up-vendor-groups"></a>Impostare gruppi di fornitori

Per lavorare con i gruppi di fornitori per la gestione degli sconti, vai a **Gestione degli sconti \> Impostazione gruppi di gestione degli sconti \> Gruppi di fornitori**. Puoi utilizzare i pulsanti nel riquadro azioni per aggiungere e rimuovere i gruppi come necessario. Per ciascun gruppo imposta i seguenti campi:

- **Gruppi di gestione degli sconti** – Immetti un nome univoco per il gruppo.
- **Descrizione** - Immetti una descrizione del gruppo per fornire ulteriori informazioni su come dovrebbe essere utilizzato.

### <a name="manage-vendor-group-assignments"></a>Gestire le assegnazioni dei gruppi di fornitori

Ogni fornitore può appartenere a un numero qualsiasi di gruppi di gestione degli sconti. Per visualizzare e assegnare i membri del gruppo, puoi iniziare dall'elenco dei gruppi o dall'elenco dei fornitori.

Per visualizzare, aggiungere o rimuovere fornitori per un gruppo selezionato, segui questi passaggi.

1. Vai a **Gestione degli sconti \> Impostazione gruppi di gestione degli sconti \> Gruppi di fornitori**.
1. Seleziona il gruppo da gestire.
1. Nel riquadro azioni, seleziona **Fornitori**. Viene visualizzata la pagina **Gruppi di gestione degli sconti** e mostra un elenco di fornitori che sono già membri del gruppo selezionato.
1. Per aggiungere un nuovo fornitore al gruppo seleziona **Nuovo** nel riquadro azioni per aggiungere una riga alla griglia. Quindi imposta i seguenti campi per la nuova riga:

    - **Conto fornitore** - Seleziona l'ID conto fornitore.
    - **Nome** - Immetti un nome e/o una descrizione del fornitore.

1. Per rimuovere un fornitore dal gruppo, seleziona il fornitore, quindi seleziona **Elimina** nel riquadro azioni.

Per visualizzare, aggiungere o rimuovere le assegnazioni di gruppo per un fornitore selezionato, segui questi passaggi.

1. Andare a **Contabilità fornitori \>Fornitori \> Tutti i fornitori**.
1. Seleziona il fornitore con cui lavorare.
1. Nel riquadro azioni, nella scheda **Fornitore**, nel gruppo **Gestione degli sconti** seleziona **Gruppi di gestione degli sconti**. Viene visualizzata la pagina **Gruppi di gestione degli sconti** e mostra un elenco di gruppi a cui il fornitore già fa parte.
1. Per aggiungere il fornitore a un nuovo gruppo seleziona **Nuovo** nel riquadro azioni per aggiungere una riga alla griglia. Quindi imposta i seguenti campi per la nuova riga:

    - **Gruppo di gestione degli sconti** - Seleziona il gruppo a cui aggiungere il fornitore.
    - **Descrizione** - Immetti una descrizione del gruppo (ad esempio, per spiegare perché il fornitore ne fa parte).

1. Per rimuovere un fornitore da un gruppo, seleziona il gruppo, quindi seleziona **Elimina** nel riquadro azioni.

## <a name="item-rebate-groups"></a>Gruppi di sconti articolo

Raggruppando gli articoli, hai una maggiore flessibilità quando vengono calcolati sconti e detrazioni. Questo approccio è spesso un modo più efficiente per impostare sconti e detrazioni per clienti e fornitori.

### <a name="set-up-item-groups"></a>Imposta i gruppi di articoli

Per lavorare con i gruppi di articoli per la gestione degli sconti, vai a **Gestione degli sconti \> Impostazione gruppi di gestione degli sconti \> Gruppi di articoli**. Puoi utilizzare i pulsanti nel riquadro azioni per aggiungere e rimuovere i gruppi come necessario. Per ciascun gruppo imposta i seguenti campi:

- **Gruppi di gestione degli sconti** – Immetti un nome univoco per il gruppo.
- **Descrizione** - Immetti una descrizione del gruppo per fornire ulteriori informazioni su come dovrebbe essere utilizzato.

### <a name="manage-item-group-assignments"></a>Gestire le assegnazioni dei gruppi di articoli

Ogni articolo può appartenere a un numero qualsiasi di gruppi di gestione degli sconti. Per visualizzare e assegnare i membri del gruppo, puoi iniziare dall'elenco dei gruppi o dall'elenco degli articoli. Puoi anche aggiungere elementi in base alla tua gerarchia di categorie.

Per visualizzare, aggiungere o rimuovere articoli per un gruppo selezionato, segui questi passaggi.

1. Vai a **Gestione degli sconti \> Impostazione gruppi di gestione degli sconti \> Gruppi di articoli**.
1. Seleziona il gruppo da gestire.
1. Nel riquadro azioni seleziona **Articoli**. Viene visualizzata la pagina **Gruppi di gestione degli sconti** e mostra un elenco di articoli che sono già membri del gruppo selezionato.
1. Per aggiungere un nuovo articolo al gruppo seleziona **Nuovo** nel riquadro azioni per aggiungere una riga alla griglia. Quindi imposta i seguenti campi per la nuova riga:

    - **Conto articolo** - Seleziona l'ID conto articolo.
    - **Nome del prodotto** - Immetti un nome e/o una descrizione dell'articolo.

1. Per rimuovere un articolo dal gruppo, seleziona l'articolo, quindi seleziona **Elimina** nel riquadro azioni.

Per visualizzare, aggiungere o rimuovere le assegnazioni di gruppo per un articolo selezionato, segui questi passaggi.

1. Fare clic su **Gestione informazioni sul prodotto \> Prodotti \> Prodotti rilasciati**.
1. Seleziona l'articolo con cui lavorare.
1. Nel riquadro azioni, nella scheda **Prodotto**, nel gruppo **Gestione degli sconti** seleziona **Gruppi di gestione degli sconti**. Viene visualizzata la pagina **Gruppi di gestione degli sconti** e mostra un elenco di gruppi a cui l'articolo già fa parte.
1. Per aggiungere l'articolo a un nuovo gruppo seleziona **Nuovo** nel riquadro azioni per aggiungere una riga alla griglia. Quindi imposta i seguenti campi per la nuova riga:

    - **Gruppo di gestione degli sconti** - Seleziona il gruppo a cui aggiungere l'articolo.
    - **Descrizione** - Immetti una descrizione del gruppo (ad esempio, per spiegare perché l'articolo ne fa parte).

1. Per rimuovere un articolo da un gruppo, seleziona il gruppo, quindi seleziona **Elimina** nel riquadro azioni.

Per aggiungere articoli a un gruppo in base alla gerarchia delle categorie, segui questi passaggi.

1. Vai a **Gestione degli sconti \> Impostazione gruppi di gestione degli sconti \> Gruppi di articoli**.
1. Seleziona il gruppo da gestire.
1. Nel riquadro azioni seleziona **Aggiungi articoli**.
1. Nella finestra di dialogo **Aggiungi articoli** nel campo **Gerarchia delle categorie** seleziona una categoria di primo livello.
1. La gerarchia degli articoli viene aperta nel riquadro sinistro. Seleziona il livello di gerarchia che stai cercando. 
1. Gli articoli della gerarchia e del livello di gerarchia selezionati sono ora elencati nel riquadro di destra. Segui questi passaggi per lavorare con il riquadro:

    - Seleziona la casella di controllo per ogni articolo che vuoi aggiungere.
    - Seleziona la casella di controllo nell'intestazione della griglia per selezionare tutti gli articoli elencati.
    - Seleziona il pulsante **Mostra selezionati** per filtrare la griglia in modo che mostri solo gli articoli selezionati fino a quel momento. Seleziona di nuovo il pulsante per tornare all'elenco completo.

1. Seleziona **OK** per applicare la selezione dell'articolo al gruppo selezionato.
