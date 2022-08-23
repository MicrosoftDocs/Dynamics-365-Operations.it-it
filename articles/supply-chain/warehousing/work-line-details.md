---
title: Dettagli riga di lavoro
description: Questo articolo fornisce informazioni sulla pagina Dettagli riga di lavoro, che mostra un elenco completo, ordinabile e filtrabile delle singole righe di lavoro nel sistema.
author: Mirzaab
ms.date: 07/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSWorkLocationChange, WHSWorkLineDetails
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: 10.0.8
ms.openlocfilehash: 1017527419acc2e4cb42b2bcb83131339d82b665
ms.sourcegitcommit: c98d55a4a6e27239ae6b317872332f01cbe8b875
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/02/2022
ms.locfileid: "9218884"
---
# <a name="work-line-details"></a>Dettagli riga di lavoro

[!include [banner](../includes/banner.md)]

La pagina **Dettagli riga di lavoro** mostra un elenco completo, ordinabile e filtrabile delle singole righe di lavoro nel sistema. Fornisce una panoramica completa del lavoro pianificato ed eseguito in magazzino. È possibile passare facilmente dalla visualizzazione di tutte le righe di lavoro alla visualizzazione delle sole righe di lavoro aperte. I dettagli forniti per ciascuna riga includono lo stato del lavoro, il numero di articolo, l'ubicazione, la quantità di lavoro, l'ID di carico e l'ID di spedizione.

## <a name="turn-on-the-work-line-details-feature"></a>Attivare la funzione Dettagli riga di lavoro

A partire dalla versione 10.0.21 di Supply Chain Management, questa funzionalità è attivata per impostazione predefinita. Gli amministratori possono utilizzare la pagina [Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) per controllare lo stato della funzione e abilitarla o disabilitarla se necessario. La funzione viene elencata come:

- **Modulo:** *Gestione Magazzino*
- **Nome funzionalità:** *Dettagli riga di lavoro*

## <a name="open-and-use-the-work-line-details-page"></a>Aprire e utilizzare la pagina Dettagli riga di lavoro

Per visualizzare l'elenco dei dettagli della riga di lavoro, vai a **Gestione del magazzino \> Lavoro \> Dettagli riga di lavoro**. Da qui, puoi effettuare le azioni riportate di seguito:

- Utilizza il campo **Filtro** per cercare le righe che hanno un valore specifico per qualsiasi parametro disponibile. (I parametri disponibili includono molti parametri che non sono mostrati come colonne nella griglia.)
- Utilizza la casella di controllo **Mostra chiuse** per mostrare o nascondere le righe chiuse.
- Seleziona **Visualizza dimensioni** per aprire la finestra di dialogo **Visualizzazione dimensioni**, in cui è possibile scegliere di mostrare o nascondere varie colonne di dimensioni nella griglia.
- Seleziona un'intestazione di colonna per aprire un menu in cui puoi scegliere di ordinare o filtrare l'elenco in base ai valori in quella colonna.
- Seleziona una riga di lavoro, quindi seleziona **Cambia ubicazione** per aprire una finestra di dialogo in cui puoi modificare l'ubicazione per quella riga di lavoro. L'ubicazione specificata sovrascriverà l'impostazione della direttiva di ubicazione.
- Seleziona una riga di lavoro, quindi seleziona **Annulla riga di lavoro** per aprire una finestra di dialogo in cui è possibile ridurre parzialmente o completamente la quantità di quella riga di lavoro.
- Regola le quantità.
- Visualizza le transazioni dietro tutte le righe di lavoro.

## <a name="try-out-the-feature"></a>Provare la funzione

Questa sezione fornisce una demo in tre parti che mostra come lavorare con i dettagli della riga di lavoro.

### <a name="make-sample-data-available"></a>Rendi disponibili i dati di esempio

Per utilizzate questa demo utilizzando i record e i valori di esempio specificati qui, devi utilizzare un sistema in cui sono installati i [dati dimostrativi](../../fin-ops-core/fin-ops/get-started/demo-data.md) standard. È inoltre necessario selezionare la persona giuridica **USMF** prima di iniziare.

È inoltre possibile utilizzare questa demo come indicazioni quando si lavora su un sistema di produzione. Tuttavia, è necessario sostituire i propri valori e potrebbero mancare alcuni tipi di record richiesti forniti dai dati demo standard.

### <a name="verify-that-the-scenario-setup-includes-enough-available-inventory"></a>Verificare che la configurazione dello scenario includa sufficienti scorte disponibili

Se stai lavorando con dati dimostrativi **USMF**, è consigliabile prima assicurarti che il tuo sistema sia configurato in modo che ci siano scorte sufficienti in ogni ubicazione di prelievo. Per questa demo, ci si aspetta che le seguenti scorte siano disponibili:

- **Articolo M9200:** 45 unità. (o più)
- **Articolo M9202:** 10 unità. (o più)

Attieniti alla seguente procedura per verificare che siano disponibili scorte sufficienti e per apportare le modifiche necessarie.

1. Vai a **Gestione del magazzino \> Impostazione \> Direttive di ubicazione** e determina quali ubicazioni di prelievo vengono utilizzate per il prelievo degli ordini cliente presso il magazzino 51. Per ulteriori informazioni, vedere [Rifornimento e Controllare il lavoro di magazzino utilizzando i modelli di lavoro e le direttive ubicazione](control-warehouse-location-directives.md).
1. Controlla i livelli di scorte nelle posizioni pertinenti.
1. Regola le scorte come richiesto. Puoi creare movimenti manuali, utilizzare il rifornimento o applicare qualsiasi altro flusso per regolare le scorte.

### <a name="part-1-create-picking-work"></a>Parte 1: creare il lavoro di prelievo

Prima di iniziare a creare lavoro, verifica che il magazzino sia impostato per rispondere alle richieste di lavoro nel modo previsto.

Segui questi passaggi per creare lavoro di prelievo.

1. Selezionare **Vendite e marketing \> Ordini cliente \> Tutti gli ordini cliente**.
1. Seleziona **Nuovo** per aprire la finestra di dialogo **Crea ordine cliente**.
1. Nella finestra di dialogo **Crea ordine cliente**, imposta i seguenti valori:

    - Nella Scheda dettaglio **Cliente**, imposta il campo **Conto cliente** su _US-001_.
    - Nel campo **Magazzino** della Scheda dettaglio **Generale**, seleziona _51_.

1. Scegli **OK** per creare l'ordine cliente e chiudere la finestra di dialogo.
1. Viene aperto il nuovo ordine cliente. Include una nuova riga vuota nella griglia **Righe ordine cliente**. Imposta i seguenti valori per questa riga ordine:

    - **Numero articolo:** _M9200_
    - **Quantità:** _20_
    - **Unità:** _ea_

1. Seleziona la nuova riga ordine, quindi sul menu **Scorte** sopra la griglia, seleziona **Prenotazione** per aprire la pagina **Prenotazione**.
1. Nella pagina **Prenotazione**, seleziona **Prenota lotto** per prenotare l'intera quantità della riga selezionata nel magazzino.
1. Chiudi la pagina **Prenotazione** per tornare all'ordine cliente.
1. Nel riquadro azioni, nella scheda **Magazzino**, seleziona **Rilascia in magazzino**. Il sistema crea una spedizione, la aggiunge a un nuovo carico e crea il lavoro richiesto.
1. Crea un secondo ordine cliente per lo stesso account cliente e magazzino utilizzato per il primo ordine. Aggiungi le seguenti due righe ordine a questo ordine:

    - **Riga 1:** imposta il campo **Numero articolo** su _M9200_, il campo **Quantità** su _25_ e il campo **Unità** su _ea_.
    - **Riga 2:** imposta il campo **Numero articolo** su _M9202_, il campo **Quantità** su _10_ e il campo **Unità** su _ea_.

1. Ripeti i passaggi da 6 a 8 per prenotare le scorte per ciascuna riga ordine (una alla volta), quindi ripeti il passaggio 9 per rilasciare l'ordine al magazzino.

### <a name="part-2-change-the-location-for-a-work-line"></a>Parte 2: modificare l'ubicazione per una riga di lavoro

1. Vai a **Gestione magazzino \> Lavoro \> Dettagli riga di lavoro**.
1. Trova e seleziona una delle righe di lavoro che hai creato per questa demo.
1. Seleziona **Cambia ubicazione** per aprire la finestra di dialogo **Seleziona nuova ubicazione**.
1. Nella finestra di dialogo **Seleziona nuova ubicazione**, nel campo **Ubicazione**, seleziona una nuova ubicazione per la riga di lavoro.
1. Seleziona **OK** per applicare la modifica e chiudere la finestra di dialogo.

> [!IMPORTANT]
> È possibile inviare le modifiche all'ubicazione solo se la nuova ubicazione dispone di scorte sufficienti (per un prelievo) o se supera la convalida del tipo di ubicazione (per un inserimento).

### <a name="part-3-change-the-quantity-of-a-work-line-or-cancel-a-work-line"></a>Parte 3: modificare la quantità di una riga di lavoro o annullare una riga di lavoro

1. Vai a **Gestione magazzino \> Lavoro \> Dettagli riga di lavoro**.
1. Trova e seleziona una delle righe di lavoro che hai creato per questa demo. Nota che è possibile annullare o modificare le quantità solo per le righe di lavoro in cui si trova il tipo di lavoro _prelievo_.
1. Seleziona **Annulla riga di lavoro** per aprire la finestra di dialogo **Quantità da annullare**.
1. Nella finestra di dialogo **Quantità da annullare**, modifica il valore nel campo **Quantità** per specificare la quantità che dovrebbe essere *sottratta da* la quantità attualmente specificata per la riga. Per impostazione predefinita, il campo **Quantità** mostra la quantità completa.

    - Se annulli l'intera quantità, il valore **Stato del lavoro** verrà modificato in _Annullato_, ma il campo **Quantità di lavoro** mostrerà comunque il valore originale.
    - Se annulli solo parte della quantità, il campo **Quantità di lavoro** verrà aggiornato per mostrare il nuovo valore, ma il valore di **Stato lavoro** non verrà modificato.

1. Seleziona **OK** per applicare la modifica e chiudere la finestra di dialogo.

> [!IMPORTANT]
> Se annulli solo una parte della quantità per una riga di lavoro, è necessario rimuovere anche la quantità obsoleta dalla riga di carico. In caso contrario, a meno che la consegna in difetto non sia impostata correttamente, la riga di carico non può essere confermata dalla spedizione.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]