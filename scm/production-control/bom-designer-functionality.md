---
title: "Funzionalità Designer DBA"
description: "In questo articolo viene descritto come utilizzare la pagina Designer DBA per progettare e utilizzare strutture ad albero per le distinte base (BOM). È possibile fare clic su Impostazione per selezionare diverse configurazioni e specificare quali informazioni visualizzare sulle righe della struttura."
author: YuyuScheller
manager: AnnBe
ms.date: 2015-12-08 21 - 09 - 22
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: BOMDesigner
audience: Application User
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 20981
ms.assetid: 2b92eec1-d28c-4965-9086-939c77b3c62b
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: 2c98039c9fa8179408394f9f66b9fca0f8cad3fe
ms.lasthandoff: 03/29/2017


---

# <a name="bom-designer-functionality"></a>Funzionalità Designer DBA

In questo articolo viene descritto come utilizzare la pagina Designer DBA per progettare e utilizzare strutture ad albero per le distinte base (BOM). È possibile fare clic su Impostazione per selezionare diverse configurazioni e specificare quali informazioni visualizzare sulle righe della struttura.

Quando viene aperta la pagina **Designer DBA** dalla pagina **Prodotti rilasciati**, vengono visualizzati la gerarchia di distinte base che sono attive e approvate per l'articolo selezionato, il sito di default dell'ordine per l'articolo e la data effettiva.  

Fare clic su **Filtro** per modificare la selezione iniziale nella visualizzazione. Impostando il principio visualizzazione su **Selezionato/Attivo o Selezionato**, è possibile selezionare singole versioni di DBA o di cicli di lavorazione da utilizzare nella visualizzazione. È possibile selezionare versioni di DBA non approvate e non attivate da visualizzare o gestire in Designer DBA.  

**Nota:** se si apre Designer DBA dalla pagina elenco **Distinte base**, non vengono visualizzate le informazioni sul ciclo di lavorazione. Attualmente, la selezione di una versione di DBA o di ciclo di lavorazione è una proprietà della versione di DBA e di ciclo di lavorazione e si applica a tutte le istanze di Designer DBA.  

Nelle sezioni seguenti vengono descritte le funzionalità disponibili nelle varie schede di Designer DBA.

## <a name="analyzing-a-bom-structure-by-using-the-bom-designer"></a>Analisi di una struttura DBA utilizzando Designer DBA
Designer DBA dispone di due sezioni:

-   La visualizzazione struttura ad albero della struttura DBA.
-   La sezione dei dettagli, contenente i dettagli dei dati selezionati. Quando si seleziona un nodo nella visualizzazione struttura ad albero, le Schede dettaglio nella sezione dettagli vengono aggiornate in base a quel nodo:
    -   **Dettagli riga DBA** - Mostra i dettagli della riga DBA selezionata nella visualizzazione struttura ad albero.
    -   **Dati articolo** - Mostra i dettagli dell'articolo principale o dell'articolo utilizzato nel nodo selezionato. È possibile fare clic su **Modifica prodotto rilasciato** per mantenere l'articolo selezionato.
    -   **DBA** - Mostra l'intestazione della DBA correlata al nodo selezionato.
    -   **Ciclo di lavorazione** - Mostra l'intestazione del ciclo che è correlato al nodo selezionato.
    -   **Operazioni ciclo di lavorazione** - Mostra un'anteprima delle operazioni per il ciclo di lavorazione. Quando una riga DBA assegnata a un'operazione specifica è selezionata, l'operazione è contrassegnata come **Componente necessario alle operazioni**.

## <a name="selecting-a-bom-and-route"></a>Selezione di una DBA e di un ciclo di lavorazione
Il filtro applicabile per la DBA e il ciclo di lavorazione viene visualizzato nell'intestazione di Designer DBA. È possibile modificare il filtro utilizzando la finestra di dialogo **Filtro**. Nella seguente tabella sono descritti i campi di questa finestra di dialogo.

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
<td>Se il prodotto finito selezionato è una rappresentazione generale prodotto, è possibile definire le dimensioni prodotto attive per la selezione principale.<strong>Nota:</strong> se si apre Designer DBA per un prodotto non è una rappresentazione generale prodotto, nessuna dimensione prodotto può essere selezionata nella finestra di dialogo <strong>Filtro</strong>.</td>
</tr>
<tr class="even">
<td>Sito</td>
<td>Modificare il sito per il quale è visualizzata la struttura DBA. Il sito predefinito è il sito di magazzino predefinito dell'articolo finito.</td>
</tr>
<tr class="odd">
<td>Principio visualizzazione</td>
<td>Selezionare il principio visualizzazione della versione applicabile alla struttura DBA e al ciclo di lavorazione correnti:
<ul>
<li>Quando il principio è impostato su <strong>Attivo o Selezionato/Attivo</strong>, viene trovata la versione valida della DBA o del ciclo di lavorazione per questa data.</li>
<li>Se il principio di visualizzazione è impostato su <strong>Selezionato/Attivo selezionata l'opzione o</strong>, è possibile selezionare una versione DBA o inviare la versione facendo <strong>DBA</strong> &gt; <strong>Versioni DBA</strong> clic su e <strong>Ciclo di lavorazione</strong> &gt; <strong>Versioni cicli di lavorazione</strong>.</li>
</ul></td>
</tr>
<tr class="even">
<td>Data versione</td>
<td>Consente di immettere la data della versione per la DBA e il ciclo di lavorazione. La versione identifica quale versione di DBA viene utilizzata in una specifica data, determinata dalle date di versione specificate nell'impostazione della versione della DBA.</td>
</tr>
<tr class="odd">
<td>Da quantità</td>
<td>Consente di filtrare le versioni selezionandone una specifica da quantità. Se si imposta un valore, è possibile che vengano selezionate versioni differenti di DBA e di ciclo di lavorazione.</td>
</tr>
<tr class="even">
<td>Visualizza solo validi</td>
<td>Quando si seleziona la casella di controllo, nella struttura ad albero vengono visualizzate solo le righe DBA con date valide. Fare clic con il pulsante destro del mouse oppure fare doppio clic su una riga DBA per aprire la pagina <strong>Modifica riga DBA</strong> e vedere le date di validità della riga DBA.</td>
</tr>
</tbody>
</table>

Quando si utilizza Designer DBA per rivedere o modificare le DBA che sono costituite da uno o più livelli di voci fittizie, il ciclo di lavorazione associato all'articolo di livello superiore in genere estende la gerarchia completa DBA. Per semplificare la panoramica, è possibile bloccare il ciclo di lavorazione è bloccato di primo livello in l facendo clic su ** visualizzazione ** &gt; ** il ciclo di lavorazione di blocchi **. Per aprire il ciclo di lavorazione, fare clic su ** visualizzazione ** &gt; ** Sblocco del ciclo di lavorazione **.

## <a name="adding-and-editing-boms-and-bom-lines"></a>Aggiunta e modifica di DBA e di righe DBA
Utilizzare ** righe DBA o ** ** DBA ** funzioni per modificare le righe DBA o la DBA. Quando si seleziona un nodo nella struttura ad albero, il tipo di nodo determina quali funzioni sono disponibili.

| Funzione                            | descrizione                                                                                               | Tipo di nodo e condizioni                                                                                                                                                                                                                                                                       |
|-------------------------------------|-----------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Modifica &gt; delle righe DBA                 | Consente di aprire una finestra di dialogo in cui è possibile modificare gli attributi della riga DBA.                                             | Questa funzione è disponibile quando un nodo della riga DBA è selezionato.                                                                                                                                                                                                                                   |
| Eliminazione &gt; delle righe DBA               | Consente di eliminare una riga DBA dalla DBA selezionata.                                                                  | Questa funzione è disponibile quando un nodo della riga DBA è selezionato e la DBA non è bloccata per la modifica.                                                                                                                                                                                             |
| Le righe &gt; DBA aggiunte prima riga      | Consente di aprire una finestra di dialogo in cui è possibile selezionare una variante prodotto da includere prima della riga DBA selezionata.         | Questa funzione è disponibile quando un nodo della riga DBA è selezionato.                                                                                                                                                                                                                                   |
| Le righe &gt; DBA aggiunti al componente DBA | Consente di aprire una finestra di dialogo in cui è possibile selezionare una variante prodotto da includere alla fine della riga DBA selezionata.       | Questa funzione è disponibile quando il nodo selezionato dispone di una DBA selezionata. Se questa funzione non è disponibile, è possibile che manchi una versione DBA per la variante selezionata dell'articolo. In questo caso, è possibile fare clic su ** DBA ** &gt; ** creazione della versione ** creare la versione mancante per il nodo selezionato. |
| Le righe &gt; DBA aggiunti dopo la riga       | Consente di aprire una finestra di dialogo in cui è possibile selezionare una variante prodotto da includere dopo la riga DBA selezionata.          | Questa funzione è disponibile quando un nodo della riga DBA è selezionato.                                                                                                                                                                                                                                   |
| DBA &gt; creazione della versione             | Consente di creare una nuova versione DBA o una nuova DBA per la variante prodotto del nodo selezionato.                             | Questa funzione è disponibile quando il nodo della riga DBA selezionato è collegato a un articolo che ha un tipo di produzione **DBA** o **Formula**.                                                                                                                                                  |
| Calcolo DBA &gt;                | Consente di aprire una finestra di dialogo in cui è possibile eseguire il calcolo del costo e del prezzo di vendita per la variante prodotto selezionata. | Questa funzione è disponibile quando il nodo selezionato è correlato a una versione DBA.                                                                                                                                                                                                         |
| Verifica &gt; DBA                      | Consente di convalidare e verificare la DBA selezionata.                                                                      | Questa funzione è disponibile quando il nodo selezionato è correlato a una versione DBA.                                                                                                                                                                                                         |

## <a name="configuring-the-tree-view"></a>Configurazione della visualizzazione struttura ad albero
Fare clic su **Impostazione** per personalizzare le informazioni che vengono mostrate nella visualizzazione struttura ad albero di Designer DBA.

| Gruppo campi | Descrizione                                                                                                                                                  |
|-------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------|
| DBA         | Utilizzare le caselle di controllo per selezionare i criteri che vengono visualizzati nella struttura ad albero. I criteri selezionati vengono visualizzati nella parte inferiore di entrambe le schede di Designer DBA. |
| Ciclo di lavorazione       | Utilizzare le caselle di controllo per selezionare i criteri che vengono visualizzati per i cicli di lavorazione.                                                                                    |




