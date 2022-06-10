---
title: Registrazione degli ordini di produzione
description: Questo argomento fornisce informazioni sui diversi tipi di registrazione degli ordini di produzione.
author: rachelprofitt
ms.date: 04/25/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: InventPosting, InventItemGroup, ProdGroup, WrkCtrTable, WrkCtrResourceGroup, ProjCategory, CostSheetDesigner
audience: Application User
ms.search.region: Global
ms.author: raprofit
ms.openlocfilehash: cd1b6c49e59f9480fd831ad5ff143033ca09792c
ms.sourcegitcommit: 5b55f2913e736d12e40c227bf3ce3a9abec815bd
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/24/2022
ms.locfileid: "8803024"
---
# <a name="production-postings"></a>Registrazioni di produzione

Questo argomento fornisce informazioni sui diversi tipi di registrazione nel processo ordine di produzione.


## <a name="material-consumption"></a>Consumo materiali

I materiali vengono registrati come utilizzati in produzione quando il giornale di registrazione distinte di prelievo produzione viene registrato. Questo processo crea le transazioni in uscita che riducono le scorte disponibili. Nei **parametri di produzione** è possibile specificare se il valore delle materie prime in lavorazione (chiamato WIP) deve essere registrato nella contabilità generale.

Il valore delle materie prime in lavorazione (WIP) viene registrato nei conti **Costo stimato dei materiali consumati** e **Costo stimato dei materiali consumati, WIP**. Il processo della distinta di prelievo per l'ordine di produzione è un aggiornamento fisico delle transazioni di magazzino relative all'ordine di produzione. Quando un ordine di produzione viene registrato come terminato, le transazioni fisiche vengono stornate e le relative transazioni di magazzino vengono aggiornate finanziariamente. Quando il giornale di registrazione finale viene registrato, i tipi di registrazione **Costo dei materiali consumati** e **Costo dei materiali consumati, WIP** vengono utilizzati.

La scheda **Produzione** nella pagina **Profili di registrazione inventario** controlla la modalità di registrazione degli ordini di produzione nella contabilità generale. Questo viene utilizzato quando il campo **Registrazione contabile** è impostato su **Articolo e risorsa** o **Articolo e categoria** nella pagina **Parametri di controllo produzione**. 

Affinché un giornale di registrazione della distinta di prelievo venga registrato nella contabilità generale per un ordine di produzione, devono essere soddisfatte le seguenti condizioni:

-   La casella di controllo **Registra distinta di prelievo nella contabilità generale** deve essere selezionata nella pagina **Parametri di controllo della produzione**. Questa impostazione può essere ignorata per un sito specifico nella pagina **Parametri di controllo della produzione per sito**.
-   La casella di controllo **Registra inventario fisico** deve essere selezionata nella pagina **Gruppi di modelli di articoli** per l'articolo selezionato nella riga dell'ordine fornitore.
-   I conti principali devono essere specificati nella pagina **Profilo di registrazione inventario** per i seguenti tipi di registrazione:
    -   **Costo stimato di materiali consumati**
    -   **Costo stimato di materiali consumati, WIP**

## <a name="time-consumption"></a>Consumo di tempo

Il tempo che i lavoratori utilizzano per i processi di produzione viene registrato nel **giornale di registrazione schede cicli di lavorazione** o nel **giornale di registrazione schede processi**. Quando questi giornali di registrazione vengono registrati, viene elaborata la registrazione contabile in un conto dedicato per le risorse in lavorazione (WIP). Questa registrazione rappresenta il valore del tempo dedicato sull'ordine di produzione. Una volta che l'ordine di produzione viene registrato come finito, i conti WIP vengono liquidati.

Esistono tre modi possibili per registrare il consumo di tempo a seconda dell'opzione selezionata nel campo **Registrazione contabile** della pagina **Parametri di controllo della produzione**.

## <a name="reporting-finished-goods-and-error-quantities"></a>Report su prodotti finiti e quantità di errore

Quando un ordine di produzione viene **segnalato come finito**, la quantità di prodotti finiti che sono stati completati viene aggiornata nella gestione inventario tramite il giornale di registrazione **dichiarazioni di finito**. Se si utilizza la contabilità WIP, viene generato un giornale di registrazione contabile per ridurre i conti WIP e aumentare le scorte dei prodotti finiti. Il giornale di registrazione utilizza il costo standard definito per il prodotto. Se l'opzione **Usa il prezzo di costo stimato** è selezionata nella pagina **Parametri di controllo della produzione** verrà utilizzato il costo stimato dell'ordine di produzione.

Il valore delle materie prime in lavorazione (WIP) viene registrato nei conti **Costo di produzione stimato** e **Costo di produzione stimato, WIP**. Il processo **Dichiarazione di finito** per l'ordine di produzione è un aggiornamento fisico delle transazioni di magazzino relative all'ordine di produzione. Quando un ordine di produzione è terminato, le transazioni fisiche vengono stornate e le relative transazioni di magazzino vengono aggiornate finanziariamente. Quando il giornale di registrazione finale viene registrato, i tipi di registrazione **Costo di produzione** e **Costo di produzione, WIP** vengono utilizzati.

La scheda **Produzione** nella pagina **Profili di registrazione inventario** viene utilizzata per controllare la modalità di registrazione degli ordini di produzione nella contabilità generale. Questo viene utilizzato quando il campo **Registrazione contabile** è impostato su **Articolo e risorsa** o **Articolo e categoria** nella pagina **Parametri di controllo produzione**. La Scheda dettaglio **Contabilità generale - Articoli** sulla pagina **Gruppi di produzione** può essere utilizzata anche per controllare la registrazione per gli ordini di produzione quando il campo è impostato su **Gruppi di produzione**.

Affinché un giornale di registrazione **Dichiarazione di finito** venga registrato nella contabilità generale per un ordine di produzione, devono essere soddisfatte le seguenti condizioni:
-   La casella di controllo **Registra la dichiarazione di finito nella contabilità generale** deve essere selezionata nella pagina **Parametri di controllo della produzione**. Questa impostazione può essere ignorata per un sito specifico nella pagina **Parametri di controllo della produzione per sito**.
-   La casella di controllo **Registra inventario fisico** deve essere selezionata nella pagina **Gruppi di modelli di articoli** per l'articolo selezionato nella riga dell'ordine fornitore.
-   I conti principali devono essere specificati nella pagina **Profilo di registrazione inventario** per i seguenti tipi di registrazione:
    -   **Costo di produzione stimato**
    -   **Costo di produzione stimato, WIP**

## <a name="ending-the-production-order"></a>Fine dell'ordine di produzione

Prima che un ordine di produzione venga terminato, vengono calcolati i costi effettivi della quantità prodotta. Tutti i costi stimati in termini di materiali, manodopera e gestione generale vengono annullati e sostituiti con i costi effettivi. Il costo complessivo dell'articolo finito viene addebitato dal conto **Costo di produzione** e accreditato sul conto **Costo di produzione, WIP**. I materiali consumati durante l'ordine di produzione vengono accreditati nel conto **Costo dei materiali consumati** e addebitati nel conto **Costo dei materiali, WIP**.

Se selezioni la casella di controllo **Processo finale** quando esegui il calcolo dei costi, lo stato dell'ordine di produzione viene impostato su **Finito**. Tale stato impedisce che vengano inavvertitamente registrati ulteriori costi per un ordine di produzione completato. È possibile specificare che il valore delle quantità difettose dichiarate finite deve essere allocato alle quantità idonee dichiarate finite. In alternativa, è possibile specificare che il valore delle quantità di errore venga registrato in un conto scarti dedicato. 

Per specificare un conto scarti specifico, procedi nel seguente modo:
1.  Vai a **Controllo produzione** > **Impostazioni** > **Parametri di controllo produzione**.
2.  Seleziona la scheda **Aggiornamento standard**.
3.  Nel campo **Metodo scarti** seleziona **Conto scarti**.
4.  Nel campo **Conto scarti** seleziona il conto principale in cui registrare la quantità di scarto per errore al termine dell'ordine di produzione. Ad esempio, seleziona un conto spese come 510380: Scarto di produzione.

Affinché il giornale di registrazione finale venga registrato nella contabilità generale per un ordine di produzione, devono essere soddisfatte le seguenti condizioni:
-   I conti principali devono essere specificati nella pagina **Profilo di registrazione inventario** o **Gruppi di produzioni** per i seguenti tipi di registrazione:
    -   **Costo di materiali consumati**
    -   **Costo di materiali consumati, WIP**
    -   **Costo di produzione**
    -   **Costo di produzione, WIP**
-   I conti principali devono essere specificati nella pagina **Categorie di costo**, **Risorse**, o **Gruppi di risorse** per i seguenti tipi:
    -   **Costo di produzione assorbito**
    -   **Costo di produzione consumato, WIP**

## <a name="indirect-costs-for-production-orders"></a>Costi indiretti per ordini di produzione

Quando si elaborano le transazioni per un ordine di produzione, è possibile configurare i costi indiretti per acquisire i costi generali o le commissioni aggiuntive nella contabilità generale. Le transazioni fisiche per i costi indiretti vengono rilevate nell'inventario quando registri un giornale di registrazione distinta di prelievo o un giornale di registrazione di dichiarazione di finito. Le transazioni finanziarie per i costi indiretti vengono rilevate nell'inventario quando si registra il giornale di registrazione finale.

Puoi riconoscere i costi indiretti del consumo di tempo relativi ai giornali di registazione **Scheda ciclo di lavorazione** o **Scheda processo**. Queste transazioni vengono stornate e registrate nei conti finanziari al termine dell'ordine di produzione. Per ulteriori informazioni, vai a [Schede di determinazione costi](/supply-chain/cost-management/costing-sheets.md).

## <a name="controlling-the-level-of-ledger-posting"></a>Controllo del livello di registrazione contabile

Nella pagina **Parametri di controllo produzione**, è possibile utilizzare il campo **Registrazione contabile** per impostare il livello di registrazione contabile per i processi di produzione. 

Sono disponibili i campi seguenti:

### <a name="item-and-resource"></a>Articolo e risorsa

Quando selezioni l'opzione **Articolo e risorsa** nel campo **Registrazione contabile**, i conti di registrazione provengono dalla risorsa o dal gruppo di risorse in funzione nel ciclo di lavorazione. I conti sulla risorsa specifica saranno la prima opzione di registrazione. Se non viene specificato un conto, verranno utilizzati i conti specificati nel gruppo di risorse. Ciascuna riga operazione in un ciclo di lavorazione può avere una sola risorsa specificata come **Risorsa determinazione costi**. Questa risorsa viene utilizzata per determinare il conto da utilizzare. Questa opzione viene comunemente utilizzata quando un'organizzazione assegna i costi operativi alle risorse. I costi sono spesso più elevati per le risorse e vengono utilizzati per aiutare a prendere decisioni di tipo "fare anziché comprare". Questa è la configurazione di registrazione più dettagliata e consente il controllo più granulare delle registrazioni e un'analisi molto dettagliata del processo di produzione.

### <a name="item-and-category"></a>Articolo e categoria

Quando selezioni l'opzione **Articolo e categoria** nel campo **Registrazione contabile**, i conti di registrazione proverranno dalla pagina **Categoria di costo** relativa a ciascuna riga del ciclo di lavorazione. Ciascuna riga operazione del ciclo di lavorazione può avere tre categorie di costo: tempo di **attrezzaggio**, tempo di **esecuzione** e la **quantità**. Questa opzione viene comunemente utilizzata quando l'obiettivo principale dell'organizzazione è l'efficienza dei processi e la durata dell'attività. Questa opzione è un modo più riepilogativo di registrazione e fornisce comunque un modo per raggruppare i costi in categorie.

### <a name="production-group"></a>Gruppo di produzioni

Quando selezioni l'opzione **Gruppi di produzione** nel campo **Registrazione contabile**, i conti di registrazione provengono dalla pagina **Gruppi di produzione**. I **Gruppi di produzione** vengono in genere utilizzati quando più di una riga di produzione esegue prodotti simili o dispone di apparecchiature simili. È possibile utilizzare questa opzione per confrontare i costi tra due diversi gruppi di produzione.  
  
> [!NOTE]
> Se per il calcolo del costo dell'articolo finito è stato utilizzato il metodo standard, nelle transazioni finali verrà riflesso anche questo aspetto. In caso di differenza tra i costi effettivi e i costi calcolati con il metodo standard, tale differenza verrà registrata sul conto che mostra il profitto o la perdita.

### <a name="route-groups-and-ledger-posting"></a>Gruppi di cicli di lavorazione e registrazione contabile

Ogni riga operazione in un ciclo di produzione ha un **Gruppo di cicli di lavorazione** specificato. I campi **Tempo di attrezzaggio**, **Tempo di esecuzione**, e **Quantità** sul **Gruppo di cicli di lavorazione** nel gruppo **Stima e costi** vengono utilizzati per controllare se il tempo verrà utilizzato per la determinazione dei costi durante la registrazione di una **Scheda processo** o un **Giornale di registrazione schede cicli di lavorazione** sull'ordine di produzione. Se le opzioni sono disabilitate, non verrà creato un giustificativo nella contabilità generale per il consumo di tempo.

Affinché una **Scheda ciclo di lavorazione** o un **Giornale di registrazione schede processi** venga registrato nella contabilità generale per un ordine di produzione, devono essere soddisfatte le seguenti condizioni:

-   Il campo **Tempo di attrezzaggio**, **Tempo di esecuzione** o **Quantità** deve essere selezionato nel gruppo **Stima e costi** sulla pagina **Gruppo di cicli di lavorazione**.
-   I conti principali devono essere specificati nella pagina **Categoria di costo**, **Ciclo di lavorazione**, **Gruppo di cicli di lavorazione**, o **Gruppi di produzione** per i seguenti tipi di registrazione:
    -   Costi di produzione assorbiti stimati
    -   Costo stimato di produzione consumato, WIP

Il diagramma seguente mostra la relazione tra il gruppo di cicli di lavorazione e il calcolo del costo totale per ciascuna operazione (riga di ciclo di lavorazione) in un determinato ciclo di lavorazione. Ogni riga di ciclo di lavorazione ha un gruppo di cicli di lavorazione. Il gruppo di cicli di lavorazione controlla i parametri per il tempo di attrezzaggio, il tempo di esecuzione e la quantità. La scheda **Categoria di costo** ha tre opzioni per **Attrezzaggio**, **Esecuzione**, e **Quantità** abilitate in base all'impostazione dei gruppi di cicli di lavorazione. La scheda dettaglio **Tempi** ha tre campi basati sul gruppo di cicli di lavorazione.

La formula utilizzata si basa sul fatto che l'opzione sia abilitata nel gruppo di cicli di lavorazione. Il costo della categoria di costo selezionata viene moltiplicato per la quantità inserita nei tempi per calcolare il costo totale.

:::image type="complex" source="media/RouteGroupRelationship.png" alt-text="La relazione tra i gruppi di cicli di lavorazione e il costo totale calcolato.":::
La relazione tra i gruppi di cicli di lavorazione e il costo totale calcolato. Ogni riga di ciclo di lavorazione ha un gruppo di cicli di lavorazione. Il gruppo di cicli di lavorazione controlla i parametri per il tempo di attrezzaggio, il tempo di esecuzione e la quantità. La scheda Ccategoria di costo ha tre opzioni per Attrezzaggio, Esecuzione, e Quantità abilitate in base all'impostazione dei gruppi di cicli di lavorazione. La scheda dettaglio Tempi ha tre campi abilitati e calcolati basati sul gruppo di cicli di lavorazione. La formula utilizzata si basa sul fatto che l'opzione sia abilitata nel gruppo di cicli di lavorazione. Il costo della categoria di costo selezionata viene moltiplicato per la quantità inserita nei tempi per calcolare il costo totale.
:::image-end:::

## <a name="sample-posting-profile-configuration"></a>Esempio di configurazione del profilo di registrazione

La tabella seguente mostra esempi dei tipi di registrazione predefiniti con conti principali e descrizioni di esempio. 

 - La colonna **Debito/Credito** indica se la transazione in genere viene addebitata o accreditata o in alcuni casi può essere registrata. 
 - La colonna **Conto di compensazione** indica se il tipo di registrazione è un conto di compensazione. L'importo registrato in questo conto viene automaticamente stornato quando viene registrata una transazione successiva. 
 - La colonna **P/F** indica **P** per la pubblicazione fisica e **F** per la registrazione finanziaria. 
 - La colonna **Segui** indica se il conto principale per un tipo di registrazione specifico è in genere uguale a un altro tipo di registrazione. Il valore nella colonna indica il tipo di registrazione generalmente utilizzato.

> [!NOTE]
> I conti principali e i nomi di conti principali sono suggerimenti. Ti consigliamo di collaborare con il tuo commercialista per determinare la configurazione migliore per le tue esigenze aziendali.


| Tipo di registrazione  | Esempio di conto principale | Esempio nome di conto principale| Tipo di account | Dare/Avere? | Conto di compensazione | Fisico o finanziario | Segui | Description |
|---------------|----------------------|--------------------------|--------------|----------------|------------------|-----------------------|--------|------------|
| Costo stimato di materiali consumati      | 140100               | Inventario dei materiali        | Cespite        | Credito         | Y                | P                     | Costo di materiali consumati                | Questo conto viene utilizzato quando si registra un giornale di registrazione distinta di prelievo per un ordine di produzione. La compensazione sul conto è il costo stimato dei materiali, WIP. L'importo in questo conto viene automaticamente stornato al termine dell'ordine di produzione. Questo conto rappresenta il conto inventario nello stato patrimoniale.       |
| Costo stimato di materiali consumati, WIP | 150150               | WIP produzione – Materiali | Cespite        | Dare          | Y                | P                     | Costo di produzione stimato, WIP          | Questo conto viene utilizzato quando si registra un giornale di registrazione distinta di prelievo per un ordine di produzione. La compensazione sul conto è il costo stimato dei materiali consumati. L'importo in questo conto viene automaticamente stornato al termine dell'ordine di produzione. Questo conto rappresenta il WIP nello stato patrimoniale.                  |
| Costo di produzione stimato               | 140200               | Inventario dei prodotti finiti   | Cespite        | Dare          | Y                | P                     | Costo di produzione                         | Questo conto viene utilizzato quando si registra un giornale di registrazione di dichiarazione di finito per un ordine di produzione. La compensazione sul conto è il costo di produzione stimato, WIP. L'importo in questo conto viene automaticamente stornato al termine dell'ordine di produzione. Questo conto rappresenta il conto inventario nello stato patrimoniale. |
| Costo di produzione stimato, WIP          | 150150               | WIP produzione – Materiali | Cespite        | Credito         | Y                | P                     | Costo di produzione, WIP                    | Questo conto viene utilizzato quando si registra un giornale di registrazione di dichiarazione di finito per un ordine di produzione. La compensazione sul conto è il costo di produzione stimato. L'importo in questo conto viene automaticamente stornato al termine dell'ordine di produzione. Questo conto rappresenta il WIP nello stato patrimoniale.                     |
| Costo di materiali consumati                | 140100               | Inventario dei materiali        | Cespite        | Credito         | N                 | V                     | Costo stimato di materiali consumati      | Questo conto viene utilizzato per riconoscere i materiali consumati nell'ordine di produzione durante il processo finale. La compensazione sul conto è il costo dei materiali consumati, WIP.                                                                                                    |
| Costo di materiali consumati, WIP           | 150150               | WIP produzione – Materiali | Cespite        | Dare          | N                 | V                     | Costo stimato di materiali consumati, WIP | Questo conto viene utilizzato per riconoscere i materiali in WIP consumati nell'ordine di produzione durante il processo finale. La compensazione sul conto è il costo dei materiali consumati.                                                |
| Costo di produzione                         | 140200               | Inventario dei prodotti finiti   | Cespite        | Dare          | N                 | V                     | Costo di produzione stimato               | Questo conto viene utilizzato per riconoscere il costo del bene finito prodotto da un ordine di produzione al termine dell'ordine di produzione. La compensazione sul conto è il conto costo di produzione, WIP.                                                                  |
| Costo di produzione, WIP                    | 150150               | WIP produzione – Materiali | Cespite        | Credito         | N                 | V                     | Costo di produzione stimato, WIP          | Questo conto viene utilizzato per riconoscere il costo del bene finito in WIP prodotto da un ordine di produzione al termine dell'ordine di produzione. La compensazione sul conto è il conto costo di produzione.                                     |

> [!NOTE]
> Le impostazioni **Entrata WIP servizio produzione snella** e **Conto di compensazione WIP per servizi di produzione snella** vengono utilizzati con la determinazione costi di tipo backflush per lean manufacturing. Per ulteriori informazioni, vai a [Determinazione costi di tipo backflush](/supply-chain/cost-management/backflush-costing.md).

