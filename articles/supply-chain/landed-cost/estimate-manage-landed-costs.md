---
title: Stimare e gestire i costi sbarcati
description: Il sistema utilizza la configurazione dei costi automatici per determinare una stima del costo sbarcato. In questo argomento viene descritto come definire vari scenari per fornire una stima più accurata.
author: sherry-zheng
ms.date: 01/26/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ITMCostTemplateTable, ITM CostEstimateDialog, ITMCostEstimateTable, SysOperationTemplateForm
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-01-26
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 5a8df57eaa779fe7b1f709a59372d9c634447c4a
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/29/2021
ms.locfileid: "7565809"
---
# <a name="estimate-and-manage-landed-costs"></a>Stimare e gestire i costi sbarcati

[!include [banner](../../includes/banner.md)]

Il sistema utilizza la [configurazione dei costi automatici](auto-cost-setup.md) per determinare una stima del costo sbarcato. Inoltre, è possibile definire vari scenari per fornire una stima più accurata. Questi scenari vengono memorizzati. Pertanto, è possibile esaminarli in un secondo momento e confrontarli con i valori effettivi in un report. È anche possibile aggiornare il prezzo dell'articolo.

## <a name="set-up-cost-estimates"></a>Configurare stime dei costi

### <a name="set-up-cost-templates"></a>Imposta i modelli dei costi

I modelli di costo stabiliscono impostazioni predefinite che gli utenti che ottengono la stima non conosceranno necessariamente. I modelli possono aiutare a ridurre la complessità del processo di stima riducendo al minimo le selezioni che gli utenti devono specificare per ottenere una stima accurata. Se utilizzi il modello di costo standard, puoi utilizzare i modelli di costo mentre imposti il costo delle merci.

Per impostare modelli di costo, selezionare **Costo sbarcato \> Configurazione dei costi \> Modelli di costo**. Nella pagina **Modelli di costo**, il riquadro elenco a sinistra mostra tutti i modelli di costo correnti. È possibile utilizzare i pulsanti nel riquadro azioni per creare, eliminare e modificare i modelli.

Nella seguente tabella vengono descritti i campi disponibili per ogni modello.

| Campo | Descrizione |
|---|---|
| Modello dei costi | Immettere un nome univoco per il modello di costo. Il nome in genere descrive il fattore o il moltiplicatore di costo per il modello. |
| Descrizione | Immettere una descrizione del modello di costo. |
| Società di spedizione | Selezionare la società di spedizione da applicare quando viene utilizzato il modello. |
| Modalità di consegna | Selezionare la modalità di consegna, come via mare o via aerea, da applicare quando viene utilizzato il modello. Questo campo consente di determinare i costi automatici associati alle merci in una stima dei costi. |
| Tipo di contenitore di spedizione | Selezionare il tipo di contenitore di spedizione da applicare quando viene utilizzato il modello. Questo campo consente di determinare i costi automatici associati alle merci in una stima dei costi. |
| Broker doganale | Il broker doganale (fornitore) da applicare quando viene utilizzato il modello. Questo campo consente di determinare i costi automatici associati alla stima dei costi. |
| Fattore | Immettere il moltiplicatore (percentuale) da applicare automaticamente alla stima dei costi quando si utilizza il modello. Ad esempio, per aggiungere il 10 percento alla stima dei costi calcolata, immettere *1,10*. |

### <a name="create-a-cost-estimate"></a>Creare una stima dei costi

Usare la finestra di dialogo **Stima dei costi** per generare una nuova stima dei costi basata su un modello di costo selezionato, un insieme di articoli selezionato e altri dettagli di un percorso. Queste impostazioni vengono quindi utilizzate per determinare i costi sbarcati stimati delle merci. Queste stime dei costi vengono utilizzate principalmente con voci di costo standard. Aggiungendo i costi sbarcati stimati al costo standard delle merci in inventario, si dovrebbero avere transazioni con uno scostamento minore quando le merci vengono aggiunte a un viaggio, poiché il costo standard rifletterà le stime di tali costi sbarcati.

Per aprire la finestra di dialogo **Stima dei costi**, selezionare **Costo sbarcato \> Attività periodiche \> Stima dei costi**. Quindi impostare i campi descritti nelle sottosezioni seguenti. Infine, selezionare **OK** per creare la stima. Viene quindi visualizzata la pagina **Stima dei costi** (**Costo sbarcato \> Informazioni \> Stima dei costi**) in cui appare la nuova stima, come descritto più avanti in questo argomento.

### <a name="settings-on-the-parameters-tab"></a>Impostazioni nella scheda Parametri

La tabella seguente descrive i campi disponibili nella scheda **Parametri** della finestra di dialogo **Stima dei costi**.


| Campo | Descrizione |
|---|---|
| Modello dei costi | Selezionare un modello di costo. Le impostazioni associate al modello selezionato verranno utilizzate per determinare i costi automatici applicati. |
| Data stima | Per impostazione predefinita, questo campo è impostato sulla data odierna, ma è possibile modificare il valore. La data specificata verrà utilizzata per selezionare i prezzi di vendita, i prezzi di acquisto, i costi automatici e il tasso di cambio appropriati se viene utilizzata una tariffa di spedizione. |
| Misura | I costi potrebbero dipendere da una misura. Ad esempio, quando viene utilizzato il trasporto aereo, potrebbe essere applicato il prezzo volumetrico. Se il costo dipende da una misura, immettere il valore di tale misura. In caso contrario, è consigliabile impostare questo campo su *1*, a meno che non si abbia la certezza che non si verifichi alcuna ripartizione utilizzando la misura. Immettere un valore decimale. L'unità è quella definita nel record del costo automatico applicabile. |
| Modello di percorso | Selezionare un [modello di percorso](multi-leg-journey-setup.md). Questo campo viene utilizzato per determinare i costi automatici corretti da applicare. |
| Porto di origine | Il porto da cui verranno spediti gli articoli. Questo campo viene impostato in base al modello di percorso selezionato. |
| Porto di destinazione | Il porto a cui verranno spediti gli articoli. Questo campo viene impostato in base al modello di percorso selezionato. |
| Valuta | Selezionare la valuta in cui verranno acquistati gli articoli. |
| Contenitori | Se in genere vengono utilizzati più contenitori, specificare il numero di contenitore. Il sistema utilizzerà quindi i costi per più contenitori quando stima i costi. |
| Registrazioni | Se in genere vengono utilizzate più registrazioni, specificare la quantità. In genere la quantità è *1*. |
| Sito | Specificare il sito in cui verrà consegnata la merce. |

### <a name="settings-on-the-items-tab"></a>Impostazioni della scheda Articoli

Nella scheda **Articoli**, è possibile aggiungere alla stima tutti gli articoli desiderati. Utilizzare la barra degli strumenti per aggiungere articoli alla griglia o rimuovere elementi. Selezionare **Inventario \> Visualizza dimensioni** nella barra degli strumenti per aprire una finestra di dialogo in cui è possibile aggiungere colonne dimensione alla griglia o rimuovere colonne.

Nella seguente tabella vengono descritti i campi disponibili per ogni articolo.

| Campo | Descrizione |
|---|---|
| Numero articolo | Selezionare l'articolo per cui determinare il prezzo. Se l'articolo non esiste ancora nel sistema, creare un articolo fittizio, allegarlo eventualmente a un gruppo di costi dell'articolo di viaggio, quindi lasciare vuoto il prezzo oppure creare o modificare il prezzo. |
| Account fornitore | Seleziona il fornitore da utilizzare per la stima di questo articolo. Se all'articolo viene assegnato un fornitore predefinito, questo campo viene impostato automaticamente. |
| Quantità | Selezionare la quantità che verrà acquistata. |
| Prezzo di costo | Il sistema utilizza le regole di determinazione dei prezzi per trovare un prezzo iniziale, ma è possibile sovrascrivere quel prezzo se necessario. |
| Prezzo di vendita | Immettere il prezzo di vendita previsto delle merci. |
| Misura | Immettere un valore decimale per la misura delle merci. L'unità è quella impostata per il prodotto rilasciato applicabile. |
| Aggiorna peso/volume articolo | Selezionare questa casella di controllo per aggiornare la misura del peso o del volume del prodotto rilasciato in modo che corrisponda al valore **Misura** immesso per questa riga. |
| (Altre dimensioni) | A seconda delle dimensioni selezionate per la visualizzazione, è possibile che siano visibili altre colonne di informazioni su ciascun elemento. |

Per visualizzare o modificare i dettagli del volume e/o del peso di un articolo, selezionare l'elemento nella griglia, quindi utilizzare i campi nella parte inferiore della pagina.

## <a name="manage-estimated-costs"></a>Gestire i costi stimati

Per visualizzare e modificare le stime dei costi create, selezionare **Costo sbarcato \> Informazioni \> Stime dei costi**. Nella pagina **Stime dei costi**, il riquadro elenco a sinistra mostra tutte le stime dei costi correnti. È possibile utilizzare i pulsanti del riquadro Azioni con una stima selezionata. Notare che non è possibile creare una nuova stima dei costi nella pagina **Stima dei costi**. Utilizzare invece la finestra di dialogo **Stima dei costi** (**Costo sbarcato \> Attività periodiche \> Stima dei costi**), come descritto in precedenza in questo argomento.

La pagina **Stime dei costi** mostra come è stato derivato ciascun costo stimato. Mostra anche il costo sbarcato stimato per ogni articolo. È possibile modificare una stima dei costi cambiando il prezzo di costo e/o la valuta associata alle varie merci. È inoltre possibile modificare i costi di viaggio associati sia a livello di viaggio che a livello di contenitore. Quando si utilizza questa pagina per modificare i costi, viene richiesto di ricalcolare i costi stimati per gli articoli nella stima dei costi. Quando si è pronti, è possibile utilizzare le stime per aggiornare il prezzo di costo degli articoli nel modello di costo.

### <a name="information-on-the-header"></a>Informazioni nell'intestazione

La parte superiore della pagina **Stima dei costi** mostra le impostazioni che sono state utilizzate per generare la stima dei costi selezionata, come descritto nella sezione precedente. 

### <a name="settings-and-buttons-on-the-lines-fasttab"></a>Impostazioni e pulsanti nella Scheda dettaglio Righe

La Scheda dettaglio **Righe** elenca ogni articolo incluso nella stima corrente. Nella seguente tabella viene descritto il campo disponibile per ogni riga.

| Campo | Descrizione |
|---|---|
| Account fornitore | Il conto fornitore associato all'articolo. |
| Numero articolo | Il numero di articolo. |
| Quantità | Il numero di articoli utilizzati per determinare il costo. |
| Prezzo di costo | Il prezzo di costo secondo l'accordo commerciale. Questo valore viene espresso nella valuta locale. |
| Misura | La singola misura. L'unità è quella definita per il prodotto rilasciato applicabile. |
| Costo sbarcato stimato | Il costo sbarcato stimato per la quantità totale. |
| Per unità | Il costo sbarcato stimato diviso per la quantità totale. |
| (Altre dimensioni) | A seconda delle dimensioni selezionate per la visualizzazione, è possibile che siano visibili altre colonne di informazioni su ciascun elemento. |

Nella seguente tabella vengono descritti i pulsanti disponibili nella barra degli strumenti della Scheda dettaglio **Righe**.

| Pulsante | Descrizione |
|---|---|
| Aggiungi | Aggiungere articoli alla stima dei costi. Dopo aver aggiunto articoli, è necessario selezionare **Ricalcola** nel riquadro Azioni. |
| Rimuovi | Rimuovere gli articoli dalla stima dei costi. Dopo aver rimosso articoli, è necessario selezionare **Ricalcola** nel riquadro Azioni. |
| Costi di viaggio | Apre una pagina in cui è possibile visualizzare e modificare vari tipi di costi di viaggio per l'articolo. |
| Magazzino \> Visualizza dimensioni | Apre una finestra di dialogo in cui è possibile aggiungere colonne dimensione alla griglia o rimuovere colonne. |

### <a name="settings-on-the-general-fasttab"></a>Impostazioni nella Scheda dettaglio Generale

La Scheda dettaglio **Generale** mostra i dettagli sull'articolo attualmente selezionato nella scheda Dettaglio **Righe**. Molte di queste informazioni sono ripetute nella Scheda dettaglio **Righe** e possono essere modificate in entrambe le schede. Tuttavia, ulteriori dettagli sono disponibili anche qui. I valori dei campi aggiuntivi sono basati sulla configurazione del prodotto rilasciato applicabile.

### <a name="settings-on-the-dimension-fasttab"></a>Impostazioni nella Scheda dettaglio Dimensione

La Scheda dettaglio **Dimensione** mostra i valori per tutte le dimensioni inventariali disponibili per l'articolo selezionato nella Scheda dettaglio **Righe**, indipendentemente dalle dimensioni che si è scelto di mostrare lì. Qualsiasi valore visualizzato in questa scheda proviene dal modello di stima dei costi applicabile. Questi valori sono facoltativi nel modello di stima dei costi.

### <a name="buttons-on-the-action-pane"></a>Pulsanti nel riquadro Azioni

È possibile utilizzare i pulsanti nel riquadro Azioni della pagina **Stima dei costi** con la stima dei costi selezionata. Nella seguente tabella vengono descritti i pulsanti disponibili.

| Azione | Descrizione |
|---|---|
| Richiesta di informazioni sui costi | Visualizza tutti i costi per il viaggio. È possibile visualizzare i costi a livello di singolo articolo in base alle esigenze. |
| Aggiorna costo standard | <p>Aggiornare il costo standard utilizzando la versione di determinazione costi predefinita definita nella pagina **Parametri del costo sbarcato**. È possibile sovrascrivere questa versione.</p><p>**Nota:** se un articolo ha diverse dimensioni articolo (ad esempio, vari colori e configurazioni), ma queste dimensioni non sono state selezionate per la stima, il sistema creerà un prezzo in sospeso per ciascuna combinazione.</p><p>**Importante:** la ripartizione dei prezzi viene creata e utilizzata per determinare lo scostamento costo standard per costo sbarcato.</p> |
| Costi di viaggio | Visualizzare e modificare i costi di viaggio per tutte le merci nella spedizione. |
| Ricalcola | Aggiorna i costi sbarcati stimati dopo che i costi di viaggio sono stati aggiornati, aggiunti o rimossi. |
| Blocca | Blocca il record della stima dei costi in modo che non sia possibile apportare ulteriori modifiche. |

## <a name="item-cost-price-update"></a>Aggiornamento prezzo di costo articoli

L'attività periodica **Aggiornamento prezzo di costo articoli** aggiorna tutte le stime dei costi che corrispondono ai filtri impostati quando si esegue l'attività. L'effetto è simile alla selezione di **Aggiorna costo standard** nel riquadro Azioni di una singola stima. Tuttavia, in questo caso, l'aggiornamento si applica a tutte le stime corrispondenti.

Per eseguire l'attività periodica, attenersi alla seguente procedura.

1. Selezionare **Costo sbarcato \> Attività periodiche \> Aggiornamento prezzo di costo articoli**.
1. Nella finestra di dialogo **Aggiorna prezzo di costo da stima**, impostare i seguenti campi come richiesto per limitare l'ambito dell'aggiornamento:

    - **Versione** - Aggiorna solo le stime che utilizzano la versione di determinazione costi specificata.
    - **Sito** - Aggiorna solo le stime che utilizzano il sito specificato.
    - **Modello dei costi** - Aggiorna solo le stime che utilizzano il modello specificato.
    - **Porto di destinazione** - Aggiorna solo le stime che utilizzano il porto di destinazione specificato.
    - **Data stima** - Aggiorna solo le stime che hanno la data specificata.

1. Impostare le opzioni nelle Schede dettaglio **Record da includere** e **Esecuzione in background** come al solito per le attività periodiche.
1. Selezionare **OK** per eseguire l'attività.

> [!NOTE]
> Questa attività periodica verrà eseguita correttamente solo a condizione che siano disponibili le seguenti informazioni:
>
> - **Profondità lorda**, **Larghezza lorda** e **Altezza lorda** per ogni prodotto pertinente.
> - Un **Porto di origine** per ogni fornitore pertinente.
