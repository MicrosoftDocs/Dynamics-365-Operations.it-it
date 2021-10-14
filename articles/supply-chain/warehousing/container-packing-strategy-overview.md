---
title: Strategie di imballaggio dei contenitori
description: Questo argomento descrive le differenze tra le strategie di imballaggio dei contenitori e fornisce esempi.
author: GalynaFedorova
ms.date: 06/11/2021
ms.topic: article
ms.search.form: WHSWaveTemplateTable, InventLocationIdLookup, WHSContainerType, WHSContainerGroup, WHSContainerizationTable, WHSContainerizationBreak, WHSCreateContainerBreak, WHSContainerStructure, WHSContainerTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: intro-internal
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-06-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 4e5faf8e4544b2bcb58f3c578789b2bd379a27b0
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/29/2021
ms.locfileid: "7572363"
---
# <a name="container-packing-strategies"></a>Strategie di imballaggio dei contenitori

[!include [banner](../includes/banner.md)]

Una *strategia di imballaggio del contenitore* è una strategia che è possibile utilizzare per definire le allocazioni di articoli tra i contenitori. Questo argomento spiega le differenze tra le strategie *Imballa in tutti i contenitori aperti* e *Imballa solo nel contenitore corrente*.

- **Imballa in tutti i contenitori aperti** – Il sistema deve controllare tutti i contenitori aperti che sono già stati creati durante il ciclo di containerizzazione, per assicurarsi che l'articolo rientri in uno di essi. Durante l'imballaggio, il sistema controlla ogni articolo per determinare se entrerà in uno dei contenitori creati in precedenza. Se l'articolo non entra in un contenitore esistente, il sistema crea un nuovo contenitore e continua fino a quando non ha finito di imballare l'intero ordine.

    Per esempio, *n* articoli ordinati richiedono la containerizzazione. Nel peggiore dei casi, ogni volta che il sistema elabora un articolo che non rientra in nessun contenitore esistente, esegue il totale di (\[(*n* – 1) × (*n* + 1)\] ÷ 2) per verificare se l'articolo rientra nei contenitori esistenti.

- **Imballa solo nel contenitore corrente** – Il sistema deve controllare solo il contenitore creato più di recente per assicurarsi che l'articolo possa rientrarvi. Durante l'imballaggio, il sistema controlla ogni articolo per determinare se entrerà nel contenitore creato più di recente. Se l'articolo non entra nel contenitore, il sistema crea un nuovo contenitore e continua fino a quando non ha finito di imballare l'intero ordine.

    Per esempio, *n* articoli ordinati richiedono la containerizzazione. Nel peggiore dei casi, il sistema eseguirà il totale di (*n* – 1) per valutare se l'articolo rientra nei contenitori.

## <a name="example-of-the-flow-for-container-packing-strategies"></a>Esempio del flusso per le strategie di imballaggio dei contenitori

Imposta i seguenti articoli per la containerizzazione.

| Articolo | Dimensioni fisiche (larghezza × profondità × altezza) | Peso |
|---|---|---|
| Cavo HDMI 6' | 1 × 1 × 1 | 1 |
| Cavo HDMI 12' | 2 × 1 × 1 | 1 |
| Cavo HDMI 18' | 3 × 1 × 1 | 2 |

Imposti anche la seguente scatola che verrà utilizzata per l'imballaggio.

| Contenitore | Dimensioni fisiche (lunghezza × larghezza × altezza) | Peso | Volume |
|---|---|---|---|
| Scatola media | 6 × 3 × 2 | 10 | 100 |

Infine, imposti un ordine con i seguenti prodotti e quantità.

| Riga ordine cliente | Quantità |
|---|---|
| Cavo HDMI 12' | 9 |
| Cavo HDMI 18' | 8 |
| Cavo HDMI 6' | 13 |

La tabella seguente riepiloga il funzionamento della containerizzazione quando usi la strategia *Imballa in tutti i contenitori aperti* e quando usi la strategia *Imballa solo nel contenitore corrente*.

| Imballa in tutti i contenitori aperti | Imballa nel contenitore corrente |
|---|---|
| <p>Cavo HDMI 12':</p><ol><li>Crea un nuovo contenitore, CONT0001.</li><li>Metti 9 ea nel contenitore CONT0001.</li></ol> | <p>Cavo HDMI 12':</p><ol><li>Crea un nuovo contenitore, CONT0001.</li><li>Metti 9 ea nel contenitore CONT0001.</li></ol> |
| <p>Cavo HDMI 18':</p><ol><li>Verifica se l'articolo può essere inserito nel contenitore CONT0001.</li><li>Crea un nuovo contenitore, CONT0002.</li><li>Metti 5 ea nel contenitore CONT0002.</li><li>Crea un nuovo contenitore, CONT0003.</li><li>Metti 3 ea nel contenitore CONT0003.</li></ol> | <p>Cavo HDMI 18':</p><ol><li>Verifica se l'articolo può essere inserito nel contenitore CONT0001.</li><li>Crea un nuovo contenitore, CONT0002.</li><li>Metti 5 ea nel contenitore CONT0002.</li><li>Crea un nuovo contenitore, CONT0003.</li><li>Metti 3 ea nel contenitore CONT0003.</li></ol> |
| <p>Cavo HDMI 6':</p><ol><li>Verifica se l'articolo può essere inserito nel contenitore CONT0001.</li><li>Metti 1 ea nel contenitore CONT0001.</li><li>Verifica se l'articolo può essere inserito nel contenitore CONT0002.</li><li>Verifica se l'articolo può essere inserito nel contenitore CONT0003.</li><li>Metti 4 ea nel contenitore CONT0003.</li><li>Crea un nuovo contenitore, CONT0004.</li><li>Metti 8 ea nel contenitore CONT0004.</li></ol> | <p>Cavo HDMI 6':</p><ol><li>Verifica se l'articolo può essere inserito nel contenitore CONT0003.</li><li>Metti 4 ea nel contenitore CONT0003.</li><li>Crea un nuovo contenitore, CONT0004.</li><li>Metti 9 ea nel contenitore CONT0004.</li></ol> |

## <a name="example-scenario-pack-single-orders-per-container"></a>Scenario di esempio: imballa ordini singoli per contenitore

Questa sezione presenta uno scenario in cui il sistema viene impostato per consolidare più ordini in un'unica spedizione. Pertanto, la containerizzazione verrà eseguita dall'ordine cliente per garantire che ogni ordine che contiene più prodotti sia imballato nel proprio contenitore.

Questa funzionalità consente di gestire scenari in cui è necessario imballare un solo ordine cliente in ciascun contenitore, in modo che il centro di distribuzione possa effettuare il cross-docking dei contenitori pieni tra i negozi al dettaglio. Oltre agli scenari di vendita al dettaglio (ordine per negozio al dettaglio e spedizione a un centro di distribuzione per il cross-docking), questa tecnica è comunemente utilizzata anche nelle catene di approvvigionamento snelle (ordine cliente per linea di produzione just-in-time).

Questo scenario mostra come è possibile ridurre il numero di contenitori valutati durante l'imballaggio utilizzando la strategia *Imballa solo nel contenitore corrente* per la containerizzazione.

### <a name="prerequisites"></a>Prerequisiti

#### <a name="turn-on-the-consolidate-shipments-feature-in-your-system"></a>Attiva la funzione Consolida spedizioni nel tuo sistema

Questo scenario utilizza la funzionalità *Consolida spedizioni*. Se quella funzione non è già disponibile nel tuo sistema, devi attivarla usando [Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

#### <a name="make-demo-data-available"></a>Rendi disponibili i dati dimostrativi

Questo scenario fa riferimento a valori e record inclusi nei dati demo standard forniti per Microsoft Dynamics 365 Supply Chain Management. Se desideri utilizzare i valori forniti qui durante l'esecuzione degli esercizi, assicurati di lavorare in un ambiente in cui sono installati i dati dimostrativi e imposta la persona giuridica su **USMF** prima di iniziare.

### <a name="inspect-or-create-container-types"></a>Ispezionare o creare tipi di contenitori

Per ispezionare i tipi di contenitore o per creare nuovi tipi di contenitore, se necessari, segui questi passaggi.

1. Vai a **Gestione magazzino** \> **Impostazioni** \> **Contenitori** \> **Tipi di contenitore**.
1. Assicurati che ciascuno dei seguenti tipi di contenitore sia disponibile nei dati demo. Modifica o crea tipi di contenitori come richiesto.

    - Tipo di contenitore 1:

        - **Codice tipo di contenitore:** *Scatola-grande*
        - **Descrizione:** *Scatola grande*
        - **Peso netto massimo:** *100*
        - **Volume:** *400*
        - **Lunghezza:** *4*
        - **Larghezza:** *10*
        - **Altezza:** *10*

    - Tipo di contenitore 2:

        - **Codice tipo di contenitore:** *Scatola-media*
        - **Descrizione:** *Scatola media*
        - **Peso netto massimo:** *50*
        - **Volume:** *200*
        - **Lunghezza:** *2*
        - **Larghezza:** *10*
        - **Altezza:** *10*

    - Tipo di contenitore 3:

        - **Codice tipo di contenitore:** *Scatola-piccola*
        - **Descrizione:** *Scatola piccola*
        - **Peso netto massimo:** *20*
        - **Volume:** *100*
        - **Lunghezza:** *1*
        - **Larghezza:** *10*
        - **Altezza:** *10*

### <a name="inspect-or-create-container-groups"></a>Ispezionare o creare gruppi di contenitori

Per ispezionare i gruppi di contenitore o per creare nuovi gruppi di contenitore, se necessari, segui questi passaggi.

1. Vai a **Gestione magazzino** \> **Impostazioni** \> **Contenitori** \> **Gruppi di contenitori**.
1. Assicurati che il seguente gruppo di contenitori sia disponibile nei dati demo. Se non è disponibile, seleziona **Nuovo** per crearlo.

    - **ID gruppo di contenitori:** *Scatole*
    - **Descrizione:** *Dimensioni della scatola*

1. Nella scheda dettaglio **Dettagli** per il gruppo di contenitori *Scatole* assicurati che esistano le seguenti righe. Se non esistono, seleziona **Nuovo** per aggiungerle.

    - Riga 1:

        - **Numero progressivo:** *1*
        - **Tipo di contenitore:** *Scatola-grande*
        - **Percentuale di utilizzo contenitore:** *100*

    - Riga 2:

        - **Numero progressivo:** *2*
        - **Tipo di contenitore:** *Scatola-media*
        - **Percentuale di utilizzo contenitore:** *100*

    - Riga 3:

        - **Numero progressivo:** *3*
        - **Tipo di contenitore:** *Scatola-piccola*
        - **Percentuale di utilizzo contenitore:** *100*

### <a name="create-a-new-container-build-template"></a>Creare un nuovo modello di versione del contenitore

Per creare un nuovo modello di versione del contenitore, effettua le operazioni seguenti.

1. Vai a **Gestione magazzino** \> **Impostazioni** \> **Contenitori** \> **Modello di versione contenitore**.
1. Seleziona **Nuovo** per creare un modello di versione del contenitore con le seguenti impostazioni:

    - **Numero progressivo:** *1*
    - **ID modello contenitore:** *Scatola*
    - **ID gruppo di contenitori:** *Scatole*
    - **Tipi di query di base:** *Riga allocazione vendite*
    - **Codice del passaggio ciclo:** *234*
    - **Consenti prelievi suddivisi:** *Sì*
    - **Strategia di imballaggio del contenitore:** *Imballa solo nel contenitore corrente*
    - **Imballa per unità direttiva:** *No*

1. Mentre la riga per il nuovo modello è ancora selezionata, seleziona **Modifica query** nel riquadro azioni.
1. Viene visualizzata la finestra di dialogo dell'editor di query standard. Nella scheda **Ordinamento** seleziona **Aggiungi** per aggiungere una riga con le seguenti impostazioni:

    - **Tabella:** *Transazioni lavoro temporanee*
    - **Tabella derivata:** *Transazioni lavoro temporanee*
    - **Campo:** *Numero d'ordine*
    - **Direzione di ricerca:** *Crescente*

    > [!IMPORTANT]
    > Per evitare di scorrere su tutti gli altri contenitori aperti e per accelerare il processo controllando un contenitore alla volta, utilizza la strategia *Imballa solo nel contenitore corrente* oltre all'ordinamento per numero d'ordine. Questa combinazione funzionerà come una pausa di lavoro su un modello di lavoro.

1. Selezionare **OK** per chiudere la finestra di dialogo dell'editor di query.
1. Mentre la riga per il nuovo modello è ancora selezionata, seleziona **Vincoli combinazione contenitore** nel riquadro azioni.

    Ora aggiungerai un vincolo che inserisce gli articoli di un singolo ordine in un unico contenitore. Gli articoli di qualsiasi altro ordine verranno inseriti in un contenitore separato.

1. Seleziona **Nuovo** per creare un vincolo di combinazione del contenitore con le seguenti impostazioni:

    - **Tabella:** *Ordini cliente*
    - **Seleziona campo:** *SalesId* (Il campo apparirà come *Ordine cliente* nella griglia.)

1. Seleziona **OK** per aggiungere il vincolo.
1. Chiudere la pagina.

### <a name="set-up-a-wave-template-for-containerization"></a>Impostare un modello di ondata per la containerizzazione

Per impostare un modello ciclo, effettua le operazioni seguenti.

1. Selezionare **Gestione magazzino \> Impostazioni \> Ondate \> Modelli ondata**.
1. Nel riquadro dell'elenco, imposta il campo **Tipo di modello ondata** su *Spedizione*.
1. Seleziona il modello **63 Containerizzazione** nell'elenco.
1. Nel riquadro azioni, seleziona **Modifica**.
1. Nella Scheda dettaglio **Metodi**, nella colonna **Metodi selezionati**, trova la seguente riga:

    - **Nome del metodo:** *containerizzazione*
    - **Nome:** *Containerizzazione*

1. Impostare il campo **Codice passaggio ondata** per la riga su *234*.

### <a name="set-up-a-work-template"></a>Configurare un modello di lavoro

Per impostare un modello lavoro, effettua le operazioni seguenti.

1. Accedi a **Gestione magazzino \> Impostazione \> Lavoro \> Modelli di lavoro**.
1. Imposta il campo **Tipo ordine di lavoro** su *Ordini cliente*.
1. Nella griglia **Panoramica**, trovare e selezionare il modello di lavoro da utilizzare per imballare singoli ordini per contenitore. Per questo scenario, selezionare il modello **63 Prelievo per contenitore**.
1. Nel riquadro azioni, seleziona **Modifica query**.
1. Viene visualizzata la finestra di dialogo dell'editor di query standard. Nella scheda **Ordinamento** aggiungi le righe seguenti:

    - Riga 1:

        - **Tabella:** *Transazioni lavoro temporanee*
        - **Tabella derivata:** *Transazioni lavoro temporanee*
        - **Campo:** *ID spedizione*
        - **Direzione di ricerca:** *Crescente*

    - Riga 2:

        - **Tabella:** *Transazioni lavoro temporanee*
        - **Tabella derivata:** *Transazioni lavoro temporanee*
        - **Campo:** *Numero d'ordine*
        - **Direzione di ricerca:** *Crescente*

    - Riga 3:

        - **Tabella:** *Transazioni lavoro temporanee*
        - **Tabella derivata:** *Transazioni lavoro temporanee*
        - **Campo:** *ID contenitore*
        - **Direzione di ricerca:** *Crescente*

1. Selezionare **OK** per chiudere la finestra di dialogo dell'editor di query.
1. Viene visualizzato il messaggio seguente: "Il raggruppamento verrà ripristinato. Continuare?". Selezionare **Sì** per continuare.
1. Mentre il modello **63 Prelievo per contenitore** è ancora selezionato, seleziona **Suddivisioni intestazione lavoro** nel riquadro azioni.

    Ora applicherai le impostazioni per suddividere il lavoro in modo che ogni contenitore nell'ordine sia collegato a un ordine di lavoro.

1. Seleziona la casella di controllo **Raggruppa per questo campo** per ogni riga della pagina **Suddivisioni intestazione lavoro** (**ID spedizione**, **Numero d'ordine**, e **ID contenitore**).
1. Chiudere la pagina.

### <a name="set-up-shipment-consolidation-policies"></a>Impostare i criteri consolidamento spedizione

Per configurare un criterio di consolidamento spedizione, segui questi passaggi.

1. Vai a **Gestione magazzino \> Impostazione \>Rilascia in magazzino \> Criteri di consolidamento della spedizione**.
1. Nel riquadro dell'elenco, imposta il campo **Tipo di criterio** su *Ordini cliente*.
1. Seleziona il criterio **predefinito** nell'elenco.
1. Nel riquadro azioni, seleziona **Modifica**.
1. Nella Scheda dettaglio **Campi di consolidamento**, nell'elenco **Campi selezionati**, seleziona la riga in cui il campo **Nome campo** è impostato su *Numero ordine*.
1. Selezionare il pulsante **Rimuovi** ![Freccia SINISTRA.](media/backward-button.png) per spostare il campo nell'elenco **Campi rimanenti**.
1. Nel riquadro azioni selezionare **Salva**.

### <a name="set-up-physical-dimensions-for-the-product"></a>Impostare le dimensioni fisiche del prodotto

Per impostare le dimensioni fisiche per i prodotti che verranno utilizzati in questo scenario, attieniti alla seguente procedura.

1. Fai clic su **Gestione informazioni sul prodotto \> Prodotti \> Prodotti rilasciati**.
1. Seleziona il prodotto in cui il campo **Numero articolo** è impostato su *A0001*.
1. Nel riquadro azioni della scheda **Gestione articoli**, nel gruppo **Magazzino**, selezionare **Dimensioni fisiche**.
1. Nella pagina **Dimensioni fisiche** vedi la seguente riga nella griglia:

    - **Unità:** *pezzi*
    - **Peso lordo:** *3,00*
    - **Larghezza:** *2,00*
    - **Profondità:** *2,00*
    - **Altezza:** *4,00*
    - **Volume:** *16,00*

1. Chiudere la pagina.
1. Seleziona il prodotto in cui il campo **Numero articolo** è impostato su *A0002*.
1. Nel riquadro azioni della scheda **Gestione articoli**, nel gruppo **Magazzino**, selezionare **Dimensioni fisiche**.
1. Nella pagina **Dimensioni fisiche** vedi la seguente riga nella griglia:

    - **Unità:** *pezzi*
    - **Peso lordo:** *4,00*
    - **Larghezza:** *3,00*
    - **Profondità:** *1,00*
    - **Altezza:** *3,00*
    - **Volume:** *9,00*

### <a name="create-sales-order-1"></a>Creare l'ordine cliente 1

Per creare un ordine cliente, procedere come segue.

1. Seleziona **Vendite e marketing \> Ordini cliente \> Tutti gli ordini cliente**.
1. Nel Riquadro azioni selezionare **Nuovo**.
1. Viene visualizzata una finestra di dialogo per la creazione di un nuovo ordine cliente. Imposta i valori seguenti:

    - **Conto cliente:** *US-001*
    - **Magazzino:** *63*

1. Scegli **OK** per creare l'ordine cliente e chiudere la finestra di dialogo.
1. Viene aperto il nuovo ordine cliente. Nella Scheda dettagli **Righe ordine cliente**, aggiungi le seguenti righe di vendita:

    - Riga 1:

        - **Numero articolo:** *A0001*
        - **Quantità:** *2*

    - Riga 2:

        - **Numero articolo:** *A0002*
        - **Quantità:** *2*

1. Seleziona la prima riga, quindi seleziona **Inventario \> Prenotazione**.
1. Nella pagina **Prenotazione**, selezionare **Prenota lotto**. Quindi, chiudere la pagina.
1. Ripeti i due passaggi precedenti per la seconda riga.
1. Chiudere la pagina.

### <a name="create-sales-order-2"></a>Creare l'ordine cliente 2

Per creare un secondo ordine cliente, segui questi passaggi.

1. Seleziona **Vendite e marketing \> Ordini cliente \> Tutti gli ordini cliente**.
1. Nel Riquadro azioni selezionare **Nuovo**.
1. Viene visualizzata una finestra di dialogo per la creazione di un nuovo ordine cliente. Imposta i valori seguenti:

    - **Conto cliente:** *US-001*
    - **Magazzino:** *63*

1. Scegli **OK** per creare l'ordine cliente e chiudere la finestra di dialogo.
1. Viene aperto il nuovo ordine cliente. Nella Scheda dettagli **Righe ordine cliente**, aggiungi le seguenti righe di vendita:

    - Riga 1:

        - **Numero articolo:** *A0001*
        - **Quantità:** *4*

    - Riga 2:

        - **Numero articolo:** *A0002*
        - **Quantità:** *4*

1. Seleziona la prima riga, quindi seleziona **Inventario \> Prenotazione**.
1. Nella pagina **Prenotazione**, selezionare **Prenota lotto**. Quindi, chiudere la pagina.
1. Ripeti i due passaggi precedenti per la seconda riga.
1. Chiudere la pagina.

### <a name="create-the-load"></a>Creare il carico

Segui questi passaggi per creare un carico per ciascun ordine creato per questo scenario e quindi rilascialo nel magazzino.

1. Vai a **Gestione magazzino \> Carichi \> Workbench pianificazione carico**.
1. Nella scheda **Righe di vendita**, trova e seleziona tutte le righe degli ordini cliente creati per questo scenario.
1. Nel riquadro azioni, nella scheda **Domanda e offerta**, nel gruppo **Aggiungi** seleziona **Al nuovo carico**. Le righe dell'ordine selezionate vengono aggiunte a un nuovo carico.
1. Nella finestra di dialogo **Assegnazione modello di carico**, nel campo **ID modello carico**, seleziona un modello di caricamento, ad esempio *40' Contenitore*.
1. Selezionare **OK** per chiudere la finestra di dialogo.
1. Nella sezione **Carichi**, trova e seleziona il carico che hai appena creato.
1. Seleziona **Rilascia \> Rilascia in magazzino**.
1. Nella finestra di dialogo **Rilascia in magazzino** seleziona **OK** per rilasciare il carico selezionato nel magazzino.

### <a name="verify-the-shipments-and-containers"></a>Verificare le spedizioni e i contenitori

La seguente procedura consente di verificare le spedizioni che sono state create. Usala per rivedere l'ordine che hai creato per questo scenario e per assicurarti di aver ottenuto i risultati previsti.

1. Vai a **Gestione magazzino \> Spedizioni \> Tutte le spedizioni**.
1. Trova e seleziona la spedizione che è stata creata per il carico che hai appena rilasciato.
1. Nel riquadro azioni, nella scheda **Trasporto** seleziona **Visualizza contenitori**.
1. Verifica che gli articoli degli ordini cliente sono stati containerizzati in due contenitori diversi.

## <a name="additional-resources"></a>Risorse aggiuntive

- [Containerizzazione](wave-containerization.md)
