---
title: Unisci batch di magazzino
description: In questo articolo vengono fornite informazioni sul consolidamento di due o più batch di magazzino in un batch unito.
author: pjacobse
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventBatchJournalListPage, InventBatchJournalMerge
audience: Application User
ms.reviewer: kamaybac
ms.custom: 39782
ms.assetid: 07c5e98b-10fd-4f5c-b471-41d2150f47b0
ms.search.region: Global
ms.author: pjacobse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d43733455765bc8b69ce8595c46b00942ddac6b7
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5228589"
---
# <a name="merge-inventory-batches"></a>Unisci batch di magazzino

[!include [banner](../includes/banner.md)]

In questo articolo vengono fornite informazioni sul consolidamento di due o più batch di magazzino in un batch unito.

Quando i batch vengono uniti, i calcoli possono consentire di ottimizzare le caratteristiche e gli attributi batch nel batch unito. Dopo la selezione dei batch di origine, quello unito può essere rivisto e modificato prima della registrazione. È inoltre possibile trasferire l'unione batch in un giornale di registrazione magazzino per l'approvazione. Le scorte possono quindi essere prenotate o registrate direttamente dal giornale di registrazione magazzino. Quando si registra un batch unito, il magazzino viene regolato per i batch di origine e il batch unito.

## <a name="are-there-any-prerequisites"></a>Esistono altri prerequisiti?
Sì, sono disponibili alcune cose che è necessario impostare prima di utilizzare gli strumenti del batch di unione. Nella seguente tabella vengono illustrati i prerequisiti.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Pagina</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Nomi giornale di registrazione, Magazzino</td>
<td>È necessario creare un nome del giornale di registrazione di tipo DB utilizzato per impostazione predefinita quando si registrano le unioni batch nei giornali di registrazione magazzino. È facoltativo, ma consigliato, specificare che le prenotazioni vengano effettuate automaticamente quando l'unione batch viene trasferita nel giornale di registrazione magazzino. In caso contrario, c'è il rischio che venga apportata una modifica al magazzino disponibile dopo aver impostato i dettagli dell'unione batch e aver registrato il giornale di registrazione. Per abilitare le prenotazioni automatiche per il nome del giornale di registrazione, selezionare <strong>Automatico</strong> nel campo <strong><strong>Prenotazione</strong></strong>.</td>
</tr>
<tr class="even">
<td>Parametri di Gestione articoli e magazzino</td>
<td>È necessario specificare il nome del giornale di registrazione predefinito per il giornale di registrazione magazzino.</td>
</tr>
<tr class="odd">
<td>Prodotti rilasciati</td>
<td>Di seguito sono riportate le impostazioni consigliate per l'articolo:
<ul>
<li>Per generare automaticamente i numeri batch per i batch uniti, è necessario assegnare il prodotto rilasciato a un gruppo del numero batch. È inoltre possibile immettere un numero batch manualmente quando si crea un batch unito oppure selezionare un numero batch esistente. Se viene selezionato un numero batch esistente, assicurarsi che il batch selezionato non sia stato incluso in alcuna operazione di magazzino.</li>
<li>Se si utilizza la durata a scaffale o la data di consumo consigliata per il prodotto rilasciato, le date per un batch unito verranno calcolate in base alla selezione nel campo <strong>Calcolo data unione batch</strong>. Sono disponibili le seguenti opzioni:
<ul>
<li><strong>Prima possibile</strong>: il calcolo si basa sulla prima data specificata per un batch di origine selezionato per l'unione batch.</li>
<li><strong>Ultima possibile</strong>: il calcolo si basa sull'ultima data specificata per un batch di origine selezionato per l'unione batch.</li>
<li><strong>Manuale</strong>: non viene eseguito alcun calcolo. Se una data è la stessa in tutti i batch di origine, verrà suggerita una data. È possibile modificare tale data. Se una data non corrisponde ai batch di origine, è possibile immetterla manualmente.</li>
</ul></li>
</ul></td>
</tr>
<tr class="even">
<td>Gruppo numeri batch</td>
<td>Facoltativo: per generare un numero batch quando si crea un batch unito, è necessario assegnare un gruppo del numero batch al prodotto rilasciato. In alternativa, è possibile immettere un numero batch manualmente.</td>
</tr>
</tbody>
</table>

## <a name="when-might-i-want-to-merge-batches-of-inventory"></a>Quando si devono unire i batch dell'inventario?
Di seguito sono riportati alcuni scenari di esempio dove può essere utile unire i batch:

-   Sammy sta camminando in magazzino e nota che sono presenti più batch dello stesso articolo con quantità ridotte. Sa inoltre che arriveranno diverse nuove spedizioni, si rende conto che può liberare dello spazio unendo le quantità vecchie in un nuovo batch.
-   Sammy riceve l'inventario e desidera combinare il nuovo batch con uno già ricevuto per migliorare il valore dell'attributo batch del batch esistente. In tal modo si crea un nuovo batch.

## <a name="can-i-merge-batches-across-sites-and-legal-entities"></a>Posso unire i batch tra più siti e persone giuridiche?
No, è possibile unire solo i batch con le stesse dimensioni di immagazzinamento del sito e del magazzino in una persona giuridica. Tuttavia, è possibile specificare un'ubicazione diversa l'ID del pallet per il batch unito.

## <a name="can-i-merge-partial-quantities"></a>È possibile unire quantità parziali?
No, è possibile unire solo l'intera quantità di batch. La funzionalità di unione batch è una funzionalità di inventario, non di produzione.

## <a name="what-if-the-batches-have-different-batch-attribute-values"></a>Cosa accade se i batch hanno valori di attributo batch diversi?
Quando vengono selezionati i batch di origine per combinarli nel batch unito, Supply Chain Management verifica se tutti i batch hanno caratteristiche o valori di attributo. Quando un valore attributo è lo stesso, verrà suggerito un valore per il batch unito. È possibile modificare questo valore. I valori di attributo che non sono uguali vengono lasciati vuoti per il batch unito ed è possibile immettere tali valori manualmente. Se il tipo di attributo batch per il valore di attributo è un numero intero o una frazione e i valori non sono uguali per tutti i batch di origine, il valore verrà calcolato utilizzando un calcolo medio ponderato. Il valore calcolato viene arrotondato verso l'alto o verso il basso verso l'incremento più vicino. Se il valore è vuoto per un batch di origine, il batch e la relativa quantità non vengono inclusi nel calcolo. **Esempio** Nel seguente esempio viene illustrato un calcolo media ponderata per un batch unito. Due dei batch di origine hanno un valore vuoto per un tipo di attributo batch che è un numero intero. Il seguente attributo è assegnato ai batch di origine.

| Attributo | Minimo | Incremento | Massimo |
|-----------|---------|-----------|---------|
| Scala     | 3       | 3         | 30      |

I batch di origine hanno i seguenti valori di attributi per l'attributo batch **Scala**.

| Lotto | Quantità | Attributo | Valore attributo |
|-------|----------|-----------|-----------------|
| B1    | 10       | Scala     | Vuoto           |
| B2    | 15       | Scala     | 15              |
| B3    | 20       | Scala     | 20              |
| B4    | 25       | Scala     | Vuoto           |
| B5    | 30       | Scala     | 25              |

Quando si aggiungono tali batch come batch di origine, al batch unito vengono assegnati i seguenti valori.

| Lotto | Quantità | Attributo | Valore attributo |
|-------|----------|-----------|-----------------|
| B6    | 100      | Scala     | 21              |

I valori e le quantità per i batch B1 e B4 non sono inclusi nel calcolo della media ponderata. Di conseguenza, il valore per il batch unito viene calcolato come indicato di seguito.

| Valore | Quantità (peso)                              | Peso relativo | Peso relativo x Valore                                               |
|-------|------------------------------------------------|-----------------|-----------------------------------------------------------------------|
| 15    | 15                                             | 0.230769231     | 3.461538462                                                           |
| 20    | 20                                             | 0.307692308     | 6.153846154                                                           |
| 25    | 30                                             | 0.461538462     | 11.53846154                                                           |
|       | **Totale:** 65, che corrisponde alla somma dei pesi |                 | **Totale:** 21,5384615, arrotondato a 21 (l'incremento più vicino). |

## <a name="what-if-the-batches-have-different-batch-dates"></a>Cosa accade se i batch hanno date batch diverse?
Se i batch hanno date batch diverse, alcune date vengono calcolate in base ai valori del gruppo **Date batch** nella scheda dettaglio **Batch unito** della pagina **Unione batch**. Il sistema calcola i valori per i campi nel gruppo **Date batch**. Questi valori includono la data di produzione, la data di scadenza, la data di durata a scaffale e la data di consumo consigliata. Le date vengono calcolate in base alle impostazioni per l'articolo nel gruppo di campi **Dati articolo** della pagina **Dettagli prodotto rilasciato**. È possibile modificare i valori o inserirli manualmente. Per tutte le altre date, non viene effettuato alcun calcolo. Lo stesso principio viene utilizzato per i valori degli attributi batch. Se una data è la stessa per tutti i batch di origine, tale data verrà suggerita per il batch unito. Se la data non è la stessa per tutti i batch di origine, la data è vuota nel batch unito ed è possibile immetterla manualmente.

## <a name="what-if-the-dimensions-are-different-on-the-batches-that-i-want-to-merge"></a>Cosa accade se le dimensioni sono diverse nei batch che desidero unire?
Di seguito viene indicato come vengono gestite le dimensioni prodotto, le dimensioni di tracciabilità e le dimensioni di immagazzinamento:

-   **Dimensioni prodotto**: tutte le dimensioni prodotto per l'articolo selezionato devono essere uguali. Non è possibile unire i batch tra le dimensioni prodotto.
-   **Dimensioni di tracciabilità**: un nuovo numero batch viene generato automaticamente se viene specificato un gruppo del numero batch per l'articolo. Se un gruppo del numero batch non viene assegnato a un articolo, è possibile selezionare un batch esistente o immettere il numero manualmente. I numeri di serie vengono trasferiti dal batch di origine alle righe del giornale di registrazione magazzino per il batch unito.
-   **Dimensioni di immagazzinamento**: le dimensioni di immagazzinamento di sito e magazzino devono essere uguali per tutti batch di origine e il batch unito. Tuttavia, è possibile specificare una nuova ubicazione e l'ID del pallet per il batch unito.

## <a name="how-does-posting-work"></a>Come funziona la registrazione?
La registrazione funziona in due modi, a seconda che si utilizzi un processo di approvazione per giornali di registrazione. È possibile utilizzare le azioni **Trasferisci nel giornale di registrazione** e **Registra l'unione batch** per trasferire l'unione batch in un giornale di registrazione in cui possa essere verificata e registrata oppure è possibile registrare direttamente l'unione batch. La differenza principale tra le due azioni è che il trasferimento in un giornale di registrazione non registra l'unione batch. Entrambe le azioni creeranno un nuovo batch se quello esistente non è stato selezionato, aggiorneranno tutti i dettagli del batch e i valori degli attributi e creeranno un giornale di registrazione magazzino.

-   **Trasferisci nel giornale di registrazione**: trasferisce i dettagli di unione del batch in un nuovo giornale di registrazione magazzino. Se sono state impostate prenotazioni automatiche, le quantità nei batch di origine vengono prenotate. I dettagli dell'unione batch non possono essere modificati. Per modificare l'unione batch, è necessario eliminare il giornale di registrazione. Il giornale di registrazione può essere utilizzato come attività che un altro dipendente deve eseguire in un secondo momento. La prenotazione della quantità batch nella riga del giornale di registrazione è protetta. Questa allocazione consente a un responsabile dei controlli di qualità o a un responsabile del magazzino di creare attività per sé o per i propri dipendenti.
-   **Registra l'unione batch**: registra direttamente l'unione batch. Questa azione può essere eseguita dopo l'unione fisica.

È possibile approvare il giornale di registrazione magazzino per l'unione batch dalla pagina elenco **Tutte le unioni batch**. Fare clic su **Giornale di registrazione** &gt; **Registra**. Dopo aver registrato un giornale di registrazione, non è possibile modificare i dettagli nel batch unito. Dopo aver trasferito un'unione batch in un giornale di registrazione magazzino, è possibile modificare i dettagli solo se il giornale di registrazione viene eliminato.

## <a name="after-i-merged-a-catchweight-item-why-cant-i-see-the-catchweight-information-in-the-inventory-journal"></a>Perché non riesco a visualizzare le informazioni sul peso variabile nel giornale di registrazione magazzino dopo aver unito un articolo a peso variabile?
È possibile unire i batch degli articoli a peso variabile come tutti gli altri articoli. Tuttavia, le informazioni sul peso variabile non vengono visualizzate nel giornale di registrazione magazzino. Si consiglia di verificare le informazioni sul peso variabile prima di trasferire l'unione batch nel giornale di registrazione magazzino.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]