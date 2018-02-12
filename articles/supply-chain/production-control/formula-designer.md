---
title: Designer formula
description: In questo argomento viene descritto come utilizzare Designer formula per analizzare e gestire le formule in una visualizzazione struttura.
author: cvocph
manager: AnnBe
ms.date: 06/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PlanActivity, ReqSupplyDemandSchedule
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.search.industry: 
ms.author: conradv
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: ace0d73cba7102f909d6d0400bd5b340c3c382b8
ms.contentlocale: it-it
ms.lasthandoff: 11/03/2017

---

# <a name="formula-designer"></a>Designer formula

[!include[banner](../includes/banner.md)]

In questo argomento viene descritto come utilizzare Designer formula per analizzare e gestire le formule in una visualizzazione struttura.

Quando si apre la pagina **Designer formula** dalla pagina **Prodotti rilasciati**, la struttura nel riquadro a sinistra mostra l'elenco dei co-prodotti e la gerarchia degli ingredienti del prodotto rilasciato. La struttura deriva dalla gerarchia delle formule attive e approvate per l'articolo selezionato e i relativi ingredienti, il sito di ordine predefinito dell'articolo e la data di validità.

Fare clic su **Impostazione** per selezionare diverse configurazioni e specificare quali informazioni visualizzare sulle righe della struttura.

Fare clic su **Filtro** per modificare la selezione iniziale nella visualizzazione. Impostando il principio visualizzazione su **Selezionato/Attivo** o **Selezionato**, è possibile selezionare singole versioni di formula o di cicli di lavorazione da utilizzare nella visualizzazione. È possibile selezionare versioni di formula non approvate e non attivate da visualizzare o gestire in Designer formula.  

> [!NOTE]
> Se si apre **Designer formula** dalla pagina elenco **Distinte base**, non vengono visualizzate le informazioni sul ciclo di lavorazione. Attualmente, la selezione di una versione di formula o ciclo di lavorazione viene applicata a tutte le istanze del designer formula.  

Nelle sezioni seguenti vengono descritte le funzionalità disponibili in Designer DBA.

## <a name="analyze-a-formula-structure-by-using-the-formula-designer"></a>Analizzare una struttura della formula in Designer formula
Designer formula dispone di due sezioni:

-   La visualizzazione struttura ad albero della struttura formula.
-   La sezione dei dettagli, contenente i dettagli dei dati selezionati. Quando si seleziona un nodo nella visualizzazione struttura ad albero, le Schede dettaglio nella sezione dettagli vengono aggiornate in base a quel nodo:
    -   **Dettagli riga formula** - Mostra i dettagli della riga formula selezionata nella visualizzazione struttura ad albero.
    -   **Dati articolo** - Mostra i dettagli dell'articolo principale o dell'articolo utilizzato nel nodo selezionato. È possibile fare clic su **Modifica prodotto rilasciato** per mantenere l'articolo selezionato.
    -   **Formula** - Mostra l'intestazione della formula che è correlata al nodo selezionato.
    -   **Ciclo di lavorazione** - Mostra l'intestazione del ciclo che è correlato al nodo selezionato.
    -   **Operazioni ciclo di lavorazione** - Mostra un'anteprima delle operazioni per il ciclo di lavorazione. Quando una riga distinta base (DBA) assegnata a un'operazione specifica è selezionata, l'operazione è contrassegnata come **Componente necessario alle operazioni**.

## <a name="select-a-formula-and-route"></a>Selezionare una formula e un ciclo di lavorazione
Il filtro applicabile per la formula e il ciclo di lavorazione viene visualizzato nell'intestazione di Designer formula. È possibile modificare il filtro utilizzando la finestra di dialogo **Filtro**. Nella seguente tabella sono descritti i campi di questa finestra di dialogo.

<table>
<thead>
<tr class="header">
<th>Campo</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Dimensioni prodotto</td>
<td>Se il prodotto finito selezionato è una rappresentazione generale prodotto, è possibile definire le dimensioni prodotto attive per la selezione principale. Se si apre Designer formula per un prodotto che non è una rappresentazione generale prodotto, nessuna dimensione prodotto può essere selezionata nella finestra di dialogo <strong>Filtro</strong>.</p></td>
</tr>
<tr class="even">
<td>Sito</td>
<td>Modificare il sito per il quale è visualizzata la struttura ingredienti. Il sito predefinito è il sito di magazzino predefinito dell'articolo finito.</td>
</tr>
<tr class="odd">
<td>Principio visualizzazione</td>
<td><p>Selezionare il principio di visualizzazione della versione applicabile alla struttura della formula e al ciclo di lavorazione correnti.</p>
<ul>
<li>Se il principio di visualizzazione è impostato su <strong>Attivo</strong> o su <strong>Selezionato/Attivo</strong>, viene trovata la versione valida della formula o del ciclo di lavorazione.</li>
<li>Quando il principio è impostato su <strong>Selezionato/Attivo</strong> o <strong>Selezionato</strong>, è possibile selezionare una versione di formula o di ciclo di lavorazione facendo clic su <strong>Formula</strong> &gt; <strong>Versioni formula</strong> o <strong>Ciclo di lavorazione</strong> &gt; <strong>Versioni cicli di lavorazione</strong>.</li>
</ul></td>
</tr>
<tr class="even">
<td>Data versione</td>
<td>Immettere la data della versione per la formula e il ciclo di lavorazione. La versione identifica la versione della formula utilizzata in una data specifica, determinata dalle date della versione specificate nell'impostazione della versione di formula.</td>
</tr>
<tr class="odd">
<td>Da quantità</td>
<td>Consente di filtrare le versioni selezionando una specifica quantità "iniziale". Se si imposta un valore, è possibile che vengano selezionate versioni differenti di formula e di ciclo di lavorazione.</td>
</tr>
<tr class="even">
<td>Visualizza solo validi</td>
<td>Quando si seleziona la casella di controllo, nella struttura ad albero vengono visualizzate solo le righe formula con date valide. Fare clic con il pulsante destro del mouse oppure fare doppio clic su una riga formula per aprire la pagina <strong>Modifica riga formula</strong> e vedere le date di validità della riga formula.</td>
</tr>
</tbody>
</table>

Quando si utilizza Designer formula per rivedere o modificare le formule che sono costituite da uno o più livelli di voci fittizie, il ciclo di lavorazione associato all'articolo di livello superiore in genere estende la gerarchia completa formula. Per semplificare la panoramica, è possibile bloccare il ciclo di livello superiore nella visualizzazione facendo clic su **Visualizza** &gt; **Blocca ciclo di lavorazione**. Per sbloccare il ciclo di lavorazione, fare clic su **Visualizza** &gt; **Sblocca ciclo di lavorazione**.

## <a name="add-and-edit-formulas-and-formula-lines"></a>Aggiungere e modificare formule e righe della formula 
Utilizzare le funzioni **Righe DBA** o **Formula** per modificare le righe formula o la formula. Quando si seleziona un nodo nella struttura ad albero, il tipo di nodo determina quali funzioni sono disponibili.

| Funzione                            | descrizione                                                                                               | Tipo di nodo e condizioni |
|-------------------------------------|-----------------------------------------------------------------------------------------------------------|--------------------------|
| Righe DBA &gt; Modifica                 | Consente di aprire una finestra di dialogo in cui è possibile modificare gli attributi della riga formula.                                         | Questa funzione è disponibile quando un nodo della riga formula è selezionato. |
| Righe DBA &gt; Elimina               | Eliminare una riga formula dalla formula selezionata.                                                          | Questa funzione è disponibile quando un nodo della riga formula è selezionato e la formula non è bloccata per la modifica. |
| Righe DBA &gt; Aggiungi prima della riga      | Consente di aprire una finestra di dialogo in cui è possibile selezionare una variante prodotto da includere prima della riga formula selezionata.     | Questa funzione è disponibile quando un nodo della riga formula è selezionato. |
| Righe DBA &gt; Aggiungi a DBA dei componenti | Consente di aprire una finestra di dialogo in cui è possibile selezionare una variante prodotto da includere alla fine della riga formula selezionata.   | Questa funzione è disponibile quando il nodo selezionato dispone di una formula selezionata. Se questa funzione non è disponibile, è possibile che manchi una versione formula per la variante selezionata dell'articolo. In questo caso, è possibile fare clic su **Formula** &gt; **Crea versione** per creare la versione mancante per il nodo selezionato. |
| Righe DBA &gt; Aggiungi dopo la riga       | Consente di aprire una finestra di dialogo in cui è possibile selezionare una variante prodotto da includere dopo la riga formula selezionata.      | Questa funzione è disponibile quando un nodo della riga formula è selezionato. |
| Formula &gt; Crea versione         | Consente di creare una nuova versione formula o una nuova formula per la variante prodotto del nodo selezionato.                     | Questa funzione è disponibile quando il nodo della riga formula selezionato è collegato a un articolo che ha un tipo di produzione **DBA** o **Formula**. |
| Formula &gt; Calcolo            | Consente di aprire una finestra di dialogo in cui è possibile eseguire il calcolo del costo e del prezzo di vendita per la variante prodotto selezionata. | Questa funzione è disponibile quando il nodo selezionato è correlato a una versione formula. |
| Formula &gt; Verifica                  | Consente di convalidare e verificare la formula selezionata.                                                                  | Questa funzione è disponibile quando il nodo selezionato è correlato a una versione formula. |

## <a name="configuring-the-tree-view"></a>Configurazione della visualizzazione struttura ad albero
Fare clic su **Impostazione** per personalizzare le informazioni che vengono mostrate nella visualizzazione struttura ad albero di Designer formula.

| Gruppo campi | descrizione |
|-------------|-------------|
| DBA         | Utilizzare le caselle di controllo per selezionare i criteri che vengono visualizzati nella struttura ad albero. I criteri selezionati verranno visualizzati nella parte inferiore di entrambe le schede. |
| Ciclo       | Utilizzare le caselle di controllo per selezionare i criteri che vengono visualizzati per i cicli di lavorazione. |

