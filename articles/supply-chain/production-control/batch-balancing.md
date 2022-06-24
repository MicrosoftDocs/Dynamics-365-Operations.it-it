---
title: Bilanciamento del batch
description: In questo articolo viene illustrato il processo di bilanciamento del batch.
author: johanhoffmann
ms.date: 01/04/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BOMTable, WHSReservationHierarchy, WHSInventTableReservationHierarchy
audience: Application User
ms.reviewer: kamaybac
ms.custom: 1705903
ms.assetid: 427e01b3-4968-4cff-9b85-1717530f72e4
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 8.0.0
ms.openlocfilehash: 50392e8aa0deb568a57e1df59ced70625a4f8a78
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8856050"
---
# <a name="batch-balancing"></a>Bilanciamento del batch

[!include [banner](../includes/banner.md)]

In questo articolo viene illustrata la modalità con cui il processo di bilanciamento del batch è supportato.

Per ulteriori informazioni, guardare il [video sul bilanciamento del batch](https://www.youtube.com/watch?v=4SNLWsU9KyI&feature=youtu.be)

Nel processo di bilanciamento del batch, la quantità di ingredienti da utilizzare in un batch di produzione viene calcolata dalla concentrazione di principi attivi nei batch dei prodotti selezionati.

## <a name="products-that-have-an-active-ingredient"></a>Prodotti con un principio attivo

Un prodotto può essere definito dalla relativa concentrazione di un principio attivo. Il principio attivo di un prodotto è modellato utilizzando un attributo batch specifico del prodotto con un valore minimo, un valore massimo e un livello stabilito.

Il livello stabilito di un attributo batch rappresenta la percentuale prevista di un principio attivo in un prodotto. I valori minimo e massimo rappresentano la deviazione accettata dal livello stabilito. Possono essere utilizzati, ad esempio, come tolleranza accettata per i batch all'entrata del prodotto.

Un prodotto può disporre di un solo principio attivo. Per specificare il principio attivo di un prodotto, è necessario definire innanzitutto un attributo batch specifico del prodotto. Si associa quindi l'attributo come attributo di base del prodotto.

A livello di prodotto, è inoltre necessario specificare come il livello del principio attivo per un batch del prodotto deve essere registrato: come parte del processo di ricevimento degli acquisti o come parte di un processo di ordine di controllo qualità.

Per associare un attributo di base a un prodotto, è necessario impostare quanto segue:

- Il prodotto deve essere controllato per batch. Per controllare un prodotto per batch, è necessario assegnare un gruppo di dimensioni di tracciabilità al prodotto con una dimensione del batch attiva.

- L'attributo che indica i livelli dell'ingrediente devono essere definiti come un attributo batch specifico del prodotto.

Per cercare e modificare il valore effettivo del principio attivo per un batch:
1. Andare a **Gestione articoli \> Richieste di informazioni e report \> Dimensioni di tracciabilità \> Batch**.
1. Selezionare un numero di batch dalla griglia.
1. Nel riquadro azioni, aprire la scheda **Visualizza** e selezionare **Attributi batch di magazzino**.

## <a name="ingredient-types-and-how-they-interact-in-the-batch-balancing-process"></a>Tipi di ingredienti e come interagiscono nel processo di bilanciamento del batch

Una riga della formula creata può disporre di uno di questi tipi di ingrediente:

- Nessuna
- Attive
- Compensazione
- Dipendente generico

Nella parte restante di questa sezione vengono forniti alcuni esempi relativi al funzionamento di ciascun tipo di ingrediente. Gli esempi sono basati sulla seguente formula con una dimensione di batch totale di 100 litri.

| Tipo di ingrediente | Numero articolo | Quantità riga formula | Unità |
|---|---|---|---|
| Nessuna | A | 20 | litro |
| Attive | B | 30 | litro |
| Compensazione | C | 10 | litro |
| Dipendente generico | D | 40 | litro |

La tabella seguente fornisce una panoramica dei risultati di ogni esempio.

| Numero articolo | Tipo di ingrediente | Quantità stimata | Quantità bilanciata | Quantità attiva | Unità | Valore di base |
|---|---|---|---|---|---|---|
| A | Nessuna | 20 | 20 | | litro | |
| B | Attive | 30 | 25.71 | 9.00 | litro | 30.00 |
| C | Compensazione | 10 | 14.72 | | litro | |
| D | Dipendente generico | 40 | 39.57 | | litro | |

### <a name="active-ingredients"></a>Principi attivi

Quando un prodotto con un attributo di base viene aggiunto a una riga della formula, viene definito *principio attivo* della formula. Gli ordini batch con formule che includono principi attivi possono essere utilizzati per il processo di bilanciamento del batch. Per ogni ingrediente nella formula, il processo di bilanciamento del batch stima la quantità necessaria per la realizzazione del prodotto. La stima delle quantità si basa sulla concentrazione dei principi attivi nei batch selezionati.

#### <a name="active-ingredient-example"></a>Esempio di principio attivo

L'ingrediente B ha l'attributo di base X e un livello stabilito di 30 ed è incluso in una formula che richiede 30 litri di ingrediente B per ogni 100 litri di prodotto. Vinee creato un ordine batch con una dimensione batch di 100 litri. L'ordine batch viene avviato e, durante il processo di bilanciamento del batch, l'utente seleziona un batch di ingrediente B con un livello di potenza di 35. Poiché il livello di potenza di 35 è superiore al livello stabilito di 30, la quantità bilanciata di ingrediente B viene ridotta utilizzando il rapporto tra il valore di potenza e il livello stabilito del batch, che viene moltiplicato per la quantità stimata. Il calcolo della quantità bilanciata risulta come segue:

(30 ÷ 35) × 30 litri = 25,71 litri

### <a name="none-ingredients"></a>Nessun ingrediente

Se si applica il processo di bilanciamento del batch quando il **tipo di ingrediente** è *Nessuno*, la quantità stimata e la quantità bilanciata della riga della formula nell'ordine batch sono corrispondenti.

#### <a name="none-ingredient-example"></a>Esempio di nessun ingrediente

L'ingrediente viene assegnato a un ingrediente di tipo *Nessuno* e viene aggiunto a una formula per un prodotto finito. La formula richiede 10 litri di ingrediente A per ogni 100 litri di prodotto finito. Se un ordine batch richiede 200 litri, sia la quantità stimata che la quantità bilanciata di ingrediente A vengono calcolate come 20 litri.

### <a name="compensating-ingredients"></a>Ingredienti di compensazione

Un ingrediente di compensazione può compensare o integrare l'effetto del principio attivo in un prodotto. Di conseguenza, la quantità di ingrediente di compensazione utilizzato dipende dalla potenza del prodotto:

- **Effetto contrapposto** - Se la quantità di principio attivo è maggiore del previsto, è necessario aggiungere una quantità minore di ingrediente di compensazione.

- **Effetto complementare** - Se la quantità di principio attivo è minore del previsto, è necessario aggiungere una quantità maggiore di ingrediente di compensazione.

La relazione tra un principio attivo e un ingrediente complementare viene impostata nella pagina **Principio di compensazione**.

Per impostare le relazioni tra gli ingredienti, attenersi alla procedura indicata di seguito.

1. Selezionare **Gestione informazioni sul prodotto \> Distinte base e formule \> Formule**.
1. Aprire una riga della formula e quindi selezionare **Ingredienti** per aprire la pagina **Principio di compensazione**.
1. Selezionare la riga che rappresenta un principio di compensazione, quindi selezionare il principio attivo per compensare.

Nel principio di compensazione si immette inoltre un fattore di compensazione positivo o negativo per specificare la quantità per cui compensare e se il principio deve essere contrapposto o complementare. Un fattore positivo indica un effetto complementare e un fattore negativo indica un effetto contrapposto.

#### <a name="compensating-ingredient-example"></a>Esempio di ingrediente di compensazione

L'ingrediente B è un principio attivo con l'attributo di base X e un livello stabilito di 30. È incluso in una formula che richiede 30 litri di ingrediente B per ogni 100 litri di prodotto. L'ingrediente C è un ingrediente di compensazione e una quantità pari a 10 è inclusa nella stessa formula. Un fattore di compensazione di 1,10 è impostato per il principio di compensazione. Di conseguenza, la quantità bilanciata dell'ingrediente di compensazione verrà ridotta della differenza tra la quantità bilanciata del principio attivo e la quantità stimata richiesta moltiplicata per 1,10.

Nell'esempio per il tipo di ingrediente *Attivo*, la quantità bilanciata del principio attivo richiesto è stata calcolata come 25,71 e la quantità stimata richiesta è stata calcolata come 30. In questo caso, la quantità bilanciata dell'ingrediente di compensazione verrà calcolata come segue:

1. Viene determinata la differenza tra la quantità stimata e quella bilanciata:  
    25,71 - 30 = - 4,29

1. Il risultato viene moltiplicato per il fattore di compensazione:  
    4,29 × 1,10 = - 4,72

1. La quantità di compensazione stimata viene ridotta di - 4,72 per determinare la quantità di compensazione bilanciata:  
    10 - (- 4,72) = 14,72

Poiché 1,10 è un fattore di compensazione positivo, il principio di compensazione ha un effetto complementare. In questo caso, il principio attivo è più potente di quanto previsto. Di conseguenza, è necessaria una quantità maggiore di ingrediente di compensazione.

### <a name="filler-ingredients"></a>Riempitivi

Un *riempitivo* è un ingrediente neutro utilizzato per ottenere la quantità desiderata del prodotto finito. Le rettifiche alle quantità di riempitivo vengono calcolate in base alle variazioni di principio attivo e di ingrediente di compensazione rispetto alla quantità standard.

#### <a name="filler-ingredient-example"></a>Esempio di riempitivo

È stato formulato un prodotto che include gli ingredienti A, B, C e D per una dimensione di formula di 100 litri. È stata calcolata la quantità bilanciata di tutti i tipi di ingredienti eccetto il tipo di ingrediente *Riempitivo* utilizzato in una riga.
La quantità bilanciata del riempitivo viene calcolata come la differenza tra la dimensione batch di 100 litri e la somma degli ingredienti A, B e C:

100 - (20 + 25,71 + 14,72) = 39,57

## <a name="the-batch-balancing-process"></a>Il processo di bilanciamento del batch

Il processo di bilanciamento del batch viene eseguito dalla pagina **Bilanciamento del batch**.
Selezionare **Gestione costi \> Ordini batch**, quindi nella scheda **Processo** selezionare **Bilanciamento del batch**. Il bilanciamento del batch è disponibile per gli ordini batch con stato **Iniziato**.

In genere, il bilanciamento del batch può essere applicato agli ordini batch se la formula dispone di almeno una riga della formula in cui il **tipo di ingrediente** è *Attivo*. Per l'eccezione a questa regola, vedere la sezione "Ordini batch non applicabili al bilanciamento del batch" più avanti in questo articolo.

Il processo di bilanciamento del batch può essere diviso in due processi secondari:

1. Bilancia ingredienti batch
1. Confermare e rilasciare la formula

### <a name="balance-batch-ingredients"></a>Bilancia ingredienti batch

Nel processo secondario Bilancia ingredienti batch, la quantità di ingredienti da utilizzare per il batch di produzione viene calcolata in base ai batch selezionati con principi attivi. In generale, il calcolo può essere completato solo in caso di copertura totale di tutti gli ingredienti. Non è possibile bilanciare solo parte del batch che l'ordine batch è impostato per produrre.

> [!NOTE]
> Non è possibile salvare un calcolo e quindi completare il processo di bilanciamento del batch in un secondo momento. Se si chiude la pagina **Bilanciamento del batch**, è necessario ripetere il calcolo per completare il processo.

### <a name="confirm-and-release-the-formula"></a>Confermare e rilasciare la formula

Dopo che le quantità di ingredienti sono state calcolate, è possibile confermare e rilasciare la formula. Il processo di rilascio varia a seconda che i prodotti siano attivati per i processi di gestione magazzino:

- Se un prodotto è attivato per i processi di gestione magazzino, la riga della formula viene rilasciata al magazzino in base ai principi per i processi di gestione magazzino. La riga della formula viene rilasciata in quantità corrispondenti alle quantità rilasciate e viene rilasciata per i batch specifici selezionati per i principi attivi.

    > [!NOTE]
    > Le righe della formula possono essere rilasciate al magazzino solo come parte del processo di bilanciamento del batch. Anche se sono presenti altre opzioni per il rilascio di materiali per la produzione al magazzino, queste opzioni non possono essere utilizzate per le righe della formula.

- Se un prodotto non è attivato per i processi di gestione magazzino, una distinta di prelievo di produzione viene creata per il prodotto quando si conferma e si rilascia la formula.

In un'unica formula, è possibile combinare i prodotti attivati per i processi di gestione magazzino e i prodotti che non sono attivati per tali processi. Quando i due tipi di prodotti sono inclusi in una formula, i prodotti attivati per i processi di gestione magazzino vengono rilasciati al magazzino. Per i prodotti non attivati per i processi di gestione magazzino, una distinta di prelievo viene creata quando si conferma e si rilascia la formula.

### <a name="batch-orders-that-arent-applicable-for-batch-balancing"></a>Ordini batch non applicabili al bilanciamento del batch

Esistono due eccezioni alla regola in base alla quale gli ordini batch sono applicabili al bilanciamento del batch se la formula dispone di almeno una riga della formula in cui il **tipo di ingrediente** è *Attivo*.

1. Se una formula contiene un principio attivo per un prodotto attivato per i processi di gestione magazzino, ma il numero batch è sotto il percorso nella gerarchia prenotazioni, l'ordine batch non è applicabile al bilanciamento del batch.
1. Se l'unità di misura della formula è diversa dall'unità di misura dell'inventario del principio attivo, l'ordine batch non è applicabile per il bilanciamento del batch.

Un ordine batch non applicabile al bilanciamento del batch viene sottoposto al ciclo di lavorazione standard per gli ordini batch.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]